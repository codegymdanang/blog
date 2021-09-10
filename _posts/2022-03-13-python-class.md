---
layout: course-python
title: Sử dụng Class trong Python
slug : su-dung-class-trong-python
category: laptrinhpython
tags: [python]
summery: Class
image: /images/blog/feature_javascript.png
description : Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách sử dụng Class trong python là gì

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách <b> sử dụng Class trong Python </b>. Tất cả mọi thứ trong Python đều là đối tượng chứa các thuộc tính và phương thức. Để tạo ra đối tượng thì chúng ta sử dụng từ khóa class để khai báo.


## **1. Tạo Class**

Chúng ta sử dụng từ khóa class để tạo một Class trong Python như sau.


{% highlight python  linenos %}

  	class MyClass:
  		x = 5


{% endhighlight %}

Để tạo một đối tượng từ class MyClass ta tạo như sau.

{% highlight python  linenos %}

  	p1 = MyClass()
		print(p1.x)


{% endhighlight %}

## **2. Hàm khởi tạo**

Để tạo một hàm khởi tạo của một đối tượng ta sử dụng hàm __int__(). Ví dụ như khi tạo ra đối tượng Person có các giá trị được khởi tạo là tên và tuổi ta làm như sau.

{% highlight python  linenos %}

  	class Person:
	  def __init__(self, name, age):
	    self.name = name
	    self.age = age

	p1 = Person("John", 36)

	print(p1.name)
	print(p1.age)


{% endhighlight %}

Tham số seft dùng để tham chiếu đến đối tượng mà ta đang dùng. Trong trường hợp này self chính là class Person

## **3. Khởi tạo phương thức trong đối tượng**

Trong đối tượng thì mình sẽ có phương phức để mô tả cho đối tượng đó. Để tạo một phương thức của một đối tượng thì ta sử dụng từ khóa def để tạo phương thức bên trong của đối tượng.

Ví dụ đối tượng Person có phương thức là run thì ta làm như sau.

{% highlight python  linenos %}

  	class Person:
	  def __init__(self, name, age):
	    self.name = name
	    self.age = age

	  	def run(self):
	    	print("Hello my name is " + self.name)

	p1 = Person("John", 36)
	p1.run()


{% endhighlight %}

## **4. Thay đổi giá trị trong đối tượng**

Để set (thay đổi) một giá trị mới cho thuộc tính ta gán giá trị đó cho một giá trị mới như sau.

{% highlight python  linenos %}

  	class Person:
	  def __init__(self, name, age):
	    self.name = name
	    self.age = age

	p1 = Person("John", 36)

	p1.age = 40


{% endhighlight %}

## **5. Xóa giá trị trong đối tượng**

Để xóa một đối tượng ta sử dụng từ khóa del như sau.

{% highlight python  linenos %}

  	class Person:
	  def __init__(self, name, age):
	    self.name = name
	    self.age = age

	p1 = Person("John", 36)

	del p1.age



{% endhighlight %}

## **6. Xóa giá  đối tượng**

Để xóa một đối tượng ta sử dụng từ khóa del như sau.

{% highlight python  linenos %}

  	class Person:
	  def __init__(self, name, age):
	    self.name = name
	    self.age = age

	p1 = Person("John", 36)

	del p1



{% endhighlight %}

## **7. Mệnh đề pass**

Khi tạo Class thì Python bắt buộc chúng ta phải khai báo giá trị biến và phương thức và không được để trống. Tuy nhiên có một vài trường hợp chúng ta muốn để trống và không muốn Python bắt lỗi thì ta dùng mệnh đề pass như sau.

{% highlight python  linenos %}

  	class Person:
  		pass



{% endhighlight %}
























