---
layout: blog
title: Bộ  Heap va Stack
slug : phan-biet-bo-nho-heap-va-stack
category: laptrinhjava
tags: [java core]
summery: Phân Biệt Bộ Nhớ  Heap va Stack
image: /images/blog/java.png
description : Phân biệt bộ nhớ heap và stack . bộ nhớ heap là gì , bộ nhớ stack là gì , bộ nhớ trong lập trình java
youtubeId: werAdblsT1s
---

### **1. Giới thiệu nội dung bài viết**

Chào bạn, chắc hẳn bạn đang phân vân khi mình khai báo biến , object , phương thức , tham số thì nó sẽ được lưu ở đâu trong bộ nhớ phải không ?
Ai sẽ quản lý bộ nhớ ? Bài viết sau đây anh sẽ giải thích cho các bạn 2 bộ nhớ Heap và Stack lưu trữ dữ liệu gì và lưu như thế nào nhé . Các nội dung sau sẽ được trình bày
trong bài viết hôm nay

- Các thuật ngữ về bộ nhớ
- Heap và Stack là gì ?
- Bộ nhớ Heap dùng làm gì ?
- Bộ nhớ Stack dùng làm gì ?
- Giải thích về cách lưu trữ của Heap và Stack
- Video demo về Heap và Stack

<br>
### **2. Các thuật ngữ**

{:refdef: style="text-align: center;"}
![Các thuật ngữ ](/images/post/javacore/cacthuatngu.png){:class="img-responsive"}
{: refdef}

- Runtime : thời gian chạy của chương trình
- Java Heap Memory : Bộ nhớ Heap trong Java
- Java Stack Memory: Bộ nhớ Stack trong Java
- JVM : Java Virtual Machine , máy ảo Java để chạy các chương trình Java
- Object : là đối tượng được khởi tạo từ khoá new từ một class

<br>
### **3 Heap và Stack**

Java Heap và Stack Memory là một phần của bộ nhớ được JVM sử dụng để chạy chương trình Java của bạn. Khi bạn chạy chương trình Java, JVM sẽ yêu cầu hệ điều hành cấp cho một không gian bộ nhớ trong RAM để dùng cho việc chạy chương trình.
JVM sẽ chia bộ nhớ được cấp phát này thành 2 phần: Heap và Stack cho việc quản lý.

{:refdef: style="text-align: center;"}
![Heap và Stack trong Java  ](/images/post/javacore/stackandheap.png){:class="img-responsive"}
{: refdef}

<br>
### **4 Bộ nhớ Heap**

- Java Heap Memory là bộ nhớ được sử dụng ở runtime để lưu các Objects. Bất cứ khi nào ở đâu trong chương trình của bạn khi bạn tạo Object thì nó sẽ được lưu trong Heap (thực thi toán tử new).
- Các objects trong Heap đều được truy cập bởi tất cả các các nơi trong ứng dụng, bởi các threads khác nhau.
- Thời gian sống của object phụ thuộc vào Garbage Collection của java.
- Garbage Collection sẽ chạy trên bộ nhớ Heap để xoá các Object không được sử dụng nữa, nghĩa là object không được referece trong chương trình.
- Dung lượng sử dụng của Heap sẽ tăng giảm phụ thuộc vào Objects sử dụng.
- Dung lượng Heap thường lớn hơn Stack.

<br>
### **5 Bộ nhớ Stack**

- Bộ nhớ để lưu các biến local trong hàm và lời gọi hàm ở runtime trong một Thread java.
- Các biến local bao gồm loại nguyên thuỷ (primitive) và loại tham chiếu tới đối tượng trong heap (reference) khai báo trong hàm, hoặc đối số được truyền vào hàm, thường có thời gian sống ngắn.
- Bộ  nhớ stack thường nhỏ.
- Cơ chế hoạt động là LIFO (Last-In-First-Out), chạy sau chết trước.
- Bất cứ khi nào gọi 1 hàm, một khối bộ nhớ mới sẽ được tạo trong Stack cho hàm đó để lưu các biến local. Khi hàm thực hiện xong, khối bộ nhớ cho hàm sẽ bị xoá, và giải phóng bộ nhớ trong stack.
<br>

- Ví dụ về Heap và Stack

{:refdef: style="text-align: center;"}
![Ví dụ về Heap và Stack  ](/images/post/javacore/vdheapstack.png){:class="img-responsive"}
{: refdef}

{% highlight java linenos %}

public class Memory {

    public static void main (String[] args,) { // line 1
        int i = 1 ; //line 2
        Object obj = new Object(); // line 3
        Memory mem = new Memory(); // line 4
        mem.foo(obj); // line 5
    }//line 9

    private static void foo(Object param) { // line 6
        String str = param.toString(); // line 7
        System.out.println(str)// line 8
    }
}

{% endhighlight %}

- Dòng 1 phương thức public static void main sẽ lưu bên Stack (vì stack sẽ cấp phát vùng nhớ cho phương thức).
- Dòng 2 khai báo biến i = 2 thì nằm bên stack vì stack lưu các biến.
- Dòng 3 khai báo biến Object obj = new Object  thì biến obj  nằm bên stack vì stack lưu các biến còn đối tượng Object được lưu bên Heap và biến obj sẽ tham
chiếu đến đối tượng Object bên bộ nhớ Heap .
- Dòng 4 Memory mem = new Memory thì đối tượng Memory sẽ lưu bên bộ nhớ heap còn biến mem thì lưu bên bộ nhớ stack , và mem tham chiếu tới đối
tượng Memory bên Heap.
- Dòng 5  mem.foo() thì phương thức foo() được tạo ra ở dòng 5. Phương thức foo này là nằm trong phương thức main . Như ta thấy bên bộ nhớ Stack
Hình chữ nhật bự nhất bao ở ngoài là hàm main () . Bên trong hàm main là bộ nhớ phương thức foo. Khi chương trình chạy xong thì bộ nhớ foo() sẽ
được giải phóng trước sau đó mới đến main.
- Dòng 6 private void foo() thì hàm foo()  được lưu trong bộ nhó Stack.
- Dòng 7 String str = param.toString() . Trong java String là kiểu đặc biệt . Nó là kiểu Object và được quản lý bởi String Pool riêng. Chính vì vậy nó
được lưu bên Heap.

<br>
###  **6. Video demo Heap và Stack**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}
