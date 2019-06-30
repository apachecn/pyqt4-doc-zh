# QTextEncoder Class Reference

## [[QtCore](index.htm) module]

该QTextEncoder类提供了一个基于状态的编码器。[More...](#details)

### Methods

*   `__init__ (self, QTextCodec codec)`
*   `__init__ (self, QTextCodec codec, QTextCodec.ConversionFlags flags)`
*   `QByteArray fromUnicode (self, QString str)`

* * *

## Detailed Description

该QTextEncoder类提供了一个基于状态的编码器。

文字编码转换从Unicode文本转换成使用特定的编解码器编码的文本格式。

该编码器的Unicode转换成另一种格式，记住，需要调用之间的任何状态。

* * *

## Method Documentation

```
QTextEncoder.__init__ (self, QTextCodec codec)
```

构造一个文本编码器给定_codec_。

```
QTextEncoder.__init__ (self, QTextCodec codec, QTextCodec.ConversionFlags flags)
```

构造一个文本编码器给定_codec_和转换_flags_。

此功能被引入Qt的4.7 。

```
QByteArray QTextEncoder.fromUnicode (self, QString str)
```

[](qbytearray.html)

[Unicode字符串转换_str_成编码的](qbytearray.html)[QByteArray](qbytearray.html)。