# 2. `justify-content` — căn theo trục chính

> **Tóm tắt tiếng Việt:** `justify-content` căn phân bố các item **dọc theo main axis** của flex container. `flex-start` dồn về đầu, `center` căn giữa, `space-between` dàn đều (2 đầu sát mép), `space-around`/`space-evenly` thêm khoảng đệm ở mép. Đây là cách "dàn hàng" phổ biến nhất trong Flexbox.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*

## Các giá trị thường dùng

Mục này liệt kê 6 giá trị phổ biến của `justify-content` — đọc để biết cách "dàn hàng" item dọc theo trục chính.

> 📄 **Code ví dụ:** [`examples/01-cac-gia-tri-thuong-dung.css`](examples/01-cac-gia-tri-thuong-dung.css)

| Giá trị | Hiệu ứng |
|---------|----------|
| `flex-start` | Dồn về đầu trục chính (default) |
| `flex-end` | Dồn về cuối trục chính |
| `center` | Căn giữa trục chính |
| `space-between` | Item đầu sát mép, item cuối sát mép, khoảng trống chia đều giữa |
| `space-around` | Mỗi item có "làn" khoảng trống hai bên — mép bằng nửa khoảng giữa |
| `space-evenly` | Mọi khoảng trống bằng nhau |

> **Cách đọc bảng này:** mỗi dòng là một giá trị, cột "Hiệu ứng" mô tả khoảng trống đi đâu. Hãy hình dung các item như người ngồi trên ghế băng dài: `flex-start` là dồn về một đầu băng, `space-between` là giãn đều bỏ hai đầu trống, `space-around` là ai cũng được "khu vực riêng" hai bên, còn `space-evenly` là khoảng cách đều tăm tắp từ đầu đến cuối.

## Ví dụ thực tế

> 📄 **Code ví dụ:** [`examples/02-vi-du-thuc-te.css`](examples/02-vi-du-thuc-te.css)

Mở `index.html` trong thư mục này, đổi từng giá trị trong `styles/style.css` để so sánh trực quan.

Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.

> **Tóm gọn 1 câu:** `justify-content` là cách "dàn người trên ghế băng" — dồn một đầu, căn giữa, hay chia khoảng trống đều nhau tùy giá trị bạn chọn.

## Tài liệu tham khảo

- [CSS-Tricks — A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [freeCodeCamp — CSS Flexbox Tutorial with Cheat Sheet](https://www.freecodecamp.org/news/css-flexbox-tutorial-with-cheatsheet/)
