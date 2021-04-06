---
layout: course-java
title: Sử dụng các tập hợp trong lập trình Java
slug : su-dung-cac-tap-hop-trong-lap-trinh-java
category: laptrinhjava
tags: [java core]
summery: Tổng hợp các tập hợp
image: /images/blog/java.png
featureImage: /images/post/javacore/feature_collection.png
description : Hướng dẫn để sử dụng được các tập hợp (collection) trong lập trình Java. Bài viết trình bày, giải thích các khái niệm collection trong học lập trình Java. Cách sử dụng các tập hợp như List , Vector , Set , Queue, Deque, Map. Giúp phân biệt giữa các tập hợp và áp dụng được khi nào nên dùng tập hợp nào là phù hợp trong Java cơ bản.
youtubeId: GXQn39fU2Kg
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, trong những bài trước anh đã giới thiệu về các tập hợp trong lập trình Java bao gồm List , Vector, Set, Queue, Deque, Map.  

<br>
Bài viết hôm nay anh sẽ tổng hợp lại các <b>tập hợp trong bộ Java Collection </b> mà chúng ta thường xuyên sử dụng trong <b>lập trình Java</b>. Phân biệt sự khác nhau giữa các tập hợp và giúp các em nhận biết được khi nào thì nên sử dụng chúng. Anh cũng sẽ trình bày về phần performance (hiệu năng) cũng như từng loại tập hợp giúp các em có thể tìm ra được tập hợp tốt nhất để áp dụng vào cho bài toán của mình trong quá trình code các chương trình <b>lập trình hướng đối tượng Java</b>.


<br>
## **1. Các collection trong lập trình java**

{:refdef: style="text-align: center;"}
![collection](/images/post/collection/collection.png){:class="img-responsive"}
{: refdef}

<br>
## **2. List**

Là một <b>cấu trúc dữ liệu</b> có thứ tự (đôi khi còn được gọi là một chuỗi).
<b>List có thể chứa các phần tử trùng lặp</b>. Thường có quyền kiểm soát chính xác vị trí các phần tử được chèn vào và có thể truy cập chúng bằng chỉ số (vị trí của chúng).

{% highlight java linenos %}
List<String> list = new ArrayList<String>();
list.add("Le Vu Nguyen ");
list.add("Java ");
list.add("Collection List ");
{% endhighlight %}

<br>
## **3. Vector**

Là một <b>cấu trúc dữ liệu</b> có thể chứa các phần tử trùng lặp. Duy trì thứ tự của phần tử được thêm vào. Vector là synchronized.

{% highlight java linenos %}
Vector<String> list3 = new Vector<String>();
        list3.add("Le Vu Nguyen ");
        list3.add("Collection");
{% endhighlight %}

<br>
## **4. Set**

Là một <b>cấu trúc dữ liệu</b> không thể chứa 2 giá trị trùng lặp.

{% highlight java linenos %}
 Set<Integer> hashsetInteger = new HashSet<>();
    hashsetInteger.add(1);
    hashsetInteger.add(2);
    hashsetInteger.add(3);
{% endhighlight %}    

<br>
## **5. Queue (hàng đợi)**

Là một <b>cấu trúc dữ liệu</b> được sử dụng để chứa nhiều phần tử trước khi xử lý. Bên cạnh các thao tác cơ bản của collection, Là tập hợp cho phép các phần tử trùng lặp, Không cho phép phần tử null
Queue cung cấp các thao tác bổ sung như chèn, lấy ra và kiểm tra. Queue có thể được sử dụng như là FIFO (first-in, first-out - vào trước, ra trước).

{% highlight java linenos %}   
    Queue<String> names = new LinkedList<String>();
    names.add("Le Vu Nguyen");
    names.add("Qu");
{% endhighlight %}  

<br>
## **6. Deque**

Là một <b>cấu trúc dữ liệu</b> cung cấp các thao tác bổ sung như chèn, lấy ra và kiểm tra. <b>Deque</b> có thể được sử dụng như là FIFO (first-in, first-out - vào trước, ra trước) và LIFO (last-in, first-out - vào sau, ra trước).
Trong một Deque, tất cả các phần tử mới có thể được chèn vào, lấy ra và lấy ra ở cả hai đầu.

{% highlight java linenos %}   
    Deque<String> deque = new LinkedList<String>();
        deque.add("Nguyên "); // add vào đuôi
        deque.addFirst("Le Vu ");
        deque.addLast("Deque");
        deque.push("Name   (Head)"); //add vào đầu
        deque.offer("Age  5 (Tail)");
{% endhighlight %}

<br>
## **7. Map**

Là một đối tượng ánh xạ mỗi key tương ứng với một giá trị. <b>Map</b> không thể chứa giá trị trùng lặp. Mỗi key có thể ánh xạ đến nhiều nhất một giá trị.

{% highlight java linenos %}
Map<Integer, String> hashMap = new HashMap<>();
    hashMap.put(1, "One");
    hashMap.put(0, "Zero");
    hashMap.put(2, "Two");
    hashMap.put(4, "Four");
    hashMap.put(21, "Twenty first");
    hashMap.put(5, "Five");
{% endhighlight %}

<br>
## **8. Phân biệt Collection vs Collections**

- <b>Collections trong java</b> là kiến trúc để lưu trữ và thao tác với nhóm các đối tượng. Tất cả các hoạt động mà bạn thực hiện trên một dữ liệu như tìm kiếm, phân loại, chèn, xóa,... có thể được thực hiện bởi Java Collections.

- <b>Java Collection</b> cung cấp nhiều interface (Set, List, Queue, Deque vv) và các lớp (ArrayList, Vector, LinkedList, PriorityQueue, HashSet, LinkedHashSet, TreeSet vv).

<br>
## **9. Sự khác nhau  Array và ArrayList**

1. Array
    * là fix size, cố định số lượng phần tử trong mảng
    * Có thể lưu trữ dữ liệu kiểu nguyên thủy và đối tượng.
    * Tốc độ lưu trữ và thao tác nhanh hơn.
    * Chỉ có thuộc tính length

2. ArrayList
    * Số lượng phần tử co giãn được
    * Chỉ có thể lưu trữ dữ liệu kiểu đối tượng. Kể từ Java 5, kiểu nguyên thủy được tự động chuyển đổi trong các đối tượng được gọi là auto-boxing.
    * Tốc độ lưu trữ vào thao tác chậm hơn.
    * Có nhiều phương thức để thao tác với dữ liệu.

<br>
## **10. Sự khác nhau Set và List**

* List các phần tử có thể trùng lặp
* Set các phần tử không trùng lặp

<br>
## **11. Sự khác nhau ArrayList và Vector**

1. ArrayList
    * ArrayList là KHÔNG synchronized
    * ArrayList tăng kích thước của nó bằng 50% kích thước mảng.

2. Vector
    * Vector là synchronized.
    * Vector tăng kích thước của nó bằng cách nhân đôi kích thước mảng.

<br>
## **12. Sự khác nhau ArrayList và LinkedList**

1. ArrayList
    * ArrayList sử dụng một mảng động
    * ArrayList nhanh hơn trong việc  trữ và lấy dữ liệu

2. LinkedList
    * LinkedList sử dụng danh sách liên kết doubly
    * LinkedList nhanh hơn trong việc thao tác dữ liệu

<br>
## **13. Sự khác nhau HashSet và TreeSet**

HashSet không duy trì thứ tự nào, trong khi TreeSet duy trì thứ tự tăng dần

<br>
## **14. Sự khác biệt giữa HashSet và HashMap**
  * HashSet với cấu trúc chứa đựng chỉ là các giá trị.
  * HashMap cấu trúc chứa đựng là key và value


<br>
## **15. Sự khác biệt giữa HashMap và TreeMap**
HashMap duy trì không có thứ tự, trong khi TreeMap duy trì thứ tự tăng dần.

<br>
## **16. Sự khác biệt giữa Sự khác nhau giữa HashMap và Hashtable**

1. HashMap
    * HashMap là KHÔNG synchronized
    * HashMap cấu trúc chỉ chứa một key null và nhiều giá trị null.

2. Hashtable
    * Hashtable là synchronized.
    * Hashtable cấu trúc không chứa bất kỳ key null hoặc giá trị null.

<br>
## **17. Sự khác nhau Set và Map**

Set chỉ chứa giá trị, trong khi Map chứa cặp key và value.

## **18. Video Demo**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **19. Source code**


{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/Java-Collections" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}
