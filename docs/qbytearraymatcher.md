# QByteArrayMatcher Class Reference

## [[QtCore](index.htm) module]

该QByteArrayMatcher类认为，可以快速匹配一个字节数组中的一个字节序列。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QByteArray pattern)`
*   `__init__ (self, QByteArrayMatcher other)`
*   `int indexIn (self, QByteArray ba, int from = 0)`
*   `QByteArray pattern (self)`
*   `setPattern (self, QByteArray pattern)`

* * *

## Detailed Description

该QByteArrayMatcher类认为，可以快速匹配一个字节数组中的一个字节序列。

当你有，你要反复对一些字节数组（也许在一个循环）匹配字节序列这个类是有用的，或者当你想搜索的字节多次相同的字节数组中相同的序列。使用一个匹配对象，[indexIn](qbytearraymatcher.html#indexIn)（）比匹配的一个普通速度[QByteArray](qbytearray.html)同[QByteArray.indexOf](qbytearray.html#indexOf)（）如果匹配的重复发生。这个类没有提供任何好处，如果你正在做一次性的字节数组匹配。

创建QByteArrayMatcher与[QByteArray](qbytearray.html)你要搜索的内容。然后调用[indexIn](qbytearraymatcher.html#indexIn)（）对[QByteArray](qbytearray.html)您要搜索。

* * *

## Method Documentation

```
QByteArrayMatcher.__init__ (self)
```

构造一个空字节数组匹配，将不符合任何东西。通话[setPattern](qbytearraymatcher.html#setPattern)（）给它一个模式来匹配。

```
QByteArrayMatcher.__init__ (self, QByteArray pattern)
```

构造一个字节数组匹配，将搜索_pattern_。通话[indexIn](qbytearraymatcher.html#indexIn)（）来执行搜索。

```
QByteArrayMatcher.__init__ (self, QByteArrayMatcher other)
```

构造一个字节数组从匹配_pattern_。_pattern_已定_length_。_pattern_必须保持在范围内，但析构函数并不删除_pattern_。

```
int QByteArrayMatcher.indexIn (self, QByteArray ba, int from = 0)
```

搜索字节数组_ba_从字节位置_from_（默认为0 ，即从第一个字节） ，为字节数组[pattern](qbytearraymatcher.html#pattern)（ ），这是设置在构造函数中，或在最近一次调用[setPattern](qbytearraymatcher.html#setPattern)（ ） 。返回该位置处[pattern](qbytearraymatcher.html#pattern)（ ）匹配_ba_，或-1，如果没有找到匹配项。

```
QByteArray QByteArrayMatcher.pattern (self)
```

[

返回字节数组模式该字节数组匹配器将搜索。

](qbytearray.html)

[**See also**](qbytearray.html) [setPattern](qbytearraymatcher.html#setPattern)（ ） 。

```
QByteArrayMatcher.setPattern (self, QByteArray pattern)
```

设置字节数组，这个字节数组匹配器将搜索到_pattern_。

**See also** [pattern](qbytearraymatcher.html#pattern)（）和[indexIn](qbytearraymatcher.html#indexIn)（ ） 。