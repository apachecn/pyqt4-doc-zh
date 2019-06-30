# QHttp Class Reference

## [[QtNetwork](index.htm) module]

该QHttp类提供了HTTP协议的实现。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum ConnectionMode { ConnectionModeHttp, ConnectionModeHttps }`
*   `enum Error { NoError, UnknownError, HostNotFound, ConnectionRefused, ..., ProxyAuthenticationRequiredError }`
*   `enum State { Unconnected, HostLookup, Connecting, Sending, ..., Closing }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `__init__ (self, QString hostName, int port = 80, QObject parent = None)`
*   `__init__ (self, QString hostname, ConnectionMode mode, int port = 0, QObject parent = None)`
*   `abort (self)`
*   `int bytesAvailable (self)`
*   `clearPendingRequests (self)`
*   `int close (self)`
*   `QIODevice currentDestinationDevice (self)`
*   `int currentId (self)`
*   `QHttpRequestHeader currentRequest (self)`
*   `QIODevice currentSourceDevice (self)`
*   `Error error (self)`
*   `QString errorString (self)`
*   `int get (self, QString path, QIODevice to = None)`
*   `bool hasPendingRequests (self)`
*   `int head (self, QString path)`
*   `ignoreSslErrors (self)`
*   `QHttpResponseHeader lastResponse (self)`
*   `int post (self, QString path, QIODevice data, QIODevice to = None)`
*   `int post (self, QString path, QByteArray data, QIODevice to = None)`
*   `str read (self, int maxlen)`
*   `QByteArray readAll (self)`
*   `int request (self, QHttpRequestHeader header, QIODevice data = None, QIODevice to = None)`
*   `int request (self, QHttpRequestHeader header, QByteArray data, QIODevice to = None)`
*   `int setHost (self, QString hostName, int port = 80)`
*   `int setHost (self, QString hostname, ConnectionMode mode, int port = 0)`
*   `int setProxy (self, QString host, int port, QString user = QString(), QString password = QString())`
*   `int setProxy (self, QNetworkProxy proxy)`
*   `int setSocket (self, QTcpSocket socket)`
*   `int setUser (self, QString userName, QString password = QString())`
*   `State state (self)`

### Qt Signals

*   `void authenticationRequired (const QString&,quint16,QAuthenticator *)`
*   `void dataReadProgress (int,int)`
*   `void dataSendProgress (int,int)`
*   `void done (bool)`
*   `void proxyAuthenticationRequired (const QNetworkProxy&,QAuthenticator *)`
*   `void readyRead (const QHttpResponseHeader&)`
*   `void requestFinished (int,bool)`
*   `void requestStarted (int)`
*   `void responseHeaderReceived (const QHttpResponseHeader&)`
*   `void sslErrors (const QList&lt;QSslError&gt;&)`
*   `void stateChanged (int)`

* * *

## Detailed Description

该QHttp类提供了HTTP协议的实现。

这个类提供了一个直接接口的HTTP ，使您可以下载和上传数据的HTTP协议。然而，对于新的应用程序，它是推荐使用[QNetworkAccessManager](qnetworkaccessmanager.html)和[QNetworkReply](qnetworkreply.html)作为这些类具有一个简单，但更强大的API和更现代的协议实现。

类以异步方式工作，所以没有阻挡功能。如果操作不能被立即执行，该函数将仍然返回直线距离，操作将被安排在以后执行。调度操作的结果通过信号报告。这种方法依赖于事件循环运行之中。

可以计划的操作（他们被称为在文档其馀部分“请求” ）如下：[setHost](qhttp.html#setHost)（ ）[get](qhttp.html#get)（ ）[post](qhttp.html#post)（ ）[head](qhttp.html#head)（）和[request](qhttp.html#request)（ ） 。

所有这些请求都返回一个唯一的标识符，可以让你保持当前执行的请求的轨道。当一个请求的执行开始时，[requestStarted](qhttp.html#requestStarted)（）信号与该标识符被发射并且当请求完成时，[requestFinished](qhttp.html#requestFinished)（ ）信号被发射的标识符和一个布尔值，表示如果有错误的要求完成。

为了使一个HTTP请求必须设置合适的HTTP标头。下面的示例演示如何从Qt的网页（即网址中要求主HTML页面`http://qt.nokia.com/index.html`） ：

```
 [QHttpRequestHeader](qhttprequestheader.html) header("GET", [QUrl](qurl.html).toPercentEncoding("/index.html"));
 header.setValue("Host", "qt.nokia.com");
 http->setHost("qt.nokia.com");
 http->request(header);

```

对于常见的HTTP请求`GET`，`POST`和`HEAD`， QHttp提供方便的功能[get](qhttp.html#get)（ ）[post](qhttp.html#post)（）和[head](qhttp.html#head)（ ） 。他们已经在使用一个合理的标题，如果你没有设置特殊的头字段，它们更容易使用。上面的例子中，也可以写为：

```
 http->setHost("qt.nokia.com");                // id == 1
 http->get([QUrl](qurl.html).toPercentEncoding("/index.html")); // id == 2

```

在这个例子中的信号按以下顺序发出（以小的变化，这取决于网络的流量等） ：

```
 requestStarted(1)
 requestFinished(1, false)

 requestStarted(2)
 stateChanged(Connecting)
 stateChanged(Sending)
 dataSendProgress(77, 77)
 stateChanged(Reading)
 responseHeaderReceived(responseheader)
 dataReadProgress(5388, 0)
 readyRead(responseheader)
 dataReadProgress(18300, 0)
 readyRead(responseheader)
 stateChanged(Connected)
 requestFinished(2, false)

 done(false)

 stateChanged(Closing)
 stateChanged(Unconnected)

```

该[dataSendProgress](qhttp.html#dataSendProgress)（）和[dataReadProgress](qhttp.html#dataReadProgress)如果你想显示（ ）在上面的例子中信号是一个非常有用[progress bar](qprogressbar.html)以通知用户有关下载的进度。第二个参数是数据的总大小。在某些情况下这是不可能知道的总量提前，在这种情况下，第二个参数是0。 （如果您连接到一个[QProgressBar](qprogressbar.html)共0个结果在一个繁忙的指标。 ）

当响应标头被读出，有报导用[responseHeaderReceived](qhttp.html#responseHeaderReceived)（）信号。

该[readyRead](qhttp.html#readyRead)（ ）信号告诉你，有数据准备好读。的数据量然后可以查询与[bytesAvailable](qhttp.html#bytesAvailable)（）函数，它可以读取与该[read](qhttp.html#read)（）或[readAll](qhttp.html#readAll)（）函数。

如果其中一个命令在命令序列的执行过程中发生了错误，所有挂起的命令（即预定的，但尚未执行的命令）被清零，并且没有信号发射它们。

例如，如果你有要求的顺序如下

```
 http->setHost("www.foo.bar");       // id == 1
 http->get("/index.html");           // id == 2
 http->post("register.html", data);  // id == 3

```

和[get](qhttp.html#get)（ ）请求失败，因为主机查找失败，则[post](qhttp.html#post)（）请求永远不会执行，并且信号是这样的：

```
 requestStarted(1)
 requestFinished(1, false)

 requestStarted(2)
 stateChanged(HostLookup)
 requestFinished(2, true)

 done(true)

 stateChanged(Unconnected)

```

然后，您可以获取与错误的详细信息[error](qhttp.html#error)（）和[errorString](qhttp.html#errorString)（）函数。请注意，只有想不到的行为，如网络故障被认为是一个错误。如果服务器响应包含错误状态，就像一个404响应，该报告为正常的反应情况。所以，你应该经常检查[status code](qhttpresponseheader.html#statusCode)响应头中。

该功能[currentId](qhttp.html#currentId)（）和[currentRequest](qhttp.html#currentRequest)（ ）提供有关当前正在执行的请求的更多信息。

该功能[hasPendingRequests](qhttp.html#hasPendingRequests)（）和[clearPendingRequests](qhttp.html#clearPendingRequests)（）允许您查询和清除挂起的请求列表。

* * *

## Type Documentation

```
QHttp.ConnectionMode
```

此枚举用于指定连接使用的方式：

| Constant | Value | Description |
| --- | --- | --- |
| `QHttp.ConnectionModeHttp` | `0` | 该连接是一个普通的HTTP连接到服务器 |
| `QHttp.ConnectionModeHttps` | `1` | HTTPS协议的使用和连接使用SSL加密。 |

当使用HTTPS模式中，应注意连接到sslErrors信号，并处理可能出现的SSL错误。

这个枚举被引入或修改的Qt 4.3 。

**See also** [QSslSocket](qsslsocket.html)。

```
QHttp.Error
```

这个枚举标识所发生的错误。

| Constant | Value | Description |
| --- | --- | --- |
| `QHttp.NoError` | `0` | 未发生错误。 |
| `QHttp.HostNotFound` | `2` | 该主机名查找失败。 |
| `QHttp.ConnectionRefused` | `3` | 服务器拒绝连接。 |
| `QHttp.UnexpectedClose` | `4` | 服务器关闭了连接意外。 |
| `QHttp.InvalidResponseHeader` | `5` | 服务器发送一个无效的响应头。 |
| `QHttp.WrongContentLength` | `6` | 客户端不能正确读出的内容，因为发生相对于所述内容的长度的错误。 |
| `QHttp.Aborted` | `7` | 该请求被中止与[abort](qhttp.html#abort)（ ） 。 |
| `QHttp.ProxyAuthenticationRequiredError` | `9` | [QHttp](qhttp.html)是使用代理，而代理服务器需要身份验证来建立连接。 |
| `QHttp.AuthenticationRequiredError` | `8` | 该网站的服务器要求身份验证来完成请求。 |
| `QHttp.UnknownError` | `1` | 发生错误比上述指定的。 |

**See also** [error](qhttp.html#error)（ ） 。

```
QHttp.State
```

此枚举用于指定状态的客户端是：

| Constant | Value | Description |
| --- | --- | --- |
| `QHttp.Unconnected` | `0` | 还有就是主机的连接。 |
| `QHttp.HostLookup` | `1` | 主机名查找正在进行中。 |
| `QHttp.Connecting` | `2` | 连接到主机的尝试正在进行中。 |
| `QHttp.Sending` | `3` | 客户端发送的请求发送到服务器。 |
| `QHttp.Reading` | `4` | 客户端的请求已发送，并且客户端读取服务器的响应。 |
| `QHttp.Connected` | `5` | 到主机的连接是打开的，但是客户端既不是发送请求，也没有等待响应。 |
| `QHttp.Closing` | `6` | 连接被关闭了，但尚未关闭。 （该状态将是`Unconnected`当连接关闭。 ） |

**See also** [stateChanged](qhttp.html#stateChanged)（）和[state](qhttp.html#state)（ ） 。

* * *

## Method Documentation

```
QHttp.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QHttp](qhttp.html)对象。该_parent_参数被传递到[QObject](qobject.html)构造函数。

```
QHttp.__init__ (self, QString hostName, int port = 80, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QHttp](qhttp.html)对象。后续请求都通过连接到服务器完成_hostName_端口_port_。

该_parent_参数被传递到[QObject](qobject.html)构造函数。

**See also** [setHost](qhttp.html#setHost)（ ） 。

```
QHttp.__init__ (self, QString hostname, ConnectionMode mode, int port = 0, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QHttp](qhttp.html)对象。后续请求都通过连接到服务器完成_hostName_端口_port_使用连接模式_mode_。

如果端口为0 ，它会使用默认端口_mode_使用（ 80用于HTTP和HTTPS使用443 ） 。

该_parent_参数被传递到[QObject](qobject.html)构造函数。

**See also** [setHost](qhttp.html#setHost)（ ） 。

```
QHttp.abort (self)
```

这种方法也是一个Qt槽与C + +的签名`void abort()`。

中止当前的请求，并删除所有已计划的请求。

对当前的请求，则[requestFinished](qhttp.html#requestFinished)（）的信号与`error`争论`true`射出。对于那些受中止（ ）所有其他请求，没有信号发射。

由于这个插槽也删除了预定的要求，没有离开请求和[done](qhttp.html#done)（）信号被发射（与`error`争论`true`） 。

**See also** [clearPendingRequests](qhttp.html#clearPendingRequests)（ ） 。

```
int QHttp.bytesAvailable (self)
```

返回可以从响应内容被读取的时刻的字节数。

**See also** [get](qhttp.html#get)（ ）[post](qhttp.html#post)（ ）[request](qhttp.html#request)（ ）[readyRead](qhttp.html#readyRead)（ ）[read](qhttp.html#read)（）和[readAll](qhttp.html#readAll)（ ） 。

```
QHttp.clearPendingRequests (self)
```

删除从原定的请求列表中的所有挂起的请求。这并不会影响正在执行该请求。如果你想停止这一点，使用[abort](qhttp.html#abort)（ ） 。

**See also** [hasPendingRequests](qhttp.html#hasPendingRequests)（）和[abort](qhttp.html#abort)（ ） 。

```
int QHttp.close (self)
```

关闭连接，如果你有一个保持活动的连接，并希望将其关闭，这是很有用的。

对于发出的请求[get](qhttp.html#get)（ ）[post](qhttp.html#post)（）和[head](qhttp.html#head)（ ）[QHttp](qhttp.html)设置连接要保持活动。您也可以使用您传递给头做到这一点[request](qhttp.html#request)（）函数。[QHttp](qhttp.html)只有关闭连接到HTTP服务器，如果响应头要求它这样做。

该函数不会阻塞，而是立即返回。该请求被预定，并且是异步执行的执行。该函数返回一个唯一的标识符，它是由通过[requestStarted](qhttp.html#requestStarted)（）和[requestFinished](qhttp.html#requestFinished)（ ） 。

当该请求被启动[requestStarted](qhttp.html#requestStarted)（）信号被发射。当它完成时的[requestFinished](qhttp.html#requestFinished)（）信号被发射。

如果你想立即关闭连接，你必须使用[abort](qhttp.html#abort)（ ）来代替。

**See also** [stateChanged](qhttp.html#stateChanged)（ ）[abort](qhttp.html#abort)（ ）[requestStarted](qhttp.html#requestStarted)（ ）[requestFinished](qhttp.html#requestFinished)（）和[done](qhttp.html#done)（ ） 。

```
QIODevice QHttp.currentDestinationDevice (self)
```

[](qiodevice.html)

[返回](qiodevice.html)[QIODevice](qiodevice.html)指针，该指针被用作用于存储正在执行的HTTP请求的数据。如果没有当前请求或者请求不将数据存储到一个IO设备，该函数返回0 。

此功能可用于删除的[QIODevice](qiodevice.html)在连接到插槽[requestFinished](qhttp.html#requestFinished)（）信号。

**See also** [currentSourceDevice](qhttp.html#currentSourceDevice)（ ）[get](qhttp.html#get)（ ）[post](qhttp.html#post)（）和[request](qhttp.html#request)（ ） 。

```
int QHttp.currentId (self)
```

返回正在执行的HTTP请求或标识符0 ，如果没有请求被执行（即他们已经全部完成） 。

**See also** [currentRequest](qhttp.html#currentRequest)（ ） 。

```
QHttpRequestHeader QHttp.currentRequest (self)
```

[](qhttprequestheader.html)

[返回正在执行的HTTP请求的请求头。如果请求的是一个接发](qhttprequestheader.html)[setHost](qhttp.html#setHost)（）或[close](qhttp.html#close)（ ） ，它返回一个无效的请求头，即[QHttpRequestHeader.isValid](qhttpheader.html#isValid)（ ）返回False 。

**See also** [currentId](qhttp.html#currentId)（ ） 。

```
QIODevice QHttp.currentSourceDevice (self)
```

[](qiodevice.html)

[返回](qiodevice.html)[QIODevice](qiodevice.html)指针，该指针被用作要执行的HTTP请求的数据源。如果没有当前请求或者请求不使用IO设备作为数据源，这个函数返回0 。

此功能可用于删除的[QIODevice](qiodevice.html)在连接到插槽[requestFinished](qhttp.html#requestFinished)（）信号。

**See also** [currentDestinationDevice](qhttp.html#currentDestinationDevice)（ ）[post](qhttp.html#post)（）和[request](qhttp.html#request)（ ） 。

```
Error QHttp.error (self)
```

[](qhttp.html#Error-enum)

[返回所发生的最后一个错误。接收时，此功能非常有用，找出发生了什么](qhttp.html#Error-enum)[requestFinished](qhttp.html#requestFinished)（）或一[done](qhttp.html#done)（）的信号与`error`争论`true`。

如果你开始一个新的请求，错误状态重置为`NoError`。

```
QString QHttp.errorString (self)
```

返回上次发生错误的人类可读的描述。接收时，这是有用的，以呈现一个错误信息给用户的[requestFinished](qhttp.html#requestFinished)（）或一[done](qhttp.html#done)（）的信号与`error`争论`true`。

```
int QHttp.get (self, QString path, QIODevice to = None)
```

发送一个GET请求_path_通过设置服务器[setHost](qhttp.html#setHost)（）或在构造函数中指定。

_path_必须像一个绝对路径`/index.html`或者像一个绝对URI`http://example.com/index.html`并且必须与任一被编码[QUrl.toPercentEncoding](qurl.html#toPercentEncoding)（）或[QUrl.encodedPath](qurl.html#encodedPath)（ ） 。

如果IO设备_to_为0的[readyRead](qhttp.html#readyRead)（ ）信号被每个新的内容数据是可读取的时间发射。

如果IO设备_to_不为0时，响应的内容数据直接写入到设备。确保_to_指针是有效的操作的持续时间（它是安全的删除当[requestFinished](qhttp.html#requestFinished)（）信号被发射） 。

#### Request Processing

该函数不会阻塞，而是立即返回。该请求被预定，并且是异步执行的执行。该函数返回一个唯一的标识符，它是由通过[requestStarted](qhttp.html#requestStarted)（）和[requestFinished](qhttp.html#requestFinished)（ ） 。

当该请求被启动[requestStarted](qhttp.html#requestStarted)（）信号被发射。当它完成时的[requestFinished](qhttp.html#requestFinished)（）信号被发射。

**See also** [setHost](qhttp.html#setHost)（ ）[post](qhttp.html#post)（ ）[head](qhttp.html#head)（ ）[request](qhttp.html#request)（ ）[requestStarted](qhttp.html#requestStarted)（ ）[requestFinished](qhttp.html#requestFinished)（）和[done](qhttp.html#done)（ ） 。

```
bool QHttp.hasPendingRequests (self)
```

返回True如果有尚未被执行计划的任何请求，否则返回False 。

正在执行的请求_not_认为作为计划的要求。

**See also** [clearPendingRequests](qhttp.html#clearPendingRequests)（ ）[currentId](qhttp.html#currentId)（）和[currentRequest](qhttp.html#currentRequest)（ ） 。

```
int QHttp.head (self, QString path)
```

发送一个请求头_path_通过设置服务器[setHost](qhttp.html#setHost)（）或在构造函数中指定。

_path_必须像一个绝对路径`/index.html`或者像一个绝对URI`http://example.com/index.html`。

该函数不会阻塞，而是立即返回。该请求被预定，并且是异步执行的执行。该函数返回一个唯一的标识符，它是由通过[requestStarted](qhttp.html#requestStarted)（）和[requestFinished](qhttp.html#requestFinished)（ ） 。

当该请求被启动[requestStarted](qhttp.html#requestStarted)（）信号被发射。当它完成时的[requestFinished](qhttp.html#requestFinished)（）信号被发射。

**See also** [setHost](qhttp.html#setHost)（ ）[get](qhttp.html#get)（ ）[post](qhttp.html#post)（ ）[request](qhttp.html#request)（ ）[requestStarted](qhttp.html#requestStarted)（ ）[requestFinished](qhttp.html#requestFinished)（）和[done](qhttp.html#done)（ ） 。

```
QHttp.ignoreSslErrors (self)
```

这种方法也是一个Qt槽与C + +的签名`void ignoreSslErrors()`。

告诉[QSslSocket](qsslsocket.html)用于HTTP连接忽略报告的错误[sslErrors](qhttp.html#sslErrors)（）信号。

注意，该功能必须从连接到一个时隙内的称为[sslErrors](qhttp.html#sslErrors)（）信号有任何影响。

**See also** [QSslSocket](qsslsocket.html)和[QSslSocket.sslErrors](qsslsocket.html#sslErrors)（ ） 。

```
QHttpResponseHeader QHttp.lastResponse (self)
```

[](qhttpresponseheader.html)

[返回最近结束的HTTP请求接收到的响应报头。如果没有反应尚未收到](qhttpresponseheader.html)[QHttpResponseHeader.isValid](qhttpheader.html#isValid)（ ）将返回False 。

**See also** [currentRequest](qhttp.html#currentRequest)（ ） 。

```
int QHttp.post (self, QString path, QIODevice data, QIODevice to = None)
```

对于发送POST请求_path_通过设置服务器[setHost](qhttp.html#setHost)（）或在构造函数中指定。

_path_必须像一个绝对路径`/index.html`或者像一个绝对URI`http://example.com/index.html`并且必须与任一被编码[QUrl.toPercentEncoding](qurl.html#toPercentEncoding)（）或[QUrl.encodedPath](qurl.html#encodedPath)（ ） 。

传入的数据来自经_data_IO设备。

如果IO设备_to_为0的[readyRead](qhttp.html#readyRead)（ ）信号被每个新的内容数据是可读取的时间发射。

如果IO设备_to_不为0时，响应的内容数据直接写入到设备。确保_to_指针是有效的操作的持续时间（它是安全的删除当[requestFinished](qhttp.html#requestFinished)（）信号被发射） 。

该函数不会阻塞，而是立即返回。该请求被预定，并且是异步执行的执行。该函数返回一个唯一的标识符，它是由通过[requestStarted](qhttp.html#requestStarted)（）和[requestFinished](qhttp.html#requestFinished)（ ） 。

当该请求被启动[requestStarted](qhttp.html#requestStarted)（）信号被发射。当它完成时的[requestFinished](qhttp.html#requestFinished)（）信号被发射。

**See also** [setHost](qhttp.html#setHost)（ ）[get](qhttp.html#get)（ ）[head](qhttp.html#head)（ ）[request](qhttp.html#request)（ ）[requestStarted](qhttp.html#requestStarted)（ ）[requestFinished](qhttp.html#requestFinished)（）和[done](qhttp.html#done)（ ） 。

```
int QHttp.post (self, QString path, QByteArray data, QIODevice to = None)
```

这是一个重载函数。

_data_作为HTTP请求的内容数据。

```
str QHttp.read (self, int maxlen)
```

阅读_maxlen_从响应内容字节到_data_并返回读取的字节数。返回-1，如果发生了错误。

**See also** [get](qhttp.html#get)（ ）[post](qhttp.html#post)（ ）[request](qhttp.html#request)（ ）[readyRead](qhttp.html#readyRead)（ ）[bytesAvailable](qhttp.html#bytesAvailable)（）和[readAll](qhttp.html#readAll)（ ） 。

```
QByteArray QHttp.readAll (self)
```

[

读取响应内容的所有字节，并返回它们。

](qbytearray.html)

[**See also**](qbytearray.html) [get](qhttp.html#get)（ ）[post](qhttp.html#post)（ ）[request](qhttp.html#request)（ ）[readyRead](qhttp.html#readyRead)（ ）[bytesAvailable](qhttp.html#bytesAvailable)（）和[read](qhttp.html#read)（ ） 。

```
int QHttp.request (self, QHttpRequestHeader header, QIODevice data = None, QIODevice to = None)
```

发送一个请求到所设定的服务器[setHost](qhttp.html#setHost)（）或在构造函数中指定。使用_header_作为HTTP请求头。你是负责建立一个头适合于您的要求。

传入的数据来自经_data_IO设备。

如果IO设备_to_为0的[readyRead](qhttp.html#readyRead)（ ）信号被每个新的内容数据是可读取的时间发射。

如果IO设备_to_不为0时，响应的内容数据直接写入到设备。确保_to_指针是有效的操作的持续时间（它是安全的删除当[requestFinished](qhttp.html#requestFinished)（）信号被发射） 。

该函数不会阻塞，而是立即返回。该请求被预定，并且是异步执行的执行。该函数返回一个唯一的标识符，它是由通过[requestStarted](qhttp.html#requestStarted)（）和[requestFinished](qhttp.html#requestFinished)（ ） 。

当该请求被启动[requestStarted](qhttp.html#requestStarted)（）信号被发射。当它完成时的[requestFinished](qhttp.html#requestFinished)（）信号被发射。

**See also** [setHost](qhttp.html#setHost)（ ）[get](qhttp.html#get)（ ）[post](qhttp.html#post)（ ）[head](qhttp.html#head)（ ）[requestStarted](qhttp.html#requestStarted)（ ）[requestFinished](qhttp.html#requestFinished)（）和[done](qhttp.html#done)（ ） 。

```
int QHttp.request (self, QHttpRequestHeader header, QByteArray data, QIODevice to = None)
```

这是一个重载函数。

_data_作为HTTP请求的内容数据。

```
int QHttp.setHost (self, QString hostName, int port = 80)
```

设置用于为请求的HTTP服务器_hostName_端口_port_。

该函数不会阻塞，而是立即返回。该请求被预定，并且是异步执行的执行。该函数返回一个唯一的标识符，它是由通过[requestStarted](qhttp.html#requestStarted)（）和[requestFinished](qhttp.html#requestFinished)（ ） 。

当该请求被启动[requestStarted](qhttp.html#requestStarted)（）信号被发射。当它完成时的[requestFinished](qhttp.html#requestFinished)（）信号被发射。

**See also** [get](qhttp.html#get)（ ）[post](qhttp.html#post)（ ）[head](qhttp.html#head)（ ）[request](qhttp.html#request)（ ）[requestStarted](qhttp.html#requestStarted)（ ）[requestFinished](qhttp.html#requestFinished)（）和[done](qhttp.html#done)（ ） 。

```
int QHttp.setHost (self, QString hostname, ConnectionMode mode, int port = 0)
```

设置用于为请求的HTTP服务器_hostName_端口_port_使用连接模式_mode_。

如果端口为0 ，它会使用默认端口_mode_使用（ 80用于HTTP和HTTPS使用443 ） 。

该函数不会阻塞，而是立即返回。该请求被预定，并且是异步执行的执行。该函数返回一个唯一的标识符，它是由通过[requestStarted](qhttp.html#requestStarted)（）和[requestFinished](qhttp.html#requestFinished)（ ） 。

当该请求被启动[requestStarted](qhttp.html#requestStarted)（）信号被发射。当它完成时的[requestFinished](qhttp.html#requestFinished)（）信号被发射。

**See also** [get](qhttp.html#get)（ ）[post](qhttp.html#post)（ ）[head](qhttp.html#head)（ ）[request](qhttp.html#request)（ ）[requestStarted](qhttp.html#requestStarted)（ ）[requestFinished](qhttp.html#requestFinished)（）和[done](qhttp.html#done)（ ） 。

```
int QHttp.setProxy (self, QString host, int port, QString user = QString(), QString password = QString())
```

启用HTTP代理支持，则使用代理服务器_host_端口_port_。_username_和_password_如果代理服务器需要身份验证可以提供。

例如：

```
 void Ticker.getTicks()
 {
   http = new [QHttp](qhttp.html)(this);
   connect(http, SIGNAL(done(bool)), this, SLOT(showPage()));
   http->setProxy("proxy.example.com", 3128);
   http->setHost("ticker.example.com");
   http->get("/ticks.asp");
 }

 void Ticker.showPage()
 {
   display(http->readAll());
 }

```

[QHttp](qhttp.html)仅支持非透明web代理服务器，如鱿鱼Web代理缓存服务器（从[http://www.squid.org/](http://www.squid.org/)） 。对于透明代理，比如SOCKS5 ，使用[QNetworkProxy](qnetworkproxy.html)代替。

**Note:**setProxy （ ）之前已被调用[setHost](qhttp.html#setHost)（ ）才能生效。如果setProxy （ ）之后调用[setHost](qhttp.html#setHost)（ ） ，那么就不会适用，直至后[setHost](qhttp.html#setHost)（）被再次调用。

**See also** [QFtp.setProxy](qftp.html#setProxy)（ ） 。

```
int QHttp.setProxy (self, QNetworkProxy proxy)
```

这是一个重载函数。

从使用的代理服务器设置启用HTTP代理支持_proxy_。如果_proxy_是一个透明代理，[QHttp](qhttp.html)将调用[QAbstractSocket.setProxy](qabstractsocket.html#setProxy)（ ）底层套接字上。如果类型是[QNetworkProxy.HttpCachingProxy](qnetworkproxy.html#ProxyType-enum)，[QHttp](qhttp.html)会像以前的功能。

**Note:**对于使用Qt 4.3的兼容性，如果代理类型是[QNetworkProxy.HttpProxy](qnetworkproxy.html#ProxyType-enum)和请求类型是未加密的（也就是[ConnectionModeHttp](qhttp.html#ConnectionMode-enum)） ，[QHttp](qhttp.html)将把代理的缓存代理。

```
int QHttp.setSocket (self, QTcpSocket socket)
```

取代了内部[QTcpSocket](qtcpsocket.html)那[QHttp](qhttp.html)与使用_socket_。如果你想使用自己定制的，这非常有用[QTcpSocket](qtcpsocket.html)子类，而不是纯[QTcpSocket](qtcpsocket.html)那[QHttp](qhttp.html)默认情况下使用。[QHttp](qhttp.html)不采取插座的所有权，并不会删除_socket_销毁时。

该函数不会阻塞，而是立即返回。该请求被预定，并且是异步执行的执行。该函数返回一个唯一的标识符，它是由通过[requestStarted](qhttp.html#requestStarted)（）和[requestFinished](qhttp.html#requestFinished)（ ） 。

当该请求被启动[requestStarted](qhttp.html#requestStarted)（）信号被发射。当它完成时的[requestFinished](qhttp.html#requestFinished)（）信号被发射。

注意：如果[QHttp](qhttp.html)用于运行其自己的事件循环的非GUI线程，你必须移动_socket_该线程调用setSocket （）之前。

**See also** [QObject.moveToThread](qobject.html#moveToThread)（）和[Thread Support in Qt](index.htm)。

```
int QHttp.setUser (self, QString userName, QString password = QString())
```

这个函数设置的用户名_userName_和密码_password_对于需要身份验证的网页。

该函数不会阻塞，而是立即返回。该请求被预定，并且是异步执行的执行。该函数返回一个唯一的标识符，它是由通过[requestStarted](qhttp.html#requestStarted)（）和[requestFinished](qhttp.html#requestFinished)（ ） 。

当该请求被启动[requestStarted](qhttp.html#requestStarted)（）信号被发射。当它完成时的[requestFinished](qhttp.html#requestFinished)（）信号被发射。

```
State QHttp.state (self)
```

[](qhttp.html#State-enum)

[返回该对象的当前状态。当状态改变时，](qhttp.html#State-enum)[stateChanged](qhttp.html#stateChanged)（）信号被发射。

**See also** [State](qhttp.html#State-enum)和[stateChanged](qhttp.html#stateChanged)（ ） 。

* * *

## Qt Signal Documentation

```
void authenticationRequired (const QString&,quint16,QAuthenticator *)
```

这是该信号的默认超载。

这个信号可以在一个Web服务器发送给发射_hostname_和_port_需要验证。该_authenticator_对象可以被填充在与必需的细节，以便验证和持续的连接。

**Note:**这是不可能使用QueuedConnection连接到该信号，就好像所述认证没有被填充了新的信息时，该信号返回的连接失败。

此功能被引入Qt的4.3 。

**See also** [QAuthenticator](qauthenticator.html)和[QNetworkProxy](qnetworkproxy.html)。

```
void dataReadProgress (int,int)
```

这是该信号的默认超载。

当这个对象读取HTTP服务器的数据来表示的下载目前的进展，这个信号被发射。

_done_是数据的已经到来，而且量_total_是数据的总量。这是可能的，应该传输的数据的总量不能确定的，在这种情况_total_为0 （如果您连接到一个[QProgressBar](qprogressbar.html)，进度条显示一个繁忙的指标，如果总为0 ） 。

**Warning:** _done_和_total_不一定以字节为单位的大小，因为对于大文件的这些值可能需要被“缩放”，以避免溢出。

**See also** [dataSendProgress](qhttp.html#dataSendProgress)（ ）[get](qhttp.html#get)（ ）[post](qhttp.html#post)（ ）[request](qhttp.html#request)（）和[QProgressBar](qprogressbar.html)。

```
void dataSendProgress (int,int)
```

这是该信号的默认超载。

当这个对象将数据发送到一个HTTP服务器通知它的上传进度这个信号被发射。

_done_是数据的已经到来，而且量_total_是数据的总量。这是可能的，应该传输的数据的总量不能确定的，在这种情况_total_为0 （如果您连接到一个[QProgressBar](qprogressbar.html)，进度条显示一个繁忙的指标，如果总为0 ） 。

**Warning:** _done_和_total_不一定以字节为单位的大小，因为对于大文件的这些值可能需要被“缩放”，以避免溢出。

**See also** [dataReadProgress](qhttp.html#dataReadProgress)（ ）[post](qhttp.html#post)（ ）[request](qhttp.html#request)（）和[QProgressBar](qprogressbar.html)。

```
void done (bool)
```

这是该信号的默认超载。

这个信号被发射时的最后一个未决请求已经完成（这是后发出的最后一个请求的[requestFinished](qhttp.html#requestFinished)（ ）信号） 。_error_是真的，如果在处理过程中发生错误，否则_error_是假的。

**See also** [requestFinished](qhttp.html#requestFinished)（ ）[error](qhttp.html#error)（）和[errorString](qhttp.html#errorString)（ ） 。

```
void proxyAuthenticationRequired (const QNetworkProxy&,QAuthenticator *)
```

这是该信号的默认超载。

这个信号可以被发射时，一_proxy_需要进行身份验证时使用。该_authenticator_对象可以被填充在与必需的细节，以便验证和持续的连接。

**Note:**这是不可能使用QueuedConnection连接到该信号，就好像所述认证没有被填充了新的信息时，该信号返回的连接失败。

此功能被引入Qt的4.3 。

**See also** [QAuthenticator](qauthenticator.html)和[QNetworkProxy](qnetworkproxy.html)。

```
void readyRead (const QHttpResponseHeader&)
```

这是该信号的默认超载。

当有新的响应数据来读取该信号被发射。

如果在其中的数据应该被写入请求中指定的一个装置，然后该信号是_not_射出，而是将数据直接写入到设备。

响应头中传递_resp_。

您可以使用读取数据[readAll](qhttp.html#readAll)（）或[read](qhttp.html#read)（ ）函数

如果你想，只要它成为可用在处理大块数据这个信号是非常有用的。如果你只关心在完整的数据，只需连接到[requestFinished](qhttp.html#requestFinished)（ ）信号并读取数据，然后代替。

**See also** [get](qhttp.html#get)（ ）[post](qhttp.html#post)（ ）[request](qhttp.html#request)（ ）[readAll](qhttp.html#readAll)（ ）[read](qhttp.html#read)（）和[bytesAvailable](qhttp.html#bytesAvailable)（ ） 。

```
void requestFinished (int,bool)
```

这是该信号的默认超载。

处理所确定的请求时，这个信号被发射_id_已完成。_error_是真的，如果在处理过程中发生错误，否则_error_是假的。

**See also** [requestStarted](qhttp.html#requestStarted)（ ）[done](qhttp.html#done)（ ）[error](qhttp.html#error)（）和[errorString](qhttp.html#errorString)（ ） 。

```
void requestStarted (int)
```

这是该信号的默认超载。

处理所确定的请求时，这个信号被发射_id_开始。

**See also** [requestFinished](qhttp.html#requestFinished)（）和[done](qhttp.html#done)（ ） 。

```
void responseHeaderReceived (const QHttpResponseHeader&)
```

这是该信号的默认超载。

当服务器响应的HTTP标头可用这个信号被发射。报头中传递_resp_。

**See also** [get](qhttp.html#get)（ ）[post](qhttp.html#post)（ ）[head](qhttp.html#head)（ ）[request](qhttp.html#request)（）和[readyRead](qhttp.html#readyRead)（ ） 。

```
void sslErrors (const QList<QSslError>&)
```

这是该信号的默认超载。

转发sslErrors从信号[QSslSocket](qsslsocket.html)在使用[QHttp](qhttp.html)。_errors_是在SSL握手期间发生的错误的列表。除非你打电话[ignoreSslErrors](qhttp.html#ignoreSslErrors)从连接到在发生错误时该信号的时隙内的（） ，[QHttp](qhttp.html)发射的信号后，立即将断开连接。

此功能被引入Qt的4.3 。

**See also** [QSslSocket](qsslsocket.html)和[QSslSocket.ignoreSslErrors](qsslsocket.html#ignoreSslErrors)（ ） 。

```
void stateChanged (int)
```

这是该信号的默认超载。

这个信号被发射时的状态[QHttp](qhttp.html)对象更改。这个论点_state_是该连接的新的状态，它是一个[State](qhttp.html#State-enum)值。

当一个请求开始这通常发生，但是当服务器关闭连接或当调用它也可以发生[close](qhttp.html#close)（ ）成功了。

**See also** [get](qhttp.html#get)（ ）[post](qhttp.html#post)（ ）[head](qhttp.html#head)（ ）[request](qhttp.html#request)（ ）[close](qhttp.html#close)（ ）[state](qhttp.html#state)（）和[State](qhttp.html#State-enum)。