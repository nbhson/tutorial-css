# Grid

## 🇻🇳 Giới thiệu chương Grid

Mục này là "bản đồ" của chương Grid: gồm những phần nào, nên học theo thứ tự nào. Đọc để đỡ lạc đường trước khi đi vào từng bài.

Chương này chia làm 3 phần — học theo thứ tự:

- [`1_parent/`](./1_parent/) — 13 thuộc tính đặt trên **grid container** (template, gap, căn chỉnh, auto-flow...)
- [`2_child/`](./2_child/) — 5 thuộc tính đặt trên **grid item** (đặt vị trí theo đường lưới, `grid-area`, self-alignment)
- [`3_units-function/`](./3_units-function/) — đơn vị `fr`, `minmax()`, `repeat()`, `auto-fit`...

Nhớ nhanh: **align = trục block (dọc), justify = trục inline (ngang)**; hậu tố `-items` căn nội dung item trong ô, `-content` căn cả lưới trong container, `-self` căn một item duy nhất.

> **Tóm gọn 1 câu:** Chương Grid là 3 lớp học xếp tầng — container định hình, item chọn chỗ, đơn vị/hàm đo đạc — học đúng thứ tự thì các bài sau dễ thở hẳn.


Bố cục lưới CSS (còn gọi là “Lưới” hoặc “Lưới CSS”), là một hệ thống bố cục dựa trên lưới hai chiều, so với bất kỳ hệ thống bố cục web nào trước đây, thay đổi hoàn toàn cách chúng ta thiết kế giao diện người dùng.

**CSS luôn được sử dụng để bố cục các trang web của chúng ta, nhưng nó chưa bao giờ làm tốt công việc đó.**

Đầu tiên, chúng tôi sử dụng bảng, sau đó là float, định vị và khối nội tuyến, nhưng tất cả các phương pháp này về cơ bản đều là hack và bỏ sót nhiều chức năng quan trọng (ví dụ: căn giữa theo chiều dọc).

*Flexbox cũng là một công cụ bố cục rất tuyệt vời, nhưng luồng một chiều của nó có các trường hợp sử dụng khác nhau — và chúng thực sự phối hợp với nhau khá tốt!*

> Grid là mô-đun CSS đầu tiên được tạo riêng để giải quyết các vấn đề về bố cục mà tất cả chúng ta đã gặp phải trong suốt quá trình tạo trang web.

## Important CSS Grid terminology

Mục này nói về **ngôn ngữ chung** của Grid: container, line, track, area, item, cell. Đọc để về sau đọc tài liệu hay thuộc tính nào cũng biết đang nhắc đến bộ phận nào của lưới — giống như phải biết tên từng bộ phận xe đạp trước khi sửa xe.

### Grid Container

Phần tử mà hiển thị: lưới được áp dụng. Nó là cha mẹ trực tiếp của tất cả các mục lưới. In this example container is the grid container. Ví von: container là "mảnh đất" — bạn khai `display: grid` lên nó thì mọi thứ bên trong bỗng ngồi vào ô kẻ sẵn.

> 📄 **Code ví dụ:** [`examples/01-grid-container.html`](examples/01-grid-container.html)

### Grid Line

Các đường phân chia tạo nên cấu trúc của lưới. Chúng có thể theo chiều dọc (“đường lưới cột”) hoặc nằm ngang (“đường lưới hàng”) và nằm ở hai bên của hàng hoặc cột. Ở đây, đường màu vàng là một ví dụ về đường lưới cột. Hãy hình dung chúng như các đường kẻ ô ly trên vở: lưới không đếm bằng px mà đếm bằng những đường kẻ này.

![alt text](https://css-tricks.com/wp-content/uploads/2018/11/terms-grid-line.svg)

### Grid Track

Khoảng cách giữa hai đường lưới liền kề. Bạn có thể coi chúng như các cột hoặc hàng của lưới. Đây là đường lưới giữa các đường lưới hàng thứ hai và thứ ba. Ví von: nếu grid line là đường kẻ thì track là **dải** nằm giữa hai đường kẻ — tức là đúng cái "rãnh" mà nội dung chiếm chỗ.

![alt text](https://css-tricks.com/wp-content/uploads/2021/08/terms-grid-track.svg)

### Grid Area

Tổng không gian được bao quanh bởi bốn đường lưới. Một vùng lưới có thể bao gồm bất kỳ số lượng ô lưới nào. Đây là vùng lưới giữa các đường lưới hàng 1 và 3 cũng như các đường lưới cột 1 và 3. Ví von: area là "lô đất gộp" — bạn có thể mua nguyên một vùng gồm nhiều ô liền kề để đặt một item lớn.

![alt text](https://css-tricks.com/wp-content/uploads/2018/11/terms-grid-area.svg)

### Grid Item

Các phần tử con (tức là hậu duệ trực tiếp) của vùng chứa lưới. Ở đây, các thành phần mục là các mục dạng lưới, còn mục phụ không phải như vậy. Ví von: chỉ con **trực tiếp** mới được ngồi vào bàn ăn — cháu nội phải được "đưa tay" (bọc lại hoặc `display: contents`) mới tính là item.

> 📄 **Code ví dụ:** [`examples/02-grid-item.html`](examples/02-grid-item.html)

### Grid Cell

Khoảng cách giữa hai hàng liền kề và hai đường lưới cột liền kề. Đó là một “đơn vị” duy nhất của lưới điện. Đây là ô lưới giữa các đường lưới hàng 1 và 2 và các đường lưới cột 2 và 3. Ví von: cell là một "ô vuông đơn" trên giấy ô ly — đơn vị nhỏ nhất mà một item có thể ngồi vào.

![alt text](https://css-tricks.com/wp-content/uploads/2018/11/terms-grid-cell.svg)

> **Tóm gọn 1 câu:** Sáu thuật ngữ xếp theo vòng tròn: container là mảnh đất, line là đường kẻ, track là dải giữa hai đường, cell là một ô vuông, area là vùng gộp nhiều ô, item là người ngồi vào ô.

<https://css-tricks.com/snippets/css/complete-guide-grid/#aa-introduction>