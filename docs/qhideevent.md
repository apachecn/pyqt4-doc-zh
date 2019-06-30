# QHideEvent Class Reference

## [[QtGui](index.htm) module]

该QHideEvent类提供了后一个小部件隐藏它发送的事件。[More...](#details)

继承[QEvent](qevent.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QHideEvent)`

* * *

## Detailed Description

该QHideEvent类提供了后一个小部件隐藏它发送的事件。

此事件之前发送[QWidget.hide](qwidget.html#hide)（ ）返回时，也当一个顶层窗口被隐藏（图标化）的用户。

If [spontaneous](qevent.html#spontaneous)（ ）为真，事件起源于应用程序之外。在这种情况下，用户使用该窗口管理器控制掩藏的窗口中，或者通过图标化的窗口或通过切换到另一个虚拟桌面，其中该窗口是不可见的。该窗口会被隐藏，但不能撤回。如果窗口被图标化，[QWidget.isMinimized](qwidget.html#minimized-prop)（ ）返回True 。

* * *

## Method Documentation

```
QHideEvent.__init__ (self)
```

构造一个[QHideEvent](qhideevent.html)。

```
QHideEvent.__init__ (self, QHideEvent)
```