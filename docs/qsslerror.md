# QSslError Class Reference

## [[QtNetwork](index.htm) module]

该QSslError类提供SSL错误。[More...](#details)

### Types

*   `enum SslError { UnspecifiedError, NoError, UnableToGetIssuerCertificate, UnableToDecryptCertificateSignature, ..., CertificateBlacklisted }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, SslError error)`
*   `__init__ (self, SslError error, QSslCertificate certificate)`
*   `__init__ (self, QSslError other)`
*   `QSslCertificate certificate (self)`
*   `SslError error (self)`
*   `QString errorString (self)`

### Special Methods

*   `bool __eq__ (self, QSslError other)`
*   `bool __ne__ (self, QSslError other)`

* * *

## Detailed Description

该QSslError类提供SSL错误。

QSslError提供了管理过程中的错误一个简单的API[QSslSocket](qsslsocket.html)的SSL握手。

* * *

## Type Documentation

```
QSslError.SslError
```

说明可能发生在SSL握手都承认错误。

| Constant | Value |
| --- | --- |
| `QSslError.NoError` | `0` |
| `QSslError.UnableToGetIssuerCertificate` | `1` |
| `QSslError.UnableToDecryptCertificateSignature` | `2` |
| `QSslError.UnableToDecodeIssuerPublicKey` | `3` |
| `QSslError.CertificateSignatureFailed` | `4` |
| `QSslError.CertificateNotYetValid` | `5` |
| `QSslError.CertificateExpired` | `6` |
| `QSslError.InvalidNotBeforeField` | `7` |
| `QSslError.InvalidNotAfterField` | `8` |
| `QSslError.SelfSignedCertificate` | `9` |
| `QSslError.SelfSignedCertificateInChain` | `10` |
| `QSslError.UnableToGetLocalIssuerCertificate` | `11` |
| `QSslError.UnableToVerifyFirstCertificate` | `12` |
| `QSslError.CertificateRevoked` | `13` |
| `QSslError.InvalidCaCertificate` | `14` |
| `QSslError.PathLengthExceeded` | `15` |
| `QSslError.InvalidPurpose` | `16` |
| `QSslError.CertificateUntrusted` | `17` |
| `QSslError.CertificateRejected` | `18` |
| `QSslError.SubjectIssuerMismatch` | `19` |
| `QSslError.AuthorityIssuerSerialNumberMismatch` | `20` |
| `QSslError.NoPeerCertificate` | `21` |
| `QSslError.HostNameMismatch` | `22` |
| `QSslError.UnspecifiedError` | `-1` |
| `QSslError.NoSslSupport` | `23` |
| `QSslError.CertificateBlacklisted` | `24` |

**See also** [QSslError.errorString](qsslerror.html#errorString)（ ） 。

* * *

## Method Documentation

```
QSslError.__init__ (self)
```

构造一个[QSslError](qsslerror.html)反对，没有错误和默认的证书。

```
QSslError.__init__ (self, SslError error)
```

构造一个[QSslError](qsslerror.html)对象。该参数指定了_error_发生。

```
QSslError.__init__ (self, SslError error, QSslCertificate certificate)
```

构造一个[QSslError](qsslerror.html)对象。两个参数指定_error_所发生的，并且其_certificate_错误涉及到。

**See also** [QSslCertificate](qsslcertificate.html)。

```
QSslError.__init__ (self, QSslError other)
```

构造完全相同的副本_other_。

```
QSslCertificate QSslError.certificate (self)
```

[

返回与此错误相关联的证书，或者一个空证书，如果该错误不涉及任何证书。

](qsslcertificate.html)

[**See also**](qsslcertificate.html) [error](qsslerror.html#error)（）和[errorString](qsslerror.html#errorString)（ ） 。

```
SslError QSslError.error (self)
```

[

返回错误的类型。

](qsslerror.html#SslError-enum)

[**See also**](qsslerror.html#SslError-enum) [errorString](qsslerror.html#errorString)（）和[certificate](qsslerror.html#certificate)（ ） 。

```
QString QSslError.errorString (self)
```

返回错误的简短本地化可读描述。

**See also** [error](qsslerror.html#error)（）和[certificate](qsslerror.html#certificate)（ ） 。

```
bool QSslError.__eq__ (self, QSslError other)
```

```
bool QSslError.__ne__ (self, QSslError other)
```