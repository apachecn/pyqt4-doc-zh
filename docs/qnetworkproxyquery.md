# QNetworkProxyQuery Class Reference

## [[QtNetwork](index.htm) module]

该QNetworkProxyQuery类用于查询套接字的代理服务器设置[More...](#details)

### Types

*   `enum QueryType { TcpSocket, UdpSocket, TcpServer, UrlRequest }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QUrl requestUrl, QueryType type = QNetworkProxyQuery.UrlRequest)`
*   `__init__ (self, QString hostname, int port, QString protocolTag = QString(), QueryType type = QNetworkProxyQuery.TcpSocket)`
*   `__init__ (self, int bindPort, QString protocolTag = QString(), QueryType type = QNetworkProxyQuery.TcpServer)`
*   `__init__ (self, QNetworkConfiguration networkConfiguration, QUrl requestUrl, QueryType queryType = QNetworkProxyQuery.UrlRequest)`
*   `__init__ (self, QNetworkConfiguration networkConfiguration, QString hostname, int port, QString protocolTag = QString(), QueryType type = QNetworkProxyQuery.TcpSocket)`
*   `__init__ (self, QNetworkConfiguration networkConfiguration, int bindPort, QString protocolTag = QString(), QueryType type = QNetworkProxyQuery.TcpServer)`
*   `__init__ (self, QNetworkProxyQuery other)`
*   `int localPort (self)`
*   `QNetworkConfiguration networkConfiguration (self)`
*   `QString peerHostName (self)`
*   `int peerPort (self)`
*   `QString protocolTag (self)`
*   `QueryType queryType (self)`
*   `setLocalPort (self, int port)`
*   `setNetworkConfiguration (self, QNetworkConfiguration networkConfiguration)`
*   `setPeerHostName (self, QString hostname)`
*   `setPeerPort (self, int port)`
*   `setProtocolTag (self, QString protocolTag)`
*   `setQueryType (self, QueryType type)`
*   `setUrl (self, QUrl url)`
*   `QUrl url (self)`

### Special Methods

*   `bool __eq__ (self, QNetworkProxyQuery other)`
*   `bool __ne__ (self, QNetworkProxyQuery other)`

* * *

## Detailed Description

该QNetworkProxyQuery类用于查询套接字的代理服务器设置

QNetworkProxyQuery持有被创建一个套接字，或正在取得请求的详细信息。它是利用[QNetworkProxy](qnetworkproxy.html)和[QNetworkProxyFactory](qnetworkproxyfactory.html)允许应用程序有一个更细粒度控制哪些代理服务器的使用，根据查询的详细信息。这使得应用程序可以应用不同的设置，根据该协议或目的地的主机名，例如。

QNetworkProxyQuery支持用于选择代理以下条件：

*   the type of query
*   the local port number to use
*   the destination host name
*   the destination port number
*   the protocol name, such as "http" or "ftp"
*   the URL being requested

目标主机名称是在即将离任的连接插座的情况下，连接的主机。它是`hostName`传递给参数[QTcpSocket.connectToHost](qabstractsocket.html#connectToHost)（）或要求与URL的主机组件[QNetworkRequest](qnetworkrequest.html)。

目的端口号是请求的端口连接到在传出插座的情况下，而本地端口号是socket希望尝试进行外部连接之前在本地使用的端口。在大多数情况下，本地端口号用于监听套接字只（[QTcpSocket](qtcpsocket.html)）或数据报套接字（[QUdpSocket](qudpsocket.html)） 。

协议名称是一个任意的字符串，它表示连接正在尝试的类型。例如，它可以匹配URL的模式，就是“http ” ， “ https”开头和“ FTP ” 。在大多数情况下，该代理选择不会取决于协议改变，但是这个信息被提供的情况下更好的选择可以由，例如用于基于HTTP的连接选择一个高速缓存的HTTP代理服务器，但对于所有其他功能更强大的SOCKSv5代理。

网络配置指定要使用的配置，当承载管理使用。例如在手机中的代理设置可能是不同的蜂窝网络与WLAN 。

有些标准可能是没有意义的所有的查询类型。下面的表列出了最常用的标准，根据查询的类型。

| Query type | Description |
| --- | --- |
| [TcpSocket](qnetworkproxyquery.html#QueryType-enum) | Normal sockets requesting a connection to a remote server, like [QTcpSocket](qtcpsocket.html). The peer hostname and peer port match the values passed to [QTcpSocket.connectToHost](qabstractsocket.html#connectToHost)(). The local port is usually -1, indicating the socket has no preference in which port should be used. The URL component is not used. |
| [UdpSocket](qnetworkproxyquery.html#QueryType-enum) | Datagram-based sockets, which can both send and receive. The local port, remote host or remote port fields can all be used or be left unused, depending on the characteristics of the socket. The URL component is not used. |
| [TcpServer](qnetworkproxyquery.html#QueryType-enum) | Passive server sockets that listen on a port and await incoming connections from the network. Normally, only the local port is used, but the remote address could be used in specific circumstances, for example to indicate which remote host a connection is expected from. The URL component is not used. |
| [UrlRequest](qnetworkproxyquery.html#QueryType-enum) | A more high-level request, such as those coming from [QNetworkAccessManager](qnetworkaccessmanager.html). These requests will inevitably use an outgoing TCP socket, but the this query type is provided to indicate that more detailed information is present in the URL component. For ease of implementation, the URL's host and port are set as the destination address. |

但应注意的是，任何一个规则可能会丢失或未知（空[QString](qstring.html)对于主机名或协议名称， -1为端口号） 。如果出现这种情况，执行查询的功能应该让他们的最好的猜测或应用某些实现定义的默认值。

* * *

## Type Documentation

```
QNetworkProxyQuery.QueryType
```

描述1的类型[QNetworkProxyQuery](qnetworkproxyquery.html)查询。

| Constant | Value | Description |
| --- | --- | --- |
| `QNetworkProxyQuery.TcpSocket` | `0` | 一个正常的，传出TCP套接字 |
| `QNetworkProxyQuery.UdpSocket` | `1` | 一个基于数据报的UDP套接字，它可以发送到多个目的地 |
| `QNetworkProxyQuery.TcpServer` | `100` | 用于侦听来自网络的传入连接TCP服务器 |
| `QNetworkProxyQuery.UrlRequest` | `101` | 一个更复杂的要求，涉及装载的URL |

**See also** [queryType](qnetworkproxyquery.html#queryType)（）和[setQueryType](qnetworkproxyquery.html#setQueryType)（ ） 。

* * *

## Method Documentation

```
QNetworkProxyQuery.__init__ (self)
```

构造一个默认的[QNetworkProxyQuery](qnetworkproxyquery.html)对象。默认情况下，查询类型将是[QNetworkProxyQuery.TcpSocket](qnetworkproxyquery.html#QueryType-enum)。

```
QNetworkProxyQuery.__init__ (self, QUrl requestUrl, QueryType type = QNetworkProxyQuery.UrlRequest)
```

构造一个[QNetworkProxyQuery](qnetworkproxyquery.html)与URL_requestUrl_并设置查询类型_queryType_。

**See also** [protocolTag](qnetworkproxyquery.html#protocolTag)（ ）[peerHostName](qnetworkproxyquery.html#peerHostName)（）和[peerPort](qnetworkproxyquery.html#peerPort)（ ） 。

```
QNetworkProxyQuery.__init__ (self, QString hostname, int port, QString protocolTag = QString(), QueryType type = QNetworkProxyQuery.TcpSocket)
```

构造一个[QNetworkProxyQuery](qnetworkproxyquery.html)类型_queryType_并将协议标籤是_protocolTag_。此构造适合[QNetworkProxyQuery.TcpSocket](qnetworkproxyquery.html#QueryType-enum)查询，因为它设置了对主机名_hostname_而到同行的端口号_port_。

```
QNetworkProxyQuery.__init__ (self, int bindPort, QString protocolTag = QString(), QueryType type = QNetworkProxyQuery.TcpServer)
```

构造一个[QNetworkProxyQuery](qnetworkproxyquery.html)类型_queryType_并将协议标籤是_protocolTag_。此构造适合[QNetworkProxyQuery.TcpSocket](qnetworkproxyquery.html#QueryType-enum)查询，因为它设置的本地端口号_bindPort_。

需要注意的是_bindPort_是类型quint16的指示所请求的具体的端口号。在此上下文中是不允许的-1 （未知）的值。

**See also** [localPort](qnetworkproxyquery.html#localPort)（ ） 。

```
QNetworkProxyQuery.__init__ (self, QNetworkConfiguration networkConfiguration, QUrl requestUrl, QueryType queryType = QNetworkProxyQuery.UrlRequest)
```

构造一个[QNetworkProxyQuery](qnetworkproxyquery.html)对象，它是一个拷贝_other_。

```
QNetworkProxyQuery.__init__ (self, QNetworkConfiguration networkConfiguration, QString hostname, int port, QString protocolTag = QString(), QueryType type = QNetworkProxyQuery.TcpSocket)
```

构造一个[QNetworkProxyQuery](qnetworkproxyquery.html)与URL_requestUrl_并设置查询类型_queryType_。指定_networkConfiguration_用于解析代理服务器设置。

此功能被引入Qt的4.8 。

**See also** [protocolTag](qnetworkproxyquery.html#protocolTag)（ ）[peerHostName](qnetworkproxyquery.html#peerHostName)（ ）[peerPort](qnetworkproxyquery.html#peerPort)（）和[networkConfiguration](qnetworkproxyquery.html#networkConfiguration)（ ） 。

```
QNetworkProxyQuery.__init__ (self, QNetworkConfiguration networkConfiguration, int bindPort, QString protocolTag = QString(), QueryType type = QNetworkProxyQuery.TcpServer)
```

构造一个[QNetworkProxyQuery](qnetworkproxyquery.html)类型_queryType_并将协议标籤是_protocolTag_。此构造适合[QNetworkProxyQuery.TcpSocket](qnetworkproxyquery.html#QueryType-enum)查询，因为它设置了对主机名_hostname_而到同行的端口号_port_。指定_networkConfiguration_用于解析代理服务器设置。

此功能被引入Qt的4.8 。

**See also** [networkConfiguration](qnetworkproxyquery.html#networkConfiguration)（ ） 。

```
QNetworkProxyQuery.__init__ (self, QNetworkProxyQuery other)
```

构造一个[QNetworkProxyQuery](qnetworkproxyquery.html)类型_queryType_并将协议标籤是_protocolTag_。此构造适合[QNetworkProxyQuery.TcpSocket](qnetworkproxyquery.html#QueryType-enum)查询，因为它设置的本地端口号_bindPort_。指定_networkConfiguration_用于解析代理服务器设置。

需要注意的是_bindPort_是类型quint16的指示所请求的具体的端口号。在此上下文中是不允许的-1 （未知）的值。

此功能被引入Qt的4.8 。

**See also** [localPort](qnetworkproxyquery.html#localPort)（）和[networkConfiguration](qnetworkproxyquery.html#networkConfiguration)（ ） 。

```
int QNetworkProxyQuery.localPort (self)
```

返回套接字将接受来自远程服务器的入站数据包或-1，如果该端口是不知道的端口号。

**See also** [peerPort](qnetworkproxyquery.html#peerPort)（ ）[peerHostName](qnetworkproxyquery.html#peerHostName)（）和[setLocalPort](qnetworkproxyquery.html#setLocalPort)（ ） 。

```
QNetworkConfiguration QNetworkProxyQuery.networkConfiguration (self)
```

[

返回代理查询的网络配置。

](qnetworkconfiguration.html)

[**See also**](qnetworkconfiguration.html) [setNetworkConfiguration](qnetworkproxyquery.html#setNetworkConfiguration)（ ） 。

```
QString QNetworkProxyQuery.peerHostName (self)
```

返回的主机名或所要求的出站连接的IP地址为，或如果远程主机名不知道一个空字符串。

如果查询的类型是[QNetworkProxyQuery.UrlRequest](qnetworkproxyquery.html#QueryType-enum)，这个函数返回所请求的URL的主机组件。

**See also** [peerPort](qnetworkproxyquery.html#peerPort)（ ）[localPort](qnetworkproxyquery.html#localPort)（）和[setPeerHostName](qnetworkproxyquery.html#setPeerHostName)（ ） 。

```
int QNetworkProxyQuery.peerPort (self)
```

返回传出请求或端口号-1，如果端口号是不知道。

如果查询的类型是[QNetworkProxyQuery.UrlRequest](qnetworkproxyquery.html#QueryType-enum)，这个函数返回所请求的URL的端口号。一般情况下，框架将在端口号填入的默认值。

**See also** [peerHostName](qnetworkproxyquery.html#peerHostName)（ ）[localPort](qnetworkproxyquery.html#localPort)（）和[setPeerPort](qnetworkproxyquery.html#setPeerPort)（ ） 。

```
QString QNetworkProxyQuery.protocolTag (self)
```

返回此协议标籤[QNetworkProxyQuery](qnetworkproxyquery.html)对象，或空[QString](qstring.html)的情况下的协议标籤是未知的。

在类型的查询的情况下，[QNetworkProxyQuery.UrlRequest](qnetworkproxyquery.html#QueryType-enum)，这个函数返回的URL的模式组件的值。

**See also** [setProtocolTag](qnetworkproxyquery.html#setProtocolTag)（）和[url](qnetworkproxyquery.html#url)（ ） 。

```
QueryType QNetworkProxyQuery.queryType (self)
```

[

返回的查询类型。

](qnetworkproxyquery.html#QueryType-enum)

[**See also**](qnetworkproxyquery.html#QueryType-enum) [setQueryType](qnetworkproxyquery.html#setQueryType)（ ） 。

```
QNetworkProxyQuery.setLocalPort (self, int port)
```

设置套接字希望使用本地接受来自远程服务器的入站数据包的端口号_port_。本地端口是最经常与使用[QNetworkProxyQuery.TcpServer](qnetworkproxyquery.html#QueryType-enum)和[QNetworkProxyQuery.UdpSocket](qnetworkproxyquery.html#QueryType-enum)查询类型。

有效值为0到65535 （ 0表示任意端口号是可以接受的）或-1 ，这意味着本地端口号是未知或不适用的。

在某些情况下，对于特殊协议，它的本地端口号也可以用类型的查询中使用[QNetworkProxyQuery.TcpSocket](qnetworkproxyquery.html#QueryType-enum)。当发生这种情况时，插座表明它希望使用的端口号_port_连接到远程主机时。

**See also** [localPort](qnetworkproxyquery.html#localPort)（ ）[setPeerPort](qnetworkproxyquery.html#setPeerPort)（）和[setPeerHostName](qnetworkproxyquery.html#setPeerHostName)（ ） 。

```
QNetworkProxyQuery.setNetworkConfiguration (self, QNetworkConfiguration networkConfiguration)
```

设置这个网络配置组件[QNetworkProxyQuery](qnetworkproxyquery.html)反对是_networkConfiguration_。网络配置可以被用来返回基于在网络中使用不同的代理设置，例如WLAN与手机的蜂窝网络。

在“选择用户”或“服务网络”配置的情况下，你应该先启动[QNetworkSession](qnetworksession.html)从它的属性得到有效配置。

此功能被引入Qt的4.8 。

**See also** [networkConfiguration](qnetworkproxyquery.html#networkConfiguration)（ ） 。

```
QNetworkProxyQuery.setPeerHostName (self, QString hostname)
```

设置的出站连接被请求的主机名_hostname_。一个空的主机名可以被用来指示该远程主机是未知的。

对端的主机名，也可以用于指示在的情况下的输入连接的预期源地址[QNetworkProxyQuery.UdpSocket](qnetworkproxyquery.html#QueryType-enum) or [QNetworkProxyQuery.TcpServer](qnetworkproxyquery.html#QueryType-enum)查询类型。

**See also** [peerHostName](qnetworkproxyquery.html#peerHostName)（ ）[setPeerPort](qnetworkproxyquery.html#setPeerPort)（）和[setLocalPort](qnetworkproxyquery.html#setLocalPort)（ ） 。

```
QNetworkProxyQuery.setPeerPort (self, int port)
```

设置用于传出连接是请求的端口号_port_。有效值为1到65535 ，或-1 ，表明远程端口号是未知的。

对端的端口号也可以用来指示在的情况下的输入连接的预期端口号[QNetworkProxyQuery.UdpSocket](qnetworkproxyquery.html#QueryType-enum) or [QNetworkProxyQuery.TcpServer](qnetworkproxyquery.html#QueryType-enum)查询类型。

**See also** [peerPort](qnetworkproxyquery.html#peerPort)（ ）[setPeerHostName](qnetworkproxyquery.html#setPeerHostName)（）和[setLocalPort](qnetworkproxyquery.html#setLocalPort)（ ） 。

```
QNetworkProxyQuery.setProtocolTag (self, QString protocolTag)
```

设置此协议标籤[QNetworkProxyQuery](qnetworkproxyquery.html)反对是_protocolTag_。

该协议的电子标籤是一个任意的字符串，指示该协议正在谈论过插座，如“ HTTP ” ， “ XMPP ” ， “远程登录” ，等等。协议标记是用于后端返回的要求是比较具体的有问题的协议：例如，一个HTTP连接可以使用缓存的HTTP代理服务器，而其他所有连接都使用一个更强大的SOCKSv5代理服务器。

**See also** [protocolTag](qnetworkproxyquery.html#protocolTag)（ ） 。

```
QNetworkProxyQuery.setQueryType (self, QueryType type)
```

设置为这个对象的查询类型_type_。

**See also** [queryType](qnetworkproxyquery.html#queryType)（ ） 。

```
QNetworkProxyQuery.setUrl (self, QUrl url)
```

设置这个网址组件[QNetworkProxyQuery](qnetworkproxyquery.html)反对是_url_。设置URL也将设置协议标籤，远程主机名和端口号。这样做是为了以方便的代码，用于确定要使用的代理服务器的执行。

**See also** [url](qnetworkproxyquery.html#url)（ ）[peerHostName](qnetworkproxyquery.html#peerHostName)（）和[peerPort](qnetworkproxyquery.html#peerPort)（ ） 。

```
QUrl QNetworkProxyQuery.url (self)
```

[](qurl.html)

[返回此网址组件](qurl.html)[QNetworkProxyQuery](qnetworkproxyquery.html)在案件类型的查询对象[QNetworkProxyQuery.UrlRequest](qnetworkproxyquery.html#QueryType-enum)。

**See also** [setUrl](qnetworkproxyquery.html#setUrl)（ ） 。

```
bool QNetworkProxyQuery.__eq__ (self, QNetworkProxyQuery other)
```

```
bool QNetworkProxyQuery.__ne__ (self, QNetworkProxyQuery other)
```