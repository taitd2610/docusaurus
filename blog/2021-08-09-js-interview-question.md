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
- [2. Sự khác biệt giữa undefined và null là gì ?](#2-sự-khác-biệt-giữa-undefined-và-null-là-gì-)

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

- Chúng là những giá trị **falsy**. Các giá trị được đánh giá thành false khi chuyển đổi nó thành boolean bằng cách sử dụng Boolean (value) hoặc !!

## 2. Sự khác biệt giữa undefined và null là gì ?
