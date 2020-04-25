---
layout: blog
title:  Access Modifier Trong Java
slug : phan-biet-access-modifier-trong-java
category: laptrinhjava
tags: [java core]
summery: Blog 1
image: /images/blog/java.png
description : Các access modifier trong java 
youtubeId: qzfMZigVMDc
---

Chào bạn, bạn đã từng nghe tới khái niệm về các access modifier  chưa ? Bài viết hôm nay giúp bạn phân biệt các từ khoá
như public , private , protected và default. Khi nào thì mình nên dùng từ khoá nào là hợp lý nhất nhằm tăng thêm tính bảo mật cho các giá trị và phương thức trong 
lớp .
<br><br>

### Từ khoá public dùng làm gì
Khi một phương thức hoặc biến được khai báo là public, có nghĩa là tất cả các class khác, kể cả các class không thuộc cùng package đều có thể truy cập.
<br>

### Từ khoá private  dùng làm gì
Khi một phương thức hoặc biến được khai báo là private nó sẽ không thể truy cập từ class khác, kể cả các class cùng source file hay các class con.
<br>

### Từ khoá default  dùng làm gì
Khi một phương thức hoặc biến được khai báo là default thì chỉ có các class thuộc cùng package với nó mới có thể truy cập. 
<br>

### Từ khoá protected   dùng làm gì
Protected modifier khá giống với default modifier, nó hạn chế khả năng truy cập trong cùng 1 package, tuy nhiên với protected modifier thì nó còn cho phép truy cập từ các class con kể cả khi class con không nằm cùng package với class cha. (truy cập theo trường hợp thừa kế).
<br>

### Từ khoá static dùng làm gì
Static : khi mình muốn chia sẽ (dùng chung, và là duy nhất tron cả hệ thống) cái biến đó cho các object khác có thể sử dụng được.
<br>

### Từ khoá final  dùng làm gì
Final : Khi mình muốn giá trị là hằng số và không thể thay đổi được (Ví dụ final double PI = 3.14).
<br> 

### Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé . 

<p align="center">
{% include youtubePlayer.html id=page.youtubeId %}
<p>