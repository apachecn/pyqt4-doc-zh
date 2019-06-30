# QGraphicsLayoutItem Class Reference

## [[QtGui](index.htm) module]

该QGraphicsLayoutItem类可以继承，允许您自定义的项目由布局管理。[More...](#details)

通过继承[QGraphicsLayout](qgraphicslayout.html)和[QGraphicsWidget](qgraphicswidget.html)。

### Methods

*   `__init__ (self, QGraphicsLayoutItem parent = None, bool isLayout = False)`
*   `QRectF contentsRect (self)`
*   `QSizeF effectiveSizeHint (self, Qt.SizeHint which, QSizeF constraint = QSizeF())`
*   `QRectF geometry (self)`
*   `(float left, float top, float right, float bottom) getContentsMargins (self)`
*   `QGraphicsItem graphicsItem (self)`
*   `bool isLayout (self)`
*   `float maximumHeight (self)`
*   `QSizeF maximumSize (self)`
*   `float maximumWidth (self)`
*   `float minimumHeight (self)`
*   `QSizeF minimumSize (self)`
*   `float minimumWidth (self)`
*   `bool ownedByLayout (self)`
*   `QGraphicsLayoutItem parentLayoutItem (self)`
*   `float preferredHeight (self)`
*   `QSizeF preferredSize (self)`
*   `float preferredWidth (self)`
*   `setGeometry (self, QRectF rect)`
*   `setGraphicsItem (self, QGraphicsItem item)`
*   `setMaximumHeight (self, float height)`
*   `setMaximumSize (self, QSizeF size)`
*   `setMaximumSize (self, float aw, float ah)`
*   `setMaximumWidth (self, float width)`
*   `setMinimumHeight (self, float height)`
*   `setMinimumSize (self, QSizeF size)`
*   `setMinimumSize (self, float aw, float ah)`
*   `setMinimumWidth (self, float width)`
*   `setOwnedByLayout (self, bool ownedByLayout)`
*   `setParentLayoutItem (self, QGraphicsLayoutItem parent)`
*   `setPreferredHeight (self, float height)`
*   `setPreferredSize (self, QSizeF size)`
*   `setPreferredSize (self, float aw, float ah)`
*   `setPreferredWidth (self, float width)`
*   `setSizePolicy (self, QSizePolicy policy)`
*   `setSizePolicy (self, QSizePolicy.Policy hPolicy, QSizePolicy.Policy vPolicy, QSizePolicy.ControlType controlType = QSizePolicy.DefaultType)`
*   `QSizeF sizeHint (self, Qt.SizeHint which, QSizeF constraint = QSizeF())`
*   `QSizePolicy sizePolicy (self)`
*   `updateGeometry (self)`

* * *

## Detailed Description

该QGraphicsLayoutItem类可以继承，允许您自定义的项目由布局管理。

QGraphicsLayoutItem是定义一组虚函数描述的尺寸，大小政策，大小提示了由任何对象的抽象类[QGraphicsLayout](qgraphicslayout.html)。该API包含相关功能为项目本身和项目的用户，因为大多数的QGraphicsLayoutItem的功能也子类“公共API的一部分。

在大多数情况下，现有的布局识别类如[QGraphicsWidget](qgraphicswidget.html)和[QGraphicsLayout](qgraphicslayout.html)已经提供您需要的功能。然而，子类化这些类可以让你同时创建与布局工作以及图形元素（[QGraphicsWidget](qgraphicswidget.html)）或自定义布局（[QGraphicsLayout](qgraphicslayout.html)） 。

### Subclassing QGraphicsLayoutItem

如果您创建QGraphicsLayoutItem的一个子类，并重新实现其虚函数，你将使布局调整和定位您的项目以及其他QGraphicsLayoutItems包括[QGraphicsWidget](qgraphicswidget.html)和[QGraphicsLayout](qgraphicslayout.html)。

你可以开始通过重新实现重要的功能：保护[sizeHint](qgraphicslayoutitem.html#sizeHint)（）函数，以及公共[setGeometry](qgraphicslayoutitem.html#setGeometry)（）函数。如果你希望你的项目做到心中有数即时几何变化，你也可以重新实现[updateGeometry](qgraphicslayoutitem.html#updateGeometry)（ ） 。

几何形状，尺寸暗示，和大小政策影响的项目的大小和位置。调用[setGeometry](qgraphicslayoutitem.html#setGeometry)（ ）总是会调整，并立即重新定位的项目。通常情况下，这个函数被调用者[QGraphicsLayout](qgraphicslayout.html)后的布局已经被激活，但它也可以由该项目的用户在任何时间被调用。

该[sizeHint](qgraphicslayoutitem.html#sizeHint)（ ）函数返回的项目'最小，首选和最大大小的提示。你可以通过调用重载这些属性[setMinimumSize](qgraphicslayoutitem.html#setMinimumSize)（ ）[setPreferredSize](qgraphicslayoutitem.html#setPreferredSize)（）或[setMaximumSize](qgraphicslayoutitem.html#setMaximumSize)（ ） 。您还可以使用的功能，如[setMinimumWidth](qgraphicslayoutitem.html#setMinimumWidth)（）或[setMaximumHeight](qgraphicslayoutitem.html#setMaximumHeight)（如果需要的话），以仅设置宽度或高度的组件。

该[effectiveSizeHint](qgraphicslayoutitem.html#effectiveSizeHint)（）函数，在另一方面，它返回一个大小暗示对于任何给定[Qt.SizeHint](qt.html#SizeHint-enum)，并保证了返回的大小被绑定到的最小和最大尺寸和大小的提示。你可以通过调用设定的项目的水平和垂直尺寸的政策[setSizePolicy](qgraphicslayoutitem.html#setSizePolicy)（ ） 。该sizePolicy属性由布局系统来描述这个项目倾向于增大或缩小。

### Nesting QGraphicsLayoutItems

可以嵌套在其他QGraphicsLayoutItems ，类似的布局，它可以包含sublayouts内QGraphicsLayoutItems 。这要么是通过传递一个QGraphicsLayoutItem指针QGraphicsLayoutItem的受保护的构造，或致电进行[setParentLayoutItem](qgraphicslayoutitem.html#setParentLayoutItem)（ ） 。该[parentLayoutItem](qgraphicslayoutitem.html#parentLayoutItem)（ ）函数返回一个指向该项目的layoutItem父。如果该项目的母公司为0 ，或者如果家长不从继承[QGraphicsItem](qgraphicsitem.html)时，[parentLayoutItem](qgraphicslayoutitem.html#parentLayoutItem)（ ）函数则返回0 。[isLayout](qgraphicslayoutitem.html#isLayout)如果QGraphicsLayoutItem子类本身就是一个布局，否则为False （）返回True 。

Qt使用QGraphicsLayoutItem提供布局功能的[Graphics View Framework](index.htm)，但在未来它的使用可能在整个Qt本身传播。

* * *

## Method Documentation

```
QGraphicsLayoutItem.__init__ (self, QGraphicsLayoutItem parent = None, bool isLayout = False)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构建[QGraphicsLayoutItem](qgraphicslayoutitem.html)对象。_parent_成为该对象的父。如果_isLayout_是真实的产品布局，否则_isLayout_是假的。

```
QRectF QGraphicsLayoutItem.contentsRect (self)
```

[

返回的内容RECT在本地坐标。

](qrectf.html)

[内容RECT定义安排子项目时所使用的相关联的布局的子矩形。这个函数是一个方便的功能，调整该项目的](qrectf.html)[geometry](qgraphicslayoutitem.html#geometry)（ ）其内容的利润率。需要注意的是[getContentsMargins](qgraphicslayoutitem.html#getContentsMargins)（）是一个虚函数，你可以重新实现返回该项目的内容利润率。

**See also** [getContentsMargins](qgraphicslayoutitem.html#getContentsMargins)（）和[geometry](qgraphicslayoutitem.html#geometry)（ ） 。

```
QSizeF QGraphicsLayoutItem.effectiveSizeHint (self, Qt.SizeHint which, QSizeF constraint = QSizeF())
```

[](qsizef.html)

[返回的有效尺寸暗示这](qsizef.html)[QGraphicsLayoutItem](qgraphicslayoutitem.html)。

_which_是有问题的大小提示。_constraint_是计算实际尺寸暗示，当定义了一个特殊约束可选参数。默认情况下，_constraint_ is [QSizeF](qsizef.html)（ -1，-1） ，表示没有约束的尺寸暗示。

如果您要指定物件的尺寸暗示对于给定的宽度或高度，可以提供固定的维度_constraint_。这是一个小工具，可以仅增长水平或垂直，并且需要设置或者其宽度或高度的一个特殊值非常有用。

例如，一个文本段落产品放进200列宽可以垂直生长。你可以通过[QSizeF](qsizef.html)（200 ，-1）作为约束得到一个合适的最小，首选和最大高度）。

您可以通过重新实现调整的有效尺寸提示[sizeHint](qgraphicslayoutitem.html#sizeHint)在（）[QGraphicsLayoutItem](qgraphicslayoutitem.html)子类，或致电以下功能之一：[setMinimumSize](qgraphicslayoutitem.html#setMinimumSize)（ ） ， setPreferredSize ，或[setMaximumSize](qgraphicslayoutitem.html#setMaximumSize)（ ）（或两者的组合） 。

这个功能每个缓存的大小的提示和保证[sizeHint](qgraphicslayoutitem.html#sizeHint)（ ）将被用于的每个值只被调用一次_which_ - 除非_constraint_没有被指定，并[updateGeometry](qgraphicslayoutitem.html#updateGeometry)（ ）被调用。

**See also** [sizeHint](qgraphicslayoutitem.html#sizeHint)（ ） 。

```
QRectF QGraphicsLayoutItem.geometry (self)
```

[](qrectf.html)

[返回该项目的几何形状（例如，位置和大小）作为](qrectf.html)[QRectF](qrectf.html)。此功能相当于[QRectF](qrectf.html)（POS （） ，面积（））。

**See also** [setGeometry](qgraphicslayoutitem.html#setGeometry)（ ） 。

```
(float left, float top, float right, float bottom) QGraphicsLayoutItem.getContentsMargins (self)
```

这个虚函数提供了_left_，_top_，_right_和_bottom_内容利润率为这个[QGraphicsLayoutItem](qgraphicslayoutitem.html)。默认实现假设所有内容边距为0 。参数指向存储在qreals值。如果有任何的指针为0 ，则该值将不会被更新。

**See also** [QGraphicsWidget.setContentsMargins](qgraphicswidget.html#setContentsMargins)（ ） 。

```
QGraphicsItem QGraphicsLayoutItem.graphicsItem (self)
```

[](qgraphicsitem.html)

[返回](qgraphicsitem.html)[QGraphicsItem](qgraphicsitem.html)这个布局项目代表。为[QGraphicsWidget](qgraphicswidget.html)它会返回自身。对于自定义项目可以返回一个汇总值。

**See also** [setGraphicsItem](qgraphicslayoutitem.html#setGraphicsItem)（ ） 。

```
bool QGraphicsLayoutItem.isLayout (self)
```

返回True如果[QGraphicsLayoutItem](qgraphicslayoutitem.html)是一个布局（例如，由一个对象，安排其他遗传[QGraphicsLayoutItem](qgraphicslayoutitem.html)对象），否则返回False 。

**See also** [QGraphicsLayout](qgraphicslayout.html)。

```
float QGraphicsLayoutItem.maximumHeight (self)
```

返回的最大高度。

**See also** [setMaximumHeight](qgraphicslayoutitem.html#setMaximumHeight)（ ）[setMaximumSize](qgraphicslayoutitem.html#setMaximumSize)（）和[maximumSize](qgraphicslayoutitem.html#maximumSize)（ ） 。

```
QSizeF QGraphicsLayoutItem.maximumSize (self)
```

[

返回的最大大小。

](qsizef.html)

[**See also**](qsizef.html) [setMaximumSize](qgraphicslayoutitem.html#setMaximumSize)（ ）[minimumSize](qgraphicslayoutitem.html#minimumSize)（ ）[preferredSize](qgraphicslayoutitem.html#preferredSize)（ ）[Qt.MaximumSize](qt.html#SizeHint-enum)和[sizeHint](qgraphicslayoutitem.html#sizeHint)（ ） 。

```
float QGraphicsLayoutItem.maximumWidth (self)
```

返回的最大宽度。

**See also** [setMaximumWidth](qgraphicslayoutitem.html#setMaximumWidth)（ ）[setMaximumSize](qgraphicslayoutitem.html#setMaximumSize)（）和[maximumSize](qgraphicslayoutitem.html#maximumSize)（ ） 。

```
float QGraphicsLayoutItem.minimumHeight (self)
```

返回最小高度。

**See also** [setMinimumHeight](qgraphicslayoutitem.html#setMinimumHeight)（ ）[setMinimumSize](qgraphicslayoutitem.html#setMinimumSize)（）和[minimumSize](qgraphicslayoutitem.html#minimumSize)（ ） 。

```
QSizeF QGraphicsLayoutItem.minimumSize (self)
```

[

返回最小尺寸。

](qsizef.html)

[**See also**](qsizef.html) [setMinimumSize](qgraphicslayoutitem.html#setMinimumSize)（ ）[preferredSize](qgraphicslayoutitem.html#preferredSize)（ ）[maximumSize](qgraphicslayoutitem.html#maximumSize)（ ）[Qt.MinimumSize](qt.html#SizeHint-enum)和[sizeHint](qgraphicslayoutitem.html#sizeHint)（ ） 。

```
float QGraphicsLayoutItem.minimumWidth (self)
```

返回最小宽度。

**See also** [setMinimumWidth](qgraphicslayoutitem.html#setMinimumWidth)（ ）[setMinimumSize](qgraphicslayoutitem.html#setMinimumSize)（）和[minimumSize](qgraphicslayoutitem.html#minimumSize)（ ） 。

```
bool QGraphicsLayoutItem.ownedByLayout (self)
```

返回一个布局是否应该删除其析构函数资料。如果为True，则布局将其删除。如果为False，那么假定另一个对象有它的所有权和布局不会删除此文件。

如果该项目既继承[QGraphicsItem](qgraphicsitem.html)和[QGraphicsLayoutItem](qgraphicslayoutitem.html)（如[QGraphicsWidget](qgraphicswidget.html)一样）的产品真的两个层次所有权的一部分。此属性通知什么样的布局应与其子项做时，它被破坏。在的情况下[QGraphicsWidget](qgraphicswidget.html)，优选的是，当布局被删除也不会删除它的孩子（因为它们也是图形项目分层结构的一部分）。

默认情况下这个值被初始化为False[QGraphicsLayoutItem](qgraphicslayoutitem.html)的，但它是由被重写[QGraphicsLayout](qgraphicslayout.html)返回True 。这是因为[QGraphicsLayout](qgraphicslayout.html)不是的正常组成部分[QGraphicsItem](qgraphicsitem.html)层次结构，因此父布局应删除它。子类可以通过调用setOwnedByLayout （真）复盖此默认行为。

此功能被引入Qt的4.6 。

**See also** [setOwnedByLayout](qgraphicslayoutitem.html#setOwnedByLayout)（ ） 。

```
QGraphicsLayoutItem QGraphicsLayoutItem.parentLayoutItem (self)
```

[](qgraphicslayoutitem.html)

[返回此父](qgraphicslayoutitem.html)[QGraphicsLayoutItem](qgraphicslayoutitem.html)，或者0 ，如果没有父母，或如果家长不从继承[QGraphicsLayoutItem](qgraphicslayoutitem.html)（[QGraphicsLayoutItem](qgraphicslayoutitem.html)往往是通过多重继承与使用[QObject](qobject.html)派生类） 。

**See also** [setParentLayoutItem](qgraphicslayoutitem.html#setParentLayoutItem)（ ） 。

```
float QGraphicsLayoutItem.preferredHeight (self)
```

返回的首选高度。

**See also** [setPreferredHeight](qgraphicslayoutitem.html#setPreferredHeight)（ ）[setPreferredSize](qgraphicslayoutitem.html#setPreferredSize)（）和[preferredSize](qgraphicslayoutitem.html#preferredSize)（ ） 。

```
QSizeF QGraphicsLayoutItem.preferredSize (self)
```

[

返回首选大小。

](qsizef.html)

[**See also**](qsizef.html) [setPreferredSize](qgraphicslayoutitem.html#setPreferredSize)（ ）[minimumSize](qgraphicslayoutitem.html#minimumSize)（ ）[maximumSize](qgraphicslayoutitem.html#maximumSize)（ ）[Qt.PreferredSize](qt.html#SizeHint-enum)和[sizeHint](qgraphicslayoutitem.html#sizeHint)（ ） 。

```
float QGraphicsLayoutItem.preferredWidth (self)
```

返回的首选宽度。

**See also** [setPreferredWidth](qgraphicslayoutitem.html#setPreferredWidth)（ ）[setPreferredSize](qgraphicslayoutitem.html#setPreferredSize)（）和[preferredSize](qgraphicslayoutitem.html#preferredSize)（ ） 。

```
QGraphicsLayoutItem.setGeometry (self, QRectF rect)
```

这个虚拟函数设置的几何[QGraphicsLayoutItem](qgraphicslayoutitem.html)至_rect_，这是在父坐标（例如，在左上角_rect_等效于在父坐标中的项的位置）。

您必须在子类中重新实现这个功能[QGraphicsLayoutItem](qgraphicslayoutitem.html)接收几何更新。该布局将调用此函数时，它做了重排。

If _rect_是的MinimumSize和MAXIMUMSIZE的范围之外，将被调整到其最接近的大小，以便它是合法范围内。

**See also** [geometry](qgraphicslayoutitem.html#geometry)（ ） 。

```
QGraphicsLayoutItem.setGraphicsItem (self, QGraphicsItem item)
```

如果[QGraphicsLayoutItem](qgraphicslayoutitem.html)代表[QGraphicsItem](qgraphicsitem.html)，以及它要采取的自动重定父级功能的优势[QGraphicsLayout](qgraphicslayout.html)它应该设置这个值。需要注意的是，如果你删除_item_而不是删除版面项目，你有责任（ 0 ） ，以避免悬空指针调用setGraphicsItem的。

**See also** [graphicsItem](qgraphicslayoutitem.html#graphicsItem)（ ） 。

```
QGraphicsLayoutItem.setMaximumHeight (self, float height)
```

设置最大高度_height_。

**See also** [maximumHeight](qgraphicslayoutitem.html#maximumHeight)（ ）[setMaximumSize](qgraphicslayoutitem.html#setMaximumSize)（）和[maximumSize](qgraphicslayoutitem.html#maximumSize)（ ） 。

```
QGraphicsLayoutItem.setMaximumSize (self, QSizeF size)
```

设置最大尺寸_size_。此属性重写[sizeHint](qgraphicslayoutitem.html#sizeHint)（ ）为[Qt.MaximumSize](qt.html#SizeHint-enum)并确保[effectiveSizeHint](qgraphicslayoutitem.html#effectiveSizeHint)（ ）将永远不会返回一个尺寸大于_size_。为了取消设置的最大大小，使用一个无效的大小。

**See also** [maximumSize](qgraphicslayoutitem.html#maximumSize)（ ）[minimumSize](qgraphicslayoutitem.html#minimumSize)（ ）[preferredSize](qgraphicslayoutitem.html#preferredSize)（ ）[Qt.MaximumSize](qt.html#SizeHint-enum)和[sizeHint](qgraphicslayoutitem.html#sizeHint)（ ） 。

```
QGraphicsLayoutItem.setMaximumSize (self, float aw, float ah)
```

这个方便的功能等同于调用setMaximumSize （[QSizeF](qsizef.html)（_w_，_h_））。

**See also** [maximumSize](qgraphicslayoutitem.html#maximumSize)（ ）[setMinimumSize](qgraphicslayoutitem.html#setMinimumSize)（ ）[setPreferredSize](qgraphicslayoutitem.html#setPreferredSize)（）和[sizeHint](qgraphicslayoutitem.html#sizeHint)（ ） 。

```
QGraphicsLayoutItem.setMaximumWidth (self, float width)
```

设置最大宽度，以_width_。

**See also** [maximumWidth](qgraphicslayoutitem.html#maximumWidth)（ ）[setMaximumSize](qgraphicslayoutitem.html#setMaximumSize)（）和[maximumSize](qgraphicslayoutitem.html#maximumSize)（ ） 。

```
QGraphicsLayoutItem.setMinimumHeight (self, float height)
```

设置最小高度_height_。

**See also** [minimumHeight](qgraphicslayoutitem.html#minimumHeight)（ ）[setMinimumSize](qgraphicslayoutitem.html#setMinimumSize)（）和[minimumSize](qgraphicslayoutitem.html#minimumSize)（ ） 。

```
QGraphicsLayoutItem.setMinimumSize (self, QSizeF size)
```

设置最小大小至_size_。此属性重写[sizeHint](qgraphicslayoutitem.html#sizeHint)（ ）为[Qt.MinimumSize](qt.html#SizeHint-enum)并确保[effectiveSizeHint](qgraphicslayoutitem.html#effectiveSizeHint)（ ）将永远不会返回一个尺寸小于_size_。为了取消设置的最小尺寸，使用一个无效的大小。

**See also** [minimumSize](qgraphicslayoutitem.html#minimumSize)（ ）[maximumSize](qgraphicslayoutitem.html#maximumSize)（ ）[preferredSize](qgraphicslayoutitem.html#preferredSize)（ ）[Qt.MinimumSize](qt.html#SizeHint-enum)，[sizeHint](qgraphicslayoutitem.html#sizeHint)（ ）[setMinimumWidth](qgraphicslayoutitem.html#setMinimumWidth)（）和[setMinimumHeight](qgraphicslayoutitem.html#setMinimumHeight)（ ） 。

```
QGraphicsLayoutItem.setMinimumSize (self, float aw, float ah)
```

这个方便的功能等同于调用setMinimumSize （[QSizeF](qsizef.html)（_w_，_h_））。

**See also** [minimumSize](qgraphicslayoutitem.html#minimumSize)（ ）[setMaximumSize](qgraphicslayoutitem.html#setMaximumSize)（ ）[setPreferredSize](qgraphicslayoutitem.html#setPreferredSize)（）和[sizeHint](qgraphicslayoutitem.html#sizeHint)（ ） 。

```
QGraphicsLayoutItem.setMinimumWidth (self, float width)
```

设置最小宽度，以_width_。

**See also** [minimumWidth](qgraphicslayoutitem.html#minimumWidth)（ ）[setMinimumSize](qgraphicslayoutitem.html#setMinimumSize)（）和[minimumSize](qgraphicslayoutitem.html#minimumSize)（ ） 。

```
QGraphicsLayoutItem.setOwnedByLayout (self, bool ownedByLayout)
```

设置一个布局是否应该删除其析构函数或不是这个项目。_ownership_必须按顺序进行布局，以删除它是真实的。

此功能被引入Qt的4.6 。

**See also** [ownedByLayout](qgraphicslayoutitem.html#ownedByLayout)（ ） 。

```
QGraphicsLayoutItem.setParentLayoutItem (self, QGraphicsLayoutItem parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

设置的这个父[QGraphicsLayoutItem](qgraphicslayoutitem.html)至_parent_。

**See also** [parentLayoutItem](qgraphicslayoutitem.html#parentLayoutItem)（ ） 。

```
QGraphicsLayoutItem.setPreferredHeight (self, float height)
```

设置首选高度_height_。

**See also** [preferredHeight](qgraphicslayoutitem.html#preferredHeight)（ ）[preferredWidth](qgraphicslayoutitem.html#preferredWidth)（ ）[setPreferredSize](qgraphicslayoutitem.html#setPreferredSize)（）和[preferredSize](qgraphicslayoutitem.html#preferredSize)（ ） 。

```
QGraphicsLayoutItem.setPreferredSize (self, QSizeF size)
```

设置首选大小_size_。此属性重写[sizeHint](qgraphicslayoutitem.html#sizeHint)（ ）为[Qt.PreferredSize](qt.html#SizeHint-enum)并提供默认值[effectiveSizeHint](qgraphicslayoutitem.html#effectiveSizeHint)（ ） 。为了取消设置的首选大小，使用一个无效的大小。

**See also** [preferredSize](qgraphicslayoutitem.html#preferredSize)（ ）[minimumSize](qgraphicslayoutitem.html#minimumSize)（ ）[maximumSize](qgraphicslayoutitem.html#maximumSize)（ ）[Qt.PreferredSize](qt.html#SizeHint-enum)和[sizeHint](qgraphicslayoutitem.html#sizeHint)（ ） 。

```
QGraphicsLayoutItem.setPreferredSize (self, float aw, float ah)
```

这个方便的功能等同于调用setPreferredSize （[QSizeF](qsizef.html)（_w_，_h_））。

**See also** [preferredSize](qgraphicslayoutitem.html#preferredSize)（ ）[setMaximumSize](qgraphicslayoutitem.html#setMaximumSize)（ ）[setMinimumSize](qgraphicslayoutitem.html#setMinimumSize)（）和[sizeHint](qgraphicslayoutitem.html#sizeHint)（ ） 。

```
QGraphicsLayoutItem.setPreferredWidth (self, float width)
```

设置首选宽度_width_。

**See also** [preferredWidth](qgraphicslayoutitem.html#preferredWidth)（ ）[preferredHeight](qgraphicslayoutitem.html#preferredHeight)（ ）[setPreferredSize](qgraphicslayoutitem.html#setPreferredSize)（）和[preferredSize](qgraphicslayoutitem.html#preferredSize)（ ） 。

```
QGraphicsLayoutItem.setSizePolicy (self, QSizePolicy policy)
```

设置大小政策_policy_。大小政策说明如何安排时，在布局中的项目应增加水平和垂直方向。

[QGraphicsLayoutItem](qgraphicslayoutitem.html)的默认大小政策（[QSizePolicy.Fixed](qsizepolicy.html#Policy-enum)，[QSizePolicy.Fixed](qsizepolicy.html#Policy-enum)，[QSizePolicy.DefaultType](qsizepolicy.html#ControlType-enum)），但它是很常见的子类来更改默认值。例如，[QGraphicsWidget](qgraphicswidget.html)默认为（[QSizePolicy.Preferred](qsizepolicy.html#Policy-enum)，[QSizePolicy.Preferred](qsizepolicy.html#Policy-enum)，[QSizePolicy.DefaultType](qsizepolicy.html#ControlType-enum)） 。

**See also** [sizePolicy](qgraphicslayoutitem.html#sizePolicy)（）和[QWidget.sizePolicy](qwidget.html#sizePolicy-prop)（ ） 。

```
QGraphicsLayoutItem.setSizePolicy (self, QSizePolicy.Policy hPolicy, QSizePolicy.Policy vPolicy, QSizePolicy.ControlType controlType = QSizePolicy.DefaultType)
```

这是一个重载函数。

此功能相当于调用setSizePolicy （[QSizePolicy](qsizepolicy.html)（_hPolicy_，_vPolicy_，_controlType_））。

**See also** [sizePolicy](qgraphicslayoutitem.html#sizePolicy)（）和[QWidget.sizePolicy](qwidget.html#sizePolicy-prop)（ ） 。

```
QSizeF QGraphicsLayoutItem.sizeHint (self, Qt.SizeHint which, QSizeF constraint = QSizeF())
```

[

这种方法是抽象的，应在任何子类中重新实现。

](qsizef.html)

[这个纯虚函数返回的大小为提示_which_的](qsizef.html)[QGraphicsLayoutItem](qgraphicslayoutitem.html)使用的宽度或高度_constraint_来限制输出。

在子类重新实现此功能[QGraphicsLayoutItem](qgraphicslayoutitem.html)提供必要的尺寸提示为您的项目。

**See also** [effectiveSizeHint](qgraphicslayoutitem.html#effectiveSizeHint)（ ） 。

```
QSizePolicy QGraphicsLayoutItem.sizePolicy (self)
```

[

返回当前大小政策。

](qsizepolicy.html)

[**See also**](qsizepolicy.html) [setSizePolicy](qgraphicslayoutitem.html#setSizePolicy)（）和[QWidget.sizePolicy](qwidget.html#sizePolicy-prop)（ ） 。

```
QGraphicsLayoutItem.updateGeometry (self)
```

这个虚函数丢弃任何缓存大小的提示信息。你应该总是调用这个函数，如果你改变的返回值[sizeHint](qgraphicslayoutitem.html#sizeHint)（）函数。重新实现此功能，当子类必须始终调用基实现。

**See also** [effectiveSizeHint](qgraphicslayoutitem.html#effectiveSizeHint)（ ） 。