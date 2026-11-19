[🏠 首页](../../README.md) / [`std_msgs`](../README.md) / `msg` / **ColorRGBA**

# `std_msgs/msg/ColorRGBA`

> 带透明度的 RGBA 颜色值

表示标准化的红、绿、蓝、透明度四通道颜色，常用于 RViz 可视化标记。

## 接口定义（`.msg`）

```msg
float32 r  # 红色通道分量，通常范围 `[0.0, 1.0]`
float32 g  # 绿色通道分量，通常范围 `[0.0, 1.0]`
float32 b  # 蓝色通道分量，通常范围 `[0.0, 1.0]`
float32 a  # Alpha 透明度分量，`0.0` 为完全透明，`1.0` 为完全不透明
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `r` | `float32` | — | 红色通道分量，通常范围 `[0.0, 1.0]` |
| `g` | `float32` | — | 绿色通道分量，通常范围 `[0.0, 1.0]` |
| `b` | `float32` | — | 蓝色通道分量，通常范围 `[0.0, 1.0]` |
| `a` | `float32` | — | Alpha 透明度分量，`0.0` 为完全透明，`1.0` 为完全不透明 |

## 使用示例

### C++ 示例

```cpp
#include "std_msgs/msg/color_rgba.hpp"

// 1. 声明消息对象
std_msgs::msg::ColorRGBA msg;

// 2. 对消息字段进行赋值
msg.r = 0.2f;
msg.g = 0.8f;
msg.b = 0.2f;
msg.a = 1.0f;
```

### Python 示例

```python
from std_msgs.msg import ColorRGBA

# 1. 声明消息对象
msg = ColorRGBA()

# 2. 对消息字段进行赋值
msg.r = 0.2
msg.g = 0.8
msg.b = 0.2
msg.a = 1.0
```

---
⬅️ [返回 `std_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
