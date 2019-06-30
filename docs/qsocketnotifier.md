# QSocketNotifier Class Reference

## [[QtCore](index.htm) module]

该QSocketNotifier类提供了一个文件描述符监测活动的支持。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum Type { Read, Write, Exception }`

### Methods

*   `__init__ (self, int socket, Type type, QObject parent = None)`
*   `bool event (self, QEvent)`
*   `bool isEnabled (self)`
*   `setEnabled (self, bool)`
*   `int socket (self)`
*   `Type type (self)`

### Qt Signals

*   `void activated (int)`

* * *

## Detailed Description

该QSocketNotifier类提供了一个文件描述符监测活动的支持。

该QSocketNotifier使得能够整合Qt的事件循环与基于文件描述符其他事件循环。例如，本 [CORBA Framework](http://qt.digia.com/products/add-on-products/catalog/4/Utilities/qtcorba/)使用它来处理CORBA的事件。在Qt的主事件循环（当检测到文件描述符行动[QCoreApplication.exec](qcoreapplication.html#exec)（））。

一旦你已经使用一个低级别（通常特定于平台）的API打开一个设备，你可以创建一个socket通知监视的文件描述符。该插座通知是默认启用的，也就是说，它发出的[activated](qsocketnotifier.html#activated)（ ）信号时对应其类型的套接字事件发生。连接[activated](qsocketnotifier.html#activated)（）信号，要在对应的插槽通知的类型的事件发生时要调用的插槽。

有三种类型的套接字通知者的：读，写和异常。类型由所描述的[Type](qsocketnotifier.html#Type-enum)枚举，而且必须构建插座通知时指定。项目建成后可利用装置[type](qsocketnotifier.html#type)（）函数。请注意，如果你需要同时监视读取和相同的文件描述符写入，您必须创建两个socket通知者。还请注意，这是不可能安装相同类型的两个插座通知器（[Read](qsocketnotifier.html#Type-enum)，[Write](qsocketnotifier.html#Type-enum)，[Exception](qsocketnotifier.html#Type-enum)）在同一个插座上。

该[setEnabled](qsocketnotifier.html#setEnabled)（ ）函数允许你禁用和启用套接字通知。它一般最好明确地启用或禁用该插座通知器，特别是用于写通知器。停用的通知忽略套接字事件（同样的效果不是创建套接字通知） 。使用[isEnabled](qsocketnotifier.html#isEnabled)（ ）函数来确定通知的当前状态。

最后，您可以使用[socket](qsocketnotifier.html#socket)（ ）函数来获取套接字标识符。虽然该类称为QSocketNotifier ，它通常是用于其它类型的设备比套接字。[QTcpSocket](qtcpsocket.html)和[QUdpSocket](qudpsocket.html)通过信号提供通知，所以通常没有必要对他们使用QSocketNotifier 。

### Notes for Windows Users

传递给QSocketNotifier插座将成为不可阻挡，即使它被创建为一个阻塞套接字。该[activated](qsocketnotifier.html#activated)（）信号是由主机上的高活性一般有时触发，即使没有要读出。然后从插座后续读取可能会失败，错误表明有可用（例如，没有数据，`WSAEWOULDBLOCK`） 。这是一个操作系统的限制，而不是在QSocketNotifier的错误。

为了确保插座通知句柄读通知正确，当你收到通知按照下列步骤操作：

1.  禁用通知。
2.  从套接字读取数据。
3.  重新启用的通知，如果您有兴趣更多的数据（如经书面一个新的命令到远程服务器后） 。

为了确保插座通知处理正确地写通知，当你收到通知按照下列步骤操作：

1.  禁用通知。
2.  写入尽可能多的数据，你可以（之前`EWOULDBLOCK`返回） 。
3.  重新启用通知，如果你有更多的数据来写。

**Further information:**在Windows下，Qt始终禁用通知得到通知后，只有重新启用它，如果更多的数据的预期。例如，如果数据是从套接字中读取，它可以被用来读取更多，或者，如果读取或写入是不可能的，因为插座会阻塞，在这种情况下，需要在尝试重新读取或写入之前的等待时间。

* * *

## Type Documentation

```
QSocketNotifier.Type
```

这个枚举变量描述了不同类型的套接字通知器可以识别的事件。构建插座通知时，必须指定类型。

请注意，如果你需要同时监视读取和相同的文件描述符写入，您必须创建两个socket通知者。另请注意，这是不可能安装在同一个插座上同类型（读，写，异常）的双插槽通知者。

| Constant | Value | Description |
| --- | --- | --- |
| `QSocketNotifier.Read` | `0` | 有数据被读取。 |
| `QSocketNotifier.Write` | `1` | 数据可以被写入。 |
| `QSocketNotifier.Exception` | `2` | 发生异常。我们不建议使用本品。 |

**See also** [QSocketNotifier](qsocketnotifier.html#QSocketNotifier)（）和[type](qsocketnotifier.html#type)（ ） 。

* * *

## Method Documentation

```
QSocketNotifier.__init__ (self, int socket, Type type, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个套接字通知给定的_parent_。它使_socket_和手表给定的事件_type_。

它一般最好明确地启用或禁用该插座通知器，特别是用于写通知器。

**Note for Windows users:**传递到插座[QSocketNotifier](qsocketnotifier.html)将成为非阻塞的，即使它被创建为一个阻塞套接字。

**See also** [setEnabled](qsocketnotifier.html#setEnabled)（）和[isEnabled](qsocketnotifier.html#isEnabled)（ ） 。

```
bool QSocketNotifier.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
bool QSocketNotifier.isEnabled (self)
```

返回True如果通知已启用，否则返回False 。

**See also** [setEnabled](qsocketnotifier.html#setEnabled)（ ） 。

```
QSocketNotifier.setEnabled (self, bool)
```

这种方法也是一个Qt槽与C + +的签名`void setEnabled(bool)`。

If _enable_为True，则通知被启用，否则通知无效。

该通知是默认启用的，也就是说，它发出的[activated](qsocketnotifier.html#activated)（ ）信号时对应于插座的事件[type](qsocketnotifier.html#type)发生。如果它被禁用，它会忽略插座事件（同样的效果不是创建套接字通知） 。

写通知者一般应后立即停用[activated](qsocketnotifier.html#activated)（）信号已经发出

**See also** [isEnabled](qsocketnotifier.html#isEnabled)（）和[activated](qsocketnotifier.html#activated)（ ） 。

```
int QSocketNotifier.socket (self)
```

返回指定给构造函数的接口标识符。

**See also** [type](qsocketnotifier.html#type)（ ） 。

```
Type QSocketNotifier.type (self)
```

[

返回指定给构造函数的套接字事件类型。

](qsocketnotifier.html#Type-enum)

[**See also**](qsocketnotifier.html#Type-enum) [socket](qsocketnotifier.html#socket)（ ） 。

* * *

## Qt Signal Documentation

```
void activated (int)
```

这是该信号的默认超载。

这个信号被发射时的插座通知器被启用，并且套接字事件对应于其[type](qsocketnotifier.html#Type-enum)发生。

套接字标识符传递的_socket_参数。

**See also** [type](qsocketnotifier.html#type)（）和[socket](qsocketnotifier.html#socket)（ ） 。