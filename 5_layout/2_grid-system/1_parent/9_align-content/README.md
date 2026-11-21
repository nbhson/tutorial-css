# align-content

> **🇻🇳 Tóm tắt:** `align-content` căn **cả lưới** theo trục block (dọc) khi lưới nhỏ hơn container — đối xứng với `justify-content` (ngang). Hỗ trợ thêm các giá trị phân bố: `space-between`, `space-around`, `space-evenly`.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*


Sometimes the total size of your grid might be less than the size of its grid container. This could happen if all of your grid items are sized with non-flexible units like px. In this case you can set the alignment of the grid within the grid container. This property aligns the grid along the block (column) axis (as opposed to justify-content which aligns the grid along the inline (row) axis).

Cùng tình huống "dãy bàn nhỏ trong phòng rộng" như `justify-content`, nhưng lần này bạn dời cả dãy **lên trên hoặc xuống dưới** — `align-content` căn cả khối lưới theo chiều dọc, và thêm bộ ba `space-*` để chia khoảng trống theo các kiểu khác nhau.

Values:
- start – aligns the grid to be flush with the start edge of the grid container
- end – aligns the grid to be flush with the end edge of the grid container
- center – aligns the grid in the center of the grid container
- stretch – resizes the grid items to allow the grid to fill the full height of the grid container
- space-around – places an even amount of space between each grid item, with half-sized spaces on the far ends
- space-between – places an even amount of space between each grid item, with no space at the far ends
- space-evenly – places an even amount of space between each grid item, including the far ends

> **Cách đọc bảng này:** mỗi dòng là một cách "dời cả dãy bàn theo chiều dọc" — nhóm đầu dồn lên mép trên/dưới/giữa hay dàn đều chiều cao, nhóm `space-*` chia khoảng trống dọc: giữa các hàng luôn đều, hai mép thì nửa / không / đầy đủ tùy kiểu.

> 📄 **Code ví dụ:** [`examples/01-align-content.scss`](examples/01-align-content.scss)

> **Tóm gọn 1 câu:** `align-content` dời **cả khối lưới** theo chiều dọc khi lưới nhỏ hơn container — là bản đối xứng dọc của `justify-content`, kèm bộ ba `space-*` để chia khoảng trống.
