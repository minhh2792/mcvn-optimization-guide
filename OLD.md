## Tối ưu hoá Server Minecraft

Đây là các kinh nghiệm cá nhân mình đúc kết được sau hơn 4 năm làm server. Các bạn mới bắt đầu có thể lấy tài liệu này để tham khảo, tất nhiên nó sẽ không thể cải thiện hiệu năng một cách xuất sắc.

## Mục lục 

 **A.**
 
- [Phần I. Lựa chọn phần cứng](#hardware)
- [Phần II. Lựa chọn Minecraft Server Software](#software)
- [Phần III. Tinh chỉnh run.bat](#batch)

**B.**

- [Phần I. Tinh chỉnh bukkit.yml](#bukkit)
- [Phần II. Tinh chỉnh spigot.yml](#spigot)
- [Phần III. Tinh chỉnh paper.yml](#paper)
- [Phần IV. Tinh chỉnh server.properties](#server-properties)
- [Phần V. Tinh chỉnh purpur.yml](#purpur)
- [Phần VI. Tinh chỉnh airplane.yml](#airplane)
- [Phần VII. Các mẹo khác](#tips)
  
## Giải thích thuật ngữ và phân loại lag

> Giải thích các thuật ngữ được dùng trong bài, tìm hiểu về server lag, connection lag và client lag

**A. Giải thích thuật ngữ**

- **TPS**: Viết tắt của **Tick Per Second**. Minecraft chạy trên 20 tick - mỗi giây bằng 20 tick. Có thể hiểu TPS càng cao thì càng mượt.

- **Timings Report**: Công cụ phân tích server, được tích hợp sẵn. Giúp bạn biết được trong một khoảng thời gian nào đó, máy chủ xử lí tác vụ nào, trong thời gian bao lâu, chủ yếu giúp bạn kiểm tra hiệu năng của server.

- **Minecraft Server Software**: Phần mềm dùng để chạy server, ví dụ: Spigot, Paper, Bukkit...

- **Ping**: Khoảng thời gian giữa việc người chơi "gửi" một thông tin nào đó lên server và server "trả về" thông tin tương ứng. Nói ngắn gọn là độ trễ của việc trao đổi thông tin giữa server và người chơi.

- **FPS**: Viết tắt của **Frame Per Second** - số khung hình một giây.

**B. Phân loại lag**

**TPS - Server lag** 

Để đánh giá độ mượt của server, có một thuật ngữ được sử dụng là **TPS** (đã giải thích ở phần I). Việc giữ TPS cao là cực kì cần thiết, nó là yếu tố quyết định đến hiệu năng và cả player base khi không ai muốn chơi các server quá lag.

|TPS|Ảnh hưởng |
|--|--|
|20|Mức TPS cao nhất và ổn định nhất. Các tác vụ như chunk generation sẽ cực kì mượt và nhanh.|
|19.95 -> 19.99|Mức TPS tốt, hầu hết các server đều nằm trong khoảng này. Các tác vụ kể trên vẫn còn rất nhanh và mượt.|
|18.5 -> 19.94|Mức TPS trung bình, lag có thể xuất hiện.|
|16 -> 18.4|Mức TPS yếu, lag xuất hiện rõ rệt. Các tác vụ bị delay, chunk generation không được nhanh.|
|< 16|Mất ổn định, không chơi được.|

**Ping - Connection lag**

|Ping|Ảnh hưởng|
|--|--|
|1 -> 90|Mượt nhất.|
|91 -> 179|Tốt, một số server PvP có thể hơi khó chịu.|
|180 -> 299|Kém, lag rõ rệt ở các tác vụ như tương tác với block, người chơi.|
|299+|Cực kém, hầu như không thể chơi được.|

**FPS - Client lag**

Hầu hết các hướng dẫn hiện tại đều chỉ người chơi đặt FPS ở mức Unlimited - Không giới hạn. Tuy nhiên, việc đặt ở mức Unlimited thực sự không nên vì sẽ tiêu tốn quá nhiều tài nguyên máy tính chỉ dành cho việc cố gắng đạt FPS càng cao càng tốt. Khuyến khích giới hạn FPS ở mức vừa phải để chừa tài nguyên cho máy tính thực hiện những tác vụ khác. (80 - 100 FPS là con số giới hạn FPS lí tưởng để gameplay không bị ảnh hưởng)

|FPS|Ảnh hưởng|
|--|--|
|60+|FPS tốt cho Minecraft.|
|40 -> 59|FPS ổn, không có vấn đề gì.|
|30 -> 15|FPS thấp, lag rõ rệt.|
|1 -> 10|Quá thấp, bạn nên nâng cấp phần cứng.| 

<h1 align="center">A.</h1>

<h1 name="hardware">Phần I. Lựa chọn phần cứng</h1>  

> Phần cứng ảnh hưởng rất nhiều đến hiệu năng  

**A. Lựa chọn CPU**  

Nhiều người nghĩ rằng, chọn CPU có nhiều core là sẽ không bao giờ bị lag. Điều này hoàn toàn sai, thứ ảnh hưởng đến hiệu năng sẽ là khả năng xử lý đơn nhân của CPU đó. Minecraft chạy trên 1 nhân đồng nghĩa nó cũng sẽ chỉ dùng 1 nhân trong CPU, việc lựa chọn CPU có hiệu năng đơn nhân tốt có thể cải thiện về hiệu năng. Ngoài ra, nếu server bạn chạy đa luồng thì một CPU có nhiều core với hiệu năng, xung nhịp tốt là rất ổn.  

[Danh sách CPU đơn nhân](https://www.cpubenchmark.net/singleThread.html)  

**B. Lựa chọn RAM**  

Về RAM, theo kinh nghiệm cá nhân thì dung lượng RAM ít nhất là 8GB. Tất nhiên các bạn có thể tự cân đo đong đếm cho phù hợp. RAM có xung nhịp cao cũng ảnh hưởng ít nhiều đến hiệu năng. 

<h1 name="software">Phần II. Minecraft Server Software</h1>  

> Chọn phần mềm thích hợp làm nền tảng để chạy server 

Theo mình, một server software tốt phải thoả mãn các yêu cầu sau:  

- **Cộng đồng người dùng đông đảo**  

- **Được làm ra bởi các lập trình viên có kinh nghiệm**  

- **Tương thích ổn định**  

- **Tối ưu tốt, API rộng**  

✅Mình gơi ý dùng các bản sau đây  

- **[PaperMC](https://github.com/PaperMC/Paper): Bản fork của Spigot khá nổi tiếng. Cải thiện rất nhiều về hiệu năng lẫn gameplay, mechanic.**
  
- **[Tuinity](https://github.com/Spottedleaf/Tuinity): Bản fork của PaperMC, hướng tới việc tối ưu server.**  

- **[Airplane](https://github.com/Technove/Airplane): Bản fork của Tuinity, hướng tới việc tối ưu server.**  

- **[Purpur](https://github.com/pl3xgaming/Purpur): Bản fork của Airplane, cho khả năng tùy biến tính năng nhiều hơn.**  

**❗Lưu ý: Không dùng Spigot/Craftbukkit hay bất kì bản fork/custom nào "đA lUồNg tỚi 99%"**  
 
<h1 name="batch">Phần III. Tinh chỉnh run.bat</h1>  

> Tùy chỉnh lại thành phần bên trong file run.bat một cách hiệu quả nhất  

Mình khuyên các bạn nên sử dụng Aikar's Flags, đây là flag đã được dùng rộng rãi trên các server lớn. Hãy copy ở bên dưới vì bản gốc không có encoding UTF-8 giúp hiện kí tự tiếng Việt:

`java -Dfile.encoding=utf-8 -Xms10G -Xmx10G -XX:+UseG1GC -XX:+ParallelRefProcEnabled -XX:MaxGCPauseMillis=200 -XX:+UnlockExperimentalVMOptions -XX:+DisableExplicitGC -XX:+AlwaysPreTouch -XX:G1NewSizePercent=30 -XX:G1MaxNewSizePercent=40 -XX:G1HeapRegionSize=8M -XX:G1ReservePercent=20 -XX:G1HeapWastePercent=5 -XX:G1MixedGCCountTarget=4 -XX:InitiatingHeapOccupancyPercent=15 -XX:G1MixedGCLiveThresholdPercent=90 -XX:G1RSetUpdatingPauseTimePercent=5 -XX:SurvivorRatio=32 -XX:+PerfDisableSharedMem -XX:MaxTenuringThreshold=1 -Dusing.aikars.flags=https://mcflags.emc.gs -Daikars.new.flags=true -jar paperclip.jar nogui`

**❗Lưu ý: Bạn chỉnh lại giá trị Xmx và Xms (nhớ để bằng nhau). Trường hợp dùng nhiều hơn 12GB tinh chỉnh lại giá trị các flag dưới đây:**  

`-XX:G1NewSizePercent=40
-XX:G1MaxNewSizePercent=50-XX:G1HeapRegionSize=16M-XX:G1ReservePercent=15-XX:InitiatingHeapOccupancyPercent=20`

<h1 align="center">B</h1>  

<h1 name="bukkit">Phần I. Tinh chỉnh bukkit.yml</h1>  

> Vào file bukkit.yml và chỉnh như sau  

|Cài đặt|Giá trị|
|--|--|
|chunk-gc.period-in-ticks|400|U
|ticks-per.(type)-spawns|monster:5, water:11, water-ambient:21, ambient:31|Đ
 
<h1 name="spigot">Phần II. Tinh chỉnh spigot.yml</h1>  

> Vào file spigot.yml và chỉnh như sau

|Cài đặt|Giá trị|
|--|--|
|save-user-cache-on-stop-only|true|
|max-tick-time|tile:1000, entity:1000|
|mob-spawn-range|6|
|entity-activation-range|animals: 16`, `monsters: 24`, `raiders: 48`, `misc: 8`, `water: 8`, `villagers: 16`, `flying-monsters: 48`|
|tick-inactive-villagers|false|
|merge-radius|item:4.0, exp:6.0|
|arrow-despawn-rate|300|
|view-distance|4|
|entity-tracking-range|`players: 48`, `animals: 48`, `monsters: 48`, `misc: 32`, `other: 64`|
|hopper-transfer|8|
|hopper-check|8|


<h1 name="paper">Phần III. Tinh chỉnh paper.yml</h1>

> Vào file paper.yml và chỉnh như sau

|Cài đặt|Giá trị|
|--|--|
|max-auto-save-chunks-per-tick|6|
|optimize-explosions|true|
|mob-spawner-tick-rate|2|
|disable-chest-cat-detection|true|
|container-update-tick-rate|3|
|max-entity-collisions|2|
|grass-spread-tick-rate|4|
|despawn-ranges|soft: 28, hard: 96|
|hopper.disable-move-event|true|
|non-player-arrow-despawn-rate|60|
|creative-arrow-despawn-rate|60|
|prevent-moving-into-unloaded-chunks|true|
|use-faster-eigencraft-redstone|true|
|armor-stands-tick|false|
|per-player-mob-spawns|true|
|alt-item-despawn-rate|true|
|anti-xray.enabled|true|
|remove-corrupt-tile-entities|true|
|nether-ceiling-void-damage-height|127|
|no-tick-view-distance|7|
|delay-chunk-unloads-by|10|
|seed-based-feature-search-loads-chunks|true|
|update-pathfinding-on-block-update|false|
|fix-climbing-bypassing-cramming-rule|true
|use-faster-eigencraft-redstone|true|
|disable-move-event|false|
|treasure-maps-return-already-discovered|true
|entity-per-chunk-save-limit|`experience_orb: 16`, `arrow: 16`, `dragonfireball: 3`, `egg: 8`, `ender_pearl: 8`, `fireball: 8`, `firework: 8`, `largefireball: 8`, `lingeringpotion: 8`, `llamaspit: 3`, `shulkerbullet: 8`, `sizedfireball: 8`, `snowball: 8`, `spectralarrow: 16`, `splashpotion: 3`, `thrownexpbottle: 3`, `trident: 16`, `witherskull: 4`|

<h1 name="server-properties">Phần IV. Tinh chỉnh server.properties</h1>  

> Mở file server.properties và chỉnh như sau

|Cài đặt|Giá trị|
|--|--|
|view-distance|5| 

<h1 name="purpur">Phần V. Tinh chỉnh purpur.yml</h1>

> Mở file purpur.yml và chỉnh như sau

|Cài đặt|Giá trị|
|--|--|
|use-alternate-keepalive|true| 
|dont-send-useless-entity-packets|true|
|aggressive-towards-villager-when-lagging|false|
|entities-can-use-portals|false|
|villager.brain-ticks|2|
|villager.lobotomize|true|
|disable-treasure-searching|true|
|teleport-if-outside-border|true|

<h1 name="airplane">Phần VI. Tinh chỉnh airplane.yml</h1>

> Mở file airplane.yml và chỉnh như sau

|Cài đặt|Giá trị|
|--|--|
|max-loads-per-projectile|8| 
|max-tick-freq|20|
|activation-dist-mod|7|

<h1 name="tips">Phần VII. Các kinh nghiệm khác</h1>

- Nói về số RAM cấp cho mỗi server, một server lag có thể là do dung lượng RAM được cấp quá ít, nhưng một server được cấp *quá nhiều dung lượng RAM* sẽ không khiến cho server của bạn không bao giờ lag. Chỉ nên cấp một lượng RAM đủ cho server hoạt động không lag, cung cấp quá nhiều sẽ là một sự lãng phí tài nguyên vô ích.  

- Mỗi gamemode sẽ có một cách tối ưu khác nhau. Đây chỉ là cách tối ưu có thể áp dụng chung cho hầu hết các server.  

<h1 align="center">Giúp đỡ</h1>

Nếu bạn cần giúp đỡ thêm, hãy liên hệ qua [Facebook](https://facebook.com/minhh2792) của mình

<h1 align="center">Lời kết</h1>  

Trong đây có thể có một số sai sót, có thể do nguyên nhân chủ quan hoặc khách quan. Hãy thoải mái contribute vào đây nhé 😉

**Các nguồn tham khảo**

 - [Tuning the JVM – G1GC Garbage Collector Flags for Minecraft](https://aikar.co/2018/07/02/tuning-the-jvm-g1gc-garbage-collector-flags-for-minecraft/)

- [[GUIDE] Server Optimization⚡](https://www.spigotmc.org/threads/guide-server-optimization%E2%9A%A1.283181/)


Được lấy ý tưởng từ [đây](https://github.com/YouHaveTrouble/minecraft-optimization)  
