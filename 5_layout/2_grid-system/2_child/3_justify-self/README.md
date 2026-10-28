# justify-self

> **🇻🇳 Tóm tắt:** `justify-self` căn **một grid item** theo trục inline (ngang) trong ô của nó, ghi đè `justify-items` của container. Giá trị: `start`, `end`, `center`, `stretch` (mặc định).
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*


Aligns a grid item inside a cell along the inline (row) axis (as opposed to align-self which aligns along the block (column) axis). This value applies to a grid item inside a single cell.

Values:
- start – aligns the grid item to be flush with the start edge of the cell
- end – aligns the grid item to be flush with the end edge of the cell
- center – aligns the grid item in the center of the cell
- stretch – fills the whole width of the cell (this is the default)

```scss
.item {
  justify-self: start | end | center | stretch;
}
```
