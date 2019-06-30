# QGraphicsSceneHoverEvent Class Reference

## [[QtGui](index.htm) module]

该QGraphicsSceneHoverEvent类提供悬停在图形事件视图框架。[More...](#details)

继承[QGraphicsSceneEvent](qgraphicssceneevent.html)。

### Methods

*   `QPointF lastPos (self)`
*   `QPointF lastScenePos (self)`
*   `QPoint lastScreenPos (self)`
*   `Qt.KeyboardModifiers modifiers (self)`
*   `QPointF pos (self)`
*   `QPointF scenePos (self)`
*   `QPoint screenPos (self)`

* * *

## Detailed Description

该QGraphicsSceneHoverEvent类提供悬停在图形事件视图框架。

当[QGraphicsView](qgraphicsview.html)收到[QHoverEvent](qhoverevent.html)事件，它翻译成QGraphicsSceneHoverEvent 。然后，此事件转发到[QGraphicsScene](qgraphicsscene.html)与视图相关联。

* * *

## Method Documentation

```
QPointF QGraphicsSceneHoverEvent.lastPos (self)
```

[

返回项的坐标最后记录的鼠标光标位置。

此功能被引入Qt的4.4 。

](qpointf.html)

[**See also**](qpointf.html) [lastScenePos](qgraphicsscenehoverevent.html#lastScenePos)（ ）[lastScreenPos](qgraphicsscenehoverevent.html#lastScreenPos)（）和[pos](qgraphicsscenehoverevent.html#pos)（ ） 。

```
QPointF QGraphicsSceneHoverEvent.lastScenePos (self)
```

[

返回最后一个记录，现场以前的鼠标或悬停事件所收到的资料，创建场景时鼠标光标位置坐标的坐标。

此功能被引入Qt的4.4 。

](qpointf.html)

[**See also**](qpointf.html) [lastPos](qgraphicsscenehoverevent.html#lastPos)（ ）[lastScreenPos](qgraphicsscenehoverevent.html#lastScreenPos)（）和[scenePos](qgraphicsscenehoverevent.html#scenePos)（ ） 。

```
QPoint QGraphicsSceneHoverEvent.lastScreenPos (self)
```

[

返回屏幕坐标的最后一个记录鼠标的光标位置。最后记录的位置是由创建该事件的观点获得了以前的鼠标或悬停事件的位置。

此功能被引入Qt的4.4 。

](qpoint.html)

[**See also**](qpoint.html) [lastPos](qgraphicsscenehoverevent.html#lastPos)（ ）[lastScenePos](qgraphicsscenehoverevent.html#lastScenePos)（）和[screenPos](qgraphicsscenehoverevent.html#screenPos)（ ） 。

```
Qt.KeyboardModifiers QGraphicsSceneHoverEvent.modifiers (self)
```

[

返回键盘功能键的时刻悬停事件被发送。

此功能被引入Qt的4.4 。

](index.htm)

```
QPointF QGraphicsSceneHoverEvent.pos (self)
```

[

返回鼠标光标在项目的位置，此刻的悬停事件被送往坐标。

](qpointf.html)

[**See also**](qpointf.html) [scenePos](qgraphicsscenehoverevent.html#scenePos)（）和[screenPos](qgraphicsscenehoverevent.html#screenPos)（ ） 。

```
QPointF QGraphicsSceneHoverEvent.scenePos (self)
```

[

返回鼠标光标在现场的位置，此刻的悬停事件被送往坐标。

](qpointf.html)

[**See also**](qpointf.html) [pos](qgraphicsscenehoverevent.html#pos)（）和[screenPos](qgraphicsscenehoverevent.html#screenPos)（ ） 。

```
QPoint QGraphicsSceneHoverEvent.screenPos (self)
```

[

返回鼠标光标在屏幕上的位置，此刻的悬停事件被送往坐标。

](qpoint.html)

[**See also**](qpoint.html) [pos](qgraphicsscenehoverevent.html#pos)（）和[scenePos](qgraphicsscenehoverevent.html#scenePos)（ ） 。