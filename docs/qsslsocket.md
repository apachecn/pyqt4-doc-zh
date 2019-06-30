# QSslSocket Class Reference

## [[QtNetwork](index.htm) module]

该QSslSocket类提供的SSL加密套接字的客户端和服务器。[More...](#details)

继承[QTcpSocket](qtcpsocket.html)。

### Types

*   `enum PeerVerifyMode { VerifyNone, QueryPeer, VerifyPeer, AutoVerifyPeer }`
*   `enum SslMode { UnencryptedMode, SslClientMode, SslServerMode }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `abort (self)`
*   `addCaCertificate (self, QSslCertificate certificate)`
*   `bool addCaCertificates (self, QString path, QSsl.EncodingFormat format = QSsl.Pem, QRegExp.PatternSyntax syntax = QRegExp.FixedString)`
*   `addCaCertificates (self, list-of-QSslCertificate certificates)`
*   `bool atEnd (self)`
*   `int bytesAvailable (self)`
*   `int bytesToWrite (self)`
*   `list-of-QSslCertificate caCertificates (self)`
*   `bool canReadLine (self)`
*   `list-of-QSslCipher ciphers (self)`
*   `close (self)`
*   `connectToHostEncrypted (self, QString hostName, int port, QIODevice.OpenMode mode = QIODevice.ReadWrite)`
*   `connectToHostEncrypted (self, QString hostName, int port, QString sslPeerName, QIODevice.OpenMode mode = QIODevice.ReadWrite)`
*   `connectToHostImplementation (self, QString hostName, int port, QIODevice.OpenMode openMode)`
*   `disconnectFromHostImplementation (self)`
*   `int encryptedBytesAvailable (self)`
*   `int encryptedBytesToWrite (self)`
*   `bool flush (self)`
*   `ignoreSslErrors (self)`
*   `ignoreSslErrors (self, list-of-QSslError errors)`
*   `bool isEncrypted (self)`
*   `QSslCertificate localCertificate (self)`
*   `SslMode mode (self)`
*   `QSslCertificate peerCertificate (self)`
*   `list-of-QSslCertificate peerCertificateChain (self)`
*   `int peerVerifyDepth (self)`
*   `PeerVerifyMode peerVerifyMode (self)`
*   `QString peerVerifyName (self)`
*   `QSslKey privateKey (self)`
*   `QSsl.SslProtocol protocol (self)`
*   `str readData (self, int maxlen)`
*   `QSslCipher sessionCipher (self)`
*   `setCaCertificates (self, list-of-QSslCertificate certificates)`
*   `setCiphers (self, list-of-QSslCipher ciphers)`
*   `setCiphers (self, QString ciphers)`
*   `setLocalCertificate (self, QSslCertificate certificate)`
*   `setLocalCertificate (self, QString path, QSsl.EncodingFormat format = QSsl.Pem)`
*   `setPeerVerifyDepth (self, int depth)`
*   `setPeerVerifyMode (self, PeerVerifyMode mode)`
*   `setPeerVerifyName (self, QString hostName)`
*   `setPrivateKey (self, QSslKey key)`
*   `setPrivateKey (self, QString fileName, QSsl.KeyAlgorithm algorithm = QSsl.Rsa, QSsl.EncodingFormat format = QSsl.Pem, QByteArray passPhrase = QByteArray())`
*   `setProtocol (self, QSsl.SslProtocol protocol)`
*   `setReadBufferSize (self, int size)`
*   `bool setSocketDescriptor (self, int socketDescriptor, QAbstractSocket.SocketState state = QAbstractSocket.ConnectedState, QIODevice.OpenMode mode = QIODevice.ReadWrite)`
*   `setSocketOption (self, QAbstractSocket.SocketOption option, QVariant value)`
*   `setSslConfiguration (self, QSslConfiguration config)`
*   `QVariant socketOption (self, QAbstractSocket.SocketOption option)`
*   `QSslConfiguration sslConfiguration (self)`
*   `list-of-QSslError sslErrors (self)`
*   `startClientEncryption (self)`
*   `startServerEncryption (self)`
*   `bool waitForBytesWritten (self, int msecs = 30000)`
*   `bool waitForConnected (self, int msecs = 30000)`
*   `bool waitForDisconnected (self, int msecs = 30000)`
*   `bool waitForEncrypted (self, int msecs = 30000)`
*   `bool waitForReadyRead (self, int msecs = 30000)`
*   `int writeData (self, str data)`

### Static Methods

*   `addDefaultCaCertificate (QSslCertificate certificate)`
*   `bool addDefaultCaCertificates (QString path, QSsl.EncodingFormat format = QSsl.Pem, QRegExp.PatternSyntax syntax = QRegExp.FixedString)`
*   `addDefaultCaCertificates (list-of-QSslCertificate certificates)`
*   `list-of-QSslCertificate defaultCaCertificates ()`
*   `list-of-QSslCipher defaultCiphers ()`
*   `setDefaultCaCertificates (list-of-QSslCertificate certificates)`
*   `setDefaultCiphers (list-of-QSslCipher ciphers)`
*   `list-of-QSslCipher supportedCiphers ()`
*   `bool supportsSsl ()`
*   `list-of-QSslCertificate systemCaCertificates ()`

### Qt Signals

*   `void encrypted ()`
*   `void encryptedBytesWritten (qint64)`
*   `void modeChanged (QSslSocket::SslMode)`
*   `void peerVerifyError (const QSslError&)`
*   `void sslErrors (const QList&lt;QSslError&gt;&)`

* * *

## Detailed Description

该QSslSocket类提供的SSL加密套接字的客户端和服务器。

QSslSocket建立可用于传输加密数据安全，加密的TCP连接。它可以同时在客户端和服务器模式下运行，并且它支持SSL的现代化协议，包括支持SSLv3和TLSv1 。默认情况下， QSslSocket使用的TLSv1 ，但是你可以通过调用改变SSL协议[setProtocol](qsslsocket.html#setProtocol)（）只要你握手之前做到这一点已经开始。

SSL加密运行在现有TCP流顶部的插座进入后[ConnectedState](qabstractsocket.html#SocketState-enum)。有两种简单的方法来建立使用QSslSocket安全连接：通过即时SSL握手，或连接已经建立了未加密模式之后延迟SSL握手发生。

使用QSslSocket最常见的方式是通过调用构造对象，并启动安全连接[connectToHostEncrypted](qsslsocket.html#connectToHostEncrypted)（ ） 。这个方法立刻执行SSL握手一旦连接已经建立。

```
 QSslSocket *socket = new QSslSocket(this);
 connect(socket, SIGNAL(encrypted()), this, SLOT(ready()));

 socket->connectToHostEncrypted("imap.example.com", 993);

```

作为一个普通的[QTcpSocket](qtcpsocket.html)， QSslSocket进入[HostLookupState](qabstractsocket.html#SocketState-enum)，[ConnectingState](qabstractsocket.html#SocketState-enum)，最后是[ConnectedState](qabstractsocket.html#SocketState-enum)如果连接成功。握手然后自动启动，如果成功，[encrypted](qsslsocket.html#encrypted)（）信号被发射，以指示插座已经进入了加密的状态，并准备好使用。

注意，数据可从返回后，立即被写入到插座[connectToHostEncrypted](qsslsocket.html#connectToHostEncrypted)（ ）（即，前[encrypted](qsslsocket.html#encrypted)（）信号被发射） 。该数据被排队在QSslSocket后才[encrypted](qsslsocket.html#encrypted)（）信号被发射。

使用延迟SSL握手，以确保现有连接的一个例子是SSL服务器固定一个传入的连接的情况下。假设你创建一个SSL服务器类作为子类[QTcpServer](qtcpserver.html)。你会复盖[QTcpServer.incomingConnection](qtcpserver.html#incomingConnection)（ ）的东西，如下面的例子，它首先构造QSslSocket的一个实例，然后调用[setSocketDescriptor](qsslsocket.html#setSocketDescriptor)（ ）新的套接字的描述符设置为现有的传入然后，它开始通过调用SSL握手[startServerEncryption](qsslsocket.html#startServerEncryption)（ ） 。

```
 void SslServer.incomingConnection(int socketDescriptor)
 {
     QSslSocket *serverSocket = new QSslSocket;
     if (serverSocket->setSocketDescriptor(socketDescriptor)) {
         connect(serverSocket, SIGNAL(encrypted()), this, SLOT(ready()));
         serverSocket->startServerEncryption();
     } else {
         delete serverSocket;
     }
 }

```

如果发生错误， QSslSocket发射[sslErrors](qsslsocket.html#sslErrors)（）信号。在这种情况下，如果不采取行动，以忽略错误（ s）时，连接将被丢弃。要继续，尽管错误的发生，你可以调用[ignoreSslErrors](qsslsocket.html#ignoreSslErrors)（ ） ，无论是从该时隙内发生的错误后，或建设QSslSocket后，连接之前的任何时间尝试。这将允许QSslSocket忽略它遇到建立对等体的身份，当出现差错。在SSL握手过程忽略错误，应谨慎使用，因为安全连接的一个基本特征是，它们应与成功握手建立。

一旦加密，您可以使用QSslSocket作为一个经常[QTcpSocket](qtcpsocket.html)。何时[readyRead](qiodevice.html#readyRead)（ ）被发射，你可以调用[read](qiodevice.html#read)（ ）[canReadLine](qsslsocket.html#canReadLine)（）和[readLine](qiodevice.html#readLine)（） ，或[getChar](qiodevice.html#getChar)（ ）读取QSslSocket的内部缓冲区解密数据，并且可以调用[write](qiodevice.html#write)（）或[putChar](qiodevice.html#putChar)（ ）将数据写回给对端。 QSslSocket会自动加密写入的数据对你来说，并放出[encryptedBytesWritten](qsslsocket.html#encryptedBytesWritten)（）一旦数据已被写入到对等体。

为方便起见， QSslSocket支持[QTcpSocket](qtcpsocket.html)的阻断功能[waitForConnected](qsslsocket.html#waitForConnected)（ ）[waitForReadyRead](qsslsocket.html#waitForReadyRead)（ ）[waitForBytesWritten](qsslsocket.html#waitForBytesWritten)（）和[waitForDisconnected](qsslsocket.html#waitForDisconnected)（ ） 。它也提供[waitForEncrypted](qsslsocket.html#waitForEncrypted)（），它会阻塞调用线程，直到一个加密的连接已经建立。

```
 QSslSocket socket;
 socket.connectToHostEncrypted("http.example.com", 443);
 if (!socket.waitForEncrypted()) {
     qDebug() << socket.errorString();
     return false;
 }

 socket.write("GET / HTTP/1.0\r\n\r\n");
 while (socket.waitForReadyRead())
     qDebug() << socket.readAll().data();

```

QSslSocket提供了用于处理加密密码，私钥和地方，同行，以及证书颁发机构（ CA）证书广泛的，易于使用的API 。它还提供了用于处理在握手阶段所发生的错误的API。

以下功能也可以定制：

*   The socket's cryptographic cipher suite can be customized before the handshake phase with [setCiphers](qsslsocket.html#setCiphers)() and [setDefaultCiphers](qsslsocket.html#setDefaultCiphers)().
*   The socket's local certificate and private key can be customized before the handshake phase with [setLocalCertificate](qsslsocket.html#setLocalCertificate)() and [setPrivateKey](qsslsocket.html#setPrivateKey)().
*   The CA certificate database can be extended and customized with [addCaCertificate](qsslsocket.html#addCaCertificate)(), [addCaCertificates](qsslsocket.html#addCaCertificates)(), [setCaCertificates](qsslsocket.html#setCaCertificates)(), [addDefaultCaCertificate](qsslsocket.html#addDefaultCaCertificate)(), [addDefaultCaCertificates](qsslsocket.html#addDefaultCaCertificates)(), and [setDefaultCaCertificates](qsslsocket.html#setDefaultCaCertificates)().

**Note:**如果可以，在Unix （不包括Mac OS X的）根证书将来自标准证书目录按需加载。如果您不希望加载的根证书上的需求，你需要调用静态函数[setDefaultCaCertificates](qsslsocket.html#setDefaultCaCertificates)（ ）前的第一个SSL握手是在你的应用程序， （例如，通过“ QSslSocket.setDefaultCaCertificates （[QSslSocket.systemCaCertificates](qsslsocket.html#systemCaCertificates)（ ） ） ;“） ，或致电[setCaCertificates](qsslsocket.html#setCaCertificates)（ ）在之前的SSL握手你QSslSocket实例。

有关密码和证书的详细信息，请参阅[QSslCipher](qsslcipher.html)和[QSslCertificate](qsslcertificate.html)。

本产品包括OpenSSL工具包的使用由OpenSSL项目开发的软件（[http://www.openssl.org/](http://www.openssl.org/)） 。

**Note:**注意之间的差值的[bytesWritten](qiodevice.html#bytesWritten)（）信号和[encryptedBytesWritten](qsslsocket.html#encryptedBytesWritten)（）信号。对于[QTcpSocket](qtcpsocket.html)，[bytesWritten](qiodevice.html#bytesWritten)（）会得到尽快的数据已被写入到TCP套接字射出。对于QSslSocket ，[bytesWritten](qiodevice.html#bytesWritten)（）会得到发射时，数据被加密并[encryptedBytesWritten](qsslsocket.html#encryptedBytesWritten)（）会得到尽快的数据已被写入到TCP套接字射出。

### Symbian Platform Security Requirements

在Symbian ，它使用这个类的进程必须有`NetworkServices`平台的安全能力。如果客户端程序缺乏这种能力，操作将失败。

平台的安全功能是通过添加[TARGET.CAPABILITY](index.htm#target-capability)qmake的变量。

* * *

## Type Documentation

```
QSslSocket.PeerVerifyMode
```

介绍了同行的验证模式[QSslSocket](qsslsocket.html)。默认模式是AutoVerifyPeer ，它选择一个合适的模式，这取决于插座的QSocket.SslMode 。

| Constant | Value | Description |
| --- | --- | --- |
| `QSslSocket.VerifyNone` | `0` | [QSslSocket](qsslsocket.html)不会要求对端的证书。如果你没有兴趣在连接的另一端的身份，您可以设置该模式。该连接仍然会被加密，你的socket仍会发送其本地证书给对端，如果它的要求。 |
| `QSslSocket.QueryPeer` | `1` | [QSslSocket](qsslsocket.html)将要求对端的证书，但不要求该证书是有效的。当你想显示对等体证书的详细信息给用户，而不会影响实际的SSL握手，这是很有用的。这种模式是默认的服务器。 |
| `QSslSocket.VerifyPeer` | `2` | [QSslSocket](qsslsocket.html)会要求对方在SSL握手阶段证书，并要求该证书是有效的。如果失败，[QSslSocket](qsslsocket.html)将发射[QSslSocket.sslErrors](qsslsocket.html#sslErrors)（）信号。这种模式是默认的客户端。 |
| `QSslSocket.AutoVerifyPeer` | `3` | [QSslSocket](qsslsocket.html)会自动使用QueryPeer的服务器套接字和VerifyPeer的客户端套接字。 |

这个枚举被引入或修改的Qt 4.4 。

**See also** [QSslSocket.peerVerifyMode](qsslsocket.html#peerVerifyMode)（ ） 。

```
QSslSocket.SslMode
```

说明可用于连接模式[QSslSocket](qsslsocket.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QSslSocket.UnencryptedMode` | `0` | 套接字是未加密的。其行为是相同的[QTcpSocket](qtcpsocket.html)。 |
| `QSslSocket.SslClientMode` | `1` | 套接字的客户端SSL套接字。它可以是alreayd加密的，或者它是在SSL握手阶段（参见[QSslSocket.isEncrypted](qsslsocket.html#isEncrypted)（））。 |
| `QSslSocket.SslServerMode` | `2` | 该插座是一个服务器端的SSL套接字。它要么已经加密的，或者它是在SSL握手阶段（参见[QSslSocket.isEncrypted](qsslsocket.html#isEncrypted)（））。 |

* * *

## Method Documentation

```
QSslSocket.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QSslSocket](qsslsocket.html)对象。_parent_被传递给[QObject](qobject.html)的构造。新的套接字的[cipher](qsslcipher.html)套件被设置为静态方法返回一个[defaultCiphers](qsslsocket.html#defaultCiphers)（ ） 。

```
QSslSocket.abort (self)
```

中止当前连接并重置插口。不像[disconnectFromHost](qabstractsocket.html#disconnectFromHost)（ ） ，这个函数立即关闭套接字，写缓冲区清除任何挂起的数据。

**See also** [disconnectFromHost](qabstractsocket.html#disconnectFromHost)（）和[close](qsslsocket.html#close)（ ） 。

```
QSslSocket.addCaCertificate (self, QSslCertificate certificate)
```

添加_certificate_此套接字的CA证书数据库。握手阶段中的CA证书数据库所使用的插座，以验证对方的证书。

要添加多个证书，使用[addCaCertificates](qsslsocket.html#addCaCertificates)（ ） 。

**See also** [caCertificates](qsslsocket.html#caCertificates)（）和[setCaCertificates](qsslsocket.html#setCaCertificates)（ ） 。

```
bool QSslSocket.addCaCertificates (self, QString path, QSsl.EncodingFormat format = QSsl.Pem, QRegExp.PatternSyntax syntax = QRegExp.FixedString)
```

搜索中的所有文件_path_对于证书编码指定_format_并将它们添加到这个套接字的CA证书数据库。_path_可以是显式的，或者它可以包含通配符在由指定的格式_syntax_。返回True如果一个或多个证书添加到套接字的CA证书数据库，否则返回False 。

握手阶段中的CA证书数据库所使用的插座，以验证对方的证书。

为了更精确的控制，使用[addCaCertificate](qsslsocket.html#addCaCertificate)（ ） 。

**See also** [addCaCertificate](qsslsocket.html#addCaCertificate)（）和[QSslCertificate.fromPath](qsslcertificate.html#fromPath)（ ） 。

```
QSslSocket.addCaCertificates (self, list-of-QSslCertificate certificates)
```

添加_certificates_此套接字的CA证书数据库。握手阶段中的CA证书数据库所使用的插座，以验证对方的证书。

为了更精确的控制，使用[addCaCertificate](qsslsocket.html#addCaCertificate)（ ） 。

**See also** [caCertificates](qsslsocket.html#caCertificates)（）和[addDefaultCaCertificate](qsslsocket.html#addDefaultCaCertificate)（ ） 。

```
QSslSocket.addDefaultCaCertificate (QSslCertificate certificate)
```

添加_certificate_到默认的CA证书数据库。每个SSL套接字的CA证书数据库被初始化为默认的CA证书数据库。

**See also** [defaultCaCertificates](qsslsocket.html#defaultCaCertificates)（）和[addCaCertificates](qsslsocket.html#addCaCertificates)（ ） 。

```
bool QSslSocket.addDefaultCaCertificates (QString path, QSsl.EncodingFormat format = QSsl.Pem, QRegExp.PatternSyntax syntax = QRegExp.FixedString)
```

搜索中的所有文件_path_具有指定证书_encoding_并将它们添加到默认的CA证书数据库。_path_可以是显式的文件中，或者它可以包含通配符在由指定的格式_syntax_。如有CA证书被添加到默认数据库，则返回True 。

每个SSL套接字的CA证书数据库被初始化为默认的CA证书数据库。

**See also** [defaultCaCertificates](qsslsocket.html#defaultCaCertificates)（ ）[addCaCertificates](qsslsocket.html#addCaCertificates)（）和[addDefaultCaCertificate](qsslsocket.html#addDefaultCaCertificate)（ ） 。

```
QSslSocket.addDefaultCaCertificates (list-of-QSslCertificate certificates)
```

添加_certificates_到默认的CA证书数据库。每个SSL套接字的CA证书数据库被初始化为默认的CA证书数据库。

**See also** [defaultCaCertificates](qsslsocket.html#defaultCaCertificates)（）和[addCaCertificates](qsslsocket.html#addCaCertificates)（ ） 。

```
bool QSslSocket.atEnd (self)
```

从重新实现[QIODevice.atEnd](qiodevice.html#atEnd)（ ） 。

```
int QSslSocket.bytesAvailable (self)
```

从重新实现[QIODevice.bytesAvailable](qiodevice.html#bytesAvailable)（ ） 。

返回解密后的字节是立即可用于阅读的数量。

```
int QSslSocket.bytesToWrite (self)
```

从重新实现[QIODevice.bytesToWrite](qiodevice.html#bytesToWrite)（ ） 。

返回正在等待被加密并写入网络未加密的字节数。

```
list-of-QSslCertificate QSslSocket.caCertificates (self)
```

返回此套接字的CA证书数据库。握手阶段中的CA证书数据库所使用的插座，以验证对方的证书。它可以与握手之前被moodified[addCaCertificate](qsslsocket.html#addCaCertificate)（ ）[addCaCertificates](qsslsocket.html#addCaCertificates)（）和[setCaCertificates](qsslsocket.html#setCaCertificates)（ ） 。

**Note:**在Unix中，这个方法可能会返回一个空列表，如果根证书按需加载。

**See also** [addCaCertificate](qsslsocket.html#addCaCertificate)（ ）[addCaCertificates](qsslsocket.html#addCaCertificates)（）和[setCaCertificates](qsslsocket.html#setCaCertificates)（ ） 。

```
bool QSslSocket.canReadLine (self)
```

从重新实现[QIODevice.canReadLine](qiodevice.html#canReadLine)（ ） 。

返回True如果你能读一而行（终止由一个单一的ASCII码为'\ n '字符）解密字符，否则返回False 。

```
list-of-QSslCipher QSslSocket.ciphers (self)
```

返回此套接字的当前密码的加密套件。在插座的握手阶段该列表用于选择一个会话密码。密码返回的列表是按递减优先级进行排序。 （例如，在列表中的第一密码是最优选的密码） 。会话密码将是第一个在也支持对等的列表。

默认情况下，握手阶段可以选择任何由该系统的SSL库支持的加密算法，这可能会有所不同从系统到系统。通过此系统的SSL库支持的密码列表是由返回[supportedCiphers](qsslsocket.html#supportedCiphers)（ ） 。你可以通过调用限制用于选择会话密码为这个套接字密码列表[setCiphers](qsslsocket.html#setCiphers)（ ）与所支持的加密算法的子集。你可以通过调用恢复使用整套[setCiphers](qsslsocket.html#setCiphers)（ ）与返回列表[supportedCiphers](qsslsocket.html#supportedCiphers)（ ） 。

您可以限制用于选择会话加密的密码清单_all_套接字通过调用[setDefaultCiphers](qsslsocket.html#setDefaultCiphers)（ ）与所支持的加密算法的子集。你可以通过调用恢复使用整套[setCiphers](qsslsocket.html#setCiphers)（ ）与返回列表[supportedCiphers](qsslsocket.html#supportedCiphers)（ ） 。

**See also** [setCiphers](qsslsocket.html#setCiphers)（ ）[defaultCiphers](qsslsocket.html#defaultCiphers)（ ）[setDefaultCiphers](qsslsocket.html#setDefaultCiphers)（）和[supportedCiphers](qsslsocket.html#supportedCiphers)（ ） 。

```
QSslSocket.close (self)
```

从重新实现[QIODevice.close](qiodevice.html#close)（ ） 。

```
QSslSocket.connectToHostEncrypted (self, QString hostName, int port, QIODevice.OpenMode mode = QIODevice.ReadWrite)
```

开始到设备的加密连接_hostName_上_port_，使用_mode_作为[OpenMode](qiodevice.html#OpenModeFlag-enum)。这等同于调用[connectToHost](qabstractsocket.html#connectToHost)（）来建立连接，然后通过调用[startClientEncryption](qsslsocket.html#startClientEncryption)（ ） 。

[QSslSocket](qsslsocket.html)首先进入[HostLookupState](qabstractsocket.html#SocketState-enum)。然后，无论是进入事件循环或一个WAITFOR的... （ ）函数后，它进入[ConnectingState](qabstractsocket.html#SocketState-enum)，发出[connected](qabstractsocket.html#connected)（ ） ，然后启动SSL客户端握手。在每个状态的变化，[QSslSocket](qsslsocket.html)发出信号[stateChanged](qabstractsocket.html#stateChanged)（ ） 。

启动SSL客户端握手，如果对等体的身份不能成立，信号经过[sslErrors](qsslsocket.html#sslErrors)（）被发射。如果你想忽略错误并继续连接，则必须调用[ignoreSslErrors](qsslsocket.html#ignoreSslErrors)（） ，无论是从一个槽函数内部连接到[sslErrors](qsslsocket.html#sslErrors)（ ）信号，或在进入加密模式之前。如果[ignoreSslErrors](qsslsocket.html#ignoreSslErrors)（ ）没有被调用，则连接断开，信号[disconnected](qabstractsocket.html#disconnected)（）被发射，并且[QSslSocket](qsslsocket.html)返回到[UnconnectedState](qabstractsocket.html#SocketState-enum)。

如果SSL握手成功，[QSslSocket](qsslsocket.html) emits [encrypted](qsslsocket.html#encrypted)（ ） 。

```
 [QSslSocket](qsslsocket.html) socket;
 connect(&socket, SIGNAL(encrypted()), receiver, SLOT(socketEncrypted()));

 socket.connectToHostEncrypted("imap", 993);
 socket->write("1 CAPABILITY\r\n");

```

**Note:**上面的例子表明，文本可以请求加密连接，以前后立即被写入套接字[encrypted](qsslsocket.html#encrypted)（）信号已经发出。在这种情况下，文本被排队的对象，并写入到插座_after_连接建立和[encrypted](qsslsocket.html#encrypted)（）信号已经发出。

默认为_mode_ is [ReadWrite](qiodevice.html#OpenModeFlag-enum)。

如果你想创建一个[QSslSocket](qsslsocket.html)在连接的服务器端，你应该改为调用[startServerEncryption](qsslsocket.html#startServerEncryption)（ ）后，通过接收传入的连接[QTcpServer](qtcpserver.html)。

**See also** [connectToHost](qabstractsocket.html#connectToHost)（ ）[startClientEncryption](qsslsocket.html#startClientEncryption)（ ）[waitForConnected](qsslsocket.html#waitForConnected)（）和[waitForEncrypted](qsslsocket.html#waitForEncrypted)（ ） 。

```
QSslSocket.connectToHostEncrypted (self, QString hostName, int port, QString sslPeerName, QIODevice.OpenMode mode = QIODevice.ReadWrite)
```

这是一个重载函数。

除了connectToHostEncrypted的原始行为，此重载方法使不同的主机名的用法（_sslPeerName_）的证书验证，而不是用于TCP连接的一（_hostName_） 。

此功能被引入Qt的4.6 。

**See also** [connectToHostEncrypted](qsslsocket.html#connectToHostEncrypted)（ ） 。

```
QSslSocket.connectToHostImplementation (self, QString hostName, int port, QIODevice.OpenMode openMode)
```

这种方法也是一个Qt槽与C + +的签名`void connectToHostImplementation(const QString&,quint16,QIODevice::OpenMode)`。

```
list-of-QSslCertificate QSslSocket.defaultCaCertificates ()
```

返回当前默认的CA证书数据库。这个数据库是最初设置为系统的默认CA证书数据库。如果没有找到系统默认的数据库，建立一个空数据库将被退回。你可以用你自己的CA证书数据库使用复盖默认的CA证书数据库[setDefaultCaCertificates](qsslsocket.html#setDefaultCaCertificates)（ ） 。

每个SSL套接字的CA证书数据库被初始化为默认的CA证书数据库。

**Note:**在Unix中，这个方法可能会返回一个空列表，如果根证书按需加载。

**See also** [setDefaultCaCertificates](qsslsocket.html#setDefaultCaCertificates)（）和[caCertificates](qsslsocket.html#caCertificates)（ ） 。

```
list-of-QSslCipher QSslSocket.defaultCiphers ()
```

返回默认的加密密码套件在这个应用程序的所有插座。此列表中的套接字的握手阶段时，与对等谈判，以选择一个会话密码使用。该列表是按优先次序排列（即，在列表中的第一个密码是最喜欢的密码） 。

默认情况下，握手阶段可以选择任何由该系统的SSL库支持的加密算法，这可能会有所不同从系统到系统。通过此系统的SSL库支持的密码列表是由返回[supportedCiphers](qsslsocket.html#supportedCiphers)（ ） 。

**See also** [setDefaultCiphers](qsslsocket.html#setDefaultCiphers)（）和[supportedCiphers](qsslsocket.html#supportedCiphers)（ ） 。

```
QSslSocket.disconnectFromHostImplementation (self)
```

这种方法也是一个Qt槽与C + +的签名`void disconnectFromHostImplementation()`。

```
int QSslSocket.encryptedBytesAvailable (self)
```

返回正在等待解密加密的字节数。通常情况下，这个函数将返回0 ，因为[QSslSocket](qsslsocket.html)只要它可以解密它的输入数据。

此功能被引入Qt的4.4 。

```
int QSslSocket.encryptedBytesToWrite (self)
```

返回的加密的字节正在等待被写入到网络的数目。

此功能被引入Qt的4.4 。

```
bool QSslSocket.flush (self)
```

该函数将尽可能从内部写缓冲区的底层网络接口，而不会阻塞。如果任何数据被写入时，该函数将返回True，否则返回False。

调用此函数，如果你需要[QSslSocket](qsslsocket.html)立即开始发送缓冲数据。成功写入的字节数依赖于操作系统。在大多数情况下，你不需要调用这个函数，因为[QAbstractSocket](qabstractsocket.html)将自动开始发送数据，一旦控制返回到事件循环。在不存在的事件循环，调用[waitForBytesWritten](qsslsocket.html#waitForBytesWritten)（ ）来代替。

**See also** [write](qiodevice.html#write)（）和[waitForBytesWritten](qsslsocket.html#waitForBytesWritten)（ ） 。

```
QSslSocket.ignoreSslErrors (self)
```

这种方法也是一个Qt槽与C + +的签名`void ignoreSslErrors()`。

这个插槽告诉[QSslSocket](qsslsocket.html)过程中忽略的错误[QSslSocket](qsslsocket.html)的握手阶段，并继续连接。如果你想继续使用，即使在握手阶段出现的错误连接，那么你必须调用这个槽，无论是从连接到一个槽[sslErrors](qsslsocket.html#sslErrors)（ ） ，或之前握手阶段。如果你不调用这个插槽，无论是在响应错误或握手之前，连接将在之后被丢弃[sslErrors](qsslsocket.html#sslErrors)（）信号已经发出。

如果在SSL握手阶段没有错误（即对方的身份确立，没有任何问题） ，[QSslSocket](qsslsocket.html)也不会发射[sslErrors](qsslsocket.html#sslErrors)（）的信号，并且它不需要调用此函数。

**Warning:**一定要始终让用户检查报告的错误[sslErrors](qsslsocket.html#sslErrors)（ ）信号，并且只从用户的程序是确定经确认后，调用此方法。如果有意外的错误，连接应被中止。不检查实际的错误调用此方法将最有可能带来安全风险的应用程序。使用它以极大的关怀！

**See also** [sslErrors](qsslsocket.html#sslErrors)（ ） 。

```
QSslSocket.ignoreSslErrors (self, list-of-QSslError errors)
```

这是一个重载函数。

这个方法告诉[QSslSocket](qsslsocket.html)忽略只在给定的误差_errors_。

请注意，您可以在SSL错误设定预期的证书：如果，例如，要连接到使用自签名证书的服务器时，请考虑下面的代码片断：

```
 [QList](index.htm)<[QSslCertificate](qsslcertificate.html)> cert = [QSslCertificate](qsslcertificate.html).fromPath(QLatin1String("server-certificate.pem"));
 [QSslError](qsslerror.html) error([QSslError](qsslerror.html).SelfSignedCertificate, cert.at(0));
 [QList](index.htm)<[QSslError](qsslerror.html)> expectedSslErrors;
 expectedSslErrors.append(error);

 [QSslSocket](qsslsocket.html) socket;
 socket.ignoreSslErrors(expectedSslErrors);
 socket.connectToHostEncrypted("server.tld", 443);

```

多次调用该函数会被替换传入以前调用的错误列表。您可以清除通过调用这个函数以一个空列表，你要忽略错误的列表。

此功能被引入Qt的4.6 。

**See also** [sslErrors](qsslsocket.html#sslErrors)（ ） 。

```
bool QSslSocket.isEncrypted (self)
```

返回True如果套接字是加密的，否则，则返回False。

加密套接字加密被写入调用的所有数据[write](qiodevice.html#write)（）或[putChar](qiodevice.html#putChar)（）之前的数据被写入到网络上，并解密所有传入的数据作为数据是从网络接收到的，在打电话之前[read](qiodevice.html#read)（ ）[readLine](qiodevice.html#readLine)（）或[getChar](qiodevice.html#getChar)（ ） 。

[QSslSocket](qsslsocket.html) emits [encrypted](qsslsocket.html#encrypted)（ ）当它进入加密模式。

您可以致电[sessionCipher](qsslsocket.html#sessionCipher)（）找到它的加密密码是用来加密和解密数据。

**See also** [mode](qsslsocket.html#mode)（ ） 。

```
QSslCertificate QSslSocket.localCertificate (self)
```

[](qsslcertificate.html)

[返回套接字的本地](qsslcertificate.html)[certificate](qsslcertificate.html)，或者一个空的证书，如果没有本地证书已分配。

**See also** [setLocalCertificate](qsslsocket.html#setLocalCertificate)（）和[privateKey](qsslsocket.html#privateKey)（ ） 。

```
SslMode QSslSocket.mode (self)
```

[](qsslsocket.html#SslMode-enum)

[返回当前模式的插座;要么](qsslsocket.html#SslMode-enum)[UnencryptedMode](qsslsocket.html#SslMode-enum)，其中[QSslSocket](qsslsocket.html)行为identially到[QTcpSocket](qtcpsocket.html)的，或者一个[SslClientMode](qsslsocket.html#SslMode-enum) or [SslServerMode](qsslsocket.html#SslMode-enum)，其中客户端可以是谈判或加密模式。

当模式改变，[QSslSocket](qsslsocket.html) emits [modeChanged](qsslsocket.html#modeChanged)（ ）

**See also** [SslMode](qsslsocket.html#SslMode-enum)。

```
QSslCertificate QSslSocket.peerCertificate (self)
```

[

返回同行的数字证书（即您已连接到主机的直接证明） ，或空凭证，如果对等未分配证书。

对等证书握手阶段中的自动检查，所以这个功能通常用来获取用于显示或连接诊断目的的证书。它包含有关对等的信息，包括它的主机名，证书颁发者，和同行的公钥。

](qsslcertificate.html)

[因为对等证书握手阶段中的设置，它是安全的，从连接到一个插槽存取等证书](qsslcertificate.html)[sslErrors](qsslsocket.html#sslErrors)（）信号或[encrypted](qsslsocket.html#encrypted)（）信号。

如果证书无效，则返回，它可能意味着SSL握手失败，或者它可能意味着您已连接到主机没有证书，或者它可能意味着没有连接。

如果你想检查对端的完整的证书链，利用[peerCertificateChain](qsslsocket.html#peerCertificateChain)（）来得到一次全部。

**See also** [peerCertificateChain](qsslsocket.html#peerCertificateChain)（ ） 。

```
list-of-QSslCertificate QSslSocket.peerCertificateChain (self)
```

返回数字证书的对等的链，或证书列表是空的。

同行证书握手阶段中的自动检查。此功能通常用于获取证书显示，或用于执行连接诊断。证书包含有关对等和证书发行机构，包括主机名，发行人名称和发行者公开密钥的信息。

对等证书的设置[QSslSocket](qsslsocket.html)握手阶段中，所以它是安全的，从连接到一个时隙调用此函数[sslErrors](qsslsocket.html#sslErrors)（）信号或[encrypted](qsslsocket.html#encrypted)（）信号。

如果返回空列表，它可能意味着SSL握手失败，或者它可能意味着您已连接到主机没有证书，或者它可能意味着没有连接。

如果你想只得到了同行的直接证明，使用[peerCertificate](qsslsocket.html#peerCertificate)（ ） 。

**See also** [peerCertificate](qsslsocket.html#peerCertificate)（ ） 。

```
int QSslSocket.peerVerifyDepth (self)
```

返回的证书在同行中的证书链，如果没有最大深度已设置在SSL握手阶段，或0 （默认值）要检查的最大数目，这表明整个证书链应该进行检查。

该证书在发出订单，开始与对端自己的证书，那么它的颁发者的证书，等检查。

此功能被引入Qt的4.4 。

**See also** [setPeerVerifyDepth](qsslsocket.html#setPeerVerifyDepth)（）和[peerVerifyMode](qsslsocket.html#peerVerifyMode)（ ） 。

```
PeerVerifyMode QSslSocket.peerVerifyMode (self)
```

[](qsslsocket.html#PeerVerifyMode-enum)

[返回套接字的验证模式。此模式模式决定是否](qsslsocket.html#PeerVerifyMode-enum)[QSslSocket](qsslsocket.html)应要求对等方的证书（即客户端从服务器请求一个证书，或请求从客户端证书的服务器） ，以及是否应当要求该证书是有效的。

默认模式是[AutoVerifyPeer](qsslsocket.html#PeerVerifyMode-enum)，它告诉[QSslSocket](qsslsocket.html)使用[VerifyPeer](qsslsocket.html#PeerVerifyMode-enum)为客户和[QueryPeer](qsslsocket.html#PeerVerifyMode-enum)用于服务器。

此功能被引入Qt的4.4 。

**See also** [setPeerVerifyMode](qsslsocket.html#setPeerVerifyMode)（ ）[peerVerifyDepth](qsslsocket.html#peerVerifyDepth)（）和[mode](qsslsocket.html#mode)（ ） 。

```
QString QSslSocket.peerVerifyName (self)
```

返回不同的主机名的证书验证，以setPeerVerifyName或connectToHostEncrypted载。

此功能被引入Qt的4.8 。

**See also** [setPeerVerifyName](qsslsocket.html#setPeerVerifyName)（）和[connectToHostEncrypted](qsslsocket.html#connectToHostEncrypted)（ ） 。

```
QSslKey QSslSocket.privateKey (self)
```

[

返回此套接字的私钥。

](qsslkey.html)

[**See also**](qsslkey.html) [setPrivateKey](qsslsocket.html#setPrivateKey)（）和[localCertificate](qsslsocket.html#localCertificate)（ ） 。

```
QSsl.SslProtocol QSslSocket.protocol (self)
```

[](qssl.html#SslProtocol-enum)

[返回套接字的SSL协议。默认情况下，](qssl.html#SslProtocol-enum)[QSsl.SecureProtocols](qssl.html#SslProtocol-enum)被使用。

**See also** [setProtocol](qsslsocket.html#setProtocol)（ ） 。

```
str QSslSocket.readData (self, int maxlen)
```

从重新实现[QIODevice.readData](qiodevice.html#readData)（ ） 。

```
QSslCipher QSslSocket.sessionCipher (self)
```

[](qsslcipher.html)

[返回套接字的密码](qsslcipher.html)[cipher](qsslcipher.html)或空密码，如果是不加密的连接。套接字的密码在会议期间握手阶段设置。密码是用于加密和解密通过套接字发送的数据。

[QSslSocket](qsslsocket.html)还提供了一些函数来设置密码从中握手阶段将最终选择会话密码的有序列表。这种有序列表必须到位握手阶段开始之前。

**See also** [ciphers](qsslsocket.html#ciphers)（ ）[setCiphers](qsslsocket.html#setCiphers)（ ）[setDefaultCiphers](qsslsocket.html#setDefaultCiphers)（ ）[defaultCiphers](qsslsocket.html#defaultCiphers)（）和[supportedCiphers](qsslsocket.html#supportedCiphers)（ ） 。

```
QSslSocket.setCaCertificates (self, list-of-QSslCertificate certificates)
```

设置此套接字的CA证书数据库是_certificates_。证书数据库之前必须设置为SSL握手。握手阶段中的CA证书数据库所使用的插座，以验证对方的证书。

CA证书数据库可以通过调用这个函数的返回通过CA证书列表被重置为当前默认的CA证书数据库[defaultCaCertificates](qsslsocket.html#defaultCaCertificates)（ ） 。

**See also** [caCertificates](qsslsocket.html#caCertificates)（）和[defaultCaCertificates](qsslsocket.html#defaultCaCertificates)（ ） 。

```
QSslSocket.setCiphers (self, list-of-QSslCipher ciphers)
```

加密的加密套件为这个套接字设置为_ciphers_，其中必须包含在返回的列表中的密码子集[supportedCiphers](qsslsocket.html#supportedCiphers)（ ） 。

限制密码套件必须在握手阶段，那里的会话密码被选为前完成。

**See also** [ciphers](qsslsocket.html#ciphers)（ ）[setDefaultCiphers](qsslsocket.html#setDefaultCiphers)（）和[supportedCiphers](qsslsocket.html#supportedCiphers)（ ） 。

```
QSslSocket.setCiphers (self, QString ciphers)
```

加密的加密套件为这个套接字设置为_ciphers_，这是密码套件名称的冒号分隔的列表。在密码中列出优先顺序，从最优先的密码。例如：

```
 [QSslSocket](qsslsocket.html) socket;
 socket.setCiphers("DHE-RSA-AES256-SHA:DHE-DSS-AES256-SHA:AES256-SHA");

```

在每个密码名称_ciphers_必须在返回的列表中选择一个加密的名称[supportedCiphers](qsslsocket.html#supportedCiphers)（ ） 。限制密码套件必须在握手阶段，那里的会话密码被选为前完成。

**See also** [ciphers](qsslsocket.html#ciphers)（ ）[setDefaultCiphers](qsslsocket.html#setDefaultCiphers)（）和[supportedCiphers](qsslsocket.html#supportedCiphers)（ ） 。

```
QSslSocket.setDefaultCaCertificates (list-of-QSslCertificate certificates)
```

设置默认的CA证书数据库_certificates_。默认的CA证书数据库最初设置为系统的默认CA证书数据库。您可以使用这个功能你自己的CA证书数据库复盖默认的CA证书数据库。

每个SSL套接字的CA证书数据库被初始化为默认的CA证书数据库。

**See also** [defaultCaCertificates](qsslsocket.html#defaultCaCertificates)（）和[addDefaultCaCertificate](qsslsocket.html#addDefaultCaCertificate)（ ） 。

```
QSslSocket.setDefaultCiphers (list-of-QSslCipher ciphers)
```

设置默认的加密密码套件在这个应用程序的所有套接字_ciphers_，其中必须包含在返回的列表中的密码子集[supportedCiphers](qsslsocket.html#supportedCiphers)（ ） 。

限制默认的密码套件仅影响履行握手阶段的默认密码套件已经被改变后， SSL套接字。

**See also** [setCiphers](qsslsocket.html#setCiphers)（ ）[defaultCiphers](qsslsocket.html#defaultCiphers)（）和[supportedCiphers](qsslsocket.html#supportedCiphers)（ ） 。

```
QSslSocket.setLocalCertificate (self, QSslCertificate certificate)
```

设置套接字的本地证书_certificate_。如果您需要确认您的身份到对端的本地证书是必要的。这是一起用私有密钥;如果设置了本地证书，还必须设置专用密钥。

本地证书和私钥总是必要的服务器套接字，但也很少使用客户端套接字，如果服务器要求客户端进行身份验证。

**See also** [localCertificate](qsslsocket.html#localCertificate)（）和[setPrivateKey](qsslsocket.html#setPrivateKey)（ ） 。

```
QSslSocket.setLocalCertificate (self, QString path, QSsl.EncodingFormat format = QSsl.Pem)
```

这是一个重载函数。

设置套接字的本地[certificate](qsslcertificate.html)在文件中找到的第一个_path_，这是根据指定的解析_format_。

```
QSslSocket.setPeerVerifyDepth (self, int depth)
```

设置证书在同行中的证书链在SSL握手阶段进行检查的最大数量，以_depth_。设置为0的深度表示没有最大深度被设定，表明整个证书链应进行检查。

该证书在发出订单，开始与对端自己的证书，那么它的颁发者的证书，等检查。

此功能被引入Qt的4.4 。

**See also** [peerVerifyDepth](qsslsocket.html#peerVerifyDepth)（）和[setPeerVerifyMode](qsslsocket.html#setPeerVerifyMode)（ ） 。

```
QSslSocket.setPeerVerifyMode (self, PeerVerifyMode mode)
```

设置套接字的验证模式_mode_。这种模式决定是否[QSslSocket](qsslsocket.html)应要求对等方的证书（即客户端从服务器请求一个证书，或请求从客户端证书的服务器） ，以及是否应当要求该证书是有效的。

默认模式是[AutoVerifyPeer](qsslsocket.html#PeerVerifyMode-enum)，它告诉[QSslSocket](qsslsocket.html)使用[VerifyPeer](qsslsocket.html#PeerVerifyMode-enum)为客户和[QueryPeer](qsslsocket.html#PeerVerifyMode-enum)用于服务器。

设置此模式下的加密开始后具有当前连接没有影响。

此功能被引入Qt的4.4 。

**See also** [peerVerifyMode](qsslsocket.html#peerVerifyMode)（ ）[setPeerVerifyDepth](qsslsocket.html#setPeerVerifyDepth)（）和[mode](qsslsocket.html#mode)（ ） 。

```
QSslSocket.setPeerVerifyName (self, QString hostName)
```

设置一个不同的主机名，由下式给出_hostName_，证书验证，而不是用于该TCP连接的那个。

此功能被引入Qt的4.8 。

**See also** [peerVerifyName](qsslsocket.html#peerVerifyName)（）和[connectToHostEncrypted](qsslsocket.html#connectToHostEncrypted)（ ） 。

```
QSslSocket.setPrivateKey (self, QSslKey key)
```

设置套接字的私人[key](qsslkey.html)至_key_。私钥和当地[certificate](qsslcertificate.html)所使用的客户端和服务器必须证明自己身份的SSL同行。

密钥和本地证书是必需的，如果你正在创建一个SSL服务器套接字。如果要创建一个SSL客户端套接字，密钥和本地证书是如果你的客户端必须确定自己的SSL服务器所需。

**See also** [privateKey](qsslsocket.html#privateKey)（）和[setLocalCertificate](qsslsocket.html#setLocalCertificate)（ ） 。

```
QSslSocket.setPrivateKey (self, QString fileName, QSsl.KeyAlgorithm algorithm = QSsl.Rsa, QSsl.EncodingFormat format = QSsl.Pem, QByteArray passPhrase = QByteArray())
```

这是一个重载函数。

读取字符串的文件_fileName_并使用指定的解码它_algorithm_和编码_format_构造一个[SSL key](qsslkey.html)。如果编码的密钥进行加密，_passPhrase_用于解密。

插座的私有密钥被设置为所构建的关键。私钥和当地[certificate](qsslcertificate.html)所使用的客户端和服务器必须证明自己身份的SSL同行。

密钥和本地证书是必需的，如果你正在创建一个SSL服务器套接字。如果要创建一个SSL客户端套接字，密钥和本地证书是如果你的客户端必须确定自己的SSL服务器所需。

**See also** [privateKey](qsslsocket.html#privateKey)（）和[setLocalCertificate](qsslsocket.html#setLocalCertificate)（ ） 。

```
QSslSocket.setProtocol (self, QSsl.SslProtocol protocol)
```

设置套接字的SSL协议_protocol_。这将影响到下一个启动的握手;对已经加密套接字调用这个函数不会影响套接字的协议。

**See also** [protocol](qsslsocket.html#protocol)（ ） 。

```
QSslSocket.setReadBufferSize (self, int size)
```

载的大小[QSslSocket](qsslsocket.html)的内部读缓冲区是_size_字节。

此功能被引入Qt的4.4 。

```
bool QSslSocket.setSocketDescriptor (self, int socketDescriptor, QAbstractSocket.SocketState state = QAbstractSocket.ConnectedState, QIODevice.OpenMode mode = QIODevice.ReadWrite)
```

初始化[QSslSocket](qsslsocket.html)与本地套接字描述符_socketDescriptor_。返回True如果_socketDescriptor_被接受为有效的套接字描述符，否则返回False 。该插座是由指定的模式打开_openMode_，并进入由指定的套接字状态_state_。

**Note:**这是不可能的初始化两个插座使用相同的本地套接字描述符。

**See also** [socketDescriptor](qabstractsocket.html#socketDescriptor)（ ） 。

```
QSslSocket.setSocketOption (self, QAbstractSocket.SocketOption option, QVariant value)
```

设置给定_option_由所描述的值_value_。

此功能被引入Qt的4.6 。

**See also** [socketOption](qsslsocket.html#socketOption)（ ） 。

```
QSslSocket.setSslConfiguration (self, QSslConfiguration config)
```

设置套接字的SSL配置是内容_configuration_。该函数设置本地证书，加密，私钥和CA证书与储存在_configuration_。

这是不可能的，设置SSL的状态相关的字段。

此功能被引入Qt的4.4 。

**See also** [sslConfiguration](qsslsocket.html#sslConfiguration)（ ）[setLocalCertificate](qsslsocket.html#setLocalCertificate)（ ）[setPrivateKey](qsslsocket.html#setPrivateKey)（ ）[setCaCertificates](qsslsocket.html#setCaCertificates)（）和[setCiphers](qsslsocket.html#setCiphers)（ ） 。

```
QVariant QSslSocket.socketOption (self, QAbstractSocket.SocketOption option)
```

返回的值_option_选项。

此功能被引入Qt的4.6 。

**See also** [setSocketOption](qsslsocket.html#setSocketOption)（ ） 。

```
QSslConfiguration QSslSocket.sslConfiguration (self)
```

[

返回套接字的SSL配置状态。套接字的缺省SSL配置是使用默认的密码，默认的CA证书，没有本地私有密钥或证书。

SSL配置还包含可随时间而改变，恕不另行通知栏。

此功能被引入Qt的4.4 。

](qsslconfiguration.html)

[**See also**](qsslconfiguration.html) [setSslConfiguration](qsslsocket.html#setSslConfiguration)（ ）[localCertificate](qsslsocket.html#localCertificate)（ ）[peerCertificate](qsslsocket.html#peerCertificate)（ ）[peerCertificateChain](qsslsocket.html#peerCertificateChain)（ ）[sessionCipher](qsslsocket.html#sessionCipher)（ ）[privateKey](qsslsocket.html#privateKey)（ ）[ciphers](qsslsocket.html#ciphers)（）和[caCertificates](qsslsocket.html#caCertificates)（ ） 。

```
list-of-QSslError QSslSocket.sslErrors (self)
```

返回最近发生的SSL错误的列表。这是相同的列表作为[QSslSocket](qsslsocket.html)通过sslErrors （ ）信号通过。如果连接已加密，没有错误，此函数将返回一个空列表。

**See also** [connectToHostEncrypted](qsslsocket.html#connectToHostEncrypted)（ ） 。

```
QSslSocket.startClientEncryption (self)
```

这种方法也是一个Qt槽与C + +的签名`void startClientEncryption()`。

启动一个客户端连接的延迟SSL握手。这个函数可以在插座是在被称为[ConnectedState](qabstractsocket.html#SocketState-enum)但仍处于[UnencryptedMode](qsslsocket.html#SslMode-enum)。如果尚未连接，或者如果它已被加密，该功能没有任何影响。

实现STARTTLS功能的客户经常使用延迟的SSL握手。大多数其他客户端可以使用避免直接调用此函数[connectToHostEncrypted](qsslsocket.html#connectToHostEncrypted)（）代替，它会自动执行握手。

**See also** [connectToHostEncrypted](qsslsocket.html#connectToHostEncrypted)（）和[startServerEncryption](qsslsocket.html#startServerEncryption)（ ） 。

```
QSslSocket.startServerEncryption (self)
```

这种方法也是一个Qt槽与C + +的签名`void startServerEncryption()`。

启动服务器连接延迟的SSL握手。这个函数可以在插座是在被称为[ConnectedState](qabstractsocket.html#SocketState-enum)但仍处于[UnencryptedMode](qsslsocket.html#SslMode-enum)。如果没有连接，或者已被加密，则该功能没有任何影响。

对于服务器套接字，则调用这个函数来启动SSL握手的唯一途径。大多数服务器将在接收到连接立即调用该函数，或作为已接受一个协议特定的命令进入SSL模式（例如的结果，服务器可能收到的响应串“ STARTTLS \ r \ N”通过调用这个函数） 。

实现SSL服务器最常用的方法是创建一个子类[QTcpServer](qtcpserver.html)并重新实现[QTcpServer.incomingConnection](qtcpserver.html#incomingConnection)（ ） 。返回的套接字描述符，然后传递到[QSslSocket.setSocketDescriptor](qsslsocket.html#setSocketDescriptor)（ ） 。

**See also** [connectToHostEncrypted](qsslsocket.html#connectToHostEncrypted)（）和[startClientEncryption](qsslsocket.html#startClientEncryption)（ ） 。

```
list-of-QSslCipher QSslSocket.supportedCiphers ()
```

返回本系统支持的加密算法列表。此列表是由系统的SSL库和设置可能会有所不同从系统到系统中。

**See also** [defaultCiphers](qsslsocket.html#defaultCiphers)（ ）[ciphers](qsslsocket.html#ciphers)（）和[setCiphers](qsslsocket.html#setCiphers)（ ） 。

```
bool QSslSocket.supportsSsl ()
```

返回True如果该平台支持SSL ，否则返回False 。如果平台不支持SSL ，套接字将在连接阶段失败。

```
list-of-QSslCertificate QSslSocket.systemCaCertificates ()
```

这个功能提供由操作系统提供的CA证书数据库。这个函数返回的CA证书数据库是用来初始化返回的数据库[defaultCaCertificates](qsslsocket.html#defaultCaCertificates)（ ） 。你可以换成你自己的数据库[setDefaultCaCertificates](qsslsocket.html#setDefaultCaCertificates)（ ） 。

**See also** [caCertificates](qsslsocket.html#caCertificates)（ ）[defaultCaCertificates](qsslsocket.html#defaultCaCertificates)（）和[setDefaultCaCertificates](qsslsocket.html#setDefaultCaCertificates)（ ） 。

```
bool QSslSocket.waitForBytesWritten (self, int msecs = 30000)
```

从重新实现[QIODevice.waitForBytesWritten](qiodevice.html#waitForBytesWritten)（ ） 。

```
bool QSslSocket.waitForConnected (self, int msecs = 30000)
```

等待，直到套接字连接，或_msecs_ milliseconds, whichever happens first. If the connection has been established, this function returns true; otherwise it returns false.

**See also** [QAbstractSocket.waitForConnected](qabstractsocket.html#waitForConnected)（ ） 。

```
bool QSslSocket.waitForDisconnected (self, int msecs = 30000)
```

等待，直到该套接字已断开或_msecs_毫秒，以先到者为准。如果连接已经断开，则该函数返回True，否则返回False 。

**See also** [QAbstractSocket.waitForDisconnected](qabstractsocket.html#waitForDisconnected)（ ） 。

```
bool QSslSocket.waitForEncrypted (self, int msecs = 30000)
```

等待，直到插座已完成SSL握手，并已发出[encrypted](qsslsocket.html#encrypted)（） ，或_msecs_毫秒，以先到者为准。如果[encrypted](qsslsocket.html#encrypted)（ ）已发出，则该函数返回True，否则（例如，插座断开，或在SSL握手失败） ，则返回False 。

下面的例子最多等待1秒到加密套接字：

```
 socket->connectToHostEncrypted("imap", 993);
 if (socket->waitForEncrypted(1000))
     qDebug("Encrypted!");

```

如果毫秒为-1 ，此功能将不会超时。

**See also** [startClientEncryption](qsslsocket.html#startClientEncryption)（ ）[startServerEncryption](qsslsocket.html#startServerEncryption)（ ）[encrypted](qsslsocket.html#encrypted)（）和[isEncrypted](qsslsocket.html#isEncrypted)（ ） 。

```
bool QSslSocket.waitForReadyRead (self, int msecs = 30000)
```

从重新实现[QIODevice.waitForReadyRead](qiodevice.html#waitForReadyRead)（ ） 。

```
int QSslSocket.writeData (self, str data)
```

从重新实现[QIODevice.writeData](qiodevice.html#writeData)（ ） 。

* * *

## Qt Signal Documentation

```
void encrypted ()
```

这是该信号的默认超载。

这个信号被发射时[QSslSocket](qsslsocket.html)进入加密模式。之后此信号被发射[QSslSocket.isEncrypted](qsslsocket.html#isEncrypted)（ ）将返回True ，并在插座所有进一步的传输将被加密。

**See also** [QSslSocket.connectToHostEncrypted](qsslsocket.html#connectToHostEncrypted)（）和[QSslSocket.isEncrypted](qsslsocket.html#isEncrypted)（ ） 。

```
void encryptedBytesWritten (qint64)
```

这是该信号的默认超载。

这个信号被发射时[QSslSocket](qsslsocket.html)它的加密数据写入到网络。该_written_参数包含已成功写入的字节数。

此功能被引入Qt的4.4 。

**See also** [QIODevice.bytesWritten](qiodevice.html#bytesWritten)（ ） 。

```
void modeChanged (QSslSocket::SslMode)
```

这是该信号的默认超载。

这个信号被发射时[QSslSocket](qsslsocket.html)从变化[QSslSocket.UnencryptedMode](qsslsocket.html#SslMode-enum)要么[QSslSocket.SslClientMode](qsslsocket.html#SslMode-enum) or [QSslSocket.SslServerMode](qsslsocket.html#SslMode-enum)。_mode_是新的模式。

**See also** [QSslSocket.mode](qsslsocket.html#mode)（ ） 。

```
void peerVerifyError (const QSslError&)
```

这是该信号的默认超载。

[QSslSocket](qsslsocket.html)可以在SSL握手期间发出此信号几次，加密已经建立之前，以表明在建立对等体的身份已经发生了错误。该_error_是通常表示[QSslSocket](qsslsocket.html)无法安全地识别对端。

这个信号提供了一个早期迹象时，什么是错的。通过连接到这个信号时，您可以手动选择推倒从连接槽内的连接握手完成之前。如果不采取行动，[QSslSocket](qsslsocket.html)将继续发光[QSslSocket.sslErrors](qsslsocket.html#sslErrors)（ ） 。

此功能被引入Qt的4.4 。

**See also** [sslErrors](qsslsocket.html#sslErrors)（ ） 。

```
void sslErrors (const QList<QSslError>&)
```

这是该信号的默认超载。

[QSslSocket](qsslsocket.html)SSL握手之后发出这一信号，表明在建立对等体的身份的一个或多个错误时有发生。该错误通常是一个迹象表明，[QSslSocket](qsslsocket.html)无法安全地识别对端。除非采取任何行动，在此之后信号已经发出的连接将被丢弃。

如果你想继续连接，尽管已发生的错误，你必须调用[QSslSocket.ignoreSslErrors](qsslsocket.html#ignoreSslErrors)（）从连接到该信号的时隙内。如果你需要访问在以后的错误列表，你可以调用[sslErrors](qsslsocket.html#sslErrors)（ ） （不带参数） 。

_errors_包含一个或多个错误，防止[QSslSocket](qsslsocket.html)从验证对等体的身份。

注意：您不能使用[Qt.QueuedConnection](qt.html#ConnectionType-enum)当连接到该信号，或呼叫[QSslSocket.ignoreSslErrors](qsslsocket.html#ignoreSslErrors)（ ）不会有任何效果。

**See also** [peerVerifyError](qsslsocket.html#peerVerifyError)（ ） 。