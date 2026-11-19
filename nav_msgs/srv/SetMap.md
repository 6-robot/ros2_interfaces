[🏠 首页](../../README.md) / [`nav_msgs`](../README.md) / `srv` / **SetMap**

# `nav_msgs/srv/SetMap`

> 设置新地图与机器人初始位姿服务

将新地图与对应的机器人初始位姿估计同时下发至定位或导航节点。

## 接口定义（`.srv`）

```srv
# 请求 (Request)
OccupancyGrid map  # 待设置的占据栅格地图
geometry_msgs/PoseWithCovarianceStamped initial_pose  # 机器人在新地图中的初始位姿与协方差
---
# 响应 (Response)
bool success  # 是否成功应用新地图与初始位姿
```

## 请求参数（Request）

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `map` | [`OccupancyGrid`](../msg/OccupancyGrid.md) | — | 待设置的占据栅格地图 |
| `initial_pose` | [`geometry_msgs/PoseWithCovarianceStamped`](../../geometry_msgs/msg/PoseWithCovarianceStamped.md) | — | 机器人在新地图中的初始位姿与协方差 |

## 响应参数（Response）

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `success` | `bool` | — | 是否成功应用新地图与初始位姿 |

## 使用示例

### C++ 示例

```cpp
#include <memory>
#include "nav_msgs/srv/set_map.hpp"

// 1. 声明服务请求与响应对象
auto request = std::make_shared<nav_msgs::srv::SetMap::Request>();
auto response = std::make_shared<nav_msgs::srv::SetMap::Response>();

// 2. 对请求与响应数据内容进行赋值
// --- 请求 (Request) ---
request->map.header.stamp.sec = 1700000000;
request->map.header.stamp.nanosec = 500000000;
request->map.header.frame_id = "map";
request->map.info.map_load_time.sec = 1700000000;
request->map.info.map_load_time.nanosec = 500000000;
request->map.info.resolution = 0.05f;
request->map.info.width = 100;
request->map.info.height = 100;
request->map.info.origin.position.x = 1.0;
request->map.info.origin.position.y = 2.0;
request->map.info.origin.position.z = 0.5;
request->map.info.origin.orientation.x = 0.0;
request->map.info.origin.orientation.y = 0.0;
request->map.info.origin.orientation.z = 0.0;
request->map.info.origin.orientation.w = 1.0;
request->map.data.assign(100 * 100, 0);  // 0=空闲, 100=障碍物, -1=未知
request->map.data[5050] = 100;
request->initial_pose.header.stamp.sec = 1700000000;
request->initial_pose.header.stamp.nanosec = 500000000;
request->initial_pose.header.frame_id = "map";
request->initial_pose.pose.pose.position.x = 1.0;
request->initial_pose.pose.pose.position.y = 2.0;
request->initial_pose.pose.pose.position.z = 0.5;
request->initial_pose.pose.pose.orientation.x = 0.0;
request->initial_pose.pose.pose.orientation.y = 0.0;
request->initial_pose.pose.pose.orientation.z = 0.0;
request->initial_pose.pose.pose.orientation.w = 1.0;
request->initial_pose.pose.covariance.fill(0.0);
request->initial_pose.pose.covariance[0] = 0.01;   // x 方差
request->initial_pose.pose.covariance[7] = 0.01;   // y 方差
request->initial_pose.pose.covariance[35] = 0.05;  // yaw 方差

// --- 响应 (Response) ---
response->success = true;
```

### Python 示例

```python
from nav_msgs.srv import SetMap

# 1. 声明服务请求与响应对象
request = SetMap.Request()
response = SetMap.Response()

# 2. 对请求与响应数据内容进行赋值
# --- 请求 (Request) ---
request.map.header.stamp.sec = 1700000000
request.map.header.stamp.nanosec = 500000000
request.map.header.frame_id = "map"
request.map.info.map_load_time.sec = 1700000000
request.map.info.map_load_time.nanosec = 500000000
request.map.info.resolution = 0.05
request.map.info.width = 100
request.map.info.height = 100
request.map.info.origin.position.x = 1.0
request.map.info.origin.position.y = 2.0
request.map.info.origin.position.z = 0.5
request.map.info.origin.orientation.x = 0.0
request.map.info.origin.orientation.y = 0.0
request.map.info.origin.orientation.z = 0.0
request.map.info.origin.orientation.w = 1.0
request.map.data = [0] * (100 * 100)
request.initial_pose.header.stamp.sec = 1700000000
request.initial_pose.header.stamp.nanosec = 500000000
request.initial_pose.header.frame_id = "map"
request.initial_pose.pose.pose.position.x = 1.0
request.initial_pose.pose.pose.position.y = 2.0
request.initial_pose.pose.pose.position.z = 0.5
request.initial_pose.pose.pose.orientation.x = 0.0
request.initial_pose.pose.pose.orientation.y = 0.0
request.initial_pose.pose.pose.orientation.z = 0.0
request.initial_pose.pose.pose.orientation.w = 1.0
request.initial_pose.pose.covariance = [0.01 if i in (0, 7, 14) else (0.05 if i in (21, 28, 35) else 0.0) for i in range(36)]

# --- 响应 (Response) ---
response.success = True
```

---
⬅️ [返回 `nav_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
