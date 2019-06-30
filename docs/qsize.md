# QSize Class Reference

## [[QtCore](index.htm) module]

该QSIZE类定义使用整数点位精度二维物体的大小。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, int w, int h)`
*   `__init__ (self, QSize)`
*   `QSize boundedTo (self, QSize otherSize)`
*   `QSize expandedTo (self, QSize otherSize)`
*   `int height (self)`
*   `bool isEmpty (self)`
*   `bool isNull (self)`
*   `bool isValid (self)`
*   `scale (self, QSize s, Qt.AspectRatioMode mode)`
*   `scale (self, int w, int h, Qt.AspectRatioMode mode)`
*   `setHeight (self, int h)`
*   `setWidth (self, int w)`
*   `transpose (self)`
*   `int width (self)`

### Special Methods

*   `QSize __add__ (self, QSize s2)`
*   `int __bool__ (self)`
*   `QSize __div__ (self, float c)`
*   `bool __eq__ (self, QSize s2)`
*   `QSize __iadd__ (self, QSize s)`
*   `QSize __idiv__ (self, float c)`
*   `QSize __imul__ (self, float c)`
*   `QSize __isub__ (self, QSize s)`
*   `QSize __mul__ (self, float c)`
*   `QSize __mul__ (self, QSize s)`
*   `bool __ne__ (self, QSize s2)`
*   `str __repr__ (self)`
*   `QSize __sub__ (self, QSize s2)`

* * *

## Detailed Description

这个类可以醃制。

该QSIZE类定义使用整数点位精度二维物体的大小。

大小是由一个指定的[width](qsize.html#width)（）和一个[height](qsize.html#height)（ ） 。它可以在构造函数中设置和使用改变了[setWidth](qsize.html#setWidth)（ ）[setHeight](qsize.html#setHeight)（） ，或[scale](qsize.html#scale)（ ）函数，或者使用算术运算符。阿尺寸也可以通过使用检索引用的宽度和高度直接操作[rwidth](qsize.html#rwidth)（）和[rheight](qsize.html#rheight)（）函数。最后，将宽度和高度可以使用被交换的[transpose](qsize.html#transpose)（）函数。

该[isValid](qsize.html#isValid)（ ）函数确定的尺寸是有效的（有效尺寸有宽度和高度大于零） 。该[isEmpty](qsize.html#isEmpty)（）函数返回真，如果任一宽度和高度是小于或等于，大于零，而[isNull](qsize.html#isNull)只有当二者的宽度和高度是零（）函数返回真。

使用[expandedTo](qsize.html#expandedTo)（）函数来检索一个大小而持有的最大高度和宽度_this_尺寸和给定的尺寸。类似地，[boundedTo](qsize.html#boundedTo)（ ）函数返回一个大小持有的最小高度和宽度_this_尺寸和给定的尺寸。

相比QSIZE对象可以被串流播放以及。

* * *

## Method Documentation

```
QSize.__init__ (self)
```

构造一个大小与一个无效的宽度和高度（即[isValid](qsize.html#isValid)（ ）返回False ） 。

**See also** [isValid](qsize.html#isValid)（ ） 。

```
QSize.__init__ (self, int w, int h)
```

构造一个大小与给定_width_和_height_。

**See also** [setWidth](qsize.html#setWidth)（）和[setHeight](qsize.html#setHeight)（ ） 。

```
QSize.__init__ (self, QSize)
```

```
QSize QSize.boundedTo (self, QSize otherSize)
```

[

返回一个大小保持这个大小的最小宽度和高度与给定的_otherSize_。

](qsize.html)

[**See also**](qsize.html) [expandedTo](qsize.html#expandedTo)（）和[scale](qsize.html#scale)（ ） 。

```
QSize QSize.expandedTo (self, QSize otherSize)
```

[

返回一个大小保持这个大小的最大宽度和高度与给定的_otherSize_。

](qsize.html)

[**See also**](qsize.html) [boundedTo](qsize.html#boundedTo)（）和[scale](qsize.html#scale)（ ） 。

```
int QSize.height (self)
```

返回的高度。

**See also** [width](qsize.html#width)（）和[setHeight](qsize.html#setHeight)（ ） 。

```
bool QSize.isEmpty (self)
```

返回True ，如果不是的宽度和高度小于或等于0 ，否则返回False 。

**See also** [isNull](qsize.html#isNull)（）和[isValid](qsize.html#isValid)（ ） 。

```
bool QSize.isNull (self)
```

返回True如果宽度和高度为0 ，否则返回False 。

**See also** [isValid](qsize.html#isValid)（）和[isEmpty](qsize.html#isEmpty)（ ） 。

```
bool QSize.isValid (self)
```

返回True，如果两者的宽度和高度是等于或大于0 ，否则返回假。

**See also** [isNull](qsize.html#isNull)（）和[isEmpty](qsize.html#isEmpty)（ ） 。

```
QSize.scale (self, QSize s, Qt.AspectRatioMode mode)
```

缩放大小的矩形与给定的_width_和_height_，根据指定的_mode_：

*   If _mode_ is [Qt.IgnoreAspectRatio](qt.html#AspectRatioMode-enum), the size is set to (_width_, _height_).
*   If _mode_ is [Qt.KeepAspectRatio](qt.html#AspectRatioMode-enum), the current size is scaled to a rectangle as large as possible inside (_width_, _height_), preserving the aspect ratio.
*   If _mode_ is [Qt.KeepAspectRatioByExpanding](qt.html#AspectRatioMode-enum), the current size is scaled to a rectangle as small as possible outside (_width_, _height_), preserving the aspect ratio.

例如：

```
 [QSize](qsize.html) t1(10, 12);
 t1.scale(60, 60, [Qt](qt.html).IgnoreAspectRatio);
 // t1 is (60, 60)

 [QSize](qsize.html) t2(10, 12);
 t2.scale(60, 60, [Qt](qt.html).KeepAspectRatio);
 // t2 is (50, 60)

 [QSize](qsize.html) t3(10, 12);
 t3.scale(60, 60, [Qt](qt.html).KeepAspectRatioByExpanding);
 // t3 is (60, 72)

```

**See also** [setWidth](qsize.html#setWidth)（）和[setHeight](qsize.html#setHeight)（ ） 。

```
QSize.scale (self, int w, int h, Qt.AspectRatioMode mode)
```

这是一个重载函数。

缩放大小的矩形与给定的_size_，根据指定的_mode_。

```
QSize.setHeight (self, int h)
```

设置高度为给定的_height_。

**See also** [rheight](qsize.html#rheight)（ ）[height](qsize.html#height)（）和[setWidth](qsize.html#setWidth)（ ） 。

```
QSize.setWidth (self, int w)
```

设置宽度为给定的_width_。

**See also** [rwidth](qsize.html#rwidth)（ ）[width](qsize.html#width)（）和[setHeight](qsize.html#setHeight)（ ） 。

```
QSize.transpose (self)
```

交换的宽度和高度的值。

**See also** [setWidth](qsize.html#setWidth)（）和[setHeight](qsize.html#setHeight)（ ） 。

```
int QSize.width (self)
```

返回的宽度。

**See also** [height](qsize.html#height)（）和[setWidth](qsize.html#setWidth)（ ） 。

```
QSize QSize.__add__ (self, QSize s2)
```

[

```
int QSize.__bool__ (self)
```

](qsize.html)

```
QSize QSize.__div__ (self, float c)
```

[

```
bool QSize.__eq__ (self, QSize s2)
```

](qsize.html)

```
QSize QSize.__iadd__ (self, QSize s)
```

[](qsize.html)

```
QSize QSize.__idiv__ (self, float c)
```

[](qsize.html)

```
QSize QSize.__imul__ (self, float c)
```

[](qsize.html)

```
QSize QSize.__isub__ (self, QSize s)
```

[](qsize.html)

```
QSize QSize.__mul__ (self, float c)
```

[](qsize.html)

```
QSize QSize.__mul__ (self, QSize s)
```

[

```
bool QSize.__ne__ (self, QSize s2)
```

```
str QSize.__repr__ (self)
```

](qsize.html)

```
QSize QSize.__sub__ (self, QSize s2)
```

[](qsize.html)