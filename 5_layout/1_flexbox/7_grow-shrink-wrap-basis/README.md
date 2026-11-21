# 7. `flex-grow`, `flex-shrink`, `flex-wrap`, `flex-basis`

> **Tóm tắt tiếng Việt:** Bài này gộp 4 thuộc tính chi phối kích thước và xuống dòng: `flex-grow` (item giãn thêm bao nhiêu khi dư chỗ), `flex-shrink` (co lại bao nhiêu khi thiếu chỗ), `flex-basis` (kích thước gốc trước khi giãn/co), `flex-wrap` (cho phép xuống dòng). Shorthand quen thuộc: `flex: 1 1 auto`.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*

## flex-grow / flex-shrink / flex-basis

Mục này nói về bộ ba quy định kích thước item: giãn bao nhiêu khi thừa chỗ, co bao nhiêu khi thiếu chỗ, và điểm xuất phát là bao nhiêu. Ví von: giống ba người cùng mướn phòng — `flex-basis` là diện tích ban đầu mỗi người được nhận, `flex-grow` là phần diện tích thừa chia theo tỉ lệ, còn `flex-shrink` là phần diện tích phải nhường khi phòng chật.

> 📄 **Code ví dụ:** [`examples/01-flex-grow-flex-shrink-flex-basis.css`](examples/01-flex-grow-flex-shrink-flex-basis.css)

> 📄 **Code ví dụ:** [`examples/02-flex-grow-flex-shrink-flex-basis.css`](examples/02-flex-grow-flex-shrink-flex-basis.css)

## flex-wrap

Mục này nói về `flex-wrap` — cho phép item "xếp hàng dọc" xuống dòng mới khi hết chỗ, thay vì chen chúc trên một dòng.

> 📄 **Code ví dụ:** [`examples/03-flex-wrap.css`](examples/03-flex-wrap.css)

> 📄 **Code ví dụ:** [`examples/04-flex-wrap.css`](examples/04-flex-wrap.css)

> 💡 **Công thức nhớ:** phần không gian dư được chia theo tổng tỉ lệ `flex-grow` của các item. `flex-basis` chiến thắng `width` khi cả hai cùng đặt (trong flex-direction: row). Mở `index.html` kèm `styles/` để thử thay đổi từng giá trị.

Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.

> **Tóm gọn 1 câu:** Bộ ba grow/shrink/basis là "hợp đồng chia phòng" — basis là chỗ gốc, grow/shrink là cách chia phần thừa hoặc nhường phần thiếu, còn `flex-wrap` quyết định có được xếp sang phòng mới hay không.

## Tài liệu tham khảo

- [CSS-Tricks — A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [freeCodeCamp — CSS Flexbox Tutorial with Cheat Sheet](https://www.freecodecamp.org/news/css-flexbox-tutorial-with-cheatsheet/)
