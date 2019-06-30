# QStyleHintReturn Class Reference

## [[QtGui](index.htm) module]

该QStyleHintReturn类提供的样式提示返回多个基本数据类型。[More...](#details)

通过继承[QStyleHintReturnMask](qstylehintreturnmask.html)和[QStyleHintReturnVariant](qstylehintreturnvariant.html)。

### Types

*   `enum HintReturnType { SH_Default, SH_Mask, SH_Variant }`
*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self, int version = QStyleOption.Version, int type = QStyleHintReturn.SH_Default)`
*   `__init__ (self, QStyleHintReturn)`

### Members

*   `int **[type](qstylehintreturn.html#type-var)**`
*   `int **[version](qstylehintreturn.html#version-var)**`

* * *

## Detailed Description

该QStyleHintReturn类提供的样式提示返回多个基本数据类型。

QStyleHintReturn及其子类是用来传递从样式信息返回给查询窗口小部件。这是最有用的，当从返回值[QStyle.styleHint](qstyle.html#styleHint)（）不提供足够的细节，例如，当一个掩膜将被返回。

* * *

## Type Documentation

```
QStyleHintReturn.HintReturnType
```

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleHintReturn.SH_Default` | `0xf000` | [QStyleHintReturn](qstylehintreturn.html) |
| `QStyleHintReturn.SH_Mask` | ？ | [QStyle.SH_RubberBand_Mask](qstyle.html#StyleHint-enum) [QStyle.SH_FocusFrame_Mask](qstyle.html#StyleHint-enum) |
| `QStyleHintReturn.SH_Variant` | ？ | [QStyle.SH_TextControl_FocusIndicatorTextCharFormat](qstyle.html#StyleHint-enum) |

```
QStyleHintReturn.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleHintReturn](qstylehintreturn.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleHintReturn.Type` | `SH_Default` | 风格选择该类型提供（[SH_Default](qstylehintreturn.html#HintReturnType-enum)这个类） 。 |

该类型在内部使用[QStyleHintReturn](qstylehintreturn.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleHintReturn](qstylehintreturn.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstylehintreturn.html#StyleOptionVersion-enum)。

```
QStyleHintReturn.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleHintReturn](qstylehintreturn.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleHintReturn.Version` | `1` | 1 |

的版本是由[QStyleHintReturn](qstylehintreturn.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstylehintreturn.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleHintReturn.__init__ (self, int version = QStyleOption.Version, int type = QStyleHintReturn.SH_Default)
```

构造一个[QStyleHintReturn](qstylehintreturn.html)与版本_version_和类型_type_。

该版本具有没有特殊含义[QStyleHintReturn](qstylehintreturn.html)它可以用于由子类不同版本的相同的提示类型之间进行区分。

**See also** [QStyleOption.version](qstyleoption.html#version-var)和[QStyleOption.type](qstyleoption.html#type-varx)。

```
QStyleHintReturn.__init__ (self, QStyleHintReturn)
```

* * *

## Member Documentation

```
int type
```

```
int version
```

这个变量保存样式提示返回容器的版本。

这个值可以由子类用于实现扩展不会破坏兼容性。如果你使用qstyleoption_cast \u003cT\u003e （ ） ，你通常并不需要检查它。