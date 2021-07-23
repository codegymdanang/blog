---
layout: course-python
title: String trong Python
slug : string-trong-python
category: laptrinhpython
tags: [python]
summery: String
image: /images/blog/feature_javascript.png
description : Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách sử dụng String trong Python. Để tạo ra kiểu dữ liệu string chúng ta có thể sử dụng một dấu một nháy hoặc hai dấu hai nháy như sau. 

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách <b>  sử dụng String trong Python </b>. 

Để tạo ra kiểu dữ liệu string chúng ta có thể sử dụng một dấu ' hoặc hai dấu " như sau. 

{% highlight python  linenos %}

     hello = 'hello' 
     hello = "hello"

{% endhighlight %}

## **1. Gán nhiều dòng text cho biến**

Chúng ta có thể tạo ra một đoạn văn bản và gán cho biến bằng cách sử dụng dấu ba nháy """

{% highlight python  linenos %}

      a = """Lorem ipsum dolor sit amet,
      consectetur adipiscing elit,
      sed do eiusmod tempor incididunt
      ut labore et dolore magna aliqua."""
      print(a

{% endhighlight %}

Hoặc chúng ta có thể sử dụng 3 nháy ''' 

{% highlight python  linenos %}

      a = '''Lorem ipsum dolor sit amet,
      consectetur adipiscing elit,
      sed do eiusmod tempor incididunt
      ut labore et dolore magna aliqua.'''
      print(a)

{% endhighlight %}

## **2. Strings là một mảng**

Giống như các ngôn ngữ lập trình khác. Chuỗi là một mảng các ký tự, chúng ta sử dụng [] để lấy từng ký tự trong mảng.

{% highlight python  linenos %}

      a = "Hello, World!"
      print(a[1])

{% endhighlight %}

## **3. Duyệt qua chuỗi**

String là một mảng nên chúng ta có thể sử dụng vòng lặp để duyệt qua các ký tự trong chuỗi.

{% highlight python  linenos %}

      for x in "banana":
      print(x)

{% endhighlight %}

## **4. Lấy kích thướt của chuỗi**

Chúng ta sử dụng phương thức len() để lấy độ dài của chuỗi.

{% highlight python  linenos %}

      a = "Hello, World!"
      print(len(a))

{% endhighlight %}

## **5. Kiểm tra ký tự hoặc từ có ở trong chuỗi**

Để kiểm tra ký tự hoặc một từ có nằm trong chuỗi không thì ta dùng từ khóa in

{% highlight python  linenos %}

      txt = "The best things in life are free!"
      print("free" in txt)

{% endhighlight %}

## **6. Kiểm tra ký tự hoặc từ không có trong chuỗi**

Ngược lại với việc kiểm tra có từ khóa trong chuỗi, thì để kiểm tra từ đó ko có trong chuỗi ta dùng từ khóa not in như sau

{% highlight python  linenos %}

      txt = "The best things in life are free!"
      print("expensive" not in txt)

{% endhighlight %}







