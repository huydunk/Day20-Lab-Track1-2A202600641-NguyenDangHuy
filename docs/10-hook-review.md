# 10 — Hook Model Review

> Bài 5 · §14–15. Chỉ thiết kế habit loop **sau khi** đã hiểu natural frequency.
> Nếu hành vi xảy ra **ít hơn weekly**, habit khó hình thành — **không ép** use case frequency thấp
> thành hành vi hằng ngày.

## 14.1. Kiểm tra sản phẩm có thực sự cần habit không

> **Kết luận (đọc trước):** core action (lập & chấp nhận lịch) chỉ ~5–8 lần/năm → **KHÔNG ép thành
> habit hằng ngày**. Tách **2 nhịp**: **(A) trong chuyến** = vòng Hook daily thật (xem & điều chỉnh
> lịch hôm nay); **(B) giữa các chuyến** = chỉ **nurture nhẹ** (cảm hứng/lưu ý tưởng), không phải habit.
> Hook Model dưới đây áp cho **nhịp (A) — trong chuyến**.

| Câu hỏi | Trả lời |
|---|---|
| Vì sao business/user cần hành vi này thành habit? | Trong chuyến, user cần liên tục bám lịch & điều chỉnh → bám sản phẩm = chuyến suôn sẻ + tạo data cá nhân hoá cho chuyến sau. **Ngoài chuyến: không cần habit.** |
| Vấn đề nào của user đang được giải quyết? | Lo "đi lệch lịch / quá dày / tới nơi quán đóng cửa" — cần điều chỉnh real-time đáng tin. |
| Hành vi cụ thể nào muốn được lặp lại? | **Trong chuyến:** mở app xem & điều chỉnh **lịch hôm nay**. |
| Hành vi đó tự nhiên xuất hiện với frequency nào? | **Daily trong chuyến** (vài ngày liên tục); ~0 ngoài chuyến. |
| Sản phẩm có đủ frequency / perceived utility để vào habit zone? | **Có — chỉ trong cửa sổ chuyến đi** (utility cao, daily). **Ngoài chuyến: không** → dùng nurture thay vì ép habit. |

## Trigger

- External trigger có thể là: paid · earned · relationship · owned.
- Dùng **5 Whys** để tìm 3 internal trigger có thể có, rồi chọn cái xảy ra thường xuyên nhất.

**5 Whys → 3 internal trigger có thể có (nhịp trong chuyến):**
1. "Tới lúc quyết định điểm/giờ tiếp theo mà phân vân" — *xảy ra nhiều lần/ngày khi đang đi.* ← **chọn (thường xuyên nhất)**
2. "Lo điểm kế tiếp có còn mở / có kịp giờ không".
3. "Buổi trống chưa biết làm gì, muốn gợi ý gần đây".

**External trigger:** *owned* — push "lịch hôm nay" buổi sáng; cảnh báo "ngày quá dày" (T6) / "dữ liệu
cũ" (T7) đúng lúc. *relationship* — bạn đồng hành chia sẻ/mở lịch nhóm.

**Hoàn thành câu:** Mỗi khi user **đang trong chuyến và tới lúc quyết định điểm/giờ tiếp theo** (internal trigger), họ sẽ **mở Lộ Trình AI để xem & điều chỉnh lịch hôm nay** (hành vi muốn tạo).

## Action (Motivation + Ability + Trigger)

| Bước | Trả lời |
|---|---|
| Số bước từ internal trigger → outcome | Mục tiêu **1 tap**: mở app → thấy ngay "lịch hôm nay" (hiện trạng có thể là mở app → tìm tab → chọn ngày = ~3 bước). |
| Rào cản đang làm giảm Ability | **Brain cycles** (phải tự tìm đúng ngày/điểm) · **Time** (vài thao tác) · **Non-routine** (chưa quen mở app khi đang đi chơi). |
| 3 cách có thể kiểm thử để action dễ hơn | (1) Mặc định mở thẳng **"lịch hôm nay"**; (2) **widget / lock-screen** điểm kế tiếp; (3) **push có nội dung** (tên điểm + giờ) bấm vào là tới đúng chỗ. |

Loại rào cản (Fogg): Time · Brain cycles · Money · Physical effort · Social deviance · Non-routine.

## Variable Reward

The Tribe (kết nối/công nhận) · The Hunt (tìm tài nguyên/thông tin) · The Self (làm chủ/tiến bộ).

| Câu hỏi | Trả lời |
|---|---|
| Reward nào giải quyết nhu cầu/pain của user? | Mở lịch ra được **điểm/quán phù hợp gần đây**, **phương án thay thế** khi điểm cũ đóng cửa (T7), và một ngày **chạy mượt** không lo sót. |
| User thấy điều gì thỏa mãn/hữu ích/đáng khích lệ? | Bất ngờ dễ chịu khi tìm thấy chỗ hay; yên tâm vì lịch khả thi & cập nhật; cảm giác chuyến đi trong tầm kiểm soát. |
| Thuộc loại nào (Tribe/Hunt/Self)? | **The Hunt** (tìm điểm/thông tin) + **The Self** (làm chủ, chuyến suôn sẻ) là chính; **The Tribe** (chia sẻ lịch nhóm, được bạn đồng hành tán thành) là phụ. |
| Reward phục vụ core action hay chỉ gamification gắn thêm? | **Phục vụ core action** — reward đến từ chính chất lượng lịch & gợi ý, **không** phải điểm/huy hiệu gắn thêm. |

## Investment

| Câu hỏi | Trả lời |
|---|---|
| User đầu tư điều gì? | Chỉnh lịch, chọn phong cách, **lưu sở thích** ("≤4 điểm/ngày" từ T6), đánh dấu điểm thích, để lại lịch sử chuyến. |
| Lưu value dưới dạng gì (content/data/followers/reputation/skill)? | **Data cá nhân hoá** (sở thích, ràng buộc) + **content** (lịch đã lưu, điểm yêu thích). |
| Tạo value cho lần sử dụng sau thế nào? | Lần sau AI đề xuất **đúng gu hơn**, ít hỏi lại hơn → lịch tốt hơn, nhanh hơn. |
| Tạo / "load" trigger tiếp theo ra sao? | **Trong chuyến:** đã lưu lịch hôm nay → push "lịch ngày mai/điểm kế tiếp". **Giữa chuyến:** sở thích đã lưu → gợi ý chuyến/điểm đến mới (nurture). |
| Sau bao lâu trigger tiếp theo xuất hiện? | **Trong chuyến:** vài giờ–1 ngày. **Chuyến kế tiếp:** ~6–10 tuần (nhịp tự nhiên). |

## 14.6. Kiểm tra tác động lên user

- [x] Thành viên nhóm có sẵn sàng dùng cơ chế này không? **Có** — đều là nhắc/gợi ý hữu ích trong chuyến, không gây nghiện vô nghĩa.
- [x] Hành vi thiết kế có thực sự cải thiện cuộc sống/công việc của user không? **Có** — chuyến đi suôn sẻ hơn, ít stress, ít sai sót.
- [x] Cơ chế có làm user mất kiểm soát / bị làm phiền / hành vi ngoài ý muốn không? **Không** — notification có thể tắt; **không spam ngoài chuyến**; mọi thay đổi đều có Undo & minh bạch (đạo đức Day 18: kiểm soát, Don't Act).

## 15. Hook Review — bảng tổng hợp

| Thành phần | Câu hỏi | Trả lời |
|---|---|---|
| Why Habit? | Vì sao cần thành habit? | Trong chuyến: bám lịch & điều chỉnh liên tục → chuyến suôn sẻ + data cá nhân hoá. Ngoài chuyến: **không** cần habit. |
| Intended Behavior | Hành vi cụ thể cần lặp lại? | Mở app xem & điều chỉnh **lịch hôm nay** (trong chuyến). |
| Frequency & Utility | Đủ thường xuyên / hữu ích để thành habit? | **Có — chỉ trong cửa sổ chuyến** (daily, utility cao); ngoài chuyến dùng nurture. |
| Internal Trigger | Nhu cầu/cảm xúc xuất hiện thường xuyên nhất? | "Tới lúc quyết định điểm/giờ tiếp theo mà phân vân". |
| External Trigger | Trigger đúng nơi đúng lúc? | Push "lịch hôm nay" (owned); cảnh báo T6/T7; chia sẻ lịch nhóm (relationship). |
| Action | Hành vi đơn giản nhất để nhận reward? | 1 tap → "lịch hôm nay". |
| Motivation | User muốn thực hiện vì điều gì? | Chuyến mượt, không sót/sai, tìm được chỗ hay, yên tâm. |
| Ability | Rào cản nào cần loại bỏ? | Brain cycles / Time / Non-routine → mặc định mở "hôm nay", widget, push có nội dung. |
| Variable Reward | Tribe / Hunt / Self? | **Hunt + Self** (chính), **Tribe** (phụ). |
| Investment | User bỏ lại gì? | Sở thích, ràng buộc ("≤4 điểm/ngày"), điểm yêu thích, lịch sử chuyến. |
| Next Trigger | Investment dẫn tới trigger tiếp theo thế nào? | Data đã lưu → push điểm kế tiếp (trong chuyến) & gợi ý chuyến mới (giữa chuyến). |
| User Impact | Habit này có thực sự có lợi cho user? | **Có** — hữu ích, tắt được, không spam ngoài chuyến, minh bạch & có Undo. |

## Hook flow — map lên prototype hiện có (nhịp trong chuyến)

> Không thêm UI mới; vòng Hook đã được thể hiện qua các màn có sẵn (`../index.html`).

```
Internal / External Trigger   → push "lịch hôm nay" / cảnh báo (T6 quá dày, T7 dữ liệu cũ)
  ↓                              [screen 04 warnbar · #r5done recovery links]
Action                        → mở & xem/điều chỉnh lịch hôm nay
  ↓                              [screen 04: chip lý do, chọn hướng sửa]
Variable Reward               → gợi ý điểm/quán phù hợp · phương án thay thế (Hunt) · lịch chạy mượt (Self)
  ↓                              [screen 04: before/after · screen 05 evidence of value]
Investment                    → ghi nhớ sở thích ("≤4 điểm/ngày"), điểm thích, lịch sử
  ↓                              [screen 04: "Ghi nhớ cho lịch sau?"]
Trigger cho vòng tiếp theo    → push điểm kế tiếp (trong chuyến) / gợi ý chuyến mới (giữa chuyến)
```

> Nếu câu trả lời là **không** → đừng ép habit loop giả tạo; quay lại `09-nature-vs-nurture.md`.
> Ở đây câu trả lời là **có nhưng chỉ trong chuyến** → áp Hook cho nhịp (A), dùng nurture cho nhịp (B).
