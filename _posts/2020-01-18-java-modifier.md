---
layout: course-java
title:  Sử dụng Access Modifier trong lập trình Java
slug :  su-dung-access-modifier-trong-lap-trinh-java
category: laptrinhjava
tags: [java core]
summery: Access Modifier
image: /images/blog/java.png
featureImage: /images/post/javacore/feature_accessmodifier.png
description : Tìm hiểu các access modifier như public , private , static, default, protected, static, final trong lập trình java. Bài viết cũng chỉ ra được tầm quan trọng của access modifier. Và ý nghĩa của mỗi từ khoá cũng như cách sử dụng mỗi access modifier khác nhau trong lập trình hướng đối tượng java. Từ đó giúp bạn biết được khi nào thì nên dùng từ khoá nào là hợp lý nhất nhằm tăng thêm tính bảo mật cho các giá trị và phương thức trong lớp khi viết các chương trình lập trình Java. 
youtubeId: J7tZ9aSzqUg
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào bạn, bạn đã từng nghe tới khái niệm về các <b>access modifier</b> trong <b>lập trình Java</b> chưa? Bài viết này sẽ giúp bạn phân biệt các loại access modifier
như public , private , protected và default. Đồng thời cũng cho bạn thấy được tầm quan trọng của access modifier. Và chỉ ra ý nghĩa của mỗi từ khoá cũng như cách sử dụng mỗi access modifier khác nhau trong <b>ngôn ngữ lập trình hướng đối tượng Java</b>. Từ đó giúp bạn biết khi nào thì nên dùng từ khoá nào là hợp lý nhất nhằm tăng thêm tính bảo mật cho các giá trị và phương thức trong lớp khi viết các <b>chương trình lập trình Java</b>. Bài viết bao gồm kèm theo một video demo hướng dẫn về access modifier trong <b>ngôn ngữ lập trình hướng đối tượng Java</b>.

## **1. Tầm quan trọng của access modifier**

Trước khi bắt đầu tìm hiểu cách sử dụng <b>access modifier</b> anh sẽ kể một câu chuyện vì sao access modifier lại quan trọng. Các đây 8 năm khi anh làm lập trình với team của anh gồm 15 <b>lập trình viên Java</b>. Bọn anh có phát triển 1 chức năng gọi là hoa hồng giao dịch. Nghĩa là khi người dùng sử dụng ứng dụng của bọn anh thanh toán mua hàng ,thì ứng dụng bọn anh sẽ thu phí là 0.001% trên mỗi lần khách hàng giao dịch.

Trong team anh lúc này có một bạn phụ trách chức năng này (anh gọi là bạn A) và khai báo biến phần trăm hoa hồng là public float hoaHong = 0.001%. Khi bạn này khai báo public nghĩa là ở đâu cũng thấy được cái biến hoaHong.

Ứng dụng chạy rất ổn trong 2 tháng đầu thì bọn anh nhận được một yêu cầu thay đổi nghiệp vụ nơi chỗ thanh toán nhận hoa hồng. Thì lúc này team anh có một bạn khác (bạn B ) phụ trách cải thiện chức năng này. Do trong quá trình làm bạn B không có sự trao đổi với bạn A dẫn đến bạn này tạo thêm một Class mới và vô tình thay đổi biển hoaHong = 0.0001%. Vì biến hoaHong là pubic nên bạn B có thể thấy và thay đổi nó. Khi bọn anh release sản phẩm được 1 tuần thì khách hàng báo về là lợi nhuận sao thấy ít vậy. Sau này bên anh điều tra mới thấy được là bạn B thay đổi giá trị hoa hồng là 0.0001% trong khi đó code của của bạn A thì vẫn lấy biết hoaHong nhưng lúc này đã bị thay đổi dẫn đến sai nghiệp vụ.

Như các em thấy qua ví dụ của anh, nếu mình không cẩn thận không khai báo đúng phạm vi của biến sẽ dẫn đến tình trạng mất tiền , ảnh hưởng nghiêm trọng đến chức năng sản phẩm. Bởi vậy trong lập trình không phải lúc nào mình cũng khai báo public như một thói quen mà mình nên suy nghĩ phạm vi , mục đích mình sử dụng các access modifier là gì?

<br>
## **2. Từ khóa public dùng làm gì**

Khi một phương thức hoặc biến được khai báo là public, có nghĩa là tất cả các class khác, kể cả các class không thuộc cùng package đều có thể truy cập.

{% highlight java  %}

public class Card {

  public int cardNumber;

}

{% endhighlight %}

<br>
## **3. Từ khóa private  dùng làm gì**

Khi một phương thức hoặc biến được khai báo là private nó sẽ không thể truy cập từ class khác, kể cả các class cùng source file hay các class con.

{% highlight java  %}

public class Card {

  private int cardNumber;

}

{% endhighlight %}

<br>
## **4. Từ khóa default  dùng làm gì**

Khi một phương thức hoặc biến được khai báo là default thì chỉ có các class thuộc cùng package với nó mới có thể truy cập.

{% highlight java  %}

public class Card {

   int cardNumber;

}

{% endhighlight %}

<br>
## **5. Từ khóa protected   dùng làm gì**

Cho phép truy cập các biến ở các class khác nhau không cùng chung một package thông qua cơ chế kế thừa.

{% highlight java  %}

public class Card {

  protected int cardNumber;

}

{% endhighlight %}

<br>
## **6. Từ khóa static dùng làm gì**

Static : khi mình muốn chia sẻ (dùng chung, và là duy nhất trong cả hệ thống) cái biến đó cho các object khác có thể sử dụng được.

{% highlight java  %}

public class Card {

  public static int cardNumber;

}

{% endhighlight %}

<br>
## **7. Từ khóa final  dùng làm gì**

Final : Khi mình muốn giá trị là <b>hằng số và không thể thay đổi được</b> (Ví dụ final double PI = 3.14).

{% highlight java  %}

public class Card {

  public final int CARNUMBER = 123123321233;

}

{% endhighlight %}

<br>
## **8. Tổng kết**

Việc sử dụng đúng scope (phạm vi) của biến rất quan trọng trong lập trình .Đối với các thuộc tính có tính bảo mật cao ta chỉ cho phép nội bộ của nó có thể thấy và thay
đổi được giá trị . Nếu ta không làm như vậy thì lớp nào cũng thấy và sẽ thay đổi giá trị đó làm cho việc kiểm soát và bảo mật không còn nữa dẫn đến chương trình chạy sai ý
định của mình , đồng thời ai cũng thấy và sẽ thay đổi được giá trị của biến

<br>
## **9. Video Demo**  

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **10. Source code**


{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/Java-Access-Modifier" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}
