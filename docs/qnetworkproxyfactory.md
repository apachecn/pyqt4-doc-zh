# QNetworkProxyFactory Class Reference

## [[QtNetwork](index.htm) module]

该QNetworkProxyFactory类提供细粒度的代理选择。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QNetworkProxyFactory)`
*   `list-of-QNetworkProxy queryProxy (self, QNetworkProxyQuery query = QNetworkProxyQuery())`

### Static Methods

*   `list-of-QNetworkProxy proxyForQuery (QNetworkProxyQuery query)`
*   `setApplicationProxyFactory (QNetworkProxyFactory factory)`
*   `setUseSystemConfiguration (bool enable)`
*   `list-of-QNetworkProxy systemProxyForQuery (QNetworkProxyQuery query = QNetworkProxyQuery())`

* * *

## Detailed Description

该QNetworkProxyFactory类提供细粒度的代理选择。

QNetworkProxyFactory是一个扩展[QNetworkProxy](qnetworkproxy.html)，允许应用程序有一个更细粒度控制哪些代理服务器使用，这取决于插座请求代理。这使得应用程序可以应用不同的设置，根据该协议或目的地的主机名，例如。

QNetworkProxyFactory可以全局设置的应用程序，在这种情况下，它会复盖设置任何全局代理[QNetworkProxy.setApplicationProxy](qnetworkproxy.html#setApplicationProxy)（ ） 。如果全局设置，使用Qt创建的套接字将查询的工厂，以确定要使用的代理服务器。

一个工厂也可以支持多个连接特定的框架，比如设置[QNetworkAccessManager](qnetworkaccessmanager.html)。当这样的对象设置，该工厂将被询问只有该框架创建的套接字。

### System Proxies

您可以配置一个工厂使用系统代理设置。调用[setUseSystemConfiguration](qnetworkproxyfactory.html#setUseSystemConfiguration)（ ）函数真正要启用此行为，或虚假禁用它。

同样，您可以使用一个工厂通过调用进行查询，直接到系统代理其[systemProxyForQuery](qnetworkproxyfactory.html#systemProxyForQuery)（）函数。

**Warning:**根据用户的系统配置，使用在某些平台上系统代理的功能可能会受到限制。该[systemProxyForQuery](qnetworkproxyfactory.html#systemProxyForQuery)（ ）文档中包含的这些限制对于那些受影响的平台列表。

* * *

## Method Documentation

```
QNetworkProxyFactory.__init__ (self)
```

创建[QNetworkProxyFactory](qnetworkproxyfactory.html)对象。

自[QNetworkProxyFactory](qnetworkproxyfactory.html)是一个抽象类，你不能创建类型的对象[QNetworkProxyFactory](qnetworkproxyfactory.html)直接。

```
QNetworkProxyFactory.__init__ (self, QNetworkProxyFactory)
```

```
list-of-QNetworkProxy QNetworkProxyFactory.proxyForQuery (QNetworkProxyQuery query)
```

这个函数接受查询请求，_query_，检查插座或请求的类型的详细信息，并返回一个列表[QNetworkProxy](qnetworkproxy.html)对象表示要使用的代理服务器，按优先顺序。

```
list-of-QNetworkProxy QNetworkProxyFactory.queryProxy (self, QNetworkProxyQuery query = QNetworkProxyQuery())
```

这种方法是抽象的，应在任何子类中重新实现。

这个函数接受查询请求，_query_，检查插座或请求的类型的详细信息，并返回一个列表[QNetworkProxy](qnetworkproxy.html)对象表示要使用的代理服务器，按优先顺序。

当重新实现这个类，照顾到返回至少一个元素。

如果你不能确定一个更好的指标替代，使用[QNetworkProxy.DefaultProxy](qnetworkproxy.html#ProxyType-enum)，它告诉在查询代理来使用更高的替代的代码。举例来说，如果这家工厂被设置为[QNetworkAccessManager](qnetworkaccessmanager.html)对象， DefaultProxy会告诉它来查询应用程序级代理设置。

如果这家工厂被设置为应用程序代理工厂， DefaultProxy和NoProxy将具有相同的含义。

```
QNetworkProxyFactory.setApplicationProxyFactory (QNetworkProxyFactory factory)
```

该_factory_说法有它的所有权转移给Qt的。

设置应用程序范围内的代理工厂是_factory_。此功能需要该对象的所有权，并在必要时将其删除。

应用范围的代理作为最后手段时返回的所有其他选择代理请求[QNetworkProxy.DefaultProxy](qnetworkproxy.html#ProxyType-enum)。例如，[QTcpSocket](qtcpsocket.html)对象可以有一个代理设置QTcpSocket.setProxy ，但如果没有设置，代理工厂类在此项功能设置将会被查询。

如果您设置了代理工厂使用此功能，设置QNetworkProxy.setApplicationProxy任何应用程序级代理将被改写。

**See also** [QNetworkProxy.setApplicationProxy](qnetworkproxy.html#setApplicationProxy)（ ）[QAbstractSocket.proxy](qabstractsocket.html#proxy)（）和[QAbstractSocket.setProxy](qabstractsocket.html#setProxy)（ ） 。

```
QNetworkProxyFactory.setUseSystemConfiguration (bool enable)
```

允许使用特定于平台的代理服务器设置，只有那些。看[systemProxyForQuery](qnetworkproxyfactory.html#systemProxyForQuery)（ ）获取更多信息。

在内部，与调用时这个方法（_enable_设置为True ）设置一个应用程序范围的代理工厂。由于这个原因，这种方法是相互排斥的[setApplicationProxyFactory](qnetworkproxyfactory.html#setApplicationProxyFactory)（ ） ：调用[setApplicationProxyFactory](qnetworkproxyfactory.html#setApplicationProxyFactory)（ ）会复盖系统的使用范围内的代理，并调用setUseSystemConfiguration （）将复盖先前设置的任何应用程序代理或代理工厂。

**Note:**请参阅[systemProxyForQuery](qnetworkproxyfactory.html#systemProxyForQuery)（）文档中的限制与使用系统代理列表。

此功能被引入Qt的4.6 。

```
list-of-QNetworkProxy QNetworkProxyFactory.systemProxyForQuery (QNetworkProxyQuery query = QNetworkProxyQuery())
```

这个函数接受查询请求，_query_，检查插座或请求的类型的详细信息，并返回一个列表[QNetworkProxy](qnetworkproxy.html)对象表示要使用的代理服务器，按优先顺序。

此功能可用于确定特定于平台的代理服务器设置。此函数将使用由操作系统提供的库来确定代理对于一个给定的连接，如果这样的库存。如果他们不这样做，这个函数将只返回一个[QNetworkProxy](qnetworkproxy.html)类型[QNetworkProxy.NoProxy](qnetworkproxy.html#ProxyType-enum)。

在Windows上，这个功能将使用WinHTTP的DLL函数。尽管它的名字，微软建议使用它需要网络连接的所有应用程序，而不仅限于HTTP 。这将尊重注册表与Proxycfg.exe工具设定的代理服务器设置。如果找不到这些设置，此功能将尝试获取Internet Explorer的设置和使用它们。

在MacOS X ，这个函数将使用来自苹果的SystemConfiguration中框架获得代理设置。它将应用FTP，HTTP和HTTPS代理配置包含协议标籤“ ftp”的疑问， “ http”和“ https”开头，分别为。如果SOCKS代理在该配置中启用，该功能将使用SOCKS服务器的所有查询。如果SOCKS没有启用，它会使用HTTPS代理所有的TCPSocket和的URLRequest查询。

黑莓，这个函数获取代理服务器设置为使用系统配置的默认配置。类型将根据协议标籤“ http”的设定，以“https ”，“ ftp”的分别。默认情况下，它假定HTTP类型。代理服务器的用户名和密码，使用系统配置在查询过程中也设置。

在其他系统上，此功能将拿起代理设置从“ HTTP_PROXY ”环境变量。此变量必须使用下列方案之一的URL ： “ HTTP ” ， “ SOCKS5 ”或“ socks5h ” 。

#### Limitations

这些都为这功能的当前版本的限制。 Qt的未来版本可能会解除一些在这里列出的限制。

*   On MacOS X, this function will ignore the Proxy Auto Configuration settings, since it cannot execute the associated ECMAScript code.
*   On Windows platforms, this function may take several seconds to execute depending on the configuration of the user's system.

    **`\li`**黑莓，只有的URLRequest和的TCPSocket查询的支持。不支持SOCKS 。该代理凭据仅撷取的默认配置。