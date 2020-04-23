---
layout: blog
title: Kỷ thuật Extract Method 
category: blog
tags: [refactoring]
summery: Kỷ thuật Extract Method 
image: /images/blog/design-patterns.png
description : Design Pattern Là Gì ?

---

Chào các e, chủ đề hôm nay của anh sẽ bàn về chủ đề  Design Pattern
<br><br>

### Vấn đề đang gặp  ?

Trong hàm printOwing ta thấy có 2 nhiệm vụ . Thứ nhất 
```
void printOwing() {
  printBanner();

  // Print details.
  System.out.println("name: " + name);
  System.out.println("amount: " + getOutstanding());
}

```


### Giải quyết vấn đề bằng kỷ thuật Extract Method


```
void printOwing() {
  printBanner();
  printDetails(getOutstanding());
}

void printDetails(double outstanding) {
  System.out.println("name: " + name);
  System.out.println("amount: " + outstanding);
}
```

<br>


### Tổng kết
Như các em thấy hầu hết các framework mà chúng ta đang dùng đều xây dựng dựa trên các design pattern . Vì nó có 
khả năng mở rộng cao . Ứng với từng mục đích , từng bài toán mà ta sẽ sử dụng pattern tương ứng để giải quyết vấn đề .




