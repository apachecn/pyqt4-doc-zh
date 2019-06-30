# QMatrix Class Reference

## [[QtGui](index.htm) module]

该系列QMatrix类指定坐标系的2D变换。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, float m11, float m12, float m21, float m22, float dx, float dy)`
*   `__init__ (self, QMatrix matrix)`
*   `float det (self)`
*   `float determinant (self)`
*   `float dx (self)`
*   `float dy (self)`
*   `(QMatrix, bool invertible) inverted (self)`
*   `bool isIdentity (self)`
*   `bool isInvertible (self)`
*   `float m11 (self)`
*   `float m12 (self)`
*   `float m21 (self)`
*   `float m22 (self)`
*   `(int tx, int ty) map (self, int x, int y)`
*   `(float tx, float ty) map (self, float x, float y)`
*   `QPoint map (self, QPoint p)`
*   `QPointF map (self, QPointF p)`
*   `QLine map (self, QLine l)`
*   `QLineF map (self, QLineF l)`
*   `QPolygonF map (self, QPolygonF a)`
*   `QPolygon map (self, QPolygon a)`
*   `QRegion map (self, QRegion r)`
*   `QPainterPath map (self, QPainterPath p)`
*   `QRect mapRect (self, QRect)`
*   `QRectF mapRect (self, QRectF)`
*   `QPolygon mapToPolygon (self, QRect r)`
*   `reset (self)`
*   `QMatrix rotate (self, float a)`
*   `QMatrix scale (self, float sx, float sy)`
*   `setMatrix (self, float m11, float m12, float m21, float m22, float dx, float dy)`
*   `QMatrix shear (self, float sh, float sv)`
*   `QMatrix translate (self, float dx, float dy)`

### Special Methods

*   `bool __eq__ (self, QMatrix)`
*   `QMatrix __imul__ (self, QMatrix)`
*   `QMatrix __mul__ (self, QMatrix o)`
*   `bool __ne__ (self, QMatrix)`

* * *

## Detailed Description

这个类可以醃制。

该系列QMatrix类指定坐标系的2D变换。

矩阵指定如何转换，缩放，剪切或旋转的坐标系，并绘制图形时，通常使用。的QMatrix ，在对比[QTransform](qtransform.html)，不允许透视变换。[QTransform](qtransform.html)是Qt的建议转换类。

一个系列QMatrix对象可使用内置的[setMatrix](qmatrix.html#setMatrix)（ ）[scale](qmatrix.html#scale)（ ）[rotate](qmatrix.html#rotate)（ ）[translate](qmatrix.html#translate)（）和[shear](qmatrix.html#shear)（）函数。另外，它可以通过施加建[basic matrix operations](#basic-matrix-operations)。该矩阵也可以被定义时构造，并且它可以使用被重置为单位矩阵（默认值）的[reset](qmatrix.html#reset)（）函数。

该系列QMatrix类支持的图形原语映射：一个给定的点，线，多边形，区域或画家路径可以映射到由坐标系定义_this_使用矩阵[map](qmatrix.html#map)（）函数。在情况下的四边形的，它的坐标可以用转化的[mapRect](qmatrix.html#mapRect)（）函数。矩形也可以被改造成一个_polygon_（映射到定义的坐标系_this_矩阵），使用[mapToPolygon](qmatrix.html#mapToPolygon)（）函数。

系列QMatrix提供[isIdentity](qmatrix.html#isIdentity)（）函数，如果矩阵是单位矩阵，并且该方法返回True，则[isInvertible](qmatrix.html#isInvertible)（ ）函数如果矩阵是非奇异的（即AB = BA = I ），它返回True 。该[inverted](qmatrix.html#inverted)（ ）函数返回一个倒置的副本_this_矩阵，如果它是可逆的（否则返回单位矩阵） 。此外，系列QMatrix提供[determinant](qmatrix.html#determinant)（ ）函数返回矩阵的行列式。

最后，该系列QMatrix类支持矩阵乘法，而类的对象可以被串流播放，以及比较。

### Rendering Graphics

在绘制图形时，矩阵定义转换，但实际转换是由绘图函数中执行[QPainter](qpainter.html)。

默认情况下，[QPainter](qpainter.html)操作相关联的设备自己的坐标系上。标准坐标系统[QPaintDevice](qpaintdevice.html)有其原点位于左上角的位置。该_x_值向右增大;_y_值向下增大。有关完整说明，请参阅[coordinate system](index.htm)文档。

[QPainter](qpainter.html)有功能转换，缩放，剪切和旋转坐标系不使用的QMatrix 。例如：

| ![](../img/qmatrix-simpletransformation.png) | 

```
 void SimpleTransformation.paintEvent([QPaintEvent](qpaintevent.html) *)
 {
     [QPainter](qpainter.html) painter(this);
     painter.setPen([QPen](qpen.html)([Qt](qt.html).blue, 1, [Qt](qt.html).DashLine));
     painter.drawRect(0, 0, 100, 100);

     painter.rotate(45);

     painter.setFont([QFont](qfont.html)("Helvetica", 24));
     painter.setPen([QPen](qpen.html)([Qt](qt.html).black, 1));
     painter.drawText(20, 10, "QMatrix");
 }

```

 |

虽然这些功能都非常的方便，它可以更有效地建立的QMatrix和呼叫[QPainter.setMatrix](index.htm#setMatrix)（ ）如果你想执行一个以上的变换操作。例如：

| ![](../img/qmatrix-combinedtransformation.png) | 

```
 void CombinedTransformation.paintEvent([QPaintEvent](qpaintevent.html) *)
 {
     [QPainter](qpainter.html) painter(this);
     painter.setPen([QPen](qpen.html)([Qt](qt.html).blue, 1, [Qt](qt.html).DashLine));
     painter.drawRect(0, 0, 100, 100);

     QMatrix matrix;
     matrix.translate(50, 50);
     matrix.rotate(45);
     matrix.scale(0.5, 1.0);
     painter.setMatrix(matrix);

     painter.setFont([QFont](qfont.html)("Helvetica", 24));
     painter.setPen([QPen](qpen.html)([Qt](qt.html).black, 1));
     painter.drawText(20, 10, "QMatrix");
 }

```

 |

### Basic Matrix Operations

![](../img/qmatrix-representation.png)

一个系列QMatrix对象包含一个3× 3的矩阵。该`dx`和`dy`元素指定水平和垂直平移。该`m11`和`m22`元素指定水平和垂直缩放。最后，本`m21`和`m12`元素指定水平和垂直_shearing_。

使用下列公式的QMatrix转换成在平面上的点到另一点：

```
 x' = m11*x + m21*y + dx
 y' = m22*y + m12*x + dy

```

点_(x, y)_是原来的点，并_(x', y')_是变换点。_(x', y')_可以转化回_(x, y)_通过执行在相同的操作[inverted](qmatrix.html#inverted)（ ）矩阵。

各矩阵元素可以构造矩阵时进行设置，或通过使用[setMatrix](qmatrix.html#setMatrix)（ ）函数以后。它们也可以通过使用操纵[translate](qmatrix.html#translate)（ ）[rotate](qmatrix.html#rotate)（ ）[scale](qmatrix.html#scale)（）和[shear](qmatrix.html#shear)（ ）的便利功能，当前设定的值可以使用检索[m11](qmatrix.html#m11)（ ）[m12](qmatrix.html#m12)（ ）[m21](qmatrix.html#m21)（ ）[m22](qmatrix.html#m22)（ ）[dx](qmatrix.html#dx)（）和[dy](qmatrix.html#dy)（）函数。

翻译是最简单的改造。环境`dx`和`dy`将移动坐标系`dx`沿X轴和单位`dy`沿Y轴的单位。缩放可以通过设置来实现`m11`和`m22`。例如，设置`m11`为2，并`m22`1.5将增加一倍的高度，增加50％的宽度。该单位矩阵`m11`和`m22`设置为1（所有其他被设置为0）的点映射到其自身。剪切被控制`m12`和`m21`。这些元件设置值不同于零将扭转的坐标系。旋转通过仔细设置两个剪切因子和比例因子实现。

下面是使用基本的矩阵运算组合变换的例子：

| ![](../img/qmatrix-combinedtransformation.png) | 

```
 void BasicOperations.paintEvent([QPaintEvent](qpaintevent.html) *)
 {
     double pi = 3.14;

     double a    = pi/180 * 45.0;
     double sina = sin(a);
     double cosa = cos(a);

     QMatrix translationMatrix(1, 0, 0, 1, 50.0, 50.0);
     QMatrix rotationMatrix(cosa, sina, -sina, cosa, 0, 0);
     QMatrix scalingMatrix(0.5, 0, 0, 1.0, 0, 0);

     QMatrix matrix;
     matrix =  scalingMatrix * rotationMatrix * translationMatrix;

     [QPainter](qpainter.html) painter(this);
     painter.setPen([QPen](qpen.html)([Qt](qt.html).blue, 1, [Qt](qt.html).DashLine));
     painter.drawRect(0, 0, 100, 100);

     painter.setMatrix(matrix);

     painter.setFont([QFont](qfont.html)("Helvetica", 24));
     painter.setPen([QPen](qpen.html)([Qt](qt.html).black, 1));
     painter.drawText(20, 10, "QMatrix");
 }

```

 |

* * *

## Method Documentation

```
QMatrix.__init__ (self)
```

构造一个单位矩阵。

所有的元素都设置为零，除了`m11`和`m22`（指定刻度），它被设置为1 。

**See also** [reset](qmatrix.html#reset)（ ） 。

```
QMatrix.__init__ (self, float m11, float m12, float m21, float m22, float dx, float dy)
```

```
QMatrix.__init__ (self, QMatrix matrix)
```

构造一个矩阵的元素，_m11_，_m12_，_m21_，_m22_，_dx_和_dy_。

**See also** [setMatrix](qmatrix.html#setMatrix)（ ） 。

```
float QMatrix.det (self)
```

```
float QMatrix.determinant (self)
```

返回矩阵的行列式。

此功能被引入Qt的4.6 。

```
float QMatrix.dx (self)
```

返回水平平移因子。

**See also** [translate](qmatrix.html#translate)（）和[Basic Matrix Operations](qmatrix.html#basic-matrix-operations)。

```
float QMatrix.dy (self)
```

返回垂直平移因子。

**See also** [translate](qmatrix.html#translate)（）和[Basic Matrix Operations](qmatrix.html#basic-matrix-operations)。

```
(QMatrix, bool invertible) QMatrix.inverted (self)
```

返回该矩阵的一个倒置的副本。

如果矩阵是奇异的（不可逆的） ，则返回的矩阵是单位矩阵。如果_invertible_是有效的（即不为0 ） ，将其值设置为True，如果矩阵是可逆的，否则设置为False 。

**See also** [isInvertible](qmatrix.html#isInvertible)（ ） 。

```
bool QMatrix.isIdentity (self)
```

返回True如果矩阵为单位矩阵，否则返回False 。

**See also** [reset](qmatrix.html#reset)（ ） 。

```
bool QMatrix.isInvertible (self)
```

返回True如果矩阵是可逆的，否则返回False 。

**See also** [inverted](qmatrix.html#inverted)（ ） 。

```
float QMatrix.m11 (self)
```

返回水平缩放系数。

**See also** [scale](qmatrix.html#scale)（）和[Basic Matrix Operations](qmatrix.html#basic-matrix-operations)。

```
float QMatrix.m12 (self)
```

返回垂直剪切因素。

**See also** [shear](qmatrix.html#shear)（）和[Basic Matrix Operations](qmatrix.html#basic-matrix-operations)。

```
float QMatrix.m21 (self)
```

返回水平剪切的因素。

**See also** [shear](qmatrix.html#shear)（）和[Basic Matrix Operations](qmatrix.html#basic-matrix-operations)。

```
float QMatrix.m22 (self)
```

返回垂直缩放系数。

**See also** [scale](qmatrix.html#scale)（）和[Basic Matrix Operations](qmatrix.html#basic-matrix-operations)。

```
(int tx, int ty) QMatrix.map (self, int x, int y)
```

对应给定的坐标_x_和_y_成由该矩阵定义的坐标系。被放置在所得到的值*_tx_和*_ty_元。

则坐标值用下面的公式转化：

```
 x' = m11*x + m21*y + dx
 y' = m22*y + m12*x + dy

```

点（x ，y）是原始的点，和（ X'，Y '）是变换后的​​点。

**See also** [Basic Matrix Operations](qmatrix.html#basic-matrix-operations)。

```
(float tx, float ty) QMatrix.map (self, float x, float y)
```

```
QPoint QMatrix.map (self, QPoint p)
```

[

这是一个重载函数。

对应给定的坐标_x_和_y_成由该矩阵定义的坐标系。被放置在所得到的值*_tx_和*_ty_元。需要注意的是转换后的坐标四舍五入到最接近的整数。

](qpoint.html)

```
QPointF QMatrix.map (self, QPointF p)
```

[

这是一个重载函数。

](qpointf.html)

[创建并返回一个](qpointf.html)[QPointF](qpointf.html)对象，它是给定一个副本_point_，映射到由该矩阵定义的坐标系。

```
QLine QMatrix.map (self, QLine l)
```

[

这是一个重载函数。

](qline.html)

[创建并返回一个](qline.html)[QPoint](qpoint.html)对象，它是给定一个副本_point_，映射到由该矩阵定义的坐标系。需要注意的是转换后的坐标四舍五入到最接近的整数。

```
QLineF QMatrix.map (self, QLineF l)
```

[

这是一个重载函数。

](qlinef.html)

[创建并返回一个](qlinef.html)[QLineF](qlinef.html)对象，它是给定一个副本_line_，映射到由该矩阵定义的坐标系。

```
QPolygonF QMatrix.map (self, QPolygonF a)
```

[

这是一个重载函数。

](qpolygonf.html)

[创建并返回一个](qpolygonf.html)[QLine](qline.html)对象，它是给定一个副本_line_，映射到由该矩阵定义的坐标系。需要注意的是转换后的坐标四舍五入到最接近的整数。

```
QPolygon QMatrix.map (self, QPolygon a)
```

[

这是一个重载函数。

](qpolygon.html)

[创建并返回一个](qpolygon.html)[QPolygonF](qpolygonf.html)对象，它是给定一个副本_polygon_，映射到由该矩阵定义的坐标系。

```
QRegion QMatrix.map (self, QRegion r)
```

[

这是一个重载函数。

](qregion.html)

[创建并返回一个](qregion.html)[QPolygon](qpolygon.html)对象，它是给定一个副本_polygon_，映射到由该矩阵定义的坐标系。需要注意的是转换后的坐标四舍五入到最接近的整数。

```
QPainterPath QMatrix.map (self, QPainterPath p)
```

[

这是一个重载函数。

](qpainterpath.html)

[创建并返回一个](qpainterpath.html)[QRegion](qregion.html)对象，它是给定一个副本_region_，映射到由该矩阵定义的坐标系。

调用此方法可以是相当昂贵的，如果旋转或剪切的使用。

```
QRect QMatrix.mapRect (self, QRect)
```

[](qrect.html)

[创建并返回一个](qrect.html)[QRectF](qrectf.html)对象，它是给定一个副本_rectangle_，映射到由该矩阵定义的坐标系。

矩形的坐标是用下面的公式转化：

```
 x' = m11*x + m21*y + dx
 y' = m22*y + m12*x + dy

```

如果已经指定旋转或剪切，这个函数返回_bounding_矩形。要检索的精确区域定_rectangle_映射到，使用[mapToPolygon](qmatrix.html#mapToPolygon)（ ）函数来代替。

**See also** [mapToPolygon](qmatrix.html#mapToPolygon)（）和[Basic Matrix Operations](qmatrix.html#basic-matrix-operations)。

```
QRectF QMatrix.mapRect (self, QRectF)
```

[

这是一个重载函数。

](qrectf.html)

[创建并返回一个](qrectf.html)[QRect](qrect.html)对象，它是给定一个副本_rectangle_，映射到由该矩阵定义的坐标系。需要注意的是转换后的坐标四舍五入到最接近的整数。

```
QPolygon QMatrix.mapToPolygon (self, QRect r)
```

[](qpolygon.html)

[创建并返回一个](qpolygon.html)[QPolygon](qpolygon.html)给定的表示_rectangle_，映射到由该矩阵定义的坐标系。

矩形的坐标是用下面的公式转化：

```
 x' = m11*x + m21*y + dx
 y' = m22*y + m12*x + dy

```

多边形和矩形的行为略有不同，当转换（由于四舍五入的整数） ，所以`matrix.map(QPolygon(rectangle))`并不总是相同`matrix.mapToPolygon(rectangle)`。

**See also** [mapRect](qmatrix.html#mapRect)（）和[Basic Matrix Operations](qmatrix.html#basic-matrix-operations)。

```
QMatrix.reset (self)
```

重置矩阵单位矩阵，即所有元素都设置为零，除非`m11`和`m22`（指定刻度），其被设置为1 。

**See also** [QMatrix](qmatrix.html#QMatrix)（ ）[isIdentity](qmatrix.html#isIdentity)（）和[Basic Matrix Operations](qmatrix.html#basic-matrix-operations)。

```
QMatrix QMatrix.rotate (self, float a)
```

[

旋转坐标系中给出_degrees_逆时针。

](qmatrix.html)

[请注意，如果你申请一个](qmatrix.html)[QMatrix](qmatrix.html)在小窗口坐标定义的一个点，该旋转方向将因为y轴指向下是顺时针。

返回一个引用到矩阵。

**See also** [setMatrix](qmatrix.html#setMatrix)（ ） 。

```
QMatrix QMatrix.scale (self, float sx, float sy)
```

[

通过缩放坐标系_sx_水平和_sy_垂直，并返回一个引用到矩阵。

](qmatrix.html)

[**See also**](qmatrix.html) [setMatrix](qmatrix.html#setMatrix)（ ） 。

```
QMatrix.setMatrix (self, float m11, float m12, float m21, float m22, float dx, float dy)
```

设置矩阵的元素为指定的值，_m11_，_m12_，_m21_，_m22_，_dx_和_dy_。

请注意，此功能取代了以前的值。[QMatrix](qmatrix.html)提供[translate](qmatrix.html#translate)（ ）[rotate](qmatrix.html#rotate)（ ）[scale](qmatrix.html#scale)（）和[shear](qmatrix.html#shear)（ ）方便的功能来操作基于当前定义的坐标系统中的各种矩阵元素。

**See also** [QMatrix](qmatrix.html#QMatrix)（ ） 。

```
QMatrix QMatrix.shear (self, float sh, float sv)
```

[

通过剪坐标系_sh_水平和_sv_垂直，并返回一个引用到矩阵。

](qmatrix.html)

[**See also**](qmatrix.html) [setMatrix](qmatrix.html#setMatrix)（ ） 。

```
QMatrix QMatrix.translate (self, float dx, float dy)
```

[

移动的坐标系统_dx_沿x轴和_dy_沿着y轴，并返回引用到矩阵。

](qmatrix.html)

[**See also**](qmatrix.html) [setMatrix](qmatrix.html#setMatrix)（ ） 。

```
bool QMatrix.__eq__ (self, QMatrix)
```

```
QMatrix QMatrix.__imul__ (self, QMatrix)
```

[](qmatrix.html)

```
QMatrix QMatrix.__mul__ (self, QMatrix o)
```

[

```
bool QMatrix.__ne__ (self, QMatrix)
```

](qmatrix.html)