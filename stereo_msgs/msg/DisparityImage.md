[🏠 首页](../../README.md) / [`stereo_msgs`](../README.md) / `msg` / **DisparityImage**

# `stereo_msgs/msg/DisparityImage`

> 双目立体视觉浮点视差图

包含经立体匹配计算得到的单通道浮点视差图以及恢复真实深度所需的焦距、基线与有效视差范围。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 左目矫正图像的时间戳与光学坐标系
sensor_msgs/Image image  # 浮点视差图（编码固定为 `32FC1`，像素值为左右目视差 $d$ [像素]）
float32 f  # 矫正后相机的焦距 [像素]
float32 t  # 双目基线距离 $T$ [m]（右目相对于左目的平移基线，通常为正值）
sensor_msgs/RegionOfInterest valid_window  # 有效视差图像窗口（排除匹配边界无效区域）
float32 min_disparity  # 最小搜索视差值（对应最远可测深度 $Z_{max} = f T / d_{min}$） [像素]
float32 max_disparity  # 最大搜索视差值（对应最近可测深度 $Z_{min} = f T / d_{max}$） [像素]
float32 delta_d  # 允许的最小亚像素视差步进分辨率 [像素]
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 左目矫正图像的时间戳与光学坐标系 |
| `image` | [`sensor_msgs/Image`](../../sensor_msgs/msg/Image.md) | — | 浮点视差图（编码固定为 `32FC1`，像素值为左右目视差 $d$ [像素]） |
| `f` | `float32` | — | 矫正后相机的焦距 [像素] |
| `t` | `float32` | — | 双目基线距离 $T$ [m]（右目相对于左目的平移基线，通常为正值） |
| `valid_window` | [`sensor_msgs/RegionOfInterest`](../../sensor_msgs/msg/RegionOfInterest.md) | — | 有效视差图像窗口（排除匹配边界无效区域） |
| `min_disparity` | `float32` | — | 最小搜索视差值（对应最远可测深度 $Z_{max} = f T / d_{min}$） [像素] |
| `max_disparity` | `float32` | — | 最大搜索视差值（对应最近可测深度 $Z_{min} = f T / d_{max}$） [像素] |
| `delta_d` | `float32` | — | 允许的最小亚像素视差步进分辨率 [像素] |

## 使用示例

### C++ 示例

```cpp
#include "stereo_msgs/msg/disparity_image.hpp"

// 1. 声明消息对象
stereo_msgs::msg::DisparityImage msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "camera_optical_frame";
msg.image.header.stamp.sec = 1700000000;
msg.image.header.stamp.nanosec = 500000000;
msg.image.header.frame_id = "camera_optical_frame";
msg.image.height = 480;
msg.image.width = 640;
msg.image.encoding = "32FC1";
msg.image.is_bigendian = 0;
msg.image.step = 2560;
msg.image.data.assign(640 * 480 * 4, 0);  // 32FC1 浮点视差字节缓冲
msg.f = 525.0f;
msg.t = 0.12f;
msg.valid_window.x_offset = 0;
msg.valid_window.y_offset = 0;
msg.valid_window.height = 480;
msg.valid_window.width = 640;
msg.valid_window.do_rectify = false;
msg.min_disparity = 0.0f;
msg.max_disparity = 64.0f;
msg.delta_d = 0.0625f;
```

### Python 示例

```python
from stereo_msgs.msg import DisparityImage

# 1. 声明消息对象
msg = DisparityImage()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "camera_optical_frame"
msg.image.header.stamp.sec = 1700000000
msg.image.header.stamp.nanosec = 500000000
msg.image.header.frame_id = "camera_optical_frame"
msg.image.height = 480
msg.image.width = 640
msg.image.encoding = "32FC1"
msg.image.is_bigendian = 0
msg.image.step = 2560
msg.image.data = [0] * (640 * 480 * 4)
msg.f = 525.0
msg.t = 0.12
msg.valid_window.x_offset = 0
msg.valid_window.y_offset = 0
msg.valid_window.height = 480
msg.valid_window.width = 640
msg.valid_window.do_rectify = False
msg.min_disparity = 0.0
msg.max_disparity = 64.0
msg.delta_d = 0.0625
```

---
⬅️ [返回 `stereo_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
