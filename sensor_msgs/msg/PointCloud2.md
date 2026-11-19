[🏠 首页](../../README.md) / [`sensor_msgs`](../README.md) / `msg` / **PointCloud2**

# `sensor_msgs/msg/PointCloud2`

> 标准通用多维三维点云消息

以紧凑的二进制缓冲流存储任意自定义通道结构的有序或无序三维点云，是 3D 激光雷达（Velodyne、Ouster、Livox 等）与 RGB-D 深度相机点云的标准接口。

## 接口定义（`.msg`）

```msg
std_msgs/Header header  # 点云采集时间戳与传感器坐标系
uint32 height  # 点云二维高度；对于无序点云固定为 `1`，对于深度图转化的有序点云则为图像行数
uint32 width  # 点云宽度；对于无序点云即为总点数
PointField[] fields  # 描述每个点内各属性通道布局的字段定义数组
bool is_bigendian  # 二进制数据是否采用大端字节序
uint32 point_step  # 单个点占用的总字节数 [bytes]
uint32 row_step  # 单行点云占用的总字节数 [bytes]
uint8[] data  # 原始二进制点云字节流，总大小为 `row_step * height`
bool is_dense  # 若点云中不包含任何 `NaN` 或 `Inf` 无效点则为 `true`
```

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `header` | [`std_msgs/Header`](../../std_msgs/msg/Header.md) | — | 点云采集时间戳与传感器坐标系 |
| `height` | `uint32` | — | 点云二维高度；对于无序点云固定为 `1`，对于深度图转化的有序点云则为图像行数 |
| `width` | `uint32` | — | 点云宽度；对于无序点云即为总点数 |
| `fields` | [`PointField`](./PointField.md)`[]` | — | 描述每个点内各属性通道布局的字段定义数组 |
| `is_bigendian` | `bool` | — | 二进制数据是否采用大端字节序 |
| `point_step` | `uint32` | — | 单个点占用的总字节数 [bytes] |
| `row_step` | `uint32` | — | 单行点云占用的总字节数 [bytes] |
| `data` | `uint8[]` | — | 原始二进制点云字节流，总大小为 `row_step * height` |
| `is_dense` | `bool` | — | 若点云中不包含任何 `NaN` 或 `Inf` 无效点则为 `true` |

## 使用示例

### C++ 示例

```cpp
#include "sensor_msgs/msg/point_cloud2.hpp"

// 1. 声明消息对象
sensor_msgs::msg::PointCloud2 msg;

// 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000;
msg.header.stamp.nanosec = 500000000;
msg.header.frame_id = "lidar_link";
msg.height = 1;
msg.width = 2;
sensor_msgs::msg::PointField point_field;
point_field.name = "x";
point_field.offset = 0;
point_field.datatype = sensor_msgs::msg::PointField::FLOAT32;
point_field.count = 1;
msg.fields.push_back(point_field);
msg.is_bigendian = false;
msg.point_step = 12;
msg.row_step = 24;
msg.data.assign(24, 0);  // 2 个点 * 12 字节/点 的示例二进制缓冲
msg.is_dense = true;
```

### Python 示例

```python
from sensor_msgs.msg import PointCloud2, PointField

# 1. 声明消息对象
msg = PointCloud2()

# 2. 对消息字段进行赋值
msg.header.stamp.sec = 1700000000
msg.header.stamp.nanosec = 500000000
msg.header.frame_id = "lidar_link"
msg.height = 1
msg.width = 2
point_field = PointField()
point_field.name = "x"
point_field.offset = 0
point_field.datatype = PointField.FLOAT32
point_field.count = 1
msg.fields.append(point_field)
msg.is_bigendian = False
msg.point_step = 12
msg.row_step = 24
msg.data = [0] * 24
msg.is_dense = True
```

---
⬅️ [返回 `sensor_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
