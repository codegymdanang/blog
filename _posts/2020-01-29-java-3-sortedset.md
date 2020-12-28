---
layout: course-java
title: Sử dụng SortedSet trong lập trình Java
slug : su-dung-sortedset-trong-lap-trinh-java
category: laptrinhjava
tags: [java core]
summery: SortedSet
image: /images/blog/java.png
featureImage: /images/post/javacore/feature_collection.png
description : Trong bài này, anh sẽ trình bày về SortedSet trong lập trình Java. Trước hết cần tìm hiểu SortedSet, tập hợp SortedSet là gì? Các phương thức có trong SortedSet. Hướng dẫn cách thêm và xoá một phần tử khỏi SortedSet. Hay cách làm như thế nào đế lấy phần tử đầu tiên hay cuối cùng trong SortedSet. Áp dụng được từ những chia sẻ trong bài viết để giải quyết các vấn đề khác bao gồm duyệt, sắp xếp các phần tử SortedSet. Cũng như cách để lấy các phần tử đầu và sau của SortedSet trong lập trình hướng đối tượng Java.
youtubeId: mwrlKKqmiSw
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chủ đề hôm nay anh chọn để chia sẻ cho các bạn sẽ về <b>SortedSet trong lập trình Java</b>. Đây được xem là một trong những kiến thức lập trình Java căn bản mà bất cứ một lập trình viên Java nào cũng cần nắm vững. Trước hết chúng ta cần tìm hiểu SortedSet, tập hợp SortedSet là gì? Sau đó, cùng tìm hiểu các phương thức có trong SortedSet. Anh sẽ hướng dẫn các bạn cách thêm và xoá một phần tử khỏi SortedSet. Hay cách làm như thế nào đế lấy phần tử đầu tiên hay cuối cùng trong SortedSet. Áp dụng được từ những chia sẻ trong bài viết để giải quyết các vấn đề khác bao gồm duyệt, sắp xếp các phần tử SortedSet. Cũng như cách để lấy các phần tử đầu và sau của SortedSet trong <b>lập trình hướng đối tượng Java</b>.

## **1. SortedSet trong lập trình Java là gì**

<b>SortedSet</b> là một interface con của Set nó có đủ các chức năng mà Set có như giới thiệu ở bài trước. Ngoài ra có một cái đặt biệt đó là tất cả phần tử trong SortedSet là đều được sắp xếp theo một thứ tự, một trật tự nhất định là sắp xếp tăng dần hay giảm dần. 

## **2. Tập hợp SortedSet**

- Tập hợp TreeSet là lớp thực thi implementation interface SortedSet. Chúng ta khai báo TreeSet như sau

{% highlight java linenos %}

  SortedSet sortedSet = new TreeSet();

{% endhighlight %}

## **3. Thêm một phần tử vào SortedSet**

{% highlight java linenos %}

 SortedSet sortedSet = new TreeSet();

 sortedSet.add("one");

{% endhighlight %}

## **4. Xoá một phần tử ra khỏi SortedSet**

{% highlight java linenos %}

sortedSet.remove("one");

{% endhighlight %}

## **5. Lấy phần tử đầu tiên SortedSet**

{% highlight java linenos %}

Object firstElement = sortedSet.first();

{% endhighlight %}

## **6. Lấy phần tử cuối cùng SortedSet**

{% highlight java linenos %}

Object lastElement = sortedSet.last();

{% endhighlight %}

## **7. Duyệt các phần tử SortedSet**

{% highlight java linenos %}

SortedSet sortedSet = new TreeSet();

sortedSet.add("one");
sortedSet.add("two");
sortedSet.add("three");

Iterator iterator = sortedSet.iterator();
while(iterator.hasNext()) {
    String element = (String) iterator.next();
    System.out.println(element);
}

{% endhighlight %}

## **8. Sắp xếp các phần tử SortedSet**

Mặc định tính năng sắp xếp các phần tử (Sort) là sort theo thứ tự tăng dần. Tuy nhiên chúng ta có thể tự viết ra một thuật toán so sánh khác bằng việc truyền vào một Comparator do chính chúng ta viết vào constructor của TreeSet như sau.

 {% highlight java linenos %}

Comparator comparator = new MyComparator();

SortedSet sortedSet = new TreeSet(comparator);

{% endhighlight %}

- Khi chúng ta duyệt qua các phần tử trong TreeSet mặt định nó sẽ duyệt từ nhỏ đến lớn. Chúng ta cũng có thể nói TreeSet duyệt ngược lại từ lớn đến nhỏ thông qua phương thức descendingIterator như sau

 {% highlight java linenos %}

TreeSet treeSet = new TreeSet();

treeSet.add("one");
treeSet.add("two");
treeSet.add("three");

Iterator iterator = treeSet.descendingIterator();
while(iterator.hasNext()) {
    String element = (String) iterator.next();
    System.out.println(element);
}

{% endhighlight %}

## **9. Lấy các phần tử đầu SortedSet**

- SortedSet cung cấp cho chúng ta phương thức headSet() trả về một SortedSet mới với tất cả các phần tử nhỏ hơn phần tử truyền vào. Ví dụ anh có tập hợp là a,b,c,d,e. Khi anh truyền vào chữ c thì nó sẽ trả cho anh về một SortedSet mới là a và b vì a và b là nhỏ hơn giá trị c mà anh truyền vào.

 {% highlight java linenos %}

SortedSet sortedSet = new TreeSet();

sortedSet.add("a");
sortedSet.add("b");
sortedSet.add("c");
sortedSet.add("d");
sortedSet.add("e");

SortedSet headSet = sortedSet.headSet("c");

{% endhighlight %}

## **10. Lấy các phần tử sau SortedSet**

- SortSet cung cấp phương thức tailSet trả về một SortedSet mới với tất cả các giá trị lớn hơn và bằng giá trị truyền vào . Cũng như ví dụ trên a có tập hợp là a,b,c,e,d. Khi anh truyền vào chữ c thì anh sẽ nhận được SortedSet mới là c,d,e

 {% highlight java linenos %}

SortedSet sortedSet = new TreeSet();

sortedSet.add("a");
sortedSet.add("b");
sortedSet.add("c");
sortedSet.add("d");
sortedSet.add("e");

SortedSet tailSet = sortedSet.tailSet("c");

{% endhighlight %}



{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}
















