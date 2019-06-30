# QSlider Class Reference

## [[QtGui](index.htm) module]

该QSlider小工具提供了一个垂直或水平滑块。[More...](#details)

继承[QAbstractSlider](qabstractslider.html)。

### Types

*   `enum TickPosition { NoTicks, TicksAbove, TicksLeft, TicksBelow, TicksRight, TicksBothSides }`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `__init__ (self, Qt.Orientation orientation, QWidget parent = None)`
*   `bool event (self, QEvent event)`
*   `initStyleOption (self, QStyleOptionSlider option)`
*   `QSize minimumSizeHint (self)`
*   `mouseMoveEvent (self, QMouseEvent ev)`
*   `mousePressEvent (self, QMouseEvent ev)`
*   `mouseReleaseEvent (self, QMouseEvent ev)`
*   `paintEvent (self, QPaintEvent ev)`
*   `setTickInterval (self, int ti)`
*   `setTickPosition (self, TickPosition position)`
*   `QSize sizeHint (self)`
*   `int tickInterval (self)`
*   `TickPosition tickPosition (self)`

* * *

## Detailed Description

该QSlider小工具提供了一个垂直或水平滑块。

滑块是经典的小部件，用于控制一个有界值。它可以让用户移动沿水平或垂直槽滑块手柄和转换手柄的位置，纳入法制范围内的整数值。

QSlider已经很少有它自己的功能，大部分的功能是在[QAbstractSlider](qabstractslider.html)。最有用的功能是[setValue](qabstractslider.html#value-prop)（ ）直接设置滑块以一定的价值;[triggerAction](qabstractslider.html#triggerAction)（）来模拟一下（为快捷键很有用）的影响;[setSingleStep](qabstractslider.html#singleStep-prop)（ ）[setPageStep](qabstractslider.html#pageStep-prop)（）来设定的步骤;和[setMinimum](qabstractslider.html#minimum-prop)（）和[setMaximum](qabstractslider.html#maximum-prop)（ ）来定义滚动条的范围。

QSlider提供了用于控制tickmarks方法。您可以使用[setTickPosition](qslider.html#tickPosition-prop)（ ）来表示您希望tickmarks是，[setTickInterval](qslider.html#tickInterval-prop)（）来指示你想有多少人。当前设置的刻度位置和间隔时间可使用查询的[tickPosition](qslider.html#tickPosition-prop)（）和[tickInterval](qslider.html#tickInterval-prop)（ ）函数，分别为。

QSlider继承了一套完整的信号：

| Signal | Description |
| --- | --- |
| [valueChanged](qabstractslider.html#valueChanged)() | Emitted when the slider's value has changed. The tracking() determines whether this signal is emitted during user interaction. |
| [sliderPressed](qabstractslider.html#sliderPressed)() | Emitted when the user starts to drag the slider. |
| [sliderMoved](qabstractslider.html#sliderMoved)() | Emitted when the user drags the slider. |
| [sliderReleased](qabstractslider.html#sliderReleased)() | Emitted when the user releases the slider. |

QSlider只提供整数范围。请注意，虽然QSlider处理非常大的数字，它为用户使用滑块精确非常大的范围变得困难。

滑块接受集中在标籤和提供了一个鼠标滚轮和键盘接口。键盘接口是以下几点：

*   Left/Right move a horizontal slider by one single step.
*   Up/Down move a vertical slider by one single step.
*   PageUp moves up one page.
*   PageDown moves down one page.
*   Home moves to the start (mininum).
*   End moves to the end (maximum).

| ![Screenshot of a Macintosh slider](../img/macintosh-slider.png) | A slider shown in the [Macintosh widget style](index.htm). |
| ![Screenshot of a Windows XP slider](../img/windows-slider.png) | A slider shown in the [Windows XP widget style](index.htm). |
| ![Screenshot of a Plastique slider](../img/plastique-slider.png) | A slider shown in the [Plastique widget style](index.htm). |

* * *

## Type Documentation

```
QSlider.TickPosition
```

这个枚举变量指定了刻度线是相对于被吸引到滑块的凹槽和处理用户动作。

| Constant | Value | Description |
| --- | --- | --- |
| `QSlider.NoTicks` | `0` | 不画任何刻度线。 |
| `QSlider.TicksBothSides` | `3` | 借鉴槽两侧刻度线。 |
| `QSlider.TicksAbove` | `1` | 画的上方（水平）滑块刻度标记 |
| `QSlider.TicksBelow` | `2` | 绘制刻度线以下（水平）滑块 |
| `QSlider.TicksLeft` | `TicksAbove` | 绘制刻度标记的（垂直）滑块的左 |
| `QSlider.TicksRight` | `TicksBelow` | 绘制刻度标记的（垂直）滑块右侧 |

* * *

## Method Documentation

```
QSlider.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个垂直滑块与给定_parent_。

```
QSlider.__init__ (self, Qt.Orientation orientation, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个滑块用给定的_parent_。该_orientation_参数确定滑块是水平的还是垂直的;有效值为[Qt.Vertical](qt.html#Orientation-enum)和[Qt.Horizontal](qt.html#Orientation-enum)。

```
bool QSlider.event (self, QEvent event)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QSlider.initStyleOption (self, QStyleOptionSlider option)
```

初始化_option_与其它的值[QSlider](qslider.html)。当他们需要一个这种方法是有用的子类[QStyleOptionSlider](qstyleoptionslider.html)，但不希望在所有的信息填写自己。

**See also** [QStyleOption.initFrom](qstyleoption.html#initFrom)（ ） 。

```
QSize QSlider.minimumSizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.minimumSizeHint](qwidget.html#minimumSizeHint-prop)（ ） 。

```
QSlider.mouseMoveEvent (self, QMouseEvent ev)
```

从重新实现[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

```
QSlider.mousePressEvent (self, QMouseEvent ev)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

```
QSlider.mouseReleaseEvent (self, QMouseEvent ev)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

```
QSlider.paintEvent (self, QPaintEvent ev)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QSlider.setTickInterval (self, int ti)
```

```
QSlider.setTickPosition (self, TickPosition position)
```

```
QSize QSlider.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

```
int QSlider.tickInterval (self)
```

```
TickPosition QSlider.tickPosition (self)
```

[](qslider.html#TickPosition-enum)