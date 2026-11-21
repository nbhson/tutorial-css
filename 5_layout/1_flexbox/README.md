# Flex

## 🇻🇳 Tóm tắt tiếng Việt

**Flexbox** là mô hình bố cục **một chiều**: sắp xếp các item dọc theo một trục (ngang hoặc dọc) — giống xếp sách trên một kệ duy nhất, chỉ chọn kệ ngang hay kệ đứng. Khóa con gồm 8 bài theo thứ tự khuyến nghị:

1. [`flex-direction`](./1_flex-direction/) — chọn trục chính (`row`/`column`)
2. [`justify-content`](./2_justify-content/) — căn theo trục chính (`center`, `space-between`...)
3. [`align-content`](./3_align-content/) — căn nhiều dòng (cần `flex-wrap`)
4. [`align-items`](./4_align-items/) — căn theo trục phụ (cách căn giữa dọc kinh điển)
5. [`align-self`](./5_align-self/) — căn riêng cho một item
6. [`gap`](./6_gap/) — khoảng cách giữa các item
7. [`grow-shrink-wrap-basis`](./7_grow-shrink-wrap-basis/) — `flex-grow`, `flex-shrink`, `flex-wrap`, `flex-basis`
8. [`order`](./8_order/) — đổi thứ tự hiển thị

Nhớ nhanh: `justify-*` tác động lên **main axis**, `align-*` lên **cross axis**; trục nào là main được quyết bởi `flex-direction`.

> **Tóm gọn 1 câu:** Flexbox là "một cái kệ, một chiều" — chọn trục bằng `flex-direction`, rồi `justify-*` xếp dọc theo trục đó và `align-*` lo trục còn lại.


## What's Flexbox

Mục này giải thích Flexbox là gì và tại sao nó là nền móng của mọi bố cục web hiện đại.

When you're building a house, you need a blueprint. In the same way, we need a blueprint when we're making websites. And Flexbox is the blueprint.

The Flexbox model allows us to layout the content of our website. Not only that, it helps us create the structures needed for creating responsive websites for multiple devices.

## Flexbox Architecture

Mục này nói về "bộ khung" của Flexbox: các item được phân bổ dọc theo main axis và cross axis, và trục nào giữ vai trò nào do `flex-direction` quyết định.

So how does Flexbox architecture work? The flex-items [Contents] are distributed along the main axis and cross axis. And, depending on the flex-direction property, the layout position changes between rows and columns.

![Architecture](./architect.png)

## Flexbox Chart

Mục này là "bảng tra nhanh" — nơi gom đủ mọi property và value của Flexbox để bạn quay lại tham khảo khi làm project.

This chart contains every possible property and value you can use when you're working with Flexbox. You can reference it while doing your projects and experiment with different values.

![Chart](./chart.png)

## Shorthand Flexbox Properties

Mục này gom các cách viết gộp (shorthand) — giống viết tắt một câu dài thành một cụm duy nhất, giúp CSS gọn và dễ đọc hơn.

### flex shorthand

![alt text](https://dev-to-uploads.s3.amazonaws.com/i/onoxj7gs9xj4wuf87kjl.png)

> 📄 **Code ví dụ:** [`examples/01-flex-shorthand.scss`](examples/01-flex-shorthand.scss)

### flex-flow shorthand

![alt text](https://dev-to-uploads.s3.amazonaws.com/i/awniqyrepbha5jdquwxh.png)

> 📄 **Code ví dụ:** [`examples/02-flex-flow-shorthand.scss`](examples/02-flex-flow-shorthand.scss)

### place-content shorthand

![alt text](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/72yaytxgighz0cjskp2e.png)

```scss
.container {
    place-content : center flex-end;
}
```

> **Tóm gọn 1 câu:** Flexbox là "bản vẽ nhà" của trang web — nắm được main/cross axis và các shorthand là bạn dựng được hầu hết bố cục một chiều.

<https://www.freecodecamp.org/news/css-flexbox-tutorial-with-cheatsheet/>

<https://css-tricks.com/snippets/css/a-guide-to-flexbox/>