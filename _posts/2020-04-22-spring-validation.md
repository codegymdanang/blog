---
layout: blog
title: Sử dụng Validation Trong  Spring
slug : su-dung-spring-validation
category: laptrinhspring
tags: [spring]
summery: Sử dụng Validation Trong  Spring
image: /images/blog/spring.png
description : Validation trong Spring 
youtubeId: ljyqbIo4jbk
---

### **1. Giới thiệu nội dung bài viết**

Chào các bạn, hôm nay anh sẽ trình bày kỷ thuật để kiểm tra dữ liệu người dùng nhập vào có đúng như định dạng mình mong muốn không ? Nếu
không đúng định dạng mình sẽ thông báo lỗi cho người dùng? Trong Spring thì mình dùng các cách nào để kiểm tra dữ liệu người dùng truyền
lên là hợp lệ. Nội dung hôm nay sẽ trình bày là

- Tại sao ràng buộc hay kiểm tra dữ liệu
- Hướng dẫn cách thực hiện buộc ràng hay kiểm tra  dữ liệu trong Spring
- Video hướng dẫn cách làm kiểm tra dữ liệu trong Spring 

### **2. Tại sao cần kiểm tra và ràng buộc dữ liệu** 

Cái quý giá và quan trọng nhất đối với một phần mềm đó chính là dữ liệu , thông tin về dữ liệu. Như các e thấy facebook hay google họ nắm 
dữ một lượng người dùng khá lớn , dự vào nguồn dữ liệu đó họ sẽ phát triển các kế hoạch dài hạn và tăng doanh thu cho công ty . Chính vì vậy
nắm được dữ liệu sẽ là yếu tố quyết định cho sự thành công. Để đảm bảo dữ liệu phải nhập đúng định dạng ví dụ như ngày tháng năm phải theo
chuẩn la dd/MM/YYYY hoặc trường dữ liệu bắt buộc người dùng nhập vào thì ta sử dụng Spring Validation để làm việc đó . Khi người dùng nhập
sai định dạnh mình yêu cầu thì mình thông báo lỗi để người dùng nhập lại.

### **2. Hướng dẫn cách làm** 

#### Bước 1 Thiết  ràng buộc dữ liệu trong Entiry

{% highlight java linenos %}
@Entity
public class User {
     
    @Id
    @GeneratedValue(strategy = GenerationType.AUTO)
    private long id;
     
    @NotBlank(message = "Name is mandatory")
    private String name;
     
    @NotBlank(message = "Email is mandatory")
    private String email;
     
    // standard constructors / setters / getters / toString
         
}
{% endhighlight %}

Như ta thấy mình sử dụng các annotaion có sẳng như @NotBlank để ràng buộc không được phép rỗng cho giá trị name.


#### Bước 2. sử dụng trong controller

Trong ví dụ sau a sẽ sử dụng Restful Webservice .

{% highlight java linenos %}
@RestController
public class UserController {
 
    @PostMapping("/users")
    ResponseEntity<String> addUser(@Valid @RequestBody User user) {
        // persisting the user
        return ResponseEntity.ok("User is valid");
    }
     
    // standard constructors / other methods
     
}
{% endhighlight %}

Như ta thấy trong đoạn code trên ta sử dụng @Valid để kiểm tra dữ liệu người dùng truyền lên có thảo mảng điều kiện ta thiết lập trong Entiry User không ?
Khi tham số trong controller có annotation @Valid nó sẽ tự động bật chế độ kiểm tra dữ liệu theo chuẩn JSR 380 cái mà cài đặt chứa năng kiểm tra 
trong thư viện Hibernate Validator để kiểm tra giá trị.


#### Ngoài ra chúng ta có thể sử dụng annotation @ExceptionHandler 

@ExceptionHandler cho phép chúng ta bắt lỗi dữ liệu cho từng method. 

{% highlight java linenos %} 
@ResponseStatus(HttpStatus.BAD_REQUEST)
@ExceptionHandler(MethodArgumentNotValidException.class)
public Map<String, String> handleValidationExceptions(
  MethodArgumentNotValidException ex) {
    Map<String, String> errors = new HashMap<>();
    ex.getBindingResult().getAllErrors().forEach((error) -> {
        String fieldName = ((FieldError) error).getField();
        String errorMessage = error.getDefaultMessage();
        errors.put(fieldName, errorMessage);
    });
    return errors;
}
{% endhighlight %}


### Bước 3. Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé . 

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}