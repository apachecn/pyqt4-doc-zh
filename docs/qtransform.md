# QTransform Class Reference

## [[QtGui](index.htm) module]

该QTransform类指定坐标系的2D变换。[More...](#details)

### Types

*   `enum TransformationType { TxNone, TxTranslate, TxScale, TxRotate, TxShear, TxProject }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, float m11, float m12, float m13, float m21, float m22, float m23, float m31, float m32, float m33 = 1)`
*   `__init__ (self, float h11, float h12, float h13, float h21, float h22, float h23)`
*   `__init__ (self, QMatrix mtx)`
*   `__init__ (self, QTransform)`
*   `QTransform adjoint (self)`
*   `float det (self)`
*   `float determinant (self)`
*   `float dx (self)`
*   `float dy (self)`
*   `(QTransform, bool invertible) inverted (self)`
*   `bool isAffine (self)`
*   `bool isIdentity (self)`
*   `bool isInvertible (self)`
*   `bool isRotating (self)`
*   `bool isScaling (self)`
*   `bool isTranslating (self)`
*   `float m11 (self)`
*   `float m12 (self)`
*   `float m13 (self)`
*   `float m21 (self)`
*   `float m22 (self)`
*   `float m23 (self)`
*   `float m31 (self)`
*   `float m32 (self)`
*   `float m33 (self)`
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
*   `QTransform rotate (self, float angle, Qt.Axis axis = Qt.ZAxis)`
*   `QTransform rotateRadians (self, float angle, Qt.Axis axis = Qt.ZAxis)`
*   `QTransform scale (self, float sx, float sy)`
*   `setMatrix (self, float m11, float m12, float m13, float m21, float m22, float m23, float m31, float m32, float m33)`
*   `QTransform shear (self, float sh, float sv)`
*   `QMatrix toAffine (self)`
*   `QTransform translate (self, float dx, float dy)`
*   `QTransform transposed (self)`
*   `TransformationType type (self)`

### Static Methods

*   `QTransform fromScale (float dx, float dy)`
*   `QTransform fromTranslate (float dx, float dy)`
*   `bool quadToQuad (QPolygonF one, QPolygonF two, QTransform result)`
*   `bool quadToSquare (QPolygonF quad, QTransform result)`
*   `bool squareToQuad (QPolygonF square, QTransform result)`

### Special Methods

*   `QTransform __add__ (self, float n)`
*   `QTransform __div__ (self, float n)`
*   `bool __eq__ (self, QTransform)`
*   `QTransform __iadd__ (self, float num)`
*   `QTransform __idiv__ (self, float div)`
*   `QTransform __imul__ (self, QTransform)`
*   `QTransform __imul__ (self, float num)`
*   `QTransform __isub__ (self, float num)`
*   `QTransform __mul__ (self, QTransform o)`
*   `QTransform __mul__ (self, float n)`
*   `bool __ne__ (self, QTransform)`
*   `QTransform __sub__ (self, float n)`

* * *

## Detailed Description

这个类可以醃制。

该QTransform类指定坐标系的2D变换。

一个转换指定如何翻译，缩放，剪切，旋转或投影坐标系，并绘制图形时，通常会使用。

QTransform不同于[QMatrix(obsolete)](qmatrix.html)中，这是一个真正的3×3矩阵，使透视变换。 QTransform的[toAffine](qtransform.html#toAffine)（ ）方法允许铸造QTransform到[QMatrix(obsolete)](qmatrix.html)。如果一个透视变换已被指定的矩阵，则转换将导致数据丢失。

QTransform是Qt推荐的转换类。

一个QTransform对象可使用内置的[setMatrix](qtransform.html#setMatrix)（ ）[scale](qtransform.html#scale)（ ）[rotate](qtransform.html#rotate)（ ）[translate](qtransform.html#translate)（）和[shear](qtransform.html#shear)（）函数。另外，它可以通过施加建[basic matrix operations](#basic-matrix-operations)。该矩阵也可以被定义时构造，并且它可以使用被重置为单位矩阵（默认值）的[reset](qtransform.html#reset)（）函数。

该QTransform类支持的图形原语映射：一个给定的点，线，多边形，区域或画家路径可以映射到由坐标系定义_this_使用矩阵[map](qtransform.html#map)（）函数。在情况下的四边形的，它的坐标可以用转化的[mapRect](qtransform.html#mapRect)（）函数。矩形也可以被改造成一个_polygon_（映射到定义的坐标系_this_矩阵），使用[mapToPolygon](qtransform.html#mapToPolygon)（）函数。

QTransform提供[isIdentity](qtransform.html#isIdentity)（）函数，如果矩阵是单位矩阵，并且该方法返回True，则[isInvertible](qtransform.html#isInvertible)（ ）函数如果矩阵是非奇异的（即AB = BA = I ），它返回True 。该[inverted](qtransform.html#inverted)（ ）函数返回一个倒置的副本_this_矩阵，如果它是可逆的（否则返回单位矩阵） ，以及[adjoint](qtransform.html#adjoint)（ ）返回矩阵的标准伴随。此外， QTransform提供[determinant](qtransform.html#determinant)（ ）函数返回矩阵的行列式。

最后， QTransform类支持矩阵乘法，加法和减法，以及类的对象可以被串流播放，以及比较。

### Rendering Graphics

在绘制图形时，矩阵定义转换，但实际转换是由绘图函数中执行[QPainter](qpainter.html)。

默认情况下，[QPainter](qpainter.html)操作相关联的设备自己的坐标系上。标准坐标系统[QPaintDevice](qpaintdevice.html)有其原点位于左上角的位置。该_x_值向右增大;_y_值向下增大。有关完整说明，请参阅[coordinate system](index.htm)文档。

[QPainter](qpainter.html)有功能，平移，缩放，剪切和旋转坐标系统，而无需使用QTransform 。例如：

| ![](../img/qtransform-simpletransformation.png) | 

```
 void SimpleTransformation.paintEvent([QPaintEvent](qpaintevent.html) *)
 {
     [QPainter](qpainter.html) painter(this);
     painter.setPen([QPen](qpen.html)([Qt](qt.html).blue, 1, [Qt](qt.html).DashLine));
     painter.drawRect(0, 0, 100, 100);

     painter.rotate(45);

     painter.setFont([QFont](qfont.html)("Helvetica", 24));
     painter.setPen([QPen](qpen.html)([Qt](qt.html).black, 1));
     painter.drawText(20, 10, "QTransform");
 }

```

 |

虽然这些功能都非常的方便，它可以更有效地建立一个QTransform和呼叫[QPainter.setTransform](qpainter.html#setTransform)（ ）如果你想执行一个以上的变换操作。例如：

| ![](../img/qtransform-combinedtransformation.png) | 

```
 void CombinedTransformation.paintEvent([QPaintEvent](qpaintevent.html) *)
 {
     [QPainter](qpainter.html) painter(this);
     painter.setPen([QPen](qpen.html)([Qt](qt.html).blue, 1, [Qt](qt.html).DashLine));
     painter.drawRect(0, 0, 100, 100);

     QTransform transform;
     transform.translate(50, 50);
     transform.rotate(45);
     transform.scale(0.5, 1.0);
     painter.setTransform(transform);

     painter.setFont([QFont](qfont.html)("Helvetica", 24));
     painter.setPen([QPen](qpen.html)([Qt](qt.html).black, 1));
     painter.drawText(20, 10, "QTransform");
 }

```

 |

### Basic Matrix Operations

![](../img/qtransform-representation.png)

一个QTransform对象包含一个3× 3的矩阵。该`m31`（`dx`）和`m32`（`dy`）元素指定水平和垂直平移。该`m11`和`m22`元素指定水平和垂直缩放。该`m21`和`m12`元素指定水平和垂直_shearing_。最后，本`m13`和`m23`元素指定水平和垂直投影，与`m33`作为一个额外的投影系数。

使用下列公式QTransform转换成在平面上的点到另一点：

```
 x' = m11*x + m21*y + dx
 y' = m22*y + m12*x + dy
 if (is not affine) {
     w' = m13*x + m23*y + m33
     x' /= w'
     y' /= w'
 }

```

The point _(x, y)_ is the original point, and _(x', y')_ is the transformed point. _(x', y')_ can be transformed back to _(x, y)_ by performing the same operation on the [inverted](qtransform.html#inverted)() matrix.

The various matrix elements can be set when constructing the matrix, or by using the [setMatrix](qtransform.html#setMatrix)() function later on. They can also be manipulated using the [translate](qtransform.html#translate)(), [rotate](qtransform.html#rotate)(), [scale](qtransform.html#scale)() and [shear](qtransform.html#shear)() convenience functions. The currently set values can be retrieved using the [m11](qtransform.html#m11)(), [m12](qtransform.html#m12)(), [m13](qtransform.html#m13)(), [m21](qtransform.html#m21)(), [m22](qtransform.html#m22)(), [m23](qtransform.html#m23)(), [m31](qtransform.html#m31)(), [m32](qtransform.html#m32)(), [m33](qtransform.html#m33)(), [dx](qtransform.html#dx)() and [dy](qtransform.html#dy)() functions.

Translation is the simplest transformation. Setting `dx` and `dy` will move the coordinate system `dx` units along the X axis and `dy` units along the Y axis. Scaling can be done by setting `m11` and `m22`. For example, setting `m11` to 2 and `m22` to 1.5 will double the height and increase the width by 50%. The identity matrix has `m11`, `m22`, and `m33` set to 1 (all others are set to 0) mapping a point to itself. Shearing is controlled by `m12` and `m21`. Setting these elements to values different from zero will twist the coordinate system. Rotation is achieved by setting both the shearing factors and the scaling factors. Perspective transformation is achieved by setting both the projection factors and the scaling factors.

Here's the combined transformations example using basic matrix operations:

| ![](../img/qtransform-combinedtransformation2.png) | 

```
 void BasicOperations.paintEvent([QPaintEvent](qpaintevent.html) *)
 {
     double pi = 3.14;

     double a    = pi/180 * 45.0;
     double sina = sin(a);
     double cosa = cos(a);

     QTransform translationTransform(1, 0, 0, 1, 50.0, 50.0);
     QTransform rotationTransform(cosa, sina, -sina, cosa, 0, 0);
     QTransform scalingTransform(0.5, 0, 0, 1.0, 0, 0);

     QTransform transform;
     transform = scalingTransform * rotationTransform * translationTransform;

     [QPainter](qpainter.html) painter(this);
     painter.setPen([QPen](qpen.html)([Qt](qt.html).blue, 1, [Qt](qt.html).DashLine));
     painter.drawRect(0, 0, 100, 100);

     painter.setTransform(transform);

     painter.setFont([QFont](qfont.html)("Helvetica", 24));
     painter.setPen([QPen](qpen.html)([Qt](qt.html).black, 1));
     painter.drawText(20, 10, "QTransform");
 }

```

 |

* * *

## Type Documentation

```
QTransform.TransformationType
```

| Constant | Value |
| --- | --- |
| `QTransform.TxNone` | `0x00` |
| `QTransform.TxTranslate` | `0x01` |
| `QTransform.TxScale` | `0x02` |
| `QTransform.TxRotate` | `0x04` |
| `QTransform.TxShear` | `0x08` |
| `QTransform.TxProject` | `0x10` |

* * *

## Method Documentation

```
QTransform.__init__ (self)
```

构造一个单位矩阵。

所有的元素都设置为零，除了`m11`和`m22`（指定刻度）和`m13`它被设置为1 。

**See also** [reset](qtransform.html#reset)（ ） 。

```
QTransform.__init__ (self, float m11, float m12, float m13, float m21, float m22, float m23, float m31, float m32, float m33 = 1)
```

```
QTransform.__init__ (self, float h11, float h12, float h13, float h21, float h22, float h23)
```

构造一个矩阵的元素，_m11_，_m12_，_m13_，_m21_，_m22_，_m23_，_m31_，_m32_，_m33_。

**See also** [setMatrix](qtransform.html#setMatrix)（ ） 。

```
QTransform.__init__ (self, QMatrix mtx)
```

构造一个矩阵的元素，_m11_，_m12_，_m21_，_m22_，_dx_和_dy_。

**See also** [setMatrix](qtransform.html#setMatrix)（ ） 。

```
QTransform.__init__ (self, QTransform)
```

构造一个矩阵，是给定一个副本_matrix_。注意，这个`m13`，`m23`和`m33`元件分别设置为0,0和1。

```
QTransform QTransform.adjoint (self)
```

[

返回该矩阵的伴随。

```
float QTransform.det (self)
```

```
float QTransform.determinant (self)
```

返回矩阵的行列式。

```
float QTransform.dx (self)
```

返回水平平移因子。

](qtransform.html)

[**See also**](qtransform.html) [m31](qtransform.html#m31)（ ）[translate](qtransform.html#translate)（）和[Basic Matrix Operations](qtransform.html#basic-matrix-operations)。

```
float QTransform.dy (self)
```

返回垂直平移因子。

**See also** [translate](qtransform.html#translate)（）和[Basic Matrix Operations](qtransform.html#basic-matrix-operations)。

```
QTransform QTransform.fromScale (float dx, float dy)
```

[](qtransform.html)

[创建其对应于缩放的矩阵_sx_水平和_sy_垂直。这是相同的](qtransform.html)[QTransform](qtransform.html#QTransform)（ ） 。规模（ SX ， SY ），但稍快。

此功能被引入Qt的4.5 。

```
QTransform QTransform.fromTranslate (float dx, float dy)
```

[](qtransform.html)

[创建其对应于翻译成矩阵_dx_沿x轴和_dy_沿y轴。这是相同的](qtransform.html)[QTransform](qtransform.html#QTransform)（ ） ，翻译（ DX，DY ），但稍快。

此功能被引入Qt的4.5 。

```
(QTransform, bool invertible) QTransform.inverted (self)
```

返回该矩阵的一个倒置的副本。

如果矩阵是奇异的（不可逆的） ，则返回的矩阵是单位矩阵。如果_invertible_是有效的（即不为0 ） ，将其值设置为True，如果矩阵是可逆的，否则设置为False 。

**See also** [isInvertible](qtransform.html#isInvertible)（ ） 。

```
bool QTransform.isAffine (self)
```

返回True如果矩阵表示仿射变换，否则返回False 。

```
bool QTransform.isIdentity (self)
```

返回True如果矩阵为单位矩阵，否则返回False 。

**See also** [reset](qtransform.html#reset)（ ） 。

```
bool QTransform.isInvertible (self)
```

返回True如果矩阵是可逆的，否则返回False 。

**See also** [inverted](qtransform.html#inverted)（ ） 。

```
bool QTransform.isRotating (self)
```

返回True如果矩阵代表某种旋转变换，否则返回False 。

**See also** [reset](qtransform.html#reset)（ ） 。

```
bool QTransform.isScaling (self)
```

返回True如果矩阵表示缩放转换，否则返回False 。

**See also** [reset](qtransform.html#reset)（ ） 。

```
bool QTransform.isTranslating (self)
```

返回True如果矩阵表示平移变换，否则返回False 。

**See also** [reset](qtransform.html#reset)（ ） 。

```
float QTransform.m11 (self)
```

返回水平缩放系数。

**See also** [scale](qtransform.html#scale)（）和[Basic Matrix Operations](qtransform.html#basic-matrix-operations)。

```
float QTransform.m12 (self)
```

返回垂直剪切因素。

**See also** [shear](qtransform.html#shear)（）和[Basic Matrix Operations](qtransform.html#basic-matrix-operations)。

```
float QTransform.m13 (self)
```

返回水平投影的因素。

**See also** [translate](qtransform.html#translate)（）和[Basic Matrix Operations](qtransform.html#basic-matrix-operations)。

```
float QTransform.m21 (self)
```

返回水平剪切的因素。

**See also** [shear](qtransform.html#shear)（）和[Basic Matrix Operations](qtransform.html#basic-matrix-operations)。

```
float QTransform.m22 (self)
```

返回垂直缩放系数。

**See also** [scale](qtransform.html#scale)（）和[Basic Matrix Operations](qtransform.html#basic-matrix-operations)。

```
float QTransform.m23 (self)
```

返回垂直投影的因素。

**See also** [translate](qtransform.html#translate)（）和[Basic Matrix Operations](qtransform.html#basic-matrix-operations)。

```
float QTransform.m31 (self)
```

返回水平平移因子。

**See also** [dx](qtransform.html#dx)（ ）[translate](qtransform.html#translate)（）和[Basic Matrix Operations](qtransform.html#basic-matrix-operations)。

```
float QTransform.m32 (self)
```

返回垂直平移因子。

**See also** [dy](qtransform.html#dy)（ ）[translate](qtransform.html#translate)（）和[Basic Matrix Operations](qtransform.html#basic-matrix-operations)。

```
float QTransform.m33 (self)
```

返回的分频因子。

**See also** [translate](qtransform.html#translate)（）和[Basic Matrix Operations](qtransform.html#basic-matrix-operations)。

```
(int tx, int ty) QTransform.map (self, int x, int y)
```

对应给定的坐标_x_和_y_成由该矩阵定义的坐标系。被放置在所得到的值*_tx_和*_ty_元。

则坐标值用下面的公式转化：

```
 x' = m11*x + m21*y + dx
 y' = m22*y + m12*x + dy
 if (is not affine) {
     w' = m13*x + m23*y + m33
     x' /= w'
     y' /= w'
 }

```

点（x ，y）是原始的点，和（ X'，Y '）是变换后的​​点。

**See also** [Basic Matrix Operations](qtransform.html#basic-matrix-operations)。

```
(float tx, float ty) QTransform.map (self, float x, float y)
```

这是一个重载函数。

创建并返回一个[QPointF](qpointf.html)对象，它是给定的点的副本，_p_，映射到由该矩阵定义的坐标系。

```
QPoint QTransform.map (self, QPoint p)
```

[

这是一个重载函数。

](qpoint.html)

[创建并返回一个](qpoint.html)[QPoint](qpoint.html)对象，它是给定一个副本_point_，映射到由该矩阵定义的坐标系。需要注意的是转换后的坐标四舍五入到最接近的整数。

```
QPointF QTransform.map (self, QPointF p)
```

[

这是一个重载函数。

](qpointf.html)

[创建并返回一个](qpointf.html)[QLineF](qlinef.html)对象，它是给定行的一个副本，_l_，映射到由该矩阵定义的坐标系。

```
QLine QTransform.map (self, QLine l)
```

[

这是一个重载函数。

](qline.html)

[创建并返回一个](qline.html)[QLine](qline.html)对象，它是给定一个副本_line_，映射到由该矩阵定义的坐标系。需要注意的是转换后的坐标四舍五入到最接近的整数。

```
QLineF QTransform.map (self, QLineF l)
```

[

这是一个重载函数。

](qlinef.html)

[创建并返回一个](qlinef.html)[QPolygonF](qpolygonf.html)对象，它是给定一个副本_polygon_，映射到由该矩阵定义的坐标系。

```
QPolygonF QTransform.map (self, QPolygonF a)
```

[

这是一个重载函数。

](qpolygonf.html)

[创建并返回一个](qpolygonf.html)[QPolygon](qpolygon.html)对象，它是给定一个副本_polygon_，映射到由该矩阵定义的坐标系。需要注意的是转换后的坐标四舍五入到最接近的整数。

```
QPolygon QTransform.map (self, QPolygon a)
```

[

这是一个重载函数。

](qpolygon.html)

[创建并返回一个](qpolygon.html)[QRegion](qregion.html)对象，它是给定一个副本_region_，映射到由该矩阵定义的坐标系。

调用此方法可以是相当昂贵的，如果旋转或剪切的使用。

```
QRegion QTransform.map (self, QRegion r)
```

[

这是一个重载函数。

](qregion.html)

[创建并返回一个](qregion.html)[QPainterPath](qpainterpath.html)对象，它是给定一个副本_path_，映射到由该矩阵定义的坐标系。

```
QPainterPath QTransform.map (self, QPainterPath p)
```

[

这是一个重载函数。

对应给定的坐标_x_和_y_成由该矩阵定义的坐标系。被放置在所得到的值*_tx_和*_ty_元。需要注意的是转换后的坐标四舍五入到最接近的整数。

](qpainterpath.html)

```
QRect QTransform.mapRect (self, QRect)
```

[](qrect.html)

[创建并返回一个](qrect.html)[QRectF](qrectf.html)对象，它是给定一个副本_rectangle_，映射到由该矩阵定义的坐标系。

矩形的坐标是用下面的公式转化：

```
 x' = m11*x + m21*y + dx
 y' = m22*y + m12*x + dy
 if (is not affine) {
     w' = m13*x + m23*y + m33
     x' /= w'
     y' /= w'
 }

```

If rotation or shearing has been specified, this function returns the _bounding_ rectangle. To retrieve the exact region the given _rectangle_ maps to, use the [mapToPolygon](qtransform.html#mapToPolygon)() function instead.

**See also** [mapToPolygon](qtransform.html#mapToPolygon)() and [Basic Matrix Operations](qtransform.html#basic-matrix-operations).

```
QRectF QTransform.mapRect (self, QRectF)
```

[](qrectf.html)

```
QPolygon QTransform.mapToPolygon (self, QRect r)
```

[](qpolygon.html)

[创建并返回一个](qpolygon.html)[QPolygon](qpolygon.html)给定的表示_rectangle_，映射到由该矩阵定义的坐标系。

矩形的坐标是用下面的公式转化：

```
 x' = m11*x + m21*y + dx
 y' = m22*y + m12*x + dy
 if (is not affine) {
     w' = m13*x + m23*y + m33
     x' /= w'
     y' /= w'
 }

```

多边形和矩形的行为略有不同，当转换（由于四舍五入的整数） ，所以`matrix.map(QPolygon(rectangle))`并不总是相同`matrix.mapToPolygon(rectangle)`。

**See also** [mapRect](qtransform.html#mapRect)（）和[Basic Matrix Operations](qtransform.html#basic-matrix-operations)。

```
bool QTransform.quadToQuad (QPolygonF one, QPolygonF two, QTransform result)
```

创建一个变换矩阵，_trans_，映射一个四边形，_one_到另一个四边多边形，_two_。返回True如果转换是可能的;否则返回False。

这是一个方便的方法相结合[quadToSquare](qtransform.html#quadToSquare)（）和[squareToQuad](qtransform.html#squareToQuad)（）方法。它允许输入四要转变成任何其他四。

**See also** [squareToQuad](qtransform.html#squareToQuad)（）和[quadToSquare](qtransform.html#quadToSquare)（ ） 。

```
bool QTransform.quadToSquare (QPolygonF quad, QTransform result)
```

创建一个变换矩阵，_trans_，映射一个四边形，_quad_，到单位正方形。返回True如果变换构造还是假，如果这样的转变并不存在。

**See also** [squareToQuad](qtransform.html#squareToQuad)（）和[quadToQuad](qtransform.html#quadToQuad)（ ） 。

```
QTransform.reset (self)
```

重置矩阵单位矩阵，即所有元素都设置为零，除非`m11`和`m22`（指定刻度）和`m33`它被设置为1 。

**See also** [QTransform](qtransform.html#QTransform)（ ）[isIdentity](qtransform.html#isIdentity)（）和[Basic Matrix Operations](qtransform.html#basic-matrix-operations)。

```
QTransform QTransform.rotate (self, float angle, Qt.Axis axis = Qt.ZAxis)
```

[

由给定的逆时针旋转的坐标系_angle_关于指定_axis_并返回一个引用到矩阵。

](qtransform.html)

[请注意，如果你申请一个](qtransform.html)[QTransform](qtransform.html)在小窗口坐标定义的一个点，该旋转方向将因为y轴指向下是顺时针。

的角度被指定为度。

**See also** [setMatrix](qtransform.html#setMatrix)（ ） 。

```
QTransform QTransform.rotateRadians (self, float angle, Qt.Axis axis = Qt.ZAxis)
```

[

由给定的逆时针旋转的坐标系_angle_关于指定_axis_并返回一个引用到矩阵。

](qtransform.html)

[请注意，如果你申请一个](qtransform.html)[QTransform](qtransform.html)在小窗口坐标定义的一个点，该旋转方向将因为y轴指向下是顺时针。

的角度被指定为弧度。

**See also** [setMatrix](qtransform.html#setMatrix)（ ） 。

```
QTransform QTransform.scale (self, float sx, float sy)
```

[

通过缩放坐标系_sx_水平和_sy_垂直，并返回一个引用到矩阵。

](qtransform.html)

[**See also**](qtransform.html) [setMatrix](qtransform.html#setMatrix)（ ） 。

```
QTransform.setMatrix (self, float m11, float m12, float m13, float m21, float m22, float m23, float m31, float m32, float m33)
```

设置矩阵的元素为指定的值，_m11_，_m12_，_m13_ _m21_，_m22_，_m23_ _m31_，_m32_和_m33_。请注意，此功能取代了以前的值。[QTransform](qtransform.html)提供[translate](qtransform.html#translate)（ ）[rotate](qtransform.html#rotate)（ ）[scale](qtransform.html#scale)（）和[shear](qtransform.html#shear)（ ）方便的功能来操作基于当前定义的坐标系统中的各种矩阵元素。

**See also** [QTransform](qtransform.html#QTransform)（ ） 。

```
QTransform QTransform.shear (self, float sh, float sv)
```

[

通过剪坐标系_sh_水平和_sv_垂直，并返回一个引用到矩阵。

](qtransform.html)

[**See also**](qtransform.html) [setMatrix](qtransform.html#setMatrix)（ ） 。

```
bool QTransform.squareToQuad (QPolygonF square, QTransform result)
```

创建一个变换矩阵，_trans_，映射一个单位正方形四边多边形，_quad_。返回True如果变换构造还是假，如果这样的转变并不存在。

**See also** [quadToSquare](qtransform.html#quadToSquare)（）和[quadToQuad](qtransform.html#quadToQuad)（ ） 。

```
QMatrix QTransform.toAffine (self)
```

[](qmatrix.html)

[返回](qmatrix.html)[QTransform](qtransform.html)作为仿射矩阵。

**Warning:**如果已指定一个透视变换，那么转换将导致数据丢失。

```
QTransform QTransform.translate (self, float dx, float dy)
```

[

移动的坐标系统_dx_沿x轴和_dy_沿着y轴，并返回引用到矩阵。

](qtransform.html)

[**See also**](qtransform.html) [setMatrix](qtransform.html#setMatrix)（ ） 。

```
QTransform QTransform.transposed (self)
```

[

返回该矩阵的转置。

](qtransform.html)

```
TransformationType QTransform.type (self)
```

[

返回这个矩阵的转换类型。

改造型是最高的枚举值捕获所有矩阵的变换。例如，如果两个矩阵规模和剪刀，类型是`TxShear`，因为`TxShear`具有比更高的枚举值`TxScale`。

了解矩阵的变换类型是优化有用：你经常可以更优化处理特定类型的处理比一般情况下。

](qtransform.html#TransformationType-enum)

```
QTransform QTransform.__add__ (self, float n)
```

[](qtransform.html)

```
QTransform QTransform.__div__ (self, float n)
```

[

```
bool QTransform.__eq__ (self, QTransform)
```

](qtransform.html)

```
QTransform QTransform.__iadd__ (self, float num)
```

[](qtransform.html)

```
QTransform QTransform.__idiv__ (self, float div)
```

[](qtransform.html)

```
QTransform QTransform.__imul__ (self, QTransform)
```

[](qtransform.html)

```
QTransform QTransform.__imul__ (self, float num)
```

[](qtransform.html)

```
QTransform QTransform.__isub__ (self, float num)
```

[](qtransform.html)

```
QTransform QTransform.__mul__ (self, QTransform o)
```

[](qtransform.html)

```
QTransform QTransform.__mul__ (self, float n)
```

[

```
bool QTransform.__ne__ (self, QTransform)
```

](qtransform.html)

```
QTransform QTransform.__sub__ (self, float n)
```

[](qtransform.html)