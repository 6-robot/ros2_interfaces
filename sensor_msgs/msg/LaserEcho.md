[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **LaserEcho**

# `sensor_msgs/msg/LaserEcho`

> 单束激光的多回波测距/强度值

记录 `MultiEchoLaserScan` 中同一发射角度下返回的多个激光回波值（如穿透玻璃、雨雾或树叶时的前后回波）。

## 接口定义（`.msg`）

```msg
float32[] echoes  # 同一激光束按返回顺序排列的多个测距值 [m] 或反射强度值
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `echoes` | `float32[]` | — | 同一激光束按返回顺序排列的多个测距值 [m] 或反射强度值 |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/laser_echo.hpp"

// 1. 声明消息对象
sensor_msgs::msg::LaserEcho msg;

// 2. 对消息字段进行赋值
msg.echoes = {1.8f, 3.4f};
```

### Python 示例

```python
from sensor_msgs.msg import LaserEcho

# 1. 声明消息对象
msg = LaserEcho()

# 2. 对消息字段进行赋值
msg.echoes = [1.8, 3.4]
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
