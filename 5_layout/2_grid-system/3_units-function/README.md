# Special Units & Functions

> **🇻🇳 Tóm tắt:** Bài tổng hợp đơn vị & hàm của Grid: `fr` (phần không gian còn lại), keywords `min-content`/`max-content`/`auto`, hàm `fit-content()`, `minmax()`, `min()`/`max()`, `repeat()` với `auto-fill`/`auto-fit` — trong đó snippet `repeat(auto-fit, minmax(250px, 1fr))` là "mẹo huyền thoại" tạo card responsive không cần media query. Gồm thêm phần Masonry (thử nghiệm) và Subgrid.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*

Mục này nói về "ngôn ngữ đo đạc" riêng của Grid: thay vì chỉ dùng px và %, Grid cho bạn đơn vị `fr`, các keyword tự đo theo nội dung, và những hàm tính size thông minh. Đọc để hiểu từng loại nên dùng lúc nào — đây là nền để viết được những lưới "tự thông minh" thay vì cắt px cứng.

## fr units

Mục này nói về `fr` — đơn vị phổ biến nhất của Grid, dùng để chia không gian còn lại theo tỷ lệ.

You’ll likely end up using a lot of fractional units in CSS Grid, like 1fr. They essentially mean “portion of the remaining space”. So a declaration like:

> grid-template-columns: 1fr 3fr;

Hãy hình dung việc chia bánh: `1fr 3fr` nghĩa là chia chiếc bánh không gian còn lại thành 4 phần, cột đầu lấy 1 phần, cột sau lấy 3 phần — tức khoảng 25% / 75%. Nhưng khác với % ở chỗ: `fr` là phần **còn lại** sau khi trừ các phần khác, và nó "mềm" hơn nhiều.

Means, loosely, 25% 75%. Except that those percentage values are much more firm than fractional units are. For example, if you added padding to those percentage-based columns, now you’ve broken 100% width (assuming a content-box box model). Fractional units also much more friendly in combination with other units, as you can imagine:

> grid-template-columns: 50px min-content 1fr;

> **Tóm gọn 1 câu:** `fr` là "chia bánh phần còn lại" theo tỷ lệ — mềm dẻo, không sợ vỡ 100% như %, và sống hòa thuận với px, min-content cùng các đơn vị khác.

## Sizing Keywords

Mục này nói về ba từ khóa tự đo size theo **nội dung** của ô: nội dung cần rộng bao nhiêu thì ô rộng bấy nhiêu. Đọc để biết khi nào muốn cột "ôm" nội dung thay vì nhận kích thước cứng.

When sizing rows and columns, you can use all the lengths you are used to, like px, rem, %, etc, but you also have keywords:

- min-content: the minimum size of the content. Imagine a line of text like “E pluribus unum”, the min-content is likely the width of the word “pluribus”.
- max-content: the maximum size of the content. Imagine the sentence above, the max-content is the length of the whole sentence.
- auto: this keyword is a lot like fr units, except that they “lose” the fight in sizing against fr units when allocating the remaining space.
Fractional units: see above

Ví von cho bộ ba này: nghĩ về một đoạn văn trong ô — `min-content` là kích thước khi bạn xuống dòng hết mức (chỉ còn từ dài nhất, giống cái áo khoác phẳng nhất có thể), `max-content` là khi bạn gộp hết vào một dòng không ngắt (đoạn văn phồng ra toàn bộ chiều dài). `auto` thì như người "nhường nhịn": cũng muốn chia không gian như `fr`, nhưng khi hai bên giành nhau phần còn lại, `auto` luôn nhường `fr`.

> **Tóm gọn 1 câu:** `min-content` là ô "co nhỏ nhất chịu được", `max-content` là "giãn hết một dòng", `auto` là bản fr "hiền lành" — giành không gian thua `fr`.

## Sizing Functions

Mục này nói về các **hàm** đặt giới hạn thông minh cho kích thước: vừa co vừa giãn nhưng không vượt qua "sàn" và "trần". Đây là phần thực dụng nhất của bài — hầu hết lưới thực tế đều dùng `minmax()`.

- The fit-content() function uses the space available, but never less than min-content and never more than max-content.
- The minmax() function does exactly what it seems like: it sets a minimum and maximum value for what the length is able to be. This is useful for in combination with relative units. Like you may want a column to be only able to shrink so far. This is extremely useful and probably what you want:

> grid-template-columns: minmax(100px, 1fr) 3fr;

- The min() function.
- The max() function.

Ví von: `minmax(min, max)` như một chiếc áo co giãn có đường may — co được nhưng không dưới "sàn" 100px, giãn được nhưng không vượt "trần". `fit-content()` thì tự động lấy đúng "sàn" và "trần" là chính nội dung của ô, bạn khỏi phải khai báo. Còn `min()`/`max()` là hai phép so từng cặp: chọn số nhỏ hơn hoặc lớn hơn trong các ứng viên.

> **Tóm gọn 1 câu:** Các hàm sizing là "đường may co giãn" của lưới — `minmax()` định sàn-trần, `fit-content()` tự lấy theo nội dung, `min()`/`max()` chọn giữa các giá trị.

## The repeat() Function and Keywords

Mục này nói về cách khỏi phải gõ tay 10 lần `1fr 1fr 1fr...` — `repeat()` viết hộ bạn, và khi ghép với `auto-fill`/`auto-fit`, lưới còn tự biết mình cần bao nhiêu cột. Đọc để nắm snippet nổi tiếng nhất của CSS Grid nằm cuối mục.

The repeat() function can save some typing:

> 📄 **Code ví dụ:** [`examples/01-the-repeat-function-and-keywords.scss`](examples/01-the-repeat-function-and-keywords.scss)

But repeat() can get extra fancy when combined with keywords:

- auto-fill: Fit as many possible columns as possible on a row, even if they are empty.
- auto-fit: Fit whatever columns there are into the space. Prefer expanding columns to fill space rather than empty columns.

Ví von: `auto-fill` là xe buýt chạy đúng lịch — cứ chật chỗ là xuất thêm chuyến, dù chuyến cuối vắng khách (giữ cột trống); `auto-fit` là xe ghép khách — bao nhiêu người bấy nhiêu chuyến, còn chỗ thừa thì chia đều cho các xe đang chạy (cột giãn ra lấp chỗ trống).

This bears the most famous snippet in all of CSS Grid and one of the all-time great CSS tricks:

> 📄 **Code ví dụ:** [`examples/02-the-repeat-function-and-keywords.scss`](examples/02-the-repeat-function-and-keywords.scss)

The difference between the keywords is spelled out in detail here.

> **Tóm gọn 1 câu:** `repeat()` thay việc gõ tay lặp đi lặp lại; ghép với `auto-fill`/`auto-fit` là lưới tự đếm xem cần bao nhiêu cột — mẹo card responsive không cần media query.

## Masonry

Mục này nói về bố cục "đá quý xếp chồng" (như Pinterest) — cách các ô cao thấp khác nhau tự kín kẽ không lỗ hổng. Lưu ý: đây vẫn là tính năng thử nghiệm, đọc để biết chứ đừng dùng vội vào production.

An experimental feature of CSS grid is masonry layout. Note that there are lots of approaches to CSS masonry, but mostly of them are trickery and either have major downsides or aren’t what you quite expect.

The spec has an official way now, and this is behind a flag in Firefox:

> 📄 **Code ví dụ:** [`examples/03-masonry.scss`](examples/03-masonry.scss)
See Rachel’s article for a deep dive.

> **Tóm gọn 1 câu:** Masonry là lưới "xếp gạch kiểu Pinterest" — spec chính thức đã có nhưng còn nằm sau flag, chưa nên dùng thật.

## Subgrid

Mục này nói về cách một item bên trong lưới có thể **mượn đường lưới của cha** để dựng lưới riêng của nó. Đọc để giải bài toán kinh điển: các card cạnh nhau có phần tiêu đề/mô tả dài ngắn khác nhau vẫn thẳng hàng.

Subgrid is an extremely useful feature of grids that allows grid items to have a grid of their own that inherits grid lines from the parent grid.

Ví von: thường thì mỗi item là một "căn hộ tự lo điện nước" — lưới bên trong nó không liên quan gì đến lưới ngoài. Với `subgrid`, căn hộ ấy "cắm vào lưới điện chung của tòa nhà": các hàng/cột bên trong thẳng hàng với các căn hộ hàng xóm.

> 📄 **Code ví dụ:** [`examples/04-subgrid.scss`](examples/04-subgrid.scss)

This is only supported in Firefox right now, but it really needs to get everywhere.

It’s also useful to know about display: contents;. This is not the same as subgrid, but it can be a useful tool sometimes in a similar fashion.

> 📄 **Code ví dụ:** [`examples/05-subgrid.html`](examples/05-subgrid.html)

> **Tóm gọn 1 câu:** Subgrid cho item "cắm vào lưới chung của cha" thay vì tự dựng lưới riêng — các card liền kề vì thế thẳng hàng hoàn hảo.
