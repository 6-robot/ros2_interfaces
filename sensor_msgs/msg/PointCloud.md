[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **PointCloud**

# `sensor_msgs/msg/PointCloud`

> 旧版三维点云消息（已弃用）

早期 ROS 1 风格的三维点云格式，将点坐标与附加属性分开存储。

> **说明**：官方已不推荐在新工程中使用，请改用更高效、结构更灵活的 `PointCloud2`。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 点云采集时间戳与坐标系
geometry_msgs/Point32[] points  # 三维点坐标数组
ChannelFloat32[] channels  # 与点数组等长的附加属性通道数组
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 点云采集时间戳与坐标系 |
| `points` | [`geometry_msgs/Point32`](../../geometry_msgs/msg/Point32.md)`[]` | — | 三维点坐标数组 |
| `channels` | [`ChannelFloat32`](./ChannelFloat32.md)`[]` | — | 与点数组等长的附加属性通道数组 |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/point_cloud.hpp"

// 1. 声明消息对象
sensor_msgs::msg::PointCloud msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "lidar_link";
geometry_msgs::msg::Point32 point32;
point32.x = 1.0f;
point32.y = 2.0f;
point32.z = 0.5f;
msg.points.push_back(point32);
sensor_msgs::msg::ChannelFloat32 channel_float32;
channel_float32.name = "intensity";
channel_float32.values = {1.0f, 2.0f, 3.0f, 4.0f};
msg.channels.push_back(channel_float32);
```

### Python 示例

```python
from geometry_msgs.msg import Point32
from sensor_msgs.msg import ChannelFloat32, PointCloud

# 1. 声明消息对象
msg = PointCloud()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "lidar_link"
point32 = Point32()
point32.x = 1.0
point32.y = 2.0
point32.z = 0.5
msg.points.append(point32)
channel_float32 = ChannelFloat32()
channel_float32.name = "intensity"
channel_float32.values = [1.0, 2.0, 3.0, 4.0]
msg.channels.append(channel_float32)
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
