# place-items

> **🇻🇳 Tóm tắt:** `place-items` là shorthand của `align-items` (giá trị đầu) + `justify-items` (giá trị thứ hai). `place-items: center` là cách căn giữa "hai chiều" kinh điển trong Grid.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*


place-items sets both the align-items and justify-items properties in a single declaration.

Values:
- <align-items> / <justify-items> – The first value sets align-items, the second value justify-items. If the second value is omitted, the first value is assigned to both properties.

```scss
.container {
  display: grid;
  place-items: center;
}
```
