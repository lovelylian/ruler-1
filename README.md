Ruler.js
=====

强大，在于简单。这是一个简单的尺规作图引擎，可用于几何分析、课件制作、计算坐标等。

## 类型

尺规作图中需要四种基本的数据结构类型。

* `Number` - 数值类型，表示坐标值、距离或索引
* `Point` - 表示一个点，其中 `x` 和 `y` 属性分别表示横坐标和纵坐标
* `Line` - 表示一条直线，给出过该直线的两个点 (`x1`, `y1`) 和 (`x2`, `y2`)，以及 `dx` = `x2` - `x1` 和 `dy` = `y2` - `y1`
* `Arc` - 表示一个圆的圆弧，给出圆心坐标 (`x`, `y`)以及半径 `r`

## 表达式

原子表达式从传统的尺规作图中提取，主要包括定点、连线、作弧、求交点。基本表达式见下表：

Expression          |Description                     
--------------------|---------------------------
P1 = (100, 200)     | 定义点 P1，坐标是 (100, 200)            
l = P1 | P2         | 定义直线 l 经过 P1 和 P2          
d = P1 ~ P2         | 定义距离 d 为 P1 到 P2 的距离          
O1 = P1 @ d         | 定义圆 O1，圆心为 P1，半径为 d          
Q1 = l1 & l2        | 定义 Q1 为 l1 和 l2 的交点
Q2 = (l1 & O1)[0]   | 定义 Q2 为直线 l1 和圆 O1 的第一个交点  
Q3 = (O1 & O2)[1]   | 定义 Q3 为圆 O1 和员 O2 的第二个交点

