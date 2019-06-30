# QNetworkReply Class Reference

## [[QtNetwork](index.htm) module]

该QNetworkReply类包含数据和标头与发送请求[QNetworkAccessManager](qnetworkaccessmanager.html) [More...](#details)

继承[QIODevice](qiodevice.html)。

### Types

*   `enum NetworkError { NoError, ConnectionRefusedError, RemoteHostClosedError, HostNotFoundError, ..., TemporaryNetworkFailureError }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `abort (self)`
*   `QVariant attribute (self, QNetworkRequest.Attribute code)`
*   `close (self)`
*   `NetworkError error (self)`
*   `bool hasRawHeader (self, QByteArray headerName)`
*   `QVariant header (self, QNetworkRequest.KnownHeaders header)`
*   `ignoreSslErrors (self)`
*   `ignoreSslErrors (self, list-of-QSslError errors)`
*   `bool isFinished (self)`
*   `bool isRunning (self)`
*   `bool isSequential (self)`
*   `QNetworkAccessManager manager (self)`
*   `QNetworkAccessManager.Operation operation (self)`
*   `QByteArray rawHeader (self, QByteArray headerName)`
*   `list-of-QByteArray rawHeaderList (self)`
*   `list-of-tuple-of-QByteArray-QByteArray rawHeaderPairs (self)`
*   `int readBufferSize (self)`
*   `QNetworkRequest request (self)`
*   `setAttribute (self, QNetworkRequest.Attribute code, QVariant value)`
*   `setError (self, NetworkError errorCode, QString errorString)`
*   `setFinished (self, bool finished)`
*   `setHeader (self, QNetworkRequest.KnownHeaders header, QVariant value)`
*   `setOperation (self, QNetworkAccessManager.Operation operation)`
*   `setRawHeader (self, QByteArray headerName, QByteArray value)`
*   `setReadBufferSize (self, int size)`
*   `setRequest (self, QNetworkRequest request)`
*   `setSslConfiguration (self, QSslConfiguration configuration)`
*   `setUrl (self, QUrl url)`
*   `QSslConfiguration sslConfiguration (self)`
*   `QUrl url (self)`
*   `int writeData (self, str data)`

### Qt Signals

*   `void downloadProgress (qint64,qint64)`
*   `void error (QNetworkReply::NetworkError)`
*   `void finished ()`
*   `void metaDataChanged ()`
*   `void sslErrors (const QList&lt;QSslError&gt;&)`
*   `void uploadProgress (qint64,qint64)`

* * *

## Detailed Description

该QNetworkReply类包含数据和标头与发送请求[QNetworkAccessManager](qnetworkaccessmanager.html)

该QNetworkReply类包含与贴有一个请求中的数据和元数据[QNetworkAccessManager](qnetworkaccessmanager.html)。喜欢[QNetworkRequest](qnetworkrequest.html)，它包含一个URL和标题（无论是在解析和原始形式） ，对答复的状态和回复本身的内容的一些信息。

QNetworkReply是顺序存取[QIODevice](qiodevice.html)，这意味着，一旦数据从对象读取时，它不再保持通过该装置。因此，它是应用程序的责任，保持这个数据，如果需要。每当更多的数据是从网络接收和处理，则[readyRead](qiodevice.html#readyRead)（）信号被发射。

该[downloadProgress](qnetworkreply.html#downloadProgress)（）信号也被发射的数据的接收时，但包含在它的字节数可能并不代表实际收到的字节，如果有的话变换完成的内容（例如，解压缩并去除协议开销）。

尽管QNetworkReply是[QIODevice](qiodevice.html)连接到应答的内容，它也发射[uploadProgress](qnetworkreply.html#uploadProgress)（）信号，其指示上载于具有这样的内容的操作的进度。

**Note:**请不要删除该对象在连接到插槽[error](qnetworkreply.html#error)（）或[finished](qnetworkreply.html#finished)（）信号。使用[deleteLater](qobject.html#deleteLater)（ ） 。

* * *

## Type Documentation

```
QNetworkReply.NetworkError
```

指示请求的处理过程中找到的所有可能的错误条件。

| Constant | Value | Description |
| --- | --- | --- |
| `QNetworkReply.NoError` | `0` | 没有错误条件。**Note:**当HTTP协议返回一个重定向没有错误将被报告。您可以检查是否有与重定向[QNetworkRequest.RedirectionTargetAttribute](qnetworkrequest.html#Attribute-enum)属性。 |
| `QNetworkReply.ConnectionRefusedError` | `1` | 远程服务器拒绝连接（服务器不接受请求） |
| `QNetworkReply.RemoteHostClosedError` | `2` | 远程服务器关闭了连接过早，整个答复接收和处理前 |
| `QNetworkReply.HostNotFoundError` | `3` | 远程主机名未找到（无效主机名） |
| `QNetworkReply.TimeoutError` | `4` | 连接到远程服务器超时 |
| `QNetworkReply.OperationCanceledError` | `5` | 该操作是通过调用取消[abort](qnetworkreply.html#abort)（）或[close](qnetworkreply.html#close)（ ），它被完成之前。 |
| `QNetworkReply.SslHandshakeFailedError` | `6` | 在SSL / TLS握手失败，加密的通道不能成立。该[sslErrors](qnetworkreply.html#sslErrors)（）信号应该被发射。 |
| `QNetworkReply.TemporaryNetworkFailureError` | `7` | 该连接由于从网络断开断裂，但是在系统启动漫游到另一个接入点。该请求应该被重新提交，并会尽快连接重新建立处理。 |
| `QNetworkReply.ProxyConnectionRefusedError` | `101` | 连接到代理服务器被拒绝（代理服务器不接受请求） |
| `QNetworkReply.ProxyConnectionClosedError` | `102` | 代理服务器关闭了连接过早，整个答复接收和处理前 |
| `QNetworkReply.ProxyNotFoundError` | `103` | 代理主机名没有被发现（无效的代理主机名） |
| `QNetworkReply.ProxyTimeoutError` | `104` | 连接到代理服务器超时或代理没有及时发送请求回复 |
| `QNetworkReply.ProxyAuthenticationRequiredError` | `105` | 代理需要身份验证才能兑现的要求，但没有接受其提供的任何凭证（如有） |
| `QNetworkReply.ContentAccessDenied` | `201` | 在访问远程内容被拒绝（类似于HTTP错误401 ） |
| `QNetworkReply.ContentOperationNotPermittedError` | `202` | 要求对远程内容的操作是不允许的 |
| `QNetworkReply.ContentNotFoundError` | `203` | 远程内容并没有在服务器上找到（类似于HTTP错误404 ） |
| `QNetworkReply.AuthenticationRequiredError` | `204` | 远程服务器要求身份验证服务的内容，但提供的凭据不被接受（如果有的话） |
| `QNetworkReply.ContentReSendError` | `205` | 请求需要再次发送，但这种失败的例子，因为上传的数据无法读取第二次。 |
| `QNetworkReply.ProtocolUnknownError` | `301` | 网络访问API无法兑现的请求，因为该协议是不为人所知的 |
| `QNetworkReply.ProtocolInvalidOperationError` | `302` | 所请求的操作是此协议无效 |
| `QNetworkReply.UnknownNetworkError` | `99` | 检测到一个未知的网络有关的错误 |
| `QNetworkReply.UnknownProxyError` | `199` | 检测到一个未知的代理相关的错误 |
| `QNetworkReply.UnknownContentError` | `299` | 检测到一个未知错误相关的远程内容 |
| `QNetworkReply.ProtocolFailure` | `399` | 检测在协议的故障（解析错误，无效的或意外的反应，等等） |

**See also** [error](qnetworkreply.html#error)（ ） 。

* * *

## Method Documentation

```
QNetworkReply.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建[QNetworkReply](qnetworkreply.html)与父对象_parent_。

你不能直接实例化[QNetworkReply](qnetworkreply.html)对象。使用[QNetworkAccessManager](qnetworkaccessmanager.html)函数来做到这一点。

```
QNetworkReply.abort (self)
```

这种方法是抽象的，应在任何子类中重新实现。

立即中止操作，并关闭所有的网络连接仍然处于打开状态。上传仍在进行中，也中止。

**See also** [close](qnetworkreply.html#close)（ ） 。

```
QVariant QNetworkReply.attribute (self, QNetworkRequest.Attribute code)
```

```
QNetworkReply.close (self)
```

从重新实现[QIODevice.close](qiodevice.html#close)（ ） 。

关闭此设备以供读取。未读取的数据将被丢弃，但是网络资源不被丢弃，直到它们被完成。特别是，如果任何的上传过程中，它会继续，直到它完成。

该[finished](qnetworkreply.html#finished)当所有的操作都​​在和网络资源被释放（ ）信号被发射。

**See also** [abort](qnetworkreply.html#abort)（）和[finished](qnetworkreply.html#finished)（ ） 。

```
NetworkError QNetworkReply.error (self)
```

[](qnetworkreply.html#NetworkError-enum)

[返回该请求的处理过程中发现错误。如果没有发现错误，返回](qnetworkreply.html#NetworkError-enum)[NoError](qnetworkreply.html#NetworkError-enum)。

**See also** [setError](qnetworkreply.html#setError)（ ） 。

```
bool QNetworkReply.hasRawHeader (self, QByteArray headerName)
```

返回True如果name原始标题_headerName_被送往由远程服务器

**See also** [rawHeader](qnetworkreply.html#rawHeader)（ ） 。

```
QVariant QNetworkReply.header (self, QNetworkRequest.KnownHeaders header)
```

返回已知的标头的值_header_，如果这头被送往由远程服务器。如果头没有被发送，返回无效[QVariant](qvariant.html)。

**See also** [rawHeader](qnetworkreply.html#rawHeader)（ ）[setHeader](qnetworkreply.html#setHeader)（）和[QNetworkRequest.header](qnetworkrequest.html#header)（ ） 。

```
QNetworkReply.ignoreSslErrors (self)
```

这种方法也是一个Qt槽与C + +的签名`void ignoreSslErrors()`。

如果这个函数被调用，涉及到网络连接的SSL错误将被忽略，包括证书验证错误。

**Warning:**一定要始终让用户检查报告的错误[sslErrors](qnetworkreply.html#sslErrors)（ ）信号，并且只从用户的程序是确定经确认后，调用此方法。如果有意外的错误，得到的答复应中止。不检查实际的错误调用此方法将最有可能带来安全风险的应用程序。使用它以极大的关怀！

这个函数可以从连接到插槽被称为[sslErrors](qnetworkreply.html#sslErrors)（）信号，这表明它被发现的错误。

**See also** [sslConfiguration](qnetworkreply.html#sslConfiguration)（ ）[sslErrors](qnetworkreply.html#sslErrors)（）和[QSslSocket.ignoreSslErrors](qsslsocket.html#ignoreSslErrors)（ ） 。

```
QNetworkReply.ignoreSslErrors (self, list-of-QSslError errors)
```

这是一个重载函数。

如果这个函数被调用时，在给定的SSL错误_errors_将被忽略。

请注意，您可以在SSL错误设定预期的证书：如果，例如，你想发出一个请求到使用自签名证书的服务器时，请考虑下面的代码片断：

```
 [QList](index.htm)<[QSslCertificate](qsslcertificate.html)> cert = [QSslCertificate](qsslcertificate.html).fromPath(QLatin1String("server-certificate.pem"));
 [QSslError](qsslerror.html) error([QSslError](qsslerror.html).SelfSignedCertificate, cert.at(0));
 [QList](index.htm)<[QSslError](qsslerror.html)> expectedSslErrors;
 expectedSslErrors.append(error);

 [QNetworkReply](qnetworkreply.html) *reply = manager.get([QNetworkRequest](qnetworkrequest.html)([QUrl](qurl.html)("https://server.tld/index.html")));
 reply->ignoreSslErrors(expectedSslErrors);
 // here connect signals etc.

```

多次调用该函数会被替换传入以前调用的错误列表。您可以清除通过调用这个函数以一个空列表，你要忽略错误的列表。

此功能被引入Qt的4.6 。

**See also** [sslConfiguration](qnetworkreply.html#sslConfiguration)（ ）[sslErrors](qnetworkreply.html#sslErrors)（）和[QSslSocket.ignoreSslErrors](qsslsocket.html#ignoreSslErrors)（ ） 。

```
bool QNetworkReply.isFinished (self)
```

返回True时，答复已完成或已中止。

此功能被引入Qt的4.6 。

**See also** [isRunning](qnetworkreply.html#isRunning)（ ） 。

```
bool QNetworkReply.isRunning (self)
```

返回True时，该请求仍在处理并答复未能完成或已中止呢。

此功能被引入Qt的4.6 。

**See also** [isFinished](qnetworkreply.html#isFinished)（ ） 。

```
bool QNetworkReply.isSequential (self)
```

```
QNetworkAccessManager QNetworkReply.manager (self)
```

[](qnetworkaccessmanager.html)

[返回](qnetworkaccessmanager.html)[QNetworkAccessManager](qnetworkaccessmanager.html)这是用于创建此[QNetworkReply](qnetworkreply.html)对象。起初，它也是父对象。

```
QNetworkAccessManager.Operation QNetworkReply.operation (self)
```

[

返回被张贴该回复操作。

](qnetworkaccessmanager.html#Operation-enum)

[**See also**](qnetworkaccessmanager.html#Operation-enum) [setOperation](qnetworkreply.html#setOperation)（ ） 。

```
QByteArray QNetworkReply.rawHeader (self, QByteArray headerName)
```

[](qbytearray.html)

[返回头的原始内容_headerName_由远程服务器发送。如果没有这样的标题，则返回一个空字节数组，这可能是从一个空的头没有区别。使用](qbytearray.html)[hasRawHeader](qnetworkreply.html#hasRawHeader)（）来验证，如果服务器发送这样的头字段。

**See also** [setRawHeader](qnetworkreply.html#setRawHeader)（ ）[hasRawHeader](qnetworkreply.html#hasRawHeader)（）和[header](qnetworkreply.html#header)（ ） 。

```
list-of-QByteArray QNetworkReply.rawHeaderList (self)
```

返回由远程服务器发送的，因为它们被发送的顺序头字段的列表。重复的头被合并在一起并发生后重复的。

```
list-of-tuple-of-QByteArray-QByteArray QNetworkReply.rawHeaderPairs (self)
```

返回原头对的列表。

```
int QNetworkReply.readBufferSize (self)
```

返回读缓冲区的大小，以字节为单位。

**See also** [setReadBufferSize](qnetworkreply.html#setReadBufferSize)（ ） 。

```
QNetworkRequest QNetworkReply.request (self)
```

[

返回被张贴于本答复的请求。在特殊的，注意的URL请求可以是比该答复的不同。

](qnetworkrequest.html)

[**See also**](qnetworkrequest.html) [QNetworkRequest.url](qnetworkrequest.html#url)（ ）[url](qnetworkreply.html#url)（）和[setRequest](qnetworkreply.html#setRequest)（ ） 。

```
QNetworkReply.setAttribute (self, QNetworkRequest.Attribute code, QVariant value)
```

设置属性_code_有值_value_。如果_code_以前设置，它会被复盖。如果_value_是无效的[QVariant](qvariant.html)，该属性将取消。

**See also** [attribute](qnetworkreply.html#attributex)（）和[QNetworkRequest.setAttribute](qnetworkrequest.html#setAttribute)（ ） 。

```
QNetworkReply.setError (self, NetworkError errorCode, QString errorString)
```

设置错误条件是_errorCode_。人类可读的消息设置_errorString_。

调用SETERROR （ ）不会发出错误（[QNetworkReply.NetworkError](qnetworkreply.html#NetworkError-enum)）信号。

**See also** [error](qnetworkreply.html#error)（）和[errorString](qiodevice.html#errorString)（ ） 。

```
QNetworkReply.setFinished (self, bool finished)
```

设置答复_finished_。

有在此之后设置回复的数据不能改变。

此功能被引入Qt的4.8 。

**See also** [finished](qnetworkreply.html#finished)（）和[isFinished](qnetworkreply.html#isFinished)（ ） 。

```
QNetworkReply.setHeader (self, QNetworkRequest.KnownHeaders header, QVariant value)
```

设置已知的头_header_有利用价值_value_。标题的相应的原始表格将被设置为好。

**See also** [header](qnetworkreply.html#header)（ ）[setRawHeader](qnetworkreply.html#setRawHeader)（）和[QNetworkRequest.setHeader](qnetworkrequest.html#setHeader)（ ） 。

```
QNetworkReply.setOperation (self, QNetworkAccessManager.Operation operation)
```

设置为是此对象的相关操作_operation_。这个值将被退回[operation](qnetworkreply.html#operation)（ ） 。

注：在创建这个对象，而不是再次改变时，操作应设置。

**See also** [operation](qnetworkreply.html#operation)（）和[setRequest](qnetworkreply.html#setRequest)（ ） 。

```
QNetworkReply.setRawHeader (self, QByteArray headerName, QByteArray value)
```

设置原始标题_headerName_有利用价值_value_。如果_headerName_以前设置，它将被重写。具有相同名称的多个HTTP头在功能上等同于串联的值，用逗号分隔的一个单头。

If _headerName_匹配一个已知的头，值_value_将被解析和相应的解析形式也将被设置。

**See also** [rawHeader](qnetworkreply.html#rawHeader)（ ）[header](qnetworkreply.html#header)（ ）[setHeader](qnetworkreply.html#setHeader)（）和[QNetworkRequest.setRawHeader](qnetworkrequest.html#setRawHeader)（ ） 。

```
QNetworkReply.setReadBufferSize (self, int size)
```

设置读缓冲要的大小_size_字节。读缓冲区存放的数据正在被下载的断网，然后才读缓冲区[QIODevice.read](qiodevice.html#read)（ ） 。设置缓冲区大小为0，将使缓冲区无限的大小。

[QNetworkReply](qnetworkreply.html)会试图阻止从网络读取一次该缓冲区已满（即，[bytesAvailable](qiodevice.html#bytesAvailable)（）返回_size_或更多） ，从而导致下载到踩下油门为好。如果缓冲区不局限于在大小，[QNetworkReply](qnetworkreply.html)会尝试从网络中尽可能快地下载。

不像[QAbstractSocket.setReadBufferSize](qabstractsocket.html#setReadBufferSize)（ ）[QNetworkReply](qnetworkreply.html)不能在读取缓冲区大小保证精度。即，[bytesAvailable](qiodevice.html#bytesAvailable)（ ）可以返回多个_size_。

**See also** [readBufferSize](qnetworkreply.html#readBufferSize)（ ） 。

```
QNetworkReply.setRequest (self, QNetworkRequest request)
```

设置相关的请求此对象是_request_。这个值将被退回[request](qnetworkreply.html#request)（ ） 。

注：在创建这个对象，而不是再次改变时，该请求应该被设置。

**See also** [request](qnetworkreply.html#request)（）和[setOperation](qnetworkreply.html#setOperation)（ ） 。

```
QNetworkReply.setSslConfiguration (self, QSslConfiguration configuration)
```

设置与此请求关联的网络连接的SSL配置，如果可能的话，是说的_config_。

**See also** [sslConfiguration](qnetworkreply.html#sslConfiguration)（ ） 。

```
QNetworkReply.setUrl (self, QUrl url)
```

设置被加工成的网址_url_。通常，该URL匹配被张贴的请求，但对各种原因也可以是不同的（例如，被制成一个文件路径的绝对或规范） 。

**See also** [url](qnetworkreply.html#url)（ ）[request](qnetworkreply.html#request)（）和[QNetworkRequest.url](qnetworkrequest.html#url)（ ） 。

```
QSslConfiguration QNetworkReply.sslConfiguration (self)
```

[

返回与此相关的答复，如果已使用SSL SSL配置和状态。它将包含远程服务器的证书，其证书链导致的证书颁发机构，以及在使用中的加密密码。

](qsslconfiguration.html)

[同行的证书，其证书链会的时候被称为](qsslconfiguration.html)[sslErrors](qnetworkreply.html#sslErrors)（）被发射，如果它的发射。

**See also** [setSslConfiguration](qnetworkreply.html#setSslConfiguration)（ ） 。

```
QUrl QNetworkReply.url (self)
```

[

返回下载或上传的内容的URL 。注意，这个URL可以是从原始请求的不同。

](qurl.html)

[**See also**](qurl.html) [request](qnetworkreply.html#request)（ ）[setUrl](qnetworkreply.html#setUrl)（）和[QNetworkRequest.url](qnetworkrequest.html#url)（ ） 。

```
int QNetworkReply.writeData (self, str data)
```

* * *

## Qt Signal Documentation

```
void downloadProgress (qint64,qint64)
```

这是该信号的默认超载。

这个信号被发射，以指示该网络请求的下载部分的进展，如果有任何。如果没有与此请求关联的下载，这个信号将被一次使用0作为发射两者的值_bytesReceived_和_bytesTotal_。

该_bytesReceived_参数表示接收的字节数，而_bytesTotal_表示预期要被下载的总字节数。如果不知道要被下载的字节数，_bytesTotal_将为-1 。

下载完成时_bytesReceived_等于_bytesTotal_。在那个时候，_bytesTotal_不会是-1。

注意，这两个值_bytesReceived_和_bytesTotal_可以从不同的[size](qiodevice.html#size)（ ） ，获得通过的总字节数[read](qiodevice.html#read)（）或[readAll](qiodevice.html#readAll)（） ，或标头（ ContentLengthHeader ）的值。其理由是，有可能是协议开销或数据可能在下载过程中被压缩。

**See also** [uploadProgress](qnetworkreply.html#uploadProgress)（）和[bytesAvailable](qiodevice.html#bytesAvailable)（ ） 。

```
void error (QNetworkReply::NetworkError)
```

这是该信号的默认超载。

当答复检测处理错误这个信号被发射。该[finished](qnetworkreply.html#finished)（）信号可能会遵循，这表明连接已经结束。

该_code_参数包含检测到的错误代码。通话[errorString](qiodevice.html#errorString)（ ）取得的错误条件的文本表示。

**Note:**不要删除对象连接到这个信号的插槽。使用[deleteLater](qobject.html#deleteLater)（ ） 。

**See also** [error](qnetworkreply.html#error)（）和[errorString](qiodevice.html#errorString)（ ） 。

```
void finished ()
```

这是该信号的默认超载。

当回复已完成处理这个信号被发射。之后此信号被发射，将没有更多的更新到应答的数据或元数据。

除非[close](qnetworkreply.html#close)（ ）被调用时，答复将仍然打开进行读取，所以数据可以通过调用来检索[read](qiodevice.html#read)（）或[readAll](qiodevice.html#readAll)（ ） 。特别是，如果没有调用[read](qiodevice.html#read)（）被提了出来的结果[readyRead](qiodevice.html#readyRead)（ ） ，调用[readAll](qiodevice.html#readAll)（ ）将获取的全部内容[QByteArray](qbytearray.html)。

这个信号在配合发出[QNetworkAccessManager.finished](qnetworkaccessmanager.html#finished)（ ）该信号的答复参数是这个对象。

**Note:**不要删除对象连接到这个信号的插槽。使用[deleteLater](qobject.html#deleteLater)（ ） 。

您也可以使用[isFinished](qnetworkreply.html#isFinished)（）来检查一个[QNetworkReply](qnetworkreply.html)您收到成品（ ）信号前完成均匀。

**See also** [setFinished](qnetworkreply.html#setFinished)（ ）[QNetworkAccessManager.finished](qnetworkaccessmanager.html#finished)（）和[isFinished](qnetworkreply.html#isFinished)（ ） 。

```
void metaDataChanged ()
```

这是该信号的默认超载。

这个信号被发射时在此回复的元数据更改。元数据是不是内容（数据）本身，包括网络报头的任何信息。在大多数情况下，元数据将完全由被接收数据的第一个字节时已知的。然而，能够将数据的处理过程中接收标题或其他元数据的更新。

**See also** [header](qnetworkreply.html#header)（ ）[rawHeaderList](qnetworkreply.html#rawHeaderList)（ ）[rawHeader](qnetworkreply.html#rawHeader)（）和[hasRawHeader](qnetworkreply.html#hasRawHeader)（ ） 。

```
void sslErrors (const QList<QSslError>&)
```

这是该信号的默认超载。

这个信号被发射，如果SSL / TLS会话期间，成立了包括证书验证错误，遇到错误。该_errors_参数包含错误的列表。

为了表明这些错误不是致命的，而连接应进行，[ignoreSslErrors](qnetworkreply.html#ignoreSslErrors)（）函数应该被称为从连接到该信号的时隙。如果它不叫， SSL会话将被推倒的任何数据交换（包括URL）之前。

这个信号可以被用来显示一个错误消息，指示安全性可能会受到影响的用户，并显示在SSL设置（见[sslConfiguration](qnetworkreply.html#sslConfiguration)（）来获取它） 。如果用户决定继续进行远程证明分析后，槽应调用[ignoreSslErrors](qnetworkreply.html#ignoreSslErrors)（ ） 。

**See also** [QSslSocket.sslErrors](qsslsocket.html#sslErrors)（ ）[QNetworkAccessManager.sslErrors](qnetworkaccessmanager.html#sslErrors)（ ）[sslConfiguration](qnetworkreply.html#sslConfiguration)（）和[ignoreSslErrors](qnetworkreply.html#ignoreSslErrors)（ ） 。

```
void uploadProgress (qint64,qint64)
```

这是该信号的默认超载。

这个信号被发射，以指示该网络请求的载部分的进展，如果有任何。如果没有与该请求相关联的上载，该信号将不会被发射。

该_bytesSent_参数表示上传的字节数，而_bytesTotal_指示要被上传的总字节数。如果不能确定要上载的字节数，_bytesTotal_将为-1 。

上传完成后，当_bytesSent_等于_bytesTotal_。在那个时候，_bytesTotal_不会是-1。

**See also** [downloadProgress](qnetworkreply.html#downloadProgress)（ ） 。