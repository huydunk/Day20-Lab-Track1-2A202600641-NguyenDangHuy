# 06 — Before / After & Recovery Path

> Bài 3 · §10. Chứng minh redesign bằng so sánh **cụ thể**, và giữ/cải thiện ≥1 recovery path.

## Before / After Comparison

| Tiêu chí | Before (Day 18) | After (Day 20) | Vì sao thay đổi? |
|---|---|---|---|
| Số bước tới core action | ~7–8 | ~**4–5** | Hoãn quyền + câu "đi với ai"; rút setup còn 1 câu. |
| Số trường phải nhập | 2 câu (phong cách, đi với ai) | **1 câu** (phong cách) | "Đi với ai" Delay tới sau nháp; AI giả định & ghi rõ. |
| Permission trước core action | **2** (Lịch, Vị trí — hiện trong onboarding) | **0** | Hoãn quyền tới sau first value, hỏi đúng ngữ cảnh (`#r5done`). |
| Time to First Core Action | ~2–4 phút | ~**1–2 phút** *(ước tính)* | Ít bước hơn trước accept. |
| Time to Value | ~2–4 phút | ~**1–2 phút** *(ước tính)* | Evidence of value hiện ngay tại nháp. |
| Điểm drop-off chính | Bước quyền / 2 câu hỏi | **Giảm** (ít bước trước value) | Bỏ rào cản quyền & câu hỏi thừa trước khi thấy lịch. |
| Evidence of value | **Ngầm** — nháp tự hiện, không nói vì sao tốt | **Tường minh** — "4 điểm/ngày · ~1.5h di chuyển · nhãn nguồn" | User biết mình đang nhận value & vì sao lịch khả thi. |
| Recovery path | T6 (lịch quá dày) + T7 (dữ liệu cũ) tồn tại | **Giữ + reachable** từ trạng thái đã accept (`#r5done` → screen 04) | Recovery không bị mất khi rút gọn onboarding. |

## Recovery Path

Chọn **ít nhất một** trường hợp:

- [ ] User chưa có đủ dữ liệu
- [ ] User từ chối permission
- [x] **Kết quả đầu tiên chưa phù hợp** (lịch quá dày) ← chọn chính
- [ ] Action thất bại hoặc bị gián đoạn
- [ ] User chưa sẵn sàng hoàn thành core action
- [x] (phụ) Dữ liệu lỗi thời (T7)

| Mục | Nội dung |
|---|---|
| Trường hợp recovery đã chọn | **"Kết quả đầu tiên chưa phù hợp"** — lịch Ngày 1 quá dày (case chính, vòng T6); kèm case phụ **dữ liệu lỗi thời** (T7). |
| Recovery flow (đưa user **quay lại** journey tới core action, **không** kết thúc ở màn lỗi) | Từ `#r5done`: "Lịch quá dày? → sửa (T6)" → screen 04: AI tự nêu vấn đề → user chọn chip lý do → hệ thống xác nhận đã hiểu → đề xuất 2–3 cách → áp dụng (có Undo) → **before/after** → tuỳ chọn ghi nhớ. User quay lại với một lịch tốt hơn, không kẹt ở màn lỗi. |
| Liên hệ với recovery Day 18 (giữ / cải thiện gì?) | **Giữ nguyên** vòng T6/T7 của Day 18 (không phá); **cải thiện** ở chỗ recovery giờ **reachable trực tiếp** từ trạng thái đã accept của luồng onboarding mới, thay vì chỉ nằm rời ở screen 04. |
