---
layout: course-angular
title: Sử dụng Directive NgSwitch trong Angular
slug : su-dung-directive-ngSwitch-trong-angular
category: laptrinhweb
tags: [angular]
summery: NgSwitch   
image: /images/blog/angular.png
description : Trong Angular, NgSwitch là một trong những directive được lựa chọn sử dụng phổ biến nhất. Bài viết giúp bạn hiểu được NgSwitch trong Angular là gì? Cú pháp của NgSwitch trong Angular là gì? Đưa ra các ví dụ minh hoạ để hiểu được mục đích của NgSwitch trong Angular là dùng để thêm, xoá các phần tử trên website. Hướng dẫn để kiểm tra điều kiện bằng trong NgSwitch và chỉ ra nó được kết hợp với NgSwitchcase và NgSwitchDefault như thế nào trong Angular.
youtubeId: 0734nF0B_BM
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn,hôm nay anh sẽ hướng dẫn mọi người cách tạo <b>NgSwitch</b> là như thế nào? 

## **1. NgSwitch là gì**

Chúng ta sử dụng ngSwitch để thêm hoặc xoá các phần tử trên website. Nó thường được kết hợp dùng chung với ngSwitchcase và ngSwitchDefault. Nó tương tự như mệnh đề switch trong javascript.

Cú pháp của ngSwitch như sau:

{% highlight html  linenos %}

 
<container_element [ngSwitch]="switch_expression">
    <inner_element *ngSwitchCase="match_expresson_1">...</inner_element>
    <inner_element *ngSwitchCase="match_expresson_2">...</inner_element>
    <inner_element *ngSwitchCase="match_expresson_3">...</inner_element>
    <inner_element *ngSwitchDefault>...</element>
</container_element>


{% endhighlight %}


## **2. Ví dụ NgSwitch**

Ví dụ ta làm một ứng dụng web. Khi người dùng nhập vào số 1 ta in ra tiếng Anh là One, 2 là Two, 3 là Three , 4 là Four, 5 là Five. Nếu nhập vào số 8 thì sẽ hiển thị giá trị mặt định vì số 8 không rơi vào trường hợp switchcase nào cả nên nó sẽ nhảy vô switch case default.

{% highlight javascript  linenos %}

export class AppComponent
{

   num: number= 0;
}

{% endhighlight %}

{% highlight html  linenos %}

<div class='card'>
  <div class='card-header'>
    ngSwitch Example
  </div>
  <div class="card-body">
    Input string : <input type='text' [(ngModel)]="num" />
 
    <div [ngSwitch]="num">
      <div *ngSwitchCase="'1'">One</div>
      <div *ngSwitchCase="'2'">Two</div>
      <div *ngSwitchCase="'3'">Three</div>
      <div *ngSwitchCase="'4'">Four</div>
      <div *ngSwitchCase="'5'">Five</div>
      <div *ngSwitchDefault>This is Default</div>
    </div>
  </div>
</div>
{% endhighlight %}

## **3. Kiểm tra điều kiện bằng trong ngSwitch**

Trong ngSwitch nếu ta nhập chuỗi rỗng nó sẽ tương ứng với giá trị 0. Ví dụ dưới đây nếu ta không nhập giá trị gì cho biến num. Thì mặc định giá trị num sẽ là 0 và rơi vào trường hợp ngSwitchCase="0"

{% highlight html  linenos %}

<div [ngSwitch]="num">
      <div *ngSwitchCase="0">Zero is Selected</div>
      <div *ngSwitchCase="1">One is Selected</div>
      <div *ngSwitchCase="2">Two is Selected</div>
      <div *ngSwitchDefault>This is Default 2</div>
    </div>
{% endhighlight %}
