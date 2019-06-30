# QAbstractSlider Class Reference

## [[QtGui](index.htm) module]

该QAbstractSlider类提供了一个范围内的整数值。[More...](#details)

继承[QWidget](qwidget.html)。

通过继承[QDial](qdial.html)，[QScrollBar](qscrollbar.html)和[QSlider](qslider.html)。

### Types

*   `enum SliderAction { SliderNoAction, SliderSingleStepAdd, SliderSingleStepSub, SliderPageStepAdd, ..., SliderMove }`
*   `enum SliderChange { SliderRangeChange, SliderOrientationChange, SliderStepsChange, SliderValueChange }`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `changeEvent (self, QEvent e)`
*   `bool event (self, QEvent e)`
*   `bool hasTracking (self)`
*   `bool invertedAppearance (self)`
*   `bool invertedControls (self)`
*   `bool isSliderDown (self)`
*   `keyPressEvent (self, QKeyEvent ev)`
*   `int maximum (self)`
*   `int minimum (self)`
*   `Qt.Orientation orientation (self)`
*   `int pageStep (self)`
*   `SliderAction repeatAction (self)`
*   `setInvertedAppearance (self, bool)`
*   `setInvertedControls (self, bool)`
*   `setMaximum (self, int)`
*   `setMinimum (self, int)`
*   `setOrientation (self, Qt.Orientation)`
*   `setPageStep (self, int)`
*   `setRange (self, int min, int max)`
*   `setRepeatAction (self, SliderAction action, int thresholdTime = 500, int repeatTime = 50)`
*   `setSingleStep (self, int)`
*   `setSliderDown (self, bool)`
*   `setSliderPosition (self, int)`
*   `setTracking (self, bool enable)`
*   `setValue (self, int)`
*   `int singleStep (self)`
*   `sliderChange (self, SliderChange change)`
*   `int sliderPosition (self)`
*   `timerEvent (self, QTimerEvent)`
*   `triggerAction (self, SliderAction action)`
*   `int value (self)`
*   `wheelEvent (self, QWheelEvent e)`

### Qt Signals

*   `void actionTriggered (int)`
*   `void rangeChanged (int,int)`
*   `void sliderMoved (int)`
*   `void sliderPressed ()`
*   `void sliderReleased ()`
*   `void valueChanged (int)`

* * *

## Detailed Description

该QAbstractSlider类提供了一个范围内的整数值。

这个类被设计成一个共同的超类的小部件一样[QScrollBar](qscrollbar.html)，[QSlider](qslider.html)和[QDial](qdial.html)。

下面是类的主要属性：

1.  [value](qabstractslider.html#value-prop)：有界整数QAbstractSlider维护。
2.  [minimum](qabstractslider.html#minimum-prop)：尽可能低的值。
3.  [maximum](qabstractslider.html#maximum-prop)：可能的最高值。
4.  [singleStep](qabstractslider.html#singleStep-prop)：是一个抽象的滑块提供，通常越小的两个自然步骤，对应于按箭头键的用户。
5.  [pageStep](qabstractslider.html#pageStep-prop)：是一个抽象的滑块提供，通常较大的两个自然步骤，相当于按压上下翻页的用户。
6.  [tracking](qabstractslider.html#tracking-prop)：滑块跟踪是否被启用。
7.  [sliderPosition](qabstractslider.html#sliderPosition-prop)：滑块的当前位置。如果[tracking](qabstractslider.html#tracking-prop)已启用（默认值） ，这是相同的[value](qabstractslider.html#value-prop)。

统一性（1）可被看作第三步长。[setValue](qabstractslider.html#value-prop)（ ）可让您在允许的范围内设定的电流值任意整数，而不仅仅是[minimum](qabstractslider.html#minimum-prop)（）+_n_*[singleStep](qabstractslider.html#singleStep-prop)（ ）为整数值_n_。一些小部件可能会允许用户设置任何价值可言，有些人可能只是提供的倍数[singleStep](qabstractslider.html#singleStep-prop)（）或[pageStep](qabstractslider.html#pageStep-prop)（ ） 。

QAbstractSlider发出一套全面的信号：

| Signal | Emitted when |
| --- | --- |
| [valueChanged](qabstractslider.html#valueChanged)() | the value has changed. The [tracking](qabstractslider.html#tracking-prop) determines whether this signal is emitted during user interaction. |
| [sliderPressed](qabstractslider.html#sliderPressed)() | the user starts to drag the slider. |
| [sliderMoved](qabstractslider.html#sliderMoved)() | the user drags the slider. |
| [sliderReleased](qabstractslider.html#sliderReleased)() | the user releases the slider. |
| [actionTriggered](qabstractslider.html#actionTriggered)() | a slider action was triggerd. |
| [rangeChanged](qabstractslider.html#rangeChanged)() | a the range has changed. |

QAbstractSlider提供了一个虚拟[sliderChange](qabstractslider.html#sliderChange)（）函数，是非常适合用于更新滑块的屏幕上的表示。通过调用[triggerAction](qabstractslider.html#triggerAction)（ ） ，子类触发滑块动作。两个辅助函数[QStyle.sliderPositionFromValue](qstyle.html#sliderPositionFromValue)（）和[QStyle.sliderValueFromPosition](qstyle.html#sliderValueFromPosition)（ ）帮助子类和样式映射屏幕坐标到逻辑范围值。

* * *

## Type Documentation

```
QAbstractSlider.SliderAction
```

| Constant | Value |
| --- | --- |
| `QAbstractSlider.SliderNoAction` | `0` |
| `QAbstractSlider.SliderSingleStepAdd` | `1` |
| `QAbstractSlider.SliderSingleStepSub` | `2` |
| `QAbstractSlider.SliderPageStepAdd` | `3` |
| `QAbstractSlider.SliderPageStepSub` | `4` |
| `QAbstractSlider.SliderToMinimum` | `5` |
| `QAbstractSlider.SliderToMaximum` | `6` |
| `QAbstractSlider.SliderMove` | `7` |

```
QAbstractSlider.SliderChange
```

| Constant | Value |
| --- | --- |
| `QAbstractSlider.SliderRangeChange` | `0` |
| `QAbstractSlider.SliderOrientationChange` | `1` |
| `QAbstractSlider.SliderStepsChange` | `2` |
| `QAbstractSlider.SliderValueChange` | `3` |

* * *

## Method Documentation

```
QAbstractSlider.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个抽象的滑块。

该_parent_参数被发送到[QWidget](qwidget.html)构造函数。

该[minimum](qabstractslider.html#minimum-prop)缺省值为0 ，则[maximum](qabstractslider.html#maximum-prop)为99，用[singleStep](qabstractslider.html#singleStep-prop)1尺寸和[pageStep](qabstractslider.html#pageStep-prop)10的尺寸，和一个初始[value](qabstractslider.html#value-prop)0 。

```
QAbstractSlider.changeEvent (self, QEvent e)
```

从重新实现[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
bool QAbstractSlider.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
bool QAbstractSlider.hasTracking (self)
```

```
bool QAbstractSlider.invertedAppearance (self)
```

```
bool QAbstractSlider.invertedControls (self)
```

```
bool QAbstractSlider.isSliderDown (self)
```

```
QAbstractSlider.keyPressEvent (self, QKeyEvent ev)
```

从重新实现[QWidget.keyPressEvent](qwidget.html#keyPressEvent)（ ） 。

```
int QAbstractSlider.maximum (self)
```

```
int QAbstractSlider.minimum (self)
```

```
Qt.Orientation QAbstractSlider.orientation (self)
```

[

```
int QAbstractSlider.pageStep (self)
```

](qt.html#Orientation-enum)

```
SliderAction QAbstractSlider.repeatAction (self)
```

[

返回当前重复动作。

](qabstractslider.html#SliderAction-enum)

[**See also**](qabstractslider.html#SliderAction-enum) [setRepeatAction](qabstractslider.html#setRepeatAction)（ ） 。

```
QAbstractSlider.setInvertedAppearance (self, bool)
```

```
QAbstractSlider.setInvertedControls (self, bool)
```

```
QAbstractSlider.setMaximum (self, int)
```

```
QAbstractSlider.setMinimum (self, int)
```

```
QAbstractSlider.setOrientation (self, Qt.Orientation)
```

这种方法也是一个Qt槽与C + +的签名`void setOrientation(Qt::Orientation)`。

```
QAbstractSlider.setPageStep (self, int)
```

```
QAbstractSlider.setRange (self, int min, int max)
```

设置滑块的最小值为_min_其最大到_max_。

If _max_小于_min_，_min_成为唯一的合法值。

**See also** [minimum](qabstractslider.html#minimum-prop)和[maximum](qabstractslider.html#maximum-prop)。

```
QAbstractSlider.setRepeatAction (self, SliderAction action, int thresholdTime = 500, int repeatTime = 50)
```

套动作_action_要的时间间隔重复地触发_repeatTime_，的一个初始延迟后_thresholdTime_。

**See also** [triggerAction](qabstractslider.html#triggerAction)（）和[repeatAction](qabstractslider.html#repeatAction)（ ） 。

```
QAbstractSlider.setSingleStep (self, int)
```

```
QAbstractSlider.setSliderDown (self, bool)
```

```
QAbstractSlider.setSliderPosition (self, int)
```

```
QAbstractSlider.setTracking (self, bool enable)
```

```
QAbstractSlider.setValue (self, int)
```

这种方法也是一个Qt槽与C + +的签名`void setValue(int)`。

```
int QAbstractSlider.singleStep (self)
```

```
QAbstractSlider.sliderChange (self, SliderChange change)
```

重新实现这个虚函数来跟踪滑块的变化，如[SliderRangeChange](qabstractslider.html#SliderChange-enum)，[SliderOrientationChange](qabstractslider.html#SliderChange-enum)，[SliderStepsChange](qabstractslider.html#SliderChange-enum)或[SliderValueChange](qabstractslider.html#SliderChange-enum)。默认实现只更新显示，而忽略了_change_参数。

```
int QAbstractSlider.sliderPosition (self)
```

```
QAbstractSlider.timerEvent (self, QTimerEvent)
```

从重新实现[QObject.timerEvent](qobject.html#timerEvent)（ ） 。

```
QAbstractSlider.triggerAction (self, SliderAction action)
```

触发一个滑块_action_。可能的操作是[SliderSingleStepAdd](qabstractslider.html#SliderAction-enum)，[SliderSingleStepSub](qabstractslider.html#SliderAction-enum)，[SliderPageStepAdd](qabstractslider.html#SliderAction-enum)，[SliderPageStepSub](qabstractslider.html#SliderAction-enum)，[SliderToMinimum](qabstractslider.html#SliderAction-enum)，[SliderToMaximum](qabstractslider.html#SliderAction-enum)和[SliderMove](qabstractslider.html#SliderAction-enum)。

**See also** [actionTriggered](qabstractslider.html#actionTriggered)（ ） 。

```
int QAbstractSlider.value (self)
```

```
QAbstractSlider.wheelEvent (self, QWheelEvent e)
```

从重新实现[QWidget.wheelEvent](qwidget.html#wheelEvent)（ ） 。

* * *

## Qt Signal Documentation

```
void actionTriggered (int)
```

这是该信号的默认超载。

这个信号被发射时，在滑块动作_action_被触发。行动[SliderSingleStepAdd](qabstractslider.html#SliderAction-enum)，[SliderSingleStepSub](qabstractslider.html#SliderAction-enum)，[SliderPageStepAdd](qabstractslider.html#SliderAction-enum)，[SliderPageStepSub](qabstractslider.html#SliderAction-enum)，[SliderToMinimum](qabstractslider.html#SliderAction-enum)，[SliderToMaximum](qabstractslider.html#SliderAction-enum)和[SliderMove](qabstractslider.html#SliderAction-enum)。

当信号被发射时，[sliderPosition](qabstractslider.html#sliderPosition-prop)根据动作进行了调整，但[value](qabstractslider.html#value-prop)尚未被传播（意味着[valueChanged](qabstractslider.html#valueChanged)（）信号还没有发出） ，并目测显示未被更新。在连接到该信号插槽，你可以这样放心地通过调用调整任何行动[setSliderPosition](qabstractslider.html#sliderPosition-prop)（ ）自己的基础上，双方的动作和滑块的值。

**See also** [triggerAction](qabstractslider.html#triggerAction)（ ） 。

```
void rangeChanged (int,int)
```

这是该信号的默认超载。

这个信号被发射时的滑块范围发生了变化，与_min_作为新的最小值，并_max_作为新的最大值。

**See also** [minimum](qabstractslider.html#minimum-prop)和[maximum](qabstractslider.html#maximum-prop)。

```
void sliderMoved (int)
```

这是该信号的默认超载。

这个信号被发射时[sliderDown](qabstractslider.html#sliderDown-prop)是真实的滑块移动。这通常发生在用户拖动滑块发生。该_value_是新的滑块位置。

即使当跟踪被关闭，这个信号被发射。

**See also** [setTracking](qabstractslider.html#tracking-prop)（ ）[valueChanged](qabstractslider.html#valueChanged)（ ）[isSliderDown](qabstractslider.html#sliderDown-prop)（ ）[sliderPressed](qabstractslider.html#sliderPressed)（）和[sliderReleased](qabstractslider.html#sliderReleased)（ ） 。

```
void sliderPressed ()
```

这是该信号的默认超载。

当用户按下滑块用鼠标或编程时setSliderDown （真）被调用，这个信号被发射。

**See also** [sliderReleased](qabstractslider.html#sliderReleased)（ ）[sliderMoved](qabstractslider.html#sliderMoved)（）和[isSliderDown](qabstractslider.html#sliderDown-prop)（ ） 。

```
void sliderReleased ()
```

这是该信号的默认超载。

当用户释放鼠标滑杆，或编程时setSliderDown （假）被称为这个信号被发射。

**See also** [sliderPressed](qabstractslider.html#sliderPressed)（ ）[sliderMoved](qabstractslider.html#sliderMoved)（）和[sliderDown](qabstractslider.html#sliderDown-prop)。

```
void valueChanged (int)
```

这是该信号的默认超载。

这个信号被发射时，滑块值发生了变化，与新的滑块_value_作为参数。