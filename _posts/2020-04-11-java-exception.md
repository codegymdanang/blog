---
layout: blog
title: Ngoại Lệ Trong Java 
slug : ngoai-le-trong-lap-trinh-java
category: laptrinhjava
tags: [java core]
summery: Ngoại Lệ Trong Java
image: /images/blog/java.png
description : Ngoại lệ trong Java 
youtubeId: 2BBAVtiks1w
---

### **1. Giới thiệu nội dung bài viết**

Chào các bạn , hôm nay chủ đề của mình sẽ nói về Exception trong lập trình là gì ? Bài hôm nay chúng ta sẽ đi 
qua các nội dung.
 
- Ngoại lệ là gì ?
- Check Exception là gì ?
- Uncheck Exception là gì ?
- Cú pháp và cách ném, bắt ngoại lệ.
- Video demo cách code Exception 

### **2. Ngoại lệ (Exception) là gì ?**

Exception (ngoại lệ) trong Java là một vấn đề xảy ra trong quá trình thực hiện của chương trình mà mình có thể dự đoán hoặc không dự đoán trước.
Exception là một sự kiện mà phá vỡ luồng chuẩn của chương trình. Anh lấy ví dụ về rút tiền ATM ở máy rút tiền. Trong tài khoản
mình chỉ có 1.000.000 nhưng nếu mình bấm trong máy ATM rút 2.000.000 thì lúc đó chương trình trong máy ATM sẽ báo lỗi vì 
số tiền mình yêu cầu rút lớn hơn số hiện tại. Đó chính là một Exception (ngoại lệ) xảy ra lúc chương trình đang chạy

Đối với lập trình viên mình phải bắt và xử lý các ngoại lệ trong chương trình. Nếu không chương trình sẽ bị dừng. Thường các
lập trình viên có thể bắt lại Expection trong lúc viết code hoặc dự đoán được Exception trong lúc chương trình đang chạy
để từ đó lập trình viên có thể xử lý các ngoại lệ đó mà chương trình vẫn tiếp tục chạy.

<br>

### **3. Check Exception**

- Những lỗi  developer có thể đoán trước được.
- Bắt buộc developer phải bắt và xử lý ngoại lệ trong lúc compile time (lúc đang code).

Ví dụ các lỗi mà trong lúc code lập trình viên có thể đoán được. 

- FileNotFoundException.
- InterruptException.
- Database Exception.
- IO Exception.
<br>

### **4. Uncheck Exception**

- Những lỗi xảy ra khi chương trình đang chạy và chúng ta không biết chắc nó có xảy ra hay không.
- Không yêu cầu developer phải bắt và xử lý ngoại lệ trong lúc compile time (lúc đang code). Nhưng mà
phải dự đoán được có khả năng xảy ra lỗi ở những đoạn code nào từ đó bắt lỗi cho đoạn code đó. 

Ví dụ : Khi mình viết một chương trình cho nhà bank với chức năng rút tiền. 
Sẽ có những trường hợp lỗi xảy ra khi chương trình đang chạy đó là việc khách hàng có thể rút tiền nhiều hơn số tiền họ hiện có trong tài khoản. 
Lúc này mình phải dự đoán cái hàm viết phương thức rút tiền có khả năng xảy ra lỗi và mình sẽ viết code  để xử lý ngoại lệ đó . 
 
<br>

{:refdef: style="text-align: center;"}
![Exception ](/images/post/javacore/exception.png){:class="img-responsive"}
{: refdef}

- Throwable : là cha của tất cả ngoại lệ xảy ra trong chương trình bao gồm lỗi (Error) và ngoại lệ (Exception)
- Error : là tất cả những lỗi được bắt từ JMV (Máy ảo Java). Ví dụ như Error OutOfMemory 
- Excepton : là cha của tất cả class Check Exception
- Exception Runtime : là cha của tất cả các class Uncheck 

<br>

### **5. Ném ngoại lệ bằng Throws hoặc throw**

- Trong Java mình có thể dùng từ khoá throws bên cạnh  tên method để ném ngoại lệ. Ví dụ như public void deposit(int depositAmount) throws Exception . Phương thức nào
mà gọi method deposit phải bắt lại ngoại lệ và xử lý . Để bắt ngoại lệ thì mình dùng khối  try, catch , finally lệnh để  ngoại lệ bắt từ hàm deposit ném ra

- Ngoài cách dùng Throws ta có thể dùng throw new Exception  bên trong method như ví dụ dưới  đây .

{% highlight java linenos %}
/**
 * @exception FileNotFoundException ...
 */
public Scanner(String fileName) throws FileNotFoundException {
   // ...
}

public void deposit(int depositAmount) throws Exception {
   if (depositAmount > getAmount()) {
       throw new Exception("Current Amount is less than Deposit");
   }
   System.out.println("Deposit is valid " + depositAmount);
}
{% endhighlight %}
<br>

### **6. Bắt ngoại lệ bằng try catch**

{% highlight java linenos %}
public int getPlayerScore(String playerFile) {
    try {
        Scanner contents = new Scanner(new File(playerFile));
        return Integer.parseInt(contents.nextLine());
    } catch (FileNotFoundException noFile) {
        throw new IllegalArgumentException("File not found");
    }
}
{% endhighlight %}
<br>

### Bắt ngoại lệ bằng nhiều catch

{% highlight java linenos %}
public int getPlayerScore(String playerFile) {
    try (Scanner contents = new Scanner(new File(playerFile))) {
        return Integer.parseInt(contents.nextLine());
    } catch (IOException e) {
        logger.warn("Player file wouldn't load!", e);
        return 0;
    } catch (NumberFormatException e) {
        logger.warn("Player file was corrupted!", e);
        return 0;
    }
}
{% endhighlight %}
<br>

### **7. Khối lệnh Finally

Khối lệnh Finally luôn luôn chạy cho dù có xảy ra lỗi ở trong khối lệnh try hay catch . Khối lệnh Finally thường dùng để.

- Đóng kết nối xuống file .
- Đóng kết nối xuống database.
- Giải phóng bộ nhớ.
<br>

### **8. Video demo tạo Exception trong Java ** 

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}
