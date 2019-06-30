# QIconDragEvent Class Reference

## [[QtGui](index.htm) module]

该QIconDragEvent类表示一个主图标拖动已经开始。[More...](#details)

继承[QEvent](qevent.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QIconDragEvent)`

* * *

## Detailed Description

该QIconDragEvent类表示一个主图标拖动已经开始。

图标拖动事件发送到窗口部件时，窗口的主图标已经被拖走。在Mac OS X ，这发生在一个窗口的代理图标拖出标题栏。

这是正常的开始使用拖放在响应此事件。

* * *

## Method Documentation

```
QIconDragEvent.__init__ (self)
```

构造一个图标拖动事件对象的接受标志设置为False 。

**See also** [accept](qevent.html#accept)（ ） 。

```
QIconDragEvent.__init__ (self, QIconDragEvent)
```