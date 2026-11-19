[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **ChannelFloat32**

# `sensor_msgs/msg/ChannelFloat32`

> 旧版点云附加属性通道

作为 `sensor_msgs/PointCloud` 的辅助字段，为点云中的每个点附加单精度浮点属性（如反射强度 `intensity`、颜色 `rgb`）。

> **说明**：仅配合旧版 `PointCloud` 使用；新工程请使用 `PointCloud2` 与 `PointField`。

## 接口定义（`.msg`）

```msg
string name  # 通道属性名称（如 `intensity`、`rgb`、`index`）
float32[] values  # 与 `PointCloud.points` 一一对应的属性值数组
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `name` | `string` | — | 通道属性名称（如 `intensity`、`rgb`、`index`） |
| `values` | `float32[]` | — | 与 `PointCloud.points` 一一对应的属性值数组 |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/channel_float32.hpp"

// 1. 声明消息对象
sensor_msgs::msg::ChannelFloat32 msg;

// 2. 对消息字段进行赋值
msg.name = "intensity";
msg.values = {1.0f, 2.0f, 3.0f, 4.0f};
```

### Python 示例

```python
from sensor_msgs.msg import ChannelFloat32

# 1. 声明消息对象
msg = ChannelFloat32()

# 2. 对消息字段进行赋值
msg.name = "intensity"
msg.values = [1.0, 2.0, 3.0, 4.0]
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
