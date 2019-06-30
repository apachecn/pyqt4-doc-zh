# QGraphicsLayout Class Reference

## [[QtGui](index.htm) module]

该QGraphicsLayout类提供了所有布局的基类的图形视图。[More...](#details)

继承[QGraphicsLayoutItem](qgraphicslayoutitem.html)。

通过继承[QGraphicsAnchorLayout](qgraphicsanchorlayout.html)，[QGraphicsGridLayout](qgraphicsgridlayout.html)和[QGraphicsLinearLayout](qgraphicslinearlayout.html)。

### Methods

*   `__init__ (self, QGraphicsLayoutItem parent = None)`
*   `activate (self)`
*   `addChildLayoutItem (self, QGraphicsLayoutItem layoutItem)`
*   `int count (self)`
*   `(float left, float top, float right, float bottom) getContentsMargins (self)`
*   `invalidate (self)`
*   `bool isActivated (self)`
*   `QGraphicsLayoutItem itemAt (self, int i)`
*   `removeAt (self, int index)`
*   `setContentsMargins (self, float left, float top, float right, float bottom)`
*   `updateGeometry (self)`
*   `widgetEvent (self, QEvent e)`

### Special Methods

*   `__len__ (self)`

* * *

## Detailed Description

该QGraphicsLayout类提供了所有布局的基类的图形视图。

QGraphicsLayout是定义一个虚拟的API，用于安排一个抽象类[QGraphicsWidget](qgraphicswidget.html)儿童和其他[QGraphicsLayoutItem](qgraphicslayoutitem.html)一个对象[QGraphicsWidget](qgraphicswidget.html)。[QGraphicsWidget](qgraphicswidget.html)通过分配责任到QGraphicsLayout[QGraphicsWidget.setLayout](qgraphicswidget.html#layout-prop)（ ） 。由于小部件的大小时，布局会自动排列窗口部件的孩子。 QGraphicsLayout继承[QGraphicsLayoutItem](qgraphicslayoutitem.html)，因此，它可以由任何布局，包括其自己的子类来管理。

### Writing a Custom Layout

您可以使用QGraphicsLayout为基础编写自己的自定义布局（例如，一个的FlowLayout ） ，但更常见的是使用它的子类而不是一个 - [QGraphicsLinearLayout](qgraphicslinearlayout.html) or [QGraphicsGridLayout](qgraphicsgridlayout.html)。当创建一个自定义布局，下面的函数必须重新实现一个最低限度：

| Function | Description |
| --- | --- |
| [QGraphicsLayoutItem.setGeometry](qgraphicslayoutitem.html#setGeometry)() | Notifies you when the geometry of the layout is set. You can store the geometry in your own layout class in a reimplementation of this function. |
| [QGraphicsLayoutItem.sizeHint](qgraphicslayoutitem.html#sizeHint)() | Returns the layout's size hints. |
| [QGraphicsLayout.count](qgraphicslayout.html#count)() | Returns the number of items in your layout. |
| [QGraphicsLayout.itemAt](qgraphicslayout.html#itemAt)() | Returns a pointer to an item in your layout. |
| [QGraphicsLayout.removeAt](qgraphicslayout.html#removeAt)() | Removes an item from your layout without destroying it. |

有关如何实现每个功能的详细信息，请参阅单独的函数文档。

每个布局定义了自己的API来安排组件和布局的项目。例如，一个网格布局，则需要一个行和可选的行和列跨度，对齐，间距和多列索引。线性布局，但是，需要一个单一的行或列的索引来定位它的项目。为网格布局，插入顺序不影响布局以任何方式，但对于一个线性布局，顺序是至关重要的。当写你自己的布局的子类，你可以自由选择最适合你的布局的API 。

对于新增项目布局到自定义布局， QGraphicsLayout提供了便利的功能[addChildLayoutItem](qgraphicslayout.html#addChildLayoutItem)（ ） 。该功能将自动重定父级的图形项目护理，如果需要的话。

### Activating the Layout

当布局的几何变化， QGraphicsLayout立即致电重新排列所有的管理项目[setGeometry](qgraphicslayoutitem.html#setGeometry)（ ）上的每个项目。此重排被称为_activating_的布局。

QGraphicsLayout更新它自己的几何形状，以匹配[contentsRect](qgraphicslayoutitem.html#contentsRect)（）的[QGraphicsLayoutItem](qgraphicslayoutitem.html)它是管理。因此，它会自动重新安排所有项目时，窗口小部件大小调整。 QGraphicsLayout缓存其所有的管理项目的大小，以避免调用[setGeometry](qgraphicslayoutitem.html#setGeometry)（ ）过于频繁。

**Note:**一个QGraphicsLayout将具有相同几何形状的[contentsRect](qgraphicslayoutitem.html#contentsRect)（）窗口小部件（未布局）它被分配给。

#### Activating the Layout Implicitly

该布局可以隐式地使用以下两种方式之一来激活：通过调用[activate](qgraphicslayout.html#activate)（ ）或致电[invalidate](qgraphicslayout.html#invalidate)（ ） 。调用[activate](qgraphicslayout.html#activate)（ ）立即启动布局。与此相反，调用[invalidate](qgraphicslayout.html#invalidate)（ ）被延迟，因为它一个职位[LayoutRequest](qevent.html#Type-enum)事件给管理部件。由于事件压缩，则[activate](qgraphicslayout.html#activate)（ ）只会被调用一次后，控制返回到事件循环。这被称为_invalidating_的布局。无效的布局也是任何缓存信息失效。此外，该[invalidate](qgraphicslayout.html#invalidate)（）函数是虚拟函数。所以，你可以通过重新实现该功能无效你自己的缓存中QGraphicsLayout的一个子类。

### Event Handling

QGraphicsLayout监听事件管理它通过虚拟的小工具[widgetEvent](qgraphicslayout.html#widgetEvent)（ ）事件处理程序。当布局被分配到一个小部件，输送到部件的所有事件首先被处理[widgetEvent](qgraphicslayout.html#widgetEvent)（ ） 。这使得布局要注意的诸如可见性的变化或布局方向的变化在部件上的任何有关的状态变化。

### Margin Handling

一个QGraphicsLayout的利润可以通过重新实现修改[setContentsMargins](qgraphicslayout.html#setContentsMargins)（）和[getContentsMargins](qgraphicslayout.html#getContentsMargins)（ ） 。

* * *

## Method Documentation

```
QGraphicsLayout.__init__ (self, QGraphicsLayoutItem parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

Contructs一个[QGraphicsLayout](qgraphicslayout.html)对象。

_parent_被传递给[QGraphicsLayoutItem](qgraphicslayoutitem.html)的构造函数和[QGraphicsLayoutItem](qgraphicslayoutitem.html)的isLayout参数设置为_true_。

If _parent_是[QGraphicsWidget](qgraphicswidget.html)的布局将被安装在该部件。 （请注意，在安装布局将删除旧的安装。 ）

```
QGraphicsLayout.activate (self)
```

激活的布局，导致在布局的所有项目要立即重新排列。此功能是基于调用[count](qgraphicslayout.html#count)（）和[itemAt](qgraphicslayout.html#itemAt)（ ） ，然后调用[setGeometry](qgraphicslayoutitem.html#setGeometry)（ ）顺序上的所有项目。当被激活时，该布局将其几何形状调整到它的父[contentsRect](qgraphicslayoutitem.html#contentsRect)（ ） 。家长就会失效任何自己的布局。

如果按顺序调用或递归，例如，通过在响应被调整的安排的项目之一，此功能不会做任何事。

注意，该布局可以自由地使用几何缓存来优化这个过程。为了有力地违反对这样的高速缓存，可以调用[invalidate](qgraphicslayout.html#invalidate)（ ）调用之前激活（ ） 。

**See also** [invalidate](qgraphicslayout.html#invalidate)（ ） 。

```
QGraphicsLayout.addChildLayoutItem (self, QGraphicsLayoutItem layoutItem)
```

该_layoutItem_说法有它的所有权转移给Qt的。

此功能提供了自定义布局一个方便的功能，并且将通过所有项目的布局和reparent他们的图形项目，最接近[QGraphicsWidget](qgraphicswidget.html)祖先的布局。

If _layoutItem_已经在不同的布局，将被从该布局中移除。

如果自定义布局需要特殊的行为，他们可以忽略使用此功能，并实现自己的行为。

此功能被引入Qt的4.6 。

**See also** [graphicsItem](qgraphicslayoutitem.html#graphicsItem)（ ） 。

```
int QGraphicsLayout.count (self)
```

这种方法是抽象的，应在任何子类中重新实现。

这个纯虚函数必须在子类中重新实现[QGraphicsLayout](qgraphicslayout.html)返回在布局中的项目数。

子类可以自由地决定如何存储的项目。

**See also** [itemAt](qgraphicslayout.html#itemAt)（）和[removeAt](qgraphicslayout.html#removeAt)（ ） 。

```
(float left, float top, float right, float bottom) QGraphicsLayout.getContentsMargins (self)
```

从重新实现[QGraphicsLayoutItem.getContentsMargins](qgraphicslayoutitem.html#getContentsMargins)（ ） 。

```
QGraphicsLayout.invalidate (self)
```

清除布局中的任何缓存的几何形状和尺寸提示信息，职位[LayoutRequest](qevent.html#Type-enum)事件到管理的父[QGraphicsLayoutItem](qgraphicslayoutitem.html)。

**See also** [activate](qgraphicslayout.html#activate)（）和[setGeometry](qgraphicslayoutitem.html#setGeometry)（ ） 。

```
bool QGraphicsLayout.isActivated (self)
```

返回True如果布局是当前被激活，否则返回False 。如果布局被激活，这意味着它是目前在重排它的产品（即，过程中的[activate](qgraphicslayout.html#activate)（ ）函数被调用，并且还没有恢复） 。

**See also** [activate](qgraphicslayout.html#activate)（）和[invalidate](qgraphicslayout.html#invalidate)（ ） 。

```
QGraphicsLayoutItem QGraphicsLayout.itemAt (self, int i)
```

[

这种方法是抽象的，应在任何子类中重新实现。

](qgraphicslayoutitem.html)

[这个纯虚函数必须在子类中重新实现](qgraphicslayoutitem.html)[QGraphicsLayout](qgraphicslayout.html)返回一个指针到了该项目的索引_i_。重新实现可以假设_i_是有效的（即，它尊重的值[count](qgraphicslayout.html#count)（））。再加上[count](qgraphicslayout.html#count)（），它是作为遍历所有项目在一个布局的一个手段。

子类可以自由地决定如何存储的项目，和视觉的安排不必通过这个功能来体现。

**See also** [count](qgraphicslayout.html#count)（）和[removeAt](qgraphicslayout.html#removeAt)（ ） 。

```
QGraphicsLayout.removeAt (self, int index)
```

这种方法是抽象的，应在任何子类中重新实现。

这个纯虚函数必须在子类中重新实现[QGraphicsLayout](qgraphicslayout.html)到删除的项_index_。重新实现可以假设_index_是有效的（即，它尊重的值[count](qgraphicslayout.html#count)（））。

实施必须确保[parentLayoutItem](qgraphicslayoutitem.html#parentLayoutItem)已删除的项目的（ ）并不指向这个布局，因为该项目被认为是从布局层次结构中移除。

如果布局是应用程序之间重复使用，我们建议布局中删除的项目，但图形视图框架并不依赖于这一点。

子类可以自由地决定如何存储的项目。

**See also** [itemAt](qgraphicslayout.html#itemAt)（）和[count](qgraphicslayout.html#count)（ ） 。

```
QGraphicsLayout.setContentsMargins (self, float left, float top, float right, float bottom)
```

设置的内容边距_left_，_top_，_right_和_bottom_。默认的内容利润率顶层布局风格依赖（通过查询pixelMetric的[QStyle.PM_LayoutLeftMargin](qstyle.html#PixelMetric-enum)，[QStyle.PM_LayoutTopMargin](qstyle.html#PixelMetric-enum)，[QStyle.PM_LayoutRightMargin](qstyle.html#PixelMetric-enum)和[QStyle.PM_LayoutBottomMargin](qstyle.html#PixelMetric-enum)） 。

对于sublayouts默认页边距为0 。

变更内容自动边距布局无效。

**See also** [invalidate](qgraphicslayout.html#invalidate)（ ） 。

```
QGraphicsLayout.updateGeometry (self)
```

从重新实现[QGraphicsLayoutItem.updateGeometry](qgraphicslayoutitem.html#updateGeometry)（ ） 。

```
QGraphicsLayout.widgetEvent (self, QEvent e)
```

这种虚拟事件处理程序接收的管理部件的所有事件。[QGraphicsLayout](qgraphicslayout.html)使用此事件处理程序以侦听布局相关的事件，如几何形状的变化，布局的变化或布局的方向变化。

_e_是一个指向该事件。

您可以重新实现此事件处理程序来跟踪自己的自定义布局类似事件。

**See also** [QGraphicsWidget.event](qgraphicswidget.html#event)（）和[QGraphicsItem.sceneEvent](qgraphicsitem.html#sceneEvent)（ ） 。

```
 QGraphicsLayout.__len__ (self)
```