---
title: Một số trick và tip trong javascript
author: Trịnh Đình Tài
author_title: Admin
author_url: https://github.com/taitd2610
author_image_url: https://scontent-sin6-1.xx.fbcdn.net/v/t1.6435-9/36756866_226907771464364_2771393154585198592_n.jpg?_nc_cat=101&ccb=1-3&_nc_sid=09cbfe&_nc_ohc=MGgQs4UzM5EAX-5FQaR&_nc_ht=scontent-sin6-1.xx&oh=24342e3e97bc53311a628434d6667de7&oe=60DCA347
tags: [Javascript]
description: This is my first post on Docusaurus 2.
image: https://i.imgur.com/mErPwqL.png
hide_table_of_contents: false
sidebar_label: "Xin chào"
sidebar_position: 1
slug: /mot-so-trick-va-tip-trong-javascript
---

![Alt](https://images.viblo.asia/33c65910-5efb-4db4-a039-d5dd1b792fa1.jpeg)

Đối với một coder web, chắc hẳn chúng ta không còn lạ lẫm gì với javascript nữa nhỉ. Bài viết hôm nay chúng ta sẽ không bàn đến sức mạnh hay công dụng của javascript mà mình sẽ giới thiệu đến mọi người 1 số trick and tip không phải ai cũng biết trong javascript

<!--truncate-->


## 1. Converting to number
Javascript là một ngôn ngữ **loosely typed**, có nghĩa là chúng ta sẽ không định dạng rõ kiểu của biến như là một số ngôn ngữ khác: C, C++,...
Cho nên nó cho phép chúng ta convert kiểu biến tùy vào từng ngữ cảnh. Việc convert 1 giá trị của biến thành số, đặc biệt là string thành số rất phổ biến

### Dùng toán tử một ngôi +

```javascript
typeof(+"10")  // "number"
```
> Phép toán một ngôi là một phép toán chỉ có một toán hạng. Toán hạng này đứng trước hoặc sau toán tử.

```javascript
+true  // 1
+false // 0
+null  // 0
```
### Number
Cú pháp `Number(value)` để convert 1 string hoặc 1 giá trị khác thành kiểu *Number* . Nếu không thể chuyển đổi được thì nó trả về giá trị `NaN`(Not a Number)

```javascript
Number('10')   // 10
Number('1.0')  // 1
Number('1.1')  // 1.1
Number('abc')  // NaN
```

### parseInt
Các bạn có thể tham khảo thêm vể các tham số tại [parseInt()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt).  
Method này luôn luôn trả về 1 integer

### parseFloat
Nếu bạn muốn trả về 1 số thập phân thì có thể dùng [parseFloat()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseFloat).

```javascript
parseFloat('10.01')   // 10.01
parseFloat('10.00')   // 10
parseFloat('10 abc')  // 10
```

## 2. Quản lý objects
Ở đây mình đề cập đến **Destructuring**, nó là 1 phần rất quan trọng trong ES6 và sử dụng rất thường xuyên  
Nó cho phép ta trích xuất dữ liệu từ object và gán ngay vào biến

```javascript
const test = {a: 100, b: 200}
const {a, b} = test
// Hoặc là đổi tên lại biến được gán
const {a: x, b: y} = test
console.log(x, y)  // 100 200
```

Ngoài ra chúng ta còn có thể lấy được riêng lẻ 1 giá trị trong 1 object trả về của 1 function

```javascript
const getUser = () => {
  return {
    firstName: 'Nguyen Khhac',
    lastName: 'Thang',
    age: 22
  }
}
const { age } = getUser()
console.log(age)    // 22
```

Bằng cách này chúng ta có thể return nhiều giá trị 1 lúc bằng cách return 1 object, và lấy ra 1 vài giá trị
Một tip nhở ở đây nếu như chúng ta muốn lấy toàn bộ object và loại bỏ 1 số thuộc tính thì:

```javascript
const { age:_, ...user } = getUser()
console.log(user)    // {firstName: "Nguyen Khac", lastName: "Thang"}
```

## 3. Hoán đổi giá trị của 2 biến
Nếu như bạn từng code các ngôn ngữ hướng cấu trúc như C thì việc hoán đổi này cần phải dùng biến tạm để lưu, ngoài ra dùng function thì chúng ta còn cần phải truyền con trỏ, khá phức tạp phải không (Hầu như cái gì liên quan đến con trỏ và địa chỉ ô nhớ đều rất phức tạp :v)  
Trong javascript thì có 1 trick đơn giản như sau:

```javascript
let a = 1, b = 2
[a, b] = [b, a]    // a = 2, b = 1
```

## 4. Thiết lập giá trị mặc định
### Variable
Ở đây mình muốn giới thiệu đến [toán tử kết hợp `nullish` (??)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Nullish_coalescing_operator)  
Đây là 1 toán tử logic mà trả về toán hạng bên phải khi toán hạng bên trái là `null` hoặc `undefined`

```javascript
const variable = test ?? []
Parameters
const getCircle =  (width, height = 100) => {
    return 2 * (width + height);
}

const circle = getCircle(50);
console.log(circle);   // 300
```

Giá trị `height` nếu như không được truyền vào thì sẽ lấy giá trị mặc định

### Objects
```javascript
const test = { height: 400 };
const { height = 750, width = 500 } = test;
console.log(height); // 400
console.log(width);  // 500
```

Giá trị mặc định được gán khi thuộc tính đó `undefined`

## 5. Random 1 số nào đó trong khoảng
Muốn random 1 số nguyên trong khoảng cho trước ta có thể sử dụng `Math.random()`, vì `Math.random()` trả về 1 số thập phân trong [0, 1], nên ta thực hiện như sau:

```javascript
const randomNumber = (min, max) => Math.floor(Math.random() * (max - min + 1) + min);
```

## 6. Đảo ngược một chuỗi
Bạn có thể đảo ngược một chuỗi bằng cách sử dụng các phương kết hợp các phương thức `split`, `join` và `reverse`

```js
const stringReverse = str => str.split("").reverse().join("");

stringReverse("Welcome to Javascript")
//tpircsavaJ ot emocleW
```

## 7. Loại bỏ các mảng bị duplicates
Ta có thể kết hợp kiểu object Set với toán tử spread (...) để tạo mảng mới với các giá trị duy nhất

```javascript
const array = [1, 1, 2, 4, 3, 2]
const uniqueArray = [...new Set(array)]    // [1, 2, 4, 3]
```

## 8. Loại bỏ các giá trị sai ra khỏi một mảng 
Có thể dễ dàng bỏ qua các giá trị sai như `0`, `undefined`, `null`, `false`, `""`, `''` thông qua tip dưới đây 

```javascript
const array = [3, 0, 6, 7, '', false];
array.filter(Boolean);
// Output
(3) [3, 6, 7]
```

## 9. Tìm tổng, giá trị nhỏ nhất, lớn nhất, giá trị trung bình của một mảng số
Javascript `reducer` cho phép tính toán các phép toán cơ bản.

```javascript
const array  = [5,4,7,8,9,2];
```

- Tổng

```javascript
const sum = array.reduce((a, b) => a + b)
// 35
```

- Giá trị nhỏ nhất

```javascript
const min = array.reduce((a,b) => a<b?a:b)
// 2
```

- Giá trị lớn nhất

```javascript
const max = array.reduce((a,b) => a>b?a:b)
// 9
```

- Giá trị trung bình

```javascript
const average = array.reduce((a, b) => a + b) / array.length
// 5.83
```

## 10. Merge 2 objects

```js
const user = { 
 name: 'Kapil Raghuwanshi', 
 gender: 'Male' 
 };
const college = { 
 primary: 'Mani Primary School', 
 secondary: 'Lass Secondary School' 
 };
const skills = { 
 programming: 'Extreme', 
 swimming: 'Average', 
 sleeping: 'Pro' 
 };

const summary = {...user, ...college, ...skills};

// Output 
gender: "Male"
name: "Kapil Raghuwanshi"
primary: "Mani Primary School"
programming: "Extreme"
secondary: "Lass Secondary School"
sleeping: "Pro"
swimming: "Average"
```

## 10. Viết hoa đầu chuỗi
Mặc dù Javascript không cung cấp phương thức viết hoa tích hợp, nhưng việc viết phương thức viết hoa đầu chuỗi chúng ta chỉ mất một dòng.

```javascript
const capitalize = str => str.charAt(0).toUpperCase() + str.slice(1)

console.log(capitalize("javascript one-liners are fun"))
//Javascript one-liners are fun
```

## 11. Sắp xếp Mảng chuỗi, số hoặc đối tượng
Chúng ta có các phương thức `sort()` và `reverse()` để sắp xếp các chuỗi nhưng còn số hoặc mảng đối tượng thì sao? Hãy cùng kiểm tra các thủ thuật sắp xếp cho số và đối tượng theo thứ tự tăng và giảm.  

- Sắp xếp mảng chuỗi

```js
const stringArr = ["Joe", "Kapil", "Steve", "Musk"]
stringArr.sort();
// Output
(4) ["Joe", "Kapil", "Musk", "Steve"]

stringArr.reverse();
// Output
(4) ["Steve", "Musk", "Kapil", "Joe"]
```  

- Sắp xếp mảng số

```js
const array  = [40, 100, 1, 5, 25, 10];
array.sort((a,b) => a-b);
// Output
(6) [1, 5, 10, 25, 40, 100]

array.sort((a,b) => b-a);
// Output
(6) [100, 40, 25, 10, 5, 1]
```  

- Sắp xếp mảng đối tượng

```js
const objectArr = [ 
    { first_name: 'Lazslo', last_name: 'Jamf'     },
    { first_name: 'Pig',    last_name: 'Bodine'   },
    { first_name: 'Pirate', last_name: 'Prentice' }
];
objectArr.sort((a, b) => a.last_name.localeCompare(b.last_name));
// Output
(3) [{…}, {…}, {…}]
0: {first_name: "Pig", last_name: "Bodine"}
1: {first_name: "Lazslo", last_name: "Jamf"}
2: {first_name: "Pirate", last_name: "Prentice"}
length: 3
```

## 12. Trộn một mảng
Sử dụng phương thức `Math.random()`

```js
const list = [1, 2, 3, 4, 5, 6, 7, 8, 9];
list.sort(() => {
    return Math.random() - 0.5;
});
// Output
(9) [2, 5, 1, 6, 9, 8, 4, 3, 7]
// Call it again
(9) [4, 1, 7, 5, 3, 8, 2, 9, 6]
```

## 11. Làm tròn số thập phân
Làm tròn số thập phân đến một vị trí thập phân cố định là một công việc khó khăn trong Javascript. Mặc dù phương thức `toFixed()` được tích hợp sẵn có thể dễ dàng thực hiện chuyển đổi này, nhưng nó cho kết quả kỳ lạ trong một số trường hợp do cách hoạt động của dấu phẩy động.

```javascript
Number((2.935).toFixed(2)) //2.94
Number((12.349345).toFixed(4)) //12.2493
Number((2.5398).toFixed(3)) //2.540

Number((1.005).toFixed(2)) //outputs 1 instead of 1.01
Number((1.555).toFixed(2)) //outputs 1.55 instead of 1.56
```

Để tránh hành vi không mong muốn này, chúng ta có thể biểu diễn các số trong ký hiệu hàm mũ và sử dụng `Math.round()` để làm tròn số thập phân đến một số vị trí thập phân nhất định.

```javascript
const round = (n, d) => Number(Math.round(n + "e" + d) + "e-" + d)

round(1.005, 2) //1.01
round(1.555, 2) //1.56
```

## 12. Tạo ID ngẫu nhiên

Hàm này tạo ra một ID ngẫu nhiên bằng cách sử dụng `Math.random()`. Vì `Math.random()` không đảm bảo rằng tất cả các số được tạo ra là duy nhất, nên phương pháp này không an toàn 100% để sử dụng trong sản xuất. Nhưng không có hại gì khi sử dụng nó trong quá trình phát triển để nhanh chóng nhận được ID để hoàn thành việc triển khai và thử nghiệm ứng dụng.

```javascript
const randomID = Math.random().toString(36).substring(2)
```

## 13. Kiểm tra xem người dùng đã cuộn xuống cuối trang hay chưa
Nếu bạn muốn hiển thị / thực thi nội dung nào đó khi người dùng cuộn xuống cuối trang, hãy sử dụng tùy chọn này để kiểm tra xem người dùng đã cuộn xuống cuối trang hay chưa.

```javascript
const scrolledToBottom = () => document.documentElement.clientHeight + window.scrollY >= document.documentElement.scrollHeight
```

## 14. Chuyển đổi Hiển thị một phần tử
Bạn có thể dễ dàng chuyển đổi giữa ẩn và hiển thị một phần tử với chỉ một dòng code.

```javascript
const toggle = element => element.style.display = (element.style.display === "none" ? "block" : "none")
```

## 15. Tạo màu Hex ngẫu nhiên
Phương thức này tạo ra một mã hex ngẫu nhiên bằng cách sử dụng `Math.random()` và `padEnd()`. 

```javascript
const hexColor = () => "#" + Math.floor(Math.random() * 0xffffff).toString(16).padEnd(6, '0')
```

## 16. Cuộn lên đầu trang
Bạn có thể cuộn lên đầu trang trong Javascript bằng phương thức `scrollTo()`. Nó chấp nhận tọa độ X và Y của vị trí mà Javascript sẽ cuộn đến. Vì vậy, khi chúng ta gán 0 cho X và Y, nó sẽ cuộn lên đầu trang.

```javascript
const toTop = () => window.scrollTo(0, 0)
```


## 17. Xóa tất cả cookie
Bạn có thể xóa tất cả các cookie được ứng dụng lưu trữ bằng cách đặt ngày hết hạn của chúng thành một ngày quá khứ. Vì vậy, nếu bạn đặt ngày hết hạn thành ngày đầu tiên trong hệ thống thời gian Javascript, hệ thống sẽ tự động hết hạn cookie. Và bạn có thể xóa dữ liệu được lưu trữ trong cookie cùng với bước trước đó.

```js
const clearCookies = document.cookie.split(';').forEach(cookie => document.cookie = cookie.replace(/^ +/, '').replace(/=.*/, `=;expires=${new Date(0).toUTCString()};path=/`));
```

## 18. Tách HTML khỏi văn bản
Khi chấp nhận đầu vào của người dùng và trong các trường hợp sử dụng khác, bạn có thể muốn tách bất kỳ phần tử HTML nào trong văn bản mà bạn xử lý. Với sự trợ giúp của `DOMParser`.

```js
const stripHtml = html => (new DOMParser().parseFromString(html, 'text/html')).body.textContent || ''
```

## 19. Phát hiện chế độ Dark Mode
Nếu bạn muốn phát hiện xem người dùng đã bật chế độ tối trong trình duyệt của họ hay chưa, hãy sử dụng  phương thức này.

```js
const isDarkMode = window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches
```

## 20. Dynamic property names

Trong ES6 bạn có thể dùng 1 biến để làm key cho objects như ví dụ sau:

```javascript
const type = "a";
const item = {
  [type]: "b"
};

console.log(item); // {fruit: "b"}
item[type]         // b
item["a"]          // b
item.a             // b
```

## 21. Toán tử kết hợp nullish
Toán tử kết hợp nullish (??) là một toán tử logic trả về toán hạng bên phải của nó khi toán hạng bên trái của nó là null hoặc không xác định, và nếu không trả về toán hạng bên trái của nó.

```js
const foo = null ?? 'my school';
// Output: "my school"

const baz = 0 ?? 42;
// Output: 0
```

Trên đây mình đã giới thiệu 1 số tip & trick sử dụng trong javascript, mong rằng nó có giúp ích cho các bạn trong việc code sau này  
Mình cũng không biết nhiều về js lắm nhưng mình cũng đang cố gắng học và sẽ cố gắng để viết một số bài chia sẻ lại chút hiểu biết của mình đến các bạn. Cảm ơn các bạn đã theo dõi.