---
layout: blog
title: Sử dụng Validation Trong  Spring
category: blog
tags: [spring]
summery: Sử dụng Validation Trong  Spring
image: /images/blog/spring.png
description : Validation trong Spring 
youtubeId: ljyqbIo4jbk
---

Chào các bạn, hôm nay anh sẽ trình bày kỷ thuật để kiểm tra dữ liệu người dùng nhập vào có đúng như định dạng mình mong muốn không ? Nếu
không đúng định dạng mình sẽ thông báo lỗi cho người dùng? Trong Spring thì mình dùng các cách nào để kiểm tra dữ liệu người dùng truyền
lên là hợp lệ.
<br><br>

### Bước 1 Thiết  ràng buộc dữ liệu trong Entiry

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
<br>

### Bước 2 sử dụng trong controller
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

Như ta thấy trong đoạn code trên ta sử dụng @Valid để kiểm tra dữ liệu ngừoi dùng truyền lên có thảo mảng điều kiện ta thiết lập trong Entiry User không ?
Khi tham số trong controller có annotation @Valid nó sẽ tự động bật chế độ kiểm tra dữ liệu theo chuẩn JSR 380 cái mà cài đặt chứa năng kiểm tra 
trong thư viện Hibernate Validator để kiểm tra giá trị.
<br>

### Ngoài ra chúng ta có thể sử dụng annotation @ExceptionHandler 

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
<br>

### Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé . 
{% include youtubePlayer.html id=page.youtubeId %}