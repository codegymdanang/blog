---
layout: blog
title: Model, ModelMap, and ModelView  
slug : su-dung-model-modelmap-modelview-trong-spring
category: laptrinhspring
tags: [spring]
summery: Model, ModelMap, and ModelView
image: /images/blog/spring.png
description : Các Model trong Spring 
youtubeId: vaQxJlfmB6s
---

Chào bạn, trong bài viết hôm nay anh sẽ giới thiệu cho các bạn phân biệt Model , ModelMap , Map và ModeAndView.
<br><br>

### Model là gì ?
Chúng ta sử dụng Interface Model để truyền dữ liệu  từ Controller sang View để hiển thị . 
Spring cho phép chúng ta sử dụng Model như là một tham số trong method của Controller nên chúng ta dể dàng lấy , chỉnh sử data 
để truyền qua cho View.

{% highlight java linenos %}

@Controller
public class GreetingController {

    @RequestMapping(path = "/getWithModel", method = RequestMethod.GET)
    public String getWithModel(@RequestParam("name") String name, Model model) {
        Greeting greeting = new Greeting(name);
        model.addAttribute("greeting", greeting);

        return "greet";
    }
}
{% endhighlight %}

Ở tầng view chúng ta có thể lấy data truyền từ model như sau 

{% highlight html  linenos %}
<!DOCTYPE html>
<html>
    <body>
        Hello <span th:text="${greeting.name}"/>!
    </body>
</html>
{% endhighlight %}
<br>

### ModelMap là gì ?
ModelMap cũng tương tư như Model. Chúng ta có thể sử dụng ModelMap như một tham số trong method của Controller.

{% highlight java  linenos %}
@RequestMapping(path = "/getWithModelMap", method = RequestMethod.GET)
public String getWithModelMap(@RequestParam("name") String name, ModelMap modelMap) {
    Greeting greeting = new Greeting(name);
    modelMap.addAttribute("greeting", greeting);
    return "greet";
}

{% endhighlight %}
<br>

### Map
Map cũng tương tự như Model . Chúng ta có thể sử dụng Map như một tham số trong method của Controller.

{% highlight java  linenos %} 
@RequestMapping(path = "/getWithMap", method = RequestMethod.GET)
public String getWithMap(@RequestParam("name") String name, Map<String, Object> model) {
    Greeting greeting = new Greeting(name);
    model.put("greeting", greeting);
    return "greet";

} 
{% endhighlight %}
<br>

### ModelAndView
Là sự kết hợp của 2 khía cạnh truyền dữ liệu và view. Như ta thấy ở ví dụ trên ta dùng 2 dòng code.
1. model.put("greeting", greeting); gán dữ liệu greeting cho biến greeting.
2. return "greet" ; trả về trang view là greet.html.
Chúng ta sử  ModelAndView("greet", modelMap) để thực hiện việc , trả về trang greet.html và mode 1 lần . 

{% highlight java  linenos %} 
@RequestMapping(path = "/get", method = RequestMethod.GET)
public ModelAndView get(@RequestParam("name") String name) {
    Map<String, Object> modelMap = new HashMap<>();
    Greeting greeting = new Greeting(name);
    modelMap.put("greeting", greeting);
    
    return new ModelAndView("greet", modelMap);
{% endhighlight %}
<br>

### Sự khác nhau giữa các model 

1. Model là một interface trong khi đó ModelMap là một Class. 
2. Model là một  interface nó chứa đựng 4 phương thức addAttribute và một phương thức  merAttribute .
3. ModelMap cài đặt lớp  Map interface. Nên nó thêm các phương thức của Map. 
4. ModelAndView là sự kết hợp của 2 mục đích  ModelMap and View . Nó cho phép controller trả về 1 giá trị bao gồm Model và View .  
<br>

### Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé .

{% include youtubePlayer.html id=page.youtubeId %}