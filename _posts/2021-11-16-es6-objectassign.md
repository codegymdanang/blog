---
layout: course-es6
title: Sử dụng Object assign trong ES6 
slug : su-dung-object-assign-trong-es6
category: laptrinhjavascript
tags: [es6]
summery: Object assign
image: /images/blog/feature_javascript.png
description : Trình bày về khi nào chúng ta  dùng  Object assign của ES6. Lần lượt giới thiệu và và đi qua các ví dụ về Object assign được sử dụng trong ES6.

youtubeId: xw-VF7Fyx4o
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn, hôm nay anh sẽ hướng dẫn mọi người về  <b>Object assign</b> của ES6. Lần lượt giới thiệu và và đi qua các ví dụ về Object assign được sử dụng trong ES6.

## **1. Giới thiệu về phương thức Object assign**

Chúng ta sử dụng phương thước Object.assign để copy hoặc merge tất cả thuộc tính của một đối tượng này qua một đối tượng khác. Cú pháp như sau.


{% highlight javascript  linenos %}

Object.assign(target, ...sources)

{% endhighlight %}

Sources : đối tượng sẽ ta sẽ copy tất cả các thuộc tính
Target : đối tượng mới nhận được các giá trị copy từ source.

Anh có ví dụ như sau.

{% highlight javascript  linenos %}

let widget = {
    color: 'red'
};

let clonedWidget = Object.assign({}, widget);

console.log(clonedWidget);

Kết quả

{ color: 'red' }

{% endhighlight %}

Như vậy ta copy các thuộc tính của đối tượng widget sang đối tượng clonedWidget. Đối tượng cloneWidget sẽ có thuộc tính color bằng red giống như đối tượng widget.

## **2. Merge 2 đối tượng**

Chúng ta có thể dùng object.assign() để trộn 2 đối tượng lại với nhau như sau

{% highlight javascript  linenos %}

let box = {
    height: 10,
    width: 20
};

let style = {
    color: 'Red',
    borderStyle: 'solid'
};

let styleBox = Object.assign({}, box, style);

console.log(styleBox);

Kết quả

{
    height: 10,
    width: 20,
    color: 'Red',
    borderStyle: 'solid'
}

{% endhighlight %}

Trường hợp nếu merge 2 đối tượng có cùng thuộc tính. Thì giá trị của thuộc tính được lấy bởi đối tượng sau cùng như sau.

{% highlight javascript  linenos %}

let box = {
    height: 10,
    width: 20,
    color: 'Red'
};

let style = {
    color: 'Blue',
    borderStyle: 'solid'
};

let styleBox = Object.assign({}, box, style);

console.log(styleBox);

Kết quả

{
    height: 10,
    width: 20,
    color: 'Blue',
    borderStyle: 'solid'
}

{% endhighlight %}

Như ta thấy 2 đối tượng box và style đều có giá trị color. Tuy nhiên khi merge 2 đối tượng thì giá trị color được lấy theo đối tượng sau cùng. Trong trường hợp này chúng ta sẽ lấy giá trị là color = Blue chứ không phải lấy giá trị color = Red.

## **3. Demo Video**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}




























