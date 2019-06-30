# QGraphicsWidget Class Reference

## [[QtGui](index.htm) module]

该QGraphicsWidget类是在所有部件项目的基类[QGraphicsScene](qgraphicsscene.html)。[More...](#details)

继承[QGraphicsObject](qgraphicsobject.html)和[QGraphicsLayoutItem](qgraphicslayoutitem.html)。

通过继承[QGraphicsProxyWidget](qgraphicsproxywidget.html)和[QGraphicsWebView](qgraphicswebview.html)。

### Methods

*   `__init__ (self, QGraphicsItem parent = None, Qt.WindowFlags flags = 0)`
*   `list-of-QAction actions (self)`
*   `addAction (self, QAction action)`
*   `addActions (self, list-of-QAction actions)`
*   `adjustSize (self)`
*   `bool autoFillBackground (self)`
*   `QRectF boundingRect (self)`
*   `changeEvent (self, QEvent event)`
*   `bool close (self)`
*   `closeEvent (self, QCloseEvent event)`
*   `bool event (self, QEvent event)`
*   `focusInEvent (self, QFocusEvent event)`
*   `bool focusNextPrevChild (self, bool next)`
*   `focusOutEvent (self, QFocusEvent event)`
*   `Qt.FocusPolicy focusPolicy (self)`
*   `QGraphicsWidget focusWidget (self)`
*   `QFont font (self)`
*   `(float left, float top, float right, float bottom) getContentsMargins (self)`
*   `(float left, float top, float right, float bottom) getWindowFrameMargins (self)`
*   `grabKeyboardEvent (self, QEvent event)`
*   `grabMouseEvent (self, QEvent event)`
*   `int grabShortcut (self, QKeySequence sequence, Qt.ShortcutContext context = Qt.WindowShortcut)`
*   `hideEvent (self, QHideEvent event)`
*   `hoverLeaveEvent (self, QGraphicsSceneHoverEvent event)`
*   `hoverMoveEvent (self, QGraphicsSceneHoverEvent event)`
*   `initStyleOption (self, QStyleOption option)`
*   `insertAction (self, QAction before, QAction action)`
*   `insertActions (self, QAction before, list-of-QAction actions)`
*   `bool isActiveWindow (self)`
*   `QVariant itemChange (self, QGraphicsItem.GraphicsItemChange change, QVariant value)`
*   `QGraphicsLayout layout (self)`
*   `Qt.LayoutDirection layoutDirection (self)`
*   `moveEvent (self, QGraphicsSceneMoveEvent event)`
*   `paint (self, QPainter painter, QStyleOptionGraphicsItem option, QWidget widget = None)`
*   `paintWindowFrame (self, QPainter painter, QStyleOptionGraphicsItem option, QWidget widget = None)`
*   `QPalette palette (self)`
*   `polishEvent (self)`
*   `QRectF rect (self)`
*   `releaseShortcut (self, int id)`
*   `removeAction (self, QAction action)`
*   `resize (self, QSizeF size)`
*   `resize (self, float w, float h)`
*   `resizeEvent (self, QGraphicsSceneResizeEvent event)`
*   `bool sceneEvent (self, QEvent event)`
*   `setAttribute (self, Qt.WidgetAttribute attribute, bool on = True)`
*   `setAutoFillBackground (self, bool enabled)`
*   `setContentsMargins (self, float left, float top, float right, float bottom)`
*   `setFocusPolicy (self, Qt.FocusPolicy policy)`
*   `setFont (self, QFont font)`
*   `setGeometry (self, QRectF rect)`
*   `setGeometry (self, float ax, float ay, float aw, float ah)`
*   `setLayout (self, QGraphicsLayout layout)`
*   `setLayoutDirection (self, Qt.LayoutDirection direction)`
*   `setPalette (self, QPalette palette)`
*   `setShortcutAutoRepeat (self, int id, bool enabled = True)`
*   `setShortcutEnabled (self, int id, bool enabled = True)`
*   `setStyle (self, QStyle style)`
*   `setWindowFlags (self, Qt.WindowFlags wFlags)`
*   `setWindowFrameMargins (self, float left, float top, float right, float bottom)`
*   `setWindowTitle (self, QString title)`
*   `QPainterPath shape (self)`
*   `showEvent (self, QShowEvent event)`
*   `QSizeF size (self)`
*   `QSizeF sizeHint (self, Qt.SizeHint which, QSizeF constraint = QSizeF())`
*   `QStyle style (self)`
*   `bool testAttribute (self, Qt.WidgetAttribute attribute)`
*   `int type (self)`
*   `ungrabKeyboardEvent (self, QEvent event)`
*   `ungrabMouseEvent (self, QEvent event)`
*   `unsetLayoutDirection (self)`
*   `unsetWindowFrameMargins (self)`
*   `updateGeometry (self)`
*   `Qt.WindowFlags windowFlags (self)`
*   `bool windowFrameEvent (self, QEvent e)`
*   `QRectF windowFrameGeometry (self)`
*   `QRectF windowFrameRect (self)`
*   `Qt.WindowFrameSection windowFrameSectionAt (self, QPointF pos)`
*   `QString windowTitle (self)`
*   `Qt.WindowType windowType (self)`

### Static Methods

*   `setTabOrder (QGraphicsWidget first, QGraphicsWidget second)`

### Qt Signals

*   `void geometryChanged ()`

* * *

## Detailed Description

该QGraphicsWidget类是在所有部件项目的基类[QGraphicsScene](qgraphicsscene.html)。

QGraphicsWidget是一个扩展的基地项目，超过提供额外的功能[QGraphicsItem](qgraphicsitem.html)。它类似于[QWidget](qwidget.html)在很多方面：

*   Provides a [palette](qgraphicswidget.html#palette-prop), a [font](qgraphicswidget.html#font-prop) and a [style](qgraphicswidget.html#style)().
*   Has a defined [geometry](qgraphicslayoutitem.html#geometry)().
*   Supports layouts with [setLayout](qgraphicswidget.html#layout-prop)() and [layout](qgraphicswidget.html#layout-prop)().
*   Supports shortcuts and actions with [grabShortcut](qgraphicswidget.html#grabShortcut)() and [insertAction](qgraphicswidget.html#insertAction)()

不像[QGraphicsItem](qgraphicsitem.html)， QGraphicsWidget不是一个抽象类，你可以创建一个QGraphicsWidget的实例，而无需继承它。这种方法对小部件，只有服务于构建子控件到布局的目的是有用的。

QGraphicsWidget如果您需要先进的输入焦点的处理，例如，标籤对焦和激活，或布局被用来作为自己的自定义项目的基础项目。

由于QGraphicsWidget酷似[QWidget](qwidget.html)并具有类似的API ，它更容易端口插件从[QWidget](qwidget.html)到QGraphicsWidget ，而不是[QGraphicsItem](qgraphicsitem.html)。

**Note:** [QWidget](qwidget.html)基于窗口小部件可以被直接嵌入到一个[QGraphicsScene](qgraphicsscene.html) using [QGraphicsProxyWidget](qgraphicsproxywidget.html)。

QGraphicsWidget之间明显的差异[QWidget](qwidget.html)分别是：

| QGraphicsWidget | [QWidget](qwidget.html) |
| --- | --- |
| Coordinates and geometry are defined with qreals (doubles or floats, depending on the platform). | [QWidget](qwidget.html) uses integer geometry ([QPoint](qpoint.html), [QRect](qrect.html)). |
| The widget is already visible by default; you do not have to call [show](qgraphicsitem.html#show)() to display the widget. | [QWidget](qwidget.html) is hidden by default until you call [show](qgraphicsitem.html#show)(). |
| A subset of widget attributes are supported. | All widget attributes are supported. |
| A top-level item's style defaults to QGraphicsScene.style | A top-level widget's style defaults to QApplication.style |
| Graphics View provides a custom drag and drop framework, different from [QWidget](qwidget.html). | Standard drag and drop framework. |
| Widget items do not support modality. | Full modality support. |

QGraphicsWidget支持Qt的窗口部件的属性的一个子集， （[Qt.WidgetAttribute](qt.html#WidgetAttribute-enum)）所示，在下表中。本表中未列出的任何属性是不支持的，或以其他方式使用。

| Widget Attribute | Usage |
| --- | --- |
| [Qt.WA_SetLayoutDirection](qt.html#WidgetAttribute-enum) | Set by [setLayoutDirection](qgraphicswidget.html#layoutDirection-prop)(), cleared by [unsetLayoutDirection](qgraphicswidget.html#layoutDirection-prop)(). You can test this attribute to check if the widget has been explicitly assigned a [layoutDirection](qgraphicswidget.html#layoutDirection-prop). If the attribute is not set, the [layoutDirection()](qgraphicswidget.html#layoutDirection-prop) is inherited. |
| [Qt.WA_RightToLeft](qt.html#WidgetAttribute-enum) | Toggled by [setLayoutDirection](qgraphicswidget.html#layoutDirection-prop)(). Inherited from the parent/scene. If set, the widget's layout will order horizontally arranged widgets from right to left. |
| [Qt.WA_SetStyle](qt.html#WidgetAttribute-enum) | Set and cleared by [setStyle](qgraphicswidget.html#setStyle)(). If this attribute is set, the widget has been explicitly assigned a style. If it is unset, the widget will use the scene's or the application's style. |
| [Qt.WA_Resized](qt.html#WidgetAttribute-enum) | Set by [setGeometry](qgraphicswidget.html#geometry-prop)() and [resize](qgraphicswidget.html#size-prop)(). |
| [Qt.WA_SetPalette](qt.html#WidgetAttribute-enum) | Set by [setPalette](qgraphicswidget.html#palette-prop)(). |
| [Qt.WA_SetFont](qt.html#WidgetAttribute-enum) | Set by [setFont](qgraphicswidget.html#font-prop)(). |
| [Qt.WA_WindowPropagation](qt.html#WidgetAttribute-enum) | Enables propagation to window widgets. |

虽然QGraphicsWidget从两个继承[QObject](qobject.html)和[QGraphicsItem](qgraphicsitem.html)，你应该使用所提供的功能[QGraphicsItem](qgraphicsitem.html)，_not_ [QObject](qobject.html)，管理父和子项之间的关系。这些功能控制项目的堆叠顺序以及它们的所有权。

**Note:**该[QObject.parent](qobject.html#parent)（ ）应该总是返回0 QGraphicsWidgets ，但这项政策没有严格的定义。

* * *

## Method Documentation

```
QGraphicsWidget.__init__ (self, QGraphicsItem parent = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QGraphicsWidget](qgraphicswidget.html)实例。可选的_parent_参数被传递给[QGraphicsItem](qgraphicsitem.html)的构造。可选的_wFlags_参数指定了小部件的窗口标志（例如，小部件是否应该是一个窗口，一个工具，一个弹出式等） 。

```
list-of-QAction QGraphicsWidget.actions (self)
```

返回这个窗口部件的动作（可能为空）列表。

此功能被引入Qt的4.5 。

**See also** [insertAction](qgraphicswidget.html#insertAction)（ ）[removeAction](qgraphicswidget.html#removeAction)（ ）[QWidget.actions](qwidget.html#actions)（ ）[QAction.associatedWidgets](qaction.html#associatedWidgets)（）和[QAction.associatedGraphicsWidgets](qaction.html#associatedGraphicsWidgets)（ ） 。

```
QGraphicsWidget.addAction (self, QAction action)
```

追加行动_action_以行动这个小工具的列表。

所有QGraphicsWidgets具有列表[QAction](qaction.html)秒，但是它们可以被以图形方式在许多不同的方式来表示。在默认情况下使用的[QAction](qaction.html)列表（所返回[actions](qgraphicswidget.html#actions)（））是创建一个上下文[QMenu](qmenu.html)。

A [QGraphicsWidget](qgraphicswidget.html)应该只有每个动作中的一个，并将其添加已经有一个操作不会导致相同的动作是在插件的两倍。

此功能被引入Qt的4.5 。

**See also** [removeAction](qgraphicswidget.html#removeAction)（ ）[insertAction](qgraphicswidget.html#insertAction)（ ）[actions](qgraphicswidget.html#actions)（）和[QWidget.addAction](qwidget.html#addAction)（ ） 。

```
QGraphicsWidget.addActions (self, list-of-QAction actions)
```

追加行动_actions_以行动这个小工具的列表。

此功能被引入Qt的4.5 。

**See also** [removeAction](qgraphicswidget.html#removeAction)（ ）[QMenu](qmenu.html)，[addAction](qgraphicswidget.html#addAction)（）和[QWidget.addActions](qwidget.html#addActions)（ ） 。

```
QGraphicsWidget.adjustSize (self)
```

调整小部件的大小达到有效的首选大小的提示。

这个函数被调用时隐式的项目显示的第一次。

**See also** [effectiveSizeHint](qgraphicslayoutitem.html#effectiveSizeHint)（）和[Qt.MinimumSize](qt.html#SizeHint-enum)。

```
bool QGraphicsWidget.autoFillBackground (self)
```

```
QRectF QGraphicsWidget.boundingRect (self)
```

[](qrectf.html)

[从重新实现](qrectf.html)[QGraphicsItem.boundingRect](qgraphicsitem.html#boundingRect)（ ） 。

```
QGraphicsWidget.changeEvent (self, QEvent event)
```

此事件处理程序可以重新实现来处理状态的变化。

在这种情况下被改变的状态可以通过检索_event_。

更改事件包括：[QEvent.ActivationChange](qevent.html#Type-enum)，[QEvent.EnabledChange](qevent.html#Type-enum)，[QEvent.FontChange](qevent.html#Type-enum)，[QEvent.StyleChange](qevent.html#Type-enum)，[QEvent.PaletteChange](qevent.html#Type-enum)，[QEvent.ParentChange](qevent.html#Type-enum)，[QEvent.LayoutDirectionChange](qevent.html#Type-enum)和[QEvent.ContentsRectChange](qevent.html#Type-enum)。

```
bool QGraphicsWidget.close (self)
```

这种方法也是一个Qt槽与C + +的签名`bool close()`。

调用这个函数来关闭该窗口小部件。

返回True如果部件被关闭，否则返回False 。此插槽会先发送一个[QCloseEvent](qcloseevent.html)到窗口小部件，它可以或不可以接受的事件。如果事件被忽略，没有任何反应。如果事件被接受，它会[hide](qgraphicsitem.html#hide)（）的部件。

如果部件有[Qt.WA_DeleteOnClose](qt.html#WidgetAttribute-enum)属性设置将被删除。

```
QGraphicsWidget.closeEvent (self, QCloseEvent event)
```

此事件处理程序，对于_event_，可重新实现在子类中接收部件关闭事件。默认实现接受的事件。

**See also** [close](qgraphicswidget.html#close)（）和[QCloseEvent](qcloseevent.html)。

```
bool QGraphicsWidget.event (self, QEvent event)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

处理_event_。[QGraphicsWidget](qgraphicswidget.html)处理以下事项：

| Polish | Delivered to the widget some time after it has been shown. |
| GraphicsSceneMove | Delivered to the widget after its local position has changed. |
| GraphicsSceneResize | Delivered to the widget after its size has changed. |
| Show | Delivered to the widget before it has been shown. |
| Hide | Delivered to the widget after it has been hidden. |
| PaletteChange | Delivered to the widget after its palette has changed. |
| FontChange | Delivered to the widget after its font has changed. |
| EnabledChange | Delivered to the widget after its enabled state has changed. |
| StyleChange | Delivered to the widget after its style has changed. |
| LayoutDirectionChange | Delivered to the widget after its layout direction has changed. |
| ContentsRectChange | Delivered to the widget after its contents margins/ contents rect has changed. |

```
QGraphicsWidget.focusInEvent (self, QFocusEvent event)
```

从重新实现[QGraphicsItem.focusInEvent](qgraphicsitem.html#focusInEvent)（ ） 。

```
bool QGraphicsWidget.focusNextPrevChild (self, bool next)
```

发现一个新的widget ，让键盘焦点，以适合Tab和Shift + Tab键，如果能找到一个新的widget返回True，否则返回False 。如果_next_诚然，这个函数向前搜索，如果_next_是假的，它向后搜索。

有时候，你会希望重新实现这个功能，为您的小工具，其subwidgets提供特别注重处理。例如，一个Web浏览器可能会重新实现它移动到其当前活动链接向前或向后，并调用基实现，只有当它到达页面上的最后一个或第一个链接。

子控件调用focusNextPrevChild （ ）对它们的父窗口部件，但只有包含的子控件的窗口决定重定向到哪里焦点。通过重新实现这个函数的对象时，你获得控制焦点遍历所有子控件。

**See also** [focusPolicy](qgraphicswidget.html#focusPolicy-prop)（ ） 。

```
QGraphicsWidget.focusOutEvent (self, QFocusEvent event)
```

从重新实现[QGraphicsItem.focusOutEvent](qgraphicsitem.html#focusOutEvent)（ ） 。

```
Qt.FocusPolicy QGraphicsWidget.focusPolicy (self)
```

[](qt.html#FocusPolicy-enum)

```
QGraphicsWidget QGraphicsWidget.focusWidget (self)
```

[

如果这个小工具的这个小工具，一个孩子或后代目前拥有输入焦点时，这个函数会返回一个指向窗口小部件。如果没有后代部件有输入焦点，则返回0 。

](qgraphicswidget.html)

[**See also**](qgraphicswidget.html) [QGraphicsItem.focusItem](qgraphicsitem.html#focusItem)（）和[QWidget.focusWidget](qwidget.html#focusWidget)（ ） 。

```
QFont QGraphicsWidget.font (self)
```

[

```
(float left, float top, float right, float bottom) QGraphicsWidget.getContentsMargins (self)
```

](qfont.html)

[从重新实现](qfont.html)[QGraphicsLayoutItem.getContentsMargins](qgraphicslayoutitem.html#getContentsMargins)（ ） 。

获取控件的内容利润率。页边距都存储在_left_，_top_，_right_和_bottom_，作为指针指向qreals 。每个参数可以是_omitted_通过传递0 。

**See also** [setContentsMargins](qgraphicswidget.html#setContentsMargins)（ ） 。

```
(float left, float top, float right, float bottom) QGraphicsWidget.getWindowFrameMargins (self)
```

获取控件的窗口框架的利润。页边距都存储在_left_，_top_，_right_和_bottom_作为指针指向qreals 。每个参数可以是_omitted_通过传递0 。

**See also** [setWindowFrameMargins](qgraphicswidget.html#setWindowFrameMargins)（）和[windowFrameRect](qgraphicswidget.html#windowFrameRect)（ ） 。

```
QGraphicsWidget.grabKeyboardEvent (self, QEvent event)
```

此事件处理程序，对于_event_，可以在子类来接收通知被重新实现[QEvent.GrabKeyboard](qevent.html#Type-enum)事件。

**See also** [grabKeyboard](qgraphicsitem.html#grabKeyboard)（）和[grabMouse](qgraphicsitem.html#grabMouse)（ ） 。

```
QGraphicsWidget.grabMouseEvent (self, QEvent event)
```

此事件处理程序，对于_event_，可以在子类来接收通知被重新实现[QEvent.GrabMouse](qevent.html#Type-enum)事件。

**See also** [grabMouse](qgraphicsitem.html#grabMouse)（）和[grabKeyboard](qgraphicsitem.html#grabKeyboard)（ ） 。

```
int QGraphicsWidget.grabShortcut (self, QKeySequence sequence, Qt.ShortcutContext context = Qt.WindowShortcut)
```

增加了一个快捷方式到Qt的快捷键系统，手表对于给定的键_sequence_在给定的_context_。如果_context_ is [Qt.ApplicationShortcut](qt.html#ShortcutContext-enum)，快捷适用于应用程序作为一个整体。否则，要么是本地的这个小工具，[Qt.WidgetShortcut](qt.html#ShortcutContext-enum)，或者窗口本身，[Qt.WindowShortcut](qt.html#ShortcutContext-enum)。对于小部件不属于窗口的一部分（即顶层widget和他们的孩子） ，[Qt.WindowShortcut](qt.html#ShortcutContext-enum)快捷方式适用于现场。

如果相同的密钥_sequence_已经抓住了由几个部件，当键_sequence_发生[QEvent.Shortcut](qevent.html#Type-enum)事件被发送到所有的，它适用于非确定性的顺序小部件，而是用``暧昧''标志设置为True 。

**Warning:**你不应该通常需要使用此功能，而是创建[QAction](qaction.html)s的您需要的快捷键顺序（如果你也想等效的菜单选项和工具栏按钮） ，或创建[QShortcut](qshortcut.html)■如果您只需要按键顺序。两[QAction](qaction.html)和[QShortcut](qshortcut.html)处理所有的事件过滤的你，提供当用户触发键序列触发信号，所以更容易比这个低层次的功能使用。

此功能被引入Qt的4.5 。

**See also** [releaseShortcut](qgraphicswidget.html#releaseShortcut)（ ）[setShortcutEnabled](qgraphicswidget.html#setShortcutEnabled)（）和[QWidget.grabShortcut](qwidget.html#grabShortcut)（ ） 。

```
QGraphicsWidget.hideEvent (self, QHideEvent event)
```

此事件处理程序，对于[Hide](qevent.html#Type-enum)事件被交付的部件已被隐藏之后，例如，其setVisible （假）被称为小部件或其祖先之一，当小部件曾表明。

您可以重新实现此事件处理程序来检测，当你的小部件被隐藏。调用[QEvent.accept](qevent.html#accept)（）或[QEvent.ignore](qevent.html#ignore)（ ）上_event_没有任何影响。

**See also** [showEvent](qgraphicswidget.html#showEvent)（ ）[QWidget.hideEvent](qwidget.html#hideEvent)（）和[ItemVisibleChange](qgraphicsitem.html#GraphicsItemChange-enum)。

```
QGraphicsWidget.hoverLeaveEvent (self, QGraphicsSceneHoverEvent event)
```

从重新实现[QGraphicsItem.hoverLeaveEvent](qgraphicsitem.html#hoverLeaveEvent)（ ） 。

```
QGraphicsWidget.hoverMoveEvent (self, QGraphicsSceneHoverEvent event)
```

从重新实现[QGraphicsItem.hoverMoveEvent](qgraphicsitem.html#hoverMoveEvent)（ ） 。

```
QGraphicsWidget.initStyleOption (self, QStyleOption option)
```

填充这个小工具基于其当前状态的样式选项对象，并存储在输出_option_。默认实现填充_option_具有以下属性。

| Style Option Property | Value |
| --- | --- |
| state & [QStyle.State_Enabled](qstyle.html#StateFlag-enum) | Corresponds to [QGraphicsItem.isEnabled](qgraphicsitem.html#isEnabled)(). |
| state & [QStyle.State_HasFocus](qstyle.html#StateFlag-enum) | Corresponds to [QGraphicsItem.hasFocus](qgraphicsitem.html#hasFocus)(). |
| state & [QStyle.State_MouseOver](qstyle.html#StateFlag-enum) | Corresponds to [QGraphicsItem.isUnderMouse](qgraphicsitem.html#isUnderMouse)(). |
| direction | Corresponds to [QGraphicsWidget.layoutDirection](qgraphicswidget.html#layoutDirection-prop)(). |
| rect | Corresponds to [QGraphicsWidget.rect](qgraphicswidget.html#rect)().toRect(). |
| palette | Corresponds to [QGraphicsWidget.palette](qgraphicswidget.html#palette-prop)(). |
| fontMetrics | Corresponds to [QFontMetrics](qfontmetrics.html)([QGraphicsWidget.font](qgraphicswidget.html#font-prop)()). |

的子类[QGraphicsWidget](qgraphicswidget.html)应该调用基实现，然后测试的类型_option_使用qstyleoption_cast \u003c\u003e（）或试验[QStyleOption.Type](qstyleoption.html#StyleOptionType-enum)之前存储部件特定的选项。

例如：

```
 void MyGroupBoxWidget.initStyleOption([QStyleOption](qstyleoption.html) *option) const
 {
     [QGraphicsWidget](qgraphicswidget.html).initStyleOption(option);
     if ([QStyleOptionGroupBox](qstyleoptiongroupbox.html) *box = qstyleoption_cast<[QStyleOptionGroupBox](qstyleoptiongroupbox.html) *>(option)) {
         // Add group box specific state.
         box->flat = isFlat();
         ...
     }
 }

```

**See also** [QStyleOption.initFrom](qstyleoption.html#initFrom)（ ） 。

```
QGraphicsWidget.insertAction (self, QAction before, QAction action)
```

插入动作_action_以行动，在行动之前，这个小工具的列表_before_。其附加的行动，如果_before_是0或_before_是不是这个小工具的有效行动。

A [QGraphicsWidget](qgraphicswidget.html)应该只有每个动作之一。

此功能被引入Qt的4.5 。

**See also** [removeAction](qgraphicswidget.html#removeAction)（ ）[addAction](qgraphicswidget.html#addAction)（ ）[QMenu](qmenu.html)，[actions](qgraphicswidget.html#actions)（）和[QWidget.insertActions](qwidget.html#insertActions)（ ） 。

```
QGraphicsWidget.insertActions (self, QAction before, list-of-QAction actions)
```

插入动作_actions_以行动，在行动之前，这个小工具的列表_before_。其附加的行动，如果_before_是0或_before_是不是这个小工具的有效行动。

A [QGraphicsWidget](qgraphicswidget.html)最多可以有各一个动作。

此功能被引入Qt的4.5 。

**See also** [removeAction](qgraphicswidget.html#removeAction)（ ）[QMenu](qmenu.html)，[insertAction](qgraphicswidget.html#insertAction)（）和[QWidget.insertActions](qwidget.html#insertActions)（ ） 。

```
bool QGraphicsWidget.isActiveWindow (self)
```

返回True如果这个窗口部件的窗口是活动窗口，或者如果控件没有窗口，但在活跃现场（即，一个场景，当前具有焦点） 。

活动窗口是不是包含当前具有输入焦点的子控件的窗口，或者说本身有输入焦点。

**See also** [QGraphicsScene.activeWindow](qgraphicsscene.html#activeWindow)（ ）[QGraphicsScene.setActiveWindow](qgraphicsscene.html#setActiveWindow)（）和[isActive](qgraphicsitem.html#isActive)（ ） 。

```
QVariant QGraphicsWidget.itemChange (self, QGraphicsItem.GraphicsItemChange change, QVariant value)
```

从重新实现[QGraphicsItem.itemChange](qgraphicsitem.html#itemChange)（ ） 。

[QGraphicsWidget](qgraphicswidget.html)使用此函数的基实现追赶，并提供相关的项状态变化的事件。因为这一点，这是很重要的，子类调用基实现。

_change_指定变化的类型，并_value_为新的值。

例如，[QGraphicsWidget](qgraphicswidget.html) uses [ItemVisibleChange](qgraphicsitem.html#GraphicsItemChange-enum)交付[Show](qevent.html#Type-enum)和[Hide](qevent.html#Type-enum)事件，[ItemPositionHasChanged](qgraphicsitem.html#GraphicsItemChange-enum)交付[Move](qevent.html#Type-enum)事件，以及[ItemParentChange](qgraphicsitem.html#GraphicsItemChange-enum)既提供[ParentChange](qevent.html#Type-enum)事件，以及用于管理的重点链。

[QGraphicsWidget](qgraphicswidget.html)使[ItemSendsGeometryChanges](qgraphicsitem.html#GraphicsItemFlag-enum)标志在默认情况下，以追踪位置的变化。

**See also** [QGraphicsItem.itemChange](qgraphicsitem.html#itemChange)（ ） 。

```
QGraphicsLayout QGraphicsWidget.layout (self)
```

[](qgraphicslayout.html)

```
Qt.LayoutDirection QGraphicsWidget.layoutDirection (self)
```

[

```
QGraphicsWidget.moveEvent (self, QGraphicsSceneMoveEvent event)
```

](qt.html#LayoutDirection-enum)

[此事件处理程序，对于](qt.html#LayoutDirection-enum)[GraphicsSceneMove](qevent.html#Type-enum)事件，交付后的小部件移动时（例如，它的局部位置发生了变化） 。

当项目在本地移动此事件只交付。调用[setTransform](qgraphicsitem.html#setTransform)（）或移动的任何项的祖先不影响产品的本地位置。

您可以重新实现此事件处理程序来检测你的部件已经移动了。调用[QEvent.accept](qevent.html#accept)（）或[QEvent.ignore](qevent.html#ignore)（ ）上_event_没有任何影响。

**See also** [ItemPositionChange](qgraphicsitem.html#GraphicsItemChange-enum)和[ItemPositionHasChanged](qgraphicsitem.html#GraphicsItemChange-enum)。

```
QGraphicsWidget.paint (self, QPainter painter, QStyleOptionGraphicsItem option, QWidget widget = None)
```

从重新实现[QGraphicsItem.paint](qgraphicsitem.html#paint)（ ） 。

```
QGraphicsWidget.paintWindowFrame (self, QPainter painter, QStyleOptionGraphicsItem option, QWidget widget = None)
```

这个虚函数被调用[QGraphicsScene](qgraphicsscene.html)绘制使用Windows的窗口框架_painter_，_option_和_widget_在局部坐标。该基地实现使用目前的风格来渲染框架和标题栏。

您可以在子类中重新实现这个功能[QGraphicsWidget](qgraphicswidget.html)提供widget的窗口框架的自定义呈现。

**See also** [QGraphicsItem.paint](qgraphicsitem.html#paint)（ ） 。

```
QPalette QGraphicsWidget.palette (self)
```

[

```
QGraphicsWidget.polishEvent (self)
```

该事件是在它已经被构造之后某一时刻传送到产品的场景，但它示出或以其它方式通过现场访问之前。您可以使用此事件处理程序做需要被完全建成的项目widget的最后一分钟的初始化。

基实现不执行任何操作。

](qpalette.html)

```
QRectF QGraphicsWidget.rect (self)
```

[](qrectf.html)

[返回该项目的本地矩形作为](qrectf.html)[QRectF](qrectf.html)。此功能相当于[QRectF](qrectf.html)（ QPointF （ ） ，[size](qgraphicswidget.html#size-prop)（））。

**See also** [setGeometry](qgraphicswidget.html#geometry-prop)（）和[resize](qgraphicswidget.html#size-prop)（ ） 。

```
QGraphicsWidget.releaseShortcut (self, int id)
```

删除快捷方式与给定_id_从Qt的快捷键系统。该部件将不再接收[QEvent.Shortcut](qevent.html#Type-enum)事件的快捷方式的按键顺序（除非它使用相同的密钥序列的其他快捷方式） 。

**Warning:**你不应该通常需要使用此功能，因为Qt的快捷键系统自动删除快捷方式时，他们的父窗口部件被销毁。最好是使用[QAction](qaction.html) or [QShortcut](qshortcut.html)处理快捷方式，因为它们更容易比这低级别的功能来使用。还请注意，这是一个昂贵的操作。

此功能被引入Qt的4.5 。

**See also** [grabShortcut](qgraphicswidget.html#grabShortcut)（ ）[setShortcutEnabled](qgraphicswidget.html#setShortcutEnabled)（）和[QWidget.releaseShortcut](qwidget.html#releaseShortcut)（ ） 。

```
QGraphicsWidget.removeAction (self, QAction action)
```

删除动作_action_从操作这个小工具的列表。

此功能被引入Qt的4.5 。

**See also** [insertAction](qgraphicswidget.html#insertAction)（ ）[actions](qgraphicswidget.html#actions)（ ）[insertAction](qgraphicswidget.html#insertAction)（）和[QWidget.removeAction](qwidget.html#removeAction)（ ） 。

```
QGraphicsWidget.resize (self, QSizeF size)
```

```
QGraphicsWidget.resize (self, float w, float h)
```

```
QGraphicsWidget.resizeEvent (self, QGraphicsSceneResizeEvent event)
```

此事件处理程序，对于[GraphicsSceneResize](qevent.html#Type-enum)事件，交付后的小部件已调整大小（即其本地大小已更改） 。_event_包含旧的和新的大小。

当小部件局部调整此事件只交付;调用[setTransform](qgraphicsitem.html#setTransform)（ ）上的小工具或任何其祖先或视图，不影响部件的局部尺寸。

您可以重新实现此事件处理程序来检测你的widget已经被调整。调用[QEvent.accept](qevent.html#accept)（）或[QEvent.ignore](qevent.html#ignore)（ ）上_event_没有任何影响。

**See also** [geometry](qgraphicslayoutitem.html#geometry)（）和[setGeometry](qgraphicswidget.html#geometry-prop)（ ） 。

```
bool QGraphicsWidget.sceneEvent (self, QEvent event)
```

从重新实现[QGraphicsItem.sceneEvent](qgraphicsitem.html#sceneEvent)（ ） 。

[QGraphicsWidget](qgraphicswidget.html)的实施sceneEvent的（ ）只是简单地传递_event_至[QGraphicsWidget.event](qgraphicswidget.html#event)（ ） 。你可以处理你的widget中的所有事件[event](qgraphicswidget.html#event)（ ），或在任何方便的功能，你不应该重写本函数中的一个子类[QGraphicsWidget](qgraphicswidget.html)。

**See also** [QGraphicsItem.sceneEvent](qgraphicsitem.html#sceneEvent)（ ） 。

```
QGraphicsWidget.setAttribute (self, Qt.WidgetAttribute attribute, bool on = True)
```

If _on_诚然，这个功能可以让_attribute_否则_attribute_被禁用。

请参阅类文档[QGraphicsWidget](qgraphicswidget.html)对于其中的完整列表属性的支持，他们是干什么用的。

**See also** [testAttribute](qgraphicswidget.html#testAttribute)（）和[QWidget.setAttribute](qwidget.html#setAttribute)（ ） 。

```
QGraphicsWidget.setAutoFillBackground (self, bool enabled)
```

```
QGraphicsWidget.setContentsMargins (self, float left, float top, float right, float bottom)
```

设置widget的内容边距_left_，_top_，_right_和_bottom_。

内容页边距所使用的分配布局定义放置subwidgets和布局。利润是制约subwidgets自身的几何形状只有部分小部件特别有用。例如，一个布局的一组框将放置subwidgets其框架内的，但下面的标题。

变更小工具的内容利润率将始终触发[update](qgraphicsitem.html#update)（ ） ，以及任何指定的布局将被自动激活。那么该部件将收到[ContentsRectChange](qevent.html#Type-enum)事件。

**See also** [getContentsMargins](qgraphicswidget.html#getContentsMargins)（）和[setGeometry](qgraphicswidget.html#geometry-prop)（ ） 。

```
QGraphicsWidget.setFocusPolicy (self, Qt.FocusPolicy policy)
```

```
QGraphicsWidget.setFont (self, QFont font)
```

```
QGraphicsWidget.setGeometry (self, QRectF rect)
```

```
QGraphicsWidget.setGeometry (self, float ax, float ay, float aw, float ah)
```

```
QGraphicsWidget.setLayout (self, QGraphicsLayout layout)
```

该_layout_说法有它的所有权转移给Qt的。

```
QGraphicsWidget.setLayoutDirection (self, Qt.LayoutDirection direction)
```

```
QGraphicsWidget.setPalette (self, QPalette palette)
```

```
QGraphicsWidget.setShortcutAutoRepeat (self, int id, bool enabled = True)
```

If _enabled_诚然，汽车与给定的快捷方式重复_id_被启用，否则它被禁用。

此功能被引入Qt的4.5 。

**See also** [grabShortcut](qgraphicswidget.html#grabShortcut)（ ）[releaseShortcut](qgraphicswidget.html#releaseShortcut)（）和[QWidget.setShortcutAutoRepeat](qwidget.html#setShortcutAutoRepeat)（ ） 。

```
QGraphicsWidget.setShortcutEnabled (self, int id, bool enabled = True)
```

If _enabled_诚然，使用快捷给定的_id_被启用，否则快捷方式被禁用。

**Warning:**你不应该通常需要使用此功能，因为Qt的快捷键系统启用/禁用自动快捷方式小部件变为隐藏/可见和获得或失去焦点。最好是使用[QAction](qaction.html) or [QShortcut](qshortcut.html)处理快捷方式，因为它们更容易比这低级别的功能来使用。

此功能被引入Qt的4.5 。

**See also** [grabShortcut](qgraphicswidget.html#grabShortcut)（ ）[releaseShortcut](qgraphicswidget.html#releaseShortcut)（）和[QWidget.setShortcutEnabled](qwidget.html#setShortcutEnabled)（ ） 。

```
QGraphicsWidget.setStyle (self, QStyle style)
```

设置widget的风格_style_。[QGraphicsWidget](qgraphicswidget.html)不_not_取得其所有权_style_。

如果没有指定样式分配，或_style_为0时，窗口小部件将使用[QGraphicsScene.style](qgraphicsscene.html#style)（） （如果这已被设置） 。否则，部件将使用[QApplication.style](qapplication.html#style)（ ） 。

该函数设置[Qt.WA_SetStyle](qt.html#WidgetAttribute-enum)如果属性_style_不为0 ，否则它清除该属性。

**See also** [style](qgraphicswidget.html#style)（ ） 。

```
QGraphicsWidget.setTabOrder (QGraphicsWidget first, QGraphicsWidget second)
```

移动_second_围绕焦点窗口小部件的环部件，以便从键盘焦点移动_first_窗口小部件的_second_当按下Tab键时控件。

需要注意的是，因为的Tab键顺序_second_窗口小部件被改变，你应该订购链是这样的：

```
 setTabOrder(a, b); // a to b
 setTabOrder(b, c); // a to b to c
 setTabOrder(c, d); // a to b to c to d

```

_not_像这样：

```
 // WRONG
 setTabOrder(c, d); // c to d
 setTabOrder(a, b); // a to b AND c to d
 setTabOrder(b, c); // a to b to c, but not c to d

```

If _first_是0 ，这表明_second_应该是要现场增益选项卡焦点（即用户点击标籤，让焦点传递到场景）来接收输入焦点的第一个部件。如果_second_是0 ，这表明_first_应该是第一个部件获得焦点，如果在现场获得了BACKTAB焦点。

默认情况下， Tab键顺序的定义是隐式使用窗口小部件创建的顺序。

**See also** [focusPolicy](qgraphicswidget.html#focusPolicy-prop)和[Keyboard Focus](index.htm)。

```
QGraphicsWidget.setWindowFlags (self, Qt.WindowFlags wFlags)
```

```
QGraphicsWidget.setWindowFrameMargins (self, float left, float top, float right, float bottom)
```

设置控件的窗口框架边距_left_，_top_，_right_和_bottom_。默认帧的利润是由风格提供，它们依赖于当前窗口的标志。

如果您想自己绘制窗口装饰，你可以设置你自己的帧的利润来复盖默认的页边距。

**See also** [unsetWindowFrameMargins](qgraphicswidget.html#unsetWindowFrameMargins)（ ）[getWindowFrameMargins](qgraphicswidget.html#getWindowFrameMargins)（）和[windowFrameRect](qgraphicswidget.html#windowFrameRect)（ ） 。

```
QGraphicsWidget.setWindowTitle (self, QString title)
```

```
QPainterPath QGraphicsWidget.shape (self)
```

[](qpainterpath.html)

[从重新实现](qpainterpath.html)[QGraphicsItem.shape](qgraphicsitem.html#shape)（ ） 。

```
QGraphicsWidget.showEvent (self, QShowEvent event)
```

此事件处理程序，对于[Show](qevent.html#Type-enum)事件，被输送的部件已被证明之前，例如，其setVisible （真）被称为用于其祖先当插件先前被隐藏的窗口小部件或1 。

您可以重新实现此事件处理程序来检测你的widget显示时。调用[QEvent.accept](qevent.html#accept)（）或[QEvent.ignore](qevent.html#ignore)（ ）上_event_没有任何影响。

**See also** [hideEvent](qgraphicswidget.html#hideEvent)（ ）[QWidget.showEvent](qwidget.html#showEvent)（）和[ItemVisibleChange](qgraphicsitem.html#GraphicsItemChange-enum)。

```
QSizeF QGraphicsWidget.size (self)
```

[](qsizef.html)

```
QSizeF QGraphicsWidget.sizeHint (self, Qt.SizeHint which, QSizeF constraint = QSizeF())
```

[](qsizef.html)

[从重新实现](qsizef.html)[QGraphicsLayoutItem.sizeHint](qgraphicslayoutitem.html#sizeHint)（ ） 。

```
QStyle QGraphicsWidget.style (self)
```

[](qstyle.html)

[返回一个指向widget的风格。如果这个窗口部件没有任何明确指定的样式，返回场景的风格来代替。反过来，如果现场没有任何指定的样式，该函数返回](qstyle.html)[QApplication.style](qapplication.html#style)（ ） 。

**See also** [setStyle](qgraphicswidget.html#setStyle)（ ） 。

```
bool QGraphicsWidget.testAttribute (self, Qt.WidgetAttribute attribute)
```

返回True如果_attribute_是启用了这个小工具，否则返回False 。

**See also** [setAttribute](qgraphicswidget.html#setAttribute)（ ） 。

```
int QGraphicsWidget.type (self)
```

从重新实现[QGraphicsItem.type](qgraphicsitem.html#type)（ ） 。

```
QGraphicsWidget.ungrabKeyboardEvent (self, QEvent event)
```

此事件处理程序，对于_event_，可以在子类来接收通知被重新实现[QEvent.UngrabKeyboard](qevent.html#Type-enum)事件。

**See also** [ungrabKeyboard](qgraphicsitem.html#ungrabKeyboard)（）和[ungrabMouse](qgraphicsitem.html#ungrabMouse)（ ） 。

```
QGraphicsWidget.ungrabMouseEvent (self, QEvent event)
```

此事件处理程序，对于_event_，可以在子类来接收通知被重新实现[QEvent.UngrabMouse](qevent.html#Type-enum)事件。

**See also** [ungrabMouse](qgraphicsitem.html#ungrabMouse)（）和[ungrabKeyboard](qgraphicsitem.html#ungrabKeyboard)（ ） 。

```
QGraphicsWidget.unsetLayoutDirection (self)
```

```
QGraphicsWidget.unsetWindowFrameMargins (self)
```

重置窗框利润率为默认值，由式提供。

**See also** [setWindowFrameMargins](qgraphicswidget.html#setWindowFrameMargins)（ ）[getWindowFrameMargins](qgraphicswidget.html#getWindowFrameMargins)（）和[windowFrameRect](qgraphicswidget.html#windowFrameRect)（ ） 。

```
QGraphicsWidget.updateGeometry (self)
```

从重新实现[QGraphicsLayoutItem.updateGeometry](qgraphicslayoutitem.html#updateGeometry)（ ） 。

如果这个小工具是由目前的布局管理，该功能会通知该物件的尺寸暗示已经有所转变，布局可能需要相应地调整和重新定位插件的布局。

调用此函数，如果widget的[sizeHint](qgraphicswidget.html#sizeHint)（ ）发生了变化。

**See also** [QGraphicsLayout.invalidate](qgraphicslayout.html#invalidate)（ ） 。

```
Qt.WindowFlags QGraphicsWidget.windowFlags (self)
```

[

```
bool QGraphicsWidget.windowFrameEvent (self, QEvent e)
```

此事件处理程序，对于_event_，用于接收窗框事件，如果这个小工具是一个窗口。其基本实现提供默认的窗口框架的互动，如移动，调整大小等支持

](index.htm)

[您可以在子类中重新实现这个处理器](index.htm)[QGraphicsWidget](qgraphicswidget.html)提供您自己的自定义窗框交互的支持。

返回True如果_event_已被确认和处理，否则返回False 。

**See also** [event](qgraphicswidget.html#event)（ ） 。

```
QRectF QGraphicsWidget.windowFrameGeometry (self)
```

[

返回父坐标包括任何窗口框架的窗口部件的几何形状。

](qrectf.html)

[**See also**](qrectf.html) [windowFrameRect](qgraphicswidget.html#windowFrameRect)（ ）[getWindowFrameMargins](qgraphicswidget.html#getWindowFrameMargins)（）和[setWindowFrameMargins](qgraphicswidget.html#setWindowFrameMargins)（ ） 。

```
QRectF QGraphicsWidget.windowFrameRect (self)
```

[

返回小部件的地方矩形包括任何窗口框架。

](qrectf.html)

[**See also**](qrectf.html) [windowFrameGeometry](qgraphicswidget.html#windowFrameGeometry)（ ）[getWindowFrameMargins](qgraphicswidget.html#getWindowFrameMargins)（）和[setWindowFrameMargins](qgraphicswidget.html#setWindowFrameMargins)（ ） 。

```
Qt.WindowFrameSection QGraphicsWidget.windowFrameSectionAt (self, QPointF pos)
```

[](qt.html#WindowFrameSection-enum)

[返回在位置窗框部分_pos_或](qt.html#WindowFrameSection-enum)[Qt.NoSection](qt.html#WindowFrameSection-enum)如果有在这个位置上没有窗框部分。

此功能用于在[QGraphicsWidget](qgraphicswidget.html)的基实现窗框互动。

如果你想自定义窗口如何可以交互移动或调整大小您可以重新实现此功能。例如，如果您只想让窗口的右下角来调整大小，您可以重新实现这个函数返回[Qt.NoSection](qt.html#WindowFrameSection-enum)对于除部分[Qt.BottomRightSection](qt.html#WindowFrameSection-enum)。

此功能被引入Qt的4.4 。

**See also** [windowFrameEvent](qgraphicswidget.html#windowFrameEvent)（ ）[paintWindowFrame](qgraphicswidget.html#paintWindowFrame)（）和[windowFrameGeometry](qgraphicswidget.html#windowFrameGeometry)（ ） 。

```
QString QGraphicsWidget.windowTitle (self)
```

```
Qt.WindowType QGraphicsWidget.windowType (self)
```

[

返回小部件窗口类型。

](qt.html#WindowType-enum)

[**See also**](qt.html#WindowType-enum) [windowFlags](qgraphicswidget.html#windowFlags-prop)（ ）[isWindow](qgraphicsitem.html#isWindow)（）和[isPanel](qgraphicsitem.html#isPanel)（ ） 。

* * *

## Qt Signal Documentation

```
void geometryChanged ()
```

这是该信号的默认超载。

这个信号被发射时的几何形状的改变[setGeometry](qgraphicswidget.html#geometry-prop)（ ） 。