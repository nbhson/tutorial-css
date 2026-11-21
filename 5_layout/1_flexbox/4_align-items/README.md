# 4. `align-items` — căn từng item theo trục phụ

> **Tóm tắt tiếng Việt:** `align-items` căn các item **theo cross axis** (trục vuông góc với main axis). Đây là thuộc tính của "căn giữa theo chiều dọc" kinh điển: `display: flex; align-items: center;` là cách chuẩn để căn giữa một dòng chữ trong nút, một item trong navbar.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*

## Các giá trị

Mục này liệt kê 5 giá trị của `align-items` — đọc để chọn cách căn dọc (cross axis) phù hợp, trong đó `center` là "cú kinh điển" nhất.

> 📄 **Code ví dụ:** [`examples/01-cac-gia-tri.css`](examples/01-cac-gia-tri.css)

| Giá trị | Hiệu ứng (với `flex-direction: row`) |
|---------|--------------------------------------|
| `stretch` | Item cao bằng container (default) |
| `flex-start` | Dồn lên trên |
| `flex-end` | Dồn xuống dưới |
| `center` | **Căn giữa dọc** — dùng nhiều nhất |
| `baseline` | Căn theo baseline của dòng chữ trong từng item |

> **Cách đọc bảng này:** mỗi dòng là một giá trị; cột "Hiệu ứng" ghi theo giả định trục chính là ngang (`row`). Hãy hình dung `align-items` như cách xếp chữ trong một dòng kẻ vở: `stretch` là chữ cao lấp kín dòng, `center` là chữ đứng giữa dòng kẻ, còn `baseline` là đáy các chữ cùng nằm trên một đường kẻ.

## Ví dụ

> 📄 **Code ví dụ:** [`examples/02-vi-du.css`](examples/02-vi-du.css)

> 💡 Lưu ý: item có `height`/`align-self` riêng sẽ không bị `stretch` chi phối. Muốn căn riêng cho 1 item, dùng [`align-self`](../5_align-self/). Mở `index.html` để thử từng giá trị.

Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.

> **Tóm gọn 1 câu:** `align-items` là "đường kẻ ngang của trang vở" — quyết định từng item đứng giữa dòng, dồn lên hay giãn lấp đầy theo trục phụ.

## Tài liệu tham khảo

- [CSS-Tricks — A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [freeCodeCamp — CSS Flexbox Tutorial with Cheat Sheet](https://www.freecodecamp.org/news/css-flexbox-tutorial-with-cheatsheet/)
