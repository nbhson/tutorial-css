# 7. `flex-grow`, `flex-shrink`, `flex-wrap`, `flex-basis`

> **Tóm tắt tiếng Việt:** Bài này gộp 4 thuộc tính chi phối kích thước và xuống dòng: `flex-grow` (item giãn thêm bao nhiêu khi dư chỗ), `flex-shrink` (co lại bao nhiêu khi thiếu chỗ), `flex-basis` (kích thước gốc trước khi giãn/co), `flex-wrap` (cho phép xuống dòng). Shorthand quen thuộc: `flex: 1 1 auto`.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*

## flex-grow / flex-shrink / flex-basis

```css
.item {
  flex-grow: 1;    /* chia phần không gian dư theo tỉ lệ (default: 0 — không giãn) */
  flex-shrink: 1;  /* cho phép co lại khi không đủ chỗ (default: 1) */
  flex-basis: 0;   /* kích thước xuất phát trước khi giãn/co (default: auto = theo content) */
}

/* Shorthand quen thuộc: */
/* flex: 1            = flex: 1 1 0    — chiếm đều không gian */
/* flex: auto         = flex: 1 1 auto */
/* flex: none         = flex: 0 0 auto — kích thước cố định theo content */
```

```css
/* Sidebar cố định 250px, content chiếm hết phần còn lại */
.sidebar { flex: 0 0 250px; }
.content { flex: 1 1 auto; }

/* 2 cột tỉ lệ 2:1 */
.col-a { flex: 2; }
.col-b { flex: 1; }
```

## flex-wrap

```css
.container {
  display: flex;
  flex-wrap: nowrap;  /* mặc định — ép 1 hàng, item bị co */
  /* flex-wrap: wrap;    cho phép xuống dòng khi hết chỗ */
  /* flex-wrap: wrap-reverse; xuống dòng ngược hướng */
}
```

```css
/* Card grid "giả": tự xuống dòng, card tối thiểu 200px */
.cards {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
}
.cards > .card {
  flex: 1 1 200px;   /* basis tối thiểu 200px, giãn/co theo không gian */
}
```

> 💡 **Công thức nhớ:** phần không gian dư được chia theo tổng tỉ lệ `flex-grow` của các item. `flex-basis` chiến thắng `width` khi cả hai cùng đặt (trong flex-direction: row). Mở `index.html` kèm `styles/` để thử thay đổi từng giá trị.

Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.

## Tài liệu tham khảo

- [CSS-Tricks — A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [freeCodeCamp — CSS Flexbox Tutorial with Cheat Sheet](https://www.freecodecamp.org/news/css-flexbox-tutorial-with-cheatsheet/)
