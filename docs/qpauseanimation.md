# QPauseAnimation Class Reference

## [[QtCore](index.htm) module]

该QPauseAnimation类提供了一个停顿[QSequentialAnimationGroup](qsequentialanimationgroup.html)。[More...](#details)

继承[QAbstractAnimation](qabstractanimation.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `__init__ (self, int msecs, QObject parent = None)`
*   `int duration (self)`
*   `bool event (self, QEvent e)`
*   `setDuration (self, int msecs)`
*   `updateCurrentTime (self, int)`

* * *

## Detailed Description

该QPauseAnimation类提供了一个停顿[QSequentialAnimationGroup](qsequentialanimationgroup.html)。

如果您希望引进的动画之间的延迟[QSequentialAnimationGroup](qsequentialanimationgroup.html)，你可以插入一个QPauseAnimation 。这个类没有任何动画，但不[finish](qabstractanimation.html#finished)之前指定的毫秒数从它开始的时候已经过去了。你在构造函数中指定暂停的持续时间。它也可以直接与设置[setDuration](qpauseanimation.html#duration-prop)（ ） 。

这是没有必要给自己建造一个QPauseAnimation 。[QSequentialAnimationGroup](qsequentialanimationgroup.html)提供方便的功能[addPause()](qsequentialanimationgroup.html#addPause)和[insertPause()](qsequentialanimationgroup.html#insertPause)。这些函数简单地采取毫秒的暂停持续的数量。

* * *

## Method Documentation

```
QPauseAnimation.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QPauseAnimation](qpauseanimation.html)。_parent_被传递给[QObject](qobject.html)的构造。默认的持续时间为0 。

```
QPauseAnimation.__init__ (self, int msecs, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QPauseAnimation](qpauseanimation.html)。_msecs_是暂停的持续时间。_parent_被传递给[QObject](qobject.html)的构造。

```
int QPauseAnimation.duration (self)
```

```
bool QPauseAnimation.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QPauseAnimation.setDuration (self, int msecs)
```

```
QPauseAnimation.updateCurrentTime (self, int)
```

从重新实现[QAbstractAnimation.updateCurrentTime](qabstractanimation.html#updateCurrentTime)（ ） 。