# 10 — Hook Model Review

> Bài 5 · §14–15. Chỉ thiết kế habit loop **sau khi** đã hiểu natural frequency.
> Nếu hành vi xảy ra **ít hơn weekly**, habit khó hình thành — **không ép** use case frequency thấp
> thành hành vi hằng ngày.

## 14.1. Kiểm tra sản phẩm có thực sự cần habit không

| Câu hỏi | Trả lời |
|---|---|
| Vì sao business/user cần hành vi này thành habit? | |
| Vấn đề nào của user đang được giải quyết? | |
| Hành vi cụ thể nào muốn được lặp lại? | |
| Hành vi đó tự nhiên xuất hiện với frequency nào? | |
| Sản phẩm có đủ frequency / perceived utility để vào habit zone? | |

## Trigger

- External trigger có thể là: paid · earned · relationship · owned.
- Dùng **5 Whys** để tìm 3 internal trigger có thể có, rồi chọn cái xảy ra thường xuyên nhất.

**Hoàn thành câu:** Mỗi khi user **\_\_\_\_\_\_\_\_** (internal trigger), họ sẽ **\_\_\_\_\_\_\_\_** (hành vi muốn tạo).

## Action (Motivation + Ability + Trigger)

| Bước | Trả lời |
|---|---|
| Số bước từ internal trigger → outcome | |
| Rào cản đang làm giảm Ability | |
| 3 cách có thể kiểm thử để action dễ hơn | |

Loại rào cản (Fogg): Time · Brain cycles · Money · Physical effort · Social deviance · Non-routine.

## Variable Reward

The Tribe (kết nối/công nhận) · The Hunt (tìm tài nguyên/thông tin) · The Self (làm chủ/tiến bộ).

| Câu hỏi | Trả lời |
|---|---|
| Reward nào giải quyết nhu cầu/pain của user? | |
| User thấy điều gì thỏa mãn/hữu ích/đáng khích lệ? | |
| Thuộc loại nào (Tribe/Hunt/Self)? | |
| Reward phục vụ core action hay chỉ gamification gắn thêm? | |

## Investment

| Câu hỏi | Trả lời |
|---|---|
| User đầu tư điều gì? | |
| Lưu value dưới dạng gì (content/data/followers/reputation/skill)? | |
| Tạo value cho lần sử dụng sau thế nào? | |
| Tạo / "load" trigger tiếp theo ra sao? | |
| Sau bao lâu trigger tiếp theo xuất hiện? | |

## 14.6. Kiểm tra tác động lên user

- [ ] Thành viên nhóm có sẵn sàng dùng cơ chế này không?
- [ ] Hành vi thiết kế có thực sự cải thiện cuộc sống/công việc của user không?
- [ ] Cơ chế có làm user mất kiểm soát / bị làm phiền / hành vi ngoài ý muốn không?

## 15. Hook Review — bảng tổng hợp

| Thành phần | Câu hỏi | Trả lời |
|---|---|---|
| Why Habit? | Vì sao cần thành habit? | |
| Intended Behavior | Hành vi cụ thể cần lặp lại? | |
| Frequency & Utility | Đủ thường xuyên / hữu ích để thành habit? | |
| Internal Trigger | Nhu cầu/cảm xúc xuất hiện thường xuyên nhất? | |
| External Trigger | Trigger đúng nơi đúng lúc? | |
| Action | Hành vi đơn giản nhất để nhận reward? | |
| Motivation | User muốn thực hiện vì điều gì? | |
| Ability | Rào cản nào cần loại bỏ? | |
| Variable Reward | Tribe / Hunt / Self? | |
| Investment | User bỏ lại gì? | |
| Next Trigger | Investment dẫn tới trigger tiếp theo thế nào? | |
| User Impact | Habit này có thực sự có lợi cho user? | |

## Hook flow (sửa trực tiếp trên prototype)

```
Internal / External Trigger
  ↓
Action
  ↓
Variable Reward
  ↓
Investment
  ↓
Trigger cho vòng tiếp theo
```

> Nếu câu trả lời là **không** → đừng ép habit loop giả tạo; quay lại `09-nature-vs-nurture.md`.
