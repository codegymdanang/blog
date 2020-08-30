---
layout: course-angular
title: Angular Pipes 
slug : angular-pipes
category: laptrinhweb
tags: [angular]
summery: Pipes  
image: /images/blog/angular.png
description : Thêm Pipes trong dự án angular. Hướng dẫn sử dụng Pipes vào dự án Angular. Hướng dẫn các tạo Pipes vào dự án.
youtubeId: 0734nF0B_BM
---

# **Giới thiệu nội dung bài viết**

Chào các bạn,hôm nay anh sẽ hướng dẫn mọi người cách tạo <b>Pipes</b> là như thế nào? 

# **1. Pipes là gì**

Chúng ta sử dụng Angular Pipes để định dạng lại kiểu hiểu thị trên webiste. Ví dụ như kiểu ngày tháng chúng ta muốn hiển thị theo kiểu MM-DD-YYYY (01-01-1983) cho người dùng.


# **2. Date Pipes là gì**

Sử dụng để định dạng lại kiểu ngày tháng trên website.

Cú pháp

{% highlight js linenos %}

date_expression | date[:format]

{% endhighlight %} 

- date_expression là đối tượng ngày hoặc là một kiểu số
- data : tên của pipe sẽ được dùng để định dạng dữ liệu

Ví dụ

{% highlight js linenos %}

<h3>Using Date Pipe </h3>
<p>Unformatted date : {{toDate }} </p>     //Without pipe
<p>Formatted date : {{toDate | date}} </p>   //With Date Pipe

{% endhighlight %} 

- Không có pipe ta sẽ nhận được là : Sun May 24 2020 19:30:12 GMT +0720 (Hong Kong)
- Có pipe thì sẽ được hiển thị là : May 24 2020

# **3. UpperCasePipe & LowerCasePipe**

Được sử dụng để viết hoa toàn bộ hoặc viết thường toàn bộ dữ liệu . Ví dụ như sau

{% highlight js linenos %}

import { Component } from '@angular/core';
import { FormsModule } from '@angular/forms';
 
@Component({
    selector: 'app-root',
    template:'<p>Unformatted :{{msg}} </p>
              <p>Uppercase :{{msg | uppercase}} </p>
              <p>Lowercase :{{msg | lowercase}} </p>'
})
export class AppComponent
{
    title: string = 'Angular pipes Example' ;
    msg: string= 'Welcome to Angular';
}
 
{% endhighlight %} 



