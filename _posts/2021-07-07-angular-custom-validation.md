---
layout: course-angular
title: Tạo Custom Validation trong Angular 
slug : tao-custom-validation-trong-angular
category: laptrinhweb
tags: [angular]
summery: Custom Validation   
image: /images/blog/angular.png
description : Custom Validation là những validator được tự tạo bởi người dùng, được sử dụng cho các dự án Angular ngoài những validator được hỗ trợ có sẵn trong Angular như required, minlength, maxlength, pattern và email. Bài viết dưới đây sẽ hướng dẫn bạn cách sử dụng Custom Validator trong Angular như thế nào cho hiệu quả, và cách thực hiện code hoàn chỉnh cho component class và template html trong Angular. Mỗi phần của bài viết kèm theo những ví dụ minh hoạ cú pháp thực hiện từng bước của custom validation vào dự án Angular.
youtubeId: OzSpfRO-AcM
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn, hôm nay anh sẽ hướng dẫn mọi người cách <b>Custom Validation</b> là như thế nào?

## **1.Custom Validation là gì**

Angular hỗ trợ một số validator như required, minlength, maxlength, pattern và email như ta đã xem ở bài trước. Ngoài những validator có sẵn của Angular ta hoàn toàn có thể tự tạo một validator cho dự án của mình.


## **2.Sử dụng Validator như thế nào**

Giả sử ta có form trong file template html như sau.

{% highlight javascript linenos %}

<h1>Custom Validator in Angular</h1>
 
<h2>Reactive Form</h2>
 
<form [formGroup]="myForm" (ngSubmit)="onSubmit()" novalidate>
 
  <div>
    <label for="numVal">Number :</label>
    <input type="text" id="numVal" name="numVal" formControlName="numVal">
  </div>
 
  <p>Is Form Valid : {{myForm.valid}} </p>
 
  <p>
    <button type="submit" [disabled]="!myForm.valid">Submit</button>
  </p>
 
</form>

{% endhighlight %} 

Như các em thấy ta có 1 field trong form là numVal. Chúng ta muốn giá trị trong numVal phải lớn hơn 10.

Bây giờ ta sẽ định nghĩa một Validator riêng cho việc kiểm tra giá trị lớn hơn 10. Ta tạo một file gte.validator.js như sau:

{% highlight javascript linenos %}

import { AbstractControl, ValidationErrors } from '@angular/forms'
 
export function gte(control: AbstractControl): ValidationErrors | null {
 
    const v=+control.value;
 
    if (isNaN(v)) {
      return { 'gte': true, 'requiredValue': 10 }
    }      
 
    if (v <= 10) {
      return { 'gte': true, 'requiredValue': 10 }
    } 
 
    return null
 
}

{% endhighlight %} 

Đầu tiên chúng ta import thư viện AbstractControl và Validation Error từ Angular Form.

{% highlight javascript linenos %}

import { AbstractControl, ValidationErrors } from '@angular/forms'

{% endhighlight %} 

ValidatorError chứa cặp key và value. Key là tên của rule chúng ta muốn sử dụng và value có thể làm bất cứ cái gì.

Trong ví dụ sau chúng ta kiểm tra giá trị của control có phải là số hay không. Để kiểm tra số ta dùng hàm isNaN. Đồng thời kiểm tra giá trị nhỏ hơn hay bằng 10. Nếu cả 2 điều kiện là đúng thì trả về null.

{% highlight javascript linenos %}

const v=+control.value;
 
    if (isNaN(v)) {
      return { 'gte': true, 'requiredValue': 10 }
    }      
 
    if (v <= 10) {
      return { 'gte': true, 'requiredValue': 10 }
    } 
 
    return null
{% endhighlight %} 

Nếu validator bị sai thì trả về Validator Error.

{% highlight javascript linenos %}

return { 'gte': true, 'requiredValue': 10 }

{% endhighlight %}

Để sử dụng Custom validator chúng ta import vào component class.

{% highlight javascript linenos %}

import { gte } from './gte.validator';

{% endhighlight %}

Thêm validator vào form như sau.


{% highlight javascript linenos %}

 myForm = new FormGroup({
    numVal: new FormControl('', [gte]),
  })
{% endhighlight %}

## **3. Code hoàn chỉnh cho component class**

{% highlight javascript linenos %}

import { Component } from '@angular/core';
import { FormGroup, FormControl, AbstractControl, ValidationErrors } from '@angular/forms'
import { gte } from './gte.validator';
 
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
 
  constructor() {
  }
 
  myForm = new FormGroup({
    numVal: new FormControl('', [gte]),
  })
 
  get numVal() {
    return this.myForm.get('numVal');
  }
 
  onSubmit() {
    console.log(this.myForm.value);
  }
}
{% endhighlight %}

## **4. Code hoàn chỉnh cho template html**

{% highlight javascript linenos %}

 <div>
    <label for="numVal">Number :</label>
    <input type="text" id="numVal" name="numVal" formControlName="numVal">
    <div *ngIf="!numVal.valid && (numVal.dirty ||numVal.touched)">
      <div *ngIf="numVal.errors.gte">
        The number should be greater than {{numVal.errors.requiredValue}}
      </div>
    </div>
 
  </div>
{% endhighlight %}

## **6. Demo Video**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **6. Source code**


{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/Angular-Custom-Validation" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}
