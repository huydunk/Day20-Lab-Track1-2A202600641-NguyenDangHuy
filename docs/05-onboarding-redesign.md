# 05 — Redesigned Onboarding → First Core Action

> Bài 3 · §10. Thiết kế lại hành trình tới first core action. Prototype scaffold: screen **05** trong
> `../index.html` (`#s05`). Phải thể hiện thay đổi **cụ thể trên prototype**, không chỉ "dễ dùng hơn".

## Hành trình mục tiêu (redesign)

```
1. User bước vào sản phẩm
  ↓
2. Hiểu value proposition
  ↓
3. Thực hiện minimum setup
  ↓
4. Được hướng dẫn thực hiện hành vi thật
  ↓
5. First core action            ★
  ↓
6. Evidence of value
  ↓
7. Aha moment / first value
  ↓
8. Bước tiếp theo
```

> Prototype: **screen 05** trình bày dạng **Trước vs Sau cạnh nhau** — cột **Before** (Day 18) là ảnh
> chụp tĩnh, khối "Khác biệt & cải tiến" ở giữa, cột **After** (Day 20) là **bản chạy được (bấm thử)**.
> Các bước dưới đây map vào cột After (giữ ID để gắn event).

| Bước | Thiết kế của nhóm | Màn hình / thành phần prototype |
|---|---|---|
| 1 Vào sản phẩm | Mở thẳng vào ô chọn điểm đến, không tường giải thích. | screen 05 · cột After `#r5s1` · `[event: onboarding_started]` |
| 2 Value proposition | 1 dòng: "Lịch khả thi trong ~1 phút"; nêu rõ "mọi quyền & chi tiết hỏi sau". | screen 05 · `#r5s1` (vt + vd) |
| 3 Minimum setup | **Chỉ 1 câu cốt lõi** (phong cách); "đi với ai" + quyền được hoãn. | screen 05 · `#r5s2` · `[event: setup_completed]` |
| 4 Hướng dẫn hành vi thật | AI dựng nháp thật (không product tour) → lịch có nhãn Dữ kiện/Suy luận. | screen 05 · `#r5draft` · `[event: draft_generated]` = activation |
| 5 First core action ★ | **User bấm "✓ Dùng lịch này"** = chấp nhận lịch. | screen 05 · `#r5acceptBtn` · `[event: itinerary_accepted]` |
| 6 Evidence of value | "4 điểm/ngày · ~1.5h di chuyển · nhãn nguồn" — gắn ngay tại bước nháp. | screen 05 · `#r5draft` (vd) |
| 7 Aha moment | Có một lịch khả thi, đáng tin & đã chốt = first value (ngay sau accept). | screen 05 · `#r5acceptBtn` (★) |
| 8 Bước tiếp theo | Hỏi quyền (deferred, mặc định TẮT) đúng ngữ cảnh + lối vào recovery T6/T7. | screen 05 · `#r5done` · `[event: permission_prompted_deferred]`; recovery → screen 04 |

## Yêu cầu tối ưu (checklist)

- [x] Loại bỏ / Delay bước không cần thiết trước core action — hoãn 2 quyền + câu "đi với ai"
- [x] Chỉ giữ minimum setup cần để tạo first value — 1 câu phong cách
- [x] CTA chính trên mỗi màn hình đủ rõ — "✓ Dùng lịch này" là hành động chính
- [x] Giải thích permission đúng thời điểm — quyền hỏi **sau** first value, đúng ngữ cảnh
- [x] Cho user thực hiện hành vi thật (không chỉ product tour) — AI dựng nháp thật để review
- [x] Hiển thị evidence of value ngay sau core action — khối "Vì sao lịch này khả thi"
- [x] Giữ / cải thiện ít nhất một recovery path từ Ngày 18 — T6/T7 reachable từ `#r5done`

## Activation & Time to Value

| Khái niệm | Định nghĩa của nhóm |
|---|---|
| **Activation** (thời điểm user lần đầu thực sự nhận value) | Khi user **chấp nhận lịch nháp lần đầu** (`itinerary_accepted`) — tức đạt first core action. |
| **Activation Rate** (tỷ lệ user đạt activation) | % user vào onboarding (`onboarding_started`) mà **chấp nhận ≥1 lịch** trong phiên/cửa sổ đầu. |
| **Time to First Core Action** | Từ `onboarding_started` → `itinerary_accepted`: ~**1–2 phút** (redesign) *(ước tính)*. |
| **Time to Value** | ≈ TTFA — vì aha (đã có lịch chốt đáng tin) xảy ra **ngay tại/sau** accept: ~**1–2 phút** *(ước tính)*. |

> **Lựa chọn:** ở sản phẩm này **Activation = First Core Action = chấp nhận lịch**; **Aha moment**
> đến **ngay sau** (màn "Đã lưu lịch của bạn", `#r5done`). Gộp activation với core action là hợp lý
> vì giá trị chỉ thực sự được xác nhận khi user **chốt** một lịch khả thi — `draft_generated` chỉ là
> mốc **trung gian (leading)**, không tự nó chứng minh value.
