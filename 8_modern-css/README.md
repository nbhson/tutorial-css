# 8. Modern CSS (2025 – 2026)

> Tổng hợp các tính năng CSS hiện đại nhất đang dùng được trong production. Nội dung tổng hợp từ **State of CSS 2025/2026**, **CSS Wrapped 2025** (Chrome for Developers) và spec chính thức của W3C.

Từ năm 2023 đến 2026, CSS có những bước nhảy vọt lớn nhất trong một thập kỷ. Nhiều việc trước đây **bắt buộc phải dùng JavaScript** (định vị tooltip, style con dựa trên trạng thái cha, animation theo scroll...) giờ đã được giải quyết hoàn toàn bằng CSS thuần. Ví von: như thể CSS vừa được "nâng cấp linh kiện bản lớn" — những việc phải thuê giúp việc (JS) giờ chủ nhà tự làm được.

## Tổng quan Browser Support (tháng 10/2026)

Mục này là "bảng giá niêm yết" hỗ trợ trình duyệt của từng tính năng. Đọc trước khi dùng để biết tính năng nào dùng thẳng được, tính năng nào phải kèm phương án dự phòng.

| Feature | Chrome | Firefox | Safari |
| --- | --- | --- | --- |
| Native Nesting | 112+ | 117+ | 16.5+ |
| Container Queries | 105+ | 110+ | 16+ |
| `:has()` | 105+ | 121+ | 15.4+ |
| Anchor Positioning | 125+ | 131+ | 18+ |
| View Transitions (same-document) | 111+ | 126+ | 18+ |
| Subgrid | 117+ | 71+ | 16+ |
| `oklch()` / `color-mix()` | 111+ | 113+ | 15.4+ |
| `@layer` | 99+ | 97+ | 15.4+ |
| `@property` | 85+ | 128+ | 16.4+ |
| Scroll-driven Animations | 115+ | chưa ổn định | đang beta |

> **Cách đọc bảng này:** mỗi dòng là một tính năng, ba cột số là **phiên bản tối thiểu** của từng trình duyệt bắt đầu hỗ trợ (số càng nhỏ = càng lâu đời = càng an toàn). Dòng nào có chữ "chưa ổn định" / "đang beta" thì đừng dùng làm tính năng sống còn — chỉ nên dùng như lớp enhancement.

Tài liệu tham khảo chính thức:

- MDN CSS: <https://developer.mozilla.org/en-US/docs/Web/CSS>
- State of CSS: <https://2025.stateofcss.com> và <https://2026.stateofcss.com>
- CSS Wrapped 2025: <https://chrome.dev/css-wrapped-2025/>

---

## 1. Native CSS Nesting (Lồng nhau trong CSS thuần)

Mục này nói về việc viết CSS lồng nhau **không cần Sass/SCSS** nữa — thứ mà ai dùng SCSS cũng quen tay. Đọc để biết cú pháp và cái bẫy selector lồng của CSS native.

Từ Chrome 112, Safari 16.5, Firefox 117, bạn có thể viết CSS lồng nhau **không cần Sass/SCSS**. Xem thêm: [MDN – CSS Nesting](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_nesting).

> 📄 **Code ví dụ:** [`examples/01-1-native-css-nesting-long-nhau-trong-css.css`](examples/01-1-native-css-nesting-long-nhau-trong-css.css)

**Lưu ý:** khác với SCSS, CSS native yêu cầu selector lồng nhau phải tham chiếu đến cha (dùng `&` hoặc bắt đầu bằng phần tử/combinator). Quy tắc an toàn: luôn viết `&` ở đầu selector lồng nhau.

> 📄 **Code ví dụ:** [`examples/02-1-native-css-nesting-long-nhau-trong-css.css`](examples/02-1-native-css-nesting-long-nhau-trong-css.css)

> **Tóm gọn 1 câu:** Native nesting cho bạn viết CSS lồng nhau như SCSS nhưng thuần CSS — chỉ cần nhớ quy tắc "luôn có `&`" là khỏi vấp.

---

## 2. Container Queries (`@container`) — component tự responsive

Mục này nói về bước nhảy "component biết tự chăm sóc bản thân": style thay đổi theo kích thước **hộp chứa** chứ không phải kích thước màn hình. Đọc để viết component dùng được ở cả sidebar hẹp lẫn vùng nội dung rộng mà không đụng vào media query.

Media queries chỉ biết kích thước **viewport**. Container Queries cho phép một component **phản ứng theo kích thước container chứa nó** — cùng một component hoạt động đúng ở sidebar hẹp lẫn main content rộng. Ví von: media query là con người nhìn **đấu trường** để quyết định mặc gì; container query là con tắc kè hoa nhìn **cái cành cây mình đang bám** để đổi màu — môi trường sát bên mình mới là điều quan trọng.

> 📄 **Code ví dụ:** [`examples/03-2-container-queries-container-component-tu-responsive.css`](examples/03-2-container-queries-container-component-tu-responsive.css)

Container query units — đơn vị tính theo container:

- `cqw` – 1% chiều rộng container, `cqi` – 1% inline size, `cqh` – chiều cao.
- Ví dụ: `font-size: clamp(1rem, 4cqi, 2rem);` — chữ phóng theo container chứ không theo viewport.

Style queries (query theo giá trị CSS, ví dụ `@container style(--theme: dark)`) hiện chỉ Chrome hỗ trợ — dùng có chọn lọc. Xem: [MDN – Container Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_containment).

> **Tóm gọn 1 câu:** Container queries chuyển "điểm đo" từ màn hình sang hộp chứa — component tự responsive đúng chỗ nó đang sống.

---

## 3. `:has()` — "Parent Selector" mà cộng đồng chờ 20 năm

Mục này nói về selector mà CSS sinh ra đã thiếu: chọn phần tử **dựa vào con của nó**. Đọc để mở khóa cả đống pattern trước đây phải nhờ JS kiểm tra DOM.

`:has()` cho phép chọn phần tử cha **dựa trên con**, hoặc chọn phần tử trước đó — thứ trước đây bất khả thi trong CSS. Ví von: trong 20 năm, CSS chỉ có thể "nhìn xuống" (cha chọn con) như ông nội gọi cháu; `:has()` cho phép "nhìn lên" — con có hành động gì thì ông cụ phản ứng theo.

> 📄 **Code ví dụ:** [`examples/04-3-has-parent-selector-ma-cong-ong-cho.css`](examples/04-3-has-parent-selector-ma-cong-ong-cho.css)

Ứng dụng kinh điển: grid thiếu phần tử cuối vẫn tự cán đều:

> 📄 **Code ví dụ:** [`examples/05-3-has-parent-selector-ma-cong-ong-cho.css`](examples/05-3-has-parent-selector-ma-cong-ong-cho.css)

Xem thêm: [MDN – :has()](https://developer.mozilla.org/en-US/docs/Web/CSS/:has).

> **Tóm gọn 1 câu:** `:has()` là "ông bố cuối cùng cũng nghe ngóng được con mình" — CSS giờ style ngược chiều được, không cần JS soi DOM.

---

## 4. Anchor Positioning — Tooltip/Popover không cần JavaScript

Mục này nói về cách "neo" một phần tử vào phần tử khác và để trình duyệt tự lo chuyện va chạm cạnh màn hình — công việc của mọi thư viện tooltip suốt nhiều năm. Đọc để thay được cả một package chỉ bằng vài dòng CSS.

Với Anchor Positioning (spec Level 1: <https://www.w3.org/TR/css-anchor-position-1/>), bạn "neo" một phần tử vào phần tử khác và để trình duyệt tự xử lý va chạm cạnh màn hình. Ví von: như dán ghi chú lên một trang sách — tờ giấy note bám chặt theo trang đó, và trình duyệt đủ khôn để tự né nếu bạn ghé sát mép sách.

> 📄 **Code ví dụ:** [`examples/06-4-anchor-positioning-tooltip-popover-khong-can-javascript.html`](examples/06-4-anchor-positioning-tooltip-popover-khong-can-javascript.html)

> 📄 **Code ví dụ:** [`examples/07-4-anchor-positioning-tooltip-popover-khong-can-javascript.css`](examples/07-4-anchor-positioning-tooltip-popover-khong-can-javascript.css)

Từ **Chrome 143 (10/2025)** có thêm **anchored container queries** (Anchor Positioning Level 2): dùng `container-type: anchored` + `@container anchored(fallback: flip-block)` để biết tooltip đã bị lật sang vị trí dự phòng hay chưa — từ đó tự đổi chiều mũi tên mà không cần JS:

> 📄 **Code ví dụ:** [`examples/08-4-anchor-positioning-tooltip-popover-khong-can-javascript.css`](examples/08-4-anchor-positioning-tooltip-popover-khong-can-javascript.css)

Kết hợp với **Popover API** (`popover` + `popovertarget`) là bộ đôi thay thế hoàn toàn thư viện tooltip/popover. Xem: [Chrome for Developers – Anchored container queries](https://developer.chrome.com/blog/anchored-container-queries).

> **Tóm gọn 1 câu:** Anchor Positioning = "dán ghi chú thông minh" — element bám vào anchor, trình duyệt tự né mép màn hình, JS khỏi tham dự.

---

## 5. CSS Color Level 4 — `oklch()` và `color-mix()`

Mục này nói về cách chọn màu "hiểu mắt người" hơn: màu sắc đều về độ sáng cảm nhận, giúp design system nhất quán. Đọc để chuyển dần từ hex/hsl sang hệ màu hiện đại.

Không gian màu `oklch()` (Lightness, Chroma, Hue) cho màu **đồng nhất về độ sáng cảm nhận**, dễ xây dựng design system hơn `hex`/`hsl`: ví von — hex/hsl là màu sơn đánh số theo công thức hóa học, còn `oklch` là màu mô tả bằng lời "sáng bao nhiêu, rực bao nhiêu, tông gì" — hai màu cùng Lightness thì nhìn "đẳng" nhau, dù sắc khác nhau. Còn `color-mix()` như chiếc cốc pha màu ngay trong CSS: đổ hai màu vào, tuông ra phiên bản trộn.

> 📄 **Code ví dụ:** [`examples/09-5-css-color-level-4-oklch-va-color.css`](examples/09-5-css-color-level-4-oklch-va-color.css)

Xem thêm: [MDN – oklch()](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/oklch), [MDN – color-mix()](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/color-mix).

> **Tóm gọn 1 câu:** `oklch()` chọn màu theo "cảm nhận mắt người" (sáng–rực–tông), `color-mix()` pha màu ngay trong CSS — cặp bài trùng cho design system.

---

## 6. Subgrid — Lưới con thẳng hàng với lưới cha

Mục này nói về cách các grid item "mượn" track của lưới cha thay vì tự kẻ lưới riêng. Đọc để giải bài toán card lệch hàng kinh điển.

Subgrid cho phép phần tử con dùng lại **track của lưới cha**, giải quyết bài toán kinh điển: các card có chiều cao tiêu đề/khác nhau vẫn thẳng hàng theo hàng. Ví von: các căn hộ không tự lo điện nước nữa mà cắm vào "lưới điện chung của tòa nhà" — hàng nào của mỗi card cũng thẳng hàng với hàng xóm.

> 📄 **Code ví dụ:** [`examples/10-6-subgrid-luoi-con-thang-hang-voi-luoi.css`](examples/10-6-subgrid-luoi-con-thang-hang-voi-luoi.css)

Xem thêm: [MDN – Subgrid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Subgrid).

> **Tóm gọn 1 câu:** Subgrid là "dây điện chung của tòa nhà" — lưới con mượn track lưới cha, mọi card liền kề tự thẳng hàng.

---

## 7. View Transitions API — Chuyển cảnh mượt mà chỉ bằng CSS

Mục này nói về chuyển cảnh khi DOM thay đổi (như khi chuyển trang SPA): chụp ảnh trạng thái cũ – mới rồi animate giữa hai ảnh. Đọc để làm hiệu ứng chuyển cảnh "chất điện ảnh" mà không cần thư viện.

Same-document View Transitions (Chrome 111+, Safari 18+, Firefox 126+) cho phép animate khi DOM thay đổi: ví von — trình duyệt tự chụp **tấm hình cũ**, để bạn cập nhật DOM, rồi chụp **tấm hình mới** và tự chiếu hiệu ứng chuyển giữa hai tấm hình, như hiệu ứng vắt trang của cuốn photo album.

> 📄 **Code ví dụ:** [`examples/11-7-view-transitions-api-chuyen-canh-muot-ma.js`](examples/11-7-view-transitions-api-chuyen-canh-muot-ma.js)

> 📄 **Code ví dụ:** [`examples/12-7-view-transitions-api-chuyen-canh-muot-ma.css`](examples/12-7-view-transitions-api-chuyen-canh-muot-ma.css)

Xem thêm: [MDN – View Transition API](https://developer.mozilla.org/en-US/docs/Web/API/View_Transitions_API).

> **Tóm gọn 1 câu:** View Transitions là "album ảnh tự vắt trang" — trình duyệt chụp ảnh trước/sau khi DOM đổi rồi tự animate giữa hai ảnh.

---

## 8. `@property` — Biến CSS có kiểu dữ liệu và có thể transition

Mục này nói về cách "chứng minh nhân thân" cho biến CSS: có kiểu dữ liệu, giá trị mặc định, quy tắc kế thừa. Đọc để animate được những thứ trước đây "chết lì" như gradient.

`@property` (CSS Houdini) khai báo custom property với **type, giá trị mặc định, kế thừa** — mở khóa animate được các thuộc tính trước đây không animate nổi (gradient, số lượng...). Ví von: biến CSS thường là "hộp đen" — trình duyệt chỉ thấy một chuỗi ký tự, không biết bên trong là màu hay số nên không cách nào nội suy được; `@property` dán nhãn rõ "hộp này đựng màu" thế là trình duyệt biết cách pha giữa hai mốc.

> 📄 **Code ví dụ:** [`examples/13-8-property-bien-css-co-kieu-du-lieu.css`](examples/13-8-property-bien-css-co-kieu-du-lieu.css)

Xem thêm: [MDN – @property](https://developer.mozilla.org/en-US/docs/Web/CSS/@property).

> **Tóm gọn 1 câu:** `@property` dán "nhãn kiểu" lên biến CSS — trình duyệt hiểu biến đang đựng gì nên biết cách chuyển tiếp mượt giữa các giá trị.

---

## 9. `@layer` — Kiểm soát độ ưu tiên (Cascade Layers)

Mục này nói về cách "chia sân đấu" cho độ ưu tiên CSS: thay vì xả `!important` như thuốc nổ, bạn quy định sẵn layer nào thắng layer nào. Đọc để dừng cuộc chiến specificity với CSS của thư viện bên thứ ba.

Thay vì phải dùng `!important` để đấu với thư viện bên thứ 3, chia CSS thành các layer với độ ưu tiên **khai báo sẵn**: ví von — như tòa nhà quy định sẵn thứ tự ưu tiên phòng họp: phòng riêng của bạn luôn thắng phòng chung, phòng chung thắng sảnh khách; không ai cần "gào to" (`!important`) để chiếm phòng.

> 📄 **Code ví dụ:** [`examples/14-9-layer-kiem-soat-o-uu-tien-cascade.css`](examples/14-9-layer-kiem-soat-o-uu-tien-cascade.css)

Xem thêm: [MDN – @layer](https://developer.mozilla.org/en-US/docs/Web/CSS/@layer).

> **Tóm gọn 1 câu:** `@layer` là "thứ tự ưu tiên khai báo sẵn" — layer nào viết sau thắng, hết thời `!important` đấu nhau.

---

## 10. Scroll-driven Animations — Animation theo scroll, không cần JS

Mục này nói về cách gắn tiến trình animation với tiến trình cuộn trang — thanh tiến trình, hiệu ứng parallax, reveal on scroll — toàn bộ bằng CSS. Đọc để bỏ được `scroll` event listener và được lợi cả hiệu năng.

Thay vì lắng nghe `scroll` event bằng JavaScript, để CSS trực tiếp gắn tiến trình animation với tiến trình scroll. Ví von: JS cũ như người đứng cửa sổ đếm "đã cuộn tới đâu" rồi hét vào trong bảo sân khấu thay bối cảnh từng khung hình; scroll-driven animation là rạp chiếu phim đồng bộ sẵn — màn chiếu tự trôi đúng nhịp với tay bạn cuộn.

> 📄 **Code ví dụ:** [`examples/15-10-scroll-driven-animations-animation-theo-scroll-khong.css`](examples/15-10-scroll-driven-animations-animation-theo-scroll-khong.css)

Lưu ý: tính đến 2026, Firefox chưa hỗ trợ ổn định — nên dùng làm **progressive enhancement** (trang vẫn hoạt động bình thường khi thiếu). Xem: [MDN – Scroll-driven animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll-driven_animations).

> **Tóm gọn 1 câu:** Scroll-driven animations là "màn chiếu đồng bộ với tay cuộn" — mượt, rẻ hiệu năng, nhưng nhớ kèm fallback vì Firefox chưa chơi.

---

## 11. Feature tổng hợp: một component hiện đại

Mục này là "màn tổng duyệt": ghép các tính năng vừa học vào một component duy nhất. Đọc code ví dụ để thấy các tính năng không sống riêng lẻ mà nâng đỡ nhau thế nào.

> 📄 **Code ví dụ:** [`examples/16-11-feature-tong-hop-mot-component-hien-ai.css`](examples/16-11-feature-tong-hop-mot-component-hien-ai.css)

## Kết luận

Mục này chốt lại chiến lược dùng CSS hiện đại mà không "đâm lao dăm gỗ": tính năng mới là gia vị, sự an toàn của layout vẫn là món chính. Đọc 3 điểm dưới đây trước khi áp dụng vào dự án thật.

Chiến lược tiếp cận CSS hiện đại 2026:

1. **Progressive enhancement**: mọi tính năng trên đều "graceful degrade" — trình duyệt cũ chỉ thiếu hiệu ứng, không vỡ layout. Ví von: dùng tính năng mới như lắp đèn LED trang trí lên ngôi nhà — có đèn thì đẹp hơn, không đèn thì ngôi nhà vẫn ở được bình thường.
2. Ưu tiên giải quyết bằng CSS trước khi viết JS (tooltip, reveal on scroll, theme...).
3. Theo dõi support tại <https://caniuse.com> và <https://web-platform-dx.github.io/web-features/>.

> **Tóm gọn 1 câu:** CSS hiện đại 2026 dùng theo nguyên tắc "ladder nâng dần": hiện đại trước, an toàn sau — thiếu hiệu ứng thì tiếc, vỡ layout thì chết.
