---
layout: course-java
title: Sử dụng TreeMap trong lập trình Java
slug : su-dung-treemap-trong-lap-trinh-java
category: laptrinhjava
tags: [java core]
summery: TreeMap
image: /images/blog/java.png
featureImage: /images/post/javacore/feature_collection.png
description : TreeMap trong lập trình Java là gì? Nó hoạt động như thế nào? Các phương thức của lớp TreeMap trong lập trình Java. Các thao tác cơ bản với TreeMap như cách tạo một TreeMap, xoá một phần tử trong TreeMap. Hay cách thực hiện với SortedMap như thế nào? Hãy cùng tìm hiểu những thông tin trên qua bài viết này nhé. Với những chia sẻ lí thuyết kèm theo ví dụ minh hoạ, bài viết sẽ giúp bạn áp dụng ngay TreeMap vào thực hành lập trình.
youtubeId: 5C2OqlhiYsg
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Để hỗ trợ cho việc tổ chức các dữ liệu trong chương trình <b>lập trình Java</b>, bên cạnh sử dụng HashMap các lập trình viên Java cũng thường chọn sử dụng lớp TreeMap. 
Cụ thể <b>TreeMap trong lập trình Java</b> là gì? Nó hoạt động như thế nào? Các phương thức của lớp TreeMap trong lập trình Java. Các thao tác cơ bản với TreeMap như cách tạo một TreeMap, xoá một phần tử trong TreeMap. Hay cách thực hiện với SortedMap như thế nào? Hãy cùng tìm hiểu những thông tin trên qua bài viết này nhé. 


## **1. TreeMap trong lập trình Java là gì**

Trong <b>lập trình Java</b>, cũng giống như HashMap thì TreeMap dùng để lưu trữ các giá trị theo kiểu key và value. Tuy nhiên có một số đặt điểm mà TreeMap khác với HashMap là

+ HashMap có thể chứa key là null nhưng TreeMap chúng ta không thể chứa key là null được
+ Các phần tử trong HashMap thì không sắp xếp theo một trật tự còn các phần tử trong TreeMap là được sắp xếp tăng dần

## **2. Tạo TreeMap**

{% highlight java linenos %}

- Chúng ta sử dụng phương thức put để thêm phần tử vào tập hợp

class TreeMap1{  
 public static void main(String args[]){  
   TreeMap<Integer,String> map=new TreeMap<Integer,String>();    
      map.put(100,"Amit");    
      map.put(102,"Ravi");    
      map.put(101,"Vijay");    
      map.put(103,"Rahul");    
        
      for(Map.Entry m:map.entrySet()){    
       System.out.println(m.getKey()+" "+m.getValue());    
      }    
 }  
}  

{% endhighlight %}

## **3. Xoá phần tử trong TreeMap**

- Chúng ta sẽ dụng phương thức remove để xoá phần tử ra khỏi tập hợp

{% highlight java linenos %}

public class TreeMap2 {  
   public static void main(String args[]) {  
    TreeMap<Integer,String> map=new TreeMap<Integer,String>();    
      map.put(100,"Amit");    
      map.put(102,"Ravi");    
      map.put(101,"Vijay");    
      map.put(103,"Rahul");    
      System.out.println("Before invoking remove() method");  
      for(Map.Entry m:map.entrySet())  
      {  
          System.out.println(m.getKey()+" "+m.getValue());      
      }  
      map.remove(102);      
      System.out.println("After invoking remove() method");  
      for(Map.Entry m:map.entrySet())  
      {  
          System.out.println(m.getKey()+" "+m.getValue());      
      }  
      }  
}  

{% endhighlight %}

## **4. SortedMap**

- Chúng ta sẽ dụng phương thức remove để xoá phần tử ra khỏi tập hợp

{% highlight java linenos %}

class TreeMap4{  
 public static void main(String args[]){  
   SortedMap<Integer,String> map=new TreeMap<Integer,String>();    
      map.put(100,"Amit");    
      map.put(102,"Ravi");    
      map.put(101,"Vijay");    
      map.put(103,"Rahul");    
      //Returns key-value pairs whose keys are less than the specified key.  
      System.out.println("headMap: "+map.headMap(102));  
      //Returns key-value pairs whose keys are greater than or equal to the specified key.  
      System.out.println("tailMap: "+map.tailMap(102));  
      //Returns key-value pairs exists in between the specified key.  
      System.out.println("subMap: "+map.subMap(100, 102));    
 }  
}  
{% endhighlight %}

- Phương thức headMap sẽ trả về cho chúng ta những key nhỏ hơn 102 (tham số truyền vào)
- Phương thức tailMap sẽ trả về cho chúng ta những key có giá trị lớn hoặc bằng 102
- Phương thức subMap sẽ trả về cho chúng ta những key nằm giữa 100 và 102.






