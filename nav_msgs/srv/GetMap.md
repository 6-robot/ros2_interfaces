[🏠 首页](../../README.md) / [`nav_msgs`](../README.md) / `srv` / **GetMap**

# `nav_msgs/srv/GetMap`

> 获取静态栅格地图服务

客户端向地图服务器（如 `map_server`）请求当前完整静态 `OccupancyGrid` 地图。

## 接口定义（`.srv`）

```srv
# 请求 (Request)
# （空，无字段）
---
# 响应 (Response)
OccupancyGrid map  # 返回的二维占据栅格地图
```

## 请求参数（Request）

*无请求参数。*

## 响应参数（Response）

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `map` | [`OccupancyGrid`](../msg/OccupancyGrid.md) | — | 返回的二维占据栅格地图 |

## 使用示例

### C++ 示例

```cpp
#include <memory>
#include "nav_msgs/srv/get_map.hpp"

// 1. 声明服务请求与响应对象
auto request = std::make_shared<nav_msgs::srv::GetMap::Request>();
auto response = std::make_shared<nav_msgs::srv::GetMap::Response>();

// 2. 对请求与响应数据内容进行赋值
// --- 请求 (Request) ---
// 请求体无字段

// --- 响应 (Response) ---
response->map.header.stamp.sec = 1700000000;
response->map.header.stamp.nanosec = 500000000;
response->map.header.frame_id = "map";
response->map.info.map_load_time.sec = 1700000000;
response->map.info.map_load_time.nanosec = 500000000;
response->map.info.resolution = 0.05f;
response->map.info.width = 100;
response->map.info.height = 100;
response->map.info.origin.position.x = 1.0;
response->map.info.origin.position.y = 2.0;
response->map.info.origin.position.z = 0.5;
response->map.info.origin.orientation.x = 0.0;
response->map.info.origin.orientation.y = 0.0;
response->map.info.origin.orientation.z = 0.0;
response->map.info.origin.orientation.w = 1.0;
response->map.data.assign(100 * 100, 0);  // 0=空闲, 100=障碍物, -1=未知
response->map.data[5050] = 100;
```

### Python 示例

```python
from nav_msgs.srv import GetMap

# 1. 声明服务请求与响应对象
request = GetMap.Request()
response = GetMap.Response()

# 2. 对请求与响应数据内容进行赋值
# --- 请求 (Request) ---
# 请求体无字段

# --- 响应 (Response) ---
response.map.header.stamp.sec = 1700000000
response.map.header.stamp.nanosec = 500000000
response.map.header.frame_id = "map"
response.map.info.map_load_time.sec = 1700000000
response.map.info.map_load_time.nanosec = 500000000
response.map.info.resolution = 0.05
response.map.info.width = 100
response.map.info.height = 100
response.map.info.origin.position.x = 1.0
response.map.info.origin.position.y = 2.0
response.map.info.origin.position.z = 0.5
response.map.info.origin.orientation.x = 0.0
response.map.info.origin.orientation.y = 0.0
response.map.info.origin.orientation.z = 0.0
response.map.info.origin.orientation.w = 1.0
response.map.data = [0] * (100 * 100)
```

---
⬅️ [返回 `nav_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
