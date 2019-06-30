# QAbstractSocket Class Reference

## [[QtNetwork](index.htm) module]

该QAbstractSocket类提供通用于所有的套接字类型的基本功能。[More...](#details)

继承[QIODevice](qiodevice.html)。

通过继承[QTcpSocket](qtcpsocket.html)和[QUdpSocket](qudpsocket.html)。

### Types

*   `enum NetworkLayerProtocol { IPv4Protocol, IPv6Protocol, UnknownNetworkLayerProtocol }`
*   `enum SocketError { ConnectionRefusedError, RemoteHostClosedError, HostNotFoundError, SocketAccessError, ..., UnknownSocketError }`
*   `enum SocketOption { LowDelayOption, KeepAliveOption, MulticastTtlOption, MulticastLoopbackOption }`
*   `enum SocketState { UnconnectedState, HostLookupState, ConnectingState, ConnectedState, ..., ClosingState }`
*   `enum SocketType { TcpSocket, UdpSocket, UnknownSocketType }`

### Methods

*   `__init__ (self, SocketType socketType, QObject parent)`
*   `abort (self)`
*   `bool atEnd (self)`
*   `int bytesAvailable (self)`
*   `int bytesToWrite (self)`
*   `bool canReadLine (self)`
*   `close (self)`
*   `connectToHost (self, QString hostName, int port, QIODevice.OpenMode mode = QIODevice.ReadWrite)`
*   `connectToHost (self, QHostAddress address, int port, QIODevice.OpenMode mode = QIODevice.ReadWrite)`
*   `connectToHostImplementation (self, QString hostName, int port, QIODevice.OpenMode mode = QIODevice.ReadWrite)`
*   `disconnectFromHost (self)`
*   `disconnectFromHostImplementation (self)`
*   `SocketError error (self)`
*   `bool flush (self)`
*   `bool isSequential (self)`
*   `bool isValid (self)`
*   `QHostAddress localAddress (self)`
*   `int localPort (self)`
*   `QHostAddress peerAddress (self)`
*   `QString peerName (self)`
*   `int peerPort (self)`
*   `QNetworkProxy proxy (self)`
*   `int readBufferSize (self)`
*   `str readData (self, int maxlen)`
*   `str readLineData (self, int maxlen)`
*   `setLocalAddress (self, QHostAddress address)`
*   `setLocalPort (self, int port)`
*   `setPeerAddress (self, QHostAddress address)`
*   `setPeerName (self, QString name)`
*   `setPeerPort (self, int port)`
*   `setProxy (self, QNetworkProxy networkProxy)`
*   `setReadBufferSize (self, int size)`
*   `bool setSocketDescriptor (self, int socketDescriptor, SocketState state = QAbstractSocket.ConnectedState, QIODevice.OpenMode mode = QIODevice.ReadWrite)`
*   `setSocketError (self, SocketError socketError)`
*   `setSocketOption (self, SocketOption option, QVariant value)`
*   `setSocketState (self, SocketState state)`
*   `int socketDescriptor (self)`
*   `QVariant socketOption (self, SocketOption option)`
*   `SocketType socketType (self)`
*   `SocketState state (self)`
*   `bool waitForBytesWritten (self, int msecs = 30000)`
*   `bool waitForConnected (self, int msecs = 30000)`
*   `bool waitForDisconnected (self, int msecs = 30000)`
*   `bool waitForReadyRead (self, int msecs = 30000)`
*   `int writeData (self, str data)`

### Qt Signals

*   `void connected ()`
*   `void disconnected ()`
*   `void error (QAbstractSocket::SocketError)`
*   `void hostFound ()`
*   `void proxyAuthenticationRequired (const QNetworkProxy&,QAuthenticator *)`
*   `void stateChanged (QAbstractSocket::SocketState)`

* * *

## Detailed Description

该QAbstractSocket类提供通用于所有的套接字类型的基本功能。

QAbstractSocket为基类[QTcpSocket](qtcpsocket.html)和[QUdpSocket](qudpsocket.html)并包含这两个类的所有常见功能。如果你需要一个插座，你有两种选择：

*   Instantiate [QTcpSocket](qtcpsocket.html) or [QUdpSocket](qudpsocket.html).
*   Create a native socket descriptor, instantiate QAbstractSocket, and call [setSocketDescriptor](qabstractsocket.html#setSocketDescriptor)() to wrap the native socket.

TCP（传输控制协议）是一种可靠的，面向流的，面向连接的传输协议。 UDP（用户数据报协议）是一种不可靠的，面向数据报的，无连接的协议。在实践中，这意味着TCP是更适合于数据的连续发送，而当可靠性是不重要的，轻量级的UDP都可以使用。

QAbstractSocket的API，最统一的两个协议之间的差异。例如，虽然UDP是无连接的，[connectToHost](qabstractsocket.html#connectToHost)（ ）建立了UDP套接字的虚拟连接，使您能够在或多或少的相同方式使用QAbstractSocket不管底层协议。在内部， QAbstractSocket记得传递给地址和端口[connectToHost](qabstractsocket.html#connectToHost)（） ，和类似的功能[read](qiodevice.html#read)（）和[write](qiodevice.html#write)（）中使用这些值。

在任何时候， QAbstractSocket具有状态（返回[state](qabstractsocket.html#state)（））。初始状态是[UnconnectedState](qabstractsocket.html#SocketState-enum)。后调用[connectToHost](qabstractsocket.html#connectToHost)（） ，插座首先进入[HostLookupState](qabstractsocket.html#SocketState-enum)。如果发现主机， QAbstractSocket进入[ConnectingState](qabstractsocket.html#SocketState-enum)和发射[hostFound](qabstractsocket.html#hostFound)（）信号。当连接已经建立时，它进入[ConnectedState](qabstractsocket.html#SocketState-enum)并发出[connected](qabstractsocket.html#connected)（ ） 。如果发生错误，在任何阶段，[error](qabstractsocket.html#error)（）被发射。每当状态发生变化，[stateChanged](qabstractsocket.html#stateChanged)（）被发射。为方便起见，[isValid](qabstractsocket.html#isValid)（ ）返回True如果套接字已准备好进行读取和写入，但请注意，插座的状态必须[ConnectedState](qabstractsocket.html#SocketState-enum)阅读和写作之前可能发生。

通过调用读取或写入数据[read](qiodevice.html#read)（）或[write](qiodevice.html#write)（ ） ，或者使用的方便功能[readLine](qiodevice.html#readLine)（）和[readAll](qiodevice.html#readAll)（ ） 。 QAbstractSocket也继承[getChar](qiodevice.html#getChar)（ ）[putChar](qiodevice.html#putChar)（）和[ungetChar](qiodevice.html#ungetChar)（ ）从[QIODevice](qiodevice.html)，其中单字节工作。该[bytesWritten](qiodevice.html#bytesWritten)当数据已经被写入到插座（即，当客户端已读出的数据）（ ）信号被发射。注意Qt不限制写入缓冲区的大小。您可以通过听这个信号监视它的大小。

该[readyRead](qiodevice.html#readyRead)每一个新的数据块已到达的时间（）信号被发射。[bytesAvailable](qabstractsocket.html#bytesAvailable)（）然后返回可用于读取的字节数。通常情况下，您将在[readyRead](qiodevice.html#readyRead)（）信号到一个槽和阅读有所有可用的数据。如果你不立即读取所有数据，其馀数据仍然可用后，任何新进入的数据将被追加到QAbstractSocket的内部读缓冲区。来限制读缓冲区的大小，调用[setReadBufferSize](qabstractsocket.html#setReadBufferSize)（ ） 。

关闭套接字，调用[disconnectFromHost](qabstractsocket.html#disconnectFromHost)（ ） 。 QAbstractSocket进入[QAbstractSocket.ClosingState](qabstractsocket.html#SocketState-enum)。在所有挂起的数据已经写入到socket ， QAbstractSocket实际上关闭套接字，进入QAbstractSocket.ClosedState ，并发出[disconnected](qabstractsocket.html#disconnected)（ ） 。如果您想立即中止连接，丢弃所有未决的数据，调用[abort](qabstractsocket.html#abort)（ ）来代替。如果远程主机关闭连接， QAbstractSocket会发出错误（[QAbstractSocket.RemoteHostClosedError](qabstractsocket.html#SocketError-enum)） ，在此期间，插座状态仍将是[ConnectedState](qabstractsocket.html#SocketState-enum)，然后在[disconnected](qabstractsocket.html#disconnected)（）信号将被发射。

所连接的对端的端口和地址是通过调用取[peerPort](qabstractsocket.html#peerPort)（）和[peerAddress](qabstractsocket.html#peerAddress)（ ） 。[peerName](qabstractsocket.html#peerName)（）返回对端的主机名，它被传递到[connectToHost](qabstractsocket.html#connectToHost)（ ） 。[localPort](qabstractsocket.html#localPort)（）和[localAddress](qabstractsocket.html#localAddress)（ ）返回本地套接字的端口和地址。

QAbstractSocket提供了一组挂起调用线程，直到某个信号发射的功能。这些功能可以用来实现阻塞套接字：

*   [waitForConnected](qabstractsocket.html#waitForConnected)() blocks until a connection has been established.
*   [waitForReadyRead](qabstractsocket.html#waitForReadyRead)() blocks until new data is available for reading.
*   [waitForBytesWritten](qabstractsocket.html#waitForBytesWritten)() blocks until one payload of data has been written to the socket.
*   [waitForDisconnected](qabstractsocket.html#waitForDisconnected)() blocks until the connection has closed.

我们显示一个例子：

```
     int numRead = 0, numReadTotal = 0;
     char buffer[50];

     forever {
         numRead  = socket.read(buffer, 50);

         // do whatever with array

         numReadTotal += numRead;
         if (numRead == 0 && !socket.waitForReadyRead())
             break;
     }

```

If [waitForReadyRead()](qiodevice.html#waitForReadyRead)返回False ，该连接已关闭或发生错误。

与阻塞套接字编程是一个非阻塞套接字编程完全不同。阻塞套接字并不需要一个事件循环，并通常会导致简单的代码。然而，在一个图形用户界面的应用程序，阻塞插座只应在非GUI线程使用，以避免冻结的用户界面。请参阅[network/fortuneclient](index.htm)和[network/blockingfortuneclient](index.htm)举例而言，两种方法的概述。

**Note:**我们不鼓励使用的阻塞函数信号一起。应该使用其中的两种可能性。

QAbstractSocket可以被用于[QTextStream](qtextstream.html)和[QDataStream](qdatastream.html)的流运算符（运算符\u003c\u003c （）和operator \u003e\u003e （ ） ） 。有一个问题需要注意，虽然：你必须确保有足够的数据可用尝试使用运算符来读取它之前\u003e\u003e （ ） 。

* * *

## Type Documentation

```
QAbstractSocket.NetworkLayerProtocol
```

这个枚举变量描述的Qt使用的网络层协议的值。

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractSocket.IPv4Protocol` | `0` | IPv4的 |
| `QAbstractSocket.IPv6Protocol` | `1` | IPv6的 |
| `QAbstractSocket.UnknownNetworkLayerProtocol` | `-1` | 除IPv4和IPv6 |

**See also** [QHostAddress.protocol](qhostaddress.html#protocol)（ ） 。

```
QAbstractSocket.SocketError
```

这个枚举说明可能发生的套接字错误。

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractSocket.ConnectionRefusedError` | `0` | 连接被对等（或超时）拒绝。 |
| `QAbstractSocket.RemoteHostClosedError` | `1` | 远程主机关闭了连接。请注意，客户端套接字（也就是该套接字）远程关闭通知发出后将会关闭。 |
| `QAbstractSocket.HostNotFoundError` | `2` | 主机地址未找到。 |
| `QAbstractSocket.SocketAccessError` | `3` | 套接字操作失败，因为该应用程序缺乏必要的特权。 |
| `QAbstractSocket.SocketResourceError` | `4` | 本地系统跑出来的资源（例如，太多的套接字）的。 |
| `QAbstractSocket.SocketTimeoutError` | `5` | 套接字操作超时。 |
| `QAbstractSocket.DatagramTooLargeError` | `6` | 数据报比操作系统的限制（其可以是低至8192字节）大。 |
| `QAbstractSocket.NetworkError` | `7` | 与网络（例如，网络电缆被意外拔出）时发生错误。 |
| `QAbstractSocket.AddressInUseError` | `8` | 指定的地址[QUdpSocket.bind](qudpsocket.html#bind)（）已经在使用中并且被设置为独占的。 |
| `QAbstractSocket.SocketAddressNotAvailableError` | `9` | 指定的地址[QUdpSocket.bind](qudpsocket.html#bind)（ ）不属于主机。 |
| `QAbstractSocket.UnsupportedSocketOperationError` | `10` | 不是由本地操作系统（例如，缺乏支持IPv6 ）的支持请求的套接字操作。 |
| `QAbstractSocket.ProxyAuthenticationRequiredError` | `12` | 该插座是使用代理，而代理服务器需要身份验证。 |
| `QAbstractSocket.SslHandshakeFailedError` | `13` | 在SSL / TLS握手失败，因此连接已关闭（仅在使用[QSslSocket](qsslsocket.html)） （此值被引入4.4 。 ） |
| `QAbstractSocket.UnfinishedSocketOperationError` | `11` | 使用QAbstractSocketEngine只，最后的操作尝试尚未完成（仍然在后台进程） 。 （这个值被引入4.4 。 ） |
| `QAbstractSocket.ProxyConnectionRefusedError` | `14` | 无法联系的代理服务器，因为连接到该服务器被拒绝（这个值被引入4.5 。 ） |
| `QAbstractSocket.ProxyConnectionClosedError` | `15` | 到代理服务器的连接意外被关闭（连接到最终的同行建立之前） （此值是在4.5推出。 ） |
| `QAbstractSocket.ProxyConnectionTimeoutError` | `16` | 到代理服务器的连接超时或代理服务器停在认证阶段响应。 （这个值被引入4.5 。 ） |
| `QAbstractSocket.ProxyNotFoundError` | `17` | 设置代理地址[setProxy](qabstractsocket.html#setProxy)（ ） （或应用程序代理）未找到。 （这个值被引入4.5 。 ） |
| `QAbstractSocket.ProxyProtocolError` | `18` | 在连接协商与代理服务器，因为从代理服务器的响应无法被理解。 （这个值被引入4.5 。 ） |
| `QAbstractSocket.UnknownSocketError` | `-1` | 发生不明的错误。 |

**See also** [QAbstractSocket.error](qabstractsocket.html#error)（ ） 。

```
QAbstractSocket.SocketOption
```

这个枚举表示可以在一个插座可以设置的选项。如果需要的话，它们可以在接收之后进行设置[connected](qabstractsocket.html#connected)（）从插座或收到一个新的套接字从后信号[QTcpServer](qtcpserver.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractSocket.LowDelayOption` | `0` | 尝试优化插座低延迟。对于[QTcpSocket](qtcpsocket.html)这将设置TCP_NODELAY选项，并禁用Nagle算法。将此值设置为1来启用。 |
| `QAbstractSocket.KeepAliveOption` | `1` | 将此值设置为1，以启用SO_KEEPALIVE套接字选项 |
| `QAbstractSocket.MulticastTtlOption` | `2` | 将其设置为一个整数值来设置IP_MULTICAST_TTL （TTL组播数据报）套接字选项。 |
| `QAbstractSocket.MulticastLoopbackOption` | `3` | 将此值设置为1 ，使IP_MULTICAST_LOOP （多播环回）套接字选项。 |

这个枚举被引入或修改的Qt 4.6 。

**See also** [QAbstractSocket.setSocketOption](qabstractsocket.html#setSocketOption)（）和[QAbstractSocket.socketOption](qabstractsocket.html#socketOption)（ ） 。

```
QAbstractSocket.SocketState
```

这个枚举变量描述了不同的状态，其中一个插座即可。

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractSocket.UnconnectedState` | `0` | 该套接字没有连接。 |
| `QAbstractSocket.HostLookupState` | `1` | 该插座是执行主机名查找。 |
| `QAbstractSocket.ConnectingState` | `2` | 插座已经开始建立连接。 |
| `QAbstractSocket.ConnectedState` | `3` | 连接建立。 |
| `QAbstractSocket.BoundState` | `4` | 套接字绑定到一个地址和端口（用于服务器） 。 |
| `QAbstractSocket.ClosingState` | `6` | 该插座是即将关闭（数据仍可能等待写入） 。 |
| `QAbstractSocket.ListeningState` | `5` | 仅供内部使用。 |

**See also** [QAbstractSocket.state](qabstractsocket.html#state)（ ） 。

```
QAbstractSocket.SocketType
```

这个枚举变量描述传输层协议。

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractSocket.TcpSocket` | `0` | TCP |
| `QAbstractSocket.UdpSocket` | `1` | UDP |
| `QAbstractSocket.UnknownSocketType` | `-1` | 除了TCP和UDP |

**See also** [QAbstractSocket.socketType](qabstractsocket.html#socketType)（ ） 。

* * *

## Method Documentation

```
QAbstractSocket.__init__ (self, SocketType socketType, QObject parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建类型的新抽象插座_socketType_。该_parent_参数被传递给[QObject](qobject.html)的构造。

**See also** [socketType](qabstractsocket.html#socketType)（ ）[QTcpSocket](qtcpsocket.html)和[QUdpSocket](qudpsocket.html)。

```
QAbstractSocket.abort (self)
```

中止当前连接并重置插口。不像[disconnectFromHost](qabstractsocket.html#disconnectFromHost)（ ） ，这个函数立即关闭套接字，丢弃在写缓冲区任何挂起的数据。

**See also** [disconnectFromHost](qabstractsocket.html#disconnectFromHost)（）和[close](qabstractsocket.html#close)（ ） 。

```
bool QAbstractSocket.atEnd (self)
```

从重新实现[QIODevice.atEnd](qiodevice.html#atEnd)（ ） 。

如果没有更多的数据，目前可供读取，则返回True ，否则返回False 。

读数从插座在一个循环中的数据时，此功能是最常用的。例如：

```
  // This slot is connected to QAbstractSocket.readyRead()
  void SocketClass.readyReadSlot()
  {
      while (!socket.atEnd()) {
          [QByteArray](qbytearray.html) data = socket.read(100);
          ....
      }
  }

```

**See also** [bytesAvailable](qabstractsocket.html#bytesAvailable)（）和[readyRead](qiodevice.html#readyRead)（ ） 。

```
int QAbstractSocket.bytesAvailable (self)
```

从重新实现[QIODevice.bytesAvailable](qiodevice.html#bytesAvailable)（ ） 。

返回传入的字节正在等待被读取的次数。

**See also** [bytesToWrite](qabstractsocket.html#bytesToWrite)（）和[read](qiodevice.html#read)（ ） 。

```
int QAbstractSocket.bytesToWrite (self)
```

从重新实现[QIODevice.bytesToWrite](qiodevice.html#bytesToWrite)（ ） 。

返回正在等待被写入的字节数。该字节被写入时，控制返回到事件循环或当[flush](qabstractsocket.html#flush)（）被调用。

**See also** [bytesAvailable](qabstractsocket.html#bytesAvailable)（）和[flush](qabstractsocket.html#flush)（ ） 。

```
bool QAbstractSocket.canReadLine (self)
```

从重新实现[QIODevice.canReadLine](qiodevice.html#canReadLine)（ ） 。

返回True如果一行数据可以从套接字读取，否则返回False 。

**See also** [readLine](qiodevice.html#readLine)（ ） 。

```
QAbstractSocket.close (self)
```

从重新实现[QIODevice.close](qiodevice.html#close)（ ） 。

关闭套接字的I / O设备，断开与主机插座的连接，关闭套接字，并重置姓名，地址，端口号和底层套接字描述符。

See [QIODevice.close](qiodevice.html#close)（ ），用于当一个I / O设备被关闭时发生的动作的说明。

**See also** [abort](qabstractsocket.html#abort)（ ） 。

```
QAbstractSocket.connectToHost (self, QString hostName, int port, QIODevice.OpenMode mode = QIODevice.ReadWrite)
```

企图使一个连接_hostName_在给定的_port_。

该插座是在给定的开_openMode_并首次进入[HostLookupState](qabstractsocket.html#SocketState-enum)，然后执行一个主机名查找_hostName_。如果查找成功，[hostFound](qabstractsocket.html#hostFound)（）被发射和[QAbstractSocket](qabstractsocket.html)进入[ConnectingState](qabstractsocket.html#SocketState-enum)。然后，它尝试连接到由查询返回的地址或地址。最后，如果建立了连接，[QAbstractSocket](qabstractsocket.html)进入[ConnectedState](qabstractsocket.html#SocketState-enum)并发出[connected](qabstractsocket.html#connected)（ ） 。

在任何点，该插座能发射[error](qabstractsocket.html#error)（）来通知发生了错误。

_hostName_可以是字符串形式（例如，“ 43.195.83.32 ” ）的IP地址，也可以是主机名（例如，“ example.com ” ） 。[QAbstractSocket](qabstractsocket.html)会做只有当需要查找。_port_是在本地字节顺序。

**See also** [state](qabstractsocket.html#state)（ ）[peerName](qabstractsocket.html#peerName)（ ）[peerAddress](qabstractsocket.html#peerAddress)（ ）[peerPort](qabstractsocket.html#peerPort)（）和[waitForConnected](qabstractsocket.html#waitForConnected)（ ） 。

```
QAbstractSocket.connectToHost (self, QHostAddress address, int port, QIODevice.OpenMode mode = QIODevice.ReadWrite)
```

这是一个重载函数。

企图使一个连接_address_端口_port_。

```
QAbstractSocket.connectToHostImplementation (self, QString hostName, int port, QIODevice.OpenMode mode = QIODevice.ReadWrite)
```

这种方法也是一个Qt槽与C + +的签名`void connectToHostImplementation(const QString&,quint16,QIODevice::OpenMode = QIODevice.ReadWrite)`。

包含的实施[connectToHost](qabstractsocket.html#connectToHost)（ ） 。

企图使一个连接_hostName_在给定的_port_。该插座是在给定的开_openMode_。

这个函数是Qt 4.1中引入。

```
QAbstractSocket.disconnectFromHost (self)
```

试图关闭套接字。如果有挂起的数据等待写入，[QAbstractSocket](qabstractsocket.html)将进入[ClosingState](qabstractsocket.html#SocketState-enum)并等待，直到所有数据已经写入。最终，将进入[UnconnectedState](qabstractsocket.html#SocketState-enum)和发射[disconnected](qabstractsocket.html#disconnected)（）信号。

**See also** [connectToHost](qabstractsocket.html#connectToHost)（ ） 。

```
QAbstractSocket.disconnectFromHostImplementation (self)
```

这种方法也是一个Qt槽与C + +的签名`void disconnectFromHostImplementation()`。

包含的实施[disconnectFromHost](qabstractsocket.html#disconnectFromHost)（ ） 。

这个函数是Qt 4.1中引入。

```
SocketError QAbstractSocket.error (self)
```

[

返回上次发生错误的类型。

](qabstractsocket.html#SocketError-enum)

[**See also**](qabstractsocket.html#SocketError-enum) [state](qabstractsocket.html#state)（）和[errorString](qiodevice.html#errorString)（ ） 。

```
bool QAbstractSocket.flush (self)
```

该函数将尽可能从内部写缓冲区的底层网络接口，而不会阻塞。如果任何数据被写入时，该函数将返回True，否则返回False。

调用此函数，如果你需要[QAbstractSocket](qabstractsocket.html)立即开始发送缓冲数据。成功写入的字节数依赖于操作系统。在大多数情况下，你不需要调用这个函数，因为[QAbstractSocket](qabstractsocket.html)将自动开始发送数据，一旦控制返回到事件循环。在不存在的事件循环，调用[waitForBytesWritten](qabstractsocket.html#waitForBytesWritten)（ ）来代替。

**See also** [write](qiodevice.html#write)（）和[waitForBytesWritten](qabstractsocket.html#waitForBytesWritten)（ ） 。

```
bool QAbstractSocket.isSequential (self)
```

从重新实现[QIODevice.isSequential](qiodevice.html#isSequential)（ ） 。

```
bool QAbstractSocket.isValid (self)
```

返回True如果套接字是有效的，并准备使用，否则返回False 。

**Note:**套接字的状态必须[ConnectedState](qabstractsocket.html#SocketState-enum)阅读和写作之前可能发生。

**See also** [state](qabstractsocket.html#state)（ ） 。

```
QHostAddress QAbstractSocket.localAddress (self)
```

[](qhostaddress.html)

[返回本地套接字如果可用的主机地址，否则返回](qhostaddress.html)[QHostAddress.Null](qhostaddress.html#SpecialAddress-enum)。

这通常是在主机的主IP地址，但也可以是[QHostAddress.LocalHost](qhostaddress.html#SpecialAddress-enum)（ 127.0.0.1）来连接到本地主机。

**See also** [localPort](qabstractsocket.html#localPort)（ ）[peerAddress](qabstractsocket.html#peerAddress)（）和[setLocalAddress](qabstractsocket.html#setLocalAddress)（ ） 。

```
int QAbstractSocket.localPort (self)
```

返回本地套接字如果可用的主机端口号（本地字节顺序） ，否则返回0 。

**See also** [localAddress](qabstractsocket.html#localAddress)（ ）[peerPort](qabstractsocket.html#peerPort)（）和[setLocalPort](qabstractsocket.html#setLocalPort)（ ） 。

```
QHostAddress QAbstractSocket.peerAddress (self)
```

[](qhostaddress.html)

[返回所连接的对端的地址，如果套接字是在](qhostaddress.html)[ConnectedState](qabstractsocket.html#SocketState-enum)否则返回[QHostAddress.Null](qhostaddress.html#SpecialAddress-enum)。

**See also** [peerName](qabstractsocket.html#peerName)（ ）[peerPort](qabstractsocket.html#peerPort)（ ）[localAddress](qabstractsocket.html#localAddress)（）和[setPeerAddress](qabstractsocket.html#setPeerAddress)（ ） 。

```
QString QAbstractSocket.peerName (self)
```

所指定的返回对端的名称[connectToHost](qabstractsocket.html#connectToHost)（ ） ，或空[QString](qstring.html)如果[connectToHost](qabstractsocket.html#connectToHost)（ ）尚未被调用。

**See also** [peerAddress](qabstractsocket.html#peerAddress)（ ）[peerPort](qabstractsocket.html#peerPort)（）和[setPeerName](qabstractsocket.html#setPeerName)（ ） 。

```
int QAbstractSocket.peerPort (self)
```

返回所连接的对端的端口，如果套接字是在[ConnectedState](qabstractsocket.html#SocketState-enum)否则返回0 。

**See also** [peerAddress](qabstractsocket.html#peerAddress)（ ）[localPort](qabstractsocket.html#localPort)（）和[setPeerPort](qabstractsocket.html#setPeerPort)（ ） 。

```
QNetworkProxy QAbstractSocket.proxy (self)
```

[](qnetworkproxy.html)

[返回此套接字的网络代理。默认情况下，](qnetworkproxy.html)[QNetworkProxy.DefaultProxy](qnetworkproxy.html#ProxyType-enum)被使用，这意味着该套接字将查询应用程序的默认代理设置。

这个函数是Qt 4.1中引入。

**See also** [setProxy](qabstractsocket.html#setProxy)（ ）[QNetworkProxy](qnetworkproxy.html)和[QNetworkProxyFactory](qnetworkproxyfactory.html)。

```
int QAbstractSocket.readBufferSize (self)
```

返回内部读缓冲区的大小。这限制了数据的客户端可以在打电话之前收取的金额[read](qiodevice.html#read)（）或[readAll](qiodevice.html#readAll)（ ） 。

0读缓冲区的大小（默认值）意味着缓冲区有没有大小限制，以确保数据不会丢失。

**See also** [setReadBufferSize](qabstractsocket.html#setReadBufferSize)（）和[read](qiodevice.html#read)（ ） 。

```
str QAbstractSocket.readData (self, int maxlen)
```

从重新实现[QIODevice.readData](qiodevice.html#readData)（ ） 。

```
str QAbstractSocket.readLineData (self, int maxlen)
```

从重新实现[QIODevice.readLineData](qiodevice.html#readLineData)（ ） 。

```
QAbstractSocket.setLocalAddress (self, QHostAddress address)
```

设置到一个连接的本地端的地址_address_。

您可以在子类中调用这个函数[QAbstractSocket](qabstractsocket.html)改变的返回值[localAddress](qabstractsocket.html#localAddress)连接后（）函数已经建立。此功能是常用的代理服务器连接虚拟连接设置。

请注意，此功能对套接字的本地地址的连接（例如，之前没有绑定，[QUdpSocket.bind](qudpsocket.html#bind)（））。

这个函数是Qt 4.1中引入。

**See also** [localAddress](qabstractsocket.html#localAddress)（ ）[setLocalPort](qabstractsocket.html#setLocalPort)（）和[setPeerAddress](qabstractsocket.html#setPeerAddress)（ ） 。

```
QAbstractSocket.setLocalPort (self, int port)
```

设置端口上连接的本地端_port_。

您可以在子类中调用这个函数[QAbstractSocket](qabstractsocket.html)改变的返回值[localPort](qabstractsocket.html#localPort)连接后（）函数已经建立。此功能是常用的代理服务器连接虚拟连接设置。

请注意，这个函数不套接字的本地端口绑定的连接（如前，[QUdpSocket.bind](qudpsocket.html#bind)（））。

这个函数是Qt 4.1中引入。

**See also** [localPort](qabstractsocket.html#localPort)（ ）[localAddress](qabstractsocket.html#localAddress)（ ）[setLocalAddress](qabstractsocket.html#setLocalAddress)（）和[setPeerPort](qabstractsocket.html#setPeerPort)（ ） 。

```
QAbstractSocket.setPeerAddress (self, QHostAddress address)
```

设置连接到的远程端的地址_address_。

您可以在子类中调用这个函数[QAbstractSocket](qabstractsocket.html)改变的返回值[peerAddress](qabstractsocket.html#peerAddress)连接后（）函数已经建立。此功能是常用的代理服务器连接虚拟连接设置。

这个函数是Qt 4.1中引入。

**See also** [peerAddress](qabstractsocket.html#peerAddress)（ ）[setPeerPort](qabstractsocket.html#setPeerPort)（）和[setLocalAddress](qabstractsocket.html#setLocalAddress)（ ） 。

```
QAbstractSocket.setPeerName (self, QString name)
```

设置远端的主机名_name_。

您可以在子类中调用这个函数[QAbstractSocket](qabstractsocket.html)改变的返回值[peerName](qabstractsocket.html#peerName)连接后（）函数已经建立。此功能是常用的代理服务器连接虚拟连接设置。

这个函数是Qt 4.1中引入。

**See also** [peerName](qabstractsocket.html#peerName)（ ） 。

```
QAbstractSocket.setPeerPort (self, int port)
```

设置连接到的远程端的端口_port_。

您可以在子类中调用这个函数[QAbstractSocket](qabstractsocket.html)改变的返回值[peerPort](qabstractsocket.html#peerPort)连接后（）函数已经建立。此功能是常用的代理服务器连接虚拟连接设置。

这个函数是Qt 4.1中引入。

**See also** [peerPort](qabstractsocket.html#peerPort)（ ）[setPeerAddress](qabstractsocket.html#setPeerAddress)（）和[setLocalPort](qabstractsocket.html#setLocalPort)（ ） 。

```
QAbstractSocket.setProxy (self, QNetworkProxy networkProxy)
```

设置此套接字明确网络代理_networkProxy_。

要禁用使用代理的这个插座，使用[QNetworkProxy.NoProxy](qnetworkproxy.html#ProxyType-enum)代理类型：

```
 socket->setProxy([QNetworkProxy](qnetworkproxy.html).NoProxy);

```

对于代理的默认值是[QNetworkProxy.DefaultProxy](qnetworkproxy.html#ProxyType-enum)，这意味着套接字将使用应用程序设置：如果将代理设置QNetworkProxy.setApplicationProxy ，它将使用，否则，如果一个工厂设置QNetworkProxyFactory.setApplicationProxyFactory ，它会查询该工厂类型[QNetworkProxyQuery.TcpSocket](qnetworkproxyquery.html#QueryType-enum)。

这个函数是Qt 4.1中引入。

**See also** [proxy](qabstractsocket.html#proxy)（ ）[QNetworkProxy](qnetworkproxy.html)和[QNetworkProxyFactory.queryProxy](qnetworkproxyfactory.html#queryProxy)（ ） 。

```
QAbstractSocket.setReadBufferSize (self, int size)
```

载的大小[QAbstractSocket](qabstractsocket.html)的内部读缓冲区是_size_字节。

如果缓冲区大小被限制为一定的大小，[QAbstractSocket](qabstractsocket.html)将不缓存数据超过此大小。特殊情况下，为0的缓冲区大小意味着读缓存器是无限的，所有输入的数据进行缓冲。这是默认的。

此选项很有用，如果你只在读取特定时间点的数据（例如，在实时流应用程序），或者如果你想保护你的插座对接收的数据过多，最终可能导致应用程序用完内存。

只[QTcpSocket](qtcpsocket.html) uses [QAbstractSocket](qabstractsocket.html)的内部缓冲区;[QUdpSocket](qudpsocket.html)不使用任何缓冲在所有的，而是依赖于由操作系统提供的隐式缓冲。正因为如此，调用这个函数上[QUdpSocket](qudpsocket.html)没有任何影响。

**See also** [readBufferSize](qabstractsocket.html#readBufferSize)（）和[read](qiodevice.html#read)（ ） 。

```
bool QAbstractSocket.setSocketDescriptor (self, int socketDescriptor, SocketState state = QAbstractSocket.ConnectedState, QIODevice.OpenMode mode = QIODevice.ReadWrite)
```

初始化[QAbstractSocket](qabstractsocket.html)与本地套接字描述符_socketDescriptor_。返回True如果_socketDescriptor_被接受为有效的套接字描述符，否则返回False 。该插座是由指定的模式打开_openMode_，并进入由指定的套接字状态_socketState_。

**Note:**这是不可能的初始化两个抽象插座，相同的本地套接字描述符。

**See also** [socketDescriptor](qabstractsocket.html#socketDescriptor)（ ） 。

```
QAbstractSocket.setSocketError (self, SocketError socketError)
```

设置最后对发生错误的类型_socketError_。

**See also** [setSocketState](qabstractsocket.html#setSocketState)（）和[setErrorString](qiodevice.html#setErrorString)（ ） 。

```
QAbstractSocket.setSocketOption (self, SocketOption option, QVariant value)
```

设置给定_option_由所描述的值_value_。

此功能被引入Qt的4.6 。

**See also** [socketOption](qabstractsocket.html#socketOption)（ ） 。

```
QAbstractSocket.setSocketState (self, SocketState state)
```

设置套接字的状态，以_state_。

**See also** [state](qabstractsocket.html#state)（ ） 。

```
int QAbstractSocket.socketDescriptor (self)
```

返回的本地套接字描述符[QAbstractSocket](qabstractsocket.html)如果对象是可用的，否则返回-1 。

如果套接字使用[QNetworkProxy](qnetworkproxy.html)，返回的描述符可能无法与原生socket函数使用。

套接字描述符时，无法使用[QAbstractSocket](qabstractsocket.html)在[UnconnectedState](qabstractsocket.html#SocketState-enum)。

**See also** [setSocketDescriptor](qabstractsocket.html#setSocketDescriptor)（ ） 。

```
QVariant QAbstractSocket.socketOption (self, SocketOption option)
```

返回的值_option_选项。

此功能被引入Qt的4.6 。

**See also** [setSocketOption](qabstractsocket.html#setSocketOption)（ ） 。

```
SocketType QAbstractSocket.socketType (self)
```

[

返回套接字的类型（ TCP，UDP或其他） 。

](qabstractsocket.html#SocketType-enum)

[**See also**](qabstractsocket.html#SocketType-enum) [QTcpSocket](qtcpsocket.html)和[QUdpSocket](qudpsocket.html)。

```
SocketState QAbstractSocket.state (self)
```

[

返回套接字的状态。

](qabstractsocket.html#SocketState-enum)

[**See also**](qabstractsocket.html#SocketState-enum) [error](qabstractsocket.html#error)（ ） 。

```
bool QAbstractSocket.waitForBytesWritten (self, int msecs = 30000)
```

从重新实现[QIODevice.waitForBytesWritten](qiodevice.html#waitForBytesWritten)（ ） 。

```
bool QAbstractSocket.waitForConnected (self, int msecs = 30000)
```

等待，直到套接字连接，高达_msecs_毫秒。如果连接已经建立，该函数将返回True，否则返回False 。当它返回False的情况下，你可以调用[error](qabstractsocket.html#error)（）来确定错误的原因。

下面的例子最多等待1秒，以建立连接：

```
 socket->connectToHost("imap", 143);
 if (socket->waitForConnected(1000))
     qDebug("Connected!");

```

如果毫秒为-1 ，此功能将不会超时。

**Note:**此功能可能稍长比等待_msecs_取决于所花费的时间来完成主机查找。

**Note:**多次调用该函数不累积的时间。如果函数超时，连接过程将被中止。

**See also** [connectToHost](qabstractsocket.html#connectToHost)（）和[connected](qabstractsocket.html#connected)（ ） 。

```
bool QAbstractSocket.waitForDisconnected (self, int msecs = 30000)
```

等待，直到插座断开连接，直至_msecs_毫秒。如果连接已经断开，则该函数返回True，否则返回False 。当它返回False的情况下，你可以调用[error](qabstractsocket.html#error)（）来确定错误的原因。

下面的例子最多等待一秒钟的连接被关闭：

```
 socket->disconnectFromHost();
     if (socket->state() == [QAbstractSocket](qabstractsocket.html).UnconnectedState ||
         socket->waitForDisconnected(1000))
         qDebug("Disconnected!");

```

如果毫秒为-1 ，此功能将不会超时。

**See also** [disconnectFromHost](qabstractsocket.html#disconnectFromHost)（）和[close](qabstractsocket.html#close)（ ） 。

```
bool QAbstractSocket.waitForReadyRead (self, int msecs = 30000)
```

从重新实现[QIODevice.waitForReadyRead](qiodevice.html#waitForReadyRead)（ ） 。

此功能块，直到新的数据可供读取和[readyRead()](qiodevice.html#readyRead)信号已经发出。之后，该函数将超时_msecs_毫秒，默认的超时时间为30000毫秒。

该函数返回True，如果[readyRead](qiodevice.html#readyRead)（ ）信号被发射，并有可供读取新数据，否则返回False （如果发生错误或者操作超时） 。

**See also** [waitForBytesWritten](qabstractsocket.html#waitForBytesWritten)（ ） 。

```
int QAbstractSocket.writeData (self, str data)
```

从重新实现[QIODevice.writeData](qiodevice.html#writeData)（ ） 。

* * *

## Qt Signal Documentation

```
void connected ()
```

这是该信号的默认超载。

之后此信号被发射[connectToHost](qabstractsocket.html#connectToHost)（ ）被调用，并连接已成功建立。

**Note:**在一些操作系统上的连接（）信号可以直接从所发射的[connectToHost](qabstractsocket.html#connectToHost)（ ）调用来连接到本地主机。

**See also** [connectToHost](qabstractsocket.html#connectToHost)（）和[disconnected](qabstractsocket.html#disconnected)（ ） 。

```
void disconnected ()
```

这是该信号的默认超载。

当插座已断开这个信号被发射。

**Warning:**如果您需要删除[sender](qobject.html#sender)在连接到它的插槽这个信号的（ ） ，请使用[deleteLater()](qobject.html#deleteLater)功能。

**See also** [connectToHost](qabstractsocket.html#connectToHost)（ ）[disconnectFromHost](qabstractsocket.html#disconnectFromHost)（）和[abort](qabstractsocket.html#abort)（ ） 。

```
void error (QAbstractSocket::SocketError)
```

这是该信号的默认超载。

这个信号被发射时发生错误之后。该_socketError_参数描述发生错误的类型。

[QAbstractSocket.SocketError](qabstractsocket.html#SocketError-enum)是不是注册的元类型，所以排队的连接，你将不得不用它注册[Q_DECLARE_METATYPE](qmetatype.html#Q_DECLARE_METATYPE)（）和[qRegisterMetaType](qmetatype.html#qRegisterMetaType)（ ） 。

**See also** [error](qabstractsocket.html#error)（ ）[errorString](qiodevice.html#errorString)（）和[Creating Custom Qt Types](index.htm)。

```
void hostFound ()
```

这是该信号的默认超载。

之后此信号被发射[connectToHost](qabstractsocket.html#connectToHost)（ ）被调用并且主机查找成功。

**Note:**由于Qt的4.6.3[QAbstractSocket](qabstractsocket.html)可以从发射hostFound （）直接[connectToHost](qabstractsocket.html#connectToHost)（ ）调用，因为一个DNS结果可能已经被缓存。

**See also** [connected](qabstractsocket.html#connected)（ ） 。

```
void proxyAuthenticationRequired (const QNetworkProxy&,QAuthenticator *)
```

这是该信号的默认超载。

这个信号可以被发射时，一_proxy_需要进行身份验证时使用。该_authenticator_对象可以被填充在与必需的细节，以便验证和持续的连接。

**Note:**这是不可能使用QueuedConnection连接到该信号，就好像所述认证没有被填充了新的信息时，该信号返回的连接失败。

此功能被引入Qt的4.3 。

**See also** [QAuthenticator](qauthenticator.html)和[QNetworkProxy](qnetworkproxy.html)。

```
void stateChanged (QAbstractSocket::SocketState)
```

这是该信号的默认超载。

这个信号被发射时[QAbstractSocket](qabstractsocket.html)的状态变化。该_socketState_参数是新的状态。

[QAbstractSocket.SocketState](qabstractsocket.html#SocketState-enum)是不是注册的元类型，所以排队的连接，你将不得不与Q_REGISTER_METATYPE （注册它）和[qRegisterMetaType](qmetatype.html#qRegisterMetaType)（ ） 。

**See also** [state](qabstractsocket.html#state)（）和[Creating Custom Qt Types](index.htm)。