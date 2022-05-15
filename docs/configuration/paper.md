Trong phần này sẽ hướng dẫn bạn tùy chỉnh lại file paper.yml

### world-settings.default

#### prevent-moving-into-unloaded-chunks

- **Mô tả**: Ngăn không cho người chơi đi vào chunk chưa được load
- **Mặc định**: `false`
- **Khuyến nghị**: `true`

#### despawn-ranges

- **Mô tả**: Cho phép tùy chỉnh khoảng cách tính bằng block mà mob sẽ despawn khi cách xa người chơi
- **Khuyến nghị**:

  ```
      monster:
          soft: 30
          hard: 60
      creature:
          soft: 30
          hard: 60
      ambient:
          soft: 30
          hard: 60
      axolotls:
          soft: 30
          hard: 60
      underground_water_creature:
          soft: 30
          hard: 60
      water_creature:
          soft: 30
          hard: 60
      water_ambient:
          soft: 30
          hard: 60
      misc:
          soft: 30
          hard: 60
  ```

#### optimize-explosions

- **Mô tả**: Cache entity lookups thay vì tính toán lại trong suốt lúc nổ
- **Mặc định**: `false`
- **Khuyến nghị**: `true`

#### redstone-implementation

- **Mô tả**: Sử dụng thuật toán redstone khác thay cho thuật toán vanilla
- **Mặc định**: `vanilla`
- **Khuyến nghị**: `alternate-current`

#### entity-per-chunk-save-limit

- **Mô tả**: Đặt giới hạn bao nhiêu entity của mỗi loại được lưu
- **Khuyến nghị**:

  ```
      experience_orb: 16
      arrow: 16
      dragon_fireball: 3
      egg: 8
      ender_pearl: 8
      eye_of_ender: 8
      fireball: 8
      small_fireball: 8
      firework_rocket: 8
      potion: 8
      llama_spit: 3
      shulker_bullet: 8
      snowball: 8
      spectral_arrow: 16
      experience_bottle: 3
      trident: 16
      wither_skull: 4
      area_effect_cloud: 8
  ```
