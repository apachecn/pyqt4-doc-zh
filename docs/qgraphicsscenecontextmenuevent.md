# QGraphicsSceneContextMenuEvent Class Reference

## [[QtGui](index.htm) module]

该QGraphicsSceneContextMenuEvent类提供在图形视图框架的上下文菜单事件。[More...](#details)

继承[QGraphicsSceneEvent](qgraphicssceneevent.html)。

### Types

*   `enum Reason { Mouse, Keyboard, Other }`

### Methods

*   `Qt.KeyboardModifiers modifiers (self)`
*   `QPointF pos (self)`
*   `Reason reason (self)`
*   `QPointF scenePos (self)`
*   `QPoint screenPos (self)`

* * *

## Detailed Description

该QGraphicsSceneContextMenuEvent类提供在图形视图框架的上下文菜单事件。

A [QContextMenuEvent](qcontextmenuevent.html)通过接收到的[QGraphicsView](qgraphicsview.html)被翻译成QGraphicsSceneContextMenuEvent 。该[QContextMenuEvent.globalPos](qcontextmenuevent.html#globalPos)（ ）被翻译成项目，场景，和屏幕坐标（[pos](qgraphicsscenecontextmenuevent.html#pos)（ ）[scenePos](qgraphicsscenecontextmenuevent.html#scenePos)（）和[screenPos](qgraphicsscenecontextmenuevent.html#screenPos)（））。

* * *

## Type Documentation

```
QGraphicsSceneContextMenuEvent.Reason
```

这个枚举说明为什么上下文事件被发送的原因。

| Constant | Value | Description |
| --- | --- | --- |
| `QGraphicsSceneContextMenuEvent.Mouse` | `0` | 鼠标导致事件被发送。在大多数平台上，这意味着鼠标右按钮被点击。 |
| `QGraphicsSceneContextMenuEvent.Keyboard` | `1` | 键盘导致此事件被发送。在Windows和Mac OS X ，这意味着菜单按钮被按下。 |
| `QGraphicsSceneContextMenuEvent.Other` | `2` | 这次活动是由一些其他的手段（即不通过鼠标或键盘）发出。 |

* * *

## Method Documentation

```
Qt.KeyboardModifiers QGraphicsSceneContextMenuEvent.modifiers (self)
```

[

返回键盘功能键在使用时要求的上下文菜单。

](index.htm)

```
QPointF QGraphicsSceneContextMenuEvent.pos (self)
```

[

返回鼠标光标在项目的位置在请求的上下文菜单的那一刻坐标。

](qpointf.html)

[**See also**](qpointf.html) [scenePos](qgraphicsscenecontextmenuevent.html#scenePos)（）和[screenPos](qgraphicsscenecontextmenuevent.html#screenPos)（ ） 。

```
Reason QGraphicsSceneContextMenuEvent.reason (self)
```

[

返回上下文菜单事件的原因。

](qgraphicsscenecontextmenuevent.html#Reason-enum)

[**See also**](qgraphicsscenecontextmenuevent.html#Reason-enum) [QGraphicsSceneContextMenuEvent.Reason](qgraphicsscenecontextmenuevent.html#Reason-enum)。

```
QPointF QGraphicsSceneContextMenuEvent.scenePos (self)
```

[

返回鼠标光标在现场的位置被要求在上下文菜单中的那一刻坐标。

](qpointf.html)

[**See also**](qpointf.html) [pos](qgraphicsscenecontextmenuevent.html#pos)（）和[screenPos](qgraphicsscenecontextmenuevent.html#screenPos)（ ） 。

```
QPoint QGraphicsSceneContextMenuEvent.screenPos (self)
```

[

返回鼠标光标在屏幕上的位置被请求的上下文菜单的那一刻坐标。

](qpoint.html)

[**See also**](qpoint.html) [pos](qgraphicsscenecontextmenuevent.html#pos)（）和[scenePos](qgraphicsscenecontextmenuevent.html#scenePos)（ ） 。