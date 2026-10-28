# Flex

## 🇻🇳 Tóm tắt tiếng Việt

**Flexbox** là mô hình bố cục **một chiều**: sắp xếp các item dọc theo một trục (ngang hoặc dọc). Khóa con gồm 8 bài theo thứ tự khuyến nghị:

1. [`flex-direction`](./1_flex-direction/) — chọn trục chính (`row`/`column`)
2. [`justify-content`](./2_justify-content/) — căn theo trục chính (`center`, `space-between`...)
3. [`align-content`](./3_align-content/) — căn nhiều dòng (cần `flex-wrap`)
4. [`align-items`](./4_align-items/) — căn theo trục phụ (cách căn giữa dọc kinh điển)
5. [`align-self`](./5_align-self/) — căn riêng cho một item
6. [`gap`](./6_gap/) — khoảng cách giữa các item
7. [`grow-shrink-wrap-basis`](./7_grow-shrink-wrap-basis/) — `flex-grow`, `flex-shrink`, `flex-wrap`, `flex-basis`
8. [`order`](./8_order/) — đổi thứ tự hiển thị

Nhớ nhanh: `justify-*` tác động lên **main axis**, `align-*` lên **cross axis**; trục nào là main được quyết bởi `flex-direction`.


## What's Flexbox

When you're building a house, you need a blueprint. In the same way, we need a blueprint when we're making websites. And Flexbox is the blueprint.

The Flexbox model allows us to layout the content of our website. Not only that, it helps us create the structures needed for creating responsive websites for multiple devices.

## Flexbox Architecture

So how does Flexbox architecture work? The flex-items [Contents] are distributed along the main axis and cross axis. And, depending on the flex-direction property, the layout position changes between rows and columns.

![Architecture](./architect.png)

## Flexbox Chart

This chart contains every possible property and value you can use when you're working with Flexbox. You can reference it while doing your projects and experiment with different values.

![Chart](./chart.png)

## Shorthand Flexbox Properties

### flex shorthand

![alt text](https://dev-to-uploads.s3.amazonaws.com/i/onoxj7gs9xj4wuf87kjl.png)

```scss
.box-2{
    flex : 2 1 30em;
}
```

### flex-flow shorthand

![alt text](https://dev-to-uploads.s3.amazonaws.com/i/awniqyrepbha5jdquwxh.png)

```scss
.container{
    flex-flow : row wrap;
}
```

### place-content shorthand

![alt text](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/72yaytxgighz0cjskp2e.png)

```scss
.container {
    place-content : center flex-end;
}

<https://www.freecodecamp.org/news/css-flexbox-tutorial-with-cheatsheet/>

<https://css-tricks.com/snippets/css/a-guide-to-flexbox/>