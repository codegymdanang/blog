---
layout: course-python
title: Sử dụng List trong Python
slug : su-dung-list-trong-python
category: laptrinhpython
tags: [python]
summery: List
image: /images/blog/feature_javascript.png
description : Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách sử dụng List trong python là gì

youtubeId: dTSp1PcvpbU
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách <b> sử dụng List trong Python </b>. List được sử dụng để lưu các giá trị trong biến List.

Ví dụ để tạo 1 list chứa một mảng các phần tử str. Ta dùng [ ] như sau.

{% highlight python  linenos %}

   mylist = ["apple", "banana", "cherry"]

{% endhighlight %}

Các phần tử trong List được sắp xếp theo tứ tự bắt đầu từ vị trí 0 (index[0]). List có thể thay đổi như ta có thể thêm, xóa các phần tử trong List. List cho phép các giá trị trùng lặp được chứa trong List như sau.


{% highlight python  linenos %}

   thislist = ["apple", "banana", "cherry", "apple", "cherry"]

{% endhighlight %}


## **1. Chiều dài của List**

Chúng ta sử dụng hàm len() để tính có bao nhiêu phần tử trong List.


{% highlight python  linenos %}

   	thislist = ["apple", "banana", "cherry"]
	print(len(thislist))

{% endhighlight %}

Hàm print dùng để in kết quả ra console.


## **2. Kiểu dữ liệu của List**

List có thể chứa đựng các kiểu dữ liệu như String, int và boolean như sau.

{% highlight python  linenos %}

   	list1 = ["apple", "banana", "cherry"]
	list2 = [1, 5, 7, 9, 3]
	list3 = [True, False, False]

{% endhighlight %}

Ngoài ra chúng ta có thể chứa đựng các loại kiểu dữ liệu khác nhau trong list như sau.

{% highlight python  linenos %}

	list1 = ["abc", 34, True, 40, "male"]

{% endhighlight %}

## **3. Hàm dựng của List**

Ngoài cách dung [] để tạo ra list. Chúng ta có thể sử dụng hàm dựng list() để tạo ra 1 list như sau.

{% highlight python  linenos %}

	thislist = list(("apple", "banana", "cherry"))

{% endhighlight %}

## **4. Lấy giá trị trong List**

Để lấy các giá trị lưu trữ trong List chúng ta sẽ sử dụng index(vị trí) các phần tử trong list.

Phần tử đầu tiên trong list sẽ có index là 0. Ví dụ dưới đây ta lấy index là 1 thì sẽ trả về giá trị là banana.

{% highlight python  linenos %}

	thislist = ["apple", "banana", "cherry"]
	print(thislist[1])


{% endhighlight %}

Nếu ta sử dung index là số âm ví dụ như -1. Thì nó sẽ lấy giá trị cuối cùng của mảng, -2 là giá trị cuối cùng ở vị trí số 2.

{% highlight python  linenos %}

	thislist = ["apple", "banana", "cherry"]
	print(thislist[-1])


{% endhighlight %}

## **5. Lấy giá trị một khoảng trong List**

Nếu chúng ta muốn lấy 1 khoảng giá trị trong List thì dùng dấu : như sau.
Ví dụ mình có List là "apple", "banana", "cherry", "orange", "kiwi", "melon", "mango". Bây giờ mình chỉ muốn lấy giá trị từ index số 2 tới số 5. Ta làm như sau.

{% highlight python  linenos %}

	thislist = ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]
	print(thislist[2:5])


{% endhighlight %}

Chú ý là khi ta lấy từ 2 đến 5. Thì list sẽ trả về giá trị bắt đầu từ index là 2 (trong trường hợp này là cherry) và kết thúc là index là 4. 

Mọi người thường nhầm lẫn là list[2:5] sẽ kết thúc là index là 5. Nó chỉ đếm tới vị trị 5 nhưng nó sẽ không lấy giá trị ở vị trí 5.

Ta sẽ có kết quả của thislist[2:5] là ['cherry', 'orange', 'kiwi']


Để lấy giá trị ở vị trí ban đầu đến 1 khoảng giá trị thì ta làm như sau.

{% highlight python  linenos %}

	thislist = ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]
	print(thislist[:4])


{% endhighlight %}

Lúc này mình sẽ nhận được giá trị tính index là 0,1,2,3 và kết quả là ['apple', 'banana', 'cherry', 'orange'].


Để lấy khoảng giá trị từ vị trí chỉ định đến vị trí cuối cùng ta làm như sau.

{% highlight python  linenos %}

	thislist = ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]
	print(thislist[2:])


{% endhighlight %}


## **6. Thay đổi giá trị trong List**

Để thay đổi giá trị ta lấy index của phần tử trong mảng và gán cho giá trị mới.

{% highlight python  linenos %}

	thislist = ["apple", "banana", "cherry"]
	thislist[1] = "blackcurrant"
	print(thislist)


{% endhighlight %}

Để thay đổi 1 range các giá trị ta làm như sau.

{% highlight python  linenos %}

	thislist = ["apple", "banana", "cherry", "orange", "kiwi", "mango"]
	thislist[1:3] = ["blackcurrant", "watermelon"]
	print(thislist)

{% endhighlight %}


## **7. Thêm phần tử vào vị trí mong muốn trong List**

Ta sử dụng phương thức insert() để thêm 1 phần tử trong List ở một vị trí mong muốn.

{% highlight python  linenos %}

	thislist = ["apple", "banana", "cherry"]
	thislist.insert(2, "watermelon")
	print(thislist)

{% endhighlight %}

## **8. Thêm phần tử vào vị trí cuốitrong List**

Ta sử dụng phương thức append() để thêm 1 phần tử trong List. Phần tử này được thêm vào vị trí cuối cùng trong List

{% highlight python  linenos %}

	thislist = ["apple", "banana", "cherry"]
	thislist.append("orange")
	print(thislist)

{% endhighlight %}

## **9. Gọp 2 list**

Để nối các phần tử của 2 List khác nhau thành 1 list thì ta dùng phương thức extend() như sau.

{% highlight python  linenos %}

	thislist = ["apple", "banana", "cherry"]
	tropical = ["mango", "pineapple", "papaya"]
	thislist.extend(tropical)
	print(thislist)

{% endhighlight %}

Ngoài cách dùng extend() ta có thể cộng 2 list như sau

{% highlight python  linenos %}

	list1 = ["a", "b", "c"]
	list2 = [1, 2, 3]

	list3 = list1 + list2
	print(list3)

{% endhighlight %}


## **10. Xóa phần tử trong list**

Chúng ta sử dụng hàm remove() để xóa phần tử như sau

{% highlight python  linenos %}

	thislist = ["apple", "banana", "cherry"]
	thislist.remove("banana")
	print(thislist)

{% endhighlight %}

## **11. Xóa phần tử ở vị trí mong muốn trong list**

Chúng ta sử dụng pop() để xóa 1 phần tử ở vị trí mong muốn như sau.

{% highlight python  linenos %}

	thislist = ["apple", "banana", "cherry"]
	thislist.pop(1)
	print(thislist

{% endhighlight %}

Nếu như ta không chỉ định index trong phương thức pop() thì nó sẽ xóa phần tử cuối cùng trong List.

Ngoài cách dùng hàm pop() thì ta có thể dùng từ khóa delete để xóa phần tử hoặc xóa list.

 {% highlight python  linenos %}

	thislist = ["apple", "banana", "cherry"]
	del thislist[0]
	print(thislist)

{% endhighlight %}

{% highlight python  linenos %}

	thislist = ["apple", "banana", "cherry"]
	del thislist

{% endhighlight %}

## **12. Xóa hết các phần tử trong list**

Để xóa hết các phần tử và làm cho List trống thì ta dùng hàm clear() như sau.

{% highlight python  linenos %}

	thislist = ["apple", "banana", "cherry"]
	thislist.clear()
	print(thislist)

{% endhighlight %}

## **13. Duyệt qua các phần tử trong list**

Để duyệt qua các phần tử trong List ta dùng vòng lặp for như sau

{% highlight python  linenos %}

	thislist = ["apple", "banana", "cherry"]
	for x in thislist:
  	print(x)

{% endhighlight %}

## **14. Sắp xếp các phần tử trong list**

Chúng ta sử dụng hàm sort() để sắp xếp các phần tử trong list như sau. Mặc định hàm sort là sắp xếp tăng dần.

 {% highlight python  linenos %}

	thislist = ["orange", "mango", "kiwi", "pineapple", "banana"]
	thislist.sort()
	print(thislist)

{% endhighlight %}

Nếu như ta muốn sắp xếp theo hướng giảm dần thì ta dùng từ khóa reverse = TRUE làm như sau.

 {% highlight python  linenos %}

	thislist = ["orange", "mango", "kiwi", "pineapple", "banana"]
	thislist.sort(reverse = True)
	print(thislist)

{% endhighlight %}

## **15. Copy list**

Để copy các phần tử của 1 list ta dùng hàm copy() như sau.

{% highlight python  linenos %}

	thislist = ["apple", "banana", "cherry"]
	mylist = thislist.copy()
	print(mylist)

{% endhighlight %}

Ngoài ra chúng ta có thể sử dụng hàm list()

{% highlight python  linenos %}

	thislist = ["apple", "banana", "cherry"]
	mylist = list(thislist)
	print(mylist)

{% endhighlight %}

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

































