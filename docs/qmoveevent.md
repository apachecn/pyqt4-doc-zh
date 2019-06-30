# QMoveEvent Class Reference

## [[QtGui](index.htm) module]

该QMoveEvent类包含事件参数的移动事件。[More...](#details)

继承[QEvent](qevent.html)。

### Methods

*   `__init__ (self, QPoint pos, QPoint oldPos)`
*   `__init__ (self, QMoveEvent)`
*   `QPoint oldPos (self)`
*   `QPoint pos (self)`

* * *

## Detailed Description

该QMoveEvent类包含事件参数的移动事件。

移动事件被发送到已经被转移到相对于其母公司新位置的部件。

该事件处理程序[QWidget.moveEvent](qwidget.html#moveEvent)（ ）接收移动事件。

* * *

## Method Documentation

```
QMoveEvent.__init__ (self, QPoint pos, QPoint oldPos)
```

构造一个move事件与广大新老部件的位置，_pos_和_oldPos_分别。

```
QMoveEvent.__init__ (self, QMoveEvent)
```

```
QPoint QMoveEvent.oldPos (self)
```

[

返回widget的老位置。

](qpoint.html)

```
QPoint QMoveEvent.pos (self)
```

[

返回widget的新位置。这不包括对顶级窗口部件的窗口框架。

](qpoint.html)