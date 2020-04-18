---
layout: blog
title: Hiểu  Spring Security 
category: blog
tags: [spring]
summery: Hiểu  Spring Security 
image: /images/blog/spring.png
youtubeId: WNfuVJptPnQ
---
 
Chào bạn, bạn đang gặp rắc rối với Spring Security? bạn không hiểu luồng đi của ứng dụng ? 
bạn đang quan tâm trong thực tế mình sẽ áp dụng như thế nào ? Hôm nay anh sẽ hướng dẫn mọi người cách sử dung Spring security.

### Demo mục đích bài hướng dẫn hôm nay
Kết thúc bài giảng hôm nay các em sẽ làm được ứng dụng phân quyền tuỳ thuộc vào user đăng nhập vào hệ thống là user hay admin mà ta cho phép họ 
vào trang web tương ứng. Ví dụ  
1. Trang Home thì ai vào cũng được 
2. Trang Admin thì chỉ có admin được vào và thấy được trang . Nếu là role user và vào trang Admin thì mình hiện thông báo lỗi bạn không có quyền
3. Trang User Info thì user và admin được phép vào. Cái này do mình hoàn toàn có thể thay đổi quyền trong database để phân quyền ai được phép vào trang nào

![Demo Spring Secu ](/images/post/spring/springsecurity.gif){:class="img-responsive"}

### Các khái niệm về Spring Security
1. Authentication : Khi nói về authentication là ta nói về chức năng đăng nhập vào hệ thống. Authentication nghĩa là bạn có phải là người dùng của hệ thống hay không
2. Authorization  : Khi nói về authorization ta nói về quyền hạn được phép làm gì ? Trong ví dụ trên mình có user và admin . Bước đầu tiên họ phải authentication 
xát thực mình là user trong hệ thống . Tiếp đến tuỳ vào role của mình là admin hay user mà mình chỉ có quyền truy cập một số trang nhất định thuộc thẩm quyền của mình


### Chúng ta bắt tay vào code ứng dụng thôi
Luồng đi của ứng dụng mình như sau
1. User nhập vào username và password sau đó bấm login 
2. Server sẽ nhận được request từ người dùng và chuyển tới controller tương ứng
3. Controller sẽ gọi Service và Service sẽ gọi database để lấy thông tin authentication đúng không và role người dùng là gì?
4. Sau khi có thông tin đúng thì trả kết quả lại cho người dùng
Okie , vậy chúng ta sẽ đi từng bước sau để xây dụng ứng dụng nhé .

## Bước 1 . Chuẩn bị database để lưu thông tin người dùng và role (vai trò,được phép làm gì) 

![Database  ](/images/post/spring/security_db.png){:class="img-responsive"}

Như vậy để làm ứng dụng spring security mình sẽ lưu user name và quyền vào trong database. Anh sẽ giải thích ý nghĩa của từng bảng.

1. Table APP_USER  dùng để lưu thông tin username và passwor . Khi người dùng đăng nhập họ truyền user name và password vào form sau đó code của mình sẽ query
trong databaPPse xem là username và password có đúng như trong database không ?d Bước này chính là authentication
2. Table APP_ROLE dùng để xát định xem user sau khi login thành công thì được phép vào những trang nào . Ví dụ admin vào được 2 trang user và admin page . Nhưng
user chỉ được phép vào 1 trang là user page
3. Table USER_ROLE là table dùng để nối 2 bảng APP_USER và APP_ROLE , nó được dùng để cho phép 1 user có thể có nhiều quyền. Ví dụ như admin có thể vào cả 2 trang user và admin 

4. Tạo database thôi nào. Anh có viết script tạo cấu trúc database và tạo dữ liệu user và admin tại đây. Mọi người copy về và chạy script này trong workbench để tạo dữ liệu nhé
https://github.com/codegymdanang/CGDN-SpringBoot-SpringSecurity
Nếu chạy script xong thì mình sẽ có 2 users sau :
+ username : dbuser1  -  Password : 123
+ username : dbadmin1 -  Password : 123






{% include youtubePlayer.html id=page.youtubeId %}
