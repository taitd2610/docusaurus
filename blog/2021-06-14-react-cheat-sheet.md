---
title: React Cheat sheet (Updated June 2021)
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
slug: /react-cheat-sheet
---

![Alt](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/r3ui703pme0meo82pu5o.png)

Tôi không sử dụng React thường xuyên và vì vậy bất cứ khi nào tôi cần làm ngay cả việc nhỏ nhất trong React, tôi phải xem tài liệu, hướng dẫn hoặc đăng câu hỏi trên diễn đàn.  

Đó là lý do tại sao tôi quyết định làm công cụ hỗ trợ trí nhớ này và cho rằng trí nhớ của tôi không tốt lắm, tôi đã nghĩ tại sao không tạo ra một công cụ hỗ trợ trí nhớ khổng lồ với tất cả các khái niệm tôi biết về React.  

Vì vậy, tôi có thể đọc nó theo thời gian và từ đó củng cố kiến ​​thức của tôi về React.  

Nếu bạn có ý tưởng hoặc đề xuất, đừng ngần ngại và hãy làm như vậy trong phần nhận xét.

<!--truncate-->

## React Cheat Sheet

### Create React App

```sh
// Create a new app
npx create-react-app my-app-name

// Run the created app
cd my-app-name
yarn start

// http://localhost:3000
```

### First React functional Component
- Không cần import React từ 'react' (kể từ React 17) 
- Phải có chữ cái đầu tiên viết hoa 
- Phải trả về JSX

```jsx title="src/App.js"
// React component
function App(){
  return <h1>Hello World</h1>
} 

export default App;
```

Làm thế nào thành phần này được hiển thị cho trình duyệt? Tệp dự án chính là src / index.js và trong tệp đó có hướng dẫn để kết xuất thành phần


