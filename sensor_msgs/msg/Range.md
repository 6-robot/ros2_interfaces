[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **Range**

# `sensor_msgs/msg/Range`

> 单点超声波/红外测距传感器读数

表示沿某一圆锥视场角发射能量的单点测距传感器（如超声波、ToF 红外测距）的读数。不适用于激光雷达或声呐阵列。

## 接口定义（`.msg`）

```msg
# --- 常量定义 ---
uint8 ULTRASOUND=0  # 超声波测距
uint8 INFRARED=1  # 红外测距

# --- 字段定义 ---
std_msgs/Header header  # 测距时间戳与传感器坐标系（探测方向为 +X 轴）
uint8 radiation_type  # 探测波类型（`ULTRASOUND` 或 `INFRARED`）
float32 field_of_view  # 有效探测圆锥弧度张角 [rad]
float32 min_range  # 最小有效量程 [m]
float32 max_range  # 最大有效量程 [m]
float32 range  # 当前测距值 [m]（小于 `min_range` 可报 `-Inf`，无回波/超量程可报 `+Inf`）
float32 variance  # 测距误差方差 [m²]（较新 ROS 2 版本引入，未知填 `0` 或负值）
```

## 常量说明

| 常量名 | 类型 | 值 | 说明 |
| :--- | :--- | :--- | :--- |
| `ULTRASOUND` | `uint8` | `0` | 超声波测距 |
| `INFRARED` | `uint8` | `1` | 红外测距 |

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 测距时间戳与传感器坐标系（探测方向为 +X 轴） |
| `radiation_type` | `uint8` | — | 探测波类型（`ULTRASOUND` 或 `INFRARED`） |
| `field_of_view` | `float32` | — | 有效探测圆锥弧度张角 [rad] |
| `min_range` | `float32` | — | 最小有效量程 [m] |
| `max_range` | `float32` | — | 最大有效量程 [m] |
| `range` | `float32` | — | 当前测距值 [m]（小于 `min_range` 可报 `-Inf`，无回波/超量程可报 `+Inf`） |
| `variance` | `float32` | — | 测距误差方差 [m²]（较新 ROS 2 版本引入，未知填 `0` 或负值） |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/range.hpp"

// 1. 声明消息对象
sensor_msgs::msg::Range msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "base_link";
msg.radiation_type = sensor_msgs::msg::Range::ULTRASOUND;
msg.field_of_view = 0.26f;
msg.min_range = 0.05f;
msg.max_range = 4.0f;
msg.range = 1.35f;
msg.variance = 0.01f;
```

### Python 示例

```python
from sensor_msgs.msg import Range

# 1. 声明消息对象
msg = Range()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "base_link"
msg.radiation_type = Range.ULTRASOUND
msg.field_of_view = 0.26
msg.min_range = 0.05
msg.max_range = 4.0
msg.range = 1.35
msg.variance = 0.01
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
