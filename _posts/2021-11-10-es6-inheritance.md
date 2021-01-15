---
layout: course-es6
title: Sử dụng kế thừa trong ES6 
slug : su-dung-ke-thua-trong-es6
category: laptrinhjavascript
tags: [es6]
summery:  Kế thừa
image: /images/blog/feature_javascript.png
description : Trình bày về cách cách sử dụng Kế thừa của ES6. Lần lượt giới thiệu và giải thích khái niệm Kế thừa trong của ES6 là gì? 

youtubeId: ttKo2gO-BCE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn, hôm nay anh sẽ hướng dẫn mọi người về  cách khai báo và sử dụng <b>Kế thừa </b> của ES6. Lần lượt giới thiệu và giải thích khái niệm và ví dụ về Kế thừa của ES6 là gì? 

## **1. Kế thừa trong JS cách củ**


Trước khi có cách viết kế thừa trong ES6 thì để làm kế thừa trong Javascript ta sử dụng prototype khai báo theo cách như sau

{% highlight javascript  linenos %}

function Animal(legs) {
    this.legs = legs;
}

Animal.prototype.walk = function() {
    console.log('walking on ' + this.legs + ' legs');
}

function Bird(legs) {
    Animal.call(this, legs);
}

Bird.prototype = Object.create(Animal.prototype);
Bird.prototype.constructor = Animal;

Bird.prototype.fly = function() {
    console.log('flying');
}

var pigeon = new Bird(2);
pigeon.walk(); // walking on 2 legs
pigeon.fly(); // flying


{% endhighlight %}

## **2. Kế thừa trong JS trong ES6**

Chúng ta sử dụng từ khoá extends để sử dụng kế thừa. Trong ví dụ dưới đây chúng ta khai báo lớp Animal, Class Bird sẽ kế thừa lại Animal

{% highlight javascript  linenos %}

class Animal {
    constructor(legs) {
        this.legs = legs;
    }
    walk() {
        console.log('walking on ' + this.legs + ' legs');
    }
}

class Bird extends Animal {
    constructor(legs) {
        super(legs);
    }
    fly() {
        console.log('flying');
    }
}


let bird = new Bird(2);

bird.walk();
bird.fly();

{% endhighlight %}

## **3. Shadowing method**

Gọi phương thức cha từ phương thức con. Ví dụ chúng ta có lớp Dog kế thừa lớp động vật và ghi đè lại phương thức walk() như sau


{% highlight javascript  linenos %}

class Dog extends Animal {
    constructor() {
        super(4);
    }
    walk() {
        console.log(`go walking`);
    }
}

let bingo = new Dog();
bingo.walk(); // go walking

{% endhighlight %}

Sau khi chương trình chạy chúng ta sẽ được kết quả là : go walking.

Bây giờ chúng ta muốn từ gọi phương thức walk trong lớp Aninal (lớp cha) thì chúng ta sử dụng từ khoá super như sau. Lúc này nó sẽ gọi hàm walk trong lớp Animal.

{% highlight javascript  linenos %}

class Dog extends Animal {
    constructor() {
        super(4);
    }
    walk() {
        super.walk(); // gọi lên phương thức walk của lớp Animal
        console.log(`go walking`);
    }
}

let bingo = new Dog();
bingo.walk();

{% endhighlight %}
























