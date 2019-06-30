# QStyleOptionViewItemV2 Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionViewItemV2类是用来描述用于绘制Qt中4.2或更高的帧所必需的参数。[More...](#details)

继承[QStyleOptionViewItem](qstyleoptionviewitem.html)。

通过继承[QStyleOptionViewItemV3](qstyleoptionviewitemv3.html)。

### Types

*   `enum StyleOptionVersion { Version }`
*   `enum ViewItemFeature { None, WrapText, Alternate, HasCheckIndicator, HasDisplay, HasDecoration }`
*   `class **[ViewItemFeatures](index.htm)**`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionViewItemV2 other)`
*   `__init__ (self, QStyleOptionViewItem other)`

### Members

*   `ViewItemFeatures **[features](qstyleoptionviewitemv2.html#features-var)**`

* * *

## Detailed Description

该QStyleOptionViewItemV2类是用来描述用于绘制Qt中4.2或更高的帧所必需的参数。

QStyleOptionViewItemV2继承[QStyleOptionViewItem](qstyleoptionviewitem.html)。

该QStyleOptionViewItemV2类的实例有[type](qstyleoption.html#type-varx) [SO_ViewItem](qstyleoption.html#OptionType-enum)和[version](qstyleoption.html#version-var)2 。该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

See [QStyleOptionFrameV2](qstyleoptionframev2.html)的详细说明如何处理“V2”类的讨论。

* * *

## Type Documentation

```
QStyleOptionViewItemV2.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionViewItemV2.Version` | `2` | 2 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptionviewitem.html#StyleOptionType-enum)。

```
QStyleOptionViewItemV2.ViewItemFeature
```

这个枚举变量描述了不同类型的功能，一个项目可以有。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionViewItemV2.None` | `0x00` | 表示正常的项目。 |
| `QStyleOptionViewItemV2.WrapText` | `0x01` | 表示有换行文本的项目。 |
| `QStyleOptionViewItemV2.Alternate` | `0x02` | 表示该项目的背景是使用alternateBase呈现。 |
| `QStyleOptionViewItemV2.HasCheckIndicator` | `0x04` | 表示该项目具有检查状态指示灯。 |
| `QStyleOptionViewItemV2.HasDisplay` | `0x08` | 表示该项目具有显示作用。 |
| `QStyleOptionViewItemV2.HasDecoration` | `0x10` | 表示该项目具有装饰作用。 |

该ViewItemFeatures类型是一个typedef为[QFlags](index.htm)\u003cViewItemFeature\u003e 。它存储ViewItemFeature值的或组合。

* * *

## Method Documentation

```
QStyleOptionViewItemV2.__init__ (self)
```

构造一个[QStyleOptionViewItemV2](qstyleoptionviewitemv2.html)对象。

```
QStyleOptionViewItemV2.__init__ (self, QStyleOptionViewItemV2 other)
```

构造的副本_other_。

```
QStyleOptionViewItemV2.__init__ (self, QStyleOptionViewItem other)
```

构造一个[QStyleOptionViewItemV2](qstyleoptionviewitemv2.html)副本_other_它可以是风格的选择[QStyleOptionViewItemV2](qstyleoptionviewitemv2.html) or [QStyleOptionViewItem](qstyleoptionviewitem.html)类型。

如果_other_风格选择的版本是1 ，新样式选项的[ViewItemFeature](qstyleoptionviewitemv2.html#ViewItemFeature-enum)值被设置为[QStyleOptionViewItemV2.None](qstyleoptionviewitemv2.html#ViewItemFeature-enum)。如果它的版本为2时，其[ViewItemFeature](qstyleoptionviewitemv2.html#ViewItemFeature-enum)值被简单地复制到新的样式选项。

**See also** [version](qstyleoption.html#version-var)。

* * *

## Member Documentation

```
ViewItemFeatures features
```

[

这个变量保存的是描述这个视图项功能按位或。

](index.htm)

[**See also**](index.htm) [ViewItemFeature](qstyleoptionviewitemv2.html#ViewItemFeature-enum)。