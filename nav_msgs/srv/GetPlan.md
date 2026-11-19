[🏠 首页](../../README.md) / [`nav_msgs`](../README.md) / `srv` / **GetPlan**

# `nav_msgs/srv/GetPlan`

> 请求全局路径规划服务

请求规划节点计算从指定起点 `start` 到目标点 `goal` 的无碰撞全局路径。

## 接口定义（`.srv`）

```srv
# 请求 (Request)
geometry_msgs/PoseStamped start  # 规划起点位姿
geometry_msgs/PoseStamped goal  # 规划终点位姿
float32 tolerance  # 若精确目标不可达，允许到达目标附近的距离容差 [m]
---
# 响应 (Response)
Path plan  # 规划生成的有序路径
```

## 请求参数（Request）

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `start` | [`geometry_msgs/PoseStamped`](../../geometry_msgs/msg/PoseStamped.md) | — | 规划起点位姿 |
| `goal` | [`geometry_msgs/PoseStamped`](../../geometry_msgs/msg/PoseStamped.md) | — | 规划终点位姿 |
| `tolerance` | `float32` | — | 若精确目标不可达，允许到达目标附近的距离容差 [m] |

## 响应参数（Response）

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `plan` | [`Path`](../msg/Path.md) | — | 规划生成的有序路径 |

## 使用示例

### C++ 示例

```cpp
#include <memory>
#include "nav_msgs/srv/get_plan.hpp"

// 1. 声明服务请求与响应对象
auto request = std::make_shared<nav_msgs::srv::GetPlan::Request>();
auto response = std::make_shared<nav_msgs::srv::GetPlan::Response>();

// 2. 对请求与响应数据内容进行赋值
// --- 请求 (Request) ---
request->start.header.stamp.sec = 1700000000;
request->start.header.stamp.nanosec = 500000000;
request->start.header.frame_id = "base_link";
request->start.pose.position.x = 1.0;
request->start.pose.position.y = 2.0;
request->start.pose.position.z = 0.5;
request->start.pose.orientation.x = 0.0;
request->start.pose.orientation.y = 0.0;
request->start.pose.orientation.z = 0.0;
request->start.pose.orientation.w = 1.0;
request->goal.header.stamp.sec = 1700000000;
request->goal.header.stamp.nanosec = 500000000;
request->goal.header.frame_id = "base_link";
request->goal.pose.position.x = 1.0;
request->goal.pose.position.y = 2.0;
request->goal.pose.position.z = 0.5;
request->goal.pose.orientation.x = 0.0;
request->goal.pose.orientation.y = 0.0;
request->goal.pose.orientation.z = 0.0;
request->goal.pose.orientation.w = 1.0;
request->tolerance = 0.2f;

// --- 响应 (Response) ---
response->plan.header.stamp.sec = 1700000000;
response->plan.header.stamp.nanosec = 500000000;
response->plan.header.frame_id = "map";
geometry_msgs::msg::PoseStamped pose_stamped;
pose_stamped.header.stamp.sec = 1700000000;
pose_stamped.header.stamp.nanosec = 500000000;
pose_stamped.header.frame_id = "base_link";
pose_stamped.pose.position.x = 1.0;
pose_stamped.pose.position.y = 2.0;
pose_stamped.pose.position.z = 0.5;
pose_stamped.pose.orientation.x = 0.0;
pose_stamped.pose.orientation.y = 0.0;
pose_stamped.pose.orientation.z = 0.0;
pose_stamped.pose.orientation.w = 1.0;
response->plan.poses.push_back(pose_stamped);
```

### Python 示例

```python
from geometry_msgs.msg import PoseStamped
from nav_msgs.srv import GetPlan

# 1. 声明服务请求与响应对象
request = GetPlan.Request()
response = GetPlan.Response()

# 2. 对请求与响应数据内容进行赋值
# --- 请求 (Request) ---
request.start.header.stamp.sec = 1700000000
request.start.header.stamp.nanosec = 500000000
request.start.header.frame_id = "base_link"
request.start.pose.position.x = 1.0
request.start.pose.position.y = 2.0
request.start.pose.position.z = 0.5
request.start.pose.orientation.x = 0.0
request.start.pose.orientation.y = 0.0
request.start.pose.orientation.z = 0.0
request.start.pose.orientation.w = 1.0
request.goal.header.stamp.sec = 1700000000
request.goal.header.stamp.nanosec = 500000000
request.goal.header.frame_id = "base_link"
request.goal.pose.position.x = 1.0
request.goal.pose.position.y = 2.0
request.goal.pose.position.z = 0.5
request.goal.pose.orientation.x = 0.0
request.goal.pose.orientation.y = 0.0
request.goal.pose.orientation.z = 0.0
request.goal.pose.orientation.w = 1.0
request.tolerance = 0.2

# --- 响应 (Response) ---
response.plan.header.stamp.sec = 1700000000
response.plan.header.stamp.nanosec = 500000000
response.plan.header.frame_id = "map"
pose_stamped = PoseStamped()
pose_stamped.header.stamp.sec = 1700000000
pose_stamped.header.stamp.nanosec = 500000000
pose_stamped.header.frame_id = "base_link"
pose_stamped.pose.position.x = 1.0
pose_stamped.pose.position.y = 2.0
pose_stamped.pose.position.z = 0.5
pose_stamped.pose.orientation.x = 0.0
pose_stamped.pose.orientation.y = 0.0
pose_stamped.pose.orientation.z = 0.0
pose_stamped.pose.orientation.w = 1.0
response.plan.poses.append(pose_stamped)
```

---
⬅️ [返回 `nav_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
