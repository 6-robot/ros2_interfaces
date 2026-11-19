[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **Transform**

# `geometry_msgs/msg/Transform`

> 三维坐标系刚体变换

描述两个坐标系之间的平移与旋转变换关系（子坐标系相对于父坐标系）。

## 接口定义（`.msg`）

```msg
Vector3 translation  # 平移向量 [m]
Quaternion rotation  # 旋转四元数
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `translation` | [`Vector3`](./Vector3.md) | — | 平移向量 [m] |
| `rotation` | [`Quaternion`](./Quaternion.md) | — | 旋转四元数 |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/transform.hpp"

// 1. 声明消息对象
geometry_msgs::msg::Transform msg;

// 2. 对消息字段进行赋值
msg.translation.x = 1.0;
msg.translation.y = 2.0;
msg.translation.z = 0.5;
msg.rotation.x = 0.0;
msg.rotation.y = 0.0;
msg.rotation.z = 0.0;
msg.rotation.w = 1.0;
```

### Python 示例

```python
from geometry_msgs.msg import Transform

# 1. 声明消息对象
msg = Transform()

# 2. 对消息字段进行赋值
msg.translation.x = 1.0
msg.translation.y = 2.0
msg.translation.z = 0.5
msg.rotation.x = 0.0
msg.rotation.y = 0.0
msg.rotation.z = 0.0
msg.rotation.w = 1.0
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
