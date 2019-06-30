# QMenu Class Reference

## [[QtGui](index.htm) module]

菜单QMenu类提供了一个菜单部件在菜单栏，上下文菜单，和其他弹出菜单中使用。[More...](#details)

继承[QWidget](qwidget.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `__init__ (self, QString title, QWidget parent = None)`
*   `QAction actionAt (self, QPoint)`
*   `actionEvent (self, QActionEvent)`
*   `QRect actionGeometry (self, QAction)`
*   `QAction activeAction (self)`
*   `addAction (self, QAction action)`
*   `QAction addAction (self, QString text)`
*   `QAction addAction (self, QIcon icon, QString text)`
*   `QAction addAction (self, QString text, QObject receiver, SLOT()SLOT() member, QKeySequence shortcut = 0)`
*   `QAction addAction (self, QString text, callable receiver, QKeySequence shortcut = 0)`
*   `QAction addAction (self, QIcon icon, QString text, QObject receiver, SLOT()SLOT() member, QKeySequence shortcut = 0)`
*   `QAction addAction (self, QIcon icon, QString text, callable receiver, QKeySequence shortcut = 0)`
*   `QAction addMenu (self, QMenu menu)`
*   `QMenu addMenu (self, QString title)`
*   `QMenu addMenu (self, QIcon icon, QString title)`
*   `QAction addSeparator (self)`
*   `changeEvent (self, QEvent)`
*   `clear (self)`
*   `int columnCount (self)`
*   `QAction defaultAction (self)`
*   `enterEvent (self, QEvent)`
*   `bool event (self, QEvent)`
*   `QAction exec_ (self)`
*   `QAction exec_ (self, QPoint p, QAction action = None)`
*   `bool focusNextPrevChild (self, bool next)`
*   `hideEvent (self, QHideEvent)`
*   `hideTearOffMenu (self)`
*   `QIcon icon (self)`
*   `initStyleOption (self, QStyleOptionMenuItem option, QAction action)`
*   `QAction insertMenu (self, QAction before, QMenu menu)`
*   `QAction insertSeparator (self, QAction before)`
*   `bool isEmpty (self)`
*   `bool isTearOffEnabled (self)`
*   `bool isTearOffMenuVisible (self)`
*   `keyPressEvent (self, QKeyEvent)`
*   `leaveEvent (self, QEvent)`
*   `QAction menuAction (self)`
*   `mouseMoveEvent (self, QMouseEvent)`
*   `mousePressEvent (self, QMouseEvent)`
*   `mouseReleaseEvent (self, QMouseEvent)`
*   `paintEvent (self, QPaintEvent)`
*   `popup (self, QPoint p, QAction action = None)`
*   `bool separatorsCollapsible (self)`
*   `setActiveAction (self, QAction act)`
*   `setDefaultAction (self, QAction)`
*   `setIcon (self, QIcon icon)`
*   `setNoReplayFor (self, QWidget widget)`
*   `setSeparatorsCollapsible (self, bool collapse)`
*   `setTearOffEnabled (self, bool)`
*   `setTitle (self, QString title)`
*   `QSize sizeHint (self)`
*   `timerEvent (self, QTimerEvent)`
*   `QString title (self)`
*   `wheelEvent (self, QWheelEvent)`

### Static Methods

*   `QAction exec_ (list-of-QAction actions, QPoint pos, QAction action = None)`
*   `QAction exec_ (list-of-QAction actions, QPoint pos, QAction at, QWidget parent)`

### Qt Signals

*   `void aboutToHide ()`
*   `void aboutToShow ()`
*   `void hovered (QAction *)`
*   `void triggered (QAction *)`

* * *

## Detailed Description

菜单QMenu类提供了一个菜单部件在菜单栏，上下文菜单，和其他弹出菜单中使用。

menu小部件是一个选择菜单。它可以是一个菜单栏下拉菜单或独立的上下文菜单。当用户点击相应的项目或按下指定的快捷键下拉菜单显示的菜单栏。使用[QMenuBar.addMenu](qmenubar.html#addMenu)（ ）插入一个菜单到菜单栏。上下文菜单通常是由一些特殊的键盘按键或单击鼠标右键调用。它们可以非同步地执行[popup](qmenu.html#popup)（）或与同步[exec_](qmenu.html#exec)（ ） 。菜单也可以响应按键操作调用，这些都是一样的上下文菜单，除了它们是如何被调用。

| ![](../img/plastique-menu.png) | ![](../img/windowsxp-menu.png) | ![](../img/macintosh-menu.png) |

图。在显示的菜单[Plastique widget style](index.htm)，[Windows XP widget style](index.htm)和[Macintosh widget style](index.htm)。

### Actions

菜单包括行动项目清单。操作时添加的[addAction](qmenu.html#addAction)（ ）[addActions](qwidget.html#addActions)（）和[insertAction](qwidget.html#insertAction)（）函数。一个动作是垂直表示和呈现[QStyle](qstyle.html)。此外，行动可以有一个文本标籤，画在最左侧的可选图标，快捷键序列，例如“ Ctrl + X键” 。

通过菜单持有的现有动作可以与发现[actions](qwidget.html#actions)（ ） 。

有四种操作项目：分隔符，即显示一个子菜单的操作，窗口小部件和执行操作的动作。分离器插入[addSeparator](qmenu.html#addSeparator)（ ） ，与子菜单[addMenu](qmenu.html#addMenu)（ ） ，和所有其他项目都被视为行动项目。

当插入操作项目您通常会指定一个接收器和一个插槽。每当产品的接收器将被notifed[triggered()](qaction.html#triggered)。此外，菜单QMenu提供两个信号，[activated](index.htm#activated)（）和[highlighted](index.htm#highlighted)（），该信号的[QAction](qaction.html)这是从菜单触发。

你清除一个菜单[clear](qmenu.html#clear)（）和remove个别行动项目[removeAction](qwidget.html#removeAction)（ ） 。

一个菜单QMenu还可以提供一个分离式菜单。可撕式菜单是包含菜单的副本的顶层窗口。这使得它可以为用户“撕下”常用菜单，并把它们在屏幕上方便的地方进行定位。如果你想为一个特定的菜单中选择此功能，将可撕式手柄[setTearOffEnabled](qmenu.html#tearOffEnabled-prop)（ ） 。当使用撕下菜单，记住，这个概念通常不使用在Microsoft Windows这样一些用户可能并不熟悉它。请考虑使用[QToolBar](qtoolbar.html)代替。

窗口小部件可以被插入到菜单与[QWidgetAction](qwidgetaction.html)类。此类的实例是用来装小部件，并插入菜单与[addAction](qmenu.html#addAction)（ ）重载采用一个[QAction](qaction.html)。

反之，操作可以被添加到窗口小部件与[addAction](qmenu.html#addAction)（ ）[addActions](qwidget.html#addActions)（）和[insertAction](qwidget.html#insertAction)（）函数。

**Warning:**为了使屏幕上的菜单QMenu可见，[exec_](qmenu.html#exec)（）或[popup](qmenu.html#popup)（ ）应该被用来代替[show](qwidget.html#show)（ ） 。

### QMenu on Qt for Windows CE

如果菜单集成到本机的菜单栏上的Windows Mobile不支持的信号： aboutToHide （ ） ， aboutToShow （）和徘徊（ ） 。这是不可能在Windows Mobile上的本机菜单显示一个图标。

### QMenu on Mac OS X with Qt build against Cocoa

菜单QMenu可以在菜单/菜单栏插入一次。后来插入不会有任何影响或将导致禁用的菜单项。

请参阅[Menus](index.htm)示例如何使用示例[QMenuBar](qmenubar.html)和菜单QMenu在你的应用程序。

**Important inherited functions:** [addAction](qmenu.html#addAction)（ ）[removeAction](qwidget.html#removeAction)（ ）[clear](qmenu.html#clear)（ ）[addSeparator](qmenu.html#addSeparator)（）和[addMenu](qmenu.html#addMenu)（ ） 。

* * *

## Method Documentation

```
QMenu.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个菜单与父_parent_。

虽然一个弹出菜单始终是一个顶级窗口部件，如果父对象被弹出菜单会时父母被破坏（与任何其他删除[QObject](qobject.html)） 。

```
QMenu.__init__ (self, QString title, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个菜单，一个_title_和_parent_。

虽然一个弹出菜单始终是一个顶级窗口部件，如果父对象被弹出菜单会时父母被破坏（与任何其他删除[QObject](qobject.html)） 。

**See also** [title](qmenu.html#title-prop)。

```
QAction QMenu.actionAt (self, QPoint)
```

[

返回位于项目_pt_;返回0 ，如果有有没有项目。

```
QMenu.actionEvent (self, QActionEvent)
```

](qaction.html)

[从重新实现](qaction.html)[QWidget.actionEvent](qwidget.html#actionEvent)（ ） 。

```
QRect QMenu.actionGeometry (self, QAction)
```

[

返回行动的几何形状_act_。

](qrect.html)

```
QAction QMenu.activeAction (self)
```

[

返回当前突出显示的动作，或者0，如果不采取行动是当前突出显示。

](qaction.html)

[**See also**](qaction.html) [setActiveAction](qmenu.html#setActiveAction)（ ） 。

```
QMenu.addAction (self, QAction action)
```

这是一个重载函数。

用这种便利函数创建一个新动作_text_。该函数将新创建的行动，行动的菜单的列表中，并返回它。

**See also** [QWidget.addAction](qwidget.html#addAction)（ ） 。

```
QAction QMenu.addAction (self, QString text)
```

[

这是一个重载函数。

这个方便的功能创建了一个新动作_icon_有的_text_。该函数将新创建的行动，行动的菜单的列表中，并返回它。

](qaction.html)

[**See also**](qaction.html) [QWidget.addAction](qwidget.html#addAction)（ ） 。

```
QAction QMenu.addAction (self, QIcon icon, QString text)
```

[

这是一个重载函数。

](qaction.html)

[这种便利函数创建一个文本新动作_text_和一个可选的快捷方式_shortcut_。动作的](qaction.html)[triggered()](qaction.html#triggered)信号被连接到_receiver_的_member_插槽。该函数将新创建的行动，行动的菜单的列表并返回它。

**See also** [QWidget.addAction](qwidget.html#addAction)（ ） 。

```
QAction QMenu.addAction (self, QString text, QObject receiver, SLOT()SLOT() member, QKeySequence shortcut = 0)
```

[

这是一个重载函数。

](qaction.html)

[这个方便的功能创建了一个新动作_icon_有的_text_和一个可选的快捷方式_shortcut_。动作的](qaction.html)[triggered()](qaction.html#triggered)信号被连接到_member_的槽_receiver_对象。该函数将新创建的行动，行动的菜单的列表中，并返回它。

**See also** [QWidget.addAction](qwidget.html#addAction)（ ） 。

```
QAction QMenu.addAction (self, QString text, callable receiver, QKeySequence shortcut = 0)
```

[

这是一个重载函数。

追加行动_action_于诉讼的菜单的列表。

](qaction.html)

[**See also**](qaction.html) [QMenuBar.addAction](qmenubar.html#addAction)（）和[QWidget.addAction](qwidget.html#addAction)（ ） 。

```
QAction QMenu.addAction (self, QIcon icon, QString text, QObject receiver, SLOT()SLOT() member, QKeySequence shortcut = 0)
```

[](qaction.html)

```
QAction QMenu.addAction (self, QIcon icon, QString text, callable receiver, QKeySequence shortcut = 0)
```

[](qaction.html)

```
QAction QMenu.addMenu (self, QMenu menu)
```

[](qaction.html)

[这个方便的功能增加_menu_作为一个子菜单，此菜单。它返回_menu_的](qaction.html)[menuAction](qmenu.html#menuAction)（ ） 。此菜单不采取所有权_menu_。

**See also** [QWidget.addAction](qwidget.html#addAction)（）和[QMenu.menuAction](qmenu.html#menuAction)（ ） 。

```
QMenu QMenu.addMenu (self, QString title)
```

[](qmenu.html)

[添加一个新的](qmenu.html)[QMenu](qmenu.html)同_title_到菜单。菜单采用了菜单的所有权。返回新菜单。

**See also** [QWidget.addAction](qwidget.html#addAction)（）和[QMenu.menuAction](qmenu.html#menuAction)（ ） 。

```
QMenu QMenu.addMenu (self, QIcon icon, QString title)
```

[](qmenu.html)

[添加一个新的](qmenu.html)[QMenu](qmenu.html)同_icon_和_title_到菜单。菜单采用了菜单的所有权。返回新菜单。

**See also** [QWidget.addAction](qwidget.html#addAction)（）和[QMenu.menuAction](qmenu.html#menuAction)（ ） 。

```
QAction QMenu.addSeparator (self)
```

[](qaction.html)

[这个便利函数创建一个新的分隔作用，即一个行动](qaction.html)[QAction.isSeparator](qaction.html#isSeparator)（ ）返回True ，并添加了新的行动，行动该菜单的列表。它返回新创建的动作。

**See also** [QWidget.addAction](qwidget.html#addAction)（ ） 。

```
QMenu.changeEvent (self, QEvent)
```

从重新实现[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
QMenu.clear (self)
```

删除所有菜单的操作。通过菜单，而不是在任何其他部件所示资的行动都将被删除。

**See also** [removeAction](qwidget.html#removeAction)（ ） 。

```
int QMenu.columnCount (self)
```

如果一个菜单不适合在屏幕上勾画出自己，以便它不适合。它的风格取决于什么布局方式（例如，在Windows上，将使用多个列） 。

该函数返回的列所必需的数量。

```
QAction QMenu.defaultAction (self)
```

[

返回当前的默认操作。

](qaction.html)

[**See also**](qaction.html) [setDefaultAction](qmenu.html#setDefaultAction)（ ） 。

```
QMenu.enterEvent (self, QEvent)
```

从重新实现[QWidget.enterEvent](qwidget.html#enterEvent)（ ） 。

```
bool QMenu.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QAction QMenu.exec_ (self)
```

[

执行此菜单同步。

这等效于`exec(pos())`。

](qaction.html)

[这将返回触发](qaction.html)[QAction](qaction.html)无论是在弹出菜单或它的一个子菜单，或者0，如果没有项目被触发（通常是因为用户按下Esc键） 。

在大多数情况下，你要自己指定的位置，例如，当前鼠标位置：

```
 exec([QCursor](qcursor.html).pos());

```

或对齐到一个小部件：

```
 exec(somewidget.mapToGlobal([QPoint](qpoint.html)(0,0)));

```

或在反应的[QMouseEvent](qmouseevent.html)* E：

```
 exec(e->globalPos());

```

```
QAction QMenu.exec_ (self, QPoint p, QAction action = None)
```

[

这是一个重载函数。

执行此菜单同步。

](qaction.html)

[弹出的菜单中，这样的动作_action_将在指定_global_位置_p_。翻译一个小部件的局部坐标系到全局坐标，使用](qaction.html)[QWidget.mapToGlobal](qwidget.html#mapToGlobal)（ ） 。

这将返回触发[QAction](qaction.html)无论是在弹出菜单或它的一个子菜单，或者0，如果没有项目被触发（通常是因为用户按下Esc键） 。

请注意，所有信号都发出如常。如果连接了[QAction](qaction.html)到一个时隙，并调用菜单的[exec_](qmenu.html#exec)（ ） ，你既可以通过信号槽连接，并在返回值获得的结果[exec_](qmenu.html#exec)（ ） 。

常见的用法是在当前鼠标位置来定位菜单：

```
 exec_([QCursor](qcursor.html).pos());

```

或对齐到一个小部件：

```
 exec_(somewidget.mapToGlobal([QPoint](qpoint.html)(0, 0)));

```

或在反应的[QMouseEvent](qmouseevent.html)* E：

```
 exec_(e->globalPos());

```

当定位一个菜单[exec_](qmenu.html#exec)（）或[popup](qmenu.html#popup)（ ） ，请记住，你不能依赖于菜单的电流[size](qwidget.html#size-prop)（ ） 。出于性能原因，菜单调整其大小只在必要时。所以在很多情况下，前和后显示的大小是不同的。相反，使用[sizeHint](qmenu.html#sizeHint)（ ），计算适当的大小取决于菜单的当前内容。

**See also** [popup](qmenu.html#popup)（）和[QWidget.mapToGlobal](qwidget.html#mapToGlobal)（ ） 。

```
QAction QMenu.exec_ (list-of-QAction actions, QPoint pos, QAction action = None)
```

[

这是一个重载函数。

执行菜单同步。

](qaction.html)

[菜单的操作由列表中指定的_actions_。该菜单会弹出让指定的动作，_at_，出现在全球的地位_pos_。如果_at_没有指定，那么在菜单出现在位置_pos_。_parent_是菜单的父控件，指定母会时提供上下文_pos_还不足以决定在哪里菜单应该去（例如，与多个桌面或当父被嵌入在](qaction.html)[QGraphicsView](qgraphicsview.html)） 。

该函数返回触发[QAction](qaction.html)无论是在弹出菜单或它的一个子菜单，或者0，如果没有项目被触发（通常是因为用户按下Esc键） 。

这相当于：

```
 [QMenu](qmenu.html) menu;
 [QAction](qaction.html) *at = actions[0]; // Assumes actions is not empty
 foreach ([QAction](qaction.html) *a, actions)
     menu.addAction(a);
 menu.exec_(pos, at);

```

**See also** [popup](qmenu.html#popup)（）和[QWidget.mapToGlobal](qwidget.html#mapToGlobal)（ ） 。

```
QAction QMenu.exec_ (list-of-QAction actions, QPoint pos, QAction at, QWidget parent)
```

[

这是一个重载函数。

执行菜单同步。

菜单的操作由列表中指定的_actions_。该菜单会弹出让指定的动作，_at_，出现在全球的地位_pos_。如果_at_没有指定，那么在菜单出现在位置_pos_。

](qaction.html)

[该函数返回触发](qaction.html)[QAction](qaction.html)无论是在弹出菜单或它的一个子菜单，或者0，如果没有项目被触发（通常是因为用户按下Esc键） 。

这相当于：

```
 [QMenu](qmenu.html) menu;
 [QAction](qaction.html) *at = actions[0]; // Assumes actions is not empty
 foreach ([QAction](qaction.html) *a, actions)
     menu.addAction(a);
 menu.exec_(pos, at);

```

**See also** [popup](qmenu.html#popup)（）和[QWidget.mapToGlobal](qwidget.html#mapToGlobal)（ ） 。

```
bool QMenu.focusNextPrevChild (self, bool next)
```

从重新实现[QWidget.focusNextPrevChild](qwidget.html#focusNextPrevChild)（ ） 。

```
QMenu.hideEvent (self, QHideEvent)
```

从重新实现[QWidget.hideEvent](qwidget.html#hideEvent)（ ） 。

```
QMenu.hideTearOffMenu (self)
```

此功能将强行隐藏撕下菜单使得它从用户的桌面上消失。

**See also** [isTearOffMenuVisible](qmenu.html#isTearOffMenuVisible)（）和[isTearOffEnabled](qmenu.html#tearOffEnabled-prop)（ ） 。

```
QIcon QMenu.icon (self)
```

[

```
QMenu.initStyleOption (self, QStyleOptionMenuItem option, QAction action)
```

](qicon.html)

[初始化_option_从这个菜单和信息的价值_action_。当他们需要一个这种方法是有用的子类](qicon.html)[QStyleOptionMenuItem](qstyleoptionmenuitem.html)，但不希望在所有的信息填写自己。

**See also** [QStyleOption.initFrom](qstyleoption.html#initFrom)（）和[QMenuBar.initStyleOption](qmenubar.html#initStyleOption)（ ） 。

```
QAction QMenu.insertMenu (self, QAction before, QMenu menu)
```

[](qaction.html)

[这个方便的功能插件_menu_行动之前，_before_并返回菜单](qaction.html)[menuAction](qmenu.html#menuAction)（ ） 。

**See also** [QWidget.insertAction](qwidget.html#insertAction)（）和[addMenu](qmenu.html#addMenu)（ ） 。

```
QAction QMenu.insertSeparator (self, QAction before)
```

[](qaction.html)

[这个便利函数创建一个新的分隔作用，即一个行动](qaction.html)[QAction.isSeparator](qaction.html#isSeparator)（ ）返回True 。该函数插入新创建的行动变成行动之前行动这个菜单的列表_before_并返回它。

**See also** [QWidget.insertAction](qwidget.html#insertAction)（）和[addSeparator](qmenu.html#addSeparator)（ ） 。

```
bool QMenu.isEmpty (self)
```

如果有，否则插入菜单中没有明显的动作，假，则返回True 。

这个函数中引入了Qt 4.2中。

**See also** [QWidget.actions](qwidget.html#actions)（ ） 。

```
bool QMenu.isTearOffEnabled (self)
```

```
bool QMenu.isTearOffMenuVisible (self)
```

当一个菜单被撕下第二个菜单显示来显示菜单内容在一个新窗口。当菜单在此模式下，菜单是可见的，则返回True ，否则返回False 。

**See also** [hideTearOffMenu](qmenu.html#hideTearOffMenu)（）和[isTearOffEnabled](qmenu.html#tearOffEnabled-prop)（ ） 。

```
QMenu.keyPressEvent (self, QKeyEvent)
```

从重新实现[QWidget.keyPressEvent](qwidget.html#keyPressEvent)（ ） 。

```
QMenu.leaveEvent (self, QEvent)
```

从重新实现[QWidget.leaveEvent](qwidget.html#leaveEvent)（ ） 。

```
QAction QMenu.menuAction (self)
```

[

返回与此菜单关联的动作。

```
QMenu.mouseMoveEvent (self, QMouseEvent)
```

](qaction.html)

[从重新实现](qaction.html)[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

```
QMenu.mousePressEvent (self, QMouseEvent)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

```
QMenu.mouseReleaseEvent (self, QMouseEvent)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

```
QMenu.paintEvent (self, QPaintEvent)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QMenu.popup (self, QPoint p, QAction action = None)
```

显示的菜单，使动作_atAction_将在指定_global_位置_p_。翻译一个小部件的局部坐标系到全局坐标，使用[QWidget.mapToGlobal](qwidget.html#mapToGlobal)（ ） 。

当定位一个菜单[exec_](qmenu.html#exec)（ ）或弹出（ ） ，请记住，你不能依赖于菜单的电流[size](qwidget.html#size-prop)（ ） 。出于性能原因，菜单调整其大小只有当必要的，所以在很多情况下，前，后演出的规模是不同的。相反，使用[sizeHint](qmenu.html#sizeHint)（ ），计算适当的大小取决于菜单的当前内容。

**See also** [QWidget.mapToGlobal](qwidget.html#mapToGlobal)（）和[exec_](qmenu.html#exec)（ ） 。

```
bool QMenu.separatorsCollapsible (self)
```

```
QMenu.setActiveAction (self, QAction act)
```

设置当前突出显示的动作_act_。

**See also** [activeAction](qmenu.html#activeAction)（ ） 。

```
QMenu.setDefaultAction (self, QAction)
```

此设置的默认操作为_act_。默认动作可以具有视觉提示，这取决于当前[QStyle](qstyle.html)。默认动作通常表示在默认情况下，当发生跌落会发生什么。

**See also** [defaultAction](qmenu.html#defaultAction)（ ） 。

```
QMenu.setIcon (self, QIcon icon)
```

```
QMenu.setNoReplayFor (self, QWidget widget)
```

```
QMenu.setSeparatorsCollapsible (self, bool collapse)
```

```
QMenu.setTearOffEnabled (self, bool)
```

```
QMenu.setTitle (self, QString title)
```

```
QSize QMenu.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

```
QMenu.timerEvent (self, QTimerEvent)
```

从重新实现[QObject.timerEvent](qobject.html#timerEvent)（ ） 。

```
QString QMenu.title (self)
```

```
QMenu.wheelEvent (self, QWheelEvent)
```

从重新实现[QWidget.wheelEvent](qwidget.html#wheelEvent)（ ） 。

* * *

## Qt Signal Documentation

```
void aboutToHide ()
```

这是该信号的默认超载。

这个信号被发射之前的菜单，从用户隐藏。

这个函数中引入了Qt 4.2中。

**See also** [aboutToShow](qmenu.html#aboutToShow)（）和[hide](qwidget.html#hide)（ ） 。

```
void aboutToShow ()
```

这是该信号的默认超载。

这个信号被发射的菜单被显示给用户之前。

**See also** [aboutToHide](qmenu.html#aboutToHide)（）和[show](qwidget.html#show)（ ） 。

```
void hovered (QAction *)
```

这是该信号的默认超载。

当一个菜单操作高亮显示这个信号被发射;_action_是导致该信号被发射的操作。

通常这是用来更新状态信息。

**See also** [triggered](qmenu.html#triggered)（）和[QAction.hovered](qaction.html#hovered)（ ） 。

```
void triggered (QAction *)
```

这是该信号的默认超载。

当在该菜单中的操作被触发这个信号被发射。

_action_是导致该信号被发射的操作。

通常情况下，在连接每个菜单操作的[triggered()](qaction.html#triggered)信号到其自己的定制插槽，但有时你会想几个动作连接到一个单一的插槽，例如，当你有一组密切相关的动作，如“左对齐” ， “中心” ， “右对齐” 。

**Note:**这个信号被发射在一个层次中的父主菜单。因此，只有父菜单需要连接到一个槽;子菜单无需进行连接。

**See also** [hovered](qmenu.html#hovered)（）和[QAction.triggered](qaction.html#triggered)（ ） 。