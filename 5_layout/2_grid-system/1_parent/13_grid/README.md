# grid

> **🇻🇳 Tóm tắt:** `grid` là shorthand lớn nhất của Grid — gộp tất cả thuộc tính explicit (`grid-template-*`) và implicit (`grid-auto-*`, `grid-auto-flow`). ⚠️ Trong một khai báo `grid` chỉ được dùng nhóm explicit HOẶC implicit, không trộn cả hai.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*


A shorthand for setting all of the following properties in a single declaration: grid-template-rows, grid-template-columns, grid-template-areas, grid-auto-rows, grid-auto-columns, and grid-auto-flow (Note: You can only specify the explicit or the implicit grid properties in a single grid declaration).

Ví von: `grid` là "chiếc vali lớn" của Grid — nhét được cả nhóm explicit lẫn implicit, nhưng một chuyến chỉ mang được một nhóm, không nhồi cả hai.

Values:
- none – sets all sub-properties to their initial values.
- <grid-template> – works the same as the grid-template shorthand.
- <grid-template-rows> / [ auto-flow && dense? ] <grid-auto-columns>? – sets grid-template-rows to the specified value. If the auto-flow keyword is to the right of the slash, it sets grid-auto-flow to column. If the dense keyword is specified additionally, the auto-placement algorithm uses a “dense” packing algorithm. If grid-auto-columns is omitted, it is set to auto.
- [ auto-flow && dense? ] <grid-auto-rows>? / <grid-template-columns> – sets grid-template-columns to the specified value. If the auto-flow keyword is to the left of the slash, it sets grid-auto-flow to row. If the dense keyword is specified additionally, the auto-placement algorithm uses a “dense” packing algorithm. If grid-auto-rows is omitted, it is set to auto.

> **Cách đọc bảng này:** đọc theo hướng "trước gạch chéo → sau gạch chéo" — phía nào có `auto-flow` thì đó là chiều auto-placement; mỗi dòng là một dạng viết gộp, từ đơn giản nhất (`none`) đến dạng đầy đủ.

> 📄 **Code ví dụ:** [`examples/01-grid.scss`](examples/01-grid.scss)

> **Tóm gọn 1 câu:** `grid` là "vali lớn" gộp mọi thuộc tính lưới trong một khai báo — nhưng mỗi lần chỉ được mang nhóm explicit hoặc implicit, đừng nhồi cả hai.
