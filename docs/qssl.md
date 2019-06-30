# QSsl Class Reference

## [[QtNetwork](index.htm) module]

该QSSL命名空间声明，以共同在所有SSL枚举类[QtNetwork](index.htm)。[More...](#details)

### Types

*   `enum AlternateNameEntryType { EmailEntry, DnsEntry }`
*   `enum EncodingFormat { Pem, Der }`
*   `enum KeyAlgorithm { Rsa, Dsa }`
*   `enum KeyType { PrivateKey, PublicKey }`
*   `enum SslOption { SslOptionDisableEmptyFragments, SslOptionDisableSessionTickets, SslOptionDisableCompression, SslOptionDisableServerNameIndication, SslOptionDisableLegacyRenegotiation }`
*   `class **[SslOptions](index.htm)**`
*   `enum SslProtocol { UnknownProtocol, SslV3, SslV2, TlsV1, ..., SecureProtocols }`

* * *

## Detailed Description

该QSSL命名空间声明，以共同在所有SSL枚举类[QtNetwork](index.htm)。

* * *

## Type Documentation

```
QSsl.AlternateNameEntryType
```

描述了密钥类型为备用名称中的条目[QSslCertificate](qsslcertificate.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QSsl.EmailEntry` | `0` | 电子邮件进入;的条目包含该证书的有效期为一个电子邮件地址。 |
| `QSsl.DnsEntry` | `1` | DNS主机名称条目;该项目包含一个主机名条目，该证书有效期为。该条目可以包含通配符。 |

**See also** [QSslCertificate.alternateSubjectNames](qsslcertificate.html#alternateSubjectNames)（ ） 。

```
QSsl.EncodingFormat
```

描述了所支持的编码格式的证书和密钥。

| Constant | Value | Description |
| --- | --- | --- |
| `QSsl.Pem` | `0` | PEM格式。 |
| `QSsl.Der` | `1` | 该DER格式。 |

```
QSsl.KeyAlgorithm
```

描述了支持不同的密钥算法[QSslKey](qsslkey.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QSsl.Rsa` | `0` | RSA算法。 |
| `QSsl.Dsa` | `1` | DSA算法。 |

```
QSsl.KeyType
```

介绍了两种类型的密钥[QSslKey](qsslkey.html)支持。

| Constant | Value | Description |
| --- | --- | --- |
| `QSsl.PrivateKey` | `0` | 私钥。 |
| `QSsl.PublicKey` | `1` | 公钥。 |

```
QSsl.SslOption
```

描述了可被用于控制的SSL行为的细节的选项。这些选项通常用于开启功能关闭，以解决马车服务器。

| Constant | Value | Description |
| --- | --- | --- |
| `QSsl.SslOptionDisableEmptyFragments` | `0x01` | 使用分组密码时禁止空片段插入到数据。当启用时，这可以防止一些攻击（如野兽攻击） ，但它是与一些服务器不兼容。 |
| `QSsl.SslOptionDisableSessionTickets` | `0x02` | 禁用SSL会话票证扩展。这可能会导致较慢的连接设置，但是某些服务器不具有扩展兼容。 |
| `QSsl.SslOptionDisableCompression` | `0x04` | 禁用SSL压缩扩展。当启用时，这允许被传递通过SSL进行压缩的数据，但是有些服务器不具有此扩展兼容。 |
| `QSsl.SslOptionDisableServerNameIndication` | `0x08` | 禁用SSL服务器名称指示扩展。当启用时，这告诉服务器被访问允许其以正确的证书进行响应的虚拟主机。 |
| `QSsl.SslOptionDisableLegacyRenegotiation` | `0x10` | 停用旧的不安全机制，重新协商连接参数。当启用时，这个选项可以允许传统服务器的连接，但它引入了一个攻击者可以注入纯文本转换成SSL会话的可能性。 |

默认情况下， SslOptionDisableEmptyFragments被接通，因为这会导致问题具有大量的服务器。 SslOptionDisableLegacyRenegotiation也已经打开，因为它引入了安全风险。 SslOptionDisableCompression被接通，以防止攻击者犯罪宣传。其他选项是关闭的。

注：可购买上述选项取决于所使用的SSL后端的版本。

该SslOptions类型是一个typedef为[QFlags](index.htm)\u003cSslOption\u003e 。它存储SslOption值的或组合。

```
QSsl.SslProtocol
```

介绍了加密的协议。

| Constant | Value | Description |
| --- | --- | --- |
| `QSsl.SslV3` | `0` | 的SSLv3 |
| `QSsl.SslV2` | `1` | 的SSLv2 |
| `QSsl.TlsV1` | `2` | 使用TLSv1 |
| `QSsl.UnknownProtocol` | `-1` | 加密的协议不能确定。 |
| `QSsl.AnyProtocol` | `3` | 插座理解的SSLv2 ， SSLv3的，和TLSv1 。这个值是由[QSslSocket](qsslsocket.html)只。 |
| `QSsl.TlsV1SslV3` | `4` | 在客户端，这将发送一个TLS 1.0客户您好，使得使用TLSv1与SSLv3的连接。在服务器端，这将使双方的SSLv3和TLSv1连接。 |
| `QSsl.SecureProtocols` | `5` | 默认的选项，使用已知的安全协议;目前的行为就像TlsV1SslV3 。 |

注意：使用SSL大多数服务器理解两个版本（ 2和3） ，但建议使用最新版本只出于安全原因。然而， SSL和TLS是不能互相兼容的：如果你得到意想不到的握手失败，请确认您选择了正确的设置为您的协议。