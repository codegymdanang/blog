---
layout: course-python
title: Hàm trong Python
slug : su-dung-ham-trong-python
category: laptrinhpython
tags: [python]
summery: Hàm
image: /images/blog/feature_javascript.png
description : Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách sử dụng hàm trong python là gì

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách <b>  sử dụng hàm trong Python </b>. Hàm là tập hợp các câu lệnh được nhóm lại với nhau và được thực thi khi được gọi


## **1. Tạo hàm**

Để tạo hàm trong python ta sử dụng từ khóa def như sau.

{% highlight python  linenos %}

   	def my_function():
  		print("Hello from a function")

{% endhighlight %}

Để gọi hàm thì ta sẽ gọi tên của hàm được gọi như sau.

{% highlight python  linenos %}

   	def my_function():
  		print("Hello from a function")

	my_function()

{% endhighlight %}

## **2. Tham số trong hàm**

Chúng ta có thể truyền tham số trong hàm như sau.

{% highlight python  linenos %}

   	def my_function(fname):
  		print(fname + " Refsnes")

	my_function("Emil")
	my_function("Tobias")
	my_function("Linus")

{% endhighlight %}

## **3. Tham số arg trong hàm**

Nếu như ta không biết sẽ có bao nhiêu tham số trong hàm thì ta có thể sử dụng dấu * trước tham số như sau.

{% highlight python  linenos %}

   	def my_function(*kids):
  		print("The youngest child is " + kids[2])

	my_function("Emil", "Tobias", "Linus")

{% endhighlight %}

## **4. Giá trị mặc địch cho tham số arg trong hàm**

Chúng ta có thể thiết lập giá trị mặc định cho tham số như sau.

{% highlight python  linenos %}

   	def my_function(country = "Norway"):
  		print("I am from " + country)

	my_function("Sweden")
	my_function("India")
	my_function()
	my_function("Brazil")

{% endhighlight %}

## **5. Kết quả trả về từ hàm**

Để trả về kết quả được tính toán trong hàm ta sử dụng từ khóa return như sau.

{% highlight python  linenos %}

   	def my_function(x):
  		return 5 * x

	print(my_function(3))
	print(my_function(5))
	print(my_function(9))

{% endhighlight %}

## **6. Mệnh đề pass**

Hàm được tạo ra không được phép trống, nếu không sẽ gây ra lỗi. Trong một số trường hợp để tránh gây lỗi thì ta sử dụng mệnh đề pass như sau.

{% highlight python  linenos %}

   	def myfunction():
  		pass

{% endhighlight %}











































