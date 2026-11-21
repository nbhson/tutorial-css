# 6. `gap` — khoảng cách giữa các item

> **Tóm tắt tiếng Việt:** `gap` tạo khoảng trống **giữa** các item trong flex/grid container, thay thế hoàn toàn cách dùng `margin` "hack" (mà hay gây thừa margin ở mép ngoài). Có `row-gap` và `column-gap` riêng, hoặc shorthand `gap: row-gap column-gap`.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*

## Cú pháp

Mục này nói về cách khai báo `gap` — một giá trị duy nhất hoặc tách riêng hàng/cột.

> 📄 **Code ví dụ:** [`examples/01-cu-phap.css`](examples/01-cu-phap.css)

## Ví dụ

> 📄 **Code ví dụ:** [`examples/02-vi-du.css`](examples/02-vi-du.css)

| So sánh | `margin` | `gap` |
|---------|----------|-------|
| Khoảng cách mép ngoài | Phải xử lý thủ công (`:first-child`, `:last-child`) | Không bao giờ tạo khoảng trống ở mép |
| Down-dòng (wrap) | Phải tính lại margin trên/dưới | Tự động áp cho cả hàng mới |
| Grid | Không áp dụng được cho track | Tác động trực tiếp lên track |

> **Cách đọc bảng này:** mỗi dòng là một tình huống thường gặp, so trực tiếp cách `margin` và `gap` xử lý. Hãy hình dung `gap` như khe hở giữa các viên gạch do người thợ (trình duyệt) tự chừa — bạn chỉ định độ rộng khe, và khe chỉ xuất hiện **giữa** các viên, không bao giờ tràn ra rìa tường như khi cố dùng margin.

> 💡 `gap` hoạt động cho cả Flexbox và Grid (khác cũ — thời đầu chỉ Grid mới hỗ trợ). Mở `index.html` kèm `styles/` để xem.

Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.

> **Tóm gọn 1 câu:** `gap` là "khe gạch do thợ tự chừa" — khoảng trống chỉ nằm giữa các item, không bao giờ thừa ra mép như margin hack.

## Tài liệu tham khảo

- [CSS-Tricks — A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [freeCodeCamp — CSS Flexbox Tutorial with Cheat Sheet](https://www.freecodecamp.org/news/css-flexbox-tutorial-with-cheatsheet/)
