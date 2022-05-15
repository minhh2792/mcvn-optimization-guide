Giải thích các thuật ngữ được sử dụng

## Tick

Minecraft chạy trên một program loop, mỗi "tick" xảy ra, game (và server) sẽ xử lý những công việc như:

- Tín hiệu đá đỏ
- Tín hiệu người chơi (Di chuyển, đập phá block..)
- Xử lý packet
- Spawn quái, xử lý Mob AI, pathfinding

... và còn rất nhiều

## TPS

Viết tắt của Tick Per Second, Minecraft chạy ổn định ở 20 TPS, tương đương 50ms. TPS càng thấp sẽ khiến server càng lag, delay

## MSPT

Viết tắt của milliseconds per tick, là thời gian game cần để xử lý 1 tick (trong số 20 tick kia). MSPT ổn định sẽ thấp hơn hoặc bằng 50ms
