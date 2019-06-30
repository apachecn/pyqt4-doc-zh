# QStyleOptionGroupBox Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionGroupBox类描述的参数绘制一组框。[More...](#details)

继承[QStyleOptionComplex](qstyleoptioncomplex.html)。

### Types

*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionGroupBox other)`

### Members

*   `QStyleOptionFrameV2.FrameFeatures **[features](qstyleoptiongroupbox.html#features-var)**`
*   `int **[lineWidth](qstyleoptiongroupbox.html#lineWidth-var)**`
*   `int **[midLineWidth](qstyleoptiongroupbox.html#midLineWidth-var)**`
*   `QString **[text](qstyleoptiongroupbox.html#text-var)**`
*   `Qt.Alignment **[textAlignment](qstyleoptiongroupbox.html#textAlignment-var)**`
*   `QColor **[textColor](qstyleoptiongroupbox.html#textColor-var)**`

* * *

## Detailed Description

该QStyleOptionGroupBox类描述的参数绘制一组框。

[QStyleOptionButton](qstyleoptionbutton.html)包含的所有信息，[QStyle](qstyle.html)函数需要一个组合框的各种图形元素。

它拥有的[lineWidth](qstyleoptiongroupbox.html#lineWidth-var)和[midLineWidth](qstyleoptiongroupbox.html#midLineWidth-var)绘制面板，组框的[title](qstyleoptiongroupbox.html#text-var)和标题的[alignment](qstyleoptiongroupbox.html#textAlignment-var)和[color](qstyleoptiongroupbox.html#textColor-var)。

出于性能方面的原因，访问成员变量是直接的（即使用`.` or `-&gt;`操作符）。这种低层次的感觉，使结构简单的使用，并强调这些只是所用的样式函数的参数。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionGroupBox.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionGroupBox.Type` | `SO_GroupBox` | 风格选择该类型提供（[SO_GroupBox](qstyleoption.html#OptionType-enum)这个类） 。 |

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstyleoptiongroupbox.html#StyleOptionVersion-enum)。

```
QStyleOptionGroupBox.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionGroupBox.Version` | `1` | 1 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptiongroupbox.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionGroupBox.__init__ (self)
```

构造一个[QStyleOptionGroupBox](qstyleoptiongroupbox.html)，初始化成员变量，它们的默认值。

```
QStyleOptionGroupBox.__init__ (self, QStyleOptionGroupBox other)
```

构造的一个副本_other_样式选项。

* * *

## Member Documentation

```
QStyleOptionFrameV2.FrameFeatures features
```

[

这个变量保存了组框框架的功能。

该框架是平的默认。

](index.htm)

[**See also**](index.htm) [QStyleOptionFrameV2.FrameFeature](qstyleoptionframev2.html#FrameFeature-enum)。

```
int lineWidth
```

这个变量保存线宽绘制面板。

这个变量的值是，目前，始终为1 。

**See also** [QFrame.lineWidth](qframe.html#lineWidth-prop)。

```
int midLineWidth
```

这个变量保存中间线宽绘制面板。

中线宽度通常用于绘图凹陷或凸起的组框框架时。这个变量的值是，目前，始终为0 。

**See also** [QFrame.midLineWidth](qframe.html#midLineWidth-prop)。

```
QString text
```

这个变量保存组框的文本。

默认值是一个空字符串。

**See also** [QGroupBox.title](qgroupbox.html#title-prop)。

```
Qt.Alignment textAlignment
```

[

这个变量保存的分组框标题的对齐方式。

](index.htm)

[缺省值是](index.htm)[Qt.AlignLeft](qt.html#AlignmentFlag-enum)。

**See also** [QGroupBox.alignment](qgroupbox.html#alignment-prop)。

```
QColor textColor
```

[

这个变量保存的分组框标题的颜色。

默认值是无效的颜色的RGB值（0，0 ，0）。无效的颜色是没有正确设置为底层窗口系统的颜色。

](qcolor.html)