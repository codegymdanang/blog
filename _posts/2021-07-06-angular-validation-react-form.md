---
layout: course-angular
title: Sử dụng Validation trong React Form của Angular 
slug : su-dung-validation-trong-react-form-cua-angular
category: laptrinhweb
tags: [angular]
summery: Validation React Form   
image: /images/blog/angular.png
description : Để kiểm tra lại các định dạng trong React Form trong Angular có đúng hay không, người dùng cần sử dụng Validator. Bài viết này giúp bạn hiểu rõ hơn về Validation React Form trong Angular là gì? Cùng tìm hiểu về một số Validator được hỗ trợ sẵn trong Angular như require, minlength, maxlength, pattern, email validator. Đồng thời hướng dẫn cách áp dụng Validator thông qua ví dụ minh hoạ thao tác thực hiện cú pháp để kiểm tra lại FormControl, FormGroup hoặc FormArray. Ngoài ra hướng dẫn cách để thực hiện được Code Validator trong Angular.
youtubeId: i4H0BZXOMog
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn,hôm nay anh sẽ hướng dẫn mọi người cách <b>Validation React Form</b> là như thế nào?

## **1.Validator là gì**

Chúng ta sử dụng Validator để kiểm tra xem FormControl, FormGroup hoặc FormArray trong React Form có đúng định dạng và yêu cầu của chúng ta hay không, nếu không thì nó sẽ trả về cho chúng ta danh sách lỗi.


## **2.Sử dụng Validator như thế nào**

Chúng ta thêm validator ở tham số thứ 2 của FormControl, FormGroup hoặc FormArray trong component class.

{% highlight javascript linenos %}

firstname: new FormControl('',[Validators.required]),

{% endhighlight %} 

Angular hỗ trợ sẵn một số Validator như require, minlenth, maxlength,pattern,email validator cho chúng ta. Trong ví dụ sau đây chúng ta sẽ sử dụng nó để kiểm tra giá trị người dùng nhập vào.

## **3.Ví dụ sử dụng Validator như thế nào**

Chúng ta sẽ viết ví dụ kiểm tra đăng ký của người dùng. Giả sử chúng ta có contacForm model như sau:

{% highlight javascript linenos %}

contactForm = new FormGroup({
    firstname: new FormControl(''),
    lastname: new FormControl(''),
    email:new FormControl(''),
    gender: new FormControl(''),
    isMarried: new FormControl(''),
    country: new FormControl(''),
    address:new FormGroup({
      city: new FormControl(''),
      street: new FormControl(''),
      pincode:new FormControl('')
    })
  })

{% endhighlight %} 
- Bước 1 : Tắt chức năng kiểm tra mặc định của trình duyệt.

Chúng ta sử dụng thuộc tính novalidate trong thẻ form để làm việc này

{% highlight javascript linenos %}

<form [formGroup]="contactForm" (ngSubmit)="onSubmit()" novalidate>
 
{% endhighlight %} 
- Bước 2 : Thêm các Validator có sẵn trong Angular

Chúng ta muốn người dùng bắt buộc phải điền vào firstname, thì chúng ta sử dụng require

{% highlight javascript linenos %}

firstname: new FormControl('',[Validators.required]),

{% endhighlight %} 

Chúng ta muốn firstname phải có độ dài ít nhất là 10 ký tự

{% highlight javascript linenos %}

firstname: new FormControl('',[Validators.required,Validators.minLength(10)]),

{% endhighlight %} 

Chúng ta muốn lastname phải có độ dài nhiều nhất là 15 ký tự

{% highlight javascript linenos %}

lastname: new FormControl('',[Validators.maxLength(15)]),

{% endhighlight %} 

Chúng ta muốn lastname người dùng điền vào phải đúng định dạng (giống như Regular Expression)

{% highlight javascript linenos %}

lastname: new FormControl('',[Validators.maxLength(15), Validators.pattern("^[a-zA-Z]+$")]),

{% endhighlight %} 

Chúng ta muốn người dùng điền đúng định dạng email

{% highlight javascript linenos %}

email:new FormControl('',[Validators.email,Validators.required]),

{% endhighlight %} 

Chúng ta có contact-form sau khi thêm các validator như sau:

{% highlight javascript linenos %}

 contactForm = new FormGroup({
    firstname: new FormControl('',[Validators.required,Validators.minLength(10)]),
    lastname: new FormControl('',[Validators.required, Validators.maxLength(15), Validators.pattern("^[a-zA-Z]+$")]),
    email:new FormControl('',[Validators.email,Validators.required]),
    gender: new FormControl('',[Validators.required]),
    isMarried: new FormControl('',[Validators.required]),
    country: new FormControl('',[Validators.required]),
    address:new FormGroup({
      city: new FormControl('',[Validators.required]),
      street: new FormControl('',[Validators.required]),
      pincode:new FormControl('',[Validators.required])
    })
  })

{% endhighlight %} 

- Bước 3 : Disable chức năng submit button

Nếu người dùng điền không đúng giá trị như ta mong muốn thì nút submit sẽ mờ đi không click được.

{% highlight javascript linenos %}

<button type="submit" [disabled]="!contactForm.valid">Submit</button>

{% endhighlight %} 

- Bước 4 : Hiển thị thông báo lỗi

Chúng ta sử dụng contactForm.controls.firstname.valid để kiểm tra xem người dùng điền đúng chưa. Nếu chưa thì ta hiển thị lỗi. Ta sử dụng ngIf để kiểm tra điều kiện

{% highlight javascript linenos %}

 <div
    *ngIf="!contactForm.controls.firstname?.valid && (contactForm.controls.firstname?.dirty
    ||contactForm.controls.firstname?.touched)">
      First Name is not valid
  </div>
{% endhighlight %} 

Ngoài cách ở trên ta có thể sử dụng phương thức getter trong component class như sau.

Ta thêm phương thức getter vào component

{% highlight javascript linenos %}

get firstname() {
   return this.contactForm.get('firstname');
} 

{% endhighlight %} 

Sau đó ta sử dụng ở template html như sau

{% highlight javascript linenos %}

  <div *ngIf="!firstname.valid && (firstname.dirty ||firstname.touched)">
      First Name is not valid
  </div>
{% endhighlight %} 

Sử dụng dirty : khi người dùng thay đổi giá trị trong firstname
Sử dụng touched : khi người dùng click vô ô firstname (blur event)

- Bước 5 : Hiển thị thông báo lỗi.

Chúng ta hiển thị First Name is not Valid

{% highlight javascript linenos %}

 <div
    *ngIf="!contactForm.controls.firstname?.valid && (contactForm.controls.firstname?.dirty
    ||contactForm.controls.firstname?.touched)">
      First Name is not valid
  </div>
{% endhighlight %} 

Cách này thì nó báo rất chung chung. Nên chúng ta muốn thông báo first name là bắt buộc nhập và min length phải là 10. Chúng ta sử dụng cách thông báo sau:

{% highlight javascript linenos %}

 <div
    *ngIf="!firstname?.valid && (firstname?.dirty ||firstname?.touched)">
    <div [hidden]="!firstname.errors.required">
      First Name is required
    </div>
    <div [hidden]="!firstname.errors.minlength">
      Min Length is 10
    </div>
  </div>
{% endhighlight %} 

## **4.Code Validator**

Chúng ta có file component class là app.component.ts

{% highlight javascript linenos %}

import { Component, ViewChild, ElementRef } from '@angular/core';
import { FormGroup, FormControl, Validators } from '@angular/forms'
  
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'Angular Reactive forms';
 
 
  contactForm = new FormGroup({
    firstname: new FormControl('',[Validators.required,Validators.minLength(10)]),
    lastname: new FormControl('',[Validators.required, Validators.maxLength(15), Validators.pattern("^[a-zA-Z]+$")]),
    email:new FormControl('',[Validators.email,Validators.required]),
    gender: new FormControl('',[Validators.required]),
    isMarried: new FormControl('',[Validators.required]),
    country: new FormControl('',[Validators.required]),
    address:new FormGroup({
      city: new FormControl('',[Validators.required]),
      street: new FormControl('',[Validators.required]),
      pincode:new FormControl('',[Validators.required])
    })
  })
 
  get firstname() {
    return this.contactForm.get('firstname');
  } 
 
  get lastname() {
    return this.contactForm.get('lastname');
  } 
 
  get email() {
    return this.contactForm.get('email');
  } 
 
  get gender() {
    return this.contactForm.get('gender');
  } 
 
  get isMarried() {
    return this.contactForm.get('isMarried');
  } 
 
  get country() {
    return this.contactForm.get('country');
  } 
 
  get city() {
    return this.contactForm.get("address").get('city');
  } 
 
  get street() {
    return this.contactForm.get("address").get('street');
  } 
 
  get pincode() {
    return this.contactForm.get("address").get('pincode');
  } 
 
 
  countryList: country[] = [
    new country("1", "India"),
    new country('2', 'USA'),
    new country('3', 'England')
  ];

  onSubmit() {
    console.log(this.contactForm.value);
  } 
}

export class contact {
  firstname:string;
  lastname:string;
  gender:string;
  isMarried:boolean;
  country:string;
  address: {
    city:string;
    street:string;
    pincode:string;
  }
} 
  
export class country {
  id: string;
  name: string;
 
  constructor(id: string, name: string) {
    this.id = id;
    this.name = name;
  }
}

{% endhighlight %}

Chúng ta có file template html app.component.html

{% highlight javascript linenos %}

<form [formGroup]="contactForm" (ngSubmit)="onSubmit()" novalidate>
 
  <p>
    <label for="firstname">First Name </label>
    <input type="text" id="firstname" name="firstname" formControlName="firstname">
  </p>
 
  <div
    *ngIf="!firstname?.valid && (firstname?.dirty ||firstname?.touched)">
    <div [hidden]="!firstname.errors.required">
      First Name is required
    </div>
    <div [hidden]="!firstname.errors.minlength">
      Min Length is 10
    </div>
  </div>
 
  <p>
    <label for="lastname">Last Name </label>
    <input type="text" id="lastname" name="lastname" formControlName="lastname">
  </p>
 
  <div *ngIf="!lastname.valid && (lastname.dirty ||lastname.touched)">
    <div [hidden]="!lastname.errors.pattern">
      Only characters are allowed
    </div>
    <div [hidden]="!lastname.errors.maxLength">
      Max length allowed is {{lastname.errors.maxlength?.requiredLength}} 
    </div>
    <div [hidden]="!lastname.errors.required">
      Last Name is required
    </div>
  </div>
 
  <p>
    <label for="email">Email </label>
    <input type="text" id="email" name="email" formControlName="email">
  </p>
  <div *ngIf="!email.valid && (email.dirty ||email.touched)">
    <div [hidden]="!email.errors.required">
      email is required
    </div>
    <div [hidden]="!email.errors.email">
      invalid email id
    </div>
  </div>
 
 
  <p>
    <label for="gender">Geneder </label>
    <input type="radio" value="male" id="gender" name="gender" formControlName="gender"> Male
    <input type="radio" value="female" id="gender" name="gender" formControlName="gender"> Female
  </p>
  <div *ngIf="!gender.valid && (gender.dirty ||gender.touched)">
    <div [hidden]="!gender.errors.required">
      gender is required
    </div>
  </div>
 
  <p>
    <label for="isMarried">Married </label>
    <input type="checkbox" id="isMarried" name="isMarried" formControlName="isMarried">
  </p>
  <div *ngIf="!isMarried.valid && (isMarried.dirty ||isMarried.touched)">
    <div [hidden]="!isMarried.errors.required">
      isMarried is required
    </div>
  </div>
 
 
  <p>
    <label for="country">country </label>
    <select id="country" name="country" formControlName="country">
      <option [ngValue]="c.id" *ngFor="let c of countryList">
        {{c.name}}
      </option>
    </select>
  </p>
  <div *ngIf="!country.valid && (country.dirty ||country.touched)">
    <div [hidden]="!country.errors.required">
      country is required
    </div>
  </div>
 
 
 
  <div formGroupName="address">
 
    <div class="form-group">
      <label for="city">City</label>
      <input type="text" class="form-control" name="city" formControlName="city">
    </div>
    <div *ngIf="!city.valid && (city.dirty ||city.touched)">
      <div [hidden]="!city.errors.required">
        city is required
      </div>
    </div>
 
 
    <div class="form-group">
      <label for="street">Street</label>
      <input type="text" class="form-control" name="street" formControlName="street">
    </div>
    <div *ngIf="!street.valid && (street.dirty ||street.touched)">
      <div [hidden]="!street.errors.required">
        street is required
      </div>
    </div>
 
    <div class="form-group">
      <label for="pincode">Pin Code</label>
      <input type="text" class="form-control" name="pincode" formControlName="pincode">
    </div>
    <div *ngIf="!pincode.valid && (pincode.dirty ||pincode.touched)">
      <div [hidden]="!pincode.errors.required">
        pincode is required
      </div>
    </div>
 
  </div>
 
  <p>{{contactForm.valid}} </p>
 
  <p>
    <button type="submit" [disabled]="!contactForm.valid">Submit</button>
  </p>
 
 
</form>
 
{% endhighlight %}

## **5. Demo Video**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **6. Source code**


{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/Angular-Validation-ReactForm" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}
