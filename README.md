# Day 20 Lab — Retention, Engagement & Habit Loop (Track 1)

Tiếp tục prototype **Ngày 18** (AI Travel Planner — "Lộ Trình AI"), áp dụng kiến thức Ngày 19 để đi
từ use case & hành vi tự nhiên của người dùng → core action → retention metric → onboarding tối ưu →
habit loop → tracking.

- **Sản phẩm:** AI Travel Planner — tạo & điều chỉnh lịch trình một chuyến đi.
- **Persona:** khách du lịch tự túc cần lịch trình thực tế cho chuyến đi ngắn (vd: Đà Nẵng 3 ngày).
- **Mã HV / Tên:** 2A202600641 — Nguyễn Đăng Huy.

## Chạy thử prototype
Mở `index.html` bằng trình duyệt (double-click). Không cần cài đặt, không cần API/model thật.
Có thể publish bằng **GitHub Pages** để lấy "liên kết prototype" nộp bài.

## Cấu trúc repo

```
index.html                 # Prototype — screens 01–04 (Day 18) + screen 05 (Day 20: onboarding tối ưu)
docs/
  design-rationale.md      # Rationale Day 18 (giữ nguyên)
  00-current-state.md      # Audit prototype Day 18 / current state
  01-retention-canvas.md   # Customer Retention Canvas — Use Case
  02-core-action-active-user.md
  03-frequency-retention-metric.md
  04-onboarding-audit.md   # Friction audit (Keep/Remove/Delay/Simplify)
  05-onboarding-redesign.md
  06-before-after-recovery.md
  07-measurement-ladder.md
  08-north-star.md
  09-nature-vs-nurture.md
  10-hook-review.md        # Hook Model
  11-metric-tracking.md    # Metric & event tracking requirement
  12-demo-path.md          # Kịch bản demo 8 phút
```

> Các file `docs/00`–`12` hiện là **template** (câu hỏi + bảng trống) để nhóm điền khi làm lab.

## Phân biệt phần Ngày 18 vs phần bổ sung Day 20

| | Ngày 18 (giữ nguyên) | Bổ sung Day 20 |
|---|---|---|
| Prototype | `index.html` screens **01–04** | `index.html` screen **05** (Onboarding tối ưu ✦, có TODO scaffold) |
| Tài liệu | `docs/design-rationale.md` | `docs/00`–`12` |

## Đầu ra bắt buộc (map tới docs)
1. Customer Retention Canvas — `01` · 2. Core Action / Active User / Retention Metric — `02`,`03` ·
3. Onboarding → First Core Action (audit + tối ưu) — `04`,`05`,`06` ·
4. Measurement Ladder & North Star — `07`,`08` · 5. Nature vs Nurture — `09` ·
6. Hook Model — `10` · 7. Metric Tracking Requirement — `11` · 8. Chỉnh sửa prototype — `index.html` screen 05.

## Nộp bài
Nộp **một liên kết duy nhất** (đã cấp quyền xem) tới prototype hoặc tệp trình bày — ưu tiên link
GitHub Pages của `index.html`. Phân biệt rõ phần Ngày 18 và phần bổ sung Day 20. Demo ≤ 8 phút.

---

## Checklist trước khi nộp (§23)

**Use case & natural behavior**
- [ ] Chỉ tập trung vào một use case chính
- [ ] Có The Problem, Persona, Anti-persona, Why và Alternative
- [ ] Frequency được suy ra từ hành vi thật và alternative

**Core action & metric**
- [ ] Core action cho thấy user nhận được value
- [ ] Active user có định nghĩa và ngưỡng rõ
- [ ] Retention metric phù hợp natural frequency
- [ ] Không copy DAU/WAU/MAU/D7 từ sản phẩm khác

**Onboarding → First Core Action**
- [ ] Có current-state journey
- [ ] Mỗi bước được audit theo Keep/Remove/Delay/Simplify
- [ ] Có redesigned journey dẫn tới first core action
- [ ] Có activation, Time to First Core Action, TTV và aha moment
- [ ] Đã chỉ ra bước thừa / friction trước core action
- [ ] Có Before/After comparison
- [ ] Giữ / cải thiện recovery flow Ngày 18

**Measurement**
- [ ] Có Measurement Ladder
- [ ] Có một North Star Metric và tối đa ba Input Metrics
- [ ] Phân biệt leading và lagging indicator
- [ ] Có một trade-off cần theo dõi

**Nature, Nurture & Hook**
- [ ] Phân biệt natural frequency với nurture
- [ ] Nurture không quá dày hoặc quá thưa
- [ ] Hook Review có Trigger, Action, Variable Reward và Investment
- [ ] Đã xác định rào cản làm action khó thực hiện
- [ ] Đã kiểm tra habit có thực sự có lợi cho user
- [ ] Không ép habit nếu frequency & utility không phù hợp

**Tracking**
- [ ] Metric có định nghĩa, công thức, window và segment
- [ ] Event map trực tiếp tới metric
- [ ] Event được gắn lên onboarding/core action flow
- [ ] Có ít nhất bốn tiêu chí nghiệm thu

**Submission**
- [ ] Chỉ nộp một liên kết đã cấp quyền xem
- [ ] Phân biệt được phần Ngày 18 và phần bổ sung Day 20
- [ ] Có demo path
- [ ] Demo không quá 8 phút
