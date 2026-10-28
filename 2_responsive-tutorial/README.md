# 2. Responsive Design Hiện Đại

> Không chỉ là `@media`. Responsive hiện đại dùng `clamp()`, fluid type, logical properties và container queries để xây layout tự thích ứng mà không cần breakpoint rời rạc.

## 1. `clamp()` — giá trị "chảy" giữa min và max

`clamp(min, preferred, max)` trả về giá trị nằm trong khoảng [min, max], dựa trên biểu thức preferred. Thường dùng cho font-size, padding, gap.

```css
/* Font chảy từ 16px (mobile) → 24px (desktop), không có breakpoint */
h1 {
  font-size: clamp(1rem, 2.5vw + 0.75rem, 1.5rem);
  /* min=16px, max=24px, preferred=2.5vw+12px
     viewport 320px → ~20px, viewport 1200px → 24px */
}

/* Padding tự điều chỉnh */
.card {
  padding: clamp(1rem, 4vw, 3rem);
  /* 320px→16px, 768px→31px, 1200px→48px */
}

/* Border-radius tự scale */
.btn {
  border-radius: clamp(4px, 1.5vw, 16px);
}
```

Xem thêm: [MDN – clamp()](https://developer.mozilla.org/en-US/docs/Web/CSS/clamp).

## 2. Fluid Typography — typography không cần breakpoint

Thay vì liệt kê font-size cho từng breakpoint, dùng `clamp()` với đơn vị `vw` để type "chảy" mượt giữa các kích thước:

```css
/* Tỷ lệ type: Major Third (1.25) */
:root {
  --text-xs:   clamp(0.64rem,  1.5vw + 0.4rem,  0.8rem);
  --text-sm:   clamp(0.8rem,   1.5vw + 0.5rem,  1rem);
  --text-base: clamp(1rem,     1.5vw + 0.6rem,  1.25rem);
  --text-lg:   clamp(1.25rem,  2vw + 0.7rem,     1.563rem);
  --text-xl:   clamp(1.563rem, 2.5vw + 0.8rem,   1.953rem);
  --text-2xl:  clamp(1.953rem, 3vw + 1rem,       2.441rem);
  --text-3xl:  clamp(2.441rem, 4vw + 1.2rem,      3.052rem);
}

body  { font-size: var(--text-base); line-height: 1.6; }
h1    { font-size: var(--text-3xl); line-height: 1.1; }
h2    { font-size: var(--text-2xl); line-height: 1.2; }
```

Công cụ hỗ trợ tính slope/intercept: <https://utopia.fity.club> giúp generate scale tùy ý.

## 3. CSS Container Queries — responsive theo container

`clamp()` + container queries là bộ đôi responsive hiện đại. Container queries trả lời câu hỏi: "component này có bao nhiêu chỗ?" thay vì "viewport rộng bao nhiêu?".

```css
/* Container báo kích thước cho con */
.card-wrapper {
  container-type: inline-size;
  container-name: wrapper;
}

/* Component phản ứng với không gian nó có, không phải viewport */
.card {
  padding: clamp(0.75rem, 3cqi, 2rem);
}

@container wrapper (min-width: 400px) {
  .card {
    display: grid;
    grid-template-columns: 140px 1fr;
  }
}

@container wrapper (max-width: 399px) {
  .card {
    display: flex;
    flex-direction: column;
  }
}
```

Xem thêm: [MDN – Container Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_containment).

## 4. Logical Properties — layout đa hướng (LTR/RTL, vertical writing)

Dùng `inline-start`/`inline-end`, `block-start`/`block-end` thay cho `left`/`right`, `top`/`bottom`. Code tự động đúng hướng với RTL (Arabic, Hebrew).

```css
/* Không dùng */
margin-left: 16px;
padding-right: 24px;
border-left: 2px solid red;

/* Dùng logical properties */
margin-inline-start: 16px;   /* trái→LTR, phải→RTL */
padding-inline-end: 24px;     /* phải→LTR, trái→RTL */
border-inline-start: 2px solid red;

/* gap thay vì margin rải */
.card-list {
  display: flex;
  flex-wrap: wrap;
  gap: clamp(0.5rem, 2vw, 1.5rem);  /* spacing tự chảy */
}

/* writing-mode dọc (cổng truyền thống) */
.cjk-card {
  writing-mode: vertical-rl;
  padding-block: clamp(1rem, 3vb, 3rem);  /* vb = vertical block */
  margin-inline: clamp(0.5rem, 1vi, 2rem); /* vi = vertical inline */
}
```

Xem thêm: [MDN – Logical properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_logical_properties_and_values).

## 5. `min()`, `max()`, `clamp()` trong layout

```css
/* Kẹp width trong khoảng, không cần breakpoint */
.card {
  width: clamp(280px, 100%, 600px);  /* full nhỏ, tối đa 600px */
  margin-inline: auto;               /* căn giữa */
}

/* Dùng min()/max() cho aspect-ratio hoặc grid */
.hero-image {
  /* Chiều cao tối thiểu 200px, tối đa 50vh, tự chảy theo width */
  height: min(50vh, max(200px, 30vw));
  aspect-ratio: 16 / 9;
  object-fit: cover;
}

/* Gap "chảy" giữa 8px và 32px */
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: clamp(0.5rem, 2vw, 2rem);
}
```

## 6. Responsive dựa trên container query units

```css
/* cqi = 1% inline size của nearest container */
.card-title {
  font-size: clamp(1rem, 4cqi, 2rem);
  /* Chữ tự phóng theo container chứa, không phải viewport */
}

.card-desc {
  /* clamp với container units */
  font-size: clamp(0.875rem, 1.5cqi, 1.125rem);
  line-height: clamp(1.4, 2cqi, 1.8);
}
```

## 7. Responsive images

```html
<!-- Ảnh responsive tự chọn src phù hợp với viewport -->
<img
  srcset="hero-480.webp 480w,
          hero-800.webp 800w,
          hero-1200.webp 1200w"
  sizes="(max-width: 480px) 100vw,
         (max-width: 900px) 80vw,
         1200px"
  src="hero-800.webp"
  alt="Hero image"
  loading="lazy"
  decoding="async"
/>

<!-- CSS cho ảnh tự co giãn theo container -->
.cover-img {
  width: 100%;
  height: auto;
  aspect-ratio: attr(width) / attr(height); /* fallback */
  object-fit: cover;
}
```

## 8. Responsive spacing strategy — hệ thống spacing dựa trên clamp

```css
/* Scale spacing từ mobile → desktop */
:root {
  --space-1: clamp(0.25rem, 1vw, 0.75rem);   /* 4→12px */
  --space-2: clamp(0.5rem,  1.5vw, 1rem);    /* 8→16px */
  --space-3: clamp(0.75rem, 2vw, 1.5rem);    /* 12→24px */
  --space-4: clamp(1rem,    2.5vw, 2rem);    /* 16→32px */
  --space-6: clamp(1.5rem,  3vw, 3rem);      /* 24→48px */
  --space-8: clamp(2rem,    4vw, 4rem);      /* 32→64px */
}

.section { padding: var(--space-6) 0; }
.card    { padding: var(--space-3); gap: var(--space-2); }
```

## 9. Responsive pattern: Grid → Stack → Card

```css
.card-wrapper {
  container-type: inline-size;
}

.card {
  display: flex;
  flex-direction: column;
  gap: var(--space-2);
  padding: var(--space-3);
}

/* ≥400px: grid 2 cột, ≥640px: grid 3 cột */
@container (min-width: 640px) {
  .card-list {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: clamp(1rem, 2vw, 1.5rem);
  }
}

@container (min-width: 400px) and (max-width: 639px) {
  .card-list {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: var(--space-2);
  }
}
```

## Tài liệu tham khảo

- MDN Responsive Design: <https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design>
- Utopia (fluid type generator): <https://utopia.fity.club>
- CSS Tricks – Complete Guide to CSS Logical Properties: <https://css-tricks.com/css-logical-properties>
- Container Queries MDN: <https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_containment>
