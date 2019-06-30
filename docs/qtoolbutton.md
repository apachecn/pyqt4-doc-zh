# QToolButton Class Reference

## [[QtGui](index.htm) module]

该QToolButton类提供了一个快速访问按钮，命令或选项，通常用于内部[QToolBar](qtoolbar.html)。[More...](#details)

继承[QAbstractButton](qabstractbutton.html)。

### Types

*   `enum ToolButtonPopupMode { DelayedPopup, MenuButtonPopup, InstantPopup }`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `actionEvent (self, QActionEvent)`
*   `Qt.ArrowType arrowType (self)`
*   `bool autoRaise (self)`
*   `changeEvent (self, QEvent)`
*   `QAction defaultAction (self)`
*   `enterEvent (self, QEvent)`
*   `bool event (self, QEvent e)`
*   `bool hitButton (self, QPoint pos)`
*   `initStyleOption (self, QStyleOptionToolButton option)`
*   `leaveEvent (self, QEvent)`
*   `QMenu menu (self)`
*   `QSize minimumSizeHint (self)`
*   `mousePressEvent (self, QMouseEvent)`
*   `mouseReleaseEvent (self, QMouseEvent)`
*   `nextCheckState (self)`
*   `paintEvent (self, QPaintEvent)`
*   `ToolButtonPopupMode popupMode (self)`
*   `setArrowType (self, Qt.ArrowType type)`
*   `setAutoRaise (self, bool enable)`
*   `setDefaultAction (self, QAction)`
*   `setMenu (self, QMenu menu)`
*   `setPopupMode (self, ToolButtonPopupMode mode)`
*   `setToolButtonStyle (self, Qt.ToolButtonStyle style)`
*   `showMenu (self)`
*   `QSize sizeHint (self)`
*   `timerEvent (self, QTimerEvent)`
*   `Qt.ToolButtonStyle toolButtonStyle (self)`

### Qt Signals

*   `void triggered (QAction *)`

* * *

## Detailed Description

该QToolButton类提供了一个快速访问按钮，命令或选项，通常用于内部[QToolBar](qtoolbar.html)。

工具按钮是一个特殊的按钮，它提供快速访问特定的命令或选项。相对于正常的命令按钮，工具按钮通常不显示文本标籤，但显示的图标来代替。

工具按钮通常是创建新的时[QAction](qaction.html)实例与创建[QToolBar.addAction](qtoolbar.html#addAction)（ ）或现有的行动被添加到工具栏[QToolBar.addAction](qtoolbar.html#addAction)（ ） 。它也可以构建以同样的方式与任何其他部件的工具按钮，并安排他们一起在布局其他部件。

其中一个经典的用的工具按钮来选择工具，例如， “笔”在一个绘图程序的工具。这将通过使用QToolButton作为切换按钮（参见实施[setToggleButton](index.htm#setToggleButton)（））。

QToolButton支持自动提高。在自动模式下加注，按钮绘制一个3D框架，只有当鼠标指向它。当使用内部的一个按钮，该功能会自动开启[QToolBar](qtoolbar.html)。与更改[setAutoRaise](qtoolbutton.html#autoRaise-prop)（ ） 。

工具按钮的图标被设置为[QIcon](qicon.html)。这使得它可以指定不同的像素映射为残疾人和活跃的状态。残疾人像素图时使用的按钮的功能不可用。当自动提出的按钮，因为将鼠标指针悬停在它显示了积极的像素图。

按钮的外观和尺寸与可调[setToolButtonStyle](qtoolbutton.html#toolButtonStyle-prop)（）和[setIconSize](qabstractbutton.html#iconSize-prop)（ ） 。当内部使用[QToolBar](qtoolbar.html)在[QMainWindow](qmainwindow.html)，该按钮会自动调整以[QMainWindow](qmainwindow.html)的设置（见[QMainWindow.setToolButtonStyle](qmainwindow.html#toolButtonStyle-prop)（）和[QMainWindow.setIconSize](qmainwindow.html#iconSize-prop)（））。取而代之的图标，工具按钮也可以显示一个箭头符号，与指定的[arrowType](qtoolbutton.html#arrowType-prop)。

一个工具按钮，可以在弹出菜单中提供了更多的选择。弹出菜单可以使用设置[setMenu](qtoolbutton.html#setMenu)（ ） 。使用[setPopupMode](qtoolbutton.html#popupMode-prop)（ ）来配置可与菜单设置工具按钮的不同模式。默认模式是DelayedPopupMode它有时被用来与“后退”按钮，在Web浏览器。按下并按住该按钮，一段时间后，弹出一个菜单显示跳转到可能的页面列表。默认延迟为600毫秒，你可以用它调整[setPopupDelay](index.htm#setPopupDelay)（ ） 。

| ![Qt Assistant's toolbar with tool buttons](../img/assistant-toolbar.png) |
| Qt Assistant's toolbar contains tool buttons that are associated with actions used in other parts of the main window. |

* * *

## Type Documentation

```
QToolButton.ToolButtonPopupMode
```

描述了一个菜单应弹出的工具按钮，有一个菜单设置，或者包含一个动作列表。

| Constant | Value | Description |
| --- | --- | --- |
| `QToolButton.DelayedPopup` | `0` | 按住工具按钮一定时间后（超时是款式依赖，见[QStyle.SH_ToolButton_PopupDelay](qstyle.html#StyleHint-enum)） ，则显示菜单。一个典型的应用实例是在某些Web浏览器的工具栏的“后退”按钮。如果用户点击它时，浏览器只是浏览回到上一个页面。如果用户按下并保持按钮一会儿，工具按钮显示包含当前历史列表菜单 |
| `QToolButton.MenuButtonPopup` | `1` | 在这种模式下，工具按钮显示一个特殊的箭头来指示菜单是否存在。当该按钮的箭头部分被按下时显示的菜单。 |
| `QToolButton.InstantPopup` | `2` | 显示菜单时，无延时，按下工具按钮时。在这种模式下，该按钮自身的动作不会被触发。 |

* * *

## Method Documentation

```
QToolButton.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个空工具按钮与父_parent_。

```
QToolButton.actionEvent (self, QActionEvent)
```

从重新实现[QWidget.actionEvent](qwidget.html#actionEvent)（ ） 。

```
Qt.ArrowType QToolButton.arrowType (self)
```

[

```
bool QToolButton.autoRaise (self)
```

```
QToolButton.changeEvent (self, QEvent)
```

](qt.html#ArrowType-enum)

[从重新实现](qt.html#ArrowType-enum)[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
QAction QToolButton.defaultAction (self)
```

[

返回默认操作。

](qaction.html)

[**See also**](qaction.html) [setDefaultAction](qtoolbutton.html#setDefaultAction)（ ） 。

```
QToolButton.enterEvent (self, QEvent)
```

从重新实现[QWidget.enterEvent](qwidget.html#enterEvent)（ ） 。

```
bool QToolButton.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
bool QToolButton.hitButton (self, QPoint pos)
```

从重新实现[QAbstractButton.hitButton](qabstractbutton.html#hitButton)（ ） 。

```
QToolButton.initStyleOption (self, QStyleOptionToolButton option)
```

初始化_option_与其它的值[QToolButton](qtoolbutton.html)。当他们需要一个这种方法是有用的子类[QStyleOptionToolButton](qstyleoptiontoolbutton.html)，但不希望在所有的信息填写自己。

**See also** [QStyleOption.initFrom](qstyleoption.html#initFrom)（ ） 。

```
QToolButton.leaveEvent (self, QEvent)
```

从重新实现[QWidget.leaveEvent](qwidget.html#leaveEvent)（ ） 。

```
QMenu QToolButton.menu (self)
```

[

返回，如果没有菜单已经被定义的相关联的菜单，或0 。

](qmenu.html)

[**See also**](qmenu.html) [setMenu](qtoolbutton.html#setMenu)（ ） 。

```
QSize QToolButton.minimumSizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.minimumSizeHint](qwidget.html#minimumSizeHint-prop)（ ） 。

```
QToolButton.mousePressEvent (self, QMouseEvent)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

```
QToolButton.mouseReleaseEvent (self, QMouseEvent)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

```
QToolButton.nextCheckState (self)
```

从重新实现[QAbstractButton.nextCheckState](qabstractbutton.html#nextCheckState)（ ） 。

```
QToolButton.paintEvent (self, QPaintEvent)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

描绘按钮响应于所述涂料_event_。

```
ToolButtonPopupMode QToolButton.popupMode (self)
```

[

```
QToolButton.setArrowType (self, Qt.ArrowType type)
```

```
QToolButton.setAutoRaise (self, bool enable)
```

```
QToolButton.setDefaultAction (self, QAction)
```

这种方法也是一个Qt槽与C + +的签名`void setDefaultAction(QAction *)`。

设置默认动作_action_。

如果一个工具按钮有一个默认的动作时，动作定义如文本，图标，工具提示等按钮的属性

](qtoolbutton.html#ToolButtonPopupMode-enum)

[**See also**](qtoolbutton.html#ToolButtonPopupMode-enum) [defaultAction](qtoolbutton.html#defaultAction)（ ） 。

```
QToolButton.setMenu (self, QMenu menu)
```

联系人给定_menu_使用此工具按钮。

菜单将根据该按钮的显示[popupMode](qtoolbutton.html#popupMode-prop)。

菜单的所有权不转移到工具按钮。

**See also** [menu](qtoolbutton.html#menu)（ ） 。

```
QToolButton.setPopupMode (self, ToolButtonPopupMode mode)
```

```
QToolButton.setToolButtonStyle (self, Qt.ToolButtonStyle style)
```

这种方法也是一个Qt槽与C + +的签名`void setToolButtonStyle(Qt::ToolButtonStyle)`。

```
QToolButton.showMenu (self)
```

这种方法也是一个Qt槽与C + +的签名`void showMenu()`。

显示（弹出）相关的弹出式菜单。如果没有这样的菜单，这个函数什么都不做。此函数不返回，直到弹出菜单已经被用户关闭。

```
QSize QToolButton.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

```
QToolButton.timerEvent (self, QTimerEvent)
```

从重新实现[QObject.timerEvent](qobject.html#timerEvent)（ ） 。

```
Qt.ToolButtonStyle QToolButton.toolButtonStyle (self)
```

[

* * *

## Qt Signal Documentation

```
void triggered (QAction *)
```

这是该信号的默认超载。

这个信号被发射给定的时_action_被触发。

该操作也可与用户界面的其他部分，如菜单项和快捷键相关联。以这种方式共享行动有助于使用户界面更一致，更是往往不那么执行工作。

](qt.html#ToolButtonStyle-enum)