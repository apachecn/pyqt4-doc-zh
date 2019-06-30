# QGraphicsSceneEvent Class Reference

## [[QtGui](index.htm) module]

该QGraphicsSceneEvent类提供了一个基类，所有图形查看相关事件。[More...](#details)

继承[QEvent](qevent.html)。

通过继承[QGraphicsSceneContextMenuEvent](qgraphicsscenecontextmenuevent.html)，[QGraphicsSceneDragDropEvent](qgraphicsscenedragdropevent.html)，[QGraphicsSceneHelpEvent](qgraphicsscenehelpevent.html)，[QGraphicsSceneHoverEvent](qgraphicsscenehoverevent.html)，[QGraphicsSceneMouseEvent](qgraphicsscenemouseevent.html)，[QGraphicsSceneMoveEvent](qgraphicsscenemoveevent.html)，[QGraphicsSceneResizeEvent](qgraphicssceneresizeevent.html)和[QGraphicsSceneWheelEvent](qgraphicsscenewheelevent.html)。

### Methods

*   `setWidget (self, QWidget widget)`
*   `QWidget widget (self)`

* * *

## Detailed Description

该QGraphicsSceneEvent类提供了一个基类，所有图形查看相关事件。

当[QGraphicsView](qgraphicsview.html)接收Qt的鼠标，键盘和拖放事件（[QMouseEvent](qmouseevent.html)，[QKeyEvent](qkeyevent.html)， QDragEvent等），它转换成QGraphicsSceneEvent子类的实例，并将其转发到[QGraphicsScene](qgraphicsscene.html)它显示。那么现场的事件转发到相关项目。

例如，当一个[QGraphicsView](qgraphicsview.html)收到[QMouseEvent](qmouseevent.html)类型MousePress作为一个用户点击一个响应，该视图发送一个[QGraphicsSceneMouseEvent](qgraphicsscenemouseevent.html)类型[GraphicsSceneMousePress](qevent.html#Type-enum)到底层[QGraphicsScene](qgraphicsscene.html)通过其[mousePressEvent()](qgraphicsscene.html#mousePressEvent)功能。默认[QGraphicsScene.mousePressEvent](qgraphicsscene.html#mousePressEvent)（）实现确定哪些项目被点击和事件转发到[QGraphicsItem.mousePressEvent](qgraphicsitem.html#mousePressEvent)（ ） 。

子类如[QGraphicsSceneMouseEvent](qgraphicsscenemouseevent.html)和[QGraphicsSceneContextMenuEvent](qgraphicsscenecontextmenuevent.html)从原来提供的坐标[QEvent](qevent.html)在屏幕上，场景和物品坐标（见[screenPos()](qgraphicsscenemouseevent.html#screenPos)，[scenePos()](qgraphicsscenemouseevent.html#scenePos)和[pos()](qgraphicsscenemouseevent.html#pos)） 。该项目的坐标通过设置[QGraphicsScene](qgraphicsscene.html)面前的事件转发到事件到[QGraphicsItem](qgraphicsitem.html)。鼠标事件也增加了可能性，从视图收到的最后一个事件获取的坐标（见[lastScreenPos()](qgraphicsscenemouseevent.html#lastScreenPos)，[lastScenePos()](qgraphicsscenemouseevent.html#lastScenePos)和[lastPos()](qgraphicsscenemouseevent.html#lastPos)） 。

* * *

## Method Documentation

```
QGraphicsSceneEvent.setWidget (self, QWidget widget)
```

```
QWidget QGraphicsSceneEvent.widget (self)
```

[

返回小部件产生事件，或者0，如果事件从另一个应用程序的起源。

](qwidget.html)