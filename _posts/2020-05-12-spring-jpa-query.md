---
layout: blog
title: Spring JPA Query
slug : spring-jpa-query
category: laptrinhspring
tags: [spring]
summery: Spring JPA Query
image: /images/blog/spring.png
description : jpa query , @query
youtubeId: WNfuVJptPnQ
---

### **1. Giới thiệu nội dung bài viết**

Chào các em ,chủ để hôm nay chúng ta sẽ tìm hiểu về các cách để query dữ liệu từ database thông qua Spring Data JPA. Nội
dung sẽ xoay quanh các vấn đề  

- @Query

Giả sử ta có entity như sau

{% highlight java  linenos %}
@Entity
@Table(name = "department")
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
### **2. Sử dung @Query để lấy dữ liệu trong table Department ?**

- Sử dụng JPQL

{% highlight java  linenos %}
@Transactional
public interface DepartmentAnnotationRepository extends JpaRepository<Department,Integer> {

    @Query("select department from Department department)
    Department findAllDepartment();
}
{% endhighlight %}

- Sử dụng Native Query

{% highlight java  linenos %}
@Query(
  value = "SELECT * FROM Department u WHERE u.status = 1",
  nativeQuery = true)
Collection<Department> findAllDepartment();
{% endhighlight %}

Để sử dung câu query thuần giống như ta thực hiện câu select trong database thì mình thêm tham số nativeQuery = true

- Tham số Index trong câu Query

{% highlight java  linenos %}
@Query("select department from Department department where department.name = ?1")
    Department findByName(String departmentName);
{% endhighlight %}

Chúng ta dùng ?1 tương ứng với tham số đầu tiên trong method findByName. ?1 sẽ được ánh xạ bằng tham số String departmentName. Nếu
chúng ta có nhiều tham số ví dụ

{% highlight java  linenos %}
@Query("select department from Department department where department.name = ?1" and department.code = ?2)
    Department findByName(String departmentName,int code);
{% endhighlight %}

Lúc đó ?1 sẽ bằng tham số departmentName và ?2 bằng code. Như vậy dùng ? để chỉ ra thứ tự các tham số trong method tương ứng với vị trí trong câu query

- Tham số Name trong câu Query

{% highlight java  linenos %}
@Query("SELECT u FROM User u WHERE u.status = :status and u.name = :name")
User findUserByStatusAndNameNamedParams(@Param("status") Integer status, @Param("name") String name);
{% endhighlight %}

Nó cũng giống na ná như Index query thay vì sử dụng vị trí (index), thì ta sử dung cái tên . Ví dụ trên ta sử dụng :status , :name để ánh xạ vào đúng tên (@Param("status") Integer status, @Param("name") String name) trong phương thức. Chú ý là ta sử dụng thêm @Param để ánh xạ tên method và tên trong @Query giống nhau

- Collection Parameter

Trong database chúng ta có toán tử IN và NOT IN như sau

{% highlight java  linenos %}
SELECT u FROM User u WHERE u.name IN :names
{% endhighlight %}

Để sử dụng được toán tử IN trong JPQL Query thì ta sử dụng tham số là Collection như sau

{% highlight java  linenos %}
@Query(value = "SELECT u FROM User u WHERE u.name IN :names")
List<User> findUserByNameList(@Param("names") Collection<String> names);
{% endhighlight %}

<br>
### **3. Sử dung Query Creation**

Spring Data JPA hỗ trở cho chúng ta sẳn các phương thức để truy cập xuống database. Chúng ta chỉ cần kế thừa JPARepository và sau đó có thể sử dụng các phương thức mà JPA cung cấp đề lấy dữ liệu từ database.

{% highlight java  linenos %}
public interface DepartmentQueryCreationRepository extends JpaRepository<Department,Integer> {

    List<Department> findByName (String name);
    List<Department> findByNameLike (String name);
    List<Department> findByNameContaining (String name);
    List<Department> findByNameStartingWith(String name);
    List<Department> findByNameEndingWith(String name);
    List<Department> findByNameIgnoreCase(String name);


    /* List<Department> findByNameAndLocal(String name,String local);
    List<Department> findByNameOrLocal(String name,String local);
    List<Department> findByNameNot(String name);
    List<Department> findByDateAfter(Date date);
    List<Department> findByDateBefore (Date date);
    List<Department> findByDateBetween(Date from,Date to); */

}
{% endhighlight %}

Trong đó findBy là từ khoá mà JPA cung cấp cho mình sau từ findBy là tên column có trong database. Ví dụ findByName tìm kiếm các user có tên là tham số name truyền vào. Trong đó findBy là từ khoá của JPA và Name chính là tên column trong database. Ngoài findBy thì JPA còn hỗ trợ nhiều phương thức khác nữa có thể xem ở đây

<br>
### **4. Sử dung @NameQuery trong Entiry**

{% highlight java  linenos %}
@Entity
@Table(name = "employee", schema="spring_data_jpa_example")
@NamedQuery(name = "Employee.fetchByLastNameLength",
        query = "SELECT e FROM Employee e WHERE CHAR_LENGTH(e.lastname) =:length "
)
public class Employee {

    @Id
    @Column(name = "id")
    @GeneratedValue(strategy = GenerationType.SEQUENCE)
    private Long id;

    @Column(name = "firstname")
    private String firstName;

    @Column(name = "lastname")
    private String lastname;
 }
{% endhighlight %}     

Như các em thấy trong Class Entity mình sử dụng @NameQuery để tạo câu lệnh select. Chú ý cho anh chổ @NamedQuery(name = "Employee.fetchByLastNameLength") Để gọi được câu lệnh này thì nơi chỗ JPA Repository ta phải có phương thức (fetchByLastNameLength) giống y chang vậy.

{% highlight java  linenos %}
@Repository
public interface EmployeeRepository extends JpaRepository<Employee,Long>, EmployeeRepositoryCustom {

    List<Employee> fetchByLastNameLength(@Param("length") Long length);
}
{% endhighlight %}

<br>
### **5. Sử dung Order in Query để sắp xếp dữ liệu theo chiều tăng hoặc giảm dần**

{% highlight java  linenos %}
departmentRepository.findAll(new Sort(Sort.Direction.ASC, "name"));
{% endhighlight %}

Dòng new Sort(Sort.Direction.ASC, "name") nghĩa là chúng ta muốn sắp xếp dữ liệu ở cột name theo chiều hướng tăng dần. Nếu muốn sắp xếp name theo chiều hướng giảm dần thì ta dùng new Sort(Sort.Direction.DESC, "name")

<br>
### **6. Sử dụng annotation @Modifying để cập nhật dữ liệu**

{% highlight java  linenos %}
@Modifying
@Query("update User u set u.status = :status where u.name = :name")
int updateUserSetStatusForName(@Param("status") Integer status,
  @Param("name") String name);
{% endhighlight %}

Kết quả trả về là bao nhiêu dòng trong database được cập nhật. Chúng ta cũng có thể sử dụng Native Query để cập nhật như sau

{% highlight java  linenos %}
@Modifying
@Query(value = "update Users u set u.status = ? where u.name = ?",
  nativeQuery = true)
int updateUserSetStatusForNameNative(Integer status, String name);
{% endhighlight %}

<br>
### **7. Sử dụng annotation @Modifying để insert dữ liệu**

Trong spring data jpa chúng ta dùng hàm save() có sẳn để insert dữ liệu xuống database. Trong trường hợp dùng native query thì chúng ta phải kết hợp @Modifiying và câu lệnh Insert chung với nhau vì Spring Data JPA chúng ta đang dùng không hổ trợ Insert

{% highlight java  linenos %}
@Modifying
@Query(
  value =
    "insert into Users (name, age, email, status) values (:name, :age, :email, :status)",
  nativeQuery = true)
void insertUser(@Param("name") String name, @Param("age") Integer age,
  @Param("status") Integer status, @Param("email") String email);
{% endhighlight %}

### **8. Sử dụng Pageable để phân trang**

Chúng ta sử dụng Pageable để lấy một tập hợp con trong database. Ví dụ như trong database có 100 dòng. Ta chỉ muốn lấy từ dùng 1 cho tới dòng 10. Để làm được như vậy chúng ta sẽ sử dụng đối tượng PageRequestObject để khai báo số lượng dòng mà ta muốn trả về , sau đó truyền đối tượng PageRequestObject vào câu lệnh truy vấn.

{% highlight java  linenos %}
Pageable first10PageWithTwoElements = PageRequest.of(0, 10);
Page<Product> allProducts = productRepository.findAll(first10PageWithTwoElements);
{% endhighlight %}

{% highlight java  linenos %}
public interface ProductRepository extends PagingAndSortingRepository<Product, Integer> {

    List<Product> findAllByPrice(double price, Pageable pageable);
}
{% endhighlight %}
