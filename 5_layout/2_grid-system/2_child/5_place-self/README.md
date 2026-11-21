# 5. `place-self` — shorthand của align-self + justify-self

> **Tóm tắt tiếng Việt:** `place-self` gộp `align-self` (trục block, giá trị đầu) và `justify-self` (trục inline, giá trị thứ hai) vào một khai báo cho từng item. Ví dụ `place-self: center` căn giữa item trong ô theo cả hai chiều.
>
> *Bài gốc tiếng Anh chỉ có nội dung copy nhầm từ `align-self` nên đã được viết lại hoàn toàn bằng tiếng Việt (file gốc quá ngắn và sai nội dung).*

> 📄 **Code ví dụ:** [`examples/01-5-place-self-shorthand-cua-align-self-justify.css`](examples/01-5-place-self-shorthand-cua-align-self-justify.css)

Mục này nói về cách "gom hai lệnh thành một": thay vì căn item hai lần (dọc một dòng, ngang một dòng), `place-self` gộp cả hai vào một khai báo. Đọc để viết CSS gọn hơn khi cần căn một item theo cả hai chiều.

Ví von: nếu `align-self` và `justify-self` là hai lần dán ghi-chú cho một item thì `place-self` là một tờ giấy ghi cả hai dòng — giá trị đầu luôn là **dọc** (align/block), giá trị sau là **ngang** (justify/inline). Nếu chỉ viết một giá trị, nó áp dụng cho cả hai chiều.

| Viết tắt | Tương đương |
|----------|-------------|
| `place-self: center` | `align-self: center; justify-self: center;` — căn giữa ô theo cả 2 trục |
| `place-self: start end` | `align-self: start; justify-self: end;` |
| `place-self: end start` | `align-self: end; justify-self: start;` |

> **Cách đọc bảng này:** cột trái là code bạn viết, cột phải là hai dòng CSS tương đương nó sinh ra. Chú ý thứ tự giá trị: **đầu tiên = align (dọc), thứ hai = justify (ngang)** — hai dòng cuối của bảng là ví dụ cho thấy đổi thứ tự là đổi kết quả.

> 📄 **Code ví dụ:** [`examples/02-5-place-self-shorthand-cua-align-self-justify.css`](examples/02-5-place-self-shorthand-cua-align-self-justify.css)

> 💡 Bảng họ "place": `place-items` (container), `place-content` (container), `place-self` (item) — đều là cặp `<align> <justify>`. Nhớ quy tắc: **align = dọc (block), justify = ngang (inline)** trong grid.

> **Tóm gọn 1 câu:** `place-self` là "hai vé một lần in" — giá trị đầu căn dọc, giá trị sau căn ngang, chỉ một dòng khai báo cho một item.

## Tài liệu tham khảo

- [MDN — place-self](https://developer.mozilla.org/en-US/docs/Web/CSS/place-self)
- [CSS-Tricks — A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)

