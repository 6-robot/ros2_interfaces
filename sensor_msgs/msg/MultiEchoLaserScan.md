[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **MultiEchoLaserScan**

# `sensor_msgs/msg/MultiEchoLaserScan`

> 支持多回波的 2D 激光雷达扫描数据

与 `LaserScan` 结构一致，但每个扫描角度可记录多个激光回波，适用于支持多回波检测的工业激光雷达（如 Hokuyo UTM-30LX-EW）。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 首束激光发射时间戳与雷达坐标系
float32 angle_min  # 起始扫描角度 [rad]
float32 angle_max  # 结束扫描角度 [rad]
float32 angle_increment  # 相邻扫描束的角度增量 [rad]
float32 time_increment  # 相邻激光束的时间间隔 [s]
float32 scan_time  # 两帧扫描之间的时间间隔 [s]
float32 range_min  # 最小有效测距值 [m]
float32 range_max  # 最大有效测距值 [m]
LaserEcho[] ranges  # 每个角度对应的多回波测距列表 [m]
LaserEcho[] intensities  # 每个角度对应的多回波反射强度列表
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 首束激光发射时间戳与雷达坐标系 |
| `angle_min` | `float32` | — | 起始扫描角度 [rad] |
| `angle_max` | `float32` | — | 结束扫描角度 [rad] |
| `angle_increment` | `float32` | — | 相邻扫描束的角度增量 [rad] |
| `time_increment` | `float32` | — | 相邻激光束的时间间隔 [s] |
| `scan_time` | `float32` | — | 两帧扫描之间的时间间隔 [s] |
| `range_min` | `float32` | — | 最小有效测距值 [m] |
| `range_max` | `float32` | — | 最大有效测距值 [m] |
| `ranges` | [`LaserEcho`](./LaserEcho.md)`[]` | — | 每个角度对应的多回波测距列表 [m] |
| `intensities` | [`LaserEcho`](./LaserEcho.md)`[]` | — | 每个角度对应的多回波反射强度列表 |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/multi_echo_laser_scan.hpp"

// 1. 声明消息对象
sensor_msgs::msg::MultiEchoLaserScan msg;

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
sensor_msgs::msg::LaserEcho laser_echo;
laser_echo.echoes = {1.8f, 3.4f};
msg.ranges.push_back(laser_echo);
sensor_msgs::msg::LaserEcho laser_echo_2;
laser_echo_2.echoes = {1.8f, 3.4f};
msg.intensities.push_back(laser_echo_2);
```

### Python 示例

```python
from sensor_msgs.msg import LaserEcho, MultiEchoLaserScan

# 1. 声明消息对象
msg = MultiEchoLaserScan()

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
laser_echo = LaserEcho()
laser_echo.echoes = [1.8, 3.4]
msg.ranges.append(laser_echo)
laser_echo_2 = LaserEcho()
laser_echo_2.echoes = [1.8, 3.4]
msg.intensities.append(laser_echo_2)
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
