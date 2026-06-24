# Design Rationale & Documentation — Lộ Trình AI (Track 1 · AI Travel Planner)

> **File giải thích thiết kế duy nhất.** Toàn bộ phần *rationale* được tách khỏi màn hình prototype: `index.html` chỉ chứa **các màn hình**, còn mọi giải thích (phạm vi, kịch bản, agency, explainability, feedback 2×2, demo path) nằm ở đây. Mỗi màn hình trong prototype có dòng "📄 Rationale →" trỏ về đúng mục dưới đây (đáp ứng mục 7.2 — rationale gắn với flow).
>
> **Lát cắt:** AI tạo & điều chỉnh lịch trình một chuyến đi. **Người dùng:** khách du lịch tự túc cần lịch trình thực tế cho chuyến đi ngắn.

---

## Mục lục

- [Phạm vi & vòng đời (flow map)](#phạm-vi--vòng-đời-flow-map)
- [Kịch bản (1 onboarding + 5)](#kịch-bản-1-onboarding--5)
- [Bảng quyết định Agency](#bảng-quyết-định-agency--rủi-ro--khả-năng-hoàn-tác)
- [T0 — Onboarding](#t0--onboarding)
- [T2 — AI hỏi trước khi lập kế hoạch](#t2--ai-hỏi-trước-khi-lập-kế-hoạch)
- [T3 — Tiêu chí khách sạn xung đột (Explainability)](#t3--tiêu-chí-khách-sạn-xung-đột-explainability)
- [T9 — Người dùng muốn đặt dịch vụ (Agency)](#t9--người-dùng-muốn-đặt-dịch-vụ-agency)
- [T6 — Lịch trình quá dày (vòng khôi phục đầy đủ)](#t6--lịch-trình-quá-dày-vòng-khôi-phục-đầy-đủ)
- [T7 — AI dùng thông tin lỗi thời (Bằng chứng)](#t7--ai-dùng-thông-tin-lỗi-thời-bằng-chứng)
- [Feedback hai chiều — Ma trận 2×2 (mục 9)](#feedback-hai-chiều--ma-trận-22-mục-9)
- [Demo path 5 phút](#demo-path-5-phút)
- [Checklist điều kiện tối thiểu (mục 19)](#checklist-điều-kiện-tối-thiểu-mục-19)

---

## Phạm vi & vòng đời (flow map)

Một lát cắt xuyên suốt: lần đầu mở tính năng → khai thác nhu cầu → tạo lịch nháp → review & điều chỉnh → phát hiện & khôi phục lỗi → vòng phản hồi hai chiều.

```
Onboarding (T0)
  → Trong hành động (T2)        : AI hỏi điều quan trọng → tạo lịch nháp
  → Sau hành động (T3, T9)      : review · dữ kiện vs suy luận · explainability · agency
  → Phản hồi & khôi phục (T6,T7): phát hiện lỗi → sửa → tiếp tục mục tiêu
  ↺ quay lại kết quả tốt hơn / lần dùng sau
```

| Giai đoạn | Nội dung |
|---|---|
| ① Onboarding | Kỳ vọng, dữ liệu & quyền, điểm bắt đầu. |
| ② Trong hành động | AI hỏi điều quan trọng → tạo lịch nháp. |
| ③ Sau hành động | Review, giải thích, agency. |
| ④ Phản hồi & khôi phục | Phát hiện lỗi → sửa → tiếp tục. |

5 kịch bản nối thành **một** sản phẩm (không phải 5 mini-app rời): tất cả xoay quanh cùng một chuyến Đà Nẵng 3 ngày của cùng một người dùng.

---

## Kịch bản (1 onboarding + 5)

| Kịch bản | Giai đoạn | Mô tả ngắn |
|---|---|---|
| **T0** Lần đầu mở app | Onboarding | Thiết lập kỳ vọng, dữ liệu & quyền, điểm bắt đầu. |
| **T2** AI hỏi trước khi lập | During · Ask | Đà Nẵng nhưng thiếu bối cảnh → hỏi điều quan trọng nhất. |
| **T3** Tiêu chí khách sạn xung đột | During · Evidence | Giải thích xếp hạng + cho chỉnh trọng số. |
| **T6** Lịch quá dày | Failure · Don't Act→Act | Vòng phát hiện → sửa → ghi nhớ đầy đủ. |
| **T7** Thông tin lỗi thời | Failure · Warn | Lớp bằng chứng + đường thay thế. |
| **T9** Đặt dịch vụ | Agency | Act · Ask · Don't Act. |

---

## Bảng quyết định Agency — rủi ro × khả năng hoàn tác

Nguyên tắc: **chi phí khi sai × độ khó hoàn tác → mức tự chủ**. Không ép AI tự làm việc nguy hiểm chỉ để "đủ Act".

| Kịch bản | Điều có thể sai & hậu quả | Dễ phát hiện / hoàn tác? | Quyết định |
|---|---|---|---|
| **T0** Onboarding | Người dùng tưởng AI tự đặt chỗ → thất vọng, mất tin | Dễ — chưa hành động gì | **Don't Act** — nêu rõ ranh giới trước |
| **T2** Hỏi trước khi lập | Lịch lệch nhu cầu → làm lại (chi phí trung bình) | Dễ — lịch là nháp | **Ask** 2 câu cốt lõi, giải thích vì sao |
| **T3** Xếp khách sạn | Ưu tiên sai tiêu chí → đặt phòng lệch nhu cầu | Dễ — bảng điểm minh bạch, re-rank ngay | Trình bày dưới dạng **suy luận** + cho chỉnh trọng số |
| **T6** Lịch quá dày | Kiệt sức, bỏ lỡ điểm; phát hiện sớm khi còn nháp | Dễ — có Undo + before/after | **Act** chỉ *sau khi* người dùng chọn hướng |
| **T7** Dữ liệu cũ | Tới nơi quán đóng cửa → hỏng buổi, khó sửa tại chỗ | Khó tại chỗ → phải chặn từ trước | **Don't Act** — phơi bày độ tin cậy + thay thế |
| **T9** Thanh toán | Trừ tiền sai / đặt nhầm → tổn thất tài chính | Rất khó hoàn tác | **Don't Act** thanh toán + **Act** điền form (undo) + **Ask** xác nhận |

**Hai câu lập luận mẫu (đúng tinh thần mục 7.2):**
- *"Thanh toán có chi phí khi sai cao và khó hoàn tác, vì vậy AI phải dừng ở bước chuẩn bị & xin xác nhận — **Don't Act**."*
- *"Giãn lịch là rủi ro thấp, người dùng nhìn thấy ngay và có Undo, vì vậy AI được tự thực hiện sau khi người dùng chọn hướng — **Act**."*

---

## T0 — Onboarding
*(màn hình: trang 01)*

1. **AI đang biết gì?** Đây là người dùng mới, chưa có dữ liệu sở thích.
2. **Chưa biết / không chắc?** Người dùng muốn nghỉ dưỡng hay khám phá, đi với ai, ngân sách.
3. **Giả định nào?** Không giả định gì về chuyến đi — onboarding chỉ thiết lập kỳ vọng.
4. **Điều gì có thể sai?** Người dùng kỳ vọng AI tự đặt chỗ/thanh toán → thất vọng khi không có.
5. **Nếu sai, hậu quả & ai chịu?** Mất niềm tin ngay từ đầu; ảnh hưởng toàn bộ trải nghiệm sau.
6. **Dễ phát hiện & hoàn tác?** Dễ — chưa có hành động nào diễn ra.
7. **Act / Ask / Don't Act?** **Don't Act** — chưa làm gì; chỉ **Ask** các quyền *tùy chọn*, mặc định TẮT.
8. **Người dùng kiểm tra/sửa/từ chối/hoàn tác ở đâu?** Mọi quyền có thể bỏ qua & rút lại trong Cài đặt → Quyền riêng tư.
9. **Phản hồi thu thập / trả lại?** System→User explicit: nêu rõ AI làm gì / không làm gì, phạm vi dùng dữ liệu.
10. **Giúp tiếp tục mục tiêu thế nào?** 3 điểm xuất phát (mơ hồ / có điểm đến / nhập sẵn) giảm tải nhận thức, dẫn thẳng vào luồng — tránh biểu mẫu dài.

> **System→User implicit:** toggle quyền mặc định TẮT và nút "Bỏ qua" đặt ngang nút "Tiếp tục" → affordance ngầm rằng cấp quyền là *tùy chọn*, không phải điều kiện bắt buộc.

---

## T2 — AI hỏi trước khi lập kế hoạch
*(màn hình: trang 02 · gồm cả nhánh T1 "nhu cầu mơ hồ")*

1. **AI đang biết gì?** Điểm đến (Đà Nẵng), số ngày (3).
2. **Chưa biết / không chắc?** Phong cách, người đi cùng, ngân sách — quyết định mật độ & loại điểm.
3. **Giả định nào?** Nếu thiếu, AI giả định "cân bằng" và **ghi rõ giả định**, không giấu.
4. **Điều gì có thể sai?** Tạo lịch quá sớm → lệch nhu cầu, người dùng phải làm lại.
5. **Hậu quả & ai chịu?** Trung bình — mất thời gian; người dùng chịu nhưng dễ sửa.
6. **Dễ phát hiện & hoàn tác?** Có — kết quả là nháp, sửa được ngay.
7. **Act / Ask / Don't Act?** **Ask** — phong cách là giả định quan trọng tác động lớn tới kết quả. Nhưng chỉ hỏi **2 câu cốt lõi** để tránh "hỏi quá nhiều gây mệt" (T2).
8. **Người dùng kiểm tra/sửa ở đâu?** Trả lời bằng chip; có thể bỏ qua để AI giả định.
9. **Phản hồi thu thập / trả lại?** System→User explicit: giải thích *vì sao* mỗi câu cần thiết. User→System implicit: tốc độ trả lời & câu bị bỏ qua → điều chỉnh số câu hỏi lần sau (tín hiệu sở thích, **không** coi là nhãn đúng/sai).
10. **Giúp tiếp tục mục tiêu thế nào?** Sau 2 câu, AI tạo nháp ngay với trạng thái rõ và recap giả định.

> **Nhánh T1 (mơ hồ):** nếu vào bằng "đi đâu đó nghỉ ngơi" (chưa có điểm đến), AI **không** tạo lịch (Don't Act — thiếu dữ liệu) mà gợi 2–3 vùng phù hợp và hỏi từng bước, **không quyết thay** người dùng.

---

## T3 — Tiêu chí khách sạn xung đột (Explainability)
*(màn hình: trang 03 · "Vì sao #1")*

1. **AI đang biết gì?** 3 khách sạn + thuộc tính (giá, khoảng cách, sao) — đều là dữ kiện.
2. **Chưa biết / không chắc?** Người dùng coi trọng *tiêu chí nào nhất* — AI chỉ đang giả định "gần biển".
3. **Giả định nào?** Gần biển quan trọng hơn giá → phơi bày trọng số để người dùng sửa.
4. **Điều gì có thể sai?** Xếp sai ưu tiên → người dùng đặt nhầm phòng đắt hơn / xa nhu cầu.
5. **Hậu quả & ai chịu?** Trung bình — chi nhiều tiền hơn cần; người dùng chịu, nhưng chưa đặt nên sửa được.
6. **Dễ phát hiện & hoàn tác?** Dễ — bảng điểm minh bạch, đổi trọng số là re-rank ngay.
7. **Act / Ask / Don't Act?** Trình bày kết quả dưới dạng **suy luận** (không tự chốt). Không cần Ask vì rủi ro thấp; thay vào đó cho người dùng **điều khiển trực tiếp** tiêu chí.
8. **Người dùng kiểm tra/sửa ở đâu?** Kéo slider trọng số → thứ hạng đổi tức thì.
9. **Phản hồi thu thập / trả lại?** User→System explicit: chỉnh trọng số = dạy hệ thống tiêu chí thật. System→User explicit: bảng điểm + lý do xếp hạng.
10. **Giúp tiếp tục mục tiêu thế nào?** Người dùng hiểu & tự điều chỉnh, rồi đi tiếp tới bước đặt chỗ với lựa chọn đúng nhu cầu. **Đây là lớp bằng chứng / explainability bắt buộc (mục 10).**

---

## T9 — Người dùng muốn đặt dịch vụ (Agency)
*(màn hình: trang 03 · khối "Đặt khách sạn")*

1. **AI đang biết gì?** Lựa chọn khách sạn, ngày, số khách của người dùng.
2. **Chưa biết / không chắc?** Thông tin thanh toán, ý định cuối cùng có thật sự muốn đặt.
3. **Giả định nào?** Người dùng muốn tiến tới đặt → AI chỉ *chuẩn bị*, không *thực hiện*.
4. **Điều gì có thể sai?** Đặt nhầm phòng/ngày, trừ tiền sai.
5. **Hậu quả & ai chịu?** Cao — tổn thất tài chính trực tiếp cho người dùng.
6. **Dễ phát hiện & hoàn tác?** Thanh toán **rất khó hoàn tác**; điền form thì dễ (có Undo).
7. **Act / Ask / Don't Act? (đủ 3 mức trong một flow)**
   - **Act:** điền sẵn thông tin đặt chỗ từ lựa chọn đã có — rủi ro thấp, nhìn thấy ngay, có Undo.
   - **Ask:** xin xác nhận thông tin trước khi sang trang thanh toán.
   - **Don't Act:** không tự thanh toán / đặt chỗ — nút khoá 🔒, người dùng tự thực hiện trên trang nhà cung cấp.
8. **Người dùng kiểm tra/sửa/hoàn tác ở đâu?** Sửa form nháp; "Hoàn tác" cạnh hành động Act; tự bấm thanh toán.
9. **Phản hồi thu thập / trả lại?** System→User explicit: nêu rõ vì sao AI dừng ở chuẩn bị.
10. **Giúp tiếp tục mục tiêu thế nào?** AI làm hết phần an toàn (điền, tóm tắt) để người dùng chỉ cần một bước cuối có kiểm soát.

> **System→User implicit:** nút "Thanh toán" hiển thị **mờ + ổ khoá**, còn "Hoàn tác" luôn nằm cạnh hành động Act → affordance ngầm cho biết AI *được* và *không được* làm gì mà không cần đọc chữ.

---

## T6 — Lịch trình quá dày (vòng khôi phục đầy đủ)
*(màn hình: trang 04 · T6) — kịch bản thể hiện **trọn vẹn** vòng lặp mục 5D.*

```
AI tự nêu vấn đề (Ngày 1 quá dày)
 → Người dùng chọn lý do cụ thể        (User→System explicit)
 → Hệ thống xác nhận đã hiểu vấn đề gì
 → Hệ thống đề xuất 2–3 cách khôi phục
 → Người dùng chọn → AI áp dụng         (Act · có Undo)
 → Before/After
 → Hệ thống nói rõ điều gì được sửa & hỏi có ghi nhớ không (người dùng kiểm soát)
```

1. **AI đang biết gì?** Số điểm/ngày, khoảng cách, thời gian di chuyển (dữ kiện tính được).
2. **Chưa biết / không chắc?** Ngưỡng "quá dày" tùy người → AI **gắn cờ** chứ không tự xoá điểm.
3. **Giả định nào?** "Cân bằng" nghĩa là ~4 điểm/ngày — nhưng để người dùng xác nhận.
4. **Điều gì có thể sai?** Người dùng kiệt sức giữa chuyến, bỏ lỡ điểm muốn đi.
5. **Hậu quả & ai chịu?** Trải nghiệm chuyến đi xấu; nhưng phát hiện sớm khi còn nháp.
6. **Dễ phát hiện & hoàn tác?** Dễ — có Undo và so sánh before/after.
7. **Act / Ask / Don't Act?** Tự gắn cờ = cung cấp thông tin; **sửa chỉ sau khi người dùng chọn hướng = Act có Undo.** Không tự ý đổi lịch (tránh phá ý định người dùng).
8. **Người dùng kiểm tra/sửa/từ chối ở đâu?** Chip lý do cụ thể; chọn hướng khôi phục; Undo; "Giữ nguyên".
9. **Phản hồi thu thập / trả lại?** User→System explicit (chip lý do — chỉ ra **loại lỗi**, không chỉ "không hữu ích"). System xác nhận đã hiểu *trước khi* sửa. Ghi nhớ "≤4 điểm/ngày" **chỉ khi người dùng đồng ý**.
10. **Giúp tiếp tục mục tiêu thế nào?** Không dừng ở "không hữu ích" — dẫn tới lịch đã sửa + before/after + tùy chọn ghi nhớ cho lần sau.

---

## T7 — AI dùng thông tin lỗi thời (Bằng chứng)
*(màn hình: trang 04 · T7)*

1. **AI đang biết gì?** Có hồ sơ nhà hàng + thời điểm đồng bộ dữ liệu (03/2026).
2. **Chưa biết / không chắc?** Giờ mở cửa / giá hiện tại — dữ liệu đã cũ 3 tháng.
3. **Giả định nào?** Không giả định dữ liệu còn đúng → đánh dấu độ tin cậy thấp.
4. **Điều gì có thể sai?** Người dùng tới nơi quán đóng cửa → hỏng buổi tối.
5. **Hậu quả & ai chịu?** Cao cho trải nghiệm tại chỗ; **khó hoàn tác khi đang đi**.
6. **Dễ phát hiện & hoàn tác?** Khó tại chỗ → phải chặn từ trước bằng cảnh báo + thay thế.
7. **Act / Ask / Don't Act?** **Don't Act** — không tự chốt dữ liệu cũ thành "đã xác nhận"; giữ trạng thái "cần xác nhận".
8. **Người dùng kiểm tra/sửa ở đâu?** "Mở để kiểm tra lại" hoặc "Xem phương án thay thế" (dữ liệu hôm nay).
9. **Phản hồi thu thập / trả lại?** System→User explicit: nhãn "cập nhật 3 tháng trước" + nguồn + thời điểm đồng bộ → **lớp bằng chứng (mục 10).**
10. **Giúp tiếp tục mục tiêu thế nào?** Luôn có phương án mới để người dùng đi tiếp; lịch không bị kẹt.

> **Nguyên tắc:** một dòng "AI có thể sai" *không thay* thiết kế. Ở đây có nguồn, nhãn độ tin cậy, trạng thái "cần xác nhận" và đường khôi phục thật.

---

## Feedback hai chiều — Ma trận 2×2 (mục 9)

> Nguyên tắc xuyên suốt: **Hành vi ≠ ý định ≠ sự thật chuẩn.** "Undo" có thể vì AI sai, cũng có thể vì người dùng đổi ý → hệ thống diễn giải thận trọng, ưu tiên xác nhận tường minh trước khi học.

| | Explicit — Tường minh | Implicit — Ngầm định |
|---|---|---|
| **User → System** | Chọn lý do "lịch quá dày", chỉnh trọng số khách sạn, từ chối/sửa điểm | Bỏ qua câu ngân sách, undo, thời gian dừng ở bảng so sánh |
| **System → User** | "Đang kiểm tra giờ mở cửa", nhãn độ tin cậy, nguồn, bước tiếp theo | Nút Thanh toán mờ+khoá, nhãn "BẢN NHÁP", progressive disclosure |

### ① User → System · EXPLICIT
*Xuất hiện ở: T3 (chỉnh trọng số), T6 (chip lý do "quá dày"), review (sửa/từ chối điểm).*

- **Thời điểm:** khi người dùng review & sửa kết quả.
- **Giúp đạt mục tiêu gì:** dạy hệ thống **tiêu chí thật** và **loại lỗi cụ thể**, không chỉ "không hữu ích".
- **Vì sao tường minh:** tín hiệu rõ, ít mơ hồ → dùng được để sửa ngay và (nếu được phép) học lâu dài.
- **Ý nghĩa khác có thể có:** "quá dày" có thể chỉ do hôm đó người dùng mệt → hệ thống **xác nhận đã hiểu** trước khi sửa.
- **Sản phẩm phản ứng ngay:** re-rank / giãn lịch + hiển thị before/after.
- **Dùng cho cá nhân hoá / cải thiện sau?** Chỉ ghi nhớ "≤4 điểm/ngày" **khi người dùng bấm đồng ý** (nút Có/Không).
- **Người dùng biết & kiểm soát?** Có — thấy & sửa được điều đã ghi nhớ trong Cài đặt.
- **Có gây gián đoạn quá mức?** Không — nằm đúng trong ngữ cảnh review.

### ② User → System · IMPLICIT
*Xuất hiện ở: T2 (bỏ qua câu ngân sách), T6 (undo), T3 (dừng lâu ở bảng so sánh).*

- **Thời điểm:** trong lúc tương tác bình thường, không có thao tác feedback riêng.
- **Giúp đạt mục tiêu gì:** suy ra sở thích nhẹ (thích trả lời nhanh / đang phân vân) để giảm ma sát.
- **Vì sao ngầm định:** không muốn ngắt lời bằng câu hỏi; quan sát rồi **đề xuất** nhẹ (cue ngầm trước khi hướng dẫn trực tiếp).
- **Ý nghĩa khác có thể có:** **undo ≠ AI sai** — có thể người dùng đổi ý. **Không** tự gán nhãn đúng/sai.
- **Sản phẩm phản ứng ngay:** hỏi ít câu hơn lần sau; **không** tự đổi lịch dựa trên tín hiệu ngầm.
- **Dùng cho cá nhân hoá / cải thiện sau?** Chỉ làm gợi ý, có chú thích "dựa trên hành vi gần đây" & cho tắt.
- **Người dùng biết & kiểm soát?** Có — mục "Vì sao tôi thấy gợi ý này?" minh bạch tín hiệu ngầm.
- **Có gây gián đoạn quá mức?** Không — hoàn toàn nền.

### ③ System → User · EXPLICIT
*Xuất hiện ở: T2 (đang xử lý), T7 (nhãn độ tin cậy + nguồn), T9 (giải thích vì sao chặn thanh toán).*

- **Thời điểm:** khi đang xử lý, khi dữ liệu không chắc, khi chặn hành động rủi ro cao.
- **Giúp đạt mục tiêu gì:** giúp người dùng hiểu AI đang làm gì, giới hạn ở đâu, bước tiếp theo là gì.
- **Vì sao tường minh:** rủi ro & giới hạn phải nói thẳng, không để người dùng đoán.
- **Ý nghĩa khác có thể có:** —
- **Sản phẩm phản ứng ngay:** hiển thị nguồn, thời điểm đồng bộ, đường thay thế.
- **Dùng cho cá nhân hoá?** Không — đây là minh bạch trạng thái.
- **Người dùng kiểm soát?** Có thể bỏ qua/đóng; không bắt buộc đọc.
- **Có gây gián đoạn quá mức?** Đặt ở điểm dừng tự nhiên (trước khi đặt chỗ), không nhảy liên tục.

### ④ System → User · IMPLICIT
*Xuất hiện xuyên suốt: nút Thanh toán mờ+khoá, nhãn "BẢN NHÁP", toggle quyền mặc định tắt, "Vì sao #1" ẩn tới khi cần.*

- **Thời điểm:** liên tục, qua chính thiết kế giao diện.
- **Giúp đạt mục tiêu gì:** truyền đạt giới hạn & quyền kiểm soát qua **affordance**, không cần đọc chữ.
- **Vì sao ngầm định:** dùng cue ngầm trước khi ngắt lời bằng hướng dẫn trực tiếp; **progressive disclosure** chi tiết nâng cao.
- **Ý nghĩa khác có thể có:** —
- **Sản phẩm phản ứng ngay:** nút khoá ⇒ không thể bấm nhầm sang hành động rủi ro cao.
- **Dùng cho cá nhân hoá?** Không.
- **Người dùng kiểm soát?** Có — mở chi tiết khi muốn; trạng thái nháp luôn rõ.
- **Có gây gián đoạn quá mức?** Tối thiểu — chỉ hiện chi tiết khi người dùng chủ động mở.

### Vòng feedback tốt giúp người dùng hiểu
> *Mình vừa làm gì · hệ thống vừa làm gì · bước tiếp theo nên là gì.*

Trong lát cắt này, vòng đó thể hiện rõ nhất ở **T6**: người dùng nêu lỗi (đã làm gì) → hệ thống xác nhận & sửa (hệ thống làm gì) → before/after + tùy chọn ghi nhớ (bước tiếp theo).

---

## Demo path 5 phút

| Thời lượng | Nội dung | Màn hình |
|---|---|---|
| 0:00–0:30 | Người dùng, vấn đề & lát cắt — khách du lịch tự túc cần lịch trình thực tế. | (mở đầu) |
| 0:30–1:15 | Onboarding: 3 bước — kỳ vọng, quyền (mặc định tắt), điểm bắt đầu. | 01 Onboarding |
| 1:15–2:15 | Luồng chính + Act/Ask/Don't Act: AI Ask 2 câu → nháp → review → T3 explainability → T9 agency. | 02 + 03 |
| 2:15–3:45 | Hai kịch bản sai sót & recovery: T6 vòng đầy đủ + Undo + before/after; T7 dữ liệu cũ + thay thế. | 04 |
| 3:45–4:45 | Feedback hai chiều (đủ 4 loại): ma trận 2×2, mỗi ô là một tín hiệu thật trong flow. | (tài liệu này) |
| 4:45–5:00 | Quyết định quan trọng nhất & rủi ro còn lại: ranh giới Don't Act (thanh toán, dữ liệu cũ). Rủi ro còn lại: người dùng có thể bỏ qua nhãn độ tin cậy. | — |

---

## Checklist điều kiện tối thiểu (mục 19)

- [x] Onboarding cho lần đầu sử dụng tính năng — **T0**
- [x] ≥ 4 kịch bản ngoài onboarding — **T2, T3, T6, T7, T9** (5)
- [x] Lát cắt xuyên suốt Onboarding → During → After → Feedback
- [x] Đủ **Act / Ask / Don't Act**
- [x] ≥ 1 vòng feedback + recovery hoàn chỉnh — **T6**
- [x] Đủ 4 loại feedback trong ma trận 2×2 — xem [Feedback 2×2](#feedback-hai-chiều--ma-trận-22-mục-9)
- [x] ≥ 1 lớp bằng chứng / giải thích — **T3, T7**
- [x] Design rationale gắn với flow — file này + link "📄 Rationale →" trong prototype
