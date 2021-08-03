---
layout: course-python
title: Vòng lặp trong Python
slug : su-dung-vong-lap-trong-python
category: laptrinhpython
tags: [python]
summery: Vòng lặp
image: /images/blog/feature_javascript.png
description : Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách sử dụng vòng lặp trong python là gì

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách <b>  sử dụng vòng lặp trong Python </b>. 
Python hỗ trợ 2 loại vòng lặp sau :

- Vòng lặp while
- Vòng lặp for



## **1. Vòng lặp While**

Vòng lặp while thực thi khi điều kiện trong while là còn đúng.


{% highlight python  linenos %}

   	i = 1
	while i < 6:
	  print(i)
	  i += 1

{% endhighlight %}


## **2. Lệnh break**

Lệnh break dùng để thoát khỏi vòng lặp cho dù điều kiện vẫn đang đúng

{% highlight python  linenos %}

   	i = 1
	while i < 6:
	  print(i)
	  if i == 3:
	    break
	  i += 1

{% endhighlight %}


## **3. Lệnh continue**

Lệnh continue sẽ dừng vòng lặp tại điều kiện ta đưa vào và tiếp tục bước nhảy tiếp theo của vòng lặp

{% highlight python  linenos %}

   	i = 0
	while i < 6:
	  i += 1
	  if i == 3:
	    continue
	  print(i)

{% endhighlight %}

## **4. Lệnh else**

Câu lệnh else sau vòng lặp để thực hiện các đoạn code khi đều kiện trong vòng lặp không còn đúng nữa

{% highlight python  linenos %}

   	i = 1
	while i < 6:
	  print(i)
	  i += 1
	else:
	  print("i is no longer less than 6")

{% endhighlight %}

## **5. Vòng lặp for**

Vòng lặp for dùng để duyệt qua các phần tử trong tập hợp

{% highlight python  linenos %}

   	fruits = ["apple", "banana", "cherry"]
	for x in fruits:
	  print(x)

{% endhighlight %}

Cũng giống như while ta có thể sử dụng break, continue và else trong for như sau.

{% highlight python  linenos %}

   	fruits = ["apple", "banana", "cherry"]
	for x in fruits:
	  if x == "banana":
	    break
	  print(x)

{% endhighlight %}

{% highlight python  linenos %}

   	fruits = ["apple", "banana", "cherry"]
	for x in fruits:
	  if x == "banana":
	    continue
	  print(x)

{% endhighlight %}

{% highlight python  linenos %}

   	for x in range(6):
	  print(x)
	else:
	  print("Finally finished!")

{% endhighlight %}

## **6. Sử dụng range**

Chúng ta sử dụng hàm range() để chỉ ra số lần vòng lặp được chạy. Bắt đầu từ vị trí 0. Mỗi lần vòng lặp chạy sẽ tăng lên 1 đơn vị

{% highlight python  linenos %}

   	for x in range(6):
  		print(x)

{% endhighlight %}

## **7. Vòng lặp lồng nhau**

Chúng ta có thể tạo vòng lặp lồng nhau như sau.

{% highlight python  linenos %}

   	adj = ["red", "big", "tasty"]
	fruits = ["apple", "banana", "cherry"]

	for x in adj:
	  for y in fruits:
	    print(x, y)

{% endhighlight %}

## **8. Pass**

Vòng lặp for không được phép bỏ trống, nếu bỏ trống sẽ bị báo lỗi. Nhưng nếu mình muốn không bị lỗi thì dùng từ khóa  pass

{% highlight python  linenos %}

   	for x in [0, 1, 2]:
  		pass

{% endhighlight %}






