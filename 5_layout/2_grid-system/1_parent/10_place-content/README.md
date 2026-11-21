# place-content

> **🇻🇳 Tóm tắt:** `place-content` là shorthand của `align-content` (giá trị đầu) + `justify-content` (giá trị thứ hai) — căn cả khối lưới theo hai chiều trong một khai báo.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*


place-content sets both the align-content and justify-content properties in a single declaration.

Ví von: thay vì dặn dò hai lần (một lần theo chiều dọc, một lần theo chiều ngang), bạn viết một mẩu giấy ghi chú duy nhất cho cả hai chiều.

Values:
- <align-content> / <justify-content> – The first value sets align-content, the second value justify-content. If the second value is omitted, the first value is assigned to both properties.

> 📄 **Code ví dụ:** [`examples/01-place-content.scss`](examples/01-place-content.scss)

> **Tóm gọn 1 câu:** `place-content` là "một lời dặn cho hai chiều" — giá trị đầu lo dọc (`align-content`), giá trị sau lo ngang (`justify-content`), thiếu giá trị sau thì cả hai dùng chung.
