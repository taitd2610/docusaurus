---
title: Tìm hiểu về Object Destructuring trong ES6
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
slug: /tim-hieu-ve-object-destructuring-trong-es6
---

![Alt](https://miro.medium.com/max/3564/1*I_tLXChoCNAbQzVnUifILg.png)

***Object destructuring*** là một tính năng JavaScript hữu ích để trích xuất các thuộc tính từ các đối tượng và gán chúng cho các biến riêng biệt.  

Hơn nữa, ***object destructuring*** có thể trích xuất nhiều thuộc tính trong một câu lệnh, có thể truy cập thuộc tính từ các đối tượng lồng nhau và có thể đặt giá trị mặc định nếu thuộc tính không tồn tại. 

<!--truncate-->

Thông thường, chúng ta sẽ truy cập các đối tượng bằng key. Như thế này.  

```
object.key
```

Hãy xem nhanh ví dụ dưới đây:  

```js
// object (Literal)
var user = {
    name: "Hidayt",
    city: "Delhi",
    type: "Admin"
}
console.log(user.name); // Hidayt
```

Chúng ta có một đối tượng `user` chứa thông tin `user` (tên, thành phố, loại). Chúng ta sẽ sử dụng ví dụ này để tìm hiểu về object destructuring.

## Object destructuring

![Alt](https://miro.medium.com/max/700/1*f0chEeG4RhjGiMgihO2N6A.png)

Hãy sử dụng object destructuring để gán đối tượng thành các biến.  

```js
// object destructuring
var {name, city, type} = user;
// access as a normal variable
console.log(name); // Hidayt
console.log(city); // Delhi
console.log(type); // Admin
```

Bạn có thể truy cập trực tiếp vào `name` thay vì `user.name`  

> Bây giờ biến `name` có thể được truy cập như một biến bình thường.  

Trên đây mình đã giới thiệu về cú pháp về object destructuring. Mình mong là bài viết của mình sẽ giúp bạn hiểu hơn về object destructuring và sử dụng tính năng này trong code của mình.

Via: https://hidaytrahman.medium.com/object-destructuring-in-javascript-feb8bd425bd8

