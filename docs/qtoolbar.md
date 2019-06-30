# QToolBar Class Reference

## [[QtGui](index.htm) module]

该QToolBar类提供了一个可移动的面板，它包含了一组控件。[More...](#details)

继承[QWidget](qwidget.html)。

### Methods

*   `__init__ (self, QString title, QWidget parent = None)`
*   `__init__ (self, QWidget parent = None)`
*   `QAction actionAt (self, QPoint p)`
*   `QAction actionAt (self, int ax, int ay)`
*   `actionEvent (self, QActionEvent event)`
*   `QRect actionGeometry (self, QAction action)`
*   `addAction (self, QAction action)`
*   `QAction addAction (self, QString text)`
*   `QAction addAction (self, QIcon icon, QString text)`
*   `QAction addAction (self, QString text, QObject receiver, SLOT()SLOT() member)`
*   `QAction addAction (self, QString text, callable receiver)`
*   `QAction addAction (self, QIcon icon, QString text, QObject receiver, SLOT()SLOT() member)`
*   `QAction addAction (self, QIcon icon, QString text, callable receiver)`
*   `QAction addSeparator (self)`
*   `QAction addWidget (self, QWidget widget)`
*   `Qt.ToolBarAreas allowedAreas (self)`
*   `changeEvent (self, QEvent event)`
*   `childEvent (self, QChildEvent event)`
*   `clear (self)`
*   `bool event (self, QEvent event)`
*   `QSize iconSize (self)`
*   `initStyleOption (self, QStyleOptionToolBar option)`
*   `QAction insertSeparator (self, QAction before)`
*   `QAction insertWidget (self, QAction before, QWidget widget)`
*   `bool isAreaAllowed (self, Qt.ToolBarArea area)`
*   `bool isFloatable (self)`
*   `bool isFloating (self)`
*   `bool isMovable (self)`
*   `Qt.Orientation orientation (self)`
*   `paintEvent (self, QPaintEvent event)`
*   `resizeEvent (self, QResizeEvent event)`
*   `setAllowedAreas (self, Qt.ToolBarAreas areas)`
*   `setFloatable (self, bool floatable)`
*   `setIconSize (self, QSize iconSize)`
*   `setMovable (self, bool movable)`
*   `setOrientation (self, Qt.Orientation orientation)`
*   `setToolButtonStyle (self, Qt.ToolButtonStyle toolButtonStyle)`
*   `QAction toggleViewAction (self)`
*   `Qt.ToolButtonStyle toolButtonStyle (self)`
*   `QWidget widgetForAction (self, QAction action)`

### Qt Signals

*   `void actionTriggered (QAction *)`
*   `void allowedAreasChanged (Qt::ToolBarAreas)`
*   `void iconSizeChanged (const QSize&)`
*   `void movableChanged (bool)`
*   `void orientationChanged (Qt::Orientation)`
*   `void toolButtonStyleChanged (Qt::ToolButtonStyle)`
*   `void topLevelChanged (bool)`
*   `void visibilityChanged (bool)`

* * *

## Detailed Description

该QToolBar类提供了一个可移动的面板，它包含了一组控件。

工具栏按钮加入添加_actions_，使用[addAction](qtoolbar.html#addAction)（）或[insertAction](qwidget.html#insertAction)（ ） 。按钮组，可以使用分离[addSeparator](qtoolbar.html#addSeparator)（）或[insertSeparator](qtoolbar.html#insertSeparator)（ ） 。如果工具栏按钮是不合适的，一个部件可以被插入，而不是使用[addWidget](qtoolbar.html#addWidget)（）或[insertWidget](qtoolbar.html#insertWidget)（）;合适的窗口小部件的实例是[QSpinBox](qspinbox.html)，[QDoubleSpinBox](qdoublespinbox.html)和[QComboBox](qcombobox.html)。当按下工具栏按钮，它发出的[actionTriggered](qtoolbar.html#actionTriggered)（）信号。

工具栏可以被固定在适当位置中的特定区域（例如，在窗口的顶部） ，或者它可以是可移动的（[isMovable](qtoolbar.html#movable-prop)（ ） ）工具栏区域之间，见[allowedAreas](qtoolbar.html#allowedAreas-prop)（）和[isAreaAllowed](qtoolbar.html#isAreaAllowed)（ ） 。

当一个工具栏调整大小以这样一种方式，它是太小，无法显示其包含的所有项目，分机键会出现在工具栏上的最后一个项目。按分机键会弹出包含目前不适合工具栏上的项目菜单。

当QToolBar不是一个孩子[QMainWindow](qmainwindow.html)，它失去了使用带有添加到工具栏小工具来填充扩展弹出的能力[addWidget](qtoolbar.html#addWidget)（ ） 。请使用通过继承创建控件的行为[QWidgetAction](qwidgetaction.html)和实施[QWidgetAction.createWidget](qwidgetaction.html#createWidget)（ ）来代替。

* * *

## Method Documentation

```
QToolBar.__init__ (self, QString title, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QToolBar](qtoolbar.html)用给定的_parent_。

给定的窗口_title_标识的工具栏，并显示在所提供的上下文菜单[QMainWindow](qmainwindow.html)。

**See also** [setWindowTitle](qwidget.html#windowTitle-prop)（ ） 。

```
QToolBar.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QToolBar](qtoolbar.html)用给定的_parent_。

```
QAction QToolBar.actionAt (self, QPoint p)
```

[

返回点的动作_p_。该函数返回零，如果发现任何行动。

](qaction.html)

[**See also**](qaction.html) [QWidget.childAt](qwidget.html#childAt)（ ） 。

```
QAction QToolBar.actionAt (self, int ax, int ay)
```

[

这是一个重载函数。

返回行动在点_x_，_y_。该函数返回零，如果发现任何行动。

```
QToolBar.actionEvent (self, QActionEvent event)
```

](qaction.html)

[从重新实现](qaction.html)[QWidget.actionEvent](qwidget.html#actionEvent)（ ） 。

```
QRect QToolBar.actionGeometry (self, QAction action)
```

[

```
QToolBar.addAction (self, QAction action)
```

这是一个重载函数。

追加行动_action_对行动的工具栏的列表。

](qrect.html)

[**See also**](qrect.html) [QMenu.addAction](qmenu.html#addAction)（）和[QWidget.addAction](qwidget.html#addAction)（ ） 。

```
QAction QToolBar.addAction (self, QString text)
```

[

这是一个重载函数。

创建一个新的动作与给定_text_。这个动作被添加到工具栏的末尾。

](qaction.html)

```
QAction QToolBar.addAction (self, QIcon icon, QString text)
```

[

这是一个重载函数。

创建一个新的动作与给定_icon_和_text_。这个动作被添加到工具栏的末尾。

](qaction.html)

```
QAction QToolBar.addAction (self, QString text, QObject receiver, SLOT()SLOT() member)
```

[

这是一个重载函数。

](qaction.html)

[创建一个新的动作与给定_text_。这个动作被添加到工具栏的末尾。动作的](qaction.html)[triggered()](qaction.html#triggered)信号被连接到_member_在_receiver_。

```
QAction QToolBar.addAction (self, QString text, callable receiver)
```

[

这是一个重载函数。

](qaction.html)

[创建带有图标的新动作_icon_和文本_text_。这个动作被添加到工具栏的末尾。动作的](qaction.html)[triggered()](qaction.html#triggered)信号被连接到_member_在_receiver_。

```
QAction QToolBar.addAction (self, QIcon icon, QString text, QObject receiver, SLOT()SLOT() member)
```

[](qaction.html)

```
QAction QToolBar.addAction (self, QIcon icon, QString text, callable receiver)
```

[](qaction.html)

```
QAction QToolBar.addSeparator (self)
```

[

添加分隔到工具栏的末尾。

](qaction.html)

[**See also**](qaction.html) [insertSeparator](qtoolbar.html#insertSeparator)（ ） 。

```
QAction QToolBar.addWidget (self, QWidget widget)
```

[

该_widget_说法有它的所有权转移给Qt的。

将给定_widget_到工具栏与工具栏的最后一个项目。

该工具栏需要的所有权_widget_。

](qaction.html)

[如果添加](qaction.html)[QToolButton](qtoolbutton.html)用这种方法，工具栏的[Qt.ToolButtonStyle](qt.html#ToolButtonStyle-enum)将不被尊重。

**Note:**您应该使用[QAction.setVisible](qaction.html#visible-prop)（ ）来改变控件的可见性。运用[QWidget.setVisible](qwidget.html#visible-prop)（ ）[QWidget.show](qwidget.html#show)（）和[QWidget.hide](qwidget.html#hide)（ ）不起作用。

**See also** [insertWidget](qtoolbar.html#insertWidget)（ ） 。

```
Qt.ToolBarAreas QToolBar.allowedAreas (self)
```

[

```
QToolBar.changeEvent (self, QEvent event)
```

](index.htm)

[从重新实现](index.htm)[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
QToolBar.childEvent (self, QChildEvent event)
```

从重新实现[QObject.childEvent](qobject.html#childEvent)（ ） 。

```
QToolBar.clear (self)
```

移除工具栏上的所有操作。

**See also** [removeAction](qwidget.html#removeAction)（ ） 。

```
bool QToolBar.event (self, QEvent event)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QSize QToolBar.iconSize (self)
```

[

```
QToolBar.initStyleOption (self, QStyleOptionToolBar option)
```

](qsize.html)

```
QAction QToolBar.insertSeparator (self, QAction before)
```

[

插入分隔到工具栏与相关的工具栏项前_before_行动。

](qaction.html)

[**See also**](qaction.html) [addSeparator](qtoolbar.html#addSeparator)（ ） 。

```
QAction QToolBar.insertWidget (self, QAction before, QWidget widget)
```

[

该_widget_说法有它的所有权转移给Qt的。

插入给定_widget_与相关的工具栏项前_before_行动。

](qaction.html)

[注意：您应该使用](qaction.html)[QAction.setVisible](qaction.html#visible-prop)（ ）来改变控件的可见性。运用[QWidget.setVisible](qwidget.html#visible-prop)（ ）[QWidget.show](qwidget.html#show)（）和[QWidget.hide](qwidget.html#hide)（ ）不起作用。

**See also** [addWidget](qtoolbar.html#addWidget)（ ） 。

```
bool QToolBar.isAreaAllowed (self, Qt.ToolBarArea area)
```

返回True如果这个工具栏可停靠在给定的_area_否则返回False 。

```
bool QToolBar.isFloatable (self)
```

```
bool QToolBar.isFloating (self)
```

```
bool QToolBar.isMovable (self)
```

```
Qt.Orientation QToolBar.orientation (self)
```

[

```
QToolBar.paintEvent (self, QPaintEvent event)
```

](qt.html#Orientation-enum)

[从重新实现](qt.html#Orientation-enum)[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QToolBar.resizeEvent (self, QResizeEvent event)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
QToolBar.setAllowedAreas (self, Qt.ToolBarAreas areas)
```

```
QToolBar.setFloatable (self, bool floatable)
```

```
QToolBar.setIconSize (self, QSize iconSize)
```

这种方法也是一个Qt槽与C + +的签名`void setIconSize(const QSize&)`。

```
QToolBar.setMovable (self, bool movable)
```

```
QToolBar.setOrientation (self, Qt.Orientation orientation)
```

```
QToolBar.setToolButtonStyle (self, Qt.ToolButtonStyle toolButtonStyle)
```

这种方法也是一个Qt槽与C + +的签名`void setToolButtonStyle(Qt::ToolButtonStyle)`。

```
QAction QToolBar.toggleViewAction (self)
```

[

返回一个可用于显示或隐藏该工具栏可检查的动作。

该操作的文本设置为工具栏的窗口标题。

](qaction.html)

[**See also**](qaction.html) [QAction.text](qaction.html#text-prop)和[QWidget.windowTitle](qwidget.html#windowTitle-prop)。

```
Qt.ToolButtonStyle QToolBar.toolButtonStyle (self)
```

[](qt.html#ToolButtonStyle-enum)

```
QWidget QToolBar.widgetForAction (self, QAction action)
```

[

返回与指定相关的部件_action_。

这个函数中引入了Qt 4.2中。

](qwidget.html)

[**See also**](qwidget.html) [addWidget](qtoolbar.html#addWidget)（ ） 。

* * *

## Qt Signal Documentation

```
void actionTriggered (QAction *)
```

这是该信号的默认超载。

当在这个工具栏的作用是触发这个信号被发射。发生这种情况时按下的动作的工具按钮时，或当动作被触发在工具栏以外的其他方式。该参数保存在触发_action_。

```
void allowedAreasChanged (Qt::ToolBarAreas)
```

这是该信号的默认超载。

当允许的区域为工具栏的集合更改这个信号被发射。在该工具条可以定位在新的区域被指定_allowedAreas_。

**See also** [allowedAreas](qtoolbar.html#allowedAreas-prop)。

```
void iconSizeChanged (const QSize&)
```

这是该信号的默认超载。

当图标大小改变这个信号被发射。该_iconSize_参数保存工具栏上的新图标的大小。

**See also** [iconSize](qtoolbar.html#iconSize-prop)和[QMainWindow.iconSize](qmainwindow.html#iconSize-prop)。

```
void movableChanged (bool)
```

这是该信号的默认超载。

当工具栏变成可移动的或固定的这个信号被发射。如果工具栏可以移动，_movable_为True，否则为False 。

**See also** [movable](qtoolbar.html#movable-prop)。

```
void orientationChanged (Qt::Orientation)
```

这是该信号的默认超载。

这个信号被发射时的工具栏上的变化的方向。新的方向被指定的_orientation_给出。

**See also** [orientation](qtoolbar.html#orientation-prop)。

```
void toolButtonStyleChanged (Qt::ToolButtonStyle)
```

这是该信号的默认超载。

当工具按钮样式改变这个信号被发射。该_toolButtonStyle_参数保存工具栏的新工具按钮样式。

**See also** [toolButtonStyle](qtoolbar.html#toolButtonStyle-prop)和[QMainWindow.toolButtonStyle](qmainwindow.html#toolButtonStyle-prop)。

```
void topLevelChanged (bool)
```

这是该信号的默认超载。

这个信号被发射时的[floating](qtoolbar.html#floating-prop)属性更改。该_topLevel_参数为True时，如果工具栏现在是浮动的，否则它是假的。

此功能被引入Qt的4.6 。

**See also** [isWindow](qwidget.html#isWindow)（ ） 。

```
void visibilityChanged (bool)
```

这是该信号的默认超载。

当工具栏变成这个信号被发射_visible_（或不可见） 。这种情况发生在小部件隐藏或显示。

此功能被引入Qt的4.7 。