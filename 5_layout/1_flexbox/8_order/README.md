# 8. `order` — đổi thứ tự hiển thị

> **Tóm tắt tiếng Việt:** `order` thay đổi thứ tự **hiển thị** của item trong flex container mà không cần sửa HTML. Mặc định mọi item có `order: 0`; item có `order` nhỏ hơn hiện trước. ⚠️ Chỉ đổi hình ảnh trực quan — thứ tự đọc của screen reader và tab focus vẫn theo HTML.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*

Hãy hình dung hàng đợi ra vào: ai có "số thứ tự" nhỏ hơn thì lên trước, còn ai bằng nhau thì cứ giữ vị trí ban đầu. `order` hoạt động y hệt — bạn không phải dời ai trong hàng HTML, chỉ cấp lại con số để màn hình xếp lại.

## Cú pháp

Mục này nói về cách `order` nhận giá trị số và quy tắc sắp xếp khi các item bằng điểm nhau.

> 📄 **Code ví dụ:** [`examples/01-cu-phap.css`](examples/01-cu-phap.css)

| Giá trị | Hiệu ứng |
|---------|----------|
| Số nguyên (âm/0/dương) | Sắp theo tăng dần; items cùng `order` giữ thứ tự theo HTML |
| `0` (mặc định) | Giữ nguyên thứ tự HTML |

> **Cách đọc bảng này:** đọc từ trên xuống theo cột "Giá trị" — dòng đầu là cách cấp số để sắp lại, dòng hai nhắc bạn rằng không làm gì cả thì mọi item đều `0`. Nhớ thêm: điểm bằng nhau → về vị trí cũ theo HTML.

## Ví dụ

Mục này đưa tình huống thực tế để bạn thấy `order` "nhích" một item lên/xuống chỉ bằng một dòng CSS.

> 📄 **Code ví dụ:** [`examples/02-vi-du.css`](examples/02-vi-du.css)

> ⚠️ **Cảnh báo accessibility:** đừng dùng `order` để "vá" thứ tự HTML sai. Screen reader và phím Tab đi theo DOM, không theo hình ảnh hiển thị. Thứ tự HTML nên là thứ tự logic; `order` chỉ dùng cho điều chỉnh layout nhỏ. Mở `index.html` để thử.

> **Tóm gọn 1 câu:** `order` như cấp lại số thứ tự trong hàng đợi — màn hình xếp theo điểm, nhưng screen reader và Tab vẫn đi theo hàng thật của HTML.

Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.

## Tài liệu tham khảo

- [CSS-Tricks — A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [freeCodeCamp — CSS Flexbox Tutorial with Cheat Sheet](https://www.freecodecamp.org/news/css-flexbox-tutorial-with-cheatsheet/)
