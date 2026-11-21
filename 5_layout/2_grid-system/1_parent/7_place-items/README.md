# place-items

> **🇻🇳 Tóm tắt:** `place-items` là shorthand của `align-items` (giá trị đầu) + `justify-items` (giá trị thứ hai). `place-items: center` là cách căn giữa "hai chiều" kinh điển trong Grid.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*


place-items sets both the align-items and justify-items properties in a single declaration.

Giống như gửi một tin nhắn duy nhất cho cả hai bộ phận dọc và ngang thay vì gọi từng nơi một — một khai báo, item được căn theo cả hai chiều.

Values:
- <align-items> / <justify-items> – The first value sets align-items, the second value justify-items. If the second value is omitted, the first value is assigned to both properties.

> 📄 **Code ví dụ:** [`examples/01-place-items.scss`](examples/01-place-items.scss)

> **Tóm gọn 1 câu:** `place-items` là "một tin nhắn cho hai chiều" — giá trị đầu lo dọc (`align-items`), giá trị sau lo ngang (`justify-items`); viết `place-items: center` là công thức căn giữa kinh điển.
