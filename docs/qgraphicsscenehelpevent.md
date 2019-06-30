# QGraphicsSceneHelpEvent Class Reference

## [[QtGui](index.htm) module]

该QGraphicsSceneHelpEvent类提供事件时，工具提示请求。[More...](#details)

继承[QGraphicsSceneEvent](qgraphicssceneevent.html)。

### Methods

*   `QPointF scenePos (self)`
*   `QPoint screenPos (self)`

* * *

## Detailed Description

该QGraphicsSceneHelpEvent类提供事件时，工具提示请求。

当[QGraphicsView](qgraphicsview.html)收到[QEvent](qevent.html)类型[QEvent.ToolTip](qevent.html#Type-enum)，它会创建一个QGraphicsSceneHelpEvent ，被转发到了现场。您可以在设置的工具提示[QGraphicsItem](qgraphicsitem.html)同[setToolTip()](qgraphicsitem.html#setToolTip);默认[QGraphicsScene](qgraphicsscene.html)显示的工具提示[QGraphicsItem](qgraphicsitem.html)最高的z值下的鼠标位置（即最上面的项目） 。

[QGraphicsView](qgraphicsview.html)不转发事件时，["What's This"](qwhatsthis.html)和[status tip](qstatustipevent.html)帮助请求。如果你需要，你可以重新实现[QGraphicsView.viewportEvent](qgraphicsview.html#viewportEvent)（ ）和远期[QStatusTipEvent](qstatustipevent.html)事件和[QEvents](qevent.html)类型[QEvent.WhatsThis](qevent.html#Type-enum)到现场。

* * *

## Method Documentation

```
QPointF QGraphicsSceneHelpEvent.scenePos (self)
```

[

返回鼠标光标在现场的位置，此刻的帮助事件被送往坐标。

](qpointf.html)

[**See also**](qpointf.html) [screenPos](qgraphicsscenehelpevent.html#screenPos)（ ） 。

```
QPoint QGraphicsSceneHelpEvent.screenPos (self)
```

[

返回鼠标光标在屏幕上的位置，此刻的帮助下事件被送往坐标。

](qpoint.html)

[**See also**](qpoint.html) [scenePos](qgraphicsscenehelpevent.html#scenePos)（ ） 。