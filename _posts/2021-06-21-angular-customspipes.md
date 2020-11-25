---
layout: course-angular
title: Hướng dẫn tự tạo Pipes trong Angular 
slug : huong-dan-tu-tao-pipes-trong-angular
category: laptrinhweb
tags: [angular]
summery: Tự tạo Pipes  
image: /images/blog/angular.png
description : Bên cạnh các Pipes có sẵn trong Angular như ngày, tiền tệ, số, phần trăm thì người dùng có thể tự viết một Pipe riêng để sử dụng. Bài viết sẽ hướng dẫn bạn cách tự tạo Pipes trong dự án Angular như Pipes hiển thị nhiệt độ. Đồng thời hướng dẫn cách để sử dụng những Pipes tự tạo đó vào dự án Angular. Bài viết đưa ra các hình ảnh ví dụ minh hoạ cho cú pháp thực hiện Customs Pipes trong Angular.
youtubeId: 0734nF0B_BM
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn, hôm nay anh sẽ hướng dẫn mọi người cách tạo <b>Customs Pipes</b> là như thế nào? 

## **1. Custom Pipes là gì**

Chúng ta sử dụng Angular Pipes để định dạng lại kiểu hiển thị trên webiste. Ngoài các kiểu có sẵn định dạng cho ngày, tiền tệ, số thì ta có thể tự viết một pipe riêng.


## **2. Tự tạo Pipes hiển thị nhiệt độ**

- Bước 1 : Chúng ta tạo file temp-convertor.pipe.ts

Cú pháp

{% highlight javascript linenos %}

import { Pipe, PipeTransform } from '@angular/core';
 
@pipe( {
    name: 'tempConverter'
} )
export class TempConverterPipe implements PipeTransform {
    transform(value: number, unit: string) {
        if(value && !isNaN(value)) {
            if (unit === 'C') {
                var temperature = (value - 32) /1.8 ;
                return temperature.toFixed(2);
            } else if (unit === 'F'){
                var temperature = (value * 1.8 ) + 32
                return temperature.toFixed(2);
            }
        }
        return;
    }
}

{% endhighlight %} 

Đầu tiên chúng ta import thư viện Pipe vào 

{% highlight javascript linenos %}

import { Pipe, PipeTransform } from '@angular/core';

{% endhighlight %} 

Tiếp theo ta định nghĩa annotation pipe và đặt tên là tempConverter

{% highlight javascript linenos %}

@pipe( {
    name: 'tempConverter'
} )

{% endhighlight %} 

Viết file converter nhiệt độ. File này sẽ implement PipeTransform

{% highlight javascript linenos %}

@pipe( {
    name: 'tempConverter'
} )
export class TempConverterPipe implements PipeTransform {
 
 
}
{% endhighlight %} 

- Bước 2 : Viết lại nghiệp vụ coverter trong method transform của PipeTransform


{% highlight javascript linenos %}

export class TempConverterPipe implements PipeTransform {
 
    transform(value: number, unit: string) {
        if(value && !isNaN(value)) {
            if (unit === 'C') {
               var temperature = (value - 32) /1.8 ;
               return temperature.toFixed(2);
            } else if (unit === 'F'){
               var temperature = (value * 1.8 ) + 32
               return temperature.toFixed(2);
            }
        }
        return;
    }
 
}
{% endhighlight %} 

- Bước 3 : Khai báo TempConverterPipe trong AppModule

{% highlight javascript linenos %}

import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { FormsModule } from '@angular/forms';
import { HttpModule } from '@angular/http';
 
import { AppComponent } from './app.component';
 
import {TempConverterPipe} from './temp-convertor.pipe';
 
@NgModule({
    declarations: [AppComponent,TempConverterPipe],
    imports: [BrowserModule,FormsModule,HttpModule],
    bootstrap: [AppComponent]
})
export class AppModule { }
{% endhighlight %} 

- Bước 4 : Sử dụng Pipe

{% highlight html linenos %}

<div class='card'>
  <div class='card-header'>
    <p>{{title}} </p>
  </div>
  <div class="card-body">
 
    <div class="row">
      <h3>Fahrenheit to Celsius </h3>
    </div>
    <div class="row">
      <p> Fahrenheit : <input type="text" [(ngModel)]="Fahrenheit" /> 
      Celsius : { { Fahrenheit | tempConverter:'C' } } </p>
    </div>
 
    <div class="row">
      <h3>Celsius to Fahrenheit </h3>
    </div>
    <div class="row">
      <p> celsius : <input type="text" [(ngModel)]="celcius" /> 
       Fahrenheit : { { celcius | tempConverter:'F' } } </p>
    </div>
  </div>
</div>

{% endhighlight %} 






