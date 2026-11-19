[🏠 首页](../../README.md) / [`nav_msgs`](../README.md) / `srv` / **LoadMap**

# `nav_msgs/srv/LoadMap`

> 从文件或 URI 加载地图服务

指示地图服务器从指定路径（通常为 `.yaml` 地图描述文件）读取并返回占据栅格地图。

## 接口定义（`.srv`）

```srv
# 请求 (Request)
string map_url  # 地图配置文件的路径或 URI（支持绝对路径、`package://` 或 `file://`）
---
# 响应 (Response)
# --- 常量定义 ---
uint8 RESULT_SUCCESS=0  # 地图加载成功
uint8 RESULT_MAP_DOES_NOT_EXIST=1  # 指定路径的地图文件不存在
uint8 RESULT_INVALID_MAP_DATA=2  # 地图图像数据损坏或格式非法
uint8 RESULT_INVALID_MAP_METADATA=3  # 地图 YAML 元数据格式错误
uint8 RESULT_UNDEFINED_FAILURE=255  # 未定义的其他错误

# --- 字段定义 ---
OccupancyGrid map  # 成功加载后返回的占据栅格地图
uint8 result  # 加载结果状态码（见上方常量定义）
```

## 请求参数（Request）

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `map_url` | `string` | — | 地图配置文件的路径或 URI（支持绝对路径、`package://` 或 `file://`） |

## 响应参数（Response）

### 响应常量

| 常量名 | 类型 | 值 | 说明 |
| :--- | :--- | :--- | :--- |
| `RESULT_SUCCESS` | `uint8` | `0` | 地图加载成功 |
| `RESULT_MAP_DOES_NOT_EXIST` | `uint8` | `1` | 指定路径的地图文件不存在 |
| `RESULT_INVALID_MAP_DATA` | `uint8` | `2` | 地图图像数据损坏或格式非法 |
| `RESULT_INVALID_MAP_METADATA` | `uint8` | `3` | 地图 YAML 元数据格式错误 |
| `RESULT_UNDEFINED_FAILURE` | `uint8` | `255` | 未定义的其他错误 |

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `map` | [`OccupancyGrid`](../msg/OccupancyGrid.md) | — | 成功加载后返回的占据栅格地图 |
| `result` | `uint8` | — | 加载结果状态码（见上方常量定义） |

## 使用示例

### C++ 示例

```cpp
#include <memory>
#include "nav_msgs/srv/load_map.hpp"

// 1. 声明服务请求与响应对象
auto request = std::make_shared<nav_msgs::srv::LoadMap::Request>();
auto response = std::make_shared<nav_msgs::srv::LoadMap::Response>();

// 2. 对请求与响应数据内容进行赋值
// --- 请求 (Request) ---
request->map_url = "/maps/office_map.yaml";

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
response->result = nav_msgs::srv::LoadMap::Response::RESULT_SUCCESS;
```

### Python 示例

```python
from nav_msgs.srv import LoadMap

# 1. 声明服务请求与响应对象
request = LoadMap.Request()
response = LoadMap.Response()

# 2. 对请求与响应数据内容进行赋值
# --- 请求 (Request) ---
request.map_url = "/maps/office_map.yaml"

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
response.result = LoadMap.Response.RESULT_SUCCESS
```

---
⬅️ [返回 `nav_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
