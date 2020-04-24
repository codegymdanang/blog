---
layout: blog
title: Json Web Token là gì  
slug : json-web-token-la-gi
category: blog
tags: [spring]
summery: Json Web Token là gì  
image: /images/blog/spring.png
description : Spring Json WebToken là gì 
youtubeId: 6VCjvbbR_SI
---

Chào bạn, có phải bạn đang tự hỏi Json Web Token là gì  không ? Nó mã hoá như thế nào ? Nó khác gì với session và cookie. Và nó được sử dụng ở đâu trong lập trình
Hôm nay anh sẽ giải thích cho các bạn các câu hỏi trên ở video sau nhé.
<br><br>

#### JSON Web Token là gì ?
JSON Web Token (JWT) là 1 tiêu chuẩn mở (RFC 7519) định nghĩa cách thức truyền tin an toàn giữa client và server bằng đối tượng JSON. Thông tin này có thể được xác thực và đánh dấu tin cậy nhờ vào "chữ ký" của nó. 
Phần chữ ký của JWT sẽ được mã hóa lại bằng HMAC hoặc RSA.

### Cấu tạo của 1 JWT
![JWT](/images/post/spring/jwt.png){:class"img-responsive"}
JWT bao gồm 3 phần và ngăn cách nhau bởi dấu chấm
1. Header
2. Payload
3. Signature (chữ ký số )



### Và bây giờ, chúng ta sẽ đi kỷ hơn cách tạo và mã hoá của JWT  . 
{% include youtubePlayer.html id=page.youtubeId %}