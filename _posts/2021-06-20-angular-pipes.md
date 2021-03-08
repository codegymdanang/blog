---
layout: course-angular
title: Sử dụng Pipes trong Angular 
slug : su-dung-pipes-trong-angular
category: laptrinhweb
tags: [angular]
summery: Pipes  
image: /images/blog/angular.png
description : Khi lập trình web, để định dạng lại các kiểu hiển thị trên website người dùng sẽ phải sử dụng đến Angular Pipes. Bài viết dưới đây sẽ giúp hiểu được Pipes trong Angular là gì? Cách sử dụng Date Pipes, UpperCasePipe và LowerCasePipe, SlicePipe, DecimalPipe và NumberPipe, PercentePipe và CurrencyPipe trong Angular. Đồng thời đưa ra các hình ảnh ví dụ minh hoạ cú pháp thực hiện cho mỗi tác vụ trên của Pipes trong Angular.
youtubeId: AOZ0_At_l90
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn, hôm nay anh sẽ hướng dẫn mọi người cách tạo <b>Pipes</b> là như thế nào? 

## **1. Pipes là gì**

Chúng ta sử dụng Angular Pipes để định dạng lại kiểu hiển thị trên webiste. Ví dụ như kiểu ngày, tháng chúng ta muốn hiển thị theo kiểu MM-DD-YYYY (01-01-1983) cho người dùng.


## **2. Date Pipes là gì**

Sử dụng để định dạng lại kiểu ngày tháng trên website.

Cú pháp

{% highlight javascript linenos %}

date_expression | date[:format]

{% endhighlight %} 

- date_expression là đối tượng ngày hoặc là một kiểu số.
- data : tên của pipe sẽ được dùng để định dạng dữ liệu.

{% highlight js linenos %}

<h3>Using Date Pipe </h3>
<p>Unformatted date : { { toDate } } </p>     //Without pipe
<p>Formatted date :  { {toDate | date } } </p>   //With Date Pipe

{% endhighlight %} 

- Không có pipe ta sẽ nhận được là : Sun May 24 2020 19:30:12 GMT +0720 (Hong Kong)
- Có pipe thì sẽ được hiển thị là : May 24 2020

## **3. UpperCasePipe & LowerCasePipe**

Được sử dụng để viết hoa toàn bộ hoặc viết thường toàn bộ dữ liệu. Ví dụ như sau:

{% highlight javascript linenos %}

import { Component } from '@angular/core';
import { FormsModule } from '@angular/forms';
 
@Component({
    selector: 'app-root',
    template:'<p>Unformatted : { { msg } } </p>
              <p>Uppercase : { { msg | uppercase } } </p>
              <p>Lowercase : { {msg | lowercase } } </p>'
})
export class AppComponent
{
    title: string = 'Angular pipes Example' ;
    msg: string= 'Welcome to Angular';
}
 
{% endhighlight %} 

## **4. SlicePipe**

Dùng để cắt một chuỗi từ vị trí muốn cắt đến vị trí kết thúc.

{% highlight javascript linenos %}

import { Component } from '@angular/core';
import { FormsModule } from '@angular/forms';
@Component({
    selector: 'app-root',
    template:'<p>Complete String :{ { msg } } </p>
              <p>Example 1 : { {msg | slice:11:20 } } </p>
              <p>Example 2 : { {msg | slice:-9 } } </p>'
})
 
export class AppComponent
{
    title: string = 'Angular pipes Example' ;
    msg: string= 'Welcome to Angular ';
}

{% endhighlight %} 

## **5. DecimalPipe và NumberPipe**

Dùng để format cho kiểu số và kiểu thập phân. Với cú pháp như sau:

{% highlight javascript linenos %}

number_expression | number[:digitInfo]

{% endhighlight %} 

- number_expression : số mà mình cần format
- number tên pipe

## **6. PercentePipe**

Định dạnh số theo phần trăm

{% highlight javascript linenos %}

import { Component } from '@angular/core';
import { FormsModule } from '@angular/forms';
 
@Component({
    selector: 'app-root',
    template:'<p>Unformatted :{ { per } } </p>
              <p>Example 1 : { {per | percent  } } </p>
              <p>Example 2 : { {per | percent:'1.2-2' } } </p>'
})
export class AppComponent
{
    title: string = 'Angular pipes Example' ;
    per: number= .7414;2';
}

{% endhighlight %} 

## **7. CurrencyPipe**

Định dạng để sử dụng cho tiền tệ như USD, hay VNĐ

{% highlight javascript linenos %}

import { Component } from '@angular/core';
import { FormsModule } from '@angular/forms';
@Component({
    selector: 'app-root',
    template: '<p>Unformatted :{ { cur } } </p>
               <p>Example 1 :{ {cur | currency } } </p>
               <p>Example 2 :{ {cur | currency:'INR':true:'4.2-2' } } </p>'
})
 
export class AppComponent
{
    title: string = 'Angular pipes Example' ;
    cur: number= 175;
}

{% endhighlight %} 

## **8. Video Demo**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **9. Source code**


{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/Angular-Directive-Pipe" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
