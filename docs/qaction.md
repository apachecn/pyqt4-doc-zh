# QAction Class Reference

## [[QtGui](index.htm) module]

QAction类负责提供可插入小部件抽象的用户界面操作。[More...](#details)

继承[QObject](qobject.html)。

通过继承[QWidgetAction](qwidgetaction.html)。

### Types

*   `enum ActionEvent { Trigger, Hover }`
*   `enum MenuRole { NoRole, TextHeuristicRole, ApplicationSpecificRole, AboutQtRole, ..., QuitRole }`
*   `enum Priority { LowPriority, NormalPriority, HighPriority }`
*   `enum SoftKeyRole { NoSoftKey, PositiveSoftKey, NegativeSoftKey, SelectSoftKey }`

### Methods

*   `__init__ (self, QObject parent)`
*   `__init__ (self, QString text, QObject parent)`
*   `__init__ (self, QIcon icon, QString text, QObject parent)`
*   `QActionGroup actionGroup (self)`
*   `activate (self, ActionEvent event)`
*   `list-of-QGraphicsWidget associatedGraphicsWidgets (self)`
*   `list-of-QWidget associatedWidgets (self)`
*   `bool autoRepeat (self)`
*   `QVariant data (self)`
*   `bool event (self, QEvent)`
*   `QFont font (self)`
*   `hover (self)`
*   `QIcon icon (self)`
*   `QString iconText (self)`
*   `bool isCheckable (self)`
*   `bool isChecked (self)`
*   `bool isEnabled (self)`
*   `bool isIconVisibleInMenu (self)`
*   `bool isSeparator (self)`
*   `bool isVisible (self)`
*   `QMenu menu (self)`
*   `MenuRole menuRole (self)`
*   `QWidget parentWidget (self)`
*   `Priority priority (self)`
*   `setActionGroup (self, QActionGroup group)`
*   `setAutoRepeat (self, bool)`
*   `setCheckable (self, bool)`
*   `setChecked (self, bool)`
*   `setData (self, QVariant var)`
*   `setDisabled (self, bool b)`
*   `setEnabled (self, bool)`
*   `setFont (self, QFont font)`
*   `setIcon (self, QIcon icon)`
*   `setIconText (self, QString text)`
*   `setIconVisibleInMenu (self, bool visible)`
*   `setMenu (self, QMenu menu)`
*   `setMenuRole (self, MenuRole menuRole)`
*   `setPriority (self, Priority priority)`
*   `setSeparator (self, bool b)`
*   `setShortcut (self, QKeySequence shortcut)`
*   `setShortcutContext (self, Qt.ShortcutContext context)`
*   `setShortcuts (self, list-of-QKeySequence shortcuts)`
*   `setShortcuts (self, QKeySequence.StandardKey)`
*   `setSoftKeyRole (self, SoftKeyRole softKeyRole)`
*   `setStatusTip (self, QString statusTip)`
*   `setText (self, QString text)`
*   `setToolTip (self, QString tip)`
*   `setVisible (self, bool)`
*   `setWhatsThis (self, QString what)`
*   `QKeySequence shortcut (self)`
*   `Qt.ShortcutContext shortcutContext (self)`
*   `list-of-QKeySequence shortcuts (self)`
*   `bool showStatusText (self, QWidget widget = None)`
*   `SoftKeyRole softKeyRole (self)`
*   `QString statusTip (self)`
*   `QString text (self)`
*   `toggle (self)`
*   `QString toolTip (self)`
*   `trigger (self)`
*   `QString whatsThis (self)`

### Qt Signals

*   `void changed ()`
*   `void hovered ()`
*   `void toggled (bool)`
*   `void triggered (bool = 0)`

* * *

## Detailed Description

QAction类负责提供可插入小部件抽象的用户界面操作。

在实际应用中很多常见的命令可以通过菜单，工具栏按钮和键盘快捷键来调用。由于用户期望要以相同的方式执行的每个命令，而不管所使用的用户界面，它表示每个命令作为一个非常有用_action_。

操作可以被添加到菜单和工具栏，并且会自动使它们保持同步。例如，在一个文字处理器，如果用户按下一个大胆的工具栏按钮，粗体菜单项将自动进行检查。

动作可以被创建为独立的对象，但它们也可以菜单的施工过程中产生;的[QMenu](qmenu.html)类包含用于创建适合用作菜单项行动方便的功能。

一个的QAction可能包含图标，菜单文本，快捷键，状态文字， “这是什么？ ”文本和工具提示。大多数这些可以在构造函数中设置。它们也可以独立地设置[setIcon](qaction.html#icon-prop)（ ）[setText](qaction.html#text-prop)（ ）[setIconText](qaction.html#iconText-prop)（ ）[setShortcut](qaction.html#shortcut-prop)（ ）[setStatusTip](qaction.html#statusTip-prop)（ ）[setWhatsThis](qaction.html#whatsThis-prop)（）和[setToolTip](qaction.html#toolTip-prop)（ ） 。为菜单项，可以设置一个单独的字体与[setFont](qaction.html#font-prop)（ ） 。

操作使用添加小工具[QWidget.addAction](qwidget.html#addAction)（）或[QGraphicsWidget.addAction](qgraphicswidget.html#addAction)（ ） 。请注意，一个动作必须被添加到窗口小部件可以被使用之前，这也是真实的，当快捷方式应该是全局的（也就是[Qt.ApplicationShortcut](qt.html#ShortcutContext-enum)如[Qt.ShortcutContext](qt.html#ShortcutContext-enum)） 。

一次的QAction已创建它应该被添加到相关的菜单和工具栏上，然后连接到将执行的动作的插槽。例如：

```
     openAct = new QAction([QIcon](qicon.html)(":/../img/open.png"), tr("&Open..."), this);
     openAct->setShortcuts([QKeySequence](qkeysequence.html).Open);
     openAct->setStatusTip(tr("Open an existing file"));
     connect(openAct, SIGNAL(triggered()), this, SLOT(open()));

     fileMenu->addAction(openAct);
     fileToolBar->addAction(openAct);

```

我们建议的行动被创建为使用它们。在大多数情况下，操作窗口的孩子们将应用程序的主窗口的儿童。

* * *

## Type Documentation

```
QAction.ActionEvent
```

该枚举类型是调用时使用[QAction.activate](qaction.html#activate)（ ）

| Constant | Value | Description |
| --- | --- | --- |
| `QAction.Trigger` | `0` | 这将导致[QAction.triggered](qaction.html#triggered)（）信号被发射。 |
| `QAction.Hover` | `1` | 这将导致[QAction.hovered](qaction.html#hovered)（）信号被发射。 |

```
QAction.MenuRole
```

这个枚举变量描述了如何一个动作应该被移动到应用程序菜单上的Mac OS X。

| Constant | Value | Description |
| --- | --- | --- |
| `QAction.NoRole` | `0` | 这个动作不应该被放到应用程序菜单 |
| `QAction.TextHeuristicRole` | `1` | 这个动作应该在应用程序菜单的基础上采取行动的文本中所描述的放[QMenuBar](qmenubar.html)文档。 |
| `QAction.ApplicationSpecificRole` | `2` | 这个动作应该被放置在应用程序菜单中有一个特定的应用程序角色 |
| `QAction.AboutQtRole` | `3` | 这个动作匹配处理“关于Qt ”菜单项。 |
| `QAction.AboutRole` | `4` | 这个动作应该放在哪里“关于”菜单项，在应用程序菜单。菜单项的文本将被设置为“关于\u003capplication NAME\u003e ” 。该应用程序的名称是从牵强`Info.plist`在应用程序的包文件（见[Deploying an Application on Mac OS X](index.htm)） 。 |
| `QAction.PreferencesRole` | `5` | 这个动作应该放在那里的“首选项... ”菜单项，在应用程序菜单。 |
| `QAction.QuitRole` | `6` | 这个动作应该放在哪里Quit菜单项是在应用程序菜单。 |

设置此值只对那些在菜单栏，而不是那些菜单的子菜单的直接菜单项的效果。例如，如果你有文件菜单中的菜单栏和文件菜单中有一个子菜单，设置MenuRole在该子菜单中的操作没有任何效果。他们将永远不会被移动。

```
QAction.Priority
```

这个枚举变量定义为在用户界面操作的优先事项。

| Constant | Value | Description |
| --- | --- | --- |
| `QAction.LowPriority` | `0` | 该操作不应该被优先在用户界面中。 |
| `QAction.NormalPriority` | `128` |   |
| `QAction.HighPriority` | `256` | 该行动应优先在用户界面。 |

这个枚举被引入或修改的Qt 4.6 。

**See also** [priority](qaction.html#priority-prop)。

```
QAction.SoftKeyRole
```

这个枚举说明如何动作应放置在软键栏。目前，该枚举只有在Symbian平台上的效果。

| Constant | Value | Description |
| --- | --- | --- |
| `QAction.NoSoftKey` | `0` | 此操作不应该被用来作为一个软键 |
| `QAction.PositiveSoftKey` | `1` | 这个动作是用来描述一个软键以积极的还是非破坏性的作用，如OK，选择或选项。 |
| `QAction.NegativeSoftKey` | `2` | 这个动作是用来描述一个软安永具有负的或破坏性的角色作用，如取消，丢弃，或关闭。 |
| `QAction.SelectSoftKey` | `3` | 这个动作是用来描述用于选择应用程序中的特定项目或插件的作用。 |

与定义的功能键角色的动作才可见在软键栏时，包含动作的部件具有焦点。如果没有小工具​​目前拥有焦点时，软键框架将向上遍历父控件层次结构查找包含软键操作的部件。

这个枚举被引入或修改的Qt 4.6 。

* * *

## Method Documentation

```
QAction.__init__ (self, QObject parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个行动_parent_。如果_parent_是一个行动小组的行动将被自动插入到组。

```
QAction.__init__ (self, QString text, QObject parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个动作与一些_text_和_parent_。如果_parent_是一个行动小组的行动将被自动插入到组。

该操作使用的一个简化版本_text_（例如：“和菜单选项... ”变成“菜单选项” ）作为描述性文本工具按钮。您可以通过设置特定的描述与复盖此[setText](qaction.html#text-prop)（ ） 。同样的文本将被用于工具提示除非您指定使用不同的文字[setToolTip](qaction.html#toolTip-prop)（ ） 。

```
QAction.__init__ (self, QIcon icon, QString text, QObject parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个动作与_icon_有的_text_和_parent_。如果_parent_是一个行动小组的行动将被自动插入到组。

该操作使用的一个简化版本_text_（例如：“和菜单选项... ”变成“菜单选项” ）作为描述性文本工具按钮。您可以通过设置特定的描述与复盖此[setText](qaction.html#text-prop)（ ） 。同样的文本将被用于工具提示除非您指定使用不同的文字[setToolTip](qaction.html#toolTip-prop)（ ） 。

```
QActionGroup QAction.actionGroup (self)
```

[

返回该行动小组的这一行动。如果不采取行动组管理这个行动，那么将返回0 。

](qactiongroup.html)

[**See also**](qactiongroup.html) [QActionGroup](qactiongroup.html)和[QAction.setActionGroup](qaction.html#setActionGroup)（ ） 。

```
QAction.activate (self, ActionEvent event)
```

发送相关信号[ActionEvent](qaction.html#ActionEvent-enum) _event_。

根据动作的部件使用这个API使[QAction](qaction.html)以发射信号，以及发射自己。

```
list-of-QGraphicsWidget QAction.associatedGraphicsWidgets (self)
```

返回部件此操作已被添加到列表。

此功能被引入Qt的4.5 。

**See also** [QWidget.addAction](qwidget.html#addAction)（）和[associatedWidgets](qaction.html#associatedWidgets)（ ） 。

```
list-of-QWidget QAction.associatedWidgets (self)
```

返回部件此操作已被添加到列表。

这个函数中引入了Qt 4.2中。

**See also** [QWidget.addAction](qwidget.html#addAction)（）和[associatedGraphicsWidgets](qaction.html#associatedGraphicsWidgets)（ ） 。

```
bool QAction.autoRepeat (self)
```

```
QVariant QAction.data (self)
```

返回用户数据作为在QAction.setData设置。

**See also** [setData](qaction.html#setData)（ ） 。

```
bool QAction.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QFont QAction.font (self)
```

[

```
QAction.hover (self)
```

这种方法也是一个Qt槽与C + +的签名`void hover()`。

这是一个方便的插槽调用激活（哈弗） 。

](qfont.html)

```
QIcon QAction.icon (self)
```

[

```
QString QAction.iconText (self)
```

```
bool QAction.isCheckable (self)
```

```
bool QAction.isChecked (self)
```

```
bool QAction.isEnabled (self)
```

```
bool QAction.isIconVisibleInMenu (self)
```

```
bool QAction.isSeparator (self)
```

返回True如果这个动作是一个分离器的动作，否则返回False 。

](qicon.html)

[**See also**](qicon.html) [QAction.setSeparator](qaction.html#setSeparator)（ ） 。

```
bool QAction.isVisible (self)
```

```
QMenu QAction.menu (self)
```

[

返回包含由这个动作菜单。包含菜单操作，可用于创建带有子菜单的菜单项，或插入到工具栏来创建弹出式菜单的按钮。

](qmenu.html)

[**See also**](qmenu.html) [setMenu](qaction.html#setMenu)（）和[QMenu.addAction](qmenu.html#addAction)（ ） 。

```
MenuRole QAction.menuRole (self)
```

[](qaction.html#MenuRole-enum)

```
QWidget QAction.parentWidget (self)
```

[

返回父控件。

](qwidget.html)

```
Priority QAction.priority (self)
```

[

```
QAction.setActionGroup (self, QActionGroup group)
```

设置此行动组_group_。该动作将被自动添加到行动组的列表。

组内的行动将是相互排斥的。

](qaction.html#Priority-enum)

[**See also**](qaction.html#Priority-enum) [QActionGroup](qactiongroup.html)和[QAction.actionGroup](qaction.html#actionGroup)（ ） 。

```
QAction.setAutoRepeat (self, bool)
```

```
QAction.setCheckable (self, bool)
```

```
QAction.setChecked (self, bool)
```

这种方法也是一个Qt槽与C + +的签名`void setChecked(bool)`。

```
QAction.setData (self, QVariant var)
```

该行动的内部数据设置为给定_userData_。

**See also** [data](qaction.html#data)（ ） 。

```
QAction.setDisabled (self, bool b)
```

这种方法也是一个Qt槽与C + +的签名`void setDisabled(bool)`。

这是一个方便的功能为[enabled](qaction.html#enabled-prop)财产，那是非常有用的信号 - 槽连接。如果_b_是真实的动作被禁止，否则将被启用。

```
QAction.setEnabled (self, bool)
```

这种方法也是一个Qt槽与C + +的签名`void setEnabled(bool)`。

```
QAction.setFont (self, QFont font)
```

```
QAction.setIcon (self, QIcon icon)
```

```
QAction.setIconText (self, QString text)
```

```
QAction.setIconVisibleInMenu (self, bool visible)
```

```
QAction.setMenu (self, QMenu menu)
```

设置包含在这个动作菜单到指定的_menu_。

**See also** [menu](qaction.html#menu)（ ） 。

```
QAction.setMenuRole (self, MenuRole menuRole)
```

```
QAction.setPriority (self, Priority priority)
```

```
QAction.setSeparator (self, bool b)
```

If _b_是真的，那么这个动作将被视为分隔符。

如何隔板被表示取决于它被插入到插件。在大多数情况下文本，子菜单，图标将被忽略分隔符的行为。

**See also** [QAction.isSeparator](qaction.html#isSeparator)（ ） 。

```
QAction.setShortcut (self, QKeySequence shortcut)
```

```
QAction.setShortcutContext (self, Qt.ShortcutContext context)
```

```
QAction.setShortcuts (self, list-of-QKeySequence shortcuts)
```

Sets _shortcuts_作为触发动作的快捷键列表。列表中的第一个元素是主要的捷径。

这个函数中引入了Qt 4.2中。

**See also** [shortcuts](qaction.html#shortcuts)（）和[shortcut](qaction.html#shortcut-prop)。

```
QAction.setShortcuts (self, QKeySequence.StandardKey)
```

设置快捷方式的基础上，一个平台相关的清单_key_。调用此函数的结果将取决于当前运行的平台上。请注意，一个以上的快捷方式可通过此操作分配。如果只有主快捷方式是必需的，使用setShortcut代替。

这个函数中引入了Qt 4.2中。

**See also** [QKeySequence.keyBindings](qkeysequence.html#keyBindings)（ ） 。

```
QAction.setSoftKeyRole (self, SoftKeyRole softKeyRole)
```

```
QAction.setStatusTip (self, QString statusTip)
```

```
QAction.setText (self, QString text)
```

```
QAction.setToolTip (self, QString tip)
```

```
QAction.setVisible (self, bool)
```

这种方法也是一个Qt槽与C + +的签名`void setVisible(bool)`。

```
QAction.setWhatsThis (self, QString what)
```

```
QKeySequence QAction.shortcut (self)
```

[](qkeysequence.html)

```
Qt.ShortcutContext QAction.shortcutContext (self)
```

[

```
list-of-QKeySequence QAction.shortcuts (self)
```

返回快捷键的列表，与主快捷键为列表的第一个元素。

这个函数中引入了Qt 4.2中。

](qt.html#ShortcutContext-enum)

[**See also**](qt.html#ShortcutContext-enum) [setShortcuts](qaction.html#setShortcuts)（ ） 。

```
bool QAction.showStatusText (self, QWidget widget = None)
```

更新了相关的状态栏_widget_通过发送一个指定[QStatusTipEvent](qstatustipevent.html)它的父控件。如果返回的事件被送往True，否则返回False 。

如果指定的一个空小部件，则该事件被发送到该操作的父代。

**See also** [statusTip](qaction.html#statusTip-prop)。

```
SoftKeyRole QAction.softKeyRole (self)
```

[

```
QString QAction.statusTip (self)
```

```
QString QAction.text (self)
```

```
QAction.toggle (self)
```

这种方法也是一个Qt槽与C + +的签名`void toggle()`。

](qaction.html#SoftKeyRole-enum)

[这是一个方便的功能为](qaction.html#SoftKeyRole-enum)[checked](qaction.html#checked-prop)属性。连接到它的选中状态更改为相反的状态。

```
QString QAction.toolTip (self)
```

```
QAction.trigger (self)
```

这种方法也是一个Qt槽与C + +的签名`void trigger()`。

这是一个方便的插槽调用激活（触发） 。

```
QString QAction.whatsThis (self)
```

* * *

## Qt Signal Documentation

```
void changed ()
```

这是该信号的默认超载。

这个信号被发射时的动作已经改变。如果你只关心在一个给定的窗口小部件的动作，你可以观察[QWidget.actionEvent](qwidget.html#actionEvent)（ ）发送与[QEvent.ActionChanged](qevent.html#Type-enum)。

**See also** [QWidget.actionEvent](qwidget.html#actionEvent)（ ） 。

```
void hovered ()
```

这是该信号的默认超载。

这个信号被发射时的动作是由用户突出显示的，例如，当用户暂停使用光标移到菜单选项，工具栏按钮，或按下一个操作的快捷键组合。

**See also** [QAction.activate](qaction.html#activate)（ ） 。

```
void toggled (bool)
```

这是该信号的默认超载。

这个信号被发射每当一个辨认的作用改变其[isChecked](qaction.html#checked-prop)（ ）状态。这可以是用户交互的结果，或者是因为[setChecked](qaction.html#checked-prop)（ ）被调用。

_checked_是如果动作被选中真的，还是假的，如果动作是听之任之。

**See also** [QAction.activate](qaction.html#activate)（ ）[QAction.triggered](qaction.html#triggered)（）和[checked](qaction.html#checked-prop)。

```
void triggered (bool = 0)
```

这是该信号的默认超载。

这个信号被发射时的动作是由用户激活的，例如，当用户点击一个菜单选项，工具栏按钮，或按下一个操作的快捷键组合，或当[trigger](qaction.html#trigger)（ ）被调用。值得注意的是，它是_not_当发射[setChecked](qaction.html#checked-prop)（）或[toggle](qaction.html#toggle)（）被调用。

如果动作是可复，_checked_是如果动作被选中真的，还是假的，如果动作是听之任之。

**See also** [QAction.activate](qaction.html#activate)（ ）[QAction.toggled](qaction.html#toggled)（）和[checked](qaction.html#checked-prop)。