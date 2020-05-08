---
layout: blog
title: Sự khác  giữa abstract và interface
slug : su-khac-nhau-giua-abstract-interface
category: laptrinhjava
tags: [java core]
summery: Sự khác  giữa abstract và interface
image: /images/blog/java.png
description : Sự khác  giữa abstract và interface trong java. Interface là gì ? Abstract là gì? Khi nào dùng abstract, khi nào dùng interface
youtubeId1 : t9in5g6vsSg
youtubeId2 : rUFUgrkMg4o
---

### **1. Giới thiệu nội dung bài viết**

Chào bạn, nếu bạn là người mới tìm hiểu về lập trình, hẳn bạn đã từng nghe tới khái niệm về Abstract và Interface.
Nhưng bạn có biết khi nào mình sẽ dùng abstract và khi nào mình dùng interface không? Khi mới bước chân vào
nghề lập trình a cũng rất hoang mang về công dụng và lợi ý của Abstract và Interface. Chính vì vậy anh
viết bài này nhằm giúp mọi người có cái nhìn rõ hơn khi nào mình dùng abstract và Interface. Bài viết hôm nay sẽ xoay quanh các chủ đề sau.

- Interface là gì ?
- Abstract là gì ?
- Sự khác nhau giữa Abstract và Interface
- Khi nào chúng ta nên dùng Abstract hoặc Interface
- Video demo

### **1. Interface là gì**

Interface chính là cách mình áp dụng tính trừa tượng trong lập trình. Interface chính là 100% abstract class để nhóm các phương thức liên quan với nhau và không có
phần thân. Phần thân của method sẽ được implement (cài đặt) ở trong lớp implement Interface.

{% highlight java linenos %}
// Interface
interface Animal {
  public void animalSound(); // method của Interface không có phần thân
  public void sleep(); //method của Interface không có phần thân
}

// Pig "implements"  Interface  Animal
class Pig implements Animal {
  public void animalSound() {
    // phần thân của interface sẽ được code  trong class PI
    System.out.println("The pig says: wee wee");
  }
  public void sleep() {
    // phần thân của interface sẽ được code trong class PIG
    System.out.println("Zzz");
  }
}

{% endhighlight %}

Một số chú ý khi sử dụng Interface.

- Cũng giống như Abstract Class. Chúng ta không thể tạo đối tượng từ Interface bằng toán tử new
- Interface hỉ chứa method trống không có phần thân. Phần thân sẽ được code bởi những class implement (cài đặt) interface đó
- Lớp cài đặt Interface phải implement hết tất cả các method có trong interface. Nó định nghĩa một mẫu chung các hành động mà các lớp implements nó follow theo.
- Các method trong Interface mặc định là abstract  public và
- Các biến (thuộc tính) trong Interface mặc định là public,static và final  
- Các lớp có thể cài đặt (implements) một hoặc nhiều Interface.
- Interface thì không có constructor chính vì vậy mà ta không thể tạo object của một Interface được


### **2. Abstract là gì**

Data Abstraction là quá trình che giấu đi những dữ liệu quan trọng mình chỉ đưa ra những thông tin cần thiết cho người dùng. Để làm được abstraction trong lập  ta
có thể sử dụng abstract và interface . Ta có thể sử dụng abstract cho class hoặc method .Chúng ta sử dụng từ khoá abstract để khai báo abstract class và method.

- Abstract class : cũng giống như Interface chúng ta không thể tạo đối tượng từ Abstract Class
- Abstract method : cũng giống như Interface chúng không có phần thân . Phần thân sẽ được cài đặt trong lớp kế thừa nó

{% highlight java linenos %}

// Abstract class
abstract class Animal {
  // abstract class không có phần
  public abstract void animalSound();

  // abstract class không có phần thân
  public void sleep() {
    System.out.println("Zzz");
  }
}


class Pig extends Animal {
  public void animalSound() {
    // phần code thực thi của abstract method được viết bới lớp con kế thừa nó
    System.out.println("The pig says: wee wee");
  }
}

{% endhighlight %}

### **3. Sự khác nhau giữa abstract và interface**

 {:class="table table-bordered"}
 |  Các điểm so sánh  	|  Abstract	                    |   Interface	                                  |
 |---	                |---	                        |---	     	                                  |
 |   Đa kế thừa 	    | Không hỗ trợ đa kế thừa	    | Một class có thể kế thừa nhiều Interface        |
 |   Defaul (mặc định) 	| Có thể định nghĩa thuộc tính , và thân phương thức có thể chứa code 	    | chỉ chứa hằng số , không có code trong phần thân method |
 |   Access Modifier	                |   có thể đặt tất cả modifier	    |   Mọi phương thức và thuộc tính là  public	        |  
 |   Mục đích sử dụng                   |     IS  A    |    HAS A (Can do)    |


### **4. Khi nào dùng abstract**

- Khả năng mở rộng không cần xoá hết code làm lại.
- Tăng tính bảo mật e dấu các dữ liệu quan trong ch
- Khi các lớp có mối liên hệ cha  với nhau ví dụ như con gà , chó , mèo  chúng đều là động vật (Animal)

### **5. Khi nào dùng interface**

- Mục đích chính của interface là dùng cho tính đa hình. Khả năng thực hiện các hành động khác nhau trên các ngữ cảnh khác nhau.
- Chúng ta muốn các lớp không liên quan với nhau liên kết lại với nhau.
- Chúng ta muốn chú trọng vào hành động hơn  về cấu trúc đối tượng.
- Chúng ta muốn sử dụng đa thừa kế.
- Tăng cường tính bảo mật . Người dùng chỉ có thể thấy được method nhưng không thấy được nội dung code bên trong

### **6. Demo tạo abstract**  

<center>
{% include youtubePlayer.html id=page.youtubeId1 %}
</center>
<br>

### **6. Demo tạo interface**  

<center>
{% include youtubePlayer.html id=page.youtubeId2 %}
</center>
