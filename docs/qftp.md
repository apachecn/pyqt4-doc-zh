# QFtp Class Reference

## [[QtNetwork](index.htm) module]

该QFtp类提供FTP协议的客户端的实现。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum Command { None_, SetTransferMode, SetProxy, ConnectToHost, ..., RawCommand }`
*   `enum Error { NoError, UnknownError, HostNotFound, ConnectionRefused, NotConnected }`
*   `enum State { Unconnected, HostLookup, Connecting, Connected, LoggedIn, Closing }`
*   `enum TransferMode { Active, Passive }`
*   `enum TransferType { Binary, Ascii }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `abort (self)`
*   `int bytesAvailable (self)`
*   `int cd (self, QString directory)`
*   `clearPendingCommands (self)`
*   `int close (self)`
*   `int connectToHost (self, QString host, int port = 21)`
*   `Command currentCommand (self)`
*   `QIODevice currentDevice (self)`
*   `int currentId (self)`
*   `Error error (self)`
*   `QString errorString (self)`
*   `int get (self, QString file, QIODevice device = None, TransferType type = QFtp.Binary)`
*   `bool hasPendingCommands (self)`
*   `int list (self, QString directory = QString())`
*   `int login (self, QString user = QString(), QString password = QString())`
*   `int mkdir (self, QString dir)`
*   `int put (self, QByteArray data, QString file, TransferType type = QFtp.Binary)`
*   `int put (self, QIODevice device, QString file, TransferType type = QFtp.Binary)`
*   `int rawCommand (self, QString command)`
*   `str read (self, int maxlen)`
*   `QByteArray readAll (self)`
*   `int remove (self, QString file)`
*   `int rename (self, QString oldname, QString newname)`
*   `int rmdir (self, QString dir)`
*   `int setProxy (self, QString host, int port)`
*   `int setTransferMode (self, TransferMode mode)`
*   `State state (self)`

### Qt Signals

*   `void commandFinished (int,bool)`
*   `void commandStarted (int)`
*   `void dataTransferProgress (qint64,qint64)`
*   `void done (bool)`
*   `void listInfo (const QUrlInfo&)`
*   `void rawCommandReply (int,const QString&)`
*   `void readyRead ()`
*   `void stateChanged (int)`

* * *

## Detailed Description

该QFtp类提供FTP协议的客户端的实现。

这个类提供了一个直接接口到FTP ，让您拥有更多的控制权的要求。然而，对于新的应用程序，它是推荐使用[QNetworkAccessManager](qnetworkaccessmanager.html)和[QNetworkReply](qnetworkreply.html)作为这些类具有一个简单，但更强大的API 。

类以异步方式工作，所以没有阻挡功能。如果操作不能被立即执行，该函数将仍然返回直线距离，操作将被安排在以后执行。调度操作的结果通过信号报告。这种方法依赖于事件循环运行之中。

可以计划的操作（它们在文档其馀部分被称为“命令” ）有以下几种：[connectToHost](qftp.html#connectToHost)（ ）[login](qftp.html#login)（ ）[close](qftp.html#close)（ ）[list](qftp.html#list)（ ）[cd](qftp.html#cd)（ ）[get](qftp.html#get)（ ）[put](qftp.html#put)（ ）[remove](qftp.html#remove)（ ）[mkdir](qftp.html#mkdir)（ ）[rmdir](qftp.html#rmdir)（ ）[rename](qftp.html#rename)（）和[rawCommand](qftp.html#rawCommand)（ ） 。

所有这些命令都返回一个唯一的标识符，它允许你跟踪当前正在执行的命令。当一个指令的执行开始时，[commandStarted](qftp.html#commandStarted)（ ）信号与命令的识别码被发射。当命令完成后，[commandFinished](qftp.html#commandFinished)（ ）信号发出的命令的标识符和一个布尔值，表示该命令是否有错误完成。

在某些情况下，您可能要执行的命令序列，例如：如果你想连接并登录到FTP服务器。这是简单的实现：

```
 QFtp *ftp = new QFtp(parent);
 ftp->connectToHost("ftp.qt.nokia.com");
 ftp->login();

```

在这种情况下，两个FTP命令已排定。当最后一个调度命令已完成，一[done](qftp.html#done)（ ）信号被发射一个布尔参数，它告诉你的序列是否有错误完成。

如果其中一个命令在命令序列的执行过程中发生了错误，所有挂起的命令（即预定的，但尚未执行的命令）被清零，并且没有信号发射它们。

一些命令，例如[list](qftp.html#list)（ ） ，发出额外的信号来报告他们的成果。

例如：如果你想从Qt的FTP服务器上下载安装文件，你会这样写：

```
 ftp->connectToHost("ftp.qt.nokia.com");   // id == 1
 ftp->login();                             // id == 2
 ftp->cd("qt");                            // id == 3
 ftp->get("INSTALL");                      // id == 4
 ftp->close();                             // id == 5

```

在这个例子中的信号按以下顺序发出（以小的变化，这取决于网络的流量等） ：

```
 start(1)
 stateChanged(HostLookup)
 stateChanged(Connecting)
 stateChanged(Connected)
 finished(1, false)

 start(2)
 stateChanged(LoggedIn)
 finished(2, false)

 start(3)
 finished(3, false)

 start(4)
 dataTransferProgress(0, 3798)
 dataTransferProgress(2896, 3798)
 readyRead()
 dataTransferProgress(3798, 3798)
 readyRead()
 finished(4, false)

 start(5)
 stateChanged(Closing)
 stateChanged(Unconnected)
 finished(5, false)

 done(false)

```

该[dataTransferProgress](qftp.html#dataTransferProgress)如果要显示在上面的例子（）信号是有用的一[progress bar](qprogressbar.html)以通知用户有关下载的进度。该[readyRead](qftp.html#readyRead)（ ）信号告诉你，有数据准备好读。可被查询的数据量，然后与[bytesAvailable](qftp.html#bytesAvailable)（）函数，它可以读取与该[read](qftp.html#read)（）或[readAll](qftp.html#readAll)（）函数。

如果登录失败对于上面的例子中，信号是这样的：

```
 start(1)
 stateChanged(HostLookup)
 stateChanged(Connecting)
 stateChanged(Connected)
 finished(1, false)

 start(2)
 finished(2, true)

 done(true)

```

然后，您可以获取与错误的详细信息[error](qftp.html#error)（）和[errorString](qftp.html#errorString)（）函数。

对于文件传输， QFtp可以同时使用主动或被动模式，并使用被动传输文件的默认模式，见文档[setTransferMode](qftp.html#setTransferMode)（ ） ，以便了解更多的细节。

Call [setProxy](qftp.html#setProxy)（ ）使QFtp通过FTP代理服务器进行连接。

该功能[currentId](qftp.html#currentId)（）和[currentCommand](qftp.html#currentCommand)（ ）提供有关当前正在执行的命令的详细信息。

该功能[hasPendingCommands](qftp.html#hasPendingCommands)（）和[clearPendingCommands](qftp.html#clearPendingCommands)（）允许您查询和清除挂起的命令的列表。

如果你是一个有经验的网络程序员，并希望有完全的控制，您可以使用[rawCommand](qftp.html#rawCommand)（）来执行任意FTP命令。

**Warning:**QFtp的当前版本不完全支持非Unix的FTP服务器。

* * *

## Type Documentation

```
QFtp.Command
```

该枚举被用作返回值[currentCommand](qftp.html#currentCommand)（）函数。这可以让你执行特定命令的具体行动，例如：在FTP客户端，你可能想清除的目录视图时，[list](qftp.html#list)如果在这种情况下，你可以简单地检查连接到启动的插槽（ ）信号， （ ）命令启动[currentCommand](qftp.html#currentCommand)（）是`List`。

| Constant | Value | Description |
| --- | --- | --- |
| `QFtp.None` | `0` | 正在执行任何命令。 |
| `QFtp.SetTransferMode` | `1` | 设置[transfer](qftp.html#TransferMode-enum)模式。 |
| `QFtp.SetProxy` | `2` | 打开或关闭代理。 |
| `QFtp.ConnectToHost` | `3` | [connectToHost](qftp.html#connectToHost)（）被执行。 |
| `QFtp.Login` | `4` | [login](qftp.html#login)（）被执行。 |
| `QFtp.Close` | `5` | [close](qftp.html#close)（）被执行。 |
| `QFtp.List` | `6` | [list](qftp.html#list)（）被执行。 |
| `QFtp.Cd` | `7` | [cd](qftp.html#cd)（）被执行。 |
| `QFtp.Get` | `8` | [get](qftp.html#get)（）被执行。 |
| `QFtp.Put` | `9` | [put](qftp.html#put)（）被执行。 |
| `QFtp.Remove` | `10` | [remove](qftp.html#remove)（）被执行。 |
| `QFtp.Mkdir` | `11` | [mkdir](qftp.html#mkdir)（）被执行。 |
| `QFtp.Rmdir` | `12` | [rmdir](qftp.html#rmdir)（）被执行。 |
| `QFtp.Rename` | `13` | [rename](qftp.html#rename)（）被执行。 |
| `QFtp.RawCommand` | `14` | [rawCommand](qftp.html#rawCommand)（）被执行。 |

**See also** [currentCommand](qftp.html#currentCommand)（ ） 。

```
QFtp.Error
```

这个枚举标识所发生的错误。

| Constant | Value | Description |
| --- | --- | --- |
| `QFtp.NoError` | `0` | 未发生错误。 |
| `QFtp.HostNotFound` | `2` | 该主机名查找失败。 |
| `QFtp.ConnectionRefused` | `3` | 服务器拒绝连接。 |
| `QFtp.NotConnected` | `4` | 试图发送一个命令，但有一个服务器的任何连接。 |
| `QFtp.UnknownError` | `1` | 发生错误比上述指定的。 |

**See also** [error](qftp.html#error)（ ） 。

```
QFtp.State
```

这个枚举变量定义的连接状态：

| Constant | Value | Description |
| --- | --- | --- |
| `QFtp.Unconnected` | `0` | 还有就是主机的连接。 |
| `QFtp.HostLookup` | `1` | 主机名查找正在进行中。 |
| `QFtp.Connecting` | `2` | 连接到主机的尝试正在进行中。 |
| `QFtp.Connected` | `3` | 到主机的连接已经完成。 |
| `QFtp.LoggedIn` | `4` | 连接和用户登录已经实现。 |
| `QFtp.Closing` | `5` | 连接被关闭了，但它尚未关闭。 （该状态将是`Unconnected`当连接关闭。 ） |

**See also** [stateChanged](qftp.html#stateChanged)（）和[state](qftp.html#state)（ ） 。

```
QFtp.TransferMode
```

FTP使用两种套接字连接，一个用于命令和另一个用于传输数据。而总是由客户端发起命令连接，第二连接可以通过在客户端或服务器来启动。

这个枚举定义了客户端（被动模式）或服务器（主动模式）是否应该建立数据连接。

| Constant | Value | Description |
| --- | --- | --- |
| `QFtp.Passive` | `1` | 客户端连接到服务器传送数据。 |
| `QFtp.Active` | `0` | 该服务器连接到客户端发送其数据。 |

```
QFtp.TransferType
```

这个枚举标识与get和put命令中使用的数据传输类型。

| Constant | Value | Description |
| --- | --- | --- |
| `QFtp.Binary` | `0` | 这些数据将被传输二进制模式。 |
| `QFtp.Ascii` | `1` | 这些数据将被转移在ASCII模式和新行字符将被转换为本地格式。 |

* * *

## Method Documentation

```
QFtp.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QFtp](qftp.html)与给定对象_parent_。

```
QFtp.abort (self)
```

这种方法也是一个Qt槽与C + +的签名`void abort()`。

中止当前命令，并删除所有已计划的命令。

如果有一个未完成的命令（即命令的量，[commandStarted](qftp.html#commandStarted)（）信号已被发射，但是该[commandFinished](qftp.html#commandFinished)（）信号没有被发射的） ，该函数发送一个`ABORT`命令给服务器。当服务器回复该命令被中止，[commandFinished](qftp.html#commandFinished)（）的信号与`error`参数设置为`true`发出该命令。由于定时问题，有可能在命令已经完成之前中止请求到达服务器，在这种情况下，该[commandFinished](qftp.html#commandFinished)（）信号被发射的`error`参数设置为`false`。

对于那些受中止（ ）其他所有的命令，没有信号发射。

如果你不开始进一步直接中止后FTP命令（ ） ，将不会有任何计划的命令和[done](qftp.html#done)（）信号被发射。

**Warning:**有些FTP服务器，例如BSD的FTP守护程序（ 0.3版本） ，返回错误已经发生中止，即使一个肯定的答复。对于这些服务器的[commandFinished](qftp.html#commandFinished)（ ）信号有错误标志设置为`false`，即使命令没有成功完成。

**See also** [clearPendingCommands](qftp.html#clearPendingCommands)（ ） 。

```
int QFtp.bytesAvailable (self)
```

返回可从数据套接字中读取的时刻的字节数。

**See also** [get](qftp.html#get)（ ）[readyRead](qftp.html#readyRead)（ ）[read](qftp.html#read)（）和[readAll](qftp.html#readAll)（ ） 。

```
int QFtp.cd (self, QString directory)
```

改变了服务器的工作目录_dir_。

该功能不会阻止，并立即返回。该命令是预定的，并且是异步执行的执行。该函数返回一个唯一的标识符，它是由通过[commandStarted](qftp.html#commandStarted)（）和[commandFinished](qftp.html#commandFinished)（ ） 。

当命令开始[commandStarted](qftp.html#commandStarted)（）信号被发射。当它完成时的[commandFinished](qftp.html#commandFinished)（）信号被发射。

**See also** [commandStarted](qftp.html#commandStarted)（）和[commandFinished](qftp.html#commandFinished)（ ） 。

```
QFtp.clearPendingCommands (self)
```

删除所有挂起的命令从预定的命令列表。这并不会影响正在执行的命令。如果你想停止这一点，使用[abort](qftp.html#abort)（ ） 。

**See also** [hasPendingCommands](qftp.html#hasPendingCommands)（）和[abort](qftp.html#abort)（ ） 。

```
int QFtp.close (self)
```

关闭连接到FTP服务器。

该[stateChanged](qftp.html#stateChanged)（）信号被发射时，在连接过程的状态变化，例如至`Closing`，然后`Unconnected`。

该功能不会阻止，并立即返回。该命令是预定的，并且是异步执行的执行。该函数返回一个唯一的标识符，它是由通过[commandStarted](qftp.html#commandStarted)（）和[commandFinished](qftp.html#commandFinished)（ ） 。

当命令开始[commandStarted](qftp.html#commandStarted)（）信号被发射。当它完成时的[commandFinished](qftp.html#commandFinished)（）信号被发射。

**See also** [stateChanged](qftp.html#stateChanged)（ ）[commandStarted](qftp.html#commandStarted)（）和[commandFinished](qftp.html#commandFinished)（ ） 。

```
int QFtp.connectToHost (self, QString host, int port = 21)
```

连接到FTP服务器_host_使用端口_port_。

该[stateChanged](qftp.html#stateChanged)（）信号被发射时，在连接过程的状态变化，例如至`HostLookup`，然后`Connecting`，然后`Connected`。

该功能不会阻止，并立即返回。该命令是预定的，并且是异步执行的执行。该函数返回一个唯一的标识符，它是由通过[commandStarted](qftp.html#commandStarted)（）和[commandFinished](qftp.html#commandFinished)（ ） 。

当命令开始[commandStarted](qftp.html#commandStarted)（）信号被发射。当它完成时的[commandFinished](qftp.html#commandFinished)（）信号被发射。

**See also** [stateChanged](qftp.html#stateChanged)（ ）[commandStarted](qftp.html#commandStarted)（）和[commandFinished](qftp.html#commandFinished)（ ） 。

```
Command QFtp.currentCommand (self)
```

[

返回FTP命令被执行的命令类型或`None`如果没有命令被执行。

](qftp.html#Command-enum)

[**See also**](qftp.html#Command-enum) [currentId](qftp.html#currentId)（ ） 。

```
QIODevice QFtp.currentDevice (self)
```

[](qiodevice.html)

[返回](qiodevice.html)[QIODevice](qiodevice.html)指针所使用的FTP命令来读取数据或存储数据。如果有正在执行无电流的FTP命令，或者如果命令不使用的IO设备，该函数返回0 。

此功能可用于删除的[QIODevice](qiodevice.html)在连接到插槽[commandFinished](qftp.html#commandFinished)（）信号。

**See also** [get](qftp.html#get)（）和[put](qftp.html#put)（ ） 。

```
int QFtp.currentId (self)
```

返回正在执行FTP命令或标识符0 ，如果没有命令被执行。

**See also** [currentCommand](qftp.html#currentCommand)（ ） 。

```
Error QFtp.error (self)
```

[](qftp.html#Error-enum)

[返回所发生的最后一个错误。接收时，此功能非常有用，找出什么地方出了错一](qftp.html#Error-enum)[commandFinished](qftp.html#commandFinished)（）或一[done](qftp.html#done)（）的信号与`error`参数设置为`true`。

如果你开始一个新的命令，错误状态重置为`NoError`。

```
QString QFtp.errorString (self)
```

返回上次发生错误的人类可读的描述。接收时，这是用于呈现错误信息给用户有用的一[commandFinished](qftp.html#commandFinished)（）或一[done](qftp.html#done)（）的信号与`error`参数设置为`true`。

错误字符串通常是（但不总是）​​从服务器的应答，因此它并不总是可能的翻译的字符串。如果消息来自Qt中，字符串已通过[tr](qobject.html#tr)（ ） 。

```
int QFtp.get (self, QString file, QIODevice device = None, TransferType type = QFtp.Binary)
```

下载文件_file_从服务器。

If _dev_是0，则[readyRead](qftp.html#readyRead)当有数据可供读取（ ）信号被发射。然后，您可以与读取数据[read](qftp.html#read)（）或[readAll](qftp.html#readAll)（）函数。

If _dev_不为0时，数据被直接写入设备_dev_。确保_dev_指针是有效的操作的持续时间（它是安全的删除当[commandFinished](qftp.html#commandFinished)（）信号被发射） 。在这种情况下[readyRead](qftp.html#readyRead)（）信号是_not_发出的，你不能与读取数据[read](qftp.html#read)（）或[readAll](qftp.html#readAll)（）函数。

如果不立即读取数据变得可用，即当[readyRead](qftp.html#readyRead)（）信号被发射，它仍然是可用的，直到下一个指令开始。

例如，如果你想尽快有一些可用的数据呈现给用户，连接到[readyRead](qftp.html#readyRead)（）信号，并立即读出的数据。在另一方面，如果只想用完整的数据来工作，你可以连接到[commandFinished](qftp.html#commandFinished)（ ）信号和读取时的get （ ）命令完成的数据。

这取决于价值的数据作为二进制或ASCII_type_。

该功能不会阻止，并立即返回。该命令是预定的，并且是异步执行的执行。该函数返回一个唯一的标识符，它是由通过[commandStarted](qftp.html#commandStarted)（）和[commandFinished](qftp.html#commandFinished)（ ） 。

当命令开始[commandStarted](qftp.html#commandStarted)（）信号被发射。当它完成时的[commandFinished](qftp.html#commandFinished)（）信号被发射。

[commandFinished](qftp.html#commandFinished)（ ）

**See also** [readyRead](qftp.html#readyRead)（ ）[dataTransferProgress](qftp.html#dataTransferProgress)（）和[commandStarted](qftp.html#commandStarted)（ ） 。

```
bool QFtp.hasPendingCommands (self)
```

返回True如果有尚未被执行计划的任何命令，否则返回False 。

正在执行的命令是_not_视为一个调度命令。

**See also** [clearPendingCommands](qftp.html#clearPendingCommands)（ ）[currentId](qftp.html#currentId)（）和[currentCommand](qftp.html#currentCommand)（ ） 。

```
int QFtp.list (self, QString directory = QString())
```

列出目录的内容_dir_在FTP服务器上。如果_dir_是空的，它会列出当前目录的内容。

该[listInfo](qftp.html#listInfo)（ ）信号被发射对找到的每个目录项。

该功能不会阻止，并立即返回。该命令是预定的，并且是异步执行的执行。该函数返回一个唯一的标识符，它是由通过[commandStarted](qftp.html#commandStarted)（）和[commandFinished](qftp.html#commandFinished)（ ） 。

当命令开始[commandStarted](qftp.html#commandStarted)（）信号被发射。当它完成时的[commandFinished](qftp.html#commandFinished)（）信号被发射。

**See also** [listInfo](qftp.html#listInfo)（ ）[commandStarted](qftp.html#commandStarted)（）和[commandFinished](qftp.html#commandFinished)（ ） 。

```
int QFtp.login (self, QString user = QString(), QString password = QString())
```

登录到FTP服务器的用户名_user_和密码_password_。

该[stateChanged](qftp.html#stateChanged)（）信号被发射时，在连接过程的状态变化，例如至`LoggedIn`。

该功能不会阻止，并立即返回。该命令是预定的，并且是异步执行的执行。该函数返回一个唯一的标识符，它是由通过[commandStarted](qftp.html#commandStarted)（）和[commandFinished](qftp.html#commandFinished)（ ） 。

当命令开始[commandStarted](qftp.html#commandStarted)（）信号被发射。当它完成时的[commandFinished](qftp.html#commandFinished)（）信号被发射。

**See also** [commandStarted](qftp.html#commandStarted)（）和[commandFinished](qftp.html#commandFinished)（ ） 。

```
int QFtp.mkdir (self, QString dir)
```

创建一个名为目录_dir_在服务器上。

该功能不会阻止，并立即返回。该命令是预定的，并且是异步执行的执行。该函数返回一个唯一的标识符，它是由通过[commandStarted](qftp.html#commandStarted)（）和[commandFinished](qftp.html#commandFinished)（ ） 。

当命令开始[commandStarted](qftp.html#commandStarted)（）信号被发射。当它完成时的[commandFinished](qftp.html#commandFinished)（）信号被发射。

**See also** [commandStarted](qftp.html#commandStarted)（）和[commandFinished](qftp.html#commandFinished)（ ） 。

```
int QFtp.put (self, QByteArray data, QString file, TransferType type = QFtp.Binary)
```

读取IO设备中的数据_dev_，并将其写入到被调用的文件_file_在服务器上。读取数据从IO设备的块，所以此重载允许您传输大量的数据，而不需要读取所有的数据到内存中一次。

这取决于价值的数据作为二进制或ASCII_type_。

确保_dev_指针是有效的操作的持续时间（它是安全的删除当[commandFinished](qftp.html#commandFinished)（）被发射） 。

```
int QFtp.put (self, QIODevice device, QString file, TransferType type = QFtp.Binary)
```

这是一个重载函数。

写入给定的一个副本_data_要调用的文件_file_在服务器上。上传的进度报告的[dataTransferProgress](qftp.html#dataTransferProgress)（）信号。

这取决于价值的数据作为二进制或ASCII_type_。

该功能不会阻止，并立即返回。该命令是预定的，并且是异步执行的执行。该函数返回一个唯一的标识符，它是由通过[commandStarted](qftp.html#commandStarted)（）和[commandFinished](qftp.html#commandFinished)（ ） 。

当命令开始[commandStarted](qftp.html#commandStarted)（）信号被发射。当它完成时的[commandFinished](qftp.html#commandFinished)（）信号被发射。

由于该功能需要的副本_data_，你可以放弃自己的副本时，该函数返回。

**See also** [dataTransferProgress](qftp.html#dataTransferProgress)（ ）[commandStarted](qftp.html#commandStarted)（）和[commandFinished](qftp.html#commandFinished)（ ） 。

```
int QFtp.rawCommand (self, QString command)
```

将原始的FTP命令_command_到FTP服务器。这是低层次的FTP访问有用的。如果你想执行的操作具有等效[QFtp](qftp.html)的功能，我们建议使用该功能，而不是原始的FTP命令，因为功能更容易，更安全。

该功能不会阻止，并立即返回。该命令是预定的，并且是异步执行的执行。该函数返回一个唯一的标识符，它是由通过[commandStarted](qftp.html#commandStarted)（）和[commandFinished](qftp.html#commandFinished)（ ） 。

当命令开始[commandStarted](qftp.html#commandStarted)（）信号被发射。当它完成时的[commandFinished](qftp.html#commandFinished)（）信号被发射。

**See also** [rawCommandReply](qftp.html#rawCommandReply)（ ）[commandStarted](qftp.html#commandStarted)（）和[commandFinished](qftp.html#commandFinished)（ ） 。

```
str QFtp.read (self, int maxlen)
```

阅读_maxlen_从数据插座成字节_data_并返回读取的字节数。返回-1，如果发生了错误。

**See also** [get](qftp.html#get)（ ）[readyRead](qftp.html#readyRead)（ ）[bytesAvailable](qftp.html#bytesAvailable)（）和[readAll](qftp.html#readAll)（ ） 。

```
QByteArray QFtp.readAll (self)
```

[

读取所有可用的数据套接字的字节数，并返回它们。

](qbytearray.html)

[**See also**](qbytearray.html) [get](qftp.html#get)（ ）[readyRead](qftp.html#readyRead)（ ）[bytesAvailable](qftp.html#bytesAvailable)（）和[read](qftp.html#read)（ ） 。

```
int QFtp.remove (self, QString file)
```

删除的文件称为_file_从服务器。

该功能不会阻止，并立即返回。该命令是预定的，并且是异步执行的执行。该函数返回一个唯一的标识符，它是由通过[commandStarted](qftp.html#commandStarted)（）和[commandFinished](qftp.html#commandFinished)（ ） 。

当命令开始[commandStarted](qftp.html#commandStarted)（）信号被发射。当它完成时的[commandFinished](qftp.html#commandFinished)（）信号被发射。

**See also** [commandStarted](qftp.html#commandStarted)（）和[commandFinished](qftp.html#commandFinished)（ ） 。

```
int QFtp.rename (self, QString oldname, QString newname)
```

所谓重命名文件_oldname_至_newname_在服务器上。

该功能不会阻止，并立即返回。该命令是预定的，并且是异步执行的执行。该函数返回一个唯一的标识符，它是由通过[commandStarted](qftp.html#commandStarted)（）和[commandFinished](qftp.html#commandFinished)（ ） 。

当命令开始[commandStarted](qftp.html#commandStarted)（）信号被发射。当它完成时的[commandFinished](qftp.html#commandFinished)（）信号被发射。

**See also** [commandStarted](qftp.html#commandStarted)（）和[commandFinished](qftp.html#commandFinished)（ ） 。

```
int QFtp.rmdir (self, QString dir)
```

所谓删除的目录_dir_从服务器。

该功能不会阻止，并立即返回。该命令是预定的，并且是异步执行的执行。该函数返回一个唯一的标识符，它是由通过[commandStarted](qftp.html#commandStarted)（）和[commandFinished](qftp.html#commandFinished)（ ） 。

当命令开始[commandStarted](qftp.html#commandStarted)（）信号被发射。当它完成时的[commandFinished](qftp.html#commandFinished)（）信号被发射。

**See also** [commandStarted](qftp.html#commandStarted)（）和[commandFinished](qftp.html#commandFinished)（ ） 。

```
int QFtp.setProxy (self, QString host, int port)
```

允许主机使用FTP代理的_host_和端口_port_。调用此函数_host_空禁用代理。

[QFtp](qftp.html)不支持FTP环比HTTP代理服务器。使用[QNetworkAccessManager](qnetworkaccessmanager.html)这一点。

```
int QFtp.setTransferMode (self, TransferMode mode)
```

设置当前FTP传输模式_mode_。默认值是[QFtp.Passive](qftp.html#TransferMode-enum)。

**See also** [QFtp.TransferMode](qftp.html#TransferMode-enum)。

```
State QFtp.state (self)
```

[](qftp.html#State-enum)

[返回该对象的当前状态。当状态改变时，](qftp.html#State-enum)[stateChanged](qftp.html#stateChanged)（）信号被发射。

**See also** [State](qftp.html#State-enum)和[stateChanged](qftp.html#stateChanged)（ ） 。

* * *

## Qt Signal Documentation

```
void commandFinished (int,bool)
```

这是该信号的默认超载。

处理确定的命令时，这个信号被发射_id_已完成。_error_是真的，如果在处理过程中发生错误，否则_error_是假的。

**See also** [commandStarted](qftp.html#commandStarted)（ ）[done](qftp.html#done)（ ）[error](qftp.html#error)（）和[errorString](qftp.html#errorString)（ ） 。

```
void commandStarted (int)
```

这是该信号的默认超载。

处理确定的命令时，这个信号被发射_id_开始。

**See also** [commandFinished](qftp.html#commandFinished)（）和[done](qftp.html#done)（ ） 。

```
void dataTransferProgress (qint64,qint64)
```

这是该信号的默认超载。

此信号响应于被发射[get](qftp.html#get)（）或[put](qftp.html#put)（）请求指示下载或上传的当前进度。

_done_是数据的一个已经被转移及金额_total_是数据要被读出或写入的总量。它是可能的[QFtp](qftp.html)类是不能够确定数据应该被转移的总量，在此情况_total_为0。 （如果这个信号连接到[QProgressBar](qprogressbar.html)，进度条显示一个繁忙的指标，如果总为0 ） 。

**Warning:** _done_和_total_不一定以字节为单位的大小，因为对于大文件的这些值可能需要被“缩放”，以避免溢出。

**See also** [get](qftp.html#get)（ ）[put](qftp.html#put)（）和[QProgressBar](qprogressbar.html)。

```
void done (bool)
```

这是该信号的默认超载。

这个信号被发射时的最后等候命令完成（这是后发出的最后一个命令的[commandFinished](qftp.html#commandFinished)（ ）信号） 。_error_是真的，如果在处理过程中发生错误，否则_error_是假的。

**See also** [commandFinished](qftp.html#commandFinished)（ ）[error](qftp.html#error)（）和[errorString](qftp.html#errorString)（ ） 。

```
void listInfo (const QUrlInfo&)
```

这是该信号的默认超载。

这个信号被发射的每个目录项的[list](qftp.html#list)（ ）命令的发现。条目的详细信息存储在_i_。

**See also** [list](qftp.html#list)（ ） 。

```
void rawCommandReply (int,const QString&)
```

这是该信号的默认超载。

此信号响应于所述发射[rawCommand](qftp.html#rawCommand)（）函数。_replyCode_是3位数字应答码和_detail_是遵循应答码的文本。

**See also** [rawCommand](qftp.html#rawCommand)（ ） 。

```
void readyRead ()
```

这是该信号的默认超载。

此信号响应于被发射[get](qftp.html#get)（ ）命令时有新的数据读取。

如果指定的设备如在第二个参数[get](qftp.html#get)（）命令，该信号是_not_射出，而是将数据直接写入到设备。

您可以使用读取数据[readAll](qftp.html#readAll)（）或[read](qftp.html#read)（）函数。

如果你想，只要它成为可用在处理大块数据这个信号是非常有用的。如果你只关心在完整的数据，只需连接到[commandFinished](qftp.html#commandFinished)（ ）信号并读取数据，然后代替。

**See also** [get](qftp.html#get)（ ）[read](qftp.html#read)（ ）[readAll](qftp.html#readAll)（）和[bytesAvailable](qftp.html#bytesAvailable)（ ） 。

```
void stateChanged (int)
```

这是该信号的默认超载。

这个信号被发射时的连接状态发生改变。这个论点_state_是该连接的新的状态，它是一个[State](qftp.html#State-enum)值。

它通常是在响应于发射[connectToHost](qftp.html#connectToHost)（）或[close](qftp.html#close)（）命令，但它也可以被发射的“自发地” ，例如当服务器意外关闭连接。

**See also** [connectToHost](qftp.html#connectToHost)（ ）[close](qftp.html#close)（ ）[state](qftp.html#state)（）和[State](qftp.html#State-enum)。