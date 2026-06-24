# 01 — Customer Retention Canvas (Use Case)

> Bài 1 · §4–5. Nền tảng của retention: hiểu đúng **use case** và **persona** trước khi chọn metric.
> Chỉ chọn **MỘT use case chính** để phân tích sâu.

## Canvas

| Thành phần | Câu hỏi | Câu trả lời của nhóm |
|---|---|---|
| **The Problem** | Vấn đề bằng **lời của user** là gì? (không mô tả bằng tính năng) | *"Mỗi lần tự đi du lịch, tôi tốn nhiều giờ gom thông tin từ nhiều nguồn mà vẫn lo lịch không thực tế — quá dày, di chuyển lòng vòng, hoặc tới nơi mới biết quán đã đóng cửa."* |
| **The Persona** | Ai đang có vấn đề đó? (vai trò/hoàn cảnh, mục tiêu, kinh nghiệm, điều kiện đổi hành vi) | Khách **du lịch tự túc, 18–55 tuổi**, đi chuyến **ngắn 2–5 ngày** (vd Đà Nẵng 3 ngày), thường đi **theo cặp đôi hoặc nhóm bạn**. Quen dùng app/smartphone. **Mục tiêu:** có một lịch trình theo ngày khả thi mà vẫn tự kiểm soát & sửa được. **Điều kiện đổi hành vi:** đang trong giai đoạn chuẩn bị / đang đi một chuyến cụ thể. |
| **Anti-persona** | Ai **không** thuộc use case này? | Người đi **tour trọn gói** (đã có người lo lịch, không tự lập); **khách công tác** lịch cố định do công ty sắp; người **đi lại thường xuyên trong cùng một thành phố** (commuter — không cần lập kế hoạch chuyến). |
| **The Why** | Động lực cốt lõi / outcome user muốn đạt là gì? | Muốn một lịch trình **thực tế · đáng tin · sửa được** để **tận hưởng chuyến đi, ít stress, không sót/sai và không phí thời gian** — và **giữ quyền quyết định cuối cùng**. (Outcome, không lặp lại tên tính năng.) |
| **The Alternative** | Hiện họ giải quyết bằng cách nào khi chưa có sản phẩm? | Làm **thủ công**: search Google/blog review, hỏi bạn bè & nhóm Facebook/cộng đồng, xem YouTube/TikTok, ghi chú vào Notes/Google Sheets, ước lượng quãng đường & thời gian bằng Google Maps. |
| **The Frequency** | Vấn đề tự nhiên xuất hiện bao lâu một lần? | **Theo chuyến đi (bursty / mùa vụ)** — intensive, gần như **daily** trong vài ngày trước & trong chuyến, rồi **giảm mạnh về ~0 sau chuyến**. Số chuyến: **~5–8 chuyến/năm** → trung bình một chuyến **mỗi ~6–10 tuần**. ⚠️ **Cờ quan trọng:** base-frequency này **dưới ngưỡng weekly** của "habit zone" → KHÔNG ép thành habit hằng ngày; nên đo retention theo **window per-trip / hằng tháng–quý** (`03`) và dùng nurture giữa các chuyến (`09`). |

## Ghi chú hỗ trợ

**The Problem** — viết theo góc nhìn user, ví dụ kiểu: *"Tôi mất quá nhiều thời gian để… và vẫn thường…"*. Không viết "User cần một AI có dashboard thông minh".

**The Alternative** — có thể là: làm thủ công · spreadsheet · gọi/nhắn · Google · hỏi người khác · chấp nhận không giải quyết.

**The Frequency** — chọn & giải thích: nhiều lần/ngày · daily · weekly · monthly · quarterly · yearly · theo project/mùa vụ/không đều.
- Quan sát: user làm alternative bao lâu một lần?
- Frequency có đổi giữa các persona / theo giai đoạn use case không?

| Câu hỏi quan sát frequency | Trả lời |
|---|---|
| User thực hiện alternative bao lâu một lần? | Cũng theo chuyến — họ chỉ lục Google/hỏi nhóm khi sắp đi; ngoài chuyến gần như không làm. Khớp với nhịp bursty của vấn đề. |
| Frequency có thay đổi giữa các persona? | Có, nhưng persona chính (cặp đôi / nhóm bạn 18–55) khá đồng nhất: lập kế hoạch tương đối sát ngày, linh hoạt, ưu tiên trải nghiệm — nhịp ~5–8 chuyến/năm. |
| Frequency có thay đổi theo giai đoạn use case? | Có, rõ rệt: **trước chuyến** (lập kế hoạch) → cao; **trong chuyến** (điều chỉnh real-time, recovery T6/T7) → cao nhất; **sau chuyến** → ~0 cho tới chuyến kế tiếp. |
