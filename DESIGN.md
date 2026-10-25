# DESIGN.md — Landing page quán trà đạo Tĩnh Trà (MSR-36)

Tài liệu thiết kế chốt cho sprint TEC-276. Dev (TEC-278) dựng đúng tài liệu này, không tự thêm màu, font hay khối ngoài danh sách. QA (task QA của sprint) đối chiếu bản dựng với tài liệu này.

## 1. Tổng quan

- Sản phẩm: landing page 1 trang cho quán trà đạo Tĩnh Trà, Hà Nội.
- Mục tiêu: khách vào là thấy ngay không gian tĩnh lặng và đặt được chỗ cho buổi thưởng trà — ảnh là nội dung chính, chữ ít, khoảng trắng nhiều.
- Phong cách tham chiếu duy nhất: **wabi-sabi kiểu nhà trà Kyoto** — mộc mạc, tĩnh lặng, tinh tế, không cầu kỳ, không bóng bẩy kiểu thương mại.

## 2. Bảng màu (chỉ dùng đúng 6 mã hex này)

| Mã hex | Vai trò |
|---|---|
| `#F7F1E3` | Nền chính toàn trang (giấy ấm) |
| `#EFE6D0` | Nền khối phụ (thẻ buổi trà, khối bộ sưu tập) |
| `#2B2620` | Chữ chính (nâu đen) |
| `#6B5F4E` | Chữ phụ (mô tả, chú thích, giá mẫu ghi chú) |
| `#3E5C3A` | Nhấn chính (xanh trà đậm): tiêu đề khối, nút đặt chỗ, link, hover |
| `#D8C9A8` | Viền, đường kẻ phân tách khối |

Quy tắc: nền luôn sáng ấm; màu nhấn `#3E5C3A` chỉ dùng cho tiêu đề, nút và điểm nhấn nhỏ — không làm nền khối lớn. Không dùng màu nào ngoài 6 mã trên.

## 3. Font chữ

- Tiêu đề: **Cormorant Garamond** (serif, thanh mảnh, hợp khí chất trà đạo).
- Nội dung: **Be Vietnam Pro** (dễ đọc tiếng Việt có dấu).
- Cỡ chữ desktop: H1 hero 64px / H2 khối 40px / H3 24px / body 17px, line-height 1.7.
- Cỡ chữ mobile: H1 40px / H2 30px / H3 20px / body 16px.
- Breakpoint: 768px (dưới 768px xếp 1 cột).

## 4. Quy tắc hình ảnh (ảnh mẫu)

- Ảnh là nội dung chính, bố cục ảnh lớn + nhiều khoảng trắng (visual-first).
- Tông ảnh: đồng tông ấm/tối — gỗ tối, ánh sáng ấm, hơi trà, không gian tĩnh; ảnh màu sáng phẳng kiểu sàn thương mại điện tử bị cấm.
- Tỉ lệ khung:
  - Hero: 16:9, toàn màn hình, cảnh rót trà.
  - Khối triết lý + không gian: ảnh ngang 3:2 xen kẽ chữ, không xếp lưới đều.
  - Bộ sưu tập trà và ấm chén: ảnh vuông 1:1, lưới lệch editorial (không đều tăm tắp).
  - Buổi thưởng trà: ảnh 4:3.
- Tất cả ảnh trên trang là **ảnh mẫu** (chưa phải ảnh thật của quán); ghi rõ trong comment kết quả của Dev.
- Tổng số ảnh mẫu: 8–10 ảnh.

## 5. Bố cục — đúng 6 khối, theo thứ tự

1. **Hero**: ảnh toàn màn hình cảnh rót trà + tên quán "Tĩnh Trà" (Cormorant Garamond 64px) + 1 câu ngắn về trà đạo + nút "Đặt chỗ" (nền `#3E5C3A`, chữ `#F7F1E3`).
2. **Triết lý trà đạo + không gian**: 2–3 đoạn ngắn về triết lý (tĩnh, chậm, trọn vẹn) xen ảnh không gian gỗ tối ánh sáng ấm.
3. **Các buổi thưởng trà**: 3 buổi mẫu, mỗi buổi có tên, thời lượng, mô tả ngắn và giá ghi rõ "Giá mẫu": 250.000đ, 350.000đ, 450.000đ/người.
4. **Bộ sưu tập trà và ấm chén thủ công**: lưới lệch editorial, mỗi món có tên + ghi chú ngắn; giá (nếu có) ghi "Giá mẫu".
5. **Lịch buổi trà trong tuần**: bảng lịch 7 ngày đơn giản (ngày, giờ, buổi); giờ và nội dung là mẫu, chưa phải lịch thật.
6. **Form đặt chỗ**: các trường họ tên, số điện thoại, ngày mong muốn, buổi quan tâm, ghi chú. **CHỈ giao diện** (preventDefault, không gửi dữ liệu thật, không backend, không thanh toán). Kèm ghi chú: "Form hiện chỉ nhận thông tin hiển thị — chưa gửi đi thật."

## 6. Thông tin thật — placeholder

- Địa chỉ, số điện thoại, giờ mở cửa thật, tên người phụ trách: **[CẦN BỔ SUNG]** ở mọi vị trí xuất hiện (hero footer, form, cuối trang). Không bịa số liệu thật.
- Toàn bộ giá trên trang là **giá mẫu**, phải ghi rõ chữ "Giá mẫu" cạnh giá.

## 7. Điều cấm

- Không dùng template bán hàng phổ thông, lưới thẻ đều tăm tắp, icon stock.
- Không thêm màu, font hay khối ngoài danh sách trên.
- Không có nút "mua ngay", giỏ hàng, thanh toán online.
- Không dùng ảnh sáng phẳng kiểu sàn thương mại điện tử, không dùng ảnh AI méo mó tay/chén.
