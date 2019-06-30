# QStyleOptionSpinBox Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionSpinBox类用于描述绘制一个微调框必要的参数。[More...](#details)

继承[QStyleOptionComplex](qstyleoptioncomplex.html)。

### Types

*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionSpinBox other)`

### Members

*   `QAbstractSpinBox.ButtonSymbols **[buttonSymbols](qstyleoptionspinbox.html#buttonSymbols-var)**`
*   `bool **[frame](qstyleoptionspinbox.html#frame-var)**`
*   `QAbstractSpinBox.StepEnabled **[stepEnabled](qstyleoptionspinbox.html#stepEnabled-var)**`

* * *

## Detailed Description

该QStyleOptionSpinBox类用于描述绘制一个微调框必要的参数。

QStyleOptionSpinBox包含的所有信息，[QStyle](qstyle.html)功能需要绘制[QSpinBox](qspinbox.html)和[QDateTimeEdit](qdatetimeedit.html)。

出于性能方面的原因，访问成员变量是直接的（即使用`.` or `-&gt;`操作符）。这种低层次的感觉，使结构简单的使用，并强调这些只是所用的样式函数的参数。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionSpinBox.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionSpinBox.Type` | `SO_SpinBox` | 风格选择该类型提供（[SO_SpinBox](qstyleoption.html#OptionType-enum)这个类） 。 |

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstyleoptionspinbox.html#StyleOptionVersion-enum)。

```
QStyleOptionSpinBox.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionSpinBox.Version` | `1` | 1 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptionspinbox.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionSpinBox.__init__ (self)
```

构造一个[QStyleOptionSpinBox](qstyleoptionspinbox.html)，初始化成员变量，它们的默认值。

```
QStyleOptionSpinBox.__init__ (self, QStyleOptionSpinBox other)
```

构造的一个副本_other_样式选项。

* * *

## Member Documentation

```
QAbstractSpinBox.ButtonSymbols buttonSymbols
```

[

这个变量保存按钮的符号绘制的旋转框的类型。

](qabstractspinbox.html#ButtonSymbols-enum)

[缺省值是](qabstractspinbox.html#ButtonSymbols-enum)[QAbstractSpinBox.UpDownArrows](qabstractspinbox.html#ButtonSymbols-enum)specufying小箭头的经典款式。

**See also** [QAbstractSpinBox.ButtonSymbols](qabstractspinbox.html#ButtonSymbols-enum)。

```
bool frame
```

这个变量保存旋转框是否有一个框架。

默认值为False ，即旋转框有没有框架。

```
QAbstractSpinBox.StepEnabled stepEnabled
```

[

这个变量保存已启用的旋转框的哪个按钮。

](index.htm)

[缺省值是](index.htm)[QAbstractSpinBox.StepNone](qabstractspinbox.html#StepEnabledFlag-enum)。

**See also** [QAbstractSpinBox.StepEnabled](qabstractspinbox.html#StepEnabledFlag-enum)。