## 🧠 Đếm số lượng ký số bằng Dictionary Comprehension 

### 🎯 **Yêu cầu:**
Viết chương trình cho người dùng **nhập vào một số n** (có thể là số âm hoặc số thực).  
Sử dụng **dictionary comprehension** để:

1. **Đếm số lần xuất hiện của từng ký số** trong n (chỉ tính các chữ số từ 0 đến 9).
2. **Loại bỏ** các ký tự không phải là chữ số như:
   - Dấu trừ `-` (nếu là số âm)
   - Dấu chấm `.` (nếu là số thực)

3. **Chỉ in ra các chữ số có xuất hiện**, theo **thứ tự tăng dần**.
4. **Xác định chữ số xuất hiện nhiều nhất** (có thể có nhiều chữ số cùng tần suất cao nhất).

---
```lua

                   ┌──────────────────────────┐
                   │       Bắt đầu chương trình │
                   └───────────────┬──────────┘
                                   │
                                   ▼
                   ┌──────────────────────────┐
                   │ Nhập số n từ người dùng   │
                   └───────────────┬──────────┘
                                   │
                                   ▼
                   ┌──────────────────────────┐
                   │ Loại bỏ ký tự không phải │
                   │ số (dấu '-' và '.')      │
                   └───────────────┬──────────┘
                                   │
                                   ▼
                   ┌──────────────────────────┐
                   │ Tạo dictionary bằng      │
                   │ dict comprehension để đếm│
                   │ số lần xuất hiện từng ký │
                   │ số 0-9                   │
                   └───────────────┬──────────┘
                                   │
                                   ▼
                   ┌──────────────────────────┐
                   │ In các chữ số đã xuất    │
                   │ hiện theo thứ tự tăng dần│
                   └───────────────┬──────────┘
                                   │
                                   ▼
                   ┌──────────────────────────┐
                   │ Tìm tần suất xuất hiện    │
                   │ nhiều nhất (max)          │
                   └───────────────┬──────────┘
                                   │
             ┌─────────────────────┴──────────────────────┐
             │                                            │
             ▼                                            ▼
 ┌────────────────────────────┐                 ┌────────────────────────────┐
 │ Chỉ có 1 chữ số max        │                 │ Có nhiều chữ số cùng max   │
 │ xuất hiện nhiều nhất       │                 │ xuất hiện nhiều lần        │
 │ → In chữ số và số lần      │                 │ → In tất cả chữ số và số   │
 └────────────────────────────┘                 │ lần                         │
                                                └────────────────────────────┘
             │
             ▼
       ┌──────────────┐
       │ Kết thúc chương│
       │ trình         │
       └──────────────┘
```