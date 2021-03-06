---
layout: course-angular
title: Sử dụng Directive trong Angular  
slug : su-dung-directive-trong-angular
category: laptrinhweb
tags: [angular]
summery: Directive   
image: /images/blog/angular.png
description : Directive trong Angular được sử dụng để thao tác, cập nhật các thành phần giao diện khi lập trình web. Angular Directive được chia 3 loại gồm Component  Directive, Structural Directive và Attribute Directive. Ngoài ra các lập trình viên cũng có thể tự tạo ra một directive riêng cho dự án gọi là Customs Directive. Bài viết trình bày để bạn hiểu được các khái niệm trên là gì và hướng dẫn cách để tạo, thêm và sử dụng Directive trong dự án Angular.
youtubeId: 0734nF0B_BM
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn, hôm nay anh sẽ hướng dẫn mọi người cách tạo <b>Directive</b> là như thế nào? 

## **1. Directive là gì**

Chúng ta sử dụng Directive để thao tác, cập nhật, thêm, xóa các thành phần giao diện trên web. Hay nói cách khác chúng ta thao tác với các element của DOM. Các nút, ảnh, text box, table mà ta thấy trên website được một đối tượng DOM quản lý. DOM có nhiệm vụ vẽ ra các đối tượng này trên website để ta có thể thấy được.

Angular Directive được chia là 3 loại gồm:

- Component Directive
- Structural Directive
- Attribute Directive

## **2. Component Directive là gì**

Component directive là ví dụ về khách hàng mà ta đã làm trong bài thêm component con và component cha ở [đây](https://levunguyen.com/laptrinhweb/2021/06/09/angular-add-child-component/)

## **3. Structural Directive là gì**

Chúng ta sử dụng Structure Directive để thay đổi layout của trang website bằng cách thêm hoặc xóa các thành phần trên web (DOM Elements).

Một số thẻ về Structural Directive như

- ngFor : dùng để lặp lại các phần HTML cho mỗi item. Nó giống như vòng lặp for. Mỗi lần lặp nó sẽ chạy lại các đoạn code trong vòng lặp

{% highlight html  linenos %}

<tr *ngFor="let customer of customers;">
    <td>{{customer.customerNo}}</td>
    <td>{{customer.name}}</td>
    <td>{{customer.address}}</td>
    <td>{{customer.city}}</td>
    <td>{{customer.state}}</td>
</tr>

{% endhighlight %}

- ngSwitch : chúng ta dùng để quyết định thêm hoặc xóa các thành phần của web phụ thuộc vào điều kiện có thoả mãn hay không. Chúng ta thường dùng chung với ngSwitchCase và ngSwitchDefault

{% highlight html  linenos %}

<div [ngSwitch]="Switch_Expression"> 
    <div *ngSwitchCase="MatchExpression1”> First Template</div>
    <div *ngSwitchCase="MatchExpression2">Second template</div> 
    <div *ngSwitchCase="MatchExpression3">Third Template</div> 
    <div *ngSwitchCase="MatchExpression4">Third Template</div> 
    <div *ngSwitchDefault?>Default Template</div>
</div>

{% endhighlight %}

- ngIf : chúng ta sử dụng ngIf để thêm và xóa các thành phần HTML dựa vào điều kiện có thoả mãn không. Điều kiện phải đúng mới thực hiện các câu lệnh bên trong.

{% highlight html  linenos %}

<div *ngIf="condition"> 
    This is shown if condition is true
</div>

{% endhighlight %}

## **4. Attribute Directive là gì**

Attribute Directive được dùng để thay đổi sự hiển thị hoặc hành vi của một thành phần trên web.

- ngModel : được sử dụng cho việc binding 2 chiều như ta đã học trong bài databinding.

- ngClass : được sử dụng để thêm hoặc xoá một class của một thành phần web.

{% highlight html  linenos %}

<div [ngClass]="'first second'">...</div>

{% endhighlight %}

- ngStyle : dùng để thêm nhiều thuộc tính css cho một thành phần của web.

{% highlight html  linenos %}

<div [ngStyle]="{'color': 'blue', 'font-size': '24px', 'font-weight': 'bold'}">
    some text
</div> 

{% endhighlight %}

## **5. Customs Directive là gì**

Ngoài các Directive có sẵn trong Angular chúng ta có thể tự tạo ra một directive riêng cho chính mình. Chúng ta sẽ xem bài sau về cách tạo một Directive riêng cho dự án.












