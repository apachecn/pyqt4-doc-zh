# QCloseEvent Class Reference

## [[QtGui](index.htm) module]

该QCloseEvent类包含描述一个close事件的参数。[More...](#details)

继承[QEvent](qevent.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QCloseEvent)`

* * *

## Detailed Description

该QCloseEvent类包含描述一个close事件的参数。

关闭事件发送到窗口部件，用户要关闭，通常是通过从窗口菜单中选择“关闭” ，或按一下**X**标题栏按钮。当你调用他们还派出[QWidget.close](qwidget.html#close)（ ）以编程方式关闭一个widget 。

关闭事件包含一个标志，指示接收者是否希望小部件被关闭与否。当一个组件的所有close事件，它是隐藏的（并销毁，如果它是与创建[Qt.WA_DeleteOnClose](qt.html#WidgetAttribute-enum)标志） 。如果拒绝接受close事件没有任何反应。 （在X11下有可能是窗口管理器将强制关闭该窗口，但在写作的时候，我们并不知悉有任何窗口管理器，确实如此。 ）

该事件处理程序[QWidget.closeEvent](qwidget.html#closeEvent)（ ）接收关闭事件。这个事件处理程序的默认实现接受close事件。如果您不希望您的小部件被隐藏，或者想一些特殊处理，你应该重新实现事件处理程序和[ignore](qevent.html#ignore)（）的事件。

该[closeEvent() in the Application example](index.htm#close-event-handler)显示关闭事件处理程序会询问是否在关闭之前保存文档。

如果你想，当它关闭时，窗口小部件被删除，与创建它[Qt.WA_DeleteOnClose](qt.html#WidgetAttribute-enum)标志。这是独立的顶层窗口在多窗口应用非常有用。

[QObject](qobject.html)s放出[destroyed()](qobject.html#destroyed)它们被删除时发出信号。

如果最后一个顶层窗口被关闭，[QApplication.lastWindowClosed](qapplication.html#lastWindowClosed)（）信号被发射。

该[isAccepted](qevent.html#accepted-prop)（ ）函数返回True，如果该事件的接收方已同意关闭的小部件;调用[accept](qevent.html#accept)（）同意关闭窗口小部件并调用[ignore](qevent.html#ignore)（ ）如果此事件的接收方不想要的小工具被关闭。

* * *

## Method Documentation

```
QCloseEvent.__init__ (self)
```

构造一个close事件对象。

**See also** [accept](qevent.html#accept)（ ） 。

```
QCloseEvent.__init__ (self, QCloseEvent)
```