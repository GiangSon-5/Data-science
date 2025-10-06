
### 🧮 CÂU 1: Dãy cấp số nhân bằng List Comprehension

**Yêu cầu:**

1. Nhập 2 số nguyên `n` và `a`, cách nhau bởi dấu phẩy:
   - Cả hai phải là **số nguyên dương**.
   - **Ước số chung lớn nhất (USCLN)** của `n` và `a` phải là **bội số của 5**.
   - Ví dụ hợp lệ: `n = 20`, `a = 15` → USCLN = 5 ✅

2. Kiểm tra kiểu dữ liệu:
   - `n` và `a` phải là **số nguyên**, không được là:
     - Chuỗi ký tự (ví dụ: `'Sài gòn 5'`) ❌
     - Số thực (ví dụ: `3.14`) ❌
   - Nếu nhập sai, **yêu cầu nhập lại cả hai số**.

3. Nếu nhập đúng, cho nhập tiếp giá trị của `q` (công bội):
   - Không cần kiểm tra kiểu dữ liệu của `q`.

4. In ra **dãy cấp số nhân gồm `n` số**, bắt đầu từ `a`, công bội là `q`:
   - Sử dụng **list comprehension**.

---




---

## 🧮 Tên bài: *Dãy cấp số nhân bằng List Comprehension*

### 1️⃣ Về **mặt toán học**

Một **cấp số nhân (geometric sequence)** là dãy số mà **mỗi số sau** bằng **số trước nhân với một hằng số gọi là công bội** `q`.

> Ví dụ:
> Nếu `a = 2`, `q = 3`, `n = 5`
> thì dãy là:
> 2, 6, 18, 54, 162

Vì:

```
số 1 = a = 2
số 2 = a * q = 2 * 3 = 6
số 3 = a * q^2 = 2 * 3^2 = 18
số 4 = a * q^3 = 2 * 3^3 = 54
số 5 = a * q^4 = 2 * 3^4 = 162
```

Công thức tổng quát:

$$
x_i = a \times q^{i-1} \quad \text{với } i = 1 \ldots n
$$

---

### 2️⃣ Về **yêu cầu nhập liệu**

Người dùng sẽ nhập 2 số đầu tiên `n` và `a`, cách nhau bởi dấu phẩy (`,`).

* `n`: số phần tử trong dãy.
* `a`: phần tử đầu tiên.

Ví dụ nhập:

```
20,15
```

→ `n = 20`, `a = 15`

Nhưng:

* Cả `n` và `a` phải là **số nguyên dương**.
* **USCLN (Ước số chung lớn nhất)** của `n` và `a` phải là **bội số của 5**.

> Ví dụ:
>
> * `n = 20`, `a = 15` → USCLN = 5 ✅ (vì 5 là bội số của 5)
> * `n = 30`, `a = 45` → USCLN = 15 ✅ (vì 15 chia hết cho 5)
> * `n = 12`, `a = 18` → USCLN = 6 ❌ (6 không chia hết cho 5)

Nếu người dùng nhập sai:

* Số âm ❌
* Không phải số nguyên ❌
* Không đúng định dạng (ví dụ `"Sài gòn 5"`, `"3.14, 2"`) ❌
  → thì phải yêu cầu nhập lại.

---

### 3️⃣ Nhập giá trị công bội `q`

Sau khi `n` và `a` hợp lệ, người dùng nhập thêm `q`.
Không cần kiểm tra kiểu dữ liệu (chỉ cần Python đọc được).

---

### 4️⃣ In ra dãy cấp số nhân bằng **List Comprehension**

Thay vì dùng vòng lặp `for`, ta dùng cú pháp ngắn gọn:

```python
geometric_sequence = [a * (q ** i) for i in range(n)]
```

Trong đó:

* `range(n)` tạo ra các giá trị từ `0 → n-1`
* `q ** i` là `q` mũ `i`
* Mỗi phần tử là `a * q^i`

Ví dụ:

```
a = 2, q = 3, n = 5
→ [2*3^0, 2*3^1, 2*3^2, 2*3^3, 2*3^4]
→ [2, 6, 18, 54, 162]
```

---

```lua
             ┌────────────────────────────┐
             │   Bắt đầu chương trình     │
             └────────────┬───────────────┘
                          │
                          ▼
             ┌────────────────────────────┐
             │ Nhập n, a (cách nhau bằng ,)│
             └────────────┬───────────────┘
                          │
                          ▼
             ┌────────────────────────────┐
             │  Chuyển n, a sang kiểu int │
             └────────────┬───────────────┘
                          │
                ┌─────────┴──────────┐
                │ Có lỗi ValueError? │
                └───────┬────────────┘
                        │ Có
                        ▼
           ┌──────────────────────────┐
           │ Báo lỗi: "Nhập sai định  │
           │ dạng. Nhập lại n, a."    │
           └──────────┬───────────────┘
                      │
                      └───────────────┐
                                      │ Không
                                      ▼
                      ┌───────────────────────────┐
                      │ n > 0 và a > 0 ?          │
                      └───────────┬───────────────┘
                                  │ Có
                                  ▼
                      ┌───────────────────────────┐
                      │ Tính USCLN(n, a) (thuật   │
                      │ toán Euclid tự viết)      │
                      └───────────┬───────────────┘
                                  │
                                  ▼
                      ┌───────────────────────────┐
                      │ USCLN % 5 == 0 ?          │
                      └───────────┬───────────────┘
                          │ Có           ▲       │ Không
                          ▼              │       ▼
             ┌────────────────────┐   ┌───────────────────────────────────────────┐
             │ Nhập giá trị q     │   │ Báo lỗi: "USCLN phảilà bội số của 5."     │
             └───────┬────────────┘   │             Nhập lại n,a                  │
                     │                └───────────────────────────────────────────┘
                     ▼                           
     ┌──────────────────────────────┐            
     │ Tạo dãy: [a * (q**i) for i   │
     │ in range(n)] (List Comp.)    │
     └───────────┬──────────────────┘
                 │
                 ▼
     ┌──────────────────────────────┐
     │ In ra dãy cấp số nhân        │
     └───────────┬──────────────────┘
                 │
                 ▼
         ┌───────────────────┐
         │  Kết thúc chương  │
         │      trình         │
         └───────────────────┘

```
