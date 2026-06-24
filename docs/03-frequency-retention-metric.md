# 03 — Natural Frequency → Retention Metric

> Bài 2 · §8. Retention trả lời: *sau một khoảng thời gian, còn bao nhiêu user quay lại?*
> **Không mặc định** chọn D1/D7/D30 — chọn nhịp đo theo **natural frequency** của use case.
> **Không copy** DAU/WAU/MAU/D7 từ sản phẩm khác.

## Bảng tham chiếu (lab) — frequency → metric có thể cân nhắc

| Natural frequency | Metric có thể cân nhắc |
|---|---|
| Daily | DAU · D1/D7/D30 Retention · DAU/WAU hoặc DAU/MAU |
| Weekly | WAU · weekly cohort retention · WAU/MAU |
| Monthly | MAU · monthly cohort retention |
| Quarterly / yearly / không đều | Window phản ánh lần xuất hiện tự nhiên tiếp theo; **không ép** daily retention |

## Lựa chọn của nhóm

| Thành phần | Câu trả lời |
|---|---|
| Persona và use case | Khách du lịch tự túc 18–55, cặp đôi/nhóm bạn — **lập & điều chỉnh lịch trình cho một chuyến đi ngắn** (xem `01`). |
| Natural frequency | **~5–8 chuyến/năm** (mỗi ~6–10 tuần), dạng **bursty**: intensive trước & trong chuyến, ~0 sau chuyến. |
| Core action | **Chấp nhận lịch nháp** (`itinerary_accepted`) — xem `02`. |
| Active user definition | Usage-inclusive: ≥1 hành vi giá trị (tạo/điều chỉnh/chấp nhận lịch, hoặc dùng lịch trong chuyến) trong **30 ngày** — xem `02`. |
| Retention metric đã chọn | **Headline — Trip-to-trip retention:** % user quay lại lập/chấp nhận một chuyến **kế tiếp** trong **120 ngày** (~4 tháng — đủ bao quát lần xuất hiện tự nhiên tiếp theo của nhịp 5–8 chuyến/năm). **Hỗ trợ (engagement) — MAU + monthly cohort retention + stickiness** trong mùa có chuyến (khớp active-user 30 ngày). ❌ **Không** dùng D1/D7 daily retention làm thước đo chính. |
| Vì sao metric phù hợp với frequency? | Use case 5–8 lần/năm → ép daily/weekly retention sẽ sai lệch (đúng cảnh báo lab). **Trip-to-trip** phản ánh đúng value loop "quay lại khi có chuyến mới"; **monthly cohort/MAU** phản ánh engagement trong & quanh chuyến. ⚠️ **Tension có chủ đích:** active window = 30 ngày nhưng nhịp chuyến ~6–10 tuần → monthly retention **tự nhiên thấp**; hai metric trả lời **hai câu hỏi khác nhau** (engagement vs quay lại dùng lại), không mâu thuẫn. Điểm này nối sang Nature/Nurture (`09`) và North Star (`08`). |
