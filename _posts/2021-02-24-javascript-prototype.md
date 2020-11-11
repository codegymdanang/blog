---
layout: course-javascript
title: Sử dụng Prototype trong Javascript 
slug : su-dung-prototype-trong-javascript
category: laptrinhjavascript
tags: [javascript]
summery: Prototype   
image: /images/blog/feature_javascript.png
description : Giới thiệu về Prototype trong Javascrip, cách hoạt động của Prototype trong Javascript
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trong bài chia sẻ trước anh đã chia sẻ về tính kế thừa (inheritance) trong JavaScript, đây cũng chính là cách thức làm việc của một <b>Prototype</b> trong <b>lập trình web</b>.

Trong phạm vi bài viết này, anh sẽ chia sẻ về <b>Prototype</b>. Hi vọng qua đó giúp các bạn hiểu được <b>Prototype</b> trong ngôn ngữ <b>lập trình web</b> JavaScript là gì? Cũng như học được cách sử dụng <b>Prototype trong lập trình web</b> như cách prototype gán giá trị.
 

## **1. Prototype là gì**

Javascript là ngôn ngữ động chúng ta có thể thêm thuộc tính mới với Object bất cứ lúc nào. Chúng ta hãy xem ví dụ sau

{% highlight javascript  linenos %}

function Student() {
    this.name = 'John';
    this.gender = 'Male';
}

var studObj1 = new Student();
studObj1.age = 15;
alert(studObj1.age); // 15

var studObj2 = new Student();
alert(studObj2.age); // undefined

{% endhighlight %}

Anh có một đối tượng là Student có 2 thuộc tính là name và gender. Nhưng các em thấy ở đối tượng studObj1 anh có thêm 1 thuộc tính mới là age. Thuộc tính này ban đầu không có trong đối tượng Student.

{% highlight javascript  linenos %}

var studObj1 = new Student();
studObj1.age = 15;

{% endhighlight %}

Tuy nhiên đối tượng studObj2 không có thuộc tính age, chính vì vậy khi get giá trị từ biến age là báo lỗi.

Như vậy khi muốn thêm một thuộc tính mới và đối tượng có sẵn ta dùng Prototype.

Protype được cài đặt mặt định trong tất cả function và đối tượng của Javascript. Được sử dụng để ta có thể lấy thêm và chỉnh sửa các giá trị trong đối tượng và function. 

 ## **2. Prototype gán giá trị**

Như các em thấy ở ví dụ 1 biến age chỉ có ở đối tượng studObj1, có cách nào để nó có thể có cho tất cả các đối tượng khác được không. Trong trường hợp này là studObj2. Để làm được việc này ta khai báo như sau

{% highlight javascript  linenos %}

function Student() {
    this.name = 'John';
    this.gender = 'M';
}

Student.prototype.age = 15;

var studObj1 = new Student();
alert(studObj1.age); // 15

var studObj2 = new Student();
alert(studObj2.age); // 15

{% endhighlight %}

Như các bạn thấy chúng ta có dòng Student.prototype.age = 15; để thêm giá trị age cho tất cả các đối tượng là Student. Bây giờ studObj2 không bị lỗi giống như ví dụ 1.









