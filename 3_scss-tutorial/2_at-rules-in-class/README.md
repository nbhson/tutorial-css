# Sass @-Rules and Directives

Mục này là "bản đồ" liệt kê toàn bộ các @-rules và directives của Sass — đọc để biết Sass có những công cụ gì và mỗi công cụ đảm nhận việc nào trước khi đi sâu vào từng cái.

Sass rule Directive

| Index | Directive  | Description                                                                                                                                          |
| ----- | ---------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1     | `@import`  | It is used to import the sass or scss files. It directly takes the filename to import.                                                               |
| 2     | `@media`   | It is used to set style rule to different media types.                                                                                               |
| 3     | `@extend`  | It specifies and shares the rules and relationships between selectors.                                                                               |
| 4     | `@at-root` | It is specified as a collection of nested rules which is able to make style block at root of the document.                                           |
| 5     | `@debug`   | This directive is used to detect the errors and display the SassScript expression values to the standard error output stream.                        |
| 6     | `@warn`    | This directive is used to get cautionary advice about the problem. It displays the SassScript expression values to the standard error output stream. |
| 7     | `@error`   | This directive is used to display the SassScript expression value as fatal error.                                                                    |

> **Cách đọc bảng này:** mỗi dòng là một directive với cột `Index` chỉ số thứ tự; đọc từ trên xuống theo hướng "nhập file → điều kiện media → chia sẻ style → debug/lỗi". Muốn biết directive làm gì, nhìn cột Description; nhớ tên thì nhìn cột Directive. Ví von: đây là danh mục dụng cụ trong tủ — `@import` là kho nguyên liệu, `@debug`/`@warn`/`@error` là chuông báo, còn `@extend` là cách dùng chung một công thức.

> **Tóm gọn 1 câu:** @-rules là "bộ điều khiển" của Sass — import file, chia style theo media, dùng chung selector và văng thông báo khi có sự cố.
