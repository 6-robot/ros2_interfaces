[🏠 首页](../README.md) / **geometry_msgs**

# `geometry_msgs` — 几何空间基元消息包

提供三维空间中点、向量、四元数、位姿、坐标变换、速度、加速度、力/力矩、惯性张量与多边形的标准几何定义，是 TF2、导航、规划与控制的基础依赖。

## 消息列表（`msg/`，共 33 个）

| 消息名称 | 简介 |
| :--- | :--- |
| [`Accel`](./msg/Accel.md) | 自由空间线加速度与角加速度 |
| [`AccelStamped`](./msg/AccelStamped.md) | 带消息头的线加速度与角加速度 |
| [`AccelWithCovariance`](./msg/AccelWithCovariance.md) | 带 6×6 协方差矩阵的加速度 |
| [`AccelWithCovarianceStamped`](./msg/AccelWithCovarianceStamped.md) | 带消息头与协方差矩阵的加速度 |
| [`Inertia`](./msg/Inertia.md) | 刚体质量与惯性张量 |
| [`InertiaStamped`](./msg/InertiaStamped.md) | 带消息头的刚体惯性参数 |
| [`Point`](./msg/Point.md) | 三维空间点（双精度 `float64`） |
| [`Point32`](./msg/Point32.md) | 三维空间点（单精度 `float32`） |
| [`PointStamped`](./msg/PointStamped.md) | 带坐标系与时间戳的三维点 |
| [`Polygon`](./msg/Polygon.md) | 闭合多边形顶点列表 |
| [`PolygonInstance`](./msg/PolygonInstance.md) | 带唯一 ID 的多边形实例 |
| [`PolygonInstanceStamped`](./msg/PolygonInstanceStamped.md) | 带消息头与唯一 ID 的多边形实例 |
| [`PolygonStamped`](./msg/PolygonStamped.md) | 带消息头的闭合多边形 |
| [`Pose`](./msg/Pose.md) | 三维空间位姿（位置 + 姿态） |
| [`Pose2D`](./msg/Pose2D.md) | 二维平面位姿（已弃用） |
| [`PoseArray`](./msg/PoseArray.md) | 同一坐标系下的一组位姿集合 |
| [`PoseStamped`](./msg/PoseStamped.md) | 带坐标系与时间戳的三维位姿 |
| [`PoseWithCovariance`](./msg/PoseWithCovariance.md) | 带 6×6 协方差矩阵的三维位姿 |
| [`PoseWithCovarianceStamped`](./msg/PoseWithCovarianceStamped.md) | 带消息头与协方差矩阵的位姿 |
| [`Quaternion`](./msg/Quaternion.md) | 三维旋转单位四元数 |
| [`QuaternionStamped`](./msg/QuaternionStamped.md) | 带消息头的单位四元数 |
| [`Transform`](./msg/Transform.md) | 三维坐标系刚体变换 |
| [`TransformStamped`](./msg/TransformStamped.md) | 带时间戳与父子坐标系名称的坐标变换 |
| [`Twist`](./msg/Twist.md) | 自由空间线速度与角速度 |
| [`TwistStamped`](./msg/TwistStamped.md) | 带消息头的线速度与角速度 |
| [`TwistWithCovariance`](./msg/TwistWithCovariance.md) | 带 6×6 协方差矩阵的速度 |
| [`TwistWithCovarianceStamped`](./msg/TwistWithCovarianceStamped.md) | 带消息头与协方差矩阵的速度 |
| [`Vector3`](./msg/Vector3.md) | 三维自由向量（仅含方向与大小） |
| [`Vector3Stamped`](./msg/Vector3Stamped.md) | 带消息头的三维向量 |
| [`VelocityStamped`](./msg/VelocityStamped.md) | 显式标注本体与参考系的广义空间速度 |
| [`VelocityWithCovarianceStamped`](./msg/VelocityWithCovarianceStamped.md) | 带协方差矩阵的广义空间速度（显式标注本体与参考系） |
| [`Wrench`](./msg/Wrench.md) | 自由空间力与力矩 |
| [`WrenchStamped`](./msg/WrenchStamped.md) | 带消息头的力与力矩 |

---
⬅️ [返回总目录](../README.md)
