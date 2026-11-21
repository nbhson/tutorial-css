
# Cross Browser Code

Bạn từng thấy cùng một trang web hiển thị đẹp trên Chrome nhưng "vỡ layout" trên Safari? Đó chính là bài toán mà mục này giải quyết: làm sao để CSS của bạn hoạt động nhất quán trên mọi trình duyệt.

Khả năng tương thích giữa các trình duyệt là điều bắt buộc trong quá trình phát triển phần mềm, vì mọi trang web phải hoạt động hoàn hảo trên các nền tảng hệ điều hành và trình duyệt khác nhau.

Hãy hình dung: trình duyệt là những "đầu bếp" khác nhau, cùng nhận một công thức (CSS) nhưng mỗi người hiểu và nấu theo kiểu riêng. Vì CSS là một yếu tố cần thiết trong việc phát triển bất kỳ trang web hiện đại nào. Với mức độ phân mảnh trình duyệt thiết bị trên thế giới, CSS đương nhiên sẽ phải tương thích với nhiều trình duyệt để cho phép một trang web hiển thị hoàn hảo cho người dùng có các tùy chọn trình duyệt khác nhau.

CSS là một khía cạnh tạo kiểu được sử dụng trên các trang web để làm cho chúng trông vượt trội hơn về mặt phong cách. Bài viết này sẽ khám phá các kỹ thuật CSS khác nhau được sử dụng để cải thiện khả năng tương thích trên nhiều trình duyệt của trang web.

> **Tóm gọn 1 câu:** Cross-browser code là viết CSS sao cho "công thức" này nấu ra cùng một món ngon trên mọi "bếp" — từ Chrome, Firefox đến Safari.

## 3 CSS techniques for Improved Cross Browser Compatibility

Mục này trình bày 3 kỹ thuật thực chiến để xử lý khác biệt giữa các trình duyệt — đọc để biết cách "nói chuyện" riêng với từng đầu bếp khi công thức chung bị hiểu sai.

### Setting gradient color on div in different browsers

> 📄 **Code ví dụ:** [`examples/01-setting-gradient-color-on-div-in-different-browsers.css`](examples/01-setting-gradient-color-on-div-in-different-browsers.css)

### Setting border-radius in Popular Browsers (Mozilla, Chrome, Safari, Opera)

Syntax: `border-*-*-radius: [ <length> | <%> ] [ <length> | <%> ]`

> 📄 **Code ví dụ:** [`examples/02-setting-border-radius-in-popular-browsers-mozilla-chrome.css`](examples/02-setting-border-radius-in-popular-browsers-mozilla-chrome.css)

### Setting background image for select tags in Chrome

> 📄 **Code ví dụ:** [`examples/03-setting-background-image-for-select-tags-in-chrome.css`](examples/03-setting-background-image-for-select-tags-in-chrome.css)

## Commonly Observed Cross-Browser Compatibility Issues

Mục này điểm danh những "thủ phạm" phổ biến khiến trang web hiển thị lệch nhau giữa các trình duyệt — đọc để biết trước cần canh phòng cái gì.

- Người ta có thể tìm ra các vấn đề với HTML và CSS trong khi triển khai các tính năng sử dụng tiền tố CSS.
- Các phiên bản cũ hơn của hầu hết các trình duyệt không hỗ trợ các tính năng mới hơn như HTML5 Audio / Video, FlexBox, CSS Grids, v.v.
- Các phiên bản cũ hơn của Internet Explorer không hỗ trợ nhiều chức năng CSS như bộ chọn CSS3, Màu CSS3, Không gian tên CSS, v.v.
- Các lý do phổ biến khác gây ra sự cố tương thích trên nhiều trình duyệt là:
  + Sự không tương thích của trình duyệt với hệ điều hành (OS).
  + Các triển khai khác nhau của JavaScript 
  + Lỗi trong trình duyệt Vấn đề với căn chỉnh trang


> Supported by Edge with prefix `-webkit-`
> Supported by Firefox with prefix `-moz-`
> Supported by Chrome with prefix `-webkit-`
> Supported by Safari with prefix `-webkit-`
> Supported by Opera with prefix `-webkit-`

> **Tóm gọn 1 câu:** Khi một tính năng chưa "chuẩn hóa", mỗi trình duyệt đòi gọi bằng tên riêng (prefix) — thêm đủ prefix là cách bắt tất cả cùng hiểu một ý.

<https://www.w3schools.com/cssref/css3_browsersupport.asp>