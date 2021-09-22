---
layout: course-python
title: Phạm vi biến trong Python
slug : pham-vi-bien-trong-python
category: laptrinhpython
tags: [python]
summery: Phạm vi Biến
image: /images/blog/feature_javascript.png
description : Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách sử dụng phạm vi của biến trong python.

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách <b> sử dụng phạm vi biến trong Python </b>. 


## **1. Biến phạm vi cục bộ**

Phạm vi cục bộ có nghĩa là biến chỉ tồn tại và được sử dụng trong phạm vi một function. Khi ra khỏi function thì không còn tác dụng nữa. Ví dụ biến x sau đây chỉ có hiệu lực trong myfunc().



Ta có lớp Person được khai báo như sau.


{% highlight python  linenos %}

  	def myfunc():
	  x = 300
	  print(x)

	myfunc()

{% endhighlight %}


## **2. Biến phạm vi toàn cục**

Khác với biến cục bộ, biến toàn cục chúng ta có thể sử dụng bất kỳ ở đâu. Chúng ta có thể sử dụng bất cứ khi nào. Ta khai báo biến toàn cục x như sau.

{% highlight python  linenos %}

  	x = 300

	def myfunc():
	  print(x)

	myfunc()

	print(x)

{% endhighlight %}

## **3. Tên trùng nhau**

Nếu như ta khai báo tên của biến toàn cục và cục bộ giống nhau, thì Python sẽ tạo ra 2 biến riêng biệt. Một biến toàn cục và một biến cục bộ trong function như sau.

{% highlight python  linenos %}

  	x = 300

	def myfunc():
	  x = 200
	  print(x)

	myfunc()

	print(x)

{% endhighlight %}

## **4. Global keywork**

Chúng ta có thể tạo biến toàn cục bằng từ khóa global như sau.

{% highlight python  linenos %}

  	def myfunc():
	  global x
	  x = 300

	myfunc()

	print(x)

{% endhighlight %}

















