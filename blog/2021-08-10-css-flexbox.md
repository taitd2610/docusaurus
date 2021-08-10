---
title: Hướng dẫn đầy đủ về Flexbox
author: Trịnh Đình Tài
author_title: Admin
author_image_url: https://scontent-hkt1-1.xx.fbcdn.net/v/t1.6435-9/36756866_226907771464364_2771393154585198592_n.jpg?_nc_cat=101&ccb=1-3&_nc_sid=09cbfe&_nc_ohc=oQWlAyKcdyQAX_CL9Mj&_nc_ht=scontent-hkt1-1.xx&oh=b635b50219d2e77f2a98ee24f7cab44c&oe=611FDFC7
tags: [CSS]
description: This is my first post on Docusaurus 2.
image: https://i.imgur.com/mErPwqL.png
hide_table_of_contents: false
sidebar_label: "Xin chào"
sidebar_position: 1
slug: /flexbox-cheat-sheets-in-2021-css-2021
---

![Alt](https://res.cloudinary.com/practicaldev/image/fetch/s--QhWoPnGt--/c_imagga_scale,f_auto,fl_progressive,h_420,q_auto,w_1000/https://dev-to-uploads.s3.amazonaws.com/i/stjkq1bup9n640weob7a.png)

Đây là một hướng dẫn về mọi thứ bạn có thể làm với CSS flexbox. Đi thôi 🎖️

<!--truncate-->

## 0. Contents

- [0. Contents](#0-contents)
- [1. Flexbox là gì thế ?](#1-flexbox-là-gì-thế-)
- [2. Kiến trúc Flexbox](#2-kiến-trúc-flexbox)
- [3. Biểu đồ Flexbox](#3-biểu-đồ-flexbox)
- [4. Cách thiết lập dự án](#4-cách-thiết-lập-dự-án)
  - [4.1. HTMl](#41-html)
  - [4.2. CSS](#42-css)
- [5. `flex-direction`](#5-flex-direction)
- [6. `justify-content`](#6-justify-content)
- [7. `align-content`](#7-align-content)
- [8. `align-items`](#8-align-items)
- [Link tham khảo:](#link-tham-khảo)

![Alt](https://res.cloudinary.com/practicaldev/image/fetch/s--0D9b5bgs--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/8dj24bi57fyi3qv21u8e.png)

## 1. Flexbox là gì thế ?

Khi bạn đang xây dựng một ngôi nhà, bạn cần một bản thiết kế. Theo cách tương tự, chúng ta cần một bản thiết kế chi tiết khi chúng ta tạo ra các trang web. Và Flexbox chính là bản thiết kế đấy.

Flexbox cho phép chúng ta **bố trí nội dung** trang web của mình. Không chỉ vậy, nó giúp chúng ta tạo ra các cấu trúc cần thiết cho việc tạo các trang web `responsive` cho nhiều thiết bị.

Đây là bản demo mà tôi đã tạo bằng Flexbox làm bản thiết kế chính.

![Alt](https://www.freecodecamp.org/news/content/images/2021/04/Frame-35--1-.png)

## 2. Kiến trúc Flexbox

Vậy kiến ​​trúc Flexbox hoạt động như thế nào? Các flex-items [Contents] được phân phối dọc theo trục chính (main axis) và trục dọc (cross axis). Và tùy thuộc vào thuộc tính `flex-direction`, vị trí layout sẽ thay đổi giữa các hàng và cột.

![Alt](https://dev-to-uploads.s3.amazonaws.com/i/hy2oqjvsbk60ef92nktg.png)

## 3. Biểu đồ Flexbox

Biểu đồ này chứa mọi thuộc tính và giá trị có thể có mà bạn có thể sử dụng khi sử dụng flexbox. Bạn có thể tham khảo nó trong khi thực hiện dự án và thử nghiệm với các giá trị khác nhau.

![Alt](https://res.cloudinary.com/practicaldev/image/fetch/s--NBPSPt0K--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/gv3jyh4xt4fbwtq1qejn.png)

Đơn giản chỉ tạo một grid element không giúp bạn tiến xa. Bạn cũng cần xác định cấu trúc của grid. Để thêm một số cột vào grid, hãy sử dụng thuộc tính `grid-template-columns` trong grid container như sau:

## 4. Cách thiết lập dự án

Đối với dự án này, bạn cần biết một chút về HTML, CSS và cách làm việc với VS Code. Cùng mình theo dõi nhé ->

1. Tạo một thư mục có tên "Project-1" & Mở VS Code
2. Tạo tệp index.html & style.css
3. Cài đặt extension Live Server & chạy Live Server.

Hoặc, bạn có thể thực hành với [Codepen](https://codepen.io/). Ở cuối hướng dẫn này, bạn có thể tạo bố cục trang web chính xác hơn.

### 4.1. HTMl

Trong file `index.html`, hãy viết đoạn code sau trong thẻ `body`

```html title="index.html"
<div class="container">
  <div class="box-1">A</div>
  <div class="box-2">B</div>
  <div class="box-3">C</div>
</div>
```

### 4.2. CSS

Style cho các box ở trên, như thế này:

> Lưu ý: đừng quên đặt chiều cao của container.

```css
.container {
  height: 100vh;
}

[class^="box-"] {
  width: 140px;
  height: 140px;
  background-color: skyblue;
  border: 2px solid black;

  // To view the letter better
  font-size: 65px;
}
```

But Wait.... Trước khi bắt đầu, bạn cần hiểu mối quan hệ giữa lớp cha và con.

![Alt](https://res.cloudinary.com/practicaldev/image/fetch/s--yNcmAvd6--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/wzq3w0bys78fveqb9z0z.png)

Flexbox hoạt động trên **lớp cha**, không hoạt động trên **lớp con**.

Ở đây, lớp `.container` là **lớp cha** và các lớp `.box-` là **lớp con** của chúng.

Vì vậy, hãy áp dụng `display: flex` bên trong lớp `.container`. Và đặt đoạn code bên dưới ở giữa lớp `.box` như thế này ->

```css
.container {
  display: flex;
  height: 100vh;

  // To place some gap between boxes
  gap: 25px;
}

[class^="box-"] {
  // Code from previous step are here

  // Placing text at center
  display: flex;
  justify-content: center;
  align-items: center;
}
```

Và .... chúng ta đã sẵn sàng! Let's start coding.

## 5. `flex-direction`

Direction / Orientation trong đó các flex-item được phân phối bên trong flex-container.

![Alt](https://res.cloudinary.com/practicaldev/image/fetch/s--dSPKucCl--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/n2ggh6yy4sbgltrx2i40.png)

![Alt](https://res.cloudinary.com/practicaldev/image/fetch/s--HDcNQB2s--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/6m9fg4n5a114q1va3b9p.png)

Để tạo lại những kết quả này, hãy viết CSS như sau.

> Lưu ý: Chúng ta sẽ viết bên trong lớp `.container`

```css
.container {
  //code from setup stage are here

  // Change the value  👇 here to see results
  flex-direction: row;
}
```

## 6. `justify-content`

Thuộc tính này sắp xếp các flex-item dọc theo TRỤC CHÍNH (MAIN AXIS) bên trong flex-container.

![Alt](https://res.cloudinary.com/practicaldev/image/fetch/s--ODoBQ_kH--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/a5lhkhbhi7hxwjgyvl5x.png)

![Alt](https://res.cloudinary.com/practicaldev/image/fetch/s--h8AhHloo--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/1vyg5nf1w7plistni582.png)

Để tạo lại những kết quả này, hãy viết CSS như sau.

> Lưu ý: Chúng ta sẽ viết bên trong lớp `.container`

```css
.container {
  //code from setup stage are here

  //  Change the value  👇 here to see results
  justify-content: flex-start;
}
```

## 7. `align-content`

Thuộc tính này sắp xếp các flex-items dọc theo TRỤC DỌC (CROSS AXIS) bên trong flex-container. Điều này tương tự với `justify-content`

![Alt](https://res.cloudinary.com/practicaldev/image/fetch/s--rb2GSkzz--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/nqvvc2rhf0vx3czy0rnr.png)

![Alt](https://res.cloudinary.com/practicaldev/image/fetch/s--kat1xDe2--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/zeet3705rsmz77v66x3c.png)

Xin lưu ý rằng, nếu không có thuộc tính `flex-wrap`, thuộc tính này không hoạt động, đây là bản demo.

```css
.container {
  //  Change the value  👇 here to see results
  align-content: center;

  // without this line, align-content won't work
  flex-wrap: wrap;
}
```

## 8. `align-items`

Thuộc tính này phân phối các flex-items dọc theo TRỤC DỌC (CROSS AXIS).

![Alt](https://res.cloudinary.com/practicaldev/image/fetch/s--sjVrjCiy--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/kt25wxicd7vm8ddtmq0l.png)

Để tạo lại những kết quả này, hãy viết CSS như sau.

```css
.container {
  //code from setup stage are here

  // Change the value 👇 here to see results
  align-items: flex-end;
}
```

## Link tham khảo:

https://dev.to/joyshaheb/flexbox-cheat-sheets-in-2021-css-2021-3edl
