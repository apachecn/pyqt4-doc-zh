# QTimeLine Class Reference

## [[QtCore](index.htm) module]

该QTimeLine类提供了一个时间表来控制动画。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum CurveShape { EaseInCurve, EaseOutCurve, EaseInOutCurve, LinearCurve, SineCurve, CosineCurve }`
*   `enum Direction { Forward, Backward }`
*   `enum State { NotRunning, Paused, Running }`

### Methods

*   `__init__ (self, int duration = 1000, QObject parent = None)`
*   `int currentFrame (self)`
*   `int currentTime (self)`
*   `float currentValue (self)`
*   `CurveShape curveShape (self)`
*   `Direction direction (self)`
*   `int duration (self)`
*   `QEasingCurve easingCurve (self)`
*   `int endFrame (self)`
*   `int frameForTime (self, int msec)`
*   `int loopCount (self)`
*   `resume (self)`
*   `setCurrentTime (self, int msec)`
*   `setCurveShape (self, CurveShape shape)`
*   `setDirection (self, Direction direction)`
*   `setDuration (self, int duration)`
*   `setEasingCurve (self, QEasingCurve curve)`
*   `setEndFrame (self, int frame)`
*   `setFrameRange (self, int startFrame, int endFrame)`
*   `setLoopCount (self, int count)`
*   `setPaused (self, bool paused)`
*   `setStartFrame (self, int frame)`
*   `setUpdateInterval (self, int interval)`
*   `start (self)`
*   `int startFrame (self)`
*   `State state (self)`
*   `stop (self)`
*   `timerEvent (self, QTimerEvent event)`
*   `toggleDirection (self)`
*   `int updateInterval (self)`
*   `float valueForTime (self, int msec)`

### Qt Signals

*   `void finished ()`
*   `void frameChanged (int)`
*   `void stateChanged (QTimeLine::State)`
*   `void valueChanged (qreal)`

* * *

## Detailed Description

该QTimeLine类提供了一个时间表来控制动画。

这是最常用的定期调用插槽，一个动画图形用户界面控制。你可以通过传递它的持续时间以毫秒为单位QTimeLine的构造函数构造一个时间表。时间线的持续时间描述了多久动画将运行。然后，通过调用设置一个合适的框架范围[setFrameRange](qtimeline.html#setFrameRange)（ ） 。最后连接[frameChanged](qtimeline.html#frameChanged)（）信号到一个合适的插槽，你想在动画（例如， setValue方法（ ）的小工具[QProgressBar](qprogressbar.html)） 。当您进行呼叫[start](qtimeline.html#start)（ ） ， QTimeLine将进入运行状态，并开始发光[frameChanged](qtimeline.html#frameChanged)（ ）定期，造成你的widget的连接属性的值从低端长到你的框架范围的上限，并以稳定的速度。你可以通过调用指定的更新间隔[setUpdateInterval](qtimeline.html#updateInterval-prop)（ ） 。完成后， QTimeLine进入[NotRunning](qtimeline.html#State-enum)态，并发射[finished](qtimeline.html#finished)（ ） 。

例如：

```
 ...
 progressBar = new [QProgressBar](qprogressbar.html)(this);
 progressBar->setRange(0, 100);

 // Construct a 1-second timeline with a frame range of 0 - 100
 QTimeLine *timeLine = new QTimeLine(1000, this);
 timeLine->setFrameRange(0, 100);
 connect(timeLine, SIGNAL(frameChanged(int)), progressBar, SLOT(setValue(int)));

 // Clicking the push button will start the progress bar animation
 pushButton = new [QPushButton](qpushbutton.html)(tr("Start animation"), this);
 connect(pushButton, SIGNAL(clicked()), timeLine, SLOT(start()));
 ...

```

您还可以使用QTimeLine与[Graphics View framework](index.htm#graphics-view)为动画。该[QGraphicsItemAnimation](qgraphicsitemanimation.html)类实现的动画[QGraphicsItems](qgraphicsitem.html)有一个时间表。

默认情况下，时间线运行一次，从一开始接近尾声，在这你必须调用[start](qtimeline.html#start)（）再次从开始重新启动。若要使时间循环，可以调用[setLoopCount](qtimeline.html#loopCount-prop)（ ） ，传递时代的时间表应该在完成之前运行的次数。方向也可以改变，导致在时间轴向后运行，通过调用[setDirection](qtimeline.html#direction-prop)（ ） 。您也可以暂停及恢复的时间线，而它的运行通过调用[setPaused](qtimeline.html#setPaused)（ ） 。对于交互式的控制，[setCurrentTime](qtimeline.html#currentTime-prop)（）函数被提供，其直接设置时间线的时间位置。虽然最有用[NotRunning](qtimeline.html#State-enum)状态（例如，连接到一个[valueChanged](qtimeline.html#valueChanged)（）中的信号[QSlider](qslider.html)，），该函数可以在任何时候调用。

在框架接口是标准的部件有用的，但QTimeLine可用于控制任何类型的动画。 QTimeLine的心脏在于[valueForTime](qtimeline.html#valueForTime)（ ）函数，它产生一个_value_0和1之间一个给定的时间。这个值通常是用来描述一个动画，其中0是动画的第一步骤，和1是最后一步的步骤。在运行时， QTimeLine通过调用生成0和1之间的值[valueForTime](qtimeline.html#valueForTime)（）和发射[valueChanged](qtimeline.html#valueChanged)（ ） 。默认情况下，[valueForTime](qtimeline.html#valueForTime)（ ）适用的插值算法来生成这些值。您可以从一组预定义的时间线算法通过调用选择[setCurveShape](qtimeline.html#curveShape-prop)（ ） 。

请注意，默认情况下， QTimeLine使用EaseInOut曲线形状，它提供了一个值，生长缓慢，然后稳步增长，终于慢慢地成长。对于自定义的时间轴，你可以重新实现[valueForTime](qtimeline.html#valueForTime)（） ，在这种情况QTimeLine的[curveShape](qtimeline.html#curveShape-prop)属性被忽略。

* * *

## Type Documentation

```
QTimeLine.CurveShape
```

这个枚举变量描述的默认形状[QTimeLine](qtimeline.html)的价值曲线。默认的，形状是EaseInOutCurve 。该曲线定义的值，并在时间轴之间的关系。

| Constant | Value | Description |
| --- | --- | --- |
| `QTimeLine.EaseInCurve` | `0` | 该值开始缓慢增长，然后在速度增加。 |
| `QTimeLine.EaseOutCurve` | `1` | 该值开始稳步增长，然后慢慢结束。 |
| `QTimeLine.EaseInOutCurve` | `2` | 该值开始缓慢增长，然后稳步运行，然后再次生长缓慢。 |
| `QTimeLine.LinearCurve` | `3` | 该值线性增长（例如，如果持续时间为1000毫秒，在时间的价值500毫秒为0.5 ） 。 |
| `QTimeLine.SineCurve` | `4` | 价值增长正弦。 |
| `QTimeLine.CosineCurve` | `5` | 价值增长cosinusoidally 。 |

**See also** [setCurveShape](qtimeline.html#curveShape-prop)（ ） 。

```
QTimeLine.Direction
```

这个枚举变量描述时间轴的方向时，[Running](qtimeline.html#State-enum)状态。

| Constant | Value | Description |
| --- | --- | --- |
| `QTimeLine.Forward` | `0` | 时间轴的当前时间随时间（即从0到接近尾声/时间移动） 。 |
| `QTimeLine.Backward` | `1` | 随着时间（即从底/持续时间和对0移动）时间轴的当前时间减少。 |

**See also** [setDirection](qtimeline.html#direction-prop)（ ） 。

```
QTimeLine.State
```

这个枚举变量描述时间轴的状态。

| Constant | Value | Description |
| --- | --- | --- |
| `QTimeLine.NotRunning` | `0` | 时间轴没有运行。这是初始状态[QTimeLine](qtimeline.html)，和国家[QTimeLine](qtimeline.html)重新进入时完成。当前的时间，框架和价值保持不变，直至[setCurrentTime](qtimeline.html#currentTime-prop)（ ）被调用时，或者时间线是通过调用启动[start](qtimeline.html#start)（ ） 。 |
| `QTimeLine.Paused` | `1` | 时间轴暂停（即暂停） 。调用setPaused （假）将恢复时间表活动。 |
| `QTimeLine.Running` | `2` | 时间线运行。而控制是在事件循环，[QTimeLine](qtimeline.html)将定期更新其当前的时间，发光[valueChanged](qtimeline.html#valueChanged)（）和[frameChanged](qtimeline.html#frameChanged)（ ）在适当的时候。 |

**See also** [state](qtimeline.html#state)（）和[stateChanged](qtimeline.html#stateChanged)（ ） 。

* * *

## Method Documentation

```
QTimeLine.__init__ (self, int duration = 1000, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个带有时间线的持续时间_duration_毫秒。_parent_被传递给[QObject](qobject.html)的构造。默认持续时间为1000毫秒。

```
int QTimeLine.currentFrame (self)
```

返回对应于当前的时间框架。

**See also** [currentTime](qtimeline.html#currentTime-prop)（ ）[frameForTime](qtimeline.html#frameForTime)（）和[setFrameRange](qtimeline.html#setFrameRange)（ ） 。

```
int QTimeLine.currentTime (self)
```

```
float QTimeLine.currentValue (self)
```

返回对应于当前时间的值。

**See also** [valueForTime](qtimeline.html#valueForTime)（）和[currentFrame](qtimeline.html#currentFrame)（ ） 。

```
CurveShape QTimeLine.curveShape (self)
```

[](qtimeline.html#CurveShape-enum)

```
Direction QTimeLine.direction (self)
```

[

```
int QTimeLine.duration (self)
```

](qtimeline.html#Direction-enum)

```
QEasingCurve QTimeLine.easingCurve (self)
```

[

```
int QTimeLine.endFrame (self)
```

返回端框架，它是对应于时间线（即对于其当前值是1帧）的端部的框架。

](qeasingcurve.html)

[**See also**](qeasingcurve.html) [setEndFrame](qtimeline.html#setEndFrame)（）和[setFrameRange](qtimeline.html#setFrameRange)（ ） 。

```
int QTimeLine.frameForTime (self, int msec)
```

返回对应于时间帧_msec_。此值是使用的开始和结束帧的线性插值，基于由返回的值计算出[valueForTime](qtimeline.html#valueForTime)（ ） 。

**See also** [valueForTime](qtimeline.html#valueForTime)（）和[setFrameRange](qtimeline.html#setFrameRange)（ ） 。

```
int QTimeLine.loopCount (self)
```

```
QTimeLine.resume (self)
```

这种方法也是一个Qt槽与C + +的签名`void resume()`。

从当前时间恢复的时间表。[QTimeLine](qtimeline.html)将重新进入运行状态，一旦进入事件循环，它会更新其当前的时间，框架和价值定期进行。

在对比[start](qtimeline.html#start)（ ） ，这个函数不重新启动的时间线将恢复之前。

**See also** [start](qtimeline.html#start)（ ）[updateInterval](qtimeline.html#updateInterval-prop)（ ）[frameChanged](qtimeline.html#frameChanged)（）和[valueChanged](qtimeline.html#valueChanged)（ ） 。

```
QTimeLine.setCurrentTime (self, int msec)
```

这种方法也是一个Qt槽与C + +的签名`void setCurrentTime(int)`。

```
QTimeLine.setCurveShape (self, CurveShape shape)
```

```
QTimeLine.setDirection (self, Direction direction)
```

```
QTimeLine.setDuration (self, int duration)
```

```
QTimeLine.setEasingCurve (self, QEasingCurve curve)
```

```
QTimeLine.setEndFrame (self, int frame)
```

设置结束帧，这是对应于时间线（即对于其当前值是1帧）的端部的框架，以_frame_。

**See also** [endFrame](qtimeline.html#endFrame)（ ）[startFrame](qtimeline.html#startFrame)（）和[setFrameRange](qtimeline.html#setFrameRange)（ ） 。

```
QTimeLine.setFrameRange (self, int startFrame, int endFrame)
```

设置时间轴的帧计数器开始在_startFrame_以及端部和_endFrame_。对于每个时间值，[QTimeLine](qtimeline.html)将找到相应的帧，当你调用[currentFrame](qtimeline.html#currentFrame)（）或[frameForTime](qtimeline.html#frameForTime)（）通过内插，使用的返回值[valueForTime](qtimeline.html#valueForTime)（ ） 。

当在运行状态下，[QTimeLine](qtimeline.html)还发出了[frameChanged](qtimeline.html#frameChanged)（ ）信号时，帧的变化。

**See also** [startFrame](qtimeline.html#startFrame)（ ）[endFrame](qtimeline.html#endFrame)（ ）[start](qtimeline.html#start)（）和[currentFrame](qtimeline.html#currentFrame)（ ） 。

```
QTimeLine.setLoopCount (self, int count)
```

```
QTimeLine.setPaused (self, bool paused)
```

这种方法也是一个Qt槽与C + +的签名`void setPaused(bool)`。

If _paused_诚然，在时间轴暂停，造成[QTimeLine](qtimeline.html)进入暂停状态。没有更新将被通知，直至[start](qtimeline.html#start)（）或setPaused （假）被调用。如果_paused_是假的，时间轴恢复并继续它。

**See also** [state](qtimeline.html#state)（）和[start](qtimeline.html#start)（ ） 。

```
QTimeLine.setStartFrame (self, int frame)
```

设置开始帧，这是对应于时间线（即对于该电流值是0帧）的开始，到该帧_frame_。

**See also** [startFrame](qtimeline.html#startFrame)（ ）[endFrame](qtimeline.html#endFrame)（）和[setFrameRange](qtimeline.html#setFrameRange)（ ） 。

```
QTimeLine.setUpdateInterval (self, int interval)
```

```
QTimeLine.start (self)
```

这种方法也是一个Qt槽与C + +的签名`void start()`。

启动时间表。[QTimeLine](qtimeline.html)将进入运行状态，一旦进入事件循环，它会更新其当前的时间，框架和价值定期进行。默认时间间隔为40毫秒（即每秒25次） 。你可以通过调用更改更新时间间隔[setUpdateInterval](qtimeline.html#updateInterval-prop)（ ） 。

时间轴会从位置0 ，或结束时，如果倒退启动。如果你想恢复已停止的时间表而不需要重新启动，你可以调用[resume](qtimeline.html#resume)（ ）来代替。

**See also** [resume](qtimeline.html#resume)（ ）[updateInterval](qtimeline.html#updateInterval-prop)（ ）[frameChanged](qtimeline.html#frameChanged)（）和[valueChanged](qtimeline.html#valueChanged)（ ） 。

```
int QTimeLine.startFrame (self)
```

返回的起始帧，这是对应于时间线（即对于其当前值是0帧）的开始帧。

**See also** [setStartFrame](qtimeline.html#setStartFrame)（）和[setFrameRange](qtimeline.html#setFrameRange)（ ） 。

```
State QTimeLine.state (self)
```

[

返回时间轴的状态。

](qtimeline.html#State-enum)

[**See also**](qtimeline.html#State-enum) [start](qtimeline.html#start)（ ）[setPaused](qtimeline.html#setPaused)（）和[stop](qtimeline.html#stop)（ ） 。

```
QTimeLine.stop (self)
```

这种方法也是一个Qt槽与C + +的签名`void stop()`。

停止时间轴，造成[QTimeLine](qtimeline.html) to enter [NotRunning](qtimeline.html#State-enum)状态。

**See also** [start](qtimeline.html#start)（ ） 。

```
QTimeLine.timerEvent (self, QTimerEvent event)
```

从重新实现[QObject.timerEvent](qobject.html#timerEvent)（ ） 。

```
QTimeLine.toggleDirection (self)
```

这种方法也是一个Qt槽与C + +的签名`void toggleDirection()`。

切换时间线的方向。如果方向是前进，它变得落后，副verca 。

**See also** [setDirection](qtimeline.html#direction-prop)（ ） 。

```
int QTimeLine.updateInterval (self)
```

```
float QTimeLine.valueForTime (self, int msec)
```

返回时间轴价值的时间_msec_。返回的值，取决于曲线的形状而变化，始终为0和1之间。如果_msec_为0时，默认的实现始终返回0 。

重新实现这个函数提供一个自定义的曲线形状为你的时间表。

**See also** [CurveShape](qtimeline.html#CurveShape-enum)和[frameForTime](qtimeline.html#frameForTime)（ ） 。

* * *

## Qt Signal Documentation

```
void finished ()
```

这是该信号的默认超载。

这个信号被发射时[QTimeLine](qtimeline.html)完成（即达到其时间线的末端）和不循环。

```
void frameChanged (int)
```

这是该信号的默认超载。

[QTimeLine](qtimeline.html)以规则间隔发出该信号在时[Running](qtimeline.html#State-enum)状态，但只有在当前帧的变化。_frame_是当前帧号。

**See also** [QTimeLine.setFrameRange](qtimeline.html#setFrameRange)（）和[QTimeLine.updateInterval](qtimeline.html#updateInterval-prop)。

```
void stateChanged (QTimeLine::State)
```

这是该信号的默认超载。

这个信号被发射时[QTimeLine](qtimeline.html)的状态变化。新的状态是_newState_。

```
void valueChanged (qreal)
```

这是该信号的默认超载。

[QTimeLine](qtimeline.html)以规则间隔发出该信号在时[Running](qtimeline.html#State-enum)状态，但只有当电流值而变化。_value_是当前值。_value_是一个介于0.0和1.0之间

**See also** [QTimeLine.setDuration](qtimeline.html#duration-prop)（ ）[QTimeLine.valueForTime](qtimeline.html#valueForTime)（）和[QTimeLine.updateInterval](qtimeline.html#updateInterval-prop)。