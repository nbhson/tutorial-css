
# Animation

## What are CSS Animations?

Mục này trả lời câu hỏi đầu tiên: animation CSS là gì và "khâu chuẩn bị" gồm những gì. Đọc để hiểu khái niệm **khung hình chính** (`@keyframes`) — nền của cả chương.

- Animations cho phép một phần tử dần dần thay đổi từ kiểu này sang kiểu khác. 
- Bạn có thể thay đổi bao nhiêu thuộc tính CSS tùy thích. 
- Để sử dụng Animations CSS, trước tiên bạn phải chỉ định một số khung hình chính cho Animations. 
- Khung hình chính chứa kiểu dáng mà phần tử sẽ có tại một số thời điểm nhất định.

Ví von: `@keyframes` chính là **kịch bản hoạt hình vẽ tay** — bạn vẽ khung đầu (màu đỏ) và khung cuối (màu vàng), trình duyệt tự "vẽ thêm" các khung trung gian cho mượt, như thợ hoạt hình chèn khung giữa.
  
### @keyframes Rule

Mục này nói về hai bước bắt buộc của mọi animation: viết kịch bản `@keyframes`, rồi "gắn kịch bản" lên phần tử thật — thiếu bước nào cũng như có kịch bản mà không mời diễn viên.

- Khi bạn chỉ định kiểu CSS bên trong quy tắc @keyframes, Animations sẽ dần thay đổi từ kiểu hiện tại sang kiểu mới vào những thời điểm nhất định. 
- Để Animations hoạt động, bạn phải liên kết Animations đó với một phần tử. 
- Ví dụ sau liên kết Animations "example" với phần tử <div>. Animations sẽ kéo dài trong 4 giây và nó sẽ dần thay đổi màu nền của phần tử <div> từ "đỏ" sang "vàng":

> 📄 **Code ví dụ:** [`examples/01-keyframes-rule.css`](examples/01-keyframes-rule.css)

### animation-duration

Mục này nói về "độ dài cuộn phim": animation chạy trong bao lâu.

- Thuộc tính xác định thời gian hoàn thành một hoạt ảnh. 
- Cũng có thể sử dụng phần trăm. Bằng cách sử dụng phần trăm, bạn có thể thêm bao nhiêu thay đổi về kiểu tùy thích.

> Nếu thuộc tính thời lượng hoạt ảnh không được chỉ định thì sẽ không có hoạt ảnh nào xảy ra vì giá trị mặc định là 0s (0 giây).

### Delay an Animation

Mục này nói về việc cho diễn viên "chờ đến lượt": animation không chạy ngay mà delay vài giây, kèm mẹo dùng giá trị âm để "bỏ lỡ" n giây đầu.

- Thuộc tính animation-delay chỉ định độ trễ khi bắt đầu hoạt ảnh. Ví dụ sau có độ trễ 2 giây trước khi bắt đầu hoạt ảnh
- Giá trị âm cũng được cho phép. Nếu sử dụng giá trị âm, `hoạt ảnh sẽ bắt đầu như thể nó đã phát được N giây.` — ví von: như bước vào rạp giữa buổi chiếu, bạn bỏ qua N giây đầu tiên.

## Set How Many Times an Animation Should Run

Mục này nói về số lần lặp: chạy một lần rồi dứt, hay lặp mãi mãi như hiệu ứng nhấp nháy thông báo.

- The `animation-iteration-count` property specifies the number of times an animation should run.
- The following example uses the value "`infinite`" to make the animation continue for ever

> **Tóm gọn 1 câu:** Một animation = kịch bản `@keyframes` gắn lên phần tử, kèm ba núm vặn cơ bản: chạy bao lâu (`duration`), chờ bao lâu (`delay`), lặp mấy lần (`iteration-count`).

## Run Animation in Reverse Direction or Alternate 

Mục này nói về "hướng đi" của animation: chạy tới, chạy lui, hay tới lui như con lắc đồng hồ.

- Thuộc tính `animation-direction` chỉ định liệu một hoạt ảnh sẽ được phát tiến, lùi hay theo chu kỳ luân phiên.
- Thuộc tính animation-direction có thể có các giá trị sau: 
  - `normal` - Hoạt ảnh được phát như bình thường (chuyển tiếp). Đây là mặc định 
  - `reverse` - Hoạt ảnh được phát theo hướng ngược lại (ngược) 
  - `alternate` - Hoạt ảnh được phát tiến trước, sau đó phát lùi 
  - `alternate-reverse` - Hoạt ảnh được phát ngược trước, sau đó chuyển tiếp

Ví von: tưởng tượng một video ai đi bộ — `normal` là phát xuôi, `reverse` là tua ngược, `alternate` là tới-lui-tới-lui như con lắc, `alternate-reverse` là con lắc nhưng mở màn bằng nhịp lùi.

## Specify the Speed Curve of the Animation

Mục này nói về "dáng chạy" của animation: nhanh dần, chậm dần hay đều đều — cùng quãng đường nhưng cảm nhận khác hẳn nhau.

- Thuộc tính `animation-timing-function` chỉ định đường cong tốc độ của hoạt ảnh. 
- Thuộc tính `animation-timing-function` có thể có các giá trị sau: 
  - `ease` - Chỉ định hoạt ảnh có khởi đầu chậm, sau đó nhanh, rồi kết thúc chậm (đây là mặc định) 
  - `linear` - Chỉ định hoạt ảnh có cùng tốc độ từ đầu đến cuối 
  - `easy-in` - Chỉ định hoạt ảnh có khởi đầu chậm
  - `easy-out` - Chỉ định hoạt ảnh có kết thúc chậm 
  - `easy-in-out` - Chỉ định hoạt ảnh có khởi đầu và kết thúc chậm 
  - `cub-bezier(n,n,n,n)` - Cho phép bạn xác định các giá trị của riêng mình trong hàm cub-bezier

Ví von: giống cách tài xế lái xe — `linear` là băng quốc lộ giữ đều chân ga, `ease` là chạy trong khu dân cư (vào số rón rén, giữa đường tăng tốc, tới nhà phanh nhẹ), còn `cubic-bezier` là bạn tự hiệu chỉnh bàn đạp theo ý mình.

## Specify the fill-mode For an Animation

Mục này nói về việc animation "để lại gì sau khi diễn xong": giữ cảnh cuối hay quay về cảnh ban đầu. Đây là núm vặn hay bị quên nhất nhưng quyết định hiệu ứng có "dính lại" hay "tự xóa".

- Thuộc tính `animation-fill-mode` chỉ định kiểu cho phần tử đích khi hoạt ảnh không phát (trước khi hoạt ảnh bắt đầu, sau khi hoạt ảnh kết thúc hoặc cả hai). 
- Thuộc tính `animation-fill-mode` có thể có các giá trị sau: 
  - `none` - Giá trị mặc định. Hoạt ảnh sẽ không áp dụng bất kỳ kiểu nào cho phần tử trước hoặc sau khi nó thực thi 
  - `forwards` - Phần tử sẽ giữ lại các giá trị kiểu được đặt bởi khung hình chính cuối cùng (phụ thuộc vào hướng hoạt ảnh và số lần lặp hoạt ảnh)
  - `backwards` - Phần tử sẽ nhận các giá trị kiểu được đặt bởi khung hình chính đầu tiên (phụ thuộc vào hướng hoạt ảnh) và giữ lại giá trị này trong khoảng thời gian trễ hoạt ảnh cả hai - Hoạt ảnh sẽ tuân theo các quy tắc cho cả tiến và lùi, mở rộng các thuộc tính hoạt ảnh theo cả hai hướng

Ví von: như sân khấu sau buổi diễn — `none` là dỡ hết dàn dựng, khán giả thấy sân trống như ban đầu; `forwards` là để nguyên cảnh cuối đứng yên; `backwards` là dựng sẵn cảnh đầu ngay cả khi mới chỉ đang chờ (trong lúc delay).

## Animation Shorthand Property

Mục này nói về cách gộp tất cả các núm vặn ở trên vào **một dòng** khai báo — đọc để viết gọn và nhớ thứ tự giá trị khi viết shorthand.

> 📄 **Code ví dụ:** [`examples/02-animation-shorthand-property.css`](examples/02-animation-shorthand-property.css)

> **Tóm gọn 1 câu:** Shorthand `animation` là "tờ đơn đặt hàng gộp": name, duration, timing, delay, iteration, direction, fill-mode — một dòng thay cho bảy dòng riêng lẻ.

## Reference
https://www.w3schools.com/css/css3_transitions.asp
https://www.joshwcomeau.com/animation/css-transitions/

https://www.w3schools.com/css/css3_animations.asp
https://www.freecodecamp.org/news/how-to-create-custom-css-animations/
https://semicolon.dev/tutorial/css/css-animation-tutorial
https://marksheet.io/css-animations.html