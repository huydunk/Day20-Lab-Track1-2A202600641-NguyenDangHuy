# 07 — Measurement Ladder

> Bài 4 · §11. Đặt các metric đã chọn vào ladder. **Không cần dùng tất cả** — chỉ chọn metric trả
> lời được câu hỏi của sản phẩm.

## Ladder

```
Marketing / Traffic
  ↓
Visitor
  ↓
Activation
  ↓
Core Action
  ↓
Retention
  ↓
Revenue
```

## Chọn metric theo nhóm (đánh dấu metric nhóm sẽ dùng)

### Usage / Active
- [x] Active user
- [ ] DAU — ❌ nhịp không daily
- [ ] WAU — ❌ nhịp không weekly
- [x] MAU

### Activation & Retention
- [x] Activation
- [x] Activation Rate
- [x] Time to Value
- [x] Retention
- [ ] D1 / D7 / D30 Retention — ❌ không làm thước đo chính (use case 5–8 chuyến/năm)
- [x] Cohort Retention — monthly cohort **+ trip-to-trip (120 ngày)**
- [x] Churn

### Engagement & Stickiness
- [x] Engagement
- [ ] Stickiness: DAU/MAU — ❌ vô nghĩa ở nhịp thấp
- [ ] DAU/WAU — ❌
- [ ] WAU/MAU — ❌
- [ ] Session Length — (tuỳ chọn, phụ)
- [x] Frequency — số chuyến/năm
- [ ] Số session / user / tuần — ❌
- [ ] Time spent / user — (tuỳ chọn, phụ)

### Business
- [x] CAC
- [x] LTV
- [ ] Payback Period — (tuỳ chọn)
- [x] Revenue — hoa hồng affiliate booking

## Metric nhóm chọn + lý do

| Tầng ladder | Metric đã chọn | Vì sao chọn (câu hỏi nó trả lời) |
|---|---|---|
| Activation | Activation Rate · Time to Value | Bao nhiêu % user đạt first value (chấp nhận lịch) và nhanh thế nào? |
| Core Action | Số `itinerary_accepted` · **accepted-and-used** | User có thực sự nhận value (chấp nhận & dùng lịch) không? |
| Retention | Trip-to-trip (120 ngày) · monthly cohort · Churn | User có quay lại lập/chấp nhận chuyến kế tiếp không? |
| Usage / Active | Active user (usage-inclusive 30 ngày) · MAU | Còn bao nhiêu user thật sự dùng trong tháng? |
| Engagement | Engagement · Frequency (chuyến/năm) | Mức & nhịp dùng có khớp nhịp tự nhiên không? |
| Revenue / Business | Affiliate commission · LTV · CAC | Value có chuyển thành doanh thu bền vững không? |

> **Nối lên North Star:** tầng **Core Action → Retention** hội tụ vào North Star Metric
> *"số lịch trình được chấp nhận & dùng trong chuyến / tháng"* — xem `08-north-star.md`.
