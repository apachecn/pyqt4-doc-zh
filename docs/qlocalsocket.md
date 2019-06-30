# QLocalSocket Class Reference

## [[QtNetwork](index.htm) module]

该QLocalSocket类提供了一个本地套接字。[More...](#details)

继承[QIODevice](qiodevice.html)。

### Types

*   `enum LocalSocketError { ConnectionRefusedError, PeerClosedError, ServerNotFoundError, SocketAccessError, ..., UnknownSocketError }`
*   `enum LocalSocketState { UnconnectedState, ConnectingState, ConnectedState, ClosingState }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `abort (self)`
*   `int bytesAvailable (self)`
*   `int bytesToWrite (self)`
*   `bool canReadLine (self)`
*   `close (self)`
*   `connectToServer (self, QString name, QIODevice.OpenMode mode = QIODevice.ReadWrite)`
*   `disconnectFromServer (self)`
*   `LocalSocketError error (self)`
*   `bool flush (self)`
*   `QString fullServerName (self)`
*   `bool isSequential (self)`
*   `bool isValid (self)`
*   `int readBufferSize (self)`
*   `str readData (self, int maxlen)`
*   `QString serverName (self)`
*   `setReadBufferSize (self, int size)`
*   `bool setSocketDescriptor (self, sip.voidptr socketDescriptor, LocalSocketState state = QLocalSocket.ConnectedState, QIODevice.OpenMode mode = QIODevice.ReadWrite)`
*   `sip.voidptr socketDescriptor (self)`
*   `LocalSocketState state (self)`
*   `bool waitForBytesWritten (self, int msecs = 30000)`
*   `bool waitForConnected (self, int msecs = 30000)`
*   `bool waitForDisconnected (self, int msecs = 30000)`
*   `bool waitForReadyRead (self, int msecs = 30000)`
*   `int writeData (self, str)`

### Qt Signals

*   `void connected ()`
*   `void disconnected ()`
*   `void error (QLocalSocket::LocalSocketError)`
*   `void stateChanged (QLocalSocket::LocalSocketState)`

* * *

## Detailed Description

该QLocalSocket类提供了一个本地套接字。

在Windows上，这是一个命名管道，并在Unix上，这是一个本地的域套接字。

如果发生错误， socketError （）返回的错误的类型，并且[errorString](qiodevice.html#errorString)（ ）可以被调用来获取发生了什么可读的描述。

虽然QLocalSocket是专为一个事件循环使用，它可以使用它没有之一。在这种情况下，您必须使用[waitForConnected](qlocalsocket.html#waitForConnected)（ ）[waitForReadyRead](qlocalsocket.html#waitForReadyRead)（ ）[waitForBytesWritten](qlocalsocket.html#waitForBytesWritten)（）和[waitForDisconnected](qlocalsocket.html#waitForDisconnected)（），它会阻塞，直到操作完成或超时期满。

请注意，此功能不支持的Windows版本早于Windows XP 。

* * *

## Type Documentation

```
QLocalSocket.LocalSocketError
```

该LocalServerError枚举表示可能发生的错误。可以通过调用来检索最新的错误[QLocalSocket.error](qlocalsocket.html#error)（ ） 。

| Constant | Value | Description |
| --- | --- | --- |
| `QLocalSocket.ConnectionRefusedError` | `QAbstractSocket.ConnectionRefusedError` | 连接被对等（或超时）拒绝。 |
| `QLocalSocket.PeerClosedError` | `QAbstractSocket.RemoteHostClosedError` | 远程套接字关闭了连接。请注意，客户端套接字（也就是该套接字）远程关闭通知发出后将会关闭。 |
| `QLocalSocket.ServerNotFoundError` | `QAbstractSocket.HostNotFoundError` | 本地套接字名未找到。 |
| `QLocalSocket.SocketAccessError` | `QAbstractSocket.SocketAccessError` | 套接字操作失败，因为该应用程序缺乏必要的特权。 |
| `QLocalSocket.SocketResourceError` | `QAbstractSocket.SocketResourceError` | 本地系统跑出来的资源（例如，太多的套接字）的。 |
| `QLocalSocket.SocketTimeoutError` | `QAbstractSocket.SocketTimeoutError` | 套接字操作超时。 |
| `QLocalSocket.DatagramTooLargeError` | `QAbstractSocket.DatagramTooLargeError` | 数据报比操作系统的限制（其可以是低至8192字节）大。 |
| `QLocalSocket.ConnectionError` | `QAbstractSocket.NetworkError` | 与连接时出错。 |
| `QLocalSocket.UnsupportedSocketOperationError` | `QAbstractSocket.UnsupportedSocketOperationError` | 不是由本地操作系统支持请求的套接字操作。 |
| `QLocalSocket.UnknownSocketError` | `QAbstractSocket.UnknownSocketError` | 发生不明的错误。 |

```
QLocalSocket.LocalSocketState
```

这个枚举变量描述了不同的状态，其中一个插座即可。

| Constant | Value | Description |
| --- | --- | --- |
| `QLocalSocket.UnconnectedState` | `QAbstractSocket.UnconnectedState` | 该套接字没有连接。 |
| `QLocalSocket.ConnectingState` | `QAbstractSocket.ConnectingState` | 插座已经开始建立连接。 |
| `QLocalSocket.ConnectedState` | `QAbstractSocket.ConnectedState` | 连接建立。 |
| `QLocalSocket.ClosingState` | `QAbstractSocket.ClosingState` | 该插座是即将关闭（数据仍可能等待写入） 。 |

**See also** [QLocalSocket.state](qlocalsocket.html#state)（ ） 。

* * *

## Method Documentation

```
QLocalSocket.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建一个新的本地套接字。该_parent_参数被传递给[QObject](qobject.html)的构造。

```
QLocalSocket.abort (self)
```

中止当前连接并重置插口。不像[disconnectFromServer](qlocalsocket.html#disconnectFromServer)（ ） ，这个函数立即关闭套接字，写缓冲区清除任何挂起的数据。

**See also** [disconnectFromServer](qlocalsocket.html#disconnectFromServer)（）和[close](qlocalsocket.html#close)（ ） 。

```
int QLocalSocket.bytesAvailable (self)
```

从重新实现[QIODevice.bytesAvailable](qiodevice.html#bytesAvailable)（ ） 。

```
int QLocalSocket.bytesToWrite (self)
```

从重新实现[QIODevice.bytesToWrite](qiodevice.html#bytesToWrite)（ ） 。

```
bool QLocalSocket.canReadLine (self)
```

从重新实现[QIODevice.canReadLine](qiodevice.html#canReadLine)（ ） 。

```
QLocalSocket.close (self)
```

从重新实现[QIODevice.close](qiodevice.html#close)（ ） 。

```
QLocalSocket.connectToServer (self, QString name, QIODevice.OpenMode mode = QIODevice.ReadWrite)
```

企图使一个连接_name_。

该插座是在给定的开_openMode_并首次进入[ConnectingState](qlocalsocket.html#LocalSocketState-enum)。然后，它尝试连接到由查询返回的地址或地址。最后，如果建立了连接，[QLocalSocket](qlocalsocket.html)进入[ConnectedState](qlocalsocket.html#LocalSocketState-enum)并发出[connected](qlocalsocket.html#connected)（ ） 。

在任何点，该插座能发射[error](qlocalsocket.html#error)（）来通知发生了错误。

另请参阅[state](qlocalsocket.html#state)（ ）[serverName](qlocalsocket.html#serverName)（）和[waitForConnected](qlocalsocket.html#waitForConnected)（ ） 。

```
QLocalSocket.disconnectFromServer (self)
```

试图关闭套接字。如果有挂起的数据等待写入，[QLocalSocket](qlocalsocket.html)将进入[ClosingState](qlocalsocket.html#LocalSocketState-enum)并等待，直到所有数据已经写入。最终，将进入[UnconnectedState](qlocalsocket.html#LocalSocketState-enum)和发射disconnectedFromServer （）信号。

**See also** [connectToServer](qlocalsocket.html#connectToServer)（ ） 。

```
LocalSocketError QLocalSocket.error (self)
```

[

返回上次发生错误的类型。

](qlocalsocket.html#LocalSocketError-enum)

[**See also**](qlocalsocket.html#LocalSocketError-enum) [state](qlocalsocket.html#state)（）和[errorString](qiodevice.html#errorString)（ ） 。

```
bool QLocalSocket.flush (self)
```

该函数将尽可能地从内部写缓冲区到插座，而不会阻塞。如果任何数据被写入时，该函数将返回True，否则返回False。

调用此函数，如果你需要[QLocalSocket](qlocalsocket.html)立即开始发送缓冲数据。成功写入的字节数依赖于操作系统。在大多数情况下，你不需要调用这个函数，因为[QLocalSocket](qlocalsocket.html)将自动开始发送数据，一旦控制返回到事件循环。在不存在的事件循环，调用[waitForBytesWritten](qlocalsocket.html#waitForBytesWritten)（ ）来代替。

**See also** [write](qiodevice.html#write)（）和[waitForBytesWritten](qlocalsocket.html#waitForBytesWritten)（ ） 。

```
QString QLocalSocket.fullServerName (self)
```

返回该套接字被连接到服务器的路径。

**Note:**这个函数的返回值是特定于平台的。

**See also** [connectToServer](qlocalsocket.html#connectToServer)（）和[serverName](qlocalsocket.html#serverName)（ ） 。

```
bool QLocalSocket.isSequential (self)
```

从重新实现[QIODevice.isSequential](qiodevice.html#isSequential)（ ） 。

```
bool QLocalSocket.isValid (self)
```

返回True如果套接字是有效的，并准备使用，否则返回False 。

**Note:**套接字的状态必须[ConnectedState](qlocalsocket.html#LocalSocketState-enum)阅读和写作之前可能发生。

**See also** [state](qlocalsocket.html#state)（）和[connectToServer](qlocalsocket.html#connectToServer)（ ） 。

```
int QLocalSocket.readBufferSize (self)
```

返回内部读缓冲区的大小。这限制了数据的客户端可以在打电话之前收取的金额[read](qiodevice.html#read)（）或[readAll](qiodevice.html#readAll)（ ） 。 0读缓冲区的大小（默认值）意味着缓冲区有没有大小限制，以确保数据不会丢失。

**See also** [setReadBufferSize](qlocalsocket.html#setReadBufferSize)（）和[read](qiodevice.html#read)（ ） 。

```
str QLocalSocket.readData (self, int maxlen)
```

从重新实现[QIODevice.readData](qiodevice.html#readData)（ ） 。

```
QString QLocalSocket.serverName (self)
```

所指定的返回对端的名称[connectToServer](qlocalsocket.html#connectToServer)（ ） ，或空[QString](qstring.html)如果[connectToServer](qlocalsocket.html#connectToServer)（ ）没有被调用或者它失败了。

**See also** [connectToServer](qlocalsocket.html#connectToServer)（）和[fullServerName](qlocalsocket.html#fullServerName)（ ） 。

```
QLocalSocket.setReadBufferSize (self, int size)
```

载的大小[QLocalSocket](qlocalsocket.html)的内部读缓冲区是_size_字节。

如果缓冲区大小被限制为一定的大小，[QLocalSocket](qlocalsocket.html)将不缓存数据超过此大小。特殊情况下，为0的缓冲区大小意味着读缓存器是无限的，所有输入的数据进行缓冲。这是默认的。

此选项很有用，如果你只在读取特定时间点的数据（例如，在实时流应用程序），或者如果你想保护你的插座对接收的数据过多，最终可能导致应用程序用完内存。

**See also** [readBufferSize](qlocalsocket.html#readBufferSize)（）和[read](qiodevice.html#read)（ ） 。

```
bool QLocalSocket.setSocketDescriptor (self, sip.voidptr socketDescriptor, LocalSocketState state = QLocalSocket.ConnectedState, QIODevice.OpenMode mode = QIODevice.ReadWrite)
```

初始化[QLocalSocket](qlocalsocket.html)与本地套接字描述符_socketDescriptor_。返回True如果socketDescriptor被接受为有效的套接字描述符，否则返回False 。该插座是由指定的模式打开_openMode_，并进入由指定的套接字状态_socketState_。

**Note:**这是不可能的初始化两个本地套接字使用相同的本地套接字描述符。

**See also** [socketDescriptor](qlocalsocket.html#socketDescriptor)（ ）[state](qlocalsocket.html#state)（）和[openMode](qiodevice.html#openMode)（ ） 。

```
sip.voidptr QLocalSocket.socketDescriptor (self)
```

返回的本地套接字描述符[QLocalSocket](qlocalsocket.html)如果对象是可用的，否则返回-1 。

套接字描述符时，无法使用[QLocalSocket](qlocalsocket.html)在[UnconnectedState](qlocalsocket.html#LocalSocketState-enum)。

**See also** [setSocketDescriptor](qlocalsocket.html#setSocketDescriptor)（ ） 。

```
LocalSocketState QLocalSocket.state (self)
```

[

返回套接字的状态。

](qlocalsocket.html#LocalSocketState-enum)

[**See also**](qlocalsocket.html#LocalSocketState-enum) [error](qlocalsocket.html#error)（ ） 。

```
bool QLocalSocket.waitForBytesWritten (self, int msecs = 30000)
```

从重新实现[QIODevice.waitForBytesWritten](qiodevice.html#waitForBytesWritten)（ ） 。

```
bool QLocalSocket.waitForConnected (self, int msecs = 30000)
```

等待，直到套接字连接，高达_msecs_毫秒。如果连接已经建立，该函数将返回True，否则返回False 。当它返回False的情况下，你可以调用[error](qlocalsocket.html#error)（）来确定错误的原因。

下面的例子最多等待1秒，以建立连接：

```
 socket->connectToServer("market");
 if (socket->waitForConnected(1000))
     qDebug("Connected!");

```

If _msecs_为-1 ，此功能将不会超时。

**See also** [connectToServer](qlocalsocket.html#connectToServer)（）和[connected](qlocalsocket.html#connected)（ ） 。

```
bool QLocalSocket.waitForDisconnected (self, int msecs = 30000)
```

等待，直到插座断开连接，直至_msecs_毫秒。如果连接已经断开，则该函数返回True，否则返回False 。当它返回False的情况下，你可以调用[error](qlocalsocket.html#error)（）来确定错误的原因。

下面的例子最多等待一秒钟的连接被关闭：

```
 socket->disconnectFromServer();
 if (socket->waitForDisconnected(1000))
     qDebug("Disconnected!");

```

If _msecs_为-1 ，此功能将不会超时。

**See also** [disconnectFromServer](qlocalsocket.html#disconnectFromServer)（）和[close](qlocalsocket.html#close)（ ） 。

```
bool QLocalSocket.waitForReadyRead (self, int msecs = 30000)
```

从重新实现[QIODevice.waitForReadyRead](qiodevice.html#waitForReadyRead)（ ） 。

此功能块，直到数据可供读取和[readyRead()](qiodevice.html#readyRead)信号已经发出。之后，该函数将超时_msecs_毫秒，默认的超时时间为30000毫秒。

如果数据可供读取该函数返回True ，否则返回False （如果发生错误或者操作超时） 。

**See also** [waitForBytesWritten](qlocalsocket.html#waitForBytesWritten)（ ） 。

```
int QLocalSocket.writeData (self, str)
```

从重新实现[QIODevice.writeData](qiodevice.html#writeData)（ ） 。

* * *

## Qt Signal Documentation

```
void connected ()
```

这是该信号的默认超载。

之后此信号被发射[connectToServer](qlocalsocket.html#connectToServer)（ ）被调用，并连接已成功建立。

**See also** [connectToServer](qlocalsocket.html#connectToServer)（）和[disconnected](qlocalsocket.html#disconnected)（ ） 。

```
void disconnected ()
```

这是该信号的默认超载。

当插座已断开这个信号被发射。

**See also** [connectToServer](qlocalsocket.html#connectToServer)（ ）[disconnectFromServer](qlocalsocket.html#disconnectFromServer)（ ）[abort](qlocalsocket.html#abort)（）和[connected](qlocalsocket.html#connected)（ ） 。

```
void error (QLocalSocket::LocalSocketError)
```

这是该信号的默认超载。

这个信号被发射时发生错误之后。该_socketError_参数描述发生错误的类型。

[QLocalSocket.LocalSocketError](qlocalsocket.html#LocalSocketError-enum)是不是注册的元类型，所以排队的连接，你将不得不用它注册[Q_DECLARE_METATYPE](qmetatype.html#Q_DECLARE_METATYPE)（）和[qRegisterMetaType](qmetatype.html#qRegisterMetaType)（ ） 。

**See also** [error](qlocalsocket.html#error)（ ）[errorString](qiodevice.html#errorString)（）和[Creating Custom Qt Types](index.htm)。

```
void stateChanged (QLocalSocket::LocalSocketState)
```

这是该信号的默认超载。

这个信号被发射时[QLocalSocket](qlocalsocket.html)的状态变化。该_socketState_参数是新的状态。

QLocalSocket.SocketState是不是注册的元类型，所以排队的连接，你将不得不用它注册[Q_DECLARE_METATYPE](qmetatype.html#Q_DECLARE_METATYPE)（）和[qRegisterMetaType](qmetatype.html#qRegisterMetaType)（ ） 。

**See also** [state](qlocalsocket.html#state)（）和[Creating Custom Qt Types](index.htm)。