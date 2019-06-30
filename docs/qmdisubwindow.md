# QMdiSubWindow Class Reference

## [[QtGui](index.htm) module]

该QMdiSubWindow类提供了一个子窗口类[QMdiArea](qmdiarea.html)。[More...](#details)

继承[QWidget](qwidget.html)。

### Types

*   `enum SubWindowOption { RubberBandResize, RubberBandMove }`
*   `class **[SubWindowOptions](index.htm)**`

### Methods

*   `__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)`
*   `changeEvent (self, QEvent changeEvent)`
*   `childEvent (self, QChildEvent childEvent)`
*   `closeEvent (self, QCloseEvent closeEvent)`
*   `contextMenuEvent (self, QContextMenuEvent contextMenuEvent)`
*   `bool event (self, QEvent event)`
*   `bool eventFilter (self, QObject object, QEvent event)`
*   `focusInEvent (self, QFocusEvent focusInEvent)`
*   `focusOutEvent (self, QFocusEvent focusOutEvent)`
*   `hideEvent (self, QHideEvent hideEvent)`
*   `bool isShaded (self)`
*   `int keyboardPageStep (self)`
*   `int keyboardSingleStep (self)`
*   `keyPressEvent (self, QKeyEvent keyEvent)`
*   `leaveEvent (self, QEvent leaveEvent)`
*   `QMdiArea mdiArea (self)`
*   `QSize minimumSizeHint (self)`
*   `mouseDoubleClickEvent (self, QMouseEvent mouseEvent)`
*   `mouseMoveEvent (self, QMouseEvent mouseEvent)`
*   `mousePressEvent (self, QMouseEvent mouseEvent)`
*   `mouseReleaseEvent (self, QMouseEvent mouseEvent)`
*   `moveEvent (self, QMoveEvent moveEvent)`
*   `paintEvent (self, QPaintEvent paintEvent)`
*   `resizeEvent (self, QResizeEvent resizeEvent)`
*   `setKeyboardPageStep (self, int step)`
*   `setKeyboardSingleStep (self, int step)`
*   `setOption (self, SubWindowOption option, bool on = True)`
*   `setSystemMenu (self, QMenu systemMenu)`
*   `setWidget (self, QWidget widget)`
*   `showEvent (self, QShowEvent showEvent)`
*   `showShaded (self)`
*   `showSystemMenu (self)`
*   `QSize sizeHint (self)`
*   `QMenu systemMenu (self)`
*   `bool testOption (self, SubWindowOption)`
*   `timerEvent (self, QTimerEvent timerEvent)`
*   `QWidget widget (self)`

### Qt Signals

*   `void aboutToActivate ()`
*   `void windowStateChanged (Qt::WindowStates,Qt::WindowStates)`

* * *

## Detailed Description

该QMdiSubWindow类提供了一个子窗口类[QMdiArea](qmdiarea.html)。

QMdiSubWindow代表了一个顶层窗口[QMdiArea](qmdiarea.html)，并包含有窗装饰，内部部件，并（根据目前的风格）窗框和大小手柄一个标题栏。 QMdiSubWindow有自己的布局，其中包括标题栏和一个中心区内部小部件。

![](../img/qmdisubwindowlayout.png)

构造一个QMdiSubWindow最常见的方法是调用[QMdiArea.addSubWindow](qmdiarea.html#addSubWindow)（ ）与内部部件作为参数。您也可以自己创建一个子窗口，并通过调用设置一个内部小部件[setWidget](qmdisubwindow.html#setWidget)（ ） 。

当与子窗口与普通顶层窗口（例如，编程您可以使用相同的API ，你可以调用函数，如[show](qwidget.html#show)（ ）[hide](qwidget.html#hide)（ ）[showMaximized](qwidget.html#showMaximized)（）和[setWindowTitle](qwidget.html#windowTitle-prop)（））。

### Subwindow Handling

QMdiSubWindow还支持特定于一个MDI子窗口区域的行为。

默认情况下，每个QMdiSubWindow是MDI领域内视可见搬来搬去的时候，但它也可以指定透明窗口的移动和调整大小的行为，其中一个子窗口，只有轮廓在这些行动中被更新。该[setOption](qmdisubwindow.html#setOption)（ ）函数是用来启用此行为。

该[isShaded](qmdisubwindow.html#isShaded)（ ）函数检测子窗口当前是否处于阴影（即窗口处于折叠状态，因此只有标题栏可见） 。进入着色模式，通话时间[showShaded](qmdisubwindow.html#showShaded)（ ） 。 QMdiSubWindow放出[windowStateChanged](qmdisubwindow.html#windowStateChanged)（ ）信号时窗口状态发生了变化（例如，当窗口最小化或恢复） 。它还发出[aboutToActivate](qmdisubwindow.html#aboutToActivate)（ ）之前被激活。

在键盘的交互模式，窗户被移动和调整大小的键盘。你可以通过这个窗口的系统菜单进入该模式。该[keyboardSingleStep](qmdisubwindow.html#keyboardSingleStep-prop)和[keyboardPageStep](qmdisubwindow.html#keyboardPageStep-prop)属性控制部件被移动或改变大小为每个按键事件的距离。当换挡时按下页的步骤使用，否则单步使用。

您也可以使用键盘更改活动窗口。通过按压控制和tab键在同一时间，接下来的处理（使用当前[WindowOrder](qmdiarea.html#WindowOrder-enum)）子窗口将被激活。按Ctrl ，Shift和标籤上，您将激活上一个窗口。这等同于调用[activateNextSubWindow()](qmdiarea.html#activateNextSubWindow)和[activatePreviousSubWindow()](qmdiarea.html#activatePreviousSubWindow)。需要注意的是这些快捷方式复盖全局的快捷键，但不是[QMdiArea](qmdiarea.html)s捷径。

* * *

## Type Documentation

```
QMdiSubWindow.SubWindowOption
```

这个枚举变量描述了自定义的行为的选项[QMdiSubWindow](qmdisubwindow.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QMdiSubWindow.RubberBandResize` | `0x4` | 如果启用此选项，橡皮筋控制是用来表示子窗口的轮廓，以及用户调整，而不是子窗口本身这一点。因此，子窗口保持其原来的位置和大小，直到调整操作已经完成，届时将接受一个单一的[QResizeEvent](qresizeevent.html)。默认情况下，该选项被禁用。 |
| `QMdiSubWindow.RubberBandMove` | `0x8` | 如果启用此选项，橡皮筋控制是用来表示子窗口的轮廓，以及用户移动，而不是子窗口本身这一点。其结果是，在子窗口保持在其原来的位置，直到在移动操作已经完成，在该时间[QMoveEvent](qmoveevent.html)被发送到窗口。默认情况下，该选项被禁用。 |

该SubWindowOptions类型是一个typedef为[QFlags](index.htm)\u003cSubWindowOption\u003e 。它存储SubWindowOption值的或组合。

* * *

## Method Documentation

```
QMdiSubWindow.__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的[QMdiSubWindow](qmdisubwindow.html)小工具。该_parent_和_flags_参数被传递给[QWidget](qwidget.html)的构造。

代替使用addSubWindow （）的，它也只是可以使用[setParent](qwidget.html#setParent)（ ）当您添加子窗口到[QMdiArea](qmdiarea.html)。

请注意，只有[QMdiSubWindow](qmdisubwindow.html)S可设定为儿童[QMdiArea](qmdiarea.html)，你不能，例如，写：

```
 QMdiArea mdiArea;
 QTextEdit editor(&mdiArea); // invalid child widget

```

**See also** [QMdiArea.addSubWindow](qmdiarea.html#addSubWindow)（ ） 。

```
QMdiSubWindow.changeEvent (self, QEvent changeEvent)
```

从重新实现[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
QMdiSubWindow.childEvent (self, QChildEvent childEvent)
```

从重新实现[QObject.childEvent](qobject.html#childEvent)（ ） 。

```
QMdiSubWindow.closeEvent (self, QCloseEvent closeEvent)
```

从重新实现[QWidget.closeEvent](qwidget.html#closeEvent)（ ） 。

```
QMdiSubWindow.contextMenuEvent (self, QContextMenuEvent contextMenuEvent)
```

从重新实现[QWidget.contextMenuEvent](qwidget.html#contextMenuEvent)（ ） 。

```
bool QMdiSubWindow.event (self, QEvent event)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
bool QMdiSubWindow.eventFilter (self, QObject object, QEvent event)
```

从重新实现[QObject.eventFilter](qobject.html#eventFilter)（ ） 。

```
QMdiSubWindow.focusInEvent (self, QFocusEvent focusInEvent)
```

从重新实现[QWidget.focusInEvent](qwidget.html#focusInEvent)（ ） 。

```
QMdiSubWindow.focusOutEvent (self, QFocusEvent focusOutEvent)
```

从重新实现[QWidget.focusOutEvent](qwidget.html#focusOutEvent)（ ） 。

```
QMdiSubWindow.hideEvent (self, QHideEvent hideEvent)
```

从重新实现[QWidget.hideEvent](qwidget.html#hideEvent)（ ） 。

```
bool QMdiSubWindow.isShaded (self)
```

返回True如果此窗口阴影，否则返回False 。

如果它处于折叠状态，因此只有标题栏是可见的窗口的阴影。

```
int QMdiSubWindow.keyboardPageStep (self)
```

```
int QMdiSubWindow.keyboardSingleStep (self)
```

```
QMdiSubWindow.keyPressEvent (self, QKeyEvent keyEvent)
```

从重新实现[QWidget.keyPressEvent](qwidget.html#keyPressEvent)（ ） 。

```
QMdiSubWindow.leaveEvent (self, QEvent leaveEvent)
```

从重新实现[QWidget.leaveEvent](qwidget.html#leaveEvent)（ ） 。

```
QMdiArea QMdiSubWindow.mdiArea (self)
```

[

返回包含该子窗口，或者0，如果是没有的区域。

此功能被引入Qt的4.4 。

](qmdiarea.html)

[**See also**](qmdiarea.html) [QMdiArea.addSubWindow](qmdiarea.html#addSubWindow)（ ） 。

```
QSize QMdiSubWindow.minimumSizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.minimumSizeHint](qwidget.html#minimumSizeHint-prop)（ ） 。

```
QMdiSubWindow.mouseDoubleClickEvent (self, QMouseEvent mouseEvent)
```

从重新实现[QWidget.mouseDoubleClickEvent](qwidget.html#mouseDoubleClickEvent)（ ） 。

```
QMdiSubWindow.mouseMoveEvent (self, QMouseEvent mouseEvent)
```

从重新实现[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

```
QMdiSubWindow.mousePressEvent (self, QMouseEvent mouseEvent)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

```
QMdiSubWindow.mouseReleaseEvent (self, QMouseEvent mouseEvent)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

```
QMdiSubWindow.moveEvent (self, QMoveEvent moveEvent)
```

从重新实现[QWidget.moveEvent](qwidget.html#moveEvent)（ ） 。

```
QMdiSubWindow.paintEvent (self, QPaintEvent paintEvent)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QMdiSubWindow.resizeEvent (self, QResizeEvent resizeEvent)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
QMdiSubWindow.setKeyboardPageStep (self, int step)
```

```
QMdiSubWindow.setKeyboardSingleStep (self, int step)
```

```
QMdiSubWindow.setOption (self, SubWindowOption option, bool on = True)
```

If _on_是真的，_option_在子窗口被激活，否则将被禁用。看[SubWindowOption](qmdisubwindow.html#SubWindowOption-enum)每个选项的效果。

**See also** [SubWindowOption](qmdisubwindow.html#SubWindowOption-enum)和[testOption](qmdisubwindow.html#testOption)（ ） 。

```
QMdiSubWindow.setSystemMenu (self, QMenu systemMenu)
```

该_systemMenu_说法有它的所有权转移给Qt的。

Sets _systemMenu_作为该子窗口中当前的系统菜单。

默认情况下，每[QMdiSubWindow](qmdisubwindow.html)有一个标准的系统菜单。

QActions由创建的系统菜单[QMdiSubWindow](qmdisubwindow.html)根据当前窗口状态会自动更新;例如，窗口最小化后的最小化操作将被禁用。

由用户添加QActions不被更新[QMdiSubWindow](qmdisubwindow.html)。

[QMdiSubWindow](qmdisubwindow.html)采取所有权_systemMenu_，您不必删除它。任何现有的菜单将被删除。

**See also** [systemMenu](qmdisubwindow.html#systemMenu)（）和[showSystemMenu](qmdisubwindow.html#showSystemMenu)（ ） 。

```
QMdiSubWindow.setWidget (self, QWidget widget)
```

该_widget_说法有它的所有权转移给Qt的。

Sets _widget_作为这个子窗口的内部部件。内部小部件将显示在标题栏下的子窗口的中心。

[QMdiSubWindow](qmdisubwindow.html)采取的临时所有权_widget_，您不必删除它。任何现有的内部部件将被删除和重设父到根窗口。

**See also** [widget](qmdisubwindow.html#widget)（ ） 。

```
QMdiSubWindow.showEvent (self, QShowEvent showEvent)
```

从重新实现[QWidget.showEvent](qwidget.html#showEvent)（ ） 。

```
QMdiSubWindow.showShaded (self)
```

这种方法也是一个Qt槽与C + +的签名`void showShaded()`。

调用此函数使子窗口进入着色模式。当子窗口被遮蔽，只有标题栏可见。

虽然阴影是不支持的所有样式，这个功能仍然会显示为阴影的子窗口，无论是可用于遮阳的支持。然而，随着款式不支持底纹使用时，用户将无法从阴影模式通过用户界面返回（例如，通过在标题栏中窗帘按键） 。

**See also** [isShaded](qmdisubwindow.html#isShaded)（ ） 。

```
QMdiSubWindow.showSystemMenu (self)
```

这种方法也是一个Qt槽与C + +的签名`void showSystemMenu()`。

下面显示在标题栏中显示的系统菜单图标，系统菜单。

**See also** [setSystemMenu](qmdisubwindow.html#setSystemMenu)（）和[systemMenu](qmdisubwindow.html#systemMenu)（ ） 。

```
QSize QMdiSubWindow.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

```
QMenu QMdiSubWindow.systemMenu (self)
```

[](qmenu.html)

[返回一个指针，指向当前系统菜单，或零，如果没有系统菜单设置。](qmenu.html)[QMdiSubWindow](qmdisubwindow.html)提供了默认的系统菜单，但你也可以设置菜单与[setSystemMenu](qmdisubwindow.html#setSystemMenu)（ ） 。

**See also** [setSystemMenu](qmdisubwindow.html#setSystemMenu)（）和[showSystemMenu](qmdisubwindow.html#showSystemMenu)（ ） 。

```
bool QMdiSubWindow.testOption (self, SubWindowOption)
```

返回True如果_option_被启用，否则返回False 。

**See also** [SubWindowOption](qmdisubwindow.html#SubWindowOption-enum)和[setOption](qmdisubwindow.html#setOption)（ ） 。

```
QMdiSubWindow.timerEvent (self, QTimerEvent timerEvent)
```

从重新实现[QObject.timerEvent](qobject.html#timerEvent)（ ） 。

```
QWidget QMdiSubWindow.widget (self)
```

[

返回当前的内部部件。

](qwidget.html)

[**See also**](qwidget.html) [setWidget](qmdisubwindow.html#setWidget)（ ） 。

* * *

## Qt Signal Documentation

```
void aboutToActivate ()
```

这是该信号的默认超载。

[QMdiSubWindow](qmdisubwindow.html)发出这个信号之前立即被激活。后的子窗口已经被激活，则[QMdiArea](qmdiarea.html)管理该子窗口也将放出[subWindowActivated()](qmdiarea.html#subWindowActivated)信号。

**See also** [QMdiArea.subWindowActivated](qmdiarea.html#subWindowActivated)（ ） 。

```
void windowStateChanged (Qt::WindowStates,Qt::WindowStates)
```

这是该信号的默认超载。

[QMdiSubWindow](qmdisubwindow.html)之后，窗口状态的改变会发出这个信号。_oldState_是窗口状态才改变，_newState_是新的，目前的状态。