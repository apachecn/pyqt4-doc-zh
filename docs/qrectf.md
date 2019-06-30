# QRectF Class Reference

## [[QtCore](index.htm) module]

该QRectF类定义使用浮点精度在平面的矩形。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QPointF atopLeft, QSizeF asize)`
*   `__init__ (self, QPointF atopLeft, QPointF abottomRight)`
*   `__init__ (self, float aleft, float atop, float awidth, float aheight)`
*   `__init__ (self, QRect r)`
*   `__init__ (self, QRectF)`
*   `adjust (self, float xp1, float yp1, float xp2, float yp2)`
*   `QRectF adjusted (self, float xp1, float yp1, float xp2, float yp2)`
*   `float bottom (self)`
*   `QPointF bottomLeft (self)`
*   `QPointF bottomRight (self)`
*   `QPointF center (self)`
*   `bool contains (self, QPointF p)`
*   `bool contains (self, QRectF r)`
*   `bool contains (self, float ax, float ay)`
*   `(float xp1, float yp1, float xp2, float yp2) getCoords (self)`
*   `(float ax, float ay, float aaw, float aah) getRect (self)`
*   `float height (self)`
*   `QRectF intersect (self, QRectF r)`
*   `QRectF intersected (self, QRectF r)`
*   `bool intersects (self, QRectF r)`
*   `bool isEmpty (self)`
*   `bool isNull (self)`
*   `bool isValid (self)`
*   `float left (self)`
*   `moveBottom (self, float pos)`
*   `moveBottomLeft (self, QPointF p)`
*   `moveBottomRight (self, QPointF p)`
*   `moveCenter (self, QPointF p)`
*   `moveLeft (self, float pos)`
*   `moveRight (self, float pos)`
*   `moveTo (self, float ax, float ay)`
*   `moveTo (self, QPointF p)`
*   `moveTop (self, float pos)`
*   `moveTopLeft (self, QPointF p)`
*   `moveTopRight (self, QPointF p)`
*   `QRectF normalized (self)`
*   `float right (self)`
*   `setBottom (self, float pos)`
*   `setBottomLeft (self, QPointF p)`
*   `setBottomRight (self, QPointF p)`
*   `setCoords (self, float xp1, float yp1, float xp2, float yp2)`
*   `setHeight (self, float ah)`
*   `setLeft (self, float pos)`
*   `setRect (self, float ax, float ay, float aaw, float aah)`
*   `setRight (self, float pos)`
*   `setSize (self, QSizeF s)`
*   `setTop (self, float pos)`
*   `setTopLeft (self, QPointF p)`
*   `setTopRight (self, QPointF p)`
*   `setWidth (self, float aw)`
*   `setX (self, float pos)`
*   `setY (self, float pos)`
*   `QSizeF size (self)`
*   `QRect toAlignedRect (self)`
*   `float top (self)`
*   `QPointF topLeft (self)`
*   `QPointF topRight (self)`
*   `QRect toRect (self)`
*   `translate (self, float dx, float dy)`
*   `translate (self, QPointF p)`
*   `QRectF translated (self, float dx, float dy)`
*   `QRectF translated (self, QPointF p)`
*   `QRectF unite (self, QRectF r)`
*   `QRectF united (self, QRectF r)`
*   `float width (self)`
*   `float x (self)`
*   `float y (self)`

### Special Methods

*   `QRectF __and__ (self, QRectF r)`
*   `int __bool__ (self)`
*   `int __contains__ (self, QPointF p)`
*   `int __contains__ (self, QRectF r)`
*   `bool __eq__ (self, QRectF r2)`
*   `QRectF __iand__ (self, QRectF r)`
*   `QRectF __ior__ (self, QRectF r)`
*   `bool __ne__ (self, QRectF r2)`
*   `QRectF __or__ (self, QRectF r)`
*   `str __repr__ (self)`

* * *

## Detailed Description

这个类可以醃制。

该QRectF类定义使用浮点精度在平面的矩形。

一个矩形，通常表示为左上角和尺寸。一个QRectF的大小（宽度和高度）总是等于其形成的基础，它呈现的数学矩形。

甲QRectF可以用一组左，上，宽度和高度的整数，或者从一个被构造[QPoint](qpoint.html)和[QSize](qsize.html)。下面的代码创建两个相同的矩形。

```
 QRectF r1(100, 200, 11, 16);
 QRectF r2([QPoint](qpoint.html)(100, 200), [QSize](qsize.html)(11, 16));

```

还有一个第三个构造函数从创建QRectF[QRect](qrect.html)和一个相应[toRect](qrectf.html#toRect)（ ）函数返回一个[QRect](qrect.html)在此基础上矩形的值的对象（注意，在返回的矩形的坐标被四舍五入到最接近的整数。）

该QRectF类提供了返回的各种矩形坐标函数的集合，使操纵这些。 QRectF还提供功能，以矩形相对移动到不同的坐标。此外，还有一个[moveTo](qrectf.html#moveTo)（ ）函数，移动矩形，留下它的左上角在给定的坐标。或者，所述[translate](qrectf.html#translate)（）函数使矩形给定的偏移量相对于当前位置，并且[translated](qrectf.html#translated)（ ）函数返回这个矩形的翻译件。

该[size](qrectf.html#size)（ ）函数返回rectange的尺寸为[QSize](qsize.html)。的尺寸也可以单独使用检索到的[width](qrectf.html#width)（）和[height](qrectf.html#height)（）函数。操控方面使用[setSize](qrectf.html#setSize)（ ）[setWidth](qrectf.html#setWidth)（）或[setHeight](qrectf.html#setHeight)（）函数。可替换地，大小可以通过应用或功能设定矩形的坐标，例如被改变，[setBottom](qrectf.html#setBottom)（）或[setRight](qrectf.html#setRight)（ ） 。

该[contains](qrectf.html#contains)（ ）函数告诉一个给定的点是否是里面的矩形或没有了，[intersects](qrectf.html#intersects)如果这个矩形相交与给定的矩形（ ）函数返回True （否则返回False ） 。该QRectF类还提供了[intersected](qrectf.html#intersected)（）函数返回相交的矩形，并在[united](qrectf.html#united)（ ）函数将返回一个封装给定的矩形，这个矩形：

| ![](../img/qrect-intersect.png) | ![](../img/qrect-unite.png) |
| [intersected](qrectf.html#intersected)() | [united](qrectf.html#united)() |

该[isEmpty](qrectf.html#isEmpty)如果该矩形的宽度或高度小于或等于，大于0 ， （）函数返回真。需要注意的是一个空矩形是无效的：在[isValid](qrectf.html#isValid)如果宽度和高度大于0 （ ）函数返回True。一个空矩形（[isNull](qrectf.html#isNull)（）== TRUE） ，另一方面，也将宽度和高度设置为0。

注意，由于该方法[QRect](qrect.html)和QRectF定义，一个空QRectF在本质上以同样的方式定义为[QRect](qrect.html)。

最后，相比QRectF对象可以被串流播放，以及。

### Rendering

当使用一个[anti-aliased](qpainter.html#RenderHint-enum)画家， QRectF的边界线将对称地在数学矩形的边界线的两侧呈现。但使用一个别名画家（默认值）时，其他规则。

然后，用一个像素宽的画笔绘制时QRectF的边界线将呈现给正确的和数学矩形的边界线下方。

当与两个像素宽画笔绘制边界线会由数学矩形被分割在中间。这将是这种情况时的笔被设置成偶数个像素，而与像素数为奇数的笔绘制，备用像素将呈现向右和数学矩形中的一个像素的情况下。

| ![](../img/qrect-diagram-zero.png) | ![](../img/qrectf-diagram-one.png) |
| Logical representation | One pixel wide pen |
| ![](../img/qrectf-diagram-two.png) | ![](../img/qrectf-diagram-three.png) |
| Two pixel wide pen | Three pixel wide pen |

### Coordinates

该QRectF类提供了返回的各种矩形坐标函数的集合，使操纵这些。 QRectF还提供功能，以矩形相对移动到不同的坐标。

例如：[bottom](qrectf.html#bottom)（ ）[setBottom](qrectf.html#setBottom)（）和[moveBottom](qrectf.html#moveBottom)（ ）函数：[bottom](qrectf.html#bottom)（）返回矩形的底边的y坐标，[setBottom](qrectf.html#setBottom)（）设置矩形的底边给定的y坐标（它可能会改变高度，但决不会改变矩形的顶边）和[moveBottom](qrectf.html#moveBottom)（ ）移动整个矩形垂直，使矩形的底边在给定的y坐标和尺寸不变。

![](../img/qrectf-coordinates.png)

另外，也可以使用偏移量添加到该矩形的坐标[adjust](qrectf.html#adjust)（）函数，以及检索使用基于原来的1调整一个新的矩形的[adjusted](qrectf.html#adjusted)（）函数。如果其中的宽度和高度为负时，用[normalized](qrectf.html#normalized)（）函数来检索其中的角部被交换的矩形。

此外， QRectF提供[getCoords](qrectf.html#getCoords)（）函数，其提取的矩形的左上角和右下角的位置，并且[getRect](qrectf.html#getRect)（ ）函数，它提取矩形的左上角，宽度和高度。使用[setCoords](qrectf.html#setCoords)（）和[setRect](qrectf.html#setRect)（ ）函数来处理矩形的坐标和尺寸一气呵成。

* * *

## Method Documentation

```
QRectF.__init__ (self)
```

构造一个空矩形。

**See also** [isNull](qrectf.html#isNull)（ ） 。

```
QRectF.__init__ (self, QPointF atopLeft, QSizeF asize)
```

构造一个矩形与给定_topLeft_角部和所述定_size_。

**See also** [setTopLeft](qrectf.html#setTopLeft)（）和[setSize](qrectf.html#setSize)（ ） 。

```
QRectF.__init__ (self, QPointF atopLeft, QPointF abottomRight)
```

构造一个矩形与给定_topLeft_和_bottomRight_角落。

此功能被引入Qt的4.3 。

**See also** [setTopLeft](qrectf.html#setTopLeft)（）和[setBottomRight](qrectf.html#setBottomRight)（ ） 。

```
QRectF.__init__ (self, float aleft, float atop, float awidth, float aheight)
```

构造一个矩形（_x_，_y_）作为它的左上角和给定的_width_和_height_。

**See also** [setRect](qrectf.html#setRect)（ ） 。

```
QRectF.__init__ (self, QRect r)
```

构造一个[QRectF](qrectf.html)从给定的矩形[QRect](qrect.html) _rectangle_。

**See also** [toRect](qrectf.html#toRect)（ ） 。

```
QRectF.__init__ (self, QRectF)
```

```
QRectF.adjust (self, float xp1, float yp1, float xp2, float yp2)
```

添加_dx1_，_dy1_，_dx2_和_dy2_分别以矩形的现有的坐标。

**See also** [adjusted](qrectf.html#adjusted)（）和[setRect](qrectf.html#setRect)（ ） 。

```
QRectF QRectF.adjusted (self, float xp1, float yp1, float xp2, float yp2)
```

[

返回一个新的矩形_dx1_，_dy1_，_dx2_和_dy2_分别加入到这个矩形的现有坐标。

](qrectf.html)

[**See also**](qrectf.html) [adjust](qrectf.html#adjust)（ ） 。

```
float QRectF.bottom (self)
```

返回矩形的底边的y坐标。

**See also** [setBottom](qrectf.html#setBottom)（ ）[bottomLeft](qrectf.html#bottomLeft)（）和[bottomRight](qrectf.html#bottomRight)（ ） 。

```
QPointF QRectF.bottomLeft (self)
```

[

返回矩形的左下角的位置。

](qpointf.html)

[**See also**](qpointf.html) [setBottomLeft](qrectf.html#setBottomLeft)（ ）[bottom](qrectf.html#bottom)（）和[left](qrectf.html#left)（ ） 。

```
QPointF QRectF.bottomRight (self)
```

[

返回矩形的右下角的位置。

](qpointf.html)

[**See also**](qpointf.html) [setBottomRight](qrectf.html#setBottomRight)（ ）[bottom](qrectf.html#bottom)（）和[right](qrectf.html#right)（ ） 。

```
QPointF QRectF.center (self)
```

[

返回矩形的中心点。

](qpointf.html)

[**See also**](qpointf.html) [moveCenter](qrectf.html#moveCenter)（ ） 。

```
bool QRectF.contains (self, QPointF p)
```

返回True如果给定的_point_是内部或矩形的边缘，否则返回False 。

**See also** [intersects](qrectf.html#intersects)（ ） 。

```
bool QRectF.contains (self, QRectF r)
```

这是一个重载函数。

返回True如果点（_x_，_y_）是内部或矩形的边缘，否则返回False 。

```
bool QRectF.contains (self, float ax, float ay)
```

这是一个重载函数。

返回True如果给定的_rectangle_是这个矩形里面，否则返回False 。

```
(float xp1, float yp1, float xp2, float yp2) QRectF.getCoords (self)
```

提取矩形的左上角的位置*_x1_和*_y1_和右下角为*的位置_x2_和*_y2_。

**See also** [setCoords](qrectf.html#setCoords)（）和[getRect](qrectf.html#getRect)（ ） 。

```
(float ax, float ay, float aaw, float aah) QRectF.getRect (self)
```

提取矩形的左上角的位置*_x_和*_y_，其尺寸*_width_和*_height_。

**See also** [setRect](qrectf.html#setRect)（）和[getCoords](qrectf.html#getCoords)（ ） 。

```
float QRectF.height (self)
```

返回该矩形的高度。

**See also** [setHeight](qrectf.html#setHeight)（ ）[width](qrectf.html#width)（）和[size](qrectf.html#size)（ ） 。

```
QRectF QRectF.intersect (self, QRectF r)
```

[](qrectf.html)

```
QRectF QRectF.intersected (self, QRectF r)
```

[

返回此矩形的交集和给定的_rectangle_。需要注意的是`r.intersected(s)`相当于`r & s`。

![](../img/qrect-intersect.png)

这个函数中引入了Qt 4.2中。

](qrectf.html)

[**See also**](qrectf.html) [intersects](qrectf.html#intersects)（ ）[united](qrectf.html#united)（）和[operator&=](qrectf.html#operator-and-eq)（ ） 。

```
bool QRectF.intersects (self, QRectF r)
```

如果这个矩形相交与给定的，则返回True_rectangle_（即它们之间有重叠的非空白区域） ，否则返回False 。

相交的矩形可使用检索到的[intersected](qrectf.html#intersected)（）函数。

**See also** [contains](qrectf.html#contains)（ ） 。

```
bool QRectF.isEmpty (self)
```

返回True如果矩形为空，否则返回False 。

一个空矩形有[width](qrectf.html#width)（）\u003c = 0或[height](qrectf.html#height)（）\u003c = 0 。一个空矩形是无效的（即，参考isEmpty （ ） == ！[isValid](qrectf.html#isValid)（））。

使用[normalized](qrectf.html#normalized)（）函数来检索其中的角部被交换的矩形。

**See also** [isNull](qrectf.html#isNull)（ ）[isValid](qrectf.html#isValid)（）和[normalized](qrectf.html#normalized)（ ） 。

```
bool QRectF.isNull (self)
```

返回True如果矩形为空矩形，否则返回False 。

空矩形具有的宽度和高度设置为0。一个空的矩形也是空的，因此无效。

**See also** [isEmpty](qrectf.html#isEmpty)（）和[isValid](qrectf.html#isValid)（ ） 。

```
bool QRectF.isValid (self)
```

返回True如果矩形是有效的，否则返回False 。

一个有效的矩形有一个[width](qrectf.html#width)（）\u003e 0和[height](qrectf.html#height)（）\u003e 0 。请注意，就像十字路口不平凡的操作没有定义无效矩形。一个有效的矩形不为空（即参考isValid （ ） == ！[isEmpty](qrectf.html#isEmpty)（））。

**See also** [isNull](qrectf.html#isNull)（ ）[isEmpty](qrectf.html#isEmpty)（）和[normalized](qrectf.html#normalized)（ ） 。

```
float QRectF.left (self)
```

返回矩形的左边缘的x坐标。相当于[x](qrectf.html#x)（ ） 。

**See also** [setLeft](qrectf.html#setLeft)（ ）[topLeft](qrectf.html#topLeft)（）和[bottomLeft](qrectf.html#bottomLeft)（ ） 。

```
QRectF.moveBottom (self, float pos)
```

移动矩形垂直，使矩形的底边在给定的_y_协调。矩形的尺寸是不变的。

**See also** [bottom](qrectf.html#bottom)（ ）[setBottom](qrectf.html#setBottom)（）和[moveTop](qrectf.html#moveTop)（ ） 。

```
QRectF.moveBottomLeft (self, QPointF p)
```

移动矩形，留下左下角在给定的_position_。矩形的尺寸是不变的。

**See also** [setBottomLeft](qrectf.html#setBottomLeft)（ ）[moveBottom](qrectf.html#moveBottom)（）和[moveLeft](qrectf.html#moveLeft)（ ） 。

```
QRectF.moveBottomRight (self, QPointF p)
```

移动矩形，留下右下角的定_position_。矩形的尺寸是不变的。

**See also** [setBottomRight](qrectf.html#setBottomRight)（ ）[moveBottom](qrectf.html#moveBottom)（）和[moveRight](qrectf.html#moveRight)（ ） 。

```
QRectF.moveCenter (self, QPointF p)
```

移动矩形，而使中心点在给定的_position_。矩形的尺寸是不变的。

**See also** [center](qrectf.html#center)（ ） 。

```
QRectF.moveLeft (self, float pos)
```

水平移动矩形，使矩形的左边缘在给定的_x_协调。矩形的尺寸是不变的。

**See also** [left](qrectf.html#left)（ ）[setLeft](qrectf.html#setLeft)（）和[moveRight](qrectf.html#moveRight)（ ） 。

```
QRectF.moveRight (self, float pos)
```

水平移动矩形，使矩形的右边缘在给定的_x_协调。矩形的尺寸是不变的。

**See also** [right](qrectf.html#right)（ ）[setRight](qrectf.html#setRight)（）和[moveLeft](qrectf.html#moveLeft)（ ） 。

```
QRectF.moveTo (self, float ax, float ay)
```

移动矩形，留下左上角的指定位置（_x_，_y_） 。矩形的尺寸是不变的。

**See also** [translate](qrectf.html#translate)（）和[moveTopLeft](qrectf.html#moveTopLeft)（ ） 。

```
QRectF.moveTo (self, QPointF p)
```

这是一个重载函数。

移动矩形，留下左上角在给定的_position_。

```
QRectF.moveTop (self, float pos)
```

移动矩形垂直，使矩形的顶线在给定的_y_协调。矩形的尺寸是不变的。

**See also** [top](qrectf.html#top)（ ）[setTop](qrectf.html#setTop)（）和[moveBottom](qrectf.html#moveBottom)（ ） 。

```
QRectF.moveTopLeft (self, QPointF p)
```

移动矩形，留下左上角在给定的_position_。矩形的尺寸是不变的。

**See also** [setTopLeft](qrectf.html#setTopLeft)（ ）[moveTop](qrectf.html#moveTop)（）和[moveLeft](qrectf.html#moveLeft)（ ） 。

```
QRectF.moveTopRight (self, QPointF p)
```

移动矩形，留下右上角的定_position_。矩形的尺寸是不变的。

**See also** [setTopRight](qrectf.html#setTopRight)（ ）[moveTop](qrectf.html#moveTop)（）和[moveRight](qrectf.html#moveRight)（ ） 。

```
QRectF QRectF.normalized (self)
```

[

返回一个归一化的矩形，即，具有一个非负的宽度和高度的矩形。

](qrectf.html)

[If](qrectf.html) [width](qrectf.html#width)（）\u003c 0的函数交换的左右角部，并且交换的顶部和底部边角，如果[height](qrectf.html#height)（）\u003c 0 。

**See also** [isValid](qrectf.html#isValid)（）和[isEmpty](qrectf.html#isEmpty)（ ） 。

```
float QRectF.right (self)
```

返回矩形的右边缘的x坐标。

**See also** [setRight](qrectf.html#setRight)（ ）[topRight](qrectf.html#topRight)（）和[bottomRight](qrectf.html#bottomRight)（ ） 。

```
QRectF.setBottom (self, float pos)
```

设置的矩形的底部边缘与给定的_y_协调。可能会改变高度，但决不会改变矩形的上边缘。

**See also** [bottom](qrectf.html#bottom)（）和[moveBottom](qrectf.html#moveBottom)（ ） 。

```
QRectF.setBottomLeft (self, QPointF p)
```

设置矩形的左下角给定的_position_。可以改变大小，但决不会改变矩形的右上角。

**See also** [bottomLeft](qrectf.html#bottomLeft)（）和[moveBottomLeft](qrectf.html#moveBottomLeft)（ ） 。

```
QRectF.setBottomRight (self, QPointF p)
```

设置矩形的右下角为给定的_position_。可以改变大小，但决不会改变矩形的左上角。

**See also** [bottomRight](qrectf.html#bottomRight)（）和[moveBottomRight](qrectf.html#moveBottomRight)（ ） 。

```
QRectF.setCoords (self, float xp1, float yp1, float xp2, float yp2)
```

设置矩形的左上角的坐标为（_x1_，_y1_）和其右下角的坐标（_x2_，_y2_） 。

**See also** [getCoords](qrectf.html#getCoords)（）和[setRect](qrectf.html#setRect)（ ） 。

```
QRectF.setHeight (self, float ah)
```

设置了矩形的高度为给定的_height_。底部边缘被改变，但不顶一个。

**See also** [height](qrectf.html#height)（）和[setSize](qrectf.html#setSize)（ ） 。

```
QRectF.setLeft (self, float pos)
```

设置了矩形的左边缘到给定的_x_协调。可能会改变宽度，但决不会改变矩形的右边缘。

相当于[setX](qrectf.html#setX)（ ） 。

**See also** [left](qrectf.html#left)（）和[moveLeft](qrectf.html#moveLeft)（ ） 。

```
QRectF.setRect (self, float ax, float ay, float aaw, float aah)
```

设置矩形的左上角的坐标为（_x_，_y_） ，并且其大小为给定的_width_和_height_。

**See also** [getRect](qrectf.html#getRect)（）和[setCoords](qrectf.html#setCoords)（ ） 。

```
QRectF.setRight (self, float pos)
```

设置了矩形的右边缘到给定的_x_协调。可能会改变宽度，但决不会改变矩形的左边缘。

**See also** [right](qrectf.html#right)（）和[moveRight](qrectf.html#moveRight)（ ） 。

```
QRectF.setSize (self, QSizeF s)
```

设置了矩形的大小给定的_size_。在左上角不移动。

**See also** [size](qrectf.html#size)（ ）[setWidth](qrectf.html#setWidth)（）和[setHeight](qrectf.html#setHeight)（ ） 。

```
QRectF.setTop (self, float pos)
```

设置了矩形的顶边到给定的_y_协调。可能会改变高度，但决不会改变矩形的底边。

相当于[setY](qrectf.html#setY)（ ） 。

**See also** [top](qrectf.html#top)（）和[moveTop](qrectf.html#moveTop)（ ） 。

```
QRectF.setTopLeft (self, QPointF p)
```

设置的矩形的左上角的给定_position_。可以改变大小，但决不会改变矩形的右下角。

**See also** [topLeft](qrectf.html#topLeft)（）和[moveTopLeft](qrectf.html#moveTopLeft)（ ） 。

```
QRectF.setTopRight (self, QPointF p)
```

设置矩形的右上角，以给定的_position_。可以改变大小，但决不会改变矩形的左下角。

**See also** [topRight](qrectf.html#topRight)（）和[moveTopRight](qrectf.html#moveTopRight)（ ） 。

```
QRectF.setWidth (self, float aw)
```

设置了矩形的宽度与给定_width_。右边缘被改变，但不是左1 。

**See also** [width](qrectf.html#width)（）和[setSize](qrectf.html#setSize)（ ） 。

```
QRectF.setX (self, float pos)
```

设置了矩形的左边缘到给定的_x_协调。可能会改变宽度，但决不会改变矩形的右边缘。

相当于[setLeft](qrectf.html#setLeft)（ ） 。

**See also** [x](qrectf.html#x)（ ）[setY](qrectf.html#setY)（）和[setTopLeft](qrectf.html#setTopLeft)（ ） 。

```
QRectF.setY (self, float pos)
```

设置了矩形的顶边到给定的_y_协调。可能会改变高度，但决不会改变矩形的底边。

相当于[setTop](qrectf.html#setTop)（ ） 。

**See also** [y](qrectf.html#y)（ ）[setX](qrectf.html#setX)（）和[setTopLeft](qrectf.html#setTopLeft)（ ） 。

```
QSizeF QRectF.size (self)
```

[

返回矩形的大小。

](qsizef.html)

[**See also**](qsizef.html) [setSize](qrectf.html#setSize)（ ）[width](qrectf.html#width)（）和[height](qrectf.html#height)（ ） 。

```
QRect QRectF.toAlignedRect (self)
```

[](qrect.html)

[返回](qrect.html)[QRect](qrect.html)基于这个矩形是可能的最小整数矩形完全包含此矩形的值。

此功能被引入Qt的4.3 。

**See also** [toRect](qrectf.html#toRect)（ ） 。

```
float QRectF.top (self)
```

返回矩形的上边缘的y坐标。相当于[y](qrectf.html#y)（ ） 。

**See also** [setTop](qrectf.html#setTop)（ ）[topLeft](qrectf.html#topLeft)（）和[topRight](qrectf.html#topRight)（ ） 。

```
QPointF QRectF.topLeft (self)
```

[

返回矩形的左上角的位置。

](qpointf.html)

[**See also**](qpointf.html) [setTopLeft](qrectf.html#setTopLeft)（ ）[top](qrectf.html#top)（）和[left](qrectf.html#left)（ ） 。

```
QPointF QRectF.topRight (self)
```

[

返回矩形的右上角的位置。

](qpointf.html)

[**See also**](qpointf.html) [setTopRight](qrectf.html#setTopRight)（ ）[top](qrectf.html#top)（）和[right](qrectf.html#right)（ ） 。

```
QRect QRectF.toRect (self)
```

[](qrect.html)

[返回](qrect.html)[QRect](qrect.html)在此基础上矩形的值。请注意，在返回的矩形坐标四舍五入到最接近的整数。

**See also** [QRectF](qrectf.html#QRectF)（）和[toAlignedRect](qrectf.html#toAlignedRect)（ ） 。

```
QRectF.translate (self, float dx, float dy)
```

移动矩形_dx_沿x轴和_dy_沿着y轴，相对于当前位置。正值移动矩形向右，向下。

**See also** [moveTopLeft](qrectf.html#moveTopLeft)（ ）[moveTo](qrectf.html#moveTo)（）和[translated](qrectf.html#translated)（ ） 。

```
QRectF.translate (self, QPointF p)
```

这是一个重载函数。

移动矩形_offset_。[x()](qpointf.html#x)沿x轴和_offset_。[y()](qpointf.html#y)沿着y轴，相对于当前位置。

```
QRectF QRectF.translated (self, float dx, float dy)
```

[

返回矩形的副本被翻译_dx_沿x轴和_dy_沿着y轴，相对于当前位置。正值移动矩形向右和向下。

](qrectf.html)

[**See also**](qrectf.html) [translate](qrectf.html#translate)（ ） 。

```
QRectF QRectF.translated (self, QPointF p)
```

[

这是一个重载函数。

](qrectf.html)

[返回矩形的副本被翻译_offset_。](qrectf.html)[x()](qpointf.html#x)沿x轴和_offset_。[y()](qpointf.html#y)沿着y轴，相对于当前位置。

```
QRectF QRectF.unite (self, QRectF r)
```

[](qrectf.html)

```
QRectF QRectF.united (self, QRectF r)
```

[

返回此矩形的边框和给定_rectangle_。

![](../img/qrect-unite.png)

这个函数中引入了Qt 4.2中。

](qrectf.html)

[**See also**](qrectf.html) [intersected](qrectf.html#intersected)（ ） 。

```
float QRectF.width (self)
```

返回矩形的宽度。

**See also** [setWidth](qrectf.html#setWidth)（ ）[height](qrectf.html#height)（）和[size](qrectf.html#size)（ ） 。

```
float QRectF.x (self)
```

返回矩形的左边缘的x坐标。相当于[left](qrectf.html#left)（ ） 。

**See also** [setX](qrectf.html#setX)（ ）[y](qrectf.html#y)（）和[topLeft](qrectf.html#topLeft)（ ） 。

```
float QRectF.y (self)
```

返回矩形的上边缘的y坐标。相当于[top](qrectf.html#top)（ ） 。

**See also** [setY](qrectf.html#setY)（ ）[x](qrectf.html#x)（）和[topLeft](qrectf.html#topLeft)（ ） 。

```
QRectF QRectF.__and__ (self, QRectF r)
```

[

```
int QRectF.__bool__ (self)
```

```
int QRectF.__contains__ (self, QPointF p)
```

```
int QRectF.__contains__ (self, QRectF r)
```

```
bool QRectF.__eq__ (self, QRectF r2)
```

](qrectf.html)

```
QRectF QRectF.__iand__ (self, QRectF r)
```

[](qrectf.html)

```
QRectF QRectF.__ior__ (self, QRectF r)
```

[

```
bool QRectF.__ne__ (self, QRectF r2)
```

](qrectf.html)

```
QRectF QRectF.__or__ (self, QRectF r)
```

[

```
str QRectF.__repr__ (self)
```

](qrectf.html)