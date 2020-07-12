---
layout: blog
title: Json Web Token là gì  
slug : json-web-token-la-gi
category: laptrinhspring
tags: [spring]
summery: Json Web Token là gì  
image: /images/blog/spring.png
description : Spring Json WebToken là gì . Cách . Json Web Token  . Ví dụ JWT , ví dụ Json web token
youtubeId: NSFLGrM6pAU
---

# **Giới thiệu nội dung bài viết**

Chào bạn, có phải bạn đang tự hỏi Json Web Token là gì  không ? Nó mã hoá như thế nào ? Nó khác gì với session và cookie. Và nó được sử dụng ở đâu trong lập trình
Bài viết hôm nay chúng ta sẽ nói về .

- JSON WEB TOKEN là gì ?
- Cấu tạo của 1 JWT
- Video demo

# **1. Vì sao chúng ta cân JSON**

Anh lấy ví dụ về mua hàng online trên mạng và thanh toán tiền qua thẻ visa hoặc master. Khi các em thanh toán qua một ứng dụng trung gian để mua sản phẩm thì 
ứng dụng trung gian sẽ yêu cầu các em nhập vào số thẻ và mã cvv. Như các em thấy nếu thông tin này không bị mã hoá trước khi truyền đi trên mạng. Hacker hoàn toàn có 
thể lấy được thông tin về số thẻ và mã cvv của mình. Nếu có được 2 thông tin này hacker hoàn toàn có thể lấy hết số tiền trong thẻ hoặc sẽ dùng thông tin đó đi mua hàng
Như vậy rất nguy hiểm khi thông tin chúng ta truyền trên mạng mà không được bảo mật

Chúng ta sử dụng session và cookie để lưu thông tin cho những ứng dụng web. Nhưng nếu ứng dụng của ta là mobile thì không có session và cookie. Mà thay vào đó là dùng JWT

<br>
# **2. JSON Web Token là gì**

JSON Web Token (JWT) là 1 tiêu chuẩn mở (RFC 7519) định nghĩa cách thức truyền tin an toàn giữa client và server bằng đối tượng JSON. Thông tin này có thể được xác thực và đánh dấu tin cậy nhờ vào "chữ ký" của nó.
Phần chữ ký của JWT sẽ được mã hóa nhằm tránh các hacker có thể lấy nó thông qua mạng.  Bằng các thuật toán mã hoá có tên gọi là  HMAC hoặc các thuật toán mã hoá dữ liệu là RSA thì dữ liệu chúng ta sẽ được mã hoá trên mạng , hacker có lấy được cũng khó mà giải mã ra các dữ liệu.
Như vậy mình sẽ yên tâm hơn vì các dữ liệu mình truyền đi đều đã được mã hoá.

<br>
# **3. Cấu tạo của 1 JWT**

{:refdef: style="text-align: center;"}
![JWT](/images/post/spring/jwt.jpeg){:class"img-responsive"}
{: refdef}

JWT bao gồm 3 phần và ngăn cách nhau bởi dấu chấm

- Header
- Payload
- Signature (chữ ký số )

Ví dụ sau đây là một token được sinh ra.

eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJuZ3V5ZW4iLCJleHAiOjE1Njg3NTAxMTEsImlhdCI6MTU2ODczMjExMX0.mPuurljzpycuyy0d_B0GNVPBz7SEpPCPIoGGy2lUVgJ9rLlRJkDCdG2vwkXITUsJ4dnU5IF178yXv34izGPcpw

- Header là  eyJhbGciOiJIUzUxMiJ9
- Payload là eyJzdWIiOiJuZ3V5ZW4iLCJleHAiOjE1Njg3NTAxMTEsImlhdCI6MTU2ODczMjExMX0
- Chữ ký số là mPuurljzpycuyy0d_B0GNVPBz7SEpPCPIoGGy2lUVgJ9rLlRJkDCdG2vwkXITUsJ4dnU5IF178yXv34izGPcpw

- Header lưu trữ thông tin về loại token và thuật toán mã hoá đang dùng
- Payload là phần sẽ chứa nội dungserver (dữ liệu) ta truyền lên server . Ngoài ra nó còn chứa đựng các thông tin về tokien như ngày hết hạn , ngày sinh ra token
subject, etc
- Signature là một chuỗi được mã hoá  bao gồm các thông tin header + payload + chữ ký 

Các em có thể kiểm tra token tại trang web sau https://jwt.io

# **4. Cơ chế hoạt động của token**

<br>
# **5. Cách tạo và sử dụng JWT**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}
