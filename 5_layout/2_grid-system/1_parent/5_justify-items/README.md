# justify-items

> **🇻🇳 Tóm tắt:** `justify-items` căn nội dung **mọi grid item** theo trục inline (ngang) trong ô của nó. Giá trị: `start`, `end`, `center`, `stretch` (mặc định). Cần căn riêng một item → dùng `justify-self`.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*


Aligns grid items along the inline (row) axis (as opposed to align-items which aligns along the block (column) axis). This value applies to all grid items inside the container.

Values:
- start – aligns items to be flush with the start edge of their cell
- end – aligns items to be flush with the end edge of their cell
- center – aligns items in the center of their cell
- stretch – fills the whole width of the cell (this is the default)

```scss
.container {
  justify-items: start | end | center | stretch;
}
```
