# 8. `order` — đổi thứ tự hiển thị

> **Tóm tắt tiếng Việt:** `order` thay đổi thứ tự **hiển thị** của item trong flex container mà không cần sửa HTML. Mặc định mọi item có `order: 0`; item có `order` nhỏ hơn hiện trước. ⚠️ Chỉ đổi hình ảnh trực quan — thứ tự đọc của screen reader và tab focus vẫn theo HTML.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*

## Cú pháp

```css
.container {
  display: flex;
}

.item-1 { order: 3; }   /* hiện sau */
.item-2 { order: 1; }   /* hiện trước */
.item-3 { order: 2; }
/* Thứ tự hiển thị: item-2, item-3, item-1 */
```

| Giá trị | Hiệu ứng |
|---------|----------|
| Số nguyên (âm/0/dương) | Sắp theo tăng dần; items cùng `order` giữ thứ tự theo HTML |
| `0` (mặc định) | Giữ nguyên thứ tự HTML |

## Ví dụ

```css
/* Mobile-first: nội dung chính lên trên, sidebar xuống dưới
   Desktop: đảo lại sidebar sang trái — không cần đổi HTML */
.main {
  order: 1;
}
.sidebar {
  order: 2;
}
@media (min-width: 768px) {
  .sidebar { order: -1; }  /* sidebar nhảy lên trước */
}
```

> ⚠️ **Cảnh báo accessibility:** đừng dùng `order` để "vá" thứ tự HTML sai. Screen reader và phím Tab đi theo DOM, không theo hình ảnh hiển thị. Thứ tự HTML nên là thứ tự logic; `order` chỉ dùng cho điều chỉnh layout nhỏ. Mở `index.html` để thử.

Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.

## Tài liệu tham khảo

- [CSS-Tricks — A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [freeCodeCamp — CSS Flexbox Tutorial with Cheat Sheet](https://www.freecodecamp.org/news/css-flexbox-tutorial-with-cheatsheet/)
