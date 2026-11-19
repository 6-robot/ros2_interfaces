[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **Image**

# `sensor_msgs/msg/Image`

> 未压缩原始二维图像

ROS 2 中最核心的视觉图像传输消息，支持 RGB、BGR、灰度、深度图（16UC1/32FC1）及 Bayer 原始格式。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 图像采集时间戳与相机光学坐标系
uint32 height  # 图像高度（总行数） [像素]
uint32 width  # 图像宽度（总列数） [像素]
string encoding  # 像素编码字符串（如 `rgb8`、`bgr8`、`mono8`、`rgba8`、`16UC1`、`32FC1`）
uint8 is_bigendian  # 多字节像素是否采用大端字节序存储（`0`=小端，`1`=大端）
uint32 step  # 单行图像所占用的完整字节跨度（stride） [bytes]
uint8[] data  # 原始像素字节数组，总长度为 `step * height`
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 图像采集时间戳与相机光学坐标系 |
| `height` | `uint32` | — | 图像高度（总行数） [像素] |
| `width` | `uint32` | — | 图像宽度（总列数） [像素] |
| `encoding` | `string` | — | 像素编码字符串（如 `rgb8`、`bgr8`、`mono8`、`rgba8`、`16UC1`、`32FC1`） |
| `is_bigendian` | `uint8` | — | 多字节像素是否采用大端字节序存储（`0`=小端，`1`=大端） |
| `step` | `uint32` | — | 单行图像所占用的完整字节跨度（stride） [bytes] |
| `data` | `uint8[]` | — | 原始像素字节数组，总长度为 `step * height` |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/image.hpp"

// 1. 声明消息对象
sensor_msgs::msg::Image msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "camera_optical_frame";
msg.height = 480;
msg.width = 640;
msg.encoding = "rgb8";
msg.is_bigendian = 0;
msg.step = 1920;
msg.data.assign(640 * 480 * 3, 128);  // 填充示例 RGB 像素数据
```

### Python 示例

```python
from sensor_msgs.msg import Image

# 1. 声明消息对象
msg = Image()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "camera_optical_frame"
msg.height = 480
msg.width = 640
msg.encoding = "rgb8"
msg.is_bigendian = 0
msg.step = 1920
msg.data = [128] * (640 * 480 * 3)
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
