---
layout: course-angular
title: Sử dụng Customs Directive trong Angular
slug : su-dung-customs-directive-trong-angular
category: laptrinhweb
tags: [angular]
summery: Customs Directive  
image: /images/blog/angular.png
description : Bên cạnh 3 loại directive có sẵn trong Angular, người dùng có thể tự tạo ra directive riêng như mong muốn để sử dụng, được gọi là customs directive. Bài viết giúp hiểu rõ hơn về Customs Directive, cú pháp của Customs Directive trong Angular. Đồng thời hướng dẫn cách để tự tạo Customs Directive trong Angular bao gồm cách thao tác để làm Directive giống Attribute Directive hoặc Directive giống Structural Directive. Và cách sử dụng Customs Directive vào các dự án Angular. Những chia sẻ trong bài bao gồm các hình ảnh minh hoạ các thao tác để thực hiện các tác vụ trên trong Angular.
youtubeId: _-jAE1b1VTQ
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn, hôm nay anh sẽ hướng dẫn mọi người cách tạo <b>Customs Directive</b> là như thế nào? 

## **1. Customs Directive là gì**

Trong Angular có 3 loại directive là component, structural và attribute như ta thấy ở các bài trên. Đây là những directive có sẵn của Angular. Nhưng sẽ có những trường hợp những Directive này không phù hợp với mục đích bài toán của mình nên trong Angular cho phép chúng ta tự viết ra một directive riêng cho mình và sử dụng theo cách mình muốn.

## **2. Tự tạo Directive giống Attribute Directive là gì**

 Trong ví dụ sau đây chúng ta tự tạo một attribute có tên là ttClass directive riêng cho mình. Sau đó template html sẽ thêm thuộc tính này vào trong thẻ html.

 - Bước 1 : Chúng ta tạo file có tên là tt-class.directive.js như sau:

{% highlight javascript  linenos %}

import { Directive, ElementRef, Input, OnInit } from '@angular/core'
 
@Directive({
  selector: '[ttClass]',
})
export class ttClassDirective implements OnInit {
 
  @Input() ttClass: string;
 
  constructor(private el: ElementRef) {
  }
 
  ngOnInit() {
    this.el.nativeElement.classList.add(this.ttClass);
  }
 
}

{% endhighlight %}

Chúng ta import thư viện Directive và các thư viện cần thiết vào.

{% highlight javascript  linenos %}

import { Directive, ElementRef, Input, OnInit } from '@angular/core'

{% endhighlight %}

Chúng ta khai báo Class này là directive thông qua annotation @Directive và đặt tên cho component này là ttClass.

{% highlight javascript  linenos %}

@Directive({
  selector: '[ttClass]',
})
export class ttClassDirective implements OnInit {

{% endhighlight %}

Chúng ta sử dụng @Input() ttClass: string để nhận giá trị từ template html truyền vào thông qua thẻ thuộc tính như sau.

{% highlight html  linenos %}

<button [ttClass]="'blue'">Click Me</button>

{% endhighlight %}

Như vậy giá trị blue sẽ được truyền vào biến ttClass : String.

Chúng ta sử dụng ElementRef để thao tác với các thành phần của web.

{% highlight javascript  linenos %}

constructor(private el: ElementRef) { }
{% endhighlight %}

Hàm ngOnIt() sẽ được gọi trong hàm này chúng ta dùng el để thêm các class css cho template html.

- Bước 2 : Nhúng và sử dụng customs directive vào template html.

{% highlight html  linenos %}

<button [ttClass]="'blue'">Click Me</button>

{% endhighlight %}

Ta thấy thẻ button sử dụng thuộc tính ttClass. Đây chính là directive chúng ta tự viết ra.

## **3. Tự tạo Directive giống Structural Directive là gì**

Chúng ta sẽ tự viết một directive giống như if else có tên là ttIf. 

- Bước 1 : tạo file component class. Trong đó tạo ra directive có tên là ttIf.

{% highlight javascript  linenos %}

import { Directive, ViewContainerRef, TemplateRef, Input } from '@angular/core';
 
@Directive({ 
  selector: '[ttIf]' 
})
export class ttIfDirective  {
 
  _ttif: boolean;
 
  constructor(private _viewContainer: ViewContainerRef,
            private templateRef: TemplateRef<any>) {
  }
 
 
  @Input()
  set ttIf(condition) {
    this._ttif = condition
    this._updateView();
  }
 
  _updateView() {
    if (this._ttif) {
      this._viewContainer.createEmbeddedView(this.templateRef);
    }
    else {
      this._viewContainer.clear();
    }
  }
 
}
{% endhighlight %}

Đầu tiên chúng ta import các thư viện vào.

{% highlight javascript  linenos %}

import { Directive, ViewContainerRef, TemplateRef, Input } from '@angular/core';

{% endhighlight %}

Tiếp đến chúng ta khai báo tên của directive do mình tự tạo. Nó có tên là ttIf.

{% highlight javascript  linenos %}
 
@Directive({ 
  selector: '[ttIf]' 
})
export class ttIfDirective  {
}
{% endhighlight %}

Directive của chúng ta sẽ nhận tham số là một điều kiện từ template html truyền qua. Do vậy ta khai báo @Input để nhận giá trị. Chúng ta sẽ dùng setter bời vì chúng ta muốn thêm và xoá nội dung động phụ thuộc vào điều kiện truyền vào.

{% highlight javascript  linenos %}

	@Input()
  set ttIf(condition) {
    this._ttif = condition
    this._updateView();
  }
{% endhighlight %}

Cuối cùng hàm updateView gọi phương thức createEmbeddedView để thêm các thành phần vào web nếu điều kiện là thoả mãn.

Bước 2 : Sử dụng directive trong template html. Ta sẽ thấy directive mà ta mới viết là \*ttif.

{% highlight html  linenos %}

<h1> {{title}} </h1>
 
Show Me
<input type="checkbox" [(ngModel)]="show">
 
<div *ttIf="show">
  Using the ttIf directive
</div>
 
<div *ngIf="show">
  Using the ngIf directive
</div>

{% endhighlight %}


{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}






