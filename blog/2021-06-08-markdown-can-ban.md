---
title: Cú pháp Markdown căn bản
author: Trịnh Đình Tài
author_title: Admin
author_url: https://github.com/taitd2610
author_image_url: https://scontent-sin6-1.xx.fbcdn.net/v/t1.6435-9/36756866_226907771464364_2771393154585198592_n.jpg?_nc_cat=101&ccb=1-3&_nc_sid=09cbfe&_nc_ohc=MGgQs4UzM5EAX-5FQaR&_nc_ht=scontent-sin6-1.xx&oh=24342e3e97bc53311a628434d6667de7&oe=60DCA347
tags: [JavaScript]
description: This is my first post on Docusaurus 2.
image: https://i.imgur.com/mErPwqL.png
hide_table_of_contents: false
sidebar_label: "Xin chào"
sidebar_position: 1
slug: /cu-phap-markdown-can-ban
---

![Alt](https://hugoloveit.com/basic-markdown-syntax/featured-image.png)

## 0. Tổng quan

Markdown là ngôn ngữ đánh dấu được John Gruber tạo ra vào năm 2004. Markdown sử dụng cú pháp khá đơn giản và dễ hiểu để đánh dấu văn bản, tạo thuận tiện cho việc chuyển đổi từ văn bản thuần sang HTML. Thay vì dựa vào HTML hoặc các trình soạn thảo WYSIWYG, Markdown cho phép bạn định dạng văn bản mà không cần rời tay ra khỏi bàn phím, điều đó trực quan hơn nhiều so với HTML.

Thêm nữa, Markdown ngắn gọn và dễ hiểu hơn nhiều, bạn không cần phải biết về HTML cũng có thể sử dụng được Markdown đơn giản. Vậy còn chần chừ gì mà không theo dõi bảng tổng hợp các cú pháp cơ bản để có thể thông thạo việc sử dụng Markdown ngay bây giờ nhỉ?

## 1. Tiêu đề - Heading

Để tạo tiêu đề - heading h1, h2, h3 cho đến h6, thêm số lượng ký tự # tương ứng vào đầu dòng. Số lượng # bạn sử dụng tương ứng với cấp độ tiêu đề, một ký tự # tương đương với h1, 2 ký tự # tương đương với h2... Ví dụ: để tạo tiêu đề cấp ba (h3), sử dụng ba ký hiệu # (ví dụ: ### Tiêu đề).

| Markdown              | HTML                                | Rendered Output            |
| --------------------- | ----------------------------------- | -------------------------- |
| # Heading level 1     | &lt;h1&gt;Heading level 1&lt;/h1&gt | <h1> Heading level 1 </h1> |
| ## Heading level 2    | &lt;h1&gt;Heading level 2&lt;/h1&gt | <h2> Heading level 2 </h2> |
| ### Heading level 3   | &lt;h1&gt;Heading level 3&lt;/h1&gt | <h3> Heading level 3 </h3> |
| #### Heading level 4  | &lt;h1&gt;Heading level 4&lt;/h1&gt | <h4> Heading level 4 </h4> |
| ##### Heading level 5 | &lt;h1&gt;Heading level 5&lt;/h1&gt | <h5> Heading level 5 </h5> |
| ##### Heading level 6 | &lt;h1&gt;Heading level 6&lt;/h1&gt | <h6> Heading level 6 </h6> |

## 2. Đoạn văn - Paragraph

Để tạo các đoạn văn, sử dụng một dòng trống để tách các dòng văn bản. Bạn không nên thụt lề các đoạn bằng dấu cách hoặc tab.

| Markdown | HTML | Rendered Output |
| -------- | ---- | --------------- |

| # I really like using Markdown. | &lt;h1&gt;Heading level 1&lt;/h1&gt | <h1> Heading level 1 </h1> |

1. In đậm chữ - Bold
   Để in đậm văn bản, thêm hai dấu hoa thị hoặc dấu gạch dưới trước và sau một từ hoặc cụm từ. Để in đậm chữ cái nằm giữa một từ để nhấn mạnh, thêm hai dấu sao trước và sau các chữ cái (không sử dụng space).

Markdown HTML Output
Website **QTM**. Website <strong>QTM</strong>. Website QTM
Website **QTM**. Website <strong>QTM</strong>. Website QTM
**quantrimang**.com <strong>quantrimang</strong>.com quantrimang.com 4. In nghiêng - Italic
Để in nghiêng văn bản, thêm một dấu hoa thị hoặc gạch dưới trước và sau một từ hoặc cụm từ. Để in nghiêng chữ cái nằm giữa một từ để nhấn mạnh, thêm một dấu sao trước và sau các chữ cái (không sử dụng space).

Markdown HTML Output
Hàm _int()_ trong Python trả về một đối tượng số nguyên từ bất kỳ số hoặc chuỗi nào. Hàm <em>int()</em> trong Python trả về một đối tượng số nguyên từ bất kỳ số hoặc chuỗi nào. Hàm int() trong Python trả về một đối tượng số nguyên từ bất kỳ số hoặc chuỗi nào.
Hàm _int()_ trong Python trả về một đối tượng số nguyên từ bất kỳ số hoặc chuỗi nào. Hàm <em>int()</em> trong Python trả về một đối tượng số nguyên từ bất kỳ số hoặc chuỗi nào. Hàm int() trong Python trả về một đối tượng số nguyên từ bất kỳ số hoặc chuỗi nào..
Quan*tri*mang Quan<em>tri</em>mang Quantrimang
