# QCryptographicHash Class Reference

## [[QtCore](index.htm) module]

该QCryptographicHash类提供了一种方法来生成密码散列。[More...](#details)

### Types

*   `enum Algorithm { Md4, Md5, Sha1 }`

### Methods

*   `__init__ (self, Algorithm method)`
*   `addData (self, str data)`
*   `addData (self, QByteArray data)`
*   `reset (self)`
*   `QByteArray result (self)`

### Static Methods

*   `QByteArray hash (QByteArray data, Algorithm method)`

* * *

## Detailed Description

该QCryptographicHash类提供了一种方法来生成密码散列。

QCryptographicHash可以用来产生二进制或文本数据的加密哈希值。

目前MD4，MD5和SHA-1被支持。

* * *

## Type Documentation

```
QCryptographicHash.Algorithm
```

| Constant | Value | Description |
| --- | --- | --- |
| `QCryptographicHash.Md4` | `0` | 产生一个MD4哈希总和 |
| `QCryptographicHash.Md5` | `1` | 生成一个MD5散列总和 |
| `QCryptographicHash.Sha1` | `2` | 生成一个SHA1哈希总和 |

* * *

## Method Documentation

```
QCryptographicHash.__init__ (self, Algorithm method)
```

构造一个对象，该对象可以使用用于从数据创建密码散列_method_。

```
QCryptographicHash.addData (self, str data)
```

将第一_length_的字符_data_到的加密哈希值。

```
QCryptographicHash.addData (self, QByteArray data)
```

这个函数的重载[addData](qcryptographichash.html#addData)（ ） 。

```
QByteArray QCryptographicHash.hash (QByteArray data, Algorithm method)
```

[

返回的散列_data_ using _method_。

```
QCryptographicHash.reset (self)
```

重置对象。

](qbytearray.html)

```
QByteArray QCryptographicHash.result (self)
```

[

返回最终的哈希值。

](qbytearray.html)

[**See also**](qbytearray.html) [QByteArray.toHex](qbytearray.html#toHex)（ ） 。