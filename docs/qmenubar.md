# QMenuBar Class Reference

## [[QtGui](index.htm) module]

该QMenuBar类提供了一个水平菜单栏。[More...](#details)

继承[QWidget](qwidget.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `QAction actionAt (self, QPoint)`
*   `actionEvent (self, QActionEvent)`
*   `QRect actionGeometry (self, QAction)`
*   `QAction activeAction (self)`
*   `addAction (self, QAction action)`
*   `QAction addAction (self, QString text)`
*   `QAction addAction (self, QString text, QObject receiver, SLOT()SLOT() member)`
*   `QAction addAction (self, QString text, callable receiver)`
*   `QAction addMenu (self, QMenu menu)`
*   `QMenu addMenu (self, QString title)`
*   `QMenu addMenu (self, QIcon icon, QString title)`
*   `QAction addSeparator (self)`
*   `changeEvent (self, QEvent)`
*   `clear (self)`
*   `QWidget cornerWidget (self, Qt.Corner corner = Qt.TopRightCorner)`
*   `bool event (self, QEvent)`
*   `bool eventFilter (self, QObject, QEvent)`
*   `focusInEvent (self, QFocusEvent)`
*   `focusOutEvent (self, QFocusEvent)`
*   `int heightForWidth (self, int)`
*   `initStyleOption (self, QStyleOptionMenuItem option, QAction action)`
*   `QAction insertMenu (self, QAction before, QMenu menu)`
*   `QAction insertSeparator (self, QAction before)`
*   `bool isDefaultUp (self)`
*   `bool isNativeMenuBar (self)`
*   `keyPressEvent (self, QKeyEvent)`
*   `leaveEvent (self, QEvent)`
*   `QSize minimumSizeHint (self)`
*   `mouseMoveEvent (self, QMouseEvent)`
*   `mousePressEvent (self, QMouseEvent)`
*   `mouseReleaseEvent (self, QMouseEvent)`
*   `paintEvent (self, QPaintEvent)`
*   `resizeEvent (self, QResizeEvent)`
*   `setActiveAction (self, QAction action)`
*   `setCornerWidget (self, QWidget widget, Qt.Corner corner = Qt.TopRightCorner)`
*   `setDefaultUp (self, bool)`
*   `setNativeMenuBar (self, bool nativeMenuBar)`
*   `setVisible (self, bool visible)`
*   `QSize sizeHint (self)`
*   `timerEvent (self, QTimerEvent)`

### Qt Signals

*   `void hovered (QAction *)`
*   `void triggered (QAction *)`

* * *

## Detailed Description

该QMenuBar类提供了一个水平菜单栏。

菜单栏包含下拉菜单项列表中。您添加菜单项[addMenu](qmenubar.html#addMenu)（ ） 。例如， asuming那`menubar`是一个指针，指向一个QMenuBar和`fileMenu`是一个指针，指向[QMenu](qmenu.html)，下面的语句插入菜单进入菜单栏：

```
 menubar->addMenu(fileMenu);

```

在菜单项文本的符号设置Alt + F键作为此菜单中的快捷方式。 （您可以使用“\u0026\u0026”获得在菜单栏中一个真正的符号。 ）

有没有必要制定出一个菜单栏。它会自动将其自身的几何形状的父控件的顶部，并适当地改变它，每当父调整大小。

### Usage

在大多数的主窗口风格的应用程序，你会使用[menuBar()](qmainwindow.html#menuBar)在所提供的功能[QMainWindow](qmainwindow.html)，加入[QMenu](qmenu.html)s到菜单栏和添加[QAction](qaction.html)s到弹出式菜单。

例子（从[Menus](index.htm)为例）：

```
     fileMenu = menuBar()->addMenu(tr("&File"));
     fileMenu->addAction(newAct);

```

菜单项可以与被删除[removeAction](qwidget.html#removeAction)（ ） 。

窗口小部件可以使用的情况下被添加到菜单[QWidgetAction](qwidgetaction.html)类来保存它们。这些动作可以被插入到在通常的方式菜单，见[QMenu](qmenu.html)文档了解更多信息。

### Platform Dependent Look and Feel

不同的平台上有菜单栏的外观和行为的不同要求，当用户与其互动。举例来说， Windows系统通常配置，使得带下划线的字符助记符，表明在菜单栏项目的快捷键只显示当**Alt**键被按下。

| ![A menu bar shown in the](../img/plastique-menubar.png) Plastique widget style. | The [Plastique widget style](index.htm), like most other styles, handles the **Help** menu in the same way as it handles any other menu. |
| ![A menu bar shown in the](../img/motif-menubar.png) Motif widget style. | The [Motif widget style](index.htm) treats **Help** menus in a special way, placing them at right-hand end of the menu bar. |

### QMenuBar on Mac OS X

QMenuBar在Mac OS X是一个包装使用系统范围的菜单栏。如果您有多个菜单栏在一个对话框中的最外层的菜单栏（通常里面一个小部件与部件标志[Qt.Window](qt.html#WindowType-enum)）将用于全系统的菜单栏。

Qt的用于Mac OS X还提供了一个菜单栏合并功能，使QMenuBar更符合公认的Mac OS X的菜单栏布局。该合并功能是基于字符串匹配的标题[QMenu](qmenu.html)条目。这些字符串翻译（使用[QObject.tr](qobject.html#tr)（））中的“ QMenuBar ”的上下文。如果项目被移动及其插槽仍然会火，就好像它是在原来的地方。下表概述了字符串寻找和那里的条目，如果匹配放置：

| String matches | Placement | Notes |
| --- | --- | --- |
| about.* | Application Menu &#124; About &lt;application name&gt; | The application name is fetched from the `Info.plist` file (see note below). If this entry is not found no About item will appear in the Application Menu. |
| config, options, setup, settings or preferences | Application Menu &#124; Preferences | If this entry is not found the Settings item will be disabled |
| quit or exit | Application Menu &#124; Quit &lt;application name&gt; | If this entry is not found a default Quit item will be created to call [QApplication.quit](qcoreapplication.html#quit)() |

您可以通过使用复盖此行为[QAction.menuRole](qaction.html#menuRole-prop)（）属性。

如果你想在一台Mac应用程序的所有窗口共享一个菜单栏，你必须创建一个没有父项的菜单栏。创建一个父少菜单栏是这样的：

```
 QMenuBar *menuBar = new QMenuBar(0);

```

**Note:** Do _not_通话[QMainWindow.menuBar](qmainwindow.html#menuBar)（）来创建共享菜单栏，因为该菜单栏将有[QMainWindow](qmainwindow.html)作为其母公司。该菜单栏只会显示父[QMainWindow](qmainwindow.html)。

**Note:**从设置的值获得用于在菜单栏的应用程序名称的文本`Info.plist`文件中的应用程序的包。看[Deploying an Application on Mac OS X](index.htm)了解更多信息。

### QMenuBar on Windows CE

QMenuBar在Windows CE是一个包装使用系统范围的菜单栏，类似于苹果。此功能被激活Windows Mobile和集成QMenuBar与本地软键。左软键可以被控制[QMenuBar.setDefaultAction](qmenubar.html#setDefaultAction)（）和右软键，可用于访问菜单栏。

该[hovered](qmenubar.html#hovered)（ ）信号不支持本机菜单集成。此外，它是不可能在Windows Mobile上的本机菜单显示一个图标。

### Examples

该[Menus](index.htm)示例显示了如何使用QMenuBar和[QMenu](qmenu.html)。其他[main window application examples](index.htm)还提供了使用这些类的菜单。

* * *

## Method Documentation

```
QMenuBar.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个父菜单栏_parent_。

```
QAction QMenuBar.actionAt (self, QPoint)
```

[](qaction.html)

[返回](qaction.html)[QAction](qaction.html)在_pt_。返回0，如果有一个在无动作_pt_或者，如果位置有一个隔板。

**See also** [addAction](qmenubar.html#addAction)（）和[addSeparator](qmenubar.html#addSeparator)（ ） 。

```
QMenuBar.actionEvent (self, QActionEvent)
```

从重新实现[QWidget.actionEvent](qwidget.html#actionEvent)（ ） 。

```
QRect QMenuBar.actionGeometry (self, QAction)
```

[](qrect.html)

[返回行动的几何形状_act_作为](qrect.html)[QRect](qrect.html)。

**See also** [actionAt](qmenubar.html#actionAt)（ ） 。

```
QAction QMenuBar.activeAction (self)
```

[](qaction.html)

[返回](qaction.html)[QAction](qaction.html)这是当前突出显示。如果不采取行动是当前选定的空指针将被返回。

**See also** [setActiveAction](qmenubar.html#setActiveAction)（ ） 。

```
QMenuBar.addAction (self, QAction action)
```

这是一个重载函数。

用这种便利函数创建一个新动作_text_。该函数将新创建的行动，行动的菜单的列表中，并返回它。

**See also** [QWidget.addAction](qwidget.html#addAction)（）和[QWidget.actions](qwidget.html#actions)（ ） 。

```
QAction QMenuBar.addAction (self, QString text)
```

[

这是一个重载函数。

](qaction.html)

[用给定的这个便利函数创建一个新动作_text_。动作的](qaction.html)[triggered](qmenubar.html#triggered)（）信号被连接到_receiver_的_member_插槽。该函数将新创建的行动，行动的菜单的列表并返回它。

**See also** [QWidget.addAction](qwidget.html#addAction)（）和[QWidget.actions](qwidget.html#actions)（ ） 。

```
QAction QMenuBar.addAction (self, QString text, QObject receiver, SLOT()SLOT() member)
```

[

这是一个重载函数。

追加行动_action_于诉讼的菜单栏的列表。

](qaction.html)

[**See also**](qaction.html) [QMenu.addAction](qmenu.html#addAction)（ ）[QWidget.addAction](qwidget.html#addAction)（）和[QWidget.actions](qwidget.html#actions)（ ） 。

```
QAction QMenuBar.addAction (self, QString text, callable receiver)
```

[](qaction.html)

```
QAction QMenuBar.addMenu (self, QMenu menu)
```

[

追加可_menu_菜单栏。返回菜单的menuAction （ ） 。

](qaction.html)

[**Note:**返回](qaction.html)[QAction](qaction.html)对象可以用来隐藏相应的菜单。

**See also** [QWidget.addAction](qwidget.html#addAction)（）和[QMenu.menuAction](qmenu.html#menuAction)（ ） 。

```
QMenu QMenuBar.addMenu (self, QString title)
```

[](qmenu.html)

[添加一个新的](qmenu.html)[QMenu](qmenu.html)同_title_菜单栏。菜单栏取菜单的所有权。返回新菜单。

**See also** [QWidget.addAction](qwidget.html#addAction)（）和[QMenu.menuAction](qmenu.html#menuAction)（ ） 。

```
QMenu QMenuBar.addMenu (self, QIcon icon, QString title)
```

[](qmenu.html)

[添加一个新的](qmenu.html)[QMenu](qmenu.html)同_icon_和_title_菜单栏。菜单栏取菜单的所有权。返回新菜单。

**See also** [QWidget.addAction](qwidget.html#addAction)（）和[QMenu.menuAction](qmenu.html#menuAction)（ ） 。

```
QAction QMenuBar.addSeparator (self)
```

[

附加一个分隔符的菜单。

```
QMenuBar.changeEvent (self, QEvent)
```

](qaction.html)

[从重新实现](qaction.html)[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
QMenuBar.clear (self)
```

删除菜单栏的所有动作。

**Note:**在Mac OS X中，已合并到系统菜单栏的菜单项由该函数不会被删除。处理这一个方法是删除多馀的动作自己。您可以设置[menu role](qaction.html#MenuRole-enum)在不同的菜单，让你提前知道哪个菜单项都被合并，哪些没有。然后决定如何重新创建或删除自己。

**See also** [removeAction](qwidget.html#removeAction)（ ） 。

```
QWidget QMenuBar.cornerWidget (self, Qt.Corner corner = Qt.TopRightCorner)
```

[

返回该插件上的第一个或最后一个菜单项的右边的左边，这取决于_corner_。

](qwidget.html)

[**Note:**使用一个角落里比其他](qwidget.html)[Qt.TopRightCorner](qt.html#Corner-enum) or [Qt.TopLeftCorner](qt.html#Corner-enum)将导致警告。

**See also** [setCornerWidget](qmenubar.html#setCornerWidget)（ ） 。

```
bool QMenuBar.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
bool QMenuBar.eventFilter (self, QObject, QEvent)
```

从重新实现[QObject.eventFilter](qobject.html#eventFilter)（ ） 。

```
QMenuBar.focusInEvent (self, QFocusEvent)
```

从重新实现[QWidget.focusInEvent](qwidget.html#focusInEvent)（ ） 。

```
QMenuBar.focusOutEvent (self, QFocusEvent)
```

从重新实现[QWidget.focusOutEvent](qwidget.html#focusOutEvent)（ ） 。

```
int QMenuBar.heightForWidth (self, int)
```

从重新实现[QWidget.heightForWidth](qwidget.html#heightForWidth)（ ） 。

```
QMenuBar.initStyleOption (self, QStyleOptionMenuItem option, QAction action)
```

初始化_option_从菜单栏和信息的价值_action_。当他们需要一个这种方法是有用的子类[QStyleOptionMenuItem](qstyleoptionmenuitem.html)，但不希望在所有的信息填写自己。

**See also** [QStyleOption.initFrom](qstyleoption.html#initFrom)（）和[QMenu.initStyleOption](qmenu.html#initStyleOption)（ ） 。

```
QAction QMenuBar.insertMenu (self, QAction before, QMenu menu)
```

[

这个方便的功能插件_menu_行动之前，_before_并返回菜单menuAction （ ） 。

](qaction.html)

[**See also**](qaction.html) [QWidget.insertAction](qwidget.html#insertAction)（）和[addMenu](qmenubar.html#addMenu)（ ） 。

```
QAction QMenuBar.insertSeparator (self, QAction before)
```

[](qaction.html)

[这个便利函数创建一个新的分隔作用，即一个行动](qaction.html)[QAction.isSeparator](qaction.html#isSeparator)（ ）返回True 。该函数插入新创建的行动变成行动之前的行动为此菜单栏的列表_before_并返回它。

**See also** [QWidget.insertAction](qwidget.html#insertAction)（）和[addSeparator](qmenubar.html#addSeparator)（ ） 。

```
bool QMenuBar.isDefaultUp (self)
```

```
bool QMenuBar.isNativeMenuBar (self)
```

```
QMenuBar.keyPressEvent (self, QKeyEvent)
```

从重新实现[QWidget.keyPressEvent](qwidget.html#keyPressEvent)（ ） 。

```
QMenuBar.leaveEvent (self, QEvent)
```

从重新实现[QWidget.leaveEvent](qwidget.html#leaveEvent)（ ） 。

```
QSize QMenuBar.minimumSizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.minimumSizeHint](qwidget.html#minimumSizeHint-prop)（ ） 。

```
QMenuBar.mouseMoveEvent (self, QMouseEvent)
```

从重新实现[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

```
QMenuBar.mousePressEvent (self, QMouseEvent)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

```
QMenuBar.mouseReleaseEvent (self, QMouseEvent)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

```
QMenuBar.paintEvent (self, QPaintEvent)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QMenuBar.resizeEvent (self, QResizeEvent)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
QMenuBar.setActiveAction (self, QAction action)
```

设置当前突出显示的动作_act_。

这个函数是Qt 4.1中引入。

**See also** [activeAction](qmenubar.html#activeAction)（ ） 。

```
QMenuBar.setCornerWidget (self, QWidget widget, Qt.Corner corner = Qt.TopRightCorner)
```

该_widget_说法有它的所有权转移给Qt的。

这台给定的_widget_直接显示在第一菜单项的左侧，或在最后的菜单项的右侧，这取决于_corner_。

在菜单栏佔用的所有权_widget_，重定父级成的菜单栏。然而，如果_corner_已经包含了一个小工具，这个以前的部件将不再进行管理，并仍将是菜单栏的可见子。

**Note:**使用一个角落里比其他[Qt.TopRightCorner](qt.html#Corner-enum) or [Qt.TopLeftCorner](qt.html#Corner-enum)将导致警告。

**See also** [cornerWidget](qmenubar.html#cornerWidget)（ ） 。

```
QMenuBar.setDefaultUp (self, bool)
```

```
QMenuBar.setNativeMenuBar (self, bool nativeMenuBar)
```

```
QMenuBar.setVisible (self, bool visible)
```

从重新实现[QWidget.setVisible](qwidget.html#visible-prop)（ ） 。

```
QSize QMenuBar.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

```
QMenuBar.timerEvent (self, QTimerEvent)
```

从重新实现[QObject.timerEvent](qobject.html#timerEvent)（ ） 。

* * *

## Qt Signal Documentation

```
void hovered (QAction *)
```

这是该信号的默认超载。

当一个菜单操作高亮显示这个信号被发射;_action_是导致事件要发送的动作。

通常这是用来更新状态信息。

**See also** [triggered](qmenubar.html#triggered)（）和[QAction.hovered](qaction.html#hovered)（ ） 。

```
void triggered (QAction *)
```

这是该信号的默认超载。

当属于该菜单栏的菜单中选择操作被触发的鼠标点击一个结果，这个信号被发射;_action_是导致该信号被发射的操作。

**Note:** [QMenuBar](qmenubar.html)必须有所有权[QMenu](qmenu.html)为了这个信号来工作。

通常情况下，你使用每个菜单操作连接到一个单一的插槽[QAction.triggered](qaction.html#triggered)（ ） ，但有时你会想几个项目连接到一个单一的插槽（通常，如果用户从一个数组中选择） 。这个信号是在这样的情况下是有用的。

**See also** [hovered](qmenubar.html#hovered)（）和[QAction.triggered](qaction.html#triggered)（ ） 。