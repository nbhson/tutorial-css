# align-items

> **🇻🇳 Tóm tắt:** `align-items` căn nội dung **mọi grid item** theo trục block (dọc) — đối xứng với `justify-items` (ngang). Giá trị: `start`, `end`, `center`, `stretch` (mặc định).
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*


Aligns grid items along the block (column) axis (as opposed to justify-items which aligns along the inline (row) axis). This value applies to all grid items inside the container.

Ví von: nếu `justify-items` là nội quy xếp ngang, thì `align-items` là nội quy xếp dọc — cùng áp cho mọi item, chỉ khác "chiều me" là dọc thay vì ngang.

Values:
- stretch – fills the whole height of the cell (this is the default)
- start – aligns items to be flush with the start edge of their cell
- end – aligns items to be flush with the end edge of their cell
- center – aligns items in the center of their cell
- baseline – align items along text baseline. There are modifiers to baseline — first baseline and last baseline which will use the baseline from the first or last line in the case of multi-line text.

> 📄 **Code ví dụ:** [`examples/01-align-items.scss`](examples/01-align-items.scss)

> **Tóm gọn 1 câu:** `align-items` là "nội quy dọc áp cho mọi item" — xếp lên sát trên/dưới/giữa/trải đều theo chiều cao của từng ô; đối xứng với `justify-items` ở chiều ngang.
