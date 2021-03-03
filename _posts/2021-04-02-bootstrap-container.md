---
layout: course-bootstrap
title: Sử dụng Container trong Bootstrap 
slug : su-dung-container-trong-bootstrap
category: laptrinhweb
tags: [bootstrap]
summery: Container
image:
description : Trong lập trình web Bootstrap, để thiết lập độ dài cố định cho nội dung các phần tử trong website, các lập trình viên sẽ dùng thuộc tính Container. Bài viết này sẽ giúp các bạn hiểu được 2 loại thuộc tính Container trong Bootstrap gồm container và container-fluid là gì? Và hướng dẫn cách để các bạn sử dụng được Container trong lập trình web thông qua các hình ảnh ví dụ minh hoạ kèm theo như thiết lập độ dài cố định, độ dài tràn màn hình, cấu hình padding, border, color, responsive cho container.
youtubeId: 9jfnqDnzTqY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trong quá trình <b>lập trình web</b>, chắc hẳn các bạn sẽ gặp phải tình huống muốn thiết lập độ dài cố định cho nội dung các phần tử trong website để nội dung được bố trí rõ ràng hơn. Từ đó giúp người dùng có những trải nghiệm tốt nhất khi sử dụng trang web của bạn.

<br>
Để giải quyết trường hợp này, lúc này các lập trình viên sẽ phải cần dùng đến thuộc tính <b>container</b> trong Bootstrap. Đó cũng chính là chủ đề hôm nay mà anh muốn chia sẻ với các bạn, sử dụng Container trong Bootstrap. Trước khi đi vào cụ thể cách sử dụng, anh sẽ giải thích, giới thiệu về 2 loại Bootstrap gồm container và container-fluid để các bạn hiểu được thuộc tính này là gì? Sau đó chúng ta sẽ lần lượt đi qua các phần hướng dẫn cách để sử dụng với Container như thiết lập độ dài cố định, độ dài tràn màn hình, cấu hình padding, border, color, responsive cho container.

<br>
Hi vọng những chia sẻ dưới đây cùng với những ví dụ minh hoạ cụ thể cho mỗi phần sẽ giúp các bạn dễ dàng nắm bắt được kiến thức này và áp dụng được quá trình <b>lập trình web</b> một cách hiệu quả nhất.
 

## **1. Container là gì**

<b>Container</b> chúng ta sử dụng để bọc tất cả các thành phần của web vào trong nó. Nó giống như một cái khung trong đó ta chứa đựng các thành phần của web. Có 2 loại containers được sử dụng để bao bọc các phần tử web đó là container và container-fluid


{:refdef: style="text-align: center;"}
![container](/images/post/boostrap/container.png){:class="img-responsive"}
{: refdef}

Như các em thấy thiết kế blog của anh. Ngay tại trang chủ levunguyen.com anh sử dụng container để bao bọc các thành phần website. Các em sẽ thấy có khoảng trống ở bên tay trái và tay phải. Còn nội dung sẽ ở phần ở giữa. Sử dụng container khi chúng ta muốn thiết lập độ dài cố định cho nội dung các phần tử trong website

Còn khi các em vào các bài đọc chi tiết anh sử dụng container-fluid thì nội dung sẽ tràn đầy màn mình không có khoảng trống bên trái và bên phải

## **2. Thiết lập độ dài cố định**

Chúng ta sử dụng container khi muốn nội dung cố định của khung hiển thị. 

<br>
{% highlight html  linenos %}

 <div class="container">
  <h1>My First Bootstrap Page</h1>
  <p>This is some text.</p>
</div> 

{% endhighlight %}


## **3. Thiết lập độ dài tràn màn hình**

Chúng ta sử dụng container-fluid để tạo ra khung có chiều dài là tràn màn hình.

<br>
{% highlight html  linenos %}

 <div class="container-fluid">
  <h1>My First Bootstrap Page</h1>
  <p>This is some text.</p>
</div> 

{% endhighlight %}

## **4. Cấu hình padding cho container**

Mặc định các container trong bootstrap có padding left và right là 15px. Nó không có padding top và bottom. Chúng ta có thể thêm thuộc tính pt để container có thể padding top như sau

<br>
{% highlight html  linenos %}

 <div class="container pt-3"></div> 

{% endhighlight %}

## **5. Cấu hình border và color cho container**

<br>
{% highlight html  linenos %}

<div class="container p-3 my-3 border"></div>

<div class="container p-3 my-3 bg-dark text-white"></div>

<div class="container p-3 my-3 bg-primary text-white"></div> 
{% endhighlight %}

## **6. Cấu hình Responsive kích thướt cho container**

Chúng ta có thể sử dung container-sm|md|lg|xl để tạo nên chức năng responsive cho website hiển thị trên các thiết bị khác nhau. Ứng với mỗi sm, md, lg, xl tương ứng với độ rộng theo px như sau.

{:class="table table-bordered"}
|  class            |  màn hình cực nhỏ (<576px) |  màn hình nhỏ (>=576px) | màn hình vừa (>= 768px) | màn hình lớn (>=992px) | màn hình cực lớn|
|---                |---                         |---                      |---                      |---                     |---              |
| .container-sm     | 100%                       | 540px                   |  720px                  | 960px                  | 1140px          |
| .container-md     | 100%                       | 100%                    |  720px                  | 960px                  | 1140px          |
| .container-lg     | 100%                       | 100%                    |  100%                   | 960px                  | 1140px          |
| .container-xl     | 100%                       | 100%                    |  100%                   | 100%                   | 1140px          |

<br>
{% highlight html  linenos %}

<div class="container-sm">.container-sm</div>
<div class="container-md">.container-md</div>
<div class="container-lg">.container-lg</div>
<div class="container-xl">.container-xl</div> 

{% endhighlight %}

## **7. Video demo**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **8. Thực hành và Source code**

{:refdef: style="text-align: center;"}
<a href="https://levunguyen.com/hoc-lap-trinh-online-editor-js/" target="_blank"> ![Sourcecode ](/images/icon/tryit.png){:class="img-responsive"} </a>
{: refdef}

{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/Bootstrap" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}