---
layout: course-python
title: khai báo biến trong python
slug : khai-bao-bien-trong-python
category: laptrinhpython
tags: [python]
summery: Khai báo biến
image: /images/blog/feature_javascript.png
description : Hôm nay anh sẽ hướng dẫn mọi người cách sử khai báo biến trong Python. Biến được sử dụng để lưu trữ các giá trị. Python thì khác java và các ngôn ngữ khác khi mình khai báo biến. Ví dụ trong java mình khai báo biến number có giá trị bằng 5 thì ta làm như sau int number = 5, trong javascript thì mình khai báo var number = 5. Còn trong Python ta chỉ cần viết number = 5.

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách <b> sử khai báo biến trong Python <b>. Biến được sử dụng để lưu trữ các giá trị. Python thì khác java và các ngôn ngữ khác khi mình khai báo biến. Ví dụ trong java mình khai báo biến number có giá trị bằng 5 thì ta làm như sau int number = 5, trong javascript thì mình khai báo var number = 5. Còn trong Python ta chỉ cần viết number = 5.


{% highlight python  linenos %}

x = 5
y = "John"
print(x)
print(y)

{% endhighlight %}

## **1. Casting hay còn gọi Ép Kiểu**

Ví dụ như ta muốn ép kiểu giá trị của biến qua String ta dùng hàm str. Nếu muốn ép kiểu số ta dùng int, còn nếu ép kiểu float ta dùng hàm float như sau

{% highlight python  linenos %}

x = str(3)    # x will be '3'
y = int(3)    # y will be 3
z = float(3)  # z will be 3.0

{% endhighlight %}

## **2. Lấy kiểu dữ liệu của biến**

Để lấy được kiểu dữ liệu là kiểu gì ví dụ như chuổi, số hay kiểu số thực ta dùng hàm type() như sau

{% highlight python  linenos %}

x = 5
y = "John"
print(type(x))
print(type(y))

{% endhighlight %}

## **3. Biến chứa giá trị chuỗi**

Chúng ta có thể sử dụng dấu ' giá trị ' hoặc dấu "" giá trị "" để khởi tạo giá trị chuỗi như sau

{% highlight python  linenos %}

x = "John" # is the same as
x = 'John'

{% endhighlight %}

## **4. CaseSensitive trong Python**

Trong Python tên biến là phân biệt chữ Hoa và chữ Thường. Ví dụ biến a = 4 và biến A = "Sally" là 2 biến hoàn toàn khác nhau.

{% highlight python  linenos %}

a = 4
A = "Sally" #A will not overwrite a

{% endhighlight %}


## **5. Tên biến**

Cũng giống như các ngôn ngữ lập trình khác. Biến trong Python phải được đặt đúng theo quy định

- Biến bắt đầu bằng một từ or dấu gạch dưới
- Biến không được bắt đầu là một số
- Biến chỉ có thể chứa các chữ trong bảng chữ và số alpha (A-z, 0 - 9)
- Biến phân biệt chữ hoa và chữ thường

Ví dụ sau đây là khai báo đúng chuẩn theo Python

{% highlight python  linenos %}

myvar = "John"
my_var = "John"
_my_var = "John"
myVar = "John"
MYVAR = "John"
myvar2 = "John"

{% endhighlight %}

Ví dụ sau đây là khai báo không đúng chuẩn theo Python

{% highlight python  linenos %}

2myvar = "John"
my-var = "John"
my var = "John"

{% endhighlight %}

## **6. Tên biến nhiều từ**

Ví dụ nếu tên biến nhiều hơn 2 chữ thì ta có thể sử dụng Cammel giống java. Chữ đầu tiên viết thường. Ký tự thứ 2 của chữ thứ hai viết hoa như sau.

{% highlight python  linenos %}

myVariableName = "John" # chữ my viết thường, chữ cái đầu tiên Name viết hoa

{% endhighlight %}

Hoặc ta có thể viết Hoa ở mỗi ký tự đầu tiên

{% highlight python  linenos %}

MyVariableName = "John"

{% endhighlight %}

Hoặc ta có thể dùng dấu _ giữa các chữ như sau

{% highlight python  linenos %}

my_variable_name = "John"

{% endhighlight %}

## **7. Gán nhiều giá trị cho nhiều biến**

Python cho phép chúng ta gán nhiều giá trị cho nhiều biến như sau.

{% highlight python  linenos %}

x, y, z = "Orange", "Banana", "Cherry"

{% endhighlight %}

Biến x = Orange, biến y = Banana và biến z = Cherry.

## **8. Gán nhiều biến cùng một giá trị**

Chúng ta có thể gán nhiều biến cho một giá trị như sau.

{% highlight python  linenos %}

x = y = z = "Orange"

{% endhighlight %}

## **9. In giá trị ra màn hình**

Chúng ta sử dụng method print của Python để in các giá trị của biến ra màn hình nó giống như hàm System.out.print của java.

{% highlight python  linenos %}

x = "awesome"
print("Python is " + x)

{% endhighlight %}

## **10. Biến toàn cục**

Biến toàn cục là biến được tạo ra ngoài method. Có thể truy xuất bất cứ đâu.

{% highlight python  linenos %}

x = "awesome" //đây là biến toàn cục

def myfunc():
  print("Python is " + x) // trong function ta có thể gọi nó

myfunc()

{% endhighlight %}

## **11. Từ khóa global**

Khi chúng ta khai báo một biến trong một function thì phạm vi biến đó chỉ được sử dụng trong function đó , các function khác không thể gọi được. Cái này ta gọi là biến local chỉ tồn tại trong function. 

Nếu như ta muốn biến local trong function đó trở thành biến Global (toàn cục) thì ta sử dụng từ khóa global như sau

{% highlight python  linenos %}

def myfunc():
  global x
  x = "fantastic"

myfunc()

print("Python is " + x)

{% endhighlight %}
























