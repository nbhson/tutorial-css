# grid-column-start & grid-column-end & grid-row-start & grid-row-end

> **🇻🇳 Tóm tắt:** `grid-column-start/end`, `grid-row-start/end` đặt item vào lưới theo **đường lưới (grid line)**: `1 / 3` = từ đường 1 đến đường 3, `span 2` = chiếm 2 track, hoặc dùng tên đường lưới đã đặt. Đây là bộ 4 thuộc tính nền cho mọi cách đặt item trong Grid.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*


Determines a grid item’s location within the grid by referring to specific grid lines. grid-column-start/grid-row-start is the line where the item begins, and grid-column-end/grid-row-end is the line where the item ends.

Values:
- n<line> – can be a number to refer to a numbered grid line, or a name to refer to a named grid line
- span <number> – the item will span across the provided number of grid tracks
- span <name> – the item will span across until it hits the next line with the provided name
- auto – indicates auto-placement, an automatic span, or a default span of one

```scss
.item {
  grid-column-start: <number> | <name> | span <number> | span <name> | auto;
  grid-column-end: <number> | <name> | span <number> | span <name> | auto;
  grid-row-start: <number> | <name> | span <number> | span <name> | auto;
  grid-row-end: <number> | <name> | span <number> | span <name> | auto;
}
```
