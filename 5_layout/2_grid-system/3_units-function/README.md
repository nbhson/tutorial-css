# Special Units & Functions

> **🇻🇳 Tóm tắt:** Bài tổng hợp đơn vị & hàm của Grid: `fr` (phần không gian còn lại), keywords `min-content`/`max-content`/`auto`, hàm `fit-content()`, `minmax()`, `min()`/`max()`, `repeat()` với `auto-fill`/`auto-fit` — trong đó snippet `repeat(auto-fit, minmax(250px, 1fr))` là "mẹo huyền thoại" tạo card responsive không cần media query. Gồm thêm phần Masonry (thử nghiệm) và Subgrid.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*


## fr units

You’ll likely end up using a lot of fractional units in CSS Grid, like 1fr. They essentially mean “portion of the remaining space”. So a declaration like:

> grid-template-columns: 1fr 3fr;


Means, loosely, 25% 75%. Except that those percentage values are much more firm than fractional units are. For example, if you added padding to those percentage-based columns, now you’ve broken 100% width (assuming a content-box box model). Fractional units also much more friendly in combination with other units, as you can imagine:

> grid-template-columns: 50px min-content 1fr;

## Sizing Keywords

When sizing rows and columns, you can use all the lengths you are used to, like px, rem, %, etc, but you also have keywords:

- min-content: the minimum size of the content. Imagine a line of text like “E pluribus unum”, the min-content is likely the width of the word “pluribus”.
- max-content: the maximum size of the content. Imagine the sentence above, the max-content is the length of the whole sentence.
- auto: this keyword is a lot like fr units, except that they “lose” the fight in sizing against fr units when allocating the remaining space.
Fractional units: see above

## Sizing Functions

- The fit-content() function uses the space available, but never less than min-content and never more than max-content.
- The minmax() function does exactly what it seems like: it sets a minimum and maximum value for what the length is able to be. This is useful for in combination with relative units. Like you may want a column to be only able to shrink so far. This is extremely useful and probably what you want:

> grid-template-columns: minmax(100px, 1fr) 3fr;

- The min() function.
- The max() function.

## The repeat() Function and Keywords

The repeat() function can save some typing:

```scss
grid-template-columns:
  1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr;

/* easier: */
grid-template-columns:
  repeat(8, 1fr);

/* especially when: */
grid-template-columns:
  repeat(8, minmax(10px, 1fr));
```

But repeat() can get extra fancy when combined with keywords:

- auto-fill: Fit as many possible columns as possible on a row, even if they are empty.
- auto-fit: Fit whatever columns there are into the space. Prefer expanding columns to fill space rather than empty columns.
This bears the most famous snippet in all of CSS Grid and one of the all-time great CSS tricks:

```scss
grid-template-columns: 
  repeat(auto-fit, minmax(250px, 1fr));
```

The difference between the keywords is spelled out in detail here.

## Masonry

An experimental feature of CSS grid is masonry layout. Note that there are lots of approaches to CSS masonry, but mostly of them are trickery and either have major downsides or aren’t what you quite expect.

The spec has an official way now, and this is behind a flag in Firefox:

```scss
.container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: masonry;
}
```
See Rachel’s article for a deep dive.

## Subgrid

Subgrid is an extremely useful feature of grids that allows grid items to have a grid of their own that inherits grid lines from the parent grid.

```scss
.parent-grid {
  display: grid;
  grid-template-columns: repeat(9, 1fr);
}
.grid-item {
  grid-column: 2 / 7;

  display: grid;
  grid-template-columns: subgrid;
}
.child-of-grid-item {
  /* gets to participate on parent grid! */
  grid-column: 3 / 6;
}
```

This is only supported in Firefox right now, but it really needs to get everywhere.

It’s also useful to know about display: contents;. This is not the same as subgrid, but it can be a useful tool sometimes in a similar fashion.

```html
<div class="grid-parent">

  <div class="grid-item"></div>
  <div class="grid-item"></div>

  <ul style="display: contents;">
    <!-- These grid-items get to participate on 
         the same grid!-->
    <li class="grid-item"></li>
    <li class="grid-item"></li>
  </ul>

</div>
```