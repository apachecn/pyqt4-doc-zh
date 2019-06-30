# QDragMoveEvent Class Reference

## [[QtGui](index.htm) module]

QDragMoveEvent所类提供了发送，同时拖拽动作正在进行中的事件。[More...](#details)

继承[QDropEvent](qdropevent.html)。

通过继承[QDragEnterEvent](qdragenterevent.html)。

### Methods

*   `__init__ (self, QPoint pos, Qt.DropActions actions, QMimeData data, Qt.MouseButtons buttons, Qt.KeyboardModifiers modifiers, QEvent.Type type = QEvent.DragMove)`
*   `__init__ (self, QDragMoveEvent)`
*   `accept (self)`
*   `accept (self, QRect r)`
*   `QRect answerRect (self)`
*   `ignore (self)`
*   `ignore (self, QRect r)`

* * *

## Detailed Description

QDragMoveEvent所类提供了发送，同时拖拽动作正在进行中的事件。

一个widget将不断收到拖动移动事件而阻力是它的范围内，如果它接受[drop events](qwidget.html#acceptDrops-prop)和[enter events](qwidget.html#dragEnterEvent)。窗口小部件应检查事件，看看有什么样的数据呢[provides](index.htm#provides)，并调用[accept](qdragmoveevent.html#accept)（ ）函数来接受放置如果合适的。

由所提供的矩形[answerRect](qdragmoveevent.html#answerRect)（）函数可以被用来限制下降到插件的某些部分。例如，我们可以检查矩形是否相交的某子控件，只调用几何[acceptProposedAction()](qdropevent.html#acceptProposedAction)如果是这样的话。

注意，这个类继承了它的大部分功能从[QDropEvent](qdropevent.html)。

* * *

## Method Documentation

```
QDragMoveEvent.__init__ (self, QPoint pos, Qt.DropActions actions, QMimeData data, Qt.MouseButtons buttons, Qt.KeyboardModifiers modifiers, QEvent.Type type = QEvent.DragMove)
```

创建[QDragMoveEvent](qdragmoveevent.html)所需的_type_这表明鼠标在位置_pos_一个小部件内给予。

鼠标和键盘状态由指定_buttons_和_modifiers_和_actions_描述拖放操作是可能的类型。拖动数据传递作为MIME编码的信息_data_。

**Warning:**不要试图创建一个[QDragMoveEvent](qdragmoveevent.html)你自己。这些对象依赖于Qt的内部状态。

```
QDragMoveEvent.__init__ (self, QDragMoveEvent)
```

```
QDragMoveEvent.accept (self)
```

同为接受（ ） ，而且还通知移动未来也将是可以接受的，如果他们留在了_rectangle_在部件上给出。这可以提高性能，但是也可以由底层系统忽略。

如果矩形为空，拖动移动事件会不断发送。如果源是滚动定时器事件，这是很有用的。

```
QDragMoveEvent.accept (self, QRect r)
```

```
QRect QDragMoveEvent.answerRect (self)
```

[

返回如果接受将发生下降的插件的矩形。您可以使用此信息来限制滴在部件上的某些地方。

```
QDragMoveEvent.ignore (self)
```

](qrect.html)

[在接受（常量相反](qrect.html)[QRect](qrect.html)＆ ）函数。内移动_rectangle_是不能接受的，并且会被忽略。

```
QDragMoveEvent.ignore (self, QRect r)
```

这是一个重载函数。

电话[QDropEvent.ignore](qevent.html#ignore)（ ） 。