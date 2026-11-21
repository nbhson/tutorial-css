# 1. `flex-direction` — chọn trục chính

> **Tóm tắt tiếng Việt:** `flex-direction` quyết định trục chính (main axis) của flex container: `row` (ngang, mặc định), `column` (dọc), kèm `-reverse` để đảo hướng. Đổi trục là đổi luôn tác động của `justify-content` và `align-items` — đây là thuộc tính cần hiểu đầu tiên trong Flexbox.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*

## Giá trị

Mục này liệt kê 4 giá trị của `flex-direction` — đọc để chọn đúng "hướng dàn hàng" cho layout của mình.

> 📄 **Code ví dụ:** [`examples/01-gia-tri.css`](examples/01-gia-tri.css)

| Giá trị | Main axis | Dùng khi nào |
|---------|-----------|--------------|
| `row` | Ngang → | Navbar, danh sách nút (mặc định) |
| `row-reverse` | Ngang, ngược | Layout RTL, đưa item cuối lên đầu |
| `column` | Dọc ↓ | Danh sách dọc, card dọc |
| `column-reverse` | Dọc, ngược | Chat: tin mới nhất ở dưới nhưng muốn insert từ trên |

> **Cách đọc bảng này:** mỗi dòng là một giá trị, cột "Main axis" cho biết trục chính quay về hướng nào (mũi tên chỉ hướng item xếp), cột "Dùng khi nào" gợi ý tình huống thực tế. Hãy hình dung trục chính như trục conveyor: item luôn xếp dọc theo băng chuyền, còn `row` hay `column` chỉ là bạn xoay băng chuyền ngang hay dọc.

## Ví dụ

> 📄 **Code ví dụ:** [`examples/02-vi-du.html`](examples/02-vi-du.html)

> 📄 **Code ví dụ:** [`examples/03-vi-du.css`](examples/03-vi-du.css)

> 💡 **Điểm dễ nhầm nhất:** khi đổi `flex-direction: column` thì `justify-content` căn theo chiều **dọc** (main axis giờ là dọc), còn `align-items` căn theo chiều **ngang**. Hãy mở `index.html` trong thư mục này và đổi giá trị để thấy trực quan.

Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.

> **Tóm gọn 1 câu:** `flex-direction` là "xoay băng chuyền" — nó quyết định trục chính nằm ngang hay dọc, và mọi thuộc tính căn khác đều dựa theo trục đó.

## Tài liệu tham khảo

- [CSS-Tricks — A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [freeCodeCamp — CSS Flexbox Tutorial with Cheat Sheet](https://www.freecodecamp.org/news/css-flexbox-tutorial-with-cheatsheet/)
