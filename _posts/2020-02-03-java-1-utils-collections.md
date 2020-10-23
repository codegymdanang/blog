---
layout: course-java
title: Sử dụng Collections trong lập trình java
slug : su-dung-collections-trong-lap-trinh-java
category: laptrinhjava
tags: [java core]
summery: Tiện ích Collections
image: /images/blog/java.png
featureImage: /images/post/javacore/feature_collection.png
description : Hướng dẫn để sử dụng được Collections trong lập trình Java. Bài viết hướng dẫn cách sử dụng các phương thức được xây dựng sẵn trong Collections. Nhằm phục vụ trong quá trình làm việc với các tập hợp trong lập trình Java. Trong bài phạm vi bài viết này, anh sẽ giới thiệu những phương thức được sử dụng phổ biến nhất hiện nay trong lập trình Java. Bao gồm phương thức addAll, BinarySearch, Copy, Reverse, Shuffle, Sort, ReplaceAll.
youtubeId: GXQn39fU2Kg
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ giới thiệu với các em về cách sử dụng các phương thức được xây dựng sẵn trong <b>Collections</b>. Nhằm phục vụ trong quá trình làm việc với các tập hợp trong <b>lập trình Java</b>. Trong bài phạm vi bài viết này, anh sẽ giới thiệu những phương thức được sử dụng phổ biến nhất hiện nay trong <b>lập trình Java</b>. Bao gồm phương thức addAll, BinarySearch, Copy, Reverse, Shuffle, Sort, ReplaceAll.

<br>
## **1. Phương thức addAll**

Chúng ta sử dụng phương thức addAll để add một hoặc nhiều phần tử vào trong một list có sẳn như sau

{% highlight java linenos %}

List<String> list = new ArrayList<>();
Collections.addAll(list, "element 1", "element 2", "element 3");

{% endhighlight %}

<br>
## **2. Phương thức BinarySearch**

Chúng ta sử dụng binary search dùng để tìm kiếm phần tử trong List và sử dụng thuật toán Binary Search để tìm phần tử. Khi chúng ta áp dụng binary search cho List thì bắt buộc List phải được sắp xếp trước khi sử dụng Binary Search.

{% highlight java linenos %}

List<String> list = new ArrayList<>();
list.add("one");
list.add("two");
list.add("three");
list.add("four");
list.add("five");

Collections.sort(list);

int index = Collections.binarySearch(list, "four");

System.out.println(index);

{% endhighlight %}

- Chúng ta sử dụng method Collections.sort(list) để sắp xếp các phần tử trong List.
- Ở ví dụ trên chúng ta tìm kiếm từ four trong tập hợp list bằng cách sử dụng phương thức Collections.binarySearch

<br>
## **3. Phương thức Copy**

Chúng ta sử dụng phưogn thức Copy để copy tất cả các giá trị từ một list vào một list khác.

{% highlight java linenos %}

List<String> source = new ArrayList<>();
Collections.addAll(source, "e1", "e2", "e3");

List<String> destination = new ArrayList<>();
Collections.copy(destination, source);

{% endhighlight %}

- Chúng ta sử dụng hàm Collections.copy để copy.

<br>
## **4. Phương thức Reverse**

Chúng ta muốn thực hiện đảo ngược thứ tự vị trí trong các phần tử trong List thì sử dụng phương thức reverse() như sau

{% highlight java linenos %}

List>String< list = new ArrayList<String>();

list.add("one");
list.add("two");
list.add("three");

Collections.reverse(list);

{% endhighlight %}

- Kết qủa in ra sẽ là 3,2,1

<br>
## **5. Phương thức shuffle**

Chúng ta muốn xáo trộn các phần tử trong List thì sử dụng phương thức shuffle như sau

{% highlight java linenos %}

public class GFG 
{ 
    public static void main(String[] args) 
    { 
        ArrayList<String>  mylist = new ArrayList<String>(); 
        mylist.add("code"); 
        mylist.add("quiz"); 
        mylist.add("geeksforgeeks"); 
        mylist.add("quiz"); 
        mylist.add("practice"); 
        mylist.add("qa"); 
  
        System.out.println("Original List : \n" + mylist); 
  
        Collections.shuffle(mylist); 
  
        System.out.println("\nShuffled List : \n" + mylist); 
    } 
} 

Original List : 
[code, quiz, geeksforgeeks, quiz, practice, qa]

Shuffled List : 
[qa, quiz, practice, code, quiz, geeksforgeeks]

{% endhighlight %}

<br>
## **6. Phương thức Sort**

Dùng đề sắp xếp thứ tự các phần tử trong một List như sau

{% highlight java linenos %}

List>String< list = new ArrayList<String>();

list.add("one");
list.add("two");
list.add("three");
list.add("four");

Collections.sort(list);


{% endhighlight %}

<br>
## **7. Phương thức ReplaceAll**

Chúng ta sử dụng ReplaceAll để thay thế các phần tử có sẳn trong List bằng một phần tử khác.

{% highlight java linenos %}

List source = new ArrayList();
source.add("A");
source.add("B");
source.add("A");

boolean replacedAny = source.replaceAll(source, "A", "C");

{% endhighlight %}

- Kết quả ta nhận được sẽ là C,B,C
















