# QStyleOptionToolBoxV2 Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionToolBoxV2类是用来描述用于绘制Qt中4.3或更高的帧所必需的参数。[More...](#details)

继承[QStyleOptionToolBox](qstyleoptiontoolbox.html)。

### Types

*   `enum SelectedPosition { NotAdjacent, NextIsSelected, PreviousIsSelected }`
*   `enum StyleOptionVersion { Version }`
*   `enum TabPosition { Beginning, Middle, End, OnlyOneTab }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionToolBoxV2 other)`
*   `__init__ (self, QStyleOptionToolBox other)`

### Members

*   `TabPosition **[position](qstyleoptiontoolboxv2.html#position-var)**`
*   `SelectedPosition **[selectedPosition](qstyleoptiontoolboxv2.html#selectedPosition-var)**`

* * *

## Detailed Description

该QStyleOptionToolBoxV2类是用来描述用于绘制Qt中4.3或更高的帧所必需的参数。

QStyleOptionToolBoxV2继承[QStyleOptionToolBox](qstyleoptiontoolbox.html)这是用于绘制的标籤[QToolBox](qtoolbox.html)。

该QStyleOptionToolBoxV2类的实例有[type](qstyleoption.html#type-varx) [SO_ToolBox](qstyleoption.html#OptionType-enum)和[version](qstyleoption.html#version-var)2 。该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

如果您创建自己的[QStyle](qstyle.html)子类，你应该同时处理[QStyleOptionToolBox](qstyleoptiontoolbox.html)和QStyleOptionToolBoxV2 。

* * *

## Type Documentation

```
QStyleOptionToolBoxV2.SelectedPosition
```

这个枚举说明所选选项卡的位置。有些款式需要绘制标籤不同，这取决于它是否是相邻的选定的选项卡。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionToolBoxV2.NotAdjacent` | `0` | 该标籤是不相邻的选定选项卡（或为选定的选项卡） 。 |
| `QStyleOptionToolBoxV2.NextIsSelected` | `1` | 下一个标籤（通常在右边的选项卡）被选中。 |
| `QStyleOptionToolBoxV2.PreviousIsSelected` | `2` | 前一个标籤（通常在左侧的标籤）被选中。 |

**See also** [selectedPosition](qstyleoptiontoolboxv2.html#selectedPosition-var)。

```
QStyleOptionToolBoxV2.StyleOptionVersion
```

这个枚举持有这种风格选项的版本

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionToolBoxV2.Version` | `2` | 2 |

```
QStyleOptionToolBoxV2.TabPosition
```

这个枚举说明相对于其他标籤，标籤的位置。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionToolBoxV2.Beginning` | `0` | 该标籤是工具箱中的第一个（即最顶层）选项卡。 |
| `QStyleOptionToolBoxV2.Middle` | `1` | 该标籤被放置在工具箱的中间。 |
| `QStyleOptionToolBoxV2.End` | `2` | 该标籤被放置在工具箱的底部。 |
| `QStyleOptionToolBoxV2.OnlyOneTab` | `3` | 只有一个工具箱中的选项卡。 |

* * *

## Method Documentation

```
QStyleOptionToolBoxV2.__init__ (self)
```

Contsructs一个[QStyleOptionToolBoxV2](qstyleoptiontoolboxv2.html)对象。

```
QStyleOptionToolBoxV2.__init__ (self, QStyleOptionToolBoxV2 other)
```

构造一个[QStyleOptionToolBoxV2](qstyleoptiontoolboxv2.html)副本_other_样式选项。

```
QStyleOptionToolBoxV2.__init__ (self, QStyleOptionToolBox other)
```

构造一个[QStyleOptionToolBoxV2](qstyleoptiontoolboxv2.html)副本_other_它可以是风格的选择[QStyleOptionToolBoxV2](qstyleoptiontoolboxv2.html) or [QStyleOptionToolBox](qstyleoptiontoolbox.html)类型。

如果_other_风格选择的版本是1 ，新样式选项的[position](qstyleoptiontab.html#position-var)值被设置为[QStyleOptionToolBoxV2.Beginning](qstyleoptiontoolboxv2.html#TabPosition-enum)和[selectedPosition](qstyleoptiontoolboxv2.html#selectedPosition-var)被设置为[QStyleOptionToolBoxV2.NotAdjacent](qstyleoptiontoolboxv2.html#SelectedPosition-enum)。如果它的版本为2，则[position](qstyleoptiontab.html#position-var) [selectedPosition](qstyleoptiontoolboxv2.html#selectedPosition-var)值被简单地复制到新样式选项。

**See also** [version](qstyleoption.html#version-var)。

* * *

## Member Documentation

```
TabPosition position
```

[](qstyleoptiontoolboxv2.html#TabPosition-enum)

```
SelectedPosition selectedPosition
```

[

这个变量保存选定的选项卡中有关此选项卡的位置。

](qstyleoptiontoolboxv2.html#SelectedPosition-enum)

[缺省值是](qstyleoptiontoolboxv2.html#SelectedPosition-enum)[NotAdjacent](qstyleoptiontoolboxv2.html#SelectedPosition-enum)，即标籤是不相邻的选定选项卡，也不是选定的选项卡。