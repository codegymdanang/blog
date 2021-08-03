---
layout: course-python
title: Câu điều kiện trong Python
slug : su-dung-cau-dieu-kien-trong-python
category: laptrinhpython
tags: [python]
summery: Câu điều kiện
image: /images/blog/feature_javascript.png
description : Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách sử dụng câu điều kiện trong python là gì

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách <b>  sử dụng điều kiện if else trong Python </b>. 
Python hỗ trợ 6 loại điều kiện sau :

- Bằng : a == b
- Không bằng : a != b
- Nhỏ hơn : a < b
- Nhỏ hơn hoặc bằng : a <= b
- Lớn hơn : a > b
- Lớn hơn hoặc bằng : a >= b



## **1. IF**

Để sử dụng câu điều kiện ta dùng mệnh đề if như sau

{% highlight python  linenos %}

   	a = 33
	b = 200
	if b > a:
  		print("b is greater than a")

{% endhighlight %}

## **2. Else IF**

Sử dụng else if nếu điều kiện không đúng trong if thì thực hiện câu lệnh trong elseif

{% highlight python  linenos %}

   	a = 33
	b = 33
	if b > a:
	  print("b is greater than a")
	elif a == b:
	  print("a and b are equal")

{% endhighlight %}

## **3. Else**

Else sẽ thực hiện các câu lệnh mà điều kiện không thỏa mãn trong if và elseif

{% highlight python  linenos %}

   	a = 200
	b = 33
	if b > a:
	  print("b is greater than a")
	elif a == b:
	  print("a and b are equal")
	else:
	  print("a is greater than b")

{% endhighlight %}

## **4. Viết tắt cho If**

Nếu chỉ có 1 dòng lệnh trong khối lệnh if thì ta có thể viết tắt như sau

{% highlight python  linenos %}

   	if a > b: print("a is greater than b")

{% endhighlight %}

## **5. Viết tắt cho IfElse**

Chúng ta cũng có thể viết tắt cho If Else trên cùng 1 dòng như sau

{% highlight python  linenos %}

   	a = 2
	b = 330
	print("A") if a > b else print("B")

{% endhighlight %}

## **6. Từ khóa And**

Chúng ta sử dụng and khi muốn kết hợp nhiều điều kiện.

{% highlight python  linenos %}

   	a = 200
	b = 33
	c = 500
	if a > b and c > a:
	  print("Both conditions are True")

{% endhighlight %}

## **7. Từ khóa OR**

Ngoài từ khóa and chúng ta còn có thể sử dụng từ khóa OR để kết hợp nhiều điều kiện

{% highlight python  linenos %}

   	a = 200
	b = 33
	c = 500
	if a > b or a > c:
	  print("At least one of the conditions is True")

{% endhighlight %}

## **8. If lồng nhau**

Chúng ta có thể tạo các if lồng nhau (if trong if) như sau:

{% highlight python  linenos %}

   	x = 41

	if x > 10:
	  print("Above ten,")
	  if x > 20:
	    print("and also above 20!")
	  else:
	    print("but not above 20.")

{% endhighlight %}

## **9. Từ khóa pass**

Nếu mệnh đề if  bỏ trống thì sẽ gặp lỗi, để giải quyết việc báo lỗi này thì ta dùng từ khóa pass để không bị báo lỗi

{% highlight python  linenos %}

   	a = 33
	b = 200

	if b > a:
	  pass

{% endhighlight %}


































