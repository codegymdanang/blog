---
layout: blog
title: Tham trị và tham chiếu
slug : tham-tri-va-tham-chieu-trong-lap-trinh-java
category: laptrinhjava
tags: [java core]
summery: Blog 2
image: /images/blog/java.png
description : Tham trị và tham chiếu trong lập trình 
youtubeId: 0F_8a5_fKno
---

Chào các bạn, chắc chắn không ý bạn nhầm lẫn khái niệm tham trị và tham chiếu  ? Có rất nhiều bạn có nhận định chưa đúng về khái niệm 
Ví dụ như các bạn nói các tham số trong hàm nếu ta truyền kiểu nguyên thuỷ thid đó là tham trị còn nếu truyền kiểu object là tham chiếu. 
Hôm nay anh sẽ giải thích cho các bạn hiểu rõ 2 khái niệm này nhé . 
<br><br>

### Gán giá trị 
Trước hết chúng ta hiểu xem giá trị được gán như thế nào cho biến.
![Gán giá trị](/images/post/javacore/gangiatri.png){:class="img-responsive"}
<br>

### Truyền tham trị (pass by value) 

Tham trị Pass by value : nghĩa là mình sẽ clone (tạo ra một giá trị mới bằng cách copy giá trị gốc), và mình chỉ thao táo giá trị với bản copy. 
Khi chúng ta thay đổi các giá trị của đối tượng, thì không ảnh hưởng đến giá trị gốc. Pass-by-value được hiểu là khi bạn thay đổi biến trong hàm thì ngoài hàm sẽ không bị ảnh hưởng. 
Nó giống như bạn copy giá trị của biến vào biến khác rồi truyền vào hàm.

![Tham trị](/images/post/javacore/passbyvalue.png){:class="img-responsive"}

Ở ví dụ trên ta thấy rất rõ giá trị của biến  someValue 
Ở hàm main chúng ta khai báo nó là giá trị 7 . Sau đó ta gọi hàm process(int value) và truyền giá trị 7 vào. 
Mặc dù ta gián lại giá trị someValue = 10 . Nhưng khi kết thúc hàm process thì giá trị someValue là bằng 7 chứ không phải là 10.
Bởi vì chúng ta chỉ thao tác với giá trị copy chứ không phải giá trị gốc , nên ta gán someVaule = 10 là gián cho giá trị copy = 10.
Như vậy dù trong hàm process(int value ) ta có thay đổi giá trị như thế nào đi chăng nữa thì lúc thoát ra khỏi hàm process(int value) giá trị
gốc vẫn không thay đổi .

![Tham trị](/images/post/javacore/passbyvalue2.png){:class="img-responsive"}

Sau khi hàm process(int value) thực hiện xong nhiệm vụ của mình , thì sẽ bị giải phóng đi , trả lại bộ nhớ cho chương trình , giá trị clone 
(copy) cũng được giải phóng trả lại bộ nhớ.
<br>

### Truyền tham  chiếu
Pass by reference (Truyền tham chiếu) : Ngược lại với Pass by value . Giá trị gốc sẽ bị thay đổi Pass-by-reference là khi bạn thay đổi biến trong hàm cũng làm ngoài hàm bị ảnh hưởng. Nó giống như bạn truyền đúng địa chỉ của biến đó vào hàm.

![Tham trị](/images/post/javacore/passbyreference.png){:class="img-responsive"}

Trong trường hợp này hàm process(int &value) trỏ thằng tới địa chỉ vùng nhớ nơi lưu giá trị 7. Như vậy khi ta thay đổi giá trị trong hàm nó thay 
đổi luôn giá trị khác .
<br>

# Các bạn nên nhớ trong  Java là 100% truyền tham trị (passed by value) nhé 



