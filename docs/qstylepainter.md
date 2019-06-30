# QStylePainter Class Reference

## [[QtGui](index.htm) module]

该QStylePainter类是一个方便的类用于绘图[QStyle](qstyle.html)窗口小部件中的元素。[More...](#details)

继承[QPainter](qpainter.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QWidget w)`
*   `__init__ (self, QPaintDevice pd, QWidget w)`
*   `bool begin (self, QWidget w)`
*   `bool begin (self, QPaintDevice pd, QWidget w)`
*   `drawComplexControl (self, QStyle.ComplexControl cc, QStyleOptionComplex opt)`
*   `drawControl (self, QStyle.ControlElement ce, QStyleOption opt)`
*   `drawItemPixmap (self, QRect r, int flags, QPixmap pixmap)`
*   `drawItemText (self, QRect rect, int flags, QPalette pal, bool enabled, QString text, QPalette.ColorRole textRole = QPalette.NoRole)`
*   `drawPrimitive (self, QStyle.PrimitiveElement pe, QStyleOption opt)`
*   `QStyle style (self)`

* * *

## Detailed Description

该QStylePainter类是一个方便的类用于绘图[QStyle](qstyle.html)窗口小部件中的元素。

QStylePainter延伸[QPainter](qpainter.html)用一组高级别`draw...()`之上实现的功能[QStyle](qstyle.html)的API 。使用QStylePainter的优点在于，在参数列表获得相当短。而一个[QStyle](qstyle.html)对象必须能够借鉴使用任何画家的任何小部件（因为应用程序通常有一个[QStyle](qstyle.html)对象由所有部件共享） ，一个QStylePainter与一个插件初始化，而无需指定[QWidget](qwidget.html)时，[QPainter](qpainter.html)和[QStyle](qstyle.html)对于每个函数调用。

使用示例[QStyle](qstyle.html)直接：

```
 void MyWidget.paintEvent([QPaintEvent](qpaintevent.html) * /* event */)
 {
     [QPainter](qpainter.html) painter(this);

     [QStyleOptionFocusRect](qstyleoptionfocusrect.html) option;
     option.initFrom(this);
     option.backgroundColor = palette().color([QPalette](qpalette.html).Background);

     style()->drawPrimitive([QStyle](qstyle.html).PE_FrameFocusRect, &option, &painter, this);
 }

```

例如，使用QStylePainter ：

```
 void MyWidget.paintEvent([QPaintEvent](qpaintevent.html) * /* event */)
 {
     QStylePainter painter(this);

     [QStyleOptionFocusRect](qstyleoptionfocusrect.html) option;
     option.initFrom(this);
     option.backgroundColor = palette().color([QPalette](qpalette.html).Background);

     painter.drawPrimitive([QStyle](qstyle.html).PE_FrameFocusRect, option);
 }

```

* * *

## Method Documentation

```
QStylePainter.__init__ (self)
```

构造一个[QStylePainter](qstylepainter.html)。

```
QStylePainter.__init__ (self, QWidget w)
```

构建[QStylePainter](qstylepainter.html)使用小工具_widget_它的漆设备。

```
QStylePainter.__init__ (self, QPaintDevice pd, QWidget w)
```

构建[QStylePainter](qstylepainter.html) using _pd_其油漆设备，然后从属性_widget_。

```
bool QStylePainter.begin (self, QWidget w)
```

开始绘制操作上的指定_widget_。返回True如果画家是准备使用，否则返回False 。

这是通过采用一个构造函数自动调用[QWidget](qwidget.html)。

```
bool QStylePainter.begin (self, QPaintDevice pd, QWidget w)
```

这是一个重载函数。

开始绘制操作绘图设备上_pd_就好像它是_widget_。

这是通过采用一个构造函数自动调用[QPaintDevice](qpaintdevice.html)和[QWidget](qwidget.html)。

```
QStylePainter.drawComplexControl (self, QStyle.ComplexControl cc, QStyleOptionComplex opt)
```

使用widget的样式来绘制复杂的控制_cc_由指定的[QStyleOptionComplex](qstyleoptioncomplex.html) _option_。

**See also** [QStyle.drawComplexControl](qstyle.html#drawComplexControl)（ ） 。

```
QStylePainter.drawControl (self, QStyle.ControlElement ce, QStyleOption opt)
```

使用widget的样式来绘制控制元件_ce_通过指定[QStyleOption](qstyleoption.html) _option_。

**See also** [QStyle.drawControl](qstyle.html#drawControl)（ ） 。

```
QStylePainter.drawItemPixmap (self, QRect r, int flags, QPixmap pixmap)
```

绘制_pixmap_在矩形_rect_。像素图是根据对准的_flags_。

**See also** [QStyle.drawItemPixmap](qstyle.html#drawItemPixmap)（）和[Qt.Alignment](qt.html#AlignmentFlag-enum)。

```
QStylePainter.drawItemText (self, QRect rect, int flags, QPalette pal, bool enabled, QString text, QPalette.ColorRole textRole = QPalette.NoRole)
```

绘制_text_在矩形_rect_和调色板_pal_。该文本是根据对齐和包裹_flags_。

笔的颜色是指定_textRole_。该_enabled_布尔值指示是否该项目被启用，当重新实现这个布尔应该如何影响该项目的结论。

**See also** [QStyle.drawItemText](qstyle.html#drawItemText)（）和[Qt.Alignment](qt.html#AlignmentFlag-enum)。

```
QStylePainter.drawPrimitive (self, QStyle.PrimitiveElement pe, QStyleOption opt)
```

使用widget的样式来绘制一个本原元_pe_通过指定[QStyleOption](qstyleoption.html) _option_。

**See also** [QStyle.drawPrimitive](qstyle.html#drawPrimitive)（ ） 。

```
QStyle QStylePainter.style (self)
```

[](qstyle.html)

[返回所使用的当前样式](qstyle.html)[QStylePainter](qstylepainter.html)。