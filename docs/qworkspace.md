# QWorkspace Class Reference

## [[QtGui](index.htm) module]

该QWorkspace小部件提供一个工作区窗口，可以在MDI应用程序中使用。[More...](#details)

继承[QWidget](qwidget.html)。

### Types

*   `enum WindowOrder { CreationOrder, StackingOrder }`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `activateNextWindow (self)`
*   `activatePreviousWindow (self)`
*   `QWidget activeWindow (self)`
*   `QWidget addWindow (self, QWidget w, Qt.WindowFlags flags = 0)`
*   `arrangeIcons (self)`
*   `QBrush background (self)`
*   `cascade (self)`
*   `changeEvent (self, QEvent)`
*   `childEvent (self, QChildEvent)`
*   `closeActiveWindow (self)`
*   `closeAllWindows (self)`
*   `bool event (self, QEvent e)`
*   `bool eventFilter (self, QObject, QEvent)`
*   `hideEvent (self, QHideEvent e)`
*   `paintEvent (self, QPaintEvent e)`
*   `resizeEvent (self, QResizeEvent)`
*   `bool scrollBarsEnabled (self)`
*   `setActiveWindow (self, QWidget w)`
*   `setBackground (self, QBrush background)`
*   `setScrollBarsEnabled (self, bool enable)`
*   `showEvent (self, QShowEvent e)`
*   `QSize sizeHint (self)`
*   `tile (self)`
*   `wheelEvent (self, QWheelEvent e)`
*   `list-of-QWidget windowList (self, WindowOrder order = QWorkspace.CreationOrder)`

### Qt Signals

*   `void windowActivated (QWidget *)`

* * *

## Detailed Description

该QWorkspace小部件提供一个工作区窗口，可以在MDI应用程序中使用。

此类已被否决。使用[QMdiArea](qmdiarea.html)代替。

多文档界面（MDI ）应用程序通常由包含一个菜单栏，工具栏，和中央QWorkspace部件一个主窗口。工作空间本身是用来显示多个子窗口，其中每一个是一个部件。

工作区本身就是一个普通的Qt的部件。它有一个标准的构造函数接受一个父部件。工作空间可以被放置在任何布局，但通常被给定为在中央部件[QMainWindow](qmainwindow.html)：

```
 MainWindow.MainWindow()
 {
     workspace = new QWorkspace;
     setCentralWidget(workspace);
     ...
 }

```

子窗口（ MDI窗口）是插入到工作区中使用标准的Qt部件[addWindow](qworkspace.html#addWindow)（ ） 。与顶层窗口部件，你可以调用函数，如[show](qwidget.html#show)（ ）[hide](qwidget.html#hide)（ ）[showMaximized](qwidget.html#showMaximized)（）和[setWindowTitle](qwidget.html#windowTitle-prop)（ ）在子窗口更改工作区中它的外观。您也可以提供窗口部件标记，以确定装修或部件本身的行为的布局。

要更改或检索一个子窗口的几何形状，你必须在它的操作[parentWidget](qwidget.html#parentWidget)（ ） 。该[parentWidget](qwidget.html#parentWidget)（ ）提供了访问的装饰框，其中包含子窗口小部件。当一个子窗口最大化，它的装饰框被隐藏。如果顶层窗口部件包含一个菜单栏，它会显示最大化窗口的操作菜单中的菜单项的左侧，和窗口的控制，以正确的。

当它获取键盘焦点时，或者当子窗口被激活[setFocus](qwidget.html#setFocus)（）被调用。用户可以通过点击窗口或按Tab键移动焦点在通常的方法，例如激活的窗口。工作区中发射的信号[windowActivated](qworkspace.html#windowActivated)（ ）当活动窗口的变化，并且功能[activeWindow](qworkspace.html#activeWindow)（ ）返回一个指向活动的子窗口，或者0，如果没有窗口被激活。

便利的功能[windowList](qworkspace.html#windowList)（ ）返回所有子窗口的列表。此信息可以在含有窗口的列表的弹出式菜单中使用，例如。此功能也可作为部分[Window Menu](http://doc.qt.digia.com/qq/qq09-qt-solutions.html)解决方案。

QWorkspace为子窗口有两个内置的布局策略：[cascade](qworkspace.html#cascade)（）和[tile](qworkspace.html#tile)（ ） 。两者都是插槽让您可以轻松的菜单项连接到它们。

| ![](../img/mdi-cascade.png) | ![](../img/mdi-tile.png) |

如果你希望你的用户能够与子窗口比可见工作区面积较大的工作，设置[scrollBarsEnabled](qworkspace.html#scrollBarsEnabled-prop)属性设置为True 。

* * *

## Type Documentation

```
QWorkspace.WindowOrder
```

指定在其中的子窗口从返回的顺序[windowList](qworkspace.html#windowList)（ ） 。

| Constant | Value | Description |
| --- | --- | --- |
| `QWorkspace.CreationOrder` | `0` | 该窗口在其创建的顺序返回 |
| `QWorkspace.StackingOrder` | `1` | 该窗口在它们的层叠顺序返回 |

* * *

## Method Documentation

```
QWorkspace.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个工作区与给定_parent_。

```
QWorkspace.activateNextWindow (self)
```

这种方法也是一个Qt槽与C + +的签名`void activateNextWindow()`。

给出了输入焦点的子窗口列表中的下一个窗口。

**See also** [activatePreviousWindow](qworkspace.html#activatePreviousWindow)（ ） 。

```
QWorkspace.activatePreviousWindow (self)
```

这种方法也是一个Qt槽与C + +的签名`void activatePreviousWindow()`。

给出了输入焦点到前一个窗口中的子窗口的列表中。

**See also** [activateNextWindow](qworkspace.html#activateNextWindow)（ ） 。

```
QWidget QWorkspace.activeWindow (self)
```

[

返回一个指针，对应于活动的子窗口，或者0，如果没有窗口被激活的窗口小部件。

](qwidget.html)

[**See also**](qwidget.html) [setActiveWindow](qworkspace.html#setActiveWindow)（ ） 。

```
QWidget QWorkspace.addWindow (self, QWidget w, Qt.WindowFlags flags = 0)
```

[

该_w_说法有它的所有权转移给Qt的。

添加小工具_w_作为新的子窗口的工作空间。如果_flags_是非零的，它们将复盖在部件上设置的标志。

返回用于窗口框架的窗口部件。

](qwidget.html)

[要删除小工具_w_从工作区，只需调用](qwidget.html)[setParent](qwidget.html#setParent)（ ）与新的父（或0 ，使之成为单独的窗口）。

```
QWorkspace.arrangeIcons (self)
```

这种方法也是一个Qt槽与C + +的签名`void arrangeIcons()`。

所有排列图标化窗口在工作区的底部。

**See also** [cascade](qworkspace.html#cascade)（）和[tile](qworkspace.html#tile)（ ） 。

```
QBrush QWorkspace.background (self)
```

[

```
QWorkspace.cascade (self)
```

这种方法也是一个Qt槽与C + +的签名`void cascade()`。

安排所有子窗口在级联模式。

](qbrush.html)

[**See also**](qbrush.html) [tile](qworkspace.html#tile)（）和[arrangeIcons](qworkspace.html#arrangeIcons)（ ） 。

```
QWorkspace.changeEvent (self, QEvent)
```

从重新实现[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
QWorkspace.childEvent (self, QChildEvent)
```

从重新实现[QObject.childEvent](qobject.html#childEvent)（ ） 。

```
QWorkspace.closeActiveWindow (self)
```

这种方法也是一个Qt槽与C + +的签名`void closeActiveWindow()`。

关闭子窗口，是目前活跃。

**See also** [closeAllWindows](qworkspace.html#closeAllWindows)（ ） 。

```
QWorkspace.closeAllWindows (self)
```

这种方法也是一个Qt槽与C + +的签名`void closeAllWindows()`。

关闭所有的子窗口。

如果任何子窗口无法接受close事件，其馀窗口将继续开放。

**See also** [closeActiveWindow](qworkspace.html#closeActiveWindow)（ ） 。

```
bool QWorkspace.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
bool QWorkspace.eventFilter (self, QObject, QEvent)
```

从重新实现[QObject.eventFilter](qobject.html#eventFilter)（ ） 。

```
QWorkspace.hideEvent (self, QHideEvent e)
```

从重新实现[QWidget.hideEvent](qwidget.html#hideEvent)（ ） 。

```
QWorkspace.paintEvent (self, QPaintEvent e)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QWorkspace.resizeEvent (self, QResizeEvent)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
bool QWorkspace.scrollBarsEnabled (self)
```

```
QWorkspace.setActiveWindow (self, QWidget w)
```

这种方法也是一个Qt槽与C + +的签名`void setActiveWindow(QWidget *)`。

使得包含子窗口_w_活动的子窗口。

**See also** [activeWindow](qworkspace.html#activeWindow)（ ） 。

```
QWorkspace.setBackground (self, QBrush background)
```

```
QWorkspace.setScrollBarsEnabled (self, bool enable)
```

```
QWorkspace.showEvent (self, QShowEvent e)
```

从重新实现[QWidget.showEvent](qwidget.html#showEvent)（ ） 。

```
QSize QWorkspace.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

```
QWorkspace.tile (self)
```

这种方法也是一个Qt槽与C + +的签名`void tile()`。

安排所有子窗口的瓷砖图案。

**See also** [cascade](qworkspace.html#cascade)（）和[arrangeIcons](qworkspace.html#arrangeIcons)（ ） 。

```
QWorkspace.wheelEvent (self, QWheelEvent e)
```

从重新实现[QWidget.wheelEvent](qwidget.html#wheelEvent)（ ） 。

```
list-of-QWidget QWorkspace.windowList (self, WindowOrder order = QWorkspace.CreationOrder)
```

返回所有可见或最小化的子窗口的列表。如果_order_ is [CreationOrder](qworkspace.html#WindowOrder-enum)（默认值） ，该窗口被列在它们被插入到工作区中的顺序。如果_order_ is [StackingOrder](qworkspace.html#WindowOrder-enum)，窗口中列出了它们的堆叠顺序，与最顶层窗口的最后一个项目在列表中。

* * *

## Qt Signal Documentation

```
void windowActivated (QWidget *)
```

这是该信号的默认超载。

这个信号被发射时的子窗口_w_变得活跃。需要注意的是_w_可以是0，和一个以上的信号可用于单个激活事件发射。

**See also** [activeWindow](qworkspace.html#activeWindow)（）和[windowList](qworkspace.html#windowList)（ ） 。