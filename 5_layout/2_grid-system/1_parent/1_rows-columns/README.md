# grid-template-columns & grid-template-rows

> **🇻🇳 Tóm tắt:** `grid-template-columns` / `grid-template-rows` định nghĩa các cột và hàng của lưới — đây là thuộc tính quan trọng nhất của Grid. Dùng `fr` (phần không gian còn lại), `minmax()`, `repeat()`. Ví dụ: `grid-template-columns: 1fr 3fr` tạo 2 cột tỉ lệ 1:3.
>
> *Nội dung gốc bên dưới (phần đầu đã dịch tiếng Việt) — tham khảo thêm.*


Xác định các cột và hàng của lưới bằng danh sách các giá trị được phân tách bằng dấu cách. 

Các giá trị biểu thị kích thước rãnh và khoảng cách giữa chúng biểu thị đường lưới

Values:
- <track-size> – can be a length, a percentage, or a fraction of the free space in the grid using the fr unit (more on this unit over at DigitalOcean)
- <line-name> – an arbitrary name of your choosing

```scss
.container {
  grid-template-columns: ...  ...;
  /* e.g. 
      1fr 1fr
      minmax(10px, 1fr) 3fr
      repeat(5, 1fr)
      50px auto 100px 1fr
  */
  grid-template-rows: ... ...;
  /* e.g. 
      min-content 1fr min-content
      100px 1fr max-content
  */
}
```

![alt text](https://css-tricks.com/wp-content/uploads/2018/11/template-column-rows-02.svg)

- If your definition contains repeating parts, you can use the repeat() notation to streamline things:
```scss
.container {
  grid-template-columns: repeat(3, 20px [col-start]);
}
// same
.container {
  grid-template-columns: 20px [col-start] 20px [col-start] 20px [col-start];
}
```
- The fr unit allows you to set the size of a track as a fraction of the free space of the grid container. 

```scss
.container {
  grid-template-columns: 1fr 50px 1fr 1fr;
}
```

