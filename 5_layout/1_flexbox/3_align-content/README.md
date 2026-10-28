# 3. `align-content` — căn nhiều dòng theo trục phụ

> **Tóm tắt tiếng Việt:** `align-content` căn phân bố **các dòng** của flex container (cross axis) — chỉ có tác dụng khi container có `flex-wrap: wrap` và có nhiều dòng item. Nếu chỉ có 1 dòng, thuộc tính này không có hiệu lực gì (hãy dùng `align-items`).
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*

## Điều kiện hoạt động

```css
.container {
  display: flex;
  flex-wrap: wrap;              /* ⚠️ bắt buộc — không có wrap thì align-content vô hiệu */
  height: 300px;                /* cần container cao hơn nội dung thì mới "căn" được */
  align-content: space-between;
}
```

| Giá trị | Hiệu ứng |
|---------|----------|
| `flex-start` | Các dòng dồn về đầu trục phụ (default) |
| `center` | Cả khối các dòng căn giữa trục phụ |
| `space-between` | Dòng đầu sát mép trên, dòng cuối sát mép dưới |
| `space-around` / `space-evenly` | Khoảng trống chia đều giữa các dòng |
| `stretch` | Các dòng giãn ra lấp đầy container (default khi wrap) |

## Ví dụ

Gallery nhiều hàng trong khung cao cố định — muốn các hàng dàn đều thay vì dồn lên trên:

```css
.gallery {
  display: flex;
  flex-wrap: wrap;
  align-content: center;   /* cả cụm hàng căn giữa theo chiều cao */
  gap: 1rem;
}
```

> 💡 **Nhớ nhanh:** `align-items` căn từng item trong dòng; `align-content` căn cả các **dòng** với nhau. Mở `index.html` kèm `styles/` để thử.

Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.

## Tài liệu tham khảo

- [CSS-Tricks — A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [freeCodeCamp — CSS Flexbox Tutorial with Cheat Sheet](https://www.freecodecamp.org/news/css-flexbox-tutorial-with-cheatsheet/)
