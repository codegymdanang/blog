---
layout: course-bootstrap
title: Sử dụng Typography trong Bootstrap 
slug : su-dung-typography-trong-boostrap
category: laptrinhweb
tags: [bootstrap]
summery: Typography
image:
description : Bài viết trình bày về thuộc tính Typography, một trong những thuộc tính không thể thiếu khi làm các dự án lập trình web. Bài viết lần lượt giới thiệu về các thẻ Heading, những mặc định có sẵn trong Bootstrap 4, và các thẻ small, mark, abbr, blockquote, dl được sử dụng trong Bootstrap 4. Trong mỗi phần có kèm theo hình ảnh minh hoạ cách làm cho mỗi phần để tham khảo thêm và dễ nắm bắt với những kiến thức chia sẻ trong bài. 
youtubeId: Ex3glZTCvlY
---

{% include toc.html %}

## **Giới thiệu nội dung bài viết**

Cũng tương tự như các ngôn ngữ lập trình khác trong <b>lập trình web</b>, ngôn ngữ Bootstrap cũng có những thuộc tính để thiết lập cho các phần tử trong web.
<br>
Trong phạm vi bài viết này, anh sẽ chia sẻ với các bạn về thuộc tính <b>Typography</b> được sử dụng trong <b>lập trình web</b> Bootstrap. Bài viết lần lượt giới thiệu về các thẻ Heading, những mặc định có sẵn trong Bootstrap 4, và các thẻ small, mark, abbr, blockquote, dl được sử dụng trong Bootstrap 4. Trong mỗi phần anh có kèm theo hình ảnh minh hoạ cách làm cho mỗi phần để các bạn tham khảo thêm và dễ nắm bắt với những kiến thức anh chia sẻ trong bài.


## **1. Mặc định có sẳn trong Bootstrap 4**

Boostrap 4 sử dụng kích thước front-size là 16px và line-height là 1.5. Font mặc định được sử dụng trong bootstrap 4 là Helvetica Neue. Các thẻ <p> đều có margin top là bằng 0 và margin bottom là 16 px.

## **2. Các thẻ Heading trong Bootstrap 4**

Các thẻ Heading từ H1 tới H6 có kích thước border và font như sau.

<br>
{% highlight html  linenos %}

h1 Bootstrap heading (2.5rem = 40px)
h2 Bootstrap heading (2rem = 32px)
h3 Bootstrap heading (1.75rem = 28px)
h4 Bootstrap heading (1.5rem = 24px)
h5 Bootstrap heading (1.25rem = 20px)
h6 Bootstrap heading (1rem = 16px)

{% endhighlight %}

Để hiển thị font có kích thước to, chúng ta sử dụng class display sau đó là kích thước. Boostrap cung cấp 4 loại class để hiển thị kích thước font như sau

<br>
{% highlight html  linenos %}

<h1 class="display-1">Display 1</h1>
<h1 class="display-2">Display 2</h1>
<h1 class="display-3">Display 3</h1>
<h1 class="display-4">Display 4</h1>
{% endhighlight %}


{:refdef: style="text-align: center;"}
![Heading](/images/post/boostrap/heading.png){:class="img-responsive"}
{: refdef}

## **3. Thẻ small trong Bootstrap 4**

<br>
{% highlight html  linenos %}

<div class="container">
  <h1>Lighter, Secondary Text</h1>
  <p>The small element is used to create a lighter, secondary text in any heading:</p>       
  <h1>h1 heading <small>secondary text</small></h1>
  <h2>h2 heading <small>secondary text</small></h2>
  <h3>h3 heading <small>secondary text</small></h3>
  <h4>h4 heading <small>secondary text</small></h4>
  <h5>h5 heading <small>secondary text</small></h5>
  <h6>h6 heading <small>secondary text</small></h6>
</div>
{% endhighlight %}


{:refdef: style="text-align: center;"}
![small](/images/post/boostrap/small.png){:class="img-responsive"}
{: refdef}

## **4. Thẻ mark trong Bootstrap 4**

Dùng để highlight các chữ text lên màu vàng. Nếu chúng ta muốn sử dụng chức năng highlight

<br>
{% highlight html  linenos %}

<div class="container">
  <h1>Highlight Text</h1>    
  <p>Use the mark element to <mark>highlight</mark> text.</p>
</div>

{% endhighlight %}


{:refdef: style="text-align: center;"}
![small](/images/post/boostrap/highlight.png){:class="img-responsive"}
{: refdef}

## **5. Thẻ abbr trong Bootstrap 4**

Dùng để gạch dưới các từ mà mình mong muốn.

<br>
{% highlight html  linenos %}

<div class="container">
  <h1>Abbreviations</h1>
  <p>The abbr element is used to mark up an abbreviation or acronym:</p>
  <p>The <abbr title="World Health Organization">WHO</abbr> was founded in 1948.</p>
</div>

{% endhighlight %}

{:refdef: style="text-align: center;"}
![dotundertext](/images/post/boostrap/dotundertext.png){:class="img-responsive"}
{: refdef}

## **6. Thẻ blockquote trong Bootstrap 4**

Dùng để trích dẫn một văn bản từ một nguồn nào đó.

<br>
{% highlight html  linenos %}

<h1>Blockquotes</h1>
  <p>The blockquote element is used to present content from another source:</p>
  <blockquote class="blockquote">
    <p>For 50 years, WWF has been protecting the future of nature. The world's leading conservation organization, WWF works in 100 countries and is supported by 1.2 million members in the United States and close to 5 million globally.</p>
    <footer class="blockquote-footer">From WWF's website</footer>
  </blockquote>
</div>


{% endhighlight %}

Kết quả nhận được là

<br>
{% highlight html  linenos %}

Blockquotes

The blockquote element is used to present content from another source:

    For 50 years, WWF has been protecting the future of nature. The world's leading conservation organization, WWF works in 100 countries and is supported by 1.2 million members in the United States and close to 5 million globally.
    - From WWF's website

{% endhighlight %}

## **7. Thẻ dl trong Bootstrap 4**

Sử dụng dl để hiển thị danh sách.

<br>
{% highlight html  linenos %}

<h1>Description Lists</h1>    
  <p>The dl element indicates a description list:</p>
  <dl>
    <dt>Coffee</dt>
    <dd>- black hot drink</dd>
    <dt>Milk</dt>
    <dd>- white cold drink</dd>
  </dl> 

Coffee
    - black hot drink
Milk
    - white cold drink

{% endhighlight %}

