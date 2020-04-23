---
layout: blog
title: Tìm hiểu Generic trong Java 
category: blog
tags: [java core]
summery: Generic là gì 
image: /images/blog/java.png
description : Generic là gì trong lập trình .
youtubeId: 2ADRQUlsRtI
---

Chào bạn, bạn đã từng nghe tới khái niệm về Generic chưa ? Nếu bạn nghe rồi nhưng vẫn không hình dung được 
Generic là gì ? Các ký hiệu được sử dụng trong Generic. Cách tạo một Generic Class và Generic method như thế nào ? Và ưu điểm và nhược 
điểm của Generic thì bài hôm nay anh sẽ giúp mọi người nắm rõ các câu hỏi ở trên.
<br><br>

### Generic là gì ?
Generic có nghĩa là ta viết các phương thức và lớp để tái sử dụng cho các đối tượng thuộc các kiểu dữ liệu khác nhau (Kiểu dữ liệu như Person , Car , Student, Hotel vv).
Nghe có vẻ khó hiểu nên anh sẽ trình bày ví dụ sau đây. 

Ví dụ a muốn viết một chương trình quản lý danh sách  học sinh và giáo viên tại trường đào tạo 
công nghệ thông tin Ada. Anh sẽ sử dụng List để a lưu lại danh sách của học sinh và giáo viên như sau.

- Danh sách học sinh 

{% highlight java  %}
List<Student> students = new ArrayList<Student>();
{% endhighlight %}

- Danh sách giáo viên 

{% highlight java  %}
List<Teacher> teachers = new ArrayList<Teacher>();
{% endhighlight %}

Oh, có một điều đặc biệt tại sao List lúc thì chứa đối tượng sinh viên , lúc thì chứa đối tượng là giáo viên. Điều này có kỳ lạ không ?
Bởi vì List được cài đặt theo cách generic nên ta có thể tái sử dụng lại được các kiểu dữ liệu khác nhau  (lúc thì chứa sinh viên , lúc thì chứa giáo viên). Sinh viên và giáo viên
là 2 kiểu dữ liệu khác nhau. Do vậy tuỳ vào ngữ cảnh ta truyền vào cho List thì nó có là danh sách sinh viên (List \<Student \>) hay nó có thể là danh sách giáo viên  (List \< \>). 
Nói cách khác Generic thì ta định nghĩa một kiểu dữ liệu chung chung , và tuỳ vào ngữ cảnh ta truyền vào (Student hay Teacher) thì ta sẽ có tập hợp tương ứng. 
<br>

### Cách tạo Generic Class và Generic method

1. **Cách tạo Generic Class**
Ví dụ ta tạo  Generic Class tên là  Box . Mọi người chú ý để tạo 1 class là generic ta thêm \< T \> vào sau class. \<T\> là ký hiệu của Generic , ta sẽ tìm hiểu ở phần tiếp theo.

   {% highlight java linenos %}
   public class Box<T> {
      private T t;
   
      public void add(T t) {
         this.t = t;
      }
   
      public T get() {
         return t;
      }
   
      public static void main(String[] args) {
         Box<Integer> integerBox = new Box<Integer>();
         Box<String> stringBox = new Box<String>();
       
         integerBox.add(new Integer(10));
         stringBox.add(new String("Hello World"));
   
         System.out.printf("Integer Value :%d\n\n", integerBox.get());
         System.out.printf("String Value :%s\n", stringBox.get());
      }
   }
   {% endhighlight %}
  ** Kết quả nhận được sẽ là. ** <br>
   Integer Value :10 <br>
   String Value :Hello World <br>
   
   Như vậy ví dụ trên ta tạo một class Box là generic có 2 phương thức là add và get .Khi ta sử dụng Generic Box trong hàm main ( 58,59)  . Tuỳ vào ngữ cảnh mà Generic Box  có thể chứa kiểu đối tượng Integer (Box<Integer> ) hay nó
   chứa kiểu dữ liệu là String (Box\<String\>) . Dù kiểu dữ liệu Integer hay String ta đều sử dụng được phương thức get và set đã được định nghỉa trong lớp Generic Box. Như vậy mình thấy
   sử dụng Generic mình đỡ phải viết code nhiều. Mình có thể tái sử dụng code cho các đối tượng khác nhau. 
<br>

2. **Cách tạo Generic method**

   Ví dụ ta viết một phương thức in tất cả các phần tử là generic. Mọi người chú ý tham số truyền vào trong phương thức là chữ \<E\> đó là tham khi ta muốn viết một hàm generic.
   Tuỳ vào tham số truyền vào là kiểu dữ liệu gì . Ta cũng in được các phần tử con trong tập hợp đó
   Ví dụ ta viết phương thức printArray sau truyền vào tham số là một kiểu generic. Ký tự \<E\> ta sẽ bàn trong phần tiếp. 

   {% highlight java linenos %}
   public class GenericMethodTest {
      // generic method printArray
      public static < E > void printArray( E[] inputArray ) {
         // Display array elements
         for(E element : inputArray) {
            System.out.printf("%s ", element);
         }
         System.out.println();
      }
   
      public static void main(String args[]) {
         // Create arrays of Integer, Double and Character
         Integer[] intArray = { 1, 2, 3, 4, 5 };
         Double[] doubleArray = { 1.1, 2.2, 3.3, 4.4 };
         Character[] charArray = { 'H', 'E', 'L', 'L', 'O' };
   
         System.out.println("Array integerArray contains:");
         printArray(intArray);   // pass an Integer array
   
         System.out.println("\nArray doubleArray contains:");
         printArray(doubleArray);   // pass a Double array
   
         System.out.println("\nArray characterArray contains:");
         printArray(charArray);   // pass a Character array
      }
   }
   {% endhighlight %}
 **Kết quả nhận được sẽ là.** <br>
   Array integerArray contains:
   1 2 3 4 5 
   
   Array doubleArray contains:
   1.1 2.2 3.3 4.4 
   
   Array characterArray contains:
   H E L L O
   
Như vậy ở ví dụ trên ta tạo ra một phương thức in ra màn hình là generic . Tuỳ thuộc vào đối số truyền vào là Integer , String, hay Double thì phương thức in đều in ra được các phần tử
Nếu ta truyền  đối số là Integer thì sẽ nhận được kết quả là các số nguyên trong tập hợp được in ra  . Nếu ta truyền đối số là  Double thì ta sẽ nhận được các số thực được in ra . Như vậy ta chỉ viết code 1 lần và sử dụng được cho tất
cả các đối số là những kiểu dữ liệu khác nhau.
<br>

### Các ký tự trong Generic

Như ta thấy ở các ví dụ trên ta dùng các ký tự đặt biệt như \<T\> hay \<E\> để đặt tên các kiểu dữ liệu và  tham số . Ta có thể dùng các từ khác cũng được như X,Y,Z . Nhưng do  \<T\> hay \<E\> 
là các qui ước chung cho các lập trình viên đọc cho dể hiểu, dể bảo trì nên ta không nên đặt các từ khác gây nhầm lẫn. Chúng ta có các qui ước sau.
+ E- Element (phần tử – được sử dụng phổ biến trong Collection Framework).
+ K – Key (khóa).
+ V – Value (giá trị).
+ N – Number (kiểu số: Integer, Double, Float, …).
+ T – Type (Kiểu dữ liệu bất kỳ thuộc Wrapper class: String, Integer, Long, Float, …).
<br>

### Generic với các ký tự đại diện

Trong Generic nhiều lúc chúng ta sẽ gặp các ký tự đại diên như : (?),(wildcard), nó đại diện cho một loại dữ liệu  không rõ ràng.
Ví dụ của tham số đại diện (wildcard parameterized).

+ Collection<?> 
+ List<? extends Number>
+ Comparator<? super String>
+ Pair<String,?>.

1. Ký tự đại diện <?> chấp nhận tất cả các loại đối số (chứa mọi kiểu đối tượng). 
Ví dụ: Collection<?> mô tả một tập hợp chấp nhận tất cả các loại đối số kiểu String, Integer, Boolean, …
2. Ký tự đại diện <? extends type>: chấp nhận bất ký đối tượng nào miễn là đối tượng này kế thừa từ type hoặc đối tượng của type. 
Ví dụ: List<? extends Number> mô tả một danh sách, nơi mà các phần tử là kiểu Number hoặc kiểu con của Number.
3. Ký tự đại diện <? super type> chấp nhận bất ký đối tượng nào miễn là đối tượng này là cha của type hoặc đối tượng của type. 
Ví dụ: Comparator<? super String> Mô tả một bộ so sánh (Comparator) mà thông số phải là String hoặc cha của String.
<br>

### Generic trong abstract và inteface
Trong lập trình chúng ta thường sử dụng nhiều generic trong Abstract và Interface để code trở nên gọn hơn tái sử dụng được  nhiều lần.

1. Generic trong Abstract được khai báo như sau 

{% highlight java linenos %}
abstract class Animal<T> {
   
protected abstract <T> getAnimalName();
}
{% endhighlight %}

2. Generic trong Interface được khai báo như sau 

{% highlight java linenos %}
public interface GenericDao<T> {
 
    void insert(T obj);
 
    void update(T obj);
 
}
{% endhighlight %}
<br>

### Lợi ích khi dùng generic
1. Kiểu dữ liệu an toàn: Chúng ta chỉ có thể giữ được một loại đối tượng trong Generics. Nó không cho phép lưu trữ các loại đối tượng khác.
2. Kiểm tra dữ liệu chặt chẽ ở Compile-time mà không phải là Runtime-error. Nên chúng ta sẽ dễ dàng kiểm soát lỗi hơn.
3. Hạn chế việc ép kiểu (cast) thủ công mà không an toàn.
4. Giúp chúng ta viết các thuật toán được sử dụng nhiều (reusable), dễ dàng thay đổi, an toàn dữ liệu và dễ đọc hơn. 
Nó rất hữu ích cho những người viết software libraries (thư viện phần mềm) làm sao để generic programming (lập trình có tính tổng quát) vì nó cho phép người dùng sử dụng ở nhiều tình huống khác nhau.
<br>

### Nhược điểm 
1. Không thể gọi Generics bằng kiểu dữ liệu nguyên thủy (Primitive type: int, long, double, …), thay vào đó sử dụng các kiểu dữ liệu Object. 
2. Không thể tạo instances của kiểu dữ liệu Generics.
3. Không thể sử dụng static cho Generics.
<br>

### Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé . 

<p align="center">
{% include youtubePlayer.html id=page.youtubeId %}
<p>