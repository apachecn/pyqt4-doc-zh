# QResizeEvent Class Reference

## [[QtGui](index.htm) module]

该QResizeEvent类包含事件参数的调整大小事件。[More...](#details)

继承[QEvent](qevent.html)。

### Methods

*   `__init__ (self, QSize size, QSize oldSize)`
*   `__init__ (self, QResizeEvent)`
*   `QSize oldSize (self)`
*   `QSize size (self)`

* * *

## Detailed Description

该QResizeEvent类包含事件参数的调整大小事件。

resize事件被发送到已经调整小部件。

该事件处理程序[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ）接收调整事件。

* * *

## Method Documentation

```
QResizeEvent.__init__ (self, QSize size, QSize oldSize)
```

构造一个resize事件与广大新老部件尺寸，_size_和_oldSize_分别。

```
QResizeEvent.__init__ (self, QResizeEvent)
```

```
QSize QResizeEvent.oldSize (self)
```

[

返回widget的老大小。

](qsize.html)

```
QSize QResizeEvent.size (self)
```

[](qsize.html)

[返回该窗口小部件的新的大小。这是相同的](qsize.html)[QWidget.size](qwidget.html#size-prop)（ ） 。