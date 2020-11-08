---
layout: course-bootstrap
title: Sử dụng form trong Bootstrap 
slug : su-dung-form-trong-bootstrap
category: laptrinhweb
tags: [bootstrap]
summery: Form
image:
description : Khi làm các trang website, trong quá trình lập trình web các lập trình viên cần tạo các form để khách hàng nhập input vào. Bài viết này sẽ giúp bạn hiểu được Form trong Bootstrap là gì? Cách sử dụng các dạng Form trong lập trình web. Cụ thể bài viết chia sẻ cho các bạn 2 dạng form sử dụng trong Bootstrap 4 gồm Staked Form, Form tràn màn hình và Inline Form, Form trên cùng 1 dòng. Ngoài ra trong bài viết, anh cũng sẽ hướng dẫn cách làm để tạo dạng Form Validation trong Bootstrap 4.
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Trong quá trình <b>lập trình web</b>, khi làm các trang website, các lập trình viên sẽ cần tạo ra các dạng <b>form</b> để khách hàng nhập input vào đó. Tuỳ bố cục trang website cũng như sở thích khách hàng mà các bạn có thể chọn thiết lập kiểu dạng <b>form</b> nào thích hợp.

<br>
Trong phạm vi bài viết này anh sẽ chia sẻ cho các bạn 2 dạng <b>form</b> sử dụng trong Bootstrap 4 gồm Staked Form ( Form tràn màn hình) và Inline Form (Form trên cùng 1 dòng). Ngoài ra trong bài viết, anh cũng sẽ hướng dẫn cách làm để tạo dạng Form Validation trong Bootstrap 4.

<br>
Vậy cụ thể mỗi loại <b>form</b> trên là gì, cách làm chúng như thế nào trong <b>lập trình web</b>? Các bạn cùng đọc những chia sẻ sau đây của anh nhé! 
 

## **1. Form trong Bootstrap 4**

Trong Boostrap hỗ trợ chúng ta 2 loại form là Staked Form (form tràn màn hình) và inline Form (form trên cùng 1 dòng).



## **2. Staked Form trong Bootstrap 4**

Chúng ta sử dụng class form-group và form-control

<br>
{% highlight html  linenos %}

 <form action="/action_page.php">
  <div class="form-group">
    <label for="email">Email address:</label>
    <input type="email" class="form-control" placeholder="Enter email" id="email">
  </div>
  <div class="form-group">
    <label for="pwd">Password:</label>
    <input type="password" class="form-control" placeholder="Enter password" id="pwd">
  </div>
  <div class="form-group form-check">
    <label class="form-check-label">
      <input class="form-check-input" type="checkbox"> Remember me
    </label>
  </div>
  <button type="submit" class="btn btn-primary">Submit</button>
</form> 

{% endhighlight %}

{:refdef: style="text-align: center;"}
![stackedform](/images/post/boostrap/stackedform.png){:class="img-responsive"}
{: refdef}


## **3. Inline Form trong Bootstrap 4**

Chúng ta sử dụng class form-inline để tạo các thành phần trên một dòng.
<br>
{% highlight html  linenos %}

 <form class="form-inline" action="/action_page.php">
  <label for="email">Email address:</label>
  <input type="email" class="form-control" placeholder="Enter email" id="email">
  <label for="pwd">Password:</label>
  <input type="password" class="form-control" placeholder="Enter password" id="pwd">
  <div class="form-check">
    <label class="form-check-label">
      <input class="form-check-input" type="checkbox"> Remember me
    </label>
  </div>
  <button type="submit" class="btn btn-primary">Submit</button>
</form> 

{% endhighlight %}

{:refdef: style="text-align: center;"}
![inline form](/images/post/boostrap/inline.png){:class="img-responsive"}
{: refdef}


## **4. Form Validation trong Bootstrap 4**

Chúng ta có thể thêm điều kiện để kiểm tra nếu người dùng không nhập vào ô username hoặc password thì mình sẽ thông báo lỗi. Để form có thể thông báo được lỗi thì chúng ta kết hợp thêm javascript (trong trường hợp này là Jquery) để hiển thị thông báo.

<br>
{% highlight html  linenos %}

 <form action="/action_page.php" class="needs-validation" novalidate>
  <div class="form-group">
    <label for="uname">Username:</label>
    <input type="text" class="form-control" id="uname" placeholder="Enter username" name="uname" required>
    <div class="valid-feedback">Valid.</div>
    <div class="invalid-feedback">Please fill out this field.</div>
  </div>
  <div class="form-group">
    <label for="pwd">Password:</label>
    <input type="password" class="form-control" id="pwd" placeholder="Enter password" name="pswd" required>
    <div class="valid-feedback">Valid.</div>
    <div class="invalid-feedback">Please fill out this field.</div>
  </div>
  <div class="form-group form-check">
    <label class="form-check-label">
      <input class="form-check-input" type="checkbox" name="remember" required> I agree on blabla.
      <div class="valid-feedback">Valid.</div>
      <div class="invalid-feedback">Check this checkbox to continue.</div>
    </label>
  </div>
  <button type="submit" class="btn btn-primary">Submit</button>
</form>

<script>
// Disable form submissions if there are invalid fields
(function() {
  'use strict';
  window.addEventListener('load', function() {
    // Get the forms we want to add validation styles to
    var forms = document.getElementsByClassName('needs-validation');
    // Loop over them and prevent submission
    var validation = Array.prototype.filter.call(forms, function(form) {
      form.addEventListener('submit', function(event) {
        if (form.checkValidity() === false) {
          event.preventDefault();
          event.stopPropagation();
        }
        form.classList.add('was-validated');
      }, false);
    });
  }, false);
})();
</script> 


{% endhighlight %}



{:refdef: style="text-align: center;"}
![validation form](/images/post/boostrap/validationform.png){:class="img-responsive"}
{: refdef}
