# QStyleOptionProgressBar Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionProgressBar类用于描述绘制一个进度条所必需的参数。[More...](#details)

继承[QStyleOption](qstyleoption.html)。

通过继承[QStyleOptionProgressBarV2](qstyleoptionprogressbarv2.html)。

### Types

*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionProgressBar other)`

### Members

*   `int **[maximum](qstyleoptionprogressbar.html#maximum-var)**`
*   `int **[minimum](qstyleoptionprogressbar.html#minimum-var)**`
*   `int **[progress](qstyleoptionprogressbar.html#progress-var)**`
*   `QString **[text](qstyleoptionprogressbar.html#text-var)**`
*   `Qt.Alignment **[textAlignment](qstyleoptionprogressbar.html#textAlignment-var)**`
*   `bool **[textVisible](qstyleoptionprogressbar.html#textVisible-var)**`

* * *

## Detailed Description

该QStyleOptionProgressBar类用于描述绘制一个进度条所必需的参数。

由于Qt的4.1 ， Qt使用[QStyleOptionProgressBarV2](qstyleoptionprogressbarv2.html)子类的绘图[QProgressBar](qprogressbar.html)。

该QStyleOptionProgressBar类的实例的类型[SO_ProgressBar](qstyleoption.html#OptionType-enum)和版本1 。

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

如果您创建自己的[QStyle](qstyle.html)子类，你应该同时处理QStyleOptionProgressBar和[QStyleOptionProgressBarV2](qstyleoptionprogressbarv2.html)。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionProgressBar.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionProgressBar.Type` | `SO_ProgressBar` | 风格选择该类型提供（[SO_ProgressBar](qstyleoption.html#OptionType-enum)这个类） 。 |

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstyleoptionprogressbar.html#StyleOptionVersion-enum)。

```
QStyleOptionProgressBar.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionProgressBar.Version` | `1` | 1 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptionprogressbar.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionProgressBar.__init__ (self)
```

构造一个[QStyleOptionProgressBar](qstyleoptionprogressbar.html)，初始化成员变量，它们的默认值。

```
QStyleOptionProgressBar.__init__ (self, QStyleOptionProgressBar other)
```

构造的一个副本_other_样式选项。

* * *

## Member Documentation

```
int maximum
```

这个变量保存进度条的最大值。

这是在进度条的最大值。默认值是0。

**See also** [QProgressBar.maximum](qprogressbar.html#maximum-prop)。

```
int minimum
```

这个变量保存进度条的最小值。

这是在进度条的最小值。默认值是0。

**See also** [QProgressBar.minimum](qprogressbar.html#minimum-prop)。

```
int progress
```

这个变量保存进度条的当前进度。

目前的进展。的值[QStyleOptionProgressBar.minimum](qstyleoptionprogressbar.html#minimum-var) - 1表示该进程尚未开始。默认值是0。

**See also** [QProgressBar.value](qprogressbar.html#value-prop)。

```
QString text
```

这个变量保存的文本进度条。

进度条的文本通常只是进度表示为一个字符串。一个空的字符串表示进度条尚未开始。默认值是一个空字符串。

**See also** [QProgressBar.text](qprogressbar.html#text-prop)。

```
Qt.Alignment textAlignment
```

[

这个变量保存的文本对齐方式在QProgressBar的文字。

](index.htm)

[这可以作为在该处的文本应在进度条的指南。缺省值是](index.htm)[Qt.AlignLeft](qt.html#AlignmentFlag-enum)。

```
bool textVisible
```

这个变量保存一个标志，指示文本是否是可见的。

如果此标志为True，则文本是可见的。否则，文本是不可见的。默认值是False 。

**See also** [QProgressBar.textVisible](qprogressbar.html#textVisible-prop)。