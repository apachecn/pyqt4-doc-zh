# QMetaEnum Class Reference

## [[QtCore](index.htm) module]

该QMetaEnum类提供有关一个枚举元数据。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QMetaEnum)`
*   `bool isFlag (self)`
*   `bool isValid (self)`
*   `str key (self, int index)`
*   `int keyCount (self)`
*   `int keysToValue (self, str keys)`
*   `int keyToValue (self, str key)`
*   `str name (self)`
*   `str scope (self)`
*   `int value (self, int index)`
*   `str valueToKey (self, int value)`
*   `QByteArray valueToKeys (self, int value)`

* * *

## Detailed Description

该QMetaEnum类提供有关一个枚举元数据。

使用[name](qmetaenum.html#name)（ ）用于枚举的名字。枚举的键（每个枚举项的名称）被退回[key](qmetaenum.html#key)（ ） ;使用[keyCount](qmetaenum.html#keyCount)（）找到的键的数目。[isFlag](qmetaenum.html#isFlag)（ ）返回枚举是否是要被作为一个标志，这意味着它的值可以使用OR运算符进行组合。

转换函数[keyToValue](qmetaenum.html#keyToValue)（ ）[valueToKey](qmetaenum.html#valueToKey)（ ）[keysToValue](qmetaenum.html#keysToValue)（）和[valueToKeys](qmetaenum.html#valueToKeys)（ ）允许枚举或整数表示的设定值和它的字面表示之间的转换。该[scope](qmetaenum.html#scope)（ ）函数返回类范围这个枚举被宣布英寸

* * *

## Method Documentation

```
QMetaEnum.__init__ (self)
```

```
QMetaEnum.__init__ (self, QMetaEnum)
```

```
bool QMetaEnum.isFlag (self)
```

返回True如果枚举被用作一个标志，否则返回False 。

当作为国旗使用，普查员可以使用OR运算符进行组合。

**See also** [keysToValue](qmetaenum.html#keysToValue)（）和[valueToKeys](qmetaenum.html#valueToKeys)（ ） 。

```
bool QMetaEnum.isValid (self)
```

返回True如果该枚举是有效的（有名称） ，否则返回False 。

**See also** [name](qmetaenum.html#name)（ ） 。

```
str QMetaEnum.key (self, int index)
```

返回键与给定的_index_，或者0，如果没有这样的键存在。

**See also** [keyCount](qmetaenum.html#keyCount)（ ）[value](qmetaenum.html#value)（）和[valueToKey](qmetaenum.html#valueToKey)（ ） 。

```
int QMetaEnum.keyCount (self)
```

返回键的数目。

**See also** [key](qmetaenum.html#key)（ ） 。

```
int QMetaEnum.keysToValue (self, str keys)
```

从返回的值结合起来产生的价值_keys_使用OR运算符，或-1，如果_keys_没有定义。另外，在串_keys_必须是“|”分隔。

**See also** [isFlag](qmetaenum.html#isFlag)（ ）[valueToKey](qmetaenum.html#valueToKey)（）和[valueToKeys](qmetaenum.html#valueToKeys)（ ） 。

```
int QMetaEnum.keyToValue (self, str key)
```

返回给定枚举的整数值_key_，或-1，如果_key_没有定义。

对于标志类型，使用[keysToValue](qmetaenum.html#keysToValue)（ ） 。

**See also** [valueToKey](qmetaenum.html#valueToKey)（ ）[isFlag](qmetaenum.html#isFlag)（）和[keysToValue](qmetaenum.html#keysToValue)（ ） 。

```
str QMetaEnum.name (self)
```

返回枚举器（不带范围）的名称。

例如，本[Qt.AlignmentFlag](qt.html#AlignmentFlag-enum)枚举有`AlignmentFlag`正如它的名字和[Qt](qt.html)作为范围。

**See also** [isValid](qmetaenum.html#isValid)（）和[scope](qmetaenum.html#scope)（ ） 。

```
str QMetaEnum.scope (self)
```

返回此枚举被宣布英寸的范围

例如，本[Qt.AlignmentFlag](qt.html#AlignmentFlag-enum)枚举有`Qt`作为范围和`AlignmentFlag`作为名称。

**See also** [name](qmetaenum.html#name)（ ） 。

```
int QMetaEnum.value (self, int index)
```

用给定的返回值_index_;或返回-1，如果没有这样的价值。

**See also** [keyCount](qmetaenum.html#keyCount)（ ）[key](qmetaenum.html#key)（）和[keyToValue](qmetaenum.html#keyToValue)（ ） 。

```
str QMetaEnum.valueToKey (self, int value)
```

返回作为给定枚举的名称的字符串_value_，或者0，如果_value_没有定义。

对于标志类型，使用[valueToKeys](qmetaenum.html#valueToKeys)（ ） 。

**See also** [isFlag](qmetaenum.html#isFlag)（）和[valueToKeys](qmetaenum.html#valueToKeys)（ ） 。

```
QByteArray QMetaEnum.valueToKeys (self, int value)
```

[

返回一个字节数组'|'分隔的键表示给定_value_。

](qbytearray.html)

[**See also**](qbytearray.html) [isFlag](qmetaenum.html#isFlag)（ ）[valueToKey](qmetaenum.html#valueToKey)（）和[keysToValue](qmetaenum.html#keysToValue)（ ） 。