---
layout: course-java
title: Phân biệt String, String Buffer và String Builder trong lập trình Java
slug : phan-biet-string-stringbuffer-va-stringbuilder-trong-lap-trinh-java
category: laptrinhjava
tags: [java core]
summery: Phân biệt String vs String Buffer vs String Builder
image: /images/blog/java.png
featureImage: /images/post/javacore/feature_exception.png
description : Phân biệt String vs String Buffer vs String Builder trong ngôn ngữ lập trình java. Chúng ta sẽ tìm hiểu Phân biệt String vs String Buffer vs String Builder là gì. Cách sử dụng Phân biệt String vs String Buffer vs String Builder trong ngôn ngữ lập trình.

youtubeId: se9CcJKhi04
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay chủ đề của chúng ta là <b>Phân biệt String vs String Buffer vs String Builder </b> trong java. Chúng ta sẽ đi qua mục đích sử dụng và ưu điểm của các loại String trên


## **1. String trong lập trình Java**

- Trong <b>lập trình Java</b>, <b>String</b> là đại diện cho một chuỗi các ký tự. Chúng ta có 2 cách khởi tạo như sau :

{% highlight java linenos %}

String str = "ABC";
// or 
String str = new String("ABC");

{% endhighlight %}

- Các giá trị trong String là immutable (có nghĩa là không thay đổi được hay còn gọi là bất biến). Chính vì vậy ta có thể share (chia sẽ) trong các function của java mà không sợ giá trị bị thay đổi.

- Khi chúng ta tạo String với dấu "" ví dụ như String str = "le vu nguyen". Thì lúc này JVM sẽ tìm kiếm trên Spring Pool nếu đã có giá trị tồn tại thì nó sẽ trả về một tham chiếu của đối tượng đã có trên spring pool. Nếu không có giá trị trên Spring Pool thì nó sẽ tạo mới một đối tượng String trên Spring Pool và trả về tham chiếu của đối tượng đó. JMV sẽ giúp chúng ta tiết kiệm được khá nhiều bộ nhớ bằng việc trả về tham chiếu của những String đã có sẳn trên Spring Pool.

- Nếu chúng ta dùng toán tử new để tạo đối tượng thì nó được lấy ra từ bộ nhớ Heap.

- Chúng ta sử dụng toán tử + để nối 2 hoặc nhiều chuỗi String lại với nhau  

## **2. Phân biệt String vs StringBuffer**

Như đã nói trong phần 1. String là immutable do vậy chúng ta không thể thay đổi được giá trị của nó. Nếu chúng ta muốn thay đổi String ví dụ như nối chuỗi, cắt string thành từng đoạn. Thì chúng ta sẽ phải tạo ra một String mới và không sử dụng lại được giá trị String cũ. Giá trị String cũ sẽ bị bộ dọn rác garbage collection của Java xoá đi khỏi bộ nhớ.

Chính vì giá trị cũ tồn tại nhiều trong bộ nhớ mỗi lần chúng ta muốn thao tác với String dẫn đến bộ nhớ sẽ bị đầy do chứa nhiều giá trị rác. Để giải quyết được việc này Java cung cấp cho chúng ta 2 lớp là StringBuffer và StringBuilder để phục vụ mục đích thao tác với String. 

Khác với String hai lớp StringBuffer và StringBuilder là mutable (có thể thay đổi giá trị). 2 lớp này cung cấp cho chúng ta các method để thêm , sửa, xoá để thao tác với String.

## **3. Phân biệt StringBuilder vs StringBuffer**

Trong quá khứ StringBuffer là sự lựa chọn duy nhất được sử dụng để thao tác với String cho đến version của java là 1.4. Điểm bất lợi duy nhất khi sử dụng StringBuffer đó chính là performance (hiệu suất) khi sử dụng StringBuffer thì xử lý rất chậm. Nguyên nhân là tất cả các method trong StringBuffer là bất đồng bộ và sử dụng cơ chế thread safe (luồng an toàn) vì vậy mà quá trình sử lý phải chờ đợi lẫn nhau gây ra tình trạng sử dụng StringBuffer thì chậm.

Kể từ Java version 1.5 trở đi thì cung cấp cho chúng ta 1 class mới là StringBuilder có chức năng tương tự như StringBuffer nhưng đã loại bỏ những nhược điểm của StringBuffer như đồng bộ và luồng an toàn. Do vậy sử dung StringBuilder sẽ nhanh hơn 


{% highlight java linenos %}

import java.util.GregorianCalendar;

public class TestString {

  public static void main(String[] args) {
    System.gc();
    long start=new GregorianCalendar().getTimeInMillis();
    long startMemory=Runtime.getRuntime().freeMemory();
    StringBuffer sb = new StringBuffer();
    //StringBuilder sb = new StringBuilder();
    for(int i = 0; i<10000000; i++){
      sb.append(":").append(i);
    }
    long end=new GregorianCalendar().getTimeInMillis();
    long endMemory=Runtime.getRuntime().freeMemory();
    System.out.println("Time Taken:"+(end-start));
    System.out.println("Memory used:"+(startMemory-endMemory));
  }
}

{% endhighlight %}

- Kết quả

{:class="table table-bordered"}
|  Giá trị i           |  StringBuffer (thời gian)      |   StringBuider (thời gian)     |
|---                   |---                             |---                              |
| 1.000.000            | 808,149356704                  |  633,149356704                  |
| 10.000.000           | 7448,147783888                 |  6179,147783888                 |


## **4. Kết luận**

Tuỳ vào mục đích sử dụng trong <b>lập trình Java</b>, mà ta chọn <b>String</b> hoặc <b>StringBuffer</b> hoặc <b>StringBuilder</b>. Nếu chương trình mình có nhiều thread(tiến trình) cùng thao tác đến String thì mình sẽ chọn StrungBuffer vì nó hỗ chợ cơ chế thread safe còn nếu không cần thread safe thì ta chọn StringBuilder.









