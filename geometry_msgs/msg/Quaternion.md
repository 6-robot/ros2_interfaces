[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **Quaternion**

# `geometry_msgs/msg/Quaternion`

> 三维旋转单位四元数

以四元数形式表示自由空间中的三维姿态旋转，默认初始化为单位四元数（无旋转）。

## 接口定义（`.msg`）

```msg
float64 x 0  # 四元数虚部 `i` 分量（默认值 `0`）
float64 y 0  # 四元数虚部 `j` 分量（默认值 `0`）
float64 z 0  # 四元数虚部 `k` 分量（默认值 `0`）
float64 w 1  # 四元数实部标量分量（默认值 `1`）
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `x` | `float64` | `0` | 四元数虚部 `i` 分量（默认值 `0`） |
| `y` | `float64` | `0` | 四元数虚部 `j` 分量（默认值 `0`） |
| `z` | `float64` | `0` | 四元数虚部 `k` 分量（默认值 `0`） |
| `w` | `float64` | `1` | 四元数实部标量分量（默认值 `1`） |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/quaternion.hpp"

// 1. 声明消息对象
geometry_msgs::msg::Quaternion msg;

// 2. 对消息字段进行赋值
msg.x = 0.0;
msg.y = 0.0;
msg.z = 0.0;
msg.w = 1.0;
```

### Python 示例

```python
from geometry_msgs.msg import Quaternion

# 1. 声明消息对象
msg = Quaternion()

# 2. 对消息字段进行赋值
msg.x = 0.0
msg.y = 0.0
msg.z = 0.0
msg.w = 1.0
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
