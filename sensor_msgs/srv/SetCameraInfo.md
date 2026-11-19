[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `srv` / **SetCameraInfo**

# `sensor_msgs/srv/SetCameraInfo`

> 向相机驱动写入标定内参服务

由 `camera_calibration` 等标定工具调用，将标定完成后的 `CameraInfo` 持久化保存到相机驱动或板载 EEPROM 中。

## 接口定义（`.srv`）

```srv
# 请求 (Request)
CameraInfo camera_info  # 待写入生效的相机标定参数
---
# 响应 (Response)
bool success  # 标定参数是否成功应用并保存
string status_message  # 保存结果说明或失败原因
```

## 请求参数（Request）

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `camera_info` | [`CameraInfo`](../msg/CameraInfo.md) | — | 待写入生效的相机标定参数 |

## 响应参数（Response）

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `success` | `bool` | — | 标定参数是否成功应用并保存 |
| `status_message` | `string` | — | 保存结果说明或失败原因 |

## 使用示例

### C++ 示例

```cpp
#include <memory>
#include "sensor_msgs/srv/set_camera_info.hpp"

// 1. 声明服务请求与响应对象
auto request = std::make_shared<sensor_msgs::srv::SetCameraInfo::Request>();
auto response = std::make_shared<sensor_msgs::srv::SetCameraInfo::Response>();

// 2. 对请求与响应数据内容进行赋值
// --- 请求 (Request) ---
request->camera_info.header.stamp.sec = 1700000000;
request->camera_info.header.stamp.nanosec = 500000000;
request->camera_info.header.frame_id = "camera_optical_frame";
request->camera_info.height = 480;
request->camera_info.width = 640;
request->camera_info.distortion_model = "plumb_bob";
request->camera_info.d = {-0.1, 0.01, 0.0, 0.0, 0.0};
request->camera_info.k = {525.0, 0.0, 319.5, 0.0, 525.0, 239.5, 0.0, 0.0, 1.0};
request->camera_info.r = {1.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 1.0};
request->camera_info.p = {525.0, 0.0, 319.5, 0.0, 0.0, 525.0, 239.5, 0.0, 0.0, 0.0, 1.0, 0.0};
request->camera_info.binning_x = 1;
request->camera_info.binning_y = 1;
request->camera_info.roi.x_offset = 0;
request->camera_info.roi.y_offset = 0;
request->camera_info.roi.height = 480;
request->camera_info.roi.width = 640;
request->camera_info.roi.do_rectify = false;

// --- 响应 (Response) ---
response->success = true;
response->status_message = "Camera info saved successfully";
```

### Python 示例

```python
from sensor_msgs.srv import SetCameraInfo

# 1. 声明服务请求与响应对象
request = SetCameraInfo.Request()
response = SetCameraInfo.Response()

# 2. 对请求与响应数据内容进行赋值
# --- 请求 (Request) ---
request.camera_info.header.stamp.sec = 1700000000
request.camera_info.header.stamp.nanosec = 500000000
request.camera_info.header.frame_id = "camera_optical_frame"
request.camera_info.height = 480
request.camera_info.width = 640
request.camera_info.distortion_model = "plumb_bob"
request.camera_info.d = [-0.1, 0.01, 0.0, 0.0, 0.0]
request.camera_info.k = [525.0, 0.0, 319.5, 0.0, 525.0, 239.5, 0.0, 0.0, 1.0]
request.camera_info.r = [1.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 1.0]
request.camera_info.p = [525.0, 0.0, 319.5, 0.0, 0.0, 525.0, 239.5, 0.0, 0.0, 0.0, 1.0, 0.0]
request.camera_info.binning_x = 1
request.camera_info.binning_y = 1
request.camera_info.roi.x_offset = 0
request.camera_info.roi.y_offset = 0
request.camera_info.roi.height = 480
request.camera_info.roi.width = 640
request.camera_info.roi.do_rectify = False

# --- 响应 (Response) ---
response.success = True
response.status_message = "Camera info saved successfully"
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
