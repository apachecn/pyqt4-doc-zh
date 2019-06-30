# QTcpServer Class Reference

## [[QtNetwork](index.htm) module]

该QTcpServer既可类提供了一个基于TCP的服务器。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `addPendingConnection (self, QTcpSocket socket)`
*   `close (self)`
*   `QString errorString (self)`
*   `bool hasPendingConnections (self)`
*   `incomingConnection (self, int handle)`
*   `bool isListening (self)`
*   `bool listen (self, QHostAddress address = QHostAddress.Any, int port = 0)`
*   `int maxPendingConnections (self)`
*   `QTcpSocket nextPendingConnection (self)`
*   `QNetworkProxy proxy (self)`
*   `QHostAddress serverAddress (self)`
*   `QAbstractSocket.SocketError serverError (self)`
*   `int serverPort (self)`
*   `setMaxPendingConnections (self, int numConnections)`
*   `setProxy (self, QNetworkProxy networkProxy)`
*   `bool setSocketDescriptor (self, int socketDescriptor)`
*   `int socketDescriptor (self)`
*   `(bool, bool timedOut) waitForNewConnection (self, int msecs = 0)`

### Qt Signals

*   `void newConnection ()`

* * *

## Detailed Description

该QTcpServer既可类提供了一个基于TCP的服务器。

这个类使得它可以接受传入的TCP连接。您可以指定端口或有QTcpServer既可选择一个自动。你可以监听一个特定的地址或所有机器的地址。

Call [listen](qtcpserver.html#listen)（ ）使服务器侦听传入的连接。该[newConnection](qtcpserver.html#newConnection)（ ）信号，然后每个客户端连接到服务器时发出的。

Call [nextPendingConnection](qtcpserver.html#nextPendingConnection)（ ）接受挂起的连接作为一个连接[QTcpSocket](qtcpsocket.html)。该函数返回一个指针，指向一个[QTcpSocket](qtcpsocket.html)在[QAbstractSocket.ConnectedState](qabstractsocket.html#SocketState-enum)您可以使用与客户端通信。

如果发生错误，[serverError](qtcpserver.html#serverError)（）返回的错误的类型，并且[errorString](qtcpserver.html#errorString)（ ）可以被调用来获取发生了什么可读的描述。

当侦听连接的地址和端口的服务器正在监听可作为[serverAddress](qtcpserver.html#serverAddress)（）和[serverPort](qtcpserver.html#serverPort)（ ） 。

调用[close](qtcpserver.html#close)（ ）使得QTcpServer既可停止侦听传入的连接。

虽然QTcpServer既可主要是设计用于与一个事件循环使用，它可以使用它没有之一。在这种情况下，您必须使用[waitForNewConnection](qtcpserver.html#waitForNewConnection)（ ） ，这阻止，直到一个连接可用或者超时。

### Symbian Platform Security Requirements

在Symbian ，它使用这个类的进程必须有`NetworkServices`平台的安全能力。如果客户端程序缺乏这种能力，它会导致恐慌。

平台的安全功能是通过添加[TARGET.CAPABILITY](index.htm#target-capability)qmake的变量。

* * *

## Method Documentation

```
QTcpServer.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QTcpServer](qtcpserver.html)对象。

_parent_被传递到[QObject](qobject.html)构造函数。

**See also** [listen](qtcpserver.html#listen)（）和[setSocketDescriptor](qtcpserver.html#setSocketDescriptor)（ ） 。

```
QTcpServer.addPendingConnection (self, QTcpSocket socket)
```

调用此函数由[QTcpServer.incomingConnection](qtcpserver.html#incomingConnection)（ ）来添加_socket_要挂起传入连接的列表。

**Note:**不要忘了从重新实现调用这个成员[incomingConnection](qtcpserver.html#incomingConnection)（）如果你不想打破挂起连接机制。

此功能被引入Qt的4.7 。

**See also** [incomingConnection](qtcpserver.html#incomingConnection)（ ） 。

```
QTcpServer.close (self)
```

关闭服务器。该服务器将不再侦听传入的连接。

**See also** [listen](qtcpserver.html#listen)（ ） 。

```
QString QTcpServer.errorString (self)
```

返回上次发生错误的可读描述。

**See also** [serverError](qtcpserver.html#serverError)（ ） 。

```
bool QTcpServer.hasPendingConnections (self)
```

返回True ，如果服务器有一个挂起的连接，否则返回False 。

**See also** [nextPendingConnection](qtcpserver.html#nextPendingConnection)（）和[setMaxPendingConnections](qtcpserver.html#setMaxPendingConnections)（ ） 。

```
QTcpServer.incomingConnection (self, int handle)
```

这个虚函数被调用[QTcpServer](qtcpserver.html)当一个新的连接可用。该_socketDescriptor_参数是为接受的连接的本地套接字描述符。

该基地实现创建一个[QTcpSocket](qtcpsocket.html)，设置套接字描述符，然后存储[QTcpSocket](qtcpsocket.html)在挂起连接的内部清单。最后[newConnection](qtcpserver.html#newConnection)（）被发射。

重新实现这个函数来改变服务器的行为，当一个连接可用。

如果该服务器使用[QNetworkProxy](qnetworkproxy.html)那么_socketDescriptor_可能与原生socket函数使用，并且只应使用[QTcpSocket.setSocketDescriptor](qabstractsocket.html#setSocketDescriptor)（ ） 。

**Note:**如果你想处理的新传入的连接[QTcpSocket](qtcpsocket.html)在另一个线程对象，你必须将socketDescriptor传递给其他线程，并创建[QTcpSocket](qtcpsocket.html)有对象并使用其[setSocketDescriptor](qtcpserver.html#setSocketDescriptor)（）方法。

**See also** [newConnection](qtcpserver.html#newConnection)（ ）[nextPendingConnection](qtcpserver.html#nextPendingConnection)（）和[addPendingConnection](qtcpserver.html#addPendingConnection)（ ） 。

```
bool QTcpServer.isListening (self)
```

返回True如果服务器当前正在侦听传入连接，否则返回False 。

**See also** [listen](qtcpserver.html#listen)（ ） 。

```
bool QTcpServer.listen (self, QHostAddress address = QHostAddress.Any, int port = 0)
```

告诉服务器监听的地址传入的连接_address_和端口_port_。如果_port_为0 ，端口会自动选择。如果_address_ is [QHostAddress.Any](qhostaddress.html#SpecialAddress-enum)，服务器将监听所有网络接口。

成功时返回TRUE ，否则返回False 。

**See also** [isListening](qtcpserver.html#isListening)（ ） 。

```
int QTcpServer.maxPendingConnections (self)
```

返回未决接受的连接的最大数目。默认值是30 。

**See also** [setMaxPendingConnections](qtcpserver.html#setMaxPendingConnections)（）和[hasPendingConnections](qtcpserver.html#hasPendingConnections)（ ） 。

```
QTcpSocket QTcpServer.nextPendingConnection (self)
```

[](qtcpsocket.html)

[返回的连接下一个待连接](qtcpsocket.html)[QTcpSocket](qtcpsocket.html)对象。

套接字被作为服务器的一个子创建的，这意味着它被自动删除时[QTcpServer](qtcpserver.html)对象被销毁。它仍然是一个好主意，明确地删除的对象，当你用它做，以避免浪费内存。

如果这个函数被调用时，有没有挂起的连接则返回0 。

**Note:**返回[QTcpSocket](qtcpsocket.html)对象不能被用于从另一个线程。如果你想使用从另一个线程传入的连接，你需要重写[incomingConnection](qtcpserver.html#incomingConnection)（ ） 。

**See also** [hasPendingConnections](qtcpserver.html#hasPendingConnections)（ ） 。

```
QNetworkProxy QTcpServer.proxy (self)
```

[](qnetworkproxy.html)

[返回此套接字的网络代理。默认情况下，](qnetworkproxy.html)[QNetworkProxy.DefaultProxy](qnetworkproxy.html#ProxyType-enum)被使用。

这个函数是Qt 4.1中引入。

**See also** [setProxy](qtcpserver.html#setProxy)（）和[QNetworkProxy](qnetworkproxy.html)。

```
QHostAddress QTcpServer.serverAddress (self)
```

[](qhostaddress.html)

[返回如果服务器正在监听等待连接的服务器的地址，否则返回](qhostaddress.html)[QHostAddress.Null](qhostaddress.html#SpecialAddress-enum)。

**See also** [serverPort](qtcpserver.html#serverPort)（）和[listen](qtcpserver.html#listen)（ ） 。

```
QAbstractSocket.SocketError QTcpServer.serverError (self)
```

[

所发生的最后一个错误返回一个错误代码。

](qabstractsocket.html#SocketError-enum)

[**See also**](qabstractsocket.html#SocketError-enum) [errorString](qtcpserver.html#errorString)（ ） 。

```
int QTcpServer.serverPort (self)
```

返回如果服务器侦听连接服务器的端口，否则返回0 。

**See also** [serverAddress](qtcpserver.html#serverAddress)（）和[listen](qtcpserver.html#listen)（ ） 。

```
QTcpServer.setMaxPendingConnections (self, int numConnections)
```

设置挂起接受的最大连接数_numConnections_。[QTcpServer](qtcpserver.html)将接受不超过_numConnections_前传入的连接[nextPendingConnection](qtcpserver.html#nextPendingConnection)（）被调用。默认情况下，该限制是30未决的连接。

客户可能仍然能够服务器后连接已经达到了挂起连接的最大数目（即，[QTcpSocket](qtcpsocket.html)依然能发出连接（ ）信号） 。[QTcpServer](qtcpserver.html)将停止接受新的连接，但操作系统仍可能保持他们在队列中。

**See also** [maxPendingConnections](qtcpserver.html#maxPendingConnections)（）和[hasPendingConnections](qtcpserver.html#hasPendingConnections)（ ） 。

```
QTcpServer.setProxy (self, QNetworkProxy networkProxy)
```

设置此套接字明确网络代理_networkProxy_。

要禁用使用代理的这个插座，使用[QNetworkProxy.NoProxy](qnetworkproxy.html#ProxyType-enum)代理类型：

```
 server->setProxy([QNetworkProxy](qnetworkproxy.html).NoProxy);

```

这个函数是Qt 4.1中引入。

**See also** [proxy](qtcpserver.html#proxy)（）和[QNetworkProxy](qnetworkproxy.html)。

```
bool QTcpServer.setSocketDescriptor (self, int socketDescriptor)
```

设置套接字描述符侦听传入的连接时，该服务器应该使用_socketDescriptor_。返回True如果套接字设置成功，否则返回False 。

该插座被假定为处于监听状态。

**See also** [socketDescriptor](qtcpserver.html#socketDescriptor)（）和[isListening](qtcpserver.html#isListening)（ ） 。

```
int QTcpServer.socketDescriptor (self)
```

返回服务器用来侦听传入的指令，或-1，如果服务器没有监听本地套接字描述符。

如果服务器使用[QNetworkProxy](qnetworkproxy.html)，返回的描述符可能无法与原生socket函数使用。

**See also** [setSocketDescriptor](qtcpserver.html#setSocketDescriptor)（）和[isListening](qtcpserver.html#isListening)（ ） 。

```
(bool, bool timedOut) QTcpServer.waitForNewConnection (self, int msecs = 0)
```

最多等待_msec_毫秒或直到传入的连接是可用的。返回True如果连接可用，否则返回False 。如果操作超时，_timedOut_不为0， *_timedOut_将被设置为True。

这是一个阻塞函数调用。它的使用disadvised在一个单线程的GUI应用程序，因为整个应用程序将停止响应，直到函数返回。当没有事件循环可用waitForNewConnection （ ）是最有用。

非阻塞的替代方法是连接到[newConnection](qtcpserver.html#newConnection)（）信号。

如果毫秒为-1 ，此功能将不会超时。

**See also** [hasPendingConnections](qtcpserver.html#hasPendingConnections)（）和[nextPendingConnection](qtcpserver.html#nextPendingConnection)（ ） 。

* * *

## Qt Signal Documentation

```
void newConnection ()
```

这是该信号的默认超载。

每当一个新的连接是可用的，这个信号被发射。

**See also** [hasPendingConnections](qtcpserver.html#hasPendingConnections)（）和[nextPendingConnection](qtcpserver.html#nextPendingConnection)（ ） 。