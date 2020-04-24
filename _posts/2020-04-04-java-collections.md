---
layout: blog
title: Các collection trong Java 
slug : cac-tap-hop-trong-lap-trinh-java
category: blog
tags: [java core]
summery: Blog 5
image: /images/blog/java.png
description : Sử dụng các collection trong java 
youtubeId: 4nxuOBl5mFo
---

Chào bạn, hẳn bạn đang phân vân trong java mình có những loại collection (tập hợp nào) ? Các tập hợp đó khi nào thì nên sử dụng và nó khác nhau như thế nào.
Hôm nay anh sẽ trình bày tất cả các tập hợp mà mình hay dùng và phân biệt sự khác nhau giữa các tập hợp . 
Trước hết mình xem có những collection nào trong Java trong hình sau đây . 
<br><br>

### Các collection trong java
![Cấu trúc dự án](/images/post/collection/collection.png){:class="img-responsive"}
<br>

### List 
Là một collection có thứ tự (đôi khi còn được gọi là một chuỗi). 
List có thể chứa các phần tử trùng lặp. Thường có quyền kiểm soát chính xác vị trí các phần tử được chèn vào và có thể truy cập chúng bằng chỉ số (vị trí của chúng).

Ví dụ

{% highlight java linenos %}
List<String> list = new ArrayList<String>();
list.add("Le Vu Nguyen ");
list.add("Java ");
list.add("Collection List ");
{% endhighlight %}
<br>

### Vector 
Là một collection có thể chứa các phần tử trùng lặp.Duy trì thứ tự của phần tử được thêm vào.Vector là synchronized.

Ví dụ 
{% highlight java linenos %}
Vector<String> list3 = new Vector<String>();
        list3.add("Le Vu Nguyen ");
        list3.add("Collection");
{% endhighlight %}
<br>

### Set 
Là  một collection không thể chứa 2 giá trị trùng lặp.

Ví dụ
{% highlight java linenos %}
 Set<Integer> hashsetInteger = new HashSet<>();
    hashsetInteger.add(1);
    hashsetInteger.add(2);
    hashsetInteger.add(3);
{% endhighlight %}    
<br>    
    
### Queue (hàng đợi): 
Là một collection được sử dụng để chứa nhiều phần tử trước khi xử lý. Bên cạnh các thao tác cơ bản của collection, Là tập hợp cho phép các phần tử trùng lặp, Không cho phép phần tử null
Queue cung cấp các thao tác bổ sung như chèn, lấy ra và kiểm tra. Queue có thể được sử dụng như là FIFO (first-in, first-out - vào trước, ra trước).

Ví dụ
 {% highlight java linenos %}   
    Queue<String> names = new LinkedList<String>();
    names.add("Le Vu Nguyen");
    names.add("Qu");
{% endhighlight %}  
<br>

### Deque 
Là một collection cung cấp các thao tác bổ sung như chèn, lấy ra và kiểm tra. Deques có thể được sử dụng như là FIFO (first-in, first-out - vào trước, ra trước) và LIFO (last-in, first-out - vào sau, ra trước). 
Trong một Deque, tất cả các phần tử mới có thể được chèn vào, lấy ra và lấy ra ở cả hai đầu.

Ví dụ
 {% highlight java linenos %}   
    Deque<String> deque = new LinkedList<String>(); 
        deque.add("Nguyên "); // add vào đuôi 
        deque.addFirst("Le Vu "); 
        deque.addLast("Deque"); 
        deque.push("Name   (Head)"); //add vào đầu 
        deque.offer("Age  5 (Tail)"); 
{% endhighlight %}
<br>

### Map
Là một đối tượng ánh xạ mỗi key tương úng với một giá trị. Map không thể chứa giá trị trùng lặp. Mỗi key có thể ánh xạ đến nhiều nhất một giá trị.

Ví dụ

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

### Phân biệt Collection vs Collections

1. Collections trong java là kiến trúc để lưu trữ và thao tác tới nhóm các đối tượng. Tất cả các hoạt động mà bạn thực hiện trên một dữ liệu như tìm kiếm, phân loại, chèn, xóa,... có thể được thực hiện bởi Java Collections.

2. Collection trong java là một root interface trong hệ thống cấp bậc Collection. Java Collection cung cấp nhiều interface (Set, List, Queue, Deque vv) và các lớp (ArrayList, Vector, LinkedList, PriorityQueue, HashSet, LinkedHashSet, TreeSet vv).
<br>

### Sự khác nhau  Array và ArrayList
1. Array 
    * là fix size , cố định số lượng phần tử trong mảng
    * Có thể lưu trữ dữ liệu kiểu nguyên thủy và đối tượng.
    * Tốc độ lưu trữ và thao tác nhanh hơn.
    * Chỉ có thuộc tính length
2. ArrayList 
    * Số lượng phần tử co giản được 
    * Chỉ có thể lưu trữ dữ liệu kiểu đối tượng. Kể từ Java 5, kiểu nguyên thủy được tự động chuyển đổi trong các đối tượng được gọi là auto-boxing.
    * Tốc độ lưu trữ vào thao tác chậm hơn.
    * Có nhiều phương thức để thao tác với dữ liệu.
<br>

### Sự khác nhau Set và List
* List các phần tử có thể trùng lặp
* Set các phần tử không trung lặp
<br>

### Sự khác nhau  ArrayList và Vector
1. ArrayList
    * ArrayList là KHÔNG synchronized
    * ArrayList tăng kích thước của nó bằng 50% kích thước mảng.

2. Vector 
    * Vector là synchronized.
    * Vector tăng kích thước của nó bằng cách nhân đôi kích thước mảng.
<br>
   
### Sự khác nhau ArrayList và LinkedList 
1. ArrayList
    * ArrayList sử dụng một mảng động
    * ArrayList là tốt hơn để lưu trữ và lấy dữ liệu
    
2. LinkedList 
    * LinkedList sử dụng danh sách liên kết doubly
    * LinkedList là tốt hơn để thao tác dữ liệu
<br>

### Sự khác nhau HashSet và TreeSet là gì
HashSet không duy trì thứ tự nào, trong khi TreeSet duy trì thứ tự tăng dần
<br>

### Sự khác biệt giữa HashSet và HashMap là gì?
HashSet chỉ chứa giá trị, trong khi HashMap chứa cặp key và value.
<br>

### Sự khác biệt giữa HashMap và TreeMap là gì
HashMap duy trì không có thứ tự, trong khi TreeMap duy trì thứ tự tăng dần.
<br>

### Sự khác biệt giữa Sự khác nhau giữa HashMap và Hashtable là gì
1. HashMap
    * HashMap là KHÔNG synchronized
    * HashMap có thể chứa một khóa null và nhiều giá trị null.
2. Hashtable
    * Hashtable là synchronized.
    * Hashtable không thể chứa bất kỳ khóa null hoặc giá trị null.
<br>
    
### Sự khác nhau Set và Map  là gì
Set chỉ chứa giá trị, trong khi Map chứa cặp key và value.
<br>

### Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé . 
<p align="center">
{% include youtubePlayer.html id=page.youtubeId %}
<p>