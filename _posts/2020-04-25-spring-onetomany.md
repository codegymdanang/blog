---
layout: blog
title: OneToMany Relationship
slug : one-to-many
category: laptrinhspring
tags: [spring]
summery: OneToMany Relationship
image: /images/blog/spring.png
description : OneToMany mapping trong Spring . hướng dẫn onetomany trong spring data jpa, ví dụ onetomany  trong spring data jpa
youtubeId: WNfuVJptPnQ
---

### **1. Giới thiệu nội dung bài viết**

Chào các em ,chủ đề hôm nay chúng ta sẽ nói về các annotation @OneToMany và @ManyToOne trong Spring  .
Nội dung mình sẽ giải thích trong bài này sẽ xoay quanh các chủ đề sau đây.

- OneToMany là gì  ?
- ManyToOne là gì ?
- Cấu hình và triển khai một dự án dùng các annotation


### **2. One To Many annotation**

Anh lấy ví dụ như mình làm ứng dụng về bán hàng. Mình có chức năng lưu sản phẩm (Item)  vào  giỏ hàng (cart) .
Trong giỏ hàng (cart) sẽ chứa nhiều sản phẩm (Items). Như vậy quan hệ giữa giỏ hàng và sản phẩm  là One To Many nghĩa là 1 giỏ hàng chứa nhiều sản  .

Nếu ta thiết kết database thì ta có 2 bảng là cart và item như sau .

{% highlight mysql  linenos %}
CREATE TABLE `Cart` (
  `cart_id` int(11) unsigned NOT NULL AUTO_INCREMENT,
  PRIMARY KEY (`cart_id`)
) ENGINE=InnoDB AUTO_INCREMENT=5 DEFAULT CHARSET=utf8;

CREATE TABLE `Items` (
  `id` int(11) unsigned NOT NULL AUTO_INCREMENT,
  `cart_id` int(11) unsigned NOT NULL,
  PRIMARY KEY (`id`),
  KEY `cart_id` (`cart_id`),
  CONSTRAINT `items_ibfk_1` FOREIGN KEY (`cart_id`) REFERENCES `Cart` (`cart_id`)
) ENGINE=InnoDB AUTO_INCREMENT=7 DEFAULT CHARSET=utf8;
{% endhighlight %}


Như vậy mối quan hệ trong database giữa Cart và Item là một nhiều . Column cart_id là khoá chính trong bảng Cart và là khoá phụ trong bảng Items.

Trong Java mình thể hiện mối quan hệ 1 - nhiều qua annotation @OneToMany như sau

{% highlight java   linenos %}
public class Cart {

    @OneToMany(mappedBy="cart")
    private Set<Items> items;

}
{% endhighlight %}


### **3. Triển khai trong Java code

Bây giờ anh sẽ hướng dẫn các bạn xây dựng ứng dụng shopping cart . Sử dụng @OneToMany và @ManyToOne để thiết lập mối quan hệ giữa
Cart (gio hang) và Item (san phẩm).


#### Bước 1. Tạo các tables : Cart và Item

{% highlight mysql  linenos %}
CREATE TABLE `Cart` (
  `cart_id` int(11) unsigned NOT NULL AUTO_INCREMENT,
  PRIMARY KEY (`cart_id`)
) ENGINE=InnoDB AUTO_INCREMENT=5 DEFAULT CHARSET=utf8;

CREATE TABLE `Items` (
  `id` int(11) unsigned NOT NULL AUTO_INCREMENT,
  `cart_id` int(11) unsigned NOT NULL,
  PRIMARY KEY (`id`),
  KEY `cart_id` (`cart_id`),
  CONSTRAINT `items_ibfk_1` FOREIGN KEY (`cart_id`) REFERENCES `Cart` (`cart_id`)
) ENGINE=InnoDB AUTO_INCREMENT=7 DEFAULT CHARSET=utf8;
{% endhighlight %}

#### Bước 2. Thêm dependency trong maven

{% highlight java linenos %}
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-data-jpa</artifactId>
        </dependency>

         <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <scope>runtime</scope>
         </dependency>

{% endhighlight %}

#### Bước 3. Tạo Entity Cart

{% highlight java   linenos %}
@Entity
@Table(name="CART") // tên này trùng với tên Table trong database .
public class Cart {

    //...

    @OneToMany(mappedBy="cart") // chú ý biến cart này được khai báo trong Class Item bên dưới. Chúng phải giống y chang nhau cái tên
    private Set<Items> items;

    public Set<Items> getItems () {
      return items ;
    }
}
{% endhighlight %}

Chúng ta chú ý, theo yêu cầu thì một giỏ hàng (Cart) sẽ chứa nhiều sản phẩm giống như trong database mô tả . Để làm được việc đó
Ta sử dụng @OneToMany trong Class Cart, điều đó có nghĩa 1 giỏ hàng sẽ có nhiều sản phẩm (Items) .

Tiếp đến ta sẽ thấy từ mappedBy = "cart" . MappedBy dùng để đinh nghĩa Class Cart và Class Item sẽ liên kết với nhau thông qua tên "cart".
Và bắt buộc tên "cart" phải được định nghĩa trong Class Item. MappedBy giống như là 1 cầu nối để ta có thể từ Class Cart mình gọi hàm getItems mình
sẽ nhận được một danh sách Items

#### Bước 4. Tạo Entity Items

{% highlight java   linenos %}
@Entity
@Table(name="ITEMS")
public class Items {

    //...
    @ManyToOne
    @JoinColumn(name="cart_id", nullable=false) //cart_id chính là trường khoá phụ trong table Item liên kết với khoá chính trong table Cart
    private Cart cart;

    public Items() {}

    // getters and setters
}
{% endhighlight %}

Chúng ta thấy trong lớp Cart chúng ta định nghĩa @OneToMany và mappedBy với  giá trị "cart" để tạo liên kết giữa lớp Cart và Item  . Để liên kết
đó hoạt động thì ta cũng phải cấu hình biến "cart" trong Class Item.

Đầu tiên chúng ta sử dụng  @ManyToOne và @JoinColumn để định nghĩa cho biến cart để tạo sự liên kết ngược lại  giữa Class Items và Cart  .
.Trong @JoinColumn ta định nghĩa name = "car_id" . Cái 'cart_id ' chính là  column khoá phụ trong table Items mà ta định nghĩa trong database . nullable = false là ta ràng buộc dữ liệu không được phép null

#### Bước 5. Test ứng dụng

Chúng ta sẽ lưu giỏ hàng và các sản phẩm xuống database theo cách sau.


{% highlight java   linenos %}

 Items item1 = new Items ("Item 1");
 Items item2 = new Items ("Item 2");
 Set<Items> items = new HashSet<Items>();
 items.add(item1);
 items.add(item2);

 Cart cart = new Cart();
 cart.setItems(items);
 cart.save(); // như vậy ta sẽ lưu dữ liệu xuống 2 bảng Cart và Items


{% endhighlight %}

### **5. Kết luận**

Như vậy chúng ta sử dụng annotaion @OneToMany và @ManyToOne để thực hiện việc liên kết giữa hai entity với nhau. Từ Cart ta có thể lấy các kết quả
của Items.

Để hiểu thêm về mappedBy còn có chức năng nào mới không thì các bạn có thể đọc bài viết sau
