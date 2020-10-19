---
layout: course-java
title: Sử dụng Deque trong lập trình Java
slug : su-dung-deque-trong-lap-trinh-java
category: laptrinhjava
tags: [java core]
summery: Deque
image: /images/blog/java.png
featureImage: /images/post/javacore/feature_collection.png
description : Deque là gì? Các phương thức có trong Deque và cách sử dụng Deque trong lập trình java
youtubeId: 5C2OqlhiYsg
---

{% include toc.html %}

# **Giới thiệu nội dung bài viết**

Chào các em, hôm nay chủ đề của chúng ta về <b>Deque</b> trong lập trình java. Khi nào thì mình sẽ sử dụng nó nhé.

# **1. Deque là gì**

Khi chúng ta sử dụng Queu  thì chúng ta chỉ được phép thêm phần tử vào sau cùng của tập hợp và lấy ra từ phần đầu của tập hợp. Trong trường hợp như anh muốn thêm bất kỳ phần tử nào có thể thêm vào trước hoặc sau của một tập hợp chứ không theo nguyên lý lúc nào cũng thêm vào sau và lấy ra đầu thì anh sẽ sử dụng Deque.

- Các Class cài đặt Deque là

+ LinkedList
+ ArrayDeque

# **2. Tạo Deque**

{% highlight java linenos %}

Deque deque = new LinkedList();

Deque deque = new ArrayDeque();

{% endhighlight %}

# **3. Thêm một phần tử vào Deque**

- Chúng ta có thể sử dụng các phương thức sau để thêm phần tử vào queue như add, addLast, addFirst, offer, offerFirst, offerLast

- Sử dụng phương thức add để thêm phần tử vào đuôi của tập hợp. Nếu không add được thì sẽ nhận kết quả là false

{% highlight java linenos %}

Deque<String> deque = new ArrayDeque<>();

deque.add("element 1");

{% endhighlight %}

- Sử dụng phương thức addLast để thêm phần tử vào đuôi của tập hợp. Nếu không add được thì sẽ nhận được ngoại lệ được ném ra

{% highlight java linenos %}

Deque<String> deque = new ArrayDeque<>();

deque.addLast("element 1");

{% endhighlight %}

- Sử dụng phương thức addFirst để thêm phần tử vào đầu của tập hợp. Nếu không thêm được sẽ nhận được lỗi ngoại lệ được ném ra

{% highlight java linenos %}

Deque<String> deque = new ArrayDeque<>();

deque.addFirst("element 1");

{% endhighlight %}

- Sử dụng offer để thêm các phần tử vào đuôi của tập hợp. Nếu tập hợp đã đầy thì sẽ nhận được kết quả false

{% highlight java linenos %}

Deque<String> deque = new ArrayDeque<>();

deque.offer("element 1");

{% endhighlight %}

- Sử dụng offerLast để thêm các phần tử vào đuôi của tập hợp

{% highlight java linenos %}

Deque<String> deque = new ArrayDeque<>();

deque.offerLast("element 1");

{% endhighlight %}

- Sử dụng offerFirst để thêm các phần tử vào phần đầu của tập hợp

{% highlight java linenos %}

Deque<String> deque = new ArrayDeque<>();

deque.offerFirst("element 1");

{% endhighlight %}

- Sử dụng phương thức push để thêm vào phần tử tại vị trí đầu tiên

{% highlight java linenos %}

Deque<String> deque = new LinkedList<>();

deque.push("element 0");

{% endhighlight %}

# **4. Peek một phần tử trong Deque**

Để xem một phần tử ở đầu và ở cuối của deque chúng ta có thể sử dụng phương thức như peek, peekFirst, peekLast, getFirst, getLast

- Sử dụng peek

{% highlight java linenos %}

Deque<String> deque = new ArrayDeque<>();

deque.add("first element");
deque.add("last element");

String firstElement = deque.peek();

{% endhighlight %}

- Sử dụng peekFirst

{% highlight java linenos %}

Deque<String> deque = new ArrayDeque<>();

deque.add("first element");
deque.add("last element");

String firstElement = deque.peekFirst();

{% endhighlight %}

- Sử dụng peekLast

{% highlight java linenos %}

Deque<String> deque = new ArrayDeque<>();

deque.add("first element");
deque.add("last element");

String lastElement = deque.peekLast();

{% endhighlight %}

- Sử dụng getFirst

{% highlight java linenos %}

Deque<String> deque = new ArrayDeque<>();

deque.add("first element");
deque.add("last element");


String firstElement = deque.getFirst();

{% endhighlight %}

- Sử dụng getLast

{% highlight java linenos %}

Deque<String> deque = new ArrayDeque<>();

deque.add("first element");
deque.add("last element");

String lastElement = deque.getLast();

{% endhighlight %}

# **5. Xoá một phần tử trong Deque**

Để xoá các phần tử trong Deque chúng ta có thể sử dụng phương thức remove, removeFirst, removeLast, poll, pollFirst, pollLast

- Sử dụng remove

{% highlight java linenos %}

Deque<String> deque = new LinkedList<>();

deque.add("element 0");

String removedElement = deque.remove();

{% endhighlight %}

- Sử dụng removeFirst

{% highlight java linenos %}

Deque<String> deque = new LinkedList<>();

deque.add("element 0");

String removedElement = deque.removeFirst();

{% endhighlight %}

- Sử dụng removeLast

{% highlight java linenos %}

Deque<String> deque = new LinkedList<>();

deque.add("element 0");
deque.add("element 1");
deque.add("element 2");

String removedElement = deque.removeLast();
{% endhighlight %}

# **6. Kiểm tra một phần tử đã có trong Deque**

- Chúng ta sử dụng contains để kiểm tra phần tử đã có trong Deque hay chưa.

{% highlight java linenos %}

Deque<String> deque = new ArrayDeque<>();

deque.add("first element");

boolean containsElement1 = deque.contains("first element");
boolean containsElement2 = deque.contains("second element");

{% endhighlight %}

# **7. Duyệt qua các phần tử đã có trong Deque**

- Chúng ta sử dụng Iterator hoặc foreach để duyệt qua các phần tử

{% highlight java linenos %}

Deque<String> deque = new LinkedList<>();

deque.add("element 0");
deque.add("element 1");
deque.add("element 2");

Iterator<String> iterator = deque.iterator();
while(iterator.hasNext(){
  String element = iterator.next();
}

{% endhighlight %}

{% highlight java linenos %}

Deque<String> deque = new LinkedList<>();

deque.add("element 0");
deque.add("element 1");
deque.add("element 2");

for(String element : deque) {
    System.out.println(element);
}

{% endhighlight %}





