# QNetworkCookie Class Reference

## [[QtNetwork](index.htm) module]

该QNetworkCookie类包含一个网络的cookie 。[More...](#details)

### Types

*   `enum RawForm { NameAndValueOnly, Full }`

### Methods

*   `__init__ (self, QByteArray name = QByteArray(), QByteArray value = QByteArray())`
*   `__init__ (self, QNetworkCookie other)`
*   `QString domain (self)`
*   `QDateTime expirationDate (self)`
*   `bool isHttpOnly (self)`
*   `bool isSecure (self)`
*   `bool isSessionCookie (self)`
*   `QByteArray name (self)`
*   `QString path (self)`
*   `setDomain (self, QString domain)`
*   `setExpirationDate (self, QDateTime date)`
*   `setHttpOnly (self, bool enable)`
*   `setName (self, QByteArray cookieName)`
*   `setPath (self, QString path)`
*   `setSecure (self, bool enable)`
*   `setValue (self, QByteArray value)`
*   `QByteArray toRawForm (self, RawForm form = QNetworkCookie.Full)`
*   `QByteArray value (self)`

### Static Methods

*   `list-of-QNetworkCookie parseCookies (QByteArray cookieString)`

### Special Methods

*   `bool __eq__ (self, QNetworkCookie other)`
*   `bool __ne__ (self, QNetworkCookie other)`

* * *

## Detailed Description

该QNetworkCookie类包含一个网络的cookie 。

Cookies是少量的信息，像HTTP中使用无状态的协议，以保持在要求的一些持久信息。

一个cookie是由远程服务器设置，当它回复到一个请求，它预计在相同的cookie被发送回来的时候再发送请求。

QNetworkCookie拥有从网络接收一个这样的cookie。一个cookie有一个名字和一个值，但这些都是不透明的应用程序（也就是存储在其中的信息具有应用程序没有意义） 。一个cookie都有一个关联的路径名和域名，这表明当饼干应重新发送到服务器。

一个cookie还可以有到期日，这表明它的有效性。如果到期日不存在，cookie将被认为是一个“会话cookie ”，当应用程序退出（或会话时，它的概念是比）应该被丢弃。

QNetworkCookie提供了使用HTTP标头的格式解析一个cookie的方式[QNetworkCookie.parseCookies](qnetworkcookie.html#parseCookies)（）函数。然而，在接收时[QNetworkReply](qnetworkreply.html)，该cookie已经被解析。

所描述的这个类实现了饼干[initial cookie specification by Netscape](http://cgi.netscape.com/newsref/std/cookie_spec.html)，这有点类似于[RFC 2109](http://www.rfc-editor.org/rfc/rfc2109.txt)说明书中，加["HttpOnly" extension](http://msdn.microsoft.com/en-us/library/ms533046(VS.85).aspx)。更近的[RFC 2965](http://www.rfc-editor.org/rfc/rfc2965.txt)不支持规范（其使用Set- Cookie2头）。

* * *

## Type Documentation

```
QNetworkCookie.RawForm
```

该枚举用于与[toRawForm](qnetworkcookie.html#toRawForm)（ ）函数来声明哪些cookie中的表格将被退回。

| Constant | Value | Description |
| --- | --- | --- |
| `QNetworkCookie.NameAndValueOnly` | `0` | 品牌[toRawForm](qnetworkcookie.html#toRawForm)（ ）返回的cookie ，如适用于发送回服务器在客户端请求的只有“名称=值”部分“的Cookie ：”头。头字段：多个Cookie是由一个分号中的“曲奇”隔开。 |
| `QNetworkCookie.Full` | `1` | 品牌[toRawForm](qnetworkcookie.html#toRawForm)（ ）返回完整的cookie内容，如适用于发送到客户端在服务器的“设置Cookie ：”头。 |

需要注意的是该cookie的唯一的赛程表可以被解析回其原来的内容。

**See also** [toRawForm](qnetworkcookie.html#toRawForm)（）和[parseCookies](qnetworkcookie.html#parseCookies)（ ） 。

* * *

## Method Documentation

```
QNetworkCookie.__init__ (self, QByteArray name = QByteArray(), QByteArray value = QByteArray())
```

创建一个新的[QNetworkCookie](qnetworkcookie.html)对象，初始化cookie的名称_name_和它的价值_value_。

Cookie是唯一有效的，如果它有一个名字。但是，值是不透明的应用程序和为空可能有重要意义到远程服务器。

```
QNetworkCookie.__init__ (self, QNetworkCookie other)
```

创建一个新的[QNetworkCookie](qnetworkcookie.html)通过复制的内容对象_other_。

```
QString QNetworkCookie.domain (self)
```

返回这个cookie关联的领域。这对应于该cookie字符串的“域”字段。

注意，这里的域可以以点开始，这不是有效的主机名。然而，它意味着这个cookie匹配与该域名结尾的所有主机名。

**See also** [setDomain](qnetworkcookie.html#setDomain)（ ） 。

```
QDateTime QNetworkCookie.expirationDate (self)
```

[](qdatetime.html)

[返回的截止日期为这个cookie 。如果这个cookie是一个会话cookie时，](qdatetime.html)[QDateTime](qdatetime.html)返回的将是无效的。如果日期是在过去，这个cookie已经过期，不应该再回到远程服务器发送。

保质期对应于该cookie字符串的“过期”项的参数。

**See also** [isSessionCookie](qnetworkcookie.html#isSessionCookie)（）和[setExpirationDate](qnetworkcookie.html#setExpirationDate)（ ） 。

```
bool QNetworkCookie.isHttpOnly (self)
```

如果启用了这个cookie的“ HttpOnly ”标志，则返回True 。

一个cookie是“ HttpOnly ”仅设置并通过网络请求和回复检索，即HTTP协议。它不是从浏览器中运行的脚本访问。

此功能被引入Qt的4.5 。

**See also** [isSecure](qnetworkcookie.html#isSecure)（ ） 。

```
bool QNetworkCookie.isSecure (self)
```

如果是在cookie字符串，否则返回False指定的“安全”选项，则返回True 。

安全cookie可能包含私人信息，不应该怨恨过未加密的连接。

**See also** [setSecure](qnetworkcookie.html#setSecure)（ ） 。

```
bool QNetworkCookie.isSessionCookie (self)
```

返回True如果这个cookie是一个会话cookie 。会话cookie是没有到期日的cookie ，这意味着当会话的应用程序的概念是在（通常，应用程序退出时），它应该被丢弃。

**See also** [expirationDate](qnetworkcookie.html#expirationDate)（）和[setExpirationDate](qnetworkcookie.html#setExpirationDate)（ ） 。

```
QByteArray QNetworkCookie.name (self)
```

[

返回这个cookie的名称。一个cookie的唯一必填字段是它的名字，没有它不被视为有效。

](qbytearray.html)

[**See also**](qbytearray.html) [setName](qnetworkcookie.html#setName)（）和[value](qnetworkcookie.html#value)（ ） 。

```
list-of-QNetworkCookie QNetworkCookie.parseCookies (QByteArray cookieString)
```

解析cookie的字符串_cookieString_标题：从在“设置Cookie ”服务器响应接收。如果有一个解析错误，该函数返回一个空列表。

由于HTTP标头可以同时设置多个cookie ，这个函数返回一个[QList](index.htm)\u003c[QNetworkCookie](qnetworkcookie.html)\u003e ，一个用于解析每个cookie 。

**See also** [toRawForm](qnetworkcookie.html#toRawForm)（ ） 。

```
QString QNetworkCookie.path (self)
```

```
QNetworkCookie.setDomain (self, QString domain)
```

设置与此相关联的cookie的域为_domain_。

**See also** [domain](qnetworkcookie.html#domain)（ ） 。

```
QNetworkCookie.setExpirationDate (self, QDateTime date)
```

设置此Cookie的过期日期_date_。设置一个无效的到期日，以该cookie将意味着它是一个会话cookie 。

**See also** [isSessionCookie](qnetworkcookie.html#isSessionCookie)（）和[expirationDate](qnetworkcookie.html#expirationDate)（ ） 。

```
QNetworkCookie.setHttpOnly (self, bool enable)
```

设置这个cookie的“ HttpOnly ”标志_enable_。

此功能被引入Qt的4.5 。

**See also** [isHttpOnly](qnetworkcookie.html#isHttpOnly)（ ） 。

```
QNetworkCookie.setName (self, QByteArray cookieName)
```

设置这个cookie的是名_cookieName_。请注意，一个cookie名称设置为空[QByteArray](qbytearray.html)将这个cookie无效。

**See also** [name](qnetworkcookie.html#name)（）和[value](qnetworkcookie.html#value)（ ） 。

```
QNetworkCookie.setPath (self, QString path)
```

设置与此相关联的cookie的路径是_path_。

**See also** [path](qnetworkcookie.html#pathx)（ ） 。

```
QNetworkCookie.setSecure (self, bool enable)
```

设置此Cookie的安全标志，以_enable_。

安全cookie可能包含私人信息，不应该怨恨过未加密的连接。

**See also** [isSecure](qnetworkcookie.html#isSecure)（ ） 。

```
QNetworkCookie.setValue (self, QByteArray value)
```

设置此cookie的值是_value_。

**See also** [value](qnetworkcookie.html#value)（）和[name](qnetworkcookie.html#name)（ ） 。

```
QByteArray QNetworkCookie.toRawForm (self, RawForm form = QNetworkCookie.Full)
```

[](qbytearray.html)

[返回此的原始形式](qbytearray.html)[QNetworkCookie](qnetworkcookie.html)。该[QByteArray](qbytearray.html)此函数返回的是适用于HTTP头，无论是在服务器响应（ Set-Cookie头）或客户端请求（ Cookie头） 。您可以从以下两种格式之一选择，使用_form_。

**See also** [parseCookies](qnetworkcookie.html#parseCookies)（ ） 。

```
QByteArray QNetworkCookie.value (self)
```

[

返回此饼干值，如在cookie字符串中指定。请注意，一个cookie仍然是有效的，如果它的值为空。

cookie的名称 - 值对被认为是不透明的应用：那就是，它们的值没有任何意义。

](qbytearray.html)

[**See also**](qbytearray.html) [setValue](qnetworkcookie.html#setValue)（）和[name](qnetworkcookie.html#name)（ ） 。

```
bool QNetworkCookie.__eq__ (self, QNetworkCookie other)
```

```
bool QNetworkCookie.__ne__ (self, QNetworkCookie other)
```