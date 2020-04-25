---
layout: blog
title: Sự khác  giữa abstract và interface
slug : su-khac-nhau-giua-abstract-interface
category: laptrinhjava
tags: [java core]
summery: Sự khác  giữa abstract và interface 
image: /images/blog/java.png
description : Sự khác  giữa abstract và interface 
youtubeId1 : t9in5g6vsSg
youtubeId2 : rUFUgrkMg4o
---

Chào bạn, nếu bạn là người mới tìm hiểu về lập trình, hẳn bạn đã từng nghe tới khái niệm về Abstract và Interface.
Nhưng bạn có biết khi nào mình sẽ dùng abstract và khi nào mình dùng interface không? Khi mới bước chân vào 
nghề lập trình a cũng rất hoang mang về công dụng và lợi ý của Abstract và Interface. Chính vì vậy anh
viết bài này nhằm giúp mọi người có cái nhìn rõ hơn khi nào mình dùng abstract và Interface.
Đầu tiên mình xem quan khái niệm và sự khác nhau giữa abstract và interface trước nhé.
<br><br>

### Interface là gì ?

1. Không phải là class.
2. Chỉ chứa method trống không có phần thân.
3. Nó định nghĩa một mẫu chung các hành động mà các lớp implements nó follow theo.
4. Các lớp có thể cài đặt (implements) một hoặc nhiều Interface.
<br>

### Abstract là gì

1. Trong một class abstract có thể có 2 loại methods : abstract method và method bình thường.
2. Abstract method là method trống không có code thực thi trong đó.
3. Method thường là method có code thực thi. 
4. Các lớp chỉ có thể kế thừa được 1 abstract class.
<br>

### Sự khác nhau giữa abstract và interface

 {:class="table table-bordered"}
 |  Các điểm so sánh  	|  Abstract	                    |   Interface	                                  | 
 |---	                |---	                        |---	     	                                  |
 |   Đa kế thừa 	    | Không hỗ trợ đa kế thừa	    | Một class có thể kế thừa nhiều Interface        |
 |   Defaul (mặc định) 	| Có thể định nghĩa thuộc tính , và thân phương thức có thể chứa code 	    | chỉ chứa hằng số , không có code trong phần thân method | 
 |   Access Modifier	                |   có thể đặt tất cả modifier	    |   Mọi phương thức và thuộc tính là  public	        |  
 |   Mục đích sử dụng                   |     IS  A    |    HAS A (Can do)    |

<br>
 
### Khi nào dùng abstract

1. Khả năng mở rộng không cần xoá hết code làm lại.
2. Loại những trường hợp giá trị không cần thiết trong lớp (ví dụ store id , thì không cần thiết trong online order)
Phương thức validate và process phải check kiểu order mỗi khi thực hiện busniess logic. 
Thay vì đó ta để cho lớp con kế thừa lớp abstract và tự cài đặt riêng cho mình mà ko cần phải valide và process các kiểu.
<br>

### Khi nào dùng interface

1. Mục đích chính của interface là dùng cho tính đa hình. Khả năng thực hiện các hành động khác nhau trên các ngữ cảnh khác nhau.
2. Chúng ta muốn các lớp không liên quan với nhau liên kết lại với nhau.
3. Chúng ta muốn chú trọng vào hành động hơn lvaf về cấu trúc đối tượng.
4. Chúng ta muốn sử dụng đa thừa kế. 
<br>

### Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé . 

<center>
{% include youtubePlayer.html id=page.youtubeId1 %}
</center>
<br>

### Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé . 

<center>
{% include youtubePlayer.html id=page.youtubeId2 %}
</center>