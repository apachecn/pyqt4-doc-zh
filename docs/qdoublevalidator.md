# QDoubleValidator Class Reference

## [[QtGui](index.htm) module]

该QDoubleValidator类提供浮点数的范围检查。[More...](#details)

继承[QValidator](qvalidator.html)。

### Types

*   `enum Notation { StandardNotation, ScientificNotation }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `__init__ (self, float bottom, float top, int decimals, QObject parent = None)`
*   `float bottom (self)`
*   `int decimals (self)`
*   `Notation notation (self)`
*   `setBottom (self, float)`
*   `setDecimals (self, int)`
*   `setNotation (self, Notation)`
*   `setRange (self, float minimum, float maximum, int decimals = 0)`
*   `setTop (self, float)`
*   `float top (self)`
*   `(QValidator.State, QString, int) validate (self, QString, int)`
*   `(QValidator.State, int) validate (self, QString, int)`

* * *

## Detailed Description

该QDoubleValidator类提供浮点数的范围检查。

QDoubleValidator提供了一个上限，下限，以及对小数点后的位数的限制。它不提供一个[fixup](qvalidator.html#fixup)（）函数。

您可以设置在可接受的范围在一次调用中与[setRange](qdoublevalidator.html#setRange)（） ，或用[setBottom](qdoublevalidator.html#bottom-prop)（）和[setTop](qdoublevalidator.html#top-prop)（ ） 。设置的小数位数与[setDecimals](qdoublevalidator.html#decimals-prop)（ ） 。该[validate](qdoublevalidator.html#validate)（ ）函数返回的验证状态。

QDoubleValidator使用其[locale](qvalidator.html#locale)（）来解释的数目。例如，在德国的语言环境， “ 1234 ”将被接纳为小数1.234 。在阿拉伯语语言环境， QDoubleValidator将接受阿拉伯数字。

此外， QDoubleValidator始终保证接受了一些根据“C”区域设置。 QDoubleValidator将不接受与数千年的分隔符。

* * *

## Type Documentation

```
QDoubleValidator.Notation
```

这个枚举变量定义的符号允许进入双。

| Constant | Value | Description |
| --- | --- | --- |
| `QDoubleValidator.StandardNotation` | `0` | 该字符串被写为一个标准的编号（即0.015 ） 。 |
| `QDoubleValidator.ScientificNotation` | `1` | 该字符串是用科学的形式。它可以具有一个指数部分（即1.5E -2）。 |

这个枚举被引入或修改的Qt 4.3 。

* * *

## Method Documentation

```
QDoubleValidator.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个验证器对象有_parent_对象，它接受任何双。

```
QDoubleValidator.__init__ (self, float bottom, float top, int decimals, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个验证器对象有_parent_对象。这个验证器将接受来自双打_bottom_至_top_包容性，具有高达_decimals_小数点后的位数。

```
float QDoubleValidator.bottom (self)
```

```
int QDoubleValidator.decimals (self)
```

```
Notation QDoubleValidator.notation (self)
```

[

```
QDoubleValidator.setBottom (self, float)
```

```
QDoubleValidator.setDecimals (self, int)
```

```
QDoubleValidator.setNotation (self, Notation)
```

```
QDoubleValidator.setRange (self, float minimum, float maximum, int decimals = 0)
```

设置验证程序接受来自双打_minimum_至_maximum_包容性，具有最多_decimals_小数点后的位数。

```
QDoubleValidator.setTop (self, float)
```

```
float QDoubleValidator.top (self)
```

```
(QValidator.State, QString, int) QDoubleValidator.validate (self, QString, int)
```

](qdoublevalidator.html#Notation-enum)

[从重新实现](qdoublevalidator.html#Notation-enum)[QValidator.validate](qvalidator.html#validate)（ ） 。

Returns [Acceptable](qvalidator.html#State-enum)如果字符串_input_包含一个双精度，在有效范围内，并且以正确的格式。

Returns [Intermediate](qvalidator.html#State-enum)如果_input_包含一个双精度，超出范围或格式错误，如有太多小数点后的数字或为空。

Returns [Invalid](qvalidator.html#State-enum)如果_input_是不是双。

注意：如果在有效范围只包括正面双打（如0.0 〜100.0 ）和_input_是一种消极的双重再[Invalid](qvalidator.html#State-enum)返回。如果[notation](qdoublevalidator.html#notation-prop)（ ）被设置为[StandardNotation](qdoublevalidator.html#Notation-enum)和输入包含多个有效范围内的双重小数点前的数字可以具有[Invalid](qvalidator.html#State-enum)返回。如果[notation](qdoublevalidator.html#notation-prop)（）是[ScientificNotation](qdoublevalidator.html#Notation-enum)以及输入是不是在有效范围内，[Intermediate](qvalidator.html#State-enum)返回。的值还可能成为有效的，通过改变指数。

默认情况下，_pos_参数不使用此验证程序。

```
(QValidator.State, int) QDoubleValidator.validate (self, QString, int)
```