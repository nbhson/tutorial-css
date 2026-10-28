# Mini project: Calm Breeze — animation chữ + background

> **Mô tả:** Demo animation dựng trên thư viện [Calm Breeze Landing Page](https://codepen.io/Marko-Kudrjavcev/pen/mdEzzKQ) (Marko Kudrjavcev). Hiệu ứng chính (chữ chạy, nền đổi màu, trái tim nhấp nháy) là **CSS thuần** với `@keyframes` và `animation-*`; file `app.js` chỉ thêm hiệu ứng parallax nền theo chuyển động chuột (mượt hơn nhờ `requestAnimationFrame`).

## Cấu trúc file

| File | Vai trò |
|------|---------|
| `index.html` | Khung markup: các `<span>` ký tự để animation chữ chạy lần lượt |
| `background.css` | Animation nền: màu background chuyển động theo `@keyframes` |
| `text.css` | Animation chữ: ký tự xuất hiện lần lượt (dùng `animation-delay` cho từng span) |
| `app.js` | (Bổ sung) parallax nền theo chuột bằng `requestAnimationFrame` |

## Kiến thức luyện được

- Khai báo `@keyframes` và gắn vào phần tử qua `animation-name` / `animation-duration`
- Kết hợp nhiều animation trên một phần tử (viết trong shorthand `animation`)
- Dùng `animation-delay` + nhiều `<span>` để tạo hiệu ứng chữ chạy theo từng ký tự
- `animation-iteration-count: infinite` cho hiệu ứng lặp vô hạn

## Cách chạy

Mở `index.html` trực tiếp trong trình duyệt (không cần build) — hoặc dùng extension Live Server trong VS Code để xem trực tiếp khi sửa code.
