# QTextCodec Class Reference

## [[QtCore](index.htm) module]

该持QTextCodec类提供文本编码之间的转换。[More...](#details)

### Types

*   `enum ConversionFlag { DefaultConversion, ConvertInvalidToNull, IgnoreHeader }`
*   `class **[ConversionFlags](index.htm)**`
*   `class **[ConverterState](index.htm)**`

### Methods

*   `__init__ (self)`
*   `list-of-QByteArray aliases (self)`
*   `bool canEncode (self, QString)`
*   `QString convertToUnicode (self, str in, ConverterState state)`
*   `QByteArray fromUnicode (self, QString uc)`
*   `QTextDecoder makeDecoder (self)`
*   `QTextDecoder makeDecoder (self, ConversionFlags flags)`
*   `QTextEncoder makeEncoder (self)`
*   `QTextEncoder makeEncoder (self, ConversionFlags flags)`
*   `int mibEnum (self)`
*   `QByteArray name (self)`
*   `QString toUnicode (self, QByteArray)`
*   `QString toUnicode (self, str chars)`
*   `QString toUnicode (self, str in, ConverterState state = None)`

### Static Methods

*   `list-of-QByteArray availableCodecs ()`
*   `list-of-int availableMibs ()`
*   `QTextCodec codecForCStrings ()`
*   `QTextCodec codecForHtml (QByteArray ba)`
*   `QTextCodec codecForHtml (QByteArray ba, QTextCodec defaultCodec)`
*   `QTextCodec codecForLocale ()`
*   `QTextCodec codecForMib (int mib)`
*   `QTextCodec codecForName (QByteArray name)`
*   `QTextCodec codecForName (str name)`
*   `QTextCodec codecForTr ()`
*   `QTextCodec codecForUtfText (QByteArray ba)`
*   `QTextCodec codecForUtfText (QByteArray ba, QTextCodec defaultCodec)`
*   `setCodecForCStrings (QTextCodec c)`
*   `setCodecForLocale (QTextCodec c)`
*   `setCodecForTr (QTextCodec c)`

* * *

## Detailed Description

该持QTextCodec类提供文本编码之间的转换。

Qt使用Unicode来存储，绘制和操作字符串。在许多情况下，您可能希望处理使用不同的编码数据。例如，大多数日本人的文件仍然存储在按住Shift JIS或ISO 2022-JP ，而俄罗斯用户往往有他们的KOI8-R或Windows - 1251文档。

Qt提供了一系列QTextCodec来控制班，以帮助将非Unicode格式与Unicode的。您也可以创建自己的编解码器类。

支持的编码有：

*   Apple Roman
*   [Big5](index.htm)
*   [Big5-HKSCS](index.htm)
*   CP949
*   [EUC-JP](index.htm)
*   [EUC-KR](index.htm)
*   [GB18030-0](index.htm)
*   IBM 850
*   IBM 866
*   IBM 874
*   [ISO 2022-JP](index.htm)
*   ISO 8859-1 to 10
*   ISO 8859-13 to 16
*   Iscii-Bng, Dev, Gjr, Knd, Mlm, Ori, Pnj, Tlg, and Tml
*   JIS X 0201
*   JIS X 0208
*   KOI8-R
*   KOI8-U
*   MuleLao-1
*   ROMAN8
*   [Shift-JIS](index.htm)
*   TIS-620
*   [TSCII](index.htm)
*   UTF-8
*   UTF-16
*   UTF-16BE
*   UTF-16LE
*   UTF-32
*   UTF-32BE
*   UTF-32LE
*   Windows-1250 to 1258
*   WINSAMI2

QTextCodecs可以用如下的一些本地编码的字符串转换为Unicode 。假设你有一些字符串编码在俄罗斯KOI8-R编码，并希望将其转换为Unicode 。最简单的方法来做到这一点是这样的：

```
 [QByteArray](qbytearray.html) encodedString = "...";
 QTextCodec *codec = QTextCodec.codecForName("KOI8-R");
 [QString](qstring.html) string = codec->toUnicode(encodedString);

```

在此之后，`string`保存文本转换为Unicode 。从Unicode转换一个字符串到本地编码是一样简单：

```
 [QString](qstring.html) string = "...";
 QTextCodec *codec = QTextCodec.codecForName("KOI8-R");
 [QByteArray](qbytearray.html) encodedString = codec->fromUnicode(string);

```

要读取或写入的文件在各种编码，使用[QTextStream](qtextstream.html)其[setCodec()](qtextstream.html#setCodec)功能。请参阅[Codecs](index.htm)例如对于QTextCodec来控制的应用程序文件I / O。

尝试将数据通过网络接收它时，在转换块，例如，当一些必须小心。在这种情况下，它可能是一个多字节字符将被分割在两个块。在最好的，这可能导致一个字符的损失和在最坏的情况导致整个转换失败。

在这些情况下使用的方法是创建一个[QTextDecoder](qtextdecoder.html)对象为编解码器和使用该[QTextDecoder](qtextdecoder.html)整个解码过程，如下所示：

```
 QTextCodec *codec = QTextCodec.codecForName("Shift-JIS");
 [QTextDecoder](qtextdecoder.html) *decoder = codec->makeDecoder();

 [QString](qstring.html) string;
 while (new_data_available()) {
     [QByteArray](qbytearray.html) chunk = get_new_data();
     string += decoder->toUnicode(chunk);
 }
 delete decoder;

```

该[QTextDecoder](qtextdecoder.html)对象维护块之间的状态，因此可以正常工作，即使多字节字符分割块之间。

### Creating Your Own Codec Class

支持新的文本编码可以通过创建子类QTextCodec来控制被加入到Qt的。

该纯虚函数描述编码器系统和编码器被用作需要在所支持的不同的文本文件格式[QTextStream](qtextstream.html)和X11下，为区域设置特定的字符输入和输出。

要添加另一个编码支持Qt的，请QTextCodec来控制的一个子类，并实现下表中列出的功能。

| Function | Description |
| --- | --- |
| [name](qtextcodec.html#name)() | Returns the official name for the encoding. If the encoding is listed in the [IANA character-sets encoding file](http://www.iana.org/assignments/character-sets), the name should be the preferred MIME name for the encoding. |
| [aliases](qtextcodec.html#aliases)() | Returns a list of alternative names for the encoding. QTextCodec provides a default implementation that returns an empty list. For example, "ISO-8859-1" has "latin1", "CP819", "IBM819", and "iso-ir-100" as aliases. |
| [mibEnum](qtextcodec.html#mibEnum)() | Return the MIB enum for the encoding if it is listed in the [IANA character-sets encoding file](http://www.iana.org/assignments/character-sets). |
| [convertToUnicode](qtextcodec.html#convertToUnicode)() | Converts an 8-bit character string to Unicode. |
| [convertFromUnicode](qtextcodec.html#convertFromUnicode)() | Converts a Unicode string to an 8-bit character string. |

您可能会发现它更方便，让您的编解码器类可以作为一个插件，见[How to Create Qt Plugins](index.htm)了解详情。

* * *

## Type Documentation

```
QTextCodec.ConversionFlag
```

| Constant | Value | Description |
| --- | --- | --- |
| `QTextCodec.DefaultConversion` | `0` | 无标志被设置。 |
| `QTextCodec.ConvertInvalidToNull` | `0x80000000` | 如果设置了这个标志，每个无效输入字符输出为一个空字符。 |
| `QTextCodec.IgnoreHeader` | `0x1` | 忽略任何Unicode字节顺序标记，并且不产生任何。 |

该ConversionFlags类型是一个typedef为[QFlags](index.htm)\u003cConversionFlag\u003e 。它存储ConversionFlag值的或组合。

* * *

## Method Documentation

```
QTextCodec.__init__ (self)
```

构造一个[QTextCodec](qtextcodec.html)，并给它最高的优先级。该[QTextCodec](qtextcodec.html)应始终在堆（即构造`new`） 。 Qt可以拥有和应用程序终止时将其删除。

```
list-of-QByteArray QTextCodec.aliases (self)
```

子类可以返回一个数字的别名有问题的编解码器。

标准别名编解码器可以在被发现[IANA character-sets encoding file](http://www.iana.org/assignments/character-sets)。

```
list-of-QByteArray QTextCodec.availableCodecs ()
```

返回所有可用的编解码器的列表，按名称。通话[QTextCodec.codecForName](qtextcodec.html#codecForName)（ ），得到[QTextCodec](qtextcodec.html)为名称。

该列表可以包含相同的编解码器的许多提到，如果编解码器具有别名。

**See also** [availableMibs](qtextcodec.html#availableMibs)（ ）[name](qtextcodec.html#name)（）和[aliases](qtextcodec.html#aliases)（ ） 。

```
list-of-int QTextCodec.availableMibs ()
```

返回的MIB可用于所有硬件编解码器的列表。通话[QTextCodec.codecForMib](qtextcodec.html#codecForMib)（ ），得到[QTextCodec](qtextcodec.html)对MIB 。

**See also** [availableCodecs](qtextcodec.html#availableCodecs)（）和[mibEnum](qtextcodec.html#mibEnum)（ ） 。

```
bool QTextCodec.canEncode (self, QString)
```

返回True如果Unicode字符_ch_可以使用此编解码器完全编码，否则返回False 。

```
QTextCodec QTextCodec.codecForCStrings ()
```

[](qtextcodec.html)

[返回所使用的编解码器](qtextcodec.html)[QString](qstring.html)转换为和从`const char *`和QByteArrays 。如果这个函数返回0 （默认值） ，[QString](qstring.html)假定的Latin-1 。

**See also** [setCodecForCStrings](qtextcodec.html#setCodecForCStrings)（ ） 。

```
QTextCodec QTextCodec.codecForHtml (QByteArray ba)
```

[](qtextcodec.html)

[尝试检测的HTML给定的字节数组中所提供的代码片段的编码，_ba_通过检查BOM（字节顺序标记）和内容类型的元头，并返回一个](qtextcodec.html)[QTextCodec](qtextcodec.html)例如，它能够将HTML转换为Unicode解码。如果该编解码器不能从所提供的内容检测_defaultCodec_返回。

此功能被引入Qt的4.4 。

**See also** [codecForUtfText](qtextcodec.html#codecForUtfText)（ ） 。

```
QTextCodec QTextCodec.codecForHtml (QByteArray ba, QTextCodec defaultCodec)
```

[

这是一个重载函数。

](qtextcodec.html)

[尝试检测的HTML给定的字节数组中所提供的代码片段的编码，_ba_通过检查BOM（字节顺序标记）和内容类型的元头，并返回一个](qtextcodec.html)[QTextCodec](qtextcodec.html)例如，它能够将HTML转换为Unicode解码。如果编解码器不能被检测到，此重载返回的Latin-1[QTextCodec](qtextcodec.html)。

```
QTextCodec QTextCodec.codecForLocale ()
```

[

返回一个指向该编解码器为这个区域设置最合适。

在Windows上，编解码器将根据系统区域设置。在Unix系统中，开始用Qt 4.2 ，编解码器将使用_iconv_库。请注意，在两种情况下，编解码器的名称将是“系统” 。

](qtextcodec.html)

[**See also**](qtextcodec.html) [setCodecForLocale](qtextcodec.html#setCodecForLocale)（ ） 。

```
QTextCodec QTextCodec.codecForMib (int mib)
```

[](qtextcodec.html)

[返回](qtextcodec.html)[QTextCodec](qtextcodec.html)相匹配的[MIBenum](qtextcodec.html#mibEnum) _mib_。

```
QTextCodec QTextCodec.codecForName (QByteArray name)
```

[](qtextcodec.html)

[搜索所有已安装](qtextcodec.html)[QTextCodec](qtextcodec.html)对象并返回一个最匹配_name_，与之匹配的是不区分大小写的。返回0 ，如果没有匹配的编解码器的名称_name_可以找到。

```
QTextCodec QTextCodec.codecForName (str name)
```

[](qtextcodec.html)

[搜索所有已安装](qtextcodec.html)[QTextCodec](qtextcodec.html)对象并返回一个最匹配_name_，与之匹配的是不区分大小写的。返回0 ，如果没有匹配的编解码器的名称_name_可以找到。

```
QTextCodec QTextCodec.codecForTr ()
```

[](qtextcodec.html)

[返回所使用的编解码器](qtextcodec.html)[QObject.tr](qobject.html#tr)（ ）在其参数。如果这个函数返回0 （默认值） ， TR （）假定的Latin-1 。

**See also** [setCodecForTr](qtextcodec.html#setCodecForTr)（ ） 。

```
QTextCodec QTextCodec.codecForUtfText (QByteArray ba)
```

[](qtextcodec.html)

[尝试检测所提供的代码片段的编码_ba_通过使用BOM（字节顺序标记） ，并返回一个](qtextcodec.html)[QTextCodec](qtextcodec.html)例如，能够将文本转换为Unicode解码。如果该编解码器不能从所提供的内容检测_defaultCodec_返回。

此功能被引入Qt的4.6 。

**See also** [codecForHtml](qtextcodec.html#codecForHtml)（ ） 。

```
QTextCodec QTextCodec.codecForUtfText (QByteArray ba, QTextCodec defaultCodec)
```

[

这是一个重载函数。

](qtextcodec.html)

[尝试检测所提供的代码片段的编码_ba_通过使用BOM（字节顺序标记） ，并返回一个](qtextcodec.html)[QTextCodec](qtextcodec.html)例如，能够将文本转换为Unicode解码。如果编解码器不能被检测到，此重载返回的Latin-1[QTextCodec](qtextcodec.html)。

**See also** [codecForHtml](qtextcodec.html#codecForHtml)（ ） 。

```
QString QTextCodec.convertToUnicode (self, str in, ConverterState state)
```

这种方法是抽象的，应在任何子类中重新实现。

[QTextCodec](qtextcodec.html)子类必须重新实现此功能。

将第一_len_字符_chars_从子类到Unicode的编码，并返回结果的[QString](qstring.html)。

_state_可以是0，在这种情况下的转换是无状态的，因此应该使用默认的转换规则。如果状态不为0 ，编解码器应在转换后保存的状态_state_，并调整remainingChars和结构的invalidChars成员。

```
QByteArray QTextCodec.fromUnicode (self, QString uc)
```

[](qbytearray.html)

[皈依_str_从Unicode到该编解码器的编码，并返回结果的](qbytearray.html)[QByteArray](qbytearray.html)。

```
QTextDecoder QTextCodec.makeDecoder (self)
```

[](qtextdecoder.html)

[创建](qtextdecoder.html)[QTextDecoder](qtextdecoder.html)存储足够的状态来解码的块`char *`数据来创建Unicode数据块。

来电者是负责删除返回的对象。

```
QTextDecoder QTextCodec.makeDecoder (self, ConversionFlags flags)
```

[](qtextdecoder.html)

[创建](qtextdecoder.html)[QTextDecoder](qtextdecoder.html)用指定的_flags_要解码的块`char *`数据来创建Unicode数据块。

来电者是负责删除返回的对象。

此功能被引入Qt的4.7 。

```
QTextEncoder QTextCodec.makeEncoder (self)
```

[](qtextencoder.html)

[创建](qtextencoder.html)[QTextEncoder](qtextencoder.html)存储足够的状态以Unicode数据块编码为`char *`数据。

来电者是负责删除返回的对象。

```
QTextEncoder QTextCodec.makeEncoder (self, ConversionFlags flags)
```

[](qtextencoder.html)

[创建](qtextencoder.html)[QTextEncoder](qtextencoder.html)用指定的_flags_以Unicode数据块编码为`char *`数据。

来电者是负责删除返回的对象。

此功能被引入Qt的4.7 。

```
int QTextCodec.mibEnum (self)
```

这种方法是抽象的，应在任何子类中重新实现。

的子类[QTextCodec](qtextcodec.html)必须重新实现此功能。它返回MIBenum （见[IANA character-sets encoding file](http://www.iana.org/assignments/character-sets)获取更多信息） 。重要的是，每[QTextCodec](qtextcodec.html)子类将返回此函数的正确独特的价值。

```
QByteArray QTextCodec.name (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

](qbytearray.html)

[](qbytearray.html)[QTextCodec](qtextcodec.html)子类必须重新实现此功能。它返回由子类支持的编码的名称。

如果该编解码器被注册为一个字在设置[IANA character-sets encoding file](http://www.iana.org/assignments/character-sets)此方法应为如果定义编解码器返回的首选MIME名称，否则其名称。

```
QTextCodec.setCodecForCStrings (QTextCodec c)
```

设置使用的编解码器[QString](qstring.html)转换为和从`const char *`和QByteArrays 。如果_codec_为0 （默认值） ，[QString](qstring.html)假定的Latin-1 。

**Warning:**一些编解码器不保留在ASCII范围的字符（ 0x00到0x7F ） 。例如，日文Shift- JIS编码的反斜杠字符（为0x5A ）映射到日元的性格。为了避免不良的副作用，我们建议避免这种编解码器与setCodecsForCString （ ） 。

**Warning:**此功能不[reentrant](index.htm#reentrant)。

**See also** [codecForCStrings](qtextcodec.html#codecForCStrings)（）和[setCodecForTr](qtextcodec.html#setCodecForTr)（ ） 。

```
QTextCodec.setCodecForLocale (QTextCodec c)
```

编解码器设置为_c_;这将被返回[codecForLocale](qtextcodec.html#codecForLocale)（ ） 。如果_c_是一个空指针，编解码器被重置为默认值。

这可能需要为那些希望使用自己的机制设置的区域设置一些应用程序。

**See also** [codecForLocale](qtextcodec.html#codecForLocale)（ ） 。

```
QTextCodec.setCodecForTr (QTextCodec c)
```

设置使用的编解码器[QObject.tr](qobject.html#tr)（ ）在它的参数_c_。如果_c_为0 （默认值） ， TR （）假定的Latin-1 。

如果在程序中的文字引用的文字是不是在Latin-1编码，此功能可用于设置相应的编码。例如，韩国程序员开发的软件可以使用eucKR程序中的所有文本，在这种情况下， main（）函数可能看起来像这样：

```
 int main(int argc, char *argv[])
 {
     [QApplication](qapplication.html) app(argc, argv);
     [QTextCodec](qtextcodec.html).setCodecForTr([QTextCodec](qtextcodec.html).codecForName("eucKR"));
     ...
 }

```

请注意，这不是个好办法选择的编码，该_user_已选择。例如，要转换包含英语字符串韩国的应用程序，所有需要的是英文字符串，通过TR （ ）和要加载翻译文件传递。对于国际化的详细信息，请参阅[Internationalization with Qt](index.htm)。

**Warning:**此功能不[reentrant](index.htm#reentrant)。

**See also** [codecForTr](qtextcodec.html#codecForTr)（）和[setCodecForCStrings](qtextcodec.html#setCodecForCStrings)（ ） 。

```
QString QTextCodec.toUnicode (self, QByteArray)
```

皈依_a_从这个编解码为Unicode的编码，并返回结果的[QString](qstring.html)。

```
QString QTextCodec.toUnicode (self, str chars)
```

将第一_size_从人物_input_从这个编解码为Unicode的编码，并返回结果的[QString](qstring.html)。

该_state_所使用的转换器被更新。

```
QString QTextCodec.toUnicode (self, str in, ConverterState state = None)
```