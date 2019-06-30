# QEvent Class Reference

## [[QtCore](index.htm) module]

该QEvent的类是所有事件类的基类。事件对象包含事件参数。[More...](#details)

通过继承[QActionEvent](qactionevent.html)，[QChildEvent](qchildevent.html)，[QCloseEvent](qcloseevent.html)，[QDragLeaveEvent](qdragleaveevent.html)，[QDropEvent](qdropevent.html)，[QDynamicPropertyChangeEvent](qdynamicpropertychangeevent.html)，[QFileOpenEvent](qfileopenevent.html)，[QFocusEvent](qfocusevent.html)，[QGestureEvent](qgestureevent.html)，[QGraphicsSceneEvent](qgraphicssceneevent.html)，[QHelpEvent](qhelpevent.html)，[QHideEvent](qhideevent.html)，[QHoverEvent](qhoverevent.html)，[QIconDragEvent](qicondragevent.html)，[QInputEvent](qinputevent.html)，[QInputMethodEvent](qinputmethodevent.html)，[QMoveEvent](qmoveevent.html)，[QPaintEvent](qpaintevent.html)，[QResizeEvent](qresizeevent.html)，[QShortcutEvent](qshortcutevent.html)，[QShowEvent](qshowevent.html)，[SignalEvent](index.htm)，[WrappedEvent](index.htm)，[QStatusTipEvent](qstatustipevent.html)，[QTimerEvent](qtimerevent.html)，[QWhatsThisClickedEvent](qwhatsthisclickedevent.html)和[QWindowStateChangeEvent](qwindowstatechangeevent.html)。

### Types

*   `enum Type { None, Timer, MouseButtonPress, MouseButtonRelease, ..., MaxUser }`

### Methods

*   `__init__ (self, Type type)`
*   `__init__ (self, QEvent)`
*   `accept (self)`
*   `ignore (self)`
*   `bool isAccepted (self)`
*   `setAccepted (self, bool accepted)`
*   `bool spontaneous (self)`
*   `Type type (self)`

### Static Methods

*   `int registerEventType (int hint = -1)`

* * *

## Detailed Description

该QEvent的类是所有事件类的基类。事件对象包含事件参数。

Qt的主事件循环（[QCoreApplication.exec](qcoreapplication.html#exec)（ ） ）获取从事件队列本地窗口系统事件，将它们转换成QEvents ，并将转换事件[QObject](qobject.html)秒。

一般情况下，事件来自底层窗口系统（[spontaneous](qevent.html#spontaneous)（ ）返回True ），但它也可以使用手动发送事件[QCoreApplication.sendEvent](qcoreapplication.html#sendEvent)（）和[QCoreApplication.postEvent](qcoreapplication.html#postEvent)（ ） （[spontaneous](qevent.html#spontaneous)（ ）返回False ） 。

[QObjects](index.htm#qobjects)由有接收事件的[QObject.event](qobject.html#event)（ ）函数调用。该函数可以在子类中重新实现自定义事件处理，并添加额外的事件类型;[QWidget.event](qwidget.html#event)（）是一个显着的例子。默认情况下，事件分派到事件处理程序一样[QObject.timerEvent](qobject.html#timerEvent)（）和[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。[QObject.installEventFilter](qobject.html#installEventFilter)（ ）允许一个对象截获发往另一个对象的事件。

基本的QEvent只包含一个事件类型参数和一个“接受”的标志。在接受标志设置[accept](qevent.html#accept)（ ） ，并与清除[ignore](qevent.html#ignore)（ ） 。这是默认设置，但不靠这个作为子类可以选择清除它在其构造函数。

QEvent的子类包含描述特定事件的附加参数。

* * *

## Type Documentation

```
QEvent.Type
```

这个枚举类型定义Qt中有效的事件类型。的事件类型和专门的类为每种类型如下：

| Constant | Value | Description |
| --- | --- | --- |
| `QEvent.None` | `0` | 而不是一个事件。 |
| `QEvent.AccessibilityDescription` | `130` | 用于查询辅助说明文字（[QAccessibleEvent](index.htm)） 。 |
| `QEvent.AccessibilityHelp` | `119` | 用于查询辅助说明文字（[QAccessibleEvent](index.htm)） 。 |
| `QEvent.AccessibilityPrepare` | `86` | 请求无障碍的信息。 |
| `QEvent.ActionAdded` | `114` | 一个新的行动已添加（[QActionEvent](qactionevent.html)） 。 |
| `QEvent.ActionChanged` | `113` | 一个动作已经改变（[QActionEvent](qactionevent.html)） 。 |
| `QEvent.ActionRemoved` | `115` | 动作已被删除（[QActionEvent](qactionevent.html)） 。 |
| `QEvent.ActivationChange` | `99` | Widget的顶层窗口的激活状态发生了变化。 |
| `QEvent.ApplicationActivate` | `121` | 该应用程序已被提供给用户。 |
| `QEvent.ApplicationActivated` | `ApplicationActivate` | 这个枚举已弃用。使用ApplicationActivate代替。 |
| `QEvent.ApplicationDeactivate` | `122` | 该应用程序已暂停，并且是不可用的用户。 |
| `QEvent.ApplicationFontChange` | `36` | 默认的应用程序的字体已经改变。 |
| `QEvent.ApplicationLayoutDirectionChange` | `37` | 默认的应用程序布局的方向发生了变化。 |
| `QEvent.ApplicationPaletteChange` | `38` | 默认的应用程序的调色板已经改变。 |
| `QEvent.ApplicationWindowIconChange` | `35` | 该应用程序的图标发生了变化。 |
| `QEvent.ChildAdded` | `68` | 一个对象得到一个孩子（[QChildEvent](qchildevent.html)） 。 |
| `QEvent.ChildInserted` | `70` | 一个对象得到一个孩子（[QChildEvent](qchildevent.html)） 。[Qt3Support](index.htm)只是，使用ChildAdded代替。 |
| `QEvent.ChildPolished` | `69` | 一个widget孩子被抛光（[QChildEvent](qchildevent.html)） 。 |
| `QEvent.ChildRemoved` | `71` | 对象失去一个孩子（[QChildEvent](qchildevent.html)） 。 |
| `QEvent.Clipboard` | `40` | 剪贴板中的内容已经改变（ QClipboardEvent ） 。 |
| `QEvent.Close` | `19` | 窗口小部件被关闭（[QCloseEvent](qcloseevent.html)） 。 |
| `QEvent.CloseSoftwareInputPanel` | `200` | 一个widget要关闭该软件输入面板（SIP ） 。 |
| `QEvent.ContentsRectChange` | `178` | widget的内容矩形的边缘改变。 |
| `QEvent.ContextMenu` | `82` | 上下文弹出菜单（[QContextMenuEvent](qcontextmenuevent.html)） 。 |
| `QEvent.CursorChange` | `183` | widget的指针已经改变。 |
| `QEvent.DeferredDelete` | `52` | 后，它已清理的对象将被删除。 |
| `QEvent.DragEnter` | `60` | 光标一个拖放操作过程中进入一个小部件（[QDragEnterEvent](qdragenterevent.html)） 。 |
| `QEvent.DragLeave` | `62` | 光标一个拖放操作过程中留下一个小部件（[QDragLeaveEvent](qdragleaveevent.html)） 。 |
| `QEvent.DragMove` | `61` | 拖放操作过程中（[QDragMoveEvent](qdragmoveevent.html)） 。 |
| `QEvent.Drop` | `63` | 拖放操作完成（[QDropEvent](qdropevent.html)） 。 |
| `QEvent.EnabledChange` | `98` | Widget的启用状态已经改变。 |
| `QEvent.Enter` | `10` | 鼠标进入widget的边界。 |
| `QEvent.EnterEditFocus` | `150` | 一个编辑器控件获得焦点时进行编辑。 |
| `QEvent.EnterWhatsThisMode` | `124` | 发送到顶层widget开发应用程序进入“这是什么？ ”模式。 |
| `QEvent.FileOpen` | `116` | 打开文件的请求（[QFileOpenEvent](qfileopenevent.html)） 。 |
| `QEvent.FocusIn` | `8` | 窗口小部件获得键盘焦点（[QFocusEvent](qfocusevent.html)） 。 |
| `QEvent.FocusOut` | `9` | 窗口小部件失去键盘焦点（[QFocusEvent](qfocusevent.html)） 。 |
| `QEvent.FontChange` | `97` | Widget的字体已经改变。 |
| `QEvent.GrabKeyboard` | `188` | 项目收益键盘捕获（[QGraphicsItem](qgraphicsitem.html)只）。 |
| `QEvent.GrabMouse` | `186` | 项目获得鼠标抓（[QGraphicsItem](qgraphicsitem.html)只）。 |
| `QEvent.GraphicsSceneContextMenu` | `159` | 在图形场景上下文弹出菜单（[QGraphicsSceneContextMenuEvent](qgraphicsscenecontextmenuevent.html)） 。 |
| `QEvent.GraphicsSceneDragEnter` | `164` | 光标一个拖放操作过程中进入一个图形场景（[QGraphicsSceneDragDropEvent](qgraphicsscenedragdropevent.html)） 。 |
| `QEvent.GraphicsSceneDragLeave` | `166` | 光标一个拖放操作过程中留下的图形场景（[QGraphicsSceneDragDropEvent](qgraphicsscenedragdropevent.html)） 。 |
| `QEvent.GraphicsSceneDragMove` | `165` | 拖放操作是在一个场景中的进展（[QGraphicsSceneDragDropEvent](qgraphicsscenedragdropevent.html)） 。 |
| `QEvent.GraphicsSceneDrop` | `167` | 拖放操作完成了一个场景（[QGraphicsSceneDragDropEvent](qgraphicsscenedragdropevent.html)） 。 |
| `QEvent.GraphicsSceneHelp` | `163` | 用户请求帮助的图形场景（[QHelpEvent](qhelpevent.html)） 。 |
| `QEvent.GraphicsSceneHoverEnter` | `160` | 鼠标光标进入悬停项目在图形场景（[QGraphicsSceneHoverEvent](qgraphicsscenehoverevent.html)） 。 |
| `QEvent.GraphicsSceneHoverLeave` | `162` | 将鼠标光标离开悬停项目在图形场景（[QGraphicsSceneHoverEvent](qgraphicsscenehoverevent.html)） 。 |
| `QEvent.GraphicsSceneHoverMove` | `161` | 将鼠标光标悬停项目内移动在图形场景（[QGraphicsSceneHoverEvent](qgraphicsscenehoverevent.html)） 。 |
| `QEvent.GraphicsSceneMouseDoubleClick` | `158` | 鼠标再次按下（双击）在图形场景（[QGraphicsSceneMouseEvent](qgraphicsscenemouseevent.html)） 。 |
| `QEvent.GraphicsSceneMouseMove` | `155` | 移动鼠标在图形场景（[QGraphicsSceneMouseEvent](qgraphicsscenemouseevent.html)） 。 |
| `QEvent.GraphicsSceneMousePress` | `156` | 在图形场景中按下鼠标（[QGraphicsSceneMouseEvent](qgraphicsscenemouseevent.html)） 。 |
| `QEvent.GraphicsSceneMouseRelease` | `157` | 释放鼠标在图形场景（[QGraphicsSceneMouseEvent](qgraphicsscenemouseevent.html)） 。 |
| `QEvent.GraphicsSceneMove` | `182` | 窗口小部件被感动（[QGraphicsSceneMoveEvent](qgraphicsscenemoveevent.html)） 。 |
| `QEvent.GraphicsSceneResize` | `181` | 小部件调整大小（[QGraphicsSceneResizeEvent](qgraphicssceneresizeevent.html)） 。 |
| `QEvent.GraphicsSceneWheel` | `168` | 在图形场景中鼠标滚轮滚动（[QGraphicsSceneWheelEvent](qgraphicsscenewheelevent.html)） 。 |
| `QEvent.Hide` | `18` | 窗口小部件被隐藏（[QHideEvent](qhideevent.html)） 。 |
| `QEvent.HideToParent` | `27` | 孩子小部件已被隐藏。 |
| `QEvent.HoverEnter` | `127` | 鼠标光标进入悬停窗口小部件（[QHoverEvent](qhoverevent.html)） 。 |
| `QEvent.HoverLeave` | `128` | 将鼠标光标离开悬停窗口小部件（[QHoverEvent](qhoverevent.html)） 。 |
| `QEvent.HoverMove` | `129` | 将鼠标光标悬停widget内移动（[QHoverEvent](qhoverevent.html)） 。 |
| `QEvent.IconDrag` | `96` | 窗口的主图标已经被拖走（[QIconDragEvent](qicondragevent.html)） 。 |
| `QEvent.IconTextChange` | `101` | Widget的图标已被修改。 |
| `QEvent.InputMethod` | `83` | 一种输入方法正在使用（[QInputMethodEvent](qinputmethodevent.html)） 。 |
| `QEvent.KeyPress` | `6` | 按键（[QKeyEvent](qkeyevent.html)） 。 |
| `QEvent.KeyRelease` | `7` | 键释放（[QKeyEvent](qkeyevent.html)） 。 |
| `QEvent.LanguageChange` | `89` | 该应用程序翻译修改。 |
| `QEvent.LayoutDirectionChange` | `90` | 布局的方向改变。 |
| `QEvent.LayoutRequest` | `76` | 小部件的布局需要重做。 |
| `QEvent.Leave` | `11` | 鼠标离开控件的边界。 |
| `QEvent.LeaveEditFocus` | `151` | 一个编辑器控件失去焦点时进行编辑。 |
| `QEvent.LeaveWhatsThisMode` | `125` | 发送到顶层的小部件应用程序离开时， “这是什么？ ”模式。 |
| `QEvent.LocaleChange` | `88` | 系统语言环境发生了变化。 |
| `QEvent.NonClientAreaMouseButtonDblClick` | `176` | 鼠标双击发生在客户区之外。 |
| `QEvent.NonClientAreaMouseButtonPress` | `174` | 鼠标按下按钮时发生的工作区之外。 |
| `QEvent.NonClientAreaMouseButtonRelease` | `175` | 鼠标按钮释放发生在客户区之外。 |
| `QEvent.NonClientAreaMouseMove` | `173` | 鼠标移动时发生的工作区之外。 |
| `QEvent.MacSizeChange` | `177` | 用户改变了他的部件尺寸（仅限Mac OS X ） 。 |
| `QEvent.MenubarUpdated` | `153` | 该窗口的菜单栏已更新。 |
| `QEvent.MetaCall` | `43` | 通过异步方法调用[QMetaObject.invokeMethod](qmetaobject.html#invokeMethod)（ ） 。 |
| `QEvent.ModifiedChange` | `102` | 小工具修改状态已经改变。 |
| `QEvent.MouseButtonDblClick` | `4` | 鼠标再次按（[QMouseEvent](qmouseevent.html)） 。 |
| `QEvent.MouseButtonPress` | `2` | 按下鼠标（[QMouseEvent](qmouseevent.html)） 。 |
| `QEvent.MouseButtonRelease` | `3` | 鼠标释放（[QMouseEvent](qmouseevent.html)） 。 |
| `QEvent.MouseMove` | `5` | 鼠标移动（[QMouseEvent](qmouseevent.html)） 。 |
| `QEvent.MouseTrackingChange` | `109` | 鼠标跟踪状态已经改变。 |
| `QEvent.Move` | `13` | widget的位置改变（[QMoveEvent](qmoveevent.html)） 。 |
| `QEvent.Paint` | `12` | 屏幕更新必要的（[QPaintEvent](qpaintevent.html)） 。 |
| `QEvent.PaletteChange` | `39` | 窗口小部件的调色板改变。 |
| `QEvent.ParentAboutToChange` | `131` | 窗口小部件的父即将改变。 |
| `QEvent.ParentChange` | `21` | 窗口小部件的父已经改变。 |
| `QEvent.PlatformPanel` | `212` | 特定于平台的面板已要求。 |
| `QEvent.Polish` | `75` | 窗口小部件进行抛光。 |
| `QEvent.PolishRequest` | `74` | 窗口小部件应进行打磨。 |
| `QEvent.QueryWhatsThis` | `123` | 该部件应该接受的情况下，如果它“这是什么？ ”帮助。 |
| `QEvent.RequestSoftwareInputPanel` | `199` | 一个widget要开一个软件输入面板（SIP ） 。 |
| `QEvent.Resize` | `14` | widget的大小改变（[QResizeEvent](qresizeevent.html)） 。 |
| `QEvent.Shortcut` | `117` | 在孩子的快捷键操作按键（[QShortcutEvent](qshortcutevent.html)） 。 |
| `QEvent.ShortcutOverride` | `51` | 在孩子的按键，为压倒一切的快捷键操作（[QKeyEvent](qkeyevent.html)） 。 |
| `QEvent.Show` | `17` | 窗口小部件被显示在屏幕上（[QShowEvent](qshowevent.html)） 。 |
| `QEvent.ShowToParent` | `26` | 孩子小部件已被证明。 |
| `QEvent.SockAct` | `50` | 插座激活，用于实现[QSocketNotifier](qsocketnotifier.html)。 |
| `QEvent.StateMachineSignal` | `192` | 交付给一个状态机（信号[QStateMachine.SignalEvent](index.htm)） 。 |
| `QEvent.StateMachineWrapped` | `193` | 本次活动是一个包装，即包含，另一个事件（[QStateMachine.WrappedEvent](index.htm)） 。 |
| `QEvent.StatusTip` | `112` | 一个状态提示要求（[QStatusTipEvent](qstatustipevent.html)） 。 |
| `QEvent.StyleChange` | `100` | widget的风格已经改变了。 |
| `QEvent.TabletMove` | `87` | Wacom数位板移动（[QTabletEvent](qtabletevent.html)） 。 |
| `QEvent.TabletPress` | `92` | Wacom数位板按（[QTabletEvent](qtabletevent.html)） 。 |
| `QEvent.TabletRelease` | `93` | Wacom数位板发布（[QTabletEvent](qtabletevent.html)） 。 |
| `QEvent.OkRequest` | `94` | 在装修ok键按下。仅适用于Windows CE所支持。 |
| `QEvent.TabletEnterProximity` | `171` | Wacom数位板进入接近事件（[QTabletEvent](qtabletevent.html)） ，发送到[QApplication](qapplication.html)。 |
| `QEvent.TabletLeaveProximity` | `172` | Wacom数位板假期接近事件（[QTabletEvent](qtabletevent.html)） ，发送到[QApplication](qapplication.html)。 |
| `QEvent.Timer` | `1` | 常规的定时器​​事件（[QTimerEvent](qtimerevent.html)） 。 |
| `QEvent.ToolBarChange` | `120` | 该工具栏按钮是切换在Mac OS X |
| `QEvent.ToolTip` | `110` | 请求了工具提示（[QHelpEvent](qhelpevent.html)） 。 |
| `QEvent.ToolTipChange` | `184` | widget的工具提示发生了变化。 |
| `QEvent.UngrabKeyboard` | `189` | 项目失去键盘抢（[QGraphicsItem](qgraphicsitem.html)只）。 |
| `QEvent.UngrabMouse` | `187` | 项目失去鼠标抓（[QGraphicsItem](qgraphicsitem.html)只）。 |
| `QEvent.UpdateLater` | `78` | 窗口小部件应进行排队在稍后的时间重新绘制。 |
| `QEvent.UpdateRequest` | `77` | 窗口小部件，应重新绘制。 |
| `QEvent.WhatsThis` | `111` | 窗口小部件应显示“这是什么？ ”帮助（[QHelpEvent](qhelpevent.html)） 。 |
| `QEvent.WhatsThisClicked` | `118` | 在widget的一个链接“这是什么？ ”帮助被点击了。 |
| `QEvent.Wheel` | `31` | 鼠标滚轮滚动（[QWheelEvent](qwheelevent.html)） 。 |
| `QEvent.WinEventAct` | `132` | 发生了针对Windows的激活事件。 |
| `QEvent.WindowActivate` | `24` | 窗口被激活。 |
| `QEvent.WindowBlocked` | `103` | 该窗口被阻止通过一个模态对话框。 |
| `QEvent.WindowDeactivate` | `25` | 窗口被激活。 |
| `QEvent.WindowIconChange` | `34` | 窗口的图标发生了变化。 |
| `QEvent.WindowStateChange` | `105` | 该[window's state](qwidget.html#windowState)（最小化，最大化或全屏）已经改变（[QWindowStateChangeEvent](qwindowstatechangeevent.html)） 。 |
| `QEvent.WindowTitleChange` | `33` | 一直窗口标题改变。 |
| `QEvent.WindowUnblocked` | `104` | 该窗口是畅通的一个模态对话框退出后。 |
| `QEvent.ZOrderChange` | `126` | widget的Z顺序发生了变化。此事件不会发送给顶层窗口。 |
| `QEvent.KeyboardLayoutChange` | `169` | 键盘布局发生了变化。 |
| `QEvent.DynamicPropertyChange` | `170` | 动态属性添加，更改或从对象中删除。 |
| `QEvent.TouchBegin` | `194` | 开始的触摸屏和/或跟踪垫的事件序列（[QTouchEvent](qtouchevent.html)） |
| `QEvent.TouchUpdate` | `195` | 触摸屏事件（[QTouchEvent](qtouchevent.html)） |
| `QEvent.TouchEnd` | `196` | 触摸事件序列结束（[QTouchEvent](qtouchevent.html)） |
| `QEvent.WinIdChange` | `203` | 窗口系统标识符为这个原生窗口部件已经改变 |
| `QEvent.Gesture` | `198` | 手势被触发（[QGestureEvent](qgestureevent.html)） |
| `QEvent.GestureOverride` | `202` | 手势复盖被触发（[QGestureEvent](qgestureevent.html)） |

用户事件应具备的价值观`User`和`MaxUser`：

| Constant | Value | Description |
| --- | --- | --- |
| `QEvent.User` | `1000` | 用户定义的事件。 |
| `QEvent.MaxUser` | `65535` | 最后用户事件ID。 |

为方便起见，你可以使用[registerEventType](qevent.html#registerEventType)（ ）函数来注册的和预定你的应用程序的自定义事件类型。这样做可以让你避免意外重新使用已经在使用自定义事件类型的应用程序中的其他地方。

* * *

## Method Documentation

```
QEvent.__init__ (self, Type type)
```

Contructs类型的事件对象_type_。

```
QEvent.__init__ (self, QEvent)
```

```
QEvent.accept (self)
```

设置事件对象，调用setAccepted （真）的等价的接受标志。

设定接受参数表示该事件接收器想要的事件。不需要的事件可能会被传播到父widget 。

**See also** [ignore](qevent.html#ignore)（ ） 。

```
QEvent.ignore (self)
```

清除事件对象的接受标志参数，调用setAccepted （假）的等价物。

清除接受参数表示事件接收器不想要的事件。不需要的事件可能会被传播到父widget 。

**See also** [accept](qevent.html#accept)（ ） 。

```
bool QEvent.isAccepted (self)
```

```
int QEvent.registerEventType (int hint = -1)
```

寄存器并返回一个自定义的事件类型。该_hint_设置将被使用，如果它是可用的，否则会之间返回值[QEvent.User](qevent.html#Type-enum)和[QEvent.MaxUser](qevent.html#Type-enum)一个尚未被注册。该_hint_如果其值不间被忽略[QEvent.User](qevent.html#Type-enum)和[QEvent.MaxUser](qevent.html#Type-enum)。

**Note:**这个功能是[thread-safe](index.htm#thread-safe)。

此功能被引入Qt的4.4 。

```
QEvent.setAccepted (self, bool accepted)
```

```
bool QEvent.spontaneous (self)
```

返回True如果该事件起源于应用程序（系统事件）之外，否则返回False 。

这个函数的返回值是没有定义的绘制事件。

```
Type QEvent.type (self)
```

[

返回的事件类型。

](qevent.html#Type-enum)