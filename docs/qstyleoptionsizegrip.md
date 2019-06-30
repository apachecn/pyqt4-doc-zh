# QStyleOptionSizeGrip Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionSizeGrip类是用来描述参数绘制一个大小手柄。[More...](#details)

继承[QStyleOptionComplex](qstyleoptioncomplex.html)。

### Types

*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionSizeGrip other)`

### Members

*   `Qt.Corner **[corner](qstyleoptionsizegrip.html#corner-var)**`

* * *

## Detailed Description

该QStyleOptionSizeGrip类是用来描述参数绘制一个大小手柄。

[QStyleOptionButton](qstyleoptionbutton.html)包含的所有信息，[QStyle](qstyle.html)功能需要绘制[QSizeGrip](qsizegrip.html)。

出于性能方面的原因，访问成员变量是直接的（即使用`.` or `-&gt;`操作符）。这种低层次的感觉，使结构简单的使用，并强调这些只是所用的样式函数的参数。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionSizeGrip.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionSizeGrip.Type` | `SO_SizeGrip` | 风格选择该类型提供（[SO_TabBarBase](qstyleoption.html#OptionType-enum)这个类） 。 |

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstyleoptionsizegrip.html#StyleOptionVersion-enum)。

```
QStyleOptionSizeGrip.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionSizeGrip.Version` | `1` | 1 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptionsizegrip.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionSizeGrip.__init__ (self)
```

构造一个[QStyleOptionSizeGrip](qstyleoptionsizegrip.html)。

```
QStyleOptionSizeGrip.__init__ (self, QStyleOptionSizeGrip other)
```

构造的一个副本_other_样式选项。

* * *

## Member Documentation

```
Qt.Corner corner
```

[

其中大小手柄所在的角落。

](qt.html#Corner-enum)