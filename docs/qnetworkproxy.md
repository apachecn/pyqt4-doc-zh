# QNetworkProxy Class Reference

## [[QtNetwork](index.htm) module]

该QNetworkProxy类提供了网络层的代理。[More...](#details)

### Types

*   `class **[Capabilities](index.htm)**`
*   `enum Capability { TunnelingCapability, ListeningCapability, UdpTunnelingCapability, CachingCapability, HostNameLookupCapability }`
*   `enum ProxyType { DefaultProxy, Socks5Proxy, NoProxy, HttpProxy, HttpCachingProxy, FtpCachingProxy }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, ProxyType type, QString hostName = QString(), int port = 0, QString user = QString(), QString password = QString())`
*   `__init__ (self, QNetworkProxy other)`
*   `Capabilities capabilities (self)`
*   `QString hostName (self)`
*   `bool isCachingProxy (self)`
*   `bool isTransparentProxy (self)`
*   `QString password (self)`
*   `int port (self)`
*   `setCapabilities (self, Capabilities capab)`
*   `setHostName (self, QString hostName)`
*   `setPassword (self, QString password)`
*   `setPort (self, int port)`
*   `setType (self, ProxyType type)`
*   `setUser (self, QString userName)`
*   `ProxyType type (self)`
*   `QString user (self)`

### Static Methods

*   `QNetworkProxy applicationProxy ()`
*   `setApplicationProxy (QNetworkProxy proxy)`

### Special Methods

*   `bool __eq__ (self, QNetworkProxy other)`
*   `bool __ne__ (self, QNetworkProxy other)`

* * *

## Detailed Description

该QNetworkProxy类提供了网络层的代理。

QNetworkProxy提供了方法来配置网络层代理支持Qt的网络类。目前支持的类[QAbstractSocket](qabstractsocket.html)，[QTcpSocket](qtcpsocket.html)，[QUdpSocket](qudpsocket.html)，[QTcpServer](qtcpserver.html)，[QNetworkAccessManager](qnetworkaccessmanager.html)和[QFtp](qftp.html)。该代理支持被设计成尽可能透明。这意味着，您已经编写现有的网络应用程序应该使用下面的代码支持自动网络代理。

```
 QNetworkProxy proxy;
 proxy.setType(QNetworkProxy.Socks5Proxy);
 proxy.setHostName("proxy.example.com");
 proxy.setPort(1080);
 proxy.setUser("username");
 proxy.setPassword("password");
 QNetworkProxy.setApplicationProxy(proxy);

```

另一种方法来设置应用程序范围的代理是用来指定单个插座代理[QAbstractSocket.setProxy](qabstractsocket.html#setProxy)（）和[QTcpServer.setProxy](qtcpserver.html#setProxy)（ ） 。以这种方式，有可能禁止使用使用以下代码具体套接字的代理：

```
 serverSocket->setProxy(QNetworkProxy.NoProxy);

```

网络代理不使用，如果所使用的地址[connectToHost()](qabstractsocket.html#connectToHost)，[bind()](qudpsocket.html#bind) or [listen()](qtcpserver.html#listen)相当于[QHostAddress.LocalHost](qhostaddress.html#SpecialAddress-enum) or [QHostAddress.LocalHostIPv6](qhostaddress.html#SpecialAddress-enum)。

每种类型的代理支持具有与之相关的某些限制。你应该阅读[ProxyType](qnetworkproxy.html#ProxyType-enum)文档谨慎选择代理类型使用之前。

**Note:**向当前连接的套接字更改不会生效。如果您需要更改连接的套接字，你应该重新连接。

### SOCKS5

socks5的支持Qt的4是基于[RFC 1928](http://www.rfc-editor.org/rfc/rfc1928.txt)和[RFC 1929](http://www.rfc-editor.org/rfc/rfc1929.txt)。支持的身份验证方法是没有身份验证和用户名/密码认证。 IPv4和IPv6的支持。域名是通过SOCKS5服务器解析，如果[QNetworkProxy.HostNameLookupCapability](qnetworkproxy.html#Capability-enum)被激活，否则它们是本地解析和IP地址被发送到服务器。有几件事情使用SOCKS5用时要记住[QUdpSocket](qudpsocket.html)和[QTcpServer](qtcpserver.html)：

With [QUdpSocket](qudpsocket.html)，调用[bind()](qudpsocket.html#bind)超时错误可能会失败。如果不是0的端口号传递给[bind()](qudpsocket.html#bind)，它不能保证它是指定的端口将被使用。使用[localPort()](qabstractsocket.html#localPort)和[localAddress()](qabstractsocket.html#localAddress)得到实际使用中的地址和端口号。因为代理的UDP经过两个UDP连接，它更可能是数据包将被丢弃。

With [QTcpServer](qtcpserver.html)调用[listen()](qtcpserver.html#listen)超时错误可能会失败。如果不是0的端口号传递给[listen()](qtcpserver.html#listen)的话，就不能保证它是指定的端口将被使用。使用[serverPort()](qtcpserver.html#serverPort)和[serverAddress()](qtcpserver.html#serverAddress)得到的实际地址和端口用于侦听连接。 SOCKS5只支持一个接受每个呼叫连接到[listen()](qtcpserver.html#listen)，并且每个呼叫很可能会导致不同的[serverPort()](qtcpserver.html#serverPort)被使用。

* * *

## Type Documentation

```
QNetworkProxy.Capability
```

这些标志指示一个给定的代理服务器支持的功能。

[QNetworkProxy](qnetworkproxy.html)默认情况下，设置不同的功能在创建对象时（见[QNetworkProxy.ProxyType](qnetworkproxy.html#ProxyType-enum)为默认值的列表） 。然而，这是可以改变capabitilies后的对象已经创建与[setCapabilities](qnetworkproxy.html#setCapabilities)（ ） 。

的功能，[QNetworkProxy](qnetworkproxy.html)支持有：

| Constant | Value | Description |
| --- | --- | --- |
| `QNetworkProxy.TunnelingCapability` | `0x0001` | 能够打开到远程主机透明，隧道TCP连接。代理服务器中继传输逐字从一个侧面向其他并不做任何缓存。 |
| `QNetworkProxy.ListeningCapability` | `0x0002` | 能够创建一个监听套接字，并等待来自远程主机传入的TCP连接。 |
| `QNetworkProxy.UdpTunnelingCapability` | `0x0004` | 能够通过代理服务器，并从远程主机中继的UDP数据报。 |
| `QNetworkProxy.CachingCapability` | `0x0008` | 能力来缓存传递的内容。这种能力是具体到每个协议和代理类型。例如， HTTP代理缓存可以用“GET”命令传送网络数据的内容。 |
| `QNetworkProxy.HostNameLookupCapability` | `0x0010` | 能够连接到执行查找上一个远程主机名，并连接到它，而不是要求应用程序执行名称查找，并要求连接到的IP地址只。 |

这个枚举被引入或修改的Qt 4.5 。

功能类型是一个typedef为[QFlags](index.htm)\u003cCapability\u003e 。它存储能力值的一个或组合。

```
QNetworkProxy.ProxyType
```

这个枚举变量描述的Qt提供的网络代理的类型。

有两种类型的代理Qt的理解：透明代理和缓存代理。第一组由代理服务器可以处理任意的数据传输，而第二个只能处理特定的请求。该缓存代理服务器才有意义的特定类，他们都可以使用。

| Constant | Value | Description |
| --- | --- | --- |
| `QNetworkProxy.NoProxy` | `2` | 无代理使用 |
| `QNetworkProxy.DefaultProxy` | `0` | 代理服务器是基于使用应用程序代理组确定[setApplicationProxy](qnetworkproxy.html#setApplicationProxy)（ ） |
| `QNetworkProxy.Socks5Proxy` | `1` | [Socks5](qnetworkproxy.html#socks5)代理使用 |
| `QNetworkProxy.HttpProxy` | `3` | HTTP透明代理时（此值是在4.3推出。 ） |
| `QNetworkProxy.HttpCachingProxy` | `4` | 代理HTTP请求只（这个值被引入4.4 。 ） |
| `QNetworkProxy.FtpCachingProxy` | `5` | 代理FTP请求只（这个值被引入4.4 。 ） |

下表列出了不同的代理类型和它们的功能。由于每个代理类型具有不同的功能，了解他们选择代理类型之前，是很重要的。

| Proxy type | Description | Default capabilities |
| --- | --- | --- |
| SOCKS 5 | Generic proxy for any kind of connection. Supports TCP, UDP, binding to a port (incoming connections) and authentication. | [TunnelingCapability](qnetworkproxy.html#Capability-enum), [ListeningCapability](qnetworkproxy.html#Capability-enum), [UdpTunnelingCapability](qnetworkproxy.html#Capability-enum), [HostNameLookupCapability](qnetworkproxy.html#Capability-enum) |
| HTTP | Implemented using the "CONNECT" command, supports only outgoing TCP connections; supports authentication. | [TunnelingCapability](qnetworkproxy.html#Capability-enum), [CachingCapability](qnetworkproxy.html#Capability-enum), [HostNameLookupCapability](qnetworkproxy.html#Capability-enum) |
| Caching-only HTTP | Implemented using normal HTTP commands, it is useful only in the context of HTTP requests (see [QNetworkAccessManager](qnetworkaccessmanager.html)) | [CachingCapability](qnetworkproxy.html#Capability-enum), [HostNameLookupCapability](qnetworkproxy.html#Capability-enum) |
| Caching FTP | Implemented using an FTP proxy, it is useful only in the context of FTP requests (see [QFtp](qftp.html), [QNetworkAccessManager](qnetworkaccessmanager.html)) | [CachingCapability](qnetworkproxy.html#Capability-enum), [HostNameLookupCapability](qnetworkproxy.html#Capability-enum) |

另外请注意，你不应该设置应用程序默认的代理（[setApplicationProxy](qnetworkproxy.html#setApplicationProxy)（ ））以不具有的代理[TunnelingCapability](qnetworkproxy.html#Capability-enum)能力。如果你这样做，[QTcpSocket](qtcpsocket.html)将不知道如何打开连接。

**See also** [setType](qnetworkproxy.html#setType)（ ）[type](qnetworkproxy.html#type)（ ）[capabilities](qnetworkproxy.html#capabilities)（）和[setCapabilities](qnetworkproxy.html#setCapabilities)（ ） 。

* * *

## Method Documentation

```
QNetworkProxy.__init__ (self)
```

构造一个[QNetworkProxy](qnetworkproxy.html)同[DefaultProxy](qnetworkproxy.html#ProxyType-enum)输入;代理类型是由确定[applicationProxy](qnetworkproxy.html#applicationProxy)（ ） ，默认为[NoProxy](qnetworkproxy.html#ProxyType-enum)。

**See also** [setType](qnetworkproxy.html#setType)（）和[setApplicationProxy](qnetworkproxy.html#setApplicationProxy)（ ） 。

```
QNetworkProxy.__init__ (self, ProxyType type, QString hostName = QString(), int port = 0, QString user = QString(), QString password = QString())
```

构造一个[QNetworkProxy](qnetworkproxy.html)同_type_，_hostName_，_port_，_user_和_password_。

对代理类型的默认功能_type_会自动设定。

**See also** [capabilities](qnetworkproxy.html#capabilities)（ ） 。

```
QNetworkProxy.__init__ (self, QNetworkProxy other)
```

构造的副本_other_。

```
QNetworkProxy QNetworkProxy.applicationProxy ()
```

[

返回应用程序级的网络代理。

](qnetworkproxy.html)

[如果](qnetworkproxy.html)[QAbstractSocket](qabstractsocket.html) or [QTcpSocket](qtcpsocket.html)有[QNetworkProxy.DefaultProxy](qnetworkproxy.html#ProxyType-enum)输入时，则[QNetworkProxy](qnetworkproxy.html)用于返回由该函数。

**See also** [QNetworkProxyFactory](qnetworkproxyfactory.html)，[setApplicationProxy](qnetworkproxy.html#setApplicationProxy)（ ）[QAbstractSocket.proxy](qabstractsocket.html#proxy)（）和[QTcpServer.proxy](qtcpserver.html#proxy)（ ） 。

```
Capabilities QNetworkProxy.capabilities (self)
```

[

返回此代理服务器的功能。

此功能被引入Qt的4.5 。

](index.htm)

[**See also**](index.htm) [setCapabilities](qnetworkproxy.html#setCapabilities)（）和[type](qnetworkproxy.html#type)（ ） 。

```
QString QNetworkProxy.hostName (self)
```

返回代理主机的主机名。

**See also** [setHostName](qnetworkproxy.html#setHostName)（ ）[setPort](qnetworkproxy.html#setPort)（）和[port](qnetworkproxy.html#port)（ ） 。

```
bool QNetworkProxy.isCachingProxy (self)
```

如果该代理支持，则返回True的[QNetworkProxy.CachingCapability](qnetworkproxy.html#Capability-enum)能力。

在Qt 4.4的能力被捆绑到代理类型，但由于Qt的4.5就可以通过调用从代理中删除高速缓存的能力[setCapabilities](qnetworkproxy.html#setCapabilities)（ ） 。

此功能被引入Qt的4.4 。

**See also** [capabilities](qnetworkproxy.html#capabilities)（ ）[type](qnetworkproxy.html#type)（）和[isTransparentProxy](qnetworkproxy.html#isTransparentProxy)（ ） 。

```
bool QNetworkProxy.isTransparentProxy (self)
```

如果该代理支持TCP连接的透明隧道，则返回True 。这符合[QNetworkProxy.TunnelingCapability](qnetworkproxy.html#Capability-enum)能力。

在Qt 4.4的能力被捆绑到代理类型，但由于Qt的4.5就可以通过调用从代理中删除高速缓存的能力[setCapabilities](qnetworkproxy.html#setCapabilities)（ ） 。

此功能被引入Qt的4.4 。

**See also** [capabilities](qnetworkproxy.html#capabilities)（ ）[type](qnetworkproxy.html#type)（）和[isCachingProxy](qnetworkproxy.html#isCachingProxy)（ ） 。

```
QString QNetworkProxy.password (self)
```

返回用于验证的密码。

**See also** [user](qnetworkproxy.html#user)（ ）[setPassword](qnetworkproxy.html#setPassword)（）和[setUser](qnetworkproxy.html#setUser)（ ） 。

```
int QNetworkProxy.port (self)
```

返回代理主机的端口。

**See also** [setHostName](qnetworkproxy.html#setHostName)（ ）[setPort](qnetworkproxy.html#setPort)（）和[hostName](qnetworkproxy.html#hostName)（ ） 。

```
QNetworkProxy.setApplicationProxy (QNetworkProxy proxy)
```

设置应用程序级的网络代理是_networkProxy_。

如果[QAbstractSocket](qabstractsocket.html) or [QTcpSocket](qtcpsocket.html)有[QNetworkProxy.DefaultProxy](qnetworkproxy.html#ProxyType-enum)输入时，则[QNetworkProxy](qnetworkproxy.html)设置使用此功能。如果你想确定哪个代理更多的灵活性，可以使用[QNetworkProxyFactory](qnetworkproxyfactory.html)类。

设置默认值的代理使用此功能将复盖应用程序代理工厂集与QNetworkProxyFactory.setApplicationProxyFactory 。

**See also** [QNetworkProxyFactory](qnetworkproxyfactory.html)，[applicationProxy](qnetworkproxy.html#applicationProxy)（ ）[QAbstractSocket.setProxy](qabstractsocket.html#setProxy)（）和[QTcpServer.setProxy](qtcpserver.html#setProxy)（ ） 。

```
QNetworkProxy.setCapabilities (self, Capabilities capab)
```

设置这个代理的功能，_capabilities_。

此功能被引入Qt的4.5 。

**See also** [setType](qnetworkproxy.html#setType)（）和[capabilities](qnetworkproxy.html#capabilities)（ ） 。

```
QNetworkProxy.setHostName (self, QString hostName)
```

设置代理主机是主机名_hostName_。

**See also** [hostName](qnetworkproxy.html#hostName)（ ）[setPort](qnetworkproxy.html#setPort)（）和[port](qnetworkproxy.html#port)（ ） 。

```
QNetworkProxy.setPassword (self, QString password)
```

设置密码代理身份验证是_password_。

**See also** [user](qnetworkproxy.html#user)（ ）[setUser](qnetworkproxy.html#setUser)（）和[password](qnetworkproxy.html#password)（ ） 。

```
QNetworkProxy.setPort (self, int port)
```

设置代理主机的端口为_port_。

**See also** [hostName](qnetworkproxy.html#hostName)（ ）[setHostName](qnetworkproxy.html#setHostName)（）和[port](qnetworkproxy.html#port)（ ） 。

```
QNetworkProxy.setType (self, ProxyType type)
```

设置为代理类型此实例_type_。

请注意，更改代理服务器的类型不改变设置的这个功能[QNetworkProxy](qnetworkproxy.html)如有能力已经设置对象持有[setCapabilities](qnetworkproxy.html#setCapabilities)（ ） 。

**See also** [type](qnetworkproxy.html#type)（）和[setCapabilities](qnetworkproxy.html#setCapabilities)（ ） 。

```
QNetworkProxy.setUser (self, QString userName)
```

设置代理身份验证是用户名_user_。

**See also** [user](qnetworkproxy.html#user)（ ）[setPassword](qnetworkproxy.html#setPassword)（）和[password](qnetworkproxy.html#password)（ ） 。

```
ProxyType QNetworkProxy.type (self)
```

[

返回代理类此实例。

](qnetworkproxy.html#ProxyType-enum)

[**See also**](qnetworkproxy.html#ProxyType-enum) [setType](qnetworkproxy.html#setType)（ ） 。

```
QString QNetworkProxy.user (self)
```

返回用于认证的用户名。

**See also** [setUser](qnetworkproxy.html#setUser)（ ）[setPassword](qnetworkproxy.html#setPassword)（）和[password](qnetworkproxy.html#password)（ ） 。

```
bool QNetworkProxy.__eq__ (self, QNetworkProxy other)
```

```
bool QNetworkProxy.__ne__ (self, QNetworkProxy other)
```