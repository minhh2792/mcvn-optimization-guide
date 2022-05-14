Danh sách này được dịch và có sửa đổi từ [Hướng dẫn optimize server Minecraft của Eternity](https://eternity.community/index.php/paper-optimization117/#Hosting-Options)

Đây là một danh sách gồm những lựa chọn phổ biến khi đề cập đến việc host một server Minecraft, xếp từ mạnh cho đến củ chuối nhất.

## Dedicated Server - Cả 1 máy riêng dành cho bạn
Đắt nhất trong các lựa chọn, yêu cầu có kĩ năng quản trị Linux tối thiểu.  
Nếu muốn, bạn có thể chọn [OVH](https://www.ovhcloud.com/) hoặc [Hetzner](https://www.hetzner.com/)  
Khả thi với server ~50 người chơi

## Shared host - Cùng "chia sẻ" tài nguyên với các server khác
Khả thi với server từ 10~50 người chơi, tuỳ theo gói mà bạn mua.  

## Oracle Cloud Free Tier - Miễn phí, nhưng cũng có điểm trừ
Có thể không có cho bạn vì dạo gần đây nó khá nổi, và số lượng instance của Oracle thì có hạn. Bạn có thể tham khảo chi tiết hơn [tại đây](https://blogs.oracle.com/developers/post/how-to-set-up-and-run-a-really-powerful-free-minecraft-server-in-the-cloud)  
Khả thi với server ~20 người chơi liên tục, với instance A1 ARM-based  
Lưu ý rằng instance của bạn có khả năng bị **disable** hoặc **xoá hoàn toàn** vào ngày thứ **60**, nhưng bạn vẫn có thể xoá instance hiện tại và sử dụng một instance mới (tất nhiên bạn phải còn dung lượng trống trên cloud)  
**LƯU Ý, PHẢI CÓ BACKUP BOOT VOLUME NẾU BẠN LỰA CHỌN CÁI NÀY!**

## VPS - Virtual Private Server
Nghe thì có vẻ hời, nhưng thực chất thì VPS sẽ có thể **không bằng** shared host, vì phần lớn VPS hiện tại trên thị trường chỉ tập trung vào phân khúc **web-hosting**, vậy nên tài nguyên (CPU, RAM, v.v) có thể sẽ kém hơn, khiến cho trải nghiệm của bạn bị tệ đi rất nhiều.  
Khả thi tuỳ theo loại VPS mà bạn chọn. Nếu quyết định theo hướng này, hãy tìm VPS chuyên dụng để host server game, thay vì những VPS để host web.

## Budget Host - Rẻ hơn Shared Host, và tất nhiên là tệ hơn
Họ sẽ cố gắng nhồi nhét càng nhiều server lên 1 máy có thể càng tốt, kiểu như nhét khách vào xe buýt vậy. Đây chính là lý do mà chúng rẻ hơn shared host, đơn giản vì ít máy = ít chi phí hơn.  
Thường chi nhiều tiền cho quảng cáo hơn là chất lượng dịch vụ của chính họ.  
Thường nhắm đến những con mồi nhẹ dạ cả tin, có thể nhận biết như sau:  
* Model CPU không được đề cập đến trên các gói dịch vụ  
* Các gói được bán phân chia theo số lượng người chơi tối đa
* Quá 10GB RAM thì bắt đầu bán RAM theo GB
* "Lưu trữ không giới hạn"
* Discount "chỉ còn lại hôm nay" nhưng refresh quanh năm vẫn thấy
* Có `Xms=128M` trong JVM startup flag, [có thể dùng timings report để nhận biết](https://eternity.community/index.php/paper-optimization117/#timings)  

Khả thi cho server từ 5~25 người chơi.  
Có thể tự dưng hiệu năng bị hẻo bất thình lình, chỉ vì cái máy chủ của bạn xui xẻo bị cho lên một cái VPS chật ních.

## Summer host - Đứa con bị ghẻ của Budget Host
Thuật ngữ "Summerhost" ám chỉ những host "sớm nở, chóng tàn", mọc lên vào mùa hè khi mà nhu cầu cho server Minecraft tăng cao đột biến, để khi nhu cầu giảm thì cho sập, đợi đến năm sau thì thay tên đổi họ nhưng thực chất chỉ là "bình mới rượu cũ". Bạn có thể đọc thêm về Summerhost [tại đây](https://summerhost.pages.dev/)  
Tốt nhất là nên **tránh xa ra**, vì loại host này có thể sập bất thình lình và đưa cả cái server của bạn xuống mồ chung với nó.

## Free host - Tệ nhất của những thứ tệ trong danh sách
**"Nếu bạn không trả tiền cho sản phẩm, bạn chính là sản phẩm ở đây".**
* Với chiến thuật marketing "ở đây chúng tôi miễn phí", để chỉ phải chi rất ít chi phí, trong khi chia rất ít tài nguyên cho rất nhiều người.   

Lấy ví dụ như Aternos và Minehut, chúng đều có **rất, rất nhiều** hạn chế, như là JVM flags, config files, plugin, server JAR, không thể nhập / xuất file ra,.vân vân và mây mây. **Bạn đang tự nhảy vào hệ sinh thái và tự biến mình thành một món hàng trên kệ cho họ bán**  
Phù hợp cho... lũ nhóc nít dưới 13 tuổi vắt mũi chưa sạch xem dReAm SmP nhưng không xin được ba mẹ cho mượn Visa để mua một cái host đàng hoàng.

## Self host - Triển tại nhà
Nếu như bạn không sợ bị DDOS bởi một thằng ất ơ dở hơi / chán không có gì làm nào đó, bạn có thể tiếp tục. Tuy nhiên, phương pháp này vẫn được khuyến nghị là **không nên làm**, trừ khi bạn có đủ kiến thức và tự phòng vệ được bản thân.  
Nếu bạn vẫn muốn tiếp tục, đây là những hành trang cơ bản bạn có thể làm theo:
* [Hướng dẫn của Syscraft để host server Minecraft tại nhà - Github](https://github.com/syscraft-mc/starter-server/blob/master/README.md)
* [Lấy domain chữ thay vì <IP số của bạn> miễn phí dùng Freenom - Forum MinecraftVN](https://minecraftvn.net/tao-ip-chu-cho-server-minecraft-mien-phi-bang-freenom.t602/)
* [Hướng dẫn Port forward](https://portforward.com/), hoặc là Google `Cách mở port router <Model router của bạn>`

## Raspberry PI - Selfhost nhưng là một cực hình
Một giải pháp lý tưởng nếu bạn muốn sự tra tấn. Một chiếc Raspberry PI không thể chạy những phiên bản Minecraft mới hơn mà **không bị lược bỏ một đống tính năng**.   
Khả thi cho server từ 1~5 người, hoặc chỉ dùng để test plugin một mình bạn mà thôi.

## Nên chọn cái nào giờ ?
* Nếu bạn muốn tạo một server đàng hoàng, hãy sử dụng Dedicated Server / Shared Host  
* Nếu bạn không muốn đầu tư nhiều tiền mà vẫn muốn có server, có thể chọn Budget Host / VPS  
* Nếu bạn chỉ muốn mở server cho một số ít bạn bè chơi chung, có thể Self host / Thuê một hosting giá rẻ.  
* ~~Nếu bạn dưới 13 tuổi và không thể thuyết phục ba mẹ cho mượn thẻ tín dụng, hãy sử dụng Freehost, điển hình như youtuber Itz gì gì đó~~

Credit: [Hướng dẫn optimize server Minecraft của Eternity](https://eternity.community/index.php/paper-optimization117/#Hosting-Options)
