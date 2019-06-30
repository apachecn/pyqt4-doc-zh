# QTextLength Class Reference

## [[QtGui](index.htm) module]

该QTextLength类封装了不同类型的长度在使用[QTextDocument](qtextdocument.html)。[More...](#details)

### Types

*   `enum Type { VariableLength, FixedLength, PercentageLength }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, Type atype, float avalue)`
*   `__init__ (self, QVariant variant)`
*   `__init__ (self, QTextLength)`
*   `float rawValue (self)`
*   `Type type (self)`
*   `float value (self, float maximumLength)`

### Special Methods

*   `bool __eq__ (self, QTextLength other)`
*   `bool __ne__ (self, QTextLength other)`

* * *

## Detailed Description

该QTextLength类封装了不同类型的长度在使用[QTextDocument](qtextdocument.html)。

当我们指定在文本文档中元素的长度的值，我们往往需要提供一些其他信息，以便长度是用在我们预期的方式。例如，当我们指定一个表的宽度，该值可以代表像素的固定数量，或者它可以是一个百分比值。这个信息改变的值的两个含义，它的使用方式。

一般来说，这个类用于指定表格的宽度。这些可以被指定为像素的固定量，作为含帧的宽度的百分比，或由可变宽度，允许它佔用只是它要求的空间。

* * *

## Type Documentation

```
QTextLength.Type
```

这个枚举变量描述了不同类型的长度对象可以有。

| Constant | Value | Description |
| --- | --- | --- |
| `QTextLength.VariableLength` | `0` | 物体的宽度是可变的 |
| `QTextLength.FixedLength` | `1` | 物体的宽度是固定的 |
| `QTextLength.PercentageLength` | `2` | 物体的宽度是在最大宽度的百分比 |

**See also** [type](qtextlength.html#type)（ ） 。

* * *

## Method Documentation

```
QTextLength.__init__ (self)
```

构造一个新的长度对象，它代表一个变量的大小。

```
QTextLength.__init__ (self, Type atype, float avalue)
```

构造的赋予了新的对象的长度_type_和_value_。

```
QTextLength.__init__ (self, QVariant variant)
```

```
QTextLength.__init__ (self, QTextLength)
```

```
float QTextLength.rawValue (self)
```

返回的约束值，该值是特定的长度的类型。如果长度[QTextLength.PercentageLength](qtextlength.html#Type-enum)然后原始值的百分比，在0至100的范围内。如果长度[QTextLength.FixedLength](qtextlength.html#Type-enum)那么返回的固定金额。对于可变长度，则返回0。

```
Type QTextLength.type (self)
```

[

返回此长度的对象的类型。

](qtextlength.html#Type-enum)

[**See also**](qtextlength.html#Type-enum) [QTextLength.Type](qtextlength.html#Type-enum)。

```
float QTextLength.value (self, float maximumLength)
```

返回的有效长度，由该长度的对象的类型和指定的约束_maximumLength_。

**See also** [type](qtextlength.html#type)（ ） 。

```
bool QTextLength.__eq__ (self, QTextLength other)
```

```
bool QTextLength.__ne__ (self, QTextLength other)
```