# 02 — Core Action & Active User

> Bài 2 · §6–7. Core action là hành vi cho thấy user **thực sự nhận được value** — gắn trực tiếp với
> use case, gần với việc giải quyết vấn đề, quan sát được. **Không phải mọi click.**

## 6. Core Action

Ví dụ **không đủ**: mở app · đăng nhập · xem một màn hình · bấm bắt đầu nhưng chưa hoàn thành.

| Câu hỏi | Câu trả lời |
|---|---|
| Core job của use case là gì? | Có được một **lịch trình chuyến đi khả thi, đáng tin** mà user vẫn kiểm soát & sửa được. |
| Core action là gì? | **User chấp nhận lịch nháp** — bấm nút **"Dùng lịch này"** (event `itinerary_accepted`). |
| Vì sao action này cho thấy user nhận được value? | Chấp nhận = user xác nhận **lịch đủ tốt để dùng thật** → trực tiếp giải quyết nỗi lo "lịch không thực tế / quá dày / lòng vòng". Mở app, xem nháp, hay chỉ tạo nháp **chưa** chứng minh value (user có thể bỏ đi). |
| Khi nào action được tính là **đã xảy ra**? | Khi event `itinerary_accepted` ghi nhận trên một lịch có **≥1 ngày**. **Đếm 1 lần / lịch trình** (dedupe theo `itinerary_id`) → refresh, sửa rồi chấp nhận lại không tính trùng. |

## 7. Active User

Chỉ mở app **không** mặc định là active. Trả lời:

| Câu hỏi | Câu trả lời |
|---|---|
| Chỉ mở app có được tính active không? | **Không.** Mở app mà không có hành vi giá trị nào thì không tính. |
| User phải thực hiện core action nào? | Một **hành vi giá trị** (định nghĩa rộng, usage-inclusive): tạo / điều chỉnh / **chấp nhận** một lịch trình, **hoặc** mở & dùng lịch **trong chuyến** (xem/điều chỉnh lịch hôm nay, recovery T6/T7). |
| Cần thực hiện bao nhiêu lần? | **≥ 1 lần.** |
| Trong khoảng thời gian nào? | **30 ngày** (rolling). |

**Hoàn thành câu:**

> Một user được tính là **active** khi thực hiện **≥1 hành vi giá trị** (tạo / điều chỉnh / chấp nhận một lịch trình, hoặc mở & dùng lịch trong chuyến) trong **30 ngày**.

> **Lưu ý breadth ↔ strictness:** **Core action** (chấp nhận lịch) là tín hiệu value **chặt**; định
> nghĩa **active-user** ở đây cố ý **rộng hơn** để bắt cả engagement trong chuyến (in-trip) — phù hợp
> nhịp bursty 5–8 chuyến/năm. **Chỉ dùng MỘT định nghĩa active-user (rộng) này** — không thêm metric
> "core-active" hẹp riêng, vì tín hiệu "đã chấp nhận lịch" đã được phản ánh qua **Activation Rate**
> (`05`) và **Trip-to-trip retention** (`03`); thêm nữa sẽ trùng lặp.
