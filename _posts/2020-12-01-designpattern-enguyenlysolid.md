---
layout: course-design-pattern
title: Nguyên lý SOLID trong lập trình Java
slug: nguyen-ly-solid-trong-lap-trinh-java
category: craftmanship
tags: [designpattern]
summery: Nguyên lý SOLID
image: /images/blog/design-patterns.png
description : Hiểu Nguyên lý SOLID là gì ? vì sao sử dụng Nguyên lý SOLID. Hướng dẫn sử dụng Nguyên lý SOLID trong học lập trình java.
---

{% include toc.html %}

# **Giới thiệu nội dung bài viết**
Chào các e, chủ đề hôm nay của anh sẽ bàn về chủ đề  <b>Nguyên lý SOLID</b> trong lập trình

<br>
# **1- Nguyên lý SOLID ?**

Nguyên lý SOLID được đưa vào lập trình bắt đầu từ ý tưởng của Uncle Bob (một expert về lập trình và là thần tượng của anh). Khi sử dụng nguyên lý SOLID vào lập trình nó giúp mình trở thành một lập trình viên tốt hơn. Đương nhiên muốn trở thành lập trình viên giỏi thì cần nhiều thứ, nhiều yếu tốt. Tuân thủ cách thiết kế và viết code theo nguyên lý SOLID cũng là một nguyên nhân giúp mình trở nên giỏi hơn.

Trong thực tế anh và một số lập trình viên khi làm dự án thỉnh thoảng cũng quên không áp dụng SOLID khi tạo một class hay thiết kế một module dự án do đó các anh phải trả giá rất lớn cho việc sản phẩm không tối ưu. Nhiều khi phải đập bỏ code viết lại từ đầu. Chính vì vậy mình muốn code một cái gì đó thì nên suy nghĩ, thiết kế và áp dụng SOLID trước khi viết.

SOLID đưa ra cho chúng ta 5 nguyên lý (5 phương pháp) mà chúng ta phải tuân thủ khi lập trình. Anh sẽ giải thích từng nguyên lý ở ví dụ sau

<br>
# **2- Nguyên lý Single Responsibility ?**

Nguyên lý đầu tiên là khi chúng ta tạo ra một class thì class đó chỉ có một nhiệm vụ (trách nhiệm) duy nhất hay nói các khác là làm một việc duy nhất.

Lợi ích của sử dụng nguyên lý này giúp chúng ta trong việc:

- Kiểm thử chức năng : Class chỉ có 1 nhiệm vụ nên việc test hoặc làm unit rất đơn giản chỉ cần vài testcase có thể kiểm tra được chất lượng code.

- Giảm phụ thuộc : Ít chức năng (method) trong class dẫn đến ít sự phụ thuộc.

- Tổ chức code của dự án : Các file code càng nhỏ thì dễ quản lý và tìm kiếm.

Ví dụ anh có lớp Book gồm có name, author và text.

<br>
{% highlight java  linenos %}

public class Book {
 
    private String name;
    private String author;
    private String text;
 
    //constructor, getters and setters
 
    // methods that directly relate to the book properties
    public String replaceWordInText(String word){
        return text.replaceAll(word, text);
    }
 
    public boolean isWordInText(String word){
        return text.contains(word);
    }
}

{% endhighlight %}


- Lớp Book ở trên gồm có 2 phương thức là tìm kiếm từ trong đoạn văn (replaceWordInText) và kiểm tra xem từ đó có tồn tại trong đoạn văn không (isWordInText). Bây giờ anh mong muốn ngoài việc tìm kiếm và kiểm tra thì thêm chức năng in ra màn hình. Thông thường trong lập trình anh sẽ viết thêm method in trong class Book như sau

<br>
{% highlight java  linenos %}

public class Book {
 
    private String name;
    private String author;
    private String text;
 
    //constructor, getters and setters
 
    // methods that directly relate to the book properties
    public String replaceWordInText(String word){
        return text.replaceAll(word, text);
    }
 
    public boolean isWordInText(String word){
        return text.contains(word);
    }

    void printTextToConsole(){
        // our code for formatting and printing the text
    }
}

{% endhighlight %}

Nếu anh viết code như trên kia thì chương trình vẫn chạy đúng nhưng đang vi phạm nguyên lý Single Responsibility. Vì lớp Book chỉ nên làm một nhiệm vụ và có trách nhiệm trong việc tìm kiếm và kiểm tra thôi. Do vậy chức năng in phải di chuyển ra nơi khác và tạo một class khác chuyên cho việc in.

Code sẽ được thay đổi như sau.

<br>
{% highlight java  linenos %}

public class BookPrinter {
 
    // methods for outputting text
    void printTextToConsole(String text){
        //our code for formatting and printing the text
    }
 
    void printTextToAnotherMedium(String text){
        // code for writing to any other location..
    }
}
{% endhighlight %}

Ta tạo thêm một class tên BookPrinter có nhiệm vụ là in ra màn hình. Như vậy nhiệm vụ in của class Book sẽ do lớp mới là BookPrinter đảm nhận và class BookPrinter này chỉ làm một việc duy nhất là in.

<br>
# **3- Nguyên lý Open Extension và Close for Modification?**

Nguyên lý này nói là một class thì nên thiết kế cho khả năng mở rộng và không nên thay đổi. Trong thực tế khi tạo ra một class mình phải suy nghĩ rằng class này có  khả năng mở rộng trong tương lai hay không. Anh ví dụ mình viết phương thức thanh toán online tại thời điểm mình viết thì chỉ chấp nhận ví MOMO nhưng trong tương lai có thể chấp nhận Master hoặc Visa. Chính vì vậy khi tạo ra một class thì phải có tính năng mở rộng. 

Close Modification có nghĩa là không nên nhảy vô code đang có mà sửa đổi, đều này cực kỳ nghiêm trọng vì có những lúc code cũ đang chạy ngon. Mình vào sửa vài dòng code lúc này vô tình ảnh hưởng tới các chức năng khác gây nên tình trạng lỗi. Trong lập trình các anh gặp vấn đề này rất nhiều do người đi trước viết code không theo nguyên lý SOLID dẫn đến việc các anh phải nhảy vô code đang có sửa trực tiếp.

Anh ví dụ như mình có class Guitar như sau:

<br>
{% highlight java  linenos %}

public class Guitar {
 
    private String make;
    private String model;
    private int volume;
 
    //Constructors, getters & setters
}

{% endhighlight %}

Sau một khoảng thời gian chạy anh mong muốn thêm chức năng mới cho Guitar. Lúc này anh sẽ không vào sửa trực tiếp trong lớp Guitar mà sẽ tạo ra một lớp khác kế thừa Guitar và thêm chức năng mới.

<br>
{% highlight java  linenos %}

public class SuperCoolGuitarWithFlames extends Guitar {
 
    private String flameColor;
 
    //constructor, getters + setters
}

{% endhighlight %}

Như vậy ta không thay đổi (close modification) lớp Guitar và Class Guitar mình thiết kế ban đầu cũng có khả năng mở rộng (open for extension)

<br>
# **4- Nguyên lý Liskov Substitution?**

Nguyên lý này được hiểu như sau nếu lớp A là subtype của lớp B. Thì khi chúng ta thay lớp B bằng lớp A thì chương trình vẫn chạy đúng chức năng và nhiệm vụ. Chúng ta sẽ đi qua ví dụ sau đây.

Ví dụ anh có interface là Car trong đó có 2 phương thức là khởi động động cơ xe và vào số.

<br>
{% highlight java  linenos %}

public interface Car {
 
    void turnOnEngine();
    void accelerate();
}

{% endhighlight %}

Ví dụ anh có các phương tiện MotoCar sau đây implements Interface Car và override lại 2 phương thức là khởi động động cơ và vào số như sau. 

<br>
{% highlight java  linenos %}

public class MotorCar implements Car {
 
    private Engine engine;
 
    //Constructors, getters + setters
 
    public void turnOnEngine() {
        //turn on the engine!
        engine.on();
    }
 
    public void accelerate() {
        //move forward!
        engine.powerOn(1000);
    }
}

{% endhighlight %}

Như vậy xe MotorCar đều có chức năng khởi động động cơ và vô số. Nhưng bây giờ anh muốn thay chiếc xe là xe ô tô điện (ElectricCar). Như vậy mọi người thấy ô tô điện thì đâu có phương thức khởi động động cơ và vô số.

<br>
{% highlight java  linenos %}

public class ElectricCar implements Car {
 
    public void turnOnEngine() {
        throw new AssertionError("I don't have an engine!");
    }
 
    public void accelerate() {
        //this acceleration is crazy!
    }
}


{% endhighlight %}

Như vậy là vi phạm nguyên lý Liskov Substitution vì nguyên lý này nói khi chúng ta thay chiếc xe bằng ElectricCar thì chương trình vẫn phải chạy bình thường. Nhưng trong ví dụ trên của ta khi ta thay chiếc xe bằng ElectricCar thì không hoạt động được, bằng chứng là phương thức turnOnEngine và accelerate không hoạt động được trong môi trường điện.

Để sửa lại code cho đúng nguyên lý Liskov Substitution thì có khi chúng ta phải đập hết code và sửa lại model của chương trình cho đúng

<br>
# **5- Nguyên lý Interface Segregation?**

Nguyên lý này nói chúng ta rằng nếu chúng ta có một interface có quá nhiều phương thức và quá to thì nên chia nhỏ ra thành các interface nhỏ.

Ví dụ chúng ta có interface sau là hơi to.

<br>
{% highlight java  linenos %}

public interface BearKeeper {
    void washTheBear();
    void feedTheBear();
    void petTheBear();
}

{% endhighlight %}


Chúng ta sẽ tách nó ra thành những interface nhỏ hơn như sau

<br>
{% highlight java  linenos %}

public interface BearCleaner {
    void washTheBear();
}
{% endhighlight %}

<br>
{% highlight java  linenos %}

public interface BearFeeder {
    void feedTheBear();
}
{% endhighlight %}

<br>
{% highlight java  linenos %}

public interface BearPetter {
    void petTheBear();
}
{% endhighlight %}

Nếu chúng ta muốn một Class có chức năng wash và feed thì chúng ta implement 2 interface. Trong Java một class có thể implement 1 hoặc nhiều interface

<br>
{% highlight java  linenos %}

public class BearCarer implements BearCleaner, BearFeeder {
 
    public void washTheBear() {
        //I think we missed a spot...
    }
 
    public void feedTheBear() {
        //Tuna Tuesdays...
    }
}


{% endhighlight %}


<br>
# **6- Nguyên lý Dependency Inversion**

Sử dụng nguyên lý này để giảm sự phụ thuộc giữa các module với nhau. Trong khi làm một phần mềm sẽ có hàng trăm module. Giảm đi sự phụ thuộc giữa các module sẽ giúp cho chương trình mình ít lỗi hơn và ít phức tạp hơn.

Anh có ví dụ về Class là máy tính Windows98 bao gồm có 2 đối tượng là màn hình và bàn phím như sau:

<br>
{% highlight java  linenos %}

public class Windows98Machine {
 
    private final StandardKeyboard keyboard;
    private final Monitor monitor;
 
    public Windows98Machine() {
        monitor = new Monitor();
        keyboard = new StandardKeyboard();
    }
 
}


{% endhighlight %}

ở ví dụ trên ta thấy trong constructor của Windown98 ta tạo 2 đối tượng là new Monitor và new StandardKeyBoard như vậy vô tình ta tạo ra 3 đối tượng Windows, Monitor, Keyboard dính chặt với nhau, phụ thuộc lẫn nhau. Ví dụ như anh muốn thay cái Monitor củ bằng một cái Monitor mới cũng không được vì nó đã là một phần của Windows98. Vậy có cách nào anh giảm sự phụ thuộc này không? 

Để giảm sự phụ thuộc của KeyBoard và Monitor anh sẽ tạo ra một interface riêng như sau.

<br>
{% highlight java  linenos %}

public interface Keyboard { }

{% endhighlight %}

<br>
{% highlight java  linenos %}

public class StandardKeyboard implements Keyboard { }


{% endhighlight %}

<br>
{% highlight java  linenos %}

public class Windows98Machine{
 
    private final Keyboard keyboard;
    private final Monitor monitor;
 
    public Windows98Machine(Keyboard keyboard, Monitor monitor) {
        this.keyboard = keyboard;
        this.monitor = monitor;
    }
}

{% endhighlight %}

Như vậy ta thấy rằng 3 lớp Windows, Monitor và Keyboard đã không còn phụ thuộc vào nhau. Nếu anh muốn có một Monitor khác thì anh chỉ việc kế thừa Interface Monitor là xong.


<br>
# **7- Tóm lại**

5 nguyên lý SOLID ở trên thật sự rất cần thiết khi chúng ta làm lập trình. Các lập trình viên giỏi hay không giỏi hơn thua nhau ở chỗ biết áp dụng nguyên lý SOLID vào việc coding của mình. Nếu các em muốn trở thành lập trình viên giỏi thì cũng phải nghiệm ra 5 nguyên lý trên khi bắt tay vào code. 


















