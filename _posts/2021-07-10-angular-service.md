---
layout: course-angular
title: Sử dụng Service trong Angular  
slug : su-dung-service-trong-angular
category: laptrinhweb
tags: [angular]
summery: Service   
image: /images/blog/angular.png
description : Angular Service là những đoạn code có thể sử dụng nhiều lần từ các component khác nhau. Bài viết dưới đây sẽ giúp bạn hiểu rõ hơn về Service trong Angular cũng như mục đích và ưu điểm khi sử dụng Service trong Angular gồm những gì. Đồng thời hướng dẫn cách làm để tạo Service trong Angular và chỉ ra những nhược điểm và cách khắc phục trong một số trường hợp khi sử dụng Service trong Angular.
youtubeId: XbjWaPBpbNs
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn,hôm nay anh sẽ hướng dẫn mọi người về <b>Angular Service</b> là như thế nào?

## **1. Angular Service là gì**

Angular Service là những đoạn code mà ta có thể sử dụng nhiều lần từ các component khác nhau. Nó có chức năng sử dụng lại. Những đoạn code này sẽ thực hiện một nhiệm vụ cụ thể cho một ý định nào đó. 

Chúng ta sử dụng service cho những mục đích

- Những nhiệm vụ độc lập của component như ghi log, gọi api từ bên ngoài vv
- Chia sẻ code logic hoặc data để các component có thể dùng chung

Lợi thế của Service

- Dễ dàng thực hiện các việc test cho component và service
- Dễ dàng debugs khi có vấn đề
- Có thể được sử dụng lại ở nhiều module  

## **2. Tạo Service như thế nào**

Trong ví dụ này chúng ta sẽ tạo một Service lấy tất cả các sản phẩm. Component sẽ gọi service để lấy kết quả và hiển thị lên template html.

- Bước 1 : Tạo Model Product

{% highlight javascript linenos %}

export class Product { 
 
    constructor(productID:number,    name: string ,   price:number) {
        this.productID=productID;
        this.name=name;
        this.price=price;
    }
 
    productID:number ;
    name: string ;
    price:number;
 
}

{% endhighlight %} 

- Bước 2 : Tạo Product Service trả về mảng các Product

{% highlight javascript linenos %}

import {Product} from './Product'
 
export class ProductService{
 
    public  getProducts() {
 
        let products:Product[];
 
        products=[
            new Product(1,'Memory Card',500),
            new Product(1,'Pen Drive',750),
            new Product(1,'Power Bank',100)
        ]
 
        return products;               
    }
}

{% endhighlight %} 

- Bước 3 : Nhúng Service vào Component Product

{% highlight javascript linenos %}

import { Component } from '@angular/core';
 
import { ProductService } from './product.service';
import { Product } from './product';
 
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
})
 
export class AppComponent
{
 
   products:Product[];
   productService;
 
   constructor(){
     this.productService=new ProductService();
   }
 
   getProducts() {
     
     this.products=this.productService.getProducts();
   }
  
}


{% endhighlight %} 

- Bước 4 : Truyền dữ liệu từ Component sang cho template html

{% highlight javascript linenos %}

<div class="container">
    <h1 class="heading"><strong>Services </strong>Demo</h1>
 
    <button type="button" (click)="getProducts()">Get Products</button>
 
     <div class='table-responsive'>
            <table class='table'>
                <thead>
                    <tr>
                        <th>ID</th>
                        <th>Name</th>
                        <th>Price</th>
                    </tr>
                </thead>
                <tbody>
                    <tr *ngFor="let product of products;">
                        <td>{{product.productID}}</td>
                        <td>{{product.name}}</td>
                        <td>{{product.price}}</td>
                    </tr>
                </tbody>
            </table>
        </div>
 
</div>
{% endhighlight %} 

Chúng ta thấy ở ví dụ trên chúng ta nhúng Service vào component bằng cách

{% highlight javascript linenos %}

this.productService=new ProductService();

{% endhighlight %} 

Trong thực tế thì anh không làm như vậy vì nó có rất nhiều khuyết điểm

- Service product dính chặt vào component. Sau này có thay đổi ProductService chúng ta phải cập nhật code ở nhiều nơi, nhiều components mà đang sử dụng nó. Như vậy tính uyển chuyển sẽ không có.

- Nếu anh muốn thay ProductService bằng một Service khác thì anh phải search trong tất cả component nơi sử dụng ProductService để thay đổi. Khả năng bảo trì rất khó.

- Khó khăn trong việc test các chức năng của ProductService.

Những vấn đề này sẽ được giải quyết trong bài Dependency Injection

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}







