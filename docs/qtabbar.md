# QTabBar Class Reference

## [[QtGui](index.htm) module]

该QTabBar类提供了一个标籤栏，例如在标籤对话框中使用。[More...](#details)

继承[QWidget](qwidget.html)。

### Types

*   `enum ButtonPosition { LeftSide, RightSide }`
*   `enum SelectionBehavior { SelectLeftTab, SelectRightTab, SelectPreviousTab }`
*   `enum Shape { RoundedNorth, RoundedSouth, RoundedWest, RoundedEast, ..., TriangularEast }`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `int addTab (self, QString text)`
*   `int addTab (self, QIcon icon, QString text)`
*   `changeEvent (self, QEvent)`
*   `int count (self)`
*   `int currentIndex (self)`
*   `bool documentMode (self)`
*   `bool drawBase (self)`
*   `Qt.TextElideMode elideMode (self)`
*   `bool event (self, QEvent)`
*   `bool expanding (self)`
*   `hideEvent (self, QHideEvent)`
*   `QSize iconSize (self)`
*   `initStyleOption (self, QStyleOptionTab option, int tabIndex)`
*   `int insertTab (self, int index, QString text)`
*   `int insertTab (self, int index, QIcon icon, QString text)`
*   `bool isMovable (self)`
*   `bool isTabEnabled (self, int index)`
*   `keyPressEvent (self, QKeyEvent)`
*   `QSize minimumSizeHint (self)`
*   `mouseMoveEvent (self, QMouseEvent)`
*   `mousePressEvent (self, QMouseEvent)`
*   `mouseReleaseEvent (self, QMouseEvent)`
*   `moveTab (self, int from, int to)`
*   `paintEvent (self, QPaintEvent)`
*   `removeTab (self, int index)`
*   `resizeEvent (self, QResizeEvent)`
*   `SelectionBehavior selectionBehaviorOnRemove (self)`
*   `setCurrentIndex (self, int index)`
*   `setDocumentMode (self, bool set)`
*   `setDrawBase (self, bool drawTheBase)`
*   `setElideMode (self, Qt.TextElideMode)`
*   `setExpanding (self, bool enabled)`
*   `setIconSize (self, QSize size)`
*   `setMovable (self, bool movable)`
*   `setSelectionBehaviorOnRemove (self, SelectionBehavior behavior)`
*   `setShape (self, Shape shape)`
*   `setTabButton (self, int index, ButtonPosition position, QWidget widget)`
*   `setTabData (self, int index, QVariant data)`
*   `setTabEnabled (self, int index, bool)`
*   `setTabIcon (self, int index, QIcon icon)`
*   `setTabsClosable (self, bool closable)`
*   `setTabText (self, int index, QString text)`
*   `setTabTextColor (self, int index, QColor color)`
*   `setTabToolTip (self, int index, QString tip)`
*   `setTabWhatsThis (self, int index, QString text)`
*   `setUsesScrollButtons (self, bool useButtons)`
*   `Shape shape (self)`
*   `showEvent (self, QShowEvent)`
*   `QSize sizeHint (self)`
*   `int tabAt (self, QPoint pos)`
*   `QWidget tabButton (self, int index, ButtonPosition position)`
*   `QVariant tabData (self, int index)`
*   `QIcon tabIcon (self, int index)`
*   `tabInserted (self, int index)`
*   `tabLayoutChange (self)`
*   `QRect tabRect (self, int index)`
*   `tabRemoved (self, int index)`
*   `bool tabsClosable (self)`
*   `QSize tabSizeHint (self, int index)`
*   `QString tabText (self, int index)`
*   `QColor tabTextColor (self, int index)`
*   `QString tabToolTip (self, int index)`
*   `QString tabWhatsThis (self, int index)`
*   `bool usesScrollButtons (self)`
*   `wheelEvent (self, QWheelEvent event)`

### Special Methods

*   `__len__ (self)`

### Qt Signals

*   `void currentChanged (int)`
*   `void tabCloseRequested (int)`
*   `void tabMoved (int,int)`

* * *

## Detailed Description

该QTabBar类提供了一个标籤栏，例如在标籤对话框中使用。

QTabBar直接就能使用，它使用预定义的一个绘制标籤[shapes](qtabbar.html#Shape-enum)，并发射时，所选择的标籤的信号。它可以被子类化定制的外观和感觉。 Qt还提供了一个现成的[QTabWidget](qtabwidget.html)。

每个标籤都有一个[tabText](qtabbar.html#tabText)（） ，可选[tabIcon](qtabbar.html#tabIcon)（） ，可选[tabToolTip](qtabbar.html#tabToolTip)（ ），可选[tabWhatsThis](qtabbar.html#tabWhatsThis)（）和可选[tabData](qtabbar.html#tabData)（ ） 。的标籤的属性可以被改变[setTabText](qtabbar.html#setTabText)（ ）[setTabIcon](qtabbar.html#setTabIcon)（ ）[setTabToolTip](qtabbar.html#setTabToolTip)（ ） ， setTabWhatsThis和[setTabData](qtabbar.html#setTabData)（ ） 。每个选项卡可以启用或禁用单独[setTabEnabled](qtabbar.html#setTabEnabled)（ ） 。

每个选项卡都可以在不同的颜色显示文本。目前的文本颜色选项卡可以与发现[tabTextColor](qtabbar.html#tabTextColor)（）函数。设置文字的颜色与特定标籤[setTabTextColor](qtabbar.html#setTabTextColor)（ ） 。

标籤使用添加[addTab](qtabbar.html#addTab)（），或者使用插入在特定位置[insertTab](qtabbar.html#insertTab)（ ） 。片的总数由下式给出[count](qtabbar.html#count-prop)（ ） 。标籤可以从与标籤栏被移除[removeTab](qtabbar.html#removeTab)（ ） 。结合[removeTab](qtabbar.html#removeTab)（）和[insertTab](qtabbar.html#insertTab)（）允许您移动标籤到不同的位置。

该[shape](qtabbar.html#shape-prop)属性定义的选项卡'的出现。形状的选择是一个品味的问题，虽然选项卡对话框（对于喜好和类似的）总是使用[RoundedNorth](qtabbar.html#Shape-enum)。在windows对话框比其他选项卡控件几乎总是使用任[RoundedSouth](qtabbar.html#Shape-enum) or [TriangularSouth](qtabbar.html#Shape-enum)。许多电子表格和其他选项卡控件中的所有页面都基本类似用途[TriangularSouth](qtabbar.html#Shape-enum)，而[RoundedSouth](qtabbar.html#Shape-enum)大多采用在页面是不同的（例如，一个多页的工具选项板） 。在QTabBar默认为[RoundedNorth](qtabbar.html#Shape-enum)。

的QTabBar的API中最重要的部分是[currentChanged](qtabbar.html#currentChanged)（）信号。这是发射时在当前选项卡的变化（即使在启动时，当在当前选项卡的“无”的变化） 。还有一个槽，[setCurrentIndex](qtabbar.html#currentIndex-prop)（ ） ，它可以用来以编程方式选择一个选项卡。该功能[currentIndex](qtabbar.html#currentIndex-prop)（ ）返回当前选项卡的索引，[count](qtabbar.html#count-prop)保持标籤的数量。

QTabBar在创建的方式自动记忆键[QAbstractButton](qabstractbutton.html);如如果一个选项卡的标籤是“与图形” ， Alt + G键变成了快捷键切换到该选项卡。

下面的虚函数可能需要以重新实现来定制外观和感觉或存储额外的数据与每个选项卡：

*   [tabSizeHint](qtabbar.html#tabSizeHint)() calcuates the size of a tab.
*   [tabInserted](qtabbar.html#tabInserted)() notifies that a new tab was added.
*   [tabRemoved](qtabbar.html#tabRemoved)() notifies that a tab was removed.
*   [tabLayoutChange](qtabbar.html#tabLayoutChange)() notifies that the tabs have been re-laid out.
*   [paintEvent](qtabbar.html#paintEvent)() paints all tabs.

对于子类，你可能还需要[tabRect](qtabbar.html#tabRect)（ ）函数返回一个标籤的视觉几何形状。

| ![Screenshot of a Plastique style tab bar](../img/plastique-tabbar.png) | A tab bar shown in the Plastique widget style. |
| ![Screenshot of a truncated Plastique tab bar](../img/plastique-tabbar-truncated.png) | A truncated tab bar shown in the Plastique widget style. |

* * *

## Type Documentation

```
QTabBar.ButtonPosition
```

该枚举类型列出一个选项卡上的窗口小部件的位置。

| Constant | Value | Description |
| --- | --- | --- |
| `QTabBar.LeftSide` | `0` | 该选项卡的左侧。 |
| `QTabBar.RightSide` | `1` | 该选项卡的右侧。 |

这个枚举被引入或修改的Qt 4.5 。

```
QTabBar.SelectionBehavior
```

该枚举类型列出的行为[QTabBar](qtabbar.html)当一个标籤被删除，被删除的标籤也是当前选项卡。

| Constant | Value | Description |
| --- | --- | --- |
| `QTabBar.SelectLeftTab` | `0` | 选择标籤，以一个被删除的左侧。 |
| `QTabBar.SelectRightTab` | `1` | 选择标籤，以一个被删除的权利。 |
| `QTabBar.SelectPreviousTab` | `2` | 选择先前选定的选项卡。 |

这个枚举被引入或修改的Qt 4.5 。

```
QTabBar.Shape
```

该枚举类型列出了所支持的内建的形状[QTabBar](qtabbar.html)。把这些作为提示一些样式可能不会呈现一些形状。然而，位置应该履行。

| Constant | Value | Description |
| --- | --- | --- |
| `QTabBar.RoundedNorth` | `0` | 正常的圆形看看上面的页面 |
| `QTabBar.RoundedSouth` | `1` | 正常圆润的外观下页 |
| `QTabBar.RoundedWest` | `2` | 正常的圆润外观上页面的左侧 |
| `QTabBar.RoundedEast` | `3` | 正常的圆形的外表上的右侧的页面 |
| `QTabBar.TriangularNorth` | `4` | 三角形标籤上方的页面。 |
| `QTabBar.TriangularSouth` | `5` | 三角形标籤类似于Excel的电子表格中使用，例如 |
| `QTabBar.TriangularWest` | `6` | 三角形标籤上的页面的左侧。 |
| `QTabBar.TriangularEast` | `7` | 三角形标籤上的页面的右侧。 |

* * *

## Method Documentation

```
QTabBar.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建具有给定一个新的标籤栏_parent_。

```
int QTabBar.addTab (self, QString text)
```

增加了文本的新选项卡_text_。返回新的选项卡的索引。

```
int QTabBar.addTab (self, QIcon icon, QString text)
```

这是一个重载函数。

添加带有图标的新选项卡_icon_和文本_text_。返回新的选项卡的索引。

```
QTabBar.changeEvent (self, QEvent)
```

从重新实现[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
int QTabBar.count (self)
```

```
int QTabBar.currentIndex (self)
```

```
bool QTabBar.documentMode (self)
```

```
bool QTabBar.drawBase (self)
```

```
Qt.TextElideMode QTabBar.elideMode (self)
```

[

```
bool QTabBar.event (self, QEvent)
```

](qt.html#TextElideMode-enum)

[从重新实现](qt.html#TextElideMode-enum)[QObject.event](qobject.html#event)（ ） 。

```
bool QTabBar.expanding (self)
```

```
QTabBar.hideEvent (self, QHideEvent)
```

从重新实现[QWidget.hideEvent](qwidget.html#hideEvent)（ ） 。

```
QSize QTabBar.iconSize (self)
```

[

```
QTabBar.initStyleOption (self, QStyleOptionTab option, int tabIndex)
```

](qsize.html)

[初始化_option_与在标籤的值_tabIndex_。当他们需要一个这种方法是有用的子类](qsize.html)[QStyleOptionTab](qstyleoptiontab.html)，[QStyleOptionTabV2](qstyleoptiontabv2.html)或[QStyleOptionTabV3](qstyleoptiontabv3.html)但不希望在所有的信息填写自己。此功能将检查的版本[QStyleOptionTab](qstyleoptiontab.html)并填写了附加价值[QStyleOptionTabV2](qstyleoptiontabv2.html)和[QStyleOptionTabV3](qstyleoptiontabv3.html)。

**See also** [QStyleOption.initFrom](qstyleoption.html#initFrom)（）和[QTabWidget.initStyleOption](qtabwidget.html#initStyleOption)（ ） 。

```
int QTabBar.insertTab (self, int index, QString text)
```

插入文本的新选项卡_text_在位置_index_。如果_index_超出范围，则新的选项卡appened 。返回新的选项卡的索引。

```
int QTabBar.insertTab (self, int index, QIcon icon, QString text)
```

这是一个重载函数。

插入带有图标的新选项卡_icon_和文本_text_在位置_index_。如果_index_超出范围，则新的标籤被追加。返回新的选项卡的索引。

如果[QTabBar](qtabbar.html)为空，此函数被调用之前，插入选项卡成为当前选项卡。

插入一个新的选项卡的索引小于或等于当前的索引处将增加目前的指数，但保留当前选项卡。

```
bool QTabBar.isMovable (self)
```

```
bool QTabBar.isTabEnabled (self, int index)
```

返回True如果在位置标籤_index_被启用，否则返回False 。

```
QTabBar.keyPressEvent (self, QKeyEvent)
```

从重新实现[QWidget.keyPressEvent](qwidget.html#keyPressEvent)（ ） 。

```
QSize QTabBar.minimumSizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.minimumSizeHint](qwidget.html#minimumSizeHint-prop)（ ） 。

```
QTabBar.mouseMoveEvent (self, QMouseEvent)
```

从重新实现[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

```
QTabBar.mousePressEvent (self, QMouseEvent)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

```
QTabBar.mouseReleaseEvent (self, QMouseEvent)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

```
QTabBar.moveTab (self, int from, int to)
```

在索引位置移动项目_from_到索引位置_to_。

此功能被引入Qt的4.5 。

**See also** [tabMoved](qtabbar.html#tabMoved)（）和[tabLayoutChange](qtabbar.html#tabLayoutChange)（ ） 。

```
QTabBar.paintEvent (self, QPaintEvent)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QTabBar.removeTab (self, int index)
```

移除选项卡的位置_index_。

**See also** [SelectionBehavior](qtabbar.html#SelectionBehavior-enum)。

```
QTabBar.resizeEvent (self, QResizeEvent)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
SelectionBehavior QTabBar.selectionBehaviorOnRemove (self)
```

[

```
QTabBar.setCurrentIndex (self, int index)
```

这种方法也是一个Qt槽与C + +的签名`void setCurrentIndex(int)`。

```
QTabBar.setDocumentMode (self, bool set)
```

```
QTabBar.setDrawBase (self, bool drawTheBase)
```

```
QTabBar.setElideMode (self, Qt.TextElideMode)
```

```
QTabBar.setExpanding (self, bool enabled)
```

```
QTabBar.setIconSize (self, QSize size)
```

```
QTabBar.setMovable (self, bool movable)
```

```
QTabBar.setSelectionBehaviorOnRemove (self, SelectionBehavior behavior)
```

```
QTabBar.setShape (self, Shape shape)
```

```
QTabBar.setTabButton (self, int index, ButtonPosition position, QWidget widget)
```

该_widget_说法有它的所有权转移给Qt的。

Sets _widget_在选项卡上_index_。该插件被放置在左侧或右侧取决于_position_。

在任何先前定义插件_position_被隐藏。

标籤栏将窗口小部件的所有权，所以这里设置的所有部件将标籤栏时，它被摧毁，除非你单独reparent小部件设置一些其他的小部件（或0 ）后删除。

此功能被引入Qt的4.5 。

](qtabbar.html#SelectionBehavior-enum)

[**See also**](qtabbar.html#SelectionBehavior-enum) [tabButton](qtabbar.html#tabButton)（）和[tabsClosable](qtabbar.html#tabsClosable-prop)（ ） 。

```
QTabBar.setTabData (self, int index, QVariant data)
```

设置选项卡中的数据的位置_index_至_data_。

**See also** [tabData](qtabbar.html#tabData)（ ） 。

```
QTabBar.setTabEnabled (self, int index, bool)
```

If _enabled_为真，则在位置的标籤_index_被启用，否则在位置的项目_index_被禁用。

**See also** [isTabEnabled](qtabbar.html#isTabEnabled)（ ） 。

```
QTabBar.setTabIcon (self, int index, QIcon icon)
```

设置选项卡的位置的图标_index_至_icon_。

**See also** [tabIcon](qtabbar.html#tabIcon)（ ） 。

```
QTabBar.setTabsClosable (self, bool closable)
```

```
QTabBar.setTabText (self, int index, QString text)
```

设置选项卡的位置的文字_index_至_text_。

**See also** [tabText](qtabbar.html#tabText)（ ） 。

```
QTabBar.setTabTextColor (self, int index, QColor color)
```

在设置选项卡中的文本的颜色与给定_index_到指定的_color_。

如果指定了无效的颜色，选项卡将使用[QTabBar](qtabbar.html)前台的角色来代替。

**See also** [tabTextColor](qtabbar.html#tabTextColor)（ ） 。

```
QTabBar.setTabToolTip (self, int index, QString tip)
```

设置选项卡的刀尖位置_index_至_tip_。

**See also** [tabToolTip](qtabbar.html#tabToolTip)（ ） 。

```
QTabBar.setTabWhatsThis (self, int index, QString text)
```

设置这是什么帮助，位置标籤的文本_index_至_text_。

这个函数是Qt 4.1中引入。

**See also** [tabWhatsThis](qtabbar.html#tabWhatsThis)（ ） 。

```
QTabBar.setUsesScrollButtons (self, bool useButtons)
```

```
Shape QTabBar.shape (self)
```

[

```
QTabBar.showEvent (self, QShowEvent)
```

](qtabbar.html#Shape-enum)

[从重新实现](qtabbar.html#Shape-enum)[QWidget.showEvent](qwidget.html#showEvent)（ ） 。

```
QSize QTabBar.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

```
int QTabBar.tabAt (self, QPoint pos)
```

返回该复盖的标籤的索引_position_或者-1，如果没有选项卡盖_position_;

此功能被引入Qt的4.3 。

```
QWidget QTabBar.tabButton (self, int index, ButtonPosition position)
```

[

返回小部件设置选项卡_index_和_position_或0如果没有设置。

](qwidget.html)

[**See also**](qwidget.html) [setTabButton](qtabbar.html#setTabButton)（ ） 。

```
QVariant QTabBar.tabData (self, int index)
```

返回标籤的数据在位置_index_如果，或者一个空的变体_index_超出范围。

**See also** [setTabData](qtabbar.html#setTabData)（ ） 。

```
QIcon QTabBar.tabIcon (self, int index)
```

[

将索引标籤的位置的图标_index_如果，或者一个空图标_index_超出范围。

](qicon.html)

[**See also**](qicon.html) [setTabIcon](qtabbar.html#setTabIcon)（ ） 。

```
QTabBar.tabInserted (self, int index)
```

后一个新的选项卡中添加或插入的位置这个虚拟处理器被调用_index_。

**See also** [tabRemoved](qtabbar.html#tabRemoved)（ ） 。

```
QTabBar.tabLayoutChange (self)
```

这种虚拟处理器被调用时该选项卡的布局变化。

**See also** [tabRect](qtabbar.html#tabRect)（ ） 。

```
QRect QTabBar.tabRect (self, int index)
```

[

将索引标籤的位置的可视矩形_index_，或者一个空矩形，如果_index_超出范围。

```
QTabBar.tabRemoved (self, int index)
```

一个选项卡是从位置移除后，此虚拟处理器被调用_index_。

](qrect.html)

[**See also**](qrect.html) [tabInserted](qtabbar.html#tabInserted)（ ） 。

```
bool QTabBar.tabsClosable (self)
```

```
QSize QTabBar.tabSizeHint (self, int index)
```

[

返回尺寸暗示的位置的选项卡_index_。

```
QString QTabBar.tabText (self, int index)
```

在位置返回标籤的文本_index_如果，或者一个空字符串_index_超出范围。

](qsize.html)

[**See also**](qsize.html) [setTabText](qtabbar.html#setTabText)（ ） 。

```
QColor QTabBar.tabTextColor (self, int index)
```

[

返回标籤的文本颜色与给定_index_或无效的颜色，如果_index_超出范围。

](qcolor.html)

[**See also**](qcolor.html) [setTabTextColor](qtabbar.html#setTabTextColor)（ ） 。

```
QString QTabBar.tabToolTip (self, int index)
```

返回选项卡的刀尖位置_index_如果，或者一个空字符串_index_超出范围。

**See also** [setTabToolTip](qtabbar.html#setTabToolTip)（ ） 。

```
QString QTabBar.tabWhatsThis (self, int index)
```

返回这是什么帮助，位置标籤的文本_index_如果，或者一个空字符串_index_超出范围。

这个函数是Qt 4.1中引入。

**See also** [setTabWhatsThis](qtabbar.html#setTabWhatsThis)（ ） 。

```
bool QTabBar.usesScrollButtons (self)
```

```
QTabBar.wheelEvent (self, QWheelEvent event)
```

从重新实现[QWidget.wheelEvent](qwidget.html#wheelEvent)（ ） 。

```
 QTabBar.__len__ (self)
```

* * *

## Qt Signal Documentation

```
void currentChanged (int)
```

这是该信号的默认超载。

当标籤栏的当前选项卡改变这个信号被发射。新的当前已给定的_index_或-1 ，如果没有一个新的（例如，如果有在没有标籤[QTabBar](qtabbar.html)）

```
void tabCloseRequested (int)
```

这是该信号的默认超载。

点击一个选项卡上的关闭按钮时，这个信号被发射。该_index_是应该被删除的索引。

此功能被引入Qt的4.5 。

**See also** [setTabsClosable](qtabbar.html#tabsClosable-prop)（ ） 。

```
void tabMoved (int,int)
```

这是该信号的默认超载。

这个信号被发射时，选项栏转移的选项卡索引位置_from_到索引位置_to_。

注意：[QTabWidget](qtabwidget.html)会自动移动页面时，这个信号是从它的标籤栏发出。

此功能被引入Qt的4.5 。

**See also** [moveTab](qtabbar.html#moveTab)（ ） 。