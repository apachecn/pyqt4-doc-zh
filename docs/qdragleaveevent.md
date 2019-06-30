# QDragLeaveEvent Class Reference

## [[QtGui](index.htm) module]

该QDragLeaveEvent类提供了发送到窗口小部件时，拖放操作将保留它的事件。[More...](#details)

继承[QEvent](qevent.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDragLeaveEvent)`

* * *

## Detailed Description

该QDragLeaveEvent类提供了发送到窗口小部件时，拖放操作将保留它的事件。

此事件之前总是一[QDragEnterEvent](qdragenterevent.html)和一系列[QDragMoveEvent](qdragmoveevent.html)秒。它不如果一个发送[QDropEvent](qdropevent.html)发送代替。

* * *

## Method Documentation

```
QDragLeaveEvent.__init__ (self)
```

构造一个[QDragLeaveEvent](qdragleaveevent.html)。

**Warning:**不要创建一个[QDragLeaveEvent](qdragleaveevent.html)自己因为这些对象依赖于Qt的内部状态。

```
QDragLeaveEvent.__init__ (self, QDragLeaveEvent)
```