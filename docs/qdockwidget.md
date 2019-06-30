# QDockWidget Class Reference

## [[QtGui](index.htm) module]

该QDockWidget类提供了可以在里面一个停靠窗口小部件[QMainWindow](qmainwindow.html)或浮在桌面上的顶层窗口。[More...](#details)

继承[QWidget](qwidget.html)。

### Types

*   `enum DockWidgetFeature { DockWidgetClosable, DockWidgetMovable, DockWidgetFloatable, DockWidgetVerticalTitleBar, AllDockWidgetFeatures, NoDockWidgetFeatures }`
*   `class **[DockWidgetFeatures](index.htm)**`

### Methods

*   `__init__ (self, QString title, QWidget parent = None, Qt.WindowFlags flags = 0)`
*   `__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)`
*   `Qt.DockWidgetAreas allowedAreas (self)`
*   `changeEvent (self, QEvent event)`
*   `closeEvent (self, QCloseEvent event)`
*   `bool event (self, QEvent event)`
*   `DockWidgetFeatures features (self)`
*   `initStyleOption (self, QStyleOptionDockWidget option)`
*   `bool isAreaAllowed (self, Qt.DockWidgetArea area)`
*   `bool isFloating (self)`
*   `paintEvent (self, QPaintEvent event)`
*   `setAllowedAreas (self, Qt.DockWidgetAreas areas)`
*   `setFeatures (self, DockWidgetFeatures features)`
*   `setFloating (self, bool floating)`
*   `setTitleBarWidget (self, QWidget widget)`
*   `setWidget (self, QWidget widget)`
*   `QWidget titleBarWidget (self)`
*   `QAction toggleViewAction (self)`
*   `QWidget widget (self)`

### Qt Signals

*   `void allowedAreasChanged (Qt::DockWidgetAreas)`
*   `void dockLocationChanged (Qt::DockWidgetArea)`
*   `void featuresChanged (QDockWidget::DockWidgetFeatures)`
*   `void topLevelChanged (bool)`
*   `void visibilityChanged (bool)`

* * *

## Detailed Description

该QDockWidget类提供了可以在里面一个停靠窗口小部件[QMainWindow](qmainwindow.html)或浮在桌面上的顶层窗口。

QDockWidget提供码头部件的概念，也知道作为工具选项板或实用程序窗口。坞窗是放置在辅助窗口_dock widget area_周围的[central widget](qmainwindow.html#centralWidget)在[QMainWindow](qmainwindow.html)。

![](../img/mainwindow-docks.png)

停靠窗口可他们目前的区域内移动，移动到新的领域和浮动（例如，取消停靠）由最终用户。该QDockWidget API允许程序员来限制移动的船坞部件的能力， float和关闭，以及在它们可以被放置区域。

### Appearance

一个QDockWidget包括标题栏和内容区域。标题栏显示的停靠小部件[window title](qwidget.html#windowTitle-prop)，一_float_按钮和_close_按钮。取决于QDockWidget ，状态的_float_和_close_按钮可能会被禁用或根本不显示。

标题栏和按钮的外观取决于[style](qstyle.html)在使用中。

一个QDockWidget作为一个包装它的子控件，设置[setWidget](qdockwidget.html#setWidget)（ ） 。自定义大小的提示，最小和最大大小和尺寸的政策应该在孩子小部件来实现。 QDockWidget会尊重他们，调整自己的约束，包括框架和标题。尺寸的限制，不应在QDockWidget本身进行设置，因为它们取决于它是否停靠改变;停靠QDockWidget没有帧和一个较小的标题栏。

* * *

## Type Documentation

```
QDockWidget.DockWidgetFeature
```

| Constant | Value | Description |
| --- | --- | --- |
| `QDockWidget.DockWidgetClosable` | `0x01` | 码头widget可以被关闭。在某些系统上被告席小部件都会有一个关闭按钮时，它的（在MacOS 10.5为例）浮动。 |
| `QDockWidget.DockWidgetMovable` | `0x02` | 码头widget可以码头之间由用户移动。 |
| `QDockWidget.DockWidgetFloatable` | `0x04` | 码头小部件可以从主窗口分离，飘然作为一个独立的窗口。 |
| `QDockWidget.DockWidgetVerticalTitleBar` | `0x08` | 码头插件播放在其左侧垂直标题栏。这可以用来增加的垂直空间的量[QMainWindow](qmainwindow.html)。 |
| `QDockWidget.AllDockWidgetFeatures` | `DockWidgetClosable &#124; DockWidgetMovable &#124; DockWidgetFloatable` | （已取消）的码头小部件可以被关闭，移动和漂浮。由于新的功能可能会在以后的版本中添加，码头小部件的外观和行为，如果你使用这个标志可能会改变。请注明个人标志代替。 |
| `QDockWidget.NoDockWidgetFeatures` | `0x00` | 被告席部件不能关闭，移动或浮动。 |

该DockWidgetFeatures类型是一个typedef为[QFlags](index.htm)\u003cDockWidgetFeature\u003e 。它存储DockWidgetFeature值的或组合。

* * *

## Method Documentation

```
QDockWidget.__init__ (self, QString title, QWidget parent = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QDockWidget](qdockwidget.html)与父_parent_和窗口标志_flags_。被告席上的部件将被放置在左侧码头小工具区域。

窗口标题设置为_title_。这个标题时使用[QDockWidget](qdockwidget.html)停靠和取消停靠。它也可用于在所提供的上下文菜单[QMainWindow](qmainwindow.html)。

**See also** [setWindowTitle](qwidget.html#windowTitle-prop)（ ） 。

```
QDockWidget.__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QDockWidget](qdockwidget.html)与父_parent_和窗口标志_flags_。被告席上的部件将被放置在左侧码头小工具区域。

```
Qt.DockWidgetAreas QDockWidget.allowedAreas (self)
```

[

```
QDockWidget.changeEvent (self, QEvent event)
```

](index.htm)

[从重新实现](index.htm)[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
QDockWidget.closeEvent (self, QCloseEvent event)
```

从重新实现[QWidget.closeEvent](qwidget.html#closeEvent)（ ） 。

```
bool QDockWidget.event (self, QEvent event)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
DockWidgetFeatures QDockWidget.features (self)
```

[

```
QDockWidget.initStyleOption (self, QStyleOptionDockWidget option)
```

](index.htm)

[初始化_option_与其它的值](index.htm)[QDockWidget](qdockwidget.html)。当他们需要一个这种方法是有用的子类[QStyleOptionDockWidget](qstyleoptiondockwidget.html)，但不希望在所有的信息填写自己。

**See also** [QStyleOption.initFrom](qstyleoption.html#initFrom)（ ） 。

```
bool QDockWidget.isAreaAllowed (self, Qt.DockWidgetArea area)
```

返回True如果此停靠小部件可以放置在给定的_area_否则返回False 。

```
bool QDockWidget.isFloating (self)
```

```
QDockWidget.paintEvent (self, QPaintEvent event)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QDockWidget.setAllowedAreas (self, Qt.DockWidgetAreas areas)
```

```
QDockWidget.setFeatures (self, DockWidgetFeatures features)
```

```
QDockWidget.setFloating (self, bool floating)
```

```
QDockWidget.setTitleBarWidget (self, QWidget widget)
```

该_widget_说法有它的所有权转移给Qt的。

设置一个任意_widget_作为基座部件的标题栏。如果_widget_为0 ，任何自定义标题栏小工具以前在码头上小部件设置被删除，但不能删除，默认的标题栏将被使用。

如果标题栏小工具设置，[QDockWidget](qdockwidget.html)将不使用本机窗口装饰时，它是浮动的。

下面是实现自定义标题栏的一些提示：

*   Mouse events that are not explicitly handled by the title bar widget must be ignored by calling [QMouseEvent.ignore](qevent.html#ignore)(). These events then propagate to the [QDockWidget](qdockwidget.html) parent, which handles them in the usual manner, moving when the title bar is dragged, docking and undocking when it is double-clicked, etc.
*   When [DockWidgetVerticalTitleBar](qdockwidget.html#DockWidgetFeature-enum) is set on [QDockWidget](qdockwidget.html), the title bar widget is repositioned accordingly. In [resizeEvent](qwidget.html#resizeEvent)(), the title bar should check what orientation it should assume:

    ```
     [QDockWidget](qdockwidget.html) *dockWidget = qobject_cast&lt;[QDockWidget](qdockwidget.html)*&gt;(parentWidget());
     if (dockWidget-&gt;features() & [QDockWidget](qdockwidget.html).DockWidgetVerticalTitleBar) {
         // I need to be vertical
     } else {
         // I need to be horizontal
     }

    ```

*   The title bar widget must have a valid [QWidget.sizeHint](qwidget.html#sizeHint-prop)() and [QWidget.minimumSizeHint](qwidget.html#minimumSizeHint-prop)(). These functions should take into account the current orientation of the title bar.
*   It is not possible to remove a title bar from a dock widget. However, a similar effect can be achieved by setting a default constructed [QWidget](qwidget.html) as the title bar widget.

Using [qobject_cast](qobject.html#qobject_cast)（ ）如上图所示，在标题栏小工具可以完全访问它的父[QDockWidget](qdockwidget.html)。因此，它可以响应于用户的操作作为对接和遮盖力执行这样的操作。

此功能被引入Qt的4.3 。

**See also** [titleBarWidget](qdockwidget.html#titleBarWidget)（）和[DockWidgetVerticalTitleBar](qdockwidget.html#DockWidgetFeature-enum)。

```
QDockWidget.setWidget (self, QWidget widget)
```

该_widget_说法有它的所有权转移给Qt的。

设置部件码头小部件_widget_。

如果船坞部件是可见的，当_widget_是说，你必须[show()](qwidget.html#show)它明确。

请注意，您必须添加的布局_widget_你调用这个函数之前，如果没有，_widget_将不可见。

**See also** [widget](qdockwidget.html#widget)（ ） 。

```
QWidget QDockWidget.titleBarWidget (self)
```

[](qwidget.html)

[返回的自定义标题栏widget集](qwidget.html)[QDockWidget](qdockwidget.html)，或者0，如果没有自定义标题栏已定。

此功能被引入Qt的4.3 。

**See also** [setTitleBarWidget](qdockwidget.html#setTitleBarWidget)（ ） 。

```
QAction QDockWidget.toggleViewAction (self)
```

[

返回一个可用于显示或关闭此停靠小部件可检查的动作。

该操作的文本设置为停靠窗口小部件的窗口标题。

](qaction.html)

[**See also**](qaction.html) [QAction.text](qaction.html#text-prop)和[QWidget.windowTitle](qwidget.html#windowTitle-prop)。

```
QWidget QDockWidget.widget (self)
```

[

返回部件码头部件。该函数返回零，如果插件并未设置。

](qwidget.html)

[**See also**](qwidget.html) [setWidget](qdockwidget.html#setWidget)（ ） 。

* * *

## Qt Signal Documentation

```
void allowedAreasChanged (Qt::DockWidgetAreas)
```

这是该信号的默认超载。

这个信号被发射时的[allowedAreas](qdockwidget.html#allowedAreas-prop)属性更改。该_allowedAreas_参数给出该属性的新值。

```
void dockLocationChanged (Qt::DockWidgetArea)
```

这是该信号的默认超载。

当基座部件被移动到另一个码头这个信号被发射_area_，或移动到其当前船坞区的不同位置。发生这种情况时，基座部件被编程方式移动或由用户拖动到一个新位置。

此功能被引入Qt的4.3 。

```
void featuresChanged (QDockWidget::DockWidgetFeatures)
```

这是该信号的默认超载。

这个信号被发射时的[features](qdockwidget.html#features-prop)属性更改。该_features_参数给出该属性的新值。

```
void topLevelChanged (bool)
```

这是该信号的默认超载。

这个信号被发射时的[floating](qdockwidget.html#floating-prop)属性更改。该_topLevel_参数为True ，如果停靠小部件，现在浮动，否则为假。

**See also** [isWindow](qwidget.html#isWindow)（ ） 。

```
void visibilityChanged (bool)
```

这是该信号的默认超载。

当基座部件成为这个信号被发射_visible_（或不可见） 。这种情况发生在小部件是隐藏或显示，以及当它停靠在一个标籤式码头区，其标籤变成选择或取消选择。

此功能被引入Qt的4.3 。