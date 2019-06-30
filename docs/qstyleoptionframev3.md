# QStyleOptionFrameV3 Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionFrameV3类是用来描述用于绘制Qt中4.1或更高的帧所必需的参数。[More...](#details)

继承[QStyleOptionFrameV2](qstyleoptionframev2.html)。

### Types

*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionFrameV3 other)`
*   `__init__ (self, QStyleOptionFrame other)`

### Members

*   `QFrame.Shape **[frameShape](qstyleoptionframev3.html#frameShape-var)**`
*   `int **[unused](qstyleoptionframev3.html#unused-var)**`

* * *

## Detailed Description

该QStyleOptionFrameV3类是用来描述用于绘制Qt中4.1或更高的帧所必需的参数。

QStyleOptionFrameV3继承[QStyleOptionFrameV2](qstyleoptionframev2.html)

该QStyleOptionFrameV3类的实例有[type](qstyleoption.html#type-varx) [SO_Frame](qstyleoption.html#OptionType-enum)和[version](qstyleoption.html#version-var)3 。该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

* * *

## Type Documentation

```
QStyleOptionFrameV3.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionFrameV3.Version` | `3` | 3 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptionframe.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionFrameV3.__init__ (self)
```

构造一个[QStyleOptionFrameV3](qstyleoptionframev3.html)对象。

```
QStyleOptionFrameV3.__init__ (self, QStyleOptionFrameV3 other)
```

构造一个[QStyleOptionFrameV3](qstyleoptionframev3.html)副本_other_样式选项。

```
QStyleOptionFrameV3.__init__ (self, QStyleOptionFrame other)
```

构造一个[QStyleOptionFrameV3](qstyleoptionframev3.html)副本_other_它可以是风格的选择[QStyleOptionFrameV3](qstyleoptionframev3.html) or [QStyleOptionFrame](qstyleoptionframe.html)类型。

如果_other_风格选择的版本是1 ，新样式选项的[FrameFeature](qstyleoptionframev2.html#FrameFeature-enum)值被设置为[QStyleOptionFrameV2.None](qstyleoptionframev2.html#FrameFeature-enum)。如果它的版本号为2或更低，[QStyleOptionFrameV3.frameShape](qstyleoptionframev3.html#frameShape-var)值[QFrame.NoFrame](qframe.html#Shape-enum)

**See also** [version](qstyleoption.html#version-var)。

* * *

## Member Documentation

```
QFrame.Shape frameShape
```

[

这个变量保存这个属性保存的是帧的帧形状值。

](qframe.html#Shape-enum)

[**See also**](qframe.html#Shape-enum) [QFrame.frameShape](qframe.html#frameShape-prop)。

```
int unused
```