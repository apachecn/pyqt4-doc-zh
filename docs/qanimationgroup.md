# QAnimationGroup Class Reference

## [[QtCore](index.htm) module]

该QAnimationGroup类是动画组的抽象基类。[More...](#details)

继承[QAbstractAnimation](qabstractanimation.html)。

通过继承[QParallelAnimationGroup](qparallelanimationgroup.html)和[QSequentialAnimationGroup](qsequentialanimationgroup.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `addAnimation (self, QAbstractAnimation animation)`
*   `QAbstractAnimation animationAt (self, int index)`
*   `int animationCount (self)`
*   `clear (self)`
*   `bool event (self, QEvent event)`
*   `int indexOfAnimation (self, QAbstractAnimation animation)`
*   `insertAnimation (self, int index, QAbstractAnimation animation)`
*   `removeAnimation (self, QAbstractAnimation animation)`
*   `QAbstractAnimation takeAnimation (self, int index)`

* * *

## Detailed Description

该QAnimationGroup类是动画组的抽象基类。

动画组是一个容器的子类的动画（[QAbstractAnimation](qabstractanimation.html)） 。一组通常是负责管理[state](qabstractanimation.html#State-enum)它的动画，也就是说，它决定何时启动，停止，恢复和暂停它们。目前， Qt提供了两个这样的组：[QParallelAnimationGroup](qparallelanimationgroup.html)和[QSequentialAnimationGroup](qsequentialanimationgroup.html)。查一查他们的类的描述了解详情。

由于QAnimationGroup从继承[QAbstractAnimation](qabstractanimation.html)，你可以结合组和轻松构建复杂的动画图形。您可以查询[QAbstractAnimation](qabstractanimation.html)该组属于（使用[group()](qabstractanimation.html#group)功能）。

要启动一个顶级的动画组，您只需使用[start()](qabstractanimation.html#start)从功能[QAbstractAnimation](qabstractanimation.html)。由顶级的动画组，我们认为本身不包含在另一组一组。直接不支持启动子组，并可能导致意外的行为。

QAnimationGroup提供用于添加和检索的动画。除此之外，你可以通过调用remove （删除动画） ，并清除动画组通过调用[clear](qanimationgroup.html#clear)（ ） 。你可以通过听，保持变化组的动画轨迹[QEvent.ChildAdded](qevent.html#Type-enum)和[QEvent.ChildRemoved](qevent.html#Type-enum)事件。

QAnimationGroup需要它管理的动画的所有权，并确保当动画组将被删除，他们都将被删除。

* * *

## Method Documentation

```
QAnimationGroup.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QAnimationGroup](qanimationgroup.html)。_parent_被传递给[QObject](qobject.html)的构造。

```
QAnimationGroup.addAnimation (self, QAbstractAnimation animation)
```

该_animation_说法有它的所有权转移给Qt的。

添加_animation_这一组。这将调用insertAnimation与指数等于[animationCount](qanimationgroup.html#animationCount)（ ） 。

**Note:**该小组采用了动画的所有权。

**See also** [removeAnimation](qanimationgroup.html#removeAnimation)（ ） 。

```
QAbstractAnimation QAnimationGroup.animationAt (self, int index)
```

[](qabstractanimation.html)

[返回一个指针，指向在动画_index_在这一组。当你需要访问一个特定的动画，此功能非常有用。_index_是介于0和](qabstractanimation.html)[animationCount](qanimationgroup.html#animationCount)（ ） - 1 。

**See also** [animationCount](qanimationgroup.html#animationCount)（）和[indexOfAnimation](qanimationgroup.html#indexOfAnimation)（ ） 。

```
int QAnimationGroup.animationCount (self)
```

返回该组管理动画的数量。

**See also** [indexOfAnimation](qanimationgroup.html#indexOfAnimation)（ ）[addAnimation](qanimationgroup.html#addAnimation)（）和[animationAt](qanimationgroup.html#animationAt)（ ） 。

```
QAnimationGroup.clear (self)
```

删除，并删除所有的动画在这个动画组，和当前时间重置为0 。

**See also** [addAnimation](qanimationgroup.html#addAnimation)（）和[removeAnimation](qanimationgroup.html#removeAnimation)（ ） 。

```
bool QAnimationGroup.event (self, QEvent event)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
int QAnimationGroup.indexOfAnimation (self, QAbstractAnimation animation)
```

返回的索引_animation_。返回的索引可以传递给其他函数接受一个索引作为参数。

**See also** [insertAnimation](qanimationgroup.html#insertAnimation)（ ）[animationAt](qanimationgroup.html#animationAt)（）和[takeAnimation](qanimationgroup.html#takeAnimation)（ ） 。

```
QAnimationGroup.insertAnimation (self, int index, QAbstractAnimation animation)
```

该_animation_说法有它的所有权转移给Qt的。

Inserts _animation_这个动画组_index_。如果_index_为0的动画被插在开头。如果_index_ is [animationCount](qanimationgroup.html#animationCount)（） ，该动画被插入在末端。

**Note:**该小组采用了动画的所有权。

**See also** [takeAnimation](qanimationgroup.html#takeAnimation)（ ）[addAnimation](qanimationgroup.html#addAnimation)（ ）[indexOfAnimation](qanimationgroup.html#indexOfAnimation)（）和[removeAnimation](qanimationgroup.html#removeAnimation)（ ） 。

```
QAnimationGroup.removeAnimation (self, QAbstractAnimation animation)
```

该_animation_争论

移除_animation_从本组。所有权_animation_传送到呼叫者。

**See also** [takeAnimation](qanimationgroup.html#takeAnimation)（ ）[insertAnimation](qanimationgroup.html#insertAnimation)（）和[addAnimation](qanimationgroup.html#addAnimation)（ ） 。

```
QAbstractAnimation QAnimationGroup.takeAnimation (self, int index)
```

[

该_QAbstractAnimation_结果

返回在动画_index_从动画组中删除。

**Note:**动画的所有权转移给调用者。

](qabstractanimation.html)

[**See also**](qabstractanimation.html) [removeAnimation](qanimationgroup.html#removeAnimation)（ ）[addAnimation](qanimationgroup.html#addAnimation)（ ）[insertAnimation](qanimationgroup.html#insertAnimation)（）和[indexOfAnimation](qanimationgroup.html#indexOfAnimation)（ ） 。