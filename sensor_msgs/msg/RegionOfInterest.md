[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **RegionOfInterest**

# `sensor_msgs/msg/RegionOfInterest`

> 图像感兴趣区域（ROI）裁剪矩形

定义全分辨率图像中的一个矩形子区域，用于硬件 ROI 裁剪或相机标定对齐。

## 接口定义（`.msg`）

```msg
uint32 x_offset  # ROI 左上角相对图像左边缘的 X 像素偏移
uint32 y_offset  # ROI 左上角相对图像上边缘的 Y 像素偏移
uint32 height  # ROI 区域高度 [像素]
uint32 width  # ROI 区域宽度 [像素]
bool do_rectify  # 指示下游处理节点是否应对该 ROI 执行立体/去畸变矫正
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `x_offset` | `uint32` | — | ROI 左上角相对图像左边缘的 X 像素偏移 |
| `y_offset` | `uint32` | — | ROI 左上角相对图像上边缘的 Y 像素偏移 |
| `height` | `uint32` | — | ROI 区域高度 [像素] |
| `width` | `uint32` | — | ROI 区域宽度 [像素] |
| `do_rectify` | `bool` | — | 指示下游处理节点是否应对该 ROI 执行立体/去畸变矫正 |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/region_of_interest.hpp"

// 1. 声明消息对象
sensor_msgs::msg::RegionOfInterest msg;

// 2. 对消息字段进行赋值
msg.x_offset = 0;
msg.y_offset = 0;
msg.height = 480;
msg.width = 640;
msg.do_rectify = false;
```

### Python 示例

```python
from sensor_msgs.msg import RegionOfInterest

# 1. 声明消息对象
msg = RegionOfInterest()

# 2. 对消息字段进行赋值
msg.x_offset = 0
msg.y_offset = 0
msg.height = 480
msg.width = 640
msg.do_rectify = False
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
