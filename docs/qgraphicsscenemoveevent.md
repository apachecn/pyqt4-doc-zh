# QGraphicsSceneMoveEvent Class Reference

## [[QtGui](index.htm) module]

该QGraphicsSceneMoveEvent类提供了小部件事件在移动图形视图框架。[More...](#details)

继承[QGraphicsSceneEvent](qgraphicssceneevent.html)。

### Methods

*   `__init__ (self)`
*   `QPointF newPos (self)`
*   `QPointF oldPos (self)`

* * *

## Detailed Description

该QGraphicsSceneMoveEvent类提供了小部件事件在移动图形视图框架。

A [QGraphicsWidget](qgraphicswidget.html)立即发送本身就是一个QGraphicsSceneMoveEvent时，其局部位置的变化。输送被实现为部分[QGraphicsItem.itemChange](qgraphicsitem.html#itemChange)（ ） 。

它类似于[QMoveEvent](qmoveevent.html)，但它的位置，[oldPos](qgraphicsscenemoveevent.html#oldPos)（）和[newPos](qgraphicsscenemoveevent.html#newPos)（ ） ，使用[QPointF](qpointf.html)而不是[QPoint](qpoint.html)。

* * *

## Method Documentation

```
QGraphicsSceneMoveEvent.__init__ (self)
```

构造一个[QGraphicsSceneMoveEvent](qgraphicsscenemoveevent.html)。

```
QPointF QGraphicsSceneMoveEvent.newPos (self)
```

[

返回新的位置（即当前的位置） 。

](qpointf.html)

[**See also**](qpointf.html) [oldPos](qgraphicsscenemoveevent.html#oldPos)（）和[QGraphicsItem.setPos](qgraphicsitem.html#setPos)（ ） 。

```
QPointF QGraphicsSceneMoveEvent.oldPos (self)
```

[

返回旧位置（即位置立刻小部件被移到前） 。

](qpointf.html)

[**See also**](qpointf.html) [newPos](qgraphicsscenemoveevent.html#newPos)（）和[QGraphicsItem.setPos](qgraphicsitem.html#setPos)（ ） 。