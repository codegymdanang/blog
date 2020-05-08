---
layout: blog
title: Json Web Token là gì  
slug : json-web-token-la-gi
category: laptrinhspring
tags: [spring]
summery: Json Web Token là gì  
image: /images/blog/spring.png
description : Spring Json WebToken là gì . Cách . Json Web Token  . Ví dụ JWT , ví dụ Json web token
youtubeId: 6VCjvbbR_SI
---

### **1. Giới thiệu nội dung bài viết**

Chào bạn, có phải bạn đang tự hỏi Json Web Token là gì  không ? Nó mã hoá như thế nào ? Nó khác gì với session và cookie. Và nó được sử dụng ở đâu trong lập trình
Bài viết hôm nay chúng ta sẽ nói về .

- JSON WEB TOKEN là gì ?
- Cấu tạo của 1 JWT
- Video demo


#### **2. JSON Web Token là gì**

JSON Web Token (JWT) là 1 tiêu chuẩn mở (RFC 7519) định nghĩa cách thức truyền tin an toàn giữa client và server bằng đối tượng JSON. Thông tin này có thể được xác thực và đánh dấu tin cậy nhờ vào "chữ ký" của nó.
Phần chữ ký của JWT sẽ được mã hóa lại bằng HMAC hoặc RSA.

### **3. Cấu tạo của 1 JWT**

{:refdef: style="text-align: center;"}
![JWT](/images/post/spring/jwt.png){:class"img-responsive"}
{: refdef}

JWT bao gồm 3 phần và ngăn cách nhau bởi dấu chấm

- Header
- Payload
- Signature (chữ ký số )

### **4. Cách tạo và sử dụng JWT**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}
