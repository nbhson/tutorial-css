# grid-auto-columns & grid-auto-rows

> **🇻🇳 Tóm tắt:** `grid-auto-columns` / `grid-auto-rows` đặt kích thước cho các track **tự sinh** (implicit grid) — xuất hiện khi số item vượt số ô đã định nghĩa, hoặc item được đặt ra ngoài lưới explicit.
>
> *Nội dung gốc tiếng Anh bên dưới — tham khảo thêm.*


Specifies the size of any auto-generated grid tracks (aka implicit grid tracks). Implicit tracks get created when there are more grid items than cells in the grid or when a grid item is placed outside of the explicit grid. (see The Difference Between Explicit and Implicit Grids)

Hãy hình dung khách sạn hết phòng đã đặt trước: đoàn khách đến thừa vẫn phải được xếp phòng, dù phòng đó không có trong kế hoạch ban đầu. Implicit track chính là "phòng phát sinh" vậy — và đây là chỗ bạn đặt kích thước cho những phòng đó.

Values:
- <track-size> – can be a length, a percentage, or a fraction of the free space in the grid (using the fr unit)

> 📄 **Code ví dụ:** [`examples/01-grid-auto-columns-grid-auto-rows.scss`](examples/01-grid-auto-columns-grid-auto-rows.scss)

![alt text](https://css-tricks.com/wp-content/uploads/2018/11/grid-auto-columns-rows-01.svg)

## Reason

![alt text](https://css-tricks.com/wp-content/uploads/2018/11/grid-auto-columns-rows-02.svg)

![alt text](https://css-tricks.com/wp-content/uploads/2018/11/grid-auto-columns-rows-03.svg)

> **Tóm gọn 1 câu:** `grid-auto-columns/rows` là "quy cách phòng phát sinh" — item nào tràn ra ngoài lưới bạn vẽ sẵn thì vẫn được xếp vào track tự sinh với kích thước bạn đã định trước.