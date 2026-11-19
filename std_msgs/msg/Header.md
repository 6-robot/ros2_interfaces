[🏠 首页](../../README.md) / [`std_msgs`](../README.md) / `msg` / **Header**

# `std_msgs/msg/Header`

> 标准时间戳与坐标系消息头

用于为绝大多数空间与传感器消息附加精确时间戳和参考坐标系名称，是 TF2 坐标变换与多传感器时间同步的基础。

> **说明**：相较于 ROS 1，ROS 2 中的 `Header` 已移除 `seq` 序号字段。

## 接口定义（`.msg`）

```msg
builtin_interfaces/Time stamp  # 双整数时间戳（秒 + 纳秒）
string frame_id  # 该消息数据所关联的参考坐标系名称（如 `map`、`odom`、`base_link`）
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `stamp` | [`builtin_interfaces/Time`](../../builtin_interfaces/msg/Time.md) | — | 双整数时间戳（秒 + 纳秒） |
| `frame_id` | `string` | — | 该消息数据所关联的参考坐标系名称（如 `map`、`odom`、`base_link`） |

## 使用示例

### C++ 示例

```cpp
#include "std_msgs/msg/header.hpp"

// 1. 声明消息对象
std_msgs::msg::Header msg;

// 2. 对消息字段进行赋值
msg.stamp.sec = 1700000000;
msg.stamp.nanosec = 500000000;
msg.frame_id = "base_link";
```

### Python 示例

```python
from std_msgs.msg import Header

# 1. 声明消息对象
msg = Header()

# 2. 对消息字段进行赋值
msg.stamp.sec = 1700000000
msg.stamp.nanosec = 500000000
msg.frame_id = "base_link"
```

---
⬅️ [返回 `std_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
