[🏠 首页](../../README.md) / [`geometry_msgs`](../README.md) / `msg` / **TransformStamped**

# `geometry_msgs/msg/TransformStamped`

> 带时间戳与父子坐标系名称的坐标变换

TF2 坐标变换树（`/tf` 与 `/tf_static`）的核心底层消息，表示从 `header.frame_id` 到 `child_frame_id` 的变换。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 时间戳与父坐标系名称（`frame_id`）
string child_frame_id  # 子坐标系名称
Transform transform  # 父坐标系到子坐标系的平移与旋转变换
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 时间戳与父坐标系名称（`frame_id`） |
| `child_frame_id` | `string` | — | 子坐标系名称 |
| `transform` | [`Transform`](./Transform.md) | — | 父坐标系到子坐标系的平移与旋转变换 |

## 使用示例

### C++ 示例

```cpp
#include "geometry_msgs/msg/transform_stamped.hpp"

// 1. 声明消息对象
geometry_msgs::msg::TransformStamped msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "odom";
msg.child_frame_id = "base_link";
msg.transform.translation.x = 1.0;
msg.transform.translation.y = 2.0;
msg.transform.translation.z = 0.5;
msg.transform.rotation.x = 0.0;
msg.transform.rotation.y = 0.0;
msg.transform.rotation.z = 0.0;
msg.transform.rotation.w = 1.0;
```

### Python 示例

```python
from geometry_msgs.msg import TransformStamped

# 1. 声明消息对象
msg = TransformStamped()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "odom"
msg.child_frame_id = "base_link"
msg.transform.translation.x = 1.0
msg.transform.translation.y = 2.0
msg.transform.translation.z = 0.5
msg.transform.rotation.x = 0.0
msg.transform.rotation.y = 0.0
msg.transform.rotation.z = 0.0
msg.transform.rotation.w = 1.0
```

---
⬅️ [返回 `geometry_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
