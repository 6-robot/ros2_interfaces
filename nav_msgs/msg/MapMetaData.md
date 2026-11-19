[🏠 首页](../../README.md) / [`nav_msgs`](../README.md) / `msg` / **MapMetaData**

# `nav_msgs/msg/MapMetaData`

> 二维栅格地图元数据

描述 `OccupancyGrid` 二维概率栅格地图的分辨率、尺寸和世界坐标系原点位姿。

## 接口定义（`.msg`）

```msg
builtin_interfaces/Time map_load_time  # 地图加载时刻
float32 resolution  # 地图分辨率 [m/cell]
uint32 width  # 地图宽度（列数，沿 X 轴方向） [cells]
uint32 height  # 地图高度（行数，沿 Y 轴方向） [cells]
geometry_msgs/Pose origin  # 地图栅格索引 `(0, 0)` 在真实世界坐标系中的位姿
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `map_load_time` | [`builtin_interfaces/Time`](../../builtin_interfaces/msg/Time.md) | — | 地图加载时刻 |
| `resolution` | `float32` | — | 地图分辨率 [m/cell] |
| `width` | `uint32` | — | 地图宽度（列数，沿 X 轴方向） [cells] |
| `height` | `uint32` | — | 地图高度（行数，沿 Y 轴方向） [cells] |
| `origin` | [`geometry_msgs/Pose`](../../geometry_msgs/msg/Pose.md) | — | 地图栅格索引 `(0, 0)` 在真实世界坐标系中的位姿 |

## 使用示例

### C++ 示例

```cpp
#include "nav_msgs/msg/map_meta_data.hpp"

// 1. 声明消息对象
nav_msgs::msg::MapMetaData msg;

// 2. 对消息字段进行赋值
msg.map_load_time.sec = 1700000000;
msg.map_load_time.nanosec = 500000000;
msg.resolution = 0.05f;
msg.width = 100;
msg.height = 100;
msg.origin.position.x = 1.0;
msg.origin.position.y = 2.0;
msg.origin.position.z = 0.5;
msg.origin.orientation.x = 0.0;
msg.origin.orientation.y = 0.0;
msg.origin.orientation.z = 0.0;
msg.origin.orientation.w = 1.0;
```

### Python 示例

```python
from nav_msgs.msg import MapMetaData

# 1. 声明消息对象
msg = MapMetaData()

# 2. 对消息字段进行赋值
msg.map_load_time.sec = 1700000000
msg.map_load_time.nanosec = 500000000
msg.resolution = 0.05
msg.width = 100
msg.height = 100
msg.origin.position.x = 1.0
msg.origin.position.y = 2.0
msg.origin.position.z = 0.5
msg.origin.orientation.x = 0.0
msg.origin.orientation.y = 0.0
msg.origin.orientation.z = 0.0
msg.origin.orientation.w = 1.0
```

---
⬅️ [返回 `nav_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
