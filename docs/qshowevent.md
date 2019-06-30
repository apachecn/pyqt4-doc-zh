# QShowEvent Class Reference

## [[QtGui](index.htm) module]

该QShowEvent类提供了一个widget显示时发送的事件。[More...](#details)

继承[QEvent](qevent.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QShowEvent)`

* * *

## Detailed Description

该QShowEvent类提供了一个widget显示时发送的事件。

有两种类型的显示事件：由窗口系统（自发）显示事件，以及内部显示事件。自发的（[QEvent.spontaneous](qevent.html#spontaneous)（ ） ）显示事件发送窗口系统显示的窗口刚过，当一个顶层窗口被图标化后会重新显示它们也送。内部展示活动交付前的小部件变为可见。

* * *

## Method Documentation

```
QShowEvent.__init__ (self)
```

构造一个[QShowEvent](qshowevent.html)。

```
QShowEvent.__init__ (self, QShowEvent)
```