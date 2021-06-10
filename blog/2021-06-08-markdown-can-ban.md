---
title: Cú pháp Markdown căn bản
author: Trịnh Đình Tài
author_title: Admin
author_url: https://github.com/taitd2610
author_image_url: https://scontent-sin6-1.xx.fbcdn.net/v/t1.6435-9/36756866_226907771464364_2771393154585198592_n.jpg?_nc_cat=101&ccb=1-3&_nc_sid=09cbfe&_nc_ohc=MGgQs4UzM5EAX-5FQaR&_nc_ht=scontent-sin6-1.xx&oh=24342e3e97bc53311a628434d6667de7&oe=60DCA347
tags: [Markdown]
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
| # Heading level 1     | &lt;h1&gt;Heading level 1&lt;/h1&gt; | <h1> Heading level 1 </h1> |
| ## Heading level 2    | &lt;h1&gt;Heading level 2&lt;/h1&gt; | <h2> Heading level 2 </h2> |
| ### Heading level 3   | &lt;h1&gt;Heading level 3&lt;/h1&gt; | <h3> Heading level 3 </h3> |
| #### Heading level 4  | &lt;h1&gt;Heading level 4&lt;/h1&gt; | <h4> Heading level 4 </h4> |
| ##### Heading level 5 | &lt;h1&gt;Heading level 5&lt;/h1&gt; | <h5> Heading level 5 </h5> |
| ##### Heading level 6 | &lt;h1&gt;Heading level 6&lt;/h1&gt; | <h6> Heading level 6 </h6> |

## 2. Đoạn văn - Paragraph

Để tạo các đoạn văn, sử dụng một dòng trống để tách các dòng văn bản. Bạn không nên thụt lề các đoạn bằng dấu cách hoặc tab.

| Markdown              | HTML                                | Rendered Output            |
| --------------------- | ----------------------------------- | -------------------------- |
| I really like using Markdown.<br></br><br></br>I think I'll use it to format all of my documents from now on.     | &lt;p&gt;I really like using Markdown.&lt;/p&gt<br></br><br></br>&lt;p&gt;I think I'll use it to format all of my documents from now on.&lt;/p&gt; | I really like using Markdown.<br></br><br></br>I think I'll use it to format all of my documents from now on. |

## 3. Nhấn mạnh (Emphasis)

### 3.1. In đậm chữ - Bold
Để in đậm văn bản, thêm hai dấu hoa thị hoặc dấu gạch dưới trước và sau một từ hoặc cụm từ. Để in đậm chữ cái nằm giữa một từ để nhấn mạnh, thêm hai dấu sao trước và sau các chữ cái (không sử dụng space).

| Markdown              | HTML                                | Rendered Output            |
| --------------------- | ----------------------------------- | -------------------------- |
| Tài &#42;&#42;đẹp trai&#42;&#42;.     | Tài &lt;strong&gt;đẹp trai&lt;/strong&gt;. | Tài **đẹp trai**. |
| Tài &#95;&#95;đẹp trai&#95;&#95;.    | Tài &lt;strong&gt;đẹp trai&lt;/strong&gt;. | Tài **đẹp trai**. |
| Tài&#42;&#42;đẹp&#42;&#42;trai.    | Tài&lt;strong&gt;đẹp&lt;/strong&gt;trai. | Tài**đẹp**trai. |
 
### 3.2. In nghiêng - Italic
Để in nghiêng văn bản, thêm một dấu hoa thị hoặc gạch dưới trước và sau một từ hoặc cụm từ. Để in nghiêng chữ cái nằm giữa một từ để nhấn mạnh, thêm một dấu sao trước và sau các chữ cái (không sử dụng space).

| Markdown              | HTML                                | Rendered Output            |
| --------------------- | ----------------------------------- | -------------------------- |
| Việt Nam &#42;vô địch&#42;.     | Việt Nam &lt;em&gt;vô địch&lt;/em&gt;. | Việt Nam *vô địch*. |
| Việt Nam &#95;vô địch&#95;.     | Việt Nam &lt;em&gt;vô địch&lt;/em&gt;. | Việt Nam *vô địch*. |
| ViệtNam&#42;vôđịch&#42;.     | ViệtNam&lt;em&gt;vôđịch&lt;/em&gt;. | ViệtNam*vôđịch*. |

### 3.3. In đậm và in nghiêng
Để nhấn mạnh văn bản bằng chữ in đậm và in nghiêng cùng một lúc, thêm ba dấu hoa thị hoặc ba dấu gạch dưới trước và sau một từ hoặc cụm từ.

| Markdown              | HTML                                | Rendered Output            |
| --------------------- | ----------------------------------- | -------------------------- |
| Build &#42;&#42;&#42;A Bitch&#42;&#42;&#42;.     | Build &lt;strong&gt;&lt;em&gt;A Bitch&gt;&lt;/strong&gt;&lt;/em&gt;. | Build ***A Bitch***. |
| Build &#95;&#95;&#95;A Bitch&#95;&#95;&#95;.     | Build &lt;strong&gt;&lt;em&gt;A Bitch&gt;&lt;/strong&gt;&lt;/em&gt;. | Build ***A Bitch***. |
| Build &#95;&#95;&#42;A Bitch;&#42;&#95;&#95;.     | Build &lt;strong&gt;&lt;em&gt;A Bitch&gt;&lt;/strong&gt;&lt;/em&gt;. | Build ***A Bitch***. |
| Build &#42;&#42;&#95;A Bitch&#95;&#42;&#42;.     | Build &lt;strong&gt;&lt;em&gt;A Bitch&gt;&lt;/strong&gt;&lt;/em&gt;. | Build ***A Bitch***. |
| Build&#42;&#42;&#42;ABitch&#42;&#42;&#42;.     | Build&lt;strong&gt;&lt;em&gt;ABitch&gt;&lt;/strong&gt;&lt;/em&gt;. | Build***ABitch***. |

## 4. Trích dẫn - Blockquote
Để tạo một blockquote, hãy thêm dấu > vào trước đoạn văn.

    > Em thấy gì trong đôi mắt kẻ tương tư, một đống code hư sau những đêm không ngủ...

Output hiển thị như này:

> Em thấy gì trong đôi mắt kẻ tương tư, một đống code hư sau những đêm không ngủ...

### 4.1 Blockquote có nhiều đoạn

Blockquote có thể chứa nhiều đoạn. Thêm > vào các dòng trống giữa các đoạn.

    > Có một cái cây trong một cái vườn  
    > Trên những tán cây nở rộ những đóa hoa  
    > 
    > Có hai đứa nhóc đang chơi trốn tìm  
    > Tìm hoài tìm mãi nên quên lối về.  

Output hiển thị như này:
> Có một cái cây trong một cái vườn  
> Trên những tán cây nở rộ những đóa hoa  
> 
> Có hai đứa nhóc đang chơi trốn tìm  
> Tìm hoài tìm mãi nên quên lối về.  

### 4.2 Blockquote lồng nhau

Blockquote có thể được lồng trong một Blockquote khác. Thêm dấu >> ở phía trước đoạn bạn muốn lồng.

    > Trốn Tìm - Đen; MTV
    >> Anh đi tìm thì em trốn, anh đi trốn em không tìm  
    >> Lòng em không gợn sóng, cuối cùng anh mất công chìm  
    >> Nếu mà có cây búa anh sẽ nện cho bõ công  
    >> Vì nhớ nhung đặc quánh giờ nó khô thành bê tông   

Output hiển thị như này:
> Trốn Tìm - Đen; MTV
>> Anh đi tìm thì em trốn, anh đi trốn em không tìm  
>> Lòng em không gợn sóng, cuối cùng anh mất công chìm  
>> Nếu mà có cây búa anh sẽ nện cho bõ công  
>> Vì nhớ nhung đặc quánh giờ nó khô thành bê tông  

### 4.3 Blockquote bao gồm các yếu tố khác
Blockquote có thể chứa các yếu tố định dạng Markdown khác. Tuy nhiên, không phải tất cả các yếu tố đều có thể sử dụng được, vậy nên bạn cần thử nghiệm để xem định dạng nào sẽ hoạt động.

> #### ĐÂY THÔN VĨ DẠ
>
> - Sao anh không về chơi *thôn vĩ*
> - Nhìn nắng hàng cau nắng **mới lên**
> - Vườn ai mướt quá xanh ***như ngọc*** 
> - Lá trúc chen ngang mặt chữ điền

## 5. Danh sách
Bạn có thể sử dụng Markdown để định dạng sắp xếp các mục vào danh sách theo thứ tự hoặc không theo thứ tự.

### 5.1. Danh sách có thứ tự
Để tạo danh sách có thứ tự, bạn chỉ cần thêm các các số theo sau là dấu chấm trước nội dung muốn tạo. Các số không nhất thiết phải theo thứ tự 1 2 3 4 lần lượt, nhưng bạn nên bắt đầu bằng số một.

| Markdown              | HTML                                | Rendered Output            |
| --------------------- | ----------------------------------- | -------------------------- |
| 1. Mục thứ nhất<br/>2. Mục thứ hai<br/>3. Mục thứ ba<br/>4. Mục thứ tư    |  &lt;ol&gt;<br></br>&lt;li&gt;Mục thứ nhất&lt;/li&gt;<br/>&lt;li&gt;Mục thứ hai&lt;/li&gt;<br/>&lt;li&gt;Mục thứ ba&lt;/li&gt;<br/>&lt;li&gt;Mục thứ tư&lt;/li&gt;<br/>&lt;/ol&gt; | <ol><li>Mục thứ nhất</li><li>Mục thứ hai</li><li>Mục thứ ba</li><li>Mục thứ tư</li></ol> |
| 1. Mục thứ nhất<br/>1. Mục thứ hai<br/>1. Mục thứ ba<br/>1. Mục thứ tư    |  &lt;ol&gt;<br></br>&lt;li&gt;Mục thứ nhất&lt;/li&gt;<br/>&lt;li&gt;Mục thứ hai&lt;/li&gt;<br/>&lt;li&gt;Mục thứ ba&lt;/li&gt;<br/>&lt;li&gt;Mục thứ tư&lt;/li&gt;<br/>&lt;/ol&gt; | <ol><li>Mục thứ nhất</li><li>Mục thứ hai</li><li>Mục thứ ba</li><li>Mục thứ tư</li></ol> |
| 1. Mục thứ nhất<br/>8. Mục thứ hai<br/>3. Mục thứ ba<br/>5. Mục thứ tư    |  &lt;ol&gt;<br></br>&lt;li&gt;Mục thứ nhất&lt;/li&gt;<br/>&lt;li&gt;Mục thứ hai&lt;/li&gt;<br/>&lt;li&gt;Mục thứ ba&lt;/li&gt;<br/>&lt;li&gt;Mục thứ tư&lt;/li&gt;<br/>&lt;/ol&gt; | <ol><li>Mục thứ nhất</li><li>Mục thứ hai</li><li>Mục thứ ba</li><li>Mục thứ tư</li></ol> |
| 1. Mục thứ nhất<br/>2. Mục thứ hai<br/>3. Mục thứ ba<br/>&nbsp;&nbsp;&nbsp;&nbsp;1. Mục phụ 1<br/>&nbsp;&nbsp;&nbsp;&nbsp;2. Mục phụ 2<br/>4. Mục thứ tư    |  &lt;ol&gt;<br></br>&lt;li&gt;Mục thứ nhất&lt;/li&gt;<br/>&lt;li&gt;Mục thứ hai&lt;/li&gt;<br/>&lt;li&gt;Mục thứ ba&lt;/li&gt;<br/>&lt;ol&gt;<br></br>&lt;li&gt;Mục phụ 1&lt;/li&gt;<br/>&lt;li&gt;Mục phụ 2&lt;/li&gt;<br/>&lt;/ol&gt;<br/>&lt;li&gt;Mục thứ tư&lt;/li&gt;<br/>&lt;/ol&gt; | <ol><li>Mục thứ nhất</li><li>Mục thứ hai</li><li>Mục thứ ba</li><ol><li>Mục phụ 1</li><li>Mục phụ 2</li></ol><li>Mục thứ tư</li></ol> |  

### 5.2. Danh sách không có thứ tự
Để định đạng danh sách có các gạch đầu dòng trong Markdown, bạn dùng kí tự dấu gạch ngang -, dấu hoa thị * hoặc dấu cộng + và một dấu cách trước nội dung muốn tạo, dùng thêm 2 dấu cách ở đằng trước nếu muốn lùi vào một level.

| Markdown              | HTML                                | Rendered Output            |
| --------------------- | ----------------------------------- | -------------------------- |
| - Mục thứ nhất<br/>- Mục thứ hai<br/>- Mục thứ ba<br/>- Mục thứ tư    |  &lt;ul&gt;<br></br>&lt;li&gt;Mục thứ nhất&lt;/li&gt;<br/>&lt;li&gt;Mục thứ hai&lt;/li&gt;<br/>&lt;li&gt;Mục thứ ba&lt;/li&gt;<br/>&lt;li&gt;Mục thứ tư&lt;/li&gt;<br/>&lt;/ul&gt; | <ul><li>Mục thứ nhất</li><li>Mục thứ hai</li><li>Mục thứ ba</li><li>Mục thứ tư</li></ul> |
| &#42; Mục thứ nhất<br/>&#42; Mục thứ hai<br/>&#42; Mục thứ ba<br/>&#42; Mục thứ tư    |  &lt;ul&gt;<br></br>&lt;li&gt;Mục thứ nhất&lt;/li&gt;<br/>&lt;li&gt;Mục thứ hai&lt;/li&gt;<br/>&lt;li&gt;Mục thứ ba&lt;/li&gt;<br/>&lt;li&gt;Mục thứ tư&lt;/li&gt;<br/>&lt;/ul&gt; | <ul><li>Mục thứ nhất</li><li>Mục thứ hai</li><li>Mục thứ ba</li><li>Mục thứ tư</li></ul> |
| 1. Mục thứ nhất<br/>8. Mục thứ hai<br/>3. Mục thứ ba<br/>5. Mục thứ tư    |  &lt;ul&gt;<br></br>&lt;li&gt;Mục thứ nhất&lt;/li&gt;<br/>&lt;li&gt;Mục thứ hai&lt;/li&gt;<br/>&lt;li&gt;Mục thứ ba&lt;/li&gt;<br/>&lt;li&gt;Mục thứ tư&lt;/li&gt;<br/>&lt;/ul&gt; | <ul><li>Mục thứ nhất</li><li>Mục thứ hai</li><li>Mục thứ ba</li><li>Mục thứ tư</li></ul> |
| 1. Mục thứ nhất<br/>2. Mục thứ hai<br/>3. Mục thứ ba<br/>&nbsp;&nbsp;&nbsp;&nbsp;1. Mục phụ 1<br/>&nbsp;&nbsp;&nbsp;&nbsp;2. Mục phụ 2<br/>4. Mục thứ tư    |  &lt;ul&gt;<br></br>&lt;li&gt;Mục thứ nhất&lt;/li&gt;<br/>&lt;li&gt;Mục thứ hai&lt;/li&gt;<br/>&lt;li&gt;Mục thứ ba&lt;/li&gt;<br/>&lt;ul&gt;<br></br>&lt;li&gt;Mục phụ 1&lt;/li&gt;<br/>&lt;li&gt;Mục phụ 2&lt;/li&gt;<br/>&lt;/ul&gt;<br/>&lt;li&gt;Mục thứ tư&lt;/li&gt;<br/>&lt;/ul&gt; | <ul><li>Mục thứ nhất</li><li>Mục thứ hai</li><li>Mục thứ ba</li><ul><li>Mục phụ 1</li><li>Mục phụ 2</li></ul><li>Mục thứ tư</li></ul> |

### 5.3 Danh sách bao gồm các yếu tố khác
Để thêm một yếu tố khác vào trong mà vẫn duy trì tính liên tục của danh sách, ta lùi phần tử vào trong bằng bốn khoảng trắng hoặc một tab, ví dụ như sau.

#### 5.3.1. Thêm đoạn văn

    * Đây là mục danh sách đầu tiên.  
    * Đây là mục danh sách thứ hai.  
      Thêm một đoạn khác bên dưới mục danh sách thứ hai.  
    * Và đây là mục danh sách thứ ba.

Output hiển thị như này:

*   Đây là mục danh sách đầu tiên. 
*   Đây là mục danh sách thứ hai. 
    Thêm một đoạn khác bên dưới mục danh sách thứ hai.
*   Và đây là mục danh sách thứ ba.
#### 5.3.2. Thêm Blockquote

    * Đây là mục danh sách đầu tiên.  
    * Đây là mục danh sách thứ hai.  
        Thêm một blockquote bên dưới mục danh sách thứ hai.  
    * Và đây là mục danh sách thứ ba.

Output hiển thị:

*   Đây là mục danh sách đầu tiên. 
*   Đây là mục danh sách thứ hai. 
    > Thêm một blockquote bên dưới mục danh sách thứ hai.
*   Và đây là mục danh sách thứ ba.

#### 5.3.3. Thêm một đoạn code

    1. Mở tệp.
    2. Tìm đoạn code sau trên dòng 21:  
   
        <html>
          <head>
            <title>Test</title>
          </head>

    3. Cập nhật tiêu đề phù hợp với tên của trang web của bạn.

Output hiển thị:

 1. Mở tệp.
 2. Tìm đoạn code sau trên dòng 21:   
        <html>
          <head>
            <title>Test</title>
          </head>

3. Cập nhật tiêu đề phù hợp với tên của trang web của bạn.

## 6. Code
Để biểu thị một từ hoặc cụm từ dưới dạng code, hãy đặt nó trong dấu `.

| Markdown              | HTML                                | Rendered Output            |
| --------------------- | ----------------------------------- | -------------------------- |
| At the command prompt, type &#96;nano&#96;.     | At the command prompt, type &lt;code&gt;nano&lt;/code&gt;. | At the command prompt, type `nano`. |


### 6.1 Khối code
Các đoạn code được trình bày bằng cách thêm bốn khoảng trắng tại đầu mỗi dòng:

        <html>
          <head>
          </head>
        </html>

Output hiển thị:

    <html>
      <head>
      </head>
    </html>

### 6.2. Đường kẻ ngang - Horizontal rule
Để tạo đường kẻ ngang, hãy sử dụng ba dấu sao ***, dấu gạch ngang --- hoặc dấu gạch dưới ___ trên cùng một dòng.
    ***
    * * *
    ---
    - - -
    ___
    _ _ _

Kết quả:
***
* * *
---
- - -
___
_ _ _

## 7. Liên kết - Link
Một liên kết được tạo tự động với cặp móc nhọn <,> đơn giản bao quanh liên kết như thế này <https://duckduckgo.com>
Hoặc cầu kỳ hơn bằng cách đặt văn bản liên kết trong ngoặc (ví dụ: [Duck Duck Go]) và kèm theo URL trong ngoặc đơn (ví dụ: (https://duckduckgo.com)).

    Website yêu thích của tôi là [Duck Duck Go](https://duckduckgo.com).

Kết quả:

Website yêu thích của tôi là [Duck Duck Go](https://duckduckgo.com).

### 7.1. Thêm tiêu đề cho link
Ngoài ra, bạn có thể thêm một tiêu đề cho liên kết xuất hiện dưới dạng một tooltip khi người dùng di chuột qua liên kết. Để thêm tiêu đề, hãy đặt nó trong ngoặc đơn sau URL.

    Website yêu thích của tôi là [Duck Duck Go](https://duckduckgo.com "Công cụ tìm kiếm tốt nhất cho quyền riêng tư").

Kết quả:

Website yêu thích của tôi là [Duck Duck Go](https://duckduckgo.com "Công cụ tìm kiếm tốt nhất cho quyền riêng tư").

### 7.2 URL và địa chỉ email
Để nhanh chóng biến URL hoặc địa chỉ email thành một liên kết, hãy đặt nó trong dấu ngoặc nhọn.

    <https://www.markdownguide.org>
    <fake@example.com>

Kết quả:

<https://www.markdownguide.org>  
<fake@example.com>

### 7.3 Định dạng các liên kết
Để nhấn mạnh các liên kết, thêm dấu sao trước và sau cả cụm định dạng liên kết.

    I love supporting the **[EFF](https://eff.org)**.
    This is the *[Markdown Guide](https://www.markdownguide.org)*.
    See the section on [`code`](#code).

Kết quả:

I love supporting the **[EFF](https://eff.org)**.  
This is the *[Markdown Guide](https://www.markdownguide.org)*.  
See the section on [`code`](#code).  

## 8. Hình ảnh
Để thêm hình ảnh trong markdown, bạn thêm ký tự ! vào đầu tiên, sau đó ghi alt text trong ngoặc vuông [] và URL ảnh trong ngoặc đơn ().

    ![Philadelphia's Magic Gardens. This place was so cool!](https://d33wubrfki0l68.cloudfront.net/eab45e25bb79970178fab7a2d10cba0209372a59/94d9e/assets/images/philly-magic-garden.jpg "Philadelphia's Magic Gardens")

Kết quả:

![Philadelphia's Magic Gardens. This place was so cool!](https://d33wubrfki0l68.cloudfront.net/eab45e25bb79970178fab7a2d10cba0209372a59/94d9e/assets/images/philly-magic-garden.jpg "Philadelphia's Magic Gardens")

### 8.1. Chèn liên kết vào hình ảnh
Để thêm một liên kết vào hình ảnh trong Markdown, bạn đặt toàn bộ khai báo hình ảnh như bước trên trong ngoặc vuông [] và thêm liên kết mình cần vào ngoặc đơn () đặt ngay tiếp sau.

    [![An old rock in the desert](https://d33wubrfki0l68.cloudfront.net/70a143fdf134aacde3740662a2a47a2a1ee0d216/276c9/assets/images/shiprock.jpg "Shiprock, New Mexico by Beau Rogers")](https://www.flickr.com/photos/beaurogers/31833779864/in/photolist-Qv3rFw-34mt9F-a9Cmfy-5Ha3Zi-9msKdv-o3hgjr-hWpUte-4WMsJ1-KUQ8N-deshUb-vssBD-6CQci6-8AFCiD-zsJWT-nNfsgB-dPDwZJ-bn9JGn-5HtSXY-6CUhAL-a4UTXB-ugPum-KUPSo-fBLNm-6CUmpy-4WMsc9-8a7D3T-83KJev-6CQ2bK-nNusHJ-a78rQH-nw3NvT-7aq2qf-8wwBso-3nNceh-ugSKP-4mh4kh-bbeeqH-a7biME-q3PtTf-brFpgb-cg38zw-bXMZc-nJPELD-f58Lmo-bXMYG-bz8AAi-bxNtNT-bXMYi-bXMY6-bXMYv)

Kết quả:

 [![An old rock in the desert](https://d33wubrfki0l68.cloudfront.net/70a143fdf134aacde3740662a2a47a2a1ee0d216/276c9/assets/images/shiprock.jpg "Shiprock, New Mexico by Beau Rogers")](https://www.flickr.com/photos/beaurogers/31833779864/in/photolist-Qv3rFw-34mt9F-a9Cmfy-5Ha3Zi-9msKdv-o3hgjr-hWpUte-4WMsJ1-KUQ8N-deshUb-vssBD-6CQci6-8AFCiD-zsJWT-nNfsgB-dPDwZJ-bn9JGn-5HtSXY-6CUhAL-a4UTXB-ugPum-KUPSo-fBLNm-6CUmpy-4WMsc9-8a7D3T-83KJev-6CQ2bK-nNusHJ-a78rQH-nw3NvT-7aq2qf-8wwBso-3nNceh-ugSKP-4mh4kh-bbeeqH-a7biME-q3PtTf-brFpgb-cg38zw-bXMZc-nJPELD-f58Lmo-bXMYG-bz8AAi-bxNtNT-bXMYi-bXMY6-bXMYv)

## 9. Escaping Characters
Để hiển thị một ký tự chữ thường được sử dụng để định dạng văn bản trong tài liệu Markdown, hãy thêm dấu gạch chéo ngược (\) vào phía trước ký tự.

    \* Without the backslash, this would be a bullet in an unordered list.

Kết quả:

\* Without the backslash, this would be a bullet in an unordered list.

### 9.1. Các ký tự được phép Escape
Bạn có thể sử dụng dấu gạch chéo ngược để escape các ký tự sau.

 Ký tự      | Tên |
| ----------- | ----------- |
| \      | dấu gạch chéo ngược - backslash       |
| `   | backtick (xem thêm [escaping backticks in code](https://www.markdownguide.org/basic-syntax/#escaping-backticks))   |
| *      | dấu hoa thị - asterisk|
| _   | dấu gạch dưới - underscore|
| { }      | dấu ngoặc nhọn - curly braces       |
| [ ]   | dấu ngoặc vuông - brackets |
| < >      | dấu ngoặc nhọn - angle brackets       |
| ( )   | dấu ngoặc đơn - parentheses|
| #      | dấu thăng - pound sign      |
| +   | dấu cộng - plus sign        |
| -      | dấu trừ (gạch nối) - minus sign (hyphen)    |
| .   | dấu chấm - dot        |
| !      | dấu chấm than - exclamation mark     |
| \|   | dấu gạch đứng - pipe (xem thêm [escaping pipe in tables](https://www.markdownguide.org/extended-syntax/#escaping-pipe-characters-in-tables))        |

## 10. HTML
Nhiều ứng dụng Markdown cho phép bạn sử dụng các thẻ HTML trong văn bản có định dạng Markdown. Điều này rất hữu ích nếu bạn thích các thẻ HTML nhất định hơn là cú pháp Markdown. Ví dụ: một số người cảm thấy dễ dàng hơn khi sử dụng thẻ HTML cho hình ảnh. Sử dụng HTML cũng hữu ích khi bạn cần thay đổi các thuộc tính của một phần tử, như chỉ định màu của văn bản hoặc thay đổi chiều rộng của hình ảnh.

Để sử dụng HTML, hãy đặt các thẻ vào văn bản của tệp có định dạng Markdown của bạn.

    This **word** is bold. This <em>word</em> is italic.

This **word** is bold. This <em>word</em> is italic.

## 11. Tổng kết
Có rất nhiều lý do để sử dụng Markdown, nhưng lý do lớn nhất là do sự tiện lợi của việc sử dụng cú pháp được thiết kế riêng nhằm giúp bạn tiết kiệm thời gian, vì vậy nhớ được các cú pháp Markdown sẽ cực kỳ có lợi đấy.

Hi vọng bài viết này hữu ích đối với bạn!