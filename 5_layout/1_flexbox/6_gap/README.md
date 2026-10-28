# 6. `gap` — khoảng cách giữa các item

> **Tóm tắt tiếng Việt:** `gap` tạo khoảng trống **giữa** các item trong flex/grid container, thay thế hoàn toàn cách dùng `margin` "hack" (mà hay gây thừa margin ở mép ngoài). Có `row-gap` và `column-gap` riêng, hoặc shorthand `gap: row-gap column-gap`.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*

## Cú pháp

```css
.container {
  display: flex;
  gap: 1rem;             /* cả hai chiều đều 1rem */
  /* gap: 1rem 2rem; */  /* row-gap=1rem, column-gap=2rem */
  /* row-gap: 8px;  */   /* đặt riêng từng chiều */
  /* column-gap: 16px; */
}
```

## Ví dụ

```css
/* Danh sách tag: cách nhau đều, không cần :last-child { margin-right: 0 } */
.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;           /* 👍 thay vì .tag + .tag { margin-left: 8px } */
}
```

| So sánh | `margin` | `gap` |
|---------|----------|-------|
| Khoảng cách mép ngoài | Phải xử lý thủ công (`:first-child`, `:last-child`) | Không bao giờ tạo khoảng trống ở mép |
| Down-dòng (wrap) | Phải tính lại margin trên/dưới | Tự động áp cho cả hàng mới |
| Grid | Không áp dụng được cho track | Tác động trực tiếp lên track |

> 💡 `gap` hoạt động cho cả Flexbox và Grid (khác cũ — thời đầu chỉ Grid mới hỗ trợ). Mở `index.html` kèm `styles/` để xem.

Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.

## Tài liệu tham khảo

- [CSS-Tricks — A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [freeCodeCamp — CSS Flexbox Tutorial with Cheat Sheet](https://www.freecodecamp.org/news/css-flexbox-tutorial-with-cheatsheet/)
