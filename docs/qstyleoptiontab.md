# QStyleOptionTab Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionTab类是用来描述参数绘制一个标籤栏。[More...](#details)

继承[QStyleOption](qstyleoption.html)。

通过继承[QStyleOptionTabV2](qstyleoptiontabv2.html)。

### Types

*   `enum CornerWidget { NoCornerWidgets, LeftCornerWidget, RightCornerWidget }`
*   `class **[CornerWidgets](index.htm)**`
*   `enum SelectedPosition { NotAdjacent, NextIsSelected, PreviousIsSelected }`
*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`
*   `enum TabPosition { Beginning, Middle, End, OnlyOneTab }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionTab other)`

### Members

*   `CornerWidgets **[cornerWidgets](qstyleoptiontab.html#cornerWidgets-var)**`
*   `QIcon **[icon](qstyleoptiontab.html#icon-var)**`
*   `TabPosition **[position](qstyleoptiontab.html#position-var)**`
*   `int **[row](qstyleoptiontab.html#row-var)**`
*   `SelectedPosition **[selectedPosition](qstyleoptiontab.html#selectedPosition-var)**`
*   `QTabBar.Shape **[shape](qstyleoptiontab.html#shape-var)**`
*   `QString **[text](qstyleoptiontab.html#text-var)**`

* * *

## Detailed Description

该QStyleOptionTab类是用来描述参数绘制一个标籤栏。

该QStyleOptionTab类用于绘制几个内置的Qt部件包括[QTabBar](qtabbar.html)和面板[QTabWidget](qtabwidget.html)。需要注意的是描述绘制在Qt的4.1或以上的一帧所必需的参数，你必须使用[QStyleOptionFrameV2](qstyleoptionframev2.html)子类。

该QStyleOptiontabV2类的实例有[type](qstyleoption.html#type-varx) [SO_Tab](qstyleoption.html#OptionType-enum)和[version](qstyleoption.html#version-var)1 。该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

如果您创建自己的[QStyle](qstyle.html)子类，你应该同时处理QStyleOptionTab和[QStyleOptionTabV2](qstyleoptiontabv2.html)。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionTab.CornerWidget
```

这些标志表明了标籤的角落的小部件。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionTab.NoCornerWidgets` | `0x00` | 有没有角落的小部件 |
| `QStyleOptionTab.LeftCornerWidget` | `0x01` | 左上角小工具 |
| `QStyleOptionTab.RightCornerWidget` | `0x02` | 右上角的小工具 |

该CornerWidgets类型是一个typedef为[QFlags](index.htm)\u003cCornerWidget\u003e 。它存储CornerWidget值的或组合。

**See also** [cornerWidgets](qstyleoptiontab.html#cornerWidgets-var)。

```
QStyleOptionTab.SelectedPosition
```

这个枚举说明所选选项卡的位置。有些款式需要绘制标籤不同，这取决于它是否是相邻的选定的选项卡。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionTab.NotAdjacent` | `0` | 该标籤是不相邻的选定选项卡（或为选定的选项卡） 。 |
| `QStyleOptionTab.NextIsSelected` | `1` | 下一个标籤（通常在右边的选项卡）被选中。 |
| `QStyleOptionTab.PreviousIsSelected` | `2` | 前一个标籤（通常在左侧的标籤）被选中。 |

**See also** [selectedPosition](qstyleoptiontab.html#selectedPosition-var)。

```
QStyleOptionTab.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionTab.Type` | `SO_Tab` | 风格选择该类型提供（[SO_Tab](qstyleoption.html#OptionType-enum)这个类） 。 |

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstyleoptiontab.html#StyleOptionVersion-enum)。

```
QStyleOptionTab.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionTab.Version` | `1` | 1 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptiontab.html#StyleOptionType-enum)。

```
QStyleOptionTab.TabPosition
```

这个枚举变量描述标籤的位置。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionTab.Beginning` | `0` | 该标籤是在标籤栏的第一个选项卡。 |
| `QStyleOptionTab.Middle` | `1` | 该选项卡既不是第一个也不在标籤栏的最后一个标籤。 |
| `QStyleOptionTab.End` | `2` | 该标籤是在标籤栏的最后一个标籤。 |
| `QStyleOptionTab.OnlyOneTab` | `3` | 该标籤是第一个和在标籤栏的最后一个标籤。 |

**See also** [position](qstyleoptiontab.html#position-var)。

* * *

## Method Documentation

```
QStyleOptionTab.__init__ (self)
```

构造一个[QStyleOptionTab](qstyleoptiontab.html)对象，初始化成员变量，它们的默认值。

```
QStyleOptionTab.__init__ (self, QStyleOptionTab other)
```

构造的一个副本_other_样式选项。

* * *

## Member Documentation

```
CornerWidgets cornerWidgets
```

[

这个变量保存CornerWidget值显示标籤栏的角落的小部件的一个或组合。

](index.htm)

[缺省值是](index.htm)[NoCornerWidgets](qstyleoptiontab.html#CornerWidget-enum)。

**See also** [CornerWidget](qstyleoptiontab.html#CornerWidget-enum)。

```
QIcon icon
```

[

这个变量保存为标籤的图标。

默认值是一个空的图标，即与既不是像素图，也不是一个文件名的图标。

](qicon.html)

```
TabPosition position
```

[

这个变量保存在标籤栏的标籤的位置。

](qstyleoptiontab.html#TabPosition-enum)

[缺省值是](qstyleoptiontab.html#TabPosition-enum)[Beginning](qstyleoptiontab.html#TabPosition-enum)，即标籤是在标籤栏的第一个选项卡。

```
int row
```

这个变量保存哪一行的标籤当前所在

缺省值是0，表示在前排。目前，这个属性只能是0 。

```
SelectedPosition selectedPosition
```

[

这个变量保存选定的选项卡中有关此选项卡的位置。

](qstyleoptiontab.html#SelectedPosition-enum)

[缺省值是](qstyleoptiontab.html#SelectedPosition-enum)[NotAdjacent](qstyleoptiontab.html#SelectedPosition-enum)，即标籤是不相邻的选定选项卡，也不是选定的选项卡。

```
QTabBar.Shape shape
```

[

这个变量保存用于绘制选项卡的标籤形状，默认情况下QTabBar.RoundedNorth 。

](qtabbar.html#Shape-enum)

[**See also**](qtabbar.html#Shape-enum) [QTabBar.Shape](qtabbar.html#Shape-enum)。

```
QString text
```

这个变量保存标籤的文本。

默认值是一个空字符串。