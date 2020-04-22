---
layout: blog
title: Phân Biệt Session và Cookie 
category: blog
tags: [spring]
summery: Phân Biệt Session và Cookie 
image: /images/blog/spring.png
description : Phân biệt Session và Cookie 
youtubeId: ym4-rU9R6fM
---

Chào bạn, chắc khá nhiều bạn đang học lập trình không phân biệt  được sự khác nhau giữa session và cookie . Khi nào thì dùng chúng
Hôm nay anh sẽ trình bày nguyên lý và sự khác nhau của session và cookie cũng như khi nào mình sẽ sử dụng nó
<br><br>

### Session
Một session hay còn gọi là một phiên làm việc. Nó  là cách giao tiếp giữa client (trình duyệt web) với server.
Một session bắt đầu khi client gửi request đến sever, nó tồn tại xuyên suốt từ trang này đến trang khác trong ứng dụng và chỉ kết thúc khi hết thời gian timeout hoặc khi bạn đóng ứng dụng tắt trình duyệt . 
Giá trị của session sẽ được lưu trong một tệp tin trên máy chủ. Chúng chỉ nên lưu trữ những thông tin tạm thời trong session 
Với mỗi session sẽ được cấp phát một định danh duy nhất SessionID. Khi kết thúc một phiên làm việc và bắt đầu một phiên mới,mình sẽ nhận được một session ID khác 
Sau khi server tạo các giá trị session , server sẽ tạo ra một tệp tin cookie lưu trên trình duyệt của người  dùng  ứng với session đó. Như vậy chỉ cần so sánh tệp tin cookie bên phía client được gửi lên sever và tệp session được lưu trên server
để xem làm trình duyệt đó là mới hay cũ 
<br>

### Cookie 
Cookie cũng được dùng để lưu những thông tin tạm thời. ệp tin cookie sẽ được truyền từ server tới browser và được lưu trữ trên máy tính của bạn khi bạn truy cập vào ứng dụng.
Như vậy dù có tắt browser cũng không mất đi các giá trị vì chúng ta đã lưu nó trên máy tính của mình
<br>

### So sánh session và cookie

{:class="table table-bordered"}
 |  	 Cookie                                             |   Session	                                        | 
 |---	                                                    |---	     	                                    |
 |   Cookie được lưu trữ trên trình duyệt của người dùng.   |   Session không được lưu trữ trên trình duyệt.    |                                            
 |  Dữ liệu cookie được lưu trữ ở phía client.| Dữ liệu session được lưu trữ ở phía server. | 
 |  Dữ liệu cookie dễ dàng sửa đổi hoặc đánh cắp khi chúng được lưu trữ ở phía client      |   Dữ liệu session không dễ dàng sửa đổi vì chúng được lưu trữ ở phía máy chủ.|
 |  Dữ liệu cookie có sẵn trong trình duyệt đến khi expired.   | Sau khi đóng trình duyệt sẽ hết phiên làm việc (session)   |

<br> 


### Và bây giờ, hãy cùng xem code demo ở bên dưới để hiểu rõ hơn nhé . 

{% include youtubePlayer.html id=page.youtubeId %}