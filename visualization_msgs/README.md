[🏠 首页](../README.md) / **visualization_msgs**

# `visualization_msgs` — RViz 三维可视化与交互接口包

提供在 RViz 2 中绘制自定义三维几何图形、文本、网格纹理、二维图像叠加标记以及可鼠标拖拽交互控件（Interactive Markers）的全部消息与服务。

## 消息列表（`msg/`，共 12 个）

| 消息名称 | 简介 |
| :--- | :--- |
| [`ImageMarker`](./msg/ImageMarker.md) | 二维图像叠加可视化标记 |
| [`InteractiveMarker`](./msg/InteractiveMarker.md) | RViz 可拖拽交互式三维标记主体 |
| [`InteractiveMarkerControl`](./msg/InteractiveMarkerControl.md) | 交互式标记的单个自由度控制器 |
| [`InteractiveMarkerFeedback`](./msg/InteractiveMarkerFeedback.md) | RViz 交互标记用户操作反馈消息 |
| [`InteractiveMarkerInit`](./msg/InteractiveMarkerInit.md) | 交互标记服务器全量初始化消息 |
| [`InteractiveMarkerPose`](./msg/InteractiveMarkerPose.md) | 交互式标记的位姿增量更新 |
| [`InteractiveMarkerUpdate`](./msg/InteractiveMarkerUpdate.md) | 交互标记服务器增量更新消息 |
| [`Marker`](./msg/Marker.md) | RViz 2 三维可视化几何标记 |
| [`MarkerArray`](./msg/MarkerArray.md) | 批量三维可视化标记数组 |
| [`MenuEntry`](./msg/MenuEntry.md) | 交互式标记右键上下文菜单项 |
| [`MeshFile`](./msg/MeshFile.md) | 内嵌二进制三维网格文件 |
| [`UVCoordinate`](./msg/UVCoordinate.md) | 网格纹理映射 UV 坐标 |

## 服务列表（`srv/`，共 1 个）

| 服务名称 | 简介 |
| :--- | :--- |
| [`GetInteractiveMarkers`](./srv/GetInteractiveMarkers.md) | 请求全部当前活跃交互标记服务 |

---
⬅️ [返回总目录](../README.md)
