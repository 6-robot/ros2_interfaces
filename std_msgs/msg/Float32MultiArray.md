[🏠 首页](../../README.md) / [`std_msgs`](../README.md) / `msg` / **Float32MultiArray**

# `std_msgs/msg/Float32MultiArray`

> 32位单精度浮点多维数组消息（`float32[]`）

以展平的一维 `float32` 数组配合 `MultiArrayLayout` 布局描述来表示多维32位单精度浮点数组。

> **说明**：在 ROS 2 中，官方已将所有 `*MultiArray` 消息标记为不推荐用于新接口设计（缺乏字段语义），建议使用具名自定义消息替代。

## 接口定义（`.msg`）

```msg
MultiArrayLayout layout  # 多维数组的维度与步长排布规格
float32[] data  # 按 `layout` 规则展平存储的一维 `float32` 数据数组
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `layout` | [`MultiArrayLayout`](./MultiArrayLayout.md) | — | 多维数组的维度与步长排布规格 |
| `data` | `float32[]` | — | 按 `layout` 规则展平存储的一维 `float32` 数据数组 |

## 使用示例

### C++ 示例

```cpp
#include "std_msgs/msg/float32_multi_array.hpp"

// 1. 声明消息对象
std_msgs::msg::Float32MultiArray msg;

// 2. 对消息字段进行赋值
std_msgs::msg::MultiArrayDimension multi_array_dimension;
multi_array_dimension.label = "width";
multi_array_dimension.size = 4;
multi_array_dimension.stride = 4;
msg.layout.dim.push_back(multi_array_dimension);
msg.layout.data_offset = 0;
msg.data = {1.0f, 2.0f, 3.0f, 4.0f};
```

### Python 示例

```python
from std_msgs.msg import Float32MultiArray, MultiArrayDimension

# 1. 声明消息对象
msg = Float32MultiArray()

# 2. 对消息字段进行赋值
multi_array_dimension = MultiArrayDimension()
multi_array_dimension.label = "width"
multi_array_dimension.size = 4
multi_array_dimension.stride = 4
msg.layout.dim.append(multi_array_dimension)
msg.layout.data_offset = 0
msg.data = [1.0, 2.0, 3.0, 4.0]
```

---
⬅️ [返回 `std_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
