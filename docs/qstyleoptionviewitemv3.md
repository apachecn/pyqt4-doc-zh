# QStyleOptionViewItemV3 Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionViewItemV3类是用来描述用于绘制Qt中4.3或更高的帧所必需的参数。[More...](#details)

继承[QStyleOptionViewItemV2](qstyleoptionviewitemv2.html)。

通过继承[QStyleOptionViewItemV4](qstyleoptionviewitemv4.html)。

### Types

*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionViewItemV3 other)`
*   `__init__ (self, QStyleOptionViewItem other)`

### Members

*   `QLocale **[locale](qstyleoptionviewitemv3.html#locale-var)**`

### Static Members

*   `QWidget **[widget](qstyleoptionviewitemv3.html#widget-var)**`

* * *

## Detailed Description

该QStyleOptionViewItemV3类是用来描述用于绘制Qt中4.3或更高的帧所必需的参数。

QStyleOptionViewItemV3继承[QStyleOptionViewItem](qstyleoptionviewitem.html)。

该QStyleOptionViewItemV3类的实例有[type](qstyleoption.html#type-varx) [SO_ViewItem](qstyleoption.html#OptionType-enum)和[version](qstyleoption.html#version-var)3 。该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

See [QStyleOptionFrameV2](qstyleoptionframev2.html)的详细说明如何处理“V2”和其他版本的类的讨论。

* * *

## Type Documentation

```
QStyleOptionViewItemV3.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionViewItemV3.Version` | `3` | 3 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptionviewitem.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionViewItemV3.__init__ (self)
```

构造一个[QStyleOptionViewItemV3](qstyleoptionviewitemv3.html)对象。

```
QStyleOptionViewItemV3.__init__ (self, QStyleOptionViewItemV3 other)
```

构造的副本_other_。

```
QStyleOptionViewItemV3.__init__ (self, QStyleOptionViewItem other)
```

构造的副本_other_。

* * *

## Member Documentation

```
QLocale locale
```

[](qlocale.html)

```
QWidget widget
```

[

此构件应被视为常数。

](qwidget.html)