# grid-column-start & grid-column-end & grid-row-start & grid-row-end

> **🇻🇳 Tóm tắt:** `grid-column-start/end`, `grid-row-start/end` đặt item vào lưới theo **đường lưới (grid line)**: `1 / 3` = từ đường 1 đến đường 3, `span 2` = chiếm 2 track, hoặc dùng tên đường lưới đã đặt. Đây là bộ 4 thuộc tính nền cho mọi cách đặt item trong Grid.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*

Mục này nói về cách "chỉ tay" cho một item: muốn nó ngồi từ đâu đến đâu trên lưới, bạn không đo bằng px mà trỏ vào **đường kẻ** của lưới. Đọc xong bạn sẽ biết cách đặt một item chiếm đúng chỗ mình muốn — kể cả chiếm nhiều ô cùng lúc.

Hãy hình dung lưới Grid như một trang giấy kẻ ô ly: thay vì nói "đặt hộp này cách lề 100px", bạn nói "hộp này nằm giữa đường kẻ số 1 và số 3". Đó chính là cách 4 thuộc tính này hoạt động — đếm đường lưới chứ không đo khoảng cách.

Determines a grid item’s location within the grid by referring to specific grid lines. grid-column-start/grid-row-start is the line where the item begins, and grid-column-end/grid-row-end is the line where the item ends.

Values:
- n<line> – can be a number to refer to a numbered grid line, or a name to refer to a named grid line
- span <number> – the item will span across the provided number of grid tracks
- span <name> – the item will span across until it hits the next line with the provided name
- auto – indicates auto-placement, an automatic span, or a default span of one

> 📄 **Code ví dụ:** [`examples/01-grid-column-start-grid-column-end-grid-row.scss`](examples/01-grid-column-start-grid-column-end-grid-row.scss)

> **Tóm gọn 1 câu:** 4 thuộc tính này là cách "ghế ngồi có số" của Grid — thay vì đo đạc bằng px, bạn chỉ item vào đúng đường lưới bắt đầu và kết thúc.
