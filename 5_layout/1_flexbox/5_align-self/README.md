# 5. `align-self` — căn riêng cho một item

> **Tóm tắt tiếng Việt:** `align-self` ghi đè `align-items` của container **cho riêng một item**. Nhận cùng tập giá trị (`auto`, `flex-start`, `center`, `flex-end`, `stretch`, `baseline`). Dùng khi muốn 1 item lệch khỏi căn chung, ví dụ avatar thò xuống dưới trong thanh chat.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*

## Cú pháp

```css
.container {
  display: flex;
  align-items: center;      /* mọi item căn giữa theo cross axis */
}

.container .item-2 {
  align-self: flex-end;     /* ...nhưng item 2 dồn xuống cuối */
}
```

| Giá trị | Hiệu ứng |
|---------|----------|
| `auto` | Kế thừa `align-items` của container (default) |
| `flex-start` / `flex-end` | Dồn về đầu/cuối trục phụ |
| `center` | Căn giữa trục phụ |
| `stretch` | Giãn lấp đầy trục phụ |
| `baseline` | Căn theo baseline chữ |

## Ví dụ

```css
/* Card: tiêu đề căn trên, nút "Xem thêm" đẩy xuống đáy card */
.card {
  display: flex;
  flex-direction: column;
}

.card .btn {
  align-self: flex-end;    /* nút nằm góc phải-dưới dù card căn mặc định */
}
```

> 💡 Trong flexbox không có `justify-self` — muốn đẩy 1 item sang tận cùng theo main axis, dùng `margin-left: auto` hoặc `align-self` khi trục phù hợp. Mở `index.html` để thử.

Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.

## Tài liệu tham khảo

- [CSS-Tricks — A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [freeCodeCamp — CSS Flexbox Tutorial with Cheat Sheet](https://www.freecodecamp.org/news/css-flexbox-tutorial-with-cheatsheet/)
