# Day 20 Lab — Retention, Engagement & Habit Loop (Track 1)

> 🔗 **Liên kết nộp bài (prototype):** https://huydunk.github.io/Day20-Lab-Track1-2A202600641-NguyenDangHuy/

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
Nộp **một liên kết duy nhất** (đã cấp quyền xem):

**https://huydunk.github.io/Day20-Lab-Track1-2A202600641-NguyenDangHuy/**

Link này là GitHub Pages của `index.html`, tự cập nhật mỗi lần push lên `main`. Phân biệt rõ phần
Ngày 18 và phần bổ sung Day 20. Demo ≤ 8 phút.

---

## Checklist trước khi nộp (§23)

**Use case & natural behavior**
- [x] Chỉ tập trung vào một use case chính — lập & điều chỉnh lịch chuyến ngắn (`01`)
- [x] Có The Problem, Persona, Anti-persona, Why và Alternative (`01`)
- [x] Frequency được suy ra từ hành vi thật và alternative — 5–8 chuyến/năm (`01`)

**Core action & metric**
- [x] Core action cho thấy user nhận được value — chấp nhận lịch (`02`)
- [x] Active user có định nghĩa và ngưỡng rõ — ≥1 hành vi giá trị / 30 ngày (`02`)
- [x] Retention metric phù hợp natural frequency — trip-to-trip @30/60/90 (`03`)
- [x] Không copy DAU/WAU/MAU/D7 từ sản phẩm khác — loại daily làm chính (`03`,`07`)

**Onboarding → First Core Action**
- [x] Có current-state journey (`00`)
- [x] Mỗi bước được audit theo Keep/Remove/Delay/Simplify (`04`)
- [x] Có redesigned journey dẫn tới first core action — screen 05 (`05`)
- [x] Có activation, Time to First Core Action, TTV và aha moment (`05`)
- [x] Đã chỉ ra bước thừa / friction trước core action (`04`,`06`)
- [x] Có Before/After comparison (`06`)
- [x] Giữ / cải thiện recovery flow Ngày 18 — T6/T7 reachable (`06`)

**Measurement**
- [x] Có Measurement Ladder (`07`)
- [x] Có một North Star Metric và tối đa ba Input Metrics (`08`)
- [x] Phân biệt leading và lagging indicator (`08`)
- [x] Có một trade-off cần theo dõi — affiliate push vs trust (`08`)

**Nature, Nurture & Hook**
- [x] Phân biệt natural frequency với nurture (`09`)
- [x] Nurture không quá dày hoặc quá thưa (`09`)
- [x] Hook Review có Trigger, Action, Variable Reward và Investment (`10`)
- [x] Đã xác định rào cản làm action khó thực hiện — Fogg (`10`)
- [x] Đã kiểm tra habit có thực sự có lợi cho user (`10`)
- [x] Không ép habit nếu frequency & utility không phù hợp — Hook chỉ in-trip (`10`)

**Tracking**
- [x] Metric có định nghĩa, công thức, window và segment (`11`)
- [x] Event map trực tiếp tới metric (`11`)
- [x] Event được gắn lên onboarding/core action flow — screen 05 markers (`11`)
- [x] Có ít nhất bốn tiêu chí nghiệm thu — 6 tiêu chí (`11`)

**Submission**
- [x] Chỉ nộp một liên kết đã cấp quyền xem — GitHub Pages (public)
- [x] Phân biệt được phần Ngày 18 và phần bổ sung Day 20 — screens 01–04 vs 05; `design-rationale` vs `00–12`
- [x] Có demo path (`12`)
- [ ] Demo không quá 8 phút — *kịch bản thiết kế trong 8'; nhóm canh giờ khi demo thật*
