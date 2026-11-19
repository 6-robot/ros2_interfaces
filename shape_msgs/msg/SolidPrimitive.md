[🏠 首页](../../README.md) / [`shape_msgs`](../README.md) / `msg` / **SolidPrimitive**

# `shape_msgs/msg/SolidPrimitive`

> 基础三维规则几何实体（立方体/球/圆柱/圆锥/棱柱）

表示以局部坐标系原点为几何中心的规则三维实体，通过 `type` 与 `dimensions` 紧凑表达尺寸。

## 接口定义（`.msg`）

```msg
# --- 常量定义 ---
uint8 BOX=1  # 长方体
uint8 SPHERE=2  # 球体
uint8 CYLINDER=3  # 圆柱体（中心轴沿 Z 轴）
uint8 CONE=4  # 圆锥体（中心轴沿 Z 轴，顶点朝向 +Z）
uint8 PRISM=5  # 直棱柱（底面由 `polygon` 定义，沿 Z 轴拉伸）
uint8 BOX_X=0  # 长方体 X 轴尺寸在 `dimensions` 中的下标
uint8 BOX_Y=1  # 长方体 Y 轴尺寸在 `dimensions` 中的下标
uint8 BOX_Z=2  # 长方体 Z 轴尺寸在 `dimensions` 中的下标
uint8 SPHERE_RADIUS=0  # 球体半径在 `dimensions` 中的下标
uint8 CYLINDER_HEIGHT=0  # 圆柱体高度在 `dimensions` 中的下标
uint8 CYLINDER_RADIUS=1  # 圆柱体半径在 `dimensions` 中的下标
uint8 CONE_HEIGHT=0  # 圆锥体高度在 `dimensions` 中的下标
uint8 CONE_RADIUS=1  # 圆锥体底面半径在 `dimensions` 中的下标
uint8 PRISM_HEIGHT=0  # 棱柱高度在 `dimensions` 中的下标

# --- 字段定义 ---
uint8 type  # 几何体类型（`BOX` / `SPHERE` / `CYLINDER` / `CONE` / `PRISM`）
float64[<=3] dimensions  # 尺寸参数数组（最多 3 个元素，各下标含义见上方常量） [m]
geometry_msgs/Polygon polygon  # 仅当 `type == PRISM` 时有效，定义位于 `Z=0` 平面上的底面二维多边形
```

## 常量说明

| 常量名 | 类型 | 值 | 说明 |
| :--- | :--- | :--- | :--- |
| `BOX` | `uint8` | `1` | 长方体 |
| `SPHERE` | `uint8` | `2` | 球体 |
| `CYLINDER` | `uint8` | `3` | 圆柱体（中心轴沿 Z 轴） |
| `CONE` | `uint8` | `4` | 圆锥体（中心轴沿 Z 轴，顶点朝向 +Z） |
| `PRISM` | `uint8` | `5` | 直棱柱（底面由 `polygon` 定义，沿 Z 轴拉伸） |
| `BOX_X` | `uint8` | `0` | 长方体 X 轴尺寸在 `dimensions` 中的下标 |
| `BOX_Y` | `uint8` | `1` | 长方体 Y 轴尺寸在 `dimensions` 中的下标 |
| `BOX_Z` | `uint8` | `2` | 长方体 Z 轴尺寸在 `dimensions` 中的下标 |
| `SPHERE_RADIUS` | `uint8` | `0` | 球体半径在 `dimensions` 中的下标 |
| `CYLINDER_HEIGHT` | `uint8` | `0` | 圆柱体高度在 `dimensions` 中的下标 |
| `CYLINDER_RADIUS` | `uint8` | `1` | 圆柱体半径在 `dimensions` 中的下标 |
| `CONE_HEIGHT` | `uint8` | `0` | 圆锥体高度在 `dimensions` 中的下标 |
| `CONE_RADIUS` | `uint8` | `1` | 圆锥体底面半径在 `dimensions` 中的下标 |
| `PRISM_HEIGHT` | `uint8` | `0` | 棱柱高度在 `dimensions` 中的下标 |

## 字段说明

| 字段名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `type` | `uint8` | — | 几何体类型（`BOX` / `SPHERE` / `CYLINDER` / `CONE` / `PRISM`） |
| `dimensions` | `float64[<=3]` | — | 尺寸参数数组（最多 3 个元素，各下标含义见上方常量） [m] |
| `polygon` | [`geometry_msgs/Polygon`](../../geometry_msgs/msg/Polygon.md) | — | 仅当 `type == PRISM` 时有效，定义位于 `Z=0` 平面上的底面二维多边形 |

## 使用示例

### C++ 示例

```cpp
#include "shape_msgs/msg/solid_primitive.hpp"

// 1. 声明消息对象
shape_msgs::msg::SolidPrimitive msg;

// 2. 对消息字段进行赋值
msg.type = shape_msgs::msg::SolidPrimitive::BOX;
msg.dimensions = {0.5, 0.4, 0.3};  // 长方体尺寸 [BOX_X, BOX_Y, BOX_Z]
// 当 type == PRISM 时可为 msg.polygon.points 赋值底面多边形顶点
```

### Python 示例

```python
from shape_msgs.msg import SolidPrimitive

# 1. 声明消息对象
msg = SolidPrimitive()

# 2. 对消息字段进行赋值
msg.type = SolidPrimitive.BOX
msg.dimensions = [0.5, 0.4, 0.3]
# 当 type == PRISM 时可为 msg.polygon.points 赋值底面多边形顶点
```

---
⬅️ [返回 `shape_msgs` 目录](../README.md) ｜ 🏠 [返回总目录](../../README.md)
