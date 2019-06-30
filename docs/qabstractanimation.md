# QAbstractAnimation Class Reference

## [[QtCore](index.htm) module]

该QAbstractAnimation类是所有动画的基础。[More...](#details)

继承[QObject](qobject.html)。

通过继承[QAnimationGroup](qanimationgroup.html)，[QPauseAnimation](qpauseanimation.html)和[QVariantAnimation](qvariantanimation.html)。

### Types

*   `enum DeletionPolicy { KeepWhenStopped, DeleteWhenStopped }`
*   `enum Direction { Forward, Backward }`
*   `enum State { Stopped, Paused, Running }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `int currentLoop (self)`
*   `int currentLoopTime (self)`
*   `int currentTime (self)`
*   `Direction direction (self)`
*   `int duration (self)`
*   `bool event (self, QEvent event)`
*   `QAnimationGroup group (self)`
*   `int loopCount (self)`
*   `pause (self)`
*   `resume (self)`
*   `setCurrentTime (self, int msecs)`
*   `setDirection (self, Direction direction)`
*   `setLoopCount (self, int loopCount)`
*   `setPaused (self, bool)`
*   `start (self, DeletionPolicy policy = QAbstractAnimation.KeepWhenStopped)`
*   `State state (self)`
*   `stop (self)`
*   `int totalDuration (self)`
*   `updateCurrentTime (self, int currentTime)`
*   `updateDirection (self, Direction direction)`
*   `updateState (self, State newState, State oldState)`

### Qt Signals

*   `void currentLoopChanged (int)`
*   `void directionChanged (QAbstractAnimation::Direction)`
*   `void finished ()`
*   `void stateChanged (QAbstractAnimation::State,QAbstractAnimation::State)`

* * *

## Detailed Description

该QAbstractAnimation类是所有动画的基础。

这个类定义了所有的动画共享的功能的功能。通过继承这个类，您可以创建自定义动画，插入的动画框架的其馀部分。

动画的进度是由它的当前时间（给定[currentLoopTime](qabstractanimation.html#currentLoopTime)（）），这是从动画开始以毫秒为单位（0）到它的端部（[duration](qabstractanimation.html#duration-prop)（））。动画运行时的值会自动更新。它也可以直接与设置[setCurrentTime](qabstractanimation.html#currentTime-prop)（ ） 。

在任何时候动画是在三种状态之一：[Running](qabstractanimation.html#State-enum)，[Stopped](qabstractanimation.html#State-enum)或[Paused](qabstractanimation.html#State-enum) - 被定义[State](qabstractanimation.html#State-enum)枚举。目前的状态可以通过调用改变[start](qabstractanimation.html#start)（ ）[stop](qabstractanimation.html#stop)（ ）[pause](qabstractanimation.html#pause)（） ，或[resume](qabstractanimation.html#resume)（ ） 。动画将重新设定其[current time](qabstractanimation.html#currentTime-prop)当它被启动。如果暂停，它会继续恢复时相同的当前时间。当动画停止时，它不能被恢复，但将保持其当前时间（直到再次启动）。 QAbstractAnimation会发出[stateChanged](qabstractanimation.html#stateChanged)（ ）每当它的状态的变化。

动画可以循环通过设置任意数量的倍[loopCount](qabstractanimation.html#loopCount-prop)属性。当动画的当前时间达到[duration](qabstractanimation.html#duration-prop)（ ） ，它会重置当前的时间，并保持运行。为1，循环次数（默认值）表示该动画将运行一次。需要注意的是-1的持续时间意味着动画将运行到停止，当前的时间将增加下去。当当前时间等于[duration](qabstractanimation.html#duration-prop)（）和动画是在其最后循环中，[Stopped](qabstractanimation.html#State-enum)进入状态，而[finished](qabstractanimation.html#finished)（）信号被发射。

QAbstractAnimation提供由子类用于跟踪动画的进度纯虚函数：[duration](qabstractanimation.html#duration-prop)（）和[updateCurrentTime](qabstractanimation.html#updateCurrentTime)（ ） 。该[duration](qabstractanimation.html#duration-prop)（ ）函数可以报告一个持续时间为动画（如上所述） 。动画框架调用[updateCurrentTime](qabstractanimation.html#updateCurrentTime)（ ）时，当前时间已更改。通过重新实现此功能，您可以跟踪动画进度。请注意，无论呼叫也不调用该函数的数量之间的间隔被定义，虽然，它通常是每秒60更新。

通过重新实现[updateState](qabstractanimation.html#updateState)（ ） ，你可以跟踪动画的状态发生变化，这是不是由时间驱动的动画特别有用。

* * *

## Type Documentation

```
QAbstractAnimation.DeletionPolicy
```

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractAnimation.KeepWhenStopped` | `0` | 停止时的动画效果将不会被删除。 |
| `QAbstractAnimation.DeleteWhenStopped` | `1` | 停止时，动画将被自动删除。 |

```
QAbstractAnimation.Direction
```

这个枚举变量描述了动画的方向时，[Running](qabstractanimation.html#State-enum)状态。

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractAnimation.Forward` | `0` | 随时间的增加动画的当前时间（即从0到接近尾声/时间移动） 。 |
| `QAbstractAnimation.Backward` | `1` | 随着时间（即从底/持续时间和对0移动）动画的当前时间减少。 |

**See also** [direction](qabstractanimation.html#direction-prop)。

```
QAbstractAnimation.State
```

这个枚举变量描述了动画的状态。

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractAnimation.Stopped` | `0` | 动画没有运行。这是初始状态[QAbstractAnimation](qabstractanimation.html)，和国家[QAbstractAnimation](qabstractanimation.html)重新进入时完成。当前时间保持不变，直至[setCurrentTime](qabstractanimation.html#currentTime-prop)（）被调用，或动画是通过调用启动[start](qabstractanimation.html#start)（ ） 。 |
| `QAbstractAnimation.Paused` | `1` | 动画暂停（即暂停） 。调用[resume](qabstractanimation.html#resume)（ ）将恢复动画活动。 |
| `QAbstractAnimation.Running` | `2` | 在动画运行。而控制是在事件循环，[QAbstractAnimation](qabstractanimation.html)将定期更新其当前的时间，调用[updateCurrentTime](qabstractanimation.html#updateCurrentTime)（ ）在适当的时候。 |

**See also** [state](qabstractanimation.html#state-prop)（）和[stateChanged](qabstractanimation.html#stateChanged)（ ） 。

* * *

## Method Documentation

```
QAbstractAnimation.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构建[QAbstractAnimation](qabstractanimation.html)基类和通行证_parent_至[QObject](qobject.html)的构造。

**See also** [QVariantAnimation](qvariantanimation.html)和[QAnimationGroup](qanimationgroup.html)。

```
int QAbstractAnimation.currentLoop (self)
```

```
int QAbstractAnimation.currentLoopTime (self)
```

返回当前循环内的当前时间。它可以从0到[duration](qabstractanimation.html#duration-prop)（ ） 。

**See also** [duration](qabstractanimation.html#duration-prop)（）和[currentTime](qabstractanimation.html#currentTime-prop)。

```
int QAbstractAnimation.currentTime (self)
```

```
Direction QAbstractAnimation.direction (self)
```

[

```
int QAbstractAnimation.duration (self)
```

这种方法是抽象的，应在任何子类中重新实现。

```
bool QAbstractAnimation.event (self, QEvent event)
```

](qabstractanimation.html#Direction-enum)

[从重新实现](qabstractanimation.html#Direction-enum)[QObject.event](qobject.html#event)（ ） 。

```
QAnimationGroup QAbstractAnimation.group (self)
```

[](qanimationgroup.html)

[如果这个动画的一部分](qanimationgroup.html)[QAnimationGroup](qanimationgroup.html)，这个函数返回一个指针到组，否则返回0 。

**See also** [QAnimationGroup.addAnimation](qanimationgroup.html#addAnimation)（ ） 。

```
int QAbstractAnimation.loopCount (self)
```

```
QAbstractAnimation.pause (self)
```

这种方法也是一个Qt槽与C + +的签名`void pause()`。

暂停动画。当动画暂停时，[state](qabstractanimation.html#state-prop)（）返回暂停。价值[currentTime](qabstractanimation.html#currentTime-prop)将保持不变，直到[resume](qabstractanimation.html#resume)（）或[start](qabstractanimation.html#start)（）被调用。如果你想从当前时间继续，请致电[resume](qabstractanimation.html#resume)（ ） 。

**See also** [start](qabstractanimation.html#start)（ ）[state](qabstractanimation.html#state-prop)（）和[resume](qabstractanimation.html#resume)（ ） 。

```
QAbstractAnimation.resume (self)
```

这种方法也是一个Qt槽与C + +的签名`void resume()`。

它恢复暂停后动画。当动画恢复时，它发出的恢复（）和[stateChanged](qabstractanimation.html#stateChanged)（ ）信号。该currentTime的不被改变。

**See also** [start](qabstractanimation.html#start)（ ）[pause](qabstractanimation.html#pause)（）和[state](qabstractanimation.html#state-prop)（ ） 。

```
QAbstractAnimation.setCurrentTime (self, int msecs)
```

这种方法也是一个Qt槽与C + +的签名`void setCurrentTime(int)`。

```
QAbstractAnimation.setDirection (self, Direction direction)
```

```
QAbstractAnimation.setLoopCount (self, int loopCount)
```

```
QAbstractAnimation.setPaused (self, bool)
```

这种方法也是一个Qt槽与C + +的签名`void setPaused(bool)`。

If _paused_诚然，动画暂停。如果_paused_是假的，动画重新开始。

**See also** [state](qabstractanimation.html#state-prop)（ ）[pause](qabstractanimation.html#pause)（）和[resume](qabstractanimation.html#resume)（ ） 。

```
QAbstractAnimation.start (self, DeletionPolicy policy = QAbstractAnimation.KeepWhenStopped)
```

这种方法也是一个Qt槽与C + +的签名`void start(QAbstractAnimation::DeletionPolicy = QAbstractAnimation.KeepWhenStopped)`。

启动动画。该_policy_论证说，不论是否当它完成的动画应该被删除。当动画开始，则[stateChanged](qabstractanimation.html#stateChanged)（）信号被发射，和[state](qabstractanimation.html#state-prop)（）返回运行。当控制到达事件循环，动画将自行运行，周期性地调用[updateCurrentTime](qabstractanimation.html#updateCurrentTime)（ ）作为动画的进展。

如果动画目前已停止或已走到了尽头，调用start （ ）将回放动画，并从头开始。当动画到达末尾时，动画要么停止，或者如果在循环水平大于1，它会倒带，并从开头继续。

如果动画已经在运行，这个函数不执行任何操作。

**See also** [stop](qabstractanimation.html#stop)（）和[state](qabstractanimation.html#state-prop)（ ） 。

```
State QAbstractAnimation.state (self)
```

[

```
QAbstractAnimation.stop (self)
```

这种方法也是一个Qt槽与C + +的签名`void stop()`。

](qabstractanimation.html#State-enum)

[停止播放动画。当动画停止时，它发出的](qabstractanimation.html#State-enum)[stateChanged](qabstractanimation.html#stateChanged)（）信号，并[state](qabstractanimation.html#state-prop)（ ）返回时停止。当前的时间不会改变。

如果在到达终点后停止动画本身（即，[currentLoopTime](qabstractanimation.html#currentLoopTime)（）==[duration](qabstractanimation.html#duration-prop)（）和[currentLoop](qabstractanimation.html#currentLoop-prop)（ ） \u003e[loopCount](qabstractanimation.html#loopCount-prop)（） - 1 ），则[finished](qabstractanimation.html#finished)（）信号被发射。

**See also** [start](qabstractanimation.html#start)（）和[state](qabstractanimation.html#state-prop)（ ） 。

```
int QAbstractAnimation.totalDuration (self)
```

返回动画的总有效和持续时间，包括循环计数。

**See also** [duration](qabstractanimation.html#duration-prop)（）和[currentTime](qabstractanimation.html#currentTime-prop)。

```
QAbstractAnimation.updateCurrentTime (self, int currentTime)
```

这种方法是抽象的，应在任何子类中重新实现。

这个纯虚函数被调用每次动画的_currentTime_变化。

**See also** [updateState](qabstractanimation.html#updateState)（ ） 。

```
QAbstractAnimation.updateDirection (self, Direction direction)
```

这个虚函数被调用[QAbstractAnimation](qabstractanimation.html)当动画的方向被改变。该_direction_参数是新的方向。

**See also** [setDirection](qabstractanimation.html#direction-prop)（）和[direction](qabstractanimation.html#direction-prop)（ ） 。

```
QAbstractAnimation.updateState (self, State newState, State oldState)
```

这个虚函数被调用[QAbstractAnimation](qabstractanimation.html)当动画的状态从变_oldState_至_newState_。

**See also** [start](qabstractanimation.html#start)（ ）[stop](qabstractanimation.html#stop)（ ）[pause](qabstractanimation.html#pause)（）和[resume](qabstractanimation.html#resume)（ ） 。

* * *

## Qt Signal Documentation

```
void currentLoopChanged (int)
```

这是该信号的默认超载。

[QAbstractAnimation](qabstractanimation.html)发出该信号时电流回路的改变。_currentLoop_是电流回路。

**See also** [currentLoop](qabstractanimation.html#currentLoop-prop)（）和[loopCount](qabstractanimation.html#loopCount-prop)（ ） 。

```
void directionChanged (QAbstractAnimation::Direction)
```

这是该信号的默认超载。

[QAbstractAnimation](qabstractanimation.html)发出该信号时的方向已经改变。_newDirection_是新的方向。

**See also** [direction](qabstractanimation.html#direction-prop)。

```
void finished ()
```

这是该信号的默认超载。

[QAbstractAnimation](qabstractanimation.html)发出此信号后的动画已经停止，并已达到结束。

之后此信号被发射[stateChanged](qabstractanimation.html#stateChanged)（ ） 。

**See also** [stateChanged](qabstractanimation.html#stateChanged)（ ） 。

```
void stateChanged (QAbstractAnimation::State,QAbstractAnimation::State)
```

这是该信号的默认超载。

[QAbstractAnimation](qabstractanimation.html)发出这个信号时动画的状态已经从_oldState_至_newState_。之后虚拟这个信号被发射[updateState](qabstractanimation.html#updateState)（ ）函数被调用。

**See also** [updateState](qabstractanimation.html#updateState)（ ） 。