# QFocusFrame Class Reference

## [[QtGui](index.htm) module]

该QFocusFrame小部件提供它可以是一个小部件的正常绘画区域之外的对焦框。[More...](#details)

继承[QWidget](qwidget.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `bool event (self, QEvent e)`
*   `bool eventFilter (self, QObject, QEvent)`
*   `initStyleOption (self, QStyleOption option)`
*   `paintEvent (self, QPaintEvent)`
*   `setWidget (self, QWidget widget)`
*   `QWidget widget (self)`

* * *

## Detailed Description

该QFocusFrame小部件提供它可以是一个小部件的正常绘画区域之外的对焦框。

通常，应用程序将不再需要建立自己的QFocusFrame为[QStyle](qstyle.html)将处理这个细节给你的。样式作家可以选择使用QFocusFrame有小部件的可绘制几何图形以外的重点区域。在这样的空间不需要被保留以供小窗口具有焦点，但只设置在一个[QWidget](qwidget.html)与QFocusFrame.setWidget 。它是，但是，法律上的自定义窗口小部件创建自己的QFocusFrame并通过QWidget.setGeometry手动设置它的几何形状，但是你不会得到自动放置时，聚焦小部件更改大小或位置。

* * *

## Method Documentation

```
QFocusFrame.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QFocusFrame](qfocusframe.html)。

对焦框不会监视_parent_更新而是可以手动放置或使用QFocusFrame.setWidget 。一[QFocusFrame](qfocusframe.html) sets [Qt.WA_NoChildEventsForParent](qt.html#WidgetAttribute-enum)属性，这样一来的父进程将不会收到[QEvent.ChildInserted](qevent.html#Type-enum)事件，这将使得有可能手动设置的几何形状[QFocusFrame](qfocusframe.html)内部的[QSplitter](qsplitter.html)或其他子事件监控部件。

**See also** [QFocusFrame.setWidget](qfocusframe.html#setWidget)（ ） 。

```
bool QFocusFrame.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
bool QFocusFrame.eventFilter (self, QObject, QEvent)
```

从重新实现[QObject.eventFilter](qobject.html#eventFilter)（ ） 。

```
QFocusFrame.initStyleOption (self, QStyleOption option)
```

初始化_option_与其它的值[QFocusFrame](qfocusframe.html)。当他们需要一个这种方法是有用的子类[QStyleOption](qstyleoption.html)，但不希望在所有的信息填写自己。

**See also** [QStyleOption.initFrom](qstyleoption.html#initFrom)（ ） 。

```
QFocusFrame.paintEvent (self, QPaintEvent)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QFocusFrame.setWidget (self, QWidget widget)
```

[QFocusFrame](qfocusframe.html)将跟踪更改_widget_并自动调整自身的大小。如果被监控的小部件的父变化，[QFocusFrame](qfocusframe.html)将按照窗口小部件并自动将自己周围的部件。如果被监视的部件被删除时，[QFocusFrame](qfocusframe.html)将其设置为零。

**See also** [QFocusFrame.widget](qfocusframe.html#widget)（ ） 。

```
QWidget QFocusFrame.widget (self)
```

[

返回当前监控的部件自动调整和更新。

](qwidget.html)

[**See also**](qwidget.html) [QFocusFrame.setWidget](qfocusframe.html#setWidget)（ ） 。