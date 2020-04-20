---
layout: blog
title: Bộ  Heap va Stack
category: blog
tags: [java core]
summery: Phân Biệt Bộ Nhớ  Heap va Stack
image: /images/blog/java.png
youtubeId: werAdblsT1s
---
Chào bạn, chắc hẳn bạn đang phân vân khi mình khai báo biến , object , phương thức , tham số thì nó sẽ được lưu ở đâu trong bộ nhớ phải không ?
Ai sẽ quản lý bộ nhớ ? Bài viết sau đây anh sẽ tóm tắt lại các ý chính 
<br/><br/>


### Các thuật ngữ 
![Các thuật ngữ ](/images/post/javacore/cacthuatngu.png){:class="img-responsive"}

### Heap và Stack
Java Heap và Stack Memory là một phần của bộ nhớ được JVM sử dụng để chạy chương trình Java của bạn. Khi bạn chạy chương trình Java, JVM sẽ yêu cầu hệ điều hành cấp cho một không gian bộ nhớ trong RAM để dùng cho việc chạy chương trình. JVM sẽ chia bộ nhớ được cấp phát này thành 2 phần: Heap và Stack cho việc quản lý.

![Heap và Stack trong Java  ](/images/post/javacore/stackandheap.png){:class="img-responsive"}

### Bộ nhớ Heap 
1. Java Heap Memory là bộ nhớ được sử dụng ở runtime để lưu các Objects. Bất cứ khi nào ở đâu trong chương trình của bạn khi bạn tạo Object thì nó sẽ được lưu trong Heap (thực thi toán tử new).
2. Các objects trong Heap đều được truy cập bởi tất cả các các nơi trong ứng dụng, bởi các threads khác nhau.
3. Thời gian sống của object phụ thuộc vào Garbage Collection của java.
4. Garbage Collection sẽ chạy trên bộ nhớ Heap để xoá các Object không được sử dụng nữa, nghĩa là object không được referece trong chương trình.
5. Dung lượng sử dụng của Heap sẽ tăng giảm phụ thuộc vào Objects sử dụng.
6. Dung lượng Heap thường lớn hơn Stack

### Bộ nhớ Stack

1. Bộ nhớ để lưu các biến local trong hàm và lời gọi hàm ở runtime trong một Thread java.
2. Các biến local bao gồm loại nguyên thuỷ (primitive) và loại tham chiếu tới đối tượng trong heap (reference) khai báo trong hàm, hoặc đối số được truyền vào hàm, thường có thời gian sống ngắn.
3. Bộ  nhớ stack thường nhỏ.
4. Cơ chế hoạt động là LIFO (Last-In-First-Out), chạy sau chết trước.
5. Bất cứ khi nào gọi 1 hàm, một khối bộ nhớ mới sẽ được tạo trong Stack cho hàm đó để lưu các biến local. Khi hàm thực hiện xong, khối bộ nhớ cho hàm sẽ bị xoá, và giải phóng bộ nhớ trong stack.

### Ví dụ về Heap và Stack 
![Ví dụ về Heap và Stack  ](/images/post/javacore/vdheapstack.png){:class="img-responsive"}

### Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé . 
<p align="center">
{% include youtubePlayer.html id=page.youtubeId %}
<p>
