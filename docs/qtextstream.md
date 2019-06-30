# QTextStream Class Reference

## [[QtCore](index.htm) module]

该QTextStream进行类提供了一个方便的接口，用于读取和写入文字。[More...](#details)

### Types

*   `enum FieldAlignment { AlignLeft, AlignRight, AlignCenter, AlignAccountingStyle }`
*   `enum NumberFlag { ShowBase, ForcePoint, ForceSign, UppercaseBase, UppercaseDigits }`
*   `class **[NumberFlags](index.htm)**`
*   `enum RealNumberNotation { SmartNotation, FixedNotation, ScientificNotation }`
*   `enum Status { Ok, ReadPastEnd, ReadCorruptData, WriteFailed }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QIODevice device)`
*   `__init__ (self, QString string, QIODevice.OpenMode mode = QIODevice.ReadWrite)`
*   `__init__ (self, QByteArray array, QIODevice.OpenMode mode = QIODevice.ReadWrite)`
*   `bool atEnd (self)`
*   `bool autoDetectUnicode (self)`
*   `QTextCodec codec (self)`
*   `QIODevice device (self)`
*   `FieldAlignment fieldAlignment (self)`
*   `int fieldWidth (self)`
*   `flush (self)`
*   `bool generateByteOrderMark (self)`
*   `int integerBase (self)`
*   `QLocale locale (self)`
*   `NumberFlags numberFlags (self)`
*   `QChar padChar (self)`
*   `int pos (self)`
*   `QString read (self, int maxlen)`
*   `QString readAll (self)`
*   `QString readLine (self, int maxLength = 0)`
*   `RealNumberNotation realNumberNotation (self)`
*   `int realNumberPrecision (self)`
*   `reset (self)`
*   `resetStatus (self)`
*   `bool seek (self, int pos)`
*   `setAutoDetectUnicode (self, bool enabled)`
*   `setCodec (self, QTextCodec codec)`
*   `setCodec (self, str codecName)`
*   `setDevice (self, QIODevice device)`
*   `setFieldAlignment (self, FieldAlignment alignment)`
*   `setFieldWidth (self, int width)`
*   `setGenerateByteOrderMark (self, bool generate)`
*   `setIntegerBase (self, int base)`
*   `setLocale (self, QLocale locale)`
*   `setNumberFlags (self, NumberFlags flags)`
*   `setPadChar (self, QChar ch)`
*   `setRealNumberNotation (self, RealNumberNotation notation)`
*   `setRealNumberPrecision (self, int precision)`
*   `setStatus (self, Status status)`
*   `setString (self, QString string, QIODevice.OpenMode mode = QIODevice.ReadWrite)`
*   `skipWhiteSpace (self)`
*   `Status status (self)`
*   `QString string (self)`

### Special Methods

*   `QTextStream __lshift__ (self, QDomNode)`
*   `QTextStream __lshift__ (self, QSplitter)`
*   `QTextStream __rshift__ (self, QSplitter)`
*   `QTextStream __lshift__ (self, float f)`
*   `QTextStream __lshift__ (self, bool b)`
*   `QTextStream __lshift__ (self, int i)`
*   `QTextStream __lshift__ (self, int i)`
*   `QTextStream __lshift__ (self, int i)`
*   `QTextStream __lshift__ (self, QString s)`
*   `QTextStream __lshift__ (self, QByteArray array)`
*   `QTextStream __lshift__ (self, QTextStreamManipulator m)`
*   `QTextStream __rshift__ (self, QChar ch)`
*   `QTextStream __rshift__ (self, QString s)`
*   `QTextStream __rshift__ (self, QByteArray array)`

* * *

## Detailed Description

该QTextStream进行类提供了一个方便的接口，用于读取和写入文字。

QTextStream进行可以在一个操作[QIODevice](qiodevice.html)，一[QByteArray](qbytearray.html)或[QString](qstring.html)。使用QTextStream进行的流媒体运营商，你可以方便地读取和写入文字，线条和数字。对于生成文本， QTextStream进行支持领域填充和对齐和数字的格式格式化选项。例如：

```
 [QFile](qfile.html) data("output.txt");
 if (data.open([QFile](qfile.html).WriteOnly | [QFile](qfile.html).Truncate)) {
     QTextStream out(&data);
     out << "Result: " << qSetFieldWidth(10) << left << 3.14 << 2.7;
     // writes "Result: 3.14      2.7       "
 }

```

这也是通常使用QTextStream来读取控制台输入，写控制台输出。 QTextStream进行的是语言环境感知，并使用正确的编解码器会自动解码标准输入。例如：

```
 QTextStream stream(stdin);
 [QString](qstring.html) line;
 do {
     line = stream.readLine();
 } while (!line.isNull());

```

除了使用QTextStream进行的构造函数，您还可以设置该设备或字符串QTextStream进行操作的调用[setDevice](qtextstream.html#setDevice)（）或[setString](qtextstream.html#setString)（ ） 。你可以通过调用争取到一个位置[seek](qtextstream.html#seek)（）和[atEnd](qtextstream.html#atEnd)（）返回真时，有没有的待读出的数据。如果你打电话[flush](index.htm#flush)（ ） ， QTextStream进行将清空其写入缓冲区中的所有数据到设备，并调用[flush](index.htm#flush)（）在设备上。

在内部， QTextStream进行使用一个基于Unicode的缓冲区，[QTextCodec](qtextcodec.html)是使用QTextStream来自动支持不同的字符集。默认情况下，[QTextCodec.codecForLocale](qtextcodec.html#codecForLocale)（ ）用于读取和写入，但你也可以通过调用设定的编解码器[setCodec](qtextstream.html#setCodec)（ ） 。也支持自动检测Unicode的。当此功能被启用（默认行为） ， QTextStream进行将检测UTF- 16或UTF -32 BOM（字节顺序标记） ，在读取时切换到相应的UTF编码解码器。 QTextStream进行默认不写一个BOM ，但是你可以通过调用setGenerateByteOrderMark （真）启用此。当QTextStream进行运行在一个[QString](qstring.html)直接，编解码器被禁用。

有读取文本文件时使用QTextStream进行三种一般方法：

*   Chunk by chunk, by calling [readLine](qtextstream.html#readLine)() or [readAll](qtextstream.html#readAll)().
*   Word by word. QTextStream supports streaming into QStrings, QByteArrays and char* buffers. Words are delimited by space, and leading white space is automatically skipped.
*   Character by character, by streaming into [QChar](qchar.html) or char types. This method is often used for convenient input handling when parsing files, independent of character encoding and end-of-line semantics. To skip white space, call [skipWhiteSpace](qtextstream.html#skipWhiteSpace)().

由于文本流使用的缓冲区，你不应该使用一个超类的实现流中读取。举例来说，如果你有一个[QFile](qfile.html)并从中直接读取使用[QFile.readLine](qiodevice.html#readLine)代替）使用流（ ，文本流的内部位置会出与该文件的位置同步。

默认情况下，从文本流中读取数字时， QTextStream进行会自动检测数字的基来表示。例如，如果该号码以“0x”启动时，它被假定为在十六进制形式。如果它与数字1-9启动时，它被假定为以十进制形式，等等。您可以设置整数基地，从而禁用自动检测，通过调用[setIntegerBase](qtextstream.html#setIntegerBase)（ ） 。例如：

```
 QTextStream in("0x50 0x20");
 int firstNumber, secondNumber;

 in >> firstNumber;             // firstNumber == 80
 in >> dec >> secondNumber;     // secondNumber == 0

 char ch;
 in >> ch;                      // ch == 'x'

```

QTextStream进行支持，用于生成文本的许多格式选项。你可以通过调用设置字段宽度和填充字符[setFieldWidth](qtextstream.html#setFieldWidth)（）和[setPadChar](qtextstream.html#setPadChar)（ ） 。使用[setFieldAlignment](qtextstream.html#setFieldAlignment)（ ）在每个字段内设置的对齐方式。对于实数，请致电[setRealNumberNotation](qtextstream.html#setRealNumberNotation)（）和[setRealNumberPrecision](qtextstream.html#setRealNumberPrecision)（ ）来设置符号（[SmartNotation](qtextstream.html#RealNumberNotation-enum)，[ScientificNotation](qtextstream.html#RealNumberNotation-enum)，[FixedNotation](qtextstream.html#RealNumberNotation-enum)）和精度在生成的数字的位数。一些额外的数字格式选项也可通过[setNumberFlags](qtextstream.html#setNumberFlags)（ ） 。

喜欢`&lt;iostream&gt;`在标准C + +库， QTextStream进行还定义了几个全球机械手功能：

| Manipulator | Description |
| --- | --- |
| `bin` | Same as setIntegerBase(2). |
| `oct` | Same as setIntegerBase(8). |
| `dec` | Same as setIntegerBase(10). |
| `hex` | Same as setIntegerBase(16). |
| `showbase` | Same as setNumberFlags([numberFlags](qtextstream.html#numberFlags)() &#124; [ShowBase](qtextstream.html#NumberFlag-enum)). |
| `forcesign` | Same as setNumberFlags([numberFlags](qtextstream.html#numberFlags)() &#124; [ForceSign](qtextstream.html#NumberFlag-enum)). |
| `forcepoint` | Same as setNumberFlags([numberFlags](qtextstream.html#numberFlags)() &#124; [ForcePoint](qtextstream.html#NumberFlag-enum)). |
| `noshowbase` | Same as setNumberFlags([numberFlags](qtextstream.html#numberFlags)() & ~[ShowBase](qtextstream.html#NumberFlag-enum)). |
| `noforcesign` | Same as setNumberFlags([numberFlags](qtextstream.html#numberFlags)() & ~[ForceSign](qtextstream.html#NumberFlag-enum)). |
| `noforcepoint` | Same as setNumberFlags([numberFlags](qtextstream.html#numberFlags)() & ~[ForcePoint](qtextstream.html#NumberFlag-enum)). |
| `uppercasebase` | Same as setNumberFlags([numberFlags](qtextstream.html#numberFlags)() &#124; [UppercaseBase](qtextstream.html#NumberFlag-enum)). |
| `uppercasedigits` | Same as setNumberFlags([numberFlags](qtextstream.html#numberFlags)() &#124; [UppercaseDigits](qtextstream.html#NumberFlag-enum)). |
| `lowercasebase` | Same as setNumberFlags([numberFlags](qtextstream.html#numberFlags)() & ~[UppercaseBase](qtextstream.html#NumberFlag-enum)). |
| `lowercasedigits` | Same as setNumberFlags([numberFlags](qtextstream.html#numberFlags)() & ~[UppercaseDigits](qtextstream.html#NumberFlag-enum)). |
| `fixed` | Same as setRealNumberNotation([FixedNotation](qtextstream.html#RealNumberNotation-enum)). |
| `scientific` | Same as setRealNumberNotation([ScientificNotation](qtextstream.html#RealNumberNotation-enum)). |
| `left` | Same as setFieldAlignment([AlignLeft](qtextstream.html#FieldAlignment-enum)). |
| `right` | Same as setFieldAlignment([AlignRight](qtextstream.html#FieldAlignment-enum)). |
| `center` | Same as setFieldAlignment([AlignCenter](qtextstream.html#FieldAlignment-enum)). |
| `endl` | Same as operator&lt;&lt;('\n') and [flush](index.htm#flush)(). |
| `flush` | Same as [flush](index.htm#flush)(). |
| `reset` | Same as [reset](index.htm#reset)(). |
| `ws` | Same as [skipWhiteSpace](qtextstream.html#skipWhiteSpace)(). |
| `bom` | Same as setGenerateByteOrderMark(true). |

此外， Qt提供了带一个参数三个全球机械手：[qSetFieldWidth](index.htm#qSetFieldWidth)（ ）[qSetPadChar](index.htm#qSetPadChar)（）和[qSetRealNumberPrecision](index.htm#qSetRealNumberPrecision)（ ） 。

* * *

## Type Documentation

```
QTextStream.FieldAlignment
```

此枚举指定如何对齐文本字段中时，现场比它佔用的文字更广泛。

| Constant | Value | Description |
| --- | --- | --- |
| `QTextStream.AlignLeft` | `0` | 垫在右侧的字段。 |
| `QTextStream.AlignRight` | `1` | 垫场的左侧。 |
| `QTextStream.AlignCenter` | `2` | 焊盘上字段的两侧。 |
| `QTextStream.AlignAccountingStyle` | `3` | 同AlignRight ，除了数字的标志是左对齐。 |

**See also** [setFieldAlignment](qtextstream.html#setFieldAlignment)（ ） 。

```
QTextStream.NumberFlag
```

该枚举指定可以设置为影响整数的输出各种标志，`float`s和`double`秒。

| Constant | Value | Description |
| --- | --- | --- |
| `QTextStream.ShowBase` | `0x1` | 示的基作为前缀，如果该碱是16 （的“0x ” ），8（ “0”） ，或2（“ 0b”时） 。 |
| `QTextStream.ForcePoint` | `0x2` | 始终把小数点分隔符的数字，即使没有小数。 |
| `QTextStream.ForceSign` | `0x4` | 始终把符号在数量上，即使是正数。 |
| `QTextStream.UppercaseBase` | `0x8` | 使用基地的前缀（ “0X” ， “ 0B ” ）的大写版本。 |
| `QTextStream.UppercaseDigits` | `0x10` | 使用大写字母表示数字10 ，而不是小写35 。 |

该NumberFlags类型是一个typedef为[QFlags](index.htm)\u003cNumberFlag\u003e 。它存储NumberFlag值的或组合。

**See also** [setNumberFlags](qtextstream.html#setNumberFlags)（ ） 。

```
QTextStream.RealNumberNotation
```

这个枚举指定用于表达的符号`float`和`double`为字符串。

| Constant | Value | Description |
| --- | --- | --- |
| `QTextStream.ScientificNotation` | `2` | 科学记数法（`printf()`的`%e`标志） 。 |
| `QTextStream.FixedNotation` | `1` | 定点表示法（`printf()`的`%f`标志） 。 |
| `QTextStream.SmartNotation` | `0` | 科学或定点表示法，这取决于哪个最有意义（`printf()`的`%g`标志） 。 |

**See also** [setRealNumberNotation](qtextstream.html#setRealNumberNotation)（ ） 。

```
QTextStream.Status
```

这个枚举变量描述了文本流的当前状态。

| Constant | Value | Description |
| --- | --- | --- |
| `QTextStream.Ok` | `0` | 文本流运行正常。 |
| `QTextStream.ReadPastEnd` | `1` | 文本流已经读取过的底层设备中的数据的结尾。 |
| `QTextStream.ReadCorruptData` | `2` | 文本流已经阅读损坏的数据。 |
| `QTextStream.WriteFailed` | `3` | 文本流不能写入到基础设备。 |

**See also** [status](qtextstream.html#status)（ ） 。

* * *

## Method Documentation

```
QTextStream.__init__ (self)
```

构造一个[QTextStream](qtextstream.html)。之前，你可以用它来读取或写入时，必须指定一个设备或一个字符串。

**See also** [setDevice](qtextstream.html#setDevice)（）和[setString](qtextstream.html#setString)（ ） 。

```
QTextStream.__init__ (self, QIODevice device)
```

构造一个[QTextStream](qtextstream.html)上操作_device_。

```
QTextStream.__init__ (self, QString string, QIODevice.OpenMode mode = QIODevice.ReadWrite)
```

构造一个[QTextStream](qtextstream.html)上操作_fileHandle_，使用_openMode_以限定开放模式。在内部，[QFile](qfile.html)创建处理文件指针。

这个构造函数是直接与普通基于文件的输入和输出流时非常有用：标准输入，标准输出和标准错误。例如：

```
 [QString](qstring.html) str;
 [QTextStream](qtextstream.html) in(stdin);
 in >> str;

```

```
QTextStream.__init__ (self, QByteArray array, QIODevice.OpenMode mode = QIODevice.ReadWrite)
```

构造一个[QTextStream](qtextstream.html)上操作_string_，使用_openMode_以限定开放模式。

```
bool QTextStream.atEnd (self)
```

返回True ，如果没有更多的数据被从读[QTextStream](qtextstream.html)否则返回False 。这是类似的，但不一样的呼叫[QIODevice.atEnd](qiodevice.html#atEnd)（ ） ，如[QTextStream](qtextstream.html)也考虑到其内部的Unicode缓冲区。

```
bool QTextStream.autoDetectUnicode (self)
```

返回True如果启用了自动统一检测，否则返回False 。 Unicode的自动检测是默认启用的。

**See also** [setAutoDetectUnicode](qtextstream.html#setAutoDetectUnicode)（）和[setCodec](qtextstream.html#setCodec)（ ） 。

```
QTextCodec QTextStream.codec (self)
```

[

返回是当前分配给该流的编解码器。

](qtextcodec.html)

[**See also**](qtextcodec.html) [setCodec](qtextstream.html#setCodec)（ ）[setAutoDetectUnicode](qtextstream.html#setAutoDetectUnicode)（）和[locale](qtextstream.html#locale)（ ） 。

```
QIODevice QTextStream.device (self)
```

[](qiodevice.html)

[返回与关联的当前设备](qiodevice.html)[QTextStream](qtextstream.html)，或者0，如果没有设备已经被分配。

**See also** [setDevice](qtextstream.html#setDevice)（）和[string](qtextstream.html#string)（ ） 。

```
FieldAlignment QTextStream.fieldAlignment (self)
```

[

返回当前字段对齐。

](qtextstream.html#FieldAlignment-enum)

[**See also**](qtextstream.html#FieldAlignment-enum) [setFieldAlignment](qtextstream.html#setFieldAlignment)（）和[fieldWidth](qtextstream.html#fieldWidth)（ ） 。

```
int QTextStream.fieldWidth (self)
```

返回当前字段宽度。

**See also** [setFieldWidth](qtextstream.html#setFieldWidth)（ ） 。

```
QTextStream.flush (self)
```

刷新所有缓冲的数据等待被写入设备。

If [QTextStream](qtextstream.html)运行在一个字符串，这个函数不执行任何操作。

```
bool QTextStream.generateByteOrderMark (self)
```

返回True如果[QTextStream](qtextstream.html)设置使用UTF编码解码器时产生的UTF BOM（字节顺序标记），否则返回False 。 UTF BOM生成的默认设置为False 。

**See also** [setGenerateByteOrderMark](qtextstream.html#setGenerateByteOrderMark)（ ） 。

```
int QTextStream.integerBase (self)
```

返回整数的电流基础。 0表示当读出，或10 （十进制）生成数字时检测到的基极。

**See also** [setIntegerBase](qtextstream.html#setIntegerBase)（ ）[QString.number](qstring.html#number)（）和[numberFlags](qtextstream.html#numberFlags)（ ） 。

```
QLocale QTextStream.locale (self)
```

[

返回locale为这个流。默认的语言环境是C。

此功能被引入Qt的4.5 。

](qlocale.html)

[**See also**](qlocale.html) [setLocale](qtextstream.html#setLocale)（ ） 。

```
NumberFlags QTextStream.numberFlags (self)
```

[

返回当前数字标志。

](index.htm)

[**See also**](index.htm) [setNumberFlags](qtextstream.html#setNumberFlags)（ ）[integerBase](qtextstream.html#integerBase)（）和[realNumberNotation](qtextstream.html#realNumberNotation)（ ） 。

```
QChar QTextStream.padChar (self)
```

返回当前的填充字符。

**See also** [setPadChar](qtextstream.html#setPadChar)（）和[setFieldWidth](qtextstream.html#setFieldWidth)（ ） 。

```
int QTextStream.pos (self)
```

返回对应于流的当前位置，设备位置，或-1，如果出现错误（例如，如果没有设备或字符串，或者如果有一个设备错误） 。

因为[QTextStream](qtextstream.html)缓冲，该功能可能会寻求设备重建一个有效的设备位置。此操作可以是昂贵的，所以你可能要避免调用在紧密循环此功能。

这个函数中引入了Qt 4.2中。

**See also** [seek](qtextstream.html#seek)（ ） 。

```
QString QTextStream.read (self, int maxlen)
```

阅读次数最多_maxlen_从流中的字符，并返回读取的数据[QString](qstring.html)。

这个函数是Qt 4.1中引入。

**See also** [readAll](qtextstream.html#readAll)（ ）[readLine](qtextstream.html#readLine)（）和[QIODevice.read](qiodevice.html#read)（ ） 。

```
QString QTextStream.readAll (self)
```

读取流的全部内容，并将其作为一个[QString](qstring.html)。对大型文件时，为了避免这个功能，因为它会消耗显着的内存量。

调用[readLine](qtextstream.html#readLine)（ ）是更好，如果你不知道有多少数据是可用的。

**See also** [readLine](qtextstream.html#readLine)（ ） 。

```
QString QTextStream.readLine (self, int maxLength = 0)
```

读取一行从流文本，并将其作为一个[QString](qstring.html)。允许的最大行长度被设置为_maxlen_。如果流包含线比这更长的时间，那么行会被拆分后，_maxlen_字符和部件退回。

If _maxlen_为0时，线可以是任意长度的。为了一个共同的价值_maxlen_为75。

返回行有行尾没有尾随字符（“ \ n”或“ \ r \ N”的） ，因此调用[QString.trimmed](qstring.html#trimmed)（）是不必要的。

如果该流已读入到文件的末尾，的readLine （）将返回一个空[QString](qstring.html)。对于字符串，或者为支持它的设备，你可以明确地使用了流的末尾测试[atEnd](qtextstream.html#atEnd)（ ） 。

**See also** [readAll](qtextstream.html#readAll)（）和[QIODevice.readLine](qiodevice.html#readLine)（ ） 。

```
RealNumberNotation QTextStream.realNumberNotation (self)
```

[

返回当前的实数表示法。

](qtextstream.html#RealNumberNotation-enum)

[**See also**](qtextstream.html#RealNumberNotation-enum) [setRealNumberNotation](qtextstream.html#setRealNumberNotation)（ ）[realNumberPrecision](qtextstream.html#realNumberPrecision)（ ）[numberFlags](qtextstream.html#numberFlags)（）和[integerBase](qtextstream.html#integerBase)（ ） 。

```
int QTextStream.realNumberPrecision (self)
```

返回当前的实数精度或小数位数的数字[QTextStream](qtextstream.html)生成实数时会写。

**See also** [setRealNumberPrecision](qtextstream.html#setRealNumberPrecision)（ ）[setRealNumberNotation](qtextstream.html#setRealNumberNotation)（ ）[realNumberNotation](qtextstream.html#realNumberNotation)（ ）[numberFlags](qtextstream.html#numberFlags)（）和[integerBase](qtextstream.html#integerBase)（ ） 。

```
QTextStream.reset (self)
```

复位[QTextStream](qtextstream.html)的格式选项，把它恢复到原来的构造状态。该装置，字符串和任何缓冲的数据保持不变。

```
QTextStream.resetStatus (self)
```

重设文本流的状态。

这个函数是Qt 4.1中引入。

**See also** [QTextStream.Status](qtextstream.html#Status-enum)，[status](qtextstream.html#status)（）和[setStatus](qtextstream.html#setStatus)（ ） 。

```
bool QTextStream.seek (self, int pos)
```

搜索到的位置_pos_在设备中。成功时返回TRUE ，否则返回False 。

```
QTextStream.setAutoDetectUnicode (self, bool enabled)
```

If _enabled_是真的，[QTextStream](qtextstream.html)将尝试检测Unicode编码通过窥视到的流数据，看看是否能找到的UTF -16或UTF- 32 BOM（字节顺序标记） 。如果发现该标志，[QTextStream](qtextstream.html)将与UTF编解码器替换当前的编解码器。

这个功能可以一起使用[setCodec](qtextstream.html#setCodec)（ ） 。这是常见的编解码器设置为UTF- 8 ，然后启用UTF-16的检测。

**See also** [autoDetectUnicode](qtextstream.html#autoDetectUnicode)（）和[setCodec](qtextstream.html#setCodec)（ ） 。

```
QTextStream.setCodec (self, QTextCodec codec)
```

设置编解码器，该流_codec_。编解码器，用于解码所读取的分配装置，和用于编码被写入任何数据的任何数据。默认情况下，[QTextCodec.codecForLocale](qtextcodec.html#codecForLocale)（）被使用，并且被使能自动unicode的检测。

If [QTextStream](qtextstream.html)运行在一个字符串，这个函数不执行任何操作。

**Warning:**如果你调用这个函数而文本流从打开的顺序socket读取，内部缓冲区可能仍然包含使用旧文本的编解码器解码。

**See also** [codec](qtextstream.html#codec)（ ）[setAutoDetectUnicode](qtextstream.html#setAutoDetectUnicode)（）和[setLocale](qtextstream.html#setLocale)（ ） 。

```
QTextStream.setCodec (self, str codecName)
```

设置编解码器，该数据流的[QTextCodec](qtextcodec.html)对于由指定的编码_codecName_。为共同的价值观`codecName`包括“ ISO 8859 ”，“ UTF-8” ，和“UTF- 16” 。如果编码不被识别，没有任何反应。

例如：

```
 [QTextStream](qtextstream.html) out(&file);
 out.setCodec("UTF-8");

```

**See also** [QTextCodec.codecForName](qtextcodec.html#codecForName)（）和[setLocale](qtextstream.html#setLocale)（ ） 。

```
QTextStream.setDevice (self, QIODevice device)
```

设置当前设备_device_。如果设备已经被分配，[QTextStream](qtextstream.html)将调用[flush](index.htm#flush)（ ）旧设备被替换之前。

**Note:**此功能将区域设置为默认语言环境（' C'）和编解码器为默认的编解码器，[QTextCodec.codecForLocale](qtextcodec.html#codecForLocale)（ ） 。

**See also** [device](qtextstream.html#device)（）和[setString](qtextstream.html#setString)（ ） 。

```
QTextStream.setFieldAlignment (self, FieldAlignment alignment)
```

设置字段对齐到_mode_。当一起使用[setFieldWidth](qtextstream.html#setFieldWidth)（ ） ，这个函数允许您生成格式化输出文本左对齐，对齐到右边或中间。

**See also** [fieldAlignment](qtextstream.html#fieldAlignment)（）和[setFieldWidth](qtextstream.html#setFieldWidth)（ ） 。

```
QTextStream.setFieldWidth (self, int width)
```

设置当前字段宽度为_width_。如果_width_为0 （默认值） ，字段宽度等于生成的文本的长度。

**Note:**字段宽度适用于这个函数被调用（例如，它也垫ENDL ）后追加到该流的每一个元素。此行为是由相似的类在STL ，那里的字段宽度仅适用于下一个元素不同。

**See also** [fieldWidth](qtextstream.html#fieldWidth)（）和[setPadChar](qtextstream.html#setPadChar)（ ） 。

```
QTextStream.setGenerateByteOrderMark (self, bool generate)
```

If _generate_是真实，一个UTF编码解码器时，[QTextStream](qtextstream.html)将插入BOM（字节顺序标记）之前的任何数据被写入到设备。如果_generate_是假的，没有BOM将被插入。任何数据写入之前，这个函数必须被调用。否则，它什么都不做。

**See also** [generateByteOrderMark](qtextstream.html#generateByteOrderMark)（）和[bom](index.htm#bom)（ ） 。

```
QTextStream.setIntegerBase (self, int base)
```

整数的基本设置为_base_，既用于读和用于产生数字。_base_可以是2 （二进制）， 8 （八进制） ， 10（十进制）或16（十六进制）。如果_base_为0时，[QTextStream](qtextstream.html)将试图通过检查流上的数据来检测的基础。当生成的数字，[QTextStream](qtextstream.html)假设基准是10 ，除非该基地已显式设置。

**See also** [integerBase](qtextstream.html#integerBase)（ ）[QString.number](qstring.html#number)（）和[setNumberFlags](qtextstream.html#setNumberFlags)（ ） 。

```
QTextStream.setLocale (self, QLocale locale)
```

设置语言环境为这个流_locale_。指定的语言环境是用于数字和它们的字符串表示形式之间的转换。

默认区域设置为C ，它是一种特殊情况 - 在成千上万的组分隔符不能用于向后兼容的原因。

此功能被引入Qt的4.5 。

**See also** [locale](qtextstream.html#locale)（ ） 。

```
QTextStream.setNumberFlags (self, NumberFlags flags)
```

设置当前数字标志_flags_。_flags_是从一组标志[NumberFlag](qtextstream.html#NumberFlag-enum)枚举，并介绍了用于格式化生成的代码（例如，是否总是写一些基地或符号）选项。

**See also** [numberFlags](qtextstream.html#numberFlags)（ ）[setIntegerBase](qtextstream.html#setIntegerBase)（）和[setRealNumberNotation](qtextstream.html#setRealNumberNotation)（ ） 。

```
QTextStream.setPadChar (self, QChar ch)
```

设置填充字符以_ch_。默认值是ASCII空格字符（' '） ，或[QChar](qchar.html)（ 0X20 ） 。此符号用于生成文本时填写的空间领域。

例如：

```
 [QString](qstring.html) s;
 [QTextStream](qtextstream.html) out(&s);
 out.setFieldWidth(10);
 out.setFieldAlignment([QTextStream](qtextstream.html).AlignCenter);
 out.setPadChar('-');
 out << "Qt" << "rocks!";

```

字符串`s`包含：

```
 ----[Qt](qt.html)------rocks!--

```

**See also** [padChar](qtextstream.html#padChar)（）和[setFieldWidth](qtextstream.html#setFieldWidth)（ ） 。

```
QTextStream.setRealNumberNotation (self, RealNumberNotation notation)
```

设置实数表示法_notation_（[SmartNotation](qtextstream.html#RealNumberNotation-enum)，[FixedNotation](qtextstream.html#RealNumberNotation-enum)，[ScientificNotation](qtextstream.html#RealNumberNotation-enum)） 。当读取和生成数字，[QTextStream](qtextstream.html)使用这个值来检测实数的格式。

**See also** [realNumberNotation](qtextstream.html#realNumberNotation)（ ）[setRealNumberPrecision](qtextstream.html#setRealNumberPrecision)（ ）[setNumberFlags](qtextstream.html#setNumberFlags)（）和[setIntegerBase](qtextstream.html#setIntegerBase)（ ） 。

```
QTextStream.setRealNumberPrecision (self, int precision)
```

设置实数的精度来_precision_。这个值描述的部分位数[QTextStream](qtextstream.html)生成实数时，应该写。

精度不能是负值。默认值是6 。

**See also** [realNumberPrecision](qtextstream.html#realNumberPrecision)（）和[setRealNumberNotation](qtextstream.html#setRealNumberNotation)（ ） 。

```
QTextStream.setStatus (self, Status status)
```

设置文本流的状态的_status_给出。

后续调用setStatus （）被忽略，直到[resetStatus](qtextstream.html#resetStatus)（）被调用。

这个函数是Qt 4.1中引入。

**See also** [Status](qtextstream.html#Status-enum)，[status](qtextstream.html#status)（）和[resetStatus](qtextstream.html#resetStatus)（ ） 。

```
QTextStream.setString (self, QString string, QIODevice.OpenMode mode = QIODevice.ReadWrite)
```

设置当前字符串_string_，使用给定的_openMode_。如果设备已经被分配，[QTextStream](qtextstream.html)将调用[flush](index.htm#flush)（ ）替换它。

**See also** [string](qtextstream.html#string)（）和[setDevice](qtextstream.html#setDevice)（ ） 。

```
QTextStream.skipWhiteSpace (self)
```

读取并丢弃空白从流，直到一个非空格字符被检测到，或直到[atEnd](qtextstream.html#atEnd)（ ）返回True 。按字符读取字符流时，此功能非常有用。

空白字符都是字符的[QChar.isSpace](qchar.html#isSpace)（ ）返回True 。

**See also** [operator&gt;&gt;](qtextstream.html#operator-gt-gt)（ ） 。

```
Status QTextStream.status (self)
```

[

返回文本流的状态。

](qtextstream.html#Status-enum)

[**See also**](qtextstream.html#Status-enum) [QTextStream.Status](qtextstream.html#Status-enum)，[setStatus](qtextstream.html#setStatus)（）和[resetStatus](qtextstream.html#resetStatus)（ ） 。

```
QString QTextStream.string (self)
```

返回分配给当前字符串[QTextStream](qtextstream.html)，或者0，如果没有字符串被分配。

**See also** [setString](qtextstream.html#setString)（）和[device](qtextstream.html#device)（ ） 。

```
QTextStream __lshift__ (self, QDomNode)
```

[

如果QtXml模块导入此方法仅适用。

](qtextstream.html)

```
QTextStream __lshift__ (self, QSplitter)
```

[

如果QtGui模块导入此方法仅适用。

](qtextstream.html)

```
QTextStream __rshift__ (self, QSplitter)
```

[

如果QtGui模块导入此方法仅适用。

](qtextstream.html)

```
QTextStream QTextStream.__lshift__ (self, float f)
```

[](qtextstream.html)

```
QTextStream QTextStream.__lshift__ (self, bool b)
```

[](qtextstream.html)

```
QTextStream QTextStream.__lshift__ (self, int i)
```

[](qtextstream.html)

```
QTextStream QTextStream.__lshift__ (self, int i)
```

[](qtextstream.html)

```
QTextStream QTextStream.__lshift__ (self, int i)
```

[](qtextstream.html)

```
QTextStream QTextStream.__lshift__ (self, QString s)
```

[](qtextstream.html)

```
QTextStream QTextStream.__lshift__ (self, QByteArray array)
```

[](qtextstream.html)

```
QTextStream QTextStream.__lshift__ (self, QTextStreamManipulator m)
```

[](qtextstream.html)

```
QTextStream QTextStream.__rshift__ (self, QChar ch)
```

[](qtextstream.html)

```
QTextStream QTextStream.__rshift__ (self, QString s)
```

[](qtextstream.html)

```
QTextStream QTextStream.__rshift__ (self, QByteArray array)
```

[](qtextstream.html)