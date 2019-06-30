# QStyleHintReturnVariant Class Reference

## [[QtGui](index.htm) module]

该QStyleHintReturnVariant类提供的样式提示，返回[QVariant](qvariant.html)。[More...](#details)

继承[QStyleHintReturn](qstylehintreturn.html)。

### Types

*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleHintReturnVariant)`

### Members

*   `QVariant **[variant](qstylehintreturnvariant.html#variant-var)**`

* * *

## Detailed Description

该QStyleHintReturnVariant类提供的样式提示，返回[QVariant](qvariant.html)。

* * *

## Type Documentation

```
QStyleHintReturnVariant.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleHintReturn](qstylehintreturn.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleHintReturnVariant.Type` | `SH_Variant` | 风格选择该类型提供（[SH_Variant](qstylehintreturn.html#HintReturnType-enum)这个类） 。 |

该类型在内部使用[QStyleHintReturn](qstylehintreturn.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleHintReturn](qstylehintreturn.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstylehintreturnvariant.html#StyleOptionVersion-enum)。

```
QStyleHintReturnVariant.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleHintReturn](qstylehintreturn.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleHintReturnVariant.Version` | `1` | 1 |

的版本是由[QStyleHintReturn](qstylehintreturn.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstylehintreturnvariant.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleHintReturnVariant.__init__ (self)
```

构造一个[QStyleHintReturnVariant](qstylehintreturnvariant.html)。该成员变量被初始化为默认值。

```
QStyleHintReturnVariant.__init__ (self, QStyleHintReturnVariant)
```

* * *

## Member Documentation

```
QVariant variant
```

这个变量保存了变体的样式提示，返回的QVariant 。