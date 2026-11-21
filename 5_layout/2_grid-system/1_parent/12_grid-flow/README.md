# grid-auto-flow

> **🇻🇳 Tóm tắt:** `grid-auto-flow` điều khiển thuật toán **auto-placement** — cách Grid tự điền các item chưa được chỉ định vị trí. Giá trị: `row` (mặc định, đi theo hàng), `column` (theo cột), kèm `dense` để "lấp chỗ trống" bằng item nhỏ hơn.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*


If you have grid items that you don’t explicitly place on the grid, the auto-placement algorithm kicks in to automatically place the items. This property controls how the auto-placement algorithm works.

Giống như hướng dẫn nhân viên xếp hàng lên kệ: đi theo từng hàng trước (row) hay từng cột trước (column), và có chấp nhận "chèn vào chỗ trống phía trước" (dense) hay không — `grid-auto-flow` chính là mẩu hướng dẫn đó.

Values:
- row – tells the auto-placement algorithm to fill in each row in turn, adding new rows as necessary (default)
- column – tells the auto-placement algorithm to fill in each column in turn, adding new columns as necessary
- dense – tells the auto-placement algorithm to attempt to fill in holes earlier in the grid if smaller items come up later

> 📄 **Code ví dụ:** [`examples/01-grid-auto-flow.scss`](examples/01-grid-auto-flow.scss)

> **Cách đọc bảng này:** mỗi dòng là một "kiểu xếp hàng" của thuật toán auto-placement — đọc từ trên xuống để thấy mặc định là `row`, rồi so `column` khác gì, cuối cùng là option `dense` lấp chỗ trống.

> **Tóm gọn 1 câu:** `grid-auto-flow` là mẩu "hướng dẫn xếp kệ" — item chưa ai chỉ chỗ thì thuật toán tự điền theo hàng hay theo cột, và `dense` cho phép quay lại lấp các ô trống phía trước.
