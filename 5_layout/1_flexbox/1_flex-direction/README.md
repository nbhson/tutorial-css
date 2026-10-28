# 1. `flex-direction` — chọn trục chính

> **Tóm tắt tiếng Việt:** `flex-direction` quyết định trục chính (main axis) của flex container: `row` (ngang, mặc định), `column` (dọc), kèm `-reverse` để đảo hướng. Đổi trục là đổi luôn tác động của `justify-content` và `align-items` — đây là thuộc tính cần hiểu đầu tiên trong Flexbox.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*

## Giá trị

```css
.container {
  display: flex;
  flex-direction: row;            /* mặc định — items xếp ngang, theo hướng đọc */
  /* flex-direction: row-reverse; */   /* xếp ngang, ngược phải sang trái */
  /* flex-direction: column; */        /* xếp dọc, từ trên xuống */
  /* flex-direction: column-reverse; *//* xếp dọc, từ dưới lên */
}
```

| Giá trị | Main axis | Dùng khi nào |
|---------|-----------|--------------|
| `row` | Ngang → | Navbar, danh sách nút (mặc định) |
| `row-reverse` | Ngang, ngược | Layout RTL, đưa item cuối lên đầu |
| `column` | Dọc ↓ | Danh sách dọc, card dọc |
| `column-reverse` | Dọc, ngược | Chat: tin mới nhất ở dưới nhưng muốn insert từ trên |

## Ví dụ

```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

```css
.container {
  display: flex;
  flex-direction: column;   /* 3 item xếp chồng dọc thay vì ngang */
}
```

> 💡 **Điểm dễ nhầm nhất:** khi đổi `flex-direction: column` thì `justify-content` căn theo chiều **dọc** (main axis giờ là dọc), còn `align-items` căn theo chiều **ngang**. Hãy mở `index.html` trong thư mục này và đổi giá trị để thấy trực quan.

Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.

## Tài liệu tham khảo

- [CSS-Tricks — A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [freeCodeCamp — CSS Flexbox Tutorial with Cheat Sheet](https://www.freecodecamp.org/news/css-flexbox-tutorial-with-cheatsheet/)
