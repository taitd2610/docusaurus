---
title: Giải Thích về Async/Await trong Javascript
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
slug: /async-await-trong-javascript
---

![Alt](https://codelearn.io/Upload/Blog/asyncawait-trong-javascript-63741267332.9522.jpg)

Hôm nay chúng ta sẽ xây dựng một trang web nhỏ, đồng thời tìm hiểu về bất đồng bộ trong Javascript.Trong quá trình này, bạn sẽ học cách sử dụng:  

- Callbacks
- Promises
- Async / Await

Đây là những gì chúng tôi sẽ đề cập trong bài viết này:

- JavaScript bất đồng bộ là gì? 
- JavaScript đồng bộ (Synchronous) và bất đồng bộ (Asynchronous) 
- Cách Callbacks hoạt động trong JavaScript
- Cách Promises hoạt động trong JavaScript
- Cách Async / Await hoạt động trong JavaScript

## JavaScript đồng bộ (Synchronous) và bất đồng bộ (Asynchronous)
### Hệ thống đồng bộ là gì?
Trong một hệ thống đồng bộ, các task lần lượt được hoàn thành theo trình tự.  

Hãy coi điều này như thể bạn chỉ có 1 cánh tay nhưng có 10 công việc cần thực hiện vậy. Vì vậy, bạn cần phải hoàn thành từng nhiệm vụ một.  

Hãy xem ảnh GIF bên dưới 👇 Bạn có thể thấy rằng mỗi hình ảnh tải cùng một lúc.

![Synchronous System](https://media.giphy.com/media/ICIS16DkE9qB9HVxtq/giphy.gif)  

Bạn sẽ thấy rằng cho đến khi hình ảnh đầu tiên được tải xong hoàn toàn thì hình ảnh thứ hai mới bắt đầu tải. JavaScript theo mặc định là đồng bộ **[đơn luồng]**. 

### Hệ thống bất đồng bộ là gì?
Trong hệ thống này, các task được hoàn thành một cách độc lập.  

Ở đây, hãy tưởng tượng rằng đối với 10 task, bạn có 10 bàn tay. Vì vậy, mỗi tay có thể làm từng nhiệm vụ một cách độc lập và cùng một lúc.  

Hãy xem ảnh GIF bên dưới 👇 - tất cả hình ảnh được load cùng một thời điểm:

![Asynchronous System](https://media.giphy.com/media/MMDnmJnE7uhX6KtcKc/giphy.gif)  

Để tóm tắt JS đồng bộ so với không đồng bộ:

Hãy tưởng tượng ba hình ảnh trên như là 3 người trong một cuộc chạy marathon:

- **Hệ thống đồng bộ**, ba người cùng làn,  người này không thể vượt qua người kia. Cuộc đua đã kết thúc từng người một. Nếu ảnh số 2 dừng thì ảnh sau dừng.

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/w1r9y4ghhq0t8wjb1u9h.png)  

- **Hệ thống bất đồng bộ**, ba hình ảnh nằm trong các làn đường khác nhau. Họ sẽ hoàn thành cuộc đua theo tốc độ của riêng mình. Không ai dừng lại cho bất kỳ ai:

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ehknx5shc4orh32s0ktk.png)  

### Ví dụ về đồng bộ và bất đồng bộ

Trước khi bắt đầu dự án của chúng tôi, chúng ta hãy xem xét một số ví dụ và làm rõ bất kỳ nghi ngờ nào.

#### Ví dụ về đồng bộ
Để kiểm tra hệ thống đồng bộ, hãy viết đoạn code sau bằng JavaScript:

```js
console.log(" I ");

console.log(" eat ");

console.log(" Ice Cream ");
```

Đây là kết quả trong console: 👇  

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/54izy7zyo52j2z6netls.png) 

#### Ví dụ về bất đồng bộ

Để kiểm tra hệ thống đồng bộ, hãy viết đoạn code sau bằng JavaScript:

**Lưu ý**: Đừng lo lắng, chúng ta sẽ thảo luận về hàm `setTimeout()` ở phần sau của bài viết này.

```js
console.log("I");

// This will be shown after 2 seconds

setTimeout(()=>{
  console.log("eat");
},2000)

console.log("Ice Cream")
```

Đây là kết quả trong console: 👇  

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/o44c2t0r7bknkadoumgx.png) 

Bây giờ bạn đã biết sự khác biệt giữa hoạt động đồng bộ và không đồng bộ, hãy cùng xây dựng một project.

#### Thiết lập dự án.
Đối với dự án này, bạn chỉ cần mở [Codepen.io](https://codepen.io/) và bắt đầu viết code. Hoặc, bạn có thể làm điều đó trong VSCode hoặc bất cứ editor nào mà bạn thích.  

## Callbacks là gì ?
Khi bạn truyền một hàm B vào hàm A dưới dạng 1 tham số, thì đó được gọi là callback. 

Đây là một minh họa về callback:

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/uz3pl56lmoc2pq7wzi2s.png) 

Đừng lo lắng, chúng ta sẽ xem một số ví dụ về callback ở phần sau.

### Tại sao cần sử dụng callback ?

Khi thực hiện một nhiệm vụ phức tạp, chúng ta chia nhiệm vụ đó thành các bước nhỏ hơn. Để giúp chúng ta thiết lập mối quan hệ giữa các bước này theo thời gian (tùy chọn) và thứ tự, chúng ta sử dụng callback.  

Hãy xem ví dụ sau: 👇  

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/o05q7ortgctx2oeyntfn.png)  

Đây là những bước nhỏ bạn cần làm tạo ra 1 ly kem. Cũng lưu ý rằng trong ví dụ này, thứ tự của các bước và thời gian là rất quan trọng. Bạn không thể chỉ cắt trái cây và phục vụ kem.  

Đồng thời, nếu bước trước đó chưa hoàn thành, chúng ta không thể chuyển sang bước tiếp theo.

Để giải thích chi tiết hơn điều đó, chúng ta hãy bắt đầu viết một project về kinh doanh cửa hàng kem.

Cửa hàng sẽ có hai phần:  

- Kho sẽ có tất cả các thành phần **[Backend]** 
- Chúng ta sẽ sản xuất kem trong nhà bếp **[Frontend]**

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/i69bws707m5rvsj34i9o.png)  

#### Lưu trữ dữ liệu

Bây giờ, chúng ta sẽ lưu trữ các thành phần bên trong một đối tượng (object). Hãy bắt đầu!  

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ihezrht8dgg9xn8lm2k9.png)  

Bạn có thể lưu trữ các thành phần bên trong các objects như thế này: 👇  

```js
let stocks = {
    Fruits : ["strawberry", "grapes", "banana", "apple"]
}
```  

Các thành phần khác của chúng ta ở đây: 👇  

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/6dcwr770l0ubupv0r2gj.png)  

Bạn có thể lưu trữ các thành phần khác này trong các đối tượng JavaScript như thế này: 👇  

```js
let stocks = {
    Fruits : ["strawberry", "grapes", "banana", "apple"],
    liquid : ["water", "ice"],
    holder : ["cone", "cup", "stick"],
    toppings : ["chocolate", "peanuts"],
};
```  

Toàn bộ hoạt động kinh doanh phụ thuộc vào những gì khách hàng đặt hàng. Khi chúng ta có đơn đặt hàng, chúng ta bắt đầu sản xuất và sau đó phục vụ kem. Vì vậy, chúng ta sẽ tạo hai hàm ->  

- `order`
- `production`  

Đây là cách tất cả hoạt động: 👇  

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/r8h8ra9wor8cs3dgddpb.png)  

Hãy thực hiện tạo hàm. Chúng ta sẽ sử dụng các arrow functions ở đây:  

```js
let order = () =>{};

let production = () =>{};
```  

Bây giờ, hãy thiết lập mối quan hệ giữa hai hàm này bằng cách sử dụng một callback, như thế này: 👇  

```js
let order = (call_production) =>{
  call_production();
};

let production = () =>{};
```  

#### Hãy làm một bài kiểm tra nhỏ

Chúng ta sẽ sử dụng hàm `console.log()` để tiến hành các bài kiểm tra nhằm xóa bỏ bất kỳ nghi ngờ nào mà chúng tôi có thể có về cách chúng tôi thiết lập mối quan hệ giữa hai hàm.