# grid-template-columns & grid-template-rows

> **🇻🇳 Tóm tắt:** `grid-template-columns` / `grid-template-rows` định nghĩa các cột và hàng của lưới — đây là thuộc tính quan trọng nhất của Grid. Dùng `fr` (phần không gian còn lại), `minmax()`, `repeat()`. Ví dụ: `grid-template-columns: 1fr 3fr` tạo 2 cột tỉ lệ 1:3.
>
> *Nội dung gốc bên dưới (phần đầu đã dịch tiếng Việt) — tham khảo thêm.*


Xác định các cột và hàng của lưới bằng danh sách các giá trị được phân tách bằng dấu cách. 

Hãy hình dung lưới như một ô đất chia sân: bạn đứng ngoài vạch ranh từng ô (kích thước rãnh), còn khoảng cách giữa hai vạch liền kề chính là "đường lưới" — đây là thứ các giá trị biểu thị.

Các giá trị biểu thị kích thước rãnh và khoảng cách giữa chúng biểu thị đường lưới

Values:
- <track-size> – can be a length, a percentage, or a fraction of the free space in the grid using the fr unit (more on this unit over at DigitalOcean)
- <line-name> – an arbitrary name of your choosing

> 📄 **Code ví dụ:** [`examples/01-grid-template-columns-grid-template-rows.scss`](examples/01-grid-template-columns-grid-template-rows.scss)

![alt text](https://css-tricks.com/wp-content/uploads/2018/11/template-column-rows-02.svg)

- If your definition contains repeating parts, you can use the repeat() notation to streamline things:
> 📄 **Code ví dụ:** [`examples/02-grid-template-columns-grid-template-rows.scss`](examples/02-grid-template-columns-grid-template-rows.scss)
- The fr unit allows you to set the size of a track as a fraction of the free space of the grid container. Ví von: `fr` như chia phần theo tỷ lệ khi chia bánh — các ô nhận đúng phần "không gian còn lại" theo tỷ lệ bạn ghi.

> 📄 **Code ví dụ:** [`examples/03-grid-template-columns-grid-template-rows.scss`](examples/03-grid-template-columns-grid-template-rows.scss)

> **Tóm gọn 1 câu:** `grid-template-columns/rows` là bản vẽ chia ô đất của lưới — viết danh sách kích thước, dùng `repeat()` để gộp phần lặp và `fr` để chia tỷ lệ phần còn lại.

