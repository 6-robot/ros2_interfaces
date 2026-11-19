[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **MagneticField**

# `sensor_msgs/msg/MagneticField`

> 三轴磁场强度读数（磁力计）

表示磁力计或电子罗盘测得的三维磁场矢量，单位严格为特斯拉（`Tesla`，非高斯）。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 采样时间戳与磁力计坐标系
geometry_msgs/Vector3 magnetic_field  # 三轴磁场矢量 [Tesla]
float64[9] magnetic_field_covariance  # 行优先 3×3 协方差矩阵（全 0 表示未知）
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 采样时间戳与磁力计坐标系 |
| `magnetic_field` | [`geometry_msgs/Vector3`](../../geometry_msgs/msg/Vector3.md) | — | 三轴磁场矢量 [Tesla] |
| `magnetic_field_covariance` | `float64[9]` | — | 行优先 3×3 协方差矩阵（全 0 表示未知） |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/magnetic_field.hpp"

// 1. 声明消息对象
sensor_msgs::msg::MagneticField msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "imu_link";
msg.magnetic_field.x = 1.0;
msg.magnetic_field.y = 2.0;
msg.magnetic_field.z = 0.5;
msg.magnetic_field_covariance = {0.01, 0.0, 0.0, 0.0, 0.01, 0.0, 0.0, 0.0, 0.01};
```

### Python 示例

```python
from sensor_msgs.msg import MagneticField

# 1. 声明消息对象
msg = MagneticField()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "imu_link"
msg.magnetic_field.x = 1.0
msg.magnetic_field.y = 2.0
msg.magnetic_field.z = 0.5
msg.magnetic_field_covariance = [0.01, 0.0, 0.0, 0.0, 0.01, 0.0, 0.0, 0.0, 0.01]
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
