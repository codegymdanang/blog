---
layout: blog
title:  Access Modifier Trong Java
slug : phan-biet-access-modifier-trong-java
category: laptrinhjava
tags: [java core]
summery: Blog 1
image: /images/blog/java.png
description : Các access modifier trong java . học lập trình  ngôn ngữ lập trình lập trình java java cơ bản khóa học lập trình java học ngôn ngữ lập trình java
youtubeId: qzfMZigVMDc
---

### **1. Giới thiệu nội dung bài viết**

Chào bạn, bạn đã từng nghe tới khái niệm về các access modifier  chưa ? Bài viết hôm nay giúp bạn phân biệt các từ khoá
như public , private , protected và default. Khi nào thì mình nên dùng từ khoá nào là hợp lý nhất nhằm tăng thêm tính bảo mật cho các giá trị và phương thức trong 
lớp . Trong bài viết hôm nay chúng ta sẽ thảo luận các vấn đề sau .

- Sử dụng từ khoá public 
- Sử dụng từ khoá private 
- Sử dụng từ khoá default
- Sử dụng từ khoá protected 
- Sử dụng từ khoá static
- Sử dụng từ khoá final 
- Video hướng dẫn sử 

### **1. Từ khoá public dùng làm gì**

Khi một phương thức hoặc biến được khai báo là public, có nghĩa là tất cả các class khác, kể cả các class không thuộc cùng package đều có thể truy cập.

### **2. Từ khoá private  dùng làm gì**

Khi một phương thức hoặc biến được khai báo là private nó sẽ không thể truy cập từ class khác, kể cả các class cùng source file hay các class con.

### **3. Từ khoá default  dùng làm gì**

Khi một phương thức hoặc biến được khai báo là default thì chỉ có các class thuộc cùng package với nó mới có thể truy cập. 

### **4. Từ khoá protected   dùng làm gì**

Protected modifier khá giống với default modifier, nó hạn chế khả năng truy cập trong cùng 1 package, tuy nhiên với protected modifier thì nó còn cho phép truy cập từ các class con kể cả khi class con không nằm cùng package với class cha. (truy cập theo trường hợp thừa kế).

### **5. Từ khoá static dùng làm gì**

Static : khi mình muốn chia sẽ (dùng chung, và là duy nhất tron cả hệ thống) cái biến đó cho các object khác có thể sử dụng được.

### **6. Từ khoá final  dùng làm gì**

Final : Khi mình muốn giá trị là hằng số và không thể thay đổi được (Ví dụ final double PI = 3.14).

### **7. Tổng kết**

Việc sự dụng đúng scope (phạm vi) của biến rất quan trọng trong lập trình .Đối với các thuộc tính có tính bảo mật cao ta chỉ cho phép nội bộ của nó có thể thấy và thay
đổi được giá trị . Nếu ta không làm như vậy thì lớp nào cũng thấy và sẽ thay đổi giá trị đó làm cho việc kiểm soát và bảo mật không còn nữa dẫn đến chương trình chạy sai ý 
định của mình , đồng thời ai cũng thấy và sẽ thay đổi được giá trị của biến 

### Video demo  

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}