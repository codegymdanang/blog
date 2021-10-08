---
layout: course-python
title: Sử dụng Kế thừa trong Python
slug : su-dung-ke-thua-trong-python
category: laptrinhpython
tags: [python]
summery: Kế thừa
image: /images/blog/feature_javascript.png
description : Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách sử dụng kế thừa trong python là gì

youtubeId: z0yEn1itf0M
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách <b> sử dụng kế thừa trong Python </b>. 


## **1. Tạo Kế thừa**

Anh ví dụ mình có class Person với các thuộc tính là fistname, lastname và phương thức printname. Sau đó anh sẽ tạo một lớp Student kế thừa các giá trị của Person.

Ta có lớp Person được khai báo như sau.


{% highlight python  linenos %}

  	class Person:
	  def __init__(self, fname, lname):
	    self.firstname = fname
	    self.lastname = lname

	  def printname(self):
    	print(self.firstname, self.lastname)

	x = Person("John", "Doe")
	x.printname()

{% endhighlight %}


Chúng ta sử dụng ( ) để khai báo Class Student kế thừa Class Person như sau.


{% highlight python  linenos %}

  	class Student(Person):
  		pass

  	x = Student("Mike", "Olsen")
	x.printname()

{% endhighlight %}

Như vậy đối tượng Student sẽ được thừa hưởng các giá trị firstname, lastname và phương thức printname() từ đối tượng Person.

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}









