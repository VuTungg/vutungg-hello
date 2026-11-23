# BÀI LÀM PHA 2 (ĐỀ LUYỆN TẬP CHỦ ĐỀ TÀI CHÍNH CÁ NHÂN)

- **Họ tên:Vu Nam Tung**
- **Lớp:CNTT3**
- **Link repository Pha2:**
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):**

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đăng ký hội thảo ra JSON

**KET QUA AI**

````text
```json
[
  {
    "ma_goi": "CB",
    "ngay_hoi_thao": "2026-12-20",
    "nguoi_lon": 2,
    "tre_em": 1,
    "hang_ve": "thuong",
    "ghi_chu": "3 ghế ngồi cạnh nhau ở dãy bàn đầu gần màn hình chiếu"
  },
  {
    "ma_goi": null,
    "ngay_hoi_thao": null,
    "nguoi_lon": 0,
    "tre_em": 0,
    "hang_ve": null,
    "ghi_chu": null
  },
  {
    "ma_goi": null,
    "ngay_hoi_thao": null,
    "nguoi_lon": 0,
    "tre_em": 0,
    "hang_ve": null,
    "ghi_chu": null
  }
]

````

`````

**Link trò chuyện:https://share.gemini.google/T9mZ4JYQkUB4**

## 4.3. Báo giá vé hội thảo bằng Chain-of-Thought

**KET QUA AI**

````text
```python
adult_price = 1500000
adults = 4
adult_total = adults * adult_price

child_6_12 = 2
child_under_6 = 1
child_price = adult_price * 0.5
child_total = child_6_12 * child_price + child_under_6 * 0

ticket_total = adult_total + child_total

discount = ticket_total * 0.10 if adults >= 4 else 0
ticket_after_discount = ticket_total - discount

notebooks = 2
notebook_price = 200000
surcharge = notebooks * notebook_price

grand_total = ticket_after_discount + surcharge

print(f"{adult_total=}")
print(f"{child_total=}")
print(f"{ticket_total=}")
print(f"{discount=}")
print(f"{ticket_after_discount=}")
print(f"{surcharge=}")
print(f"{grand_total=}")


`````

```text
adult_total=6000000
child_total=1500000.0
ticket_total=7500000.0
discount=750000.0
ticket_after_discount=6750000.0
surcharge=400000
grand_total=7150000.0


```

| Hạng mục                 | Chi tiết / Đơn giá  | Thành tiền (đồng) |
| ------------------------ | ------------------- | ----------------- |
| Vé người lớn (Gói DT)    | 4 người × 1.500.000 | 6.000.000         |
| Vé trẻ em (6–12 tuổi)    | 2 trẻ × 750.000     | 1.500.000         |
| Vé trẻ em (dưới 6 tuổi)  | 1 bé × 0            | 0                 |
| **Tổng tiền vé**         |                     | **7.500.000**     |
| Giảm giá nhóm (10%)      | 10% × 7.500.000     | -750.000          |
| Tiền vé sau giảm         | 7.500.000 - 750.000 | 6.750.000         |
| Phụ thu sổ tay tài chính | 2 bộ × 200.000      | 400.000           |
| **Tổng cộng thanh toán** |                     | **7.150.000**     |

---

1. **Tiền người lớn:**

$$4 \times 1.500.000 = 6.000.000\text{ đồng}$$

2. **Tiền trẻ em:**

- 2 trẻ em (8 tuổi và 11 tuổi, thuộc nhóm 6–12 tuổi): $2 \times (1.500.000 \times 50\%) = 2 \times 750.000 = 1.500.000\text{ đồng}$
- 1 bé (4 tuổi, dưới 6 tuổi): $1 \times 0 = 0\text{ đồng}$
- Tổng tiền trẻ em: $1.500.000 + 0 = 1.500.000\text{ đồng}$

3. **Tiền vé:**

$$6.000.000 + 1.500.000 = 7.500.000\text{ đồng}$$

4. **Giảm giá nhóm:**
   Vì nhóm có 4 người lớn (đạt điều kiện từ 4 người lớn trở lên) nên được giảm 10% trên tiền vé:

$$7.500.000 \times 10\% = 750.000\text{ đồng}$$

Tiền vé sau giảm:

$$7.500.000 - 750.000 = 6.750.000\text{ đồng}$$

5. **Phụ thu sổ tay:**

$$2 \times 200.000 = 400.000\text{ đồng}$$

6. **Tổng tiền:**

$$6.750.000 + 400.000 = 7.150.000\text{ đồng}$$

[RESULT: 7.150.000 đồng]

````

**Link trò chuyện:https://share.gemini.google/KwWmRTnmWoHU**

### b) Kiểm tra kết quả AI

dung

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{
  "loai_su_co": "sai_khu_vuc",
  "so_khach": 2,
  "so_phien_bi_anh_huong": 2,
  "tom_tat": "Xếp sai khu vực ngồi thiếu bàn viết và ổ cắm sạc cho 2 khách trong 2 phiên đầu."
}
````

**Link trò chuyện:https://share.gemini.google/LnEGsymTXJAm**

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
| Tiêu chí | Điểm | Minh chứng | Đề xuất sửa |
| --- | --- | --- | --- |
| **Đúng thông tin (50%)** | 3.0 / 5.0 | **Trích nguyên văn:** *"Vé gói Đầu Tư bên em giá chỉ 1.200.000đ/người thôi"*, *"Anh/chị báo huỷ trước 4 ngày thì bên em hoàn lại đủ 100% tiền vé nha"*.<br>

<br>**Lý do sai:** Dữ liệu gốc chưa có văn bản quy định chuẩn của ban tổ chức để đối chiếu tính chính xác của mức giá 1.200.000đ và điều kiện hoàn tiền trước 4 ngày nên không đủ căn cứ chấm điểm tối đa. | Cần đối chiếu với bảng giá và quy định hoàn hủy chính thức của ban tổ chức để xác nhận hoặc điều chỉnh lại con số chính xác trước khi gửi khách hàng. |
| **Đầy đủ (30%)** | 1.5 / 3.0 | **Trích nguyên văn:** *"Anh/chị báo huỷ trước 4 ngày thì bên em hoàn lại đủ 100% tiền vé nha, cứ yên tâm chốt đơn đi ạ!"*<br>

<br>**Lý do sai:** Câu trả lời đã giải đáp được về giá vé và chính sách hủy vé, nhưng thiếu hoàn toàn phần kêu gọi hành động mời khách hàng cung cấp thông tin ngày tham dự hội thảo và số lượng vé muốn đăng ký. | *"Để hỗ trợ giữ chỗ sớm nhất, anh/chị vui lòng phản hồi giúp em ngày tham dự hội thảo và số lượng vé muốn đăng ký ạ."* |
| **Giọng điệu (20%)** | 0.5 / 2.0 | **Trích nguyên văn:** *"Dạ chào anh/chị nha!"*, *"nha"*, *"cứ yên tâm chốt đơn đi ạ!"*, *"đi học về đầu tư chứng khoán lời khủng luôn ạ."*<br>

<br>**Lý do sai:** Sử dụng nhiều từ ngữ suồng sã, thiếu chuyên nghiệp (*"nha"*, *"chốt đơn đi ạ"*); đồng thời đưa ra cam kết, hứa hẹn lợi nhuận quá đà (*"lời khủng luôn ạ"*), vi phạm nghiêm trọng chuẩn mực tư vấn tài chính. | *"Kính chào anh/chị. Vé gói Đầu Tư hiện có mức phí là 1.200.000đ/người, khóa học giúp anh/chị trang bị kiến thức và phương pháp đầu tư chứng khoán bài bản. Trường hợp anh/chị thông báo hủy trước 4 ngày, ban tổ chức sẽ hỗ trợ hoàn lại 100% phí tham dự."* |
| **Tổng điểm** | **5.0 / 10** |  |  |
```

**Link trò chuyện:https://share.gemini.google/aeYdXVdx0j3W**
