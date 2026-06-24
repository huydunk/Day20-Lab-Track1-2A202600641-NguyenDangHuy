# 11 — Metric Tracking Requirement

> Bài 6 · §16–19. **Không tạo metric mới** — chuyển các metric đã chọn ở Bài 2 (`03`) và Bài 4
> (`07`, `08`) thành yêu cầu tracking. Chỉ tạo event **cần thiết** để tính các metric đó.

## 16. Bảng định nghĩa metric

| Trường | Metric 1 | Metric 2 | Metric 3 |
|---|---|---|---|
| Tên metric (đúng tên đã chọn) | | | |
| Câu hỏi cần trả lời | | | |
| Định nghĩa (ai/hành vi nào được tính) | | | |
| Công thức (tử/mẫu/cách tổng hợp) | | | |
| Khoảng thời gian (daily/weekly/monthly/window) | | | |
| Segment (persona/use case áp dụng) | | | |
| Event cần có | | | |

## 17. Bảng yêu cầu tracking event

| Trường | Event 1 | Event 2 | Event 3 |
|---|---|---|---|
| Event name | | | |
| Được ghi khi nào? (trạng thái/hành vi vừa thực sự xảy ra) | | | |
| User identity (user_id / account_id / …) | | | |
| Properties (dữ liệu cần để tính metric / phân tích segment) | | | |
| Metric sử dụng event | | | |
| Tránh ghi trùng (refresh/retry/autosave xử lý thế nào) | | | |

## 18. Gắn event lên flow

> Đối chiếu với marker `[event: ...]` trong screen 05 của `../index.html`.

```
Onboarding bắt đầu
  ↓
[event: ____]
  ↓
User hoàn thành bước cần thiết
  ↓
[event: ____]
  ↓
First core action
  ↓
[event: ____]
  ↓
Activation / Aha moment
  ↓
[event: ____]
```

## 19. Tiêu chí nghiệm thu tracking (viết ≥ 4)

- [ ] Event chỉ được ghi khi hành vi **thực sự** xảy ra
- [ ] Refresh / retry / autosave **không** làm dữ liệu ghi trùng
- [ ] Event có đủ identity & properties cần thiết
- [ ] Timestamp & timezone nhất quán
- [ ] Event dùng được để tính metric **đúng công thức**
- [ ] Không thu thập dữ liệu cá nhân không cần thiết

> _Ví dụ lab: chỉ ghi `task_completed` khi nhiệm vụ chuyển từ chưa hoàn thành → hoàn thành; tải lại
> trang không tạo thêm event cho cùng lần chuyển trạng thái._
