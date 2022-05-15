## Profiler là gì ?

Profiler là công cụ giúp bạn kiểm tra và phân tích những tác vụ, ứng dụng, hoạt động đang sử dụng tài nguyên của hệ thống. Profiler cho bạn biết về lượng tài nguyên sử dụng, thời gian xử lý..

Minecraft cũng có những công cụ Profiler riêng như sau

## Timings v2

Timings được viết bởi Aikar (developer của [Paper](https://papermc.io) và một số dự án nổi tiếng khác), được tích hợp sẵn trong Paper

## spark

[spark](https://spark.lucko.me/) được viết bởi lucko (cũng là developer của [LuckPerms](https://luckperms.net)), dựa trên [WarmRoast](https://github.com/sk89q/warmroast) của sk89q (developer của [WorldEdit](https://enginehub.org/worldedit/), [WorldGuard](https://enginehub.org/worldguard/).. và [Bukkit](https://bukkit.org)). spark không được tích hợp sẵn mà là dưới dạng plugins, spark hỗ trợ các nền tảng như Bukkit, Fabric, Client.. Hỗ trợ nhiều chức năng như Memory Inspection, tạo heap dumps..

!!! info "Lưu ý"
    spark chạy tốt và hiệu quả nhất ở hệ điều hành nhân Linux

## Cách sử dụng

### Timings v2

Gõ lệnh sau trong server hoặc console, Timings sẽ được kích hoạt

```
/timings on
```

Để Timings chạy trong khoảng 10 phút, sau đó gõ lệnh sau để lấy kết quả

```
/timings paste
```

### spark

Gõ lệnh sau trong server hoặc console, spark sẽ được kích hoạt

```
/spark profiler --start
```

Hoặc bạn có thể dùng lệnh sau để spark tự ngừng sau x giây

```
/spark profiler --timeout <số giây>
```

Để lấy kết quả, gõ lệnh

```
/spark profiler --stop
```

Hướng dẫn chi tiết về spark có thể xem [tại đây](https://spark.lucko.me/docs)
