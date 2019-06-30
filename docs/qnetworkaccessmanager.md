# QNetworkAccessManager Class Reference

## [[QtNetwork](index.htm) module]

该QNetworkAccessManager类允许应用程序发送网络请求和接收回复[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum NetworkAccessibility { UnknownAccessibility, NotAccessible, Accessible }`
*   `enum Operation { HeadOperation, GetOperation, PutOperation, PostOperation, DeleteOperation, CustomOperation }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `QNetworkConfiguration activeConfiguration (self)`
*   `QAbstractNetworkCache cache (self)`
*   `QNetworkConfiguration configuration (self)`
*   `QNetworkCookieJar cookieJar (self)`
*   `QNetworkReply createRequest (self, Operation op, QNetworkRequest request, QIODevice device = None)`
*   `QNetworkReply deleteResource (self, QNetworkRequest request)`
*   `QNetworkReply get (self, QNetworkRequest request)`
*   `QNetworkReply head (self, QNetworkRequest request)`
*   `NetworkAccessibility networkAccessible (self)`
*   `QNetworkReply post (self, QNetworkRequest request, QIODevice data)`
*   `QNetworkReply post (self, QNetworkRequest request, QByteArray data)`
*   `QNetworkReply post (self, QNetworkRequest request, QHttpMultiPart multiPart)`
*   `QNetworkProxy proxy (self)`
*   `QNetworkProxyFactory proxyFactory (self)`
*   `QNetworkReply put (self, QNetworkRequest request, QIODevice data)`
*   `QNetworkReply put (self, QNetworkRequest request, QByteArray data)`
*   `QNetworkReply put (self, QNetworkRequest request, QHttpMultiPart multiPart)`
*   `QNetworkReply sendCustomRequest (self, QNetworkRequest request, QByteArray verb, QIODevice data = None)`
*   `setCache (self, QAbstractNetworkCache cache)`
*   `setConfiguration (self, QNetworkConfiguration config)`
*   `setCookieJar (self, QNetworkCookieJar cookieJar)`
*   `setNetworkAccessible (self, NetworkAccessibility accessible)`
*   `setProxy (self, QNetworkProxy proxy)`
*   `setProxyFactory (self, QNetworkProxyFactory factory)`

### Qt Signals

*   `void authenticationRequired (QNetworkReply *,QAuthenticator *)`
*   `void finished (QNetworkReply *)`
*   `void networkAccessibleChanged (QNetworkAccessManager::NetworkAccessibility)`
*   `void proxyAuthenticationRequired (const QNetworkProxy&,QAuthenticator *)`
*   `void sslErrors (QNetworkReply *,const QList&lt;QSslError&gt;&)`

* * *

## Detailed Description

该QNetworkAccessManager类允许应用程序发送网络请求和接收回复

网络访问API是​​围绕一个QNetworkAccessManager对象，它保存了常见的配置和设置它发出的请求构造。它包含的代理和高速缓存配置，以及有关这些问题的信号，并且可以被用于监控网络操作的进度的答复信号。一个QNetworkAccessManager应该够整个Qt应用程序。

一旦QNetworkAccessManager对象已经创建，应用程序可以用它来通过网络发送请求。 A组的标准功能提供，它接受一个请求和可选的数据，并且每个回报[QNetworkReply](qnetworkreply.html)对象。返回的对象，用于获取响应于对应的请求返回的任何数据。

一个简单的下载断网可以完成与：

```
 QNetworkAccessManager *manager = new QNetworkAccessManager(this);
 connect(manager, SIGNAL(finished([QNetworkReply](qnetworkreply.html)*)),
         this, SLOT(replyFinished([QNetworkReply](qnetworkreply.html)*)));

 manager->get([QNetworkRequest](qnetworkrequest.html)([QUrl](qurl.html)("http://qt.nokia.com")));

```

QNetworkAccessManager有一个异步的API。当`replyFinished`槽上面被调用时，它需要的参数是[QNetworkReply](qnetworkreply.html)包含下载数据以及元数据（标题等）的对象。

**Note:**后的请求已经完成，它是用户的责任，以删除该[QNetworkReply](qnetworkreply.html)对象在适当的时间。不直接连接到插槽内删除[finished](qnetworkaccessmanager.html#finished)（ ） 。您可以使用[deleteLater](qobject.html#deleteLater)（）函数。

**Note:**QNetworkAccessManager队列接收到的请求。并行执行的请求的数目是依赖于该协议。目前，在桌面平台上的HTTP协议， 6请求是并行的一个主机/端口组合执行。

一个更复杂的例子，假设经理已经存在，可以是：

```
 [QNetworkRequest](qnetworkrequest.html) request;
 request.setUrl([QUrl](qurl.html)("http://qt.nokia.com"));
 request.setRawHeader("User-Agent", "MyOwnBrowser 1.0");

 [QNetworkReply](qnetworkreply.html) *reply = manager->get(request);
 connect(reply, SIGNAL(readyRead()), this, SLOT(slotReadyRead()));
 connect(reply, SIGNAL(error([QNetworkReply](qnetworkreply.html).NetworkError)),
         this, SLOT(slotError([QNetworkReply](qnetworkreply.html).NetworkError)));
 connect(reply, SIGNAL(sslErrors([QList](index.htm)<[QSslError](qsslerror.html)>)),
         this, SLOT(slotSslErrors([QList](index.htm)<[QSslError](qsslerror.html)>)));

```

### Network and Roaming support

与另外的[Bearer Management](index.htm)API来的Qt 4.7 QNetworkAccessManager获得了管理网络连接的能力。 QNetworkAccessManager可以从网络接口，如果该设备处于脱机状态，并终止该接口，如果当前过程是最后一个要使用的上行链路。请注意，某些平台利用从上次停止的应用程序使用一个上行，直到系统实际终止的连接链路的宽限期。漫游同样透明。任何排队/挂起的网络请求都自动转移到新的接入点。

客户想利用此功能不应该进行任何更改。事实上，它很可能是现有的特定于平台的连接代码可以简单地从应用程序中删除。

**Note:**在QNetworkAccessManager网络和漫游支持须待该平台支持连接管理。该[QNetworkConfigurationManager.NetworkSessionRequired](qnetworkconfigurationmanager.html#Capability-enum)可用于检测QNetworkAccessManager是否利用该功能。目前仅的Meego /哈麦丹和Symbian平台提供了连接管理支持。

**Note:**这个功能可以不与承载管理API结合使用以将QtMobility提供。应用程序必须迁移到Qt的版本承载管理。

### Symbian Platform Security Requirements

在Symbian ，它使用这个类的进程必须有`NetworkServices`平台的安全能力。如果客户端程序缺乏这种能力，操作将导致恐慌。

平台的安全功能是通过添加[TARGET.CAPABILITY](index.htm#target-capability)qmake的变量。

* * *

## Type Documentation

```
QNetworkAccessManager.NetworkAccessibility
```

指示网络是否是通过这个网络访问管理器访问。

| Constant | Value | Description |
| --- | --- | --- |
| `QNetworkAccessManager.UnknownAccessibility` | `-1` | 该网络可访问性不能确定。 |
| `QNetworkAccessManager.NotAccessible` | `0` | 该网络目前无法使用，要么是因为没有网络复盖或网络访问已通过调用明确禁用目前还[setNetworkAccessible](qnetworkaccessmanager.html#networkAccessible-prop)（ ） 。 |
| `QNetworkAccessManager.Accessible` | `1` | 该网络可访问。 |

**See also** [networkAccessible](qnetworkaccessmanager.html#networkAccessible-prop)。

```
QNetworkAccessManager.Operation
```

指示操作此回复正在处理。

| Constant | Value | Description |
| --- | --- | --- |
| `QNetworkAccessManager.HeadOperation` | `1` | 检索标题操作（创建[head](qnetworkaccessmanager.html#head)（）） |
| `QNetworkAccessManager.GetOperation` | `2` | 检索标题和​​下载内容（与创建[get](qnetworkaccessmanager.html#get)（）） |
| `QNetworkAccessManager.PutOperation` | `3` | 上传内容操作（创建[put](qnetworkaccessmanager.html#put)（）） |
| `QNetworkAccessManager.PostOperation` | `4` | 通过HTTP POST发送处理HTML表单的内容（与创建[post](qnetworkaccessmanager.html#post)（）） |
| `QNetworkAccessManager.DeleteOperation` | `5` | 删除的内容操作（创建[deleteResource](qnetworkaccessmanager.html#deleteResource)（）） |
| `QNetworkAccessManager.CustomOperation` | `6` | 自定义操作（创建[sendCustomRequest](qnetworkaccessmanager.html#sendCustomRequest)（）） |

这个枚举被引入或修改的Qt 4.7 。

**See also** [QNetworkReply.operation](qnetworkreply.html#operation)（ ） 。

* * *

## Method Documentation

```
QNetworkAccessManager.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QNetworkAccessManager](qnetworkaccessmanager.html)对象，它是网络访问的API ，并设置中心_parent_作为父对象。

```
QNetworkConfiguration QNetworkAccessManager.activeConfiguration (self)
```

[

返回当前活动的网络配置。

](qnetworkconfiguration.html)

[如果网络配置通过返回](qnetworkconfiguration.html)[configuration](qnetworkaccessmanager.html#configuration)（ ）的类型为[QNetworkConfiguration.ServiceNetwork](qnetworkconfiguration.html#Type-enum)这个函数将返回配置的当前活动的子网络配置。否则返回相同的网络配置，[configuration](qnetworkaccessmanager.html#configuration)（ ） 。

使用此功能可返回当前的实际网络配置中的网络会话使用。

此功能被引入Qt的4.7 。

**See also** [configuration](qnetworkaccessmanager.html#configuration)（ ） 。

```
QAbstractNetworkCache QNetworkAccessManager.cache (self)
```

[

返回用于存储从网络获得的数据的高速缓存。

此功能被引入Qt的4.5 。

](qabstractnetworkcache.html)

[**See also**](qabstractnetworkcache.html) [setCache](qnetworkaccessmanager.html#setCache)（ ） 。

```
QNetworkConfiguration QNetworkAccessManager.configuration (self)
```

[](qnetworkconfiguration.html)

[返回将被用来创建网络配置中的](qnetworkconfiguration.html)[network session](qnetworksession.html)处理网络请求时，将被使用。

此功能被引入Qt的4.7 。

**See also** [setConfiguration](qnetworkaccessmanager.html#setConfiguration)（）和[activeConfiguration](qnetworkaccessmanager.html#activeConfiguration)（ ） 。

```
QNetworkCookieJar QNetworkAccessManager.cookieJar (self)
```

[](qnetworkcookiejar.html)

[返回](qnetworkcookiejar.html)[QNetworkCookieJar](qnetworkcookiejar.html)用来存储从所述网络以及饼干是将要被发送得到的cookie。

**See also** [setCookieJar](qnetworkaccessmanager.html#setCookieJar)（ ） 。

```
QNetworkReply QNetworkAccessManager.createRequest (self, Operation op, QNetworkRequest request, QIODevice device = None)
```

[](qnetworkreply.html)

[返回一个新的](qnetworkreply.html)[QNetworkReply](qnetworkreply.html)反对处理操作_op_并要求_req_。该装置_outgoingData_始终为0 GET和HEAD请求，但该值传递给[post](qnetworkaccessmanager.html#post)（）和[put](qnetworkaccessmanager.html#put)（ ）这些操作（[QByteArray](qbytearray.html)变种会通过一个[QBuffer](qbuffer.html)对象） 。

默认实现调用[QNetworkCookieJar.cookiesForUrl](qnetworkcookiejar.html#cookiesForUrl)（ ）上的饼干罐设置[setCookieJar](qnetworkaccessmanager.html#setCookieJar)（）来获得将要发送到远程服务器的饼干。

返回的对象必须处于打开状态。

```
QNetworkReply QNetworkAccessManager.deleteResource (self, QNetworkRequest request)
```

[

发送删除确定的URL的资源的请求_request_。

**Note:**此功能目前仅适用于HTTP ，执行一个HTTP DELETE请求。

此功能被引入Qt的4.6 。

](qnetworkreply.html)

[**See also**](qnetworkreply.html) [get](qnetworkaccessmanager.html#get)（ ）[post](qnetworkaccessmanager.html#post)（ ）[put](qnetworkaccessmanager.html#put)（）和[sendCustomRequest](qnetworkaccessmanager.html#sendCustomRequest)（ ） 。

```
QNetworkReply QNetworkAccessManager.get (self, QNetworkRequest request)
```

[](qnetworkreply.html)

[投递一个请求，以获得目标的内容_request_并返回一个新的](qnetworkreply.html)[QNetworkReply](qnetworkreply.html)对象打开阅读，发射的[readyRead()](qiodevice.html#readyRead)每当新的数据到达信号。

的内容以及相关的头文件会被下载。

**See also** [post](qnetworkaccessmanager.html#post)（ ）[put](qnetworkaccessmanager.html#put)（ ）[deleteResource](qnetworkaccessmanager.html#deleteResource)（）和[sendCustomRequest](qnetworkaccessmanager.html#sendCustomRequest)（ ） 。

```
QNetworkReply QNetworkAccessManager.head (self, QNetworkRequest request)
```

[](qnetworkreply.html)

[投递一个请求以获得对网络的标头_request_并返回一个新的](qnetworkreply.html)[QNetworkReply](qnetworkreply.html)对象将包含这个头。

相关（ HEAD ）的HTTP请求后，该函数命名。

```
NetworkAccessibility QNetworkAccessManager.networkAccessible (self)
```

[](qnetworkaccessmanager.html#NetworkAccessibility-enum)

```
QNetworkReply QNetworkAccessManager.post (self, QNetworkRequest request, QIODevice data)
```

[](qnetworkreply.html)

[发送一个HTTP POST请求向指定的目的地_request_并返回一个新的](qnetworkreply.html)[QNetworkReply](qnetworkreply.html)对象为读而打开将包含由服务器发送回复。的内容_data_设备将被上传到服务器。

_data_必须是开放的阅读和必须保持有效，直到[finished](qnetworkaccessmanager.html#finished)（ ）信号被发射这个答复。

**Note:**在协议比HTTP和HTTPS等发送POST请求是不确定的，可能会失败。

**See also** [get](qnetworkaccessmanager.html#get)（ ）[put](qnetworkaccessmanager.html#put)（ ）[deleteResource](qnetworkaccessmanager.html#deleteResource)（）和[sendCustomRequest](qnetworkaccessmanager.html#sendCustomRequest)（ ） 。

```
QNetworkReply QNetworkAccessManager.post (self, QNetworkRequest request, QByteArray data)
```

[

这是一个重载函数。

发送的内容_data_字节数组通过指定的目标_request_。

](qnetworkreply.html)

```
QNetworkReply QNetworkAccessManager.post (self, QNetworkRequest request, QHttpMultiPart multiPart)
```

[

这是一个重载函数。

发送的内容_multiPart_消息由指定的目标_request_。

这可以用于通过HTTP发送的MIME多部分消息。

此功能被引入Qt的4.8 。

](qnetworkreply.html)

[**See also**](qnetworkreply.html) [QHttpMultiPart](qhttpmultipart.html)，[QHttpPart](qhttppart.html)和[put](qnetworkaccessmanager.html#put)（ ） 。

```
QNetworkProxy QNetworkAccessManager.proxy (self)
```

[](qnetworkproxy.html)

[返回](qnetworkproxy.html)[QNetworkProxy](qnetworkproxy.html)使用这个发送的请求[QNetworkAccessManager](qnetworkaccessmanager.html)对象将使用。对于代理的默认值是[QNetworkProxy.DefaultProxy](qnetworkproxy.html#ProxyType-enum)。

**See also** [setProxy](qnetworkaccessmanager.html#setProxy)（ ）[setProxyFactory](qnetworkaccessmanager.html#setProxyFactory)（）和[proxyAuthenticationRequired](qnetworkaccessmanager.html#proxyAuthenticationRequired)（ ） 。

```
QNetworkProxyFactory QNetworkAccessManager.proxyFactory (self)
```

[](qnetworkproxyfactory.html)

[返回的代理工厂，这](qnetworkproxyfactory.html)[QNetworkAccessManager](qnetworkaccessmanager.html)对象正在使用，以确定要用于请求的代理。

请注意，这个函数返回的指针是由管理[QNetworkAccessManager](qnetworkaccessmanager.html)并且可以在任何时候被删除。

此功能被引入Qt的4.5 。

**See also** [setProxyFactory](qnetworkaccessmanager.html#setProxyFactory)（）和[proxy](qnetworkaccessmanager.html#proxy)（ ） 。

```
QNetworkReply QNetworkAccessManager.put (self, QNetworkRequest request, QIODevice data)
```

[](qnetworkreply.html)

[上传的内容_data_到目的地_request_和returnes新](qnetworkreply.html)[QNetworkReply](qnetworkreply.html)对象将公开答复。

_data_必须打开进行读取时，这个函数被调用，并且必须保持有效，直到[finished](qnetworkaccessmanager.html#finished)（ ）信号被发射这个答复。

无论是什么将可从返回的对象中读取取决于协议。对于HTTP ，服务器可能会发送一个小的HTML页面显示上传成功（或不）。其他协议可能会在他们的答复内容。

**Note:**对于HTTP ，申请将发送一个PUT请求，其中大部分服务器不允许。表单上传机制，包括通过HTML表单上传文件，使用POST机制。

**See also** [get](qnetworkaccessmanager.html#get)（ ）[post](qnetworkaccessmanager.html#post)（ ）[deleteResource](qnetworkaccessmanager.html#deleteResource)（）和[sendCustomRequest](qnetworkaccessmanager.html#sendCustomRequest)（ ） 。

```
QNetworkReply QNetworkAccessManager.put (self, QNetworkRequest request, QByteArray data)
```

[

这是一个重载函数。

发送的内容_multiPart_消息由指定的目标_request_。

这可以用于通过HTTP发送的MIME多部分消息。

此功能被引入Qt的4.8 。

](qnetworkreply.html)

[**See also**](qnetworkreply.html) [QHttpMultiPart](qhttpmultipart.html)，[QHttpPart](qhttppart.html)和[post](qnetworkaccessmanager.html#post)（ ） 。

```
QNetworkReply QNetworkAccessManager.put (self, QNetworkRequest request, QHttpMultiPart multiPart)
```

[

这是一个重载函数。

发送的内容_data_字节数组通过指定的目标_request_。

](qnetworkreply.html)

```
QNetworkReply QNetworkAccessManager.sendCustomRequest (self, QNetworkRequest request, QByteArray verb, QIODevice data = None)
```

[

发送一个自定义的要求确定的URL的服务器_request_。

它是用户的责任来发送_verb_到，根据HTTP规范是有效的服务器。

](qnetworkreply.html)

[这种方法提供了手段来发送动词比普通的人通过其他提供](qnetworkreply.html)[get](qnetworkaccessmanager.html#get)（）或[post](qnetworkaccessmanager.html#post)（ ）等，例如发送一个HTTP OPTIONS命令。

If _data_不为空，的内容_data_设备将被上传到服务器，在这种情况下，数据必须是开放的阅读和必须保持有效，直到[finished](qnetworkaccessmanager.html#finished)（ ）信号被发射这个答复。

**Note:**此功能目前仅适用于HTTP（S ）只。

此功能被引入Qt的4.7 。

**See also** [get](qnetworkaccessmanager.html#get)（ ）[post](qnetworkaccessmanager.html#post)（ ）[put](qnetworkaccessmanager.html#put)（）和[deleteResource](qnetworkaccessmanager.html#deleteResource)（ ） 。

```
QNetworkAccessManager.setCache (self, QAbstractNetworkCache cache)
```

该_cache_说法有它的所有权转移给Qt的。

设置管理器的网络缓存是_cache_规定。缓存用于由经理分派的所有请求。

使用此功能可在网络缓存对象设置为实现附加功能的类，比如保存cookie来永久存储。

**Note:** [QNetworkAccessManager](qnetworkaccessmanager.html)采取所有权_cache_对象。

[QNetworkAccessManager](qnetworkaccessmanager.html)默认情况下，没有一个集缓存。 Qt提供了一个简单的磁盘缓存，[QNetworkDiskCache](qnetworkdiskcache.html)，它可以被使用。

此功能被引入Qt的4.5 。

**See also** [cache](qnetworkaccessmanager.html#cache)（）和[QNetworkRequest.CacheLoadControl](qnetworkrequest.html#CacheLoadControl-enum)。

```
QNetworkAccessManager.setConfiguration (self, QNetworkConfiguration config)
```

设置创建时将要使用的网络配置中的[network session](qnetworksession.html)至_config_。

网络配置使用了需要网络接入过程中的任何请求之前创建并打开一个网络会话。如果没有网络配置通过此功能的网络配置返回的明确设置[QNetworkConfigurationManager.defaultConfiguration](qnetworkconfigurationmanager.html#defaultConfiguration)（）将被使用。

要恢复设置网络配置值的默认网络配置从返回[QNetworkConfigurationManager.defaultConfiguration](qnetworkconfigurationmanager.html#defaultConfiguration)（ ） 。

```
 [QNetworkConfigurationManager](qnetworkconfigurationmanager.html) manager;
 networkAccessManager->setConfiguration(manager.defaultConfiguration());

```

如果一个无效的网络配置设置，一个网络会话将无法建立。在这种情况下，网络请求将照常进行处理，但可能会失败。例如：

```
 networkAccessManager->setConfiguration([QNetworkConfiguration](qnetworkconfiguration.html)());

```

此功能被引入Qt的4.7 。

**See also** [configuration](qnetworkaccessmanager.html#configuration)（）和[QNetworkSession](qnetworksession.html)。

```
QNetworkAccessManager.setCookieJar (self, QNetworkCookieJar cookieJar)
```

该_cookieJar_说法有它的所有权转移给Qt的。

设置管理员的饼干罐是_cookieJar_规定。饼干罐是用来由经理分派的所有请求。

使用此功能可将饼干罐对象设置为实现附加功能的类，比如保存cookie来永久存储。

**Note:** [QNetworkAccessManager](qnetworkaccessmanager.html)采取所有权_cookieJar_对象。

If _cookieJar_是在同一个线程，因为这[QNetworkAccessManager](qnetworkaccessmanager.html)，它将设置的父_cookieJar_所以，当这个对象被删除，以及饼干罐被删除。如果你想与不同的共享饼干罐[QNetworkAccessManager](qnetworkaccessmanager.html)对象，你可能要调用此函数后的饼干罐的父设置为0 。

[QNetworkAccessManager](qnetworkaccessmanager.html)默认情况下，不执行任何自己的cookie策略：它接受由服务器发送的所有cookie ，只要他们形成良好并符合最低安全要求（ cookie的域相匹配的要求及cookie路径相匹配的要求的） 。为了实现自己的安全策略，复盖[QNetworkCookieJar.cookiesForUrl](qnetworkcookiejar.html#cookiesForUrl)（）和[QNetworkCookieJar.setCookiesFromUrl](qnetworkcookiejar.html#setCookiesFromUrl)（ ）虚函数。这些功能是通过所谓的[QNetworkAccessManager](qnetworkaccessmanager.html)它检测到一个新的cookie时。

**See also** [cookieJar](qnetworkaccessmanager.html#cookieJar)（ ）[QNetworkCookieJar.cookiesForUrl](qnetworkcookiejar.html#cookiesForUrl)（）和[QNetworkCookieJar.setCookiesFromUrl](qnetworkcookiejar.html#setCookiesFromUrl)（ ） 。

```
QNetworkAccessManager.setNetworkAccessible (self, NetworkAccessibility accessible)
```

```
QNetworkAccessManager.setProxy (self, QNetworkProxy proxy)
```

设置要用于以后的请求被代理_proxy_。这不会影响已发送的请求。该[proxyAuthenticationRequired](qnetworkaccessmanager.html#proxyAuthenticationRequired)（ ）信号，如果代理要求验证发射。

代理设置此功能将被用于发出的所有请求[QNetworkAccessManager](qnetworkaccessmanager.html)。在某些情况下，可能需要选择不同的代理取决于被发送的请求的类型或目的主机。如果是那样的话，你应该考虑使用[setProxyFactory](qnetworkaccessmanager.html#setProxyFactory)（ ） 。

**See also** [proxy](qnetworkaccessmanager.html#proxy)（）和[proxyAuthenticationRequired](qnetworkaccessmanager.html#proxyAuthenticationRequired)（ ） 。

```
QNetworkAccessManager.setProxyFactory (self, QNetworkProxyFactory factory)
```

该_factory_说法有它的所有权转移给Qt的。

设置代理工厂这个类是_factory_。代理工厂被用来确定代理要用于给定要求的更具体的列表，而不是试图用所有请求相同的代理值。

通过发送所有查询[QNetworkAccessManager](qnetworkaccessmanager.html)将有型[QNetworkProxyQuery.UrlRequest](qnetworkproxyquery.html#QueryType-enum)。

例如，一个代理工厂可以应用下面的规则：

*   if the target address is in the local network (for example, if the hostname contains no dots or if it's an IP address in the organization's range), return [QNetworkProxy.NoProxy](qnetworkproxy.html#ProxyType-enum)
*   if the request is FTP, return an FTP proxy
*   if the request is HTTP or HTTPS, then return an HTTP proxy
*   otherwise, return a SOCKSv5 proxy server

的对象的生存期_factory_将由管理[QNetworkAccessManager](qnetworkaccessmanager.html)。它会删除该对象时必要的。

**Note:**如果一个特定的代理设置与[setProxy](qnetworkaccessmanager.html#setProxy)（） ，工厂将不会被使用。

此功能被引入Qt的4.5 。

**See also** [proxyFactory](qnetworkaccessmanager.html#proxyFactory)（ ）[setProxy](qnetworkaccessmanager.html#setProxy)（）和[QNetworkProxyQuery](qnetworkproxyquery.html)。

* * *

## Qt Signal Documentation

```
void authenticationRequired (QNetworkReply *,QAuthenticator *)
```

这是该信号的默认超载。

每当最后服务器请求验证之前它提供所请求的内容这个信号被发射。连接到这个信号槽应填写凭证的内容（这可以通过检查来确定_reply_对象）的_authenticator_对象。

[QNetworkAccessManager](qnetworkaccessmanager.html)将在内部缓存的凭据，将发送相同的值，如果服务器再次需要认证，不发光的authenticationRequired （ ）信号。如果它拒绝的凭据，该信号将被再次发射。

**Note:**这是不可能使用QueuedConnection连接到该信号，就好像所述认证没有被填充了新的信息时，该信号返回的连接失败。

**See also** [proxyAuthenticationRequired](qnetworkaccessmanager.html#proxyAuthenticationRequired)（ ） 。

```
void finished (QNetworkReply *)
```

这是该信号的默认超载。

每当一个悬而未决的网络应答结束这个信号被发射。该_reply_参数将包含一个指针，它指向刚刚结束的答复。这个信号在串联与发射[QNetworkReply.finished](qnetworkreply.html#finished)（）信号。

See [QNetworkReply.finished](qnetworkreply.html#finished)（）以了解关于状态的对象将是英寸信息

**Note:**不要删除_reply_对象在连接到该信号的时隙。使用[deleteLater](qobject.html#deleteLater)（ ） 。

**See also** [QNetworkReply.finished](qnetworkreply.html#finished)（）和[QNetworkReply.error](qnetworkreply.html#error)（ ） 。

```
void networkAccessibleChanged (QNetworkAccessManager::NetworkAccessibility)
```

这是该信号的默认超载。

这个信号被发射时的值[networkAccessible](qnetworkaccessmanager.html#networkAccessible-prop)属性更改。_accessible_是新的网络接入。

```
void proxyAuthenticationRequired (const QNetworkProxy&,QAuthenticator *)
```

这是该信号的默认超载。

这个信号被发射时的代理请求验证和[QNetworkAccessManager](qnetworkaccessmanager.html)无法找到一个有效的，缓存的凭据。连接到这个信号的时隙应填写为代理的凭据_proxy_在_authenticator_对象。

[QNetworkAccessManager](qnetworkaccessmanager.html)将在内部缓存的凭据。在下一次代理请求验证，[QNetworkAccessManager](qnetworkaccessmanager.html)会自动发送相同的认证，而无需再次发射proxyAuthenticationRequired信号。

如果代理服务器拒绝的凭据，[QNetworkAccessManager](qnetworkaccessmanager.html)将再次发射该信号。

**See also** [proxy](qnetworkaccessmanager.html#proxy)（ ）[setProxy](qnetworkaccessmanager.html#setProxy)（）和[authenticationRequired](qnetworkaccessmanager.html#authenticationRequired)（ ） 。

```
void sslErrors (QNetworkReply *,const QList<QSslError>&)
```

这是该信号的默认超载。

这个信号被发射，如果SSL / TLS会话期间，成立了包括证书验证错误，遇到错误。该_errors_参数包含错误的列表，_reply_是[QNetworkReply](qnetworkreply.html)所遇到的这些错误。

为了表明这些错误不是致命的，而连接应进行，[QNetworkReply.ignoreSslErrors](qnetworkreply.html#ignoreSslErrors)（）函数应该被称为从连接到该信号的时隙。如果它不叫， SSL会话将被推倒的任何数据交换（包括URL）之前。

这个信号可以被用来显示一个错误消息，指示安全性可能会受到影响的用户，并显示在SSL设置（参见sslConfiguration （）来获得的话）。如果用户决定继续进行远程证明分析后，槽应调用ignoreSslErrors （） 。

**See also** [QSslSocket.sslErrors](qsslsocket.html#sslErrors)（ ）[QNetworkReply.sslErrors](qnetworkreply.html#sslErrors)（ ）[QNetworkReply.sslConfiguration](qnetworkreply.html#sslConfiguration)（）和[QNetworkReply.ignoreSslErrors](qnetworkreply.html#ignoreSslErrors)（ ） 。