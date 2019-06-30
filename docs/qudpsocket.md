# QUdpSocket Class Reference

## [[QtNetwork](index.htm) module]

该QUdpSocket类提供了一个UDP套接字。[More...](#details)

继承[QAbstractSocket](qabstractsocket.html)。

### Types

*   `enum BindFlag { DefaultForPlatform, ShareAddress, DontShareAddress, ReuseAddressHint }`
*   `class **[BindMode](index.htm)**`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `bool bind (self, QHostAddress address, int port)`
*   `bool bind (self, int port = 0)`
*   `bool bind (self, QHostAddress address, int port, BindMode mode)`
*   `bool bind (self, int port, BindMode mode)`
*   `bool hasPendingDatagrams (self)`
*   `bool joinMulticastGroup (self, QHostAddress groupAddress)`
*   `bool joinMulticastGroup (self, QHostAddress groupAddress, QNetworkInterface iface)`
*   `bool leaveMulticastGroup (self, QHostAddress groupAddress)`
*   `bool leaveMulticastGroup (self, QHostAddress groupAddress, QNetworkInterface iface)`
*   `QNetworkInterface multicastInterface (self)`
*   `int pendingDatagramSize (self)`
*   `(str, QHostAddress host, int port) readDatagram (self, int maxlen)`
*   `setMulticastInterface (self, QNetworkInterface iface)`
*   `int writeDatagram (self, str data, QHostAddress host, int port)`
*   `int writeDatagram (self, QByteArray datagram, QHostAddress host, int port)`

* * *

## Detailed Description

该QUdpSocket类提供了一个UDP套接字。

UDP（用户数据报协议）是一个轻量级的，不可靠的，面向数据报的，无连接的协议。它可以在可靠性并不重要使用。 QUdpSocket是的一个子类[QAbstractSocket](qabstractsocket.html)它允许您发送和接收UDP数据包。

使用这个类中最常用的方法是结合使用的地址和端口[bind](qudpsocket.html#bind)（ ） ，然后调用[writeDatagram](qudpsocket.html#writeDatagram)（）和[readDatagram](qudpsocket.html#readDatagram)（）来传输数据。如果你想使用标准[QIODevice](qiodevice.html) functions [read](qiodevice.html#read)（ ）[readLine](qiodevice.html#readLine)（ ）[write](qiodevice.html#write)（ ）等，你必须首先通过直接调用连接的套接字同行[connectToHost](qabstractsocket.html#connectToHost)（ ） 。

套接字发出的[bytesWritten](qiodevice.html#bytesWritten)（）信号每一个数据报被写入网络时间。如果你只是想发送数据报，你不需要调用[bind](qudpsocket.html#bind)（ ） 。

该[readyRead](qiodevice.html#readyRead)（）信号被发射时的数据报到达。在这种情况下，[hasPendingDatagrams](qudpsocket.html#hasPendingDatagrams)（ ）返回True 。通话[pendingDatagramSize](qudpsocket.html#pendingDatagramSize)（）以获得第一待处理数据包的大小，并[readDatagram](qudpsocket.html#readDatagram)（）来读取它。

**Note:**当您收到传入的数据报应该读的[readyRead](qiodevice.html#readyRead)（）信号，否则，该信号将不被发射的下一个数据报。

例如：

```
 void Server.initSocket()
 {
     udpSocket = new QUdpSocket(this);
     udpSocket->bind([QHostAddress](qhostaddress.html).LocalHost, 7755);

     connect(udpSocket, SIGNAL(readyRead()),
             this, SLOT(readPendingDatagrams()));
 }

 void Server.readPendingDatagrams()
 {
     while (udpSocket->hasPendingDatagrams()) {
         [QByteArray](qbytearray.html) datagram;
         datagram.resize(udpSocket->pendingDatagramSize());
         [QHostAddress](qhostaddress.html) sender;
         [quint16](index.htm#quint16-typedef) senderPort;

         udpSocket->readDatagram(datagram.data(), datagram.size(),
                                 &sender, &senderPort);

         processTheDatagram(datagram);
     }
 }

```

QUdpSocket还支持UDP多播。使用[joinMulticastGroup](qudpsocket.html#joinMulticastGroup)（）和[leaveMulticastGroup](qudpsocket.html#leaveMulticastGroup)（ ）来控制组成员，并[QAbstractSocket.MulticastTtlOption](qabstractsocket.html#SocketOption-enum)和[QAbstractSocket.MulticastLoopbackOption](qabstractsocket.html#SocketOption-enum)设置TTL和环回套接字选项。使用[setMulticastInterface](qudpsocket.html#setMulticastInterface)（ ）来控制出接口为组播数据报，并[multicastInterface](qudpsocket.html#multicastInterface)（）进行查询。

随着QUdpSocket ，您也可以使用建立一个UDP服务器的虚拟连接[connectToHost](qabstractsocket.html#connectToHost)（） ，然后使用[read](qiodevice.html#read)（）和[write](qiodevice.html#write)（ ）不指定接收器为每个数据报交换数据报。

该[Broadcast Sender](index.htm)，[Broadcast Receiver](index.htm)，[Multicast Sender](index.htm)和[Multicast Receiver](index.htm)示例说明了如何使用QUdpSocket中的应用。

### Symbian Platform Security Requirements

在Symbian ，它使用这个类的进程必须有`NetworkServices`平台的安全能力。如果客户端程序缺乏这种能力，操作将导致恐慌。

平台的安全功能是通过添加[TARGET.CAPABILITY](index.htm#target-capability)qmake的变量。

* * *

## Type Documentation

```
QUdpSocket.BindFlag
```

这个枚举变量描述了不同的标志，您可以通过修改的行为[QUdpSocket.bind](qudpsocket.html#bind)（ ） 。

**Note:**基于Symbian操作系统的绑定标志的行为依赖于过程capabilties 。如果过程中有NetworkControl能力，即使地址和端口已经被绑定了另一个套接字与任何标志的绑定尝试与ReuseAddressHint总是会成功的。如果进程没有NetworkControl能力，绑定企图地址和端口已经绑定了另一个套接字总是会失败。

| Constant | Value | Description |
| --- | --- | --- |
| `QUdpSocket.ShareAddress` | `0x1` | 允许其他服务绑定到同一个地址和端口。当多个进程共享听相同的地址和端口的单个服务的负载，这是有用的（例如，一个Web服务器与多个预分叉听众可以大大提高响应时间） 。然而，因为任何服务被允许重新绑定，此选项是受到一定的安全考虑。请注意，与ReuseAddressHint结合这个选项，你也可以让你的服务重新绑定现有的共享地址。在Unix上，这相当于SO_REUSEADDR套接字选项。在Windows上，这个选项被忽略。 |
| `QUdpSocket.DontShareAddress` | `0x2` | 完全绑定的地址和端口，所以没有其他的服务被允许重新绑定。通过将此选项[QUdpSocket.bind](qudpsocket.html#bind)（ ） ，这样保证了在successs ，你的服务是唯一一个监听地址和端口。没有服务被允许重新绑定，即使他们通过ReuseAddressHint 。此选项提供了比ShareAddress更安全，但在某些操作系统，它需要你以管理员权限运行的服务器。在Unix和Mac OS X ，不共享是用于绑定的地址和端口的默认行为，所以这个选项被忽略。在Windows中，此选项使用SO_EXCLUSIVEADDRUSE套接字选项。 |
| `QUdpSocket.ReuseAddressHint` | `0x4` | 提供一个提示[QUdpSocket](qudpsocket.html)它应该尝试重新绑定服务，即使地址和端口已经绑定了另一个套接字。在Windows上，这相当于SO_REUSEADDR套接字选项。在Unix中，该选项将被忽略。 |
| `QUdpSocket.DefaultForPlatform` | `0x0` | 在当前平台的默认选项。在Unix和Mac OS X ，这相当于（ DontShareAddress + ReuseAddressHint ） ，而在Windows相当于ShareAddress ，其。 |

这个枚举被引入或修改的Qt 4.1 。

该BindMode类型是一个typedef为[QFlags](index.htm)\u003cBindFlag\u003e 。它存储BindFlag值的或组合。

* * *

## Method Documentation

```
QUdpSocket.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建[QUdpSocket](qudpsocket.html)对象。

_parent_被传递到[QObject](qobject.html)构造函数。

**See also** [socketType](qabstractsocket.html#socketType)（ ） 。

```
bool QUdpSocket.bind (self, QHostAddress address, int port)
```

将此套接字绑定到地址_address_和端口_port_。当结合时，信号[readyRead](qiodevice.html#readyRead)（ ）每当一个UDP数据报到达指定的地址和端口发出。此功能是写的UDP服务器非常有用。

如果成功，该函数返回True，插座进入[BoundState](qabstractsocket.html#SocketState-enum)否则返回False。

该插座是使用绑定的[DefaultForPlatform](qudpsocket.html#BindFlag-enum) [BindMode](qudpsocket.html#BindFlag-enum)。

**See also** [readDatagram](qudpsocket.html#readDatagram)（ ） 。

```
bool QUdpSocket.bind (self, int port = 0)
```

这是一个重载函数。

结合_address_端口_port_使用[BindMode](qudpsocket.html#BindFlag-enum) _mode_。

这个函数是Qt 4.1中引入。

```
bool QUdpSocket.bind (self, QHostAddress address, int port, BindMode mode)
```

这是一个重载函数。

结合[QHostAddress](qhostaddress.html)：任何端口_port_。

```
bool QUdpSocket.bind (self, int port, BindMode mode)
```

这是一个重载函数。

结合[QHostAddress](qhostaddress.html)：任何端口_port_使用[BindMode](qudpsocket.html#BindFlag-enum) _mode_。

这个函数是Qt 4.1中引入。

```
bool QUdpSocket.hasPendingDatagrams (self)
```

返回True如果至少有一个数据报被等待被读取，否则返回False 。

**See also** [pendingDatagramSize](qudpsocket.html#pendingDatagramSize)（）和[readDatagram](qudpsocket.html#readDatagram)（ ） 。

```
bool QUdpSocket.joinMulticastGroup (self, QHostAddress groupAddress)
```

通过加入指定的组播组_groupAddress_由操作系统选择的缺省接口上。该插座必须是[BoundState](qabstractsocket.html#SocketState-enum)，否则会发生错误。

如果成功该函数返回True，否则返回False ，并相应地设置套接字错误。

此功能被引入Qt的4.8 。

**See also** [leaveMulticastGroup](qudpsocket.html#leaveMulticastGroup)（ ） 。

```
bool QUdpSocket.joinMulticastGroup (self, QHostAddress groupAddress, QNetworkInterface iface)
```

这是一个重载函数。

加入组播组的地址_groupAddress_接口上_iface_。

此功能被引入Qt的4.8 。

**See also** [leaveMulticastGroup](qudpsocket.html#leaveMulticastGroup)（ ） 。

```
bool QUdpSocket.leaveMulticastGroup (self, QHostAddress groupAddress)
```

叶由指定的组播组_groupAddress_由操作系统选择的缺省接口上。该插座必须是[BoundState](qabstractsocket.html#SocketState-enum)，否则会发生错误。

如果成功该函数返回True，否则返回False ，并相应地设置套接字错误。

此功能被引入Qt的4.8 。

**See also** [joinMulticastGroup](qudpsocket.html#joinMulticastGroup)（ ） 。

```
bool QUdpSocket.leaveMulticastGroup (self, QHostAddress groupAddress, QNetworkInterface iface)
```

这是一个重载函数。

叶由指定的组播组_groupAddress_接口上_iface_。

此功能被引入Qt的4.8 。

**See also** [joinMulticastGroup](qudpsocket.html#joinMulticastGroup)（ ） 。

```
QNetworkInterface QUdpSocket.multicastInterface (self)
```

[](qnetworkinterface.html)

[返回的出接口的组播数据报的接口。这相当于对IPv4套接字IP_MULTICAST_IF套接字选项和IPv6的套接字IPV6_MULTICAST_IF套接字选项。如果没有接口已经被预先设定的，这个函数返回一个无效的](qnetworkinterface.html)[QNetworkInterface](qnetworkinterface.html)。该插座必须是[BoundState](qabstractsocket.html#SocketState-enum)，否则无效[QNetworkInterface](qnetworkinterface.html)返回。

此功能被引入Qt的4.8 。

**See also** [setMulticastInterface](qudpsocket.html#setMulticastInterface)（ ） 。

```
int QUdpSocket.pendingDatagramSize (self)
```

返回第一个悬而未决的UDP数据报的大小。如果没有可用的数据报，这个函数返回-1 。

**See also** [hasPendingDatagrams](qudpsocket.html#hasPendingDatagrams)（）和[readDatagram](qudpsocket.html#readDatagram)（ ） 。

```
(str, QHostAddress host, int port) QUdpSocket.readDatagram (self, int maxlen)
```

接收到的数据报不大于_maxSize_字节并将其存储在_data_。发送者的主机地址和端口存储在*_address_和*_port_（除非该指针是0）。

在成功时返回数据包的大小，否则返回-1 。

If _maxSize_过小，则数据报的剩馀部分将会丢失。为了避免数据丢失，请致电[pendingDatagramSize](qudpsocket.html#pendingDatagramSize)（）尝试读出之前，以确定待处理数据报的大小。如果_maxSize_是0 ，则数据报将被丢弃。

**See also** [writeDatagram](qudpsocket.html#writeDatagram)（ ）[hasPendingDatagrams](qudpsocket.html#hasPendingDatagrams)（）和[pendingDatagramSize](qudpsocket.html#pendingDatagramSize)（ ） 。

```
QUdpSocket.setMulticastInterface (self, QNetworkInterface iface)
```

设置出接口的组播数据报的接口_iface_。这相当于对IPv4套接字IP_MULTICAST_IF套接字选项和IPv6的套接字IPV6_MULTICAST_IF套接字选项。该插座必须是[BoundState](qabstractsocket.html#SocketState-enum)，否则这个函数不执行任何操作。

此功能被引入Qt的4.8 。

**See also** [multicastInterface](qudpsocket.html#multicastInterface)（ ）[joinMulticastGroup](qudpsocket.html#joinMulticastGroup)（）和[leaveMulticastGroup](qudpsocket.html#leaveMulticastGroup)（ ） 。

```
int QUdpSocket.writeDatagram (self, str data, QHostAddress host, int port)
```

发送数据报的_data_大小_size_到主机地址_address_在端口_port_。返回发送成功的字节数，否则返回-1 。

数据包总是写成一个街区。一个数据报的最大尺寸是高度依赖于平台的，但可以低至8192字节。如果数据报太大，此函数将返回-1，[error](qabstractsocket.html#error)（ ）将返回[DatagramTooLargeError](qabstractsocket.html#SocketError-enum)。

发送数据包大于512字节一般是disadvised ，因为即使他们发送成功，他们很可能由IP层到达其最终目的地之前是支离破碎。

**Warning:**在S60 5.0和更早的版本中， writeDatagram返回值是不可靠的大型数据包。

**Warning:**在连接的UDP套接字调用这个函数可能会导致发送错误，并且没有数据包。如果您使用的是连接的socket ，使用[write](qiodevice.html#write)（ ）来发送数据报。

**See also** [readDatagram](qudpsocket.html#readDatagram)（）和[write](qiodevice.html#write)（ ） 。

```
int QUdpSocket.writeDatagram (self, QByteArray datagram, QHostAddress host, int port)
```

这是一个重载函数。

发送的数据报_datagram_到主机地址_host_并在端口_port_。