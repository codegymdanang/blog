---
layout: course-javascript
title: Lập trình hướng đối tượng trong Javascript 
slug : lap-trinh-huong-doi-tuong-trong-javascript
category: laptrinhjavascript
tags: [javascript]
summery: OOP   
image: /images/blog/feature_javascript.png
description : Hầu hết các ngôn ngữ lập trình web hiện nay đều có tính hướng đối tượng, OOP trong đó bao gồm cả ngôn ngữ lập trình JavaScript. Những chia sẻ trong bài viết này sẽ đi sâu vào giải thích giúp cho bạn hiểu rõ hơn về tính hướng đối tượng trong lập trình web với JavaScript và Object là gì? Đồng thời tìm hiểu về Constructor và định nghĩa phương thức trong ngôn ngữ lập trình hướng đối tượng JavaScript. 
youtubeId: -VKr_JxgnXM
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn, hôm nay anh sẽ chia sẻ về chủ đề <b>OOP, lập trình hướng đối tượng</b> trong ngôn ngữ <b>lập trình web</b> JavaScript. 

Trước khi đi vào bài này anh muốn mọi người đọc qua bài <b>lập trình hướng đối tượng</b> là gì tại [đây](https://levunguyen.com/laptrinhjava/2020/01/14/lap-trinh-huong-doi-tuong/). Vì bài <b>OOP</b> này khá khó cho người mới bắt đầu nên các em hãy đọc trước bài hướng đối tượng ở trên. Các bạn có thể không đọc những phần code Java viết trong đó, mà chỉ cần hiểu ví dụ anh đưa ra để hiểu hướng đối tượng là gì sau đó hãy đọc tiếp bài viết sau đây.

Trong những chia sẻ dưới đây, anh sẽ đi sâu vào giải thích cho các bạn hiểu rõ hơn về <b>OOP</b>, Object trong ngôn ngữ lập trình hướng đối tượng JavaScript là gì? Đồng thời tìm hiểu về Constructor và định nghĩa phương thức trong ngôn ngữ <b>lập trình hướng đối tượng</b> JavaScript.

## **1. OOP là gì**

Sau khi đọc bài hướng đối tượng là gì thì các em sẽ thấy mọi thứ xung quanh ta đều là đối tượng. Để cho việc lập trình được dễ dàng thì hướng đối tượng là cách tốt nhất để xây dựng các chương trình phục vụ đời sống. Như các em thấy các ứng dụng hiện nay đều xây dựng trên hướng đối tượng có nghĩa là ở ngoài đời có những đối tượng nào, những thuộc tính gì và hành động gì đều được thể hiện qua các dòng code để mô tả lại.

## **2. Object là gì**

Object là những đối tượng mà ta ánh xạ ở ngoài thực tế. Ví dụ thực tế có ông giáo viên thì được ánh xạ thành đối tượng giáo viên trong lập trình.

Javascript Object bao gồm thuộc tính và phương thức. Thông thường Object là danh từ ví dụ như Giảng Viên, thuộc tính là tính chất của danh từ ví dụ ông giảng viên sẽ có tên, tuổi, địa chỉ. Phương thức là những hành động của ông giảng viên như chạy, dạy, chấm thi. Như vậy các em thấy trong lập trình mình mô tả y chang thực tế.

- Có 3 cách để tạo đối tượng trong javascript:

- Tạo đối tượng bằng object literal

Cú pháp như sau 

{% highlight javascript  linenos %}

object={property1:value1,property2:value2.....propertyN:valueN}  

{% endhighlight %}

Ví dụ chúng ta tạo một nhân viên tên Kumar và mức lương là 4K. Nó mô tả giống như thực tế ta có ông nhân viên là Kumar và mức lương 4k.

{% highlight javascript  linenos %}
    <script>  
    emp={id:102,name:"Shyam Kumar",salary:40000}  
    document.write(emp.id+" "+emp.name+" "+emp.salary);  
    </script>  
{% endhighlight %}

- Tạo đối tượng bằng new Object

Chúng ta sử dụng từ khóa new để tạo ra một đối tượng

Cú pháp

{% highlight javascript  linenos %}

var objectname=new Object(); 

{% endhighlight %}

Ví dụ tạo đối tượng nhân viên tên Malik và lương 5K

{% highlight javascript  linenos %}

<script>  
var emp=new Object();  
emp.id=101;  
emp.name="Ravi Malik";  
emp.salary=50000;  
document.write(emp.id+" "+emp.name+" "+emp.salary);  
</script>

{% endhighlight %}

- Tạo đối tượng bằng hàm khởi tạo constructor của Object

{% highlight javascript  linenos %}

<script>  

function emp(id,name,salary){  
this.id = id;  
this.name = name;  
this.salary = salary;  

}  
emp = new emp(103,"Vimal Jaiswal",30000);  

</script>  

{% endhighlight %}

Chúng ta sử dụng từ khóa this để tham chiếu đến đối tượng hiện tại trong 
trường hợp này this chính là emp.

Các tham số id, name, salary chính là thuộc tính của đối tượng. Thuộc tính sẽ được mô tả thành các biến trong đối tượng

## **3. Định nghĩa phương thức**

Như chúng ta thấy đối tượng trong thực tế của các hành động, thì tương tự như vậy trong lập trình đối tượng của chúng ta cũng có những hành động. Hành động của đối tượng được thể hiện ở phương thức của đối tượng như sau

{% highlight javascript  linenos %}

    <script>  
        function emp(id,name,salary){  
            this.id=id;  
            this.name=name;  
            this.salary=salary;  
      
            this.changeSalary=changeSalary;  
    
            function changeSalary(otherSalary){  
                this.salary=otherSalary;  
            }  
    }  
    e=new emp(103,"Sonoo Jaiswal",30000);  
    document.write(e.id+" "+e.name+" "+e.salary);  
    e.changeSalary(45000);  
    document.write("<br>"+e.id+" "+e.name+" "+e.salary);  
    </script>  
{% endhighlight %}

Như ta thấy function changeSalary() chính là phương thức trong đối tượng employ. Khai báo phương thức của đối tượng chúng ta dùng từ khoá function.

## **4. Constructor**

Javascript constructor là một phương thức đặc biệt chúng ta sử dụng nó để khởi tạo các giá trị cho đối tượng 


{% highlight javascript  linenos %}

    <script>  
    class Employee {  
      constructor() {  
        this.id=101;  
        this.name = "Martin Roy";  
      }   
    }  
    var emp = new Employee();  
    document.writeln(emp.id+" "+emp.name);  
    </script>  
{% endhighlight %}

Chúng ta tạo constructor của class Employee với từ khoá là constructor. Trong method constructor ta khởi tạo giá trị ban đầu cho object Employee là id = 101 và name là Martin. Như vậy ta sử dụng constructor để khởi tạo giá trị ban đầu cho đối tượng.

Khi ta gọi var emp = new Employee() thì 2 giá trị id và name đã có sẵn giá trị là 101 và Martin

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}









