---
layout: blog
title: Ngoại Lệ Trong Java 
category: blog
tags: [java core]
summery: Ngoại Lệ Trong Java
image: /images/blog/java.png
youtubeId: 2BBAVtiks1w
---


<br><br>

### Ngoại lệ là gì ?
Exception là một tình trạng bất thường. Trong Java, Exception là một sự kiện mà phá vỡ luồng chuẩn của chương trình. 
Nó là một đối tượng mà được ném tại Runtime. Một exception (ngoại lệ) trong Java là một vấn đề xảy ra trong quá trình thực hiện của chương trình. 
<br>

### Exception 
![Exception ](/images/post/javacore/exception.png){:class="img-responsive"}
<br>

### Check Exception
1. Những lỗi và developer có thể đoán trước được
2. Bắt buộc developer phải bắt và xử lý ngoại lệ trong lúc compile time (lúc đang code)

Ví dụ các lỗi mà trong lúc code lập trình viên có thể đoán được 
1. FileNotFoundException
2. InterruptException
3. Database Exception
4. IO Exception
<br>

### Uncheck Exception
1. Những lỗi xảy ra khi chương trình đang chạy và chúng ta không biết chắc nó có xảy ra hay không
2. Không yêu cầu developer phải bắt và xử lý ngoại lệ trong lúc compile time (lúc đang code)

Ví dụ
Khi mình viết một chương trình cho nhà bank với chức năng rút tiền. Sẽ có những trường hợp lỗi xảy ra khi chương trình đang chạy đó là việc khách hàng có thể rút tiền nhiều hơn tiền họ hiện có trong tài khoản. Lúc này mình phải viết Uncheck Exception để xử lý việc này 
<br>

### Ném ngoại lệ bằng Throws hoặc throw

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

### Bắt ngoại lệ bằng try catch

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

### Khối lệnh Finally
Khối lệnh Finally luôn luôn chạy . Nó thường dùng để
1. Đóng kết nối xuống file 
2. Đóng kết nối xuống database
3. Giải phóng bộ nhớ
<br>

### Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé . 

{% include youtubePlayer.html id=page.youtubeId %}

