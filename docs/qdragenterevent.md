# QDragEnterEvent Class Reference

## [[QtGui](index.htm) module]

该QDragEnterEvent类提供被发送到一个widget时，拖放动作进入它的事件。[More...](#details)

继承[QDragMoveEvent](qdragmoveevent.html)。

### Methods

*   `__init__ (self, QPoint pos, Qt.DropActions actions, QMimeData data, Qt.MouseButtons buttons, Qt.KeyboardModifiers modifiers)`
*   `__init__ (self, QDragEnterEvent)`

* * *

## Detailed Description

该QDragEnterEvent类提供被发送到一个widget时，拖放动作进入它的事件。

一个widget必须接受这个事件，以接收[drag move events](qdragmoveevent.html)被发送，而拖放操作正在进行中。拖动输入事件始终紧跟一个拖动移动事件。

QDragEnterEvent继承其大部分的功能从[QDragMoveEvent](qdragmoveevent.html)，这反过来又继承它的大部分功能由[QDropEvent](qdropevent.html)。

* * *

## Method Documentation

```
QDragEnterEvent.__init__ (self, QPoint pos, Qt.DropActions actions, QMimeData data, Qt.MouseButtons buttons, Qt.KeyboardModifiers modifiers)
```

构造一个[QDragEnterEvent](qdragenterevent.html)它表示在给定的输入控件拖拽_point_由指定的鼠标和键盘状态_buttons_和_modifiers_。

拖动数据传递作为MIME编码的信息_data_和指定的_actions_描述的可能类型拖放可以执行的操作。

**Warning:**不要创建一个[QDragEnterEvent](qdragenterevent.html)自己因为这些对象依赖于Qt的内部状态。

```
QDragEnterEvent.__init__ (self, QDragEnterEvent)
```