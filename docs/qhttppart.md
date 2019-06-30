# QHttpPart Class Reference

## [[QtNetwork](index.htm) module]

该QHttpPart类包含一个身体的一部分被里面一个HTTP多部分MIME消息中使用。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QHttpPart other)`
*   `setBody (self, QByteArray body)`
*   `setBodyDevice (self, QIODevice device)`
*   `setHeader (self, QNetworkRequest.KnownHeaders header, QVariant value)`
*   `setRawHeader (self, QByteArray headerName, QByteArray headerValue)`

### Special Methods

*   `bool __eq__ (self, QHttpPart other)`
*   `bool __ne__ (self, QHttpPart other)`

* * *

## Detailed Description

该QHttpPart类包含一个身体的一部分被里面一个HTTP多部分MIME消息中使用。

该QHttpPart类持有被里面一个HTTP多部分MIME消息中使用身体的一部分（这是由代表[QHttpMultiPart](qhttpmultipart.html)类）。一个QHttpPart由一个头块和数据块，这是由彼此分开由两个连续的新行。为一个部分的一个例子是：

```
 Content-Type: text/plain
 Content-Disposition: form-data; name="text"

 here goes the body

```

设置页眉，使用[setHeader](qhttppart.html#setHeader)（）和[setRawHeader](qhttppart.html#setRawHeader)（），它的行为完全一样[QNetworkRequest.setHeader](qnetworkrequest.html#setHeader)（）和[QNetworkRequest.setRawHeader](qnetworkrequest.html#setRawHeader)（ ） 。

读取小块数据，使用[setBody](qhttppart.html#setBody)（）;对于像例如更大的数据块图像，使用[setBodyDevice](qhttppart.html#setBodyDevice)（ ） 。后一种方法通过不复制数据在内部，而是直接从设备读取节省内存。这意味着该设备必须打开，并在读取时，含有人体部分的多部分消息是通过发送网络上的那一刻[QNetworkAccessManager.post](qnetworkaccessmanager.html#post)（ ） 。

要构造一个小的身体QHttpPart ，考虑下面的代码片断（这将产生在上面的例子中显示的数据） ：

```
 QHttpPart textPart;
 textPart.setHeader([QNetworkRequest](qnetworkrequest.html).ContentTypeHeader, [QVariant](qvariant.html)("text/plain"));
 textPart.setHeader([QNetworkRequest](qnetworkrequest.html).ContentDispositionHeader, [QVariant](qvariant.html)("form-data; name=\"text\""));
 textPart.setBody("here goes the body");

```

构建一个QHttpPart从设备（例如文件）读取，下面可以应用：

```
 QHttpPart imagePart;
 imagePart.setHeader([QNetworkRequest](qnetworkrequest.html).ContentTypeHeader, [QVariant](qvariant.html)("image/jpeg"));
 imagePart.setHeader([QNetworkRequest](qnetworkrequest.html).ContentDispositionHeader, [QVariant](qvariant.html)("form-data; name=\"image\""));
 imagePart.setRawHeader("Content-ID", "my@content.id"); // add any headers you like via setRawHeader()
 [QFile](qfile.html) *file = new [QFile](qfile.html)("image.jpg");
 file->open([QIODevice](qiodevice.html).ReadOnly);
 imagePart.setBodyDevice(file);

```

请注意， QHttpPart不走设备的所有权时设置，所以它是开发人员的责任消灭它时，它不再需要。一个好的想法可能是设置多部分消息，作为该设备的父对象，如记录在该文件[QHttpMultiPart](qhttpmultipart.html)。

* * *

## Method Documentation

```
QHttpPart.__init__ (self)
```

构造一个空[QHttpPart](qhttppart.html)对象。

```
QHttpPart.__init__ (self, QHttpPart other)
```

创建副本_other_。

```
QHttpPart.setBody (self, QByteArray body)
```

设置此MIME部分的正文_body_。该机构设置用这种方法将被使用，除非该设备是通过设置[setBodyDevice](qhttppart.html#setBodyDevice)（ ） 。对于大量的数据（例如图像） ，利用[setBodyDevice](qhttppart.html#setBodyDevice)（），它不会在内部复制数据。

**See also** [setBodyDevice](qhttppart.html#setBodyDevice)（ ） 。

```
QHttpPart.setBodyDevice (self, QIODevice device)
```

设置设备从阅读的内容_device_。对于大量的数据，该方法应优先于[setBody](qhttppart.html#setBody)（），因为使用这种方法，当内容不被复制，而是直接从设备读取。_device_必须是开放性和可读性。[QHttpPart](qhttppart.html)不采取所有权_device_，即该设备必须被关闭，并且，如果必要的破坏。如果_device_是连续的（如插座，但不是文件） ，[QNetworkAccessManager.post](qnetworkaccessmanager.html#post)（ ）后，应该调用_device_已发出的成品（ ） 。为你重置设备，并通过使用数据集[setBody](qhttppart.html#setBody)（ ）时，使用“ setBodyDevice （0）” 。

**See also** [setBody](qhttppart.html#setBody)（）和[QNetworkAccessManager.post](qnetworkaccessmanager.html#post)（ ） 。

```
QHttpPart.setHeader (self, QNetworkRequest.KnownHeaders header, QVariant value)
```

设置了已知头的值_header_要_value_，复盖任何先前设置的标头。

**See also** [QNetworkRequest.KnownHeaders](qnetworkrequest.html#KnownHeaders-enum)，[setRawHeader](qhttppart.html#setRawHeader)（）和[QNetworkRequest.setHeader](qnetworkrequest.html#setHeader)（ ） 。

```
QHttpPart.setRawHeader (self, QByteArray headerName, QByteArray headerValue)
```

设置页眉_headerName_有利用价值_headerValue_。如果_headerName_对应于一个已知的报头（参见[QNetworkRequest.KnownHeaders](qnetworkrequest.html#KnownHeaders-enum)） ， raw格式将被解析和相应的“熟”头将被设置为好。

注意：在设置相同的头两次将复盖以前的设置。为了实现多个同名的HTTP头的行为，你应该将两者连接起来的值，用逗号将它们隔开（ “，” ），并设置一个单一的原始标题。

**See also** [QNetworkRequest.KnownHeaders](qnetworkrequest.html#KnownHeaders-enum)，[setHeader](qhttppart.html#setHeader)（）和[QNetworkRequest.setRawHeader](qnetworkrequest.html#setRawHeader)（ ） 。

```
bool QHttpPart.__eq__ (self, QHttpPart other)
```

```
bool QHttpPart.__ne__ (self, QHttpPart other)
```