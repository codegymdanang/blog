---
layout: course-spring-web
title: Sử dụng Generation Identifier trong lập trình Spring
slug : su-dung-generation-identifier-trong-spring
category: laptrinhspring
tags: [spring-web]
summery: Generation Identifier
image: /images/blog/spring.png

description : Hiểu nguyên lý của Auto generation, identity generation, sequence generation và table generation trong lập trình Spring. Hướng dẫn cách cấu hình các generation trong dự án spring.
youtubeId: ewuf9UN9aFY
youtubeId1: oZ6BhOTOjoU
---

{% include toc.html %}

# **Giới thiệu nội dung bài viết**

Chào các em, như các em thấy trong các Entity mình annotation <b>@GeneratedValue</b> và nó có các strategy(dịch nôm na là các cách để tạo ra giá trị cho khóa chính) như GenerationType.IDENTITY,sequence-generator. Vậy Generation Identifier trong lập trình Spring là gì, chủ đề hôm nay chúng ta sẽ làm rõ hơn về các loại Generation trong <b>Hibernate</b>.

<br>
# **1. Auto Generation**

Nếu ta không khai báo strategy thì mình sẽ sử dụng default generation để sinh ra giá trị cho khóa chính. Thì trường khóa chính sẽ có giá trị là số (như là 1,2,3,4,5,6) hoặc UUID (dãy số và chữ kết hợp với nhau 8dd5f315-9788-4d00-87bb-10eed9eff566)

Nếu khóa chính là kiểu số thì Persisten sẽ tự động sinh giá trị cho khóa chính dựa trên cơ chế  sequence number. Sequence number có nghĩa là giá trị sẽ tăng lên 1,2,3,4,5,6,7,8 ... 

Nếu khóa chính là kiểu UUID thì giá trị của khóa chính nó sẽ được sinh theo thuật toán UUID Generation

Ví dụ sau đây ta khai báo khóa chính là kiểu số. Và nó là duy nhất trong table .

{% highlight java  linenos %}
@Entity
public class Student {

    @Id
    @GeneratedValue
    private long studentId;

    // ...
}
{% endhighlight %}

Chúng ta sử dụng annotation <b>@GeneratedValue</b> để khai báo cách sinh ra giá trị.

Ví dụ sau đây ta khai báo khóa chính là kiểu số. Thì giá trị của trường studentId sẽ tự động tăng dần lên và nó là duy nhất trong table.

Nếu khóa chính kiểu UUID ví dụ như UUID sau : 8dd5f315-9788-4d00-87bb-10eed9eff566. Giá trị này do thuật toán có trong UUID Generation sinh ra và là duy nhất.

{% highlight java  linenos %}
@Entity
public class Course {

    @Id
    @GeneratedValue
    private UUID courseId;

    // ...
}
{% endhighlight %}

<br>
# **2. IDENTITY Generation**

Khi sử dụng <b>strategy Identity</b> có nghĩa khóa chính sẽ tự động tăng lên cấp tiến như 1,2,3,4

{% highlight java  linenos %}
@Entity
public class Student {

    @Id
    @GeneratedValue (strategy = GenerationType.IDENTITY)
    private long studentId;

    // ...
}
{% endhighlight %}

Chúng ta sử dụng annotation <b>@GeneratedValue (strategy = GenerationType.IDENTITY)</b> để khai báo cách sinh ra giá trị.

Lúc này giá trị cửa studentId sẽ là 1,2,3,4,5 ...

<br>
# **3. SEQUENCE Generation**

Chúng ta sử dụng <b>sequence-generator</b> để có cấu hình cách tạo ra các giá trị cho khóa chính.
Như ta thấy ở ví dụ Identify Generation. Thì thứ tự bắt đầu là 1 , sau đó tăng lên 2,3,4.
Khi sử dụng sequence-generator ta hoàn toàn có thể thay đổi lại bước nhảy . Như ví dụ bên dưới, ta yêu cầu
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

- Chúng ta sử dụng annotation <b>@GeneratedValue(generator = "sequence-generator")</b> để sinh ra giá trị

- sequence_name  : tên sequence
- initial_value  : giá trị ban đầu
- increment_size : bước nhảy
<br>
# **4. Table Generation**

<b>Table Generation Strategy</b> cũng gần tương tự như sequence strategy. Nhưng trong phương pháp này ta sử dụng table để hỗ trợ việc tạo ra các giá trị cho trường khóa chính. Anh có ví dụ sau

{% highlight java  linenos %}
@Entity
@TableGenerator(name="person", initialValue=0, allocationSize=50)
public class Persion {

  @GeneratedValue(strategy=GenerationType.Table, generator="person")
  @Id
  Long id;
}
{% endhighlight %}

- Trong ví dụ trên ta khai báo annotation @TableGenerator để khai báo strategy dùng là Generator Table
- initialValue=0 Giá trị ban đầu được gán, trong trường hợp này id sẽ bằng 0.
- allocationSize Giá trị sequence sẽ được sinh ra dựa trên khai báo allocationSize. Mặc định giá trị này là 50. Thì giá trị tăng 50 lần sau mỗi lần gọi. Nếu mình set là allocationSize = 1 thì nó sẽ tự động tăng dần đều.

Sự khác nhau giữa SEQUENCE và Table Generator là giá trị initialValue. Nếu là SEQUENCE nó sẽ lưu giá trị tiếp theo của dãy số vào table. Còn Table Generator sẽ lưu trữ giá trị cuối cùng đã được sử dụng vào table


<br>
# **5. Tự tạo Generation cho chúng ta**

Chúng ta có thể hoàn toàn tự tạo một Generator theo ý của mình bằng cách implements <b>IdentifierGenerator</b>. Ví dụ như
ta có thể tạo ra một identifier chứ biểu mẫu chính quy gồm cả String và số. Ta sẽ override lại method generate

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

<br>
# **6. Kết luận**

Chúng ta có 4 loại generator chúng trả về kết quả gần như nhau nhưng khác nhau ở cơ chế thực hiện của database  

# **7. Demo Part 1**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}

# **8. Demo Part 2**

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId1 %}
{: refdef}
