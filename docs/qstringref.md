# QStringRef Class Reference

## [[QtCore](index.htm) module]

该QStringRef类提供了简单包装的[QString](qstring.html)子。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QString aString, int aPosition, int aSize)`
*   `__init__ (self, QString aString)`
*   `__init__ (self, QStringRef other)`
*   `QStringRef appendTo (self, QString string)`
*   `QChar at (self, int i)`
*   `clear (self)`
*   `int compare (self, QString other, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int compare (self, QStringRef other, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int compare (self, QLatin1String other, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `QChar constData (self)`
*   `bool contains (self, QString str, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `bool contains (self, QLatin1String str, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `bool contains (self, QStringRef str, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int count (self)`
*   `int count (self, QString str, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int count (self, QStringRef str, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `QChar data (self)`
*   `bool endsWith (self, QString str, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `bool endsWith (self, QLatin1String str, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `bool endsWith (self, QStringRef str, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int indexOf (self, QString str, int from = 0, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int indexOf (self, QLatin1String str, int from = 0, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int indexOf (self, QStringRef str, int from = 0, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `bool isEmpty (self)`
*   `bool isNull (self)`
*   `int lastIndexOf (self, QString str, int from = -1, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int lastIndexOf (self, QLatin1String str, int from = -1, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int lastIndexOf (self, QStringRef str, int from = -1, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int length (self)`
*   `int localeAwareCompare (self, QString s)`
*   `int localeAwareCompare (self, QStringRef s)`
*   `int position (self)`
*   `int size (self)`
*   `bool startsWith (self, QString str, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `bool startsWith (self, QLatin1String str, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `bool startsWith (self, QStringRef str, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `QString string (self)`
*   `QByteArray toAscii (self)`
*   `QByteArray toLatin1 (self)`
*   `QByteArray toLocal8Bit (self)`
*   `QString toString (self)`
*   `list-of-int toUcs4 (self)`
*   `QByteArray toUtf8 (self)`
*   `QChar unicode (self)`

### Static Methods

*   `int compare (QStringRef s1, QString s2, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int compare (QStringRef s1, QStringRef s2, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int compare (QStringRef s1, QLatin1String s2, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int localeAwareCompare (QStringRef s1, QString s2)`
*   `int localeAwareCompare (QStringRef s1, QStringRef s2)`

### Special Methods

*   `bool __eq__ (self, QStringRef s2)`
*   `bool __eq__ (self, QString s2)`
*   `bool __eq__ (self, QLatin1String s2)`
*   `bool __ge__ (self, QStringRef s2)`
*   `bool __gt__ (self, QStringRef s2)`
*   `bool __le__ (self, QStringRef s2)`
*   `__len__ (self)`
*   `bool __lt__ (self, QStringRef s2)`
*   `bool __ne__ (self, QStringRef s2)`
*   `bool __ne__ (self, QString s2)`
*   `bool __ne__ (self, QLatin1String s2)`
*   `str __str__ (self)`
*   `unicode __unicode__ (self)`

* * *

## Detailed Description

该QStringRef类提供了简单包装的[QString](qstring.html)子。

QStringRef提供的一个只读子集[QString](qstring.html)API。

一个字符串引用明确引用的一部分[string](qstringref.html#string)（）与给定的[size](qstringref.html#size)（） ，起始于一个特定的[position](qstringref.html#position)（ ） 。调用[toString](qstringref.html#toString)（）返回的数据的一个副本作为一个真正的[QString](qstring.html)实例。

本课程的目的是操纵现有获得字符串时，提高子处理性能[QString](qstring.html)实例。 QStringRef避免了一个标准的内存分配和引用计数的开销[QString](qstring.html)通过简单地引用原字符串的一部分。这可以证明是有利的，低级别的代码，例如，在一个解析器使用，在潜在的更复杂的代码的费用。

对于大多数用户来说，也有使用QStringRef ，而不是没有任何语义的好处[QString](qstring.html)因为QStringRef需要注意支付给内存管理问题，可能使代码更复杂的编写和维护。

**Warning:**一个QStringRef是唯一有效的，只要所引用的字符串存在。如果原始字符串将被删除，该字符串引用指向无效的内存位置。

我们建议您仅在稳定的代码，其中分析已经清楚地确定了性能的提升可以通过这个类提供了优化的子字符串处理来替代标准的字符串操作进行使用这个类。

* * *

## Method Documentation

```
QStringRef.__init__ (self)
```

构造一个空字符串引用。

```
QStringRef.__init__ (self, QString aString, int aPosition, int aSize)
```

构造一个字符串引用的字符范围在给定的_string_由起始指定_position_和_length_在字符。

**Warning:**此功能的存在是为了提高性能，尽可能地，并且不执行边界检查。对于程序的正确性，_position_和_length_必须描述一个有效的子串_string_。

这意味着它们的起始_position_必须为正或0和小于_string_的长度，_length_必须是正数或0 ，但比字符串的长度减去较小的起点_position_，即， 0 \u003c =位置\u003c字符串\u003e[length](qstringref.html#length)（ ）且0 \u003c =长度\u003c =字符串\u003e[length](qstringref.html#length)（ ） - 位置必须同时满足。

```
QStringRef.__init__ (self, QString aString)
```

构造一个字符串引用给定的_string_。

```
QStringRef.__init__ (self, QStringRef other)
```

构造的一个副本_other_字符串引用。

```
QStringRef QStringRef.appendTo (self, QString string)
```

追加字符串引用_string_，并返回一个新的参考组合的字符串数据。

```
QChar QStringRef.at (self, int i)
```

返回字符的给定索引处_position_在字符串引用。

该_position_必须是在字符串中的有效索引位置（即0 \u003c =_position_\u003c[size](qstringref.html#size)（））。

```
QStringRef.clear (self)
```

通过使空和空清除的字符串引用的内容。

**See also** [isEmpty](qstringref.html#isEmpty)（）和[isNull](qstringref.html#isNull)（ ） 。

```
int QStringRef.compare (self, QString other, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

比较字符串_s1_与串_s2_并返回一个整数大于零小于，等于，或大于，如果_s1_小于，等于或大于_s2_。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)，比较是区分大小写的，否则比较不区分大小写。

此功能被引入Qt的4.5 。

```
int QStringRef.compare (self, QStringRef other, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这是一个重载函数。

比较字符串_s1_与串_s2_并返回一个整数大于零小于，等于，或大于，如果_s1_小于，等于或大于_s2_。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)，比较是区分大小写的，否则比较不区分大小写。

此功能被引入Qt的4.5 。

```
int QStringRef.compare (self, QLatin1String other, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这是一个重载函数。

比较字符串_s1_与串_s2_并返回一个整数大于零小于，等于，或大于，如果_s1_小于，等于或大于_s2_。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)，比较是区分大小写的，否则比较不区分大小写。

此功能被引入Qt的4.5 。

```
int QStringRef.compare (QStringRef s1, QString s2, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这是一个重载函数。

比较此字符串与_other_字符串并返回比，等于大于零的整数更少，或更大，如果该字符串比小于，等于，或大于_other_字符串。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)，比较是区分大小写的，否则比较不区分大小写。

相当于`compare(*this, other, cs)`。

此功能被引入Qt的4.5 。

**See also** [QString.compare](qstring.html#compare)（ ） 。

```
int QStringRef.compare (QStringRef s1, QStringRef s2, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这是一个重载函数。

比较此字符串与_other_字符串并返回比，等于大于零的整数更少，或更大，如果该字符串比小于，等于，或大于_other_字符串。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)，比较是区分大小写的，否则比较不区分大小写。

相当于`compare(*this, other, cs)`。

此功能被引入Qt的4.5 。

**See also** [QString.compare](qstring.html#compare)（ ） 。

```
int QStringRef.compare (QStringRef s1, QLatin1String s2, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这是一个重载函数。

比较此字符串与_other_字符串并返回比，等于大于零的整数更少，或更大，如果该字符串比小于，等于，或大于_other_字符串。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)，比较是区分大小写的，否则比较不区分大小写。

相当于`compare(*this, other, cs)`。

此功能被引入Qt的4.5 。

**See also** [QString.compare](qstring.html#compare)（ ） 。

```
QChar QStringRef.constData (self)
```

同[unicode](qstringref.html#unicode)（ ） 。

```
bool QStringRef.contains (self, QString str, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

如果这个字符串引用包含字符串的出现，则返回True_str_否则返回False 。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

此功能被引入Qt的4.8 。

**See also** [indexOf](qstringref.html#indexOf)（）和[count](qstringref.html#count)（ ） 。

```
bool QStringRef.contains (self, QLatin1String str, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这个函数的重载[contains](qstringref.html#contains)（ ） 。

如果这个字符串包含的字符的出现，则返回True_ch_否则返回False 。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

此功能被引入Qt的4.8 。

```
bool QStringRef.contains (self, QStringRef str, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这个函数的重载[contains](qstringref.html#contains)（ ） 。

如果此字符串包含引用的字符串引用的出现，则返回True_str_否则返回False 。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

此功能被引入Qt的4.8 。

**See also** [indexOf](qstringref.html#indexOf)（）和[count](qstringref.html#count)（ ） 。

```
int QStringRef.count (self)
```

返回由字符串引用所指的字符数。相当于[size](qstringref.html#size)（）和[length](qstringref.html#length)（ ） 。

**See also** [position](qstringref.html#position)（）和[string](qstringref.html#string)（ ） 。

```
int QStringRef.count (self, QString str, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

返回（可能重叠）字符串的出现次数_str_在此字符串中引用。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

此功能被引入Qt的4.8 。

**See also** [QString.count](qstring.html#count)（ ）[contains](qstringref.html#contains)（）和[indexOf](qstringref.html#indexOf)（ ） 。

```
int QStringRef.count (self, QStringRef str, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这个函数的重载[count](qstringref.html#count)（ ） 。

返回出现的字符数量_ch_在字符串引用。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

此功能被引入Qt的4.8 。

**See also** [QString.count](qstring.html#count)（ ）[contains](qstringref.html#contains)（）和[indexOf](qstringref.html#indexOf)（ ） 。

```
QChar QStringRef.data (self)
```

同[unicode](qstringref.html#unicode)（ ） 。

```
bool QStringRef.endsWith (self, QString str, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

如果字符串参考结尾，则返回True_str_否则返回False 。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

此功能被引入Qt的4.8 。

**See also** [QString.endsWith](qstring.html#endsWith)（）和[startsWith](qstringref.html#startsWith)（ ） 。

```
bool QStringRef.endsWith (self, QLatin1String str, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这个函数的重载[endsWith](qstringref.html#endsWith)（ ） 。

如果字符串参考结尾，则返回True_ch_否则返回False 。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

此功能被引入Qt的4.8 。

**See also** [QString.endsWith](qstring.html#endsWith)（）和[endsWith](qstringref.html#endsWith)（ ） 。

```
bool QStringRef.endsWith (self, QStringRef str, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这个函数的重载[endsWith](qstringref.html#endsWith)（ ） 。

此功能被引入Qt的4.8 。

**See also** [QString.endsWith](qstring.html#endsWith)（）和[endsWith](qstringref.html#endsWith)（ ） 。

```
int QStringRef.indexOf (self, QString str, int from = 0, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

返回字符串中第一次出现的索引位置_str_在这个字符串引用，向前搜索的索引位置_from_。返回-1，如果_str_是没有找到。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

If _from_为-1，搜索从最后一个字符，如果是-2 ，在倒数第二个字符等等。

此功能被引入Qt的4.8 。

**See also** [QString.indexOf](qstring.html#indexOf)（ ）[lastIndexOf](qstringref.html#lastIndexOf)（ ）[contains](qstringref.html#contains)（）和[count](qstringref.html#count)（ ） 。

```
int QStringRef.indexOf (self, QLatin1String str, int from = 0, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

返回字符串中第一次出现的索引位置_str_在这个字符串引用，向前搜索的索引位置_from_。返回-1，如果_str_是没有找到。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

If _from_为-1，搜索从最后一个字符，如果是-2 ，在倒数第二个字符等等。

此功能被引入Qt的4.8 。

**See also** [QString.indexOf](qstring.html#indexOf)（ ）[lastIndexOf](qstringref.html#lastIndexOf)（ ）[contains](qstringref.html#contains)（）和[count](qstringref.html#count)（ ） 。

```
int QStringRef.indexOf (self, QStringRef str, int from = 0, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这个函数的重载[indexOf](qstringref.html#indexOf)（ ） 。

返回字符的第一个匹配项的索引位置_ch_在字符串参考，向前搜索的索引位置_from_。返回-1，如果_ch_找不到。

此功能被引入Qt的4.8 。

**See also** [QString.indexOf](qstring.html#indexOf)（ ）[lastIndexOf](qstringref.html#lastIndexOf)（ ）[contains](qstringref.html#contains)（）和[count](qstringref.html#count)（ ） 。

```
bool QStringRef.isEmpty (self)
```

返回True如果字符串引用没有字符，否则返回False 。

一个字符串引用是空的，如果它的大小是零。

**See also** [size](qstringref.html#size)（ ） 。

```
bool QStringRef.isNull (self)
```

返回True如果[string](qstringref.html#string)（ ）返回一个空指针或指向一个空字符串，否则返回True。

**See also** [size](qstringref.html#size)（ ） 。

```
int QStringRef.lastIndexOf (self, QString str, int from = -1, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

返回字符串中最后一次出现的索引位置_str_在这个字符串引用，从索引位置向后搜索_from_。如果_from_为-1 （默认），搜索从最后一个字符，如果_from_为-2 ，在倒数第二个字符等等。返回-1，如果_str_是没有找到。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

此功能被引入Qt的4.8 。

**See also** [QString.lastIndexOf](qstring.html#lastIndexOf)（ ）[indexOf](qstringref.html#indexOf)（ ）[contains](qstringref.html#contains)（）和[count](qstringref.html#count)（ ） 。

```
int QStringRef.lastIndexOf (self, QLatin1String str, int from = -1, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这个函数的重载[lastIndexOf](qstringref.html#lastIndexOf)（ ） 。

返回字符的最后一个匹配项的索引位置_ch_从位置向后搜索_from_。

此功能被引入Qt的4.8 。

**See also** [QString.lastIndexOf](qstring.html#lastIndexOf)（ ）[indexOf](qstringref.html#indexOf)（ ）[contains](qstringref.html#contains)（）和[count](qstringref.html#count)（ ） 。

```
int QStringRef.lastIndexOf (self, QStringRef str, int from = -1, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这个函数的重载[lastIndexOf](qstringref.html#lastIndexOf)（ ） 。

返回字符串中最后一次出现的索引位置_str_在这个字符串引用，从索引位置向后搜索_from_。如果_from_为-1 （默认），搜索从最后一个字符，如果_from_为-2 ，在倒数第二个字符等等。返回-1，如果_str_是没有找到。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

此功能被引入Qt的4.8 。

**See also** [QString.lastIndexOf](qstring.html#lastIndexOf)（ ）[indexOf](qstringref.html#indexOf)（ ）[contains](qstringref.html#contains)（）和[count](qstringref.html#count)（ ） 。

```
int QStringRef.length (self)
```

返回由字符串引用所指的字符数。相当于[size](qstringref.html#size)（）和[count](qstringref.html#count)（ ） 。

**See also** [position](qstringref.html#position)（）和[string](qstringref.html#string)（ ） 。

```
int QStringRef.localeAwareCompare (self, QString s)
```

比较_s1_同_s2_并返回一个整数大于零小于，等于，或大于，如果_s1_小于，等于或大于_s2_。

比较是在一个语言环境，也依赖于平台的方式进行。使用此功能可呈现字符串排序的列表给用户。

在Mac OS X ，此功能根据“订单的排序列表”，在国际prefereces面板设置进行比较。

此功能被引入Qt的4.5 。

**See also** [compare](qstringref.html#compare)（）和[QTextCodec.locale](index.htm#locale)（ ） 。

```
int QStringRef.localeAwareCompare (self, QStringRef s)
```

这是一个重载函数。

比较_s1_同_s2_并返回一个整数大于零小于，等于，或大于，如果_s1_小于，等于或大于_s2_。

比较是在一个语言环境，也依赖于平台的方式进行。使用此功能可呈现字符串排序的列表给用户。

此功能被引入Qt的4.5 。

```
int QStringRef.localeAwareCompare (QStringRef s1, QString s2)
```

这是一个重载函数。

比较此字符串与_other_字符串并返回比，等于大于零的整数更少，或更大，如果该字符串比小于，等于，或大于_other_字符串。

比较是在一个语言环境，也依赖于平台的方式进行。使用此功能可呈现字符串排序的列表给用户。

此功能被引入Qt的4.5 。

```
int QStringRef.localeAwareCompare (QStringRef s1, QStringRef s2)
```

这是一个重载函数。

比较此字符串与_other_字符串并返回比，等于大于零的整数更少，或更大，如果该字符串比小于，等于，或大于_other_字符串。

比较是在一个语言环境，也依赖于平台的方式进行。使用此功能可呈现字符串排序的列表给用户。

此功能被引入Qt的4.5 。

```
int QStringRef.position (self)
```

返回由字符串引用所引用的参考的字符串的开始位置。

**See also** [size](qstringref.html#size)（）和[string](qstringref.html#string)（ ） 。

```
int QStringRef.size (self)
```

返回由字符串引用所指的字符数。相当于[length](qstringref.html#length)（）和[count](qstringref.html#count)（ ） 。

**See also** [position](qstringref.html#position)（）和[string](qstringref.html#string)（ ） 。

```
bool QStringRef.startsWith (self, QString str, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

如果字符串引用开头，则返回True_str_否则返回False 。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

此功能被引入Qt的4.8 。

**See also** [QString.startsWith](qstring.html#startsWith)（）和[endsWith](qstringref.html#endsWith)（ ） 。

```
bool QStringRef.startsWith (self, QLatin1String str, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这个函数的重载[startsWith](qstringref.html#startsWith)（ ） 。

此功能被引入Qt的4.8 。

**See also** [QString.startsWith](qstring.html#startsWith)（）和[endsWith](qstringref.html#endsWith)（ ） 。

```
bool QStringRef.startsWith (self, QStringRef str, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这个函数的重载[startsWith](qstringref.html#startsWith)（ ） 。

此功能被引入Qt的4.8 。

**See also** [QString.startsWith](qstring.html#startsWith)（）和[endsWith](qstringref.html#endsWith)（ ） 。

```
QString QStringRef.string (self)
```

返回一个指向由字符串引用，或0称为如果它不引用的字符串的字符串。

**See also** [unicode](qstringref.html#unicode)（ ） 。

```
QByteArray QStringRef.toAscii (self)
```

[](qbytearray.html)

[返回字符串的8位表示为](qbytearray.html)[QByteArray](qbytearray.html)。

如果一个编解码器已使用设置[QTextCodec.setCodecForCStrings](qtextcodec.html#setCodecForCStrings)（ ） ，它是用来为Unicode转换为8位字符，否则这个函数一样[toLatin1](qstringref.html#toLatin1)（ ） 。

需要注意的是，尽管这个名字，这个功能并不一定返回一个US-ASCII （ ANSI X3.4 - 1986）的字符串，其结果可能不是US-ASCII兼容。

此功能被引入Qt的4.8 。

**See also** [toLatin1](qstringref.html#toLatin1)（ ）[toUtf8](qstringref.html#toUtf8)（ ）[toLocal8Bit](qstringref.html#toLocal8Bit)（）和[QTextCodec](qtextcodec.html)。

```
QByteArray QStringRef.toLatin1 (self)
```

[](qbytearray.html)

[返回字符串的的Latin-1表示为](qbytearray.html)[QByteArray](qbytearray.html)。

返回的字节数组是不确定的，如果字符串包含非拉丁文字符。这些字符可以被抑制或问号代替。

此功能被引入Qt的4.8 。

**See also** [toAscii](qstringref.html#toAscii)（ ）[toUtf8](qstringref.html#toUtf8)（ ）[toLocal8Bit](qstringref.html#toLocal8Bit)（）和[QTextCodec](qtextcodec.html)。

```
QByteArray QStringRef.toLocal8Bit (self)
```

[](qbytearray.html)

[返回字符串作为当地8位表示](qbytearray.html)[QByteArray](qbytearray.html)。返回的字节数组是不确定的，如果该字符串包含不支持的本地8位编码的字符。

[QTextCodec.codecForLocale](qtextcodec.html#codecForLocale)（ ）是用来从Unicode执行转换。如果本地编码不能确定，这个函数一样[toLatin1](qstringref.html#toLatin1)（ ） 。

如果这个字符串包含不能在语言环境进行编码的任何字符，返回的字节数组是不确定的。这些字符可以由另一被抑制或更换。

此功能被引入Qt的4.8 。

**See also** [toAscii](qstringref.html#toAscii)（ ）[toLatin1](qstringref.html#toLatin1)（ ）[toUtf8](qstringref.html#toUtf8)（）和[QTextCodec](qtextcodec.html)。

```
QString QStringRef.toString (self)
```

返回的字符串引用的副本作为[QString](qstring.html)对象。

如果字符串引用不是字符串的一个完整的参考（即[position](qstringref.html#position)（）为0，并且[size](qstringref.html#size)（ ）等于[string](qstringref.html#string)（） - \u003e[size](qstringref.html#size)（ ） ） ，这个函数会分配一个新的字符串返回。

**See also** [string](qstringref.html#string)（ ） 。

```
list-of-int QStringRef.toUcs4 (self)
```

返回字符串的UCS-4/UTF-32表示为[QVector](index.htm)\u003cuint\u003e 。

UCS-4是一个统一码的编解码器，并且是无损的。所有从这个字符串中的字符可以被编码在UCS- 4 。

此功能被引入Qt的4.8 。

**See also** [toAscii](qstringref.html#toAscii)（ ）[toLatin1](qstringref.html#toLatin1)（ ）[toLocal8Bit](qstringref.html#toLocal8Bit)（）和[QTextCodec](qtextcodec.html)。

```
QByteArray QStringRef.toUtf8 (self)
```

[](qbytearray.html)

[返回字符串的UTF-8表示为](qbytearray.html)[QByteArray](qbytearray.html)。

UTF - 8是Unicode编码，可以表示所有字符的Unicode字符串像[QString](qstring.html)。

然而，在Unicode的范围内，但是也有一些不被视为某些字符码点。 Unicode标准中保留每个Unicode平面（ U + FFFE ， U + FFFF ， U +1 FFFE ， U +1 FFFF ， U +2 FFFE等） ，以及16码点在范围U + FDD0最后两个码点.. U + FDDF ，包容性的，非字符。如果任何这些出现在字符串中，它们可以被丢弃，而不会出现在UTF-8表示，或者它们可以由一个或多个字符替换被替换。

此功能被引入Qt的4.8 。

**See also** [toAscii](qstringref.html#toAscii)（ ）[toLatin1](qstringref.html#toLatin1)（ ）[toLocal8Bit](qstringref.html#toLocal8Bit)（）和[QTextCodec](qtextcodec.html)。

```
QChar QStringRef.unicode (self)
```

返回的字符串引用一个Unicode表示。由于数据直接源于所引用的字符串，它是不是空终止，除非引用字符串包含字符串的空终止符。

**See also** [string](qstringref.html#string)（ ） 。

```
bool QStringRef.__eq__ (self, QStringRef s2)
```

```
bool QStringRef.__eq__ (self, QString s2)
```

```
bool QStringRef.__eq__ (self, QLatin1String s2)
```

```
bool QStringRef.__ge__ (self, QStringRef s2)
```

```
bool QStringRef.__gt__ (self, QStringRef s2)
```

```
bool QStringRef.__le__ (self, QStringRef s2)
```

```
 QStringRef.__len__ (self)
```

```
bool QStringRef.__lt__ (self, QStringRef s2)
```

```
bool QStringRef.__ne__ (self, QStringRef s2)
```

```
bool QStringRef.__ne__ (self, QString s2)
```

```
bool QStringRef.__ne__ (self, QLatin1String s2)
```

```
str QStringRef.__str__ (self)
```

```
unicode QStringRef.__unicode__ (self)
```