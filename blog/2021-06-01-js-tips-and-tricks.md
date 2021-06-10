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

# Trang tài liệu đầu tiên

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


## 8. Lấy giá trị trung bình của một mảng số
Javascript `reducer` cho phép tính giá trị trung bình của một mảng số

```javascript
const average = arr => arr.reduce((a, b) => a + b) / arr.length

console.log(average([21, 56, 23, 122, 67]))
//57.8
```

## 9. Viết hoa đầu chuỗi
Mặc dù Javascript không cung cấp phương thức viết hoa tích hợp, nhưng việc viết phương thức viết hoa một chuỗi của riêng chúng tôi chỉ mất một dòng.

```javascript
const average = arr => arr.reduce((a, b) => a + b) / arr.length

console.log(average([21, 56, 23, 122, 67]))
//57.8
```

## 9. Dynamic property names
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

Trên đây mình đã giới thiệu 1 số tip & trick sử dụng trong javascript, mong rằng nó có giúp ích cho các bạn trong việc code sau này  
Mình cũng không biết nhiều về js lắm nhưng mình cũng đang cố gắng học và sẽ cố gắng để viết một số bài chia sẻ lại chút hiểu biết của mình đến các bạn. Cảm ơn các bạn đã theo dõi.