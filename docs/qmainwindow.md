# QMainWindow Class Reference

## [[QtGui](index.htm) module]

QMainWindow类提供了一个主应用程序窗口。[More...](#details)

继承[QWidget](qwidget.html)。

### Types

*   `enum DockOption { AnimatedDocks, AllowNestedDocks, AllowTabbedDocks, ForceTabbedDocks, VerticalTabs }`
*   `class **[DockOptions](index.htm)**`

### Methods

*   `__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)`
*   `addDockWidget (self, Qt.DockWidgetArea area, QDockWidget dockwidget)`
*   `addDockWidget (self, Qt.DockWidgetArea area, QDockWidget dockwidget, Qt.Orientation orientation)`
*   `addToolBar (self, Qt.ToolBarArea area, QToolBar toolbar)`
*   `addToolBar (self, QToolBar toolbar)`
*   `QToolBar addToolBar (self, QString title)`
*   `addToolBarBreak (self, Qt.ToolBarArea area = Qt.TopToolBarArea)`
*   `QWidget centralWidget (self)`
*   `contextMenuEvent (self, QContextMenuEvent event)`
*   `Qt.DockWidgetArea corner (self, Qt.Corner corner)`
*   `QMenu createPopupMenu (self)`
*   `DockOptions dockOptions (self)`
*   `Qt.DockWidgetArea dockWidgetArea (self, QDockWidget dockwidget)`
*   `bool documentMode (self)`
*   `bool event (self, QEvent event)`
*   `QSize iconSize (self)`
*   `insertToolBar (self, QToolBar before, QToolBar toolbar)`
*   `insertToolBarBreak (self, QToolBar before)`
*   `bool isAnimated (self)`
*   `bool isDockNestingEnabled (self)`
*   `bool isSeparator (self, QPoint pos)`
*   `QMenuBar menuBar (self)`
*   `QWidget menuWidget (self)`
*   `removeDockWidget (self, QDockWidget dockwidget)`
*   `removeToolBar (self, QToolBar toolbar)`
*   `removeToolBarBreak (self, QToolBar before)`
*   `bool restoreDockWidget (self, QDockWidget dockwidget)`
*   `bool restoreState (self, QByteArray state, int version = 0)`
*   `QByteArray saveState (self, int version = 0)`
*   `setAnimated (self, bool enabled)`
*   `setCentralWidget (self, QWidget widget)`
*   `setCorner (self, Qt.Corner corner, Qt.DockWidgetArea area)`
*   `setDockNestingEnabled (self, bool enabled)`
*   `setDockOptions (self, DockOptions options)`
*   `setDocumentMode (self, bool enabled)`
*   `setIconSize (self, QSize iconSize)`
*   `setMenuBar (self, QMenuBar menubar)`
*   `setMenuWidget (self, QWidget menubar)`
*   `setStatusBar (self, QStatusBar statusbar)`
*   `setTabPosition (self, Qt.DockWidgetAreas areas, QTabWidget.TabPosition tabPosition)`
*   `setTabShape (self, QTabWidget.TabShape tabShape)`
*   `setToolButtonStyle (self, Qt.ToolButtonStyle toolButtonStyle)`
*   `setUnifiedTitleAndToolBarOnMac (self, bool set)`
*   `splitDockWidget (self, QDockWidget after, QDockWidget dockwidget, Qt.Orientation orientation)`
*   `QStatusBar statusBar (self)`
*   `list-of-QDockWidget tabifiedDockWidgets (self, QDockWidget dockwidget)`
*   `tabifyDockWidget (self, QDockWidget first, QDockWidget second)`
*   `QTabWidget.TabPosition tabPosition (self, Qt.DockWidgetArea area)`
*   `QTabWidget.TabShape tabShape (self)`
*   `Qt.ToolBarArea toolBarArea (self, QToolBar toolbar)`
*   `bool toolBarBreak (self, QToolBar toolbar)`
*   `Qt.ToolButtonStyle toolButtonStyle (self)`
*   `bool unifiedTitleAndToolBarOnMac (self)`

### Qt Signals

*   `void iconSizeChanged (const QSize&)`
*   `void toolButtonStyleChanged (Qt::ToolButtonStyle)`

* * *

## Detailed Description

QMainWindow类提供了一个主应用程序窗口。

### Qt Main Window Framework

一个主窗口提供了构建应用程序的用户界面的框架。 Qt拥有的QMainWindow和其[related classes](index.htm)主窗口管理。 QMainWindow中有自己的布局中，您可以添加[QToolBar](qtoolbar.html)秒，[QDockWidget](qdockwidget.html)秒，一个[QMenuBar](qmenubar.html)和[QStatusBar](qstatusbar.html)。布局具有能够由任何类型的窗口小部件所佔据的中心区域。你可以看到下面的布局的图像。

![](../img/mainwindowlayout.png)

**Note:**创建没有中央部件的主窗口，不支持。你必须有一个中心窗体，即使它只是一个佔位符。

### Creating Main Window Components

一个核心部件，通常是一个标准的Qt窗口部件，如[QTextEdit](qtextedit.html)或[QGraphicsView](qgraphicsview.html)。自定义部件也可用于高级应用。您设置的中央小部件`setCentralWidget()`。

主窗口有一个单一（ SDI ）或多个（ MDI）的文档界面。您可以通过使用创建Qt中MDI应用程序[QMdiArea](qmdiarea.html)作为中央部件。

现在，我们将检查每一个可以添加到主窗口中的其他部件。我们就如何创建和添加他们的例子。

#### Creating Menus

Qt的实现在菜单[QMenu](qmenu.html)和QMainWindow的让他们在一个[QMenuBar](qmenubar.html)。[QAction](qaction.html)s的加入到菜单，它们显示为菜单项。

你可以通过调用添加新的菜单到主窗口的菜单栏`menuBar()`，它返回[QMenuBar](qmenubar.html)为窗口，然后添加一个菜单[QMenuBar.addMenu](qmenubar.html#addMenu)（ ） 。

QMainWindow中带有一个默认的菜单栏，但你也可以设置一个与自己`setMenuBar()`。如果你想实现一个自定义菜单栏（即不使用[QMenuBar](qmenubar.html)小工具） ，你可以用它设置`setMenuWidget()`。

如何创建菜单的示例如下：

```
 void MainWindow.createMenus()
 {
     fileMenu = menuBar()->addMenu(tr("&File"));
     fileMenu->addAction(newAct);
     fileMenu->addAction(openAct);
     fileMenu->addAction(saveAct);

```

该`createPopupMenu()`函数创建一个弹出式菜单，当主窗口接收上下文菜单事件。默认的实现产生与从码头小部件和工具栏的可复操作的菜单。您可以重新实现`createPopupMenu()`自定义菜单。

#### Creating Toolbars

工具栏的实现[QToolBar](qtoolbar.html)类。你将工具栏添加到主窗口`addToolBar()`。

您可以通过将其分配到特定的控制工具栏的初始位置[Qt.ToolBarArea](qt.html#ToolBarArea-enum)。您可以通过插入一个工具栏断裂分割的区域 - 认为这是在文本编辑换行符 - 与`addToolBarBreak()` or `insertToolBarBreak()`。您还可以通过与用户的位置限制[QToolBar.setAllowedAreas](qtoolbar.html#allowedAreas-prop)（）和[QToolBar.setMovable](qtoolbar.html#movable-prop)（ ） 。

工具栏图标的大小可以检索与`iconSize()`。的大小是依赖于平台的，你可以设置一个固定大小`setIconSize()`。你可以改变所有工具按钮在工具栏的外观`setToolButtonStyle()`。

工具栏上创建的示例如下：

```
 void MainWindow.createToolBars()
 {
     fileToolBar = addToolBar(tr("File"));
     fileToolBar->addAction(newAct);

```

#### Creating Dock Widgets

底座部件都在实施[QDockWidget](qdockwidget.html)类。一个可停靠小部件是一个可以停靠到主窗口的窗口。您添加小部件码头到主窗口`addDockWidget()`。

有四个底座部件领域给予的[Qt.DockWidgetArea](qt.html#DockWidgetArea-enum)枚举：左，右，顶部和底部。您可以指定哪些码头小工具区域，应该佔据的区域中重叠的角落`setCorner()`。默认情况下每个区域只能包含一行坞窗口小部件（垂直或水平） ，但如果你启用拼图与`setDockNestingEnabled()`，停靠小部件可以在任一方向被添加。

两底座部件也可以堆叠在彼此的顶部上。一[QTabBar](qtabbar.html)然后，用于选择哪一个应该被显示的窗口小部件。

我们给出了如何创建和添加停靠小部件到主窗口的例子：

```
     [QDockWidget](qdockwidget.html) *dockWidget = new [QDockWidget](qdockwidget.html)(tr("Dock Widget"), this);
     dockWidget->setAllowedAreas([Qt](qt.html).LeftDockWidgetArea |
                                 [Qt](qt.html).RightDockWidgetArea);
     dockWidget->setWidget(dockWidgetContents);
     addDockWidget([Qt](qt.html).LeftDockWidgetArea, dockWidget);

```

#### The Status Bar

你可以设置一个状态栏与`setStatusBar()`，但一个是创建的第一次`statusBar()`（返回主窗口的状态栏）被调用。看[QStatusBar](qstatusbar.html)关于如何使用它的信息。

### Storing State

QMainWindow中可以存储与布局的状态`saveState()`它可在以后被检索以`restoreState()`。它的位置和大小存储工具栏和停靠窗口小部件（相对于主窗口的大小） 。

* * *

## Type Documentation

```
QMainWindow.DockOption
```

此枚举包含指定的停靠行为的标志[QMainWindow](qmainwindow.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QMainWindow.AnimatedDocks` | `0x01` | 相同的[animated](qmainwindow.html#animated-prop)属性。 |
| `QMainWindow.AllowNestedDocks` | `0x02` | 相同的[dockNestingEnabled](qmainwindow.html#dockNestingEnabled-prop)属性。 |
| `QMainWindow.AllowTabbedDocks` | `0x04` | 用户可以在“上面”的另一个摔个码头部件。这两个部件堆叠和标籤栏出现选择哪一个是可见的。 |
| `QMainWindow.ForceTabbedDocks` | `0x08` | 每个码头区域包含标籤船坞部件的单一堆栈。换句话说，基座部件不能彼此相邻放置在一个基座区域。如果这个选项被设置， AllowNestedDocks没有效果。 |
| `QMainWindow.VerticalTabs` | `0x10` | 在主窗口的两侧的两个垂直的码头区展示自己的标籤垂直。如果未设置此选项，则所有码头区展示自己的标籤在底部。意味着AllowTabbedDocks 。另请参阅[setTabPosition](qmainwindow.html#setTabPosition)（ ） 。 |

这些选项仅控制如何停靠小部件可以在一个被丢弃[QMainWindow](qmainwindow.html)。他们不重新安排了被告席小部件，以符合指定的选项。出于这个原因，他们应该之前设置任何船坞小部件添加到主窗口。例外情况是在AnimatedDocks和VerticalTabs选项，其可以在任何时候设置。

这个枚举被引入或修改的Qt 4.3 。

该DockOptions类型是一个typedef为[QFlags](index.htm)\u003cDockOption\u003e 。它存储DockOption值的或组合。

* * *

## Method Documentation

```
QMainWindow.__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QMainWindow](qmainwindow.html)用给定的_parent_和指定的窗口小部件_flags_。

[QMainWindow](qmainwindow.html)设置[Qt.Window](qt.html#WindowType-enum)标志本身，并会因此总是被创建为一个顶级窗口部件。

```
QMainWindow.addDockWidget (self, Qt.DockWidgetArea area, QDockWidget dockwidget)
```

该_dockwidget_说法有它的所有权转移给Qt的。

将给定_dockwidget_到指定的_area_。

```
QMainWindow.addDockWidget (self, Qt.DockWidgetArea area, QDockWidget dockwidget, Qt.Orientation orientation)
```

该_dockwidget_说法有它的所有权转移给Qt的。

添加_dockwidget_在给定的_area_在由指定的方向_orientation_。

```
QMainWindow.addToolBar (self, Qt.ToolBarArea area, QToolBar toolbar)
```

该_toolbar_说法有它的所有权转移给Qt的。

添加_toolbar_到指定的_area_在这个主窗口。该_toolbar_被放置在当前工具栏块（即行）的端部。如果主窗口已经管理_toolbar_那么它只是将工具栏移动到_area_。

**See also** [insertToolBar](qmainwindow.html#insertToolBar)（ ）[addToolBarBreak](qmainwindow.html#addToolBarBreak)（）和[insertToolBarBreak](qmainwindow.html#insertToolBarBreak)（ ） 。

```
QMainWindow.addToolBar (self, QToolBar toolbar)
```

该_toolbar_说法有它的所有权转移给Qt的。

这是一个重载函数。

相当于调用addToolBar （中[Qt.TopToolBarArea](qt.html#ToolBarArea-enum)，_toolbar_）

```
QToolBar QMainWindow.addToolBar (self, QString title)
```

[

这是一个重载函数。

](qtoolbar.html)

[创建](qtoolbar.html)[QToolBar](qtoolbar.html)对象，其窗口标题设置为_title_，并将其插入到顶部的工具栏区域。

**See also** [setWindowTitle](qwidget.html#windowTitle-prop)（ ） 。

```
QMainWindow.addToolBarBreak (self, Qt.ToolBarArea area = Qt.TopToolBarArea)
```

增加了一个工具栏突破给定的_area_所有存在的其它对象之后。

```
QWidget QMainWindow.centralWidget (self)
```

[

返回中央部件的主窗口。该函数返回零，如果中央部件尚未确定。

](qwidget.html)

[**See also**](qwidget.html) [setCentralWidget](qmainwindow.html#setCentralWidget)（ ） 。

```
QMainWindow.contextMenuEvent (self, QContextMenuEvent event)
```

从重新实现[QWidget.contextMenuEvent](qwidget.html#contextMenuEvent)（ ） 。

```
Qt.DockWidgetArea QMainWindow.corner (self, Qt.Corner corner)
```

[

返回码头小工具区域，佔据指定_corner_。

](qt.html#DockWidgetArea-enum)

[**See also**](qt.html#DockWidgetArea-enum) [setCorner](qmainwindow.html#setCorner)（ ） 。

```
QMenu QMainWindow.createPopupMenu (self)
```

[

返回包含存在于主窗口中的工具栏和停靠小部件可选中条目的弹出式菜单。如果没有工具栏和停靠小部件存在，此函数返回一个空指针。

默认情况下，该功能是由所谓的主窗口当用户激活上下文菜单，通常通过一个工具栏或停靠控件上单击鼠标右键。

如果你想创建一个自定义弹出菜单，重新实现这个函数，并返回一个新创建的弹出式菜单。在弹出菜单的所有权被传递给调用者。

](qmenu.html)

[**See also**](qmenu.html) [addDockWidget](qmainwindow.html#addDockWidget)（ ）[addToolBar](qmainwindow.html#addToolBar)（）和[menuBar](qmainwindow.html#menuBar)（ ） 。

```
DockOptions QMainWindow.dockOptions (self)
```

[](index.htm)

```
Qt.DockWidgetArea QMainWindow.dockWidgetArea (self, QDockWidget dockwidget)
```

[](qt.html#DockWidgetArea-enum)

[返回](qt.html#DockWidgetArea-enum)[Qt.DockWidgetArea](qt.html#DockWidgetArea-enum)为_dockwidget_。如果_dockwidget_还没有被添加到主窗口，该函数返回`Qt.NoDockWidgetArea`。

**See also** [addDockWidget](qmainwindow.html#addDockWidget)（ ）[splitDockWidget](qmainwindow.html#splitDockWidget)（）和[Qt.DockWidgetArea](qt.html#DockWidgetArea-enum)。

```
bool QMainWindow.documentMode (self)
```

```
bool QMainWindow.event (self, QEvent event)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QSize QMainWindow.iconSize (self)
```

[

```
QMainWindow.insertToolBar (self, QToolBar before, QToolBar toolbar)
```

该_toolbar_说法有它的所有权转移给Qt的。

插入_toolbar_到由所佔用的面积_before_工具栏，使其出现之前它。例如，在正常的左到右的布局的操作中，这意味着_toolbar_会出现由指定的工具栏左侧_before_在水平工具栏区域。

](qsize.html)

[**See also**](qsize.html) [insertToolBarBreak](qmainwindow.html#insertToolBarBreak)（ ）[addToolBar](qmainwindow.html#addToolBar)（）和[addToolBarBreak](qmainwindow.html#addToolBarBreak)（ ） 。

```
QMainWindow.insertToolBarBreak (self, QToolBar before)
```

通过插入指定的工具栏前一个工具栏突破_before_。

```
bool QMainWindow.isAnimated (self)
```

```
bool QMainWindow.isDockNestingEnabled (self)
```

```
bool QMainWindow.isSeparator (self, QPoint pos)
```

```
QMenuBar QMainWindow.menuBar (self)
```

[

返回主窗口中的菜单栏。这个函数创建并返回一个空的菜单栏，如果菜单栏不存在。

](qmenubar.html)

[如果你想在一台Mac应用程序的所有窗口共享一个菜单栏，请不要使用此功能来创建它，因为在这里创建的菜单栏都会有这样的](qmenubar.html)[QMainWindow](qmainwindow.html)作为其母公司。相反，你必须创建一个没有父母，然后您可以将所有的Mac窗口之间共享一个菜单栏。创建一个父少菜单栏是这样的：

```
 [QMenuBar](qmenubar.html) *menuBar = new [QMenuBar](qmenubar.html)(0);

```

**See also** [setMenuBar](qmainwindow.html#setMenuBar)（ ） 。

```
QWidget QMainWindow.menuWidget (self)
```

[

返回主窗口中的菜单栏。如果菜单栏没有已建成但这个函数返回null。

这个函数中引入了Qt 4.2中。

](qwidget.html)

[**See also**](qwidget.html) [setMenuWidget](qmainwindow.html#setMenuWidget)（ ） 。

```
QMainWindow.removeDockWidget (self, QDockWidget dockwidget)
```

该_dockwidget_争论

移除_dockwidget_从主窗口的布局和隐藏它。注意，这个_dockwidget_ is _not_删除。

```
QMainWindow.removeToolBar (self, QToolBar toolbar)
```

移除_toolbar_从主窗口的布局和隐藏它。注意，这个_toolbar_ is _not_删除。

```
QMainWindow.removeToolBarBreak (self, QToolBar before)
```

通过删除指定的工具栏之前，先前插入一个工具栏突破_before_。

```
bool QMainWindow.restoreDockWidget (self, QDockWidget dockwidget)
```

恢复的状态_dockwidget_如果它被调用之后创建[restoreState](qmainwindow.html#restoreState)（ ） 。返回True如果状态得到恢复，否则返回False 。

**See also** [restoreState](qmainwindow.html#restoreState)（）和[saveState](qmainwindow.html#saveState)（ ） 。

```
bool QMainWindow.restoreState (self, QByteArray state, int version = 0)
```

恢复_state_这个主窗口的工具栏和dockwidgets 。该_version_号与存储在比较_state_。如果它们不匹配，则主窗口的状态保持不变，并且该函数返回`false`否则，该状态被恢复，并且该函数返回`true`。

要使用恢复保存几何[QSettings](qsettings.html)，你可以使用如下代码：

```
 void MainWindow.readSettings()
 {
     [QSettings](qsettings.html) settings("MyCompany", "MyApp");
     restoreGeometry(settings.value("myWidget/geometry").toByteArray());
     restoreState(settings.value("myWidget/windowState").toByteArray());
 }

```

**See also** [saveState](qmainwindow.html#saveState)（ ）[QWidget.saveGeometry](qwidget.html#saveGeometry)（ ）[QWidget.restoreGeometry](qwidget.html#restoreGeometry)（）和[restoreDockWidget](qmainwindow.html#restoreDockWidget)（ ） 。

```
QByteArray QMainWindow.saveState (self, int version = 0)
```

[

保存这个主窗口的工具栏和dockwidgets的当前状态。该_version_号码被存储作为数据的一部分。

](qbytearray.html)

[该](qbytearray.html)[objectName](qobject.html#objectName-prop)属性是用于识别每个[QToolBar](qtoolbar.html)和[QDockWidget](qdockwidget.html)。您应该确保这个属性是唯一的每个[QToolBar](qtoolbar.html)和[QDockWidget](qdockwidget.html)您添加到[QMainWindow](qmainwindow.html)

要恢复保存的状态，通过返回值和_version_数[restoreState](qmainwindow.html#restoreState)（ ） 。

要保存窗口关闭时的几何形状，可以实现这样一个close事件：

```
 void MyMainWindow.closeEvent([QCloseEvent](qcloseevent.html) *event)
 {
     [QSettings](qsettings.html) settings("MyCompany", "MyApp");
     settings.setValue("geometry", saveGeometry());
     settings.setValue("windowState", saveState());
     [QMainWindow](qmainwindow.html).closeEvent(event);
 }

```

**See also** [restoreState](qmainwindow.html#restoreState)（ ）[QWidget.saveGeometry](qwidget.html#saveGeometry)（）和[QWidget.restoreGeometry](qwidget.html#restoreGeometry)（ ） 。

```
QMainWindow.setAnimated (self, bool enabled)
```

这种方法也是一个Qt槽与C + +的签名`void setAnimated(bool)`。

```
QMainWindow.setCentralWidget (self, QWidget widget)
```

该_widget_说法有它的所有权转移给Qt的。

设置给定_widget_要在主窗口的中央窗口部件。

注意：[QMainWindow](qmainwindow.html)采取所有权_widget_指针并删除它在适当的时候。

**See also** [centralWidget](qmainwindow.html#centralWidget)（ ） 。

```
QMainWindow.setCorner (self, Qt.Corner corner, Qt.DockWidgetArea area)
```

设置给定坞窗口小部件_area_佔据了指定_corner_。

**See also** [corner](qmainwindow.html#corner)（ ） 。

```
QMainWindow.setDockNestingEnabled (self, bool enabled)
```

这种方法也是一个Qt槽与C + +的签名`void setDockNestingEnabled(bool)`。

```
QMainWindow.setDockOptions (self, DockOptions options)
```

```
QMainWindow.setDocumentMode (self, bool enabled)
```

```
QMainWindow.setIconSize (self, QSize iconSize)
```

```
QMainWindow.setMenuBar (self, QMenuBar menubar)
```

该_menubar_说法有它的所有权转移给Qt的。

设置主窗口菜单栏_menuBar_。

注意：[QMainWindow](qmainwindow.html)采取所有权_menuBar_指针并删除它在适当的时候。

**See also** [menuBar](qmainwindow.html#menuBar)（ ） 。

```
QMainWindow.setMenuWidget (self, QWidget menubar)
```

该_menubar_说法有它的所有权转移给Qt的。

设置主窗口菜单栏_menuBar_。

[QMainWindow](qmainwindow.html)采取所有权_menuBar_指针并删除它在适当的时候。

这个函数中引入了Qt 4.2中。

**See also** [menuWidget](qmainwindow.html#menuWidget)（ ） 。

```
QMainWindow.setStatusBar (self, QStatusBar statusbar)
```

该_statusbar_说法有它的所有权转移给Qt的。

设置主窗口的状态栏_statusbar_。

状态栏设置为0将在主窗口中删除它。需要注意的是[QMainWindow](qmainwindow.html)采取所有权_statusbar_指针并删除它在适当的时候。

**See also** [statusBar](qmainwindow.html#statusBar)（ ） 。

```
QMainWindow.setTabPosition (self, Qt.DockWidgetAreas areas, QTabWidget.TabPosition tabPosition)
```

设置为给定的码头插件的选项卡位置_areas_到指定的_tabPosition_。默认情况下，所有的停靠区域显示在底部的标籤。

**Note:**该[VerticalTabs](qmainwindow.html#DockOption-enum)码头选项将复盖此方法设置的制表位位置。

此功能被引入Qt的4.5 。

**See also** [tabPosition](qmainwindow.html#tabPosition)（）和[setTabShape](qmainwindow.html#tabShape-prop)（ ） 。

```
QMainWindow.setTabShape (self, QTabWidget.TabShape tabShape)
```

```
QMainWindow.setToolButtonStyle (self, Qt.ToolButtonStyle toolButtonStyle)
```

```
QMainWindow.setUnifiedTitleAndToolBarOnMac (self, bool set)
```

```
QMainWindow.splitDockWidget (self, QDockWidget after, QDockWidget dockwidget, Qt.Orientation orientation)
```

该_dockwidget_说法有它的所有权转移给Qt的。

分割复盖的空间_first_停靠小部件分为两个部分，移动_first_对接构件到第一部分中，并且使_second_停靠小部件进入第二部分。

该_orientation_指定如何将空间划分：一个[Qt.Horizontal](qt.html#Orientation-enum)拆分将第二码头Widget在第一个的右边，一个[Qt.Vertical](qt.html#Orientation-enum)分割放置下面的第一个，第二码头部件。

_Note_：如果_first_目前在一个标籤式的停靠区域，_second_将作为一个新的标籤，而不是作为一个邻居_first_。这是因为一个标籤只能包含一个基座部件。

_Note_：该[Qt.LayoutDirection](qt.html#LayoutDirection-enum)影响中的划分区域的两个部分的基座部件的顺序。当从右到左的布局方向被启用，码头部件的摆放将得到扭转。

**See also** [tabifyDockWidget](qmainwindow.html#tabifyDockWidget)（ ）[addDockWidget](qmainwindow.html#addDockWidget)（）和[removeDockWidget](qmainwindow.html#removeDockWidget)（ ） 。

```
QStatusBar QMainWindow.statusBar (self)
```

[

返回主窗口的状态栏中。这个函数创建并返回一个空的状态栏，如果状态栏不存在。

](qstatusbar.html)

[**See also**](qstatusbar.html) [setStatusBar](qmainwindow.html#setStatusBar)（ ） 。

```
list-of-QDockWidget QMainWindow.tabifiedDockWidgets (self, QDockWidget dockwidget)
```

返回与tabified在一起了被告席小部件_dockwidget_。

此功能被引入Qt的4.5 。

**See also** [tabifyDockWidget](qmainwindow.html#tabifyDockWidget)（ ） 。

```
QMainWindow.tabifyDockWidget (self, QDockWidget first, QDockWidget second)
```

Moves _second_之上码头部件_first_停靠窗口小部件，创建主窗口的选项卡式停靠区域。

**See also** [tabifiedDockWidgets](qmainwindow.html#tabifiedDockWidgets)（ ） 。

```
QTabWidget.TabPosition QMainWindow.tabPosition (self, Qt.DockWidgetArea area)
```

[

把标籤位置_area_。

](qtabwidget.html#TabPosition-enum)

[**Note:**该](qtabwidget.html#TabPosition-enum)[VerticalTabs](qmainwindow.html#DockOption-enum)码头选项复盖由该函数返回的标籤位置。

此功能被引入Qt的4.5 。

**See also** [setTabPosition](qmainwindow.html#setTabPosition)（）和[tabShape](qmainwindow.html#tabShape-prop)（ ） 。

```
QTabWidget.TabShape QMainWindow.tabShape (self)
```

[](qtabwidget.html#TabShape-enum)

```
Qt.ToolBarArea QMainWindow.toolBarArea (self, QToolBar toolbar)
```

[](qt.html#ToolBarArea-enum)

[返回](qt.html#ToolBarArea-enum)[Qt.ToolBarArea](qt.html#ToolBarArea-enum)为_toolbar_。如果_toolbar_还没有被添加到主窗口，该函数返回`Qt.NoToolBarArea`。

**See also** [addToolBar](qmainwindow.html#addToolBar)（ ）[addToolBarBreak](qmainwindow.html#addToolBarBreak)（）和[Qt.ToolBarArea](qt.html#ToolBarArea-enum)。

```
bool QMainWindow.toolBarBreak (self, QToolBar toolbar)
```

返回是否有前一个工具栏突破_toolbar_。

**See also** [addToolBarBreak](qmainwindow.html#addToolBarBreak)（）和[insertToolBarBreak](qmainwindow.html#insertToolBarBreak)（ ） 。

```
Qt.ToolButtonStyle QMainWindow.toolButtonStyle (self)
```

[

```
bool QMainWindow.unifiedTitleAndToolBarOnMac (self)
```

* * *

## Qt Signal Documentation

```
void iconSizeChanged (const QSize&)
```

这是该信号的默认超载。

当在窗口中使用的图标的大小改变时，这个信号被发射。新的图标大小是通过在_iconSize_。

您可以将此信号连接到其他组件，以帮助保持一致的外观为您的应用程序。

](qt.html#ToolButtonStyle-enum)

[**See also**](qt.html#ToolButtonStyle-enum) [setIconSize](qmainwindow.html#iconSize-prop)（ ） 。

```
void toolButtonStyleChanged (Qt::ToolButtonStyle)
```

这是该信号的默认超载。

当用于在窗口中的工具按钮的样式改变时，这个信号被发射。新样式传入_toolButtonStyle_。

您可以将此信号连接到其他组件，以帮助保持一致的外观为您的应用程序。

**See also** [setToolButtonStyle](qmainwindow.html#toolButtonStyle-prop)（ ） 。