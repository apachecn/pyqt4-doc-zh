# QHttpMultiPart Class Reference

## [[QtNetwork](index.htm) module]

该QHttpMultiPart类类似于MIME多消息通过HTTP发送。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum ContentType { MixedType, RelatedType, FormDataType, AlternativeType }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `__init__ (self, ContentType contentType, QObject parent = None)`
*   `append (self, QHttpPart httpPart)`
*   `QByteArray boundary (self)`
*   `setBoundary (self, QByteArray boundary)`
*   `setContentType (self, ContentType contentType)`

* * *

## Detailed Description

该QHttpMultiPart类类似于MIME多消息通过HTTP发送。

该QHttpMultiPart类似于MIME多的消息，如RFC 2046 ，这是要通过HTTP发送的描述。多部分消息由身体各部位任意数量（见[QHttpPart](qhttppart.html)） ，这是由独特的边界隔开。该QHttpMultiPart的边界构造字符串“ boundary_.oOo 。[_](index.html)“后跟随机字符，并提供了足够的独特性，以确保它不会发生部件本身的内部。如果需要，该边界仍可以通过设置[setBoundary](qhttpmultipart.html#setBoundary)（ ） 。

作为一个例子，考虑下面的代码片断，它构造一个包含文本部分后跟一个图像部分多部分消息：

```
 QHttpMultiPart *multiPart = new QHttpMultiPart(QHttpMultiPart.FormDataType);

 [QHttpPart](qhttppart.html) textPart;
 textPart.setHeader([QNetworkRequest](qnetworkrequest.html).ContentDispositionHeader, [QVariant](qvariant.html)("form-data; name=\"text\""));
 textPart.setBody("my text");

 [QHttpPart](qhttppart.html) imagePart;
 imagePart.setHeader([QNetworkRequest](qnetworkrequest.html).ContentTypeHeader, [QVariant](qvariant.html)("image/jpeg"));
 imagePart.setHeader([QNetworkRequest](qnetworkrequest.html).ContentDispositionHeader, [QVariant](qvariant.html)("form-data; name=\"image\""));
 [QFile](qfile.html) *file = new [QFile](qfile.html)("image.jpg");
 file->open([QIODevice](qiodevice.html).ReadOnly);
 imagePart.setBodyDevice(file);
 file->setParent(multiPart); // we cannot delete the file now, so delete it with the multiPart

 multiPart->append(textPart);
 multiPart->append(imagePart);

 [QUrl](qurl.html) url("http://my.server.tld");
 [QNetworkRequest](qnetworkrequest.html) request(url);

 [QNetworkAccessManager](qnetworkaccessmanager.html) manager;
 [QNetworkReply](qnetworkreply.html) *reply = manager.post(request, multiPart);
 multiPart->setParent(reply); // delete the multiPart with the reply
 // here connect signals etc.

```

* * *

## Type Documentation

```
QHttpMultiPart.ContentType
```

在RFC 2046和其他人描述的已知内容类型的多部分子类型的列表。

| Constant | Value | Description |
| --- | --- | --- |
| `QHttpMultiPart.MixedType` | `0` | 对应于“多部分/混合”子类型，这意味着身体部分是彼此独立的，如RFC 2046中描述。 |
| `QHttpMultiPart.RelatedType` | `1` | 对应于“多部分/相关”子类型，这意味着，如RFC 2387中描述的主体部分彼此相关。 |
| `QHttpMultiPart.FormDataType` | `2` | 对应于“多部分/窗体的数据”子类型，这意味着身体部位含有表单元素，如RFC 2388中描述。 |
| `QHttpMultiPart.AlternativeType` | `3` | 对应于“ multipart / alternative的”子类型，这意味着身体部位是相同的信息替代表示，在RFC 2046中描述。 |

**See also** [setContentType](qhttpmultipart.html#setContentType)（ ） 。

* * *

## Method Documentation

```
QHttpMultiPart.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QHttpMultiPart](qhttpmultipart.html)与内容类型[MixedType](qhttpmultipart.html#ContentType-enum)和套_parent_作为父对象。

**See also** [QHttpMultiPart.ContentType](qhttpmultipart.html#ContentType-enum)。

```
QHttpMultiPart.__init__ (self, ContentType contentType, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QHttpMultiPart](qhttpmultipart.html)与内容类型_contentType_并设置父父对象。

**See also** [QHttpMultiPart.ContentType](qhttpmultipart.html#ContentType-enum)。

```
QHttpMultiPart.append (self, QHttpPart httpPart)
```

追加可_httpPart_这个多部分。

```
QByteArray QHttpMultiPart.boundary (self)
```

[

返回的边界。

](qbytearray.html)

[**See also**](qbytearray.html) [setBoundary](qhttpmultipart.html#setBoundary)（ ） 。

```
QHttpMultiPart.setBoundary (self, QByteArray boundary)
```

设置边界_boundary_。

通常情况下，你不需要自己生成一个边界，在建筑界开始以字符串“ boundary_.oOo 。[_](index.html)“其次是随机字符，并提供足够的独特性，以确保它不会发生的部位本身内。

**See also** [boundary](qhttpmultipart.html#boundary)（ ） 。

```
QHttpMultiPart.setContentType (self, ContentType contentType)
```

设置内容类型_contentType_。内容类型会在HTTP标头部分通过发送多部分消息时，可以使用[QNetworkAccessManager.post](qnetworkaccessmanager.html#post)（ ） 。如果你想使用不包含在一个多亚型[QHttpMultiPart.ContentType](qhttpmultipart.html#ContentType-enum)，您可以添加“的Content-Type ”头字段的[QNetworkRequest](qnetworkrequest.html)手，然后用申请，连同张贴的多部分消息。

**See also** [QHttpMultiPart.ContentType](qhttpmultipart.html#ContentType-enum)和[QNetworkAccessManager.post](qnetworkaccessmanager.html#post)（ ） 。