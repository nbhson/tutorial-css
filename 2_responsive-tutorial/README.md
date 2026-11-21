# 2. Responsive Design Hiện Đại

> Không chỉ là `@media`. Responsive hiện đại dùng `clamp()`, fluid type, logical properties và container queries để xây layout tự thích ứng mà không cần breakpoint rời rạc.

## 1. `clamp()` — giá trị "chảy" giữa min và max

Mục này nói về hàm `clamp()` — công cụ giúp giá trị CSS tự co giãn trong một khoảng cho phép, thay vì phải nhảy bậc theo từng breakpoint.

`clamp(min, preferred, max)` trả về giá trị nằm trong khoảng [min, max], dựa trên biểu thức preferred. Thường dùng cho font-size, padding, gap. Ví von: giống như vòi nước có van giới hạn — dòng chảy (kích thước) tự điều chỉnh theo áp lực, nhưng không bao giờ nhỏ hơn van dưới hay tràn qua van trên.

> 📄 **Code ví dụ:** [`examples/01-1-clamp-gia-tri-chay-giua-min-va.css`](examples/01-1-clamp-gia-tri-chay-giua-min-va.css)

Xem thêm: [MDN – clamp()](https://developer.mozilla.org/en-US/docs/Web/CSS/clamp).

> **Tóm gọn 1 câu:** `clamp(min, ideal, max)` là "van điều tiết" — giá trị chảy mượt theo màn hình nhưng không bao giờ lọt ra ngoài hai giới hạn.

## 2. Fluid Typography — typography không cần breakpoint

Mục này áp dụng `clamp()` vào đúng việc lặt vặt nhất nhưng hay gặp nhất: cho cỡ chữ tự lớn nhỏ theo màn hình mà không liệt kê từng breakpoint.

Thay vì liệt kê font-size cho từng breakpoint, dùng `clamp()` với đơn vị `vw` để type "chảy" mượt giữa các kích thước — giống như chữ viết tự co giãn theo khung ảnh thay vì phải cắt lại từng kích thước:

> 📄 **Code ví dụ:** [`examples/02-2-fluid-typography-typography-khong-can-breakpoint.css`](examples/02-2-fluid-typography-typography-khong-can-breakpoint.css)

Công cụ hỗ trợ tính slope/intercept: <https://utopia.fity.club> giúp generate scale tùy ý.

> **Tóm gọn 1 câu:** Fluid typography là "chữ có độ co giãn" — một dòng `clamp()` thay cho cả bảng breakpoint.

## 3. CSS Container Queries — responsive theo container

Mục này nói về container queries — bước ngoặt giúp component tự biết cách "ở đoan trang" tùy chỗ nó được đặt, thay vì phải dò xem viewport rộng bao nhiêu.

`clamp()` + container queries là bộ đôi responsive hiện đại. Container queries trả lời câu hỏi: "component này có bao nhiêu chỗ?" thay vì "viewport rộng bao nhiêu?". Ví von: cùng một người nhân viên, làm việc gọn gàng hay bày biện rộng rãi tùy vào kích thước bàn làm việc được giao — chứ không phải tùy cả sảnh công ty.

> 📄 **Code ví dụ:** [`examples/03-3-css-container-queries-responsive-theo-container.css`](examples/03-3-css-container-queries-responsive-theo-container.css)

Xem thêm: [MDN – Container Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_containment).

> **Tóm gọn 1 câu:** Container queries cho component "nhìn quanh chỗ ngồi của mình" — cùng một card, rộng thì bày đầy, chật thì xếp gọn.

## 4. Logical Properties — layout đa hướng (LTR/RTL, vertical writing)

Mục này nói về logical properties — cách viết "trái/phải" thành "đầu dòng/cuối dòng" để layout tự lật đúng hướng khi ngôn ngữ đọc ngược chiều.

Dùng `inline-start`/`inline-end`, `block-start`/`block-end` thay cho `left`/`right`, `top`/`bottom`. Code tự động đúng hướng với RTL (Arabic, Hebrew). Ví von: thay vì chỉ dẫn "rẽ trái", bạn ghi "rẽ theo hướng đọc" — ai đọc từ phải sang trái cũng tự hiểu đúng.

> 📄 **Code ví dụ:** [`examples/04-4-logical-properties-layout-a-huong-ltr-rtl.css`](examples/04-4-logical-properties-layout-a-huong-ltr-rtl.css)

Xem thêm: [MDN – Logical properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_logical_properties_and_values).

> **Tóm gọn 1 câu:** Logical properties là "chỉ đường theo hướng đọc" — một bản CSS chạy đúng cả trang đọc xuôi lẫn đọc ngược.

## 5. `min()`, `max()`, `clamp()` trong layout

Mục này nói về bộ ba hàm `min()`/`max()`/`clamp()` dùng ngoài typography — áp vào width, gap để layout tự chọn kích thước hợp lý nhất.

> 📄 **Code ví dụ:** [`examples/05-5-min-max-clamp-trong-layout.css`](examples/05-5-min-max-clamp-trong-layout.css)

> **Tóm gọn 1 câu:** `min()`/`max()`/`clamp()` là "ban giám khảo" chọn giá trị — CSS tự quyết số cuối cùng giữa nhiều phương án bạn đưa ra.

## 6. Responsive dựa trên container query units

Mục này nói về các đơn vị mới (`cqw`, `cqh`...) — đo kích thước theo container thay vì theo viewport.

> 📄 **Code ví dụ:** [`examples/06-6-responsive-dua-tren-container-query-units.css`](examples/06-6-responsive-dua-tren-container-query-units.css)

> **Tóm gọn 1 câu:** Container query units là "thước đo trong phòng" — mọi thứ tính theo container chứa nó, không phải cả tòa nhà (viewport).

## 7. Responsive images

Mục này nói về cách cho ảnh tự chọn kích thước/độ phân giải phù hợp — nhẹ máy cho điện thoại, sắc nét cho màn lớn.

> 📄 **Code ví dụ:** [`examples/07-7-responsive-images.html`](examples/07-7-responsive-images.html)

> **Tóm gọn 1 câu:** Responsive images là "giao đúng cỡ áo cho đúng người" — màn nhỏ nhận ảnh nhẹ, màn lớn nhận ảnh nét.

## 8. Responsive spacing strategy — hệ thống spacing dựa trên clamp

Mục này nói về cách xây hệ thống khoảng cách (spacing) co giãn mượt bằng `clamp()` thay vì định cứng px.

> 📄 **Code ví dụ:** [`examples/08-8-responsive-spacing-strategy-he-thong-spacing-dua.css`](examples/08-8-responsive-spacing-strategy-he-thong-spacing-dua.css)

> **Tóm gọn 1 câu:** Spacing dựa trên `clamp()` là "lưng ghế tự điều chỉnh" — đệm giữa các thành phần nở ra hoặc thu vào theo màn hình.

## 9. Responsive pattern: Grid → Stack → Card

Mục này nói về một pattern responsive kinh điển: layout xếp dọc khi chật, trải grid khi rộng — dùng chung một cấu trúc HTML.

> 📄 **Code ví dụ:** [`examples/09-9-responsive-pattern-grid-stack-card.css`](examples/09-9-responsive-pattern-grid-stack-card.css)

> **Tóm gọn 1 câu:** Pattern Grid → Stack → Card là "đội hình co giãn" — chỗ hẹp xếp hàng dọc, chỗ rộng dàn thành lưới, HTML không đổi.

## Tài liệu tham khảo

- MDN Responsive Design: <https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design>
- Utopia (fluid type generator): <https://utopia.fity.club>
- CSS Tricks – Complete Guide to CSS Logical Properties: <https://css-tricks.com/css-logical-properties>
- Container Queries MDN: <https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_containment>
