---
title: Tổng hợp những VS Code Extensions xịn xò cho Front-End Developers
author: Trịnh Đình Tài
author_title: Admin
author_url: https://github.com/taitd2610
author_image_url: https://scontent-sin6-1.xx.fbcdn.net/v/t1.6435-9/36756866_226907771464364_2771393154585198592_n.jpg?_nc_cat=101&ccb=1-3&_nc_sid=09cbfe&_nc_ohc=MGgQs4UzM5EAX-5FQaR&_nc_ht=scontent-sin6-1.xx&oh=24342e3e97bc53311a628434d6667de7&oe=60DCA347
tags: [VSCode]
description: This is my first post on Docusaurus 2.
image: https://i.imgur.com/mErPwqL.png
hide_table_of_contents: false
sidebar_label: "Xin chào"
sidebar_position: 1
slug: /vs-code-extension
---

![Alt](https://blog.logrocket.com/wp-content/uploads/2021/01/Top-10-Code-Extensions-of-2021.png)

Visual Studio Code(VSCode) là một text editor cross-flatform miễn phí, được phát triển bởi Microsoft. VSCode nhanh chóng trở thành một công cụ ưa thích của rất nhiều lập trình viên nhờ hiệu suất tuyệt vời và rất nhiều tính năng phong phú mà nó cung cấp.  

Cũng giống như rất nhiều IDE khác, VSCode cũng hỗ trợ các extension, có hẳn 1 khu chợ với hàng nghìn plugin để developer có thể mua, download và sử dụng. Trong bài này tôi xin giới thiệu những plugin rất hữu ích để các bạn sử dụng trong quá trình làm việc với VSCode
<!--truncate-->


## 1. Automating Log Messages
Thay vì gõ những dòng `console.log()` nhàm chán thì với extension [turbo-console-log](https://github.com/Chakroun-Anas/turbo-console-log) bạn có thể tự động việc đó bằng phím tắt.
Ngoài ra còn tự động thêm các tiêu đề có nghĩa cho các giá trị được log ra.

![Alt](https://images.viblo.asia/8b6a91be-035e-42db-8266-065f0119614e.gif)

Tất cả những gì bạn cần làm là chọn biến mà bạn muốn in ra console, nhấn tổ hợp phím `Ctrl + Alt + L` và log sẽ được tự động chèn vào dòng tiếp theo. 

## 2. Keeping Bundle Size Under Control
Tất cả chúng ta đều biết rằng hiệu suất rất quan trọng. Để kiểm soát kích thước các thư viện được import trong dự án, [Import Cost](https://github.com/Chakroun-Anas/turbo-console-log) sẽ cho bạn biết những thư viện nào quá nặng, nên thay thế hoặc loại bỏ, hoặc import 1 phần nhỏ thôi. 

![Alt](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/b80c0489-6d8b-40cc-a93c-d0ce4591110a/12-useful-vs-code-extensions.png)

**Import Cost** không phải là một công cụ phân tích mà được xây dựng với ý tưởng giúp bạn tìm ra những **điểm nghẽn hiệu suất** có thể xảy ra trước khi bạn gửi chúng cho người dùng của mình. Để làm như vậy, nó cung cấp cho bạn phản hồi tức thì bằng cách hiển thị kích thước của thư viện bên thứ ba đã khi bạn import thư viện đó, ngay bên cạnh dòng code của bạn. Một extension khá hữu ích.


## 3. Code Formatting, Automated
Khi viết code, rất nhiều thời gian dành cho việc định dạng. Prettier tự động hóa nhiệm vụ cho bạn. Nó loại bỏ tất cả kiểu dáng ban đầu và đảm bảo rằng mã đầu ra tuân theo một kiểu nhất quán.

![Alt](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/83e743ec-2b55-40e6-b1cc-2bcf32314391/13-useful-vs-code-extensions.png)


Prettier phân tích cú pháp mã của bạn và **định dạng lại nó bằng các quy tắc riêng**, tính đến độ dài dòng tối đa và gói mã khi cần thiết. Bạn quyết định xem bạn muốn áp dụng nó cho tất cả các ngôn ngữ hay cách khác, bạn có thể xác định những ngôn ngữ bạn muốn định dạng theo cách thủ công. Đây cũng là một giải pháp tuyệt vời cho các nhóm đang gặp khó khăn trong việc tìm kiếm một hướng dẫn phong cách chung.


## 4. Useful Code Snippets (React, Vue, TypeScript, JQuery)

Bạn có cảm thấy mệt mỏi khi phải nhập đi nhập lại các đoạn code mà bạn thường xuyên cần lặp đi lặp lại, luôn luôn từ đầu không? Dưới đây là một số trợ giúp nhỏ hữu ích để dễ dàng công việc. Đối với Vue, hãy nhớ xem phần mở rộng [Vue.js VS Code Snippets](https://marketplace.visualstudio.com/items?itemName=sdras.vue-vscode-snippets). Nó được xây dựng để sử dụng trong thế giới thực và tập trung vào công thái học của nhà phát triển thay vì lập danh mục các định nghĩa API.

Burke Holland cung cấp cho bạn một bộ sưu tập [Simple React Snippets](https://marketplace.visualstudio.com/items?itemName=burkeholland.simple-react-snippets) mà anh ấy đã chọn từ việc sử dụng React hàng ngày của mình. Và nếu bạn đang tìm kiếm các đoạn trích Angular, John Papa sẽ giúp bạn. Phần mở rộng của anh ấy thêm [snippets for Angular for TypeScript and HTML](https://github.com/johnpapa/vscode-angular-snippets) vào thiết lập VS Code của bạn.

![Alt](https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/0ff02aef-a105-4121-91cc-af9d03cf28da/vs-code-snippets.png)


Nói về snippets: Nếu bạn thích một thư viện snippets tốt hơn là tự mình xác định chúng từ đầu, thì những bộ sưu tập này đã giúp bạn:

1. [ES7 React/Redux/GraphQL/React-Native](https://marketplace.visualstudio.com/items?itemName=dsznajder.es7-react-js-snippets)
2. [Javascript (ES6) Code Snippets](https://marketplace.visualstudio.com/items?itemName=xabikos.JavaScriptSnippets)
3. [Svelte 3 Snippets](https://marketplace.visualstudio.com/items?itemName=fivethree.vscode-svelte-snippets)


## 5. Code Screenshots, The Fancy Way
Thành thật mà nói, chụp ảnh màn hình mã đẹp mắt có thể là một thách thức. [Polacode](https://marketplace.visualstudio.com/items?itemName=pnp.polacode) ở đây để thay đổi điều đó.

![Alt](https://res.cloudinary.com/indysigner/image/fetch/f_auto,q_auto/w_2000/https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/842b0f9b-f49e-4d10-9269-cc2ef34ea2ad/polacode.png)

Được mô tả là “Polaroid for your code”, Polacode cho phép bạn chụp và chỉnh sửa ảnh chụp màn hình mã của mình trực tiếp trong VS Code. Bạn có thể thay đổi kích thước của vùng chứa code bằng cách kéo góc và sử dụng các lệnh để kiểm soát giao diện hình ảnh. Một giải pháp tuyệt vời để làm cho code mà bạn đã dành nhiều giờ để tỏa sáng trong điều kiện ánh sáng tốt nhất - chẳng hạn như trong các bài đăng hoặc bài thuyết trình trên blog.

## 6. Human-Friendly Comments
Làm thế nào để bạn xử lý các comments? Nếu code của bạn yêu cầu nhiều comment, có thể là một ý kiến ​​hay để làm cho những comment đó thân thiện với con người hơn, để dễ dàng xem nhanh hơn nếu một comment cảnh báo bạn về một phương pháp không được dùng nữa, chẳng hạn như hoặc nếu đó là một trò đùa mà đồng đội của bạn để lại cho bạn.

![Alt](https://res.cloudinary.com/indysigner/image/fetch/f_auto,q_auto/w_2000/https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/0e1c1941-2e52-4ed6-a192-8bfcf743d31a/6-useful-vs-code-extensions.png)


Extension [Better Comments](https://marketplace.visualstudio.com/items?itemName=aaron-bond.better-comments) giúp bạn làm điều đó, phân loại các comment thành các cảnh báo, truy vấn, việc cần làm, đánh dấu và hơn thế nữa. Comment code cũng có thể được tạo kiểu để làm rõ ràng rằng nó không nên ở đó.

## 7. Chrome Debugging Inside VS Code
Bạn có sử dụng Chrome và thấy mình chuyển đổi qua lại giữa trình duyệt và trình chỉnh sửa của mình khi debug không? Sau đó, bạn có thể muốn dùng thử [VS Code Chrome debugger](https://code.visualstudio.com/blogs/2016/02/23/introducing-chrome-debugger-for-vs-code). Nó giúp bạn debug code JavaScript phía client chạy trong Chrome trực tiếp từ VS Code.


![Alt](https://res.cloudinary.com/indysigner/image/fetch/f_auto,q_auto/w_2000/https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/2d2443a6-a085-4749-a7bc-a8621949eae0/14-useful-vs-code-extensions.png)

Trình debug kết nối với Chrome qua giao thức Chrome Debugger, nơi nó ánh xạ các tệp được tải trong trình duyệt với các tệp bạn đã mở trong VS Code. Vì vậy, không cần rời khỏi editor, bạn có thể **đặt các breakpoints trong code của mình**, thiết lập các biến để xem và xem toàn bộ call stack khi debug. Một công cụ nhỏ để làm cho quy trình debug của bạn trở nên đơn giản hơn.

## 8. Adding Tags To Files In Your Editor
Trong các dự án lớn, việc tìm kiếm một biến thể cụ thể của một thành phần hoặc chỉ tệp phù hợp đòi hỏi bạn phải biết tệp mà bạn thực sự đang tìm kiếm. Nhưng điều gì sẽ xảy ra nếu bạn có thể **thêm dấu trang hoặc nhãn** vào các tệp cụ thể để bạn có thể tìm thấy chúng nhanh hơn?

![Alt](https://res.cloudinary.com/indysigner/image/fetch/f_auto,q_auto/w_2000/https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/5bb0e6cc-1680-47e2-8739-d7388264db2d/2-useful-vs-code-extensions.png)

Trình debug kết nối với Chrome qua giao thức Chrome Debugger, nơi nó ánh xạ các tệp được tải trong trình duyệt với các tệp bạn đã mở trong VS Code. Vì vậy, không cần rời khỏi editor, bạn có thể **đặt các breakpoints trong code của mình**, thiết lập các biến để xem và xem toàn bộ call stack khi debug. Một công cụ nhỏ để làm cho quy trình debug của bạn trở nên đơn giản hơn.

[File Ops](https://marketplace.visualstudio.com/items?itemName=mehullakhanpal.file-ops) cho phép bạn **gắn thẻ và các tệp bí danh**, sau đó nhanh chóng chuyển đổi giữa chúng. Bạn cũng có thể nhanh chóng liệt kê tất cả các thẻ trong trường hợp bạn mất dấu chúng, xem tất cả các tệp từ thư mục hiện tại và chuyển đổi giữa các tệp .css và .js trong cùng một thư mục. Bạn cũng có thể xem [video](https://www.youtube.com/watch?v=ze9KtYe3f48) giải thích cách hoạt động của tất cả. Bây giờ điều đó sẽ có ích!

## 9. Git Supercharged
Một extension hữu ích để tăng cường các khả năng Git được tích hợp trong VS Code là [GitLens](https://github.com/eamodio/vscode-gitlens). Để hiểu rõ hơn về mã bạn đang làm việc, GitLens cho phép bạn xem qua ai, tại sao và khi nào một dòng hoặc khối mã được thay đổi.

![Alt](https://res.cloudinary.com/indysigner/image/fetch/f_auto,q_auto/w_2000/https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/2d84c863-d40f-4055-8730-86a689d3c935/11-useful-vs-code-extensions.png)

Extension **trực quan hóa các quyền tác giả mã** trong nháy mắt, giúp bạn điều hướng và khám phá các kho lưu trữ Git một cách liền mạch, có được thông tin chi tiết có giá trị thông qua các lệnh so sánh và hơn thế nữa. Mọi thứ bạn cần biết về cơ sở mã của mình ngay trong tầm tay bạn mà không cần rời khỏi trình chỉnh sửa.

## 10. Git History In VS Code
Xem và tìm kiếm nhật ký git cùng với biểu đồ và chi tiết, xem bản sao trước đó của tệp bạn đang làm việc, **tìm kiếm lịch sử**, so sánh các nhánh và cam kết - đây chỉ là một vài tính năng mà extension [Git History](https://github.com/eamodio/vscode-gitlens) cung cấp để hợp lý hóa quy trình làm việc của bạn.

![Alt](https://res.cloudinary.com/indysigner/image/fetch/f_auto,q_auto/w_2000/https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/7ae03994-3294-4c07-b0dd-9b307aa1d1dc/git-graph-opt.png)


## 11. Highlight Annotations In Your Code
Đôi khi bạn quên xem lại những việc cần làm mà bạn đã thêm trong khi viết code? Tiện ích [TODO Highlight](https://marketplace.visualstudio.com/items?itemName=wayou.vscode-todo-highlight) nhắc nhở bạn rằng có những ghi chú hoặc những điều bạn cần chú ý trước khi xuất bản lên phiên bản sản xuất.

Xem và tìm kiếm nhật ký git cùng với biểu đồ và chi tiết, xem bản sao trước đó của tệp bạn đang làm việc, **tìm kiếm lịch sử**, so sánh các nhánh và cam kết - đây chỉ là một vài tính năng mà extension  cung cấp để hợp lý hóa quy trình làm việc của bạn.

![Alt](https://res.cloudinary.com/indysigner/image/fetch/f_auto,q_auto/w_2000/https://cloud.netlifyusercontent.com/assets/344dbf88-fdf9-42bb-adb4-46f01eedd629/87bebcbc-fb2e-4390-80dc-2a669a590ada/todo-highlight-opt.png)

Từ khóa `TODO` và `FIXME` được cấu hình sẵn, nhưng bạn có thể **tùy chỉnh cấu hình** theo ý muốn của mình nếu muốn. Một lệnh làm nổi bật các comment đang mở cho bạn ngay trong code của bạn hoặc dưới dạng danh sách tất cả các chú thích. Một lời nhắc nhở nhỏ tuyệt vời.