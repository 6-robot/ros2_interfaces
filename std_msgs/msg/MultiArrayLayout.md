[🏠 首页](../../README.md) / [`std_msgs`](../README.md) / `msg` / **MultiArrayLayout**

# `std_msgs/msg/MultiArrayLayout`

> 多维数组的内存排布规格

定义如何将一维展平数组 `data` 重新索引为多维张量或矩阵。

> **说明**：官方在 ROS 2 中已不推荐在新接口中使用 `*MultiArray` 系列消息。

## 接口定义（`.msg`）

```msg
MultiArrayDimension[] dim  # 从最外层到最内层排列的各维度属性数组
uint32 data_offset  # 有效数据起始前的前导填充元素数量
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `dim` | [`MultiArrayDimension`](./MultiArrayDimension.md)`[]` | — | 从最外层到最内层排列的各维度属性数组 |
| `data_offset` | `uint32` | — | 有效数据起始前的前导填充元素数量 |

## 使用示例

### C++ 示例

```cpp
#include "std_msgs/msg/multi_array_layout.hpp"

// 1. 声明消息对象
std_msgs::msg::MultiArrayLayout msg;

// 2. 对消息字段进行赋值
std_msgs::msg::MultiArrayDimension multi_array_dimension;
multi_array_dimension.label = "width";
multi_array_dimension.size = 4;
multi_array_dimension.stride = 4;
msg.dim.push_back(multi_array_dimension);
msg.data_offset = 0;
```

### Python 示例

```python
from std_msgs.msg import MultiArrayDimension, MultiArrayLayout

# 1. 声明消息对象
msg = MultiArrayLayout()

# 2. 对消息字段进行赋值
multi_array_dimension = MultiArrayDimension()
multi_array_dimension.label = "width"
multi_array_dimension.size = 4
multi_array_dimension.stride = 4
msg.dim.append(multi_array_dimension)
msg.data_offset = 0
```

---
⬅️ [返回 `std_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
