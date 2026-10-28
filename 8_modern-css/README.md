# 8. Modern CSS (2025 – 2026)

> Tổng hợp các tính năng CSS hiện đại nhất đang dùng được trong production. Nội dung tổng hợp từ **State of CSS 2025/2026**, **CSS Wrapped 2025** (Chrome for Developers) và spec chính thức của W3C.

Từ năm 2023 đến 2026, CSS có những bước nhảy vọt lớn nhất trong một thập kỷ. Nhiều việc trước đây **bắt buộc phải dùng JavaScript** (định vị tooltip, style con dựa trên trạng thái cha, animation theo scroll...) giờ đã được giải quyết hoàn toàn bằng CSS thuần.

## Tổng quan Browser Support (tháng 10/2026)

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

Tài liệu tham khảo chính thức:

- MDN CSS: <https://developer.mozilla.org/en-US/docs/Web/CSS>
- State of CSS: <https://2025.stateofcss.com> và <https://2026.stateofcss.com>
- CSS Wrapped 2025: <https://chrome.dev/css-wrapped-2025/>

---

## 1. Native CSS Nesting (Lồng nhau trong CSS thuần)

Từ Chrome 112, Safari 16.5, Firefox 117, bạn có thể viết CSS lồng nhau **không cần Sass/SCSS**. Xem thêm: [MDN – CSS Nesting](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_nesting).

```css
/* Trước đây chỉ SCSS làm được, giờ là CSS thuần */
.card {
  padding: 1rem;
  background: white;

  /* & đại diện cho selector cha, giống SCSS */
  &:hover {
    box-shadow: 0 4px 12px rgb(0 0 0 / 15%);
  }

  & .title {
    font-size: 1.25rem;
  }

  /* @media lồng bên trong cũng được */
  @media (width >= 768px) {
    display: grid;
    grid-template-columns: 200px 1fr;
  }
}
```

**Lưu ý:** khác với SCSS, CSS native yêu cầu selector lồng nhau phải tham chiếu đến cha (dùng `&` hoặc bắt đầu bằng phần tử/combinator). Quy tắc an toàn: luôn viết `&` ở đầu selector lồng nhau.

```css
/* KHÔNG nên — ngầm hiểu là :is(.card) div */
div & { ... }

/* NÊN viết tường minh */
& div { ... }
```

---

## 2. Container Queries (`@container`) — component tự responsive

Media queries chỉ biết kích thước **viewport**. Container Queries cho phép một component **phản ứng theo kích thước container chứa nó** — cùng một component hoạt động đúng ở sidebar hẹp lẫn main content rộng.

```css
/* 1. Khai báo container */
.card-wrapper {
  container-type: inline-size;
  container-name: card;
}

/* 2. Component bên trong phản ứng theo container, không phải viewport */
@container card (min-width: 400px) {
  .card {
    display: grid;
    grid-template-columns: 200px 1fr;
  }
}

@container card (max-width: 399px) {
  .card {
    display: flex;
    flex-direction: column;
  }
}
```

Container query units — đơn vị tính theo container:

- `cqw` – 1% chiều rộng container, `cqi` – 1% inline size, `cqh` – chiều cao.
- Ví dụ: `font-size: clamp(1rem, 4cqi, 2rem);` — chữ phóng theo container chứ không theo viewport.

Style queries (query theo giá trị CSS, ví dụ `@container style(--theme: dark)`) hiện chỉ Chrome hỗ trợ — dùng có chọn lọc. Xem: [MDN – Container Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_containment).

---

## 3. `:has()` — "Parent Selector" mà cộng đồng chờ 20 năm

`:has()` cho phép chọn phần tử cha **dựa trên con**, hoặc chọn phần tử trước đó — thứ trước đây bất khả thi trong CSS.

```css
/* Card có ảnh → đổi layout */
.card:has(img) {
  grid-template-columns: 120px 1fr;
}

/* Form field đang có lỗi → tô đỏ cả hàng */
.form-row:has(input:user-invalid) {
  --color-danger: oklch(55% 0.2 25);
  border-color: var(--color-danger);
}

/* Label đi trước input focus */
label:has(+ input:focus) {
  color: oklch(55% 0.15 250);
}

/* Modal đang mở → khóa scroll của body */
body:has(dialog[open]) {
  overflow: hidden;
}
```

Ứng dụng kinh điển: grid thiếu phần tử cuối vẫn tự cán đều:

```css
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
}
/* Khi ở hàng cuối thiếu 1 item, kéo dài item áp chót */
.grid:has(.item:nth-last-child(2):nth-child(odd)) .item:last-child {
  grid-column: span 2;
}
```

Xem thêm: [MDN – :has()](https://developer.mozilla.org/en-US/docs/Web/CSS/:has).

---

## 4. Anchor Positioning — Tooltip/Popover không cần JavaScript

Với Anchor Positioning (spec Level 1: <https://www.w3.org/TR/css-anchor-position-1/>), bạn "neo" một phần tử vào phần tử khác và để trình duyệt tự xử lý va chạm cạnh màn hình.

```html
<button class="btn-trigger" popovertarget="tip">Hover me</button>
<div id="tip" class="tooltip" popover>Tooltip tự định vị, không cần JS.</div>
```

```css
/* Phần tử được neo */
.btn-trigger {
  anchor-name: --my-button;
}

/* Phần tử được định vị theo anchor */
.tooltip {
  position: absolute;
  position-anchor: --my-button;
  position-area: bottom;          /* đặt dưới anchor, căn giữa */
  position-try-fallbacks: flip-block, flip-inline; /* tự lật nếu chạm mép */
}
```

Từ **Chrome 143 (10/2025)** có thêm **anchored container queries** (Anchor Positioning Level 2): dùng `container-type: anchored` + `@container anchored(fallback: flip-block)` để biết tooltip đã bị lật sang vị trí dự phòng hay chưa — từ đó tự đổi chiều mũi tên mà không cần JS:

```css
.tooltip {
  container-type: anchored;

  &::before {
    content: '▲';        /* mũi tên hướng lên mặc định */
    position: absolute;
    bottom: 100%;
  }
}

@container anchored(fallback: flip-block) {
  .tooltip::before {
    content: '▼';        /* tooltip bị lật lên trên → đổi mũi tên */
    bottom: auto;
    top: 100%;
  }
}
```

Kết hợp với **Popover API** (`popover` + `popovertarget`) là bộ đôi thay thế hoàn toàn thư viện tooltip/popover. Xem: [Chrome for Developers – Anchored container queries](https://developer.chrome.com/blog/anchored-container-queries).

---

## 5. CSS Color Level 4 — `oklch()` và `color-mix()`

Không gian màu `oklch()` (Lightness, Chroma, Hue) cho màu **đồng nhất về độ sáng cảm nhận**, dễ xây dựng design system hơn `hex`/`hsl`:

```css
:root {
  --brand: oklch(60% 0.15 250);   /* L: độ sáng 0-100%, C: độ rực, H: góc màu */
  --brand-dark: oklch(45% 0.15 250);   /* cùng tông, chỉ giảm sáng */
  --surface: oklch(98% 0.01 250);
}

/* color-mix(): pha trộn màu ngay trong CSS */
.button {
  background: color-mix(in oklch, var(--brand) 100%, white);
}
.button:hover {
  /* tự sinh màu hover = pha 20% đen — không cần khai thêm biến */
  background: color-mix(in oklch, var(--brand), black 20%);
}

/* Tự động tương phản theo theme sáng/tối */
.card {
  background: var(--brand);
  color: color-mix(in oklch, white calc(100% - var(--contrast)), black calc(var(--contrast)));
}
```

Xem thêm: [MDN – oklch()](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/oklch), [MDN – color-mix()](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/color-mix).

---

## 6. Subgrid — Lưới con thẳng hàng với lưới cha

Subgrid cho phép phần tử con dùng lại **track của lưới cha**, giải quyết bài toán kinh điển: các card có chiều cao tiêu đề/khác nhau vẫn thẳng hàng theo hàng.

```css
.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
}

.card {
  display: grid;
  grid-row: span 3;
  /* Thừa hưởng đúng 3 hàng của lưới cha: title, body, footer */
  grid-template-rows: subgrid;
}

.card h3   { grid-row: 1; }
.card p    { grid-row: 2; }
.card button { grid-row: 3; }
```

Xem thêm: [MDN – Subgrid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Subgrid).

---

## 7. View Transitions API — Chuyển cảnh mượt mà chỉ bằng CSS

Same-document View Transitions (Chrome 111+, Safari 18+, Firefox 126+) cho phép animate khi DOM thay đổi:

```javascript
// JavaScript: chỉ cần 1 dòng bao quanh thay đổi DOM
document.startViewTransition(() => {
  swapView();
});
```

```css
/* CSS: đặt tên cho phần tử chuyển động */
.hero-image {
  view-transition-name: hero;
}

/* CSS tự animate từ vị trí cũ sang vị trí mới */
::view-transition-old(hero) { animation: 300ms ease both fade-out; }
::view-transition-new(hero) { animation: 300ms ease both fade-in; }
```

Xem thêm: [MDN – View Transition API](https://developer.mozilla.org/en-US/docs/Web/API/View_Transitions_API).

---

## 8. `@property` — Biến CSS có kiểu dữ liệu và có thể transition

`@property` (CSS Houdini) khai báo custom property với **type, giá trị mặc định, kế thừa** — mở khóa animate được các thuộc tính trước đây không animate nổi (gradient, số lượng...):

```css
@property --angle {
  syntax: '<angle>';
  initial-value: 0deg;
  inherits: false;
}

.gradient-border {
  background: linear-gradient(var(--angle), oklch(70% 0.15 250), oklch(70% 0.15 120));
  animation: spin 3s linear infinite;
}

@keyframes spin {
  to { --angle: 360deg; }   /* không có @property thì dòng này không chạy được */
}
```

Xem thêm: [MDN – @property](https://developer.mozilla.org/en-US/docs/Web/CSS/@property).

---

## 9. `@layer` — Kiểm soát độ ưu tiên (Cascade Layers)

Thay vì phải dùng `!important` để đấu với thư viện bên thứ 3, chia CSS thành các layer với độ ưu tiên **khai báo sẵn**:

```css
/* Thứ tự khai báo quyết định độ ưu tiên: layer sau > layer trước */
@layer reset, base, components, utilities;

@layer reset {
  * { margin: 0; box-sizing: border-box; }
}

@layer base {
  a { color: oklch(55% 0.15 250); }
}

@layer components {
  /* Ghi đè được style của framework mà không cần !important */
  .btn { border-radius: 999px; }
}

/* CSS bên ngoài mọi layer luôn mạnh hơn CSS trong layer */
```

Xem thêm: [MDN – @layer](https://developer.mozilla.org/en-US/docs/Web/CSS/@layer).

---

## 10. Scroll-driven Animations — Animation theo scroll, không cần JS

Thay vì lắng nghe `scroll` event bằng JavaScript, để CSS trực tiếp gắn tiến trình animation với tiến trình scroll:

```css
/* Thanh tiến trình đọc bài viết */
.progress-bar {
  position: fixed;
  inset-inline-start: 0;
  width: 100%;
  height: 4px;
  background: var(--brand);
  transform-origin: 0 50%;

  animation: grow-progress linear;
  animation-timeline: scroll(root);   /* gắn với thanh scroll của root */
}

@keyframes grow-progress {
  from { transform: scaleX(0); }
  to   { transform: scaleX(1); }
}

/* Hiệu ứng reveal khi phần tử đi vào viewport */
.reveal {
  animation: fade-up linear both;
  animation-timeline: view();          /* theo vị trí phần tử trong viewport */
  animation-range: entry 0% cover 40%; /* chạy từ lúc bắt đầu lóe ra đến 40% */
}

@keyframes fade-up {
  from { opacity: 0; translate: 0 40px; }
  to   { opacity: 1; translate: 0 0; }
}
```

Lưu ý: tính đến 2026, Firefox chưa hỗ trợ ổn định — nên dùng làm **progressive enhancement** (trang vẫn hoạt động bình thường khi thiếu). Xem: [MDN – Scroll-driven animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll-driven_animations).

---

## 11. Feature tổng hợp: một component hiện đại

```css
.card-wrapper {
  container-type: inline-size;
}

@layer components {
  .card {
    display: grid;
    gap: 0.75rem;
    padding: clamp(1rem, 3cqi, 2rem);
    border-radius: 12px;
    background: color-mix(in oklch, white 92%, var(--brand));

    &:hover { box-shadow: 0 8px 24px oklch(0% 0 0 / 12%); }

    &:has(img) {
      grid-template-columns: subgrid;
      grid-template-rows: auto 1fr;
    }

    @container (min-width: 480px) {
      grid-template-columns: 180px 1fr;
    }
  }
}
```

## Kết luận

Chiến lược tiếp cận CSS hiện đại 2026:

1. **Progressive enhancement**: mọi tính năng trên đều "graceful degrade" — trình duyệt cũ chỉ thiếu hiệu ứng, không vỡ layout.
2. Ưu tiên giải quyết bằng CSS trước khi viết JS (tooltip, reveal on scroll, theme...).
3. Theo dõi support tại <https://caniuse.com> và <https://web-platform-dx.github.io/web-features/>.
