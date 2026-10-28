# 4. `align-self` — căn một item theo trục block

> **Tóm tắt tiếng Việt:** `align-self` căn **một item duy nhất** theo trục block (dọc), ghi đè `align-items` của container. Giá trị: `start`, `end`, `center`, `stretch` (mặc định). (File này từng bị copy nhầm nội dung của `justify-self` — đã sửa đúng thành `align-self`.)
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*

```css
.item {
  align-self: start | end | center | stretch;
}
```

So sánh nhanh:

| Thuộc tính | Đặt trên | Trục | Ghi đè |
|------------|----------|------|--------|
| `align-items` | Container | block (dọc) | — |
| `align-self` | **Item** | block (dọc) | `align-items` cho item đó |

Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.

---

# justify-self

Aligns a grid item inside a cell along the inline (row) axis (as opposed to align-self which aligns along the block (column) axis). This value applies to the content inside a single grid item.

Values:
- start – aligns the grid item to be flush with the start edge of the cell
- end – aligns the grid item to be flush with the end edge of the cell
- center – aligns the grid item in the center of the cell
- stretch – fills the whole width of the cell (this is the default)

```scss
.item {
  align-self: start | end | center | stretch;
}
```
