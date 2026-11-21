# Mini project: Calm Breeze — animation chữ + background

> **Mô tả:** Demo animation dựng trên thư viện [Calm Breeze Landing Page](https://codepen.io/Marko-Kudrjavcev/pen/mdEzzKQ) (Marko Kudrjavcev). Hiệu ứng chính (chữ chạy, nền đổi màu, trái tim nhấp nháy) là **CSS thuần** với `@keyframes` và `animation-*`; file `app.js` chỉ thêm hiệu ứng parallax nền theo chuyển động chuột (mượt hơn nhờ `requestAnimationFrame`).

Mục này giới thiệu một mini project để "tay chân biết việc" sau phần lý thuyết animation: đọc cấu trúc file, biết vai trò từng file, rồi mở demo lên mổ xẻ. Ví von: đây là phòng tập thực hành — lý thuyết `@keyframes` ở chương trên là giáo án, còn đây là lúc bạn thực sự nhảy.

## Cấu trúc file

| File | Vai trò |
|------|---------|
| `index.html` | Khung markup: các `<span>` ký tự để animation chữ chạy lần lượt |
| `background.css` | Animation nền: màu background chuyển động theo `@keyframes` |
| `text.css` | Animation chữ: ký tự xuất hiện lần lượt (dùng `animation-delay` cho từng span) |
| `app.js` | (Bổ sung) parallax nền theo chuột bằng `requestAnimationFrame` |

> **Cách đọc bảng này:** đọc theo cột "Vai trò" để biết mỗi hiệu ứng sống ở file nào — muốn sửa màu nền chuyển động thì vào `background.css`, muốn chữ xuất hiện nhanh/chậm hơn thì chỉnh `animation-delay` trong `text.css`, còn `app.js` tách riêng vì parallax là phần JS duy nhất.

## Kiến thức luyện được

Đọc mục này để biết làm xong project bạn "ra nghề" được gì — nếu mục nào còn lơ mơ thì quay lại lý thuyết tương ứng.

- Khai báo `@keyframes` và gắn vào phần tử qua `animation-name` / `animation-duration`
- Kết hợp nhiều animation trên một phần tử (viết trong shorthand `animation`)
- Dùng `animation-delay` + nhiều `<span>` để tạo hiệu ứng chữ chạy theo từng ký tự — ví von: mỗi ký tự là một diễn viên, `animation-delay` là tờ lịch diễn riêng bảo "cậu vào sân chậm hơn chị ấy 0.1 giây"
- `animation-iteration-count: infinite` cho hiệu ứng lặp vô hạn

## Cách chạy

Mở `index.html` trực tiếp trong trình duyệt (không cần build) — hoặc dùng extension Live Server trong VS Code để xem trực tiếp khi sửa code.

> **Tóm gọn 1 câu:** Calm Breeze là "bàn thí nghiệm" cho cả chương animation: CSS thuần làm diễn viên chính, JS chỉ vào vai phụ phụ trợ nền parallax.

