# place-content

> **🇻🇳 Tóm tắt:** `place-content` là shorthand của `align-content` (giá trị đầu) + `justify-content` (giá trị thứ hai) — căn cả khối lưới theo hai chiều trong một khai báo.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*


place-content sets both the align-content and justify-content properties in a single declaration.

Values:
- <align-content> / <justify-content> – The first value sets align-content, the second value justify-content. If the second value is omitted, the first value is assigned to both properties.

```scss
.container {
  place-content: start | end | center | stretch | space-around | space-between | space-evenly;    
}
```
