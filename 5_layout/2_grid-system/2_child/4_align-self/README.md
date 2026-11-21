# 4. `align-self` — căn một item theo trục block

> **Tóm tắt tiếng Việt:** `align-self` căn **một item duy nhất** theo trục block (dọc), ghi đè `align-items` của container. Giá trị: `start`, `end`, `center`, `stretch` (mặc định). (File này từng bị copy nhầm nội dung của `justify-self` — đã sửa đúng thành `align-self`.)
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*

> 📄 **Code ví dụ:** [`examples/01-4-align-self-can-mot-item-theo-truc.css`](examples/01-4-align-self-can-mot-item-theo-truc.css)

Mục này nói về căn chỉnh dọc cho **một item duy nhất** — "em út" của họ `align-*`. Đọc để biết khi nào cần một item tự tách khỏi quy tắc chung của container theo chiều dọc.

Ví von: nếu `align-items` là giờ giấc chung của cả phòng thì `align-self` là đơn xin làm việc giờ riêng của một nhân viên — chỉ người đó được lệch, ai không khai báo thì vẫn theo giờ chung. Và vì nó hoạt động trên **trục block (dọc)**, nó chính là "người anh em song sinh" của `justify-self` (trục ngang) — cùng tính năng, chỉ khác hướng.

So sánh nhanh:

| Thuộc tính | Đặt trên | Trục | Ghi đè |
|------------|----------|------|--------|
| `align-items` | Container | block (dọc) | — |
| `align-self` | **Item** | block (dọc) | `align-items` cho item đó |

> **Cách đọc bảng này:** đọc theo cột "Đặt trên" trước — đó là điểm khác biệt cốt lõi: một cái viết trên container (quy tắc chung), một cái viết trên item (quy tắc riêng). Cột "Ghi đè" cho biết ai thắng khi cả hai cùng xuất hiện.

Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.

---

# justify-self

Phần tiếng Anh bên dưới là tài liệu tham khảo gốc (nội dung gốc của chủ đề này lấy từ CSS-Tricks). Aligns a grid item inside a cell along the inline (row) axis (as opposed to align-self which aligns along the block (column) axis). This value applies to the content inside a single grid item.

Values:
- start – aligns the grid item to be flush with the start edge of the cell
- end – aligns the grid item to be flush with the end edge of the cell
- center – aligns the grid item in the center of the cell
- stretch – fills the whole width of the cell (this is the default)

> 📄 **Code ví dụ:** [`examples/02-justify-self.scss`](examples/02-justify-self.scss)

> **Tóm gọn 1 câu:** `align-self` là "đơn xin lệch giờ" của một item theo chiều dọc — viết trên item, thắng `align-items` của container.
