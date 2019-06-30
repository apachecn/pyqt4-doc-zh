# QChar Class Reference

## [[QtCore](index.htm) module]

该QChar类提供了一个16位的Unicode字符。[More...](#details)

### Types

*   `enum Category { NoCategory, Mark_NonSpacing, Mark_SpacingCombining, Mark_Enclosing, ..., Symbol_Other }`
*   `enum CombiningClass { Combining_BelowLeftAttached, Combining_BelowAttached, Combining_BelowRightAttached, Combining_LeftAttached, ..., Combining_IotaSubscript }`
*   `enum Decomposition { NoDecomposition, Canonical, Font, NoBreak, ..., Fraction }`
*   `enum Direction { DirL, DirR, DirEN, DirES, ..., DirBN }`
*   `enum Joining { OtherJoining, Dual, Right, Center }`
*   `enum SpecialCharacter { Null, Nbsp, ReplacementCharacter, ObjectReplacementCharacter, ..., LineSeparator }`
*   `enum UnicodeVersion { Unicode_Unassigned, Unicode_1_1, Unicode_2_0, Unicode_2_1_2, ..., Unicode_5_0 }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, str c)`
*   `__init__ (self, QLatin1Char ch)`
*   `__init__ (self, str c, str r)`
*   `__init__ (self, int rc)`
*   `__init__ (self, SpecialCharacter s)`
*   `__init__ (self, QChar)`
*   `Category category (self)`
*   `str cell (self)`
*   `str combiningClass (self)`
*   `QString decomposition (self)`
*   `Decomposition decompositionTag (self)`
*   `int digitValue (self)`
*   `Direction direction (self)`
*   `bool hasMirrored (self)`
*   `bool isDigit (self)`
*   `bool isHighSurrogate (self)`
*   `bool isLetter (self)`
*   `bool isLetterOrNumber (self)`
*   `bool isLower (self)`
*   `bool isLowSurrogate (self)`
*   `bool isMark (self)`
*   `bool isNull (self)`
*   `bool isNumber (self)`
*   `bool isPrint (self)`
*   `bool isPunct (self)`
*   `bool isSpace (self)`
*   `bool isSymbol (self)`
*   `bool isTitleCase (self)`
*   `bool isUpper (self)`
*   `Joining joining (self)`
*   `QChar mirroredChar (self)`
*   `str row (self)`
*   `setCell (self, str acell)`
*   `setRow (self, str arow)`
*   `str toAscii (self)`
*   `QChar toCaseFolded (self)`
*   `str toLatin1 (self)`
*   `QChar toLower (self)`
*   `QChar toTitleCase (self)`
*   `QChar toUpper (self)`
*   `int unicode (self)`
*   `UnicodeVersion unicodeVersion (self)`

### Static Methods

*   `Category category (int ucs4)`
*   `str combiningClass (int ucs4)`
*   `UnicodeVersion currentUnicodeVersion ()`
*   `QString decomposition (int ucs4)`
*   `Decomposition decompositionTag (int ucs4)`
*   `int digitValue (int ucs4)`
*   `Direction direction (int ucs4)`
*   `QChar fromAscii (str c)`
*   `QChar fromLatin1 (str c)`
*   `int highSurrogate (int ucs4)`
*   `bool isHighSurrogate (int ucs4)`
*   `bool isLowSurrogate (int ucs4)`
*   `Joining joining (int ucs4)`
*   `int lowSurrogate (int ucs4)`
*   `int mirroredChar (int ucs4)`
*   `bool requiresSurrogates (int ucs4)`
*   `int surrogateToUcs4 (int high, int low)`
*   `int surrogateToUcs4 (QChar high, QChar low)`
*   `int toCaseFolded (int ucs4)`
*   `int toLower (int ucs4)`
*   `int toTitleCase (int ucs4)`
*   `int toUpper (int ucs4)`
*   `UnicodeVersion unicodeVersion (int ucs4)`

### Special Methods

*   `QString __add__ (self, QString s2)`
*   `bool __eq__ (self, QChar c2)`
*   `bool __ge__ (self, QChar c2)`
*   `bool __gt__ (self, QChar c2)`
*   `int __hash__ (self)`
*   `bool __le__ (self, QChar c2)`
*   `bool __lt__ (self, QChar c2)`
*   `bool __ne__ (self, QChar c2)`
*   `str __repr__ (self)`
*   `str __str__ (self)`
*   `unicode __unicode__ (self)`

* * *

## Detailed Description

这个类可以醃制。

该QChar类提供了一个16位的Unicode字符。

在Qt中， Unicode字符是没有任何标记或结构的16位实体。此类表示这样的实体。它是轻量级的，因此它可以随处使用。大多数编译器把它当作`unsigned short`。

QChar提供的测试/分类功能全套，转换和从其他格式，从组成到分解的Unicode转换，并试图比较和大小写转换，如果你问它。

分类功能包括像那些在标准C + +头\u003ccctype\u003e （原\u003cCTYPE.H\u003e ）功能，但在全方位的Unicode字符操作。他们都返回True，如果该字符是某种类型的字符，否则返回假。这些分类功能[isNull](qchar.html#isNull)（ ） （如果字符是'\ 0'返回True ） ，[isPrint](qchar.html#isPrint)（ ） （ True如果字符是任何类型的可打印字符，包括空格的） ，[isPunct](qchar.html#isPunct)（ ） （任何种类的点状的） ，[isMark](qchar.html#isMark)（ ） （ Unicode的标志） ，[isLetter](qchar.html#isLetter)（ ） （一个字母） ，[isNumber](qchar.html#isNumber)（ ） （任何种类的数字字符，不只是0-9 ） ，[isLetterOrNumber](qchar.html#isLetterOrNumber)（）和[isDigit](qchar.html#isDigit)（ ） （小数位数） 。所有这些都是围绕包装[category](qchar.html#category)（ ），它返回的Unicode定义的每个字符的类别。

QChar还提供[direction](qchar.html#direction)（ ），表示这个人物的“自然”的写作方向。该[joining](qchar.html#joining)（ ）函数指示如何连接字符与邻国（主要是阿拉伯语需要） ，最后[hasMirrored](qchar.html#hasMirrored)（ ），这表明该字符是否需要打印时在其“非自然”的写作方向进行镜像。

由Unicode字符（如A ）可以通过使用被转换为Unicode的分解（ “一”加“环以上” ）[decomposition](qchar.html#decomposition)（ ） 。

在Unicode中，比较未必能够和大小写转换是非常困难的最好的。 Unicode的，涵盖了“全”的世界，也包括世界上大部分的情况下和排序问题。运算符== （）和朋友会做的字符的数值Unicode值（代码点）完全基于比较和[toUpper](qchar.html#toUpper)（）和[toLower](qchar.html#toLower)（ ）会做改变的情况下，当角色有一个明确定义的大写/小写形式。对于区域设置相关的比较，使用[QString.localeAwareCompare](qstring.html#localeAwareCompare)（ ） 。

该转换功能包括[unicode](qchar.html#unicode)（ ）（一个标量） ，[toLatin1](qchar.html#toLatin1)（ ） （标量，但将所有非Latin-1字符为0） ，[row](qchar.html#row)（ ） （给出了统一行） ，[cell](qchar.html#cell)（ ） （给出了Unicode的细胞） ，[digitValue](qchar.html#digitValue)（ ） （给出任何的众多数字字符的整数值） ，以及一系列的构造函数。

QChar提供了构造函数和类型转换运算符，可以很容易转换，并从传统的8位`char`秒。如果你定义`QT_NO_CAST_FROM_ASCII`和`QT_NO_CAST_TO_ASCII`，如在解释[QString](qstring.html)文档，你将需要显式调用[fromAscii](qchar.html#fromAscii)（）或[fromLatin1](qchar.html#fromLatin1)（ ） ，或使用[QLatin1Char](qlatin1char.html)，从8位构建QChar`char`，你将需要调用[toAscii](qchar.html#toAscii)（）或[toLatin1](qchar.html#toLatin1)（ ）来得到8位的值返回。

* * *

## Type Documentation

```
QChar.Category
```

此枚举映射的Unicode字符类别。

下面的字符是规范性的统一：

| Constant | Value | Description |
| --- | --- | --- |
| `QChar.Mark_NonSpacing` | `1` | Unicode类名的Mn |
| `QChar.Mark_SpacingCombining` | `2` | Unicode类名MC |
| `QChar.Mark_Enclosing` | `3` | Unicode类的名字我 |
| `QChar.Number_DecimalDigit` | `4` | Unicode类名的Nd |
| `QChar.Number_Letter` | `5` | Unicode类名标准升 |
| `QChar.Number_Other` | `6` | Unicode类名无 |
| `QChar.Separator_Space` | `7` | Unicode类Zs的名字 |
| `QChar.Separator_Line` | `8` | Unicode类名ZL |
| `QChar.Separator_Paragraph` | `9` | Unicode类名Zp中 |
| `QChar.Other_Control` | `10` | Unicode类名副本 |
| `QChar.Other_Format` | `11` | Unicode类名比照 |
| `QChar.Other_Surrogate` | `12` | Unicode类名铯 |
| `QChar.Other_PrivateUse` | `13` | Unicode类公司名称 |
| `QChar.Other_NotAssigned` | `14` | Unicode类名称CN |

以下类别的信息以Unicode ：

| Constant | Value | Description |
| --- | --- | --- |
| `QChar.Letter_Uppercase` | `15` | Unicode类名陆 |
| `QChar.Letter_Lowercase` | `16` | Unicode类名LL |
| `QChar.Letter_Titlecase` | `17` | Unicode类名中尉 |
| `QChar.Letter_Modifier` | `18` | Unicode类名流明 |
| `QChar.Letter_Other` | `19` | Unicode类名罗 |
| `QChar.Punctuation_Connector` | `20` | Unicode类名称PC |
| `QChar.Punctuation_Dash` | `21` | Unicode类名的Pd |
| `QChar.Punctuation_Open` | `22` | Unicode类名诗 |
| `QChar.Punctuation_Close` | `23` | Unicode类名PE |
| `QChar.Punctuation_InitialQuote` | `24` | Unicode类名皮 |
| `QChar.Punctuation_FinalQuote` | `25` | Unicode类名PF |
| `QChar.Punctuation_Other` | `26` | Unicode类名宝 |
| `QChar.Symbol_Math` | `27` | Unicode类名称SM |
| `QChar.Symbol_Currency` | `28` | Unicode类名钪 |
| `QChar.Symbol_Modifier` | `29` | Unicode类名Sk的 |
| `QChar.Symbol_Other` | `30` | Unicode的类名，这样 |
| `QChar.NoCategory` | `0` | Qt可以找不到一个合适的类别的字符。 |

**See also** [category](qchar.html#category)（ ） 。

```
QChar.CombiningClass
```

```
QChar.Decomposition
```

这个枚举类型定义了Unicode的分解特性。请参阅[Unicode Standard](http://www.unicode.org/)对值的说明。

| Constant | Value |
| --- | --- |
| `QChar.NoDecomposition` | `0` |
| `QChar.Canonical` | `1` |
| `QChar.Circle` | `8` |
| `QChar.Compat` | `16` |
| `QChar.Final` | `6` |
| `QChar.Font` | `2` |
| `QChar.Fraction` | `17` |
| `QChar.Initial` | `4` |
| `QChar.Isolated` | `7` |
| `QChar.Medial` | `5` |
| `QChar.Narrow` | `13` |
| `QChar.NoBreak` | `3` |
| `QChar.Small` | `14` |
| `QChar.Square` | `15` |
| `QChar.Sub` | `10` |
| `QChar.Super` | `9` |
| `QChar.Vertical` | `11` |
| `QChar.Wide` | `12` |

**See also** [decomposition](qchar.html#decomposition)（ ） 。

```
QChar.Direction
```

这个枚举类型定义了统一的方向属性。请参阅[Unicode Standard](http://www.unicode.org/)对值的说明。

为了符合C / C + +的命名约定“dir”是预先考虑到Unicode标准中使用的代码。

| Constant | Value |
| --- | --- |
| `QChar.DirAL` | `13` |
| `QChar.DirAN` | `5` |
| `QChar.DirB` | `7` |
| `QChar.DirBN` | `18` |
| `QChar.DirCS` | `6` |
| `QChar.DirEN` | `2` |
| `QChar.DirES` | `3` |
| `QChar.DirET` | `4` |
| `QChar.DirL` | `0` |
| `QChar.DirLRE` | `11` |
| `QChar.DirLRO` | `12` |
| `QChar.DirNSM` | `17` |
| `QChar.DirON` | `10` |
| `QChar.DirPDF` | `16` |
| `QChar.DirR` | `1` |
| `QChar.DirRLE` | `14` |
| `QChar.DirRLO` | `15` |
| `QChar.DirS` | `8` |
| `QChar.DirWS` | `9` |

**See also** [direction](qchar.html#direction)（ ） 。

```
QChar.Joining
```

这个枚举类型定义的Unicode加入属性。请参阅[Unicode Standard](http://www.unicode.org/)对值的说明。

| Constant | Value |
| --- | --- |
| `QChar.Center` | `3` |
| `QChar.Dual` | `1` |
| `QChar.OtherJoining` | `0` |
| `QChar.Right` | `2` |

**See also** [joining](qchar.html#joining)（ ） 。

```
QChar.SpecialCharacter
```

| Constant | Value | Description |
| --- | --- | --- |
| `QChar.Null` | `0x0000` | A [QChar](qchar.html)与此值[isNull](qchar.html#isNull)（ ） 。 |
| `QChar.Nbsp` | `0x00a0` | 不换行空格。 |
| `QChar.ReplacementCharacter` | `0xfffd` | 所示的字符时，字体没有字形一定的编码点。一个特殊的问号字符被经常使用。编解码器使用此代码点，当输入的数据不能以Unicode来表示。 |
| `QChar.ObjectReplacementCharacter` | `0xfffc` | 用于表示一个对象，例如图像时这样的对象不能被提交。 |
| `QChar.ByteOrderMark` | `0xfeff` |   |
| `QChar.ByteOrderSwapped` | `0xfffe` |   |
| `QChar.ParagraphSeparator` | `0x2029` |   |
| `QChar.LineSeparator` | `0x2028` |   |

```
QChar.UnicodeVersion
```

指定哪些版本[Unicode standard](http://www.unicode.org/)引入了一定的角色。

| Constant | Value | Description |
| --- | --- | --- |
| `QChar.Unicode_1_1` | `1` | 1.1版 |
| `QChar.Unicode_2_0` | `2` | 2.0版 |
| `QChar.Unicode_2_1_2` | `3` | 版本2.1.2 |
| `QChar.Unicode_3_0` | `4` | 3.0版 |
| `QChar.Unicode_3_1` | `5` | 3.1版 |
| `QChar.Unicode_3_2` | `6` | 3.2版 |
| `QChar.Unicode_4_0` | `7` | 4.0版 |
| `QChar.Unicode_4_1` | `8` | 4.1版 |
| `QChar.Unicode_5_0` | `9` | 5.0版 |
| `QChar.Unicode_Unassigned` | `0` | 该值不会分配给任何字符的Unicode 5.0版。 |

**See also** [unicodeVersion](qchar.html#unicodeVersion)（ ） 。

* * *

## Method Documentation

```
QChar.__init__ (self)
```

构造一个空[QChar](qchar.html)（ '\ 0' ） 。

**See also** [isNull](qchar.html#isNull)（ ） 。

```
QChar.__init__ (self, str c)
```

构造一个[QChar](qchar.html)对应ASCII/Latin-1字符_ch_。

```
QChar.__init__ (self, QLatin1Char ch)
```

构造一个[QChar](qchar.html)对应ASCII/Latin-1字符_ch_。

```
QChar.__init__ (self, str c, str r)
```

构造一个[QChar](qchar.html)对应ASCII/Latin-1字符_ch_。

```
QChar.__init__ (self, int rc)
```

构造一个[QChar](qchar.html)对于Unicode细胞_cell_行_row_。

**See also** [cell](qchar.html#cell)（）和[row](qchar.html#row)（ ） 。

```
QChar.__init__ (self, SpecialCharacter s)
```

构造一个[QChar](qchar.html)对于字符与Unicode代码点_code_。

```
QChar.__init__ (self, QChar)
```

构造一个[QChar](qchar.html)对于字符与Unicode代码点_code_。

```
Category QChar.category (self)
```

[

返回字符的类别。

](qchar.html#Category-enum)

```
Category QChar.category (int ucs4)
```

[

这是一个重载函数。

返回由指定的UCS - 4编码的字符的类别_ucs4_。

此功能被引入Qt的4.3 。

```
str QChar.cell (self)
```

返回Unicode字符的单元格（最显着字节） 。

](qchar.html#Category-enum)

[**See also**](qchar.html#Category-enum) [row](qchar.html#row)（ ） 。

```
str QChar.combiningClass (self)
```

返回结合类的字符作为Unicode标准定义。这主要是有用的定位提示为连接到一个基本字符标记。

Qt的文本渲染引擎使用这些信息来正确定位围绕一个基本字符为非空格标记。

```
str QChar.combiningClass (int ucs4)
```

这是一个重载函数。

返回组合类由指定的UCS - 4编码的字符_ucs4_，如Unicode标准定义。

```
UnicodeVersion QChar.currentUnicodeVersion ()
```

[

返回最近支持Unicode版本。

此功能被引入Qt的4.8 。

```
QString QChar.decomposition (self)
```

分解一个字符到它的部分。返回如果没有分解存在一个空字符串。

```
QString QChar.decomposition (int ucs4)
```

这是一个重载函数。

分解所指定的UCS - 4编码的字符_ucs4_成其组成部分。返回如果没有分解存在一个空字符串。

](qchar.html#UnicodeVersion-enum)

```
Decomposition QChar.decompositionTag (self)
```

[](qchar.html#Decomposition-enum)

[返回定义的字符的组合物中的标记。回报](qchar.html#Decomposition-enum)[QChar.Single](qchar.html#Decomposition-enum)如果没有分解的存在。

```
Decomposition QChar.decompositionTag (int ucs4)
```

[

这是一个重载函数。

](qchar.html#Decomposition-enum)

[返回定义所指定的UCS-4编码的字符的组合物中的标记_ucs4_。回报](qchar.html#Decomposition-enum)[QChar.Single](qchar.html#Decomposition-enum)如果没有分解的存在。

```
int QChar.digitValue (self)
```

返回数字的数值，或者-1如果字符是不是数字。

```
int QChar.digitValue (int ucs4)
```

这是一个重载函数。

返回数字的数字值，由UCS-2编码的字符指定_ucs2_，或-1，如果字符不是一个数字。

```
Direction QChar.direction (self)
```

[

返回字符的方向。

](qchar.html#Direction-enum)

```
Direction QChar.direction (int ucs4)
```

[

这是一个重载函数。

返回由指定的UCS - 4编码的字符的方向_ucs4_。

```
QChar QChar.fromAscii (str c)
```

](qchar.html#Direction-enum)

[ASCII字符转换_c_它的等效](qchar.html#Direction-enum)[QChar](qchar.html)。这主要是针对非国际化的软件非常有用。

一个替代方案是使用[QLatin1Char](qlatin1char.html)。

**See also** [fromLatin1](qchar.html#fromLatin1)（ ）[unicode](qchar.html#unicode)（）和[QTextCodec.codecForCStrings](qtextcodec.html#codecForCStrings)（ ） 。

```
QChar QChar.fromLatin1 (str c)
```

拉丁- 1字符转换_c_它的等效[QChar](qchar.html)。这主要是针对非国际化的软件非常有用。

**See also** [fromAscii](qchar.html#fromAscii)（ ）[unicode](qchar.html#unicode)（）和[QTextCodec.codecForCStrings](qtextcodec.html#codecForCStrings)（ ） 。

```
bool QChar.hasMirrored (self)
```

返回True如果如果文本方向是相反的性格应该得到扭转，否则返回False 。

同（章[mirroredChar](qchar.html#mirroredChar)（ ！） = CH） 。

**See also** [mirroredChar](qchar.html#mirroredChar)（ ） 。

```
int QChar.highSurrogate (int ucs4)
```

返回一个UCS4代码点的高代理项值。返回的结果是不确定的，如果_ucs4_比0x10000处小。

```
bool QChar.isDigit (self)
```

如果字符是十进制数字，则返回True （[Number_DecimalDigit](qchar.html#Category-enum)），否则返回False 。

```
bool QChar.isHighSurrogate (self)
```

返回True如果[QChar](qchar.html)是UTF16代理（也就是说，如果它的代码点是0xd800和0xdbff （含）之间）的高位部分。

```
bool QChar.isHighSurrogate (int ucs4)
```

返回True如果指定的UCS - 4编码的字符_ucs4_是UTF16代理（也就是说，如果它的代码点是0xd800和0xdbff （含）之间）的高位部分。

此功能被引入Qt的4.7 。

```
bool QChar.isLetter (self)
```

返回True如果该字符是字母（ Letter_ *类），否则返回False 。

```
bool QChar.isLetterOrNumber (self)
```

返回True如果该字符是字母或数字（ Letter_ *或[Number_](index.htm#number)*类），否则返回False 。

```
bool QChar.isLower (self)
```

返回True如果该字符是小写字母，即[category](qchar.html#category)（）是[Letter_Lowercase](qchar.html#Category-enum)。

**See also** [isUpper](qchar.html#isUpper)（ ）[toLower](qchar.html#toLower)（）和[toUpper](qchar.html#toUpper)（ ） 。

```
bool QChar.isLowSurrogate (self)
```

返回True如果[QChar](qchar.html)是UTF16代理（也就是说，如果它的代码点是介于0xDC00和0xdfff （含）之间）的低部。

```
bool QChar.isLowSurrogate (int ucs4)
```

返回True如果指定的UCS - 4编码的字符_ucs4_是UTF16代理（也就是说，如果它的代码点是介于0xDC00和0xdfff （含）之间）的低部。

此功能被引入Qt的4.7 。

```
bool QChar.isMark (self)
```

返回True如果字符是标记（ Mark_ *类），否则返回False 。

See [QChar.Category](qchar.html#Category-enum)了解有关标记的更多信息。

```
bool QChar.isNull (self)
```

返回True如果该字符是Unicode字符为0x0000 （ '\ 0' ），否则返回False 。

```
bool QChar.isNumber (self)
```

返回True如果该字符是数字（[Number_](index.htm#number)*类别，而不只是0-9 ），否则返回False 。

**See also** [isDigit](qchar.html#isDigit)（ ） 。

```
bool QChar.isPrint (self)
```

返回True如果字符是可打印字符，否则返回False 。这是不是类抄送或CN任意字符。

请注意，这没有给出的字符是否是在一个特定的字体。

```
bool QChar.isPunct (self)
```

返回True如果字符是一个标点符号（ Punctuation_ *类），否则返回False 。

```
bool QChar.isSpace (self)
```

返回True如果该字符是一个分隔符（ Separator_ *类），否则返回False 。

```
bool QChar.isSymbol (self)
```

返回True如果该字符是符号（ Symbol_ *类），否则返回False 。

```
bool QChar.isTitleCase (self)
```

返回True如果该字符是首字母大写字母，即[category](qchar.html#category)（）是[Letter_Titlecase](qchar.html#Category-enum)。

此功能被引入Qt的4.3 。

**See also** [isLower](qchar.html#isLower)（ ）[toUpper](qchar.html#toUpper)（ ）[toLower](qchar.html#toLower)（）和[toTitleCase](qchar.html#toTitleCase)（ ） 。

```
bool QChar.isUpper (self)
```

返回True如果该字符是一个大写字母，即[category](qchar.html#category)（）是[Letter_Uppercase](qchar.html#Category-enum)。

**See also** [isLower](qchar.html#isLower)（ ）[toUpper](qchar.html#toUpper)（）和[toLower](qchar.html#toLower)（ ） 。

```
Joining QChar.joining (self)
```

[

返回有关字符（需要一定的语言，如阿拉伯语）的连接属性的信息。

](qchar.html#Joining-enum)

```
Joining QChar.joining (int ucs4)
```

[

这是一个重载函数。

返回有关指定的UCS - 4编码的字符的连接属性的信息_ucs4_（需要特定的语言，如阿拉伯语） 。

```
int QChar.lowSurrogate (int ucs4)
```

返回一个UCS4代码点的低代理项值。返回的结果是不确定的，如果_ucs4_比0x10000处小。

```
QChar QChar.mirroredChar (self)
```

返回镜像的字符，如果这个字符是一个镜像字符，否则返回字符本身。

](qchar.html#Joining-enum)

[**See also**](qchar.html#Joining-enum) [hasMirrored](qchar.html#hasMirrored)（ ） 。

```
int QChar.mirroredChar (int ucs4)
```

这是一个重载函数。

返回镜像的字符，如果所指定的UCS - 4编码的字符_ucs4_是一个镜像字符，否则返回字符本身。

**See also** [hasMirrored](qchar.html#hasMirrored)（ ） 。

```
bool QChar.requiresSurrogates (int ucs4)
```

返回True如果指定的UCS - 4编码的字符_ucs4_可以拆分成UTF16替代的高和低的部分（也就是说，如果它的代码点大于或等于0x10000处） 。

此功能被引入Qt的4.7 。

```
str QChar.row (self)
```

返回Unicode字符的行（最显着字节）。

**See also** [cell](qchar.html#cell)（ ） 。

```
QChar.setCell (self, str acell)
```

```
QChar.setRow (self, str arow)
```

```
int QChar.surrogateToUcs4 (int high, int low)
```

一个UTF16代理对给定的转换_high_和_low_值其UCS- 4码点。

```
int QChar.surrogateToUcs4 (QChar high, QChar low)
```

一个UTF16代理对（转换_high_，_low_）其UCS4代码点。

```
str QChar.toAscii (self)
```

返回的字符值[QChar](qchar.html)使用用于读取C字符串当前的编解码器，或者0，如果使用此编解码器的字符是不能表示获得的。默认的编解码处理的Latin-1编码的文本，但是这是可以改变的，以帮助开发人员使用其它的编码编写源代码。

此功能的主要目的是保存在C字符串中使用ASCII字符。这主要是针对非国际化的软件开发者很有用。

**See also** [toLatin1](qchar.html#toLatin1)（ ）[unicode](qchar.html#unicode)（）和[QTextCodec.codecForCStrings](qtextcodec.html#codecForCStrings)（ ） 。

```
QChar QChar.toCaseFolded (self)
```

返回的情况下折叠的字符等效的。对于大多数的Unicode字符，这是相同toLowerCase （） 。

```
int QChar.toCaseFolded (int ucs4)
```

这是一个重载函数。

返回的情况下通过折叠指定的UCS - 4编码的字符等效_ucs4_。对于大多数的Unicode字符，这是相同toLowerCase （） 。

```
str QChar.toLatin1 (self)
```

返回的Latin-1字符等同于[QChar](qchar.html)或0。这主要是针对非国际化的软件非常有用。

**See also** [toAscii](qchar.html#toAscii)（ ）[unicode](qchar.html#unicode)（）和[QTextCodec.codecForCStrings](qtextcodec.html#codecForCStrings)（ ） 。

```
QChar QChar.toLower (self)
```

返回小写等效如果字符是大写或首字母大写，否则返回字符本身。

```
int QChar.toLower (int ucs4)
```

这是一个重载函数。

返回由指定的UCS - 4编码的字符的小写等效_ucs4_如果字符是大写或首字母大写，否则返回字符本身。

```
QChar QChar.toTitleCase (self)
```

返回标题等同的情况下如果字符是小写或大写，否则返回字符本身。

```
int QChar.toTitleCase (int ucs4)
```

这是一个重载函数。

返回标题等同的情况下通过指定的UCS - 4编码的字符_ucs4_如果字符是小写或大写，否则返回字符本身。

```
QChar QChar.toUpper (self)
```

返回大写等价的，如果该字符是小写或首字母大写，否则返回字符本身。

```
int QChar.toUpper (int ucs4)
```

这是一个重载函数。

返回由指定的UCS - 4编码的字符的大写形式_ucs4_如果字符是小写或首字母大写，否则返回字符本身。

```
int QChar.unicode (self)
```

返回一个引用的数字Unicode值[QChar](qchar.html)。

```
UnicodeVersion QChar.unicodeVersion (self)
```

[

返回介绍这个人物的Unicode版本。

](qchar.html#UnicodeVersion-enum)

```
UnicodeVersion QChar.unicodeVersion (int ucs4)
```

[

这是一个重载函数。

返回介绍了其UCS- 4编码的形式指定的字符的Unicode版本_ucs4_。

```
QString QChar.__add__ (self, QString s2)
```

```
bool QChar.__eq__ (self, QChar c2)
```

```
bool QChar.__ge__ (self, QChar c2)
```

```
bool QChar.__gt__ (self, QChar c2)
```

```
int QChar.__hash__ (self)
```

```
bool QChar.__le__ (self, QChar c2)
```

```
bool QChar.__lt__ (self, QChar c2)
```

```
bool QChar.__ne__ (self, QChar c2)
```

```
str QChar.__repr__ (self)
```

```
str QChar.__str__ (self)
```

```
unicode QChar.__unicode__ (self)
```

](qchar.html#UnicodeVersion-enum)