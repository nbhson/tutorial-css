# grid

> **🇻🇳 Tóm tắt:** `grid` là shorthand lớn nhất của Grid — gộp tất cả thuộc tính explicit (`grid-template-*`) và implicit (`grid-auto-*`, `grid-auto-flow`). ⚠️ Trong một khai báo `grid` chỉ được dùng nhóm explicit HOẶC implicit, không trộn cả hai.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*


A shorthand for setting all of the following properties in a single declaration: grid-template-rows, grid-template-columns, grid-template-areas, grid-auto-rows, grid-auto-columns, and grid-auto-flow (Note: You can only specify the explicit or the implicit grid properties in a single grid declaration).

Values:
- none – sets all sub-properties to their initial values.
- <grid-template> – works the same as the grid-template shorthand.
- <grid-template-rows> / [ auto-flow && dense? ] <grid-auto-columns>? – sets grid-template-rows to the specified value. If the auto-flow keyword is to the right of the slash, it sets grid-auto-flow to column. If the dense keyword is specified additionally, the auto-placement algorithm uses a “dense” packing algorithm. If grid-auto-columns is omitted, it is set to auto.
- [ auto-flow && dense? ] <grid-auto-rows>? / <grid-template-columns> – sets grid-template-columns to the specified value. If the auto-flow keyword is to the left of the slash, it sets grid-auto-flow to row. If the dense keyword is specified additionally, the auto-placement algorithm uses a “dense” packing algorithm. If grid-auto-rows is omitted, it is set to auto.

```scss
.container {
  grid: 100px 300px / 3fr 1fr;
}

// same
.container {
  grid-template-rows: 100px 300px;
  grid-template-columns: 3fr 1fr;
}

.container {
  grid: [row1-start] "header header header" 1fr [row1-end]
        [row2-start] "footer footer footer" 25px [row2-end]
        / auto 50px auto;
}

// same 
.container {
  grid-template-areas: 
    "header header header"
    "footer footer footer";
  grid-template-rows: [row1-start] 1fr [row1-end row2-start] 25px [row2-end];
  grid-template-columns: auto 50px auto;    
}
```
