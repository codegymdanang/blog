---
layout: blog
title: Spring Optional PathVariable
slug : optional-pathvariable
category: laptrinhspring
tags: [spring]
summery: Spring Optional PathVariable
image: /images/blog/spring.png
description : Optional PathVariable trong Spring .học lập trình  ngôn ngữ lập trình lập trình java java cơ bản khóa học lập trình java học ngôn ngữ lập trình java
youtubeId: WNfuVJptPnQ
---

### **1. Giới thiệu nội dung bài viết**

Chào các em ,chủ đề hôm nay chúng ta sẽ nói về Spring Optional PathVariable sử dụng như thế nào.
Nội dung mình sẽ giải thích trong bài này sẽ xoay quanh các chủ đề sau đây.

- PathVariable dùng để làm gì ?
- Sử dụng Optional PathVariable ?
- Cấu hình và triển khai một dự án dùng các annotation


### **2. PathVariable dùng để làm gì**

Như các em đã thấy trong bài RequestMaping anh viết lần trước. Chúng ta sử dụng
@PathVariable để mapping URI mà người dùng nhập trên trình duyệt vào Controller tưng ứng.

Ví dụ anh có một controller có phương thức là getArticle sau.

{% highlight java  linenos %}
@RequestMapping(value = {"/article", "/article/{id}"})
public Article getArticle(@PathVariable(name = "id") Integer articleId) {
    if (articleId != null) {
        //...
    } else {
        //...
    }
}
{% endhighlight %}

Ở đây chúng ta mong muốn khi người dùng gõ vào url là /article hay /article/id .
Thì Spring sẽ tự động mapping vô method getArticle trong Controller.

Nếu ta có request là /article/123 thì mình gán giá trị 123 vô tham số articleId

Nếu ta có request là /article thì Spring sẽ trả về lỗi 500

{% highlight java  linenos %}
org.springframework.web.bind.MissingPathVariableException:
  Missing URI template variable 'id' for method parameter of type Integer
{% endhighlight %}

Như vậy để làm sao mình không bị lỗi như trên . Giải pháp sẽ là dùng optional

### **3. Sử dụng Optional Parameter**

Cũng ví dụ code về controller trên. Bây giờ ta thêm Optional vào

{% highlight java  linenos %}
@RequestMapping(value = {"/article", "/article/{id}"}")
public Article getArticle(@PathVariable Optional<Integer> optionalArticleId) {
    if (optionalArticleId.isPresent()) {
        Integer articleId = optionalArticleId.get();
        //...
    } else {
        //...
    }
}
{% endhighlight %}

Ở ví dụ trên ta sử dụng Optional<Integer> optiontalArticleId để mapping giá trị id từ request url của người dùng

Nếu ta có request là /article/123 thì mình gán giá trị 123 vô tham số optiontalArticleId

Nếu ta có request là /article thì optiontalArticleId sẽ là null. Khi sử dụng Optional ta sẽ cos được các method của Optional như isPresent(), get(), or orElse() để ta có thể truy cập và thao tác và xử lý theo ý ta mong

### **4. Kết luận**

Mình không nên sử dụng @RequestMapping(value = {"/article", "/article/{id}"}") cho cùng môt method vì nó dể gây ra nhầm lẫn. Tốt nhất 1 request nên được xử lý bởi môt method.
Ta có thể tách ra như sau

{% highlight java  linenos %}
@RequestMapping(value = "/article/{id}")
public Article getArticle(@PathVariable(name = "id") Integer articleId) {
    //...        
}

@RequestMapping(value = "/article")
public Article getDefaultArticle() {
    //...
}
{% endhighlight %}