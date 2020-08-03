---
layout: course-java
title: Bo nho
slug : bo-nho
category: khoajava
tags: [java core]
summery: Lập Trình Hướng Đối Tượng  
image: /images/blog/java.png
featureImage: /images/post/javacore/feature_oop.png
description : Hiều về lập trình hướng đối tượng là gì trong lập trình java ? Các khái niệm về tính đa hình, tính trừu tượng, tính kế thừa, và tính đóng gói trong lập trình hướng đối tượng.
youtubeId: 0F_8a5_fKno
---

Memory

<br>
# **1. Lập trình hướng đối tượng là gì**

Lập trình hướng đối tượng là 1 kỹ thuật lập trình, cho phép lập trình viên trừu tượng hóa các đối tượng thực tế thành các đối tượng trong code .
Anh sẽ lấy một ví dụ : Trong thực tế để quản lý 1 khách sạn thì mình có các công việc như : quản lý khách hàng ở tại khách sạn, mình có kế toán để thống kê tài chính, mình có bảo vệ.
Cũng tương tự như vậy lập trình hướng đối tượng nghĩa là trong thực tế có đối tượng khác hàng thì trong lập trình mình cũng có đối tượng khách hàng
Trong thực tế khách hàng có tên, tuổi, địa chỉ thì trong lập trình hướng đối tượng mình cũng có tên, tuổi, địa chỉ. Nói tóm lại hướng đối tượng là ngoài thực tế có gì thì mình ánh xạ y chang như vậy trong
lập trình.

Ví dụ như anh dùng Java để viết một ứng dụng quản lý nhà hàng ở trên,   thực tế có đối tượng là Khách hàng thì anh sẽ ánh xạ nó thành ngôn ngữ Java như sau.

{% highlight java linenos %}

 class KhachHang {
  private String name;
  private int age;

}
{% endhighlight %}

Như vậy khi chương trình chạy các đối tượng đó tương tác trao đổi dữ liệu với nhau để thực thi các nghiệp vụ mà mình mong muốn. Trong thực tế mình có hằng trăm đối tượng trong một chương trình. Nhờ có lập trình hướng đối tượng mà mình có thể dể dàng xây dựng được các ứng dụng, chức năng tương ứng với thực tế .

<br>
# **2. Các tính chất của lập trình hướng đối tượng và ví dụ minh hoạ**

- Tính trừu tượng

Bạn đã từng mua hàng online trên trang Tiki chưa ? Khi bạn click vào mua sản phẩm sau đó 1 tuần sau bạn nhận được sản phẩm của mình. Trừu tượng ở chổ mình không biết
Tiki sẽ lấy đơn hàng của mình, đóng gói ra sao và họ vận chuyển như thế nào qua các thành phố. Bạn chỉ biết là khi bấm nút mua hàng thì bạn sẽ nhận được hàng mà không
cần quan tâm họ làm như thế nào để ship hàng về đúng địa chỉ. Trong lập trình cũng vậy khi bạn gọi một phương thức từ một đối tượng, bạn chỉ quan tâm giá trị (tham số) cung cấp cho phương thức
và kết quả trả về của phương thức đó. Bạn không biết code thực sự bên trong phương thức đó làm gì. Trong thực tế gặp rất nhiều khi mình gọi một API từ một dịch vụ khác. Anh ví dụ như mình tích hợp chức năng login của facebook vào chương trình của mình. Mình chỉ cần nhúng thư viện facebook vào và cung cấp các tham số mà thư viện facebook cần. Mình không quan tâm các cái code viết trong thư viện đó là gì? Điều mình quan tâm là khi mình truyền đúng các tham số thì facebook sẽ trả về một giá trị tương ứng và mình dùng nó để đăng nhập vào hệ thống của mình.

- Tính đa hình

Ví dụ cũng là phương thức chạy thì con gà chạy bằng 2 chân nhưng con chó chạy bằng 4 chân. Cùng một hành động chạy nhưng ở những ngữ cảnh khác nhau thì hành động khác nhau. Ví dụ như ứng dụng thanh toán điện tử mà anh đã từng tham gia. Cũng là phương thức thanh toán nhưng nếu người dùng dùng thể HSBC thì anh sẽ dùng thư viện HSBC để thực hiện giao dịch. Nếu người dùng muốn sử dụng thẻ Techcombank thì anh sẽ dùng thư viện Techcombank. Vậy như mọi người thấy cũng là phương thức payment nhưng nếu là ngữ cảnh khác nhau (HSBC, Techcombank) thì anh sẽ dùng thư viện thanh toán tương ứng

- Tính kế thừa

Ví dụ như con kế thừa tài sản của cha. Hoặc ví dụ khác như có lớp Animal có các thuộc tính tên, tuổi , và phương thức di chuyển. Nếu con chó kế thừa Animal thì nó sẽ kế thừa các thuộc tính tên , tuổi , và phương thức của lớp cha Animal.
Chúng ta không cần phải khai báo lại biến tên, tuổi trong lớp con chó. Trong lúc lập trình anh sẽ dụng rất nhiều kế thừa vì nó giảm đi số lượng các dòng code thay vì phải khai báo đi khai báo lại một cái biến ở nhiều nơi.

- Tính đóng gói

Tính đóng gói hay còn goi là che dấu dữ liệu . Đối với những dữ liêu quan trọng chúng ta không muốn cho các lớp khác truy cập và sử dung thì ta hạn chế không cho các lớp khác truy cập vào biến hay phương thức bảo mật.
Chúng ta dùng các access modifier như public , protected , private , default để che giấu các dữ liệu và không để lớp khác có thể thấy nó. Để hiểu rõ hơn mục đích các em hãy xem bài viêt Access Modifier ở đây (https://levunguyen.com/laptrinhjava/2020/04/05/phan-biet-access-modifier-trong-java/)

<br>
# **3. Lợi ích của các tính chất lập trình hướng đối tượng**

- Tính kế thừa
    - Lớp con (lớp A) có thể tận dụng lại các thuộc tính và phương thức của lớp cha (lớp B) (nghĩa là các thuộc tính và phương thức của lớp B có thể được tái sử dụng bởi lớp A).
    - Lớp A có thể định nghĩa thêm thuộc tính và phương thức mới của riêng nó và có thể định nghĩa lại (hay còn gọi là ghi đè  phương thức, overriding) phương thức được kế thừa từ lớp B cho phù hợp với mục đích của nó.

- Tính đóng gói
    - Tính đóng gói hay còn gọi là che dấu dữ liệu . Đối với những dữ liêu quan trọng chúng ta không muốn cho các lớp khác truy cập và sử dung thì ta hạn chế không cho các lớp khác truy cập vào biến hay phương thức bảo mật.

- Tính đa hình
    - Giúp chúng ta tái sử dụng code  classes, methods.  
    - Chúng có thể tái sử dụng trong nhiều trường hợp code khác nhau.
    - Giảm sự phụ thuộc (low coupling) giữa các object từ đó dể dàng mở rộng chức năng mà không sợ ảnh hưởng tới các chức năng liên quan.

- Tính trừu tượng
    - Khả năng tái sử dụng code.
    - Giúp chúng ta tập trung nghĩ về object có khả năng làm được gì hơn là nó hoạt động như thế nào.
    - Nhóm nhiều object có chung các tính chất và hành động lại với nhau.

<br>
# **4. Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé.**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}