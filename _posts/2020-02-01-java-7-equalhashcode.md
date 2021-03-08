---
layout: course-java
title: Sử dụng Equal và Hashcode trong lập trình Java
slug : su-dung-equal-va-hashcode-trong-lap-trinh-java
category: laptrinhjava
tags: [java core]
summery: Equal và Hashcode
image: /images/blog/java.png
featureImage: /images/post/javacore/feature_collection.png
description : Equal và Hashcode là gì? Các phương thức có trong Equal và Hashcode và cách sử dụng Equal và Hashcode trong lập trình java
youtubeId: hJwK_NvKZHE
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trong <b>lập trình Java</b>, <b>Equal và Hashcode</b> là những phương thức quan trọng đối với tất cả các Object. 
Vậy Equal, Hashcode là gì? Chúng quan trọng như thế nào trong <b>lập trình Java</b>? Mục đích sử dụng và cách để thao tác với Equal và Hashcode trong lập trình hướng đối tượng Java. Bài viết dưới đây với những ví dụ minh hoạ kèm theo trong mỗi phần sẽ giúp bạn hiểu được Equal và Hashcode cũng như biết được cách áp dụng hai phương thức này  vào trong thực hành <b>lập trình Java</b>.


## **1. Equal trong lập trình Java là gì**

Phương thức equals được sử dụng trong hầu hết các tập hợp để kiểm tra xem phần tử đã tồn tại trong tập hợp hay chưa. Ví dụ như mình muốn kiểm tra xem giá trị 123 đã có trong tập hợp list chưa ở ví dụ sau:

{% highlight java linenos %}

List list = new ArrayList();
list.add("123");

boolean contains123 = list.contains("123");

{% endhighlight %}

- Ở ví dụ trên chúng ta  sẽ duyệt qua hết các phần tử ở trong list sau đó thực thi phép so sánh từng phần tử list có bằng giá trị 123 không. Vì ta truyền vào là một chuỗi nên phương thức String.equals() được sử dụng để xem 2 chuỗi có bằng nhau hay không

- Phương thức equals ngoài được dùng cho việc tìm kiếm phần tử đã tồn tại trong tập hợp hay không thì nó cũng được dùng để xoá một phần tử ra khỏi tập hợp. 

{% highlight java linenos %}

List list = new ArrayList();
list.add("123");
boolean removed = list.remove("123");

{% endhighlight %}

- Ở ví dụ trên thì list sẽ duyệt qua các phần tử sau đó thực thi phép so sánh nếu tham số truyền vào (123) có bằng với từng phần tử trong tập hợp không. Nếu bằng thì nó xoá đi.

- Ở 2 ví dụ trên ta thấy tham số truyền vào là một chuỗi nên chúng ta có thể so sánh là String.equals. Nhưng nếu như ta truyền là đối tượng thì sao. Lúc này chúng ta sẽ tự viết ra cách mà so sánh các đối tượng. Ví dụ như anh muốn so sánh 2 đối tượng Employee có bằng nhau hay không.

- Đầu tiên anh có lớp Employee như sau

{% highlight java linenos %}

public class Employee {
    protected long   employeeId;
    protected String firstName;
    protected String lastName;
}

{% endhighlight %}

Ví dụ ta mong muốn nến 2 đối tượng Employee mà có cùng employeeId thì nó là bằng nhau. Ta tiến hành override phương thức equals như sau.

{% highlight java linenos %}

public class Employee {
  
  public boolean equals(Object o){
    if(o == null)                return false;
    if(!(o instanceof) Employee) return false;

    Employee other = (Employee) o;
    return this.employeeId == other.employeeId;
  }
}

{% endhighlight %}

- Ngoài cách so sánh bằng employeeID chúng ta có thể hoàn toàn so sánh bằng firstName hoặc lastName.

Như vậy equals được sử dụng trong tập hợp để so sánh các phần tử nhằm mục đích kiểm tra phần tử có tồn tại hay chưa hoặc mình muốn xoá nó ra khỏi tập hợp.

## **2. HashCode trong lập trình Java là gì**

Ví dụ như anh có một lớp Student gồm có 2 thuộc tính là id và name như sau 

{% highlight java linenos %}

public class Student {
  
  private int id;
  private String name

  public Student(int id,String name) {
  	this.id = id;
  	this.name = name;
  }
  
}

{% endhighlight %}


- Anh tạo một hàm main để in ra hashcode của đối tượng Student

{% highlight java linenos %}

public class Main {
  
  public static void main(String[] args) {

    Student nguyen = new Student(1,"Le Vu Nguyên")
    Student vu = new Student(2,"Le Nguyen Vu")

    System.out.println("HashCode Nguyên" + nguyen.hashCode())
    System.out.println("HashCode Vũ" + vu.hashCode())

  }
  
}

{% endhighlight %}

- Như chúng ta thấy trong Java tất cả các đối tượng đều kế thừa từ một đối tượng cha là Object. Trong đối tượng Object có 11 phương thức và hashCode là một trong các phương thức đó. Do vậy khi ta tạo đối tượng là Student thì trong Student đã kế thừa phương thức hashCode. Chính vì vậy mà ta có thể gọi phương thức nguyen.hashCode() trong đối tượng nguyen và vu.hashCode() trong đối tượng vu.

- Khi ta chạy hàm main thì ta nhận được kết quả là một số nguyên như sau :

+ HashCode Nguyên : 1852704110
+ HashCode Vũ : 2032578917

Như vậy hàm hashCode có nghĩa là sẽ trả về một số duy nhất tương ứng với từng object. Mỗi Object trong java đều có 1 định danh và định danh để phân biệt mỗi object chính là giá trị hashcode. Tương tự như chúng ta đều có một số chứng minh nhân dân vậy.

- Vậy hashcode được tạo ra như thế nào.

Khi ta tạo một đối tượng thì đối tượng đó sẽ được lưu vào bộ nhớ HEAP và nó được lưu tại một địa chỉ trong bộ nhớ. Hashcode được tạo ra cho đối tượng bằng cách kết hợp giữa địa chỉ bộ nhớ cộng thêm các tác nhân khác (như nhân thêm 30 rồi cộng thêm 2) sau đó sẽ cho ra một mã hashcode.

- Như vậy hashcode không phải là địa chỉ vùng nhớ chứa đối tượng mà nó là một thành phần để tạo ra hashcode.

## **3. Demo Video**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

## **4. Source code**


{:refdef: style="text-align: center;"}
<a href="https://github.com/levunguyen/Java-Equal-HashCode" target="_blank"> ![Sourcecode ](/images/icon/githubsource.png){:class="img-responsive"} </a>
{: refdef}

