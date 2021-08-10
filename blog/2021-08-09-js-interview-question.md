---
title: 70 câu hỏi phỏng vấn JavaScript
author: Trịnh Đình Tài
author_title: Admin
author_image_url: https://scontent-hkt1-1.xx.fbcdn.net/v/t1.6435-9/36756866_226907771464364_2771393154585198592_n.jpg?_nc_cat=101&ccb=1-3&_nc_sid=09cbfe&_nc_ohc=oQWlAyKcdyQAX_CL9Mj&_nc_ht=scontent-hkt1-1.xx&oh=b635b50219d2e77f2a98ee24f7cab44c&oe=611FDFC7
tags: [CSS]
description: This is my first post on Docusaurus 2.
image: https://i.imgur.com/mErPwqL.png
hide_table_of_contents: false
sidebar_label: "Xin chào"
sidebar_position: 1
slug: /70-javascript-interview-questions
---

![Alt](https://res.cloudinary.com/practicaldev/image/fetch/s--Y3M4cvj9--/c_imagga_scale,f_auto,fl_progressive,h_420,q_auto,w_1000/https://thepracticaldev.s3.amazonaws.com/i/uoeeq22yciso8gpu6etl.png)

## 0. Contents

- [0. Contents](#0-contents)
- [1. Sự khác biệt giữa undefined và null là gì ?](#1-sự-khác-biệt-giữa-undefined-và-null-là-gì-)
- [2. Toán tử `&&` dùng để làm gì?](#2-toán-tử--dùng-để-làm-gì)
- [3. Toán tử `||` dùng để làm gì??](#3-toán-tử--dùng-để-làm-gì)
- [4. Sử dụng toán tử + hoặc toán tử cộng 1 ngôi (Unary) có phải là cách nhanh nhất để chuyển đổi một chuỗi thành một số không?](#4-sử-dụng-toán-tử--hoặc-toán-tử-cộng-1-ngôi-unary-có-phải-là-cách-nhanh-nhất-để-chuyển-đổi-một-chuỗi-thành-một-số-không)
- [5. DOM là gì ?](#5-dom-là-gì-)
- [6. **Event Propagation** là gì?](#6-event-propagation-là-gì)
- [7. **Event Bubbling** là gì?](#7-event-bubbling-là-gì)
- [8. **Capturing Phase** là gì?](#8-capturing-phase-là-gì)
- [9. Sự khác biệt giữa phương thức `event.preventDefault()` và `event.stopPropagation()` là gì?](#9-sự-khác-biệt-giữa-phương-thức-eventpreventdefault-và-eventstoppropagation-là-gì)
- [10. Làm thế nào để biết phương thức `event.preventDefault()` đã được sử dụng trong một phần tử hay chưa?](#10-làm-thế-nào-để-biết-phương-thức-eventpreventdefault-đã-được-sử-dụng-trong-một-phần-tử-hay-chưa)
- [11. Tại sao đoạn code `obj.someprop.x` lại gặp lỗi?](#11-tại-sao-đoạn-code-objsomepropx-lại-gặp-lỗi)
- [12. `event.target` là gì?](#12-eventtarget-là-gì)
- [13. `event.currentTarget` là gì?](#13-eventcurrenttarget-là-gì)
- [14. Sự khác biệt giữa == và === là gì?](#14-sự-khác-biệt-giữa--và--là-gì)
- [2. Link tham khảo](#2-link-tham-khảo)

## 1. Sự khác biệt giữa undefined và null là gì ?

Trước khi hiểu sự khác biệt giữa `undefined` và `null`, chúng ta phải hiểu những điểm tương đồng giữa chúng.

- Chúng thuộc về 7 kiểu nguyên thủy của **_JavaScript_**.

```js
let primitiveTypes = [
  "string",
  "number",
  "null",
  "undefined",
  "boolean",
  "symbol",
  "bigint",
];
```

- Chúng là những giá trị giả **(falsy)**, các giá trị được đánh giá thành false khi chuyển đổi nó thành boolean bằng cách sử dụng `Boolean(value)` hoặc `!!value`

```js
console.log(!!null); //logs false
console.log(!!undefined); //logs false

console.log(Boolean(null)); //logs false
console.log(Boolean(undefined)); //logs false
```

Ok, hãy nói về sự khác biệt.

- `undefined` là giá trị mặc định của một biến chưa được gán giá trị cụ thể. Hoặc một hàm không có giá trị trả về rõ ràng, ví dụ: `console.log(1)`. Hoặc một thuộc tính không tồn tại trong một đối tượng.

```js
let _thisIsUndefined;
const doNothing = () => {};
const someObj = {
  a: "ay",
  b: "bee",
  c: "si",
};

console.log(_thisIsUndefined); //logs undefined
console.log(doNothing()); //logs undefined
console.log(someObj["d"]); //logs undefined
```

- `null` là "một giá trị đại diện cho không có giá trị nào". `null` là giá trị đã được xác định rõ ràng cho một biến. Trong ví dụ sau, chúng ta nhận được giá trị `null` khi phương thức `fs.readFile` không báo lỗi.

```js
fs.readFile("path/to/file", (e, data) => {
  console.log(e); //it logs null when no error occurred
  if (e) {
    console.log(e);
  }
  console.log(data);
});
```

Khi so sánh `null` và `undefined`, chúng ta nhận được `true` khi sử dụng `==` và `false` khi sử dụng `===.` Bạn có thể đọc lý do [tại đây](#14-sự-khác-biệt-giữa--và--là-gì).

## 2. Toán tử `&&` dùng để làm gì?

Toán tử JavaScript gồm có các toán tử số học, các toán tử so sánh, toán tử logic và các toán tử với chuỗi ký tự.

Toán từ `&&` là một toán tử logic. Toán tử `&&` hoặc toán tử `AND` tìm biểu thức `falsy` đầu tiên trong các toán hạng của nó và trả về giá trị đó (`false`), nếu không tìm thấy bất kỳ biểu thức `falsy` nào, nó sẽ trả về `true`. Nó sử dụng `short-circuiting` để giảm thiểu các logic không cần thiết.

```js
console.log(false && 1 && []); //logs false
console.log(" " && true && 5); //logs 5
```

Sử dụng câu lệnh if.

```js
const router: Router = Router();

router.get("/endpoint", (req: Request, res: Response) => {
  let conMobile: PoolConnection;
  try {
    //do some db operations
  } catch (e) {
    if (conMobile) {
      conMobile.release();
    }
  }
});
```

Sử dụng toán tử `&&`.

```js
const router: Router = Router();

router.get("/endpoint", (req: Request, res: Response) => {
  let conMobile: PoolConnection;
  try {
    //do some db operations
  } catch (e) {
    conMobile && conMobile.release();
  }
});
```

## 3. Toán tử `||` dùng để làm gì??

Toán từ `||` là một toán tử logic. Toán tử `||` hoặc toán tử `OR` tìm biểu thức `truthy` đầu tiên trong các toán hạng của nó và trả về giá trị đó (`true`), hoặc nếu không tìm thấy bất kỳ biểu thức `truthy` nào, nó sẽ trả về `false`. Nó cũng sử dụng `short-circuiting` để giảm thiểu các logic không cần thiết.

Toán từ `||` được sử dụng trước đây để khởi tạo các giá trị tham số mặc định trước khi các tham số mặc định function của ES6 được hỗ trợ.

```js
console.log(null || 1 || undefined); //logs 1

function logName(name) {
  var n = name || "Mark";
  console.log(n);
}

logName(); //logs "Mark"
```

## 4. Sử dụng toán tử + hoặc toán tử cộng 1 ngôi (Unary) có phải là cách nhanh nhất để chuyển đổi một chuỗi thành một số không?

Theo [MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#Unary_plus), dấu `+` là cách nhanh nhất để chuyển đổi một chuỗi thành một số vì nó không thực hiện bất kỳ thao tác nào đối với giá trị nếu nó đã là một số.

## 5. DOM là gì ?

**DOM** là viết tắt của **Document Object Model** là một interface (**API**) cho các tài liệu HTML và XML. Khi trình duyệt lần đầu tiên đọc (phân tích cú pháp) tài liệu HTML, nó sẽ tạo ra một đối tượng lớn dựa trên tài liệu HTML gọi là **DOM**. Nó là một cấu trúc dạng cây được mô hình hóa từ tài liệu HTML. **DOM** được sử dụng để tương tác và sửa đổi **cấu trúc DOM** hoặc các phần tử (elements) hoặc nút (nodes) cụ thể.

Hãy tưởng tượng nếu chúng ta có một cấu trúc HTML như thế này.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Document Object Model</title>
  </head>

  <body>
    <div>
      <p>
        <span></span>
      </p>
      <label></label>
      <input />
    </div>
  </body>
</html>
```

**DOM** sẽ trông giống như thế này.

![Alt](https://res.cloudinary.com/practicaldev/image/fetch/s--z_mRQj0_--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/mbqphfbjfie45ynj0teo.png)

Đối tượng `document` trong JavaScript đại diện cho **DOM**. Nó cung cấp cho chúng ta nhiều phương thức để chọn các phần tử nhằm cập nhật nội dung phần tử và nhiều phương thức khác.

## 6. **Event Propagation** là gì?

Khi một **sự kiện** (event) xảy ra trên một phần tử (element) **DOM**, **sự kiện** đó không hoàn toàn xảy ra trên một phần tử đó. Trong **Bubbling Phase**, **sự kiện** nổi lên hoặc đi đến cha của nó, đến ông của nó, đến cha của ông nó =)) cho đến khi nó chạm tới `window` trong khi ở **Capturing Phase** , **sự kiện** bắt đầu từ `window` xuống đến phần tử đã kích hoạt **sự kiện** hoặc `event.target`.

**Event Propagation** có 3 giai đoạn (phases).

1. [**Capturing Phase**](#8-capturing-phase-là-gì) - sự kiện bắt đầu từ `window` sau đó đi xuống từng phần tử cho đến khi nó đến phần tử đích.

2. [**Target Phase**](#12-eventtarget-là-gì) - sự kiện đã đạt đến phần tử mục tiêu.

3. [**Bubbling Phase**](#7-event-bubbling-là-gì) - sự kiện nổi lên từ phần tử mục tiêu sau đó đi lên mọi phần tử cho đến khi nó đến `window`.

## 7. **Event Bubbling** là gì?

Khi một **sự kiện** (event) xảy ra trên một phần tử (element) **DOM**, **sự kiện** đó không hoàn toàn xảy ra trên một phần tử đó. Trong **Bubbling Phase**, **sự kiện** nổi lên hoặc đi đến cha của nó, đến ông của nó, đến cha của ông nó =)) cho đến khi nó chạm tới `window`.

Nếu chúng ta có một ví dụ như thế này.

```html
<div class="grandparent">
  <div class="parent">
    <div class="child">1</div>
  </div>
</div>
```

Và đây là code js.

```js
function addEvent(el, event, callback, isCapture = false) {
  if (!el || !event || !callback || typeof callback !== "function") return;
  if (typeof el === "string") {
    el = document.querySelector(el);
  }
  el.addEventListener(event, callback, isCapture);
}

addEvent(document, "DOMContentLoaded", () => {
  const child = document.querySelector(".child");
  const parent = document.querySelector(".parent");
  const grandparent = document.querySelector(".grandparent");

  addEvent(child, "click", function (e) {
    console.log("child");
  });

  addEvent(parent, "click", function (e) {
    console.log("parent");
  });

  addEvent(grandparent, "click", function (e) {
    console.log("grandparent");
  });

  addEvent(document, "click", function (e) {
    console.log("document");
  });

  addEvent("html", "click", function (e) {
    console.log("html");
  });

  addEvent(window, "click", function (e) {
    console.log("window");
  });
});
```

Phương thức `addEventListener` có tham số tùy chọn thứ ba `useCapture`, với giá trị mặc định là `false` sự kiện sẽ xảy ra trong **Bubbling phase**, nếu giá trị mặc định là `true` thì sự kiện sẽ xảy ra trong **Capturing Phase**. Nếu chúng ta nhấp vào phần tử `child` , nó sẽ ghi lại lần lượt các phần tử `child`, `parent`, `grandparent`, `html`, `document` và `window` trên console. Đây là **Event Bubbling**.

## 8. **Capturing Phase** là gì?

Khi một **sự kiện** (event) xảy ra trên một phần tử (element) **DOM**, **sự kiện** đó không hoàn toàn xảy ra trên một phần tử đó. Trong **Capturing Phase**, sự kiện bắt đầu từ `window` cho đến phần tử đã kích hoạt sự kiện.

Nếu chúng ta có một ví dụ như thế này.

```html
<div class="grandparent">
  <div class="parent">
    <div class="child">1</div>
  </div>
</div>
```

Và đây là code js.

```js
function addEvent(el, event, callback, isCapture = false) {
  if (!el || !event || !callback || typeof callback !== "function") return;
  if (typeof el === "string") {
    el = document.querySelector(el);
  }
  el.addEventListener(event, callback, isCapture);
}

addEvent(document, "DOMContentLoaded", () => {
  const child = document.querySelector(".child");
  const parent = document.querySelector(".parent");
  const grandparent = document.querySelector(".grandparent");

  addEvent(
    child,
    "click",
    function (e) {
      console.log("child");
    },
    true
  );

  addEvent(
    parent,
    "click",
    function (e) {
      console.log("parent");
    },
    true
  );

  addEvent(
    grandparent,
    "click",
    function (e) {
      console.log("grandparent");
    },
    true
  );

  addEvent(
    document,
    "click",
    function (e) {
      console.log("document");
    },
    true
  );

  addEvent(
    "html",
    "click",
    function (e) {
      console.log("html");
    },
    true
  );

  addEvent(
    window,
    "click",
    function (e) {
      console.log("window");
    },
    true
  );
});
```

Phương thức `addEventListener` có tham số tùy chọn thứ ba `useCapture`, với giá trị mặc định là `false` sự kiện sẽ xảy ra trong **Bubbling phase**, nếu giá trị mặc định là `true` thì sự kiện sẽ xảy ra trong **Capturing Phase**. Nếu chúng ta nhấp vào phần tử `child` , nó sẽ ghi lại lần lượt các phần tử `child`, `parent`, `grandparent`, `html`, `document` và `window` trên console. Đây là **Event Capturing**.

## 9. Sự khác biệt giữa phương thức `event.preventDefault()` và `event.stopPropagation()` là gì?

Phương thức `event.preventDefault()` **ngăn chặn** hành vi mặc định của một phần tử. Nếu được sử dụng trong một phần tử của `form`, phương thức này sẽ ngăn không cho nó submit. Nếu được sử dụng trong một phần tử `anchor` , phương thức này sẽ ngăn việc điều hướng. Nếu được sử dụng trong một `contextmenu` , phương thức này sẽ ngăn nó hiển thị hoặc hiển thị. Trong khi phương thức `event.stopPropagation()` dừng việc đề xuất một sự kiện hoặc nó dừng sự kiện xảy ra trong giai đoạn [bubbling](#7-event-bubbling-là-gì) hoặc [capturing](#8-capturing-phase-là-gì).

## 10. Làm thế nào để biết phương thức `event.preventDefault()` đã được sử dụng trong một phần tử hay chưa?

Chúng ta có thể sử dụng phương thức `event.defaultPrevented` trong `event` object. Nó trả về một `boolean` cho biết `event.preventDefault()` đã được gọi trong một phần tử cụ thể hay chưa.

## 11. Tại sao đoạn code `obj.someprop.x` lại gặp lỗi?

```js
const obj = {};
console.log(obj.someprop.x);
```

Rõ ràng, đoạn code trên gây ra lỗi vì chúng ta đang cố gắng truy cập thuộc tính `x` trong thuộc tính `someprop` có giá trị `undefined`. Hãy nhớ rằng các **thuộc tính** trong một đối tượng không tồn tại trong chính nó và **prototype** của nó có giá trị mặc định là `undefined` và `undefined` không có thuộc tính `x`.

## 12. `event.target` là gì?

Theo thuật ngữ đơn giản nhất, `event.target` là phần tử mà sự kiện **đã xảy ra** hoặc phần tử **đã kích hoạt** sự kiện.

Ví dụ trong HTML.

```html
<div
  onclick="clickFunc(event)"
  style="text-align: center;margin:15px;
border:1px solid red;border-radius:3px;"
>
  <div style="margin: 25px; border:1px solid royalblue;border-radius:3px;">
    <div style="margin:25px;border:1px solid skyblue;border-radius:3px;">
      <button style="margin:10px">Button</button>
    </div>
  </div>
</div>
```

Ví dụ trong Javascipt.

```js
function clickFunc(event) {
  console.log(event.target);
}
```

Nếu bạn click vào button, nó sẽ ghi lại đánh dấu button mặc dù chúng ta gán sự kiện trên thẻ `div` ngoài cùng, nó sẽ luôn ghi lại button để chúng ta có thể kết luận rằng `event.target` là phần tử đã kích hoạt sự kiện.

## 13. `event.currentTarget` là gì?

`event.currentTarget` là phần tử mà chúng ta gán trình xử lý sự kiện **một cách rõ ràng**.

Sao chép phần code HTML trong Câu hỏi 12.

```html
<div
  onclick="clickFunc(event)"
  style="text-align: center;margin:15px;
border:1px solid red;border-radius:3px;"
>
  <div style="margin: 25px; border:1px solid royalblue;border-radius:3px;">
    <div style="margin:25px;border:1px solid skyblue;border-radius:3px;">
      <button style="margin:10px">Button</button>
    </div>
  </div>
</div>
```

Và thay đổi code JS một chút.

```js
function clickFunc(event) {
  console.log(event.currentTarget);
}
```

Nếu bạn click vào button, nó sẽ ghi lại đánh dấu thẻ `div` ngoài cùng ngay cả khi chúng ta click vào button. Trong ví dụ này, chúng ta có thể kết luận rằng `event.currentTarget` là phần tử mà chúng ta gán trình xử lý sự kiện.

## 14. Sự khác biệt giữa == và === là gì?

Sự khác biệt giữa `==` (so sánh trừu tượng / abstract equality) và `===` (so sánh nghiêm ngặt / strict equality) là `==` so sánh theo giá trị sau khi ép kiểu và `===` so sánh theo giá trị và kiểu.

Giả sử chúng ta so sánh giá trị `x` và `y` bằng phép `==`.

1. Nếu `x` và `y` có cùng kiểu. Sau đó so sánh chúng bằng toán tử `===`.
2. Nếu `x` là `null` và `y` là `undefined` thì trả về `true`.
3. Nếu `x` là `undefined` và `y` là `null` thì trả về `true`.
4. Nếu `x` là `number` và `y` là `string` sau đó trả về `x == toNumber(y)`.
5. Nếu `x` là `string` và `y` là `number` sau đó trả về `toNumber(x) == y`.
6. Nếu `x` là `boolean` sau đó trả về `toNumber(x) == y`.
7. Nếu `y` là `boolean` sau đó trả về `x == toNumber(y)`.
8. Nếu `x` là `string`, `symbol` hoặc `number` và `y` là `object` thì trả về `x == toPrimitive(y)`.
9. Nếu `x` là `object`, `y` là `string` hoặc `symbol` thì trả về `toPrimitive(x) == y`.
10. Trả về `false`.

> Lưu ý: `toPrimitive` sử dụng phương thức `valueOf` sau đó là phương thức `toString` trong các đối tượng để lấy giá trị nguyên thủy của đối tượng đó.

Chúng ta có các ví dụ sau:

| `x`               | `y`       | `x==y` |
| ----------------- | --------- | ------ |
| 5                 | 5         | true   |
| 1                 | '1'       | true   |
| null              | undefined | true   |
| 0                 | false     | true   |
| '1,2'             | [1,2]     | true   |
| '[object Object]' | {}        | true   |

Tất cả các ví dụ trên đều trả về `true`.

- Ví dụ 1 chuyển sang điều kiện 1. vì `x` và `y` có cùng kiểu và giá trị.
- Ví dụ 2 chuyển sang điều kiện 4. vì `y` được convert thành `number` trước khi so sánh.
- Ví dụ 3 chuyển sang điều kiện 2.
- Ví dụ 4 chuyển sang điều kiện 7. vì `y` là `boolean`.
- Ví dụ 5 chuyển sang điều kiện 8. Mảng được chuyển đổi thành chuỗi bằng phương thức `toString()` và trả về 1,2.
- Ví dụ 6 chuyển sang điều kiện 1o. Đối tượng được chuyển đổi thành một chuỗi bằng cách sử dụng phương thức `toString()` trả về `[object Object]`.

| `x`               | `y`       | `x===y` |
| ----------------- | --------- | ------- |
| 5                 | 5         | true    |
| 1                 | '1'       | false   |
| null              | undefined | false   |
| 0                 | false     | false   |
| '1,2'             | [1,2]     | false   |
| '[object Object]' | {}        | false   |

Nếu chúng ta sử dụng toán tử `===,` tất cả các phép so sánh ngoại trừ ví dụ đầu tiên sẽ trả về `false` vì chúng không có cùng kiểu trong khi ví dụ đầu tiên sẽ trả về `true` vì cả hai có cùng kiểu và giá trị.

## 2. Link tham khảo

https://dev.to/macmacky/70-javascript-interview-questions-5gfi
