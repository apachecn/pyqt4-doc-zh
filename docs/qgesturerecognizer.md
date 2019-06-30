# QGestureRecognizer Class Reference

## [[QtGui](index.htm) module]

该QGestureRecognizer类提供了手势识别的基础设施。[More...](#details)

### Types

*   `class **[Result](index.htm)**`
*   `enum ResultFlag { Ignore, MayBeGesture, TriggerGesture, FinishGesture, CancelGesture, ConsumeEventHint }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QGestureRecognizer)`
*   `QGesture create (self, QObject target)`
*   `Result recognize (self, QGesture state, QObject watched, QEvent event)`
*   `reset (self, QGesture state)`

### Static Methods

*   `Qt.GestureType registerRecognizer (QGestureRecognizer recognizer)`
*   `unregisterRecognizer (Qt.GestureType type)`

* * *

## Detailed Description

该QGestureRecognizer类提供了手势识别的基础设施。

手势识别器负责创建和管理[QGesture](qgesture.html)对象和发送到监视输入事件[QWidget](qwidget.html)和[QGraphicsObject](qgraphicsobject.html)子类。 QGestureRecognizer是实现自定义手势的基类。

开发人员只需要提供手势识别的标准手势不需要直接使用这个类。实例将在幕后由框架创建。

手势使用手势在你的应用程序在处理Qt和信息的概述，请参阅[Gestures Programming](index.htm)文档。

### Recognizing Gestures

识别手势的过程涉及发送给特定对象的过滤输入事件，并修改相关[QGesture](qgesture.html)对象以包含有关用户的输入相关的信息。

创建手势时，框架调用[create](qgesturerecognizer.html#create)（）来处理的特定实例的用户输入[QWidget](qwidget.html) or [QGraphicsObject](qgraphicsobject.html)子类。一[QGesture](qgesture.html)对象为被配置为使用手势每个插件或项目创建。

一旦[QGesture](qgesture.html)已经为一个目标对象创建时，手势识别将获得它的活动[recognize](qgesturerecognizer.html#recognize)（ ）处理函数。

当手势被取消，[reset](qgesturerecognizer.html#reset)（ ）函数被调用，从而使识别器，以更新相应的适当的属性的机会[QGesture](qgesture.html)对象。

### Supporting New Gestures

要添加新手势的支持，你需要从QGestureRecognizer派生来创建一个自定义识别器类，构造这个类的一个实例，并与应用程序通过调用它注册[QGestureRecognizer.registerRecognizer](qgesturerecognizer.html#registerRecognizer)（ ） 。您也可以继承[QGesture](qgesture.html)创建一个自定义手势类，或依赖动态特性来表达你要处理的姿态具体细节。

您的自定义QGestureRecognizer子类需要重新实现[recognize](qgesturerecognizer.html#recognize)（ ）函数来处理和过滤的传入输入事件[QWidget](qwidget.html)和[QGraphicsObject](qgraphicsobject.html)子类。虽然手势识别的逻辑在这个函数的实现，你可以存储在识别过程中的状态持久性信息[QGesture](qgesture.html)对象提供。该[recognize](qgesturerecognizer.html#recognize)（ ）函数必须返回一个值[QGestureRecognizer.Result](qgesturerecognizer.html#ResultFlag-enum)这说明，对于一个给定的姿态和目标物体识别的状态。这决定了一个手势事件是否将被传递到的目标对象。

如果您选择自定义来表示一种姿态[QGesture](qgesture.html)子类，你需要重新实现[create](qgesturerecognizer.html#create)（ ）函数来构造你的手势类的实例。同样，您可能需要重新实现[reset](qgesturerecognizer.html#reset)（ ）函数，如果要特殊处理，当手势被取消您的自定义手势对象需要。

* * *

## Type Documentation

```
QGestureRecognizer.ResultFlag
```

这个枚举变量描述了一个手势识别状态机的当前事件的过滤步骤的结果。

该结果由一个状态值（一个忽略， MayBeGesture ， TriggerGesture ， FinishGesture ， CancelGesture ）和一个可选的提示（ ConsumeEventHint ） 。

| Constant | Value | Description |
| --- | --- | --- |
| `QGestureRecognizer.Ignore` | `0x0001` | 该事件不改变识别器的状态。 |
| `QGestureRecognizer.MayBeGesture` | `0x0002` | 事件改变识别器的内部状态，但目前还不清楚，如果它是一个手势或没有。该识别需要过滤更多的事件来决定。在MayBeGesture状态手势识别，如果他们需要很长时间才能识别手势可能会自动复位。 |
| `QGestureRecognizer.TriggerGesture` | `0x0004` | 姿态已被触发并且相应[QGesture](qgesture.html)对象将被传递到的目标，作为一个部分[QGestureEvent](qgestureevent.html)。 |
| `QGestureRecognizer.FinishGesture` | `0x0008` | 手势已经成功完成，并适当[QGesture](qgesture.html)对象将被传递到的目标，作为一个部分[QGestureEvent](qgestureevent.html)。 |
| `QGestureRecognizer.CancelGesture` | `0x0010` | 事件清楚表明，它不是一种姿态。如果手势识别是GestureTriggered状态之前，则该手势被取消，相应的[QGesture](qgesture.html)对象将被传递到的目标，作为一个部分[QGestureEvent](qgestureevent.html)。 |
| `QGestureRecognizer.ConsumeEventHint` | `0x0100` | 这提示指定的手势框架应该消耗的过滤事件，并没有提供它的接收器。 |

结果类型是一个typedef为[QFlags](index.htm)\u003cResultFlag\u003e 。它存储ResultFlag值的或组合。

**See also** [QGestureRecognizer.recognize](qgesturerecognizer.html#recognize)（ ） 。

* * *

## Method Documentation

```
QGestureRecognizer.__init__ (self)
```

构造一个新的手势识别对象。

```
QGestureRecognizer.__init__ (self, QGestureRecognizer)
```

```
QGesture QGestureRecognizer.create (self, QObject target)
```

[](qgesture.html)

[这个功能是通过Qt的调用来创建一个新的](qgesture.html)[QGesture](qgesture.html)对象为给定的_target_（[QWidget](qwidget.html) or [QGraphicsObject](qgraphicsobject.html)） 。

重新实现这个函数来创建一个自定义[QGesture](qgesture.html)衍生的手势对象如有必要。

该应用程序需要创建的手势对象的所有权。

```
Result QGestureRecognizer.recognize (self, QGesture state, QObject watched, QEvent event)
```

[

这种方法是抽象的，应在任何子类中重新实现。

处理给定的_event_为_watched_对象，更新的状态_gesture_为所需的对象，并返回一个合适的结果，当前识别步骤。

](index.htm)

[这个函数由框架调用，以允许识别器来过滤派往输入事件](index.htm)[QWidget](qwidget.html) or [QGraphicsObject](qgraphicsobject.html)情况下，它正在监视。

其结果反映了手势的多已被确认。的状态_gesture_根据结果对象被设置。

**See also** [QGestureRecognizer.Result](qgesturerecognizer.html#ResultFlag-enum)。

```
Qt.GestureType QGestureRecognizer.registerRecognizer (QGestureRecognizer recognizer)
```

[

该_recognizer_说法有它的所有权转移给Qt的。

注册给定的_recognizer_在手势框架，并返回一个手势ID为它。

](qt.html#GestureType-enum)

[该应用程序采用的所有权_recognizer_并返回与它相关联的手势类型ID。对于手势识别的处理自定义](qt.html#GestureType-enum)[QGesture](qgesture.html)对象（即，那些回报[Qt.CustomGesture](qt.html#GestureType-enum)在[QGesture.gestureType](qgesture.html#gestureType-prop)（ ）函数）的返回值是与生成的手势识别码[Qt.CustomGesture](qt.html#GestureType-enum)标志设置。

**See also** [unregisterRecognizer](qgesturerecognizer.html#unregisterRecognizer)（ ）[QGestureRecognizer.create](qgesturerecognizer.html#create)（）和[QGesture](qgesture.html)。

```
QGestureRecognizer.reset (self, QGesture state)
```

调用此函数由框架来重置一个给定的_gesture_。

重新实现这个函数来实现自定义的附加要求[QGesture](qgesture.html)对象。如果你实现一个自定义的，这可能是必要的[QGesture](qgesture.html)其性质需要当手势被复位特殊处理。

```
QGestureRecognizer.unregisterRecognizer (Qt.GestureType type)
```

取消注册所有手势指定的识别_type_。

**See also** [registerRecognizer](qgesturerecognizer.html#registerRecognizer)（ ） 。