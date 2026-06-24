# 09 — Nature vs Nurture

> Bài 5 · §13. **Nature** = nhịp nhu cầu tự nhiên của user. **Nurture** = những gì sản phẩm/team chủ
> động làm để nuôi & khuếch đại nhịp đó. **Nurture không tạo nhu cầu từ số 0.**

## Nature
- Vấn đề xảy ra bao lâu một lần? **~5–8 lần/năm** (mỗi ~6–10 tuần), dạng **bursty**: dồn trước & trong chuyến, ~0 sau chuyến.
- User tự nhiên quay lại với loại sản phẩm này theo nhịp nào? Theo **chuyến đi** — quay lại khi có chuyến mới; **trong chuyến** thì dùng gần như **hằng ngày**.
- Nhịp đó khác nhau giữa persona / use case ra sao? Persona chính (cặp đôi/nhóm bạn 18–55) khá đồng nhất; khác chủ yếu theo **giai đoạn** (trước / trong / sau chuyến) hơn là giữa các persona.

## Nurture (onboarding · notification · email reminder · content · CRM · in-product trigger)

| Nội dung | Câu trả lời |
|---|---|
| Natural frequency của use case | ~5–8 chuyến/năm (bursty); daily **trong** chuyến. |
| Internal trigger | "Sắp/đang muốn một chuyến đi" + lo "lịch không thực tế / quá dày"; **trong chuyến:** "tới lúc quyết định điểm/giờ tiếp theo mà phân vân". |
| External trigger hiện có | **Trong chuyến:** push "lịch hôm nay", cảnh báo điểm quá dày (T6) / dữ liệu cũ (T7). **Giữa các chuyến:** email/nội dung gợi ý điểm đến. |
| Một hoạt động nurture phù hợp | **Giữa chuyến:** content gợi ý điểm đến theo mùa + "lưu ý tưởng du lịch". **Trong chuyến:** nhắc lịch hôm nay & đề xuất điều chỉnh đúng lúc. |
| Vì sao nurture **không quá dày hoặc quá thưa**? | **Không spam ngoài chuyến** (user không có nhu cầu → dày sẽ gây churn/opt-out); **dày hợp lý trong chuyến** vì đúng nhu cầu daily. Nurture **khuếch đại** nhịp tự nhiên, không tạo nhu cầu giả. |
| Metric dùng để theo dõi tác động | Trip-to-trip retention (120 ngày) · in-trip engagement · notification opt-out rate. |

> Nếu core use case có **frequency thấp**, có thể cân nhắc hành vi/use case liên quan có frequency
> cao hơn để duy trì sự hiện diện — **không** giả định user dùng hằng ngày một cách gượng ép.
> _(Ví dụ lab — Zillow: mua/bán nhà rất thưa; Zestimate + content tạo điểm chạm thường xuyên hơn.)_

Hành vi liên quan tần suất cao hơn (nếu có): **"Lưu ý tưởng / cảm hứng du lịch"** giữa các chuyến —
user lưu điểm đến, bộ sưu tập, đọc gợi ý theo mùa. Tần suất cao hơn lập-lịch-trọn-chuyến, giúp duy
trì hiện diện & "load" trigger cho chuyến kế tiếp (giống Zillow dùng Zestimate/content giữa các lần
mua–bán nhà). **Không** vì vậy giả định user lập lịch hằng ngày.
