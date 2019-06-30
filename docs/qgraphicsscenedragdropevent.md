# QGraphicsSceneDragDropEvent Class Reference

## [[QtGui](index.htm) module]

该QGraphicsSceneDragDropEvent类提供了拖放在图形视图框架的事件。[More...](#details)

继承[QGraphicsSceneEvent](qgraphicssceneevent.html)。

### Methods

*   `acceptProposedAction (self)`
*   `Qt.MouseButtons buttons (self)`
*   `Qt.DropAction dropAction (self)`
*   `QMimeData mimeData (self)`
*   `Qt.KeyboardModifiers modifiers (self)`
*   `QPointF pos (self)`
*   `Qt.DropActions possibleActions (self)`
*   `Qt.DropAction proposedAction (self)`
*   `QPointF scenePos (self)`
*   `QPoint screenPos (self)`
*   `setDropAction (self, Qt.DropAction action)`
*   `QWidget source (self)`

* * *

## Detailed Description

该QGraphicsSceneDragDropEvent类提供了拖放在图形视图框架的事件。

[QGraphicsView](qgraphicsview.html)继承提供的拖放功能[QWidget](qwidget.html)。当它收到一个拖放事件，它转换到一个QGraphicsSceneDragDropEvent 。

类型QGraphicsSceneDragDropEvent店活动[GraphicsSceneDragEnter](qevent.html#Type-enum)，[GraphicsSceneDragLeave](qevent.html#Type-enum)，[GraphicsSceneDragMove](qevent.html#Type-enum)或[GraphicsSceneDrop](qevent.html#Type-enum)。

QGraphicsSceneDragDropEvent包含鼠标光标的位置在这两个项目，场景，和屏幕坐标，这可以检索与[pos](qgraphicsscenedragdropevent.html#pos)（ ）[scenePos](qgraphicsscenedragdropevent.html#scenePos)（）和[screenPos](qgraphicsscenedragdropevent.html#screenPos)（ ） 。

现场将事件发送到所述第一[QGraphicsItem](qgraphicsitem.html)接受滴鼠标光标下，一个图形项目被设定为接受滴用[setAcceptDrops()](qgraphicsitem.html#setAcceptDrops)。

* * *

## Method Documentation

```
QGraphicsSceneDragDropEvent.acceptProposedAction (self)
```

设置为接受所建议的行动，即降操作设置为所建议的行动。这等于：

```
 setDropAction(proposedAction());

```

使用此功能时，应该不叫`accept()`。

**See also** [dropAction](qgraphicsscenedragdropevent.html#dropAction)（ ）[setDropAction](qgraphicsscenedragdropevent.html#setDropAction)（）和[proposedAction](qgraphicsscenedragdropevent.html#proposedAction)（ ） 。

```
Qt.MouseButtons QGraphicsSceneDragDropEvent.buttons (self)
```

[](index.htm)

[返回](index.htm)[Qt.MouseButtons](qt.html#MouseButton-enum)值，表示该按钮被时生成此鼠标事件鼠标按下。

**See also** [Qt.MouseButtons](qt.html#MouseButton-enum)。

```
Qt.DropAction QGraphicsSceneDragDropEvent.dropAction (self)
```

[](qt.html#DropAction-enum)

[返回此拖放进行的操作。这应该由液滴的接收器被设置，并通过返回](qt.html#DropAction-enum)[QDrag.exec](qdrag.html#exec)（ ） 。

**See also** [setDropAction](qgraphicsscenedragdropevent.html#setDropAction)（）和[acceptProposedAction](qgraphicsscenedragdropevent.html#acceptProposedAction)（ ） 。

```
QMimeData QGraphicsSceneDragDropEvent.mimeData (self)
```

[

该函数返回事件的MIME数据。

](qmimedata.html)

```
Qt.KeyboardModifiers QGraphicsSceneDragDropEvent.modifiers (self)
```

[

返回拖放事件被创建时所按下键盘功能键。

](index.htm)

[**See also**](index.htm) [Qt.KeyboardModifiers](qt.html#KeyboardModifier-enum)。

```
QPointF QGraphicsSceneDragDropEvent.pos (self)
```

[

返回到发送的事件查看事件相对的鼠标位置。

](qpointf.html)

[**See also**](qpointf.html) [QGraphicsView](qgraphicsview.html)，[screenPos](qgraphicsscenedragdropevent.html#screenPos)（）和[scenePos](qgraphicsscenedragdropevent.html#scenePos)（ ） 。

```
Qt.DropActions QGraphicsSceneDragDropEvent.possibleActions (self)
```

[

返回的可能的放置动作的拖放会导致英寸

](index.htm)

[**See also**](index.htm) [Qt.DropActions](qt.html#DropAction-enum)。

```
Qt.DropAction QGraphicsSceneDragDropEvent.proposedAction (self)
```

[

返回最好建议的下拉作用，即， 。所定义的动作必须为可能采取的行动之一`possibleActions()`。

](qt.html#DropAction-enum)

[**See also**](qt.html#DropAction-enum) [Qt.DropAction](qt.html#DropAction-enum)和[possibleActions](qgraphicsscenedragdropevent.html#possibleActions)（ ） 。

```
QPointF QGraphicsSceneDragDropEvent.scenePos (self)
```

[

返回鼠标在场景坐标中的位置。

](qpointf.html)

[**See also**](qpointf.html) [pos](qgraphicsscenedragdropevent.html#pos)（）和[screenPos](qgraphicsscenedragdropevent.html#screenPos)（ ） 。

```
QPoint QGraphicsSceneDragDropEvent.screenPos (self)
```

[

返回到屏幕上的鼠标相对的位置。

](qpoint.html)

[**See also**](qpoint.html) [pos](qgraphicsscenedragdropevent.html#pos)（）和[scenePos](qgraphicsscenedragdropevent.html#scenePos)（ ） 。

```
QGraphicsSceneDragDropEvent.setDropAction (self, Qt.DropAction action)
```

此功能可下拉的接收器设置进行到下拉动作_action_，这应该是一个[possible actions](qgraphicsscenedragdropevent.html#possibleActions)。通话`accept()`在代替`acceptProposedAction()`如果您使用此功能。

**See also** [dropAction](qgraphicsscenedragdropevent.html#dropAction)（ ）[accept](qevent.html#accept)（）和[possibleActions](qgraphicsscenedragdropevent.html#possibleActions)（ ） 。

```
QWidget QGraphicsSceneDragDropEvent.source (self)
```

[](qwidget.html)

[该函数返回](qwidget.html)[QGraphicsView](qgraphicsview.html)创建该[QGraphicsSceneDragDropEvent](qgraphicsscenedragdropevent.html)。