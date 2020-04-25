---
layout: blog
title: Luồng đi của ứng dụng Spring MVC 
slug : spring-mvc-la-gi
category: laptrinhspring
tags: [spring]
summery: Luồng đi của ứng dụng Spring MVC 
image: /images/blog/spring.png
description : Luồng đi ứng dụng Spring MVC 
youtubeId: 7Wpi_jC8CqA
---

Chào bạn, bạn đang học Spring MVC nhưng chưa hiểu luồng đi của ứng dụng nó chạy  như thế nào. Ví dụ như khi người dùng gõ một url như sau vào trình duyệt
http://localhost8080 thì ứng dụng mình sẽ chạy qua các tầng nào của springmvc  để trả kết quả là trang home cho người dùng thấy được ?
Trong bài này anh sẽ hướng dẫn mọi người các bước mà SpringMVC xử lý một request (yêu cầu) từ người dùng. 
<br><br>
 
## Luồng đi của ứng dụng MVC qua các tầng
Trước hết mình đi qua hình ảnh về luồng đi của ứng dụng spring gồm có các thành phần nào.
![Luồn đi của ứng dụng MVC  ](/images/post/spring/springmvcflow.jpg){:class="img-responsive"}

1. Người dùng điền vào tên website mình cần truy cập trên browser sau đó bấm enter. Lúc này mình gửi 1 request lên server nơi mà mình triển khai sourcecode. 

2. Thành phần DispatcherServlet của  Spring MVC sẽ nhận được request (yêu cầu) của người dùng ở bước 1. 

3. Sau khi nhận được request(yêu cầu) DispatcherServlet sẽ chuyển yêu cầu đó tới Controller bằng các cơ chế mapping mà ta khai báo trong Handler Mapping (có nhiều cách để cấu hình mapping từ yêu cầu 
 người dùng vào Controller).

4. Sau khi vào controller tư ứng thì từ controller ta gọi services, service gọi repository, repository sẽ sử dung tầng persisten để thao tác với database lấy dữ liệu .
và chuyển hoá dữ liệu trong database thành model và trả ngược lại cho controller.

5. Controller sẽ trả về tên view (tên trang web  ) và model cho Dispatchervleter. 

6. DispatcherServlet sẽ dự vào tên view mà controler trả về . Nó sẽ đi tìm trang view (thymeleaf,jsp) tương ứng dựa vào việc ta cấu hình View Reolver mà Dispatcher biết phải tìm thấy trang view ở đâu
 đồng thời truyền model để trang view hiểu thị dữ liệu. Kết quả cuối cùng là ta có một trang website hoàn chỉnh có HTML và dữ liệu .
7. Cuối cùng DispatchServlet gửi lại kết quả trang web cho client.
<br>

### Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé . 

{% include youtubePlayer.html id=page.youtubeId %}