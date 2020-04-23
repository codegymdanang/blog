---
layout: blog
title: Các phương thức HTTP
category: blog
tags: [spring]
summery:  Các phương thức HTTP
image: /images/blog/spring.png
description : Các loại Request HTTP 
youtubeId: Awpe1PIC-M4
---


<br><br>

### Tổng hợp các loại request 

Có tất cả 9 loại request.

1. GET: được sử dụng để lấy thông tin từ sever theo URI đã cung cấp.
2. HEAD: giống với GET nhưng response trả về không có body, chỉ có header.
3. POST: gửi thông tin tới sever thông qua các biểu mẫu http( đăng kí chả hạn..).
4. PUT: ghi đè tất cả thông tin của đối tượng với những gì được gửi lên.
5. PATCH: ghi đè các thông tin được thay đổi của đối tượng.
6. DELETE: xóa tài nguyên trên server.
7. CONNECT: thiết lập một kết nối tới server theo URI.
8. OPTIONS: mô tả các tùy chọn giao tiếp cho resource.
9. TRACE: thực hiện một bài test loop - back theo đường dẫn đến resource.
<br>

### Một số khái niệm khác 
SAFE
một method được coi là safe khi nó không làm thay đổi trạng thái "sate" của server. Nói cách khác, an toàn là chỉ đọc mà không làm thay đổi bất kì điều gì. Các method được coi là safe chỉ có: GET, HEAD và OPTIONS.
Unsafe: PUT, DELETE, POST và PATCH.

IDEMPOTENT
các method được coi là idempotent khi nó có thể thực hiên n + 1 lần mà vẫn trả lại 1 kết quả như ban đầu.

vì điều này nên các method safe thì đều idempotent. Nhưng unsafe chưa chắc đã idempotent.

1 số lưu ý: header dài tối đa 8kb và cũng phụ thuộc cả vào trình duyệt.
body thì limit của nó tùy trình duyệt. Url không dài quá 2 nghìn kí tự (ror).
<br>

### GET VS POST
ột ứng dụng web được thiết kế theo restful thì get chỉ dùng để lấy dữ liệu và post chỉ dùng để đẩy dữ liệu lên. 
Một chút khác biệt dễ nhận thấy giữa get và post là get thì không có body. Khi dùng get để truyền dữ liệu lên sever chúng ta thấy rằng tất cả các paramater đều bị hiển thị trên url của request, xét về khía cạnh bảo mật thì điều này thật là tệ.
Post thì khác, nó giấu parameters trong body và mã hóa chúng đi, ngăn cản các phần tử trung gian ăn cắp nội dung. Nhưng post chỉ có tính an toàn đối với client, còn với sever thì lại khác. Các method như post, put, delete bị coi là unsafe và not idempotent cho server.
<br>

### POST/PUT/PATCH
Điểm khác biệt giữ post và put đơn giản là put là idempotent còn post thì không, bạn sẽ nhận được thông báo lỗi khi gửi một request post với cùng 1 nội dung 2 lần nhưng put thì không, nó luôn trả về kết quả như nhau.
post: tạo mới.
put: ghi đè(toàn bộ) hoặc tạo mới 1 resource.
patch: cập một 1 phần của resource.
<br>

### Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé .

{% include youtubePlayer.html id=page.youtubeId %}