---
title: 25 lệnh Git cơ bản cần nhớ
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
slug: /25-lenh-git-co-ban-can-nho
---

![Alt](https://res.cloudinary.com/practicaldev/image/fetch/s--zoBzMyS5--/c_imagga_scale,f_auto,fl_progressive,h_420,q_auto,w_1000/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/fm2p9ezqdmje2l90y593.png)

## Cơ bản vê Git

Git là tên gọi của một Hệ thống quản lý phiên bản phân tán (Distributed Version Control System – DVCS) là một trong những hệ thống quản lý phiên bản phân tán phổ biến nhất hiện nay. DVCS nghĩa là hệ thống giúp mỗi máy tính có thể lưu trữ nhiều phiên bản khác nhau của một mã nguồn được nhân bản (clone) từ một kho chứa mã nguồn (repository), mỗi thay đổi vào mã nguồn trên máy tính sẽ có thể ủy thác (commit) rồi đưa lên máy chủ nơi đặt kho chứa chính. Và một máy tính khác (nếu họ có quyền truy cập) cũng có thể clone lại mã nguồn từ kho chứa hoặc clone lại một tập hợp các thay đổi mới nhất trên máy tính kia. Trong Git, thư mục làm việc trên máy tính gọi là Working Tree.

<!--truncate-->

## 25 lệnh Git cơ bản

- `git add` : sau khi bạn thay đổi source code: thêm mới, sửa, xoá files,… Bạn cần phải cập nhật lên Staging Area bằng cách sử dụng `git add`.
- `git commit`: sau lệnh add, bạn cần sử dụng câu lệnh `git commit` để đây thông tin thay đổi lên Local Respository.
- `git config`: thiết lập chứng thực cá nhân.
- `git help`:hiển thị tất cả thông tin cần thiết về lệnh git.
- `git status`: cung cấp tất cả thông tin về branch hiện tại.
- `git log`: cho bạn biết về người commit, ngày giờ, message của những lần commit đó.
- `git diff`: lệnh này giúp bạn biết những gì đã được thay đổi giữa branch hiện tại và branch trước nó.
- `git reset --hard`: dùng khi bạn quyết định hủy hoàn toàn commit cuối.
- `git remote add <url or address>`: add mới một remote.
- `git remove rm`: để loại bỏ mẫu file Git repository.
- `git push -u origin master`: cập nhật local files lên server github.
- `git branch`: khi sử dụng Git, bạn có thể tạo ra nhiều nhánh (branch) khác nhau. Câu lệnh Git này dùng để kiểm tra `branch` hiện tại.
- `git checkout`: trước khi muốn thay đổi source code, điều đầu tiên mà bạn cần phải làm là checkout một nhánh. Để checkout một nhánh, bạn dùng câu lệnh `git checkout`.
- `git tag`: gắn thẻ đánh dấu (tag) cho mỗi commit.
- `git fetch`: cập nhật dữ liệu thay đổi từ remote repo về local repo.
- `git rebase`: được sử dụng để nhập một branch đã gần hoàn thiện vào branch gốc (branch master).
- `git config -global color.ui true`: thấy màu sắc khác nhau trên các đầu ra khác nhau.
- `git init`: tạo một kho git repo mới.
- `git commit -m "New file Readme.md"`: lưu các thay đổi của bạn trong kho local repo.
- `git show`: xem những files thay đổi tại một commit bất kỳ.
- `git merge`: ghép branch mới vào master.
- `git pull` : lệnh trên sẽ gộp những thay đổi mới kéo về từ máy chủ từ xa với nhánh hiện tại trên máy local.
- `git stash save`: được sử dụng khi muốn lưu lại các thay đổi chưa commit.
- `git stash drop`: lấy lại thay đổi và xoá nội dung thay đổi lưu trong stack đi.

Via: https://dev.to/devdefinitive/25-git-commands-i-use-daily-and-you-should-know-1kj5
