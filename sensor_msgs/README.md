[🏠 首页](../README.md) / **sensor_msgs**

# `sensor_msgs` — 传感器标准数据接口包

定义机器人常用传感器的全套标准接口，涵盖 2D/3D 激光雷达、单目与压缩图像、相机标定内参、三维点云、IMU、磁力计、GNSS/GPS、关节状态、手柄摇杆、电池及各类环境传感器。

## 消息列表（`msg/`，共 27 个）

| 消息名称 | 简介 |
| :--- | :--- |
| [`BatteryState`](./msg/BatteryState.md) | 电池电压、电流、电量与健康状态 |
| [`CameraInfo`](./msg/CameraInfo.md) | 相机内参、畸变参数与投影矩阵 |
| [`ChannelFloat32`](./msg/ChannelFloat32.md) | 旧版点云附加属性通道 |
| [`CompressedImage`](./msg/CompressedImage.md) | 压缩格式图像数据（JPEG / PNG） |
| [`FluidPressure`](./msg/FluidPressure.md) | 流体压力（气压/水压）读数 |
| [`Illuminance`](./msg/Illuminance.md) | 环境光照强度读数 |
| [`Image`](./msg/Image.md) | 未压缩原始二维图像 |
| [`Imu`](./msg/Imu.md) | 惯性测量单元（姿态 + 角速度 + 线加速度） |
| [`JointState`](./msg/JointState.md) | 机器人各关节实时位置、速度与力矩 |
| [`Joy`](./msg/Joy.md) | 游戏手柄/遥控器摇杆与按键输入 |
| [`JoyFeedback`](./msg/JoyFeedback.md) | 单个手柄震动/LED 反馈控制指令 |
| [`JoyFeedbackArray`](./msg/JoyFeedbackArray.md) | 手柄反馈控制指令数组 |
| [`LaserEcho`](./msg/LaserEcho.md) | 单束激光的多回波测距/强度值 |
| [`LaserScan`](./msg/LaserScan.md) | 单线（2D）平面激光雷达扫描数据 |
| [`MagneticField`](./msg/MagneticField.md) | 三轴磁场强度读数（磁力计） |
| [`MultiDOFJointState`](./msg/MultiDOFJointState.md) | 多自由度关节实时状态 |
| [`MultiEchoLaserScan`](./msg/MultiEchoLaserScan.md) | 支持多回波的 2D 激光雷达扫描数据 |
| [`NavSatFix`](./msg/NavSatFix.md) | 全球卫星定位经纬高（WGS84）数据 |
| [`NavSatStatus`](./msg/NavSatStatus.md) | 全球卫星导航系统（GNSS/GPS）定位状态 |
| [`PointCloud`](./msg/PointCloud.md) | 旧版三维点云消息（已弃用） |
| [`PointCloud2`](./msg/PointCloud2.md) | 标准通用多维三维点云消息 |
| [`PointField`](./msg/PointField.md) | PointCloud2 中单个点属性的二进制布局描述 |
| [`Range`](./msg/Range.md) | 单点超声波/红外测距传感器读数 |
| [`RegionOfInterest`](./msg/RegionOfInterest.md) | 图像感兴趣区域（ROI）裁剪矩形 |
| [`RelativeHumidity`](./msg/RelativeHumidity.md) | 环境相对湿度读数 |
| [`Temperature`](./msg/Temperature.md) | 环境或设备温度读数 |
| [`TimeReference`](./msg/TimeReference.md) | 外部硬件时钟参考（如 GPS PPS） |

## 服务列表（`srv/`，共 1 个）

| 服务名称 | 简介 |
| :--- | :--- |
| [`SetCameraInfo`](./srv/SetCameraInfo.md) | 向相机驱动写入标定内参服务 |

---
⬅️ [返回总目录](../README.md)
