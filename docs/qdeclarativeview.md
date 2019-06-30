# QDeclarativeView Class Reference

## [[QtDeclarative](index.htm) module]

该QDeclarativeView类提供了一个小工具来显示一个Qt声明式的用户界面。[More...](#details)

继承[QGraphicsView](qgraphicsview.html)。

### Types

*   `enum ResizeMode { SizeViewToRootObject, SizeRootObjectToView }`
*   `enum Status { Null, Ready, Loading, Error }`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `__init__ (self, QUrl source, QWidget parent = None)`
*   `QDeclarativeEngine engine (self)`
*   `list-of-QDeclarativeError errors (self)`
*   `bool eventFilter (self, QObject watched, QEvent e)`
*   `QSize initialSize (self)`
*   `paintEvent (self, QPaintEvent event)`
*   `resizeEvent (self, QResizeEvent)`
*   `ResizeMode resizeMode (self)`
*   `QDeclarativeContext rootContext (self)`
*   `QGraphicsObject rootObject (self)`
*   `setResizeMode (self, ResizeMode)`
*   `setSource (self, QUrl)`
*   `QSize sizeHint (self)`
*   `QUrl source (self)`
*   `Status status (self)`
*   `timerEvent (self, QTimerEvent)`

### Qt Signals

*   `void sceneResized (QSize)`
*   `void statusChanged (QDeclarativeView::Status)`

* * *

## Detailed Description

该QDeclarativeView类提供了一个小工具来显示一个Qt声明式的用户界面。

[QDeclarativeItem](qdeclarativeitem.html)对象可以被放置在一个标准[QGraphicsScene](qgraphicsscene.html)并与显示[QGraphicsView](qgraphicsview.html)。 QDeclarativeView是[QGraphicsView](qgraphicsview.html)子类提供方便显示QML文件和QML和C + +的Qt对象之间的连接。

QDeclarativeView提供：

*   Management of [QDeclarativeComponent](qdeclarativecomponent.html) loading and object creation
*   Initialization of [QGraphicsView](qgraphicsview.html) for optimal performance with QML using these settings:
    *   QGraphicsView.setOptimizationFlags([QGraphicsView.DontSavePainterState](qgraphicsview.html#OptimizationFlag-enum))
    *   QGraphicsView.setViewportUpdateMode([QGraphicsView.BoundingRectViewportUpdate](qgraphicsview.html#ViewportUpdateMode-enum))
    *   QGraphicsScene.setItemIndexMethod([QGraphicsScene.NoIndex](qgraphicsscene.html#ItemIndexMethod-enum))
*   Initialization of [QGraphicsView](qgraphicsview.html) for QML key handling using these settings:
    *   [QGraphicsView.viewport](qabstractscrollarea.html#viewport)()-&gt;setFocusPolicy([Qt.NoFocus](qt.html#FocusPolicy-enum))
    *   QGraphicsView.setFocusPolicy([Qt.StrongFocus](qt.html#FocusPolicy-enum))
    *   QGraphicsScene.setStickyFocus(true)

典型的用法：

```
 QDeclarativeView *view = new QDeclarativeView;
 view->setSource([QUrl](qurl.html).fromLocalFile("myqmlfile.qml"));
 view->show();

```

由于QDeclarativeView是[QWidget](qwidget.html)基类时，它可以被用来在显示QML接口[QWidget](qwidget.html)基于GUI的应用程序不使用图形视图框架。

要获得有关加载和执行QML与QDeclarativeView错误，您可以连接到[statusChanged](qdeclarativeview.html#statusChanged)（ ）信号和显示器[QDeclarativeView.Error](qdeclarativeview.html#Status-enum)。这些错误通过可[QDeclarativeView.errors](qdeclarativeview.html#errors)（ ） 。

如果你使用你自己的[QGraphicsScene](qgraphicsscene.html)基于场景QDeclarativeView ，记得让现场的粘对焦模式和设置itemIndexMethod到[QGraphicsScene.NoIndex](qgraphicsscene.html#ItemIndexMethod-enum)。

* * *

## Type Documentation

```
QDeclarativeView.ResizeMode
```

此枚举指定如何调整视图。

| Constant | Value | Description |
| --- | --- | --- |
| `QDeclarativeView.SizeViewToRootObject` | `0` | 该视图调整大小与在QML根项目。 |
| `QDeclarativeView.SizeRootObjectToView` | `1` | 该视图会自动调整根项到视图的大小。 |

```
QDeclarativeView.Status
```

指定的加载状态[QDeclarativeView](qdeclarativeview.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QDeclarativeView.Null` | `0` | This [QDeclarativeView](qdeclarativeview.html)没有源集。 |
| `QDeclarativeView.Ready` | `1` | This [QDeclarativeView](qdeclarativeview.html)已加载并创建了QML组件。 |
| `QDeclarativeView.Loading` | `2` | This [QDeclarativeView](qdeclarativeview.html)正在加载网络数据。 |
| `QDeclarativeView.Error` | `3` | 已发生一个或多个错误。通话[errors](qdeclarativeview.html#errors)（）来检索错误的列表。 |

* * *

## Method Documentation

```
QDeclarativeView.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QDeclarativeView](qdeclarativeview.html)用给定的_parent_。

```
QDeclarativeView.__init__ (self, QUrl source, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QDeclarativeView](qdeclarativeview.html)用给定的QML_source_和_parent_。

```
QDeclarativeEngine QDeclarativeView.engine (self)
```

[](qdeclarativeengine.html)

[返回一个指针](qdeclarativeengine.html)[QDeclarativeEngine](qdeclarativeengine.html)用于实例化QML组件。

```
list-of-QDeclarativeError QDeclarativeView.errors (self)
```

返回的最后一个编译期间发生的错误的列表或创建操作。当状态不是错误，则返回一个空列表。

```
bool QDeclarativeView.eventFilter (self, QObject watched, QEvent e)
```

```
QSize QDeclarativeView.initialSize (self)
```

[

返回根对象的初始大小

```
QDeclarativeView.paintEvent (self, QPaintEvent event)
```

```
QDeclarativeView.resizeEvent (self, QResizeEvent)
```

](qsize.html)

```
ResizeMode QDeclarativeView.resizeMode (self)
```

[](qdeclarativeview.html#ResizeMode-enum)

```
QDeclarativeContext QDeclarativeView.rootContext (self)
```

[](qdeclarativecontext.html)

[该函数返回上下文层次结构的根。每个QML组件实例化的](qdeclarativecontext.html)[QDeclarativeContext](qdeclarativecontext.html)。[QDeclarativeContext](qdeclarativecontext.html)的是将数据传递到QML组件是必不可少的。在QML中，上下文是分级排列并且这种层次结构是由管理[QDeclarativeEngine](qdeclarativeengine.html)。

```
QGraphicsObject QDeclarativeView.rootObject (self)
```

[](qgraphicsobject.html)

[返回视图的根](qgraphicsobject.html)[item](qgraphicsobject.html)。

```
QDeclarativeView.setResizeMode (self, ResizeMode)
```

```
QDeclarativeView.setSource (self, QUrl)
```

```
QSize QDeclarativeView.sizeHint (self)
```

[](qsize.html)

```
QUrl QDeclarativeView.source (self)
```

[](qurl.html)

```
Status QDeclarativeView.status (self)
```

[

```
QDeclarativeView.timerEvent (self, QTimerEvent)
```

* * *

## Qt Signal Documentation

```
void sceneResized (QSize)
```

这是该信号的默认超载。

当视图改变到这一信号被发射_size_。

```
void statusChanged (QDeclarativeView::Status)
```

这是该信号的默认超载。

这个信号被发射时，该组件的电流_status_变化。

](qdeclarativeview.html#Status-enum)