# 08 — North Star Metric & Input Metrics

> Bài 4 · §12. North Star Metric = chỉ số cốt lõi phản ánh **value chính** sản phẩm tạo ra.

North Star cần: thể hiện value · đại diện vision/strategy · là **leading indicator** · không phải
vanity metric · hành động được · dễ hiểu · đo được.

## Nộp

| Mục | Câu trả lời |
|---|---|
| **North Star Metric** (1) | **Số lịch trình được CHẤP NHẬN & SỬ DỤNG trong chuyến, mỗi tháng.** Đo từ `itinerary_accepted` + event "dùng lịch trong chuyến" (in-trip usage). Đạt tiêu chí NSM: thể hiện value · leading · **không vanity** (accept mà không dùng thì không tính) · actionable · dễ hiểu · đo được. |
| **Input Metric 1** | **Activation Rate** — % `onboarding_started → itinerary_accepted` (nhiều user đạt first value). |
| **Input Metric 2** | **Draft→Accept conversion** — % `draft_generated → itinerary_accepted` (chất lượng nháp đủ tốt để chốt). |
| **Input Metric 3** _(tối đa 3)_ | **Trip-to-trip retention (120 ngày)** — % user quay lại lập/chấp nhận chuyến kế tiếp. |
| Kết quả business / customer value (trung–dài hạn) | Doanh thu **affiliate booking** + tăng trưởng do **word-of-mouth/referral** + **niềm tin & sự hài lòng** của user. |
| Đâu là **leading** indicator? | **North Star** + 3 input metric (báo trước value & tăng trưởng tương lai). |
| Đâu là **lagging** indicator? | **Affiliate revenue, churn, cohort retention trưởng thành** (phản ánh kết quả sau khi đã xảy ra). |

> **Vì sao 3 input nhân nhau ra NSM:** (Activation Rate × Draft→Accept) quyết định **bao nhiêu lịch
> được chấp nhận**; Trip-to-trip retention quyết định **tần suất quay lại** → cùng nhau đẩy tổng số
> "lịch được chấp nhận & dùng / tháng".

## Quan hệ

```
The Work
  (cải thiện onboarding, chất lượng nháp, recovery, hữu ích in-trip)
  ↓
Input Metrics
  (Activation Rate · Draft→Accept · Trip-to-trip retention)
  ↓
North Star Metric
  (lịch được chấp nhận & dùng trong chuyến / tháng)
  ↓
Mid/Long-term Business Results & Customer Value
  (affiliate revenue · word-of-mouth growth · trust & satisfaction)
```

## Trade-off

> Giải thích **một** trade-off có thể xảy ra.

**Đẩy mạnh affiliate booking / nudge đặt phòng để tăng doanh thu ngắn hạn** có thể khiến gợi ý trở
nên **kém khách quan** (ưu tiên đối tác trả hoa hồng cao hơn nhu cầu thật của user) → làm giảm
**chất lượng lịch**, kéo **accepted-and-used (NSM)** và **trust** đi xuống về dài hạn.

→ **Lựa chọn:** tối ưu cho **NSM (value thật)** thay vì ép booking; giữ minh bạch xếp hạng & "khóa
thanh toán / Don't Act" như Day 18. Hoa hồng là **kết quả** của value, không phải đòn bẩy ép buộc.
