---
layout: course-python
title: Sử dụng Dictionaries trong Python
slug : su-dung-dictionaries-trong-python
category: laptrinhpython
tags: [python]
summery: Dictionary
image: /images/blog/feature_javascript.png
description : Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách sử dụng dictionary trong python là gì

youtubeId: cGaGMOwzl6Q
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách <b> sử dụng dictionary trong Python </b>.


## **1. Tạo dictionary**

Dictionary được sử dụng để lưu giá trị theo dạng key và value. Để tạo dictionary ta sử dụng dấu { }.

Các phần tử trong dictionary được sắp xếp theo tứ tự, chúng ta có thể thay đổi (thêm hoặc xóa) các phần tử nhưng dictionary không cho phép các phần tử được trùng lặp.

{% highlight python  linenos %}

  	thisdict = {
		"brand": "Ford",
		"model": "Mustang",
		year": 1964
	}

	print(thisdict)


{% endhighlight %}

hoặc chúng ta có thể tạo dictionary thông qua contructor như sau.

{% highlight python  linenos %}

  	result = dict([(1, 'One'), [2, 'Two'], [3,'Three']])

	print(result)


{% endhighlight %}



## **2. Kiểu dữ liệu trong dictionary**

Chúng ta có thể lưu kiểu dữ liệu String, int, boolean và list trong dictionary.

{% highlight python  linenos %}

  	thisdict = {
	  "brand": "Ford",
	  "electric": False,
	  "year": 1964,
	  "colors": ["red", "white", "blue"]
	}


{% endhighlight %}

## **3. Kiểm tra Kiểu dữ liệu của dictionary**

Để kiểm tra tập hợp có phải là dictionary không ta dùng hàm type() như sau.

{% highlight python  linenos %}

  	thisdict = {
	  "brand": "Ford",
	  "model": "Mustang",
	  "year": 1964
	}

	print(type(thisdict))

{% endhighlight %}


## **4. Lấy phần tử trong dictionary**

Ta sử dụng key để lấy giá trị các phần tử trong dictionary như sau.

{% highlight python  linenos %}

  	thisdict = {
	  "brand": "Ford",
	  "model": "Mustang",
	  "year": 1964
	}

	x = thisdict["model"]

{% endhighlight %}

Ngoài ra chúng ta có thể sử dụng phương thức get để lấy kết quả.

{% highlight python  linenos %}

  	x = thisdict.get("model")

{% endhighlight %}

## **5. Lấy tất cả các key trong dictionary**

Để lấy tất cả các key ta dùng hàm keys().

{% highlight python  linenos %}

  	car = {
		"brand": "Ford",
		"model": "Mustang",
		"year": 1964
	}

	x = car.keys()

	print(x) 

{% endhighlight %}

## **6. Lấy tất cả các value trong dictionary**

Để lấy tất cả values chúng ta sử dụng hàm values() như sau.

{% highlight python  linenos %}

  	car = {
		"brand": "Ford",
		"model": "Mustang",
		"year": 1964
	}

	x = car.values()

	print(x) 

{% endhighlight %}

## **7. Lấy tất cả các phần tử trong dictionary**

Ta sử dụng hàm items() để lấy tất cả các phần tử trong dictionary.

{% highlight python  linenos %}

  	car = {
		"brand": "Ford",
		"model": "Mustang",
		"year": 1964
	}

	x = car.items()

	print(x) 

{% endhighlight %}

## **8. Kiểm tra key có tồn tại trong dictionary**

Chúng ta sử dụng từ khóa in để kiểm tra xem có key trong dictionary không?

{% highlight python  linenos %}

  	thisdict = {
	  "brand": "Ford",
	  "model": "Mustang",
	  "year": 1964
	}

	if "model" in thisdict:
  		print("Yes, 'model' is one of the keys in the thisdict dictionary")

{% endhighlight %}

## **9. Thay đổi giá trị của phần tử trong dictionary**

Chúng ta có thể thay đổi giá trị của phần tử thông qua key của nó như sau.

{% highlight python  linenos %}

  	thisdict = {
	  "brand": "Ford",
	  "model": "Mustang",
	  "year": 1964
	}

	thisdict["year"] = 2018

{% endhighlight %}

Ngoài ra chúng ta có thể dùng phương thức update() như sau.

{% highlight python  linenos %}

  	thisdict = {
	  "brand": "Ford",
	  "model": "Mustang",
	  "year": 1964
	}

	thisdict.update({"year": 2020})

{% endhighlight %}

## **10. Thêm phần tử trong dictionary**

Chúng ta sử dụng tạo một key mới và gán giá trị cho nó như sau.

{% highlight python  linenos %}

  	thisdict = {
	  "brand": "Ford",
	  "model": "Mustang",
	  "year": 1964
	}

	thisdict["color"] = "red"

{% endhighlight %}

Chúng ta cũng có thể sử dụng hàm update() như sau.

{% highlight python  linenos %}

  	thisdict = {
	  "brand": "Ford",
	  "model": "Mustang",
	  "year": 1964
	}

	thisdict.update({"color": "red"})

{% endhighlight %}

## **11. Xóa phần tử trong dictionary**

Để xóa phần tử chúng ta có thể sử dụng phương thức pop() như sau.

{% highlight python  linenos %}

  	thisdict = {
	  "brand": "Ford",
	  "model": "Mustang",
	  "year": 1964
	}

	thisdict.pop("model")
	print(thisdict)

{% endhighlight %}

Sử dụng từ khóa del

{% highlight python  linenos %}

  	thisdict = {
	  "brand": "Ford",
	  "model": "Mustang",
	  "year": 1964
	}

	del thisdict["model"]

	print(thisdict)

{% endhighlight %}

Để xóa tất cả các phần tử trong dictionary ta dùng phương thức clear().

{% highlight python  linenos %}

  	thisdict = {
	  "brand": "Ford",
	  "model": "Mustang",
	  "year": 1964
	}

	thisdict.clear()
	
	print(thisdict)

{% endhighlight %}

## **12. Duyệt các phần tử trong dictionary**

Để duyệt các phần tử trong dictionary chúng ta sử dụng vòng lặp for như sau.

{% highlight python  linenos %}

  	for x in thisdict:
  		print(x)

{% endhighlight %}

Nếu muốn duyện qua các giá trị của dictionary ta làm như sau.

{% highlight python  linenos %}

  	for x in thisdict.values():
  		print(x)

{% endhighlight %}

Nếu muốn duyệt qua các key ta làm như sau.

{% highlight python  linenos %}

  	for x in thisdict.keys():
  		print(x)

{% endhighlight %}

Muốn duyệt qua cả key và value ta sử dụng items như sau.

{% highlight python  linenos %}

  	for x, y in thisdict.items():
 		print(x, y)

{% endhighlight %}

## **13. Copy 2 dictionaries**

Để gọp 2 dictionaries chúng ta có thể sử dụng phương thức copy() như sau.

{% highlight python  linenos %}

  	thisdict = {
	  "brand": "Ford",
	  "model": "Mustang",
	  "year": 1964
	}

	mydict = thisdict.copy()

	print(mydict)

{% endhighlight %}

## **14. Dictionary lồng nhau**

Chúng ta có thể tạo một hoặc nhiều dictionary trong một dictionary khác như sau.

{% highlight python  linenos %}

  	child1 = {
	  "name" : "Emil",
	  "year" : 2004
	}

	child2 = {
	  "name" : "Tobias",
	  "year" : 2007
	}
	
	child3 = {
	  "name" : "Linus",
	  "year" : 2011
	}

	myfamily = {
	  "child1" : child1,
	  "child2" : child2,
	  "child3" : child3
	}

{% endhighlight %}


{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}
























