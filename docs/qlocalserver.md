# QLocalServer Class Reference

## [[QtNetwork](index.htm) module]

该QLocalServer类提供了一个基于本地套接字服务器。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `close (self)`
*   `QString errorString (self)`
*   `QString fullServerName (self)`
*   `bool hasPendingConnections (self)`
*   `incomingConnection (self, sip.voidptr socketDescriptor)`
*   `bool isListening (self)`
*   `bool listen (self, QString name)`
*   `int maxPendingConnections (self)`
*   `QLocalSocket nextPendingConnection (self)`
*   `QAbstractSocket.SocketError serverError (self)`
*   `QString serverName (self)`
*   `setMaxPendingConnections (self, int numConnections)`
*   `(bool, bool timedOut) waitForNewConnection (self, int msecs = 0)`

### Static Methods

*   `bool removeServer (QString name)`

### Qt Signals

*   `void newConnection ()`

* * *

## Detailed Description

该QLocalServer类提供了一个基于本地套接字服务器。

这个类使得它可以接受传入本地套接字连接。

Call [listen](qlocalserver.html#listen)（ ）让服务器开始侦听在指定的键进入的连接。该[newConnection](qlocalserver.html#newConnection)（ ）信号，然后每个客户端连接到服务器时发出的。

Call [nextPendingConnection](qlocalserver.html#nextPendingConnection)（ ）接受挂起的连接作为一个连接[QLocalSocket](qlocalsocket.html)。该函数返回一个指针，指向一个[QLocalSocket](qlocalsocket.html)可以用于与客户机进行通信。

如果发生错误，[serverError](qlocalserver.html#serverError)（）返回的错误的类型，并且[errorString](qlocalserver.html#errorString)（ ）可以被调用来获取发生了什么可读的描述。

当侦听连接，服务器正在侦听的名称，可通过[serverName](qlocalserver.html#serverName)（ ） 。

调用[close](qlocalserver.html#close)（ ）使得QLocalServer停止侦听传入的连接。

虽然QLocalServer是专为一个事件循环使用，它可以使用它没有之一。在这种情况下，您必须使用[waitForNewConnection](qlocalserver.html#waitForNewConnection)（ ） ，这阻止，直到一个连接可用或者超时。

* * *

## Method Documentation

```
QLocalServer.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建一个新的本地套接字服务器与给定_parent_。

**See also** [listen](qlocalserver.html#listen)（ ） 。

```
QLocalServer.close (self)
```

停止侦听传入的连接。现有的连接将不受影响，但任何新的连接将被拒绝。

**See also** [isListening](qlocalserver.html#isListening)（）和[listen](qlocalserver.html#listen)（ ） 。

```
QString QLocalServer.errorString (self)
```

返回人类可读的消息恰当报告的当前错误[serverError](qlocalserver.html#serverError)（ ） 。如果没有合适的字符串是可用的，则返回一个空字符串。

**See also** [serverError](qlocalserver.html#serverError)（ ） 。

```
QString QLocalServer.fullServerName (self)
```

返回该服务器监听的完整路径。

注：这是具体平台

**See also** [listen](qlocalserver.html#listen)（）和[serverName](qlocalserver.html#serverName)（ ） 。

```
bool QLocalServer.hasPendingConnections (self)
```

返回True ，如果服务器有一个挂起的连接，否则返回False 。

**See also** [nextPendingConnection](qlocalserver.html#nextPendingConnection)（）和[setMaxPendingConnections](qlocalserver.html#setMaxPendingConnections)（ ） 。

```
QLocalServer.incomingConnection (self, sip.voidptr socketDescriptor)
```

这个虚函数被调用[QLocalServer](qlocalserver.html)当一个新的连接可用。_socketDescriptor_对于接受连接的本地套接字描述符。

该基地实现创建一个[QLocalSocket](qlocalsocket.html)，设置套接字描述符，然后存储[QLocalSocket](qlocalsocket.html)在挂起连接的内部清单。最后[newConnection](qlocalserver.html#newConnection)（）被发射。

重新实现这个函数来改变服务器的行为，当一个连接可用。

**See also** [newConnection](qlocalserver.html#newConnection)（ ）[nextPendingConnection](qlocalserver.html#nextPendingConnection)（）和[QLocalSocket.setSocketDescriptor](qlocalsocket.html#setSocketDescriptor)（ ） 。

```
bool QLocalServer.isListening (self)
```

如果服务器正在侦听传入连接，否则为False ，则返回True 。

**See also** [listen](qlocalserver.html#listen)（）和[close](qlocalserver.html#close)（ ） 。

```
bool QLocalServer.listen (self, QString name)
```

告诉服务器侦听传入的连接_name_。如果服务器当前正在侦听那么它将返回False 。返回True成功，否则为False 。

_name_可以是单一的名称和[QLocalServer](qlocalserver.html)将确定正确的特定于平台的路径。[serverName](qlocalserver.html#serverName)（ ）将返回传递到听的名字。

通常你会只是通过像“foo”的名称，但在Unix上，这也可能是诸如“ / tmp目录/富”的路径，在Windows上，这可能是一个管道的路径，例如“ \ \ \管道\富” 。对于以下路径的VxWorks必须始终使用“ / comp/socket/0xNumber ”，其中“ 0xNumber ”是十六进制格式的16位数字的字符串表示形式。例如“ / comp/socket/0x00AA ” 。

注意：在Unix上，如果不关闭服务器崩溃听会失败， AddressInUseError 。创建该文件应该被删除新服务器。在Windows两个本地服务器可以听同一管道的同时，但任何连接将转到服务器之一。

**See also** [serverName](qlocalserver.html#serverName)（ ）[isListening](qlocalserver.html#isListening)（）和[close](qlocalserver.html#close)（ ） 。

```
int QLocalServer.maxPendingConnections (self)
```

返回未决接受的连接的最大数目。默认值是30 。

**See also** [setMaxPendingConnections](qlocalserver.html#setMaxPendingConnections)（）和[hasPendingConnections](qlocalserver.html#hasPendingConnections)（ ） 。

```
QLocalSocket QLocalServer.nextPendingConnection (self)
```

[](qlocalsocket.html)

[返回的连接下一个待连接](qlocalsocket.html)[QLocalSocket](qlocalsocket.html)对象。

套接字被作为服务器的一个子创建的，这意味着它被自动删除时[QLocalServer](qlocalserver.html)对象被销毁。它仍然是一个好主意，明确地删除的对象，当你用它做，以避免浪费内存。

如果这个函数被调用时，有没有挂起的连接则返回0 。

**See also** [hasPendingConnections](qlocalserver.html#hasPendingConnections)（ ）[newConnection](qlocalserver.html#newConnection)（）和[incomingConnection](qlocalserver.html#incomingConnection)（ ） 。

```
bool QLocalServer.removeServer (QString name)
```

删除可能导致调用任何服务器实例[listen](qlocalserver.html#listen)（）失败，如果成功返回True，否则返回False 。此功能是为了从崩溃中，当以前的服务器实例还没有被清理回收。

在Windows中，这个函数不做任何事情;在Unix上，它消除由给定的套接字文件_name_。

**Warning:**要小心，以避免删除运行实例的插座。

此功能被引入Qt的4.5 。

```
QAbstractSocket.SocketError QLocalServer.serverError (self)
```

[

最后返回NOERROR或发生错误的类型。

](qabstractsocket.html#SocketError-enum)

[**See also**](qabstractsocket.html#SocketError-enum) [errorString](qlocalserver.html#errorString)（ ） 。

```
QString QLocalServer.serverName (self)
```

返回如果服务器正在监听等待连接的服务器名，否则返回的QString （ ）

**See also** [listen](qlocalserver.html#listen)（）和[fullServerName](qlocalserver.html#fullServerName)（ ） 。

```
QLocalServer.setMaxPendingConnections (self, int numConnections)
```

设置挂起接受的最大连接数_numConnections_。[QLocalServer](qlocalserver.html)将接受不超过_numConnections_前传入的连接[nextPendingConnection](qlocalserver.html#nextPendingConnection)（）被调用。

注：即使[QLocalServer](qlocalserver.html)将停止接受新的连接后，它已经达到了挂起连接的最大数量，操作系统可能仍然让他们在队列中，这将导致客户端的信号，它是连通的。

**See also** [maxPendingConnections](qlocalserver.html#maxPendingConnections)（）和[hasPendingConnections](qlocalserver.html#hasPendingConnections)（ ） 。

```
(bool, bool timedOut) QLocalServer.waitForNewConnection (self, int msecs = 0)
```

最多等待_msec_毫秒或直到传入的连接是可用的。返回True如果连接可用，否则返回False 。如果操作超时，_timedOut_不为0 ， * TIMEDOUT将被设置为True。

这是一个阻塞函数调用。它的使用是不明智的单线程GUI应用程序，因为整个应用程序将停止响应，直到函数返回。当没有事件循环可用waitForNewConnection （ ）是最有用。

非阻塞的替代方法是连接到[newConnection](qlocalserver.html#newConnection)（）信号。

如果毫秒为-1 ，此功能将不会超时。

**See also** [hasPendingConnections](qlocalserver.html#hasPendingConnections)（）和[nextPendingConnection](qlocalserver.html#nextPendingConnection)（ ） 。

* * *

## Qt Signal Documentation

```
void newConnection ()
```

这是该信号的默认超载。

每当一个新的连接是可用的，这个信号被发射。

**See also** [hasPendingConnections](qlocalserver.html#hasPendingConnections)（）和[nextPendingConnection](qlocalserver.html#nextPendingConnection)（ ） 。