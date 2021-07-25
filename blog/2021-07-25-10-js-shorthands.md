---
title: 10 Shorthands JavaScript tuyệt vời
author: Trịnh Đình Tài
author_title: Admin
author_image_url: https://scontent-hkt1-1.xx.fbcdn.net/v/t1.6435-9/36756866_226907771464364_2771393154585198592_n.jpg?_nc_cat=101&ccb=1-3&_nc_sid=09cbfe&_nc_ohc=oQWlAyKcdyQAX_CL9Mj&_nc_ht=scontent-hkt1-1.xx&oh=b635b50219d2e77f2a98ee24f7cab44c&oe=611FDFC7
tags: [Javascript]
description: This is my first post on Docusaurus 2.
image: https://i.imgur.com/mErPwqL.png
hide_table_of_contents: false
sidebar_label: "Xin chào"
sidebar_position: 1
slug: /10-awesome-js-shorthands
---

![Alt](https://iampalash.hashnode.dev/_next/image?url=https%3A%2F%2Fcdn.hashnode.com%2Fres%2Fhashnode%2Fimage%2Fupload%2Fv1627195486358%2FMFtV0vsKJh.png%3Fw%3D1600%26h%3D840%26fit%3Dcrop%26crop%3Dentropy%26auto%3Dcompress%2Cformat%26format%3Dwebp&w=1920&q=75)

Xin chào tất cả mọi người 👋 Hôm nay tôi muốn chia sẻ với bạn 10 shorthands **_JavaScript_** tuyệt vời sẽ giúp tăng tốc độ của bạn bằng cách giúp bạn viết ít code hơn.

Bắt đầu nào!

<!--truncate-->

## 1. Hợp nhất mảng

**Longhand:**
Chúng ta thường hợp nhất hai mảng bằng cách sử dụng phương thức Array `concat()`. Phương thức `concat()` được sử dụng để hợp nhất hai hoặc nhiều mảng. Phương thức này không thay đổi các mảng hiện có mà thay vào đó trả về một mảng mới. Sau đây là một ví dụ đơn giản:

```js
let apples = ["🍎", "🍏"];
let fruits = ["🍉", "🍊", "🍇"].concat(apples);

console.log(fruits);
//=> ["🍉", "🍊", "🍇", "🍎", "🍏"]
```

**Shorthand:**
Chúng ta có thể rút viết ngắn hơn bằng cách sử dụng Toán tử Spread của ES6 (...) như sau:

let apples = ['🍎', '🍏'];
let fruits = ['🍉', '🍊', '🍇', ...apples]; // <-- here

console.log( fruits );
//=> ["🍉", "🍊", "🍇", "🍎", "🍏"]
và chúng ta vẫn nhận được kết quả tương tự. 😃

## 2. Merge Arrays (nhưng khi bắt đầu)

Giả sử chúng ta muốn thêm tất cả các mục từ mảng `apples` vào đầu mảng `fruits` , thay vì ở cuối như chúng ta đã thấy trong ví dụ trước. Chúng ta có thể làm điều này bằng cách sử dụng `Array.prototype.unshift()` như sau:

```js
let apples = ["🍎", "🍏"];
let fruits = ["🥭", "🍌", "🍒"];

// Add all items from apples onto fruits at start
Array.prototype.unshift.apply(fruits, apples);

console.log(fruits);
//=> ["🍎", "🍏", "🥭", "🍌", "🍒"]
```

Bây giờ phẩn tử của mảng `apples` sẽ ở đầu thay vì ở cuối mảng mới sau khi hợp nhất.

**Shorthand:**
Chúng ta có thể rút ngắn đoạn code này bằng cách sử dụng Toán tử Spread ES6 (...) như sau:

```js
let apples = ["🍎", "🍏"];
let fruits = [...apples, "🥭", "🍌", "🍒"]; // <-- here

console.log(fruits);
//=> ["🍎", "🍏", "🥭", "🍌", "🍒"]
```

## 3. Sao chép một mảng

**Longhand:**
Chúng ta có thể dễ dàng sao chép một mảng bằng phương thức Array `slice()` như sau:

```js
let fruits = ["🍉", "🍊", "🍇", "🍎"];
let cloneFruits = fruits.slice();

console.log(cloneFruits);
//=> ["🍉", "🍊", "🍇", "🍎"]
```

**Shorthand:**

Sử dụng Toán tử Spread ES6 (...), chúng ta có thể sao chép một mảng như thế này:

```js
let fruits = ["🍉", "🍊", "🍇", "🍎"];
let cloneFruits = [...fruits]; // <-- here

console.log(cloneFruits);
//=> ["🍉", "🍊", "🍇", "🍎"]
```

## 4. Destructuring Assignment

**Longhand:**
Trong khi làm việc với mảng, đôi khi chúng ta cần "giải nén" các mảng thành một loạt các biến như sau:

```js
let apples = ["🍎", "🍏"];
let redApple = apples[0];
let greenApple = apples[1];

console.log(redApple); //=> 🍎
console.log(greenApple); //=> 🍏
```

**Shorthand:**
Chúng tôi có thể đạt được kết quả tương tự trong một dòng duy nhất bằng cách sử dụng [**Destructuring assignment**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment) như thế này:

```js
let apples = ["🍎", "🍏"];
let [redApple, greenApple] = apples; // <-- here

console.log(redApple); //=> 🍎
console.log(greenApple); //=> 🍏
```

## 5. Template literals

**Longhand:**
Thông thường, khi chúng ta phải thêm một biểu thức vào một chuỗi, chúng ta làm như sau:

```js
// Display name in between two strings
let name = "Palash";
console.log("Hello, " + name + "!");
//=> Hello, Palash!

// Add & Subtract two numbers
let num1 = 20;
let num2 = 10;
console.log("Sum = " + (num1 + num2) + " and Subtract = " + (num1 - num2));
//=> Sum = 30 and Subtract = 10
```

**Shorthand:**
Với các ký tự của `Template literals`, chúng ta có thể sử dụng backticks (`` ` ``), cho phép chúng ta nhúng bất kỳ biểu thức nào vào chuỗi, bằng cách đặt nó trong `${...}` như sau:

```js
// Display name in between two strings
let name = "Palash";
console.log(`Hello, ${name}!`); // <-- No need to use + var + anymore
//=> Hello, Palash!

// Add two numbers
let num1 = 20;
let num2 = 10;
console.log(`Sum = ${num1 + num2} and Subtract = ${num1 - num2}`);
//=> Sum = 30 and Subtract = 10
```

## 6. Vòng lặp For

**Longhand:**
Sử dụng vòng lặp `for`, chúng ta có thể lặp qua một mảng như thế này:

```js
let fruits = ["🍉", "🍊", "🍇", "🍎"];

// Loop through each fruit
for (let index = 0; index < fruits.length; index++) {
  console.log(fruits[index]); // <-- get the fruit at current index
}

//=> 🍉
//=> 🍊
//=> 🍇
//=> 🍎
```

**Shorthand:**

Chúng ta có thể đạt được kết quả tương tự bằng cách sử dụng câu lệnh `for ... of` nhưng với rất ít code như thế này:

```js
let fruits = ["🍉", "🍊", "🍇", "🍎"];

// Using for...of statement
for (let fruit of fruits) {
  console.log(fruit);
}

//=> 🍉
//=> 🍊
//=> 🍇
//=> 🍎
```

## 7. Arrow Functions

**Longhand:**
Để lặp qua một mảng, chúng ta cũng có thể sử dụng phương thức Array `forEach()`. Nhưng chúng ta phải viết nhiều code hơn một chút, ít hơn so với vòng lặp `for` phổ biến nhất mà chúng ta đã thấy ở trên, nhưng vẫn nhiều hơn một chút so với câu lệnh `for...of`:

```js
let fruits = ["🍉", "🍊", "🍇", "🍎"];

// Using forEach method
fruits.forEach(function (fruit) {
  console.log(fruit);
});

//=> 🍉
//=> 🍊
//=> 🍇
//=> 🍎
```

**Shorthand:**
Nhưng với [Arrow function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions), chúng ta có thể viết code vòng lặp đầy đủ trong một dòng như thế này:

```js
let fruits = ["🍉", "🍊", "🍇", "🍎"];
fruits.forEach((fruit) => console.log(fruit)); // <-- Magic ✨

//=> 🍉
//=> 🍊
//=> 🍇
//=> 🍎
```

Tôi chủ yếu sử dụng vòng lặp `forEach` với các hàm mũi tên, nhưng tôi muốn chỉ cho bạn cả cách viết tắt của vòng lặp: câu lệnh `for...of` và vòng lặp `forEach`. Vì vậy, bạn có thể sử dụng bất kỳ code nào bạn thích dựa trên sở thích của bạn. 😃

## 8. Tìm một đối tượng trong một mảng

**Longhand:**
Để tìm một đối tượng trong một mảng đối tượng bằng một trong các thuộc tính của nó, chúng ta thường sử dụng vòng lặp `for` như sau:

```js
let inventory = [
  { name: "Bananas", quantity: 5 },
  { name: "Apples", quantity: 10 },
  { name: "Grapes", quantity: 2 },
];

// Get the object with the name `Apples` inside the array
function getApples(arr, value) {
  for (let index = 0; index < arr.length; index++) {
    // Check the value of this object property `name` is same as 'Apples'
    if (arr[index].name === "Apples") {
      //=> 🍎

      // A match was found, return this object
      return arr[index];
    }
  }
}

let result = getApples(inventory);
console.log(result);
//=> { name: "Apples", quantity: 10 }
```

**Shorthand:**
Ồ! Chúng ta phải viết rất nhiều trước đây, để thực hiện logic này. Nhưng với phương thức của `Array.find()` và arrow function `=>`, chúng ta có thể dễ dàng đạt được điều này trong một dòng như thế này:

```js
// Get the object with the name `Apples` inside the array
function getApples(arr, value) {
  return arr.find((obj) => obj.name === "Apples"); // <-- here
}

let result = getApples(inventory);
console.log(result);
//=> { name: "Apples", quantity: 10 }
```

## 9. Chuyển đổi chuỗi thành số nguyên

**Longhand:**
Hàm `parseInt()` được sử dụng để phân tích cú pháp một chuỗi và trả về một số nguyên:

```js
let num = parseInt("10");

console.log(num); //=> 10
console.log(typeof num); //=> "number"
```

**Shorthand:**
Chúng ta có thể đạt được kết quả tương tự bằng cách thêm tiền tố `+` trước chuỗi như thế này:

```js
let num = +"10";

console.log(num); //=> 10
console.log(typeof num); //=> "number"
console.log(+"10" === 10); //=> true
```

## 10. Short-circuit Evaluation

**Longhand:**
Chủ yếu câu lệnh `if-else` được sử dụng nếu chúng ta phải đặt một giá trị dựa trên một giá trị khác không phải là một giá trị **_falsy_** như thế này:

```js
function getUserRole(role) {
  let userRole;

  // If role is not falsy value
  // set `userRole` as passed `role` value
  if (role) {
    userRole = role;
  } else {
    // else set the `userRole` as USER
    userRole = "USER";
  }

  return userRole;
}

console.log(getUserRole()); //=> "USER"
console.log(getUserRole("ADMIN")); //=> "ADMIN"
```

**Shorthand:**
Nhưng khi sử dụng short-circuit evaluationh (`||`), chúng ta có thể thực hiện điều này trong một dòng như sau:

```js
function getUserRole(role) {
  return role || "USER"; // <-- here
}

console.log(getUserRole()); //=> "USER"
console.log(getUserRole("ADMIN")); //=> "ADMIN"
```

Về cơ bản, `biểu thức1 || biểu thức 2` là short-circuit evaluated **_truthy_**. Vì vậy, nó giống như nói rằng nếu `biểu thức1` là đúng, đừng bận tâm đánh giá phần còn lại của biểu thức.

Cuối cùng, tôi muốn kết thúc bài viết này bằng cách chia sẻ một trích dẫn của **_Jeff Atwood_**:

> "Code is only our enemy because there are so many of us programmers writing so damn much of it. If you can’t get away with no code, the next best thing is to start with brevity.
>
> If you love writing code — really, truly love to write code — you’ll love it enough to write as little of it as possible."

Nếu bạn thích bài viết này, hãy để lại một ❤ cho tớ nhé!.

Happy Coding!

---

## Link tham khảo:

https://iampalash.hashnode.dev/10-awesome-javascript-shorthands
