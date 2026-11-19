[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **Pose**

# `geometry_msgs/msg/Pose`

> 三维空间位姿（位置 + 姿态）

由三维位置点 `position` 和四元数朝向 `orientation` 组成，表示刚体在自由空间中的完整位姿。

## 接口定义（`.msg`）

```msg
Point position  # 三维空间位置坐标 [m]
Quaternion orientation  # 三维旋转姿态四元数
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `position` | [`Point`](./Point.md) | — | 三维空间位置坐标 [m] |
| `orientation` | [`Quaternion`](./Quaternion.md) | — | 三维旋转姿态四元数 |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/pose.hpp"

// 1. 声明消息对象
geometry_msgs::msg::Pose msg;

// 2. 对消息字段进行赋值
msg.position.x = 1.0;
msg.position.y = 2.0;
msg.position.z = 0.5;
msg.orientation.x = 0.0;
msg.orientation.y = 0.0;
msg.orientation.z = 0.0;
msg.orientation.w = 1.0;
```

### Python 示例

```python
from geometry_msgs.msg import Pose

# 1. 声明消息对象
msg = Pose()

# 2. 对消息字段进行赋值
msg.position.x = 1.0
msg.position.y = 2.0
msg.position.z = 0.5
msg.orientation.x = 0.0
msg.orientation.y = 0.0
msg.orientation.z = 0.0
msg.orientation.w = 1.0
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
