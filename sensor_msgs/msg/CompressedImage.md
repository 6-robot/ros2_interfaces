[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **CompressedImage**

# `sensor_msgs/msg/CompressedImage`

> 压缩格式图像数据（JPEG / PNG）

承载经过压缩编码的二维图像二进制流，显著降低网络带宽占用，常由 `image_transport` 插件发布。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 曝光时间戳与相机光学坐标系
string format  # 压缩格式描述（如 `jpeg`、`png`、`tiff` 或 `bgr8; jpeg compressed bgr8`）
uint8[] data  # 压缩后的图像原始字节流
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 曝光时间戳与相机光学坐标系 |
| `format` | `string` | — | 压缩格式描述（如 `jpeg`、`png`、`tiff` 或 `bgr8; jpeg compressed bgr8`） |
| `data` | `uint8[]` | — | 压缩后的图像原始字节流 |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/compressed_image.hpp"

// 1. 声明消息对象
sensor_msgs::msg::CompressedImage msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "camera_optical_frame";
msg.format = "jpeg";
msg.data = {0xFF, 0xD8, 0xFF, 0xE0};  // 示例 JPEG 字节头
```

### Python 示例

```python
from sensor_msgs.msg import CompressedImage

# 1. 声明消息对象
msg = CompressedImage()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "camera_optical_frame"
msg.format = "jpeg"
msg.data = [0xFF, 0xD8, 0xFF, 0xE0]
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
