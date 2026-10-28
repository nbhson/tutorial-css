# 2. `justify-content` — căn theo trục chính

> **Tóm tắt tiếng Việt:** `justify-content` căn phân bố các item **dọc theo main axis** của flex container. `flex-start` dồn về đầu, `center` căn giữa, `space-between` dàn đều (2 đầu sát mép), `space-around`/`space-evenly` thêm khoảng đệm ở mép. Đây là cách "dàn hàng" phổ biến nhất trong Flexbox.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*

## Các giá trị thường dùng

```css
.container {
  display: flex;
  /* justify-content: flex-start;   */ /* mặc định — dồn về đầu trục */
  /* justify-content: center;       */ /* căn giữa cụm item */
  /* justify-content: flex-end;     */ /* dồn về cuối trục */
  /* justify-content: space-between;*/ /* khoảng cách đều nhau, mép ngoài = 0 */
  /* justify-content: space-around; */ /* khoảng đệm mép = 1/2 khoảng giữa */
  /* justify-content: space-evenly; */ /* mọi khoảng cách bằng nhau, kể cả mép */
  justify-content: space-between;
}
```

| Giá trị | Hiệu ứng |
|---------|----------|
| `flex-start` | Dồn về đầu trục chính (default) |
| `flex-end` | Dồn về cuối trục chính |
| `center` | Căn giữa trục chính |
| `space-between` | Item đầu sát mép, item cuối sát mép, khoảng trống chia đều giữa |
| `space-around` | Mỗi item có "làn" khoảng trống hai bên — mép bằng nửa khoảng giữa |
| `space-evenly` | Mọi khoảng trống bằng nhau |

## Ví dụ thực tế

```css
/* Navbar: logo trái, menu phải */
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

/* Phân trang: các nút căn giữa */
.pagination {
  display: flex;
  justify-content: center;
  gap: 0.5rem;
}
```

Mở `index.html` trong thư mục này, đổi từng giá trị trong `styles/style.css` để so sánh trực quan.

Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.

## Tài liệu tham khảo

- [CSS-Tricks — A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [freeCodeCamp — CSS Flexbox Tutorial with Cheat Sheet](https://www.freecodecamp.org/news/css-flexbox-tutorial-with-cheatsheet/)
