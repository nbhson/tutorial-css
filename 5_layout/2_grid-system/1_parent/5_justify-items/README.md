# justify-items

> **🇻🇳 Tóm tắt:** `justify-items` căn nội dung **mọi grid item** theo trục inline (ngang) trong ô của nó. Giá trị: `start`, `end`, `center`, `stretch` (mặc định). Cần căn riêng một item → dùng `justify-self`.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*


Aligns grid items along the inline (row) axis (as opposed to align-items which aligns along the block (column) axis). This value applies to all grid items inside the container.

Ví von: đây là "nội quy chung cho mọi căn hộ trong tòa nhà" — mỗi item được xếp sang trái, phải, giữa hay trải đều trong căn ô của chính nó, áp dụng cho tất cả cùng lúc.

Values:
- start – aligns items to be flush with the start edge of their cell
- end – aligns items to be flush with the end edge of their cell
- center – aligns items in the center of their cell
- stretch – fills the whole width of the cell (this is the default)

> 📄 **Code ví dụ:** [`examples/01-justify-items.scss`](examples/01-justify-items.scss)

> **Tóm gọn 1 câu:** `justify-items` là "nội quy ngang áp cho mọi item" — xếp trái/phải/giữa/trải đều trong ô của từng item; cần ngoại lệ cho một item thì dùng `justify-self`.
