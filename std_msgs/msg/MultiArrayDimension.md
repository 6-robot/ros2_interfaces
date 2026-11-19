[🏠 首页](../../README.md) / [`std_msgs`](../README.md) / `msg` / **MultiArrayDimension**

# `std_msgs/msg/MultiArrayDimension`

> 多维数组的单个维度元数据

描述 `*MultiArray` 中某一维度的标签、元素数量和步长（stride）。

> **说明**：官方在 ROS 2 中已不推荐在新接口中使用 `*MultiArray` 系列消息，建议改用带明确语义字段的自定义消息。

## 接口定义（`.msg`）

```msg
string label  # 当前维度的名称标签（如 `height`、`width`、`channel`）
uint32 size  # 当前维度包含的元素个数
uint32 stride  # 当前维度的元素跨度（从内层到外层的累乘长度）
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `label` | `string` | — | 当前维度的名称标签（如 `height`、`width`、`channel`） |
| `size` | `uint32` | — | 当前维度包含的元素个数 |
| `stride` | `uint32` | — | 当前维度的元素跨度（从内层到外层的累乘长度） |

## 使用示例

### C++ 示例

```cpp
#include "std_msgs/msg/multi_array_dimension.hpp"

// 1. 声明消息对象
std_msgs::msg::MultiArrayDimension msg;

// 2. 对消息字段进行赋值
msg.label = "width";
msg.size = 4;
msg.stride = 4;
```

### Python 示例

```python
from std_msgs.msg import MultiArrayDimension

# 1. 声明消息对象
msg = MultiArrayDimension()

# 2. 对消息字段进行赋值
msg.label = "width"
msg.size = 4
msg.stride = 4
```

---
⬅️ [返回 `std_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
