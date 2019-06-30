# QSslCertificate Class Reference

## [[QtNetwork](index.htm) module]

该QSslCertificate类提供了一个X509证书了方便的API 。[More...](#details)

### Types

*   `enum SubjectInfo { Organization, CommonName, LocalityName, OrganizationalUnitName, CountryName, StateOrProvinceName }`

### Methods

*   `__init__ (self, QIODevice device, QSsl.EncodingFormat format = QSsl.Pem)`
*   `__init__ (self, QByteArray data = QByteArray(), QSsl.EncodingFormat format = QSsl.Pem)`
*   `__init__ (self, QSslCertificate other)`
*   `dict-of-QSsl.AlternateNameEntryType-list-of-QString alternateSubjectNames (self)`
*   `clear (self)`
*   `QByteArray digest (self, QCryptographicHash.Algorithm algorithm = QCryptographicHash.Md5)`
*   `QDateTime effectiveDate (self)`
*   `QDateTime expiryDate (self)`
*   `int handle (self)`
*   `bool isNull (self)`
*   `QString issuerInfo (self, SubjectInfo info)`
*   `QString issuerInfo (self, QByteArray tag)`
*   `bool isValid (self)`
*   `QSslKey publicKey (self)`
*   `QByteArray serialNumber (self)`
*   `QString subjectInfo (self, SubjectInfo info)`
*   `QString subjectInfo (self, QByteArray tag)`
*   `QByteArray toDer (self)`
*   `QByteArray toPem (self)`
*   `QByteArray version (self)`

### Static Methods

*   `list-of-QSslCertificate fromData (QByteArray data, QSsl.EncodingFormat format = QSsl.Pem)`
*   `list-of-QSslCertificate fromDevice (QIODevice device, QSsl.EncodingFormat format = QSsl.Pem)`
*   `list-of-QSslCertificate fromPath (QString path, QSsl.EncodingFormat format = QSsl.Pem, QRegExp.PatternSyntax syntax = QRegExp.FixedString)`

### Special Methods

*   `bool __eq__ (self, QSslCertificate other)`
*   `bool __ne__ (self, QSslCertificate other)`

* * *

## Detailed Description

该QSslCertificate类提供了一个X509证书了方便的API 。

QSslCertificate存储X509证书，并且通常用于验证有关本地主机，远程连接等，或可信任的第三方认证机构的标识和存储信息。

有许多方法来构造一个QSslCertificate 。最常见的方法是调用[QSslSocket.peerCertificate](qsslsocket.html#peerCertificate)（ ） ，它返回一个QSslCertificate对象，或[QSslSocket.peerCertificateChain](qsslsocket.html#peerCertificateChain)（ ） ，它返回它们的列表。您也可以加载一个DER证书（二进制）或PEM （ Base64编码）编码的捆绑，通常存储为一个或多个本地文件，或在Qt的资源。

您可以致电[isNull](qsslcertificate.html#isNull)（）来检查，如果你的证书为null 。默认情况下， QSslCertificate构造一个空证书。要检查证书是否有效，呼叫[isValid](qsslcertificate.html#isValid)（ ） 。空证书是无效的，但一个无效的证书不一定空。如果你想重置所有内容的凭证，请致电[clear](qsslcertificate.html#clear)（ ） 。

加载证书后，您可以找到有关证书，它的主题，它的发行者信息，通过调用许多存取功能之一，包括[version](qsslcertificate.html#version)（ ）[serialNumber](qsslcertificate.html#serialNumber)（ ）[issuerInfo](qsslcertificate.html#issuerInfo)（）和[subjectInfo](qsslcertificate.html#subjectInfo)（ ） 。您可以致电[effectiveDate](qsslcertificate.html#effectiveDate)（）和[expiryDate](qsslcertificate.html#expiryDate)（）来检查时，启动证书是有效，当它过期。该[publicKey](qsslcertificate.html#publicKey)（ ）函数返回证书主题的公钥作为[QSslKey](qsslkey.html)。您可以致电[issuerInfo](qsslcertificate.html#issuerInfo)（）或[subjectInfo](qsslcertificate.html#subjectInfo)（）来获取有关证书颁发者和它的主题的详细信息。

在内部， QSslCertificate被存储为一个X509结构。您可以通过调用访问此手柄[handle](qsslcertificate.html#handle)（） ，但结果可能不是可移植的。

* * *

## Type Documentation

```
QSslCertificate.SubjectInfo
```

介绍了可以传递给钥匙[QSslCertificate.issuerInfo](qsslcertificate.html#issuerInfo)（）或[QSslCertificate.subjectInfo](qsslcertificate.html#subjectInfo)（）来获取有关证书颁发者或主题的信息。

| Constant | Value | Description |
| --- | --- | --- |
| `QSslCertificate.Organization` | `0` | “O”的组织的名称。 |
| `QSslCertificate.CommonName` | `1` | “CN”的通用名称;最常这是用来存储主机名。 |
| `QSslCertificate.LocalityName` | `2` | “L”的地方。 |
| `QSslCertificate.OrganizationalUnitName` | `3` | 「其他指定用途“的组织单位名称。 |
| `QSslCertificate.CountryName` | `4` | “C”的国家。 |
| `QSslCertificate.StateOrProvinceName` | `5` | “ST”的州或省。 |

* * *

## Method Documentation

```
QSslCertificate.__init__ (self, QIODevice device, QSsl.EncodingFormat format = QSsl.Pem)
```

构造一个[QSslCertificate](qsslcertificate.html)阅读_format_从编码数据_device_并使用找到的第一个证书。您可以稍后致电[isNull](qsslcertificate.html#isNull)（） ，以查看是否_device_包含一个证书，如果加载成功后，该证书。

```
QSslCertificate.__init__ (self, QByteArray data = QByteArray(), QSsl.EncodingFormat format = QSsl.Pem)
```

构造一个[QSslCertificate](qsslcertificate.html)通过解析_format_编码_data_并使用找到的第一个可用的证书。您可以稍后致电[isNull](qsslcertificate.html#isNull)（） ，以查看是否_data_包含一个证书，如果加载成功后，该证书。

```
QSslCertificate.__init__ (self, QSslCertificate other)
```

构造完全相同的副本_other_。

```
dict-of-QSsl.AlternateNameEntryType-list-of-QString QSslCertificate.alternateSubjectNames (self)
```

返回此证书备用主题名的列表。备选主题名称通常包含主机名，可以使用通配符，即有效期为这个​​证书。

这些名称对所连接的对端的主机名进行测试，如果任一标的信息[CommonName](qsslcertificate.html#SubjectInfo-enum)没有定义一个有效的主机名，或拍摄主体信息名称不匹配对端的主机名。

**See also** [subjectInfo](qsslcertificate.html#subjectInfo)（ ） 。

```
QSslCertificate.clear (self)
```

清除该证书的内容，使之成为一个空证书。

**See also** [isNull](qsslcertificate.html#isNull)（ ） 。

```
QByteArray QSslCertificate.digest (self, QCryptographicHash.Algorithm algorithm = QCryptographicHash.Md5)
```

[

返回此证书的加密摘要。默认情况下，一个MD5摘要将会产生，但您也可以指定自定义_algorithm_。

](qbytearray.html)

```
QDateTime QSslCertificate.effectiveDate (self)
```

[](qdatetime.html)

[返回的日期，时间，该证书生效，或空](qdatetime.html)[QDateTime](qdatetime.html)如果这是一个无效的证书。

**See also** [expiryDate](qsslcertificate.html#expiryDate)（ ） 。

```
QDateTime QSslCertificate.expiryDate (self)
```

[](qdatetime.html)

[返回日期时间的证书过期，或空](qdatetime.html)[QDateTime](qdatetime.html)如果这是一个无效的证书。

**See also** [effectiveDate](qsslcertificate.html#effectiveDate)（ ） 。

```
list-of-QSslCertificate QSslCertificate.fromData (QByteArray data, QSsl.EncodingFormat format = QSsl.Pem)
```

搜索和分析所有证书_data_被编码在指定_format_并返回他们的证书的列表。

**See also** [fromDevice](qsslcertificate.html#fromDevice)（ ） 。

```
list-of-QSslCertificate QSslCertificate.fromDevice (QIODevice device, QSsl.EncodingFormat format = QSsl.Pem)
```

搜索和分析所有证书_device_被编码在指定_format_并返回他们的证书的列表。

**See also** [fromData](qsslcertificate.html#fromData)（ ） 。

```
list-of-QSslCertificate QSslCertificate.fromPath (QString path, QSsl.EncodingFormat format = QSsl.Pem, QRegExp.PatternSyntax syntax = QRegExp.FixedString)
```

搜索中的所有文件_path_对于证书编码指定_format_并返回它们在列表中。_must_是一个文件或一个图案匹配一个或多个文件，所指定的_syntax_。

例如：

```
 foreach (const [QSslCertificate](qsslcertificate.html) &cert, [QSslCertificate](qsslcertificate.html).fromPath("C:/ssl/certificate.*.pem", [QSsl](qssl.html).Pem,
                                                          [QRegExp](qregexp.html).Wildcard)) {
     qDebug() << cert.issuerInfo([QSslCertificate](qsslcertificate.html).Organization);
 }

```

**See also** [fromData](qsslcertificate.html#fromData)（ ） 。

```
int QSslCertificate.handle (self)
```

返回一个指向本地证书手柄，如果有一个或一个空指针，否则。

你可以使用这个句柄，与原生API一起，访问有关证书的扩展信息。

**Warning:**使用此功能有被非便携式的概率很高，它的返回值可能会有所不同从平台到平台或次要版本变更次要版本。

```
bool QSslCertificate.isNull (self)
```

返回True如果这是一个空证书（即一个没有内容的证书），否则返回False 。

默认情况下，[QSslCertificate](qsslcertificate.html)构造一个空证书。

**See also** [isValid](qsslcertificate.html#isValid)（）和[clear](qsslcertificate.html#clear)（ ） 。

```
QString QSslCertificate.issuerInfo (self, SubjectInfo info)
```

返回发行人信息的_subject_从证书，或空字符串，如果没有信息_subject_在证书中。

**See also** [subjectInfo](qsslcertificate.html#subjectInfo)（ ） 。

```
QString QSslCertificate.issuerInfo (self, QByteArray tag)
```

返回发行人信息_tag_从证书，或空字符串，如果没有信息_tag_在证书中。

**See also** [subjectInfo](qsslcertificate.html#subjectInfo)（ ） 。

```
bool QSslCertificate.isValid (self)
```

返回True如果该证书是有效的，否则返回False 。

注：目前，该功能会检查当前的数据时间是在此期间，该证书被认为有效的日期时间范围内，并检查该证书是不是在欺诈证书的黑名单。

**See also** [isNull](qsslcertificate.html#isNull)（ ） 。

```
QSslKey QSslCertificate.publicKey (self)
```

[

返回证书主题的公钥。

](qsslkey.html)

```
QByteArray QSslCertificate.serialNumber (self)
```

[

以十进制格式返回该证书的序列号字符串。若序列号不能转换为十进制格式（例如，如果它大于4294967295 ，这意味着它不适合4个字节） ，则返回其十六进制的版本。

```
QString QSslCertificate.subjectInfo (self, SubjectInfo info)
```

返回的信息为_subject_，或空字符串，如果没有信息_subject_在证书中。

](qbytearray.html)

[**See also**](qbytearray.html) [issuerInfo](qsslcertificate.html#issuerInfo)（ ） 。

```
QString QSslCertificate.subjectInfo (self, QByteArray tag)
```

返回主题信息_tag_，或空字符串，如果没有信息_tag_在证书中。

**See also** [issuerInfo](qsslcertificate.html#issuerInfo)（ ） 。

```
QByteArray QSslCertificate.toDer (self)
```

[

返回此证书转换为DER （二进制）编码表示。

](qbytearray.html)

```
QByteArray QSslCertificate.toPem (self)
```

[

返回此证书转换为PEM （ Base64编码）编码表示。

](qbytearray.html)

```
QByteArray QSslCertificate.version (self)
```

[

返回证书的版本字符串。

```
bool QSslCertificate.__eq__ (self, QSslCertificate other)
```

```
bool QSslCertificate.__ne__ (self, QSslCertificate other)
```

](qbytearray.html)