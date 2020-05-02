---
layout: blog
title: Generation Identifier
slug : generation-identifier
category: laptrinhspring
tags: [spring]
summery: Lập Trình Spring Security
image: /images/blog/spring.png
description : Spring Security .học lập trình  ngôn ngữ lập trình lập trình java java cơ bản khóa học lập trình java học ngôn ngữ lập trình java
youtubeId: WNfuVJptPnQ
---

### **1. Giới thiệu nội dung bài viết**

Chào các em ,như các em thấy trong các Entity mình annotation @GeneratedValue và nó có các strategy như GenerationType.IDENTITY,sequence-generator. Vậy nó là cái gì thì chủ đề hôm nay chúng ta sẽ nói về các loại Generation trong Hibernate

- Auto Generation ?
- Identity Generation ?
- Sequence Generation ?
- Table  Generation ?
- Cấu hình và triển khai một dự án dùng các annotation


### **2. Auto Generation**

Nếu ta không khai báo strategy thì mình sẽ sử dụng default generation để sinh ra giá trị cho khoá chính. Thì trường khoá chính sẽ có giá trị là số hoặc UUID

Nếu khoá chính là kiểu interger thì Persisten sẽ tự động sinh giá trị cho khoá chính  dựa trên cơ chế  sequence number

Nếu khoá chính là kiểu UUID thì giá trị của khoá chính nó sẽ được sinh theo thuật toán UUID Generation

Ví dụ sau đây ta khai báo khoá chính là kiểu số. Và nó là duy nhất trong table .


{% highlight java  linenos %}
@Entity
public class Student {

    @Id
    @GeneratedValue
    private long studentId;

    // ...
}
{% endhighlight %}

Ví dụ sau đây ta khai báo khoá chính là kiểu . Thì studentId sẽ tự động tăng dần lên và nó là duy nhất trong table.
Lúc đó giá trị của nó là 8dd5f315-9788-4d00-87bb-10eed9eff566. Đây là giá do UUID Generation sinh ra

{% highlight java  linenos %}
@Entity
public class Course {

    @Id
    @GeneratedValue
    private UUID courseId;

    // ...
}
{% endhighlight %}

### **3. IDENTITY Generation**

Khi sử dụng strategy Identity có nghĩa khoá chính sẽ tự động tăng lên

{% highlight java  linenos %}
@Entity
public class Student {

    @Id
    @GeneratedValue (strategy = GenerationType.IDENTITY)
    private long studentId;

    // ...
}
{% endhighlight %}

Lúc này giá trị cửa studentId sẽ là 1,2,3,4,5 ...

### **4. SEQUENCE Generation**

Chúng ta sử dụng sequen-generator để có cấu hình cách tạo ra các giá trị cho khoá chính.
Như ta thấy ở ví dụ Identify Generation. Thì thứ tự bắt đầu là 1 , sau đó tăng lên 2,3,4.
Khi xử dụng sequen-generator ta hoàn toàn có thể thay đổi lại . Như ví dụ bên dưới, ta yêu cầu
giá trị ban đầu là 4 (@Parameter(name = "initial_value", value = "4"). Và ta muốn mỗi lần tăng là 2 đơn vị
@Parameter(name = "increment_size", value = "2"). Như vậy giá trị của userId sẽ là : 4,6,8,10

{% highlight java  linenos %}
@Entity
public class User {
    @Id
    @GeneratedValue(generator = "sequence-generator")
    @GenericGenerator(
      name = "sequence-generator",
      strategy = "org.hibernate.id.enhanced.SequenceStyleGenerator",
      parameters = {
        @Parameter(name = "sequence_name", value = "user_sequence"),
        @Parameter(name = "initial_value", value = "4"),
        @Parameter(name = "increment_size", value = "2")
        }
    )
    private long userId;

    // ...
}
{% endhighlight %}

### **4. Table Generation**

### **5. Tự tạo Generation cho chúng ta**

Chúng ta có thể hoàn toàn tự tạo một Generator theo ý của mình bằng cách implements IdentifierGenerator. Ví dụ như
ta có thể tạo ra một identifier chứ biểu mẫu chính quy gồm cả String và số . Ta sẽ override lại method generate

{% highlight java  linenos %}
public class MyGenerator
  implements IdentifierGenerator, Configurable {

    private String prefix;

    @Override
    public Serializable generate(
      SharedSessionContractImplementor session, Object obj)
      throws HibernateException {

        String query = String.format("select %s from %s",
            session.getEntityPersister(obj.getClass().getName(), obj)
              .getIdentifierPropertyName(),
            obj.getClass().getSimpleName());

        Stream ids = session.createQuery(query).stream();

        Long max = ids.map(o -> o.replace(prefix + "-", ""))
          .mapToLong(Long::parseLong)
          .max()
          .orElse(0L);

        return prefix + "-" + (max + 1);
    }

    @Override
    public void configure(Type type, Properties properties,
      ServiceRegistry serviceRegistry) throws MappingException {
        prefix = properties.getProperty("prefix");
    }
}
{% endhighlight %}

Chúng ta sử dụng như sau

{% highlight java  linenos %}
@Entity
public class Product {

    @Id
    @GeneratedValue(generator = "prod-generator")
    @GenericGenerator(name = "prod-generator",
      parameters = @Parameter(name = "prefix", value = "prod"),
      strategy = "codegym.levunguyen.MyGenerator")
    private String prodId;

    // ...
}
{% endhighlight %}

### **6. Kết luận**

Chúng ta có 4 loại generator chúng trả về kết quả gần như nhau nhưng khác nhau ở cơ chế thực hiện  của database  
