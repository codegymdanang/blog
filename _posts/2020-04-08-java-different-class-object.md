---
layout: blog
title: Sự Khác Nhau Giữa Class và Object  
category: Sự Khác Nhau Giữa Class và Object
tags: [java core]
summery: Blog 2
image: /images/blog/java.png
youtubeId: 0F_8a5_fKno
---

# Lập trình hướng đối tượng

## Lập trình hướng đối tượng là gì ?
Trả lời: lập trình hướng đối tượng là 1 kỹ thuật lập trình, cho phép lập trình viên trừu tượng hóa các đối tượng thực tế thành các đối tượng trong code. <br>
Ví dụ : Trong thực tế để quản lý 1 khách sạn thì mình có các công việc như quản lý khách tới khách sạn, mình có kế toán để thống kê tài chính, mình có bảo vệ. Như vậy lập trình hướng đối tượng thì trong thực tế có đối tượng khách hàng thì trong lập trình mình cũng có đối tượng khách hàng. Trong thực tế khách hàng có tên , tuổi, địa chỉ thì trong lập trình hướng đối tượng mình cũng có tên tuổi địa chỉ. Hướng đối tượng là ngoài thực tế có cái gì thì mình ánh xạ y chang trong lập trình

## Các tính chất của lập trình hướng đối tượng
Trả lời: Có 4 tính chất (tính trừu tượng, tính đóng gói, tính kế thừa, tính đa hình) <br>
+ Cho ví dụ minh hoạ cho mỗi tính chất <br>
  * Ví dụ tính trừa tượng <br>
    Ví dụ khi mình mua hàng online trên mạng như trang lazada, tiki hay amazon. Mình click vào mua sản phẩm sau đó 1 tuần sau     mình nhận được sản phẩm của mình. Trừa tượng ở chổ mình không biết lazada, tiki hay amazon sẽ lấy đơn hàng của mình, đóng    gói ra sao và họ vận chuyển như thế nào qua các thành phố và quốc gia. Mình chỉ biết là khi mình bấm vô nút mua hàng thì      mình sẽ nhận được hàng mà không cần quan tâm họ làm như thế nào đế ship hàng mình về đúng địa chỉ . Trong lập trình cũng      vậy khi mình gọi một phương thức từ một đối tượng mình chỉ quan tâm giá trị cung cấp cho phương thức đó và kết quả của        phương thức đó trả về, mình không biết code thực sự bên trong phương thức đó làm gì<br>

  * Ví dụ tính đa hình <br>
   Ví dụ cũng là phương thức chạy thì con gà chạy bằng 2 chân nhưng con chó chạy bằng 4 chân. Cùng một hành động chạy nhưng ở    những ngữ cảnh khác nhau thì hành động khác nhau <br>
  
  * Ví dụ tính kế thừa <br>
Ví dụ như con kế thừa tài sản của cha. Hoặc ví dụ khác như có lớp Animal có các thuộc tính tên, tuổi , và phương thức di chuyển. Nếu con chó kế thừa Animal thì nó sẽ kế thừa các thuộc tính tên , tuổi , và phương thức của lớp cha Animal. Chúng ta không cần phải khai báo lại biến tên, tuổi trong lớp con chó. <br>
* * Lợi ích của tính kế thừa
  Lớp con (lớp A) có thể tận dụng lại các thuộc tính và phương thức của lớp cha (lớp B) (nghĩa là các thuộc tính và phương       thức của lớp B có thể được tái sử dụng bởi lớp A).
  Lớp A có thể định nghĩa thêm thuộc tính và phương thức mới của riêng nó và có thể định nghĩa lại (hay còn gọi là ghi đè       phương thức, overriding) phương thức được kế thừa từ lớp B cho phù hợp với mục đích của nó.

  * Ví dụ tính đóng gói <br>
Tính đóng gói hay còn goi là che dấu dữ liệu . Đối với những dữ liêu quan trọng chúng ta không muốn cho các lớp khác truy cập và sử dung thì ta hạn chế không cho các lớp khác truy cập vào biến hay phương thức bảo mật


{% include youtubePlayer.html id=page.youtubeId %}

