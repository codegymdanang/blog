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
Ai sẽ quản lý bộ nhớ ? Bài viết sau đây anh sẽ giải thích cho các bạn 2 bộ nhớ Heap và Stack lưu trữ dữ liệu gì và lưu như thế nào nhé .. 
<br><br>

### Các thuật ngữ 
![Các thuật ngữ ](/images/post/javacore/cacthuatngu.png){:class="img-responsive"}
<br>

### Heap và Stack
Java Heap và Stack Memory là một phần của bộ nhớ được JVM sử dụng để chạy chương trình Java của bạn. Khi bạn chạy chương trình Java, JVM sẽ yêu cầu hệ điều hành cấp cho một không gian bộ nhớ trong RAM để dùng cho việc chạy chương trình. JVM sẽ chia bộ nhớ được cấp phát này thành 2 phần: Heap và Stack cho việc quản lý.

![Heap và Stack trong Java  ](/images/post/javacore/stackandheap.png){:class="img-responsive"}
<br>

### Bộ nhớ Heap 
1. Java Heap Memory là bộ nhớ được sử dụng ở runtime để lưu các Objects. Bất cứ khi nào ở đâu trong chương trình của bạn khi bạn tạo Object thì nó sẽ được lưu trong Heap (thực thi toán tử new).
2. Các objects trong Heap đều được truy cập bởi tất cả các các nơi trong ứng dụng, bởi các threads khác nhau.
3. Thời gian sống của object phụ thuộc vào Garbage Collection của java.
4. Garbage Collection sẽ chạy trên bộ nhớ Heap để xoá các Object không được sử dụng nữa, nghĩa là object không được referece trong chương trình.
5. Dung lượng sử dụng của Heap sẽ tăng giảm phụ thuộc vào Objects sử dụng.
6. Dung lượng Heap thường lớn hơn Stack
<br>

### Bộ nhớ Stack

1. Bộ nhớ để lưu các biến local trong hàm và lời gọi hàm ở runtime trong một Thread java.
2. Các biến local bao gồm loại nguyên thuỷ (primitive) và loại tham chiếu tới đối tượng trong heap (reference) khai báo trong hàm, hoặc đối số được truyền vào hàm, thường có thời gian sống ngắn.
3. Bộ  nhớ stack thường nhỏ.
4. Cơ chế hoạt động là LIFO (Last-In-First-Out), chạy sau chết trước.
5. Bất cứ khi nào gọi 1 hàm, một khối bộ nhớ mới sẽ được tạo trong Stack cho hàm đó để lưu các biến local. Khi hàm thực hiện xong, khối bộ nhớ cho hàm sẽ bị xoá, và giải phóng bộ nhớ trong stack.
<br>

### Ví dụ về Heap và Stack 
![Ví dụ về Heap và Stack  ](/images/post/javacore/vdheapstack.png){:class="img-responsive"}

1. Dòng 1 phương thức public static void main sẽ lưu bên Stack (vì stack sẽ cấp phát vùng nhớ cho phương thức)
2. Dòng 2 khai báo biến i = 2 thì nằm bên stack vì stack lưu các biến
3. Dòng 3 khai báo biến Object obj = new Object  thì biến obj  nằm bên stack vì stack lưu các biến còn đối tượng Object được lưu bên Heap và biến obj sẽ tham 
chiếu đến đối tượng Object bên bộ nhớ Heap .
4. Dòng 4 Memory mem = new Memory thì đối tượng Memory sẽ lưu bên bộ nhớ heap còn biến mem thì lưu bên bộ nhớ stack , và mem tham chiếu tới đối
tượng Memory bên Heap 
5. Dòng 5  mem.foo() thì phương thức foo() được tạo ra ở dòng 5. Phương thức foo này là nằm trong phương thức main . Như ta thấy bên bộ nhớ Stack
Hình chữ nhật bự nhất bao ở ngoài là hàm main () . Bên trong hàm main là bộ nhớ phương thức foo. Khi chương trình chạy xong thì bộ nhớ foo() sẽ 
được giải phóng trước sau đó mới đến main. 
6. Dòng 6 private void foo() thì hàm foo()  được lưu trong bộ nhó Stack 
7. Dòng 7 String str = param.toString() . Trong java String là kiểu đặc biệt . Nó là kiểu Object và được quản lý bởi String Pool riêng. Chính vì vậy nó 
được lưu bên Heap 
<br>

### Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé . 

<p align="center">
{% include youtubePlayer.html id=page.youtubeId %}
<p>
