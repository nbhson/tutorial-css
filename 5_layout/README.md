# 5. Layout — Flexbox & CSS Grid

> Phần quan trọng nhất của khóa học: mọi layout web đều xoay quanh **Flexbox** (bố cục 1 chiều) và **CSS Grid** (bố cục 2 chiều). Phần này gồm 2 chương: `1_flexbox/` (8 bài) và `2_grid-system/` (13+5 bài).
>
> ⚠️ **Về ngôn ngữ:** các bài con gốc là tài liệu tiếng Anh (tổng hợp từ CSS-Tricks, freeCodeCamp...). Mỗi bài có **tóm tắt tiếng Việt ở đầu file**; bạn đọc tóm tắt trước, nội dung gốc bên dưới để tham khảo chi tiết và cú pháp đầy đủ.

---

## Chương 1: Flexbox (`1_flexbox/`)

Mục này là mục lục chương Flexbox: 8 bài học theo thứ tự, mỗi bài một thuộc tính. Đọc bảng để chọn lộ trình — đi từ trên xuống dưới là đường ngắn nhất.

Flexbox sắp xếp các item **dọc theo một trục** (main axis). Học theo thứ tự 8 bài:

| Bài | Thuộc tính | Nội dung chính |
|-----|-----------|----------------|
| [1](./1_flexbox/1_flex-direction/) | `flex-direction` | Chọn trục chính: `row` / `column` (kèm `-reverse`). Đổi trục = đổi cả hướng justify/align |
| [2](./1_flexbox/2_justify-content/) | `justify-content` | Căn items **theo trục chính**: `flex-start`, `center`, `space-between`... |
| [3](./1_flexbox/3_align-content/) | `align-content` | Căn **nhiều dòng** (khi có `flex-wrap`) theo trục phụ |
| [4](./1_flexbox/4_align-items/) | `align-items` | Căn từng item **theo trục phụ** (cross axis) — cách căn giữa dọc kinh điển |
| [5](./1_flexbox/5_align-self/) | `align-self` | Ghi đè `align-items` cho **một** item duy nhất |
| [6](./1_flexbox/6_gap/) | `gap` | Khoảng cách giữa các item — thay thế triệt để margin "hack" |
| [7](./1_flexbox/7_grow-shrink-wrap-basis/) | `flex-grow`, `flex-shrink`, `flex-wrap`, `flex-basis` | Bốn thuộc tính chi phối kích thước và xuống dòng |
| [8](./1_flexbox/8_order/) | `order` | Đổi thứ tự hiển thị mà không đổi HTML |

> **Cách đọc bảng này:** mỗi dòng là một bài học, cột "Thuộc tính" là thứ bạn sẽ gõ vào CSS, cột "Nội dung chính" là câu trả lời cho câu hỏi "bài đó giải quyết chuyện gì". Bài 1–3 đặt trên container và lấy gốc ở bài 1 (`flex-direction`) — hiểu bài 1 thì bài 2, 3 gần như tự động hiểu.

**Kiến thức nền cần nhớ trước khi vào bài:**

> 📄 **Code ví dụ:** [`examples/01-chuong-1-flexbox-1-flexbox.css`](examples/01-chuong-1-flexbox-1-flexbox.css)

- **Main axis** đi theo `flex-direction`; **cross axis** vuông góc với nó. `justify-*` luôn tác động lên main axis, `align-*` lên cross axis — nắm được điều này là giải thích được 90% hành vi Flexbox. Ví von: Flexbox như một hàng ghế ở chờ — mọi người xếp dọc theo một trục chính, còn `justify-*` canh vị trí dọc hàng ghế, `align-*` canh độ cao người ngồi.
- Mẹo căn giữa cả hai chiều: `display: flex; justify-content: center; align-items: center;`

> **Tóm gọn 1 câu:** Flexbox là hàng ghế một trục — `flex-direction` chọn hướng hàng ghế, `justify` canh dọc theo hàng, `align` canh vuông góc với hàng.

## Chương 2: CSS Grid (`2_grid-system/`)

Mục này dẫn đường vào chương Grid: thuộc tính chia làm 2 nhóm theo nơi đặt (container hay item), cộng thêm một mục đơn vị & hàm. Đọc để biết "thuộc tính này viết lên ai" — đó là chìa khóa của Grid.

Grid định nghĩa lưới **hàng + cột** rồi đặt item vào ô. Tài liệu gốc tổng hợp từ [CSS-Tricks Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/). Ví von: Grid là việc kẻ ô ly lên cả trang giấy trước, rồi xếp từng mảnh ghép vào ô — khác Flexbox là sắp một hàng người vào ghế.

### `2_grid-system/1_parent/` — thuộc tính đặt trên **container** (13 bài)

| Bài | Thuộc tính | Nội dung chính |
|-----|-----------|----------------|
| [1](./2_grid-system/1_parent/1_rows-columns/) | `grid-template-columns` / `grid-template-rows` | Định nghĩa hàng/cột: `1fr 3fr`, `minmax(10px, 1fr)`, `repeat(5, 1fr)` |
| [2](./2_grid-system/1_parent/2_grid-areas/) | `grid-template-areas` | Vẽ layout bằng tên vùng — nhìn là hiểu ngay cấu trúc trang |
| [3](./2_grid-system/1_parent/3_grid-template/) | `grid-template` | Shorthand của rows + columns + areas |
| [4](./2_grid-system/1_parent/4_gap/) | `gap` / `row-gap` / `column-gap` | Khoảng cách giữa các ô lưới |
| [5](./2_grid-system/1_parent/5_justify-items/) | `justify-items` | Căn nội dung item theo trục inline (ngang) — áp cho toàn bộ |
| [6](./2_grid-system/1_parent/6_align-items/) | `align-items` | Căn nội dung item theo trục block (dọc) |
| [7](./2_grid-system/1_parent/7_place-items/) | `place-items` | Shorthand `align-items justify-items` |
| [8](./2_grid-system/1_parent/8_justify-content/) | `justify-content` | Căn cả lưới trong container khi lưới nhỏ hơn container |
| [9](./2_grid-system/1_parent/9_align-content/) | `align-content` | Như trên nhưng theo trục dọc |
| [10](./2_grid-system/1_parent/10_place-content/) | `place-content` | Shorthand `align-content justify-content` |
| [11](./2_grid-system/1_parent/11_auto-rows-columns/) | `grid-auto-columns` / `grid-auto-rows` | Kích thước cho các track tự sinh (implicit grid) |
| [12](./2_grid-system/1_parent/12_grid-flow/) | `grid-auto-flow` | Cách thuật toán auto-placement điền item: `row`, `column`, `dense` |
| [13](./2_grid-system/1_parent/13_grid/) | `grid` | Shorthand lớn gộp tất cả thuộc tính explicit + implicit |

> **Cách đọc bảng này:** 13 dòng chia theo công năng — bài 1–3 vẽ khung lưới (hàng/cột/vùng), bài 4–7 căn **nội dung item trong ô**, bài 8–10 căn **cả lưới trong container**, bài 11–13 xử lý phần tự sinh và shorthand. Gặp vấn đề cụ thể thì tra theo đúng nhóm ấy thay vì học vẹt từ bài 1 đến bài 13.

### `2_grid-system/2_child/` — thuộc tính đặt trên **item** (5 bài)

Mục này liệt kê 5 thuộc tính viết **trực tiếp lên item** — tức là mỗi phần tử con tự quyết định chỗ ngồi của mình. Đọc bảng để nắm bộ công cụ "quyền cá nhân" của item.

| Bài | Thuộc tính | Nội dung chính |
|-----|-----------|----------------|
| [1](./2_grid-system/2_child/1_row-column-start-end/) | `grid-column-start/end`, `grid-row-start/end` | Đặt item theo **đường lưới**: `1 / 3`, `span 2`, tên đường lưới |
| [2](./2_grid-system/2_child/2_grid-area/) | `grid-area` | Đặt tên item cho `grid-template-areas`, hoặc shorthand 4 đường lưới |
| [3](./2_grid-system/2_child/3_justify-self/) | `justify-self` | Căn một item theo trục inline trong ô của nó |
| [4](./2_grid-system/2_child/4_align-self/) | `align-self` | Căn một item theo trục block trong ô của nó |
| [5](./2_grid-system/2_child/5_place-self/) | `place-self` | Shorthand `align-self justify-self` |

> **Cách đọc bảng này:** bài 1–2 là "ghế ngồi" (đặt item vào đâu trên lưới), bài 3–5 là "tư thế ngồi" (căn trong ô như thế nào). Nếu chỉ nhớ một điều: 3 bài cuối cùng đều tôn trọng quy tắc **align = dọc, justify = ngang**.

### `2_grid-system/3_units-function/` — đơn vị & hàm đặc biệt

Đọc bài [3_units-function](./2_grid-system/3_units-function/) để nắm: `fr`, `min-content`/`max-content`/`auto`, `fit-content()`, `minmax()`, `min()`/`max()`, `repeat()` với `auto-fill`/`auto-fit`, và snippet nổi tiếng:

> 📄 **Code ví dụ:** [`examples/02-2-grid-system-3-units-function-on-vi.css`](examples/02-2-grid-system-3-units-function-on-vi.css)

---

## Ví dụ tổng hợp: layout dashboard 2 cột với Grid + Flexbox

> 📄 **Code ví dụ:** [`examples/03-vi-du-tong-hop-layout-dashboard-2-cot.css`](examples/03-vi-du-tong-hop-layout-dashboard-2-cot.css)

> 💡 **Quy tắc chọn:** cần kiểm soát cả **hàng lẫn cột** (trang, dashboard, gallery) → Grid. Cần phân bố nội dung **trên một trục** (navbar, danh sách nút, card) → Flexbox. Hai công cụ này bổ trợ nhau, không thay thế nhau — giống chăn và gối: không cái nào thay được cái nào, dùng cùng mới ấm.

> **Tóm gọn 1 câu:** Chọn công cụ theo chiều của bài toán — bài toán 1 chiều dùng Flexbox, bài toán 2 chiều dùng Grid, và layout thật thường dùng cả hai lồng nhau.

## Tài liệu tham khảo

- [MDN — Flexbox](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Flexbox) & [MDN — Grid](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Grids)
- [web.dev — Learn CSS Layout](https://web.dev/learn/css/layout)
- [CSS-Tricks Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
- Bổ trợ hiện đại: [Subgrid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Subgrid) và [container queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_containment/Container_queries) (đã Baseline — xem [8_modern-css](../8_modern-css/)).
