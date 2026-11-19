[🏠 首页](../README.md) / **nav_msgs**

# `nav_msgs` — 机器人导航接口包

定义了移动机器人定位、建图、里程计与路径规划的标准消息与服务，是 Nav2、SLAM Toolbox 与 Cartographer 等导航栈的核心接口。

## 消息列表（`msg/`，共 6 个）

| 消息名称 | 简介 |
| :--- | :--- |
| [`Goals`](./msg/Goals.md) | 多目标航点集合 |
| [`GridCells`](./msg/GridCells.md) | 二维栅格中心点集合 |
| [`MapMetaData`](./msg/MapMetaData.md) | 二维栅格地图元数据 |
| [`OccupancyGrid`](./msg/OccupancyGrid.md) | 二维概率占据栅格地图 |
| [`Odometry`](./msg/Odometry.md) | 机器人里程计估计（位姿 + 速度） |
| [`Path`](./msg/Path.md) | 导航规划路径（有序位姿序列） |

## 服务列表（`srv/`，共 4 个）

| 服务名称 | 简介 |
| :--- | :--- |
| [`GetMap`](./srv/GetMap.md) | 获取静态栅格地图服务 |
| [`GetPlan`](./srv/GetPlan.md) | 请求全局路径规划服务 |
| [`LoadMap`](./srv/LoadMap.md) | 从文件或 URI 加载地图服务 |
| [`SetMap`](./srv/SetMap.md) | 设置新地图与机器人初始位姿服务 |

---
⬅️ [返回总目录](../README.md)
