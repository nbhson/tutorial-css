# Control Directives & Expressions

Vậy làm sao cho stylesheet "biết suy nghĩ"? Control directives & expressions của Sass cho phép style theo điều kiện (if/else) và lặp lại style nhiều lần với biến thể khác nhau — tất cả chạy trên SassScript.

Ví von: nếu biến là nguyên liệu thì control directive là công thức nấu có điều kiện — "nếu món mặn thì nêm muối, mỗi vòng khuấy thêm một chút gia vị". Control directives là một phần của thư viện compass, chủ yếu dùng trong mixin và đòi hỏi sự linh hoạt đáng kể.

| Index | Directive                                   | Description                                                                                                                                             |
| ----- | ------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1     | `if() function`                             | The if() function is based on the condition. It returns only one result from two possible values.                                                       |
| 2     | `@if directive`                             | The @if directive accepts SassScript expressions and uses the nested styles whenever the result of the expression is anything other than false or null. |
| 3     | `@else if directive`                        | The Sass @else-if directive is used when @if directive is failed. If it is failed @else directive is used.                                              |
| 4     | `@for directive with through keyword`       | The @for directive facilitates you to generate styles in a loop.                                                                                        |
| 5     | `@each directive`                           | A variable is defined within the @each directive which contains the value of each item in a list.                                                       |
| 6     | `@each directive with multiple assignments` | We can use Sass @each directive with multiple values like $var1, $var2, $var3, ... in .                                                                 |
| 7     | `@for directive with to keyword`            | In Sass @for directive, the "to" keyword is used to specify the range form value to the value before value.                                             |
| 8     | `@while directives`                         | It takes SassScript expressions and until the statement evaluates to false it iteratively outputs nested styles.                                        |

> **Cách đọc bảng này:** đọc theo cột Directive để biết có bao nhiêu công cụ rẽ nhánh (`if`, `@if`, `@else if`) và vòng lặp (`@for`, `@each`, `@while`); cột Description mô tả cơ chế từng cái. Hơi hướng đọc: nhóm 1–3 là "ra quyết định", nhóm 4–8 là "lặp có kiểm soát".

> **Tóm gọn 1 câu:** Control directives là "bộ não có điều kiện và vòng lặp" của Sass — style tự rẽ nhánh và lặp theo dữ liệu thay vì chép tay.
