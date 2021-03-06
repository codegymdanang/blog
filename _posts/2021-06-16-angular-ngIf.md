---
layout: course-angular
title: Sử dụng Directive ngIf trong Angular
slug : su-dung-directive-ngif-trong-angular
category: laptrinhweb
tags: [angular]
summery: NgIF
image: /images/blog/angular.png
description : Trong Angular, NgIf là một trong những directive được lựa chọn sử dụng phổ biến nhất. Bài viết giúp bạn hiểu được NgIf trong Angular là gì? Cú pháp của NgIf trong Angular là gì? Đưa ra các ví dụ minh hoạ để hiểu được mục đích của NgIf trong Angular. Hướng dẫn để sử dụng phủ định, if else, then else trong NgIf. Kèm theo ví dụ cụ thể về sử dụng NgIf và NgModeal để lấy một giá trị true nào đó. 
youtubeId: dVwdaTKaO20
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn,hôm nay anh sẽ hướng dẫn mọi người cách tạo <b>ngIf</b> là như thế nào? 

## **1. ngIf là gì**

Chúng ta sử dụng ngIf để xóa hoặc thêm một phần tử trên web dựa vào điều kiện có thoả mãn hay không.

- Cú pháp ngIf như sau:

{% highlight html  linenos %}

<p *ngIf="condition">
    các thẻ html sẽ được hiển thị nếu điều kiện là đúng
</p>

{% endhighlight %}

- Chúng ta có thể sử dụng thuộc tính hide để làm điều tương tự như sau:

{% highlight html  linenos %}

<p [hidden]="condition">
    content to render, when the condition is true 
</p>


{% endhighlight %}

Sự khác nhau ở chỗ ngIf sẽ xóa hoàn toàn phần tử web ra khỏi DOM. Còn hide thì không xoá hẳn phần tử đó ra khỏi DOM. Mặc dù trên giao diện ta thấy phần tử đó bị mất đi.

## **2. Sử dụng phủ định trong ngIf**

{% highlight html  linenos %}

<p *ngIf="!condition">
    content to render, when the condition is false
</p>

{% endhighlight %}

## **3. Sử dụng if else trong ngIf**

{% highlight html  linenos %}

<div *ngIf="condition; else elseBlock">
    content to render, when the condition is true 
</div>
 
<ng-template #elseBlock>
    content to render, when the condition is false 
</ng-template>

{% endhighlight %}

## **4. Sử dụng then else trong ngIf**

{% highlight html  linenos %}

<div *ngIf="condition; then thenBlock else elseBlock"> 
    This content is not shown
</div>
 
<ng-template #thenBlock>
    content to render when the condition is true.
</ng-template>
 
<ng-template #elseBlock>
    content to render when condition is false.
</ng-template>

{% endhighlight %}


## **5.Ví dụ ngIf**

Ta sẽ làm ví dụ về kiểm tra một check box có bị check hay không? Nếu check box bị check thì ta sẽ thay đổi giá trị.

Ta có component class có chứa giá trị showMe. Mặc định là true.

{% highlight javascript  linenos %}

import { Component } from '@angular/core';
 
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title: string = 'ngIf Example' ;
  showMe: boolean;
}

{% endhighlight %}

Tiếp đến ta có file template html như sau:

{% highlight html  linenos %}

<h1>Simple example of ngIf </h1>
 
 
<div class="row">
  Show <input type="checkbox" [(ngModel)]="showMe" />
</div>
 
<h1>ngIf </h1>
 
<p *ngIf="showMe">
  ShowMe is checked
</p>
<p *ngIf="!showMe">
  ShowMe is unchecked
</p>
 
<h1>ngIf Else</h1>
 
<p *ngIf="showMe; else elseBlock1">
  ShowMe is checked
</p>
 
<ng-template #elseBlock1>
  <p>ShowMe is unchecked Using elseBlock</p>
</ng-template>
 
<h1>ngIf then else</h1>
 
<p *ngIf="showMe; then thenBlock2 else elseBlock2">
  This is not rendered
</p>
 
<ng-template #thenBlock2>
  <p>ShowMe is checked Using thenblock</p>
</ng-template>
 
<ng-template #elseBlock2>
  <p>ShowMe is unchecked Using elseBlock</p>
</ng-template>
 
<h1>using hidden </h1>
 
<p [hidden]="showMe">
    content to render, when the condition is true  using hidden property binding
</p>
 
<p [hidden]="!showMe">
    content to render, when the condition is false. using hidden property binding
</p>
{% endhighlight %}

Chúng ta sử dụng ngIf và sử dụng ngModel để lấy giá trị của showMe. Nếu true thì ta sẽ show ra dòng chữ ShowMe is checked còn ngược lại là ShowMe is unchecked.

## **6. Video Demo**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **7. Source code**


{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/Angular-Template-Form" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>










