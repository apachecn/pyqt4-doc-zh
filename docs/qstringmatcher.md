# QStringMatcher Class Reference

## [[QtCore](index.htm) module]

该QStringMatcher类认为，可以快速匹配一个Unicode字符串的字符序列。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QString pattern, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `__init__ (self, QStringMatcher other)`
*   `Qt.CaseSensitivity caseSensitivity (self)`
*   `int indexIn (self, QString str, int from = 0)`
*   `QString pattern (self)`
*   `setCaseSensitivity (self, Qt.CaseSensitivity cs)`
*   `setPattern (self, QString pattern)`

* * *

## Detailed Description

该QStringMatcher类认为，可以快速匹配一个Unicode字符串的字符序列。

当你有一个序列这个类是非常有用的[QChar](qchar.html)要反复对一些字符串（也许在一个循环）相匹配，或s当你要搜索的字符中多次相同的字符串相同的序列。使用一个匹配对象，[indexIn](qstringmatcher.html#indexIn)（）比匹配的一个普通速度[QString](qstring.html)同[QString.indexOf](qstring.html#indexOf)（）如果匹配的重复发生。这个类没有提供任何好处，如果你正在做一次性的字符串匹配。

创建QStringMatcher与[QString](qstring.html)你要搜索的内容。然后调用[indexIn](qstringmatcher.html#indexIn)（）对[QString](qstring.html)您要搜索。

* * *

## Method Documentation

```
QStringMatcher.__init__ (self)
```

构造一个空字符串匹配，将不符合任何东西。通话[setPattern](qstringmatcher.html#setPattern)（）给它一个模式来匹配。

```
QStringMatcher.__init__ (self, QString pattern, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

构造一个字符串匹配，将搜索_pattern_，有区分大小写_cs_。

Call [indexIn](qstringmatcher.html#indexIn)（）来执行搜索。

```
QStringMatcher.__init__ (self, QStringMatcher other)
```

构造一个字符串匹配，将搜索者提到的模式_uc_用给定的_length_并通过指定的区分大小写_cs_。

此功能被引入Qt的4.5 。

```
Qt.CaseSensitivity QStringMatcher.caseSensitivity (self)
```

[

返回区分大小写设置该字符串匹配。

](qt.html#CaseSensitivity-enum)

[**See also**](qt.html#CaseSensitivity-enum) [setCaseSensitivity](qstringmatcher.html#setCaseSensitivity)（ ） 。

```
int QStringMatcher.indexIn (self, QString str, int from = 0)
```

搜索字符串_str_从字符位置_from_（默认为0 ，即从第一个字符） ，字符串[pattern](qstringmatcher.html#pattern)（ ），这是设置在构造函数中，或在最近一次调用[setPattern](qstringmatcher.html#setPattern)（ ） 。返回该位置处[pattern](qstringmatcher.html#pattern)（ ）匹配_str_，或-1，如果没有找到匹配项。

**See also** [setPattern](qstringmatcher.html#setPattern)（）和[setCaseSensitivity](qstringmatcher.html#setCaseSensitivity)（ ） 。

```
QString QStringMatcher.pattern (self)
```

返回字符串的模式，这个字符串匹配器将搜索。

**See also** [setPattern](qstringmatcher.html#setPattern)（ ） 。

```
QStringMatcher.setCaseSensitivity (self, Qt.CaseSensitivity cs)
```

设置该字符串匹配的区分大小写设置为_cs_。

**See also** [caseSensitivity](qstringmatcher.html#caseSensitivity)（ ）[setPattern](qstringmatcher.html#setPattern)（）和[indexIn](qstringmatcher.html#indexIn)（ ） 。

```
QStringMatcher.setPattern (self, QString pattern)
```

设置该字符串匹配器将搜索到的字符串_pattern_。

**See also** [pattern](qstringmatcher.html#pattern)（ ）[setCaseSensitivity](qstringmatcher.html#setCaseSensitivity)（）和[indexIn](qstringmatcher.html#indexIn)（ ） 。