---
layout: blog
title: Design Pattern Là Gì ?
slug: design-pattern-la-gi
category: craftmanship
tags: [designpattern]
summery: Design Pattern Là Gì ?
image: /images/blog/design-patterns.png
description : design pattern là gì ? vì sao sử dụng design pattern, các mẫu design pattern

---

Chào các e, chủ đề hôm nay của anh sẽ bàn về chủ đề  Design Pattern
<br><br>

### Design Pattern là gì ?
Design Pattern là một giải pháp cho một vấn đề chung trong thiết kế phần mềm . Nó mô tả cách giải quyết một vấn đề được lập đi lập lại
nhiều lần. A lấy ví dụ về giải pháp khi mình thay đổi giá trị trong database thì nó tự động cập nhập giá trị đó lên các giao diện ứng dung
khác nhau như mobile , web, tivi cùng một lúc. Để giải quyết được vấn đề đó thì người ta áp dụng MVC pattern để giải quyết vấn đề.
Như vậy người ta áp dụng design pattern để giải quyết cho những vấn đề gặp phải ở nhiều tình huống khác nhau.
<br>

### Tại sao nên sử dụng Design Pattern
1. Design Pattern giúp cho dự án chúng ta dể dàng mở rộng mà không phải xoá đi code. Chúng ta chỉ cần viết thêm Class mới cho
chức năng mới
2. Các mẫu Design Pattern này do các kỷ sư hàng đầu thế giới nghiêu cứu và phát triển nên ta hoàn toàn tin tưởng khả
năng mở rộng khi dùng chúng
3. Design Pattern như một ngôn ngữ chung mà tất cả developers trên thế giới đều biết , giúp chúng ta hiểu được các
thiết kế hệ thống của các developer

### Các loại design pattern hiện nay
Design Pattern được chia làm 3 mục chính là : Creational Pattern ( nhóm khởi tạo), Structural (nhóm cấu trúc) và Behavioral patterns (nhóm hành vi ) .

Creational Pattern ( nhóm khởi tạo): Nhóm này sẽ giúp bạn rất nhiều trong việc khởi tạo đối tượng

1. Abstract Factory.
2. Builder.
3. Factory Method.
4. Multiton.
5. Pool.
6. Prototype.
7. Simple Factory.
8. Singleton.
10. Static Factory.

Structural (nhóm cấu trúc): Nhóm này sẽ giúp chúng ta thiết lập, định nghĩa quan hệ giữa các đối tượng. Cấu trúc để tạo đối tượng

1. Adapter/ Wrapper.
2.    Bridge.
3.    Composite.
4.    Data Mapper.
5.    Decorator.
6.    Dependency Injection.
7.    Facade.
8.    Fluent Interface.
9.    Flyweight.
10.    Registry.
11.    Proxy

Behavioral patterns (nhóm hành vi): Nhóm này sẽ tập trung thực hiện các hành vi của đối tượng.

1.    Chain Of Responsibilities.
2.    Command.
3.    Iterator.
4.    Mediator.
5.    Memento.
6.    Null Object.
7.    Observer.
8.    Specification.
9.    State.
10.   Strategy.
11.   Template Method.
12.   Visitor.

### Tổng kết
Như các em thấy hầu hết các framework mà chúng ta đang dùng đều xây dựng dựa trên các design pattern . Vì nó có
khả năng mở rộng cao . Ứng với từng mục đích , từng bài toán mà ta sẽ sử dụng pattern tương ứng để giải quyết vấn đề .
