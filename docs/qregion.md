# QRegion Class Reference

## [[QtGui](index.htm) module]

该QRegion类指定一个画家的剪辑区域。[More...](#details)

### Types

*   `enum RegionType { Rectangle, Ellipse }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, int x, int y, int w, int h, RegionType type = QRegion.Rectangle)`
*   `__init__ (self, QRect r, RegionType type = QRegion.Rectangle)`
*   `__init__ (self, QPolygon a, Qt.FillRule fillRule = Qt.OddEvenFill)`
*   `__init__ (self, QBitmap bitmap)`
*   `__init__ (self, QRegion region)`
*   `__init__ (self, QVariant variant)`
*   `QRect boundingRect (self)`
*   `bool contains (self, QPoint p)`
*   `bool contains (self, QRect r)`
*   `QRegion eor (self, QRegion r)`
*   `QRegion intersect (self, QRegion r)`
*   `QRegion intersected (self, QRegion r)`
*   `QRegion intersected (self, QRect r)`
*   `bool intersects (self, QRegion r)`
*   `bool intersects (self, QRect r)`
*   `bool isEmpty (self)`
*   `int numRects (self)`
*   `int rectCount (self)`
*   `list-of-QRect rects (self)`
*   `QRegion subtract (self, QRegion r)`
*   `QRegion subtracted (self, QRegion r)`
*   `swap (self, QRegion other)`
*   `translate (self, int dx, int dy)`
*   `translate (self, QPoint p)`
*   `QRegion translated (self, int dx, int dy)`
*   `QRegion translated (self, QPoint p)`
*   `QRegion unite (self, QRegion r)`
*   `QRegion united (self, QRegion r)`
*   `QRegion united (self, QRect r)`
*   `QRegion xored (self, QRegion r)`

### Special Methods

*   `QRegion __add__ (self, QRegion r)`
*   `QRegion __add__ (self, QRect r)`
*   `QRegion __and__ (self, QRegion r)`
*   `QRegion __and__ (self, QRect r)`
*   `int __bool__ (self)`
*   `int __contains__ (self, QPoint p)`
*   `int __contains__ (self, QRect r)`
*   `bool __eq__ (self, QRegion r)`
*   `QRegion __iadd__ (self, QRegion r)`
*   `QRegion __iadd__ (self, QRect r)`
*   `QRegion __iand__ (self, QRegion r)`
*   `QRegion __iand__ (self, QRect r)`
*   `QRegion __ior__ (self, QRegion r)`
*   `QRegion __isub__ (self, QRegion r)`
*   `QRegion __ixor__ (self, QRegion r)`
*   `QRegion __mul__ (self, QMatrix m)`
*   `QRegion __mul__ (self, QTransform m)`
*   `bool __ne__ (self, QRegion r)`
*   `QRegion __or__ (self, QRegion r)`
*   `QRegion __sub__ (self, QRegion r)`
*   `QRegion __xor__ (self, QRegion r)`

* * *

## Detailed Description

该QRegion类指定一个画家的剪辑区域。

QRegion一起使用[QPainter.setClipRegion](qpainter.html#setClipRegion)（ ），以限制油漆区，以什么需要上漆。还有一个[QWidget.repaint](qwidget.html#repaint)（ ）函数，它接受一个QRegion参数。 QRegion对于减少屏幕区域由一个重绘更新量的最佳工具。

这个类是不适合于构建形状呈现，尤其是作为轮廓。使用[QPainterPath](qpainterpath.html)创建路径和形状与使用[QPainter](qpainter.html)。

QRegion是[implicitly shared](index.htm#implicitly-shared)类。

### Creating and Using Regions

一个区域可以由一个矩形，椭圆形，多边形或一个位图被创建。复杂区域可以通过结合简单的使用区域来创建[united](qregion.html#united)（ ）[intersected](qregion.html#intersected)（ ）[subtracted](qregion.html#subtracted)（） ，或[xored](qregion.html#xored)（） （异或） 。您可以使用移动区域[translate](qregion.html#translate)（ ） 。

您可以测试是否一个区域[isEmpty](qregion.html#isEmpty)（） ，或者如果它[contains](qregion.html#contains)（ ）一[QPoint](qpoint.html) or [QRect](qrect.html)。该边框可以找到[boundingRect](qregion.html#boundingRect)（ ） 。

该功能[rects](qregion.html#rects)（）给出的区域的分解成矩形。

使用复杂的区域的例子：

```
 void MyWidget.paintEvent([QPaintEvent](qpaintevent.html) *)
 {
     QRegion r1([QRect](qrect.html)(100, 100, 200, 80),    // r1: elliptic region
                QRegion.Ellipse);
     QRegion r2([QRect](qrect.html)(100, 120, 90, 30));    // r2: rectangular region
     QRegion r3 = r1.intersected(r2);        // r3: intersection

     [QPainter](qpainter.html) painter(this);
     painter.setClipRegion(r3);
     ...                                     // paint clipped graphics
 }

```

### Additional License Information

在嵌入式Linux ， Windows CE和X11平台上，这个类的部分依靠以以下授权协议获得的代码：

版权所有（c ）1987 X联盟

特此免费授予的，对任何获得本软件副本及相关文档文件（ “软件” ） ，以处理本软件不受任何限制，包括但不限于使用权，复制，修改，合并，发布，分发，再许可和/或销售软件副本，并允许他人为之软体家具是这样做的，须符合下列条件：

上述版权声明和本许可声明应包含在所有的副本或实质性部分的软件。

本软件按“原样”，没有任何形式的担保，明示或默示的担保，包括但不限于适销性，适用于特定用途和非侵权的保证。在任何情况下X联盟承担任何索赔，损害赔偿或其他责任，无论是合同行为，侵权行为或其他原因所产生的，运出或与本软件或使用，或软件中的其他交易。

除本通知所载， X联盟的名称不得用于广告或其他方式来促进销售，使用或本软件中的其他交易未经X联盟事先书面授权。

版权所有1987年由数字设备公司，梅纳德，马萨诸塞。

保留所有权利

许可使用，复制，修改和分发本软件及其文档的任何目的免费特此授予，前提是上述版权声明出现在所有副本中，并且两种版权声明和本许可声明出现在支持文档，并且在广告或宣传有关软件分发没有具体的不能用数字的名称，事先书面许可。

DIGITAL声明不提供本软件有关，包括对适销性和适用性的所有默示保证，在任何情况下数字都不对任何特殊，间接或后果性损害或任何损害因无法使用，数据丢失或利润，无论是在动作的合同，疏忽或其它侵权行为，所产生的或与本软件的使用或性能。

* * *

## Type Documentation

```
QRegion.RegionType
```

指定区域的要创建的形状。

| Constant | Value | Description |
| --- | --- | --- |
| `QRegion.Rectangle` | `0` | 该区域复盖了整个矩形。 |
| `QRegion.Ellipse` | `1` | 该区域是在矩形内的椭圆形。 |

* * *

## Method Documentation

```
QRegion.__init__ (self)
```

构造一个空区域。

**See also** [isEmpty](qregion.html#isEmpty)（ ） 。

```
QRegion.__init__ (self, int x, int y, int w, int h, RegionType type = QRegion.Rectangle)
```

构造一个矩形或椭圆形区域。

If _t_ is `Rectangle`的区域是填充矩形（_x_，_y_，_w_，_h_） 。如果_t_ is `Ellipse`，该地区是充满椭圆与中心（_x_+_w_/ 2，_y_+_h_/ 2）和尺寸（_w_，_h_） 。

```
QRegion.__init__ (self, QRect r, RegionType type = QRegion.Rectangle)
```

从点阵列构造一个多边形区域_a_由指定的填充规则_fillRule_。

If _fillRule_ is [Qt.WindingFill](qt.html#FillRule-enum)，多边形区域是使用捲绕算法中定义，如果是[Qt.OddEvenFill](qt.html#FillRule-enum)，奇偶填充算法被使用。

**Warning:**这个构造函数可以用来创建复杂的地区使用时，将减缓画。

```
QRegion.__init__ (self, QPolygon a, Qt.FillRule fillRule = Qt.OddEvenFill)
```

```
QRegion.__init__ (self, QBitmap bitmap)
```

构造一个新的区域，它等于区域_r_。

```
QRegion.__init__ (self, QRegion region)
```

从位图构造一个区域_bm_。

所得到的区域由以位图的像素的_bm_是[Qt.color1](qt.html#GlobalColor-enum)，好像每个像素是一个1×1的矩形。

这个构造函数可以创建复杂的地区使用时，将减缓画。请注意，绘图蒙面像素映射可以做到更快使用[QPixmap.setMask](qpixmap.html#setMask)（ ） 。

```
QRegion.__init__ (self, QVariant variant)
```

这是一个重载函数。

创建基于rectange区域_r_与区域类型_t_。

如果矩形是无效的空区域将被创建。

**See also** [QRegion.RegionType](qregion.html#RegionType-enum)。

```
QRect QRegion.boundingRect (self)
```

[](qrect.html)

[返回此区域的边界矩形。一个空的区域给出了一个矩形，它是](qrect.html)[QRect.isNull](qrect.html#isNull)（ ） 。

```
bool QRegion.contains (self, QPoint p)
```

如果该区域包含该点，则返回True_p_否则返回False 。

```
bool QRegion.contains (self, QRect r)
```

这是一个重载函数。

如果该区域的矩形重叠，则返回True_r_否则返回False 。

```
QRegion QRegion.eor (self, QRegion r)
```

[](qregion.html)

```
QRegion QRegion.intersect (self, QRegion r)
```

[](qregion.html)

```
QRegion QRegion.intersected (self, QRegion r)
```

[

返回作为此区域的交集和地区_r_。

![Region Intersection](../img/rintersect.png)

该图显示了两个椭圆区域的交界处。

这个函数中引入了Qt 4.2中。

](qregion.html)

[**See also**](qregion.html) [subtracted](qregion.html#subtracted)（ ）[united](qregion.html#united)（）和[xored](qregion.html#xored)（ ） 。

```
QRegion QRegion.intersected (self, QRect r)
```

[

返回作为此区域的交集和给定的区域_rect_。

此功能被引入Qt的4.4 。

](qregion.html)

[**See also**](qregion.html) [subtracted](qregion.html#subtracted)（ ）[united](qregion.html#united)（）和[xored](qregion.html#xored)（ ） 。

```
bool QRegion.intersects (self, QRegion r)
```

如果这个区域相交，则返回True_region_，否则返回False 。

这个函数中引入了Qt 4.2中。

```
bool QRegion.intersects (self, QRect r)
```

如果这个区域相交，则返回True_rect_，否则返回False 。

这个函数中引入了Qt 4.2中。

```
bool QRegion.isEmpty (self)
```

返回True如果该区域为空，否则返回False 。空白区是一个不包含任何点的区域中。

例如：

```
 [QRegion](qregion.html) r1(10, 10, 20, 20);
 r1.isEmpty();               // false

 [QRegion](qregion.html) r3;
 r3.isEmpty();               // true

 [QRegion](qregion.html) r2(40, 40, 20, 20);
 r3 = r1.intersected(r2);    // r3: intersection of r1 and r2
 r3.isEmpty();               // true

 r3 = r1.united(r2);         // r3: union of r1 and r2
 r3.isEmpty();               // false

```

```
int QRegion.numRects (self)
```

```
int QRegion.rectCount (self)
```

返回将在返回矩形数[rects](qregion.html#rects)（ ） 。

此功能被引入Qt的4.6 。

```
list-of-QRect QRegion.rects (self)
```

返回非重叠的矩形组成区域的数组。

所有矩形的并集等于原来的区域。

**See also** [setRects](qregion.html#setRects)（ ） 。

```
QRegion QRegion.subtract (self, QRegion r)
```

[](qregion.html)

```
QRegion QRegion.subtracted (self, QRegion r)
```

[

返回其是区域_r_减去这一地区。

![Region Subtraction](../img/rsubtract.png)

图中示出了结果，当在右侧的椭圆是从左侧的椭圆（减去`left - right`） 。

这个函数中引入了Qt 4.2中。

](qregion.html)

[**See also**](qregion.html) [intersected](qregion.html#intersected)（ ）[united](qregion.html#united)（）和[xored](qregion.html#xored)（ ） 。

```
QRegion.swap (self, QRegion other)
```

交换区_other_与这一地区。这个操作是非常快的，而且永远不会。

此功能被引入Qt的4.8 。

```
QRegion.translate (self, int dx, int dy)
```

平移（移动）的区域_dx_沿X轴和_dy_沿着Y轴。

```
QRegion.translate (self, QPoint p)
```

这是一个重载函数。

转译区_point__.x()_沿x轴和_point__.y()_沿着y轴，相对于当前位置。正值移动的区域向右和向下。

转换为给定的_point_。

```
QRegion QRegion.translated (self, int dx, int dy)
```

[

返回区域的一个副本被翻译_dx_沿x轴和_dy_沿着y轴，相对于当前位置。正值移动的区域向右和向下。

这个函数是Qt 4.1中引入。

](qregion.html)

[**See also**](qregion.html) [translate](qregion.html#translate)（ ） 。

```
QRegion QRegion.translated (self, QPoint p)
```

[

这是一个重载函数。

返回regtion的副本翻译_p__.x()_沿x轴和_p__.y()_沿着y轴，相对于当前位置。正值移动矩形向右和向下。

这个函数是Qt 4.1中引入。

](qregion.html)

[**See also**](qregion.html) [translate](qregion.html#translate)（ ） 。

```
QRegion QRegion.unite (self, QRegion r)
```

[](qregion.html)

```
QRegion QRegion.united (self, QRegion r)
```

[

返回作为此区域的和工会的区域_r_。

![Region Union](../img/runion.png)

该图显示了两个椭圆区域的联合。

这个函数中引入了Qt 4.2中。

](qregion.html)

[**See also**](qregion.html) [intersected](qregion.html#intersected)（ ）[subtracted](qregion.html#subtracted)（）和[xored](qregion.html#xored)（ ） 。

```
QRegion QRegion.united (self, QRect r)
```

[

返回作为此区域的和工会给定一个区域_rect_。

此功能被引入Qt的4.4 。

](qregion.html)

[**See also**](qregion.html) [intersected](qregion.html#intersected)（ ）[subtracted](qregion.html#subtracted)（）和[xored](qregion.html#xored)（ ） 。

```
QRegion QRegion.xored (self, QRegion r)
```

[

返回作为此区域的异或（ XOR）和一个区_r_。

![Region XORed](../img/rxor.png)

该图显示了专用的两个椭圆区域或。

这个函数中引入了Qt 4.2中。

](qregion.html)

[**See also**](qregion.html) [intersected](qregion.html#intersected)（ ）[united](qregion.html#united)（）和[subtracted](qregion.html#subtracted)（ ） 。

```
QRegion QRegion.__add__ (self, QRegion r)
```

[](qregion.html)

```
QRegion QRegion.__add__ (self, QRect r)
```

[](qregion.html)

```
QRegion QRegion.__and__ (self, QRegion r)
```

[](qregion.html)

```
QRegion QRegion.__and__ (self, QRect r)
```

[

```
int QRegion.__bool__ (self)
```

```
int QRegion.__contains__ (self, QPoint p)
```

```
int QRegion.__contains__ (self, QRect r)
```

```
bool QRegion.__eq__ (self, QRegion r)
```

](qregion.html)

```
QRegion QRegion.__iadd__ (self, QRegion r)
```

[](qregion.html)

```
QRegion QRegion.__iadd__ (self, QRect r)
```

[](qregion.html)

```
QRegion QRegion.__iand__ (self, QRegion r)
```

[](qregion.html)

```
QRegion QRegion.__iand__ (self, QRect r)
```

[](qregion.html)

```
QRegion QRegion.__ior__ (self, QRegion r)
```

[](qregion.html)

```
QRegion QRegion.__isub__ (self, QRegion r)
```

[](qregion.html)

```
QRegion QRegion.__ixor__ (self, QRegion r)
```

[](qregion.html)

```
QRegion QRegion.__mul__ (self, QMatrix m)
```

[](qregion.html)

```
QRegion QRegion.__mul__ (self, QTransform m)
```

[

```
bool QRegion.__ne__ (self, QRegion r)
```

](qregion.html)

```
QRegion QRegion.__or__ (self, QRegion r)
```

[](qregion.html)

```
QRegion QRegion.__sub__ (self, QRegion r)
```

[](qregion.html)

```
QRegion QRegion.__xor__ (self, QRegion r)
```

[](qregion.html)