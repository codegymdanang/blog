---
layout: blog
title: JPA Thao Tác Database Trong Spring 
category: blog
tags: [spring]
summery: JPA Thao Tác Database Trong Spring 
image: /images/blog/spring.png
youtubeId: 4dQlWJQ7ZQo
---

Chào các e, chủ đề hôm nay của anh là về JPA ? Anh sẽ giải thích nó là gì ? Cấu hình dự án sử dụng JPA ra sao ?
Đồng thời anh sẽ giới thiệu các cách truy vấn dữ liệu trong database 
<br><br>

### ORM là gì ?
ORM là viết tắt của Object Relational Mapping, là một công nghệ/ khái niệm/ quá trình chuyển đổi dữ liệu từ ngôn ngữ hướng đối tượng sang Database quan hệ và ngược lại. Ví dụ, trong Java nó được thực hiện với sự trợ giúp của Reflection và JDBC.
ORM có khả năng xử lý các thao tác của nhiều loại cơ sở dữ liệu khác nhau một cách dễ dàng mà không quan tâm đến loại database sử dụng (SQL Server, MySQL, PostgreSQL, …) hay loại thao tác sử dụng (INSERT, UPDATE, DELETE, SELECT, …).
<br>

### JPA là gì ?

<br>

### Bước 1 -  Chuẩn bị dependency trong file pom.xml 

{% highlight xml linenos %}
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-data-jpa</artifactId>
        </dependency>
        
         <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <scope>runtime</scope>
         </dependency>

{% endhighlight %}
<br>

### Bước 2 - Cấu hình connection kết nối database trong file application.properties

spring.datasource.driver-class-name=com.mysql.jdbc.Driver
spring.datasource.url=jdbc:mysql://localhost:3306/company
spring.datasource.username=root
spring.datasource.password=Nguy!n12345
<br>

### Bước 3 - Chuẩn bị entiry . Mapping xuóng table Department trong dâtbas e

{% highlight xml linenos %}
@Data
@Entity
@Table(name = "department")
@NamedQuery( name="findAllCustomersWithName",
        query="SELECT c FROM Customer c WHERE c.name LIKE :custName" )
public class Department implements Serializable {

    @Column(name = "id")
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    @Id
    public int id;

    @Column(name = "name")
    public String name;

    @Column(name = "description")
    public String description;


}

{% endhighlight %}
<br>

### Bước 4 - Chuẩn bị Controller để mapping request từ client

{% highlight xml linenos %}
@Controller
public class CreationQueryController {


    @Autowired
    DepartmentQueryCreationService departmentQueryCreationService;

    @GetMapping("/creationFindbyDepartmentName/{name}")
    public ModelAndView findbyDepartment(@PathVariable("name") String name) {
        ModelAndView modelAndView = new ModelAndView("creation");
        List<Department> departments = departmentQueryCreationService.findByDepartment(name);
        modelAndView.addObject("departments",departments);
        return modelAndView;

    }
}
{% endhighlight %}
<br>

### Bước 5 - Tạo file DepartmentQueryCreationService

{% highlight xml linenos %}
@Service
public class DepartmentQueryCreationService {

    @Autowired
    DepartmentQueryCreationRepository departmentQueryCreationRepository;

    public List<Department> findByDepartment(String name) {
        return departmentQueryCreationRepository.findByName(name);
    }
}
{% endhighlight %}
<br>

### Bước 6 - Tạo file DepartmentAnnotationRepository sử dụng JPA 

{% highlight xml linenos %} 
@Transactional
public interface DepartmentAnnotationRepository extends JpaRepository<Department,Integer> {

    @Query("select department from Department department where department.name = ?1")
    Department findByName(String departmentName);

    @Query("select department from Department department where department.name like %?1")
    List<Department> findByFirstnameEndsWith(String departmentName);

    @Query(value = "select department from Department department where department.name = ?1", nativeQuery = true)
    Department findByName2(String departmentName);
}
{% endhighlight %}
<br>

### Bước 7 - Test ứng dụng 

<br>

### Tổng hợp các cachs query xuống database 
1. Sử dụng Query Creation

2. Sử dụng @Query

3. Sử dụng @NameQuery

https://thoughts-on-java.org/what-is-spring-data-jpa-and-why-should-you-use-it/
<br>

### Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé .
{% include youtubePlayer.html id=page.youtubeId %}