[🏠 首页](../README.md) / **sensor_msgs_py**

# `sensor_msgs_py` — 传感器消息 Python 辅助工具库

`sensor_msgs_py` 是 [`ros2/common_interfaces`](https://github.com/ros2/common_interfaces) 仓库中包含的官方 Python 辅助包（不含独立 `.msg`/`.srv` 定义），主要用于在 Python 节点中高效读写二进制点云 [`sensor_msgs/msg/PointCloud2`](../sensor_msgs/msg/PointCloud2.md)。

## 核心模块：`sensor_msgs_py.point_cloud2`

| 函数名 | 功能说明 |
| :--- | :--- |
| `read_points(cloud, field_names=None, skip_nans=False, uvs=None, reshape_organized_cloud=False)` | 从 `PointCloud2` 中读取点数据，返回结构化 NumPy 数组 |
| `read_points_numpy(cloud, field_names=None, skip_nans=False, uvs=None, reshape_organized_cloud=False)` | 直接将相同数据类型的点云字段提取为普通 2D NumPy 浮点数组（性能更高） |
| `read_points_list(cloud, field_names=None, skip_nans=False, uvs=None)` | 将 `PointCloud2` 转为 Python `namedtuple` 列表 |
| `create_cloud(header, fields, points, step=None)` | 根据自定义 [`PointField`](../sensor_msgs/msg/PointField.md) 列表与点数据构造 `PointCloud2` 消息 |
| `create_cloud_xyz32(header, points)` | 快捷创建仅包含 `x, y, z`（`float32`）三通道的 `PointCloud2` 消息 |

## 快速使用示例

```python
from sensor_msgs_py import point_cloud2
from std_msgs.msg import Header

# 1. 读取点云 XYZ 坐标为 NumPy 数组
points_np = point_cloud2.read_points_numpy(cloud_msg, field_names=("x", "y", "z"), skip_nans=True)

# 2. 创建仅含 XYZ 的 PointCloud2 消息
header = Header(frame_id="lidar_link")
new_cloud = point_cloud2.create_cloud_xyz32(header, [[1.0, 2.0, 0.5], [1.5, 2.1, 0.4]])
```

---
⬅️ [返回总目录](../README.md)
