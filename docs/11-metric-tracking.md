# 11 — Metric Tracking Requirement

> Bài 6 · §16–19. **Không tạo metric mới** — chuyển các metric đã chọn ở Bài 2 (`03`) và Bài 4
> (`07`, `08`) thành yêu cầu tracking. Chỉ tạo event **cần thiết** để tính các metric đó.

## 16. Bảng định nghĩa metric

| Trường | Metric 1 | Metric 2 | Metric 3 |
|---|---|---|---|
| Tên metric (đúng tên đã chọn) | **Activation Rate** | **Trip-to-trip Retention** (đường cong @30/60/90 ngày) | **North Star — Accepted-and-used / tháng** |
| Câu hỏi cần trả lời | Bao nhiêu % user đạt first value (chấp nhận lịch)? | User có quay lại lập/chấp nhận chuyến kế tiếp không, và nhanh thế nào? | Sản phẩm đang tạo ra bao nhiêu value thật mỗi tháng? |
| Định nghĩa (ai/hành vi nào được tính) | User vào onboarding **và** có ≥1 `itinerary_accepted` | User đã accept ≥1 lịch (cohort) **và** accept một lịch cho **chuyến khác** trong 30/60/90 ngày | Lịch vừa được `itinerary_accepted` vừa có ≥1 `itinerary_used` trong chuyến |
| Công thức (tử/mẫu/cách tổng hợp) | users có `itinerary_accepted` ÷ users có `onboarding_started` | users accept chuyến kế tiếp ≤ N ngày ÷ users trong cohort (N = 30, 60, 90) | COUNT(distinct `itinerary_id` thoả điều kiện) / tháng |
| Khoảng thời gian (daily/weekly/monthly/window) | Theo cohort onboarding (vd tuần/tháng) | Cohort theo lịch đầu; mốc 30/60/90 ngày | Monthly |
| Segment (persona/use case áp dụng) | Khách tự túc 18–55, cặp đôi/nhóm bạn; lập lịch chuyến ngắn | nt | nt |
| Event cần có | `onboarding_started`, `itinerary_accepted` | `itinerary_accepted` (+ `trip_id` để phân biệt chuyến) | `itinerary_accepted`, `itinerary_used` |

## 17. Bảng yêu cầu tracking event

> Chỉ tạo event cần thiết để tính các metric ở §16. Identity chung: `user_id` (+ `itinerary_id`,
> `trip_id` khi liên quan). Bảng theo **mỗi event một dòng** cho dễ đọc.

| Event name | Được ghi khi nào? (hành vi thật vừa xảy ra) | Properties | Metric sử dụng | Tránh ghi trùng |
|---|---|---|---|---|
| `onboarding_started` | User mở luồng onboarding (screen 05, lần đầu của phiên) | `user_id`, `entry_type` (đà nẵng/gợi ý), `ts` | Activation Rate (mẫu số) | 1 lần / phiên onboarding |
| `setup_completed` | User chọn xong **phong cách** (câu setup tối thiểu) | `user_id`, `style` | Funnel onboarding | 1 lần / phiên; chọn lại = cập nhật, không tạo event mới |
| `draft_generated` | AI dựng xong lịch nháp đầu tiên (activation milestone) | `user_id`, `itinerary_id`, `style` | Draft→Accept conversion (mẫu số) | 1 lần / `itinerary_id` lần tạo đầu |
| `itinerary_accepted` ★ | User bấm **"Dùng lịch này"** trên lịch có ≥1 ngày (CORE ACTION) | `user_id`, `itinerary_id`, `trip_id`, `ts` | Activation Rate, Draft→Accept, Trip-to-trip, North Star | **1 lần / `itinerary_id`** (sửa rồi accept lại không tính lại) |
| `itinerary_used` | User mở & dùng một lịch **đã accept** khi đang trong chuyến (xem/điều chỉnh lịch hôm nay) | `user_id`, `itinerary_id`, `trip_id`, `day` | North Star (accepted-and-used), in-trip engagement | **1 lần / `itinerary_id` / ngày** |
| `permission_prompted_deferred` | Hiển thị xin quyền (Lịch/Vị trí) **sau** first value | `user_id`, `permission`, `granted` (bool) | Tỉ lệ cấp quyền (phụ) | 1 lần / loại quyền / phiên |

## 18. Gắn event lên flow

> Đối chiếu với marker `[event: ...]` trong screen 05 của `../index.html`.

```
Onboarding bắt đầu (screen 05 · #r5s1)
  ↓
[event: onboarding_started]
  ↓
Chọn phong cách (minimum setup · #r5s2)
  ↓
[event: setup_completed]
  ↓
AI dựng lịch nháp (activation · #r5draft)
  ↓
[event: draft_generated]
  ↓
★ First core action — bấm "Dùng lịch này" (#r5acceptBtn)
  ↓
[event: itinerary_accepted]
  ↓
Sau accept: hỏi quyền (deferred) + dùng lịch trong chuyến
  ↓
[event: permission_prompted_deferred] · [event: itinerary_used]
```

## 19. Tiêu chí nghiệm thu tracking (viết ≥ 4)

- [x] Event chỉ được ghi khi hành vi **thực sự** xảy ra — vd `itinerary_accepted` chỉ khi bấm "Dùng lịch này", không phải khi chỉ xem nháp.
- [x] Refresh / retry / autosave **không** làm dữ liệu ghi trùng — dedupe theo khoá: `itinerary_accepted` 1×/`itinerary_id`; `itinerary_used` 1×/`itinerary_id`/ngày.
- [x] Event có đủ identity & properties cần thiết — luôn có `user_id` (+ `itinerary_id`/`trip_id` khi cần) để tính cohort & segment.
- [x] Timestamp & timezone nhất quán — lưu UTC + **giờ địa phương của chuyến** (để "lịch hôm nay"/ngày chuyến đúng).
- [x] Event dùng được để tính metric **đúng công thức** — mỗi metric ở §16 map tới đúng event ở §17.
- [x] Không thu thập dữ liệu cá nhân không cần thiết — chỉ thuộc tính phục vụ metric; vị trí/lịch chỉ khi user **đã cấp quyền** (deferred).

> _Ví dụ lab: chỉ ghi `task_completed` khi nhiệm vụ chuyển từ chưa hoàn thành → hoàn thành; tải lại
> trang không tạo thêm event cho cùng lần chuyển trạng thái._
