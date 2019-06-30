# QTextDecoder Class Reference

## [[QtCore](index.htm) module]

该QTextDecoder类提供了一个基于状态的解码器。[More...](#details)

### Methods

*   `__init__ (self, QTextCodec codec)`
*   `__init__ (self, QTextCodec codec, QTextCodec.ConversionFlags flags)`
*   `QString toUnicode (self, str chars)`
*   `toUnicode (self, QString target, str chars)`
*   `QString toUnicode (self, QByteArray ba)`

* * *

## Detailed Description

该QTextDecoder类提供了一个基于状态的解码器。

文本解码器使用一个特定的编解码器编码的文本格式转换成Unicode文本转换。

该解码器转换成这种格式的文本转换成Unicode ，记住，需要调用之间的任何状态。

* * *

## Method Documentation

```
QTextDecoder.__init__ (self, QTextCodec codec)
```

构造一个文本解码器为给定的_codec_。

```
QTextDecoder.__init__ (self, QTextCodec codec, QTextCodec.ConversionFlags flags)
```

构造一个文本解码器为给定的_codec_和转换_flags_。

此功能被引入Qt的4.7 。

```
QString QTextDecoder.toUnicode (self, str chars)
```

将第一_len_以字节为单位_chars_为Unicode ，返回结果。

如果不是所有的字符都使用（例如，如果一个多字节编码中只有一部分是在字符的末尾） ，解码器会记住足够的状态，继续给这个函数在下次调用。

```
QTextDecoder.toUnicode (self, QString target, str chars)
```

这是一个重载函数。

转换后的字符串中返回_target_。

```
QString QTextDecoder.toUnicode (self, QByteArray ba)
```

这是一个重载函数。

由指定的字节数组中转换字节_ba_为Unicode并返回结果。