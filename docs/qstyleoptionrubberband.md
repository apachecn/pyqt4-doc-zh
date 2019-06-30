# QStyleOptionRubberBand Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionRubberBand类是用来描述需要绘制橡皮筋的参数。[More...](#details)

继承[QStyleOption](qstyleoption.html)。

### Types

*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionRubberBand other)`

### Members

*   `bool **[opaque](qstyleoptionrubberband.html#opaque-var)**`
*   `QRubberBand.Shape **[shape](qstyleoptionrubberband.html#shape-var)**`

* * *

## Detailed Description

该QStyleOptionRubberBand类是用来描述需要绘制橡皮筋的参数。

QStyleOptionRubberBand包含的所有信息，[QStyle](qstyle.html)功能需要绘制[QRubberBand](qrubberband.html)。

出于性能方面的原因，访问成员变量是直接的（即使用`.` or `-&gt;`操作符）。这种低层次的感觉，使结构简单的使用，并强调这些只是所用的样式函数的参数。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionRubberBand.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionRubberBand.Type` | `SO_RubberBand` | 风格选择该类型提供（[SO_RubberBand](qstyleoption.html#OptionType-enum)这个类） 。 |

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstyleoptionrubberband.html#StyleOptionVersion-enum)。

```
QStyleOptionRubberBand.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionRubberBand.Version` | `1` | 1 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptionrubberband.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionRubberBand.__init__ (self)
```

创建[QStyleOptionRubberBand](qstyleoptionrubberband.html)，初始化成员变量，它们的默认值。

```
QStyleOptionRubberBand.__init__ (self, QStyleOptionRubberBand other)
```

构造的一个副本_other_样式选项。

* * *

## Member Documentation

```
bool opaque
```

这个变量保存是否需要橡皮筋在一个不透明的风格绘制。

默认值是True 。

```
QRubberBand.Shape shape
```

[

这个变量保存橡皮筋的形状。

](qrubberband.html#Shape-enum)

[默认的形状](qrubberband.html#Shape-enum)[QRubberBand.Line](qrubberband.html#Shape-enum)。