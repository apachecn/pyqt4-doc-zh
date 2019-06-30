# QSslKey Class Reference

## [[QtNetwork](index.htm) module]

该QSslKey类提供了私钥和公钥的接口。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QByteArray encoded, QSsl.KeyAlgorithm algorithm, QSsl.EncodingFormat encoding = QSsl.Pem, QSsl.KeyType type = QSsl.PrivateKey, QByteArray passPhrase = QByteArray())`
*   `__init__ (self, QIODevice device, QSsl.KeyAlgorithm algorithm, QSsl.EncodingFormat encoding = QSsl.Pem, QSsl.KeyType type = QSsl.PrivateKey, QByteArray passPhrase = QByteArray())`
*   `__init__ (self, QSslKey other)`
*   `QSsl.KeyAlgorithm algorithm (self)`
*   `clear (self)`
*   `int handle (self)`
*   `bool isNull (self)`
*   `int length (self)`
*   `QByteArray toDer (self, QByteArray passPhrase = QByteArray())`
*   `QByteArray toPem (self, QByteArray passPhrase = QByteArray())`
*   `QSsl.KeyType type (self)`

### Special Methods

*   `bool __eq__ (self, QSslKey key)`
*   `bool __ne__ (self, QSslKey key)`

* * *

## Detailed Description

该QSslKey类提供了私钥和公钥的接口。

QSslKey提供了用于管理密钥的简单的API 。

* * *

## Method Documentation

```
QSslKey.__init__ (self)
```

构造一个空的关键。

**See also** [isNull](qsslkey.html#isNull)（ ） 。

```
QSslKey.__init__ (self, QByteArray encoded, QSsl.KeyAlgorithm algorithm, QSsl.EncodingFormat encoding = QSsl.Pem, QSsl.KeyType type = QSsl.PrivateKey, QByteArray passPhrase = QByteArray())
```

构造一个[QSslKey](qsslkey.html)由字符串的字节数组中的解码_encoded_使用指定的_algorithm_和_encoding_格式。如果编码的密钥进行加密，_passPhrase_用于解密。_type_指定是否关键是公营或私营。

施工，使用后[isNull](qsslkey.html#isNull)（ ）来检查_encoded_包含一个有效的密钥。

```
QSslKey.__init__ (self, QIODevice device, QSsl.KeyAlgorithm algorithm, QSsl.EncodingFormat encoding = QSsl.Pem, QSsl.KeyType type = QSsl.PrivateKey, QByteArray passPhrase = QByteArray())
```

构造一个[QSslKey](qsslkey.html)通过从读取和解码数据_device_使用指定的_algorithm_和_encoding_格式。如果编码的密钥进行加密，_passPhrase_用于解密。_type_指定是否关键是公营或私营。

施工，使用后[isNull](qsslkey.html#isNull)（ ）来检查_device_提供了一个有效的密钥。

```
QSslKey.__init__ (self, QSslKey other)
```

构造完全相同的副本_other_。

```
QSsl.KeyAlgorithm QSslKey.algorithm (self)
```

[

返回密钥算法。

```
QSslKey.clear (self)
```

清除该键的内容，使之成为一个空键。

](qssl.html#KeyAlgorithm-enum)

[**See also**](qssl.html#KeyAlgorithm-enum) [isNull](qsslkey.html#isNull)（ ） 。

```
int QSslKey.handle (self)
```

返回一个指向本地密钥句柄，如果可用，否则返回空指针。

你可以使用这个句柄连同原生API来访问有关的关键扩展信息。

**Warning:**使用此功能有被非便携式的概率很高，它的返回值可以跨平台有所不同，轻微之间的Qt版本。

```
bool QSslKey.isNull (self)
```

返回True如果这是一个空的关键，否则为False 。

**See also** [clear](qsslkey.html#clear)（ ） 。

```
int QSslKey.length (self)
```

返回键的长度位，或-1，如果key为null 。

```
QByteArray QSslKey.toDer (self, QByteArray passPhrase = QByteArray())
```

[

返回DER编码的关键。结果进行加密_passPhrase_如果该键是一个私钥和_passPhrase_非空。

](qbytearray.html)

```
QByteArray QSslKey.toPem (self, QByteArray passPhrase = QByteArray())
```

[

返回PEM编码的关键。结果进行加密_passPhrase_如果该键是一个私钥和_passPhrase_非空。

](qbytearray.html)

```
QSsl.KeyType QSslKey.type (self)
```

[

返回键（即公钥或PrivateKey）对其的类型。

```
bool QSslKey.__eq__ (self, QSslKey key)
```

```
bool QSslKey.__ne__ (self, QSslKey key)
```

](qssl.html#KeyType-enum)