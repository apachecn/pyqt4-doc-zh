# QPaintEvent Class Reference

## [[QtGui](index.htm) module]

该QPaintEvent类包含事件参数的paint事件。[More...](#details)

继承[QEvent](qevent.html)。

### Methods

*   `__init__ (self, QRegion paintRegion)`
*   `__init__ (self, QRect paintRect)`
*   `__init__ (self, QPaintEvent)`
*   `QRect rect (self)`
*   `QRegion region (self)`

* * *

## Detailed Description

该QPaintEvent类包含事件参数的paint事件。

Paint事件被发送到需要更新自己，例如，当一个部件的一部分露出小部件，因为复盖部件被感动了。

该事件包含一个[region](qpaintevent.html#region)（）需要被更新，并且[rect](qpaintevent.html#rect)（）是该地区的边界矩形。两者都提供了，因为很多部件无法做出多大用处的[region](qpaintevent.html#region)（）和[rect](qpaintevent.html#rect)（ ）可以比快得多[region](qpaintevent.html#region)（ ） 。 boundingRect （ ） 。

### Automatic Clipping

画是夹在[region](qpaintevent.html#region)（ ）油漆事件的处理过程中。这条新闻是由Qt的油漆系统中进行，并独立可应用于任何削波[QPainter](qpainter.html)用于绘制油漆设备上。

其结果，返回的值[QPainter.clipRegion](qpainter.html#clipRegion)（ ）在新落成的[QPainter](qpainter.html)将不反映所使用的涂料系统的裁剪区域。

* * *

## Method Documentation

```
QPaintEvent.__init__ (self, QRegion paintRegion)
```

构造一个Paint事件对象需要被更新的区域。这个地区被指定_paintRegion_。

```
QPaintEvent.__init__ (self, QRect paintRect)
```

构造一个Paint事件对象与需要更新的矩形。这个地区被指定_paintRect_。

```
QPaintEvent.__init__ (self, QPaintEvent)
```

```
QRect QPaintEvent.rect (self)
```

[

返回需要被更新的矩形。

](qrect.html)

[**See also**](qrect.html) [region](qpaintevent.html#region)（）和[QPainter.setClipRect](qpainter.html#setClipRect)（ ） 。

```
QRegion QPaintEvent.region (self)
```

[

返回需要更新的区域。

](qregion.html)

[**See also**](qregion.html) [rect](qpaintevent.html#rect)（）和[QPainter.setClipRegion](qpainter.html#setClipRegion)（ ） 。