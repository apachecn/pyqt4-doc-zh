# QNetworkRequest Class Reference

## [[QtNetwork](index.htm) module]

该QNetworkRequest类持有与发送请求[QNetworkAccessManager](qnetworkaccessmanager.html)。[More...](#details)

### Types

*   `enum Attribute { HttpStatusCodeAttribute, HttpReasonPhraseAttribute, RedirectionTargetAttribute, ConnectionEncryptedAttribute, ..., UserMax }`
*   `enum CacheLoadControl { AlwaysNetwork, PreferNetwork, PreferCache, AlwaysCache }`
*   `enum KnownHeaders { ContentTypeHeader, ContentLengthHeader, LocationHeader, LastModifiedHeader, ..., ContentDispositionHeader }`
*   `enum LoadControl { Automatic, Manual }`
*   `enum Priority { HighPriority, NormalPriority, LowPriority }`

### Methods

*   `__init__ (self, QUrl url = QUrl())`
*   `__init__ (self, QNetworkRequest other)`
*   `QVariant attribute (self, Attribute code, QVariant defaultValue = QVariant())`
*   `bool hasRawHeader (self, QByteArray headerName)`
*   `QVariant header (self, KnownHeaders header)`
*   `QObject originatingObject (self)`
*   `Priority priority (self)`
*   `QByteArray rawHeader (self, QByteArray headerName)`
*   `list-of-QByteArray rawHeaderList (self)`
*   `setAttribute (self, Attribute code, QVariant value)`
*   `setHeader (self, KnownHeaders header, QVariant value)`
*   `setOriginatingObject (self, QObject object)`
*   `setPriority (self, Priority priority)`
*   `setRawHeader (self, QByteArray headerName, QByteArray value)`
*   `setSslConfiguration (self, QSslConfiguration configuration)`
*   `setUrl (self, QUrl url)`
*   `QSslConfiguration sslConfiguration (self)`
*   `QUrl url (self)`

### Special Methods

*   `bool __eq__ (self, QNetworkRequest other)`
*   `bool __ne__ (self, QNetworkRequest other)`

* * *

## Detailed Description

该QNetworkRequest类持有与发送请求[QNetworkAccessManager](qnetworkaccessmanager.html)。

QNetworkRequest是网络访问API的一部分，是类保持必要的资料，通过网络发送一个请求。它包含一个URL和一些辅助信息可以用来修改请求。

* * *

## Type Documentation

```
QNetworkRequest.Attribute
```

属性代码为[QNetworkRequest](qnetworkrequest.html)和[QNetworkReply](qnetworkreply.html)。

属性是用于控制该请求的行为，并从答复通过进一步的信息返回给应用程序的额外元数据。属性也是可扩展的，允许自定义实现通过自定义值。

下表解释了默认属性代码，该[QVariant](qvariant.html)相关类型，默认值，如果所说的属性是失踪，无论是在请求或回复使用。

| Constant | Value | Description |
| --- | --- | --- |
| `QNetworkRequest.HttpStatusCodeAttribute` | `0` | 回复只，类型：[QVariant.Int](qvariant.html#Type-enum)（没有默认值）指示从HTTP服务器接收（如200 ， 304 ， 404 ， 401等）的HTTP状态代码。如果连接不是基于HTTP的，此属性将不会出现。 |
| `QNetworkRequest.HttpReasonPhraseAttribute` | `1` | 回复只，类型：[QVariant.ByteArray](qvariant.html#Type-enum)（无默认值）表示HTTP原因短语作为从HTTP服务器接收（如“ OK”，“发现” ， “未找到” ， “拒绝访问” ，等等）这是状态码的人类可读的表示（见上文） 。如果连接不是基于HTTP的，此属性将不会出现。 |
| `QNetworkRequest.RedirectionTargetAttribute` | `2` | 回复只，类型：[QVariant.Url](qvariant.html#Type-enum)（无默认值）如果存在，则表明服务器将请求重定向到不同的URL。网络访问API，默认情况下不遵循重定向：它是由应用程序决定是否请求重定向应该被允许的，根据其安全策略。返回的URL可能是相对的。使用[QUrl.resolved](qurl.html#resolved)（ ）来创建一个绝对URL出来。 |
| `QNetworkRequest.ConnectionEncryptedAttribute` | `3` | 回复只，类型：[QVariant.Bool](qvariant.html#Type-enum)（默认：False ）表示通过加密（安全）连接的数据是否获得。 |
| `QNetworkRequest.CacheLoadControlAttribute` | `4` | 唯一的要求，请键入：[QVariant.Int](qvariant.html#Type-enum)（默认值：[QNetworkRequest.PreferNetwork](qnetworkrequest.html#CacheLoadControl-enum)）控制如何缓存应该被访问。可能的值有那些[QNetworkRequest.CacheLoadControl](qnetworkrequest.html#CacheLoadControl-enum)。注意，默认[QNetworkAccessManager](qnetworkaccessmanager.html)实现不支持缓存。然而，这个属性可以用于某些后端来修改他们的要求（例如，用于缓存代理服务器） 。 |
| `QNetworkRequest.CacheSaveControlAttribute` | `5` | 唯一的要求，请键入：[QVariant.Bool](qvariant.html#Type-enum)（默认：True）控制，如果得到的数据应该被保存到缓存以备日后使用。如果该值为False ，获得的数据将不被自动缓存。如果为True ，数据可以被缓存，只要它是可缓存的（什么是缓存依赖于所使用的协议） 。 |
| `QNetworkRequest.SourceIsFromCacheAttribute` | `6` | 回复只，类型：[QVariant.Bool](qvariant.html#Type-enum)（默认：False ）表示从高速缓存或没有数据是否获得。 |
| `QNetworkRequest.DoNotBufferUploadDataAttribute` | `7` | 唯一的要求，请键入：[QVariant.Bool](qvariant.html#Type-enum)（默认：False ）指示是否[QNetworkAccessManager](qnetworkaccessmanager.html)代码被允许缓冲上传数据，例如做一个HTTP POST时。当使用此标志与连续上传数据时，[ContentLengthHeader](qnetworkrequest.html#KnownHeaders-enum)报头必须被设置。 |
| `QNetworkRequest.HttpPipeliningAllowedAttribute` | `8` | 唯一的要求，请键入：[QVariant.Bool](qvariant.html#Type-enum)（默认：False ）指示是否[QNetworkAccessManager](qnetworkaccessmanager.html)代码被允许使用HTTP流水线这一请求。 |
| `QNetworkRequest.HttpPipeliningWasUsedAttribute` | `9` | 回复只，类型：[QVariant.Bool](qvariant.html#Type-enum)指示HTTP管线是否被用于接收此回复。 |
| `QNetworkRequest.CustomVerbAttribute` | `10` | 唯一的要求，请键入：[QVariant.ByteArray](qvariant.html#Type-enum)保存了自定义HTTP动词送价值（往其他动词的用法，而不是GET ， POST，PUT和DELETE ） 。这个动词是调用时设置[QNetworkAccessManager.sendCustomRequest](qnetworkaccessmanager.html#sendCustomRequest)（ ） 。 |
| `QNetworkRequest.CookieLoadControlAttribute` | `11` | 唯一的要求，请键入：[QVariant.Int](qvariant.html#Type-enum)（默认值：[QNetworkRequest.Automatic](qnetworkrequest.html#LoadControl-enum)）指示是否在请求中发送'曲奇'标头。此属性设置为False[QtWebKit](index.htm)创建一个跨源时[XMLHttpRequest](index.htm#xmlhttprequest)其中withCredentials尚未明确设置为True由创建该请求的Javascript 。看[here](http://www.w3.org/TR/XMLHttpRequest2/#credentials-flag)了解更多信息。 （这个值被引入4.7 。 ） |
| `QNetworkRequest.CookieSaveControlAttribute` | `13` | 唯一的要求，请键入：[QVariant.Int](qvariant.html#Type-enum)（默认值：[QNetworkRequest.Automatic](qnetworkrequest.html#LoadControl-enum)）指示是否保存就回答服务器接收到请求'曲奇'标头。此属性设置为False[QtWebKit](index.htm)创建一个跨源时[XMLHttpRequest](index.htm#xmlhttprequest)其中withCredentials尚未明确设置为True由创建该请求的Javascript 。看[here](http://www.w3.org/TR/XMLHttpRequest2/#credentials-flag)了解更多信息。 （这个值被引入4.7 。 ） |
| `QNetworkRequest.AuthenticationReuseAttribute` | `12` | 唯一的要求，请键入：[QVariant.Int](qvariant.html#Type-enum)（默认值：[QNetworkRequest.Automatic](qnetworkrequest.html#LoadControl-enum)）指示是否使用缓存的授权凭证的要求，如果有的话。如果设置为[QNetworkRequest.Manual](qnetworkrequest.html#LoadControl-enum)和身份验证机制是“基本”或“摘要”下，Qt将不会发送任何缓存凭据它可能对请求的URL的一个“授权” HTTP标头。该属性被设置为[QNetworkRequest.Manual](qnetworkrequest.html#LoadControl-enum)通过[QtWebKit](index.htm)创建一个跨源时[XMLHttpRequest](index.htm#xmlhttprequest)其中withCredentials尚未明确设置为True由创建该请求的Javascript 。看[here](http://www.w3.org/TR/XMLHttpRequest2/#credentials-flag)了解更多信息。 （这个值被引入4.7 。 ） |
| `QNetworkRequest.User` | `1000` | 特殊类型。其他信息可以在传递[QVariants](index.htm#qvariants)同类型从用户到UserMax 。网络访问的默认实现将忽略在这个范围内的任何请求的属性，它不会产生任何属性在此范围内的答复。的范围被保留用于扩展[QNetworkAccessManager](qnetworkaccessmanager.html)。 |
| `QNetworkRequest.UserMax` | `32767` | 特殊类型。请参阅用户。 |

这个枚举被引入或修改的Qt 4.7 。

```
QNetworkRequest.CacheLoadControl
```

控件的缓存机制[QNetworkAccessManager](qnetworkaccessmanager.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QNetworkRequest.AlwaysNetwork` | `0` | 总是从网络加载和不检查缓存有一个有效的条目（类似于浏览器的“刷新”功能） |
| `QNetworkRequest.PreferNetwork` | `1` | 默认值;从网络加载，如果缓存条目是早于网络入口 |
| `QNetworkRequest.PreferCache` | `2` | 从缓存中加载如果可用，否则从网络加载。请注意，这可以从缓存中返回可能是陈旧的（但没有过期）项目。 |
| `QNetworkRequest.AlwaysCache` | `3` | 从缓存中只加载，显示错误，如果该项目没有缓存（即离线模式） |

```
QNetworkRequest.KnownHeaders
```

众所周知头类型的列表[QNetworkRequest](qnetworkrequest.html)解析。每个已知的头也代表了原始形式，其完整的HTTP名字。

| Constant | Value | Description |
| --- | --- | --- |
| `QNetworkRequest.ContentTypeHeader` | `0` | 对应到HTTP Content-Type头，并包含包含媒体的字符串（ MIME）类型和任何辅助数据（例如，字符集） |
| `QNetworkRequest.ContentLengthHeader` | `1` | 对应于HTTP的Content-Length头，并包含长度在所发送的数据的字节数。 |
| `QNetworkRequest.LocationHeader` | `2` | 对应于HTTP位置报头和包含表示该数据的实际位置，包括在壳体的重定向的目标URL的URL。 |
| `QNetworkRequest.LastModifiedHeader` | `3` | 对应到HTTP Last-Modified头，并包含一个[QDateTime](qdatetime.html)代表内容的最后修改日期 |
| `QNetworkRequest.CookieHeader` | `4` | 对应于HTTP Cookie头部，并包含一个[QList](index.htm)\u003c[QNetworkCookie](qnetworkcookie.html)\u003e表示要发送回服务器的饼干 |
| `QNetworkRequest.SetCookieHeader` | `5` | 对应于HTTP的Set-Cookie报头，并包含一个[QList](index.htm)\u003c[QNetworkCookie](qnetworkcookie.html)\u003e表示由服务器发送到存储在本地的饼干 |

**See also** [header](qnetworkrequest.html#header)（ ）[setHeader](qnetworkrequest.html#setHeader)（ ）[rawHeader](qnetworkrequest.html#rawHeader)（）和[setRawHeader](qnetworkrequest.html#setRawHeader)（ ） 。

```
QNetworkRequest.LoadControl
```

指示如果请求的加载机制的一个方面已手动复盖，如通过[QtWebKit](index.htm)。

| Constant | Value | Description |
| --- | --- | --- |
| `QNetworkRequest.Automatic` | `0` | 默认值：表示默认行为。 |
| `QNetworkRequest.Manual` | `1` | 表示行为已手动复盖。 |

这个枚举被引入或修改的Qt 4.7 。

```
QNetworkRequest.Priority
```

这个枚举列出了可能的网络请求优先级。

| Constant | Value | Description |
| --- | --- | --- |
| `QNetworkRequest.HighPriority` | `1` | 高优先级 |
| `QNetworkRequest.NormalPriority` | `3` | 普通优先级 |
| `QNetworkRequest.LowPriority` | `5` | 低优先级 |

这个枚举被引入或修改的Qt 4.7 。

* * *

## Method Documentation

```
QNetworkRequest.__init__ (self, QUrl url = QUrl())
```

构造一个[QNetworkRequest](qnetworkrequest.html)与对象_url_以被请求的URL 。

**See also** [url](qnetworkrequest.html#url)（）和[setUrl](qnetworkrequest.html#setUrl)（ ） 。

```
QNetworkRequest.__init__ (self, QNetworkRequest other)
```

创建副本_other_。

```
QVariant QNetworkRequest.attribute (self, Attribute code, QVariant defaultValue = QVariant())
```

```
bool QNetworkRequest.hasRawHeader (self, QByteArray headerName)
```

返回True如果原始标题_headerName_存在于这个网络请求。

**See also** [rawHeader](qnetworkrequest.html#rawHeader)（）和[setRawHeader](qnetworkrequest.html#setRawHeader)（ ） 。

```
QVariant QNetworkRequest.header (self, KnownHeaders header)
```

返回已知的网络标头的值_header_如果它存在于这个请求。如果它不存在，则返回的QVariant （） （即，无效的变体） 。

**See also** [KnownHeaders](qnetworkrequest.html#KnownHeaders-enum)，[rawHeader](qnetworkrequest.html#rawHeader)（）和[setHeader](qnetworkrequest.html#setHeader)（ ） 。

```
QObject QNetworkRequest.originatingObject (self)
```

[

返回一个引用到启动此网络请求的对象，则返回0 ，如果没有设置或对象已经被销毁。

此功能被引入Qt的4.6 。

](qobject.html)

[**See also**](qobject.html) [setOriginatingObject](qnetworkrequest.html#setOriginatingObject)（ ） 。

```
Priority QNetworkRequest.priority (self)
```

[

返回此请求的优先级。

此功能被引入Qt的4.7 。

](qnetworkrequest.html#Priority-enum)

[**See also**](qnetworkrequest.html#Priority-enum) [setPriority](qnetworkrequest.html#setPriority)（ ） 。

```
QByteArray QNetworkRequest.rawHeader (self, QByteArray headerName)
```

[](qbytearray.html)

[返回头的原始形式_headerName_。如果没有这样的标头，空](qbytearray.html)[QByteArray](qbytearray.html)被返回，这可能是由一个标题，是目前无法区分，但没有任何内容（用[hasRawHeader](qnetworkrequest.html#hasRawHeader)（ ）来找出如果头存在与否） 。

原标题可以被设置[setRawHeader](qnetworkrequest.html#setRawHeader)（）或与[setHeader](qnetworkrequest.html#setHeader)（ ） 。

**See also** [header](qnetworkrequest.html#header)（）和[setRawHeader](qnetworkrequest.html#setRawHeader)（ ） 。

```
list-of-QByteArray QNetworkRequest.rawHeaderList (self)
```

返回在这个网络要求设置的所有原始标题的列表。这份名单是在头被设定的顺序。

**See also** [hasRawHeader](qnetworkrequest.html#hasRawHeader)（）和[rawHeader](qnetworkrequest.html#rawHeader)（ ） 。

```
QNetworkRequest.setAttribute (self, Attribute code, QVariant value)
```

设置与代码相关的属性_code_是值_value_。如果属性已经设置，以前的值将被丢弃。在特殊的，如果_value_是无效的[QVariant](qvariant.html)，属性未设置。

**See also** [attribute](qnetworkrequest.html#attributex)（）和[QNetworkRequest.Attribute](qnetworkrequest.html#Attribute-enum)。

```
QNetworkRequest.setHeader (self, KnownHeaders header, QVariant value)
```

设置了已知头的值_header_要_value_，复盖任何先前设置的标头。此操作还设置了相当于原始HTTP标头。

**See also** [KnownHeaders](qnetworkrequest.html#KnownHeaders-enum)，[setRawHeader](qnetworkrequest.html#setRawHeader)（）和[header](qnetworkrequest.html#header)（ ） 。

```
QNetworkRequest.setOriginatingObject (self, QObject object)
```

允许设置的参考_object_发起请求。

例如[QtWebKit](index.htm)设置原始对象的[QWebFrame](qwebframe.html)发起请求。

此功能被引入Qt的4.6 。

**See also** [originatingObject](qnetworkrequest.html#originatingObject)（ ） 。

```
QNetworkRequest.setPriority (self, Priority priority)
```

设置此请求的优先级，以_priority_。

**Note:**该_priority_只是一个暗示，网络访问管理器。它可以使用或不使用。目前它被用于HTTP来决定哪个请求应该被首先发送到服务器。

此功能被引入Qt的4.7 。

**See also** [priority](qnetworkrequest.html#priority)（ ） 。

```
QNetworkRequest.setRawHeader (self, QByteArray headerName, QByteArray value)
```

设置页眉_headerName_有利用价值_headerValue_。如果_headerName_对应于一个已知的报头（参见[QNetworkRequest.KnownHeaders](qnetworkrequest.html#KnownHeaders-enum)） ， raw格式将被解析和相应的“熟”头将被设置为好。

例如：

```
 request.setRawHeader("Last-Modified", "Sun, 06 Nov 1994 08:49:37 GMT");

```

还将设置称为标头[LastModifiedHeader](qnetworkrequest.html#KnownHeaders-enum)是[QDateTime](qdatetime.html)解析日期的对象。

注意：在设置相同的头两次将复盖以前的设置。为了实现多个同名的HTTP头的行为，你应该将两者连接起来的值，用逗号将它们隔开（ “，” ），并设置一个单一的原始标题。

**See also** [KnownHeaders](qnetworkrequest.html#KnownHeaders-enum)，[setHeader](qnetworkrequest.html#setHeader)（ ）[hasRawHeader](qnetworkrequest.html#hasRawHeader)（）和[rawHeader](qnetworkrequest.html#rawHeader)（ ） 。

```
QNetworkRequest.setSslConfiguration (self, QSslConfiguration configuration)
```

设置此网络请求的SSL配置是_config_。该应用设置为私有密钥，本地证书， SSL协议（的SSLv2 ， SSLv3的，使用TLSv1如适用） ，即在SSL后端被允许使用的CA证书和密码。

缺省情况下， SSL配置设置，这使得后端可以自由选择什么样的配置是最适合他们。

**See also** [sslConfiguration](qnetworkrequest.html#sslConfiguration)（）和[QSslConfiguration.defaultConfiguration](qsslconfiguration.html#defaultConfiguration)（ ） 。

```
QNetworkRequest.setUrl (self, QUrl url)
```

设置此网络请求所指的是网址_url_。

**See also** [url](qnetworkrequest.html#url)（ ） 。

```
QSslConfiguration QNetworkRequest.sslConfiguration (self)
```

[

返回此网络请求的SSL配置。缺省情况下， SSL设置中指定。

](qsslconfiguration.html)

[**See also**](qsslconfiguration.html) [setSslConfiguration](qnetworkrequest.html#setSslConfiguration)（ ） 。

```
QUrl QNetworkRequest.url (self)
```

[

返回此网络请求是指URL中。

](qurl.html)

[**See also**](qurl.html) [setUrl](qnetworkrequest.html#setUrl)（ ） 。

```
bool QNetworkRequest.__eq__ (self, QNetworkRequest other)
```

```
bool QNetworkRequest.__ne__ (self, QNetworkRequest other)
```