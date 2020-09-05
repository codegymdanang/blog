---
layout: course-typescript
title: Sử dụng Class trong Typescript  
slug : typescript-class
category: laptrinhjavascript
tags: [typescript]
summery: Class   
image: /images/blog/feature_javascript.png
description : Giới thiệu về Class trong Typescrip, cách hoạt động của Class trong Typescrip
youtubeId: Ex3glZTCvlY
---

# **Giới thiệu nội dung bài viết**

Chào các bạn,hôm nay anh sẽ hướng dẫn mọi người về <b>Class</b> là như thế nào? 

# **1. Class là gì**

Cũng giống như các ngôn ngữ lập trình Java, C# trong typescript cũng hỗ trợ Class. 

Một Class thì gồm các phần như constructor, thuộc tính và phương thức. 

Ví dụ một class Employee trong typescript

{% highlight javascript  linenos %}

class Employee {
    empCode: number;
    empName: string;

    constructor(code: number, name: string) {
            this.empName = name;
            this.empCode = code;
    }

    getSalary() : number {
        return 10000;
    }
}

{% endhighlight %}

- Khi chương trình compile nó sẽ dịch ra Javascript như sau

{% highlight javascript  linenos %}

var Employee = (function () {
    function Employee(name, code) {
        this.empName = name;
        this.empCode = code;
    }
    Employee.prototype.getSalary = function () {
        return 10000;
    };
        return Employee;
}());

{% endhighlight %}

# **2. Constructor là gì**

Constructor là một hàm đặt biệt nó được gọi khi chúng ta tạo đối tượng. Constructor được khai báo bằng từ khoá constructor

{% highlight javascript  linenos %}

class Employee {

    empCode: number;
    empName: string;
    
    constructor(empcode: number, name: string ) {
        this.empCode = empcode;
        this.name = name;
    }
}

{% endhighlight %}

- Chúng ta có thể viết code cho constructor hoặc không cần viết cũng được. Cái này là option.

{% highlight javascript  linenos %}

class Employee {
    empCode: number;
    empName: string;
}

{% endhighlight %}

- Để tạo một đối tượng từ Class ta sử dụng toán tử new

{% highlight javascript  linenos %}

class Employee {

    empCode: number;
    empName: string;
    
    constructor(empcode: number, name: string ) {
            this.empCode = empcode;
            this.name = name;
    }
}

let emp = new Employee(100,"Steve");

{% endhighlight %}

# **3. Kế thừa là gì**

Cũng giống như Java và C# chúng ta có thể kế thừa trong TypeScript thông qua từ khoá extends

{% highlight javascript  linenos %}

class Person {
    name: string;
    
    constructor(name: string) {
        this.name = name;
    }
}

class Employee extends Person {
    empCode: number;
    
    constructor(empcode: number, name:string) {
        super(name);
        this.empCode = empcode;
    }
    
    displayName():void {
        console.log("Name = " + this.name +  ", Employee Code = " + this.empCode);
    }
}

let emp = new Employee(100, "Bill");
emp.displayName(); // Name = Bill, Employee Code = 100

{% endhighlight %}

# **4. Cài đặt Interface**

Chúng ta có thể implements một hoặc nhiều Interface cho Class. Ví dụ Class Employee sau đây

{% highlight javascript  linenos %}

interface IPerson {
    name: string;
    display():void;
}

interface IEmployee {
    empCode: number;
}

class Employee implements IPerson, IEmployee {
    empCode: number;
    name: string;
    
    constructor(empcode: number, name:string) {
        this.empCode = empcode;
        this.name = name;
    }
    
    display(): void {
        console.log("Name = " + this.name +  ", Employee Code = " + this.empCode);
    }
}

let per:IPerson = new Employee(100, "Bill");
per.display(); // Name = Bill, Employee Code = 100

let emp:IEmployee = new Employee(100, "Bill");
emp.display(); //Compiler Error: Property 'display' does not exist on type 'IEmployee'

{% endhighlight %}

# **5. Overide Method Trong Class**

Chúng ta có thể overide lại method của lớp cha giống như trong Java.

{% highlight javascript  linenos %}

class Car {
    name: string;
        
    constructor(name: string) {
        this.name = name;
    }
    
    run(speed:number = 0) {
        console.log("A " + this.name + " is moving at " + speed + " mph!");
    }
}

class Mercedes extends Car {
    
    constructor(name: string) {
        super(name);
    }
    
    run(speed = 150) {
        console.log('A Mercedes started')
        super.run(speed);
    }
}

class Honda extends Car {
    
    constructor(name: string) {
        super(name);
    }
    
    run(speed = 100) {
        console.log('A Honda started')
        super.run(speed);
    }
}

let mercObj = new Mercedes("Mercedes-Benz GLA");
let hondaObj = new Honda("Honda City")

mercObj.run();  // A Mercedes started A Mercedes-Benz GLA is moving at 150 mph!
hondaObj.run(); // A Honda started A Honda City is moving at 100 mph!
{% endhighlight %}











