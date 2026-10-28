# Grid

## 🇻🇳 Giới thiệu chương Grid

Chương này chia làm 3 phần — học theo thứ tự:

- [`1_parent/`](./1_parent/) — 13 thuộc tính đặt trên **grid container** (template, gap, căn chỉnh, auto-flow...)
- [`2_child/`](./2_child/) — 5 thuộc tính đặt trên **grid item** (đặt vị trí theo đường lưới, `grid-area`, self-alignment)
- [`3_units-function/`](./3_units-function/) — đơn vị `fr`, `minmax()`, `repeat()`, `auto-fit`...

Nhớ nhanh: **align = trục block (dọc), justify = trục inline (ngang)**; hậu tố `-items` căn nội dung item trong ô, `-content` căn cả lưới trong container, `-self` căn một item duy nhất.


Bố cục lưới CSS (còn gọi là “Lưới” hoặc “Lưới CSS”), là một hệ thống bố cục dựa trên lưới hai chiều, so với bất kỳ hệ thống bố cục web nào trước đây, thay đổi hoàn toàn cách chúng ta thiết kế giao diện người dùng.

**CSS luôn được sử dụng để bố cục các trang web của chúng ta, nhưng nó chưa bao giờ làm tốt công việc đó.**

Đầu tiên, chúng tôi sử dụng bảng, sau đó là float, định vị và khối nội tuyến, nhưng tất cả các phương pháp này về cơ bản đều là hack và bỏ sót nhiều chức năng quan trọng (ví dụ: căn giữa theo chiều dọc).

*Flexbox cũng là một công cụ bố cục rất tuyệt vời, nhưng luồng một chiều của nó có các trường hợp sử dụng khác nhau — và chúng thực sự phối hợp với nhau khá tốt!*

> Grid là mô-đun CSS đầu tiên được tạo riêng để giải quyết các vấn đề về bố cục mà tất cả chúng ta đã gặp phải trong suốt quá trình tạo trang web.

## Important CSS Grid terminology

### Grid Container

Phần tử mà hiển thị: lưới được áp dụng. Nó là cha mẹ trực tiếp của tất cả các mục lưới. In this example container is the grid container.

```html
<div class="container">
  <div class="item item-1"> </div>
  <div class="item item-2"> </div>
  <div class="item item-3"> </div>
</div>
```

### Grid Line

Các đường phân chia tạo nên cấu trúc của lưới. Chúng có thể theo chiều dọc (“đường lưới cột”) hoặc nằm ngang (“đường lưới hàng”) và nằm ở hai bên của hàng hoặc cột. Ở đây, đường màu vàng là một ví dụ về đường lưới cột.

![alt text](https://css-tricks.com/wp-content/uploads/2018/11/terms-grid-line.svg)

### Grid Track

Khoảng cách giữa hai đường lưới liền kề. Bạn có thể coi chúng như các cột hoặc hàng của lưới. Đây là đường lưới giữa các đường lưới hàng thứ hai và thứ ba.

![alt text](https://css-tricks.com/wp-content/uploads/2021/08/terms-grid-track.svg)

### Grid Area

Tổng không gian được bao quanh bởi bốn đường lưới. Một vùng lưới có thể bao gồm bất kỳ số lượng ô lưới nào. Đây là vùng lưới giữa các đường lưới hàng 1 và 3 cũng như các đường lưới cột 1 và 3.

![alt text](https://css-tricks.com/wp-content/uploads/2018/11/terms-grid-area.svg)

### Grid Item

Các phần tử con (tức là hậu duệ trực tiếp) của vùng chứa lưới. Ở đây, các thành phần mục là các mục dạng lưới, còn mục phụ không phải như vậy.

```html
<div class="container">
  <div class="item"> </div>
  <div class="item">
    <p class="sub-item"> </p>
  </div>
  <div class="item"> </div>
</div>
```

### Grid Cell

Khoảng cách giữa hai hàng liền kề và hai đường lưới cột liền kề. Đó là một “đơn vị” duy nhất của lưới điện. Đây là ô lưới giữa các đường lưới hàng 1 và 2 và các đường lưới cột 2 và 3

![alt text](https://css-tricks.com/wp-content/uploads/2018/11/terms-grid-cell.svg)

<https://css-tricks.com/snippets/css/complete-guide-grid/#aa-introduction>