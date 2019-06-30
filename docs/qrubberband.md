# QRubberBand Class Reference

## [[QtGui](index.htm) module]

该QRubberBand类提供了一个矩形或线条，可以显示一个选择或边界。[More...](#details)

继承[QWidget](qwidget.html)。

### Types

*   `enum Shape { Line, Rectangle }`

### Methods

*   `__init__ (self, Shape, QWidget parent = None)`
*   `changeEvent (self, QEvent)`
*   `bool event (self, QEvent e)`
*   `initStyleOption (self, QStyleOptionRubberBand option)`
*   `move (self, QPoint p)`
*   `move (self, int ax, int ay)`
*   `moveEvent (self, QMoveEvent)`
*   `paintEvent (self, QPaintEvent)`
*   `resize (self, int w, int h)`
*   `resize (self, QSize s)`
*   `resizeEvent (self, QResizeEvent)`
*   `setGeometry (self, QRect r)`
*   `setGeometry (self, int ax, int ay, int aw, int ah)`
*   `Shape shape (self)`
*   `showEvent (self, QShowEvent)`

* * *

## Detailed Description

该QRubberBand类提供了一个矩形或线条，可以显示一个选择或边界。

一种橡胶带通常用来显示一个新的边界区域（如在一个[QSplitter](qsplitter.html)或[QDockWidget](qdockwidget.html)那是出坞） 。历史上使用这种已实施[QPainter](qpainter.html)和XOR ，但这种方法并不总是正确的，因为渲染可能发生在下面的橡皮筋​​窗口工作，但橡皮筋之前已经被“抹掉” 。

每当你需要渲染围绕一个给定区域橡皮筋（或代表一行），你可以创建一个QRubberBand ，然后调用[setGeometry](qrubberband.html#setGeometry)（ ）[move](qrubberband.html#move)（）或[resize](qrubberband.html#resize)（）来定位并调整其大小。一个常见的模式是这样做与鼠标事件一起使用。例如：

```
 void Widget.mousePressEvent([QMouseEvent](qmouseevent.html) *event)
 {
     origin = event->pos();
     if (!rubberBand)
         rubberBand = new QRubberBand(QRubberBand.Rectangle, this);
     rubberBand->setGeometry([QRect](qrect.html)(origin, [QSize](qsize.html)()));
     rubberBand->show();
 }

 void Widget.mouseMoveEvent([QMouseEvent](qmouseevent.html) *event)
 {
     rubberBand->setGeometry([QRect](qrect.html)(origin, event->pos()).normalized());
 }

 void Widget.mouseReleaseEvent([QMouseEvent](qmouseevent.html) *event)
 {
     rubberBand->hide();
     // determine selection, for example using QRect.intersects()
     // and QRect.contains().
 }

```

如果你传递一个父QRubberBand的构造函数，橡皮筋将只显示内部其父，但停留在其他的子控件的顶部。如果没有父母传递， QRubberBand将作为一个顶级窗口部件。

Call [show](qwidget.html#show)（）以使橡胶带清晰可见;也当橡胶带不是顶层。隐藏或销毁的部件将使得橡胶带消失。橡胶带可以是一个[Rectangle](qrubberband.html#Shape-enum)或[Line](qrubberband.html#Shape-enum)（垂直或水平） ，这取决于[shape](qrubberband.html#shape)（ ）获给予该建造。

* * *

## Type Documentation

```
QRubberBand.Shape
```

此枚举指定什么形状的[QRubberBand](qrubberband.html)应该有。这是向下传递到样式系统的绘图提示，并且可以由每个被解释[QStyle](qstyle.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QRubberBand.Line` | `0` | A [QRubberBand](qrubberband.html)可以代表一个垂直或水平线。几何中仍给予[rect](qwidget.html#rect-prop)（ ）而行，将填补在大多数款式给定的几何形状。 |
| `QRubberBand.Rectangle` | `1` | A [QRubberBand](qrubberband.html)可以表示一个矩形。有些款式会将此解释为填充（通常半透明）长方形或矩形轮廓。 |

* * *

## Method Documentation

```
QRubberBand.__init__ (self, Shape, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造形状的橡皮筋_s_，与父_p_。

默认情况下，一个长方形的橡胶带（_s_ is `Rectangle`）将使用的掩模，使该矩形的小边界是所有可见。有些款式（例如，原生的Mac OS X ）将改变这一点，并调用[QWidget.setWindowOpacity](qwidget.html#windowOpacity-prop)（ ）方法使一个半透明填充选择矩形。

```
QRubberBand.changeEvent (self, QEvent)
```

从重新实现[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
bool QRubberBand.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QRubberBand.initStyleOption (self, QStyleOptionRubberBand option)
```

初始化_option_与其它的值[QRubberBand](qrubberband.html)。当他们需要一个这种方法是有用的子类[QStyleOptionRubberBand](qstyleoptionrubberband.html)，但不希望在所有的信息填写自己。

**See also** [QStyleOption.initFrom](qstyleoption.html#initFrom)（ ） 。

```
QRubberBand.move (self, QPoint p)
```

移动橡皮筋到点（_x_，_y_） 。

**See also** [resize](qrubberband.html#resize)（ ） 。

```
QRubberBand.move (self, int ax, int ay)
```

这是一个重载函数。

移动橡皮筋指向_p_。

**See also** [resize](qrubberband.html#resize)（ ） 。

```
QRubberBand.moveEvent (self, QMoveEvent)
```

从重新实现[QWidget.moveEvent](qwidget.html#moveEvent)（ ） 。

```
QRubberBand.paintEvent (self, QPaintEvent)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QRubberBand.resize (self, int w, int h)
```

调整大小的橡皮筋​​，使得其宽度为_width_，它的高度是_height_。

**See also** [move](qrubberband.html#move)（ ） 。

```
QRubberBand.resize (self, QSize s)
```

这是一个重载函数。

调整大小的橡皮筋​​，使新的大小是_size_。

**See also** [move](qrubberband.html#move)（ ） 。

```
QRubberBand.resizeEvent (self, QResizeEvent)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
QRubberBand.setGeometry (self, QRect r)
```

设置橡皮筋的几何_rect_，它的父窗口部件的坐标系中指定。

**See also** [QWidget.geometry](qwidget.html#geometry-prop)。

```
QRubberBand.setGeometry (self, int ax, int ay, int aw, int ah)
```

这是一个重载函数。

设置橡皮的几何形状，其左上角位于该点的矩形（_x_，_y_）中，用由指定的尺寸_width_和_height_。几何体指定的父窗口部件的坐标系中。

```
Shape QRubberBand.shape (self)
```

[

返回此橡皮筋的形状。形状只能在构造设置。

```
QRubberBand.showEvent (self, QShowEvent)
```

](qrubberband.html#Shape-enum)

[从重新实现](qrubberband.html#Shape-enum)[QWidget.showEvent](qwidget.html#showEvent)（ ） 。