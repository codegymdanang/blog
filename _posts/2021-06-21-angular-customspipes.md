---
layout: course-angular
title: Tự tạo Pipes 
slug : angular-custom-pipes
category: laptrinhweb
tags: [angular]
summery: Tự tạo Pipes  
image: /images/blog/angular.png
description : Tự tạo Pipes trong dự án angular. Hướng dẫn Tự tạo Pipes  Pipes vào dự án Angular. Sử dụng tự tạo Pipes  vào dự án.
youtubeId: 0734nF0B_BM
---

# **Giới thiệu nội dung bài viết**

Chào các bạn,hôm nay anh sẽ hướng dẫn mọi người cách tạo <b>Customs Pipes</b> là như thế nào? 

# **1. Custom Pipes là gì**

Chúng ta sử dụng Angular Pipes để định dạng lại kiểu hiểu thị trên webiste. Ngoài các kiểu có sẳn định dạng cho ngày, tiền tệ, số thì ta có thể tự viết một pipe riêng.


# **2. Tự tạo Pipes hiển thị nhiệt độ**

- Bước 1 : Chúng ta tạo file temp-convertor.pipe.ts

Cú pháp

{% highlight js linenos %}

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

{% highlight js linenos %}

import { Pipe, PipeTransform } from '@angular/core';

{% endhighlight %} 

Tiếp theo ta định nghĩa annotation pipe và đặt tiên là tempConverter

{% highlight js linenos %}

@pipe( {
    name: 'tempConverter'
} )

{% endhighlight %} 

Viết file converter nhiệt độ. File này sẽ implement PipeTransform

{% highlight js linenos %}

@pipe( {
    name: 'tempConverter'
} )
export class TempConverterPipe implements PipeTransform {
 
 
}
{% endhighlight %} 

- Bước 2 : Viết lại nghiệp vụ coverter trong method transform của PipeTransform

{% endhighlight %} 

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

{% highlight js linenos %}

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






