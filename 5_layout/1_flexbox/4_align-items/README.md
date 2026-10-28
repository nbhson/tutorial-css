# 4. `align-items` — căn từng item theo trục phụ

> **Tóm tắt tiếng Việt:** `align-items` căn các item **theo cross axis** (trục vuông góc với main axis). Đây là thuộc tính của "căn giữa theo chiều dọc" kinh điển: `display: flex; align-items: center;` là cách chuẩn để căn giữa một dòng chữ trong nút, một item trong navbar.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*

## Các giá trị

```css
.container {
  display: flex;
  /* align-items: stretch;    */ /* mặc định — item kéo dài lấp đầy cross axis */
  /* align-items: flex-start; */ /* dồn về đầu trục phụ */
  /* align-items: center;     */ /* căn giữa trục phụ */
  /* align-items: baseline;   */ /* căn theo đường baseline của chữ */
  align-items: center;
}
```

| Giá trị | Hiệu ứng (với `flex-direction: row`) |
|---------|--------------------------------------|
| `stretch` | Item cao bằng container (default) |
| `flex-start` | Dồn lên trên |
| `flex-end` | Dồn xuống dưới |
| `center` | **Căn giữa dọc** — dùng nhiều nhất |
| `baseline` | Căn theo baseline của dòng chữ trong từng item |

## Ví dụ

```css
/* Navbar: logo + menu + avatar nằm giữa theo chiều cao */
.navbar {
  display: flex;
  justify-content: space-between;  /* ngang: dàn đều */
  align-items: center;             /* dọc: căn giữa */
  height: 64px;
}
```

> 💡 Lưu ý: item có `height`/`align-self` riêng sẽ không bị `stretch` chi phối. Muốn căn riêng cho 1 item, dùng [`align-self`](../5_align-self/). Mở `index.html` để thử từng giá trị.

Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.

## Tài liệu tham khảo

- [CSS-Tricks — A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [freeCodeCamp — CSS Flexbox Tutorial with Cheat Sheet](https://www.freecodecamp.org/news/css-flexbox-tutorial-with-cheatsheet/)
