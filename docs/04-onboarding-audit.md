# 04 — Onboarding Audit (Friction)

> Bài 3 · §9. Audit flow onboarding HIỆN TẠI (Day 18, screens 01–04), chỉ ra friction trước khi
> redesign ở `05-onboarding-redesign.md`. Đánh dấu **mỗi bước** bằng một nhãn.

## Friction Audit — gắn nhãn từng bước

| Nhãn | Ý nghĩa |
|---|---|
| **Keep** | Bắt buộc trước first core action |
| **Remove** | Không cần thiết và chưa tạo value |
| **Delay** | Cần cho sản phẩm nhưng có thể hỏi sau first core action |
| **Simplify** | Cần thiết nhưng đang quá khó / quá dài |

| # | Bước hiện tại (Day 18) | Nhãn (Keep/Remove/Delay/Simplify) | Lý do |
|---|---|---|---|
| 1 | Onboarding 1 — Kỳ vọng "AI CÓ THỂ / KHÔNG TỰ LÀM" (screen 01, ob1) | **Simplify** | Quan trọng nhưng đang là 2 callout dài trước khi user được thử → cô đọng còn 1 dòng value + ranh giới, đặt nhẹ trong luồng. |
| 2 | Onboarding 2 — Dữ liệu & quyền (Lịch, Vị trí — screen 01, ob2) | **Delay** | Không cần để tạo nháp đầu tiên. Hỏi **sau first value**, đúng ngữ cảnh → bỏ rào cản trước core action. |
| 3 | Onboarding 3 — Chọn điểm bắt đầu (screen 01, ob3) | **Keep** | Là entry tối thiểu, trực tiếp khởi động việc tạo lịch. |
| 4 | Setup câu 1 — Phong cách chuyến đi (screen 02, q1) | **Keep** | Minimum setup cần để lịch không lệch nhu cầu (quyết định mật độ điểm/ngày). |
| 5 | Setup câu 2 — Đi với ai (screen 02, q2) | **Delay** | Hữu ích nhưng không cần để tạo nháp; mặc định AI giả định "cân bằng" & ghi rõ, hỏi lại sau khi user đã thấy lịch (ở `#r5done`). |

## Checklist kiểm tra friction

| Câu hỏi | Trả lời / ghi chú |
|---|---|
| Có quá nhiều thông tin phải nhập không? | Hơi nhiều: 2 câu hỏi setup trước khi thấy bất kỳ value nào → rút còn **1 câu cốt lõi**, phần còn lại hoãn. |
| Có yêu cầu tạo tài khoản / cấp permission quá sớm không? | Có — bước quyền (Lịch, Vị trí) hiện ngay trong onboarding dù mặc định TẮT → **hoãn** sau first value. |
| Có bước giải thích dài trước khi user được thử không? | Có — màn kỳ vọng (2 callout) → **Simplify** thành 1 dòng. |
| Có cấu hình nào có thể Delay tới sau first value không? | Có — 2 quyền + câu "đi với ai" đều Delay được. |
| CTA chính trên mỗi màn hình có rõ không? | Day 18: tương đối rõ. Bản redesign làm CTA "✓ Dùng lịch này" thành hành động chính, đo được. |
| User có biết mình đang tiến gần tới value không? | Day 18: chưa hiển thị evidence rõ. Redesign thêm **evidence of value** ("4 điểm/ngày · di chuyển hợp lý") ngay tại nháp. |

## Bảng Current State (đối chiếu với `00-current-state.md`)

| Chỉ số | Current state |
|---|---|
| Số bước tới first core action | ~**7–8** (3 onboarding + điểm bắt đầu + 2 câu hỏi → xem nháp → chấp nhận) |
| Số trường thông tin phải nhập | ~**2 lựa chọn** (phong cách, đi với ai) |
| Số permission phải cấp | **0 bắt buộc**, nhưng 2 quyền tuỳ chọn **hiện sớm** trong onboarding |
| Time to First Core Action ước tính | nháp ~60–90s (activation) → chấp nhận ~**2–4 phút** *(ước tính)* |
| Time to Value ước tính | ~**2–4 phút** (≈ tới khi chấp nhận lịch) *(ước tính)* |
| Điểm drop-off có khả năng cao nhất | **Bước quyền** hoặc **2 câu hỏi setup** — thao tác trước khi thấy value |
