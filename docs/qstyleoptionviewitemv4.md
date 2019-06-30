# QStyleOptionViewItemV4 Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionViewItemV4类是用来描述用于绘制Qt中4.4或更高的帧所必需的参数。[More...](#details)

继承[QStyleOptionViewItemV3](qstyleoptionviewitemv3.html)。

### Types

*   `enum StyleOptionVersion { Version }`
*   `enum ViewItemPosition { Invalid, Beginning, Middle, End, OnlyOne }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionViewItemV4 other)`
*   `__init__ (self, QStyleOptionViewItem other)`

### Members

*   `QBrush **[backgroundBrush](qstyleoptionviewitemv4.html#backgroundBrush-var)**`
*   `Qt.CheckState **[checkState](qstyleoptionviewitemv4.html#checkState-var)**`
*   `QIcon **[icon](qstyleoptionviewitemv4.html#icon-var)**`
*   `QModelIndex **[index](qstyleoptionviewitemv4.html#index-var)**`
*   `QString **[text](qstyleoptionviewitemv4.html#text-var)**`
*   `ViewItemPosition **[viewItemPosition](qstyleoptionviewitemv4.html#viewItemPosition-var)**`

* * *

## Detailed Description

该QStyleOptionViewItemV4类是用来描述用于绘制Qt中4.4或更高的帧所必需的参数。

QStyleOptionViewItemV4继承[QStyleOptionViewItemV3](qstyleoptionviewitemv3.html)。

该QStyleOptionViewItemV4类的实例有[type](qstyleoption.html#type-varx) [SO_ViewItem](qstyleoption.html#OptionType-enum)和[version](qstyleoption.html#version-var)4 。该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

See [QStyleOptionViewItemV3](qstyleoptionviewitemv3.html)的详细说明如何处理“V3 ”类的讨论。

* * *

## Type Documentation

```
QStyleOptionViewItemV4.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionViewItemV4.Version` | `4` | 4 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptionviewitem.html#StyleOptionType-enum)。

```
QStyleOptionViewItemV4.ViewItemPosition
```

此枚举用于表示放置在一排的项目。这可以被用来通过把在开始和结束的圆形边缘和直线边缘之间绘制的项目不同，这取决于它们的位置，例如。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionViewItemV4.Invalid` | `0` | 该ViewItemPosition是未知的，应该被忽视。 |
| `QStyleOptionViewItemV4.Beginning` | `1` | 该项目将显示在该行的开头。 |
| `QStyleOptionViewItemV4.Middle` | `2` | 该项目将出现在该行的中间。 |
| `QStyleOptionViewItemV4.End` | `3` | 该项目将显示在该行的末尾。 |
| `QStyleOptionViewItemV4.OnlyOne` | `4` | 该产品是唯一的行上，因此，既在开头和结尾。 |

* * *

## Method Documentation

```
QStyleOptionViewItemV4.__init__ (self)
```

构造一个[QStyleOptionViewItemV4](qstyleoptionviewitemv4.html)对象。

```
QStyleOptionViewItemV4.__init__ (self, QStyleOptionViewItemV4 other)
```

构造的副本_other_。

```
QStyleOptionViewItemV4.__init__ (self, QStyleOptionViewItem other)
```

构造一个[QStyleOptionViewItemV4](qstyleoptionviewitemv4.html)副本_other_它可以是风格的选择[QStyleOptionViewItemV3](qstyleoptionviewitemv3.html) or [QStyleOptionViewItem](qstyleoptionviewitem.html)类型。

**See also** [version](qstyleoption.html#version-var)。

* * *

## Member Documentation

```
QBrush backgroundBrush
```

[](qbrush.html)

[该](qbrush.html)[QBrush](qbrush.html)应该用来绘制视图中的项目背景。

```
Qt.CheckState checkState
```

[

如果此视图产品可复，即ViewItemFeature.HasCheckIndicator是真实的，`checkState`是真的，如果该项目被选中，否则为假。

](qt.html#CheckState-enum)

```
QIcon icon
```

[

的图标（如果有的话）中的视图项绘制。

](qicon.html)

```
QModelIndex index
```

[

模型索引要被绘制。

```
QString text
```

文本（如果有的话）中的视图项绘制。

](qmodelindex.html)

```
ViewItemPosition viewItemPosition
```

[](qstyleoptionviewitemv4.html#ViewItemPosition-enum)

[给这个视图项的相对位置，以其他项目。请参阅](qstyleoptionviewitemv4.html#ViewItemPosition-enum)[ViewItemPosition](qstyleoptionviewitemv4.html#ViewItemPosition-enum)枚举的细节。