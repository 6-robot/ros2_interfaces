[🏠 首页](../../README.md) / [`nav_msgs`](../README.md) / `msg` / **OccupancyGrid**

# `nav_msgs/msg/OccupancyGrid`

> 二维概率占据栅格地图

使用二维栅格数组表示环境占据概率，是 2D SLAM 建图输出和 Nav2 代价地图的标准格式。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 时间戳与地图参考坐标系（通常为 `map`）
MapMetaData info  # 地图几何元数据（分辨率、宽高、原点）
int8[] data  # 行优先排列的一维栅格占据概率数组：取值 `[0, 100]`（0=空闲，100=障碍物），`-1` 表示未知区域
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 时间戳与地图参考坐标系（通常为 `map`） |
| `info` | [`MapMetaData`](./MapMetaData.md) | — | 地图几何元数据（分辨率、宽高、原点） |
| `data` | `int8[]` | — | 行优先排列的一维栅格占据概率数组：取值 `[0, 100]`（0=空闲，100=障碍物），`-1` 表示未知区域 |

## 使用示例

### C++ 示例

```cpp
#include "nav_msgs/msg/occupancy_grid.hpp"

// 1. 声明消息对象
nav_msgs::msg::OccupancyGrid msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "map";
msg.info.map_load_time.sec = 1700000000;
msg.info.map_load_time.nanosec = 500000000;
msg.info.resolution = 0.05f;
msg.info.width = 100;
msg.info.height = 100;
msg.info.origin.position.x = 1.0;
msg.info.origin.position.y = 2.0;
msg.info.origin.position.z = 0.5;
msg.info.origin.orientation.x = 0.0;
msg.info.origin.orientation.y = 0.0;
msg.info.origin.orientation.z = 0.0;
msg.info.origin.orientation.w = 1.0;
msg.data.assign(100 * 100, 0);  // 0=空闲, 100=障碍物, -1=未知
msg.data[5050] = 100;
```

### Python 示例

```python
from nav_msgs.msg import OccupancyGrid

# 1. 声明消息对象
msg = OccupancyGrid()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "map"
msg.info.map_load_time.sec = 1700000000
msg.info.map_load_time.nanosec = 500000000
msg.info.resolution = 0.05
msg.info.width = 100
msg.info.height = 100
msg.info.origin.position.x = 1.0
msg.info.origin.position.y = 2.0
msg.info.origin.position.z = 0.5
msg.info.origin.orientation.x = 0.0
msg.info.origin.orientation.y = 0.0
msg.info.origin.orientation.z = 0.0
msg.info.origin.orientation.w = 1.0
msg.data = [0] * (100 * 100)
```

---
⬅️ [返回 `nav_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
