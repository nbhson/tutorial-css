# gap

> **🇻🇳 Tóm tắt:** `gap` (cùng `row-gap`, `column-gap`) đặt độ rộng của "rãnh" giữa các hàng/cột trong lưới — tương tự Flexbox, thay thế hoàn toàn margin "hack". Shorthand: `gap: <row-gap> <column-gap>`.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*


Specifies the size of the grid lines. You can think of it like setting the width of the gutters between the columns/rows.

Values:
- <line-size> – a length value

```scss
.container {
  /* standard */
  column-gap: <line-size>;
  row-gap: <line-size>;

  /* old */
  grid-column-gap: <line-size>;
  grid-row-gap: <line-size>;
}
```
## Shorthand

Values:
- <grid-row-gap> <grid-column-gap> – length values

```scss
.container {
 /* standard */
  gap: <grid-row-gap> <grid-column-gap>;

  /* old */
  grid-gap: <grid-row-gap> <grid-column-gap>;
}

// example
.container {
  grid-template-columns: 100px 50px 100px;
  grid-template-rows: 80px auto 80px; 
  gap: 15px 10px;
}
```