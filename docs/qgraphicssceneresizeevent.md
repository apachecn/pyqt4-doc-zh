# QGraphicsSceneResizeEvent Class Reference

## [[QtGui](index.htm) module]

该QGraphicsSceneResizeEvent类提供了在图形窗口小部件大小调整事件视图框架。[More...](#details)

继承[QGraphicsSceneEvent](qgraphicssceneevent.html)。

### Methods

*   `__init__ (self)`
*   `QSizeF newSize (self)`
*   `QSizeF oldSize (self)`

* * *

## Detailed Description

该QGraphicsSceneResizeEvent类提供了在图形窗口小部件大小调整事件视图框架。

A [QGraphicsWidget](qgraphicswidget.html)立即发送本身就是一个QGraphicsSceneResizeEvent时，其几何形状的变化。

它类似于[QResizeEvent](qresizeevent.html)的，但它的尺寸，[oldSize](qgraphicssceneresizeevent.html#oldSize)（）和[newSize](qgraphicssceneresizeevent.html#newSize)（ ） ，使用[QSizeF](qsizef.html)而不是[QSize](qsize.html)。

* * *

## Method Documentation

```
QGraphicsSceneResizeEvent.__init__ (self)
```

构造一个[QGraphicsSceneResizeEvent](qgraphicssceneresizeevent.html)。

```
QSizeF QGraphicsSceneResizeEvent.newSize (self)
```

[

返回新的大小（即电流的大小） 。

](qsizef.html)

[**See also**](qsizef.html) [oldSize](qgraphicssceneresizeevent.html#oldSize)（）和[QGraphicsWidget.resize](qgraphicswidget.html#size-prop)（ ） 。

```
QSizeF QGraphicsSceneResizeEvent.oldSize (self)
```

[

返回旧的大小（即大小紧随小部件调整前） 。

](qsizef.html)

[**See also**](qsizef.html) [newSize](qgraphicssceneresizeevent.html#newSize)（）和[QGraphicsWidget.resize](qgraphicswidget.html#size-prop)（ ） 。