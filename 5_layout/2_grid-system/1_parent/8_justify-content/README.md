# justify-content

> **🇻🇳 Tóm tắt:** `justify-content` căn **cả lưới** theo trục inline (ngang) khi tổng kích thước lưới nhỏ hơn container (ví dụ các cột dùng `px` cứng). Khác `justify-items`: cái này căn item trong ô, cái này căn cả khối lưới trong container.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*


Sometimes the total size of your grid might be less than the size of its grid container. This could happen if all of your grid items are sized with non-flexible units like px. In this case you can set the alignment of the grid within the grid container. This property aligns the grid along the inline (row) axis (as opposed to align-content which aligns the grid along the block (column) axis).

Giống như một dãy bàn nhỏ kê trong căn phòng rộng: tổng diện tích bàn ít hơn diện tích phòng, vậy bạn dời cả dãy bàn sang trái, phải hay giữa phòng. `justify-content` làm đúng việc đó — căn **cả khối lưới** trong container theo chiều ngang, chứ không đụng đến từng item trong ô.

Values:
- start – aligns the grid to be flush with the start edge of the grid container
- end – aligns the grid to be flush with the end edge of the grid container
- center – aligns the grid in the center of the grid container
- stretch – resizes the grid items to allow the grid to fill the full width of the grid container
- space-around – places an even amount of space between each grid item, with half-sized spaces on the far ends
- space-between – places an even amount of space between each grid item, with no space at the far ends
- space-evenly – places an even amount of space between each grid item, including the far ends

> **Cách đọc bảng này:** mỗi dòng là một kiểu "dời cả dãy bàn" — nhóm đầu (start/end/center/stretch) dồn về một mép hay dàn đều, nhóm sau (space-*) chia khoảng trống trong phòng: giữa hai bàn là chính, hai mép thì tùy kiểu (nửa / không / đầy đủ).

> 📄 **Code ví dụ:** [`examples/01-justify-content.scss`](examples/01-justify-content.scss)

> **Tóm gọn 1 câu:** `justify-content` dời **cả khối lưới** theo chiều ngang khi lưới nhỏ hơn container — nhớ phân biệt với `justify-items` vốn chỉ căn item trong ô của nó.
