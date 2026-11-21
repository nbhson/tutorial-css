# 3. `align-content` — căn nhiều dòng theo trục phụ

> **Tóm tắt tiếng Việt:** `align-content` căn phân bố **các dòng** của flex container (cross axis) — chỉ có tác dụng khi container có `flex-wrap: wrap` và có nhiều dòng item. Nếu chỉ có 1 dòng, thuộc tính này không có hiệu lực gì (hãy dùng `align-items`).
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*

## Điều kiện hoạt động

Mục này nói về điều kiện để `align-content` "lên tiếng" — và bảng giá trị nó nhận. Đọc để tránh dùng nhầm khi container chỉ có một dòng.

> 📄 **Code ví dụ:** [`examples/01-ieu-kien-hoat-ong.css`](examples/01-ieu-kien-hoat-ong.css)

| Giá trị | Hiệu ứng |
|---------|----------|
| `flex-start` | Các dòng dồn về đầu trục phụ (default) |
| `center` | Cả khối các dòng căn giữa trục phụ |
| `space-between` | Dòng đầu sát mép trên, dòng cuối sát mép dưới |
| `space-around` / `space-evenly` | Khoảng trống chia đều giữa các dòng |
| `stretch` | Các dòng giãn ra lấp đầy container (default khi wrap) |

> **Cách đọc bảng này:** mỗi dòng là một giá trị tác động lên **cả cụm các dòng** (không phải từng item). Hãy hình dung `align-content` như người xếp các tầng bánh trong hộp: dồn hết lên đáy, căn giữa hộp, hay chia đều khe giữa các tầng — nhưng chỉ có tác dụng khi hộp có nhiều tầng (nhiều dòng do wrap).

## Ví dụ

Gallery nhiều hàng trong khung cao cố định — muốn các hàng dàn đều thay vì dồn lên trên:

> 📄 **Code ví dụ:** [`examples/02-vi-du.css`](examples/02-vi-du.css)

> 💡 **Nhớ nhanh:** `align-items` căn từng item trong dòng; `align-content` căn cả các **dòng** với nhau. Mở `index.html` kèm `styles/` để thử.

Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.

> **Tóm gọn 1 câu:** `align-content` là cách "xếp các tầng bánh trong hộp" — chỉ hoạt động khi có nhiều dòng (wrap) và điều khiển khoảng trống giữa các dòng với nhau.

## Tài liệu tham khảo

- [CSS-Tricks — A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [freeCodeCamp — CSS Flexbox Tutorial with Cheat Sheet](https://www.freecodecamp.org/news/css-flexbox-tutorial-with-cheatsheet/)
