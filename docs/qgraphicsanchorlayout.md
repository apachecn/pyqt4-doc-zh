# QGraphicsAnchorLayout Class Reference

## [[QtGui](index.htm) module]

该QGraphicsAnchorLayout类提供了一个布局，其中一个可以停泊的部件一起在图形视图。[More...](#details)

继承[QGraphicsLayout](qgraphicslayout.html)。

### Methods

*   `__init__ (self, QGraphicsLayoutItem parent = None)`
*   `QGraphicsAnchor addAnchor (self, QGraphicsLayoutItem firstItem, Qt.AnchorPoint firstEdge, QGraphicsLayoutItem secondItem, Qt.AnchorPoint secondEdge)`
*   `addAnchors (self, QGraphicsLayoutItem firstItem, QGraphicsLayoutItem secondItem, Qt.Orientations orientations = Qt.Horizontal|Qt.Vertical)`
*   `addCornerAnchors (self, QGraphicsLayoutItem firstItem, Qt.Corner firstCorner, QGraphicsLayoutItem secondItem, Qt.Corner secondCorner)`
*   `QGraphicsAnchor anchor (self, QGraphicsLayoutItem firstItem, Qt.AnchorPoint firstEdge, QGraphicsLayoutItem secondItem, Qt.AnchorPoint secondEdge)`
*   `int count (self)`
*   `float horizontalSpacing (self)`
*   `invalidate (self)`
*   `QGraphicsLayoutItem itemAt (self, int index)`
*   `removeAt (self, int index)`
*   `setGeometry (self, QRectF rect)`
*   `setHorizontalSpacing (self, float spacing)`
*   `setSpacing (self, float spacing)`
*   `setVerticalSpacing (self, float spacing)`
*   `QSizeF sizeHint (self, Qt.SizeHint which, QSizeF constraint = QSizeF())`
*   `float verticalSpacing (self)`

* * *

## Detailed Description

该QGraphicsAnchorLayout类提供了一个布局，其中一个可以停泊的部件一起在图形视图。

锚布局允许开发人员指定的部件应如何放置彼此相对，并且布局本身。本说明书是由通过添加锚的布局通过调用[addAnchor](qgraphicsanchorlayout.html#addAnchor)（ ）[addAnchors](qgraphicsanchorlayout.html#addAnchors)（）或[addCornerAnchors](qgraphicsanchorlayout.html#addCornerAnchors)（ ） 。

在布局中现有的锚可以与被访问[anchor](qgraphicsanchorlayout.html#anchor)（）函数。被锚定项目自动添加到布局，如果项目被移除，所有的锚将被自动删除。

![Using an anchor layout to align simple colored widgets.](../img/simpleanchorlayout-example.png)

锚总是成立的项目，其中的“中心”也被认为是边缘的边缘之间。请看下面的例子：

```
 layout->addAnchor(b, [Qt](qt.html).AnchorLeft, a, [Qt](qt.html).AnchorRight);
 layout->addAnchor(b, [Qt](qt.html).AnchorTop, a, [Qt](qt.html).AnchorBottom);

```

这里，项目的右边缘`a`被锚定到项目的左边缘`b`和产品的底部边缘`a`被锚定到产品的上边缘`b`，其结果是产品`b`将对角线放置在右边和下边项目`b`。

该[addCornerAnchors](qgraphicsanchorlayout.html#addCornerAnchors)（）函数提供固定的两个小部件的边角比两个单独的调用的一个简单的方法[addAnchor](qgraphicsanchorlayout.html#addAnchor)（ ）显示在上面的代码中。在这里，我们看到了一个小工具，可以锚定到封闭布局的左上角：

```
 layout->addCornerAnchors(a, [Qt](qt.html).TopLeftCorner, layout, [Qt](qt.html).TopLeftCorner);

```

在锚定器被用来匹配部件的宽度或高度的情况下，可以很方便地使用[addAnchors](qgraphicsanchorlayout.html#addAnchors)（）函数。与其它功能用于指定锚，它也可以用于固定一个部件的布局。

### Size Hints and Size Policies in an Anchor Layout

QGraphicsAnchorLayout尊重每个项目的大小提示和大小政策。请注意，有一些特性[QSizePolicy](qsizepolicy.html)是[not respected](index.htm)。

### Spacing within an Anchor Layout

布局可以分发的项目之间的一些空间。如果间距没有被明确指定，空间的实际金额通常是0 。

然而，如果在第一边缘是_opposite_第二边缘（例如，第一部件的右边缘被固定到第二部件的左边缘）的，锚的尺寸将会从样式通过查询一个像素度量：[PM_LayoutHorizontalSpacing](qstyle.html#PixelMetric-enum)水平和锚[PM_LayoutVerticalSpacing](qstyle.html#PixelMetric-enum)垂直锚。

如果该间距为负，则物品将重叠到某种程度。

### Known issues

有迹象表明， QGraphicsAnchorLayout目前不支持某些功能。这可能会改变未来，因此要避免使用这些功能，如果你想避免任何行为将来回归：

*   Stretch factors are not respected.
*   [QSizePolicy.ExpandFlag](qsizepolicy.html#PolicyFlag-enum) is not respected.
*   Height for width is not respected.

* * *

## Method Documentation

```
QGraphicsAnchorLayout.__init__ (self, QGraphicsLayoutItem parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QGraphicsAnchorLayout](qgraphicsanchorlayout.html)实例。_parent_被传递给[QGraphicsLayout](qgraphicslayout.html)的构造。

```
QGraphicsAnchor QGraphicsAnchorLayout.addAnchor (self, QGraphicsLayoutItem firstItem, Qt.AnchorPoint firstEdge, QGraphicsLayoutItem secondItem, Qt.AnchorPoint secondEdge)
```

[

该_firstItem_说法有它的所有权转移给Qt的。

该_secondItem_说法有它的所有权转移给Qt的。

创建边缘之间的锚定_firstEdge_项目_firstItem_和边缘_secondEdge_项目_secondItem_。锚的间距是从式拾取。布局边缘和产品边缘之间的锚将具有为0的大小。如果已经有边缘之间的锚，在新的锚定将取代旧的。

](qgraphicsanchor.html)

[_firstItem_和_secondItem_会自动添加到布局，如果他们不是布局的一部分。这意味着](qgraphicsanchor.html)[count](qgraphicsanchorlayout.html#count)（ ）可以通过最多2增加。

间隔的锚定会得到依赖于锚定的类型。例如，锚从一个项目的右边缘到另一个（或反之亦然）的左边缘将使用默认的水平间距。同样的行为适用于从下到上的锚， （但他们会使用默认的垂直间距） 。对于所有其它的组合锚，间距为0。所有的锚定功能将遵循这个规则。

的间隔也可以通过使用手动设置[QGraphicsAnchor.setSpacing](qgraphicsanchor.html#spacing-prop)（）方法。

调用此函数，其中_firstItem_ or _secondItem_正在布局的祖先未定义的行为。

**See also** [addAnchors](qgraphicsanchorlayout.html#addAnchors)（）和[addCornerAnchors](qgraphicsanchorlayout.html#addCornerAnchors)（ ） 。

```
QGraphicsAnchorLayout.addAnchors (self, QGraphicsLayoutItem firstItem, QGraphicsLayoutItem secondItem, Qt.Orientations orientations = Qt.Horizontal|Qt.Vertical)
```

该_firstItem_说法有它的所有权转移给Qt的。

该_secondItem_说法有它的所有权转移给Qt的。

锚定件的两个或四个边_firstItem_同的对应边缘_secondItem_，使_firstItem_具有相同的尺寸_secondItem_在所指定的尺寸_orientations_。

例如，下面的例子锚的两个项目的左，右边缘，以配合它们的宽度：

```
 layout->addAnchor(b, Qt.AnchorLeft, c, Qt.AnchorLeft);
 layout->addAnchor(b, Qt.AnchorRight, c, Qt.AnchorRight);

```

这也可以使用下面的代码行来实现：

```
 layout->addAnchors(b, c, [Qt](qt.html).Horizontal);

```

**See also** [addAnchor](qgraphicsanchorlayout.html#addAnchor)（）和[addCornerAnchors](qgraphicsanchorlayout.html#addCornerAnchors)（ ） 。

```
QGraphicsAnchorLayout.addCornerAnchors (self, QGraphicsLayoutItem firstItem, Qt.Corner firstCorner, QGraphicsLayoutItem secondItem, Qt.Corner secondCorner)
```

该_firstItem_说法有它的所有权转移给Qt的。

该_secondItem_说法有它的所有权转移给Qt的。

建立在两个锚_firstItem_和_secondItem_由指定的边角，_firstCorner_和_secondCorner_其中之一是对水平方向的边缘，另一个为垂直方向的边缘。

这是一个方便的功能，由于锚定角可以表示为锚定两条边。例如：

```
 layout->addAnchor(a, Qt.AnchorTop, layout, Qt.AnchorTop);
 layout->addAnchor(a, Qt.AnchorLeft, layout, Qt.AnchorLeft);

```

这也可以达到与下面一行代码：

```
 layout->addCornerAnchors(a, [Qt](qt.html).TopLeftCorner, layout, [Qt](qt.html).TopLeftCorner);

```

如果已经有一个边缘对之间的锚定，它将由锚被替换，该函数指定。

_firstItem_和_secondItem_会自动添加到布局，如果他们不是布局的一部分。这意味着[count](qgraphicsanchorlayout.html#count)（ ）可以通过最多2增加。

**See also** [addAnchor](qgraphicsanchorlayout.html#addAnchor)（）和[addAnchors](qgraphicsanchorlayout.html#addAnchors)（ ） 。

```
QGraphicsAnchor QGraphicsAnchorLayout.anchor (self, QGraphicsLayoutItem firstItem, Qt.AnchorPoint firstEdge, QGraphicsLayoutItem secondItem, Qt.AnchorPoint secondEdge)
```

[

返回由所定义的锚点之间的锚_firstItem_和_firstEdge_和_secondItem_和_secondEdge_。如果不存在这样的锚，该函数将返回0。

```
int QGraphicsAnchorLayout.count (self)
```

](qgraphicsanchor.html)

[从重新实现](qgraphicsanchor.html)[QGraphicsLayout.count](qgraphicslayout.html#count)（ ） 。

```
float QGraphicsAnchorLayout.horizontalSpacing (self)
```

返回默认的水平间距为锚的布局。

**See also** [verticalSpacing](qgraphicsanchorlayout.html#verticalSpacing)（）和[setHorizontalSpacing](qgraphicsanchorlayout.html#setHorizontalSpacing)（ ） 。

```
QGraphicsAnchorLayout.invalidate (self)
```

从重新实现[QGraphicsLayout.invalidate](qgraphicslayout.html#invalidate)（ ） 。

```
QGraphicsLayoutItem QGraphicsAnchorLayout.itemAt (self, int index)
```

[](qgraphicslayoutitem.html)

[从重新实现](qgraphicslayoutitem.html)[QGraphicsLayout.itemAt](qgraphicslayout.html#itemAt)（ ） 。

```
QGraphicsAnchorLayout.removeAt (self, int index)
```

从重新实现[QGraphicsLayout.removeAt](qgraphicslayout.html#removeAt)（ ） 。

删除的项目布局_index_不破坏它。该项目的所有权转移给调用者。

删除一个项目也将删除与此日志关联的锚。

**See also** [itemAt](qgraphicsanchorlayout.html#itemAt)（）和[count](qgraphicsanchorlayout.html#count)（ ） 。

```
QGraphicsAnchorLayout.setGeometry (self, QRectF rect)
```

从重新实现[QGraphicsLayoutItem.setGeometry](qgraphicslayoutitem.html#setGeometry)（ ） 。

```
QGraphicsAnchorLayout.setHorizontalSpacing (self, float spacing)
```

设置默认的水平间距为锚布局_spacing_。

**See also** [horizontalSpacing](qgraphicsanchorlayout.html#horizontalSpacing)（ ）[setVerticalSpacing](qgraphicsanchorlayout.html#setVerticalSpacing)（）和[setSpacing](qgraphicsanchorlayout.html#setSpacing)（ ） 。

```
QGraphicsAnchorLayout.setSpacing (self, float spacing)
```

设置默认的水平和用于锚定布局的默认垂直间距_spacing_。

如果一个项目是挂靠，没有与相关的锚间距，它会使用默认的间距。

[QGraphicsAnchorLayout](qgraphicsanchorlayout.html)不支持负的间距。设置一个负值将取消设置之前的间距，使布局使用由当前控件的样式所提供的空间。

**See also** [setHorizontalSpacing](qgraphicsanchorlayout.html#setHorizontalSpacing)（）和[setVerticalSpacing](qgraphicsanchorlayout.html#setVerticalSpacing)（ ） 。

```
QGraphicsAnchorLayout.setVerticalSpacing (self, float spacing)
```

设置为锚布局为默认的垂直间距_spacing_。

**See also** [verticalSpacing](qgraphicsanchorlayout.html#verticalSpacing)（ ）[setHorizontalSpacing](qgraphicsanchorlayout.html#setHorizontalSpacing)（）和[setSpacing](qgraphicsanchorlayout.html#setSpacing)（ ） 。

```
QSizeF QGraphicsAnchorLayout.sizeHint (self, Qt.SizeHint which, QSizeF constraint = QSizeF())
```

[](qsizef.html)

[从重新实现](qsizef.html)[QGraphicsLayoutItem.sizeHint](qgraphicslayoutitem.html#sizeHint)（ ） 。

```
float QGraphicsAnchorLayout.verticalSpacing (self)
```

返回锚布局默认的垂直间距。

**See also** [horizontalSpacing](qgraphicsanchorlayout.html#horizontalSpacing)（）和[setVerticalSpacing](qgraphicsanchorlayout.html#setVerticalSpacing)（ ） 。