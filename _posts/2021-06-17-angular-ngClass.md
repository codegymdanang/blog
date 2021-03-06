---
layout: course-angular
title: Sử dụng Directive ngClass trong Angular
slug : su-dung-directive-ngclass-trong-angular
category: laptrinhweb
tags: [angular]
summery: NgClass 
image: /images/blog/angular.png
description : Bài viết giúp hiểu được NgClass trong Angular là gì? Tìm hiểu NgClass được sử dụng với mục đích và trong trường hợp nào khi lập trình web. Hướng dẫn cách thực hiện cú pháp NgClass trong Angular cũng như cách thao tác NgClass với mảng, cập nhật giá trị css động, css động với array, css động với đối tượng. Ngoài ra còn kèm theo hình ảnh ví dụ minh hoạ về cách làm directive NgClass trong Angular.
youtubeId: X45e7CHu8lA
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn,hôm nay anh sẽ hướng dẫn mọi người cách tạo <b>ngClass</b> là như thế nào? 

## **1. ngClass là gì**

Chúng ta sử dụng ngClass để thêm hay xoá một css trong phần tử html.

- Cú pháp ngIf như sau

{% highlight html  linenos %}

<element [ngClass]="expression">...</element>

{% endhighlight %}

- element : chính là phần tử của web
- expression : điều kiện và css được thêm vào


## **2. Ví dụ ngClass**

Ví dụ ta có một số thuộc tính css được định nghĩa trong file component app.component.css như sau

{% highlight css  linenos %}

.red { color: red; }
.size20 { font-size: 20px; }

{% endhighlight %}


Tiếp đến ta sẽ sử dụng nó trong file template html như sau

{% highlight html  linenos %}

<div [ngClass]="'red size20'"> Red Text with Size 20px </div>

{% endhighlight %}

## **3. ngClass với mảng**

Chúng ta có thể khai báo dạng mảng css trong file template html như sau

{% highlight html  linenos %}

<div [ngClass]="['red','size20']">Red Text with Size 20px </div>

{% endhighlight %}

## **4. Cập nhật giá trị css động**

Ví dụ trong file component class ta có biến cssStringVar. Sau đó ta gán nó qua bên template html, như vậy khi giá trị cssStringVar thay đổi thì nó sẽ cập nhật giá trị đó bên template html

- Ta có file component class như sau

{% highlight javascript  linenos %}

cssStringVar: string= 'red size20';

{% endhighlight %}

- Ta sẽ binding giá trị cssStringVar qua file template

{% highlight html  linenos %}

<div class="row">     
   <div [ngClass]="cssStringVar">Red Text with Size 20px : from component     </div> 
</div>

{% endhighlight %}

## **5. Cập nhật giá trị css động với array**

{% highlight javascript  linenos %}

cssArray:string[]=['red','size20']; 

{% endhighlight %}

- Ta sẽ binding giá trị cssArray qua file template

{% highlight html  linenos %}

<div class="row">
  <div [ngClass]="cssArray">
    Red Text with Size 20px  : from CSS Array
  </div>
</div>

{% endhighlight %}

## **6. Cập nhật giá trị css động với đối tượng**

- Ví dụ ta có class tên là CssClass

{% highlight javascript  linenos %}

class CssClass {
  red: boolean= true;
  size20: boolean= true; 
}

{% endhighlight %}

- Trong file component class ta tạo đối tượng CssClass

{% highlight javascript  linenos %}

cssClass: CssClass = new CssClass();

{% endhighlight %}

- Ta truyền qua file template html

{% highlight html  linenos %}

<div class="row">     
  <div [ngClass]="cssClass"> Red Text with Size 20px : from component as object</div> 
</div>

{% endhighlight %}

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}







