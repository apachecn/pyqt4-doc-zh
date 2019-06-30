# QGraphicsItemGroup Class Reference

## [[QtGui](index.htm) module]

该QGraphicsItemGroup类提供一个容器，把一组项目作为一个单独的项目。[More...](#details)

继承[QGraphicsItem](qgraphicsitem.html)。

### Methods

*   `__init__ (self, QGraphicsItem parent = None, QGraphicsScene scene = None)`
*   `addToGroup (self, QGraphicsItem item)`
*   `QRectF boundingRect (self)`
*   `bool isObscuredBy (self, QGraphicsItem item)`
*   `QPainterPath opaqueArea (self)`
*   `paint (self, QPainter painter, QStyleOptionGraphicsItem option, QWidget widget = None)`
*   `removeFromGroup (self, QGraphicsItem item)`
*   `int type (self)`

* * *

## Detailed Description

该QGraphicsItemGroup类提供一个容器，把一组项目作为一个单独的项目。

一个QGraphicsItemGroup是一种特殊类型的复合项目，对待自身及其所有子作为一个项目（即，所有的事件和几何形状为所有儿童都合并在一起） 。这是常见的使用项目组演示工具，当用户希望将若干较小的项目变成一个大项目，以简化移动和项目的复制。

如果你想要的是存储在其它项目的项目，你可以使用任何[QGraphicsItem](qgraphicsitem.html)直接通过传递一个合适的父[setParentItem](qgraphicsitem.html#setParentItem)（ ） 。

该[boundingRect](qgraphicsitemgroup.html#boundingRect)QGraphicsItemGroup （）函数将返回所有项目的项目组中的边框。 QGraphicsItemGroup忽略[ItemIgnoresTransformations](qgraphicsitem.html#GraphicsItemFlag-enum)旗上的孩子（即，相对于该组项目的几何形状，孩子们被视为好像它们是可转换的） 。

有两种方法来构造一个项目组。最简单和最常用的方法是将项目（例如，所有选定的项目）的列表传递给[QGraphicsScene.createItemGroup](qgraphicsscene.html#createItemGroup)（ ） ，它返回一个新的QGraphicsItemGroup项目。另一种方法是手动构造一个QGraphicsItemGroup项目，将其添加到场景调用[QGraphicsScene.addItem](qgraphicsscene.html#addItem)（ ） ，然后通过调用将项目添加到该组手动，一次一个[addToGroup](qgraphicsitemgroup.html#addToGroup)（ ） 。拆除（ “取消组合” ）的项目组，您可以调用[QGraphicsScene.destroyItemGroup](qgraphicsscene.html#destroyItemGroup)（ ） ，或者你也可以手动调用从组中删除所有项目[removeFromGroup](qgraphicsitemgroup.html#removeFromGroup)（ ） 。

```
 // Group all selected items together
 QGraphicsItemGroup *group = scene->createItemGroup(scene->selecteditems());

 // Destroy the group, and delete the group item
 scene->destroyItemGroup(group);

```

添加和删除项目的操作保持了​​项目“场景的相对位置和变换，而不是调用[setParentItem](qgraphicsitem.html#setParentItem)（ ） ，其中只有子项的父，相对位置和改造被保留。

该addtoGroup （ ）函数reparents目标项目这个项目组，保持项目的位置和改造完好相对于场景。视觉上，这意味着项目通过加入[addToGroup](qgraphicsitemgroup.html#addToGroup)（ ）将保持完全不变，这个操作的结果，而不管该项目或该集团的当前位置或改造的，虽然该项目的位置和矩阵都可能发生变化。

该[removeFromGroup](qgraphicsitemgroup.html#removeFromGroup)（ ）函数有类似的语义[setParentItem](qgraphicsitem.html#setParentItem)（）;它reparents的项目到项目组的父项。与[addToGroup](qgraphicsitemgroup.html#addToGroup)（ ） ，该项目的场景相对位置和转型保持不变。

* * *

## Method Documentation

```
QGraphicsItemGroup.__init__ (self, QGraphicsItem parent = None, QGraphicsScene scene = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

该_scene_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QGraphicsItemGroup](qgraphicsitemgroup.html)。_parent_被传递给[QGraphicsItem](qgraphicsitem.html)的构造。

**See also** [QGraphicsScene.addItem](qgraphicsscene.html#addItem)（ ） 。

```
QGraphicsItemGroup.addToGroup (self, QGraphicsItem item)
```

该_item_说法有它的所有权转移给Qt的。

将给定_item_和项目的子项到这个项目组。该项目及其子项将被重设父到这个组，但它的位置和相对于场景变换将保持不变。

**See also** [removeFromGroup](qgraphicsitemgroup.html#removeFromGroup)（）和[QGraphicsScene.createItemGroup](qgraphicsscene.html#createItemGroup)（ ） 。

```
QRectF QGraphicsItemGroup.boundingRect (self)
```

[](qrectf.html)

[从重新实现](qrectf.html)[QGraphicsItem.boundingRect](qgraphicsitem.html#boundingRect)（ ） 。

返回该组项目的边界矩形，它的所有子项。

```
bool QGraphicsItemGroup.isObscuredBy (self, QGraphicsItem item)
```

从重新实现[QGraphicsItem.isObscuredBy](qgraphicsitem.html#isObscuredBy)（ ） 。

```
QPainterPath QGraphicsItemGroup.opaqueArea (self)
```

[](qpainterpath.html)

[从重新实现](qpainterpath.html)[QGraphicsItem.opaqueArea](qgraphicsitem.html#opaqueArea)（ ） 。

```
QGraphicsItemGroup.paint (self, QPainter painter, QStyleOptionGraphicsItem option, QWidget widget = None)
```

从重新实现[QGraphicsItem.paint](qgraphicsitem.html#paint)（ ） 。

```
QGraphicsItemGroup.removeFromGroup (self, QGraphicsItem item)
```

删除指定的_item_从本组。该项目将被重设父到这个组的父项，或为0，如果该组没有父。它的位置和相对于场景变换将保持不变。

**See also** [addToGroup](qgraphicsitemgroup.html#addToGroup)（）和[QGraphicsScene.destroyItemGroup](qgraphicsscene.html#destroyItemGroup)（ ） 。

```
int QGraphicsItemGroup.type (self)
```

从重新实现[QGraphicsItem.type](qgraphicsitem.html#type)（ ） 。