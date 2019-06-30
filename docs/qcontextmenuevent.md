# QContextMenuEvent Class Reference

## [[QtGui](index.htm) module]

该QContextMenuEvent类包含描述一个上下文菜单事件参数。[More...](#details)

继承[QInputEvent](qinputevent.html)。

### Types

*   `enum Reason { Mouse, Keyboard, Other }`

### Methods

*   `__init__ (self, Reason reason, QPoint pos, QPoint globalPos, Qt.KeyboardModifiers modifiers)`
*   `__init__ (self, Reason reason, QPoint pos, QPoint globalPos)`
*   `__init__ (self, Reason reason, QPoint pos)`
*   `__init__ (self, QContextMenuEvent)`
*   `QPoint globalPos (self)`
*   `int globalX (self)`
*   `int globalY (self)`
*   `QPoint pos (self)`
*   `Reason reason (self)`
*   `int x (self)`
*   `int y (self)`

* * *

## Detailed Description

该QContextMenuEvent类包含描述一个上下文菜单事件参数。

上下文菜单事件发送到窗口部件，当用户执行与打开上下文菜单相关联的动作。打开上下文菜单所需的操作平台之间有所不同，例如，在Windows上，按菜单按钮或单击鼠标右键，会导致此事件被发送。

当该事件发生时，习惯以显示[QMenu](qmenu.html)一个上下文菜单，如果这是相关的上下文。

上下文菜单事件包含一个特殊的接受标志，指示接收者是否接受该事件。如果事件处理程序不接受的事件，然后，如果可能的话，无论触发的事件将被作为常规的输入事件处理。

* * *

## Type Documentation

```
QContextMenuEvent.Reason
```

这个枚举说明为什么该事件被发送的原因。

| Constant | Value | Description |
| --- | --- | --- |
| `QContextMenuEvent.Mouse` | `0` | 鼠标导致事件被发送。通常这意味着鼠标右键被点击，但这是依赖于平台。 |
| `QContextMenuEvent.Keyboard` | `1` | 键盘导致此事件被发送。在Windows上，这意味着菜单按钮被按下。 |
| `QContextMenuEvent.Other` | `2` | 这次活动是由一些其他的手段（即不通过鼠标或键盘）发出。 |

* * *

## Method Documentation

```
QContextMenuEvent.__init__ (self, Reason reason, QPoint pos, QPoint globalPos, Qt.KeyboardModifiers modifiers)
```

构造一个上下文菜单事件对象的接受参数标志设置为False 。

该_reason_参数必须是[QContextMenuEvent.Mouse](qcontextmenuevent.html#Reason-enum) or [QContextMenuEvent.Keyboard](qcontextmenuevent.html#Reason-enum)。

该_pos_参数指定鼠标位置相对于接收部件。_globalPos_是在绝对坐标中的鼠标位置。该_modifiers_拥有键盘功能键。

```
QContextMenuEvent.__init__ (self, Reason reason, QPoint pos, QPoint globalPos)
```

构造一个上下文菜单事件对象的接受参数标志设置为False 。

该_reason_参数必须是[QContextMenuEvent.Mouse](qcontextmenuevent.html#Reason-enum) or [QContextMenuEvent.Keyboard](qcontextmenuevent.html#Reason-enum)。

该_pos_参数指定鼠标位置相对于接收部件。_globalPos_是在绝对坐标中的鼠标位置。

```
QContextMenuEvent.__init__ (self, Reason reason, QPoint pos)
```

构造一个上下文菜单事件对象的接受参数标志设置为False 。

该_reason_参数必须是[QContextMenuEvent.Mouse](qcontextmenuevent.html#Reason-enum) or [QContextMenuEvent.Keyboard](qcontextmenuevent.html#Reason-enum)。

该_pos_参数指定鼠标位置相对于接收部件。

该[globalPos](qcontextmenuevent.html#globalPos)（）被初始化为[QCursor.pos](qcursor.html#pos)（），这可能不适合。使用其他构造函数来显式地指定的国际地位。

```
QContextMenuEvent.__init__ (self, QContextMenuEvent)
```

```
QPoint QContextMenuEvent.globalPos (self)
```

[

返回在事件发生时鼠标指针的全球地位。

](qpoint.html)

[**See also**](qpoint.html) [x](qcontextmenuevent.html#x)（ ）[y](qcontextmenuevent.html#y)（）和[pos](qcontextmenuevent.html#pos)（ ） 。

```
int QContextMenuEvent.globalX (self)
```

返回在事件发生时鼠标指针的全局x位置。

**See also** [globalY](qcontextmenuevent.html#globalY)（）和[globalPos](qcontextmenuevent.html#globalPos)（ ） 。

```
int QContextMenuEvent.globalY (self)
```

返回在事件发生时鼠标指针的全局y位置。

**See also** [globalX](qcontextmenuevent.html#globalX)（）和[globalPos](qcontextmenuevent.html#globalPos)（ ） 。

```
QPoint QContextMenuEvent.pos (self)
```

[

返回到该接收到的事件的插件鼠标指针相对的位置。

](qpoint.html)

[**See also**](qpoint.html) [x](qcontextmenuevent.html#x)（ ）[y](qcontextmenuevent.html#y)（）和[globalPos](qcontextmenuevent.html#globalPos)（ ） 。

```
Reason QContextMenuEvent.reason (self)
```

[

返回此上下文事件的原因。

```
int QContextMenuEvent.x (self)
```

返回鼠标指针的x位置，相对于接收到的事件的插件。

](qcontextmenuevent.html#Reason-enum)

[**See also**](qcontextmenuevent.html#Reason-enum) [y](qcontextmenuevent.html#y)（）和[pos](qcontextmenuevent.html#pos)（ ） 。

```
int QContextMenuEvent.y (self)
```

返回鼠标指针的y位置，相对于接收事件的窗口小部件。

**See also** [x](qcontextmenuevent.html#x)（）和[pos](qcontextmenuevent.html#pos)（ ） 。