[🏠 首页](../../README.md) / [`shape_msgs`](../README.md) / `msg` / **Plane**

# `shape_msgs/msg/Plane`

> 三维空间无限平面方程

使用一般式平面方程 $ax + by + cz + d = 0$ 表示三维空间中的无限大平面。

## 接口定义（`.msg`）

```msg
float64[4] coef  # 平面方程系数 `[a, b, c, d]`
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `coef` | `float64[4]` | — | 平面方程系数 `[a, b, c, d]` |

## 使用示例

### C++ 示例

```cpp
#include "shape_msgs/msg/plane.hpp"

// 1. 声明消息对象
shape_msgs::msg::Plane msg;

// 2. 对消息字段进行赋值
msg.coef = {0.0, 0.0, 1.0, -1.0};
```

### Python 示例

```python
from shape_msgs.msg import Plane

# 1. 声明消息对象
msg = Plane()

# 2. 对消息字段进行赋值
msg.coef = [0.0, 0.0, 1.0, -1.0]
```

---
⬅️ [返回 `shape_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
