---
layout: course-python
title: Sử dụng Set trong Python
slug : su-dung-set-trong-python
category: laptrinhpython
tags: [python]
summery: Set
image: /images/blog/feature_javascript.png
description : Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách sử dụng set trong python là gì

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách <b> sử dụng Set trong Python </b>. Set dùng để lưu trữ các phần tử không theo thứ tự và các phần tử trong Set không được phép trùng nhau. Sau khi list được tạo ra thì các phần tử không thay đổi được nhưng chúng ta có thể thêm phần tử vào set.

Để tạo tập hợp Set ta dùng hai dấu { } như sau


{% highlight python  linenos %}

  	thisset = {"apple", "banana", "cherry", "apple"}

	print(thisset)


{% endhighlight %}

Ngoài ra ta có thể tạo Set thông qua constructor của Set như sau.

{% highlight python  linenos %}

  	thisset = set(("apple", "banana", "cherry")) # note the double round-brackets
	print(thisset)

{% endhighlight %}


## **1. Lấy độ dài của Set**

Chúng ta sử dụng hàm len() để lấy độ dài của Set như sau.

{% highlight python  linenos %}

  	thisset = {"apple", "banana", "cherry"}

	print(len(thisset))


{% endhighlight %}

## **2. Kiểu dữ liệu trong Set**

Chúng ta có thể chứa các kiểu dữ liệu như String,int, boolean trong Set như sau.

{% highlight python  linenos %}

  	set1 = {"apple", "banana", "cherry"}
	set2 = {1, 5, 7, 9, 3}
	set3 = {True, False, False}


{% endhighlight %}

Ngoài ra chúng ta có thể chứa nhiều kiểu dữ liệu khác nhau trong Set như sau.

{% highlight python  linenos %}

  	set1 = {"abc", 34, True, 40, "male"}

{% endhighlight %}


## **3. Kiểm tra đối tượng Set**

Để kiểm tra tập hợp có phải là set hay không ta dùng hàm type() như sau.

{% highlight python  linenos %}

  	myset = {"apple", "banana", "cherry"}
	print(type(myset))

{% endhighlight %}

## **4. Lấy các phần tử trong Set**

Chúng ta không thể lấy các phần tử của Set thông qua index (vị trí) được. Mà chúng ta sẽ sử dụng vòng for để duyệt qua các phần tử. Hoặc dùng từ khóa in để kiểm tra phần tử.


{% highlight python  linenos %}

  	thisset = {"apple", "banana", "cherry"}

	for x in thisset:
  		print(x)

{% endhighlight %}

{% highlight python  linenos %}

	thisset = {"apple", "banana", "cherry"}

	print("banana" in thisset)

{% endhighlight %}

## **5. Thêm phần tử trong Set**

Để thêm phần tử trong Set ta sử dụng hàm add() như sau.

{% highlight python  linenos %}

	thisset = {"apple", "banana", "cherry"}

	thisset.add("orange")

	print(thisset)

{% endhighlight %}

## **6. Thêm nhiều phần tử trong Set**

Để thêm nhiều phần tử vào Set ta dùng hàm update() như sau.

{% highlight python  linenos %}

	thisset = {"apple", "banana", "cherry"}
	tropical = {"pineapple", "mango", "papaya"}
	thisset.update(tropical)

{% endhighlight %}


Hàm update có thể add nhiều loại tập hợp khác nhau như lists, tuple và dictionaries vào Set đang có.

{% highlight python  linenos %}

	thisset = {"apple", "banana", "cherry"}
	mylist = ["kiwi", "orange"] // mylist là một List

	thisset.update(mylist)

{% endhighlight %}

## **7. Xóa phần tử trong Set**

Để xóa phần tử trong Set ta sử dụng hàm remove()

{% highlight python  linenos %}

	thisset = {"apple", "banana", "cherry"}
	thisset.remove("banana")

{% endhighlight %}


Ngoài sử dụng hàm remove() ta có thể sử dụng hàm discard()

{% highlight python  linenos %}

	thisset = {"apple", "banana", "cherry"}

	thisset.discard("banana")

{% endhighlight %}

Khi remove một phần tử mà phần tử đó không tồn tại trong Set. Nếu ta dùng hàm remove thì sẽ phát sinh ra lỗi, còn nếu dùng discard thì không có lỗi xảy ra.

Để remove phần tử cuối cùng trong Set ta dùng hàm pop()

{% highlight python  linenos %}

	thisset = {"apple", "banana", "cherry"}

	x = thisset.pop()

{% endhighlight %}

## **7. Xóa tất cả phần tử trong Set**

Ta sử dụng hàm clear() để xóa hết các phần tử trong Set.

{% highlight python  linenos %}

	thisset = {"apple", "banana", "cherry"}

	thisset.clear()

{% endhighlight %}

Ngoài ra nếu như ta muốn xóa luôn Set thì ta có thể dùng từ khóa del như sau.

{% highlight python  linenos %}

	thisset = {"apple", "banana", "cherry"}

	del thisset

{% endhighlight %}


## **8. Join 2 hay nhiều Set**

Để nối 2 Set lại với nhau ta có thể dùng hàm union() như sau

{% highlight python  linenos %}

	set1 = {"a", "b" , "c"}
	set2 = {1, 2, 3}

	set3 = set1.union(set2)
	print(set3)

{% endhighlight %}

















