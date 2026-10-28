# justify-content

> **🇻🇳 Tóm tắt:** `justify-content` căn **cả lưới** theo trục inline (ngang) khi tổng kích thước lưới nhỏ hơn container (ví dụ các cột dùng `px` cứng). Khác `justify-items`: cái này căn item trong ô, cái này căn cả khối lưới trong container.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*


Sometimes the total size of your grid might be less than the size of its grid container. This could happen if all of your grid items are sized with non-flexible units like px. In this case you can set the alignment of the grid within the grid container. This property aligns the grid along the inline (row) axis (as opposed to align-content which aligns the grid along the block (column) axis).

Values:
- start – aligns the grid to be flush with the start edge of the grid container
- end – aligns the grid to be flush with the end edge of the grid container
- center – aligns the grid in the center of the grid container
- stretch – resizes the grid items to allow the grid to fill the full width of the grid container
- space-around – places an even amount of space between each grid item, with half-sized spaces on the far ends
- space-between – places an even amount of space between each grid item, with no space at the far ends
- space-evenly – places an even amount of space between each grid item, including the far ends

```scss
.container {
  justify-content: start | end | center | stretch | space-around | space-between | space-evenly;    
}
```
