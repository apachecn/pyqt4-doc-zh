# QSizeF Class Reference

## [[QtCore](index.htm) module]

该QSizeF类定义了使用浮点精度的二维对象的大小。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QSize sz)`
*   `__init__ (self, float w, float h)`
*   `__init__ (self, QSizeF)`
*   `QSizeF boundedTo (self, QSizeF otherSize)`
*   `QSizeF expandedTo (self, QSizeF otherSize)`
*   `float height (self)`
*   `bool isEmpty (self)`
*   `bool isNull (self)`
*   `bool isValid (self)`
*   `scale (self, QSizeF s, Qt.AspectRatioMode mode)`
*   `scale (self, float w, float h, Qt.AspectRatioMode mode)`
*   `setHeight (self, float h)`
*   `setWidth (self, float w)`
*   `QSize toSize (self)`
*   `transpose (self)`
*   `float width (self)`

### Special Methods

*   `QSizeF __add__ (self, QSizeF s2)`
*   `int __bool__ (self)`
*   `QSizeF __div__ (self, float c)`
*   `bool __eq__ (self, QSizeF s2)`
*   `QSizeF __iadd__ (self, QSizeF s)`
*   `QSizeF __idiv__ (self, float c)`
*   `QSizeF __imul__ (self, float c)`
*   `QSizeF __isub__ (self, QSizeF s)`
*   `QSizeF __mul__ (self, float c)`
*   `QSizeF __mul__ (self, QSizeF s)`
*   `bool __ne__ (self, QSizeF s2)`
*   `str __repr__ (self)`
*   `QSizeF __sub__ (self, QSizeF s2)`

* * *

## Detailed Description

这个类可以醃制。

该QSizeF类定义了使用浮点精度的二维对象的大小。

大小是由一个指定的[width](qsizef.html#width)（）和一个[height](qsizef.html#height)（ ） 。它可以在构造函数中设置和使用改变了[setWidth](qsizef.html#setWidth)（ ）[setHeight](qsizef.html#setHeight)（） ，或[scale](qsizef.html#scale)（ ）函数，或者使用算术运算符。阿尺寸也可以通过使用检索引用的宽度和高度直接操作[rwidth](qsizef.html#rwidth)（）和[rheight](qsizef.html#rheight)（）函数。最后，将宽度和高度可以使用被交换的[transpose](qsizef.html#transpose)（）函数。

该[isValid](qsizef.html#isValid)（ ）函数判断一个尺寸是有效的。一个有效的大小具有宽度和高度大于或等于零。该[isEmpty](qsizef.html#isEmpty)如果无论是宽度和高度是（ ）函数返回True_less_比（或等于）零，而[isNull](qsizef.html#isNull)只有当二者的宽度和高度是零（）函数返回真。

使用[expandedTo](qsizef.html#expandedTo)（）函数来检索一个尺寸，持有此大小的最大高度和宽度，并在给定的尺寸。类似地，[boundedTo](qsizef.html#boundedTo)（）函数返回一个尺寸，持有此大小的最小高度和宽度，并在给定的尺寸。

该QSizeF类还提供了[toSize](qsizef.html#toSize)（ ）函数返回一个[QSize](qsize.html)这种尺寸的拷贝，通过舍入的宽度和高度为最接近的整数构成。

相比QSizeF对象可以被串流播放以及。

* * *

## Method Documentation

```
QSizeF.__init__ (self)
```

构造一个无效的大小。

**See also** [isValid](qsizef.html#isValid)（ ） 。

```
QSizeF.__init__ (self, QSize sz)
```

构造一个大小与从给定的浮点精确度_size_。

**See also** [toSize](qsizef.html#toSize)（ ） 。

```
QSizeF.__init__ (self, float w, float h)
```

构造一个大小与给定_width_和_height_。

```
QSizeF.__init__ (self, QSizeF)
```

```
QSizeF QSizeF.boundedTo (self, QSizeF otherSize)
```

[

返回一个大小保持这个大小的最小宽度和高度与给定的_otherSize_。

](qsizef.html)

[**See also**](qsizef.html) [expandedTo](qsizef.html#expandedTo)（）和[scale](qsizef.html#scale)（ ） 。

```
QSizeF QSizeF.expandedTo (self, QSizeF otherSize)
```

[

返回一个大小保持这个大小的最大宽度和高度与给定的_otherSize_。

](qsizef.html)

[**See also**](qsizef.html) [boundedTo](qsizef.html#boundedTo)（）和[scale](qsizef.html#scale)（ ） 。

```
float QSizeF.height (self)
```

返回的高度。

**See also** [width](qsizef.html#width)（）和[setHeight](qsizef.html#setHeight)（ ） 。

```
bool QSizeF.isEmpty (self)
```

返回True ，如果不是的宽度和高度小于或等于0 ，否则返回False 。

**See also** [isNull](qsizef.html#isNull)（）和[isValid](qsizef.html#isValid)（ ） 。

```
bool QSizeF.isNull (self)
```

返回True如果宽度和高度分别为0.0 ，否则返回False 。

**Note:**由于此函数将+0.0和-0.0不同，尺寸与零宽度和高度，其中一个或两个值有一个负号没有被定义为空尺寸。

**See also** [isValid](qsizef.html#isValid)（）和[isEmpty](qsizef.html#isEmpty)（ ） 。

```
bool QSizeF.isValid (self)
```

返回True，如果两者的宽度和高度是等于或大于0 ，否则返回假。

**See also** [isNull](qsizef.html#isNull)（）和[isEmpty](qsizef.html#isEmpty)（ ） 。

```
QSizeF.scale (self, QSizeF s, Qt.AspectRatioMode mode)
```

缩放大小的矩形与给定的_width_和_height_，根据指定的_mode_。

*   If _mode_ is [Qt.IgnoreAspectRatio](qt.html#AspectRatioMode-enum), the size is set to (_width_, _height_).
*   If _mode_ is [Qt.KeepAspectRatio](qt.html#AspectRatioMode-enum), the current size is scaled to a rectangle as large as possible inside (_width_, _height_), preserving the aspect ratio.
*   If _mode_ is [Qt.KeepAspectRatioByExpanding](qt.html#AspectRatioMode-enum), the current size is scaled to a rectangle as small as possible outside (_width_, _height_), preserving the aspect ratio.

例如：

```
 [QSizeF](qsizef.html) t1(10, 12);
 t1.scale(60, 60, [Qt](qt.html).IgnoreAspectRatio);
 // t1 is (60, 60)

 [QSizeF](qsizef.html) t2(10, 12);
 t2.scale(60, 60, [Qt](qt.html).KeepAspectRatio);
 // t2 is (50, 60)

 [QSizeF](qsizef.html) t3(10, 12);
 t3.scale(60, 60, [Qt](qt.html).KeepAspectRatioByExpanding);
 // t3 is (60, 72)

```

**See also** [setWidth](qsizef.html#setWidth)（）和[setHeight](qsizef.html#setHeight)（ ） 。

```
QSizeF.scale (self, float w, float h, Qt.AspectRatioMode mode)
```

这是一个重载函数。

缩放大小的矩形与给定的_size_，根据指定的_mode_。

```
QSizeF.setHeight (self, float h)
```

设置高度为给定的_height_。

**See also** [height](qsizef.html#height)（ ）[rheight](qsizef.html#rheight)（）和[setWidth](qsizef.html#setWidth)（ ） 。

```
QSizeF.setWidth (self, float w)
```

设置宽度为给定的_width_。

**See also** [width](qsizef.html#width)（ ）[rwidth](qsizef.html#rwidth)（）和[setHeight](qsizef.html#setHeight)（ ） 。

```
QSize QSizeF.toSize (self)
```

[

返回此尺寸的基于整数的副本。

请注意，在返回的大小的坐标将被四舍五入到最接近的整数。

](qsize.html)

[**See also**](qsize.html) [QSizeF](qsizef.html#QSizeF)（ ） 。

```
QSizeF.transpose (self)
```

交换的宽度和高度的值。

**See also** [setWidth](qsizef.html#setWidth)（）和[setHeight](qsizef.html#setHeight)（ ） 。

```
float QSizeF.width (self)
```

返回的宽度。

**See also** [height](qsizef.html#height)（）和[setWidth](qsizef.html#setWidth)（ ） 。

```
QSizeF QSizeF.__add__ (self, QSizeF s2)
```

[

```
int QSizeF.__bool__ (self)
```

](qsizef.html)

```
QSizeF QSizeF.__div__ (self, float c)
```

[

```
bool QSizeF.__eq__ (self, QSizeF s2)
```

](qsizef.html)

```
QSizeF QSizeF.__iadd__ (self, QSizeF s)
```

[](qsizef.html)

```
QSizeF QSizeF.__idiv__ (self, float c)
```

[](qsizef.html)

```
QSizeF QSizeF.__imul__ (self, float c)
```

[](qsizef.html)

```
QSizeF QSizeF.__isub__ (self, QSizeF s)
```

[](qsizef.html)

```
QSizeF QSizeF.__mul__ (self, float c)
```

[](qsizef.html)

```
QSizeF QSizeF.__mul__ (self, QSizeF s)
```

[

```
bool QSizeF.__ne__ (self, QSizeF s2)
```

```
str QSizeF.__repr__ (self)
```

](qsizef.html)

```
QSizeF QSizeF.__sub__ (self, QSizeF s2)
```

[](qsizef.html)