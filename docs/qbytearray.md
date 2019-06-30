# QByteArray Class Reference

## [[QtCore](index.htm) module]

The QByteArray class provides an array of bytes. [More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, int size, str c)`
*   `__init__ (self, QByteArray a)`
*   `QByteArray append (self, QByteArray a)`
*   `QByteArray append (self, QString s)`
*   `str at (self, int i)`
*   `int capacity (self)`
*   `chop (self, int n)`
*   `clear (self)`
*   `bool contains (self, QByteArray a)`
*   `int count (self, QByteArray a)`
*   `int count (self)`
*   `str data (self)`
*   `bool endsWith (self, QByteArray a)`
*   `QByteArray fill (self, str ch, int size = -1)`
*   `int indexOf (self, QByteArray ba, int from = 0)`
*   `int indexOf (self, QString str, int from = 0)`
*   `QByteArray insert (self, int i, QByteArray a)`
*   `QByteArray insert (self, int i, QString s)`
*   `bool isEmpty (self)`
*   `bool isNull (self)`
*   `int lastIndexOf (self, QByteArray ba, int from = -1)`
*   `int lastIndexOf (self, QString str, int from = -1)`
*   `QByteArray left (self, int len)`
*   `QByteArray leftJustified (self, int width, str fill = ' ', bool truncate = False)`
*   `int length (self)`
*   `QByteArray mid (self, int pos, int length = -1)`
*   `QByteArray prepend (self, QByteArray a)`
*   `push_back (self, QByteArray a)`
*   `push_front (self, QByteArray a)`
*   `QByteArray remove (self, int index, int len)`
*   `QByteArray repeated (self, int times)`
*   `QByteArray replace (self, int index, int len, QByteArray s)`
*   `QByteArray replace (self, QByteArray before, QByteArray after)`
*   `QByteArray replace (self, QString before, QByteArray after)`
*   `reserve (self, int size)`
*   `resize (self, int size)`
*   `QByteArray right (self, int len)`
*   `QByteArray rightJustified (self, int width, str fill = ' ', bool truncate = False)`
*   `QByteArray setNum (self, int n, int base = 10)`
*   `QByteArray setNum (self, float n, str format = 'g', int precision = 6)`
*   `QByteArray setNum (self, int n, int base = 10)`
*   `QByteArray setNum (self, int n, int base = 10)`
*   `QByteArray simplified (self)`
*   `int size (self)`
*   `list-of-QByteArray split (self, str sep)`
*   `squeeze (self)`
*   `bool startsWith (self, QByteArray a)`
*   `swap (self, QByteArray other)`
*   `QByteArray toBase64 (self)`
*   `(float, bool ok) toDouble (self)`
*   `(float, bool ok) toFloat (self)`
*   `QByteArray toHex (self)`
*   `(int, bool ok) toInt (self, int base = 10)`
*   `(int, bool ok) toLong (self, int base = 10)`
*   `(int, bool ok) toLongLong (self, int base = 10)`
*   `QByteArray toLower (self)`
*   `QByteArray toPercentEncoding (self, QByteArray exclude = QByteArray(), QByteArray include = QByteArray(), str percent = '%')`
*   `(int, bool ok) toShort (self, int base = 10)`
*   `(int, bool ok) toUInt (self, int base = 10)`
*   `(int, bool ok) toULong (self, int base = 10)`
*   `(int, bool ok) toULongLong (self, int base = 10)`
*   `QByteArray toUpper (self)`
*   `(int, bool ok) toUShort (self, int base = 10)`
*   `QByteArray trimmed (self)`
*   `truncate (self, int pos)`

### Static Methods

*   `QByteArray fromBase64 (QByteArray base64)`
*   `QByteArray fromHex (QByteArray hexEncoded)`
*   `QByteArray fromPercentEncoding (QByteArray input, str percent = '%')`
*   `QByteArray fromRawData (str)`
*   `QByteArray number (int n, int base = 10)`
*   `QByteArray number (float n, str format = 'g', int precision = 6)`
*   `QByteArray number (int n, int base = 10)`
*   `QByteArray number (int n, int base = 10)`

### Special Methods

*   `QByteArray __add__ (self, QByteArray a2)`
*   `QString __add__ (self, QString s)`
*   `int __contains__ (self, QByteArray a)`
*   `bool __eq__ (self, QString s2)`
*   `bool __eq__ (self, QByteArray a2)`
*   `bool __ge__ (self, QString s2)`
*   `bool __ge__ (self, QByteArray a2)`
*   `str __getitem__ (self, int i)`
*   `QByteArray __getitem__ (self, slice slice)`
*   `bool __gt__ (self, QString s2)`
*   `bool __gt__ (self, QByteArray a2)`
*   `int __hash__ (self)`
*   `QByteArray __iadd__ (self, QByteArray a)`
*   `QByteArray __iadd__ (self, QString s)`
*   `QByteArray __imul__ (self, int m)`
*   `bool __le__ (self, QString s2)`
*   `bool __le__ (self, QByteArray a2)`
*   `__len__ (self)`
*   `bool __lt__ (self, QString s2)`
*   `bool __lt__ (self, QByteArray a2)`
*   `QByteArray __mul__ (self, int m)`
*   `bool __ne__ (self, QString s2)`
*   `bool __ne__ (self, QByteArray a2)`
*   `str __repr__ (self)`
*   `str __str__ (self)`

* * *

## Detailed Description

这个类可以醃制。

可以使用Python的字符串对象，每当一个[QByteArray](qbytearray.html)预计。

该QByteArray中的类提供了一个字节数组。

QByteArray中可以用来存储原始字节（包括'\ 0的）和传统的8位'\ 0'结尾的字符串。使用QByteArray中远远比使用更方便`const char *`。在幕后，它始终确保数据后跟一个'\ 0 '终止和用途[implicit sharing](index.htm)（复制上写的），以减少内存使用量，避免数据的不必要的复制。

除了QByteArray中， Qt还提供了[QString](qstring.html)类存储字符串数据。对于大多数用途，[QString](qstring.html)是您要使用的类。它存储16位的Unicode字符，使得它易于保存non-ASCII/non-Latin-1字符在你的应用程序。此外，[QString](qstring.html)用于整个Qt的API中。两个主要的情况下， QByteArray中是合适的，当你需要存储原始二进制数据，而当内存保护是至关重要的（例如，用Qt嵌入式Linux的） 。

初始化一个QByteArray中的一种方法是简单地传递一个`const char *`它的构造函数。例如，下面的代码创建一个包含数据的“Hello ” 5大小的字节数组：

```
 QByteArray ba("Hello");

```

虽然[size](qbytearray.html#size)（ ） 5 ，字节数组也是在年底维持一个额外的'\ 0 '字符，这样，如果一个函数使用的要求一个指向基础数据（如调用[data](qbytearray.html#data)（ ） ） ，指向的数据保证是'\ 0'结尾的。

QByteArray中做的一个深层副本`const char *`数据，所以你可以在以后修改它没有遇到的副作用。 （如果由于性能原因你不希望采取的字符数据，使用深拷贝[QByteArray.fromRawData](qbytearray.html#fromRawData)（ ）来代替。 ）

另一种方法是利用设置在阵列的大小[resize](qbytearray.html#resize)（）和初始化每字节的数据字节。 QByteArray中使用基于0的索引，就像C + +中的数组。要访问在特定索引位置的字节，你可以使用operator [] （ ） 。对非const字节数组，操作符[ ] （ ）返回一个引用，可以在赋值的左侧使用一个字节。例如：

```
 QByteArray ba;
 ba.resize(5);
 ba[0] = 0x3c;
 ba[1] = 0xb8;
 ba[2] = 0x64;
 ba[3] = 0x18;
 ba[4] = 0xca;

```

对于只读访问，另一种语法是使用[at](qbytearray.html#at)（）：

```
 for (int i = 0; i < ba.size(); ++i) {
     if (ba.at(i) >= 'a' && ba.at(i) <= 'f')
         cout << "Found character in range [a-f]" << endl;
 }

```

[at](qbytearray.html#at)（ ）可以比的operator [ ] （ ）快，因为它不会导致一个[deep copy](index.htm#deep-copy)发生。

要一次提取多少字节，使用[left](qbytearray.html#left)（ ）[right](qbytearray.html#right)（） ，或[mid](qbytearray.html#mid)（ ） 。

一个QByteArray中可以嵌入'\ 0 '字节。该[size](qbytearray.html#size)（ ）函数总是返回整个数组，包括嵌入式'\ 0'的字节大小。如果你想获得的数据备份到不包括第一个' \ 0 '字符，通话时长[qstrlen](index.htm#qstrlen)（ ）的字节数组。

调用后[resize](qbytearray.html#resize)（ ） ，新分配的字节都未定义的值。要设置所有字节到一个特定的值，调用[fill](qbytearray.html#fill)（ ） 。

为了获得一个指向实际的字符数据，调用[data](qbytearray.html#data)（）或[constData](qbytearray.html#constData)（ ） 。这些函数返回一个指针，该数据的开头。指针是保证仍然有效，直到一个非const函数被调用的QByteArray中。它也保证了数据与'\ 0'字节结束，除非QByteArray中是从创建[raw data](qbytearray.html#fromRawData)。这个'\ 0'字节由QByteArray中自动地提供，并以不计数[size](qbytearray.html#size)（ ） 。

QByteArray中提供了修饰的字节数据的以下基本功能：[append](qbytearray.html#append)（ ）[prepend](qbytearray.html#prepend)（ ）[insert](qbytearray.html#insert)（ ）[replace](qbytearray.html#replace)（）和[remove](qbytearray.html#remove)（ ） 。例如：

```
 QByteArray x("and");
 x.prepend("rock ");         // x == "rock and"
 x.append(" roll");          // x == "rock and roll"
 x.replace(5, 3, "&");       // x == "rock & roll"

```

该[replace](qbytearray.html#replace)（）和[remove](qbytearray.html#remove)（ ）函数的前两个参数是要开始擦除，并应被删除的字节数的位置。

当你[append](qbytearray.html#append)（）的数据到一个非空数组，该数组将被重新分配和新的数据复制到它。您可以通过调用避免这种行为[reserve](qbytearray.html#reserve)（），它预先分配一定数量的内存。您也可以拨打[capacity](qbytearray.html#capacity)（ ）来找出QByteArray中实际上有多少内存分配。追加到一个空数组数据不被复制。

一个常见的要求是从一个字节数组（的'\ n '，' \ T' ，''，等等）删除空白字符。如果你想从一个QByteArray中的两端删除空白，使用[trimmed](qbytearray.html#trimmed)（ ） 。如果你想从两端删除空白，并与字节数组中的单个空格字符替换多个连续的空格，使用[simplified](qbytearray.html#simplified)（ ） 。

如果你想找到一个特定的字符或子串中所有出现在一个QByteArray中，使用[indexOf](qbytearray.html#indexOf)（）或[lastIndexOf](qbytearray.html#lastIndexOf)（ ） 。前者向前搜索从给定的索引位置，后者向后搜索开始。都返回字符或字符串的索引位置，如果他们找到它，否则，它们将返回-1 。例如，下面是一个典型的循环，找到一个特定的子字符串的所有匹配：

```
 QByteArray ba("We must be <b>bold</b>, very <b>bold</b>");
 int j = 0;
 while ((j = ba.indexOf("<b>", j)) != -1) {
     cout << "Found <b> tag at index position " << j << endl;
     ++j;
 }

```

如果你只是想检查一个QByteArray中是否包含特定的字符或子串，使用[contains](qbytearray.html#contains)（ ） 。如果你想了解有多少次一个特定的字符或子发生在字节数组中，使用[count](qbytearray.html#count)（ ） 。如果你想更换另一特定值的所有匹配，使用这两个参数中的一个[replace](qbytearray.html#replace)（ ）重载。

QByteArrays可以使用重载运算符，如操作符\u003c （ ） ，操作符\u003c = （ ） ，运算符== （ ）操作符\u003e = （ ） ，等进行比较。比较是完全基于字符的数值，是非常快的，但不是什么人期望的那样。[QString.localeAwareCompare](qstring.html#localeAwareCompare)（ ）是用于排序用户界面字符串一个更好的选择。

由于历史原因， QByteArray中一个空字节数组和一个空字节数组之间的区别。一_null_字节数组是使用QByteArray中的默认构造函数初始化或通过传递（为const char * ）0给构造函数的字节数组。一个_empty_字节数组是任何字节数组大小为0 。一个空字节数组始终是空的，但一个空字节数组不一定空：

```
 QByteArray().isNull();          // returns true
 QByteArray().isEmpty();         // returns true

 QByteArray("").isNull();        // returns false
 QByteArray("").isEmpty();       // returns true

 QByteArray("abc").isNull();     // returns false
 QByteArray("abc").isEmpty();    // returns false

```

之外的全部功能[isNull](qbytearray.html#isNull)（ ）把空字节数组一样的空字节数组。例如，[data](qbytearray.html#data)（ ）返回一个指向一个'\ 0 '字符为一个空字节数组（_not_一个空指针） ，和[QByteArray](qbytearray.html#QByteArray)（ ）比较等于QByteArray中（ “”） 。我们建议您始终使用[isEmpty](qbytearray.html#isEmpty)（）和避免[isNull](qbytearray.html#isNull)（ ） 。

### Notes on Locale

#### Number-String Conversions

该数值数据类型和字符串之间进行转换函数在C语言环境进行，而不管用户的区域设置。使用[QString](qstring.html)以数字和字符串之间进行区域设置的格式转换。

#### 8-bit Character Comparisons

在QByteArray中，其性格和大写和小写的概念是大于或小于另一个特点是与当前位置有关。这会影响支持不区分大小写的选项或比较或小写或大写的参数的函数。不区分大小写的操作和比较将是准确的，如果两个字符串只包含ASCII字符。 （如果`$LC_CTYPE`设置，大多数Unix系统做“正确的事” 。 ）功能，这会影响包括：[contains](qbytearray.html#contains)（ ）[indexOf](qbytearray.html#indexOf)（ ）[lastIndexOf](qbytearray.html#lastIndexOf)（ ）操作符\u003c （ ） ，操作符\u003c = （ ） ，操作者\u003e （ ） ，运算符\u003e = （ ） ，[toLower](qbytearray.html#toLower)（）和[toUpper](qbytearray.html#toUpper)（ ） 。

这个问题并不适用于将QString因为它们代表使用Unicode字符。

* * *

## Method Documentation

```
QByteArray.__init__ (self)
```

构造一个空字节数组。

**See also** [isEmpty](qbytearray.html#isEmpty)（ ） 。

```
QByteArray.__init__ (self, int size, str c)
```

构造一个字符串初始化一个字节数组_str_。

[QByteArray](qbytearray.html)使得字符串数据的深层副本。

```
QByteArray.__init__ (self, QByteArray a)
```

构造一个包含第一个字节数组_size_数组的字节_data_。

If _data_是0 ，一个空字节数组构造。

[QByteArray](qbytearray.html)使得字符串数据的深层副本。

**See also** [fromRawData](qbytearray.html#fromRawData)（ ） 。

```
QByteArray QByteArray.append (self, QByteArray a)
```

[

附加的字节数组_ba_到这个字节数组的末尾。

例如：

](qbytearray.html)

```
 QByteArray x("free");
 [QByteArray](qbytearray.html) y("dom");
 x.append(y);
 // x == "freedom"

```

这是相同的插入物（[size](qbytearray.html#size)（ ）_ba_） 。

注意：[QByteArray](qbytearray.html)是[implicitly shared](index.htm#implicitly-shared)类。因此，如果_this_是一个空[QByteArray](qbytearray.html)，然后_this_只是在共享中的数据_ba_。在这种情况下，不复制数据的操作后，取[constant time](index.htm#constant-time)。如果共享的实例被改性时，其将被复制（复制写入时） ，取[linear time](index.htm#linear-time)。

If _this_是不是空[QByteArray](qbytearray.html)，数据的深层副本中进行，取[linear time](index.htm#linear-time)。

此操作通常不会从分配开销受到影响，因为[QByteArray](qbytearray.html)预先分配额外的空间，在数据的末尾，这样它可以生长而不重新分配为每个附加的操作。

**See also** [operator+=](qbytearray.html#operator-2b-eq)（ ）[prepend](qbytearray.html#prepend)（）和[insert](qbytearray.html#insert)（ ） 。

```
QByteArray QByteArray.append (self, QString s)
```

[

这是一个重载函数。

](qbytearray.html)

[附加字符串_str_这个字节数组。在Unicode数据使用转换为8位字符](qbytearray.html)[QString.toAscii](qstring.html#toAscii)（ ） 。

如果[QString](qstring.html)包含非ASCII Unicode字符，使用此功能可能会导致信息丢失。您可以通过定义关闭此功能`QT_NO_CAST_TO_ASCII`当您编译您的应用程序。然后，您需要调用[QString.toAscii](qstring.html#toAscii)（ ）（或[QString.toLatin1](qstring.html#toLatin1)（）或[QString.toUtf8](qstring.html#toUtf8)（）或[QString.toLocal8Bit](qstring.html#toLocal8Bit)（ ） ）明确，如果你想将数据转换为`const char *`。

```
str QByteArray.at (self, int i)
```

返回字符的索引位置_i_在字节数组。

_i_必须是字节数组中的一个有效的索引位置（即0 \u003c =_i_\u003c[size](qbytearray.html#size)（））。

**See also** [operator[]](qbytearray.html#operator-5b-5d)（ ） 。

```
int QByteArray.capacity (self)
```

返回一个可存储在字节数组中，而不必强制重新分配的最大字节数。

此函数的唯一目的是提供微调的手段[QByteArray](qbytearray.html)的内存使用情况。一般情况下，你很少会需要调用这个函数。如果你想知道有多少字节在字节数组，调用[size](qbytearray.html#size)（ ） 。

**See also** [reserve](qbytearray.html#reserve)（）和[squeeze](qbytearray.html#squeeze)（ ） 。

```
QByteArray.chop (self, int n)
```

移除_n_从字节数组的末尾字节。

If _n_大于[size](qbytearray.html#size)（ ） ，结果是一个空字节数组。

例如：

```
 [QByteArray](qbytearray.html) ba("STARTTLS\r\n");
 ba.chop(2);                 // ba == "STARTTLS"

```

**See also** [truncate](qbytearray.html#truncate)（ ）[resize](qbytearray.html#resize)（）和[left](qbytearray.html#left)（ ） 。

```
QByteArray.clear (self)
```

清除字节数组的内容，使得它为空。

**See also** [resize](qbytearray.html#resize)（）和[isEmpty](qbytearray.html#isEmpty)（ ） 。

```
bool QByteArray.contains (self, QByteArray a)
```

如果字节数组包含字节数组的出现，则返回True_ba_否则返回False 。

**See also** [indexOf](qbytearray.html#indexOf)（）和[count](qbytearray.html#count)（ ） 。

```
int QByteArray.count (self, QByteArray a)
```

返回（可能重叠）出现字节数组数_ba_在这个字节数组。

**See also** [contains](qbytearray.html#contains)（）和[indexOf](qbytearray.html#indexOf)（ ） 。

```
int QByteArray.count (self)
```

这是一个重载函数。

返回（可能重叠的）串出现的次数_str_在字节数组。

```
str QByteArray.data (self)
```

返回一个指针，指向存储在字节数组中的数据。该指针可用于访问和修改构成该阵列的字节数。的数据是'\ 0'终止，即字节在返回的字符串的数目是[size](qbytearray.html#size)（ ） + 1的' \ 0 '终止。

例如：

```
 [QByteArray](qbytearray.html) ba("Hello world");
 char *data = ba.data();
 while (*data) {
     cout << "[" << *data << "]" << endl;
     ++data;
 }

```

指针仍然有效，只要将字节数组是不是重新分配或销毁。对于只读访问，[constData](qbytearray.html#constData)（ ）快，因为它不会导致一个[deep copy](index.htm#deep-copy)发生。

这个函数只是有用的一个字节数组传递给一个接受一个函数`const char *`。

下面的示例使字符*由数据（）返回的副本，但它会破坏堆并导致崩溃，因为它没有在最后分配的' \ 0 '一个字节：

```
 [QString](qstring.html) tmp = "test";
 [QByteArray](qbytearray.html) text = tmp.toLocal8Bit();
 char *data = new char[text.size()]
 strcpy(data, text.data());
 delete [] data;

```

这个分配的正确的空间量：

```
 [QString](qstring.html) tmp = "test";
 [QByteArray](qbytearray.html) text = tmp.toLocal8Bit();
 char *data = new char[text.size() + 1]
 strcpy(data, text.data());
 delete [] data;

```

注意：[QByteArray](qbytearray.html)可以存储任何字节值包括'\ 0的，但大部分的功能，采取`char *`参数假设数据在第一个'\ 0 '，他们遇到的结束。

**See also** [constData](qbytearray.html#constData)（）和[operator[]](qbytearray.html#operator-5b-5d)（ ） 。

```
bool QByteArray.endsWith (self, QByteArray a)
```

如果该字节数组byte数组结尾，则返回True_ba_否则返回False 。

例如：

```
 [QByteArray](qbytearray.html) url("http://qt.nokia.com/index.html");
 if (url.endsWith(".html"))
     ...

```

**See also** [startsWith](qbytearray.html#startsWith)（）和[right](qbytearray.html#right)（ ） 。

```
QByteArray QByteArray.fill (self, str ch, int size = -1)
```

[

设置每个字节的字节数组字符_ch_。如果_size_是从-1 （默认值）不同，字节数组大小调整大小_size_事前。

例如：

](qbytearray.html)

```
 QByteArray ba("Istambul");
 ba.fill('o');
 // ba == "oooooooo"

 ba.fill('X', 2);
 // ba == "XX"

```

**See also** [resize](qbytearray.html#resize)（ ） 。

```
QByteArray QByteArray.fromBase64 (QByteArray base64)
```

[

返回Base64数组的一个副本解码_base64_。输入不进行有效性检查，在输入无效字符被跳过，使解码过程继续进行后续字符。

例如：

](qbytearray.html)

```
 QByteArray text = [QByteArray](qbytearray.html).fromBase64("UXQgaXMgZ3JlYXQh");
 text.data();            // returns "Qt is great!"

```

用于解码Base64编码数据的算法中所定义[RFC 2045](http://www.rfc-editor.org/rfc/rfc2045.txt)。

**See also** [toBase64](qbytearray.html#toBase64)（ ） 。

```
QByteArray QByteArray.fromHex (QByteArray hexEncoded)
```

[

返回十六进制编码数组的副本解码_hexEncoded_。输入不进行有效性检查，在输入无效字符被跳过，使解码过程继续进行后续字符。

例如：

](qbytearray.html)

```
 QByteArray text = [QByteArray](qbytearray.html).fromHex("517420697320677265617421");
 text.data();            // returns "Qt is great!"

```

**See also** [toHex](qbytearray.html#toHex)（ ） 。

```
QByteArray QByteArray.fromPercentEncoding (QByteArray input, str percent = '%')
```

[](qbytearray.html)

[返回的URI / URL样式的百分比编码解码副本_input_。该_percent_参数允许你替换“％”字符为另一个（例如， '](qbytearray.html)[_](index.html)'或' ='） 。

例如：

```
 [QByteArray](qbytearray.html) text = [QByteArray](qbytearray.html).fromPercentEncoding("Qt%20is%20great%33");
 text.data();            // returns "Qt is great!"

```

此功能被引入Qt的4.4 。

**See also** [toPercentEncoding](qbytearray.html#toPercentEncoding)（）和[QUrl.fromPercentEncoding](qurl.html#fromPercentEncoding)（ ） 。

```
QByteArray QByteArray.fromRawData (str)
```

[](qbytearray.html)

[构造一个](qbytearray.html)[QByteArray](qbytearray.html)使用该第一_size_的字节_data_数组。该字节_not_复制。该[QByteArray](qbytearray.html)将包含_data_指针。调用者保证_data_也不会被删除或修改，只要这[QByteArray](qbytearray.html)并且没有被修改的任何拷贝存在。换言之，因为[QByteArray](qbytearray.html)是[implicitly shared](index.htm#implicitly-shared)类，并通过这个函数返回的实例包含_data_指针，调用者不得删除_data_或直接修改它只要返回[QByteArray](qbytearray.html)和任何副本存在。但是，[QByteArray](qbytearray.html)不采取所有权_data_的，所以[QByteArray](qbytearray.html)析构函数永远不会删除原_data_时，即使最后[QByteArray](qbytearray.html)指_data_被破坏。

随后试图修改返回的内容[QByteArray](qbytearray.html)或者从它所做的任何拷贝将导致其创建的一个深层副本_data_在做修改前的数组。这确保了生_data_数组本身将永远不会被修改[QByteArray](qbytearray.html)。

下面是如何使用一个读取数据的例子[QDataStream](qdatastream.html)在内存中的原始数据，而无需对原始数据复制到一个[QByteArray](qbytearray.html)：

```
  static const char mydata[] = {
     0x00, 0x00, 0x03, 0x84, 0x78, 0x9c, 0x3b, 0x76,
     0xec, 0x18, 0xc3, 0x31, 0x0a, 0xf1, 0xcc, 0x99,
     ...
     0x6d, 0x5b
 };

 [QByteArray](qbytearray.html) data = [QByteArray](qbytearray.html).fromRawData(mydata, sizeof(mydata));
 [QDataStream](qdatastream.html) in(&data, [QIODevice](qiodevice.html).ReadOnly);
 ...

```

**Warning:**）与fromRawData （创建的字节数组是_not_null结尾，除非原始数据包含0字符位置_size_。虽然这不要紧，[QDataStream](qdatastream.html)或相似的功能[indexOf](qbytearray.html#indexOf)（ ） ，传递字节数组的函数接受一个`const char *`预期为'\ 0'末端都将失败。

**See also** [setRawData](qbytearray.html#setRawData)（ ）[data](qbytearray.html#data)（）和[constData](qbytearray.html#constData)（ ） 。

```
int QByteArray.indexOf (self, QByteArray ba, int from = 0)
```

返回字节数组中第一次出现的索引位置_ba_在这个字节数组，向前搜索的索引位置_from_。返回-1，如果_ba_找不到。

例如：

```
 [QByteArray](qbytearray.html) x("sticky question");
 [QByteArray](qbytearray.html) y("sti");
 x.indexOf(y);               // returns 0
 x.indexOf(y, 1);            // returns 10
 x.indexOf(y, 10);           // returns 10
 x.indexOf(y, 11);           // returns -1

```

**See also** [lastIndexOf](qbytearray.html#lastIndexOf)（ ）[contains](qbytearray.html#contains)（）和[count](qbytearray.html#count)（ ） 。

```
int QByteArray.indexOf (self, QString str, int from = 0)
```

这是一个重载函数。

返回字符串中第一次出现的索引位置_str_字节数组中，寻找着从索引位置_from_。返回-1，如果_str_找不到。

在Unicode数据使用转换为8位字符[QString.toAscii](qstring.html#toAscii)（ ） 。

如果[QString](qstring.html)包含非ASCII Unicode字符，使用此功能可能会导致信息丢失。您可以通过定义关闭此功能`QT_NO_CAST_TO_ASCII`当您编译您的应用程序。然后，您需要调用[QString.toAscii](qstring.html#toAscii)（ ）（或[QString.toLatin1](qstring.html#toLatin1)（）或[QString.toUtf8](qstring.html#toUtf8)（）或[QString.toLocal8Bit](qstring.html#toLocal8Bit)（ ） ）明确，如果你想将数据转换为`const char *`。

```
QByteArray QByteArray.insert (self, int i, QByteArray a)
```

[

插入的字节数组_ba_在索引位置_i_并返回一个引用到这个字节数组。

例如：

](qbytearray.html)

```
 QByteArray ba("Meal");
 ba.insert(1, [QByteArray](qbytearray.html)("ontr"));
 // ba == "Montreal"

```

**See also** [append](qbytearray.html#append)（ ）[prepend](qbytearray.html#prepend)（ ）[replace](qbytearray.html#replace)（）和[remove](qbytearray.html#remove)（ ） 。

```
QByteArray QByteArray.insert (self, int i, QString s)
```

[

这是一个重载函数。

](qbytearray.html)

[插入字符串_str_在索引位置_i_在字节数组。在Unicode数据使用转换为8位字符](qbytearray.html)[QString.toAscii](qstring.html#toAscii)（ ） 。

If _i_大于[size](qbytearray.html#size)（） ，该阵列是第一，采用扩展[resize](qbytearray.html#resize)（ ） 。

如果[QString](qstring.html)包含非ASCII Unicode字符，使用此功能可能会导致信息丢失。您可以通过定义关闭此功能`QT_NO_CAST_TO_ASCII`当您编译您的应用程序。然后，您需要调用[QString.toAscii](qstring.html#toAscii)（ ）（或[QString.toLatin1](qstring.html#toLatin1)（）或[QString.toUtf8](qstring.html#toUtf8)（）或[QString.toLocal8Bit](qstring.html#toLocal8Bit)（ ） ）明确，如果你想将数据转换为`const char *`。

```
bool QByteArray.isEmpty (self)
```

返回True如果字节数组的大小为0 ，否则返回False 。

例如：

```
 [QByteArray](qbytearray.html)().isEmpty();         // returns true
 [QByteArray](qbytearray.html)("").isEmpty();       // returns true
 [QByteArray](qbytearray.html)("abc").isEmpty();    // returns false

```

**See also** [size](qbytearray.html#size)（ ） 。

```
bool QByteArray.isNull (self)
```

返回True如果该字节数组为null ，否则返回False 。

例如：

```
 [QByteArray](qbytearray.html)().isNull();          // returns true
 [QByteArray](qbytearray.html)("").isNull();        // returns false
 [QByteArray](qbytearray.html)("abc").isNull();     // returns false

```

Qt后，由于历史原因，空字节数组和空字节数组之间的区别。对于大多数应用来说，重要的是一个字节数组中是否包含任何数据，这可以通过使用来确定[isEmpty](qbytearray.html#isEmpty)（ ） 。

**See also** [isEmpty](qbytearray.html#isEmpty)（ ） 。

```
int QByteArray.lastIndexOf (self, QByteArray ba, int from = -1)
```

返回字节数组中最后一次出现的索引位置_ba_在这个字节数组，从索引位置向后搜索_from_。如果_from_为-1 （默认值） ，该搜索从最后一个字节。返回-1，如果_ba_找不到。

例如：

```
 [QByteArray](qbytearray.html) x("crazy azimuths");
 [QByteArray](qbytearray.html) y("az");
 x.lastIndexOf(y);           // returns 6
 x.lastIndexOf(y, 6);        // returns 6
 x.lastIndexOf(y, 5);        // returns 2
 x.lastIndexOf(y, 1);        // returns -1

```

**See also** [indexOf](qbytearray.html#indexOf)（ ）[contains](qbytearray.html#contains)（）和[count](qbytearray.html#count)（ ） 。

```
int QByteArray.lastIndexOf (self, QString str, int from = -1)
```

这是一个重载函数。

返回字符串中最后一次出现的索引位置_str_字节数组中，从索引位置向后搜索_from_。如果_from_为-1 （默认值） ，开始搜索在最后（[size](qbytearray.html#size)（ ） - 1 ）字节。返回-1，如果_str_找不到。

在Unicode数据使用转换为8位字符[QString.toAscii](qstring.html#toAscii)（ ） 。

如果[QString](qstring.html)包含非ASCII Unicode字符，使用此功能可能会导致信息丢失。您可以通过定义关闭此功能`QT_NO_CAST_TO_ASCII`当您编译您的应用程序。然后，您需要调用[QString.toAscii](qstring.html#toAscii)（ ）（或[QString.toLatin1](qstring.html#toLatin1)（）或[QString.toUtf8](qstring.html#toUtf8)（）或[QString.toLocal8Bit](qstring.html#toLocal8Bit)（ ） ）明确，如果你想将数据转换为`const char *`。

```
QByteArray QByteArray.left (self, int len)
```

[

返回包含最左边的字节数组_len_这个字节数组的字节。

](qbytearray.html)

[如果整个字节数组返回_len_大于](qbytearray.html)[size](qbytearray.html#size)（ ） 。

例如：

```
 [QByteArray](qbytearray.html) x("Pineapple");
 [QByteArray](qbytearray.html) y = x.left(4);
 // y == "Pine"

```

**See also** [right](qbytearray.html#right)（ ）[mid](qbytearray.html#mid)（ ）[startsWith](qbytearray.html#startsWith)（）和[truncate](qbytearray.html#truncate)（ ） 。

```
QByteArray QByteArray.leftJustified (self, int width, str fill = ' ', bool truncate = False)
```

[

返回大小的字节数组_width_包含由该填充字节数组_fill_字符。

](qbytearray.html)

[If _truncate_是假的而](qbytearray.html)[size](qbytearray.html#size)字节数组的（ ）超过_width_，则返回的字节数组是该字节数组的一个副本。

If _truncate_是真实的[size](qbytearray.html#size)字节数组的（ ）超过_width_，然后在后的位置的字节数组的副本的任何字节_width_被删除，并且该副本被返回。

例如：

```
 [QByteArray](qbytearray.html) x("apple");
 [QByteArray](qbytearray.html) y = x.leftJustified(8, '.');   // y == "apple..."

```

**See also** [rightJustified](qbytearray.html#rightJustified)（ ） 。

```
int QByteArray.length (self)
```

同[size](qbytearray.html#size)（ ） 。

```
QByteArray QByteArray.mid (self, int pos, int length = -1)
```

[

返回一个包含一个字节数组_len_从这个字节数组，起始于位置_pos_。

](qbytearray.html)

[If _len_为-1 （默认） ，或_pos_+_len_\u003e =](qbytearray.html)[size](qbytearray.html#size)（ ） ，返回一个包含所有字节起始于位置的字节数组_pos_直到字节数组的结尾。

例如：

```
 [QByteArray](qbytearray.html) x("Five pineapples");
 [QByteArray](qbytearray.html) y = x.mid(5, 4);     // y == "pine"
 [QByteArray](qbytearray.html) z = x.mid(5);        // z == "pineapples"

```

**See also** [left](qbytearray.html#left)（）和[right](qbytearray.html#right)（ ） 。

```
QByteArray QByteArray.number (int n, int base = 10)
```

[

返回一个包含字符串相等的数目的字节数组_n_基地_base_（默认为10 ） 。该_base_可以是2到36之间的任意值。

例如：

](qbytearray.html)

```
 int n = 63;QByteArray.number(n);              // returns "63"
 [QByteArray](qbytearray.html).number(n, 16);          // returns "3f"
 [QByteArray](qbytearray.html).number(n, 16).toUpper();  // returns "3F"

```

**Note:**数字的格式不本地化，缺省的C语言环境，不论使用者的语言环境中使用。

**See also** [setNum](qbytearray.html#setNum)（）和[toInt](qbytearray.html#toInt)（ ） 。

```
QByteArray QByteArray.number (float n, str format = 'g', int precision = 6)
```

[

这是一个重载函数。

](qbytearray.html)

[**See also**](qbytearray.html) [toUInt](qbytearray.html#toUInt)（ ） 。

```
QByteArray QByteArray.number (int n, int base = 10)
```

[

这是一个重载函数。

](qbytearray.html)

[**See also**](qbytearray.html) [toLongLong](qbytearray.html#toLongLong)（ ） 。

```
QByteArray QByteArray.number (int n, int base = 10)
```

[

这是一个重载函数。

](qbytearray.html)

[**See also**](qbytearray.html) [toULongLong](qbytearray.html#toULongLong)（ ） 。

```
QByteArray QByteArray.prepend (self, QByteArray a)
```

[

预先考虑字节数组_ba_这个字节数组并返回一个引用到这个字节数组。

例如：

](qbytearray.html)

```
 QByteArray x("ship");
 [QByteArray](qbytearray.html) y("air");
 x.prepend(y);
 // x == "airship"

```

这是相同的插入件（0，_ba_） 。

注意：[QByteArray](qbytearray.html)是[implicitly shared](index.htm#implicitly-shared)类。因此，如果_this_是一个空[QByteArray](qbytearray.html)，然后_this_只是在共享中的数据_ba_。在这种情况下，不复制数据的操作后，取[constant time](index.htm#constant-time)。如果共享的实例被改性时，其将被复制（复制写入时） ，取[linear time](index.htm#linear-time)。

If _this_是不是空[QByteArray](qbytearray.html)，数据的深层副本中进行，取[linear time](index.htm#linear-time)。

**See also** [append](qbytearray.html#append)（）和[insert](qbytearray.html#insert)（ ） 。

```
QByteArray.push_back (self, QByteArray a)
```

此功能提供了STL的兼容性。它相当于追加（_other_） 。

```
QByteArray.push_front (self, QByteArray a)
```

此功能提供了STL的兼容性。它相当于前置（_other_） 。

```
QByteArray QByteArray.remove (self, int index, int len)
```

[

移除_len_从字节数组，起始索引位置_pos_，并返回一个引用数组。

If _pos_超出范围，没有任何反应。如果_pos_是有效的，但_pos_+_len_比数组的大小较大时，阵列处被截断位置_pos_。

例如：

](qbytearray.html)

```
 QByteArray ba("Montreal");
 ba.remove(1, 4);
 // ba == "Meal"

```

**See also** [insert](qbytearray.html#insert)（）和[replace](qbytearray.html#replace)（ ） 。

```
QByteArray QByteArray.repeated (self, int times)
```

[

返回此字节数组的副本重复指定次数_times_。

If _times_小于1 ，则返回一个空字节数组。

例如：

](qbytearray.html)

```
 QByteArray ba("ab");
 ba.repeated(4);             // returns "abababab"

```

此功能被引入Qt的4.5 。

```
QByteArray QByteArray.replace (self, int index, int len, QByteArray s)
```

[

替换_len_从索引位置字节_pos_与字节数组_after_，并返回一个引用到这个字节数组。

例如：

](qbytearray.html)

```
 QByteArray x("Say yes!");
 [QByteArray](qbytearray.html) y("no");
 x.replace(4, 3, y);
 // x == "Say no!"

```

**See also** [insert](qbytearray.html#insert)（）和[remove](qbytearray.html#remove)（ ） 。

```
QByteArray QByteArray.replace (self, QByteArray before, QByteArray after)
```

[

这是一个重载函数。

替换_len_从索引位置字节_pos_以零结尾的字符串_after_。

注意：这个可以改变字节数组的长度。

](qbytearray.html)

```
QByteArray QByteArray.replace (self, QString before, QByteArray after)
```

[

这是一个重载函数。

替换_len_从索引位置字节_pos_同_alen_从字符串字节_after_。_after_允许有'\ 0 '字符。

此功能被引入Qt的4.7 。

```
QByteArray.reserve (self, int size)
```

](qbytearray.html)

[尝试分配内存，至少_size_字节。如果你事先知道将字节数组将有多大的话，你可以调用这个函数，如果你调用](qbytearray.html)[resize](qbytearray.html#resize)（ ）通常你很可能会获得更好的性能。如果_size_是低估，会发生最坏的是，[QByteArray](qbytearray.html)会有点慢。

此函数的唯一目的是提供微调的手段[QByteArray](qbytearray.html)的内存使用情况。一般情况下，你很少会需要调用这个函数。如果你想改变的字节数组的大小，请致电[resize](qbytearray.html#resize)（ ） 。

**See also** [squeeze](qbytearray.html#squeeze)（）和[capacity](qbytearray.html#capacity)（ ） 。

```
QByteArray.resize (self, int size)
```

设置字节数组的大小_size_字节。

If _size_大于该电流的大小，字节数组被扩展以使其_size_与末尾添加额外的字节字节。新的字节被初始化。

If _size_小于该电流的大小，字节被从端部除去。

**See also** [size](qbytearray.html#size)（）和[truncate](qbytearray.html#truncate)（ ） 。

```
QByteArray QByteArray.right (self, int len)
```

[

返回包含最右边的字节数组_len_这个字节数组的字节。

](qbytearray.html)

[如果整个字节数组返回_len_大于](qbytearray.html)[size](qbytearray.html#size)（ ） 。

例如：

```
 [QByteArray](qbytearray.html) x("Pineapple");
 [QByteArray](qbytearray.html) y = x.right(5);
 // y == "apple"

```

**See also** [endsWith](qbytearray.html#endsWith)（ ）[left](qbytearray.html#left)（）和[mid](qbytearray.html#mid)（ ） 。

```
QByteArray QByteArray.rightJustified (self, int width, str fill = ' ', bool truncate = False)
```

[

返回大小的字节数组_width_包含_fill_字符后跟这个字节数组。

If _truncate_是假的字节数组的大小超过_width_，则返回的字节数组是该字节数组的一个副本。

If _truncate_是真实的字节数组的大小超过_width_，然后将得到的字节数组被截断位置_width_。

例如：

](qbytearray.html)

```
 QByteArray x("apple");
 [QByteArray](qbytearray.html) y = x.rightJustified(8, '.');    // y == "...apple"

```

**See also** [leftJustified](qbytearray.html#leftJustified)（ ） 。

```
QByteArray QByteArray.setNum (self, int n, int base = 10)
```

[

设置字节数组的印刷价值_n_在基地_base_（默认为10 ），并返回一个引用到的字节数组。该_base_可以是2到36之间的任意值。

例如：

](qbytearray.html)

```
 QByteArray ba;
 int n = 63;
 ba.setNum(n);           // ba == "63"
 ba.setNum(n, 16);       // ba == "3f"

```

**Note:**数字的格式不本地化，缺省的C语言环境，不论使用者的语言环境中使用。

**See also** [number](qbytearray.html#number)（）和[toInt](qbytearray.html#toInt)（ ） 。

```
QByteArray QByteArray.setNum (self, float n, str format = 'g', int precision = 6)
```

[

这是一个重载函数。

](qbytearray.html)

[**See also**](qbytearray.html) [toUInt](qbytearray.html#toUInt)（ ） 。

```
QByteArray QByteArray.setNum (self, int n, int base = 10)
```

[

这是一个重载函数。

](qbytearray.html)

[**See also**](qbytearray.html) [toShort](qbytearray.html#toShort)（ ） 。

```
QByteArray QByteArray.setNum (self, int n, int base = 10)
```

[

这是一个重载函数。

](qbytearray.html)

[**See also**](qbytearray.html) [toUShort](qbytearray.html#toUShort)（ ） 。

```
QByteArray QByteArray.simplified (self)
```

[

返回一个字节数组，它已经从空白开始和结束时去除，并具有内部的空格用一个空格代替每个序列。

空白单元，对标准C + +的使用isspace （ ）函数返回True的任何字符。这包括ASCII字符'\ T' ，为'\ n '，' \ V' ， '\ F' ， ' \ r '和' “ 。

例如：

](qbytearray.html)

```
 QByteArray ba("  lots\t of\nwhitespace\r\n ");
 ba = ba.simplified();
 // ba == "lots of whitespace";

```

**See also** [trimmed](qbytearray.html#trimmed)（ ） 。

```
int QByteArray.size (self)
```

返回此字节数组的字节数。

字节数组中的最后一个字节是在位置的大小（ ） - 1 。另外，[QByteArray](qbytearray.html)确保在位置大小的字节（ ）总是'\ 0' ，这样就可以使用的返回值[data](qbytearray.html#data)（）和[constData](qbytearray.html#constData)（）作为参数传递给该期待'\ 0'结尾的字符串函数。如果[QByteArray](qbytearray.html)对象是从创建[raw data](qbytearray.html#fromRawData)这不包括结尾的空终止字符，然后[QByteArray](qbytearray.html)不添加它automaticall除非[deep copy](index.htm#deep-copy)被创建。

例如：

```
 [QByteArray](qbytearray.html) ba("Hello");
 int n = ba.size();          // n == 5
 ba.data()[0];               // returns 'H'
 ba.data()[4];               // returns 'o'
 ba.data()[5];               // returns '\0'

```

**See also** [isEmpty](qbytearray.html#isEmpty)（）和[resize](qbytearray.html#resize)（ ） 。

```
list-of-QByteArray QByteArray.split (self, str sep)
```

拆分字节数组转换成子阵的地方_sep_发生，并返回这些阵列的列表。如果_sep_不匹配的字节数组，分割任何地方（ ）返回一个包含此字节数组中的单个元素的列表。

```
QByteArray.squeeze (self)
```

释放任何内存不需要存储阵列的数据。

此函数的唯一目的是提供微调的手段[QByteArray](qbytearray.html)的内存使用情况。一般情况下，你很少会需要调用这个函数。

**See also** [reserve](qbytearray.html#reserve)（）和[capacity](qbytearray.html#capacity)（ ） 。

```
bool QByteArray.startsWith (self, QByteArray a)
```

如果这个字节数组开头的字节数组，则返回True_ba_否则返回False 。

例如：

```
 [QByteArray](qbytearray.html) url("ftp://ftp.qt.nokia.com/");
 if (url.startsWith("ftp:"))
     ...

```

**See also** [endsWith](qbytearray.html#endsWith)() and [left](qbytearray.html#left)().

```
QByteArray.swap (self, QByteArray other)
```

掉期的字节数组_other_与此字节数组。这个操作是非常快的，而且永远不会。

此功能被引入Qt的4.8 。

```
QByteArray QByteArray.toBase64 (self)
```

[

返回字节数组的副本，按Base64编码。

](qbytearray.html)

```
 QByteArray text("Qt is great!");
 text.toBase64();        // returns "UXQgaXMgZ3JlYXQh"

```

使用Base64编码的数据进行编码的算法定义中[RFC 2045](http://www.rfc-editor.org/rfc/rfc2045.txt)。

**See also** [fromBase64](qbytearray.html#fromBase64)（ ） 。

```
(float, bool ok) QByteArray.toDouble (self)
```

返回字节数组转换为`double`值。

如果转换失败，则返回0.0 。

If _ok_不为0 ：如果发生转换错误， *_ok_设置为False ，否则*_ok_设置为True 。

```
 [QByteArray](qbytearray.html) string("1234.56");
 double a = string.toDouble();   // a == 1234.56

```

**Note:**在默认的C语言环境下进行数字转换，而不论用户的语言环境。

**See also** [number](qbytearray.html#number)（ ） 。

```
(float, bool ok) QByteArray.toFloat (self)
```

返回字节数组转换为`float`值。

如果转换失败，则返回0.0 。

If _ok_不为0 ：如果发生转换错误， *_ok_设置为False ，否则*_ok_设置为True 。

**Note:**在默认的C语言环境下进行数字转换，而不论用户的语言环境。

**See also** [number](qbytearray.html#number)（ ） 。

```
QByteArray QByteArray.toHex (self)
```

[

返回字节数组的十六进制编码副本。十六进制编码使用数字0-9和字母AF 。

](qbytearray.html)

[**See also**](qbytearray.html) [fromHex](qbytearray.html#fromHex)（ ） 。

```
(int, bool ok) QByteArray.toInt (self, int base = 10)
```

返回字节数组转换为`int`使用基_base_，它默认为10 ，并且必须是2和36 ，或0之间。

If _base_为0时，该基地是使用以下规则自动确定：如果字节数组开始以“0x” ，它被假定为十六进制的，如果它以“ 0 ”时，它被假定为八进制，否则它被假定为是小数。

返回0，如果转换失败。

If _ok_不为0 ：如果发生转换错误， *_ok_设置为False ，否则*_ok_设置为True 。

```
 [QByteArray](qbytearray.html) str("FF");
 bool ok;
 int hex = str.toInt(&ok, 16);     // hex == 255, ok == true
 int dec = str.toInt(&ok, 10);     // dec == 0, ok == false

```

**Note:**在默认的C语言环境下进行数字转换，而不论用户的语言环境。

**See also** [number](qbytearray.html#number)（ ） 。

```
(int, bool ok) QByteArray.toLong (self, int base = 10)
```

返回字节数组转换为`long`INT使用基_base_，它默认为10 ，并且必须是2和36 ，或0之间。

If _base_为0时，该基地是使用以下规则自动确定：如果字节数组开始以“0x” ，它被假定为十六进制的，如果它以“ 0 ”时，它被假定为八进制，否则它被假定为是小数。

返回0，如果转换失败。

If _ok_不为0 ：如果发生转换错误， *_ok_设置为False ，否则*_ok_设置为True 。

```
 [QByteArray](qbytearray.html) str("FF");
 bool ok;
 long hex = str.toLong(&ok, 16);   // hex == 255, ok == true
 long dec = str.toLong(&ok, 10);   // dec == 0, ok == false

```

**Note:**在默认的C语言环境下进行数字转换，而不论用户的语言环境。

这个函数是Qt 4.1中引入。

**See also** [number](qbytearray.html#number)（ ） 。

```
(int, bool ok) QByteArray.toLongLong (self, int base = 10)
```

返回字节数组转换为`long long`使用基_base_，它默认为10 ，并且必须是2和36 ，或0之间。

If _base_为0时，该基地是使用以下规则自动确定：如果字节数组开始以“0x” ，它被假定为十六进制的，如果它以“ 0 ”时，它被假定为八进制，否则它被假定为是小数。

返回0，如果转换失败。

If _ok_不为0 ：如果发生转换错误， *_ok_设置为False ，否则*_ok_设置为True 。

**Note:**在默认的C语言环境下进行数字转换，而不论用户的语言环境。

**See also** [number](qbytearray.html#number)（ ） 。

```
QByteArray QByteArray.toLower (self)
```

[

返回字节数组的小写副本。从ByteArray中被解释为Latin-1的编码字符串。

例如：

](qbytearray.html)

```
 QByteArray x("Qt by NOKIA");
 [QByteArray](qbytearray.html) y = x.toLower();
 // y == "qt by nokia"

```

**See also** [toUpper](qbytearray.html#toUpper)（）和[8-bit Character Comparisons](qbytearray.html#8-bit-character-comparisons)。

```
QByteArray QByteArray.toPercentEncoding (self, QByteArray exclude = QByteArray(), QByteArray include = QByteArray(), str percent = '%')
```

[

返回此字节数组的一个URI / URL样式的百分比编码副本。该_percent_参数允许您复盖默认的“％”字符为另一个。

默认情况下，此功能将编码不属于下列之一的所有字符：

](qbytearray.html)

[ALPHA（ “a”到“z”的和“A”到“Z” ） /数字（0到9）/ “ - ” /“。 ” / “](qbytearray.html)[_](index.html)“/” 〜“

为了防止字符被编码它们传递给_exclude_。要强制字符进行编码它们传递给_include_。该_percent_字符总是编码。

例如：

```
 [QByteArray](qbytearray.html) text = "{a fishy string?}";
 [QByteArray](qbytearray.html) ba = text.toPercentEncoding("{}", "s");
 qDebug(ba.constData());
 // prints "{a fi%73hy %73tring%3F}"

```

十六进制编码使用数字0-9以及大写字母AF 。

此功能被引入Qt的4.4 。

**See also** [fromPercentEncoding](qbytearray.html#fromPercentEncoding)（）和[QUrl.toPercentEncoding](qurl.html#toPercentEncoding)（ ） 。

```
(int, bool ok) QByteArray.toShort (self, int base = 10)
```

返回字节数组转换为`short`使用基_base_，它默认为10 ，并且必须是2和36 ，或0之间。

If _base_为0时，该基地是使用以下规则自动确定：如果字节数组开始以“0x” ，它被假定为十六进制的，如果它以“ 0 ”时，它被假定为八进制，否则它被假定为是小数。

返回0，如果转换失败。

If _ok_不为0 ：如果发生转换错误， *_ok_设置为False ，否则*_ok_设置为True 。

**Note:**在默认的C语言环境下进行数字转换，而不论用户的语言环境。

**See also** [number](qbytearray.html#number)（ ） 。

```
(int, bool ok) QByteArray.toUInt (self, int base = 10)
```

返回字节数组转换为`unsigned int`使用基_base_，它默认为10 ，并且必须是2和36 ，或0之间。

If _base_为0时，该基地是使用以下规则自动确定：如果字节数组开始以“0x” ，它被假定为十六进制的，如果它以“ 0 ”时，它被假定为八进制，否则它被假定为是小数。

返回0，如果转换失败。

If _ok_不为0 ：如果发生转换错误， *_ok_设置为False ，否则*_ok_设置为True 。

**Note:**在默认的C语言环境下进行数字转换，而不论用户的语言环境。

**See also** [number](qbytearray.html#number)（ ） 。

```
(int, bool ok) QByteArray.toULong (self, int base = 10)
```

返回字节数组转换为`unsigned long int`使用基_base_，它默认为10 ，并且必须是2和36 ，或0之间。

If _base_为0时，该基地是使用以下规则自动确定：如果字节数组开始以“0x” ，它被假定为十六进制的，如果它以“ 0 ”时，它被假定为八进制，否则它被假定为是小数。

返回0，如果转换失败。

If _ok_不为0 ：如果发生转换错误， *_ok_设置为False ，否则*_ok_设置为True 。

**Note:**在默认的C语言环境下进行数字转换，而不论用户的语言环境。

这个函数是Qt 4.1中引入。

**See also** [number](qbytearray.html#number)（ ） 。

```
(int, bool ok) QByteArray.toULongLong (self, int base = 10)
```

返回字节数组转换为`unsigned long long`使用基_base_，它默认为10 ，并且必须是2和36 ，或0之间。

If _base_为0时，该基地是使用以下规则自动确定：如果字节数组开始以“0x” ，它被假定为十六进制的，如果它以“ 0 ”时，它被假定为八进制，否则它被假定为是小数。

返回0，如果转换失败。

If _ok_不为0 ：如果发生转换错误， *_ok_设置为False ，否则*_ok_设置为True 。

**Note:**在默认的C语言环境下进行数字转换，而不论用户的语言环境。

**See also** [number](qbytearray.html#number)（ ） 。

```
QByteArray QByteArray.toUpper (self)
```

[

返回字节数组的大写副本。从ByteArray中被解释为Latin-1的编码字符串。

例如：

](qbytearray.html)

```
 QByteArray x("Qt by NOKIA");
 [QByteArray](qbytearray.html) y = x.toUpper();
 // y == "QT BY NOKIA"

```

**See also** [toLower](qbytearray.html#toLower)（）和[8-bit Character Comparisons](qbytearray.html#8-bit-character-comparisons)。

```
(int, bool ok) QByteArray.toUShort (self, int base = 10)
```

返回字节数组转换为`unsigned short`使用基_base_，它默认为10 ，并且必须是2和36 ，或0之间。

If _base_为0时，该基地是使用以下规则自动确定：如果字节数组开始以“0x” ，它被假定为十六进制的，如果它以“ 0 ”时，它被假定为八进制，否则它被假定为是小数。

返回0，如果转换失败。

If _ok_不为0 ：如果发生转换错误， *_ok_设置为False ，否则*_ok_设置为True 。

**Note:**在默认的C语言环境下进行数字转换，而不论用户的语言环境。

**See also** [number](qbytearray.html#number)（ ） 。

```
QByteArray QByteArray.trimmed (self)
```

[

返回一个字节数组，它已经从空白开始和结束时删除。

空白单元，对标准C + +的使用isspace （ ）函数返回True的任何字符。这包括ASCII字符'\ T' ，为'\ n '，' \ V' ， '\ F' ， ' \ r '和' “ 。

例如：

](qbytearray.html)

```
 QByteArray ba("  lots\t of\nwhitespace\r\n ");
 ba = ba.trimmed();
 // ba == "lots\t of\nwhitespace";

```

不像[simplified](qbytearray.html#simplified)（ ） ，修剪（ ）独叶内部的空白。

**See also** [simplified](qbytearray.html#simplified)（ ） 。

```
QByteArray.truncate (self, int pos)
```

截断该字节数组索引位置_pos_。

If _pos_超出了数组的结尾，没有任何反应。

例如：

```
 [QByteArray](qbytearray.html) ba("Stockholm");
 ba.truncate(5);             // ba == "Stock"

```

**See also** [chop](qbytearray.html#chop)（ ）[resize](qbytearray.html#resize)（）和[left](qbytearray.html#left)（ ） 。

```
QByteArray QByteArray.__add__ (self, QByteArray a2)
```

[

```
QString QByteArray.__add__ (self, QString s)
```

```
int QByteArray.__contains__ (self, QByteArray a)
```

```
bool QByteArray.__eq__ (self, QString s2)
```

```
bool QByteArray.__eq__ (self, QByteArray a2)
```

```
bool QByteArray.__ge__ (self, QString s2)
```

```
bool QByteArray.__ge__ (self, QByteArray a2)
```

```
str QByteArray.__getitem__ (self, int i)
```

](qbytearray.html)

```
QByteArray QByteArray.__getitem__ (self, slice slice)
```

[

```
bool QByteArray.__gt__ (self, QString s2)
```

```
bool QByteArray.__gt__ (self, QByteArray a2)
```

```
int QByteArray.__hash__ (self)
```

](qbytearray.html)

```
QByteArray QByteArray.__iadd__ (self, QByteArray a)
```

[](qbytearray.html)

```
QByteArray QByteArray.__iadd__ (self, QString s)
```

[](qbytearray.html)

```
QByteArray QByteArray.__imul__ (self, int m)
```

[

```
bool QByteArray.__le__ (self, QString s2)
```

```
bool QByteArray.__le__ (self, QByteArray a2)
```

```
 QByteArray.__len__ (self)
```

```
bool QByteArray.__lt__ (self, QString s2)
```

```
bool QByteArray.__lt__ (self, QByteArray a2)
```

](qbytearray.html)

```
QByteArray QByteArray.__mul__ (self, int m)
```

[

```
bool QByteArray.__ne__ (self, QString s2)
```

```
bool QByteArray.__ne__ (self, QByteArray a2)
```

```
str QByteArray.__repr__ (self)
```

```
str QByteArray.__str__ (self)
```

](qbytearray.html)