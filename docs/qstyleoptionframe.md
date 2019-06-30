# QStyleOptionFrame Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionFrame类是用来描述的参数绘制的帧。[More...](#details)

继承[QStyleOption](qstyleoption.html)。

通过继承[QStyleOptionFrameV2](qstyleoptionframev2.html)。

### Types

*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionFrame other)`

### Members

*   `int **[lineWidth](qstyleoptionframe.html#lineWidth-var)**`
*   `int **[midLineWidth](qstyleoptionframe.html#midLineWidth-var)**`

* * *

## Detailed Description

该QStyleOptionFrame类是用来描述的参数绘制的帧。

QStyleOptionFrame用于绘制几个内置的Qt部件，包括[QFrame](qframe.html)，[QGroupBox](qgroupbox.html)，[QLineEdit](qlineedit.html)和[QMenu](qmenu.html)。需要注意的是描述绘制在Qt的4.1或以上的一帧所必需的参数，你必须使用[QStyleOptionFrameV2](qstyleoptionframev2.html)子类。

该QStyleOptionFrame类的实例有[type](qstyleoption.html#type-varx) [SO_Frame](qstyleoption.html#OptionType-enum)和[version](qstyleoption.html#version-var)1 。

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

如果您创建自己的[QStyle](qstyle.html)子类，你应该同时处理QStyleOptionFrame和[QStyleOptionFrameV2](qstyleoptionframev2.html)。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionFrame.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionFrame.Type` | `SO_Frame` | 风格选择该类型提供（[SO_Frame](qstyleoption.html#OptionType-enum)这个类） 。 |

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstyleoptionframe.html#StyleOptionVersion-enum)。

```
QStyleOptionFrame.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionFrame.Version` | `1` | 1 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptionframe.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionFrame.__init__ (self)
```

构造一个[QStyleOptionFrame](qstyleoptionframe.html)，初始化成员变量，它们的默认值。

```
QStyleOptionFrame.__init__ (self, QStyleOptionFrame other)
```

构造的一个副本_other_样式选项。

* * *

## Member Documentation

```
int lineWidth
```

这个变量保存线宽绘制框架。

默认值是0。

**See also** [QFrame.lineWidth](qframe.html#lineWidth-prop)。

```
int midLineWidth
```

这个变量保存中间线宽绘制框架。

这通常用于绘制沉船或凸起的框架。

默认值是0。

**See also** [QFrame.midLineWidth](qframe.html#midLineWidth-prop)。