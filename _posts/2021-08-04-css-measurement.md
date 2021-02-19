---
layout: course-css
title: Sử dụng đơn vị đo trong CSS  
slug : su-dung-don-vi-do-trong-css
category: laptrinhweb
tags: [css]
summery: Đơn vi đo  
image: /images/blog/angular.png
description : Những chia sẻ trong bài giúp hiểu rõ các đơn vị đó tuyệt đối và tương đối trong lập trình web CSS bao gồm đơn vị đo centimeters, ex, in, millimeters, pica, point, pixel và phần trăm, em. Với những ví dụ minh hoạ chi tiết kèm theo cho mỗi đơn vị đo, bài viết sẽ hướng dẫn được bạn cách khai báo với mỗi đơn vị đo trong lập trình web. 
youtubeId: tg1An_pzd9Q
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trong quá trình làm <b>lập trình web</b>, khi thực hiện một số các thuộc tính đòi hỏi cần sử dụng các đơn vị đo độ dài. Vì vậy trong CSS cung cấp rất nhiều đơn vị đo để người dùng có thể thao tác dễ dàng và nhanh chóng trong quá trình làm các dự án <b>lập trình web CSS</b> bao gồm các đơn vị đo tuyệt đối và tương đối. Cụ thể đơn vị centimeters, ex, in, millimeters, pica, point, pixel và phần trăm, em.
<br>
Những chia sẻ dưới đây sẽ giúp các bạn hiểu rõ hơn các đơn vị đo trên, cũng như hướng dẫn cụ thể cách khai báo đối với mỗi đơn vị đo trong <b>lập trình web CSS</b> thông qua các ví dụ minh hoạ.


## **1. Đơn vị đo**

Trong css hỗ trợ cho chúng ta các đơn vị đo như inches, centimeters, phần trăm , em hoặc point 

- Ví dụ như ta muốn border của một table có kích thướt là 1px thì ta khai báo như sau.

{% highlight html linenos %}

   table { border :1px solid #C00; }

{% endhighlight %}

## **2. Đơn vị đo phần trăm**

Ví dụ anh mong muốn các chữ trong đoạn văn bản có chiều cao là 125% thì anh khai báo như sau

{% highlight html linenos %}

  p {font-size: 16pt; line-height: 125%;}

{% endhighlight %}

## **3. Đơn vị đo centimeters**

Ví dụ như anh mong muốn khoảng cách khối lệnh div  là 2 cm thì anh khai báo như sau

{% highlight html linenos %}

div { margin-bottom: 2cm;}

{% endhighlight %}

## **4. Đơn vị đo em**

Ví dụ anh mong muốn khoảng cách giữa các ký tự trong đoạn văn là 7em.

{% highlight html linenos %}

p {letter-spacing: 7em;}

{% endhighlight %}

## **5. Đơn vị đo ex**

Ví dụ anh muốn kích thước của fornt chữ cho chiều cao trong một đoạn văn bản

{% highlight html linenos %}

p {font-size: 24pt; line-height: 3ex;}

{% endhighlight %}

## **6. Đơn vị đo in**

Ví dụ anh muốn khoảng cách giữa các từ trong một văn bản cách nhau 15 inches


{% highlight html linenos %}

p {word-spacing: .15in;}

{% endhighlight %}

## **7. Đơn vị đo milimeters**

Ví dụ anh muốn khoảng cách giữa các từ trong một văn bản cách nhau 15 milimeters


{% highlight html linenos %}

p {word-spacing: .15mm;}

{% endhighlight %}

## **8. Đơn vị đo pica**

1 pica sẽ bằng 12 points do đó 6 pica sẽ tương ứng là 1 inch. Ví dụ anh muốn kích thướt font chữ trong đoạn văn bản là 20 pica.

{% highlight html linenos %}

p {font-size: 20pc;}

{% endhighlight %}

## **9. Đơn vị đo point**

Một point sẽ tương ứng với 1/72 inch. Ví dụ anh muốn font chữ có kích thướt 18pt 

{% highlight html linenos %}

body {font-size: 18pt;}

{% endhighlight %}

## **10. Đơn vị đo pixel**

Ví dụ anh muốn khoảng cách của đoạn văn bản cách lề là 25 pixel.

{% highlight html linenos %}

      p {padding: 25px;}

{% endhighlight %}

## **11. Demo Video**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **12. Thực hành online và source code**

{:refdef: style="text-align: center;"}
<a href="https://levunguyen.com/hoc-lap-trinh-online-editor-js/" target="_blank"> ![Sourcecode ](/images/icon/tryit.png){:class="img-responsive"} </a>
{: refdef}

{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/CSS-Fundamental" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}




