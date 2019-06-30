# QSizeGrip Class Reference

## [[QtGui](index.htm) module]

该QSizeGrip类提供了一个大小调整手柄大小调整顶层窗口。[More...](#details)

继承[QWidget](qwidget.html)。

### Methods

*   `__init__ (self, QWidget parent)`
*   `bool event (self, QEvent)`
*   `bool eventFilter (self, QObject, QEvent)`
*   `hideEvent (self, QHideEvent hideEvent)`
*   `mouseMoveEvent (self, QMouseEvent)`
*   `mousePressEvent (self, QMouseEvent)`
*   `mouseReleaseEvent (self, QMouseEvent mouseEvent)`
*   `moveEvent (self, QMoveEvent moveEvent)`
*   `paintEvent (self, QPaintEvent)`
*   `setVisible (self, bool)`
*   `showEvent (self, QShowEvent showEvent)`
*   `QSize sizeHint (self)`

* * *

## Detailed Description

该QSizeGrip类提供了一个大小调整手柄大小调整顶层窗口。

这个小工具的工作方式类似于标准的Windows调整大小手柄。在X11版本的大小调整手柄通常的工作方式不同从所提供的系统，如果X11窗口管理器不支持必要的现代后ICCCM规范之一。

把这个小工具的任何地方在一个widget树，用户可以用它来调整顶层窗口或任何部件与[Qt.SubWindow](qt.html#WindowType-enum)标志设置。一般情况下，这应该是在右下角的角落。需要注意的是[QStatusBar](qstatusbar.html)已经使用这个小工具，所以如果你有一个状态栏（例如，你使用[QMainWindow](qmainwindow.html)） ，那么你就不需要显式地使用这个小工具。

在某些平台上的大小手柄自动隐藏自己当窗口显示全屏或最大化。

| ![Screenshot of a Plastique style size grip](../img/plastique-sizegrip.png) | A size grip widget at the bottom-right corner of a main window, shown in the [Plastique widget style](index.htm). |

该QSizeGrip类继承[QWidget](qwidget.html)并重新实现了[mousePressEvent()](qwidget.html#mousePressEvent)和[mouseMoveEvent()](qwidget.html#mouseMoveEvent)功能特点调整大小的功能，而[paintEvent()](qwidget.html#paintEvent)功能呈现大小手柄部件。

* * *

## Method Documentation

```
QSizeGrip.__init__ (self, QWidget parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个调整大小角落的特定子widget_parent_。

```
bool QSizeGrip.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
bool QSizeGrip.eventFilter (self, QObject, QEvent)
```

从重新实现[QObject.eventFilter](qobject.html#eventFilter)（ ） 。

```
QSizeGrip.hideEvent (self, QHideEvent hideEvent)
```

从重新实现[QWidget.hideEvent](qwidget.html#hideEvent)（ ） 。

```
QSizeGrip.mouseMoveEvent (self, QMouseEvent)
```

从重新实现[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

重新调整包含此插件的顶级窗口部件。鼠标移动事件传递的_event_参数。

```
QSizeGrip.mousePressEvent (self, QMouseEvent)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

接收到鼠标按下的事件窗口小部件，和素数的大小调整操作。鼠标按下事件传递的_event_参数。

```
QSizeGrip.mouseReleaseEvent (self, QMouseEvent mouseEvent)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

```
QSizeGrip.moveEvent (self, QMoveEvent moveEvent)
```

从重新实现[QWidget.moveEvent](qwidget.html#moveEvent)（ ） 。

```
QSizeGrip.paintEvent (self, QPaintEvent)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

绘制调整大小的抓地力。

调整握把通常呈现为在右下角的小斜线纹理的线条。该漆事件被传递的_event_参数。

```
QSizeGrip.setVisible (self, bool)
```

从重新实现[QWidget.setVisible](qwidget.html#visible-prop)（ ） 。

```
QSizeGrip.showEvent (self, QShowEvent showEvent)
```

从重新实现[QWidget.showEvent](qwidget.html#showEvent)（ ） 。

```
QSize QSizeGrip.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。