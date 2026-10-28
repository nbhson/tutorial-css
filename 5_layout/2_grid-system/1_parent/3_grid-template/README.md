# grid-template

> **🇻🇳 Tóm tắt:** `grid-template` là shorthand gộp `grid-template-rows`, `grid-template-columns` và `grid-template-areas` trong một khai báo — dùng khi muốn định nghĩa cả khung lưới explicit một lần.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*


A shorthand for setting grid-template-rows, grid-template-columns, and grid-template-areas in a single declaration.

Values:

- none – sets all three properties to their initial values
- <grid-template-rows> / <grid-template-columns> – sets grid-template-columns and grid-template-rows to the specified values, respectively, and sets grid-template-areas to none

```scss
.container {
  grid-template: none | <grid-template-rows> / <grid-template-columns>;
}

// example
.container {
  grid-template:
    [row1-start] "header header header" 25px [row1-end] // 25 row height
    [row2-start] "footer footer footer" 25px [row2-end]
    / auto 50px auto; // cell width
}

// same 
.container {
  grid-template-rows: [row1-start] 25px [row1-end row2-start] 25px [row2-end];
  grid-template-columns: auto 50px auto;
  grid-template-areas: 
    "header header header" 
    "footer footer footer";
}
```