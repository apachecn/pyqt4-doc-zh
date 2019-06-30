# QLayout Class Reference

## [[QtGui](index.htm) module]

The QLayout class is the base class of geometry managers. [More...](#details)

Inherits [QObject](qobject.html) and [QLayoutItem](qlayoutitem.html).

Inherited by [QBoxLayout](qboxlayout.html), [QFormLayout](qformlayout.html), [QGridLayout](qgridlayout.html) and [QStackedLayout](qstackedlayout.html).

### Types

*   `enum SizeConstraint { SetDefaultConstraint, SetNoConstraint, SetMinimumSize, SetFixedSize, SetMaximumSize, SetMinAndMaxSize }`

### Methods

*   `__init__ (self, QWidget parent)`
*   `__init__ (self)`
*   `bool activate (self)`
*   `addChildLayout (self, QLayout l)`
*   `addChildWidget (self, QWidget w)`
*   `addItem (self, QLayoutItem)`
*   `addWidget (self, QWidget w)`
*   `QRect alignmentRect (self, QRect)`
*   `childEvent (self, QChildEvent e)`
*   `QMargins contentsMargins (self)`
*   `QRect contentsRect (self)`
*   `int count (self)`
*   `Qt.Orientations expandingDirections (self)`
*   `QRect geometry (self)`
*   `(int left, int top, int right, int bottom) getContentsMargins (self)`
*   `int indexOf (self, QWidget)`
*   `invalidate (self)`
*   `bool isEmpty (self)`
*   `bool isEnabled (self)`
*   `QLayoutItem itemAt (self, int index)`
*   `QLayout layout (self)`
*   `int margin (self)`
*   `QSize maximumSize (self)`
*   `QWidget menuBar (self)`
*   `QSize minimumSize (self)`
*   `QWidget parentWidget (self)`
*   `removeItem (self, QLayoutItem)`
*   `removeWidget (self, QWidget w)`
*   `bool setAlignment (self, QWidget w, Qt.Alignment alignment)`
*   `bool setAlignment (self, QLayout l, Qt.Alignment alignment)`
*   `setAlignment (self, Qt.Alignment alignment)`
*   `setContentsMargins (self, int left, int top, int right, int bottom)`
*   `setContentsMargins (self, QMargins margins)`
*   `setEnabled (self, bool)`
*   `setGeometry (self, QRect)`
*   `setMargin (self, int)`
*   `setMenuBar (self, QWidget w)`
*   `setSizeConstraint (self, SizeConstraint)`
*   `setSpacing (self, int)`
*   `SizeConstraint sizeConstraint (self)`
*   `int spacing (self)`
*   `QLayoutItem takeAt (self, int index)`
*   `int totalHeightForWidth (self, int w)`
*   `QSize totalMaximumSize (self)`
*   `QSize totalMinimumSize (self)`
*   `QSize totalSizeHint (self)`
*   `update (self)`
*   `widgetEvent (self, QEvent)`

### Static Methods

*   `QSize closestAcceptableSize (QWidget w, QSize s)`

### Special Methods

*   `__len__ (self)`

* * *

## Detailed Description

该QLayout类是几何管理者的基类。

这是继承的具体类的抽象基类[QBoxLayout](qboxlayout.html)，[QGridLayout](qgridlayout.html)，[QFormLayout](qformlayout.html)和[QStackedLayout](qstackedlayout.html)。

有关的QLayout子类或用户[QMainWindow](qmainwindow.html)里面很少有任何需要使用由QLayout提供的基本功能，如[setSizeConstraint](qlayout.html#sizeConstraint-prop)（）或[setMenuBar](qlayout.html#setMenuBar)（ ） 。看[Layout Management](index.htm)了解更多信息。

为了使自己的布局管理器，实现功能[addItem](qlayout.html#addItem)（ ）[sizeHint](qlayoutitem.html#sizeHint)（ ）[setGeometry](qlayout.html#setGeometry)（ ）[itemAt](qlayout.html#itemAt)（）和[takeAt](qlayout.html#takeAt)（ ） 。你也应该实施[minimumSize](qlayout.html#minimumSize)（ ），以确保你的布局是不是调整到零尺寸，如果有空间太少。为了支持儿童，其高度依赖于它们的宽度，实施[hasHeightForWidth](qlayoutitem.html#hasHeightForWidth)（）和[heightForWidth](qlayoutitem.html#heightForWidth)（ ） 。请参阅[Border Layout](index.htm)和[Flow Layout](index.htm)示例有关实现自定义布局管理器的更多信息。

当布局管理器被删除几何管理停止。

* * *

## Type Documentation

```
QLayout.SizeConstraint
```

可能的值有：

| Constant | Value | Description |
| --- | --- | --- |
| `QLayout.SetDefaultConstraint` | `0` | 主窗口部件的最小大小设置为[minimumSize](qlayout.html#minimumSize)（）中，除插件已经具有的最小尺寸。 |
| `QLayout.SetFixedSize` | `3` | 主窗口部件的大小设置为[sizeHint](qlayoutitem.html#sizeHint)（）;它不能在所有的调整大小。 |
| `QLayout.SetMinimumSize` | `2` | 主窗口部件的最小大小设置为[minimumSize](qlayout.html#minimumSize)（）;它不能是较小的。 |
| `QLayout.SetMaximumSize` | `4` | 主窗口部件的最大大小设置为[maximumSize](qlayout.html#maximumSize)（）;它不能大。 |
| `QLayout.SetMinAndMaxSize` | `5` | 主窗口部件的最小大小设置为[minimumSize](qlayout.html#minimumSize)（） ，其最大尺寸设定为[maximumSize](qlayout.html#maximumSize)（ ） 。 |
| `QLayout.SetNoConstraint` | `1` | 窗口小部件不受限。 |

**See also** [setSizeConstraint](qlayout.html#sizeConstraint-prop)（ ） 。

* * *

## Method Documentation

```
QLayout.__init__ (self, QWidget parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的顶级[QLayout](qlayout.html)，与父_parent_。_parent_可能不是0 。

只能有一个是一个小部件的顶层布局。它是由返回[QWidget.layout](qwidget.html#layout)（ ） 。

```
QLayout.__init__ (self)
```

构造一个新的子[QLayout](qlayout.html)。

这种布局有被插入到另一个布局之前几何管理将工作。

```
bool QLayout.activate (self)
```

重做的布局[parentWidget](qlayout.html#parentWidget)（）如果需要的话。

你通常应该不需要调用这个，因为它是自动调用在最适当的时候。如果布局被再做它返回True 。

**See also** [update](qlayout.html#update)（）和[QWidget.updateGeometry](qwidget.html#updateGeometry)（ ） 。

```
QLayout.addChildLayout (self, QLayout l)
```

该_l_说法有它的所有权转移给Qt的。

此功能是从所谓的`addLayout()` or `insertLayout()`在子类的功能来添加布局_l_作为子布局。

在其中你需要把它直接调用的唯一情况是，如果你执行一个支持嵌套的布局自定义布局。

**See also** [QBoxLayout.addLayout](qboxlayout.html#addLayout)（ ）[QBoxLayout.insertLayout](qboxlayout.html#insertLayout)（）和[QGridLayout.addLayout](qgridlayout.html#addLayout)（ ） 。

```
QLayout.addChildWidget (self, QWidget w)
```

该_w_说法有它的所有权转移给Qt的。

此功能是从所谓的`addWidget()`在子类中添加功能_w_作为布局的一个管理部件。

If _w_已通过布局管理，此功能将给予警告并删除_w_从布局。这个功能，因此必须加入之前调用_w_到布局的数据结构。

```
QLayout.addItem (self, QLayoutItem)
```

这种方法是抽象的，应在任何子类中重新实现。

该_QLayoutItem_说法有它的所有权转移给Qt的。

实现在子类中添加一个_item_。它是如何添加特定于每个子类。

这个功能并不是通常所说的应用程序代码。以一个小部件添加到布局，使用[addWidget](qlayout.html#addWidget)（ ）函数;有关规定增加一个子布局，使用addLayout （ ）函数[QLayout](qlayout.html)子类。

**Note:**所有权_item_被转移到布局，它的布局的责任将其删除。

**See also** [addWidget](qlayout.html#addWidget)（ ）[QBoxLayout.addLayout](qboxlayout.html#addLayout)（）和[QGridLayout.addLayout](qgridlayout.html#addLayout)（ ） 。

```
QLayout.addWidget (self, QWidget w)
```

该_w_说法有它的所有权转移给Qt的。

添加小工具_w_在特定的布局方式这样的布局。此函数使用[addItem](qlayout.html#addItem)（ ） 。

```
QRect QLayout.alignmentRect (self, QRect)
```

[](qrect.html)

[返回时，此布局的几何形状被设置为应涵盖的矩形_r_，但前提是这个布局支持](qrect.html)[setAlignment](qlayout.html#setAlignment)（ ） 。

其结果是衍生自[sizeHint](qlayoutitem.html#sizeHint)（ ）和扩展（ ） 。这是从来没有大于_r_。

```
QLayout.childEvent (self, QChildEvent e)
```

从重新实现[QObject.childEvent](qobject.html#childEvent)（ ） 。

```
QSize QLayout.closestAcceptableSize (QWidget w, QSize s)
```

[](qsize.html)

[返回一个大小满足所有尺寸的限制_widget_包括](qsize.html)[heightForWidth](qlayoutitem.html#heightForWidth)（ ），并且是尽可能接近到_size_。

```
QMargins QLayout.contentsMargins (self)
```

[

返回周围的布局中使用的利润。

](qmargins.html)

[默认情况下，](qmargins.html)[QLayout](qlayout.html)使用由式所提供的值。在大多数平台上，保证金是在所有方向11像素。

此功能被引入Qt的4.6 。

**See also** [setContentsMargins](qlayout.html#setContentsMargins)（ ） 。

```
QRect QLayout.contentsRect (self)
```

[](qrect.html)

[返回布局的](qrect.html)[geometry](qlayout.html#geometry)（ ）的矩形，但考虑到内容的利润率。

此功能被引入Qt的4.3 。

**See also** [setContentsMargins](qlayout.html#setContentsMargins)（）和[getContentsMargins](qlayout.html#getContentsMargins)（ ） 。

```
int QLayout.count (self)
```

这种方法是抽象的，应在任何子类中重新实现。

必须在子类中实现返回布局的项目数。

**See also** [itemAt](qlayout.html#itemAt)（ ） 。

```
Qt.Orientations QLayout.expandingDirections (self)
```

[](index.htm)

[从重新实现](index.htm)[QLayoutItem.expandingDirections](qlayoutitem.html#expandingDirections)（ ） 。

返回此布局是否可以使更多的空间比使用[sizeHint](qlayoutitem.html#sizeHint)（ ） 。的值[Qt.Vertical](qt.html#Orientation-enum) or [Qt.Horizontal](qt.html#Orientation-enum)意味着它要在只有一维增长，而[Qt.Vertical](qt.html#Orientation-enum)|[Qt.Horizontal](qt.html#Orientation-enum)也就是说，它要在这两个方面的增长。

默认实现返回[Qt.Horizontal](qt.html#Orientation-enum)|[Qt.Vertical](qt.html#Orientation-enum)。子类重新实现它返回基于其子控件的一个有意义的值[size policies](qsizepolicy.html)。

**See also** [sizeHint](qlayoutitem.html#sizeHint)（ ） 。

```
QRect QLayout.geometry (self)
```

[](qrect.html)

[从重新实现](qrect.html)[QLayoutItem.geometry](qlayoutitem.html#geometry)（ ） 。

**See also** [setGeometry](qlayout.html#setGeometry)（ ） 。

```
(int left, int top, int right, int bottom) QLayout.getContentsMargins (self)
```

提取左，上，右，和周围的布局中使用上下边界，并为它们分配到*_left_*_top_*_right_和*_bottom_（除非他们是空指针） 。

默认情况下，[QLayout](qlayout.html)使用由式所提供的值。在大多数平台上，保证金是在所有方向11像素。

此功能被引入Qt的4.3 。

**See also** [setContentsMargins](qlayout.html#setContentsMargins)（ ）[QStyle.pixelMetric](qstyle.html#pixelMetric)（ ）[PM_LayoutLeftMargin](qstyle.html#PixelMetric-enum)，[PM_LayoutTopMargin](qstyle.html#PixelMetric-enum)，[PM_LayoutRightMargin](qstyle.html#PixelMetric-enum)和[PM_LayoutBottomMargin](qstyle.html#PixelMetric-enum)。

```
int QLayout.indexOf (self, QWidget)
```

搜索小工具_widget_在这种布局（不包括子布局） 。

返回的索引_widget_，或-1，如果_widget_是没有找到。

对所有项目使用默认的实现迭代[itemAt](qlayout.html#itemAt)（ ）

```
QLayout.invalidate (self)
```

从重新实现[QLayoutItem.invalidate](qlayoutitem.html#invalidate)（ ） 。

```
bool QLayout.isEmpty (self)
```

从重新实现[QLayoutItem.isEmpty](qlayoutitem.html#isEmpty)（ ） 。

```
bool QLayout.isEnabled (self)
```

返回True如果启用了布局，否则返回False 。

**See also** [setEnabled](qlayout.html#setEnabled)（ ） 。

```
QLayoutItem QLayout.itemAt (self, int index)
```

[

这种方法是抽象的，应在任何子类中重新实现。

必须在子类中实现，以在返回版面项目_index_。如果不存在这样的产品，该函数必须返回0。项目从0连续编号。如果一个项目被删除，其他项目将被重新编号。

此功能可用于迭代的布局。下面的代码将绘制在小部件的布局结构为每个布局项目的矩形。

](qlayoutitem.html)

```
 static void paintLayout(QPainter *painter, [QLayoutItem](qlayoutitem.html) *item)
 {
     [QLayout](qlayout.html) *layout = item->layout();
     if (layout) {
         for (int i = 0; i < layout->count(); ++i)
             paintLayout(painter, layout->itemAt(i));
     }
     painter->drawRect(item->geometry());
 }

 void MyWidget.paintEvent([QPaintEvent](qpaintevent.html) *)
 {
     [QPainter](qpainter.html) painter(this);
     if (layout())
         paintLayout(&painter, layout());
 }

```

**See also** [count](qlayout.html#count)（）和[takeAt](qlayout.html#takeAt)（ ） 。

```
QLayout QLayout.layout (self)
```

[](qlayout.html)

[从重新实现](qlayout.html)[QLayoutItem.layout](qlayoutitem.html#layout)（ ） 。

```
int QLayout.margin (self)
```

```
QSize QLayout.maximumSize (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QLayoutItem.maximumSize](qlayoutitem.html#maximumSize)（ ） 。

返回此布局的最大尺寸。这是该布局可以有同时仍尊重规格的最大尺寸。

返回值不包括所需的空间[QWidget.setContentsMargins](qwidget.html#setContentsMargins)（）或[menuBar](qlayout.html#menuBar)（ ） 。

默认实现允许无限制调整大小。

```
QWidget QLayout.menuBar (self)
```

[

返回菜单栏设置此布局，或者0，如果没有菜单栏设置。

](qwidget.html)

[**See also**](qwidget.html) [setMenuBar](qlayout.html#setMenuBar)（ ） 。

```
QSize QLayout.minimumSize (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QLayoutItem.minimumSize](qlayoutitem.html#minimumSize)（ ） 。

返回此布局的最小尺寸。这是该布局可以有同时仍尊重的规格的最小尺寸。

返回值不包括所需的空间[QWidget.setContentsMargins](qwidget.html#setContentsMargins)（）或[menuBar](qlayout.html#menuBar)（ ） 。

默认实现允许无限制调整大小。

```
QWidget QLayout.parentWidget (self)
```

[

返回此布局，或0的父控件，如果这个布局上没有任何部件安装。

如果布局是一个子布局，该函数返回父布局的父控件。

](qwidget.html)

[**See also**](qwidget.html) [parent](qobject.html#parent)（ ） 。

```
QLayout.removeItem (self, QLayoutItem)
```

该_QLayoutItem_争论

删除布局项目_item_从布局。它是调用者的责任要删除的项目。

请注意，_item_可以是一个布局（自[QLayout](qlayout.html)继承[QLayoutItem](qlayoutitem.html)） 。

**See also** [removeWidget](qlayout.html#removeWidget)（）和[addItem](qlayout.html#addItem)（ ） 。

```
QLayout.removeWidget (self, QWidget w)
```

删除小工具_widget_从布局。此调用后，它是调用者的责任给小部件合理的几何形状或把小工具放回布局。

**Note:**所有权_widget_保持不变它被加入时相同。

**See also** [removeItem](qlayout.html#removeItem)（ ）[QWidget.setGeometry](qwidget.html#geometry-prop)（）和[addWidget](qlayout.html#addWidget)（ ） 。

```
bool QLayout.setAlignment (self, QWidget w, Qt.Alignment alignment)
```

设置对齐部件_w_至_alignment_并返回True ，如果_w_在这种布局（不包括子布局）被发现，否则返回False 。

```
bool QLayout.setAlignment (self, QLayout l, Qt.Alignment alignment)
```

设置此项目的对齐方式_alignment_。

**See also** [QLayoutItem.setAlignment](qlayoutitem.html#setAlignment)（ ） 。

```
QLayout.setAlignment (self, Qt.Alignment alignment)
```

这是一个重载函数。

设置对齐布局_l_至_alignment_并返回True ，如果_l_在这种布局（不包括子布局）被发现，否则返回False 。

```
QLayout.setContentsMargins (self, int left, int top, int right, int bottom)
```

设置_left_，_top_，_right_和_bottom_利润使用周围的布局。

默认情况下，[QLayout](qlayout.html)使用由式所提供的值。在大多数平台上，保证金是在所有方向11像素。

此功能被引入Qt的4.3 。

**See also** [contentsMargins](qlayout.html#contentsMargins)（ ）[getContentsMargins](qlayout.html#getContentsMargins)（ ）[QStyle.pixelMetric](qstyle.html#pixelMetric)（ ）[PM_LayoutLeftMargin](qstyle.html#PixelMetric-enum)，[PM_LayoutTopMargin](qstyle.html#PixelMetric-enum)，[PM_LayoutRightMargin](qstyle.html#PixelMetric-enum)和[PM_LayoutBottomMargin](qstyle.html#PixelMetric-enum)。

```
QLayout.setContentsMargins (self, QMargins margins)
```

设置_margins_使用周围的布局。

默认情况下，[QLayout](qlayout.html)使用由式所提供的值。在大多数平台上，保证金是在所有方向11像素。

此功能被引入Qt的4.6 。

**See also** [contentsMargins](qlayout.html#contentsMargins)（ ） 。

```
QLayout.setEnabled (self, bool)
```

启用此布局，如果_enable_是真，否则禁用它。

已启用的布局动态调整​​的变化，而停用的布局行为，就好像它不存在。

默认情况下所有版面已启用。

**See also** [isEnabled](qlayout.html#isEnabled)（ ） 。

```
QLayout.setGeometry (self, QRect)
```

从重新实现[QLayoutItem.setGeometry](qlayoutitem.html#setGeometry)（ ） 。

**See also** [geometry](qlayout.html#geometry)（ ） 。

```
QLayout.setMargin (self, int)
```

```
QLayout.setMenuBar (self, QWidget w)
```

该_w_说法有它的所有权转移给Qt的。

告诉几何管理器放置在菜单栏_widget_在顶部[parentWidget](qlayout.html#parentWidget)（ ） ，外[QWidget.contentsMargins](qwidget.html#contentsMargins)（ ） 。所有子控件放置在菜单栏的底部边缘下方。

**See also** [menuBar](qlayout.html#menuBar)（ ） 。

```
QLayout.setSizeConstraint (self, SizeConstraint)
```

```
QLayout.setSpacing (self, int)
```

```
SizeConstraint QLayout.sizeConstraint (self)
```

[

```
int QLayout.spacing (self)
```

](qlayout.html#SizeConstraint-enum)

```
QLayoutItem QLayout.takeAt (self, int index)
```

[

这种方法是抽象的，应在任何子类中重新实现。

该_QLayoutItem_结果

必须在子类中实现以除去布局项目_index_从布局，并返回该项目。如果没有这样的项目，该函数必须什么也不做，返回0 。项目从0连续编号。如果一个项目被删除，其他项目将被重新编号。

下面的代码片段显示了一个安全的方式从布局中删除的所有项目：

](qlayoutitem.html)

```
 QLayoutItem *child;
 while ((child = layout->takeAt(0)) != 0) {
     ...
     delete child;
 }

```

**See also** [itemAt](qlayout.html#itemAt)（）和[count](qlayout.html#count)（ ） 。

```
int QLayout.totalHeightForWidth (self, int w)
```

```
QSize QLayout.totalMaximumSize (self)
```

[](qsize.html)

```
QSize QLayout.totalMinimumSize (self)
```

[](qsize.html)

```
QSize QLayout.totalSizeHint (self)
```

[

```
QLayout.update (self)
```

](qsize.html)

[更新的布局](qsize.html)[parentWidget](qlayout.html#parentWidget)（ ） 。

你通常应该不需要调用这个，因为它是自动调用在最适当的时候。

**See also** [activate](qlayout.html#activate)（）和[invalidate](qlayout.html#invalidate)（ ） 。

```
QLayout.widgetEvent (self, QEvent)
```

```
 QLayout.__len__ (self)
```