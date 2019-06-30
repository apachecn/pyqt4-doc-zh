# QCommonStyle Class Reference

## [[QtGui](index.htm) module]

该QCommonStyle类封装了图形用户界面的共同外观和感觉。[More...](#details)

继承[QStyle](qstyle.html)。

### Methods

*   `__init__ (self)`
*   `drawComplexControl (self, QStyle.ComplexControl cc, QStyleOptionComplex opt, QPainter p, QWidget widget = None)`
*   `drawControl (self, QStyle.ControlElement element, QStyleOption opt, QPainter p, QWidget widget = None)`
*   `drawPrimitive (self, QStyle.PrimitiveElement pe, QStyleOption opt, QPainter p, QWidget widget = None)`
*   `QPixmap generatedIconPixmap (self, QIcon.Mode iconMode, QPixmap pixmap, QStyleOption opt)`
*   `QStyle.SubControl hitTestComplexControl (self, QStyle.ComplexControl cc, QStyleOptionComplex opt, QPoint pt, QWidget widget = None)`
*   `int pixelMetric (self, QStyle.PixelMetric m, QStyleOption option = None, QWidget widget = None)`
*   `polish (self, QWidget widget)`
*   `polish (self, QApplication app)`
*   `QPalette polish (self, QPalette)`
*   `QSize sizeFromContents (self, QStyle.ContentsType ct, QStyleOption opt, QSize contentsSize, QWidget widget = None)`
*   `QIcon standardIconImplementation (self, QStyle.StandardPixmap standardIcon, QStyleOption option = None, QWidget widget = None)`
*   `QPixmap standardPixmap (self, QStyle.StandardPixmap sp, QStyleOption option = None, QWidget widget = None)`
*   `int styleHint (self, QStyle.StyleHint sh, QStyleOption option = None, QWidget widget = None, QStyleHintReturn returnData = None)`
*   `QRect subControlRect (self, QStyle.ComplexControl cc, QStyleOptionComplex opt, QStyle.SubControl sc, QWidget widget = None)`
*   `QRect subElementRect (self, QStyle.SubElement r, QStyleOption opt, QWidget widget = None)`
*   `unpolish (self, QWidget widget)`
*   `unpolish (self, QApplication application)`

* * *

## Detailed Description

该QCommonStyle类封装了图形用户界面的共同外观和感觉。

这个抽象类实现了一些小部件的外观和感觉，是常见的提供和运送作为Qt的一部分的所有图形用户界面风格。

由于QCommonStyle继承[QStyle](qstyle.html)，它的所有功能，在完全记录[QStyle](qstyle.html)文档。

* * *

## Method Documentation

```
QCommonStyle.__init__ (self)
```

构造一个[QCommonStyle](qcommonstyle.html)。

```
QCommonStyle.drawComplexControl (self, QStyle.ComplexControl cc, QStyleOptionComplex opt, QPainter p, QWidget widget = None)
```

从重新实现[QStyle.drawComplexControl](qstyle.html#drawComplexControl)（ ） 。

```
QCommonStyle.drawControl (self, QStyle.ControlElement element, QStyleOption opt, QPainter p, QWidget widget = None)
```

从重新实现[QStyle.drawControl](qstyle.html#drawControl)（ ） 。

```
QCommonStyle.drawPrimitive (self, QStyle.PrimitiveElement pe, QStyleOption opt, QPainter p, QWidget widget = None)
```

从重新实现[QStyle.drawPrimitive](qstyle.html#drawPrimitive)（ ） 。

```
QPixmap QCommonStyle.generatedIconPixmap (self, QIcon.Mode iconMode, QPixmap pixmap, QStyleOption opt)
```

[](qpixmap.html)

[从重新实现](qpixmap.html)[QStyle.generatedIconPixmap](qstyle.html#generatedIconPixmap)（ ） 。

```
QStyle.SubControl QCommonStyle.hitTestComplexControl (self, QStyle.ComplexControl cc, QStyleOptionComplex opt, QPoint pt, QWidget widget = None)
```

[](qstyle.html#SubControl-enum)

[从重新实现](qstyle.html#SubControl-enum)[QStyle.hitTestComplexControl](qstyle.html#hitTestComplexControl)（ ） 。

```
int QCommonStyle.pixelMetric (self, QStyle.PixelMetric m, QStyleOption option = None, QWidget widget = None)
```

从重新实现[QStyle.pixelMetric](qstyle.html#pixelMetric)（ ） 。

```
QCommonStyle.polish (self, QWidget widget)
```

从重新实现[QStyle.polish](qstyle.html#polish-3)（ ） 。

```
QCommonStyle.polish (self, QApplication app)
```

从重新实现[QStyle.polish](qstyle.html#polish-2)（ ） 。

```
QPalette QCommonStyle.polish (self, QPalette)
```

[](qpalette.html)

[从重新实现](qpalette.html)[QStyle.polish](qstyle.html#polish)（ ） 。

```
QSize QCommonStyle.sizeFromContents (self, QStyle.ContentsType ct, QStyleOption opt, QSize contentsSize, QWidget widget = None)
```

[](qsize.html)

[从重新实现](qsize.html)[QStyle.sizeFromContents](qstyle.html#sizeFromContents)（ ） 。

```
QIcon QCommonStyle.standardIconImplementation (self, QStyle.StandardPixmap standardIcon, QStyleOption option = None, QWidget widget = None)
```

[

这种方法也是一个Qt槽与C + +的签名`QIcon standardIconImplementation(QStyle::StandardPixmap,const QStyleOption * = 0,const QWidget * = 0) const`。

](qicon.html)

```
QPixmap QCommonStyle.standardPixmap (self, QStyle.StandardPixmap sp, QStyleOption option = None, QWidget widget = None)
```

[](qpixmap.html)

[从重新实现](qpixmap.html)[QStyle.standardPixmap](index.htm#standardPixmap)（ ） 。

```
int QCommonStyle.styleHint (self, QStyle.StyleHint sh, QStyleOption option = None, QWidget widget = None, QStyleHintReturn returnData = None)
```

从重新实现[QStyle.styleHint](qstyle.html#styleHint)（ ） 。

```
QRect QCommonStyle.subControlRect (self, QStyle.ComplexControl cc, QStyleOptionComplex opt, QStyle.SubControl sc, QWidget widget = None)
```

[](qrect.html)

[从重新实现](qrect.html)[QStyle.subControlRect](qstyle.html#subControlRect)（ ） 。

```
QRect QCommonStyle.subElementRect (self, QStyle.SubElement r, QStyleOption opt, QWidget widget = None)
```

[](qrect.html)

[从重新实现](qrect.html)[QStyle.subElementRect](qstyle.html#subElementRect)（ ） 。

```
QCommonStyle.unpolish (self, QWidget widget)
```

从重新实现[QStyle.unpolish](qstyle.html#unpolish)（ ） 。

```
QCommonStyle.unpolish (self, QApplication application)
```

从重新实现[QStyle.unpolish](qstyle.html#unpolish-2)（ ） 。