# QParallelAnimationGroup Class Reference

## [[QtCore](index.htm) module]

该QParallelAnimationGroup类提供动画的平行组。[More...](#details)

继承[QAnimationGroup](qanimationgroup.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `int duration (self)`
*   `bool event (self, QEvent event)`
*   `updateCurrentTime (self, int currentTime)`
*   `updateDirection (self, QAbstractAnimation.Direction direction)`
*   `updateState (self, QAbstractAnimation.State newState, QAbstractAnimation.State oldState)`

* * *

## Detailed Description

该QParallelAnimationGroup类提供动画的平行组。

QParallelAnimationGroup - 一个[container for animations](qanimationgroup.html) - 启动其所有的动画时，它是[started](qabstractanimation.html#start)本身，即运行在平行的所有动画。当最长的持久的动画已经完成了动画组完成。

你可以把QParallelAnimation其他任何[QAbstractAnimation](qabstractanimation.html)，例如，暂停，恢复，或将其添加到其他动画组。

```
 QParallelAnimationGroup *group = new QParallelAnimationGroup;
 group->addAnimation(anim1);
 group->addAnimation(anim2);

 group->start();

```

在这个例子中，`anim1`和`anim2`两个[QPropertyAnimation](qpropertyanimation.html)s表示已经建立起来。

* * *

## Method Documentation

```
QParallelAnimationGroup.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QParallelAnimationGroup](qparallelanimationgroup.html)。_parent_被传递给[QObject](qobject.html)的构造。

```
int QParallelAnimationGroup.duration (self)
```

从重新实现[QAbstractAnimation.duration](qabstractanimation.html#duration-prop)（ ） 。

```
bool QParallelAnimationGroup.event (self, QEvent event)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QParallelAnimationGroup.updateCurrentTime (self, int currentTime)
```

从重新实现[QAbstractAnimation.updateCurrentTime](qabstractanimation.html#updateCurrentTime)（ ） 。

```
QParallelAnimationGroup.updateDirection (self, QAbstractAnimation.Direction direction)
```

从重新实现[QAbstractAnimation.updateDirection](qabstractanimation.html#updateDirection)（ ） 。

```
QParallelAnimationGroup.updateState (self, QAbstractAnimation.State newState, QAbstractAnimation.State oldState)
```

从重新实现[QAbstractAnimation.updateState](qabstractanimation.html#updateState)（ ） 。