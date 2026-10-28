# 5. `place-self` — shorthand của align-self + justify-self

> **Tóm tắt tiếng Việt:** `place-self` gộp `align-self` (trục block, giá trị đầu) và `justify-self` (trục inline, giá trị thứ hai) vào một khai báo cho từng item. Ví dụ `place-self: center` căn giữa item trong ô theo cả hai chiều.
>
> *Bài gốc tiếng Anh chỉ có nội dung copy nhầm từ `align-self` nên đã được viết lại hoàn toàn bằng tiếng Việt (file gốc quá ngắn và sai nội dung).*

```css
.item {
  /* place-self: <align-self> <justify-self>; */
  place-self: center;        /* = align-self: center; justify-self: center; */
  place-self: start end;     /* dọc: start, ngang: end */
  place-self: center stretch;
}
```

| Viết tắt | Tương đương |
|----------|-------------|
| `place-self: center` | `align-self: center; justify-self: center;` — căn giữa ô theo cả 2 trục |
| `place-self: start end` | `align-self: start; justify-self: end;` |
| `place-self: end start` | `align-self: end; justify-self: start;` |

```css
/* Kinh điển: căn giữa tuyệt đối một item trong ô grid */
.wrapper {
  display: grid;
  place-items: center;   /* trên container */
}
/* hoặc trên item: */
.item { place-self: center; }
```

> 💡 Bảng họ "place": `place-items` (container), `place-content` (container), `place-self` (item) — đều là cặp `<align> <justify>`. Nhớ quy tắc: **align = dọc (block), justify = ngang (inline)** trong grid.

## Tài liệu tham khảo

- [MDN — place-self](https://developer.mozilla.org/en-US/docs/Web/CSS/place-self)
- [CSS-Tricks — A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)

