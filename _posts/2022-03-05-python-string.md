---
layout: course-python
title: String trong Python
slug : string-trong-python
category: laptrinhpython
tags: [python]
summery: String
image: /images/blog/feature_javascript.png
description : Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách sử dụng String trong Python. Để tạo ra kiểu dữ liệu string chúng ta có thể sử dụng một dấu một nháy hoặc hai dấu hai nháy như sau. 

youtubeId: t26YoNM_tvw
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các em, hôm nay anh sẽ hướng dẫn mọi người cách <b>  sử dụng String trong Python </b>. 

Để tạo ra kiểu dữ liệu string chúng ta có thể sử dụng một dấu ' hoặc hai dấu " như sau. 

{% highlight python  linenos %}

     hello = 'hello' 
     hello = "hello"

{% endhighlight %}

## **1. Gán nhiều dòng text cho biến**

Chúng ta có thể tạo ra một đoạn văn bản và gán cho biến bằng cách sử dụng dấu ba nháy """

{% highlight python  linenos %}

      a = """Lorem ipsum dolor sit amet,
      consectetur adipiscing elit,
      sed do eiusmod tempor incididunt
      ut labore et dolore magna aliqua."""
      print(a

{% endhighlight %}

Hoặc chúng ta có thể sử dụng 3 nháy ''' 

{% highlight python  linenos %}

      a = '''Lorem ipsum dolor sit amet,
      consectetur adipiscing elit,
      sed do eiusmod tempor incididunt
      ut labore et dolore magna aliqua.'''
      print(a)

{% endhighlight %}

## **2. Strings là một mảng**

Giống như các ngôn ngữ lập trình khác. Chuỗi là một mảng các ký tự, chúng ta sử dụng [] để lấy từng ký tự trong mảng.

{% highlight python  linenos %}

      a = "Hello, World!"
      print(a[1])

{% endhighlight %}

## **3. Duyệt qua chuỗi**

String là một mảng nên chúng ta có thể sử dụng vòng lặp để duyệt qua các ký tự trong chuỗi.

{% highlight python  linenos %}

      for x in "banana":
      print(x)

{% endhighlight %}

## **4. Lấy kích thước của chuỗi**

Chúng ta sử dụng phương thức len() để lấy độ dài của chuỗi.

{% highlight python  linenos %}

      a = "Hello, World!"
      print(len(a))

{% endhighlight %}

## **5. Kiểm tra ký tự hoặc từ có ở trong chuỗi**

Để kiểm tra ký tự hoặc một từ có nằm trong chuỗi không thì ta dùng từ khóa in

{% highlight python  linenos %}

      txt = "The best things in life are free!"
      print("free" in txt)

{% endhighlight %}

## **6. Kiểm tra ký tự hoặc từ không có trong chuỗi**

Ngược lại với việc kiểm tra có từ khóa trong chuỗi, thì để kiểm tra từ đó ko có trong chuỗi ta dùng từ khóa not in như sau

{% highlight python  linenos %}

      txt = "The best things in life are free!"
      print("expensive" not in txt)

{% endhighlight %}

## **7. Cắt chuỗi**

Chúng ta có thể lấy một nhóm ký tự trong chuỗi bằng hàm slice. Ví dụ như chữ Hello, World chúng ta có thể lấy ra chuỗi llo từ Hello World  như sau.

{% highlight python  linenos %}

      b = "Hello, World!"
      print(b[2:5])

{% endhighlight %}

Kết quả : llo.

Chúng ta có thể lấy một nhóm ký tự dự vào index cho vào. Ví dụ như chữ Hello, World chúng ta muốn lấy bắt đầu từ 0 cho đến vị trí thứ 5 để lấy được chữ Hello như sau

{% highlight python  linenos %}

      b = "Hello, World!"
      print(b[:5])

{% endhighlight %}

Kết quả : Hello.

Nếu chúng ta muốn lấy nhóm ký từ từ vị trí bắt đầu tới vị trí cuối cùng của chuỗi thì ta làm như sau.

{% highlight python  linenos %}

      b = "Hello, World!"
      print(b[2:])

{% endhighlight %}

Kết quả : llo, World!.

## **8. In chữ hoa**

Để in hoa các ký tự ta dùng hàm upper() như sau.

{% highlight python  linenos %}

      b = "Hello, World!"
      print(b[2:])

{% endhighlight %}

Kết quả là : HELLO, WORLD!.

## **9. In chữ thường**

Để in chữ thường ta dùng hàm lower() như sau

{% highlight python  linenos %}

      a = "Hello, World!"
      print(a.lower())

{% endhighlight %}

Kết quả là : hello, world!.

## **10. Xóa ký tự trắng**

Để xóa ký tự trắng ở 2 đầu của chuỗi,ta dùng hàm strip() như sau.

{% highlight python  linenos %}

      a = " Hello, World! "
      print(a.strip())

{% endhighlight %}

kết quả : Hello, World!.

## **11. Thay thế các ký tự trong chuỗi**

Ta dùng hàm replace để thay thế ký tự trong chuỗi như sau.

{% highlight python  linenos %}

      a = "Hello, World!"
      print(a.replace("H", "J"))

{% endhighlight %}

kết quả : Jello, World!.

## **12. Split các ký tự dựa vào các separator**

Chúng ta sử dụng hàm split để lấy ra các ký tự dựa vào các separator như sau:

{% highlight python  linenos %}

      a = "Hello, World!"
      print(a.split(","))

{% endhighlight %}

kết quả : ['Hello', ' World!'].

## **13. Cộng các chuỗi**

Chúng ta sử dụng dấu + để ghép 2 chuỗi lại với nhau.

{% highlight python  linenos %}

      a = "Hello"
      b = "World"
      c = a + b
      print(c)

{% endhighlight %}

kết quả : HelloWorld.

Hoặc chúng ta có thể sử dụng space và dấu "" để cộng chuỗi như sau.

{% highlight python  linenos %}

      a = "Hello"
      b = "World"
      c = a + " " + b
      print(c)

{% endhighlight %}

kết quả : Hello World.

## **14. Định dạng chuỗi**

Chúng ta có thể kết hợp chuỗi và số theo một định dạng nhất định bằng cách sử dụng hàm format() như sau.

{% highlight python  linenos %}

      age = 36
      txt = "My name is Le Academy, and I am {}"
      print(txt.format(age))

{% endhighlight %}

kết quả : My name is Le Academy, and I am 36.

Chúng ta có thể sử dụng bao nhiêu {} tùy thích như sau.

{% highlight python  linenos %}

      quantity = 4
      itemno = 567
      price = 89
      myorder = "I want {} pieces of item {} for {} dollars."
      print(myorder.format(quantity, itemno, price))

{% endhighlight %}

kết quả : I want 4 pieces of item 567 for 89 dollars..


## **14. Thêm ký tự đặt biệt trong chuỗi**

Chúng ta sử dụng \" chèn trước ký tự đặt biệt trong chuỗi như sau.

{% highlight python  linenos %}

      txt = "We are the so-called \"Le academy\" from the levunguyen.com"

{% endhighlight %}

kết quả : We are the so-called "Le academy" from the levunguyen.com.

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}


































