## Tối ưu hoá Server Minecraft

> Đây là các kinh nghiệm cá nhân mình đúc kết được sau hơn 4 năm làm server. Các bạn mới bắt đầu có thể lấy tài liệu này để tham khảo, tất nhiên nó sẽ không thể cải thiện hiệu năng một cách xuất sắc.

## Mục lục

**Khởi đầu**

 - [Phần I. Lựa chọn phần cứng](#p1)
 - [Phần II. Lựa chọn Minecraft Server Software](#p2) 
 - [Phần III. Tinh chỉnh run.bat](#p3)

## Giải thích thuật ngữ và phân loại lag

> Giải thích các thuật ngữ được dùng trong bài, tìm hiểu về server lag, connection lag và client lag

**A. Giải thích thuật ngữ**

 - **TPS**: Viết tắt của **Tick Per Second**, Minecraft chạy trên 20 tick. Mỗi giây bằng 20 tick, có thể hiểu TPS càng cao thì càng mượt.

 - **Timings Report**: Công cụ phân tích server, được tích hợp sẵn. Có tác dụng cung cấp thông tin chi tiết về hiệu năng.

 - **Minecraft Server Software**: Phần mềm dùng để chạy server, ví dụ: Spigot, Paper, Bukkit......
 
 **B. Phân loại lag**
 
 Để đánh giá độ mượt của server, có một thuật ngữ được sử dụng là **TPS** (đã giải thích ở phần I). Việc giữ TPS cao là cực kì cần thiết, nó là yếu tố quyết định đến hiệu năng và cả player base khi không ai muốn chơi các server quá lag.

* **TPS 20**: Mức TPS cao nhất và ổn định nhất. Các tác vụ như chunk generation sẽ cực kì mượt và nhanh.

* **TPS 19.95 -> 19.99**: Mức TPS tốt, hầu hết các server đều nằm trong khoảng này. Các tác vụ kể trên vẫn còn rất nhanh và mượt.

* **TPS 18.5 ->19.94**: Mức TPS trung bình, lag có thể xuất hiện.

* **TPS 16 -> 18.4**: Mức TPS yếu, lag xuất hiện rõ rệt. Các tác vụ bị delay, chunk generation không được nhanh.

* **TPS dưới 16**: Mất ổn định, không chơi được. 

**Ping - Connection Lag**

Ping là độ trễ mà dữ liệu đi từ phía server đến client. Việc bạn chọn host server ở khu vực gần với member của bạn (Việt Nam, Singapore) sẽ giúp ping thấp hơn.

* **1 -> 90ms**: Mượt nhất.

* **91 -> 179ms**: Tốt, một số server PvP có thể hơi khó chịu.

* **180 -> 299ms**: Kém, lag rõ rệt ở các tác vụ như tương tác với block, người chơi.

* **299+ms**: Cực kém, hầu như không thể chơi được.

**FPS - Client Lag**

FPS là số khung hình một giây, hiểu đơn giản càng cao game của bạn sẽ càng mượt. Cách tăng FPS và hiệu năng của game không được đề cập ở đây. Lưu ý rằng đây là lag về phía client side, không phải server.

* **60+FPS**: FPS tốt cho Minecraft.

* **40 -> 59FPS**: FPS ổn, không có vấn đề gì.

* **30 -> 15FPS**: FPS thấp, lag rõ rệt.

* **1 -> 10FPS**: Quá thấp, bạn nên nâng cấp phần cứng

<h1 align="center">Khởi đầu</h1>
 
<h1 name="p1">Phần I. Lựa chọn phần cứng</h1> 

> Phần cứng ảnh hưởng rất nhiều đến hiệu năng

**A. Lựa chọn CPU**

 Nhiều người nghĩ rằng, chọn CPU có nhiều core là sẽ không bao giờ bị lag. Điều này hoàn toàn sai, thứ ảnh hưởng đến hiệu năng sẽ là khả năng xử lý đơn nhân của CPU đó. Minecraft chạy trên 1 nhân đồng nghĩa nó cũng sẽ chỉ dùng 1 nhân trong CPU, việc lựa chọn CPU có hiệu năng đơn nhân tốt có thể cải thiện về hiệu năng. Ngoài ra, nếu server bạn chạy đa luồng thì một CPU có nhiều core với hiệu năng, xung nhịp tốt là rất ổn.

 [Danh sách CPU đơn nhân](https://www.cpubenchmark.net/singleThread.html)

**B. Lựa chọn RAM**

Về RAM, theo kinh nghiệm cá nhân thì dung lượng RAM ít nhất là 8GB. Tất nhiên các bạn có thể tự cân đo đong đếm cho phù hợp. RAM có xung nhịp cao cũng ảnh hưởng ít nhiều đến hiệu năng.

<h1 name="p2">Phần II. Minecraft Server Software</h1> 

> Công việc cần thiết khi tạo server

Theo mình, một server software tốt phải thoả mãn các yêu cầu sau:

 - **Cộng đồng người dùng đông đảo**

 - **Được code bởi các lập trình viên có kinh nghiệm**

 - **Tương thích ổn định**

- **Tối ưu tốt, API rộng**

✅Mình gơi ý dùng các bản sau đây

- **[PaperMC](https://github.com/PaperMC/Paper): Bản fork của Spigot khá nổi tiếng. Cải thiện rất nhiều về hiệu năng lẫn gameplay, mechanic.** 

- **[Tuinity](https://github.com/Spottedleaf/Tuinity): Bản fork của PaperMC, hướng tới việc tối ưu server.**

- **[Airplane](https://github.com/Technove/Airplane): Bản fork của Tuinity, hướng tới việc tối ưu server.**

- **[Purpur](https://github.com/pl3xgaming/Purpur): Bản fork của Airplane, cho khả năng tùy biến tính năng nhiều hơn.**

**❗Lưu ý: Không dùng Spigot/Craftbukkit**

<h1 name="p3">Phần III. Tinh chỉnh run.bat</h1> 

> Tùy chỉnh lại thành phần bên trong file run.bat một cách hiệu quả nhất

Mình khuyên các bạn nên sử dụng Aikar's Flags, đây là flag đã được dùng rộng rãi trên các server lớn:

> java -Xms10G -Xmx10G -XX:+UseG1GC -XX:+ParallelRefProcEnabled -XX:MaxGCPauseMillis=200 -XX:+UnlockExperimentalVMOptions -XX:+DisableExplicitGC -XX:+AlwaysPreTouch -XX:G1NewSizePercent=30 -XX:G1MaxNewSizePercent=40 -XX:G1HeapRegionSize=8M -XX:G1ReservePercent=20 -XX:G1HeapWastePercent=5 -XX:G1MixedGCCountTarget=4 -XX:InitiatingHeapOccupancyPercent=15 -XX:G1MixedGCLiveThresholdPercent=90 -XX:G1RSetUpdatingPauseTimePercent=5 -XX:SurvivorRatio=32 -XX:+PerfDisableSharedMem -XX:MaxTenuringThreshold=1 -Dusing.aikars.flags=https://mcflags.emc.gs -Daikars.new.flags=true -jar paperclip.jar nogui

**❗Lưu ý: Bạn chỉnh lại giá trị Xmx và Xms (nhớ để bằng nhau). Trường hợp dùng nhiều hơn 12GB tinh chỉnh lại giá trị các flag dưới đây:**

> -XX:G1NewSizePercent=40
-XX:G1MaxNewSizePercent=50-XX:G1HeapRegionSize=16M-XX:G1ReservePercent=15-XX:InitiatingHeapOccupancyPercent=20

<h1 align="center">Nâng cao</h1>

<h1 name="p4">Phần I. Tinh chỉnh bukkit.yml</h1> 

> Vào file bukkit.yml và chỉnh như sau

|Cài đặt |Giá trị  |
|--|--|
|chunk-gc.period-in-ticks  |400  |
|ticks-per.(type)-spawns |monster:5, water:11, water-ambient:21, ambient:31 |
|autosave |6000 | 

còn tiếp...

Trong đây có thể có một số sai sót, có thể do nguyên nhân chủ quan hoặc khách quan. Hãy thoải mái contribute vào đây nhé 😉

Được lấy ý tưởng từ [đây](https://github.com/YouHaveTrouble/minecraft-optimization)

**Sponsor**: [Thecaofast](https://thecaofast.net)

![](https://minhh2792.github.io/banner.gif)
