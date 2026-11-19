[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **CameraInfo**

# `sensor_msgs/msg/CameraInfo`

> 相机内参、畸变参数与投影矩阵

包含单目或双目相机的几何标定元数据，通常与 `sensor_msgs/Image` 同步发布在同命名空间的 `camera_info` 话题上，供 `image_proc` 去畸变和 3D 反投影使用。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 与对应图像同步的曝光时间戳与光学坐标系（Z 轴向前，X 向右，Y 向下）
uint32 height  # 标定时使用的全分辨率图像高度 [像素]
uint32 width  # 标定时使用的全分辨率图像宽度 [像素]
string distortion_model  # 镜头畸变模型名称（如 `plumb_bob`、`rational_polynomial`、`equidistant`）
float64[] d  # 畸变系数数组；在 `plumb_bob` 模式下为 `[k1, k2, t1, t2, k3]`
float64[9] k  # 行优先 3×3 原始图像内参矩阵 `[fx, 0, cx; 0, fy, cy; 0, 0, 1]`
float64[9] r  # 行优先 3×3 立体矫正旋转矩阵（单目相机通常为单位矩阵）
float64[12] p  # 行优先 3×4 投影矩阵，将 3D 相机坐标投影到矫正后的 2D 像素平面
uint32 binning_x  # 水平方向像素合并（Binning）系数（`0` 或 `1` 表示未合并）
uint32 binning_y  # 垂直方向像素合并（Binning）系数（`0` 或 `1` 表示未合并）
RegionOfInterest roi  # 当前图像相对于全分辨率画幅的感兴趣区域裁剪窗口
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 与对应图像同步的曝光时间戳与光学坐标系（Z 轴向前，X 向右，Y 向下） |
| `height` | `uint32` | — | 标定时使用的全分辨率图像高度 [像素] |
| `width` | `uint32` | — | 标定时使用的全分辨率图像宽度 [像素] |
| `distortion_model` | `string` | — | 镜头畸变模型名称（如 `plumb_bob`、`rational_polynomial`、`equidistant`） |
| `d` | `float64[]` | — | 畸变系数数组；在 `plumb_bob` 模式下为 `[k1, k2, t1, t2, k3]` |
| `k` | `float64[9]` | — | 行优先 3×3 原始图像内参矩阵 `[fx, 0, cx; 0, fy, cy; 0, 0, 1]` |
| `r` | `float64[9]` | — | 行优先 3×3 立体矫正旋转矩阵（单目相机通常为单位矩阵） |
| `p` | `float64[12]` | — | 行优先 3×4 投影矩阵，将 3D 相机坐标投影到矫正后的 2D 像素平面 |
| `binning_x` | `uint32` | — | 水平方向像素合并（Binning）系数（`0` 或 `1` 表示未合并） |
| `binning_y` | `uint32` | — | 垂直方向像素合并（Binning）系数（`0` 或 `1` 表示未合并） |
| `roi` | [`RegionOfInterest`](./RegionOfInterest.md) | — | 当前图像相对于全分辨率画幅的感兴趣区域裁剪窗口 |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/camera_info.hpp"

// 1. 声明消息对象
sensor_msgs::msg::CameraInfo msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "camera_optical_frame";
msg.height = 480;
msg.width = 640;
msg.distortion_model = "plumb_bob";
msg.d = {-0.1, 0.01, 0.0, 0.0, 0.0};
msg.k = {525.0, 0.0, 319.5, 0.0, 525.0, 239.5, 0.0, 0.0, 1.0};
msg.r = {1.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 1.0};
msg.p = {525.0, 0.0, 319.5, 0.0, 0.0, 525.0, 239.5, 0.0, 0.0, 0.0, 1.0, 0.0};
msg.binning_x = 1;
msg.binning_y = 1;
msg.roi.x_offset = 0;
msg.roi.y_offset = 0;
msg.roi.height = 480;
msg.roi.width = 640;
msg.roi.do_rectify = false;
```

### Python 示例

```python
from sensor_msgs.msg import CameraInfo

# 1. 声明消息对象
msg = CameraInfo()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "camera_optical_frame"
msg.height = 480
msg.width = 640
msg.distortion_model = "plumb_bob"
msg.d = [-0.1, 0.01, 0.0, 0.0, 0.0]
msg.k = [525.0, 0.0, 319.5, 0.0, 525.0, 239.5, 0.0, 0.0, 1.0]
msg.r = [1.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 1.0]
msg.p = [525.0, 0.0, 319.5, 0.0, 0.0, 525.0, 239.5, 0.0, 0.0, 0.0, 1.0, 0.0]
msg.binning_x = 1
msg.binning_y = 1
msg.roi.x_offset = 0
msg.roi.y_offset = 0
msg.roi.height = 480
msg.roi.width = 640
msg.roi.do_rectify = False
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
