---
layout: course-java
title: Khai báo biến trong lập trình java
slug : khai-bao-bien-trong-lap-trinh-java
category: laptrinhjava
tags: [java core]
summery: Biến  
image: /images/blog/java.png

description : Bài viết cung cấp thông tin chi tiết về Biến trong <b>lập trình Java</b>, giúp bạn hiểu rõ Biến là gì? Có các loại Biến nào trong ngôn ngữ lập trình Java? Đồng thời với các ví dụ cụ thể trong bài viết giúp bạn tiếp cận kiến thức lập trình Java căn bản này dễ dàng hơn và nhanh chóng áp dụng vào thực hành.
youtubeId: fR05ShUphxA
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trong ngôn ngữ lập trình nói chung và <b>ngôn ngữ lập trình Java</b> nói riêng. Biến là một trong những kiến thức nền tảng mà mỗi người học cần trang bị cho bản thân. Tuy nhiên hiện nay vẫn còn hạn chế các trang cung cấp các kiến thức lập trình Java căn bản này một cách đầy đủ và thiết thực cho người học. Vì vậy đó chính là lí do bài viết này ra đời, với mục đích nhằm giúp các bạn có thêm nguồn tham khảo trong quá trình học. Bài viết cung cấp thông tin chi tiết về Biến trong <b>lập trình Java</b>, giúp bạn hiểu rõ Biến là gì? Có các loại Biến nào trong ngôn ngữ lập trình Java? Đồng thời với các ví dụ cụ thể trong bài viết giúp bạn tiếp cận kiến thức lập trình Java căn bản này dễ dàng hơn và nhanh chóng áp dụng vào thực hành.
youtubeId: fR05ShUphxA

<br>
## **1. Biến trong lập trình java là gì**

Trong lập trình chúng ta sử dụng biến để lưu lại giá trị để thao tác. Anh lấy ví dụ mình muốn phát triển chương trình quản lý sinh viên thì các giá trị của sinh viên như tên, tuổi, địa chỉ và mã số sinh viên thì mình cần có một cái để lưu lại cho chương trình sử lý. Cái mà lưu lại các giá trị đó gọi là biến.

## **2. Các loại biến trong ngôn ngữ lập trình java**

Trong lập trình Java ta có các loại biến sau.

- String  : dùng để lưu các giá trị chuỗi ví dụ như tên sinh viên là Nguyễn Văn A
- int     : dùng để lưu các giá trị số ví dụ như số điện thoại 0903049583
- float   : dùng để lưu các giá trị số thập phân như tiền tệ 1.000.500 VND
- char    : dùng để lưu 1 ký tự ví dụ ký tự a hoặc b
- boolean : dùng để lưu giá trị đúng hay sai.

 ## **3. Khai báo biến trong lập trình java**

Chúng ta khai báo biến với cú pháp như sau

{% highlight java  %}

type variable = value;

{% endhighlight %}

- type     : là loại biến có thể là String, int , float, char hoặc boolean
- variable : là tên của biến
- value    : giá trị của biến

Ví dụ ta tạo một biến tên là name và chứa giá trị là "Le Vu Nguyen"

{% highlight java  %}

String name = "Le Vu Nguyen";

{% endhighlight %}

Hoặc trong trường hợp này anh tạo một biến có tên là phoneNumber và gán giá trị là 15 cho nó. 

{% highlight java  %}

int phoneNumber = 15;

{% endhighlight %}

Chú ý nếu chúng ta giá gán giá trị mới cho giá trị cũ thì nó sẽ ghi đè lên giá trị cũ. Ví dụ lúc đầu anh gán giá trị num=15 nhưng sau đó anh đổi thành num=20 thì giá trị cuối cùng của num là 20

{% highlight java  %}

int num = 15;
num = 20;  // myNum is now 20
System.out.println(myNum);

{% endhighlight %}

Biến được gán với từ khoá final thì giá trị sẽ không được thay đổi và gán giá trị mới. Trong ví dụ bên dưới anh tạo biến num với từ khoá final và gán giá trị là 15. Nếu anh gán lại giá trị 20 thì sẽ xảy ra lỗi, vì final là từ khoá mình dùng khai báo khi muốn giá trị đó là không thể thay đổi.

{% highlight java  %}

final int num = 15;
num = 20;

{% endhighlight %}

 ## **4. Hiển thị giá trị trong biến trong ngôn ngữ lập trình java**

 Để hiển thị giá trị trong biến ta sử dụng hàm println()

{% highlight java  %}

String name = "John";
System.out.println("Hello " + name);

{% endhighlight %}

Chúng ta có thể dùng dấu + để kết hợp 2 biến lại với nhau và in ra kết quả

{% highlight java  %}

String firstName = "Le ";
String lastName = "Vu Nguyen";
String fullName = firstName + lastName;
System.out.println(fullName);

{% endhighlight %}

Chúng ta có thể khai báo nhiều biến trên cùng 1 dòng. Nhưng trong thực tế lập trình anh ít khi làm vậy vì không đẹp code

{% highlight java  %}

int x = 5, y = 6, z = 50;
System.out.println(x + y + z);

{% endhighlight %}





