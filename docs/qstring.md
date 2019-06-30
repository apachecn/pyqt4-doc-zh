# QString Class Reference

## [[QtCore](index.htm) module]

QString类提供了一个Unicode字符的字符串。[More...](#details)

### Types

*   `enum NormalizationForm { NormalizationForm_D, NormalizationForm_C, NormalizationForm_KD, NormalizationForm_KC }`
*   `enum SectionFlag { SectionDefault, SectionSkipEmpty, SectionIncludeLeadingSep, SectionIncludeTrailingSep, SectionCaseInsensitiveSeps }`
*   `class **[SectionFlags](index.htm)**`
*   `enum SplitBehavior { KeepEmptyParts, SkipEmptyParts }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QKeySequence)`
*   `__init__ (self, QScriptString)`
*   `__init__ (self, int size, QChar c)`
*   `__init__ (self, QString s)`
*   `__init__ (self, QByteArray a)`
*   `__init__ (self, QUuid)`
*   `QString append (self, QString s)`
*   `QString append (self, QLatin1String s)`
*   `QString append (self, QByteArray s)`
*   `QString arg (self, int a, int fieldWidth = 0, int base = 10, QChar fillChar = QLatin1Char(' '))`
*   `QString arg (self, float a, int fieldWidth = 0, str format = 'g', int precision = -1, QChar fillChar = QLatin1Char(' '))`
*   `QString arg (self, int a, int fieldWidth = 0, int base = 10, QChar fillChar = QLatin1Char(' '))`
*   `QString arg (self, int a, int fieldWidth = 0, int base = 10, QChar fillChar = QLatin1Char(' '))`
*   `QString arg (self, QString a, int fieldWidth = 0, QChar fillChar = QLatin1Char(' '))`
*   `QString arg (self, QString a1, QString a2)`
*   `QString arg (self, QString a1, QString a2, QString a3)`
*   `QString arg (self, QString a1, QString a2, QString a3, QString a4)`
*   `QString arg (self, QString a1, QString a2, QString a3, QString a4, QString a5)`
*   `QString arg (self, QString a1, QString a2, QString a3, QString a4, QString a5, QString a6)`
*   `QString arg (self, QString a1, QString a2, QString a3, QString a4, QString a5, QString a6, QString a7)`
*   `QString arg (self, QString a1, QString a2, QString a3, QString a4, QString a5, QString a6, QString a7, QString a8)`
*   `QString arg (self, QString a1, QString a2, QString a3, QString a4, QString a5, QString a6, QString a7, QString a8, QString a9)`
*   `QChar at (self, int i)`
*   `int capacity (self)`
*   `chop (self, int n)`
*   `clear (self)`
*   `int compare (self, QString s)`
*   `int compare (self, QString s, Qt.CaseSensitivity cs)`
*   `int compare (self, QLatin1String other, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int compare (self, QStringRef ref, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `bool contains (self, QString str, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `bool contains (self, QStringRef s, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `bool contains (self, QRegExp rx)`
*   `int count (self)`
*   `int count (self, QString str, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int count (self, QStringRef str, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int count (self, QRegExp)`
*   `bool endsWith (self, QString s, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `bool endsWith (self, QStringRef s, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `bool endsWith (self, QLatin1String s, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `QString fill (self, QChar ch, int size = -1)`
*   `int indexOf (self, QString str, int from = 0, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int indexOf (self, QStringRef str, int from = 0, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int indexOf (self, QLatin1String str, int from = 0, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int indexOf (self, QRegExp rx, int from = 0)`
*   `QString insert (self, int i, QString s)`
*   `QString insert (self, int i, QLatin1String s)`
*   `bool isEmpty (self)`
*   `bool isNull (self)`
*   `bool isRightToLeft (self)`
*   `bool isSimpleText (self)`
*   `int lastIndexOf (self, QString str, int from = -1, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int lastIndexOf (self, QStringRef str, int from = -1, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int lastIndexOf (self, QLatin1String str, int from = -1, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int lastIndexOf (self, QRegExp rx, int from = -1)`
*   `QString left (self, int len)`
*   `QString leftJustified (self, int width, QChar fillChar = QLatin1Char(' '), bool truncate = False)`
*   `int length (self)`
*   `int localeAwareCompare (self, QString s)`
*   `int localeAwareCompare (self, QStringRef s)`
*   `QString mid (self, int position, int n = -1)`
*   `QString normalized (self, NormalizationForm mode)`
*   `QString normalized (self, NormalizationForm mode, QChar.UnicodeVersion version)`
*   `QString prepend (self, QString s)`
*   `QString prepend (self, QLatin1String s)`
*   `QString prepend (self, QByteArray s)`
*   `push_back (self, QString s)`
*   `push_front (self, QString s)`
*   `QString remove (self, int i, int len)`
*   `QString remove (self, QString str, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `QString remove (self, QRegExp rx)`
*   `QString repeated (self, int times)`
*   `QString replace (self, int i, int len, QString after)`
*   `QString replace (self, QString before, QString after, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `QString replace (self, QRegExp rx, QString after)`
*   `QString replace (self, QLatin1String before, QLatin1String after, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `QString replace (self, QLatin1String before, QString after, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `QString replace (self, QString before, QLatin1String after, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `reserve (self, int asize)`
*   `resize (self, int size)`
*   `QString right (self, int len)`
*   `QString rightJustified (self, int width, QChar fillChar = QLatin1Char(' '), bool truncate = False)`
*   `QString section (self, QString sep, int start, int end = -1, SectionFlags flags = QString.SectionDefault)`
*   `QString section (self, QRegExp reg, int start, int end = -1, SectionFlags flags = QString.SectionDefault)`
*   `QString setNum (self, int n, int base = 10)`
*   `QString setNum (self, float n, str format = 'g', int precision = 6)`
*   `QString setNum (self, int n, int base = 10)`
*   `QString setNum (self, int n, int base = 10)`
*   `QString simplified (self)`
*   `int size (self)`
*   `QStringList split (self, QString sep, SplitBehavior behavior = QString.KeepEmptyParts, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `QStringList split (self, QRegExp sep, SplitBehavior behavior = QString.KeepEmptyParts)`
*   `squeeze (self)`
*   `bool startsWith (self, QString s, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `bool startsWith (self, QStringRef s, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `bool startsWith (self, QLatin1String s, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `swap (self, QString other)`
*   `QByteArray toAscii (self)`
*   `QString toCaseFolded (self)`
*   `(float, bool ok) toDouble (self)`
*   `(float, bool ok) toFloat (self)`
*   `(int, bool ok) toInt (self, int base = 10)`
*   `QByteArray toLatin1 (self)`
*   `QByteArray toLocal8Bit (self)`
*   `(int, bool ok) toLong (self, int base = 10)`
*   `(int, bool ok) toLongLong (self, int base = 10)`
*   `QString toLower (self)`
*   `(int, bool ok) toShort (self, int base = 10)`
*   `(int, bool ok) toUInt (self, int base = 10)`
*   `(int, bool ok) toULong (self, int base = 10)`
*   `(int, bool ok) toULongLong (self, int base = 10)`
*   `QString toUpper (self)`
*   `(int, bool ok) toUShort (self, int base = 10)`
*   `QByteArray toUtf8 (self)`
*   `QString trimmed (self)`
*   `truncate (self, int pos)`

### Static Methods

*   `int compare (QString s1, QString s2)`
*   `int compare (QString s1, QString s2, Qt.CaseSensitivity cs)`
*   `int compare (QString s1, QLatin1String s2, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int compare (QLatin1String s1, QString s2, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `int compare (QString s1, QStringRef s2, Qt.CaseSensitivity cs = Qt.CaseSensitive)`
*   `QString fromAscii (str str, int size = -1)`
*   `QString fromLatin1 (str str, int size = -1)`
*   `QString fromLocal8Bit (str str, int size = -1)`
*   `QString fromUtf8 (str str, int size = -1)`
*   `int localeAwareCompare (QString s1, QString s2)`
*   `int localeAwareCompare (QString s1, QStringRef s2)`
*   `QString number (int n, int base = 10)`
*   `QString number (float n, str format = 'g', int precision = 6)`
*   `QString number (int n, int base = 10)`
*   `QString number (int n, int base = 10)`

### Special Methods

*   `QString __add__ (self, QString s2)`
*   `QString __add__ (self, QByteArray ba)`
*   `int __contains__ (self, QString s)`
*   `bool __eq__ (self, QString s)`
*   `bool __eq__ (self, QLatin1String s)`
*   `bool __eq__ (self, QByteArray s)`
*   `bool __eq__ (self, QStringRef s2)`
*   `bool __ge__ (self, QString s)`
*   `bool __ge__ (self, QLatin1String s)`
*   `bool __ge__ (self, QByteArray s)`
*   `QString __getitem__ (self, int i)`
*   `QString __getitem__ (self, slice slice)`
*   `bool __gt__ (self, QString s)`
*   `bool __gt__ (self, QLatin1String s)`
*   `bool __gt__ (self, QByteArray s)`
*   `int __hash__ (self)`
*   `QString __iadd__ (self, QChar.SpecialCharacter c)`
*   `QString __iadd__ (self, QString s)`
*   `QString __iadd__ (self, QLatin1String s)`
*   `QString __iadd__ (self, QByteArray s)`
*   `QString __imul__ (self, int m)`
*   `bool __le__ (self, QString s)`
*   `bool __le__ (self, QLatin1String s)`
*   `bool __le__ (self, QByteArray s)`
*   `__len__ (self)`
*   `bool __lt__ (self, QString s)`
*   `bool __lt__ (self, QLatin1String s)`
*   `bool __lt__ (self, QByteArray s)`
*   `QString __mul__ (self, int m)`
*   `bool __ne__ (self, QString s)`
*   `bool __ne__ (self, QLatin1String s)`
*   `bool __ne__ (self, QByteArray s)`
*   `bool __ne__ (self, QStringRef s2)`
*   `str __repr__ (self)`
*   `str __str__ (self)`
*   `unicode __unicode__ (self)`

* * *

## Detailed Description

这个类可以醃制。

一个Python字符串或使用unicode对象，[QLatin1String](qlatin1string.html)或[QChar](qchar.html)可用于每当一个[QString](qstring.html)预计。

QString类提供了一个Unicode字符的字符串。

卖场QString的16位字符串[QChar](qchar.html)s，其中每个[QChar](qchar.html)对应1的Unicode 4.0字符。 （ Unicode字符代码值高于65535使用代理对存储，也就是说，两个连续的[QChar](qchar.html)秒。 ）

[Unicode](index.htm#unicode)今天，它支持大多数的书写系统中使用的国际标准。它是US-ASCII （ ANSI X3.4 - 1986）和拉丁语-1 （ ISO 8859-1 ）的一个超集，所有的US-ASCII/Latin-1字符可在相同的代码的位置。

在幕后，使用的QString[implicit sharing](index.htm)（复制上写的），以减少内存使用量，避免不必要的数据复制。这也有助于减少存储16位的字符，而不是8位字符的固有开销。

除了的QString ， Qt还提供了[QByteArray](qbytearray.html)类存储原始字节和传统的8位'\ 0'结尾的字符串。在大多数情况下， QString的是您要使用的类。它是用来在整个Qt的API和Unicode支持可以确保如果您想扩展您的应用程序的市场在某些时候你的应用程序将很容易翻译。两个主要的情况下[QByteArray](qbytearray.html)当您需要存储原始二进制数据是合适的，而当内存保护是至关重要的（例如，用[Qt for Embedded Linux](index.htm)） 。

### Initializing a String

初始化一个QString的一种方法是简单地传递一个`const char *`它的构造函数。例如，下面的代码创建一个包含数据的“Hello ”大小5的QString的：

```
 QString str = "Hello";

```

QString的转换`const char *`数据转换为Unicode使用[fromAscii](qstring.html#fromAscii)（）函数。默认情况下，[fromAscii](qstring.html#fromAscii)（ ）把字符以上128为Latin-1字符，但是这可以通过调用改变[QTextCodec.setCodecForCStrings](qtextcodec.html#setCodecForCStrings)（ ） 。

在所有的QString的函数取`const char *`参数，该`const char *`被解释为经典的C风格的'\ 0'结尾的字符串。它是合法的`const char *`参数为0 。

还可以提供字符串数据作为数组[QChar](qchar.html)S：

```
 static const [QChar](qchar.html) data[4] = { 0x0055, 0x006e, 0x10e3, 0x03a3 };
 QString str(data, 4);

```

做的QString的深层副本[QChar](qchar.html)数据，所以你可以在以后修改它没有遇到的副作用。 （如果由于性能原因你不希望采取的字符数据，使用深拷贝[QString.fromRawData](qstring.html#fromRawData)（ ）来代替。 ）

另一种方法是利用设置字符串的大小[resize](qstring.html#resize)（）和初始化每个字符的数据字符。 QString的使用基于0的索引，就像C + +中的数组。要访问该字符在特定索引位置，则可以使用[operator[]](qstring.html#operator-5b-5d)（ ） 。对非const的字符串，[operator[]](qstring.html#operator-5b-5d)（ ）返回一个引用，可以在赋值的左侧使用一个字符。例如：

```
 QString str;
 str.resize(4);

 str[0] = [QChar](qchar.html)('U');
 str[1] = [QChar](qchar.html)('n');
 str[2] = [QChar](qchar.html)(0x10e3);
 str[3] = [QChar](qchar.html)(0x03a3);

```

对于只读访问，另一种语法是使用[at](qstring.html#at)（ ）函数：

```
 QString str;

 for (int i = 0; i < str.size(); ++i) {
     if (str.at(i) >= [QChar](qchar.html)('a') && str.at(i) <= [QChar](qchar.html)('f'))
         qDebug() << "Found character in range [a-f]";
 }

```

该[at](qstring.html#at)（ ）函数可以比快[operator[]](qstring.html#operator-5b-5d)（），因为它不会导致一个[deep copy](index.htm#deep-copy)发生。或者，使用[left](qstring.html#left)（ ）[right](qstring.html#right)（） ，或[mid](qstring.html#mid)（ ）函数来在一个时间提取几个字符。

一个QString的可以嵌入'\ 0 '字符（[QChar.Null](qchar.html#SpecialCharacter-enum)） 。该[size](qstring.html#size)（ ）函数总是返回整个字符串的大小，包括嵌入式'\ 0 '字符。

调用后[resize](qstring.html#resize)（ ）函数，新分配的字符都未定义的值。要设置所有字符的字符串到一个特定的值，使用[fill](qstring.html#fill)（）函数。

的QString提供几十旨在简化字符串使用重载的。例如，如果你想一个QString的一个字符串字面量进行比较，可以写出这样的代码，它会如预期般运作：

```
 QString str;

 if (str == "auto" || str == "extern"
         || str == "static" || str == "register") {
     // ...
 }

```

您也可以字符串文字传递给需要将QString作为参数，调用的QString （为const char * ）构造函数。同样，你可以通过一个QString时，一个函数，它接受一个`const char *`使用的参数[qPrintable](index.htm#qPrintable)（）宏返回给定的QString作为`const char *`。这等效于调用\u003cQString\u003e 。[toLocal8Bit](qstring.html#toLocal8Bit)（ ） 。[constData](qstring.html#constData)（ ） 。

### Manipulating String Data

的QString提供了修饰的字符数据的基本功能如下：[append](qstring.html#append)（ ）[prepend](qstring.html#prepend)（ ）[insert](qstring.html#insert)（ ）[replace](qstring.html#replace)（）和[remove](qstring.html#remove)（ ） 。例如：

```
 QString str = "and";
 str.prepend("rock ");     // str == "rock and"
 str.append(" roll");        // str == "rock and roll"
 str.replace(5, 3, "&");   // str == "rock & roll"

```

如果你正在建设一个QString的逐渐提前知道大致的QString将有多少个字符包含，你可以调用[reserve](qstring.html#reserve)（ ） ，要求QString时，预先分配一定数量的内存。您也可以拨打[capacity](qstring.html#capacity)（）来找出多少内存QString的实际分配。

该[replace](qstring.html#replace)（）和[remove](qstring.html#remove)（ ）函数的前两个参数是要开始擦除，并应被删除的字符数的位置。如果你想更换另一特定字符串的所有匹配，使用这两个参数中的一个[replace](qstring.html#replace)（ ）重载。

一个常见的要求是从一个字符串（的'\ n '，' \ T' ，''，等等）删除空白字符。如果你想从一个QString的两端删除空白字符，请使用[trimmed](qstring.html#trimmed)（）函数。如果你想从两端删除空白和字符串中的单个空格字符替换多个连续的空格，使用[simplified](qstring.html#simplified)（ ） 。

如果你想找到一个特定的字符或子串中所有出现在一个QString的，使用[indexOf](qstring.html#indexOf)（）或[lastIndexOf](qstring.html#lastIndexOf)（）函数。前者向前搜索从给定的索引位置，后者向后搜索开始。都返回字符或字符串的索引位置，如果他们找到它，否则，它们将返回-1 。例如，下面是一个典型的循环，找到一个特定的子字符串的所有匹配：

```
 QString str = "We must be <b>bold</b>, very <b>bold</b>";
 int j = 0;

 while ((j = str.indexOf("<b>", j)) != -1) {
     qDebug() << "Found <b> tag at index position" << j;
     ++j;
 }

```

的QString提供了许多功能，将数字转换成字符串和字符串转换成数字。请参阅[arg](qstring.html#arg)（）函数，该[setNum](qstring.html#setNum)（）函数，该[number](qstring.html#number)（）静态函数，并且[toInt](qstring.html#toInt)（ ）[toDouble](qstring.html#toDouble)（） ，和类似的功能。

为了得到一个字符串使用大写或小写版本[toUpper](qstring.html#toUpper)（）或[toLower](qstring.html#toLower)（ ） 。

字符串列表是由处理[QStringList](qstringlist.html)类。您可以使用字符串分割成一个字符串列表的[split](qstring.html#split)（ ）函数，并加入字符串列表与一个可选的分离器使用一个单独的字符串[QStringList.join](qstringlist.html#join)（ ） 。你可以从一个字符串列表中包含特定字符串或匹配特定得到的字符串列表[QRegExp](qregexp.html)使用[QStringList.filter](qstringlist.html#filter)（）函数。

### Querying String Data

如果你想看看一个QString的启动或与特定的子串结束使用[startsWith](qstring.html#startsWith)（）或[endsWith](qstring.html#endsWith)（ ） 。如果你只是想检查的QString是否包含特定字符或字符串，可以使用[contains](qstring.html#contains)（）函数。如果你想了解有多少次一个特定的字符或子出现在字符串，使用[count](qstring.html#count)（ ） 。

将QString可以使用重载的运算符，例如进行比较[operator&lt;](qstring.html#operator-lt)（ ）[operator&lt;=](qstring.html#operator-lt-eq)（ ）[operator==](qstring.html#operator-eq-eq)（ ）[operator&gt;=](qstring.html#operator-gt-eq)（） ，等等。请注意，比较的字符的数值Unicode值完全基于。这是非常快的，但不是什么人的期望;的[QString.localeAwareCompare](qstring.html#localeAwareCompare)（ ）函数是排序用户界面字符串一个更好的选择。

为了获得一个指向实际的字符数据，调用[data](qstring.html#data)（）或[constData](qstring.html#constData)（ ） 。这些函数返回一个指针的开始[QChar](qchar.html)数据。指针是保证仍然有效，直到一个非const函数被调用的QString的。

### Converting Between 8-Bit Strings and Unicode Strings

的QString提供以下四种函数返回一个`const char *`版本字符串为[QByteArray](qbytearray.html)：[toAscii](qstring.html#toAscii)（ ）[toLatin1](qstring.html#toLatin1)（ ）[toUtf8](qstring.html#toUtf8)（）和[toLocal8Bit](qstring.html#toLocal8Bit)（ ） 。

*   [toAscii](qstring.html#toAscii)() returns an 8-bit string encoded using the codec specified by QTextCodec.codecForCStrings (by default, that is Latin 1).
*   [toLatin1](qstring.html#toLatin1)() returns a Latin-1 (ISO 8859-1) encoded 8-bit string.
*   [toUtf8](qstring.html#toUtf8)() returns a UTF-8 encoded 8-bit string. UTF-8 is a superset of US-ASCII (ANSI X3.4-1986) that supports the entire Unicode character set through multibyte sequences.
*   [toLocal8Bit](qstring.html#toLocal8Bit)() returns an 8-bit string using the system's local encoding.

从这些编码的一个转换，提供的QString[fromAscii](qstring.html#fromAscii)（ ）[fromLatin1](qstring.html#fromLatin1)（ ）[fromUtf8](qstring.html#fromUtf8)（）和[fromLocal8Bit](qstring.html#fromLocal8Bit)（ ） 。其它的编码，通过支持[QTextCodec](qtextcodec.html)类。

如上所述， QString的提供了大量的函数和运算符可以很容易地与互操作`const char *`字符串。但是这个功能是一个双刃剑：它让QString的使用更为方便，如果所有的字符串都是US-ASCII或Latin- 1 ，但总是有风险的或隐式转换`const char *`完成使用错误的8位编码。为了尽量减少这些风险，您可以关闭这些隐式转换通过定义以下两个预处理器符号：

*   `QT_NO_CAST_FROM_ASCII` disables automatic conversions from C string literals and pointers to Unicode.
*   `QT_NO_CAST_TO_ASCII` disables automatic conversion from QString to C strings.

在全球范围内定义这些预处理器符号为您的应用程序的一种方法是将以下条目​​添加到您的[qmake project file](index.htm)：

```
 DEFINES += QT_NO_CAST_FROM_ASCII \
            QT_NO_CAST_TO_ASCII

```

然后，您需要显式调用[fromAscii](qstring.html#fromAscii)（ ）[fromLatin1](qstring.html#fromLatin1)（ ）[fromUtf8](qstring.html#fromUtf8)（） ，或[fromLocal8Bit](qstring.html#fromLocal8Bit)（）来构造从一个8位字符串的QString ，或者使用轻量[QLatin1String](qlatin1string.html)类，例如：

```
 QString url = QLatin1String("http://www.unicode.org/");

```

同样的，你必须调用[toAscii](qstring.html#toAscii)（ ）[toLatin1](qstring.html#toLatin1)（ ）[toUtf8](qstring.html#toUtf8)（） ，或[toLocal8Bit](qstring.html#toLocal8Bit)（）明确地向的QString转换为一个8位的字符串。 （其它的编码是通过支持[QTextCodec](qtextcodec.html)类。 ）

| Note for C Programmers |
| --- |
| Due to C++'s type system and the fact that QString is [implicitly shared](index.htm#implicitly-shared), QStrings may be treated like `int`s or other basic types. For example:

```
 QString Widget.boolToString(bool b)
 {
     QString result;
     if (b)
         result = "True";
     else
         result = "False";
     return result;
 }

```

该`result`变量是在堆栈上分配一个普通变量。何时`return`被调用，因为我们通过返回值，拷贝构造函数被调用和字符串的一个副本被返回。没有实际的复制发生感谢隐含共享。 |

### Distinction Between Null and Empty Strings

由于历史原因， QString的一个空字符串和空字符串之间的区别。一_null_字符串是使用的QString的默认构造函数初始化或通过传递（为const char * ）0给构造函数的字符串。一个_empty_字符串是用大小为0的字符串。空字符串总是空的，但一个空字符串不一定空：

```
 QString().isNull();               // returns true
 QString().isEmpty();              // returns true

 QString("").isNull();             // returns false
 QString("").isEmpty();            // returns true

 QString("abc").isNull();          // returns false
 QString("abc").isEmpty();         // returns false

```

之外的全部功能[isNull](qstring.html#isNull)（ ）把空字符串相同的为空字符串。例如，[toAscii](qstring.html#toAscii)（ ） 。[constData](qstring.html#constData)（ ）返回一个指向一个'\ 0 '字符为空字符串（_not_一个空指针） ，和[QString](qstring.html#QString)（ ）比较相等的QString （ “”） 。我们建议您始终使用[isEmpty](qstring.html#isEmpty)（ ）函数，并避免[isNull](qstring.html#isNull)（ ） 。

### Argument Formats

在成员函数，其中一个参数_format_可以指定（例如，[arg](qstring.html#arg)（ ）[number](qstring.html#number)（ ） ） ，参数_format_可以是下列之一：

| Format | Meaning |
| --- | --- |
| `e` | format as [-]9.9e[+&#124;-]999 |
| `E` | format as [-]9.9E[+&#124;-]999 |
| `f` | format as [-]9.9 |
| `g` | use `e` or `f` format, whichever is the most concise |
| `G` | use `E` or `f` format, whichever is the most concise |

A _precision_也与参数指定_format_。为' E' ， ' E'和'F'格式中，_precision_表示的数字的数量_after_小数点。对于“G”和“G”格式中，_precision_较显着位数（尾随零被省略）的最大数量。

### More Efficient String Construction

使用的QString`'+'`算子，它很容易从多个子构建复杂的字符串。你经常会写这样的代码：

```
     QString foo;
     QString type = "long";

     foo->setText(QLatin1String("vector<") + type + QLatin1String(">.iterator"));

     if (foo.startsWith("(" + type + ") 0x"))
         ...

```

有什么不对与任何这些字符串构造的，但也有一些隐藏的低效率。与Qt 4.6开始，你可以消灭他们。

第一，多种用途`'+'`运营商通常是指多个内存分配。当串联_n_子，其中_n &gt; 2_，可以有多达_n - 1_调用内存分配器。

第二，[QLatin1String](qlatin1string.html)不，但在内部调用存储其长度[qstrlen](index.htm#qstrlen)（）时，它需要知道它的长度。

4.6 ，内部的模板类`QStringBuilder`一直伴随着几个辅助函数添加。这个类被标记为内部并没有出现在文档中，因为你的目的不是实例化它在你的代码。它的使用将是自动的，如下面所述。该类中发现`src/corelib/tools/qstringbuilder.cpp`如果你想看看它。

`QStringBuilder`使用表达式模板和重新实现了`'%'`运营商这样当你使用`'%'`对于字符串连接，而不是`'+'`，多个子串连将被推迟到最后的结果就是即将被分配到的QString 。在这一点上，存储器所需的最终结果的量是已知的。该内存分配器，然后调用_once_获得所需要的空间，而子被复制到了一个接一个。

`QLatin1Literal`是第二类内部，可替换[QLatin1String](qlatin1string.html)，它可以出于兼容性原因不能改变。`QLatin1Literal`存储其长度，从而节省了时间，当`QStringBuilder`计算所需的内存为最后的字符串的数量。

额外的效率是通过内联和减少引用计数（从创建取得的QString`QStringBuilder`通常具有1的引用计数，而[QString.append](qstring.html#append)（ ）需要一个额外的测试） 。

有三种方法可以访问字符串构造这个改进的方法。直接的方法是包括`QStringBuilder`无论你想使用它，并使用`'%'`操盘手的`'+'`连接字符串时：

```
     #include <QStringBuilder>

     QString hello("hello");
     [QStringRef](qstringref.html) el(&hello, 2, 3);
     QLatin1String world("world");
     QString message =  hello % el % world % [QChar](qchar.html)('!');

```

更具全球性的做法，是最方便的，但不完全兼容的源代码，是这样定义你的pro文件：

```
     DEFINES *= QT_USE_QSTRINGBUILDER

```

和`'+'`会自动为所执行的`QStringBuilder` `'%'`无处不在。

* * *

## Type Documentation

```
QString.NormalizationForm
```

这个枚举描述Unicode文本的各种标准化的形式。

| Constant | Value | Description |
| --- | --- | --- |
| `QString.NormalizationForm_D` | `0` | 标准分解 |
| `QString.NormalizationForm_C` | `1` | 标准分解其次是标准合成 |
| `QString.NormalizationForm_KD` | `2` | 兼容性分解 |
| `QString.NormalizationForm_KC` | `3` | 兼容性分解其次是标准合成 |

**See also** [normalized](qstring.html#normalized)（）和[Unicode Standard Annex #15](http://www.unicode.org/reports/tr15/)。

```
QString.SectionFlag
```

该枚举指定标志，可用于影响的各个方面[section](qstring.html#section)（ ）就分隔符和空字段功能的行为。

| Constant | Value | Description |
| --- | --- | --- |
| `QString.SectionDefault` | `0x00` | 空字段进行计数，前缘和后隔板不包括在内，且所述分离器灵敏相比的情况。 |
| `QString.SectionSkipEmpty` | `0x01` | 把空字段，如果他们不存在，即它们不是尽可能考虑_start_和_end_关注。 |
| `QString.SectionIncludeLeadingSep` | `0x02` | 包括领先的分隔符（如果有的话）结果字符串。 |
| `QString.SectionIncludeTrailingSep` | `0x04` | 在结果字符串中包含尾随分隔符（如果有的话） 。 |
| `QString.SectionCaseInsensitiveSeps` | `0x08` | 不区分大小写比较的分隔符。 |

该SectionFlags类型是一个typedef为[QFlags](index.htm)\u003cSectionFlag\u003e 。它存储SectionFlag值的或组合。

**See also** [section](qstring.html#section)（ ） 。

```
QString.SplitBehavior
```

此枚举指定如何[split](qstring.html#split)（ ）函数的行为应该就空字符串。

| Constant | Value | Description |
| --- | --- | --- |
| `QString.KeepEmptyParts` | `0` | 如果某个字段是空的，保持它的结果。 |
| `QString.SkipEmptyParts` | `1` | 如果某个字段为空，不包括它的结果。 |

**See also** [split](qstring.html#split)（ ） 。

* * *

## Method Documentation

```
QString.__init__ (self)
```

构造一个空字符串。空字符串也是空的。

**See also** [isEmpty](qstring.html#isEmpty)（ ） 。

```
QString.__init__ (self, QKeySequence)
```

如果QtGui模块导入此方法仅适用。

构造一个空字符串。空字符串也是空的。

**See also** [isEmpty](qstring.html#isEmpty)（ ） 。

```
QString.__init__ (self, QScriptString)
```

如果QtScript模块导入此方法仅适用。

构造一个空字符串。空字符串也是空的。

**See also** [isEmpty](qstring.html#isEmpty)（ ） 。

```
QString.__init__ (self, int size, QChar c)
```

构造与第一次初始化字符串_size_的字符[QChar](qchar.html)排列_unicode_。

[QString](qstring.html)使得字符串数据的深层副本。 unicode的数据被原样复制，如果存在字节顺序标记被保留。

```
QString.__init__ (self, QString s)
```

构造具有的字符初始化的字符串[QChar](qchar.html)排列_unicode_，这必须终止与0 。

[QString](qstring.html)使得字符串数据的深层副本。 unicode的数据被原样复制，如果存在字节顺序标记被保留。

此功能被引入Qt的4.7 。

```
QString.__init__ (self, QByteArray a)
```

构造大小为1包含字符的字符串_ch_。

```
QString.__init__ (self, QUuid)
```

构造的给定的字符串_size_与每一个字符集_ch_。

**See also** [fill](qstring.html#fill)（ ） 。

```
QString QString.append (self, QString s)
```

附加字符串_str_到这个字符串的结尾。

例如：

```
 [QString](qstring.html) x = "free";
 [QString](qstring.html) y = "dom";

 x.append(y);
 // x == "freedom"

```

这是与使用的[insert](qstring.html#insert)（ ）函数：

```
 x.insert(x.size(), y);

```

追加（）函数通常是非常快的（[constant time](index.htm#constant-time)） ，因为[QString](qstring.html)预分配额外的空间，在字符串数据的末尾，从而无需每次都重新配置整个字符串成长。

**See also** [operator+=](qstring.html#operator-2b-eq)（ ）[prepend](qstring.html#prepend)（）和[insert](qstring.html#insert)（ ） 。

```
QString QString.append (self, QLatin1String s)
```

添加给定的字符串_reference_这个字符串，并返回结果。

此功能被引入Qt的4.4 。

```
QString QString.append (self, QByteArray s)
```

这个函数的重载[append](qstring.html#append)（ ） 。

追加Latin-1的字符串_str_这个字符串。

```
QString QString.arg (self, int a, int fieldWidth = 0, int base = 10, QChar fillChar = QLatin1Char(' '))
```

返回此字符串的一个副本，编号最小的位置标记通过字符串替换_a_即`%1`，`%2`，...，`%99`。

_fieldWidth_指定间距的最小量这样的说法_a_不得佔用。如果_a_比需要较少的空间_fieldWidth_，它被填充到_fieldWidth_与性格_fillChar_。正_fieldWidth_产生右对齐文本。负_fieldWidth_产生左对齐的文本。

这个例子显示了我们如何创建一个`status`串报告进展情况，同时处理文件的列表：

```
 [QString](qstring.html) i;           // current file's number
 [QString](qstring.html) total;       // number of files to process
 [QString](qstring.html) fileName;    // current file's name

 [QString](qstring.html) status = [QString](qstring.html)("Processing file %1 of %2: %3")
                 .arg(i).arg(total).arg(fileName);

```

First, `arg(i)`替换`%1`。然后`arg(total)`替换`%2`。最后，`arg(fileName)`替换`%3`。

一个优点使用arg的（ ）以上[sprintf](qstring.html#sprintf)（ ）是的编号的位置标记的顺序可以改变，如果应用程序的字符串翻译成其他语言，但每个ARG （ ）仍然将取代编号最小的未更换位置标记，不管它在哪里出现。此外，如果位置标记`%i`多次出现在字符串中时， ARG （ ）取代他们。

如果没有未更换位置标记剩馀，一个输出警告信息，其结果是不确定的。位置标记号码必须是范围为1至99 。

```
QString QString.arg (self, float a, int fieldWidth = 0, str format = 'g', int precision = -1, QChar fillChar = QLatin1Char(' '))
```

这个函数的重载[arg](qstring.html#arg)（ ） 。

这是相同的`str.arg(a1).arg(a2)`，除了字符串_a1_和_a2_替换在一次通过。这可以使如果有差别_a1_例如包含`%1`：

```
 [QString](qstring.html) str;
 str = "%1 %2";

 str.arg("%1f", "Hello");        // returns "%1f Hello"
 str.arg("%1f").arg("Hello");    // returns "Hellof %2"

```

```
QString QString.arg (self, int a, int fieldWidth = 0, int base = 10, QChar fillChar = QLatin1Char(' '))
```

这个函数的重载[arg](qstring.html#arg)（ ） 。

这是一样的调用`str.arg(a1).arg(a2).arg(a3)`，除了字符串_a1_，_a2_和_a3_替换在一次通过。

```
QString QString.arg (self, int a, int fieldWidth = 0, int base = 10, QChar fillChar = QLatin1Char(' '))
```

这个函数的重载[arg](qstring.html#arg)（ ） 。

这是一样的调用`str.arg(a1).arg(a2).arg(a3).arg(a4)`，除了字符串_a1_，_a2_，_a3_和_a4_替换在一次通过。

```
QString QString.arg (self, QString a, int fieldWidth = 0, QChar fillChar = QLatin1Char(' '))
```

这个函数的重载[arg](qstring.html#arg)（ ） 。

这是一样的调用`str.arg(a1).arg(a2).arg(a3).arg(a4).arg(a5)`，除了字符串_a1_，_a2_，_a3_，_a4_和_a5_替换在一次通过。

```
QString QString.arg (self, QString a1, QString a2)
```

这个函数的重载[arg](qstring.html#arg)（ ） 。

这是一样的调用`str.arg(a1).arg(a2).arg(a3).arg(a4).arg(a5).arg(a6))`，除了字符串_a1_，_a2_，_a3_，_a4_，_a5_和_a6_替换在一次通过。

```
QString QString.arg (self, QString a1, QString a2, QString a3)
```

这个函数的重载[arg](qstring.html#arg)（ ） 。

这是一样的调用`str.arg(a1).arg(a2).arg(a3).arg(a4).arg(a5).arg(a6).arg(a7)`，除了字符串_a1_，_a2_，_a3_，_a4_，_a5_，_a6_和_a7_替换在一次通过。

```
QString QString.arg (self, QString a1, QString a2, QString a3, QString a4)
```

这个函数的重载[arg](qstring.html#arg)（ ） 。

这是一样的调用`str.arg(a1).arg(a2).arg(a3).arg(a4).arg(a5).arg(a6).arg(a7).arg(a8)`，除了字符串_a1_，_a2_，_a3_，_a4_，_a5_，_a6_，_a7_和_a8_替换在一次通过。

```
QString QString.arg (self, QString a1, QString a2, QString a3, QString a4, QString a5)
```

这个函数的重载[arg](qstring.html#arg)（ ） 。

这是一样的调用`str.arg(a1).arg(a2).arg(a3).arg(a4).arg(a5).arg(a6).arg(a7).arg(a8).arg(a9)`，除了字符串_a1_，_a2_，_a3_，_a4_，_a5_，_a6_，_a7_，_a8_和_a9_替换在一次通过。

```
QString QString.arg (self, QString a1, QString a2, QString a3, QString a4, QString a5, QString a6)
```

这个函数的重载[arg](qstring.html#arg)（ ） 。

该_a_参数表现在基础_base_，它默认为10 ，并且必须在2到36之间。对于基础不是10 ，_a_被视为一个无符号整数。

_fieldWidth_指定空间的最低金额_a_被填充到与填充有字符_fillChar_。正值产生右对齐文本，负值产生左对齐的文本。

的'％'可以跟随一个“L” ，在这种情况下，序列被替换的局部表示_a_。该转换使用默认的语言环境，通过设置[QLocale.setDefault](qlocale.html#setDefault)（ ） 。如果没有指定默认的语言环境中，“ C”语言环境使用。在“L”标志将被忽略，如果_base_是不是10 。

```
 [QString](qstring.html) str;
 str = [QString](qstring.html)("Decimal 63 is %1 in hexadecimal")
         .arg(63, 0, 16);
 // str == "Decimal 63 is 3f in hexadecimal"

 [QLocale](qlocale.html).setDefault([QLocale](qlocale.html)([QLocale](qlocale.html).English, [QLocale](qlocale.html).UnitedStates));
 str = [QString](qstring.html)("%1 %L2 %L3")
         .arg(12345)
         .arg(12345)
         .arg(12345, 0, 16);
 // str == "12345 12,345 3039"

```

If _fillChar_是'0' （数字0， ASCII码48 ） ，语言环境的零被使用。对于负数，零填充可能会在减号前出现。

```
QString QString.arg (self, QString a1, QString a2, QString a3, QString a4, QString a5, QString a6, QString a7)
```

这个函数的重载[arg](qstring.html#arg)（ ） 。

该_base_参数指定的基数换算整数时使用_a_成一个字符串。所述碱必须具有2和36之间。

If _fillChar_是'0' （数字0， ASCII码48 ） ，语言环境的零被使用。对于负数，零填充可能会在减号前出现。

```
QString QString.arg (self, QString a1, QString a2, QString a3, QString a4, QString a5, QString a6, QString a7, QString a8)
```

这个函数的重载[arg](qstring.html#arg)（ ） 。

_fieldWidth_指定空间的最低金额_a_被填充到与填充有字符_fillChar_。正值产生右对齐文本，负值产生左对齐的文本。

该_a_参数表示在给定的_base_，它默认为10 ，并且必须在2到36之间。

的'％'可以跟随一个“L” ，在这种情况下，序列被替换的局部表示_a_。转换使用默认的语言环境。默认的区域是从应用程序启动时系统的区域设置决定。它可以通过改变[QLocale.setDefault](qlocale.html#setDefault)（ ） 。在“L”标志将被忽略，如果_base_是不是10 。

```
 [QString](qstring.html) str;
 str = [QString](qstring.html)("Decimal 63 is %1 in hexadecimal")
         .arg(63, 0, 16);
 // str == "Decimal 63 is 3f in hexadecimal"

 [QLocale](qlocale.html).setDefault([QLocale](qlocale.html)([QLocale](qlocale.html).English, [QLocale](qlocale.html).UnitedStates));
 str = [QString](qstring.html)("%1 %L2 %L3")
         .arg(12345)
         .arg(12345)
         .arg(12345, 0, 16);
 // str == "12345 12,345 3039"

```

If _fillChar_是'0' （数字0， ASCII码48 ） ，语言环境的零被使用。对于负数，零填充可能会在减号前出现。

```
QString QString.arg (self, QString a1, QString a2, QString a3, QString a4, QString a5, QString a6, QString a7, QString a8, QString a9)
```

这个函数的重载[arg](qstring.html#arg)（ ） 。

_fieldWidth_指定空间的最低金额_a_被填充到与填充有字符_fillChar_。正值产生右对齐文本，负值产生左对齐的文本。

该_base_参数指定的基数换算整数时使用_a_为一个字符串。该基地必须是2和36之间，给予8进制， 10进制和16进制数。

If _fillChar_是'0' （数字0， ASCII码48 ） ，语言环境的零被使用。对于负数，零填充可能会在减号前出现。

```
QChar QString.at (self, int i)
```

返回字符的给定索引处_position_在字符串中。

该_position_必须是在字符串中的有效索引位置（即0 \u003c =_position_\u003c[size](qstring.html#size)（））。

**See also** [operator[]](qstring.html#operator-5b-5d)（ ） 。

```
int QString.capacity (self)
```

返回可以存储在字符串中不强制重新分配的字符的最大数目。

此函数的唯一目的是提供微调的手段[QString](qstring.html)的内存使用情况。一般情况下，你很少会需要调用这个函数。如果你想知道有多少字符是字符串，调用[size](qstring.html#size)（ ） 。

**See also** [reserve](qstring.html#reserve)（）和[squeeze](qstring.html#squeeze)（ ） 。

```
QString.chop (self, int n)
```

移除_n_字符从字符串的结尾。

If _n_大于[size](qstring.html#size)（ ） ，结果是空字符串。

例如：

```
 [QString](qstring.html) str("LOGOUT\r\n");
 str.chop(2);
 // str == "LOGOUT"

```

如果你想从删除的字符_beginning_的字符串，使用[remove](qstring.html#remove)（ ）来代替。

**See also** [truncate](qstring.html#truncate)（ ）[resize](qstring.html#resize)（）和[remove](qstring.html#remove)（ ） 。

```
QString.clear (self)
```

清除字符串的内容，并使其为空。

**See also** [resize](qstring.html#resize)() and [isEmpty](qstring.html#isEmpty)().

```
int QString.compare (self, QString s)
```

比较_s1_同_s2_并返回一个整数大于零小于，等于，或大于，如果_s1_小于，等于或大于_s2_。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)，比较是区分大小写的，否则比较不区分大小写。

区分大小写的比较是完全基于字符的数值Unicode值和速度非常快，但不是什么人期望的那样。考虑与分拣用户可见的字符串[localeAwareCompare](qstring.html#localeAwareCompare)（ ） 。

```
 int x = [QString](qstring.html).compare("aUtO", "AuTo", [Qt](qt.html).CaseInsensitive);  // x == 0
 int y = [QString](qstring.html).compare("auto", "Car", [Qt](qt.html).CaseSensitive);     // y > 0
 int z = [QString](qstring.html).compare("auto", "Car", [Qt](qt.html).CaseInsensitive);   // z < 0

```

这个函数中引入了Qt 4.2中。

**See also** [operator==](qstring.html#operator-eq-eq)（ ）[operator&lt;](qstring.html#operator-lt)（）和[operator&gt;](qstring.html#operator-gt)（ ） 。

```
int QString.compare (self, QString s, Qt.CaseSensitivity cs)
```

这个函数的重载[compare](qstring.html#compare)（ ） 。

执行敏感的比较情况_s1_和_s2_。

```
int QString.compare (self, QLatin1String other, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这个函数的重载[compare](qstring.html#compare)（ ） 。

执行的比较_s1_和_s2_使用区分大小写设置_cs_。

这个函数中引入了Qt 4.2中。

```
int QString.compare (self, QStringRef ref, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这个函数的重载[compare](qstring.html#compare)（ ） 。

执行的比较_s1_和_s2_使用区分大小写设置_cs_。

这个函数中引入了Qt 4.2中。

```
int QString.compare (QString s1, QString s2)
```

这个函数的重载[compare](qstring.html#compare)（ ） 。

词汇与比较此字符串_other_字符串并返回比，等于大于零的整数更少，或更大，如果该字符串是比其他字符串小于，等于，或更大。

相当于`compare(*this, other)`。

```
int QString.compare (QString s1, QString s2, Qt.CaseSensitivity cs)
```

这个函数的重载[compare](qstring.html#compare)（ ） 。

同样作为比较（ *此，_other_，_cs_） 。

这个函数中引入了Qt 4.2中。

```
int QString.compare (QString s1, QLatin1String s2, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这个函数的重载[compare](qstring.html#compare)（ ） 。

同样作为比较（ *此，_other_，_cs_） 。

这个函数中引入了Qt 4.2中。

```
int QString.compare (QLatin1String s1, QString s2, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这个函数的重载[compare](qstring.html#compare)（ ） 。

比较字符串引用，_ref_与字符串并返回比，等于大于零的整数更少，或更大，如果该字符串是小于，等于或大于_ref_。

```
int QString.compare (QString s1, QStringRef s2, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这个函数的重载[compare](qstring.html#compare)（ ） 。

```
bool QString.contains (self, QString str, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

如果此字符串包含字符串的出现，则返回True_str_否则返回False 。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

例如：

```
 [QString](qstring.html) str = "Peter Pan";
 str.contains("peter", [Qt](qt.html).CaseInsensitive);    // returns true

```

**See also** [indexOf](qstring.html#indexOf)（）和[count](qstring.html#count)（ ） 。

```
bool QString.contains (self, QStringRef s, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

如果这个字符串包含的字符串引用的出现，则返回True_str_否则返回False 。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

此功能被引入Qt的4.8 。

**See also** [indexOf](qstring.html#indexOf)（）和[count](qstring.html#count)（ ） 。

```
bool QString.contains (self, QRegExp rx)
```

```
int QString.count (self)
```

返回（可能重叠）字符串的出现次数_str_在此字符串。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

**See also** [contains](qstring.html#contains)（）和[indexOf](qstring.html#indexOf)（ ） 。

```
int QString.count (self, QString str, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这个函数的重载[count](qstring.html#count)（ ） 。

返回事件字符的数目_ch_在字符串中。

```
int QString.count (self, QStringRef str, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这个函数的重载[count](qstring.html#count)（ ） 。

返回（可能重叠）出现的字符串引用数_str_在此字符串。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

此功能被引入Qt的4.8 。

**See also** [contains](qstring.html#contains)（）和[indexOf](qstring.html#indexOf)（ ） 。

```
int QString.count (self, QRegExp)
```

这个函数的重载[count](qstring.html#count)（ ） 。

返回的次数的正则表达式_rx_匹配字符串中。

此函数计算重叠的匹配，所以在下面的例子中，有“模拟”或“ AMA”的四个实例：

```
 [QString](qstring.html) str = "banana and panama";
 str.count([QRegExp](qregexp.html)("a[nm]a"));    // returns 4

```

```
bool QString.endsWith (self, QString s, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

如果字符串结尾，则返回True_s_否则返回False 。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

```
 [QString](qstring.html) str = "Bananas";
 str.endsWith("anas");         // returns true
 str.endsWith("pple");         // returns false

```

**See also** [startsWith](qstring.html#startsWith)（ ） 。

```
bool QString.endsWith (self, QStringRef s, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

```
bool QString.endsWith (self, QLatin1String s, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这个函数的重载[endsWith](qstring.html#endsWith)（ ） 。

如果字符串的字符串引用结束，则返回True_s_否则返回False 。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

此功能被引入Qt的4.8 。

**See also** [startsWith](qstring.html#startsWith)（ ） 。

```
QString QString.fill (self, QChar ch, int size = -1)
```

设置每个字符的字符串中的字符_ch_。如果_size_是从-1 （默认值）不同，该字符串被调整为_size_事前。

例如：

```
 [QString](qstring.html) str = "Berlin";
 str.fill('z');
 // str == "zzzzzz"

 str.fill('A', 2);
 // str == "AA"

```

**See also** [resize](qstring.html#resize)（ ） 。

```
QString QString.fromAscii (str str, int size = -1)
```

返回[QString](qstring.html)与第一次初始化_size_从字符串中的字符_str_。

If _size_为-1 （默认值） ，它被视为于qstrlen （_str_） 。

需要注意的是，尽管这个名字，这个功能实际上是通过使用定义的编码解码器[QTextCodec.setCodecForCStrings](qtextcodec.html#setCodecForCStrings)（ ）来转换_str_为Unicode。取决于编解码器，它可能不接受有效的US-ASCII （ANSI X3.4 - 1986）的输入。如果没有编解码器已经设置，这个函数一样[fromLatin1](qstring.html#fromLatin1)（ ） 。

**See also** [toAscii](qstring.html#toAscii)（ ）[fromLatin1](qstring.html#fromLatin1)（ ）[fromUtf8](qstring.html#fromUtf8)（）和[fromLocal8Bit](qstring.html#fromLocal8Bit)（ ） 。

```
QString QString.fromLatin1 (str str, int size = -1)
```

返回[QString](qstring.html)与第一次初始化_size_拉丁- 1字符串的字符_str_。

If _size_为-1 （默认值） ，它被视为于qstrlen （_str_） 。

**See also** [toLatin1](qstring.html#toLatin1)（ ）[fromAscii](qstring.html#fromAscii)（ ）[fromUtf8](qstring.html#fromUtf8)（）和[fromLocal8Bit](qstring.html#fromLocal8Bit)（ ） 。

```
QString QString.fromLocal8Bit (str str, int size = -1)
```

返回[QString](qstring.html)与第一次初始化_size_8位字符串的字符_str_。

If _size_为-1 （默认值） ，它被视为于qstrlen （_str_） 。

[QTextCodec.codecForLocale](qtextcodec.html#codecForLocale)（ ）是用来执行转换。

**See also** [toLocal8Bit](qstring.html#toLocal8Bit)（ ）[fromAscii](qstring.html#fromAscii)（ ）[fromLatin1](qstring.html#fromLatin1)（）和[fromUtf8](qstring.html#fromUtf8)（ ） 。

```
QString QString.fromUtf8 (str str, int size = -1)
```

返回[QString](qstring.html)与第一次初始化_size_在UTF-8字符串的字节_str_。

If _size_为-1 （默认值） ，它被视为于qstrlen （_str_） 。

UTF - 8是Unicode编码，可以表示所有字符的Unicode字符串像[QString](qstring.html)。然而，无效的序列是可以使用UTF -8和，如果有这样的发现，他们将被替换为一个或多个“替换字符” ，或抑制。这些包括非Unicode序列，非字符，过长的序列或编码成UTF-8代码点。

非字符码点是Unicode标准的储备，不能在文本交换使用。他们在每一个Unicode平面（ U + FFFE ， U + FFFF ， U +1 FFFE ， U +1 FFFF ， U +2 FFFE等） ，以及16码点在范围U + FDD0 .. U +最后两个代码点FDDF ，包容性。

**See also** [toUtf8](qstring.html#toUtf8)（ ）[fromAscii](qstring.html#fromAscii)（ ）[fromLatin1](qstring.html#fromLatin1)（）和[fromLocal8Bit](qstring.html#fromLocal8Bit)（ ） 。

```
int QString.indexOf (self, QString str, int from = 0, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

返回字符串中第一次出现的索引位置_str_在这个字符串，搜索着从索引位置_from_。返回-1，如果_str_是没有找到。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

例如：

```
 [QString](qstring.html) x = "sticky question";
 [QString](qstring.html) y = "sti";
 x.indexOf(y);               // returns 0
 x.indexOf(y, 1);            // returns 10
 x.indexOf(y, 10);           // returns 10
 x.indexOf(y, 11);           // returns -1

```

If _from_为-1，搜索从最后一个字符，如果是-2 ，在倒数第二个字符等等。

**See also** [lastIndexOf](qstring.html#lastIndexOf)（ ）[contains](qstring.html#contains)（）和[count](qstring.html#count)（ ） 。

```
int QString.indexOf (self, QStringRef str, int from = 0, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

返回字符串中第一次出现的索引位置_str_在这个字符串，搜索着从索引位置_from_。返回-1，如果_str_是没有找到。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

例如：

```
 [QString](qstring.html) x = "sticky question";
 [QString](qstring.html) y = "sti";
 x.indexOf(y);               // returns 0
 x.indexOf(y, 1);            // returns 10
 x.indexOf(y, 10);           // returns 10
 x.indexOf(y, 11);           // returns -1

```

If _from_为-1，搜索从最后一个字符，如果是-2 ，在倒数第二个字符等等。

此功能被引入Qt的4.5 。

**See also** [lastIndexOf](qstring.html#lastIndexOf)（ ）[contains](qstring.html#contains)（）和[count](qstring.html#count)（ ） 。

```
int QString.indexOf (self, QLatin1String str, int from = 0, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这个函数的重载[indexOf](qstring.html#indexOf)（ ） 。

返回字符的第一个匹配项的索引位置_ch_在字符串中，寻找着从索引位置_from_。返回-1，如果_ch_找不到。

```
int QString.indexOf (self, QRegExp rx, int from = 0)
```

这个函数的重载[indexOf](qstring.html#indexOf)（ ） 。

返回的字符串引用中第一次出现的索引位置_str_在这个字符串，搜索着从索引位置_from_。返回-1，如果_str_是没有找到。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

此功能被引入Qt的4.8 。

```
QString QString.insert (self, int i, QString s)
```

插入字符串_str_给定索引处_position_并返回一个引用这个字符串。

例如：

```
 [QString](qstring.html) str = "Meal";
 str.insert(1, [QString](qstring.html)("ontr"));
 // str == "Montreal"

```

如果给定的_position_大于[size](qstring.html#size)（） ，该阵列是第一，采用扩展[resize](qstring.html#resize)（ ） 。

**See also** [append](qstring.html#append)（ ）[prepend](qstring.html#prepend)（ ）[replace](qstring.html#replace)（）和[remove](qstring.html#remove)（ ） 。

```
QString QString.insert (self, int i, QLatin1String s)
```

这个函数的重载[insert](qstring.html#insert)（ ） 。

插入Latin-1的字符串_str_给定索引处_position_。

```
bool QString.isEmpty (self)
```

返回True如果该字符串没有字符，否则返回False 。

例如：

```
 [QString](qstring.html)().isEmpty();            // returns true
 [QString](qstring.html)("").isEmpty();          // returns true
 [QString](qstring.html)("x").isEmpty();         // returns false
 [QString](qstring.html)("abc").isEmpty();       // returns false

```

**See also** [size](qstring.html#size)（ ） 。

```
bool QString.isNull (self)
```

返回True如果该字符串为null ，否则返回False 。

例如：

```
 [QString](qstring.html)().isNull();             // returns true
 [QString](qstring.html)("").isNull();           // returns false
 [QString](qstring.html)("abc").isNull();        // returns false

```

Qt后，由于历史原因，空字符串和空字符串之间的区别。对于大多数应用来说，重要的是一个字符串是否包含任何数据，这可以通过将所确定的[isEmpty](qstring.html#isEmpty)（）函数。

**See also** [isEmpty](qstring.html#isEmpty)（ ） 。

```
bool QString.isRightToLeft (self)
```

返回True如果该字符串读取从右到左。

```
bool QString.isSimpleText (self)
```

```
int QString.lastIndexOf (self, QString str, int from = -1, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

返回字符串中最后一次出现的索引位置_str_在这个字符串，从索引位置向后搜索_from_。如果_from_为-1 （默认），搜索从最后一个字符，如果_from_为-2 ，在旁边的最后一个字符等等。返回-1，如果_str_是没有找到。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

例如：

```
 [QString](qstring.html) x = "crazy azimuths";
 [QString](qstring.html) y = "az";
 x.lastIndexOf(y);           // returns 6
 x.lastIndexOf(y, 6);        // returns 6
 x.lastIndexOf(y, 5);        // returns 2
 x.lastIndexOf(y, 1);        // returns -1

```

**See also** [indexOf](qstring.html#indexOf)（ ）[contains](qstring.html#contains)（）和[count](qstring.html#count)（ ） 。

```
int QString.lastIndexOf (self, QStringRef str, int from = -1, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这个函数的重载[lastIndexOf](qstring.html#lastIndexOf)（ ） 。

返回字符串中最后一次出现的索引位置_str_在这个字符串，从索引位置向后搜索_from_。如果_from_为-1 （默认），搜索从最后一个字符，如果_from_为-2 ，在倒数第二个字符等等。返回-1，如果_str_是没有找到。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

例如：

```
 [QString](qstring.html) x = "crazy azimuths";
 [QString](qstring.html) y = "az";
 x.lastIndexOf(y);           // returns 6
 x.lastIndexOf(y, 6);        // returns 6
 x.lastIndexOf(y, 5);        // returns 2
 x.lastIndexOf(y, 1);        // returns -1

```

此功能被引入Qt的4.5 。

**See also** [indexOf](qstring.html#indexOf)（ ）[contains](qstring.html#contains)（）和[count](qstring.html#count)（ ） 。

```
int QString.lastIndexOf (self, QLatin1String str, int from = -1, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这个函数的重载[lastIndexOf](qstring.html#lastIndexOf)（ ） 。

返回字符的最后一个匹配项的索引位置_ch_从位置向后搜索_from_。

```
int QString.lastIndexOf (self, QRegExp rx, int from = -1)
```

这个函数的重载[lastIndexOf](qstring.html#lastIndexOf)（ ） 。

返回的字符串引用的最后一个匹配项的索引位置_str_在这个字符串，从索引位置向后搜索_from_。如果_from_为-1 （默认），搜索从最后一个字符，如果_from_为-2 ，在倒数第二个字符等等。返回-1，如果_str_是没有找到。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

此功能被引入Qt的4.8 。

**See also** [indexOf](qstring.html#indexOf)（ ）[contains](qstring.html#contains)（）和[count](qstring.html#count)（ ） 。

```
QString QString.left (self, int len)
```

返回包含一个子串的_n_字符串最左边的字符。

如果整个字符串被返回_n_大于[size](qstring.html#size)（）或小于零。

```
 [QString](qstring.html) x = "Pineapple";
 [QString](qstring.html) y = x.left(4);      // y == "Pine"

```

**See also** [right](qstring.html#right)（ ）[mid](qstring.html#mid)（）和[startsWith](qstring.html#startsWith)（ ） 。

```
QString QString.leftJustified (self, int width, QChar fillChar = QLatin1Char(' '), bool truncate = False)
```

返回大小的字符串_width_包含该字符串被填充_fill_字符。

If _truncate_是假的而[size](qstring.html#size)字符串（ ）大于_width_，那么返回的字符串是字符串的一个副本。

```
 [QString](qstring.html) s = "apple";
 [QString](qstring.html) t = s.leftJustified(8, '.');    // t == "apple..."

```

If _truncate_是真实的[size](qstring.html#size)字符串（ ）大于_width_，然后在字符串的位置后，副本的任何字符_width_被删除，并且该副本被返回。

```
 [QString](qstring.html) str = "Pineapple";
 str = str.leftJustified(5, '.', true);    // str == "Pinea"

```

**See also** [rightJustified](qstring.html#rightJustified)（ ） 。

```
int QString.length (self)
```

返回此字符串中的字符数。相当于[size](qstring.html#size)（ ） 。

**See also** [setLength](index.htm#setLength)（）和[resize](qstring.html#resize)（ ） 。

```
int QString.localeAwareCompare (self, QString s)
```

比较_s1_同_s2_并返回一个整数大于零小于，等于，或大于，如果_s1_小于，等于或大于_s2_。

比较是在一个语言环境，也依赖于平台的方式进行。使用此功能可呈现字符串排序的列表给用户。

自从上的Qt 4.3的Mac OS X ，此功能根据“订单的排序列表”，在国际prefereces面板设置进行比较。

**See also** [compare](qstring.html#compare)（）和[QTextCodec.locale](index.htm#locale)（ ） 。

```
int QString.localeAwareCompare (self, QStringRef s)
```

这个函数的重载[localeAwareCompare](qstring.html#localeAwareCompare)（ ） 。

比较此字符串与_other_字符串并返回比，等于大于零的整数更少，或更大，如果该字符串比小于，等于，或大于_other_字符串。

比较是在一个语言环境，也依赖于平台的方式进行。使用此功能可呈现字符串排序的列表给用户。

同`localeAwareCompare(*this, other)`。

此功能被引入Qt的4.5 。

```
int QString.localeAwareCompare (QString s1, QString s2)
```

这个函数的重载[localeAwareCompare](qstring.html#localeAwareCompare)（ ） 。

比较_s1_同_s2_并返回一个整数大于零小于，等于，或大于，如果_s1_小于，等于或大于_s2_。

比较是在一个语言环境，也依赖于平台的方式进行。使用此功能可呈现字符串排序的列表给用户。

此功能被引入Qt的4.5 。

```
int QString.localeAwareCompare (QString s1, QStringRef s2)
```

这个函数的重载[localeAwareCompare](qstring.html#localeAwareCompare)（ ） 。

比较此字符串与_other_字符串并返回比，等于大于零的整数更少，或更大，如果该字符串比小于，等于，或大于_other_字符串。

比较是在一个语言环境，也依赖于平台的方式进行。使用此功能可呈现字符串排序的列表给用户。

同`localeAwareCompare(*this, other)`。

```
QString QString.mid (self, int position, int n = -1)
```

返回包含一个字符串_n_这串字符，起始于指定_position_索引。

返回一个空字符串，如果_position_索引超出了字符串的长度。如果有小于_n_从给定的字符串中的字符_position_，或者如果_n_为-1 （默认） ，该函数返回，可从指定的所有字符_position_。

例如：

```
 [QString](qstring.html) x = "Nine pineapples";
 [QString](qstring.html) y = x.mid(5, 4);            // y == "pine"
 [QString](qstring.html) z = x.mid(5);               // z == "pineapples"

```

**See also** [left](qstring.html#left)（）和[right](qstring.html#right)（ ） 。

```
QString QString.normalized (self, NormalizationForm mode)
```

返回字符串中给定的Unicode范式_mode_。

```
QString QString.normalized (self, NormalizationForm mode, QChar.UnicodeVersion version)
```

这是一个重载函数。

返回字符串中给定的Unicode范式_mode_，根据给定的_version_的Unicode标准。

```
QString QString.number (int n, int base = 10)
```

返回一个当量数的串_n_根据指定的_base_。

该基地默认为10 ，并且必须在2到36之间。对于基础不是10 ，_n_被视为一个无符号整数。

```
 long a = 63;
 [QString](qstring.html) s = [QString](qstring.html).number(a, 16);             // s == "3f"
 [QString](qstring.html) t = [QString](qstring.html).number(a, 16).toUpper();     // t == "3F"

```

**See also** [setNum](qstring.html#setNum)（ ） 。

```
QString QString.number (float n, str format = 'g', int precision = 6)
```

返回一个当量数的串_n_，根据指定的格式_format_和_precision_。看[Argument Formats](qstring.html#argument-formats)了解详情。

不像[QLocale.toString](qlocale.html#toString)（ ） ，这个函数不尊重用户的区域设置。

**See also** [setNum](qstring.html#setNum)（）和[QLocale.toString](qlocale.html#toString)（ ） 。

```
QString QString.number (int n, int base = 10)
```

这是一个重载函数。

```
QString QString.number (int n, int base = 10)
```

这是一个重载函数。

```
QString QString.prepend (self, QString s)
```

预先考虑字符串_str_这个字符串的开头，并返回一个引用这个字符串。

例如：

```
 [QString](qstring.html) x = "ship";
 [QString](qstring.html) y = "air";
 x.prepend(y);
 // x == "airship"

```

**See also** [append](qstring.html#append)（）和[insert](qstring.html#insert)（ ） 。

```
QString QString.prepend (self, QLatin1String s)
```

这个函数的重载[prepend](qstring.html#prepend)（ ） 。

预先考虑Latin-1的字符串_str_这个字符串。

```
QString QString.prepend (self, QByteArray s)
```

这个函数的重载[prepend](qstring.html#prepend)（ ） 。

预先考虑字节数组_ba_这个字符串。字节数组是使用转换为Unicode[fromAscii](qstring.html#fromAscii)（）函数。

您可以通过定义关闭此功能`QT_NO_CAST_FROM_ASCII`当您编译您的应用程序。如果你想确保所有用户可见的字符串经过这可能是有用的[QObject.tr](qobject.html#tr)（） ，例如。

```
QString.push_back (self, QString s)
```

此功能提供了STL的兼容性，附加给定的_other_串到这个字符串的结尾。它相当于`append(other)`。

**See also** [append](qstring.html#append)（ ） 。

```
QString.push_front (self, QString s)
```

此功能提供了STL的兼容性，前面加上给定的_other_字符串此字符串的开头。它相当于`prepend(other)`。

**See also** [prepend](qstring.html#prepend)（ ） 。

```
QString QString.remove (self, int i, int len)
```

移除_n_从字符串中的字符，开始于指定的_position_索引，并返回一个引用的字符串。

如果指定的_position_索引是字符串中，但_position_+_n_超出了字符串的结尾，字符串被截断在指定_position_。

```
 [QString](qstring.html) s = "Montreal";
 s.remove(1, 4);
 // s == "Meal"

```

**See also** [insert](qstring.html#insert)（）和[replace](qstring.html#replace)（ ） 。

```
QString QString.remove (self, QString str, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

删除的字符每次出现_ch_在这个字符串，并返回一个引用这个字符串。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

例如：

```
 [QString](qstring.html) t = "Ali Baba";
 t.remove([QChar](qchar.html)('a'), [Qt](qt.html).CaseInsensitive);
 // t == "li Bb"

```

这是相同的`replace(ch, "", cs)`。

**See also** [replace](qstring.html#replace)（ ） 。

```
QString QString.remove (self, QRegExp rx)
```

删除给定的每次出现_str_字符串在此字符串中，并返回一个指向该字符串。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

这是相同的`replace(str, "", cs)`。

**See also** [replace](qstring.html#replace)（ ） 。

```
QString QString.repeated (self, int times)
```

返回此字符串的一个副本重复指定次数_times_。

If _times_小于1 ，则返回一个空字符串。

例如：

```
 [QString](qstring.html) str("ab");
 str.repeated(4);            // returns "abababab"

```

此功能被引入Qt的4.5 。

```
QString QString.replace (self, int i, int len, QString after)
```

替换_n_字符开头索引_position_与串_after_并返回一个引用这个字符串。

例如：

```
 [QString](qstring.html) x = "Say yes!";
 [QString](qstring.html) y = "no";
 x.replace(4, 3, y);
 // x == "Say no!"

```

**See also** [insert](qstring.html#insert)（）和[remove](qstring.html#remove)（ ） 。

```
QString QString.replace (self, QString before, QString after, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

```
QString QString.replace (self, QRegExp rx, QString after)
```

```
QString QString.replace (self, QLatin1String before, QLatin1String after, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

```
QString QString.replace (self, QLatin1String before, QString after, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

```
QString QString.replace (self, QString before, QLatin1String after, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这个函数的重载[replace](qstring.html#replace)（ ） 。

替换_n_字符开头索引_position_与第一_size_的字符[QChar](qchar.html)排列_unicode_并返回一个引用这个字符串。

```
QString.reserve (self, int asize)
```

尝试分配内存，至少_size_字符。如果你事先知道该字符串将有多大的话，你可以调用这个函数，如果你调整字符串的时候你很可能会获得更好的性能。如果_size_是低估，会发生最坏的是，[QString](qstring.html)会有点慢。

此函数的唯一目的是提供微调的手段[QString](qstring.html)的内存使用情况。一般情况下，你很少会需要调用这个函数。如果你想改变字符串的大小，请致电[resize](qstring.html#resize)（ ） 。

此功能对于需要建立一个长字符串，并希望避免反复重新分配代码很有用。在这个例子中，我们要添加到字符串，直到某个条件为真，而且我们相当肯定，尺寸够大，足以让值得调用储备（ ） ：

```
 [QString](qstring.html) result;
 int maxSize;
 bool condition;
 [QChar](qchar.html) nextChar;

 result.reserve(maxSize);

 while (condition)
     result.append(nextChar);

 result.squeeze();

```

**See also** [squeeze](qstring.html#squeeze)（）和[capacity](qstring.html#capacity)（ ） 。

```
QString.resize (self, int size)
```

设置字符串的大小，以_size_字符。

If _size_大于该电流的大小，则该字符串被扩展以使其_size_字符长着多馀的字符添加到末尾。新的字符是未初始化的。

If _size_小于该电流的大小，字符被从端部除去。

例如：

```
 [QString](qstring.html) s = "Hello world";
 s.resize(5);
 // s == "Hello"

 s.resize(8);
 // s == "Hello???" (where ? stands for any character)

```

如果你要追加一定数量的相同字符的字符串，请使用[operator+=](qstring.html#operator-2b-eq)（）如下而非调整大小（）：

```
 [QString](qstring.html) t = "Hello";
 t += [QString](qstring.html)(10, 'X');
 // t == "HelloXXXXXXXXXX"

```

如果你想使之达到一定的宽度扩大字符串，并填写与特定字符的新阵地，用[leftJustified](qstring.html#leftJustified)（ ）函数：

If _size_为负时，它相当于通过零。

```
 [QString](qstring.html) r = "Hello";
 r = r.leftJustified(10, ' ');
 // r == "Hello     "

```

**See also** [truncate](qstring.html#truncate)（）和[reserve](qstring.html#reserve)（ ） 。

```
QString QString.right (self, int len)
```

返回包含一个子串的_n_字符串的最右边的字符。

如果整个字符串被返回_n_大于[size](qstring.html#size)（）或小于零。

```
 [QString](qstring.html) x = "Pineapple";
 [QString](qstring.html) y = x.right(5);      // y == "apple"

```

**See also** [left](qstring.html#left)（ ）[mid](qstring.html#mid)（）和[endsWith](qstring.html#endsWith)（ ） 。

```
QString QString.rightJustified (self, int width, QChar fillChar = QLatin1Char(' '), bool truncate = False)
```

返回的字符串[size](qstring.html#size)（ ）_width_包含_fill_字符后面的字符串。例如：

```
 [QString](qstring.html) s = "apple";
 [QString](qstring.html) t = s.rightJustified(8, '.');    // t == "...apple"

```

If _truncate_是假的而[size](qstring.html#size)字符串（ ）大于_width_，那么返回的字符串是字符串的一个副本。

If _truncate_是真实的[size](qstring.html#size)字符串（ ）大于_width_，然后将得到的字符串被截断位置_width_。

```
 [QString](qstring.html) str = "Pineapple";
 str = str.rightJustified(5, '.', true);    // str == "Pinea"

```

**See also** [leftJustified](qstring.html#leftJustified)（ ） 。

```
QString QString.section (self, QString sep, int start, int end = -1, SectionFlags flags = QString.SectionDefault)
```

该函数返回字符串的一部分。

这个字符串被视为由字符分隔的字段的顺序，_sep_。返回的字符串包含从位置字段_start_到位置_end_包容性。如果_end_没有被指定，所有从位置字段_start_到字符串的末尾都包括在内。字段被编号为0 ，1，2 ，等等，从左边算起，并从右至左-1，-2等，计数。

该_flags_参数可以被用来影响功能的行为的某些方面，例如是否区分大小写，是否跳过空字段，以及如何处理与开头和结尾的分隔符，见[SectionFlags](qstring.html#SectionFlag-enum)。

```
 [QString](qstring.html) str;
 [QString](qstring.html) csv = "forename,middlename,surname,phone";
 [QString](qstring.html) path = "/usr/local/bin/myapp"; // First field is empty
 [QString](qstring.html).SectionFlag flag = [QString](qstring.html).SectionSkipEmpty;

 str = csv.section(',', 2, 2);   // str == "surname"
 str = path.section('/', 3, 4);  // str == "bin/myapp"
 str = path.section('/', 3, 3, flag); // str == "myapp"

```

If _start_ or _end_是负的，我们指望从字符串的右边，最右边的字段为-1 ，从最右边的字段为-2之一，等等领域。

```
 str = csv.section(',', -3, -2);  // str == "middlename,surname"
 str = path.section('/', -1); // str == "myapp"

```

**See also** [split](qstring.html#split)（ ） 。

```
QString QString.section (self, QRegExp reg, int start, int end = -1, SectionFlags flags = QString.SectionDefault)
```

这个函数的重载[section](qstring.html#section)（ ） 。

```
 [QString](qstring.html) str;
 [QString](qstring.html) data = "forename**middlename**surname**phone";

 str = data.section("**", 2, 2); // str == "surname"
 str = data.section("**", -3, -2); // str == "middlename**surname"

```

**See also** [split](qstring.html#split)（ ） 。

```
QString QString.setNum (self, int n, int base = 10)
```

字符串设置为印刷价值_n_在指定的_base_，并返回一个引用的字符串。

该基地默认为10 ，并且必须在2到36之间。对于基础不是10 ，_n_被视为一个无符号整数。

```
 [QString](qstring.html) str;
 str.setNum(1234);       // str == "1234"

```

格式化始终使用[QLocale.C](qlocale.html#Language-enum)，即英语/ UnitedStates的。为了得到一些本地化的字符串表示形式，使用[QLocale.toString](qlocale.html#toString)（ ）用适当的语言环境。

```
QString QString.setNum (self, float n, str format = 'g', int precision = 6)
```

这是一个重载函数。

```
QString QString.setNum (self, int n, int base = 10)
```

这是一个重载函数。

```
QString QString.setNum (self, int n, int base = 10)
```

这是一个重载函数。

```
QString QString.simplified (self)
```

返回已经从空白开始和结束时去除，并具有内部的空格用一个空格代替每个序列的字符串。

空白是指任何字符的[QChar.isSpace](qchar.html#isSpace)（ ）返回True 。这包括ASCII字符'\ T' ，为'\ n '，' \ V' ， '\ F' ， ' \ r '和' “ 。

例如：

```
 [QString](qstring.html) str = "  lots\t of\nwhitespace\r\n ";
 str = str.simplified();
 // str == "lots of whitespace";

```

**See also** [trimmed](qstring.html#trimmed)（ ） 。

```
int QString.size (self)
```

返回此字符串中的字符数。

字符串中的最后一个字符的位置是大小（ ） - 1 。另外，[QString](qstring.html)确保字符位置的大小（ ）总是'\ 0' ，这样就可以使用的返回值[data](qstring.html#data)（）和[constData](qstring.html#constData)（）作为参数传递给该期待'\ 0'结尾的字符串函数。

例如：

```
 [QString](qstring.html) str = "World";
 int n = str.size();         // n == 5
 str.data()[0];              // returns 'W'
 str.data()[4];              // returns 'd'
 str.data()[5];              // returns '\0'

```

**See also** [isEmpty](qstring.html#isEmpty)（）和[resize](qstring.html#resize)（ ） 。

```
QStringList QString.split (self, QString sep, SplitBehavior behavior = QString.KeepEmptyParts, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

拆分字符串成子的地方_sep_发生，并返回这些字符串列表。如果_sep_不匹配的字符串中的任何位置，分割（ ）返回一个包含此字符串的单元素列表。

_cs_指定是否_sep_应不区分大小写匹配的情况下，敏感或情况。

If _behavior_ is [QString.SkipEmptyParts](qstring.html#SplitBehavior-enum)，空项不会出现在结果中。默认情况下，空项目保留。

例如：

```
 [QString](qstring.html) str = "a,,b,c";

 [QStringList](qstringlist.html) list1 = str.split(",");
 // list1: [ "a", "", "b", "c" ]

 [QStringList](qstringlist.html) list2 = str.split(",", [QString](qstring.html).SkipEmptyParts);
 // list2: [ "a", "b", "c" ]

```

**See also** [QStringList.join](qstringlist.html#join)（）和[section](qstring.html#section)（ ） 。

```
QStringList QString.split (self, QRegExp sep, SplitBehavior behavior = QString.KeepEmptyParts)
```

这是一个重载函数。

```
QString.squeeze (self)
```

释放所有的内存并不需要存储的字符数据。

此函数的唯一目的是提供微调的手段[QString](qstring.html)的内存使用情况。一般情况下，你很少会需要调用这个函数。

**See also** [reserve](qstring.html#reserve)() and [capacity](qstring.html#capacity)().

```
bool QString.startsWith (self, QString s, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

如果在字符串开头，则返回True_s_否则返回False 。

If _cs_ is [Qt.CaseSensitive](qt.html#CaseSensitivity-enum)（默认） ，搜索是区分大小写的，否则搜索不区分大小写。

```
 [QString](qstring.html) str = "Bananas";
 str.startsWith("Ban");     // returns true
 str.startsWith("Car");     // returns false

```

**See also** [endsWith](qstring.html#endsWith)（ ） 。

```
bool QString.startsWith (self, QStringRef s, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

```
bool QString.startsWith (self, QLatin1String s, Qt.CaseSensitivity cs = Qt.CaseSensitive)
```

这个函数的重载[startsWith](qstring.html#startsWith)（ ） 。

```
QString.swap (self, QString other)
```

掉期的字符串_other_与此字符串。这个操作是非常快的，而且永远不会。

此功能被引入Qt的4.8 。

```
QByteArray QString.toAscii (self)
```

[](qbytearray.html)

[返回字符串的8位表示为](qbytearray.html)[QByteArray](qbytearray.html)。

如果一个编解码器已使用设置[QTextCodec.setCodecForCStrings](qtextcodec.html#setCodecForCStrings)（ ） ，它是用来为Unicode转换为8位字符，否则这个函数一样[toLatin1](qstring.html#toLatin1)（ ） 。

需要注意的是，尽管这个名字，这个功能并不一定返回一个US-ASCII （ ANSI X3.4 - 1986）的字符串，其结果可能不是US-ASCII兼容。

**See also** [fromAscii](qstring.html#fromAscii)（ ）[toLatin1](qstring.html#toLatin1)（ ）[toUtf8](qstring.html#toUtf8)（ ）[toLocal8Bit](qstring.html#toLocal8Bit)（）和[QTextCodec](qtextcodec.html)。

```
QString QString.toCaseFolded (self)
```

返回的情况下折叠的字符串相同。对于大多数的Unicode字符，这是相同的[toLower](qstring.html#toLower)（ ） 。

```
(float, bool ok) QString.toDouble (self)
```

返回字符串转换为`double`值。

如果转换失败，则返回0.0 。

如果发生转换错误，`*`_ok_设置为False ，否则`*`_ok_设置为True 。

```
 [QString](qstring.html) str = "1234.56";
 double val = str.toDouble();   // val == 1234.56

```

各种字符串格式的浮点数可以转换为double值：

```
 bool ok;
 double d;

 d = [QString](qstring.html)( "1234.56e-02" ).toDouble(&ok); // ok == true, d == 12.3456

```

该函数试图根据当前的语言环境来解释的字符串。当前区域设置从系统中应用程序启动时确定，可以通过调用改变[QLocale.setDefault](qlocale.html#setDefault)（ ） 。如果字符串不能根据当前的locale解释，该功能将在“ C”语言环境。

```
 [QLocale](qlocale.html).setDefault([QLocale](qlocale.html).C);
 d = [QString](qstring.html)( "1234,56" ).toDouble(&ok); // ok == false
 d = [QString](qstring.html)( "1234.56" ).toDouble(&ok); // ok == true, d == 1234.56

 [QLocale](qlocale.html).setDefault([QLocale](qlocale.html).German);
 d = [QString](qstring.html)( "1234,56" ).toDouble(&ok); // ok == true, d == 1234.56
 d = [QString](qstring.html)( "1234.56" ).toDouble(&ok); // ok == true, d == 1234.56

```

由于不同的地区小数点还有数千组分隔界限的模糊，这个函数不处理数千组分隔符。如果你需要转换这些号码，请参阅[QLocale.toDouble](qlocale.html#toDouble)（ ） 。

```
 [QLocale](qlocale.html).setDefault([QLocale](qlocale.html).C);
 d = [QString](qstring.html)( "1234,56" ).toDouble(&ok); // ok == false

```

**See also** [number](qstring.html#number)（ ）[QLocale.setDefault](qlocale.html#setDefault)（ ）[QLocale.toDouble](qlocale.html#toDouble)（）和[trimmed](qstring.html#trimmed)（ ） 。

```
(float, bool ok) QString.toFloat (self)
```

返回字符串转换为`float`值。

如果发生转换错误， *_ok_设置为False ，否则*_ok_设置为True 。如果转换失败，则返回0.0 。

例如：

```
 [QString](qstring.html) str1 = "1234.56";
 str1.toFloat();             // returns 1234.56

 bool ok;
 [QString](qstring.html) str2 = "R2D2";
 str2.toFloat(&ok);          // returns 0.0, sets ok to false

```

**See also** [number](qstring.html#number)（ ）[toDouble](qstring.html#toDouble)（）和[toInt](qstring.html#toInt)（ ） 。

```
(int, bool ok) QString.toInt (self, int base = 10)
```

返回字符串转换为`int`使用基_base_，它默认为10 ，并且必须是2和36 ，或0之间。返回0，如果转换失败。

如果发生转换错误， *_ok_设置为False ，否则*_ok_设置为True 。

If _base_为0时， C语言惯例是使用：如果字符串开头的“0x ” ，基部16被使用;如果字符串以“ 0”时，基部8被使用，否则底座10被使用。

例如：

```
 [QString](qstring.html) str = "FF";
 bool ok;
 int hex = str.toInt(&ok, 16);       // hex == 255, ok == true
 int dec = str.toInt(&ok, 10);       // dec == 0, ok == false

```

**See also** [number](qstring.html#number)（ ）[toUInt](qstring.html#toUInt)（）和[toDouble](qstring.html#toDouble)（ ） 。

```
QByteArray QString.toLatin1 (self)
```

[](qbytearray.html)

[返回字符串的的Latin-1表示为](qbytearray.html)[QByteArray](qbytearray.html)。

返回的字节数组是不确定的，如果字符串包含非拉丁文字符。这些字符可以被抑制或问号代替。

**See also** [fromLatin1](qstring.html#fromLatin1)（ ）[toAscii](qstring.html#toAscii)（ ）[toUtf8](qstring.html#toUtf8)（ ）[toLocal8Bit](qstring.html#toLocal8Bit)（）和[QTextCodec](qtextcodec.html)。

```
QByteArray QString.toLocal8Bit (self)
```

[](qbytearray.html)

[返回字符串作为当地8位表示](qbytearray.html)[QByteArray](qbytearray.html)。返回的字节数组是不确定的，如果该字符串包含不支持的本地8位编码的字符。

[QTextCodec.codecForLocale](qtextcodec.html#codecForLocale)（ ）是用来从Unicode执行转换。如果本地编码不能确定，这个函数一样[toLatin1](qstring.html#toLatin1)（ ） 。

如果这个字符串包含不能在语言环境进行编码的任何字符，返回的字节数组是不确定的。这些字符可以由另一被抑制或更换。

**See also** [fromLocal8Bit](qstring.html#fromLocal8Bit)（ ）[toAscii](qstring.html#toAscii)（ ）[toLatin1](qstring.html#toLatin1)（ ）[toUtf8](qstring.html#toUtf8)（）和[QTextCodec](qtextcodec.html)。

```
(int, bool ok) QString.toLong (self, int base = 10)
```

返回字符串转换为`long`使用基_base_，它默认为10 ，并且必须是2和36 ，或0之间。返回0，如果转换失败。

如果发生转换错误， *_ok_设置为False ，否则*_ok_设置为True 。

If _base_为0时， C语言惯例是使用：如果字符串开头的“0x ” ，基部16被使用;如果字符串以“ 0”时，基部8被使用，否则底座10被使用。

例如：

```
 [QString](qstring.html) str = "FF";
 bool ok;

 long hex = str.toLong(&ok, 16);     // hex == 255, ok == true
 long dec = str.toLong(&ok, 10);     // dec == 0, ok == false

```

**See also** [number](qstring.html#number)（ ）[toULong](qstring.html#toULong)（）和[toInt](qstring.html#toInt)（ ） 。

```
(int, bool ok) QString.toLongLong (self, int base = 10)
```

返回字符串转换为`long long`使用基_base_，它默认为10 ，并且必须是2和36 ，或0之间。返回0，如果转换失败。

如果发生转换错误， *_ok_设置为False ，否则*_ok_设置为True 。

If _base_为0时， C语言惯例是使用：如果字符串开头的“0x ” ，基部16被使用;如果字符串以“ 0”时，基部8被使用，否则底座10被使用。

例如：

```
 [QString](qstring.html) str = "FF";
 bool ok;

 [long](index.htm#qint64-typedef) hex = str.toLongLong(&ok, 16);      // hex == 255, ok == true
 [long](index.htm#qint64-typedef) dec = str.toLongLong(&ok, 10);      // dec == 0, ok == false

```

**See also** [number](qstring.html#number)（ ）[toULongLong](qstring.html#toULongLong)（）和[toInt](qstring.html#toInt)（ ） 。

```
QString QString.toLower (self)
```

返回字符串的小写形式的副本。

```
 [QString](qstring.html) str = "Qt by NOKIA";
 str = str.toLower();        // str == "qt by nokia"

```

的情况下转换将总是发生在“C”语言环境。对于依赖于语言环境的情况下使用的折叠[QLocale.toLower](qlocale.html#toLower)（ ）

**See also** [toUpper](qstring.html#toUpper)（）和[QLocale.toLower](qlocale.html#toLower)（ ） 。

```
(int, bool ok) QString.toShort (self, int base = 10)
```

返回字符串转换为`short`使用基_base_，它默认为10 ，并且必须是2和36 ，或0之间。返回0，如果转换失败。

如果发生转换错误， *_ok_设置为False ，否则*_ok_设置为True 。

If _base_为0时， C语言惯例是使用：如果字符串开头的“0x ” ，基部16被使用;如果字符串以“ 0”时，基部8被使用，否则底座10被使用。

例如：

```
 [QString](qstring.html) str = "FF";
 bool ok;

 short hex = str.toShort(&ok, 16);   // hex == 255, ok == true
 short dec = str.toShort(&ok, 10);   // dec == 0, ok == false

```

**See also** [number](qstring.html#number)（ ）[toUShort](qstring.html#toUShort)（）和[toInt](qstring.html#toInt)（ ） 。

```
(int, bool ok) QString.toUInt (self, int base = 10)
```

返回字符串转换为`unsigned int`使用基_base_，它默认为10 ，并且必须是2和36 ，或0之间。返回0，如果转换失败。

如果发生转换错误， *_ok_设置为False ，否则*_ok_设置为True 。

If _base_为0时， C语言惯例是使用：如果字符串开头的“0x ” ，基部16被使用;如果字符串以“ 0”时，基部8被使用，否则底座10被使用。

例如：

```
 [QString](qstring.html) str = "FF";
 bool ok;

 [uint](index.htm#uint-typedef) hex = str.toUInt(&ok, 16);     // hex == 255, ok == true
 [uint](index.htm#uint-typedef) dec = str.toUInt(&ok, 10);     // dec == 0, ok == false

```

**See also** [number](qstring.html#number)（）和[toInt](qstring.html#toInt)（ ） 。

```
(int, bool ok) QString.toULong (self, int base = 10)
```

返回字符串转换为`unsigned long`使用基_base_，它默认为10 ，并且必须是2和36 ，或0之间。返回0，如果转换失败。

如果发生转换错误， *_ok_设置为False ，否则*_ok_设置为True 。

If _base_为0时， C语言惯例是使用：如果字符串开头的“0x ” ，基部16被使用;如果字符串以“ 0”时，基部8被使用，否则底座10被使用。

例如：

```
 [QString](qstring.html) str = "FF";
 bool ok;

 [ulong](index.htm#ulong-typedef) hex = str.toULong(&ok, 16);   // hex == 255, ok == true
 [ulong](index.htm#ulong-typedef) dec = str.toULong(&ok, 10);   // dec == 0, ok == false

```

**See also** [number](qstring.html#number)（ ） 。

```
(int, bool ok) QString.toULongLong (self, int base = 10)
```

返回字符串转换为`unsigned long long`使用基_base_，它默认为10 ，并且必须是2和36 ，或0之间。返回0，如果转换失败。

如果发生转换错误， *_ok_设置为False ，否则*_ok_设置为True 。

If _base_为0时， C语言惯例是使用：如果字符串开头的“0x ” ，基部16被使用;如果字符串以“ 0”时，基部8被使用，否则底座10被使用。

例如：

```
 [QString](qstring.html) str = "FF";
 bool ok;

 [unsigned long](index.htm#quint64-typedef) hex = str.toULongLong(&ok, 16);    // hex == 255, ok == true
 [unsigned long](index.htm#quint64-typedef) dec = str.toULongLong(&ok, 10);    // dec == 0, ok == false

```

**See also** [number](qstring.html#number)（）和[toLongLong](qstring.html#toLongLong)（ ） 。

```
QString QString.toUpper (self)
```

返回字符串的大写副本。

```
 [QString](qstring.html) str = "TeXt";
 str = str.toUpper();        // str == "TEXT"

```

的情况下转换将总是发生在“C”语言环境。对于依赖于语言环境的情况下使用的折叠[QLocale.toUpper](qlocale.html#toUpper)（ ）

**See also** [toLower](qstring.html#toLower)（）和[QLocale.toLower](qlocale.html#toLower)（ ） 。

```
(int, bool ok) QString.toUShort (self, int base = 10)
```

返回字符串转换为`unsigned short`使用基_base_，它默认为10 ，并且必须是2和36 ，或0之间。返回0，如果转换失败。

如果发生转换错误， *_ok_设置为False ，否则*_ok_设置为True 。

If _base_为0时， C语言惯例是使用：如果字符串开头的“0x ” ，基部16被使用;如果字符串以“ 0”时，基部8被使用，否则底座10被使用。

例如：

```
 [QString](qstring.html) str = "FF";
 bool ok;

 [ushort](index.htm#ushort-typedef) hex = str.toUShort(&ok, 16);     // hex == 255, ok == true
 [ushort](index.htm#ushort-typedef) dec = str.toUShort(&ok, 10);     // dec == 0, ok == false

```

**See also** [number](qstring.html#number)（）和[toShort](qstring.html#toShort)（ ） 。

```
QByteArray QString.toUtf8 (self)
```

[](qbytearray.html)

[返回字符串的UTF-8表示为](qbytearray.html)[QByteArray](qbytearray.html)。

UTF - 8是Unicode编码，可以表示所有字符的Unicode字符串像[QString](qstring.html)。

然而，在Unicode的范围内，但是也有一些不被视为某些字符码点。 Unicode标准中保留每个Unicode平面（ U + FFFE ， U + FFFF ， U +1 FFFE ， U +1 FFFF ， U +2 FFFE等） ，以及16码点在范围U + FDD0最后两个码点.. U + FDDF ，包容性的，非字符。如果任何这些出现在字符串中，它们可以被丢弃，而不会出现在UTF-8表示，或者它们可以由一个或多个字符替换被替换。

**See also** [fromUtf8](qstring.html#fromUtf8)（ ）[toAscii](qstring.html#toAscii)（ ）[toLatin1](qstring.html#toLatin1)（ ）[toLocal8Bit](qstring.html#toLocal8Bit)（）和[QTextCodec](qtextcodec.html)。

```
QString QString.trimmed (self)
```

返回已空白从开始和结束删除的字符串。

空白是指任何字符的[QChar.isSpace](qchar.html#isSpace)（ ）返回True 。这包括ASCII字符'\ T' ，为'\ n '，' \ V' ， '\ F' ， ' \ r '和' “ 。

例如：

```
 [QString](qstring.html) str = "  lots\t of\nwhitespace\r\n ";
 str = str.trimmed();
 // str == "lots\t of\nwhitespace"

```

不像[simplified](qstring.html#simplified)（ ） ，修剪（ ）独叶内部的空白。

**See also** [simplified](qstring.html#simplified)（ ） 。

```
QString.truncate (self, int pos)
```

截断字符串在给定的_position_索引。

如果指定的_position_索引超出了字符串的结尾，没有任何反应。

例如：

```
 [QString](qstring.html) str = "Vladivostok";
 str.truncate(4);
 // str == "Vlad"

```

If _position_为负时，它相当于通过零。

**See also** [chop](qstring.html#chop)（ ）[resize](qstring.html#resize)（）和[left](qstring.html#left)（ ） 。

```
QString QString.__add__ (self, QString s2)
```

```
QString QString.__add__ (self, QByteArray ba)
```

```
int QString.__contains__ (self, QString s)
```

```
bool QString.__eq__ (self, QString s)
```

```
bool QString.__eq__ (self, QLatin1String s)
```

```
bool QString.__eq__ (self, QByteArray s)
```

```
bool QString.__eq__ (self, QStringRef s2)
```

```
bool QString.__ge__ (self, QString s)
```

```
bool QString.__ge__ (self, QLatin1String s)
```

```
bool QString.__ge__ (self, QByteArray s)
```

```
QString QString.__getitem__ (self, int i)
```

```
QString QString.__getitem__ (self, slice slice)
```

```
bool QString.__gt__ (self, QString s)
```

```
bool QString.__gt__ (self, QLatin1String s)
```

```
bool QString.__gt__ (self, QByteArray s)
```

```
int QString.__hash__ (self)
```

```
QString QString.__iadd__ (self, QChar.SpecialCharacter c)
```

```
QString QString.__iadd__ (self, QString s)
```

```
QString QString.__iadd__ (self, QLatin1String s)
```

```
QString QString.__iadd__ (self, QByteArray s)
```

```
QString QString.__imul__ (self, int m)
```

```
bool QString.__le__ (self, QString s)
```

```
bool QString.__le__ (self, QLatin1String s)
```

```
bool QString.__le__ (self, QByteArray s)
```

```
 QString.__len__ (self)
```

```
bool QString.__lt__ (self, QString s)
```

```
bool QString.__lt__ (self, QLatin1String s)
```

```
bool QString.__lt__ (self, QByteArray s)
```

```
QString QString.__mul__ (self, int m)
```

```
bool QString.__ne__ (self, QString s)
```

```
bool QString.__ne__ (self, QLatin1String s)
```

```
bool QString.__ne__ (self, QByteArray s)
```

```
bool QString.__ne__ (self, QStringRef s2)
```

```
str QString.__repr__ (self)
```

```
str QString.__str__ (self)
```

```
unicode QString.__unicode__ (self)
```