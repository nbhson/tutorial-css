# 5. `align-self` — căn riêng cho một item

> **Tóm tắt tiếng Việt:** `align-self` ghi đè `align-items` của container **cho riêng một item**. Nhận cùng tập giá trị (`auto`, `flex-start`, `center`, `flex-end`, `stretch`, `baseline`). Dùng khi muốn 1 item lệch khỏi căn chung, ví dụ avatar thò xuống dưới trong thanh chat.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*

## Cú pháp

Mục này giới thiệu `align-self` và tập giá trị nó nhận — giống hệt `align-items`, nhưng áp cho **một item duy nhất**.

> 📄 **Code ví dụ:** [`examples/01-cu-phap.css`](examples/01-cu-phap.css)

| Giá trị | Hiệu ứng |
|---------|----------|
| `auto` | Kế thừa `align-items` của container (default) |
| `flex-start` / `flex-end` | Dồn về đầu/cuối trục phụ |
| `center` | Căn giữa trục phụ |
| `stretch` | Giãn lấp đầy trục phụ |
| `baseline` | Căn theo baseline chữ |

> **Cách đọc bảng này:** mỗi dòng là một giá trị của `align-self`; cách đọc là so với `align-items` — bảng này y hệt, chỉ khác là bạn đặt nó lên **từng item riêng** thay vì cả container. Ví von: nếu `align-items` là đồng phục cả lớp thì `align-self` là việc một học sinh xin mặc khác đồng phục.

## Ví dụ

> 📄 **Code ví dụ:** [`examples/02-vi-du.css`](examples/02-vi-du.css)

> 💡 Trong flexbox không có `justify-self` — muốn đẩy 1 item sang tận cùng theo main axis, dùng `margin-left: auto` hoặc `align-self` khi trục phù hợp. Mở `index.html` để thử.

Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.

> **Tóm gọn 1 câu:** `align-self` là "xin khác đồng phục" — cùng bộ giá trị với `align-items` nhưng chỉ áp cho một item duy nhất.

## Tài liệu tham khảo

- [CSS-Tricks — A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [freeCodeCamp — CSS Flexbox Tutorial with Cheat Sheet](https://www.freecodecamp.org/news/css-flexbox-tutorial-with-cheatsheet/)
