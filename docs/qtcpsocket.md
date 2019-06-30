# QTcpSocket Class Reference

## [[QtNetwork](index.htm) module]

该QTcpSocket类提供了一个TCP套接字。[More...](#details)

继承[QAbstractSocket](qabstractsocket.html)。

通过继承[QSslSocket](qsslsocket.html)。

### Methods

*   `__init__ (self, QObject parent = None)`

* * *

## Detailed Description

该QTcpSocket类提供了一个TCP套接字。

TCP（传输控制协议）是一种可靠的，面向流的，面向连接的传输协议。它特别适合用于井数据的连续传输。

QTcpSocket是一个方便的子类[QAbstractSocket](qabstractsocket.html)使您可以建立一个TCP连接和数据的传输流。请参阅[QAbstractSocket](qabstractsocket.html)文档。

**Note:**TCP套接字不能被打开[QIODevice.Unbuffered](qiodevice.html#OpenModeFlag-enum)模式。

### Symbian Platform Security Requirements

在Symbian ，它使用这个类的进程必须有`NetworkServices`平台的安全能力。如果客户端程序缺乏这种能力，它会导致恐慌。

平台的安全功能是通过添加[TARGET.CAPABILITY](index.htm#target-capability)qmake的变量。

* * *

## Method Documentation

```
QTcpSocket.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建[QTcpSocket](qtcpsocket.html)在状态对象`UnconnectedState`。

_parent_到传递[QObject](qobject.html)构造函数。

**See also** [socketType](qabstractsocket.html#socketType)（ ） 。