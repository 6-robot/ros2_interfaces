[🏠 首页](../../README.md) / [`nav_msgs`](../README.md) / `msg` / **GridCells**

# `nav_msgs/msg/GridCells`

> 二维栅格中心点集合

表示代价地图或栅格地图中满足特定条件（如障碍物或膨胀层）的栅格单元中心点集合。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 时间戳与参考坐标系
float32 cell_width  # 单个栅格宽度 [m]
float32 cell_height  # 单个栅格高度 [m]
geometry_msgs/Point[] cells  # 每个目标栅格的中心点三维坐标数组
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 时间戳与参考坐标系 |
| `cell_width` | `float32` | — | 单个栅格宽度 [m] |
| `cell_height` | `float32` | — | 单个栅格高度 [m] |
| `cells` | [`geometry_msgs/Point`](../../geometry_msgs/msg/Point.md)`[]` | — | 每个目标栅格的中心点三维坐标数组 |

## 使用示例

### C++ 示例

```cpp
#include "nav_msgs/msg/grid_cells.hpp"

// 1. 声明消息对象
nav_msgs::msg::GridCells msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "map";
msg.cell_width = 0.05f;
msg.cell_height = 0.05f;
geometry_msgs::msg::Point point;
point.x = 1.0;
point.y = 2.0;
point.z = 0.5;
msg.cells.push_back(point);
```

### Python 示例

```python
from geometry_msgs.msg import Point
from nav_msgs.msg import GridCells

# 1. 声明消息对象
msg = GridCells()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "map"
msg.cell_width = 0.05
msg.cell_height = 0.05
point = Point()
point.x = 1.0
point.y = 2.0
point.z = 0.5
msg.cells.append(point)
```

---
⬅️ [返回 `nav_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
