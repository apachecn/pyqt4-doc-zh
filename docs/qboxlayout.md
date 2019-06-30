# QBoxLayout Class Reference

## [[QtGui](index.htm) module]

该QBoxLayout班线达子部件水平或垂直。[More...](#details)

继承[QLayout](qlayout.html)。

通过继承[QHBoxLayout](qhboxlayout.html)和[QVBoxLayout](qvboxlayout.html)。

### Types

*   `enum Direction { LeftToRight, RightToLeft, TopToBottom, BottomToTop, Down, Up }`

### Methods

*   `__init__ (self, Direction direction, QWidget parent = None)`
*   `addItem (self, QLayoutItem)`
*   `addLayout (self, QLayout layout, int stretch = 0)`
*   `addSpacerItem (self, QSpacerItem spacerItem)`
*   `addSpacing (self, int size)`
*   `addStretch (self, int stretch = 0)`
*   `addStrut (self, int)`
*   `addWidget (self, QWidget, int stretch = 0, Qt.Alignment alignment = 0)`
*   `int count (self)`
*   `Direction direction (self)`
*   `Qt.Orientations expandingDirections (self)`
*   `bool hasHeightForWidth (self)`
*   `int heightForWidth (self, int)`
*   `insertItem (self, int index, QLayoutItem)`
*   `insertLayout (self, int index, QLayout layout, int stretch = 0)`
*   `insertSpacerItem (self, int index, QSpacerItem spacerItem)`
*   `insertSpacing (self, int index, int size)`
*   `insertStretch (self, int index, int stretch = 0)`
*   `insertWidget (self, int index, QWidget widget, int stretch = 0, Qt.Alignment alignment = 0)`
*   `invalidate (self)`
*   `QLayoutItem itemAt (self, int)`
*   `QSize maximumSize (self)`
*   `int minimumHeightForWidth (self, int)`
*   `QSize minimumSize (self)`
*   `setDirection (self, Direction)`
*   `setGeometry (self, QRect)`
*   `setSpacing (self, int spacing)`
*   `setStretch (self, int index, int stretch)`
*   `bool setStretchFactor (self, QWidget w, int stretch)`
*   `bool setStretchFactor (self, QLayout l, int stretch)`
*   `QSize sizeHint (self)`
*   `int spacing (self)`
*   `int stretch (self, int index)`
*   `QLayoutItem takeAt (self, int)`

* * *

## Detailed Description

该QBoxLayout班线达子部件水平或垂直。

QBoxLayout佔用空间它得到（从其父布局或从[parentWidget](qlayout.html#parentWidget)（ ） ） ，将其划分成一排箱子，并使得每个管理部件填补一个盒子。

![Horizontal box layout with five child widgets](../img/qhboxlayout-with-5-children.png)

如果QBoxLayout的方向是[Qt.Horizontal](qt.html#Orientation-enum)盒子被放置在一个行中，用合适的尺寸。每个窗口小部件（或其他框）将得到至少它的最小尺寸，并在最其最大大小。任何多馀的空间是根据拉伸​​系数（更多关于下文）共享。

![Vertical box layout with five child widgets](../img/qvboxlayout-with-5-children.png)

如果QBoxLayout的方向是[Qt.Vertical](qt.html#Orientation-enum)时，盒被放置在一个柱，再以合适的尺寸。

创建QBoxLayout最简单的方法是使用便利的一个类，例如[QHBoxLayout](qhboxlayout.html)（为[Qt.Horizontal](qt.html#Orientation-enum)框）或[QVBoxLayout](qvboxlayout.html)（为[Qt.Vertical](qt.html#Orientation-enum)框） 。您也可以直接使用QBoxLayout构造函数，指定其方向[LeftToRight](qboxlayout.html#Direction-enum)，[RightToLeft](qboxlayout.html#Direction-enum)，[TopToBottom](qboxlayout.html#Direction-enum)或[BottomToTop](qboxlayout.html#Direction-enum)。

如果QBoxLayout不是顶层布局（即它不是管理所有部件的面积和儿童） ，您必须将其添加到它的父布局之前，你可以用它做任何事情。正常的方式来添加一个布局是通过调用parentLayout - \u003e[addLayout](qboxlayout.html#addLayout)（ ） 。

一旦你这样做，你可以添加盒使用四个功能之一的QBoxLayout ：

*   [addWidget](qboxlayout.html#addWidget)() to add a widget to the QBoxLayout and set the widget's stretch factor. (The stretch factor is along the row of boxes.)
*   [addSpacing](qboxlayout.html#addSpacing)() to create an empty box; this is one of the functions you use to create nice and spacious dialogs. See below for ways to set margins.
*   [addStretch](qboxlayout.html#addStretch)() to create an empty, stretchable box.
*   [addLayout](qboxlayout.html#addLayout)() to add a box containing another [QLayout](qlayout.html) to the row and set that layout's stretch factor.

使用[insertWidget](qboxlayout.html#insertWidget)（ ）[insertSpacing](qboxlayout.html#insertSpacing)（ ）[insertStretch](qboxlayout.html#insertStretch)（）或[insertLayout](qboxlayout.html#insertLayout)（）插入一个框在布局中的指定位置。

QBoxLayout还包括两个边宽度：

*   [setContentsMargins](qlayout.html#setContentsMargins)() sets the width of the outer border on each side of the widget. This is the width of the reserved space along each of the QBoxLayout's four sides.
*   [setSpacing](qboxlayout.html#setSpacing)() sets the width between neighboring boxes. (You can use [addSpacing](qboxlayout.html#addSpacing)() to get more space at a particular spot.)

保证金默认是由风格提供。默认边距最的Qt样式指定为9子控件和11窗口。的间隔预设为相同的边宽为顶层布局，或以相同的父布局。

从布局中删除一个小部件，请致电[removeWidget](qlayout.html#removeWidget)（ ） 。调用[QWidget.hide](qwidget.html#hide)（ ）上的一个小部件也有效地消除了从布局小部件，直到[QWidget.show](qwidget.html#show)（）被调用。

你几乎总是要使用[QVBoxLayout](qvboxlayout.html)和[QHBoxLayout](qhboxlayout.html)而不是QBoxLayout因为他们的方便的构造函数。

* * *

## Type Documentation

```
QBoxLayout.Direction
```

这种类型被用来确定一个框布局的方向。

| Constant | Value | Description |
| --- | --- | --- |
| `QBoxLayout.LeftToRight` | `0` | 水平左向右。 |
| `QBoxLayout.RightToLeft` | `1` | 由右至左的水平。 |
| `QBoxLayout.TopToBottom` | `2` | 垂直从上到下。 |
| `QBoxLayout.BottomToTop` | `3` | 垂直从底部到顶部。 |

* * *

## Method Documentation

```
QBoxLayout.__init__ (self, Direction direction, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的[QBoxLayout](qboxlayout.html)与方向_dir_与父控件_parent_。

**See also** [direction](qboxlayout.html#direction)（ ） 。

```
QBoxLayout.addItem (self, QLayoutItem)
```

该_QLayoutItem_说法有它的所有权转移给Qt的。

从重新实现[QLayout.addItem](qlayout.html#addItem)（ ） 。

```
QBoxLayout.addLayout (self, QLayout layout, int stretch = 0)
```

该_layout_说法有它的所有权转移给Qt的。

添加_layout_该框，带串口拉伸系数年底_stretch_。

**See also** [insertLayout](qboxlayout.html#insertLayout)（ ）[addItem](qboxlayout.html#addItem)（）和[addWidget](qboxlayout.html#addWidget)（ ） 。

```
QBoxLayout.addSpacerItem (self, QSpacerItem spacerItem)
```

该_spacerItem_说法有它的所有权转移给Qt的。

添加_spacerItem_对这个方块布局结束。

此功能被引入Qt的4.4 。

**See also** [addSpacing](qboxlayout.html#addSpacing)（）和[addStretch](qboxlayout.html#addStretch)（ ） 。

```
QBoxLayout.addSpacing (self, int size)
```

添加非伸缩性的空间（一[QSpacerItem](qspaceritem.html)）与大小_size_对这个方块布局结束。[QBoxLayout](qboxlayout.html)提供默认边距和间距。此功能增加了额外的空间。

**See also** [insertSpacing](qboxlayout.html#insertSpacing)（ ）[addItem](qboxlayout.html#addItem)（）和[QSpacerItem](qspaceritem.html)。

```
QBoxLayout.addStretch (self, int stretch = 0)
```

增加了拉伸空间（[QSpacerItem](qspaceritem.html)）与零的最小尺寸和拉伸系数_stretch_对这个方块布局结束。

**See also** [insertStretch](qboxlayout.html#insertStretch)（ ）[addItem](qboxlayout.html#addItem)（）和[QSpacerItem](qspaceritem.html)。

```
QBoxLayout.addStrut (self, int)
```

限制框的垂直尺寸，如果盒子是（例如高度[LeftToRight](qboxlayout.html#Direction-enum)）为最小_size_。其他制约因素可能会增加限制。

**See also** [addItem](qboxlayout.html#addItem)（ ） 。

```
QBoxLayout.addWidget (self, QWidget, int stretch = 0, Qt.Alignment alignment = 0)
```

该_QWidget_说法有它的所有权转移给Qt的。

添加_widget_对这个盒子的布局，以舒展的因素到底_stretch_和对齐_alignment_。

只有拉伸系数适用于[direction](qboxlayout.html#direction)的[QBoxLayout](qboxlayout.html)，并且是相对于另一个盒和小部件在这[QBoxLayout](qboxlayout.html)。小工具和箱子具有较高的拉伸因素变得更加。

如果拉伸系数为0，没有其他的[QBoxLayout](qboxlayout.html)已拉伸因子大于零，该空间是根据分布式[QWidget](qwidget.html)： sizePolicy是涉及到每个插件的（ ） 。

该路线是由指定的_alignment_。默认的对齐是0，这意味着该插件充满整个细胞。

**See also** [insertWidget](qboxlayout.html#insertWidget)（ ）[addItem](qboxlayout.html#addItem)（ ）[addLayout](qboxlayout.html#addLayout)（ ）[addStretch](qboxlayout.html#addStretch)（ ）[addSpacing](qboxlayout.html#addSpacing)（）和[addStrut](qboxlayout.html#addStrut)（ ） 。

```
int QBoxLayout.count (self)
```

从重新实现[QLayout.count](qlayout.html#count)（ ） 。

```
Direction QBoxLayout.direction (self)
```

[](qboxlayout.html#Direction-enum)

[返回框的方向。](qboxlayout.html#Direction-enum)[addWidget](qboxlayout.html#addWidget)（）和[addSpacing](qboxlayout.html#addSpacing)（ ）工作在这个方向，舒展舒展在这个方向。

**See also** [setDirection](qboxlayout.html#setDirection)（ ）[QBoxLayout.Direction](qboxlayout.html#Direction-enum)，[addWidget](qboxlayout.html#addWidget)（）和[addSpacing](qboxlayout.html#addSpacing)（ ） 。

```
Qt.Orientations QBoxLayout.expandingDirections (self)
```

[](index.htm)

[从重新实现](index.htm)[QLayoutItem.expandingDirections](qlayoutitem.html#expandingDirections)（ ） 。

```
bool QBoxLayout.hasHeightForWidth (self)
```

从重新实现[QLayoutItem.hasHeightForWidth](qlayoutitem.html#hasHeightForWidth)（ ） 。

```
int QBoxLayout.heightForWidth (self, int)
```

从重新实现[QLayoutItem.heightForWidth](qlayoutitem.html#heightForWidth)（ ） 。

```
QBoxLayout.insertItem (self, int index, QLayoutItem)
```

该_QLayoutItem_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

Inserts _item_在进入这个位置布局框_index_。如果_index_为负，该项目是在结尾处添加。

**See also** [addItem](qboxlayout.html#addItem)（ ）[insertWidget](qboxlayout.html#insertWidget)（ ）[insertLayout](qboxlayout.html#insertLayout)（ ）[insertStretch](qboxlayout.html#insertStretch)（）和[insertSpacing](qboxlayout.html#insertSpacing)（ ） 。

```
QBoxLayout.insertLayout (self, int index, QLayout layout, int stretch = 0)
```

该_layout_说法有它的所有权转移给Qt的。

Inserts _layout_在位置_index_，用拉伸系数_stretch_。如果_index_是负的，布局是在后面。

_layout_成为框布局的孩子。

**See also** [addLayout](qboxlayout.html#addLayout)（）和[insertItem](qboxlayout.html#insertItem)（ ） 。

```
QBoxLayout.insertSpacerItem (self, int index, QSpacerItem spacerItem)
```

该_spacerItem_说法有它的所有权转移给Qt的。

Inserts _spacerItem_在位置_index_，零最小尺寸和拉伸因子。如果_index_为负的空间在后面。

此功能被引入Qt的4.4 。

**See also** [addSpacerItem](qboxlayout.html#addSpacerItem)（ ）[insertStretch](qboxlayout.html#insertStretch)（）和[insertSpacing](qboxlayout.html#insertSpacing)（ ） 。

```
QBoxLayout.insertSpacing (self, int index, int size)
```

插入一个非伸缩性的空间（一[QSpacerItem](qspaceritem.html)）在位置_index_，大小为_size_。如果_index_为负的空间在后面。

框布局有默认边距和间距。此功能增加了额外的空间。

**See also** [addSpacing](qboxlayout.html#addSpacing)（ ）[insertItem](qboxlayout.html#insertItem)（）和[QSpacerItem](qspaceritem.html)。

```
QBoxLayout.insertStretch (self, int index, int stretch = 0)
```

插入一个伸缩空间（[QSpacerItem](qspaceritem.html)）在位置_index_，零最小尺寸和拉伸系数_stretch_。如果_index_为负的空间在后面。

**See also** [addStretch](qboxlayout.html#addStretch)（ ）[insertItem](qboxlayout.html#insertItem)（）和[QSpacerItem](qspaceritem.html)。

```
QBoxLayout.insertWidget (self, int index, QWidget widget, int stretch = 0, Qt.Alignment alignment = 0)
```

该_widget_说法有它的所有权转移给Qt的。

Inserts _widget_在位置_index_，用拉伸系数_stretch_和对齐_alignment_。如果_index_是否定的，则窗口部件被加在最后。

只有拉伸系数适用于[direction](qboxlayout.html#direction)的[QBoxLayout](qboxlayout.html)，并且是相对于另一个盒和小部件在这[QBoxLayout](qboxlayout.html)。小工具和箱子具有较高的拉伸因素变得更加。

如果拉伸系数为0，没有其他的[QBoxLayout](qboxlayout.html)已拉伸因子大于零，该空间是根据分布式[QWidget](qwidget.html)： sizePolicy是涉及到每个插件的（ ） 。

该路线是由指定的_alignment_。默认的对齐是0，这意味着该插件充满整个细胞。

**See also** [addWidget](qboxlayout.html#addWidget)（）和[insertItem](qboxlayout.html#insertItem)（ ） 。

```
QBoxLayout.invalidate (self)
```

从重新实现[QLayoutItem.invalidate](qlayoutitem.html#invalidate)（ ） 。

复位缓存的信息。

```
QLayoutItem QBoxLayout.itemAt (self, int)
```

[](qlayoutitem.html)

[从重新实现](qlayoutitem.html)[QLayout.itemAt](qlayout.html#itemAt)（ ） 。

```
QSize QBoxLayout.maximumSize (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QLayoutItem.maximumSize](qlayoutitem.html#maximumSize)（ ） 。

```
int QBoxLayout.minimumHeightForWidth (self, int)
```

从重新实现[QLayoutItem.minimumHeightForWidth](qlayoutitem.html#minimumHeightForWidth)（ ） 。

```
QSize QBoxLayout.minimumSize (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QLayoutItem.minimumSize](qlayoutitem.html#minimumSize)（ ） 。

```
QBoxLayout.setDirection (self, Direction)
```

设置此布局的方向_direction_。

**See also** [direction](qboxlayout.html#direction)（ ） 。

```
QBoxLayout.setGeometry (self, QRect)
```

从重新实现[QLayoutItem.setGeometry](qlayoutitem.html#setGeometry)（ ） 。

```
QBoxLayout.setSpacing (self, int spacing)
```

重新实现[QLayout.setSpacing](qlayout.html#spacing-prop)（ ） 。间距属性设置为_spacing_。

**See also** [QLayout.setSpacing](qlayout.html#spacing-prop)（）和[spacing](qboxlayout.html#spacing)（ ） 。

```
QBoxLayout.setStretch (self, int index, int stretch)
```

设置拉伸因子在位置_index_。至_stretch_。

此功能被引入Qt的4.5 。

**See also** [stretch](qboxlayout.html#stretch)（ ） 。

```
bool QBoxLayout.setStretchFactor (self, QWidget w, int stretch)
```

设置为拉伸因子_widget_至_stretch_并返回True ，如果_widget_在这种布局（不包括子布局）被发现，否则返回False 。

**See also** [setAlignment](qlayout.html#setAlignment)（ ） 。

```
bool QBoxLayout.setStretchFactor (self, QLayout l, int stretch)
```

这是一个重载函数。

设置为布局的拉伸因子_layout_至_stretch_并返回True ，如果_layout_在这种布局（不包括子布局）被发现，否则返回False 。

```
QSize QBoxLayout.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QLayoutItem.sizeHint](qlayoutitem.html#sizeHint)（ ） 。

```
int QBoxLayout.spacing (self)
```

重新实现[QLayout.spacing](qlayout.html#spacing-prop)（ ） 。如果spacing属性是有效的，则返回该值。否则，对于间距属性的值被计算并返回。由于在一个小部件的布局间距的风格有关，如果父母是一个小部件，它会查询的样式布局（水平或垂直）的间距。否则，父是一个布局，它会查询父布局的间距（ ） 。

**See also** [QLayout.spacing](qlayout.html#spacing-prop)（）和[setSpacing](qboxlayout.html#setSpacing)（ ） 。

```
int QBoxLayout.stretch (self, int index)
```

返回拉伸因子在位置_index_。

此功能被引入Qt的4.5 。

**See also** [setStretch](qboxlayout.html#setStretch)（ ） 。

```
QLayoutItem QBoxLayout.takeAt (self, int)
```

[

该_QLayoutItem_结果

](qlayoutitem.html)

[从重新实现](qlayoutitem.html)[QLayout.takeAt](qlayout.html#takeAt)（ ） 。