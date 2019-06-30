# QSslCipher Class Reference

## [[QtNetwork](index.htm) module]

该QSslCipher类表示一个SSL加密密码。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QString name, QSsl.SslProtocol protocol)`
*   `__init__ (self, QSslCipher other)`
*   `QString authenticationMethod (self)`
*   `QString encryptionMethod (self)`
*   `bool isNull (self)`
*   `QString keyExchangeMethod (self)`
*   `QString name (self)`
*   `QSsl.SslProtocol protocol (self)`
*   `QString protocolString (self)`
*   `int supportedBits (self)`
*   `int usedBits (self)`

### Special Methods

*   `bool __eq__ (self, QSslCipher other)`
*   `bool __ne__ (self, QSslCipher other)`

* * *

## Detailed Description

该QSslCipher类表示一个SSL加密密码。

大约一个加密密码QSslCipher存储信息。它是最常见的是用[QSslSocket](qsslsocket.html)，无论是配置的加密套接字可以使用，或者用来显示套接字的密码给用户。

* * *

## Method Documentation

```
QSslCipher.__init__ (self)
```

构造一个空[QSslCipher](qsslcipher.html)对象。

```
QSslCipher.__init__ (self, QString name, QSsl.SslProtocol protocol)
```

构造一个[QSslCipher](qsslcipher.html)对于对象所确定的密码_name_和_protocol_。该构造函数只接受支持的密码（即_name_和_protocol_必须确定在所返回的密码列表中选择一个密码[QSslSocket.supportedCiphers](qsslsocket.html#supportedCiphers)（））。

您可以致电[isNull](qsslcipher.html#isNull)（ ）施工后检查，如果_name_和_protocol_正确地确定了支持的密码。

```
QSslCipher.__init__ (self, QSslCipher other)
```

构造的完全相同的副本_other_密码。

```
QString QSslCipher.authenticationMethod (self)
```

返回密码的认证方式为[QString](qstring.html)。

```
QString QSslCipher.encryptionMethod (self)
```

返回密码的加密方式为[QString](qstring.html)。

```
bool QSslCipher.isNull (self)
```

返回True如果这是一个空密码，否则返回False 。

```
QString QSslCipher.keyExchangeMethod (self)
```

返回加密的密钥交换方法为[QString](qstring.html)。

```
QString QSslCipher.name (self)
```

返回的加密的名称，或空[QString](qstring.html)如果这是一个空密码。

**See also** [isNull](qsslcipher.html#isNull)（ ） 。

```
QSsl.SslProtocol QSslCipher.protocol (self)
```

[](qssl.html#SslProtocol-enum)

[返回加密的协议类型，或](qssl.html#SslProtocol-enum)[QSsl.UnknownProtocol](qssl.html#SslProtocol-enum)如果[QSslCipher](qsslcipher.html)无法确定的协议（[protocolString](qsslcipher.html#protocolString)（ ）可能包含更多信息） 。

**See also** [protocolString](qsslcipher.html#protocolString)（ ） 。

```
QString QSslCipher.protocolString (self)
```

返回加密的协议作为[QString](qstring.html)。

**See also** [protocol](qsslcipher.html#protocol)（ ） 。

```
int QSslCipher.supportedBits (self)
```

返回由加密支持的比特数。

**See also** [usedBits](qsslcipher.html#usedBits)（ ） 。

```
int QSslCipher.usedBits (self)
```

返回使用的密码的位数。

**See also** [supportedBits](qsslcipher.html#supportedBits)（ ） 。

```
bool QSslCipher.__eq__ (self, QSslCipher other)
```

```
bool QSslCipher.__ne__ (self, QSslCipher other)
```