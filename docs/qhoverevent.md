# QHoverEvent Class Reference

## [[QtGui](index.htm) module]

该QHoverEvent类包含描述一个鼠标事件参数。[More...](#details)

继承[QEvent](qevent.html)。

### Methods

*   `__init__ (self, QEvent.Type type, QPoint pos, QPoint oldPos)`
*   `__init__ (self, QHoverEvent)`
*   `QPoint oldPos (self)`
*   `QPoint pos (self)`

* * *

## Detailed Description

该QHoverEvent类包含描述一个鼠标事件参数。

当鼠标光标移入，出，或窗口小部件中的鼠标事件发生时，如果部件有[Qt.WA_Hover](qt.html#WidgetAttribute-enum)属性。

该功能[pos](qhoverevent.html#pos)（ ）给出当前光标位置，而[oldPos](qhoverevent.html#oldPos)（ ）给出的旧鼠标的位置。

有事件之间有一些相似之处[QEvent.HoverEnter](qevent.html#Type-enum)和[QEvent.HoverLeave](qevent.html#Type-enum)和事件[QEvent.Enter](qevent.html#Type-enum)和[QEvent.Leave](qevent.html#Type-enum)。然而，他们都略有不同，因为我们做一个更新（ ）中的事件处理程序[HoverEnter](qevent.html#Type-enum)和[HoverLeave](qevent.html#Type-enum)。

[QEvent.HoverMove](qevent.html#Type-enum)也是从稍微不同的[QEvent.MouseMove](qevent.html#Type-enum)。让我们考虑包含这又包含子C（所有带鼠标跟踪启用）儿童B中的顶层窗口答：

![](../img/hoverevents.png)

现在，如果你从顶部到A的中间底部移动光标，你将得到下面的[QEvent.MouseMove](qevent.html#Type-enum)事件：

1.  A.MouseMove
2.  B.MouseMove
3.  C.MouseMove

你会得到相同的事件[QEvent.HoverMove](qevent.html#Type-enum)，除了事件始终传播到顶层，无论该事件是否被接受与否。它只会停止与传播[Qt.WA_NoMousePropagation](qt.html#WidgetAttribute-enum)属性。

在这种情况下，事件将发生在下列方式：

1.  A.HoverMove
2.  A.HoverMove ， B.HoverMove
3.  A.HoverMove ， B.HoverMove ， C.HoverMove

* * *

## Method Documentation

```
QHoverEvent.__init__ (self, QEvent.Type type, QPoint pos, QPoint oldPos)
```

构造一个悬停事件对象。

该_type_参数必须是[QEvent.HoverEnter](qevent.html#Type-enum)，[QEvent.HoverLeave](qevent.html#Type-enum)或[QEvent.HoverMove](qevent.html#Type-enum)。

该_pos_是当前鼠标光标的位置相对于接收部件，而_oldPos_是先前的鼠标光标的位置相对于接收部件。

```
QHoverEvent.__init__ (self, QHoverEvent)
```

```
QPoint QHoverEvent.oldPos (self)
```

[](qpoint.html)

[返回鼠标光标的前面的位置，相对于接收到的事件的插件。如果没有之前的位置， oldPos （ ）将返回相同的位置](qpoint.html)[pos](qhoverevent.html#pos)（ ） 。

On [QEvent.HoverEnter](qevent.html#Type-enum)活动，这一立场永远是[QPoint](qpoint.html)（-1 ，-1）。

**See also** [pos](qhoverevent.html#pos)（ ） 。

```
QPoint QHoverEvent.pos (self)
```

[

返回鼠标光标的位置，相对于接收到的事件的插件。

](qpoint.html)

[On](qpoint.html) [QEvent.HoverLeave](qevent.html#Type-enum)活动，这一立场永远是[QPoint](qpoint.html)（-1 ，-1）。

**See also** [oldPos](qhoverevent.html#oldPos)（ ） 。