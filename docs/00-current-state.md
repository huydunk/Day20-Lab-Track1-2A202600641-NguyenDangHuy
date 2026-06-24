# 00 — Prototype Ngày 18 / Current State

> Bài 3 · §9 — Audit prototype Ngày 18. Đây là **điểm xuất phát**: tóm tắt sản phẩm Day 18 và
> chụp lại hiện trạng onboarding TRƯỚC khi tối ưu. Prototype: `../index.html` (screens 01–04).
> Rationale Day 18 đầy đủ: `design-rationale.md`.

## Tóm tắt sản phẩm (carry-over từ Day 18)

| Mục | Nội dung |
|---|---|
| Sản phẩm | AI Travel Planner — "Lộ Trình AI" |
| Scenario / lát cắt | AI **tạo & điều chỉnh lịch trình một chuyến đi** (Onboarding → During → Review → Failure/Recovery). |
| Persona đã chọn | Khách du lịch tự túc **18–55 tuổi, đi theo cặp đôi/nhóm bạn**, chuyến ngắn 2–5 ngày (xem `01-retention-canvas.md`). |
| Use case chính sẽ phân tích sâu | **Lập & điều chỉnh lịch trình cho một chuyến đi ngắn** (chỉ MỘT use case này). |

## Audit prototype Ngày 18 (đánh dấu trên screens 01–04)

1. User bắt đầu onboarding ở đâu? **Screen 01** — 3 bước: (1) kỳ vọng "AI CÓ THỂ / KHÔNG TỰ LÀM", (2) dữ liệu & quyền (Lịch, Vị trí — mặc định **TẮT**), (3) chọn điểm bắt đầu (mơ hồ / có điểm đến / nhập sẵn).
2. Phải đi qua những bước nào? Onboarding 3 bước → **screen 02**: AI hỏi **2 câu** (phong cách · đi với ai) → AI dựng **lịch nháp**.
3. First core action xảy ra ở đâu? **Khi user chấp nhận lịch nháp** — bấm nút **"Dùng lịch này"** (event `itinerary_accepted`). ⚠️ Nút này **chưa có** trong prototype Day 18 → sẽ **thêm vào screen 05** (redesign). Trước đó, **"AI tạo lịch nháp đầu tiên"** (`draft_generated`, cuối screen 02 `#genDone`) là **mốc activation** (leading milestone), **không phải** core action.
4. Aha moment xảy ra ở đâu? Khi user **có trong tay một lịch khả thi, đáng tin mà mình đã chốt** — sau khi review nháp thực tế (nhãn Dữ kiện/Suy luận, T3 explainability) và thấy AI tự phát hiện & sửa lỗi (T6/T7) → "cái này dùng được & mình kiểm soát được". Thường trùng hoặc ngay sau core action (accept).
5. Time to First Core Action hiện dài bao lâu? Tạo nháp (activation) ~**60–90s**; **chấp nhận nháp (first core action) ~2–4 phút** (gồm thời gian review/điều chỉnh). *(ước tính từ prototype, chưa có tracking)*
6. Time to Value hiện dài bao lâu? ≈ **tới khi chấp nhận lịch** (~2–4 phút) — vì aha ≈ "đã có lịch chốt đáng tin". *(ước tính từ prototype)*
7. Bước nào không cần thiết trước core action? **Ứng viên Delay:** 2 toggle quyền (Lịch, Vị trí) ở bước onboarding 2 — không cần để tạo nháp đầu tiên, có thể hỏi sau first value. `[DECIDE: xác nhận ở doc 04]`
8. Recovery flow nào của Ngày 18 được giữ lại? **T6** (lịch quá dày → phát hiện → sửa → before/after + ghi nhớ) và **T7** (dữ liệu lỗi thời → cảnh báo + phương án thay thế).

## Current-State Journey (vẽ lại flow hiện tại)

```
Entry point — mở tính năng (screen 01)
  ↓
Onboarding step 1 — Kỳ vọng: AI CÓ THỂ / KHÔNG TỰ LÀM
  ↓
Onboarding step 2 — Dữ liệu & quyền (Lịch, Vị trí — mặc định TẮT)   ← ứng viên Delay
  ↓
Onboarding step 3 — Chọn điểm bắt đầu (mơ hồ / có điểm đến / nhập sẵn)
  ↓
Setup — AI hỏi 2 câu: phong cách · đi với ai (screen 02)
  ↓
Activation — AI tạo lịch trình NHÁP đầu tiên (#genDone · event: draft_generated)
  ↓
Review & điều chỉnh nháp (screen 03 — T3 trọng số khách sạn, sửa điểm…)
  ↓
★ First core action — user bấm "Dùng lịch này" (event: itinerary_accepted)   ← CẦN THÊM ở screen 05
  ↓
Aha moment / first value — đã có một lịch khả thi, đáng tin & mình đã chốt
```

## Bảng Current State

| Chỉ số | Current state |
|---|---|
| Số bước tới first core action | ~**7–8** (3 onboarding + điểm bắt đầu + 2 câu hỏi → xem nháp → review → bấm "Dùng lịch này") `[DECIDE: cách đếm]` |
| Số trường thông tin phải nhập | ~**2 lựa chọn bắt buộc** (phong cách, đi với ai — chọn chip, có thể bỏ qua câu 2); điểm đến nhập ở entry point |
| Số permission phải cấp | **0 bắt buộc** — 2 quyền tuỳ chọn (Lịch, Vị trí), mặc định TẮT, có thể bỏ qua |
| Time to First Core Action (ước tính) | nháp ~60–90s (activation) → **chấp nhận ~2–4 phút** (first core action) *(ước tính)* |
| Time to Value (ước tính) | ≈ tới khi chấp nhận lịch, ~**2–4 phút** *(ước tính)* |
| Điểm drop-off có khả năng cao nhất | **Bước onboarding 2 (quyền)** hoặc **2 câu hỏi setup** — user phải làm vài thao tác *trước khi* thấy bất kỳ value nào. `[DECIDE: xác nhận]` |

> _Nếu chưa có dữ liệu tracking: ghi rõ đây là **ước tính từ prototype**._
