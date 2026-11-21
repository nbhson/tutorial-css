# justify-self

> **🇻🇳 Tóm tắt:** `justify-self` căn **một grid item** theo trục inline (ngang) trong ô của nó, ghi đè `justify-items` của container. Giá trị: `start`, `end`, `center`, `stretch` (mặc định).
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*

Mục này nói về việc căn chỉnh **riêng lẻ một item** theo chiều ngang trong ô của nó. Đọc để biết cách "ưu tiên cá nhân" — khi cả lưới đã có quy tắc căn chung nhưng bạn muốn một item lệch khỏi đám đông.

Hãy hình dung ô lưới như một chỗ để xe có vạch: `justify-items` của container là quy định chung cho cả bãi, còn `justify-self` là tấm biển riêng bạn cắm trước chỗ của mình — nó **ghi đè** quy định chung. Muốn item dồn sát mép trái (`start`), mép phải (`end`), đứng giữa (`center`), hay trải rộng kín ô (`stretch` — mặc định), đều chỉnh ở đây.

Aligns a grid item inside a cell along the inline (row) axis (as opposed to align-self which aligns along the block (column) axis). This value applies to a grid item inside a single cell.

Values:
- start – aligns the grid item to be flush with the start edge of the cell
- end – aligns the grid item to be flush with the end edge of the cell
- center – aligns the grid item in the center of the cell
- stretch – fills the whole width of the cell (this is the default)

> 📄 **Code ví dụ:** [`examples/01-justify-self.scss`](examples/01-justify-self.scss)

> **Tóm gọn 1 câu:** `justify-self` là "quyền cá nhân" của một item — tự căn mình theo chiều ngang trong ô, ghi đè quy tắc chung của container.
