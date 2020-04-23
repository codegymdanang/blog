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



```
void printOwing() {
  printBanner();

  // Print details.
  System.out.println("name: " + name);
  System.out.println("amount: " + getOutstanding());
}

```


### Giải quyết vấn đề bằng kỷ thuật Extract Method




### Kết quả 

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




