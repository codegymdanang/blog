---
layout: course-javascript
title: Sử dụng kế thừa trong Javascript  
slug : su-dung-ke-thua-trong-javascript
category: laptrinhjavascript
tags: [javascript]
summery: Kế thừa   
image: /images/blog/feature_javascript.png
description : Ngôn ngữ lập trình web JavaScript là một ngôn ngữ lập trình hướng đối tượng OOP, mà một OOP thì thường bao gồm các tính chất tính đa hình, đóng gói, trừu tượng và kế thừa. Một trong những tính chất nổi trội đó chính là tính kế thừa. Bài viết sẽ giúp bạn hiểu được tính kế thừa trong ngôn ngữ lập trình web JavaScript là gì. Đồng thời hướng dẫn cách sử dụng nó để áp dụng được vào quá trình thực hành. Bài viết có kèm theo ví dụ minh hoạ hoàn chỉnh về tính kế thừa để bạn tham khảo thêm trong quá trình học.
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Ngôn ngữ <b>lập trình web</b> JavaScript là một ngôn ngữ lập trình hướng đối tượng (OOP), mà một OOP thì thường bao gồm các tính chất: tính đa hình, đóng gói, trừu tượng và kế thừa. Một trong những tính chất nổi trội đó chính là tính <b>kế thừa</b>.

Trong những chia sẻ dưới đây anh sẽ giúp các bạn hiểu được tính <b>kế thừa</b> trong ngôn ngữ <b>lập trình web</b> JavaScript là gì. Đồng thời hướng dẫn cách sử dụng nó để áp dụng được vào quá trình thực hành. Bài viết có kèm theo ví dụ minh hoạ hoàn chỉnh về <b>tính kế thừa</b> để bạn tham khảo thêm trong quá trình học.
 

## **1. Kế thừa là gì**

<b>Kế thừa</b> là một khái niệm quan trọng trong lập trình hướng đối tượng. Một đối tượng kế thừa một đối tượng khác thì nó sẽ có thuộc tính và phương thức có sẵn của đối tượng mà nó kế thừa.

Trong Javascript, kế thừa được hỗ trợ khi ta dùng Prototype.

Hãy xem ví dụ sau về đối tượng Student kế thừa từ đối tượng Person

{% highlight javascript  linenos %}

function Person(firstName, lastName) {
    this.FirstName = firstName || "unknown";
    this.LastName = lastName || "unknown";
};

Person.prototype.getFullName = function () {
    return this.FirstName + " " + this.LastName;
}

{% endhighlight %}

Ở ví dụ trên ta định nghĩa lớp Person có 2 thuộc tính là firstNam và lastName. Đồng thời chúng ta sử dụng prototype tạo thêm phương thức getFullName cho đối tượng Person

Bây giờ chúng ta sẽ tạo đối tượng Student kế thừa đối tượng Person và mặc định nó sẽ kế thừa 2 thuộc tính là firstName, lastName và phương thức getFullName của Person

{% highlight javascript  linenos %}

function Student(firstName, lastName, schoolName, grade)
{
    Person.call(this, firstName, lastName);

    this.SchoolName = schoolName || "unknown";
    this.Grade = grade || 0;
}

Student.prototype = new Person();
Student.prototype.constructor = Student

{% endhighlight %}

Chúng ta sử dụng Student.prototype để tạo ra đối tượng Person

## **2. Ví dụ hoàn chỉnh về kế thừa**

{% highlight javascript  linenos %}


function Person(firstName, lastName) {
    this.FirstName = firstName || "unknown";
    this.LastName = lastName || "unknown";            
}

Person.prototype.getFullName = function () {
    return this.FirstName + " " + this.LastName;
}
function Student(firstName, lastName, schoolName, grade)
{
    Person.call(this, firstName, lastName);

    this.SchoolName = schoolName || "unknown";
    this.Grade = grade || 0;
}
//Student.prototype = Person.prototype;
Student.prototype = new Person();
Student.prototype.constructor = Student;

var std = new Student("James","Bond", "XYZ", 10);
            
alert(std.getFullName()); // James Bond
alert(std instanceof Student); // true
alert(std instanceof Person); // true


{% endhighlight %}




