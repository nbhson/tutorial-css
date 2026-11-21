# gap

> **🇻🇳 Tóm tắt:** `gap` (cùng `row-gap`, `column-gap`) đặt độ rộng của "rãnh" giữa các hàng/cột trong lưới — tương tự Flexbox, thay thế hoàn toàn margin "hack". Shorthand: `gap: <row-gap> <column-gap>`.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*


Specifies the size of the grid lines. You can think of it like setting the width of the gutters between the columns/rows.

Hãy hình dung khoảng hở giữa các gạch lát: `gap` chính là độ rộng "mạch vữa" giữa hàng và cột — khoảng trống này thuộc về lưới, không phải nhờ margin mỗi item "chừa ra" từng bên như cách hack cũ.

Values:
- <line-size> – a length value

> 📄 **Code ví dụ:** [`examples/01-gap.scss`](examples/01-gap.scss)

## Shorthand

Mục này nói về cách viết gộp: một dòng duy nhất đặt cả khoảng cách theo hàng lẫn theo cột.

Values:
- <grid-row-gap> <grid-column-gap> – length values

> 📄 **Code ví dụ:** [`examples/02-shorthand.scss`](examples/02-shorthand.scss)

> **Tóm gọn 1 câu:** `gap` là "mạch vữa" giữa hàng và cột — viết gộp `gap: <hàng> <cột>` thay vì margin hack từng item.