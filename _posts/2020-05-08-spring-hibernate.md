---
layout: blog
title: Hibernate trong Spring
slug : hibernate trong java
category: laptrinhspring
tags: [spring]
summery: OneToOne Relationship
image: /images/blog/spring.png
description : hibernate là gì .học lập trình  ngôn ngữ lập trình lập trình java java cơ bản khóa học lập trình java học ngôn ngữ lập trình java
youtubeId: WNfuVJptPnQ
---

### **1. Giới thiệu nội dung bài viết**

Chào các em ,chủ để hôm nay chúng ta sẽ tìm hiểu về Hibernate là -  .
Nội dung mình sẽ giải thích trong bài này sẽ xoay quanh các chủ đề sau đây.

- Hibernate là gì ?
- Tại sao mình sử dụng Hibernate
- So sánh ưu điểm của Hibernate so với JDBC
- Cấu hình Hibernate với Spring (https://www.baeldung.com/hibernate-4-spring)

### **2. Giới thiệu Hibernate**

Như các em biết để hiển thị được dữ liệu lưu trữ trong cơ sở dữ liệu (database) ra cho người dùng thì mình phải thao tác xuống database như kết nối vào database .Sau đó thực hiện các câu lệnh truy vấn như select , insert, update , join các. Cuối cùng là lấy dữ liệu từ database về và xử lý. Trong lập trình java mình may mắn có một framework giúp mình làm được tất cả các việc đó. Nó chính là  Hibernate.

Vì sao ta nên sử dụng framework , bởi vì nó đã có sẳn các thư viện như kết nối xuống database, thực hiện các câu truy vấn chúng ta chỉ sử dụng các thư việc có sẳn mà framework cung cấp và nhiệm vụ của chúng ta chỉ tập trung vào xử lý các nghiệp vụ của phần mềm.

Hibernate là một framework được sử dụng ở tầng Persistence. Tầng Persisten có nghĩa là lưu trử và sử lý dữ liệu trong một khoảng thời gian dài. Hibernate là mã nguồn mở , ta có thể nhúng vào dự án và dùng không phải trả tiền

Các chức năng được hỗ trợ khi ta sử dụng Hibernate

- Auto DDL : DDL có nghĩa là các câu lệnh định nghĩa cấu trúc để lưu trữ dữ liệu như create table , columns , kiểu dữ liệu.  
