# grid-template

> **🇻🇳 Tóm tắt:** `grid-template` là shorthand gộp `grid-template-rows`, `grid-template-columns` và `grid-template-areas` trong một khai báo — dùng khi muốn định nghĩa cả khung lưới explicit một lần.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*


A shorthand for setting grid-template-rows, grid-template-columns, and grid-template-areas in a single declaration.

Giống như đi chợ gộp cả ba mặt hàng (hàng, cột, vùng đặt tên) vào một lần trả tiền — `grid-template` gộp ba thuộc tính explicit vào một khai báo duy nhất.

Values:

- none – sets all three properties to their initial values
- <grid-template-rows> / <grid-template-columns> – sets grid-template-columns and grid-template-rows to the specified values, respectively, and sets grid-template-areas to none

> **Cách đọc bảng này:** mỗi dòng là một "combo" bạn được đặt — `none` để reset cả ba, còn dạng `<rows> / <columns>` là đặt hàng và cột một lần (lưu ý: vùng đặt tên bị về `none`).

> 📄 **Code ví dụ:** [`examples/01-grid-template.scss`](examples/01-grid-template.scss)

> **Tóm gọn 1 câu:** `grid-template` là "gói combo" cho khung lưới explicit — hàng, cột, vùng tên gộp một dòng, nhưng combo dạng `rows / columns` sẽ xóa sạch vùng tên.