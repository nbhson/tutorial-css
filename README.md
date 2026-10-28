# CSS Tutorial — Khóa học CSS từ cơ bản đến hiện đại (tiếng Việt)

> Khóa học CSS hoàn toàn bằng tiếng Việt: từ cú pháp cơ bản, responsive, SCSS cho đến các tính năng hiện đại nhất của CSS 2026 (nesting, `:has()`, container queries...). Mỗi phần có lý thuyết, ví dụ code và bài thực hành.

---

## 🗺️ Bản đồ khóa học

Khóa học gồm **8 phần**, sắp xếp theo thứ tự tăng dần độ khó:

| # | Thư mục | Nội dung | Cấp độ |
|---|---------|----------|--------|
| 1 | [`1_css-tutorial/`](./1_css-tutorial/) | CSS cơ bản: cú pháp, box model (`margin`/`padding`/`border`), background, position, Flexbox, BEM + 4 bài thực hành (The Band, Luxstay, Shopee, cross-browser) | 🌱 Cơ bản |
| 2 | [`2_responsive-tutorial/`](./2_responsive-tutorial/) | Responsive hiện đại: `clamp()`, fluid type, logical properties, container queries, Grid system + thực hành Shopee responsive | 🌱→🌿 Cơ bản–Trung cấp |
| 3 | [`3_scss-tutorial/`](./3_scss-tutorial/) | SCSS/Sass: biến, at-rules, directives, mixin, kế thừa | 🌿 Trung cấp |
| 4 | [`4_mini-css/`](./4_mini-css/) | Mini project: sticky navigation bar khi scroll | 🌿 Trung cấp |
| 5 | [`5_layout/`](./5_layout/) | **Layout chuyên sâu**: Flexbox (8 thuộc tính) và CSS Grid (parent + child + units) — hệ thống bài học chi tiết nhất khóa học | 🌿→🌳 Trung cấp–Nâng cao |
| 6 | [`6_animation/`](./6_animation/) | CSS Animations: `@keyframes`, `animation-*`, project "Calm Breeze" | 🌳 Nâng cao |
| 7 | [`7_transition/`](./7_transition/) | CSS Transitions: `transition-property`, `duration`, `timing-function`, `delay` | 🌳 Nâng cao |
| 8 | [`8_modern-css/`](./8_modern-css/) | Modern CSS 2025–2026: nesting thuần, `:has()`, container queries, anchor positioning, `oklch()`, view transitions, `@layer`... | 🌳 Nâng cao |

## 📖 Thứ tự đọc khuyến nghị

**Nếu bạn mới học CSS:**

```
1_css-tutorial (1→9) → 5_layout/1_flexbox → 2_responsive-tutorial → 5_layout/2_grid-system
→ 3_scss-tutorial → 6_animation → 7_transition → 8_modern-css
```

**Nếu bạn đã biết CSS cơ bản, muốn nâng cấp lên level hiện đại:**

```
5_layout (ôn lại nền tảng) → 2_responsive-tutorial → 8_modern-css
```

**Nếu bạn chỉ cần tra cứu nhanh:**

- Tra thuộc tính Flexbox → `5_layout/1_flexbox/`
- Tra thuộc tính Grid → `5_layout/2_grid-system/`
- Tra tính năng mới (dùng được ngay trong production) → `8_modern-css/`

## 📚 Chi tiết từng phần

### 1. `1_css-tutorial/` — CSS cơ bản

Học theo thứ tự thư mục con:

| Bài | Nội dung |
|-----|----------|
| `1_lam-quen-voi-css` | CSS là gì, cách viết (`inline`, `internal`, `external`), selector cơ bản |
| `2_margin-padding-border` | Box model — nền tảng của mọi layout |
| `3_background` | `background-color` / `-image`, `background-size`, gradient |
| `4_position` | `static`, `relative`, `absolute`, `fixed`, `sticky` |
| `5-6_practice-the-band-template` | Thực hành template The Band (kèm bản responsive) |
| `7_flexbox` | Flexbox căn bản (sâu hơn ở phần 5) |
| `8_bem` | Đặt tên class theo chuẩn BEM |
| `9_practice-shoppe` | Thực hành clone giao diện Shopee |
| `10_practice-Luxstay` | Thực hành clone trang Luxstay |
| `11_cross-browser-code` | Viết CSS tương thích đa trình duyệt |

### 2. `2_responsive-tutorial/` — Responsive hiện đại

Không chỉ `@media`: `clamp()` cho font/padding "chảy", logical properties (`margin-inline`...), container queries, Grid system, rồi thực hành làm Shopee responsive. Xem [`2_responsive-tutorial/README.md`](./2_responsive-tutorial/README.md).

### 3. `3_scss-tutorial/` — SCSS

Cài đặt và syntax cơ bản → biến, toán tử, hàm → at-rules (`@if`, `@each`, `@for`...) → mixin, directives (`@extend`, `@include`, `@use`).

### 5. `5_layout/` — Layout chuyên sâu (Flexbox + Grid)

Đây là phần dày nhất khóa học — xem [`5_layout/README.md`](./5_layout/) (giáo trình tiếng Việt đầy đủ). Tóm tắt:

- `1_flexbox/` — 8 bài: `flex-direction`, `justify-content`, `align-content`, `align-items`, `align-self`, `gap`, `flex-grow/shrink/basis` + `flex-wrap`, `order`
- `2_grid-system/1_parent/` — 13 thuộc tính của grid container
- `2_grid-system/2_child/` — 5 thuộc tính của grid item
- `2_grid-system/3_units-function/` — `fr`, `minmax()`, `repeat()`, `auto-fit`...

### 8. `8_modern-css/` — Modern CSS

File dài nhất (400+ dòng): native nesting, `:has()`, container queries, anchor positioning, `oklch()`, view transitions, `@layer`, `@property`... kèm bảng hỗ trợ trình duyệt chi tiết.

## 🚦 CSS 2026: Trạng thái các tính năng quan trọng

Trạng thái theo [Baseline](https://web.dev/baseline) (web-features / MDN), kiểm tra tháng 10/2026. **"Baseline Widely available"** = dùng an toàn trong production mà không cần polyfill hay build step.

| Tính năng | Trạng thái Baseline | Ghi chú |
|-----------|--------------------|---------| 
| **CSS Nesting** (`&`) | ✅ Widely available (từ 2024) | Lồng selector thuần, thay thế phần lớn SCSS. Xem [`8_modern-css/`](./8_modern-css/) |
| **`:has()`** (parent selector) | ✅ Widely available (từ 12/2024) | Style phần tử cha/dựa trên con — không cần JS để kiểm tra DOM |
| **Container Queries** (`@container`) | ✅ Widely available (từ 09/2023) | Component tự responsive theo kích thước container, không phải viewport |
| **`oklch()` / `color-mix()`** | ✅ Widely available (từ 2023) | Màu hiện đại, gam rộng, trộn màu ngay trong CSS |
| **Anchor Positioning** | ⚠️ Limited availability | Định vị element bám vào anchor — chưa đạt Baseline, chưa dùng production rộng rãi |
| **Scroll-driven Animations** (`scroll()`, `view()`) | ⚠️ Limited availability | Chrome/Edge 115+, Safari mới có; Firefox chưa — luôn kèm `@supports` fallback |

> 💡 **Quy tắc thực dụng:** những gì ✅ Widely available hãy dùng thẳng, không build step; những gì ⚠️ Limited thì dùng với `@supports (anchor-name: --a) { ... }` và để fallback cho trình duyệt cũ. Trạng thái thay đổi nhanh — tra phiên bản mới nhất tại [web.dev/baseline](https://web.dev/baseline) hoặc MDN.

## 🛠️ Cách học trong repo này

- Mỗi bài là một thư mục với `README.md` (lý thuyết) + `index.html` / `styles/` (ví dụ chạy được). Mở file HTML trong trình duyệt để thấy trực quan.
- Phần [`5_layout/`](./5_layout/) có đầy đủ ví dụ SCSS (`style.scss`) kèm CSS đã compile — nếu chưa học SCSS, chỉ cần đọc file `.css`.
- Các phần 1, 2, 8 viết hoàn toàn bằng tiếng Việt; phần `5_layout/` gốc là tài liệu tiếng Anh (web.dev / CSS-Tricks), mỗi bài đã có **phần tóm tắt tiếng Việt ở đầu file**.

## 🔗 Tài liệu tham khảo chính

- [MDN CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) — tài liệu chuẩn nhất, có bảng browser support
- [web.dev — Learn CSS](https://web.dev/learn/css) — khóa học chính thức của Google
- [CSS-Tricks: A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) & [A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [State of CSS](https://stateofcss.com) — khảo sát xu hướng CSS hằng năm
- [Baseline (web.dev)](https://web.dev/baseline) — theo dõi tính năng nào dùng được production
