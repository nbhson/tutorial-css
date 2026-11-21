# grid-area

> **🇻🇳 Tóm tắt:** `grid-area` có 2 cách dùng: (1) gán **tên** cho item để `grid-template-areas` tham chiếu; (2) shorthand 4 đường lưới `row-start / column-start / row-end / column-end`.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*

Mục này nói về "cây đa năng" của Grid: một dòng khai báo, hai cách dùng hoàn toàn khác nhau. Đọc để biết khi nào nên đặt tên cho item, khi nào nên gộp 4 thuộc tính đường lưới thành một.

Ví von cho cách 1: đặt tên cho item giống như dán **nhãn tên** lên thùng đồ — sau đó `grid-template-areas` chỉ cần gọi tên là xếp đúng chỗ. Cách 2 thì giống viết tắt địa chỉ: thay vì nói 4 lần "bắt đầu hàng, bắt đầu cột, kết thúc hàng, kết thúc cột", bạn gộp cả 4 vào một dòng, thứ tự luôn là `row-start / column-start / row-end / column-end` — đọc ngược kim đồng hồ từ góc trên trái.

Gives an item a name so that it can be referenced by a template created with the grid-template-areas property. Alternatively, this property can be used as an even shorter shorthand for grid-row-start + grid-column-start + grid-row-end + grid-column-end.

Values:
- <name> – a name of your choosing
- <row-start> / <column-start> / <row-end> / <column-end> – can be numbers or named lines

> 📄 **Code ví dụ:** [`examples/01-grid-area.scss`](examples/01-grid-area.scss)

> **Tóm gọn 1 câu:** `grid-area` là hai-trong-một: hoặc dán tên cho item để template gọi tên, hoặc gộp 4 đường lưới thành một dòng khai báo.
