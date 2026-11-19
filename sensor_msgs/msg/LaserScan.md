[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **LaserScan**

# `sensor_msgs/msg/LaserScan`

> 单线（2D）平面激光雷达扫描数据

表示 2D 激光雷达完成单帧平面扫描的极坐标距离与强度读数，按逆时针（绕 +Z 轴）从 `angle_min` 扫至 `angle_max`。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 第一束激光发射的时间戳与激光雷达坐标系
float32 angle_min  # 起始扫描角度 [rad]
float32 angle_max  # 结束扫描角度 [rad]
float32 angle_increment  # 相邻两束激光的角度步进增量 [rad]
float32 time_increment  # 相邻两次测距的时间间隔 [s]（用于运动畸变补偿）
float32 scan_time  # 相邻两帧完整扫描之间的时间间隔 [s]
float32 range_min  # 雷达最小有效量程 [m]
float32 range_max  # 雷达最大有效量程 [m]
float32[] ranges  # 测距读数数组 [m]（超出 `[range_min, range_max]` 或 `Inf`/`NaN` 应丢弃）
float32[] intensities  # 反射强度数组（与设备相关；若设备不提供则为空数组）
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 第一束激光发射的时间戳与激光雷达坐标系 |
| `angle_min` | `float32` | — | 起始扫描角度 [rad] |
| `angle_max` | `float32` | — | 结束扫描角度 [rad] |
| `angle_increment` | `float32` | — | 相邻两束激光的角度步进增量 [rad] |
| `time_increment` | `float32` | — | 相邻两次测距的时间间隔 [s]（用于运动畸变补偿） |
| `scan_time` | `float32` | — | 相邻两帧完整扫描之间的时间间隔 [s] |
| `range_min` | `float32` | — | 雷达最小有效量程 [m] |
| `range_max` | `float32` | — | 雷达最大有效量程 [m] |
| `ranges` | `float32[]` | — | 测距读数数组 [m]（超出 `[range_min, range_max]` 或 `Inf`/`NaN` 应丢弃） |
| `intensities` | `float32[]` | — | 反射强度数组（与设备相关；若设备不提供则为空数组） |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/laser_scan.hpp"

// 1. 声明消息对象
sensor_msgs::msg::LaserScan msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "laser_frame";
msg.angle_min = -1.57f;
msg.angle_max = 1.57f;
msg.angle_increment = 0.01745f;
msg.time_increment = 0.0001f;
msg.scan_time = 0.1f;
msg.range_min = 0.1f;
msg.range_max = 12.0f;
msg.ranges = {1.2f, 1.5f, 2.3f, 3.1f};
msg.intensities = {100.0f, 120.0f, 95.0f, 80.0f};
```

### Python 示例

```python
from sensor_msgs.msg import LaserScan

# 1. 声明消息对象
msg = LaserScan()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "laser_frame"
msg.angle_min = -1.57
msg.angle_max = 1.57
msg.angle_increment = 0.01745
msg.time_increment = 0.0001
msg.scan_time = 0.1
msg.range_min = 0.1
msg.range_max = 12.0
msg.ranges = [1.2, 1.5, 2.3, 3.1]
msg.intensities = [100.0, 120.0, 95.0, 80.0]
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
