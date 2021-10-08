---
layout: course-python
title: Sử dụng Tuple trong Python
slug : su-dung-tuple-trong-python
category: laptrinhpython
tags: [python]
summery: Tuple
image: /images/blog/feature_javascript.png
description : Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách sử dụng Tuple trong python là gì

youtubeId: fLetzMIhZTs
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách <b> sử dụng Tuple trong Python </b>. 

Chức năng của Tuple cũng giống như list là lưu trữ các giá trị trong tập hợp. Nhưng có điểm khác biệt với list là các phần tử trong tuple được sắp xếp theo thứ tự và không thay đổi các giá trị trong phần tử được như là thay đổi giá trị, thêm mới hoặc xóa các phần tử trong tuple.


Để tạo Tuple ta sử dụng dấu () như sau.

{% highlight python  linenos %}

  	thistuple = ("apple", "banana", "cherry")
	print(thistuple)

{% endhighlight %}



Ngoài ra chúng ta có thể sử dụng Tuple constructor để tạo một tuple như sau

{% highlight python  linenos %}

  	thistuple = tuple(("apple", "banana", "cherry"))
	print(thistuple)

{% endhighlight %}




## **1. Lấy độ dài của Tuple**

Chúng ta sử dụng hàm len() để lấy độ dài của tuple như sau.

{% highlight python  linenos %}

  	thistuple = ("apple", "banana", "cherry")
	print(len(thistuple))

{% endhighlight %}

## **2. Tạo Tuple với một phần tử**

Để tạo tuple chứa duy nhất 1 phần tử thì ta chú ý thêm dấu , sau phần tử, nếu không thì python hiểu đó là kiểu str.

{% highlight python  linenos %}

  	thistuple = ("apple",)
	print(type(thistuple)) // Đây là kiểu tuple

	#NOT a tuple
	thistuple = ("apple") 
	print(type(thistuple)) // Đây là kiểu str

{% endhighlight %}

## **3. Các kiểu dữ liệu chứa trong Tuple**

Tuple có thể chứa các kiểu dữ liệu như chuỗi, số, boolean

{% highlight python  linenos %}

  	tuple1 = ("apple", "banana", "cherry")
	tuple2 = (1, 5, 7, 9, 3)
	tuple3 = (True, False, False)

{% endhighlight %}

Tuple có thể chứa nhiều kiểu dữ liệu khác nhau cùng một lúc.

{% highlight python  linenos %}

  	tuple1 = ("abc", 34, True, 40, "male")

{% endhighlight %}



## **4. Kiểm tra kiểu Tuple**

Để kiểm tra một đối tượng có phải là Tuple không ta sử dụng hàm type() như sau.

{% highlight python  linenos %}

  	mytuple = ("apple", "banana", "cherry")
	print(type(mytuple))


{% endhighlight %}

## **5. Lấy phần tử trong Tuple**

Các phần tử trong Tuple được đánh index từ ví trí 0,2,3,4 ... . Để lấy giá trị đầu tiên thì ta có thể lấy index như sau

{% highlight python  linenos %}

  	thistuple = ("apple", "banana", "cherry")
	print(thistuple[0])

{% endhighlight %}

Để lấy phần tử cuối cùng của Tuple ta sẽ sử dụng số âm như sau.

{% highlight python  linenos %}

  	thistuple = ("apple", "banana", "cherry")
	print(thistuple[-1])

{% endhighlight %}

## **6. Lấy phần tử trong một khoản nhât định trong Tuple**

Chúng ta có thể lấy 1 khoảng phần tử bằng cách chỉ ra nơi bắt đầu lấy phần tử và nơi kết thúc lấy phần tử như sau.

{% highlight python  linenos %}

  	thistuple = ("apple", "banana", "cherry", "orange", "kiwi", "melon", "mango")
	print(thistuple[2:5])

{% endhighlight %}

Kết quả là : ('cherry', 'orange', 'kiwi')

## **8. Duyệt các phần tử trong Tuple**

Chúng ta có thể sử dụng vòng lặp for để duyệt qua các phần tử trong Tuple như sau.

{% highlight python  linenos %}

  	thistuple = ("apple", "banana", "cherry")
	for x in thistuple:
 		 print(x)

{% endhighlight %}

Chúng ta có thể duyệt qua các phần tử bằng cách khác như sử dụng kết hợp hàm range() và len() như sau.

{% highlight python  linenos %}

  	thistuple = ("apple", "banana", "cherry")
	for i in range(len(thistuple)):
  		print(thistuple[i])

{% endhighlight %}

## **9. Nối 2 Tuple**

Để nối 2 tuples ta sử dụng dấu + như sau.

{% highlight python  linenos %}

  	tuple1 = ("a", "b" , "c")
	tuple2 = (1, 2, 3)

	tuple3 = tuple1 + tuple2
	print(tuple3)

{% endhighlight %}

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}















