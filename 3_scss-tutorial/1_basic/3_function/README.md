# Sass Function

Mục này giới thiệu cách dùng hàm trong SCSS — nơi bạn "gọi tên" một đoạn logic đã được đóng gói sẵn, giống như gọi món trong menu thay vì tự nấu từ đầu.

## Build-in

Hàm `Math`: Sass cung cấp các hàm tính toán cơ bản như `add()`, `subtract()`, `multiply()`, `divide()` để thực hiện các phép tính toán đơn giản. Ví von: đây là "tủ dụng cụ có sẵn" — mở nắp là dùng, không phải tự rèn dụng cụ.

> 📄 **Code ví dụ:** [`examples/01-build-in.scss`](examples/01-build-in.scss)

## Cách define một function bằng @mixin

Khi không có hàm dựng sẵn nào vừa ý, bạn tự "đóng khuôn" một hàm riêng bằng `@mixin` — nấu một lần, gọi món mãi về sau.

> 📄 **Code ví dụ:** [`examples/02-cach-define-mot-function-bang-mixin.scss`](examples/02-cach-define-mot-function-bang-mixin.scss)

> **Tóm gọn 1 câu:** Hàm SCSS là "món trong menu": built-in là món nhà bếp có sẵn, `@mixin` là công thức bạn tự tạo ra để gọi đi gọi lại.
