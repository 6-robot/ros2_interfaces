[🏠 首页](../../README.md) / [`visualization_msgs`](../README.md) / `msg` / **UVCoordinate**

# `visualization_msgs/msg/UVCoordinate`

> 网格纹理映射 UV 坐标

表示三维网格顶点在二维纹理图像上的归一化 UV 采样坐标。

## 接口定义（`.msg`）

```msg
float32 u  # 纹理水平坐标，范围 `[0.0, 1.0]`
float32 v  # 纹理垂直坐标，范围 `[0.0, 1.0]`
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `u` | `float32` | — | 纹理水平坐标，范围 `[0.0, 1.0]` |
| `v` | `float32` | — | 纹理垂直坐标，范围 `[0.0, 1.0]` |

## 使用示例

### C++ 示例

```cpp
#include "visualization_msgs/msg/uv_coordinate.hpp"

// 1. 声明消息对象
visualization_msgs::msg::UVCoordinate msg;

// 2. 对消息字段进行赋值
msg.u = 0.5f;
msg.v = 0.5f;
```

### Python 示例

```python
from visualization_msgs.msg import UVCoordinate

# 1. 声明消息对象
msg = UVCoordinate()

# 2. 对消息字段进行赋值
msg.u = 0.5
msg.v = 0.5
```

---
⬅️ [返回 `visualization_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
