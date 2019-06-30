# QSequentialAnimationGroup Class Reference

## [[QtCore](index.htm) module]

该QSequentialAnimationGroup类提供动画的顺序组。[More...](#details)

继承[QAnimationGroup](qanimationgroup.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `QPauseAnimation addPause (self, int msecs)`
*   `QAbstractAnimation currentAnimation (self)`
*   `int duration (self)`
*   `bool event (self, QEvent event)`
*   `QPauseAnimation insertPause (self, int index, int msecs)`
*   `updateCurrentTime (self, int)`
*   `updateDirection (self, QAbstractAnimation.Direction direction)`
*   `updateState (self, QAbstractAnimation.State newState, QAbstractAnimation.State oldState)`

### Qt Signals

*   `void currentAnimationChanged (QAbstractAnimation *)`

* * *

## Detailed Description

该QSequentialAnimationGroup类提供动画的顺序组。

QSequentialAnimationGroup是[QAnimationGroup](qanimationgroup.html)运行其动画顺序，也就是说，它启动一个动画陆续完成播放。动画的播放它们添加到组中的顺序（使用[addAnimation()](qanimationgroup.html#addAnimation) or [insertAnimation()](qanimationgroup.html#insertAnimation)） 。当其最后的动画已经完成了动画组完成。

在每一时刻至多有一个动画处于活动状态的组中，它是由返回[currentAnimation](qsequentialanimationgroup.html#currentAnimation-prop)（ ） 。一个空的组没有当前动画。

一个连续的动画组可以被视为任何其他动画，也就是说，它可以启动，停止，添加到其他组。您也可以拨打[addPause](qsequentialanimationgroup.html#addPause)（）或[insertPause](qsequentialanimationgroup.html#insertPause)（）来暂停添加到一个连续的动画组。

```
 QSequentialAnimationGroup *group = new QSequentialAnimationGroup;

 group->addAnimation(anim1);
 group->addAnimation(anim2);

 group->start();

```

在这个例子中，`anim1`和`anim2`是两个已经建立[QPropertyAnimation](qpropertyanimation.html)秒。

* * *

## Method Documentation

```
QSequentialAnimationGroup.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QSequentialAnimationGroup](qsequentialanimationgroup.html)。_parent_被传递给[QObject](qobject.html)的构造。

```
QPauseAnimation QSequentialAnimationGroup.addPause (self, int msecs)
```

[](qpauseanimation.html)

[增加了一个暂停_msecs_这个动画组。暂停被认为是一种特殊类型的动画，从而](qpauseanimation.html)[animationCount](qanimationgroup.html#animationCount)将增加1 。

**See also** [insertPause](qsequentialanimationgroup.html#insertPause)（）和[QAnimationGroup.addAnimation](qanimationgroup.html#addAnimation)（ ） 。

```
QAbstractAnimation QSequentialAnimationGroup.currentAnimation (self)
```

[

```
int QSequentialAnimationGroup.duration (self)
```

](qabstractanimation.html)

[从重新实现](qabstractanimation.html)[QAbstractAnimation.duration](qabstractanimation.html#duration-prop)（ ） 。

```
bool QSequentialAnimationGroup.event (self, QEvent event)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QPauseAnimation QSequentialAnimationGroup.insertPause (self, int index, int msecs)
```

[

插入的暂停_msecs_毫秒_index_在这个动画组。

](qpauseanimation.html)

[**See also**](qpauseanimation.html) [addPause](qsequentialanimationgroup.html#addPause)（）和[QAnimationGroup.insertAnimation](qanimationgroup.html#insertAnimation)（ ） 。

```
QSequentialAnimationGroup.updateCurrentTime (self, int)
```

从重新实现[QAbstractAnimation.updateCurrentTime](qabstractanimation.html#updateCurrentTime)（ ） 。

```
QSequentialAnimationGroup.updateDirection (self, QAbstractAnimation.Direction direction)
```

从重新实现[QAbstractAnimation.updateDirection](qabstractanimation.html#updateDirection)（ ） 。

```
QSequentialAnimationGroup.updateState (self, QAbstractAnimation.State newState, QAbstractAnimation.State oldState)
```

从重新实现[QAbstractAnimation.updateState](qabstractanimation.html#updateState)（ ） 。

* * *

## Qt Signal Documentation

```
void currentAnimationChanged (QAbstractAnimation *)
```

这是该信号的默认超载。

[QSequentialAnimationGroup](qsequentialanimationgroup.html)发出该信号时[currentAnimation](qsequentialanimationgroup.html#currentAnimation-prop)已经改变。_current_是当前的动画。

**See also** [currentAnimation](qsequentialanimationgroup.html#currentAnimation-prop)（ ） 。