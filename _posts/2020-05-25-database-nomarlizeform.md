---
layout: course-relationaldatabase
title:  Các bước chuẩn hoá dữ liệu trong thiết kế database
slug :  chuan-hoa-du-lieu-trong-thiet-ke-database
category: database
tags: [database]
summery: Các bước chuẩn hoá dữ liệu    
image: /images/blog/database.png
description : Bài viết trình bày về thiết kế Database. Trong đó, tác giả hướng dẫn cụ thể các bước thực hiện để thiết kế một Database chuẩn. Trước đó bài viết sẽ giới thiệu để bạn hiểu được tại sao phải cần chuẩn hoá dữ liệu, và chuẩn hoá dữ liệu trong thiết kế Database là gì. Tìm hiểu thêm về 4 dạng chuẩn hoá dữ liệu. Trong bài giảng tác giả chia sẻ kèm theo ví dụ cụ thể minh hoạ cho từng bước làm. Ngoài ra bài viết đưa ra một số lưu ý và thủ thuật để giúp quá trình thiết kế Database được chuẩn hoá dữ liệu hơn.
youtubeId: Thx8bBqIY28
---


{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn, chắc hẳn sẽ có lúc các bạn gặp phải những khó khăn trong việc <b>tối ưu hoá dữ liệu trong Database</b> một vài lần rồi nhỉ? Các bạn không biết mình nên
bắt đầu từ đâu khi xây dựng một <b>Database</b> và làm thế nào để thiết kế một Database tối ưu. Trong bài viết hôm nay anh sẽ trình bày các kĩ thuật để các bạn có thể xây dựng được một Database chuẩn hoá.

<br>
## **Tại sao phải cần chuẩn hoá dữ liệu**

Để hiểu tại sao phải chuẩn hoá dữ liệu thì ta sẽ trả lời chuẩn hoá dữ liệu giúp được gì cho ta.

<br>
1. Chuẩn hoá dữ liệu giúp ta giảm bớt sự dư thừa dữ liệu trong Database, giúp chương trình chaỵ nhanh hơn, quản lí trở nên dễ dàng hơn.

<br>
Anh lấy một ví dụ. Công ty Amazon nhờ team chúng ta xây dựng một ứng dụng kho hàng để quản lí sản phẩm. Nếu chúng ta thiết kế không theo các bước chuẩn hoá chắc chắn 100% chúng ta sẽ tạo ra các Tables và các Column mà dữ liệu sẽ trùng lặp không cần thiết.
Vậy các em hãy tưởng tượng một ngày ở Amazon cả hàng triệu sản phẩm được nhập kho thì lượng dữ liệu bị dư thừa là bao nhiêu.
Trong khi Database có kích thước giới hạn. Đồng thời khi ta truy vấn dữ liệu cũng sẽ làm cho câu Query chậm đi. Tiếp đến khi mình bảo trì sẽ gặp khó khăn vì không biết dữ liệu thừa đó xoá đi có ảnh hưởng gì đến các chức năng khác không?

<br>
2. Giảm bớt các lỗi xảy ra khi thực hiện các câu lệnh truy vấn xuống Database như Insert , Update , Delete do dư thừa dữ liệu gây ra.
<br>

<br>
## **Vậy chuẩn hoá dữ liệu là gì?**
Là quá trình phân tích chia bảng thành những bảng nhỏ hơn dựa vào các quy luật chuẩn hoá.

<b>Có 4 dạng chuẩn hoá dữ liệu</b>: 1NF, 2NF, 3NF, 4NF, và dạng BCNF (Boyce Codd Normal Form) .

<br>
## **Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé.**
{% include youtubePlayer.html id=page.youtubeId %}
