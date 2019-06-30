# QStyleOptionSlider Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionSlider类是用来描述所需要的绘制一个滑块的参数。[More...](#details)

继承[QStyleOptionComplex](qstyleoptioncomplex.html)。

### Types

*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionSlider other)`

### Members

*   `bool **[dialWrapping](qstyleoptionslider.html#dialWrapping-var)**`
*   `int **[maximum](qstyleoptionslider.html#maximum-var)**`
*   `int **[minimum](qstyleoptionslider.html#minimum-var)**`
*   `float **[notchTarget](qstyleoptionslider.html#notchTarget-var)**`
*   `Qt.Orientation **[orientation](qstyleoptionslider.html#orientation-var)**`
*   `int **[pageStep](qstyleoptionslider.html#pageStep-var)**`
*   `int **[singleStep](qstyleoptionslider.html#singleStep-var)**`
*   `int **[sliderPosition](qstyleoptionslider.html#sliderPosition-var)**`
*   `int **[sliderValue](qstyleoptionslider.html#sliderValue-var)**`
*   `int **[tickInterval](qstyleoptionslider.html#tickInterval-var)**`
*   `QSlider.TickPosition **[tickPosition](qstyleoptionslider.html#tickPosition-var)**`
*   `bool **[upsideDown](qstyleoptionslider.html#upsideDown-var)**`

* * *

## Detailed Description

该QStyleOptionSlider类是用来描述所需要的绘制一个滑块的参数。

QStyleOptionSlider包含的所有信息，[QStyle](qstyle.html)功能需要绘制[QSlider](qslider.html)和[QScrollBar](qscrollbar.html)。

出于性能方面的原因，访问成员变量是直接的（即使用`.` or `-&gt;`操作符）。这种低层次的感觉，使结构简单的使用，并强调这些只是所用的样式函数的参数。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionSlider.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionSlider.Type` | `SO_Slider` | 风格选择该类型提供（[SO_Slider](qstyleoption.html#OptionType-enum)这个类） 。 |

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstyleoptionslider.html#StyleOptionVersion-enum)。

```
QStyleOptionSlider.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionSlider.Version` | `1` | 1 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptionslider.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionSlider.__init__ (self)
```

构造一个[QStyleOptionSlider](qstyleoptionslider.html)，初始化成员变量，它们的默认值。

```
QStyleOptionSlider.__init__ (self, QStyleOptionSlider other)
```

构造的一个副本_other_样式选项。

* * *

## Member Documentation

```
bool dialWrapping
```

这个变量保存的拨号是否换行还是不行。

默认值为False ，即转盘没有包裹。

**See also** [QDial.wrapping](qdial.html#wrapping-prop)（ ） 。

```
int maximum
```

这个变量保存为滑块的最大值。

默认值是0。

```
int minimum
```

这个变量保存为滑块的最小值。

默认值是0。

```
float notchTarget
```

这个变量保存像素的缺口之间的数字。

默认值是0.0 。

**See also** [QDial.notchTarget](qdial.html#notchTarget-prop)（ ） 。

```
Qt.Orientation orientation
```

[

这个变量保存滑块的方向（水平或垂直） 。

](qt.html#Orientation-enum)

[默认的方向是](qt.html#Orientation-enum)[Qt.Horizontal](qt.html#Orientation-enum)。

**See also** [Qt.Orientation](qt.html#Orientation-enum)。

```
int pageStep
```

这个变量保存滑块的页面步长的大小。

默认值是0。

**See also** [QAbstractSlider.pageStep](qabstractslider.html#pageStep-prop)。

```
int singleStep
```

这个变量保存滑块的单一步骤的大小。

默认值是0。

**See also** [QAbstractSlider.singleStep](qabstractslider.html#singleStep-prop)。

```
int sliderPosition
```

这个变量保存滑块手柄的位置。

如果滑块具有积极的反馈（即，[QAbstractSlider.tracking](qabstractslider.html#tracking-prop)为真） ，则此值将是相同的[sliderValue](qstyleoptionslider.html#sliderValue-var)。否则，它将具有手柄的当前位置。默认值是0。

**See also** [QAbstractSlider.tracking](qabstractslider.html#tracking-prop)和[sliderValue](qstyleoptionslider.html#sliderValue-var)。

```
int sliderValue
```

这个变量保存滑块的值。

如果滑块具有积极的反馈（即，[QAbstractSlider.tracking](qabstractslider.html#tracking-prop)为真） ，则此值将是相同的[sliderPosition](qstyleoptionslider.html#sliderPosition-var)。否则，它的值将鼠标被按下之前，滑块了。

默认值是0。

**See also** [QAbstractSlider.tracking](qabstractslider.html#tracking-prop)和[sliderPosition](qstyleoptionslider.html#sliderPosition-var)。

```
int tickInterval
```

这个变量保存，应该刻度线之间绘制的时间间隔。

默认值是0。

```
QSlider.TickPosition tickPosition
```

[

这个变量保存滑块的刻度线的位置，如果有的话。

](qslider.html#TickPosition-enum)

[缺省值是](qslider.html#TickPosition-enum)[QSlider.NoTicks](qslider.html#TickPosition-enum)。

**See also** [QSlider.TickPosition](qslider.html#TickPosition-enum)。

```
bool upsideDown
```

这个变量保存滑块控件方向。

通常一个滑块随着它向上移动或向右侧; upsideDown表明它应该做相反（增加，因为它移动向下或向左） 。默认值为False，即滑块随着它向上移动或向右移动。

**See also** [QStyle.sliderPositionFromValue](qstyle.html#sliderPositionFromValue)（ ）[QStyle.sliderValueFromPosition](qstyle.html#sliderValueFromPosition)（）和[QAbstractSlider.invertedAppearance](qabstractslider.html#invertedAppearance-prop)。