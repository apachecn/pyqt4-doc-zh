# QStyleOptionProgressBarV2 Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionProgressBarV2类是用来描述绘制在Qt的4.1或以上的一个进度条所必需的参数。[More...](#details)

继承[QStyleOptionProgressBar](qstyleoptionprogressbar.html)。

### Types

*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionProgressBar other)`
*   `__init__ (self, QStyleOptionProgressBarV2 other)`

### Members

*   `bool **[bottomToTop](qstyleoptionprogressbarv2.html#bottomToTop-var)**`
*   `bool **[invertedAppearance](qstyleoptionprogressbarv2.html#invertedAppearance-var)**`
*   `Qt.Orientation **[orientation](qstyleoptionprogressbarv2.html#orientation-var)**`

* * *

## Detailed Description

该QStyleOptionProgressBarV2类是用来描述绘制在Qt的4.1或以上的一个进度条所必需的参数。

这个类的一个实例有[type](qstyleoption.html#type-varx) [SO_ProgressBar](qstyleoption.html#OptionType-enum)和[version](qstyleoption.html#version-var)2 。

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

如果您创建自己的[QStyle](qstyle.html)子类，你应该同时处理[QStyleOptionProgressBar](qstyleoptionprogressbar.html)和QStyleOptionProgressBarV2 。实现这一目标的方法之一是使用QStyleOptionProgressBarV2拷贝构造函数。例如：

```
     if (const [QStyleOptionProgressBar](qstyleoptionprogressbar.html) *progressBarOption =
            qstyleoption_cast<const [QStyleOptionProgressBar](qstyleoptionprogressbar.html) *>(option)) {
         QStyleOptionProgressBarV2 progressBarV2(*progressBarOption);

         // draw the progress bar using progressBarV2
     }

```

在上面的例子：如果`progressBarOption`的版本为1时，额外的部件（[orientation](qstyleoptionprogressbarv2.html#orientation-var)，[invertedAppearance](qstyleoptionprogressbarv2.html#invertedAppearance-var)和[bottomToTop](qstyleoptionprogressbarv2.html#bottomToTop-var)）被设置为默认值`progressBarV2`。如果`progressBarOption`的版本是2 ，构造简单地将多馀的成员复制到progressBarV2 。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionProgressBarV2.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionProgressBarV2.Type` | `SO_ProgressBar` | 风格选择该类型提供（[SO_ProgressBar](qstyleoption.html#OptionType-enum)这个类） 。 |

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstyleoptionprogressbarv2.html#StyleOptionVersion-enum)。

```
QStyleOptionProgressBarV2.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionProgressBarV2.Version` | `2` | 2 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptionprogressbarv2.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionProgressBarV2.__init__ (self)
```

构造一个[QStyleOptionProgressBarV2](qstyleoptionprogressbarv2.html)，他初始化成员变量，它们的默认值。

```
QStyleOptionProgressBarV2.__init__ (self, QStyleOptionProgressBar other)
```

构造的一个副本_other_它可以是风格的选择[QStyleOptionProgressBar](qstyleoptionprogressbar.html)和[QStyleOptionProgressBarV2](qstyleoptionprogressbarv2.html)类型。

如果_other_样式选项的版本为1 ，额外成员（[orientation](qstyleoptionprogressbarv2.html#orientation-var)，[invertedAppearance](qstyleoptionprogressbarv2.html#invertedAppearance-var)和[bottomToTop](qstyleoptionprogressbarv2.html#bottomToTop-var)）被设置为默认值的新样式选项。如果_other_的版本是2 ，额外的成员是简单地复制。

**See also** [version](qstyleoption.html#version-var)。

```
QStyleOptionProgressBarV2.__init__ (self, QStyleOptionProgressBarV2 other)
```

构造的一个副本_other_样式选项。

* * *

## Member Documentation

```
bool bottomToTop
```

这个变量保存的文本是否从底部读取到顶部时，进度条是垂直的。

默认值是False 。

**See also** [QProgressBar.textDirection](qprogressbar.html#textDirection-prop)。

```
bool invertedAppearance
```

这个变量保存进度条的外观是否反转。

默认值是False 。

**See also** [QProgressBar.invertedAppearance](qprogressbar.html#invertedAppearance-prop)。

```
Qt.Orientation orientation
```

[

这个变量保存进度条的方向（水平或垂直） ，默认orentation是Qt.Horizontal 。

](qt.html#Orientation-enum)

[**See also**](qt.html#Orientation-enum) [QProgressBar.orientation](qprogressbar.html#orientation-prop)。