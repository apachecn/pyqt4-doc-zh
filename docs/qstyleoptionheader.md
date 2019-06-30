# QStyleOptionHeader Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionHeader类是用来描述的参数绘制一个标头。[More...](#details)

继承[QStyleOption](qstyleoption.html)。

### Types

*   `enum SectionPosition { Beginning, Middle, End, OnlyOneSection }`
*   `enum SelectedPosition { NotAdjacent, NextIsSelected, PreviousIsSelected, NextAndPreviousAreSelected }`
*   `enum SortIndicator { None, SortUp, SortDown }`
*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionHeader other)`

### Members

*   `QIcon **[icon](qstyleoptionheader.html#icon-var)**`
*   `Qt.Alignment **[iconAlignment](qstyleoptionheader.html#iconAlignment-var)**`
*   `Qt.Orientation **[orientation](qstyleoptionheader.html#orientation-var)**`
*   `SectionPosition **[position](qstyleoptionheader.html#position-var)**`
*   `int **[section](qstyleoptionheader.html#section-var)**`
*   `SelectedPosition **[selectedPosition](qstyleoptionheader.html#selectedPosition-var)**`
*   `SortIndicator **[sortIndicator](qstyleoptionheader.html#sortIndicator-var)**`
*   `QString **[text](qstyleoptionheader.html#text-var)**`
*   `Qt.Alignment **[textAlignment](qstyleoptionheader.html#textAlignment-var)**`

* * *

## Detailed Description

该QStyleOptionHeader类是用来描述的参数绘制一个标头。

QStyleOptionHeader包含的所有信息，[QStyle](qstyle.html)功能需要借助该项目的意见“标题窗格中，头排序箭头，标题标籤。

出于性能方面的原因，访问成员变量是直接的（即使用`.` or `-&gt;`操作符）。这种低层次的感觉，使结构简单的使用，并强调这些只是所用的样式函数的参数。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionHeader.SectionPosition
```

这个枚举让你知道哪里有部分的位置是相对于其他部分。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionHeader.Beginning` | `0` | 在头部的beginining |
| `QStyleOptionHeader.Middle` | `1` | 在标题中的中间 |
| `QStyleOptionHeader.End` | `2` | 在报头的末尾 |
| `QStyleOptionHeader.OnlyOneSection` | `3` | 只有一个头节 |

**See also** [position](qstyleoptionheader.html#position-var)。

```
QStyleOptionHeader.SelectedPosition
```

这个枚举让你知道哪里有部分的立场是相对于选定的部分。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionHeader.NotAdjacent` | `0` | 不相邻的选定部分 |
| `QStyleOptionHeader.NextIsSelected` | `1` | 接下来的部分被选择 |
| `QStyleOptionHeader.PreviousIsSelected` | `2` | 在上一节中选择 |
| `QStyleOptionHeader.NextAndPreviousAreSelected` | `3` | 无论是下一个和前一节被选中 |

**See also** [selectedPosition](qstyleoptionheader.html#selectedPosition-var)。

```
QStyleOptionHeader.SortIndicator
```

指示哪个方向排序指标应绘制

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionHeader.None` | `0` | 没有排序的指标是必要的 |
| `QStyleOptionHeader.SortUp` | `1` | 绘制了指标 |
| `QStyleOptionHeader.SortDown` | `2` | 画一个向下的指标 |

**See also** [sortIndicator](qstyleoptionheader.html#sortIndicator-var)。

```
QStyleOptionHeader.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionHeader.Type` | `SO_Header` | 风格选择该类型提供（[SO_Header](qstyleoption.html#OptionType-enum)这个类） 。 |

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstyleoptionheader.html#StyleOptionVersion-enum)。

```
QStyleOptionHeader.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionHeader.Version` | `1` | 1 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptionheader.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionHeader.__init__ (self)
```

构造一个[QStyleOptionHeader](qstyleoptionheader.html)，初始化成员变量，它们的默认值。

```
QStyleOptionHeader.__init__ (self, QStyleOptionHeader other)
```

构造的一个副本_other_样式选项。

* * *

## Member Documentation

```
QIcon icon
```

[

这个变量保存了头的图标。

默认值是一个空的图标，即与既不是像素图，也不是一个文件名的图标。

](qicon.html)

```
Qt.Alignment iconAlignment
```

[

这个变量保存了头的图标对齐标志。

](index.htm)

[缺省值是](index.htm)[Qt.AlignLeft](qt.html#AlignmentFlag-enum)。

```
Qt.Orientation orientation
```

[

这个变量保存了头的方向（水平或垂直） 。

](qt.html#Orientation-enum)

[默认的方向是](qt.html#Orientation-enum)[Qt.Horizontal](qt.html#Orientation-enum)

```
SectionPosition position
```

[

这个变量保存在相对于其他部分的部分的位置。

](qstyleoptionheader.html#SectionPosition-enum)

[缺省值是](qstyleoptionheader.html#SectionPosition-enum)[QStyleOptionHeader.Beginning](qstyleoptionheader.html#SectionPosition-enum)。

```
int section
```

这个变量保存它的报头部分被绘制。

默认值是0。

```
SelectedPosition selectedPosition
```

[

这个变量保存在关系到选定的部分区段的位置。

](qstyleoptionheader.html#SelectedPosition-enum)

[缺省值是](qstyleoptionheader.html#SelectedPosition-enum)[QStyleOptionHeader.NotAdjacent](qstyleoptionheader.html#SelectedPosition-enum)

```
SortIndicator sortIndicator
```

[

这个变量保存的方向排序指标应绘制。

](qstyleoptionheader.html#SortIndicator-enum)

[缺省值是](qstyleoptionheader.html#SortIndicator-enum)[QStyleOptionHeader.None](qstyleoptionheader.html#SortIndicator-enum)。

```
QString text
```

这个变量保存标题的文本。

默认值是一个空字符串。

```
Qt.Alignment textAlignment
```

[

这个变量保存为标题的文本对齐标志。

](index.htm)

[缺省值是](index.htm)[Qt.AlignLeft](qt.html#AlignmentFlag-enum)。