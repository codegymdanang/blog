---
layout: blog
title: OneToOne Relationship
slug : one-to-one
category: laptrinhspring
tags: [spring]
summery: Lập Trình Spring Security
image: /images/blog/spring.png
description : Spring Security
youtubeId: WNfuVJptPnQ
---

### **1. Giới thiệu nội dung bài viết**

Chào các em ,chủ đề hôm nay chúng ta sẽ nói về các annotation @OneToOne  .
Nội dung mình sẽ giải thích trong bài này sẽ xoay quanh các chủ đề sau đây.

- OneToOne là   ?
- Cấu hình và triển khai một dự án dùng các annotation


### **2. One To Many annotation**

Anh lấy ví dụ như mình làm ứng dụng về quản lý nhân sự ở công ty . Một nhân viên chỉ có một địa chỉ duy nhất.

Nếu ta thiết kết database thì ta có 2 bảng là user  và address như sau .

{% highlight mysql  linenos %}
CREATE TABLE `address` (
  `id` int(11) unsigned NOT NULL AUTO_INCREMENT,
  PRIMARY KEY (`cart_id`)
  'street' varchar(45),
  'city' varchar(45)
) ENGINE=InnoDB AUTO_INCREMENT=5 DEFAULT CHARSET=utf8;

CREATE TABLE `user` (
  `id` int(11) unsigned NOT NULL AUTO_INCREMENT,
  `street` int(11),
  'city' varchar(45)
  KEY `adress_id` (`user_address`),
  CONSTRAINT `usser_address` FOREIGN KEY (`id`) REFERENCES `Address` (`address_id`)
) ENGINE=InnoDB AUTO_INCREMENT=7 DEFAULT CHARSET=utf8;
{% endhighlight %}

Ta tạo 2 database user và address . addressid trong table user là khoá phụ liên kết đến bảng Address


### **3. Triển khai trong Java

Đầu tiên mình tạo Class User và sử dụng annotation @OneToOne để nói rằng. Một user chỉ có một địa chỉ duy nhất.  

{% highlight java   linenos %}
@Entity
@Table(name = "users")
public class User {

    @Id
    @GeneratedValue(strategy = GenerationType.AUTO)
    @Column(name = "id")
    private Long id;
    //...

    @OneToOne(cascade = CascadeType.ALL)
    @JoinColumn(name = "address_id", referencedColumnName = "id")
    private Address address; // biến address này sẽ trùng  với giá trị  mappedBy trong Class User dưới đ

    // ... getters and setters
}
{% endhighlight %}

Như các em thấy ở trên ta sử dụng annotation @OneToOne để nói rằng một user chỉ có 1 đối tượng Address .

Tiếp đến cascade = CascadeType.ALL nghĩa là khi xoá một dòng dữ liệu trong table Address. Thì bên bản User cũng sẽ bị xoá 1 đòng tương ứng với dòng bị xoá bên table User . Như vậy dữ liệu ở 2 table User và Address dữ liệu sẽ giống nhau. Mục đích của Casecade là để toàn vẹn dữ liệu, dữ liệu sẽ thống nhất ở 2 bảng,tránh thừa dữ liệu không cần thiết.

Chúng ta sử dụng @JoinColumn để cấu hình cho biến address là tìm kiếm trong column nào trong database mà map vào (nó chính là foregin key)
.Biến address này được khai báo trong Class Address dưới đây.

{% highlight java   linenos %}
@Entity
@Table(name = "address")
public class Address {

    @Id
    @GeneratedValue(strategy = GenerationType.AUTO)
    @Column(name = "id")
    private Long id;
    //...

    @OneToOne(mappedBy = "address")
    private User user;

    //... getters and setters
}
{% endhighlight %}

#### Bước 5. Test ứng dụng

Chúng ta sẽ lưu xuống database theo cách sau.


{% highlight java   linenos %}

 Address address = new Address ("Address 1");

 User user  = new User();
 user.setAddress(address);
 user.save(); // như vậy ta sẽ lưu dữ liệu xuống 2 bảng User và Address  


{% endhighlight %}

### **5. Kết luận**

Như vậy chúng ta sử dụng annotaion @OneToOne để thực hiện việc liên kết giữa hai entity với nhau mà chúng có quan hệ 1-1. Từ User mình có thể
suy ra địa chỉ của user và ngược lại

Để hiểu thêm về mappedBy còn có chức năng nào mới không thì các bạn có thể đọc bài viết sau
