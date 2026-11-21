# grid-template-areas

> **🇻🇳 Tóm tắt:** `grid-template-areas` "vẽ" layout bằng tên vùng — mỗi dòng chuỗi là một hàng, mỗi tên là một ô. Dễ đọc nhất trong Grid: nhìn chuỗi là thấy ngay cấu trúc trang. Item được gán vào vùng bằng `grid-area: <tên>`.
>
> *Nội dung gốc bên dưới (phần đầu đã dịch tiếng Việt) — tham khảo thêm.*


Xác định mẫu lưới bằng cách tham chiếu tên của các vùng lưới được chỉ định bằng thuộc tính khu vực lưới (đại khái là xác định được element trên html bằng cách đặt tên với areas)

Ví von: đây là cách "vẽ sơ đồ mặt bằng bằng chữ" — mỗi dòng chuỗi là một hàng, mỗi tên là một ô; nhìn vào chuỗi là thấy ngay bố cục trang, như đọc bản đồ tầng của tòa nhà.

Việc lặp lại tên của vùng lưới sẽ khiến nội dung trải rộng trên các ô đó. Dấu chấm biểu thị một ô trống. Bản thân cú pháp cung cấp một hình ảnh trực quan về cấu trúc của lưới.

Values:

- <grid-area-name> – the name of a grid area specified with grid-area
- . – a period signifies an empty grid cell
none – no grid areas are defined

> **Cách đọc bảng này:** 3 dòng ứng với 3 "con dấu" bạn được phép dùng khi vẽ sơ đồ — tên vùng để gán chỗ, dấu `.` để chừa ô trống, và `none` để xóa sạch sơ đồ.

> 📄 **Code ví dụ:** [`examples/01-grid-template-areas.scss`](examples/01-grid-template-areas.scss)

> **Tóm gọn 1 câu:** `grid-template-areas` là bản đồ mặt bằng viết bằng chữ — tên vùng là phòng, dấu chấm là chỗ để trống, lặp tên là nới phòng sang ô liền kề.
