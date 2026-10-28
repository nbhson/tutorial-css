# grid-auto-flow

> **🇻🇳 Tóm tắt:** `grid-auto-flow` điều khiển thuật toán **auto-placement** — cách Grid tự điền các item chưa được chỉ định vị trí. Giá trị: `row` (mặc định, đi theo hàng), `column` (theo cột), kèm `dense` để "lấp chỗ trống" bằng item nhỏ hơn.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*


If you have grid items that you don’t explicitly place on the grid, the auto-placement algorithm kicks in to automatically place the items. This property controls how the auto-placement algorithm works.

Values:
- row – tells the auto-placement algorithm to fill in each row in turn, adding new rows as necessary (default)
- column – tells the auto-placement algorithm to fill in each column in turn, adding new columns as necessary
- dense – tells the auto-placement algorithm to attempt to fill in holes earlier in the grid if smaller items come up later

```scss
.container {
  grid-auto-columns: <track-size> ...;
  grid-auto-rows: <track-size> ...;
}

// example
.container {
  grid-auto-flow: row | column | row dense | column dense;
}
```
