---
layout: course-jquery
title: Sử dụng Jquery Ajax
slug : su-dung-jquery-ajax
category: laptrinhweb
tags: [jquery]
summery: Ajax 
image: /images/blog/angular.png
description : Sử dụng Jquery ajax để thao tác các thành phần trên website như lấy nội dung, chỉnh sửa nội dung các phần tử trên website
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

# **Giới thiệu nội dung bài viết**

Chào các bạn,hôm nay anh sẽ hướng dẫn mọi người cách sử dụng <b>jquery ajax hoạt động</b>là như thế nào?


# **1. Ajax là gì**

Kỷ thuật Ajax được dùng trong lập trình web với mục đích là lấy dữ liệu hoặc sử lý dữ liệu từ server. Sau đó hiển thị nó lên trang web NHƯNG KHÔNG RELOAD lại trang web.

Anh lấy ví dụ như anh có một table chứa danh sách người dùng sau trên hệ thống chăm sóc khách hàng của anh.

{:refdef: style="text-align: center;"}
![position1](/images/post/jquery/ajax.png){:class="img-responsive"}
{: refdef}

Bây giờ anh muốn xoá một dòng (khách hàng) thì anh click vào dấu ba chấm bên tay phải sau đó chọn nút "Xoá khỏi tài khoản".

- Trường hợp 1 : nếu như anh không dùng AJAX thì khi hành động xoá tài khoản thành công thì trang web sẽ reload lại nguyên cả trang. Nó sẽ vẽ lại (load lại) phần header, phần footer và các menu của trang web.

- Trường hợp 2 : nếu anh sử dụng AJAX thì khi hành động xoá tài khoản thành công. Trang web sẽ không reload lại toàn bộ cả trang, mà nó chỉ vẽ lại chỗ table với 1 dòng bị xoá đi. Như vậy nó chỉ ảnh hưởng một phần chỗ table được vẽ lại thôi còn nguyên trang web vẫn không thay đổi

Như vậy các em có thể thấy Ajax được sử dụng để vẽ lại giao diện cho phần mà ta muốn thay đổi chứ không reload lại toàn trang web. Như các em biết khi reload toàn trang web thì lúc này trình duyệt sẽ vẽ lại tất cả các phần tử trên web và sẽ mất rất nhiều thời gian để vẽ toàn bộ các phần tử. Dẫn đến việc là người dùng sẽ chờ đợi rất lâu mới thấy được trang web.

Nhờ có Ajax mà chúng ta có thể tăng Performance (hiệu năng) của website lên rất nhiều. Trước khi có công nghệ VueJS, Angular hay ReactJS thì Jquery Ajax được sử dụng hầu hết trong tất cả dự án web.

Ngoài việc tăng hiệu năng vì không reload lại nguyên trang web. Ajax còn hoạt động theo cơ chế bất đồng bộ có nghĩa là khi anh bấm vô nút "Xoá khỏi tài khoản" thì nó sẽ thực hiện việc gọi lên server. Trong lúc đó anh có thể tiếp tục thực hiện các nhiệm vụ hay tác vụ khác trên website mà không cần phải chờ cho việc xoá tài khoản thành công rồi anh mới được phép thực hiện các nhiệm vụ khác. 

# **2. Ajax Load**

Để lấy dữ liệu từ server trả về client thì Jquery cung cấp cho chúng ta phương thức load(). Cú pháp như sau

{% highlight javascript linenos %}

$(selector).load(URL,data,callback);

{% endhighlight %}

- selector : thành phần HTML được chọn để thực hiện thao tác load
- load(URL,data,callback) : 
+ trong đó URL chính là đường dẫn đến server (ví dụ https://server.com), 
+ data chính là dữ liệu mà ta muốn truyền lên cho server
+ callback : phương thức sẽ thực thi các dòng lệnh sau khi phương thức load hoàn thành


Anh có ví dụ dưới đây khi click vô button "Load Content" nó sẽ gọi lên server lúc này server sẽ trả về file là test.html. Giả sử anh có file test.html với nội dung như sau

{% highlight javascript linenos %}

<h1>Simple Ajax Demo</h1>
<p id="hint">This is a simple example of Ajax loading.</p>
<p><img src="sky.jpg" alt="Cloudy Sky"></p>
{% endhighlight %}


Như vậy khi anh click vào button "Load Content" trong trường hợp gọi lên server thành công thì anh sẽ hiển thị alert thành công, còn nếu thất bại thì anh hiển thị alert thất bại 

{% highlight javascript linenos %}

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>Showing Ajax Load Request Status in jQuery</title>
<script src="https://code.jquery.com/jquery-3.5.1.min.js"></script>
<script>
$(document).ready(function(){
    $("button").click(function(){
        $("#box").load("/examples/html/test.html", function(responseTxt, statusTxt, jqXHR){
            if(statusTxt == "success"){
                alert("New content loaded successfully!");
            }
            if(statusTxt == "error"){
                alert("Error: " + jqXHR.status + " " + jqXHR.statusText);
            }
        });
    });
});
</script>
</head>
<body>
    <div id="box">
        <h2>Click button to load new content inside DIV box</h2>
    </div>
    <button type="button">Load Content</button>
</body>
</html>

{% endhighlight %}

- $("button").click : mình đăng ký sự kiện click cho nút button
- load("/examples/html/test.html") : mình nhận vào đường link trên server lên server để lấy kết quả
- responseTxt : đây là kết quả trả về từ server. Trong trường hợp này là file test.html của mình. Sau khi có kết quả thì mình sẽ xử lý như thế nào là tuỳ thuộc vào bài toán của mình.
- statusTxt : status của request từ client lên server nếu server trả về thành công thì mình nhận HTTP status là 200 hoặc status text là success từ server trả về. Dựa vào dây mà mình có thể 

# **3. Ajax Get Post**

Ngoài Ajax load chúng ta có thêm 2 phương thức là GET và POST để lấy dữ liệu và cập nhật dữ liệu giữa client và server. Cái này thì các anh dùng nhiều trong lập trình web. Trong đó phương thức GET dùng để lấy dữ liệu còn POST dùng để truyền dữ liệu từ client lên server để server cập nhập thông tin.

- Cú pháp GET như sau

{% highlight javascript linenos %}

$.get(URL,callback);

{% endhighlight %}

- ULR : là đường link của server
- callback : phương thức sẽ xử lý sau khi server trả về kết quả


- Ví dụ khi anh click vào button "send and HTTP GET" lúc này mình sẽ gửi 1 yêu cầu lên server để server trả về dữ liệu mà mình yêu cầu.

{% highlight javascript linenos %}

<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
  $("button").click(function(){
    $.get("demo_test.asp", function(data, status){
      alert("Data: " + data + "\nStatus: " + status);
    });
  });
});
</script>
</head>
<body>

<button>Send an HTTP GET request to a page and get the result back</button>

</body>
</html>
{% endhighlight %}

- $.get : mình khai báo jquery get
- demo_test.asp : đường link của server. Nó có thể là https://levunguyen/update hay bất kỳ một đường dẫn nào của server.
- data : dữ liệu trả về từ server
- status : tình trạng server trả về thành công hoặc có lỗi.

Nếu như chúng ta muốn truyền dữ liệu lên cho server và nhận kết quả từ server trả về thì dùng phương thức POST

- Cú pháp POST như sau

{% highlight javascript linenos %}

$.post(URL,data,callback);

{% endhighlight %}

- URL : là đường link của server
- data : các tham số ta muốn gửi theo request cho server
- callback : phương thức sẽ xử lý khi server trả về kết quả

{% highlight javascript linenos %}

$("button").click(function(){
  $.post("demo_test_post.asp",
  {
    name: "le vu nguyen",
    city: "da nang"
  },
  function(data, status){
    alert("Data: " + data + "\nStatus: " + status);
  });
});

{% endhighlight %}

- Chúng ta sử dụng $.post để thực hiện method post
- demo_test_post.asp : đường link của server
- name: "le vu nguyen", city: "da nang" là 2 tham số mà ta gửi lên server
- function(data,status) : trong đó data là cái mình nhận được từ server và status là thông báo server xử lý thành công hay thất bại.

# **4. Sử dụng phương thức ajax**

Trong tất cả dự án anh làm thì anh thường dùng Jquery Ajax dưới đây để code

{% highlight javascript linenos %}

var search = {}
search["username"] = $("#username").val(); // lấy dữ liệu trong ô username và truyền lên cho server

$.ajax({
        type: "POST",
        contentType: "application/json",
        url: "/api/search",
        data: JSON.stringify(search),
        dataType: 'json',
        cache: false,
        timeout: 600000,
        success: function (data) {

            var json = "<h4>Ajax Response</h4><pre>"
                + JSON.stringify(data, null, 4) + "</pre>";
            $('#feedback').html(json);

            console.log("SUCCESS : ", data);
            $("#btn-search").prop("disabled", false);

        },
        error: function (e) {

            var json = "<h4>Ajax Response</h4><pre>"
                + e.responseText + "</pre>";
            $('#feedback').html(json);

            console.log("ERROR : ", e);
            $("#btn-search").prop("disabled", false);

        }
    });

{% endhighlight %}

- Bước 1.  khai báo sử dụng jquery ajax

{% highlight javascript linenos %}
 $.ajax
{% endhighlight %}

- Bước 2 : khai báo kiểu yêu cầu là POST hoặc GET và tham số truyền vào cho request

+ type: "POST" : khai báo phương thức là POST hoặc GET
+ url: "/api/search" : đường link của server
+ data: JSON.stringify(search) : dùng thư viện JSON để chuyển đổi dữ liệu thành định dạng JSON và truyền lên cho server
+ dataType: 'json' : kiểu định dạnh dữ liệu cho server

- Bước 3 : khi server xử lý thành công

+ success: function (data) : khi server xử lý thành công thì kết quả sẽ được lưu trong biến data. Sau đó chúng ta sẽ sử lý data bằng việc dùng Jquery tìm các phần tử cần thay đổi sau đó gán dữ liệu vào  $('#feedback').html(json). Các em thấy chúng ta chỉ thay đổi 1 phần trên website chứ không reload nguyên cả trang như anh nói ở phần mở bài. Chính vì vậy mà hiệu suất website rất nhanh. Các em có thay đổi gì thì thay đổi và xử lý web trong method success này.

- Bước 4 : khi server xử lý thất bại

Chúng ta sử dụng method  error: function (e) để xử lý trường hợp server không trả về được kết quả như mình mong muốn


# **5. Kết luận**

Hầu như các dự án web sau này anh làm đều không dùng JQuery Ajax nữa mà đã sử dụng các công nghệ làm web mới như ReacJS, VueJS hoặc Angular. Từ năm 2009 về trước thì các dự án anh làm đều dùng Jquery Ajax 




