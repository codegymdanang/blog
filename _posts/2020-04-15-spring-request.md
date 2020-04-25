---
layout: blog
title: Phân biệt  Request Param và  PathVariable
slug : phan-biet-request-param-va-path-variable
category: laptrinhspring
tags: [spring]
summery: Phân biệt  Request Param và  PathVariable
image: /images/blog/spring.png
description : Phân biệt Request Param và Path Variable 
youtubeId: luc3zTLri6M
---

Chào bạn , chắc bạn đang phân vân Request Param và PathVariable có khác gì nhau không ? Khi nào dùng thì bài viết hôm nay 
anh sẽ trình bày sự khác nhau đó .
<br><br>

### Request Param
Sử dụng Request Param ở server  để lấy giá trị người dùng nhập trên trình duyệt .
Ví dụ khi người dùng gõ vào đường link như sau để gửi 2 giá trị 10 và 20 lên server .
http://localhost:8080/springmvc/hello/101?param1=10&param2=20

Phía Controller ta bắt lại 2 giá trị 10 và 20 như sau :

{% highlight java linenos %} 
public String getDetails(@RequestParam(value="param1", required=true) String param1, @RequestParam(value="param2", required=false) String param2){
    
}
{% endhighlight %}
<br>

### Path Variable
Sử dụng Path Variable ở server  để lấy giá trị người dùng nhập trên trình duyệt. 

Ví dụ khi người dùng nhập vào url sau và muốn truyền 1234 lên server thì bên server ta sử lý như sau .
http://localhost:8080/MyApp/user/1234

{% highlight java linenos %} 
@RequestMapping(value="/user/{userId}", method = RequestMethod.GET)
public List<Invoice> listUsersInvoices(
            @PathVariable("userId") int user) {
  ...
}
{% endhighlight %}
<br>

### Kết hợp cả 2 trong 1 request 
http://localhost:8080/MyApp/user/1234/invoices?date=12-05-2013

{% highlight java linenos %} 
@RequestMapping(value="/user/{userId}/invoices", method = RequestMethod.GET)
public List<Invoice> listUsersInvoices(
            @PathVariable("userId") int user,
            @RequestParam(value = "date", required = false) Date dateOrNull) {
  
}
{% endhighlight %}
<br>

### Kết luận 
Cả 2 cách trên đều thực hiện chung một nhiệm vụ là lấy các tham số từ người dùng truyền lên. Bạn sử dụng cái nào cũng làm được 
mục đích của mình . Tuy nhiên tuỳ vào thiết kế của một hệ thống mà lựa chọn Request Param hoặc  Path Variable để sử dụng mới đem lại
hiệu quả cao được . Lấy ví dụ mình viết Restfull Web Service thì chắc chắn mình phải dùng Path Variable . Còn thường Request Param khi ta chỉ muống
query data trên URL. 
<br>

### Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé .

{% include youtubePlayer.html id=page.youtubeId %}