# grid-auto-columns & grid-auto-rows

> **🇻🇳 Tóm tắt:** `grid-auto-columns` / `grid-auto-rows` đặt kích thước cho các track **tự sinh** (implicit grid) — xuất hiện khi số item vượt số ô đã định nghĩa, hoặc item được đặt ra ngoài lưới explicit.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*


Specifies the size of any auto-generated grid tracks (aka implicit grid tracks). Implicit tracks get created when there are more grid items than cells in the grid or when a grid item is placed outside of the explicit grid. (see The Difference Between Explicit and Implicit Grids)


Values:
- <track-size> – can be a length, a percentage, or a fraction of the free space in the grid (using the fr unit)

```scss
.container {
  grid-auto-columns: <track-size> ...;
  grid-auto-rows: <track-size> ...;
}

// example
.container {
  grid-template-columns: 60px 60px;
  grid-template-rows: 90px 90px;
}
```

![alt text](https://css-tricks.com/wp-content/uploads/2018/11/grid-auto-columns-rows-01.svg)

## Reason

![alt text](https://css-tricks.com/wp-content/uploads/2018/11/grid-auto-columns-rows-02.svg)

![alt text](https://css-tricks.com/wp-content/uploads/2018/11/grid-auto-columns-rows-03.svg)