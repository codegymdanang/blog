---
layout: course-python
title: Các kiểu dữ liệu trong Python
slug : kieu-du-lieu-trong-python
category: laptrinhpython
tags: [python]
summery: Kiểu dữ liệu
image: /images/blog/feature_javascript.png
description : Hôm nay anh sẽ hướng dẫn mọi người cách sử khai báo biến trong Python. Biến được sử dụng để lưu trữ các giá trị. Python thì khác java và các ngôn ngữ khác khi mình khai báo biến. Ví dụ trong java mình khai báo biến number có giá trị bằng 5 thì ta làm như sau int number = 5, trong javascript thì mình khai báo var number = 5. Còn trong Python ta chỉ cần viết number = 5.

youtubeId: -V2V0E-87TY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách <b>  sử dụng các kiểu dữ liệu có sẳn trong Python </b>. 

Python đã xây dựng sẳn một số kiểu dữ liệu để lập trình viên có thể sử dụng. Nó được thể hiện trong các mục sau. Chúng ta sẽ đi chuyên sâu vào cách sử dụng trong các bài sau.

{% highlight python  linenos %}

      Text Type:  str
      Numeric Types:    int, float, complex
      Sequence Types:   list, tuple, range
      Mapping Type:     dict
      Set Types:  set, frozenset
      Boolean Type:     bool
      Binary Types:     bytes, bytearray, memoryview

{% endhighlight %}

## **1. Ví dụ các kiểu dữ liệu**

Trong Python chúng ta có thể gán giá trị cho biến như sau.

{:class="table table-bordered"}
|  Ví dụ                                           |  kiểu dữ liệu    |                
|---                                               |---        |                  
| x = "Hello World"                                |     str   |
| x = 20                                           |     int        |
| x = 20.5                                         |     float      |
| x = 1j                                           |     complex      |
| x = ["apple", "banana", "cherry"]                |     list |
| x = ("apple", "banana", "cherry")                | tuple|
| x = range(6)                                     | range|
| x = {"name" : "John", "age" : 36}                | dict|
| x = {"apple", "banana", "cherry"}                | set |
| x = frozenset({"apple", "banana", "cherry"})     |frozenset|
| x = True                                         |bool|
| x = b"Hello"                                     | bytes|
| x = bytearray(5)                                 | bytearray |
| x = memoryview(bytes(5))                         |memoryview|                                             


Nhưng nếu mình muốn chỉ định kiểu dữ liệu thì mình khai báo như sau

{:class="table table-bordered"}
|  Ví dụ                                           |  kiểu dữ liệu    |                
|---                                               |---        |                  
| x = str("Hello World")                                |     str   |
| x = int(20)                                           |     int        |
| x = float(20.5)                                         |     float      |
| x = complex(1j)                                           |     complex      |
| x = list(("apple", "banana", "cherry"))                |     list |
| x = tuple(("apple", "banana", "cherry"))                | tuple|
| x = range(6)                                     | range|
| x = dict(name="John", age=36)               | dict|
| x = set(("apple", "banana", "cherry"))                | set |
| x = frozenset({"apple", "banana", "cherry"})     |frozenset|
| x = bool(5)                                        |bool|
| x = bytes(5)                                     | bytes|
| x = bytearray(5)                                | bytearray |
| x = memoryview(bytes(5))                         |memoryview|


## **2. Python Number**

Python hỗ trợ 3 loại kiểu dữ liệu số
+ int
+ float
+ complex

{% highlight python  linenos %}

      x = 1    # int
      y = 2.8  # float
      z = 1j   # complex

{% endhighlight %}

## **3. Random Number**

Tạo số ngẫu nhiên, python không có function random để tạo ra các số random. Tuy nhiên Python có xây dựng một module có sẳn gọi là random để tạo ra các số ngẫu nhiên.

{% highlight python  linenos %}

      import random

      print(random.randrange(1, 10))

{% endhighlight %}


## **4. Casting trong Python**

Trong Python chúng ta có thể conver (chuyển đổi) kiểu dữ liệu này qua kiểu dữ liệu khác. Ví dụ từ chữ sang số

Ví dụ chuyển đổi kiểu str và float qua int 

{% highlight python  linenos %}

      x = int(1)   # x will be 1
      y = int(2.8) # y will be 2
      z = int("3") # z will be 3

{% endhighlight %}

Ví dụ chuyển đổi kiểu str và int qua float 

{% highlight python  linenos %}

      x = float(1)     # x will be 1.0
      y = float(2.8)   # y will be 2.8
      z = float("3")   # z will be 3.0
      w = float("4.2") # w will be 4.2

{% endhighlight %}

Ví dụ chuyển đổi kiểu float và int qua str 

{% highlight python  linenos %}

      x = str("s1") # x will be 's1'
      y = str(2)    # y will be '2'
      z = str(3.0)  # z will be '3.0'

{% endhighlight %}


{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

