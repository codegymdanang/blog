---
layout: course-angular
title: Sử dụng Directive NgFor trong Angular
slug : su-dung-directive-ngFor-trong-angular
category: laptrinhweb
tags: [angular]
summery: NgFor   
image: /images/blog/angular.png
description : Giải thích được Directive NgFor trong Angular là gì? Tìm hiểu cú pháp của NgFor trong Angular. Hướng dẫn cách để tạo, thêm NgFor cũng như cách sử dụng NgFor vào dự án Angular như sử dụng 2 vòng NgFor, sử dụng NgFor mảng trong mảng, sử dụng Index, định dạng format dòng chẵn lẻ trong table và cách để lấy phần tử đầu và cuối trong mảng. Bài viết có kèm theo hình ảnh ví dụ minh hoạ cụ thể cách thao tác cho mỗi phần.
youtubeId: nspfUGvho28
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Chào các bạn, hôm nay anh sẽ hướng dẫn mọi người cách tạo <b>NgFor</b> là như thế nào? 

## **1. NgFor là gì**

Chúng ta sử dụng ngFor để duyệt qua các tập hợp dữ liệu như array, list. Sau đó ta tạo các thành phần web tương ứng với mỗi vòng lặp.

Cú pháp của ngFor như sau:

{% highlight html  linenos %}

<html-element ngFor="let <item> of <items>;"> 
     <html-Template></html-Template>
</html-element>


{% endhighlight %}

- <html-element> : là thẻ web mà ta muốn sử dụng ngFor directive
- \*ngFor : dấu \* tượng trưng cho cú pháp của Angular
-  let <item> of <items> : item là giá trị hiện tại của phần tử trong mảng, items chính là mảng các phần tử

## **2. Sử dụng NgFor**

Ví dụ sau ta sẽ hiển thị danh sách các bộ films. Ta có component class như sau:

{% highlight javascript  linenos %}

import { Component } from '@angular/core';
 
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title: string ="Top 5 Movies" ;
 
 
  movies: Movie[] =[
 
  {title:'Zootopia',director:'Byron Howard, Rich Moore',cast:'Idris Elba, Ginnifer Goodwin, Jason Bateman',releaseDate:'March 4, 2016'},
  {title:'Batman v Superman: Dawn of Justice',director:'Zack Snyder',cast:'Ben Affleck, Henry Cavill, Amy Adams',releaseDate:'March 25, 2016'},
  {title:'Captain American: Civil War',director:'Anthony Russo, Joe Russo',cast:'Scarlett Johansson, Elizabeth Olsen, Chris Evans',releaseDate:'May 6, 2016'},
  {title:'X-Men: Apocalypse',director:'Bryan Singer',cast:'Jennifer Lawrence, Olivia Munn, Oscar Isaac',releaseDate:'May 27, 2016'},
  {title:'Warcraft',director:'Duncan Jones',cast:'Travis Fimmel, Robert Kazinsky, Ben Foster',releaseDate:'June 10, 2016'},
]
 
CompositeKey (index,item){
    return item.title + item.director ; 
   }
}
 
class Movie {
  title : string;
  director : string;
  cast : string;
  releaseDate : string;
}
{% endhighlight %}

Chúng ta sử dụng ngFor để duyệt qua từng bộ phim trong mảng movides ở file html như sau:

{% highlight html  linenos %}

<h1> {{title}} </h1>
 
  <ul>
    <li *ngFor="let movie of movies">
      {{ movie.title }} - {{movie.director}}
    </li>
  </ul>
 
{% endhighlight %}

 ## **3. Sử dụng NgFor mảng trong mảng**

 Ví dụ ta có danh sách các nhân viên, trong mỗi nhân viên lại có danh sách các skills.

{% highlight javascript  linenos %}

 employees = [
    {
      name: "Rahul", email: "rahul@gmail.com",
      skills: [{ skill: 'Angular', exp: '2' },{ skill: 'Javascript', exp: '7' },{ skill: 'TypeScript', exp: '3' }
      ]
    },
    {
      name: "Sachin", email: "sachin@gmail.com",
      skills: [{ skill: 'Angular', exp: '1' },{ skill: 'Android', exp: '3' },{ skill: 'React', exp: '2' }
      ]
    },
    {
      name: "Laxman", email: "laxman@gmail.com",
      skills: [{ skill: 'HTML', exp: '2' },{ skill: 'CSS', exp: '2' },{ skill: 'Javascript', exp: '1' }
      ]
    }
  ]
{% endhighlight %}

- Chúng ta sẽ sử dụng 2 vòng ngFor như sau

{% highlight html  linenos %}

<div class='table-responsive'>
    <table class='table table-bordered table-sm '>
      <thead class="thead-dark">
        <tr>
          <th>Name</th>
          <th>Mail</th>
          <th>Skills</th>
        </tr>
      </thead>
      <tbody>
        <tr *ngFor="let employee of employees;">
          <td>{{employee.name}}</td>
          <td>{{employee.email}}</td>
          <td>
            <table class='table table-sm '>
              <tbody>
                <tr *ngFor="let skill of employee.skills;">
                  <td>{{skill.skill}}</td>
                  <td>{{skill.exp}}</td>
                </tr>
              </tbody>
            </table>
 
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</div>
{% endhighlight %}

 ## **4. Sử dụng Index**

 Chúng ta có thể sử dụng biến local index trong ngFor để xem số thứ tự của mỗi phần tử trong mảng.

{% highlight html  linenos %}

 <tr *ngFor="let movie of movies; let i=index;">
    <td> {{i}} </td>
    <td>{{movie.title}}</td>
    <td>{{movie.director}}</td>
    <td>{{movie.cast}}</td>
    <td>{{movie.releaseDate}}</td>
</tr>
{% endhighlight %}

 ## **5. Format dòng chẵn dòng lẻ trong table**

{% highlight html  linenos %}

<tr *ngFor="let movie of movies; let i=index; let o= odd; let e=even;"
[ngClass]="{ odd: o, even: e }">
    <td> {{i}} </td>
    <td>{{movie.title}}</td>
    <td>{{movie.director}}</td>
    <td>{{movie.cast}}</td>
    <td>{{movie.releaseDate}}</td>
</tr>
{% endhighlight %}

 ## **6. Lấy phần tử đầu và cuối trong mảng**

{% highlight html  linenos %}
<tr *ngFor="let movie of movies; let i=index; let first= first; let last=last;" [ngClass]="{ first: first, last: last }">
    <td> {{i}} </td>
    <td>{{movie.title}}</td>
    <td>{{movie.director}}</td>
    <td>{{movie.cast}}</td>
    <td>{{movie.releaseDate}}</td>
</tr>

{% endhighlight %}

{:refdef: style="text-align: center;"}
{% include youtubePlayer.html id=page.youtubeId %}
{: refdef}























