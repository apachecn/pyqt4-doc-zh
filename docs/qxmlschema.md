# QXmlSchema Class Reference

## [[QtXmlPatterns](index.htm) module]

该QXmlSchema类提供了一个W3C XML模式的加载和验证。[More...](#details)

### Methods

*   `__init__ (self)`
*   `QUrl documentUri (self)`
*   `bool isValid (self)`
*   `bool load (self, QUrl source)`
*   `bool load (self, QIODevice source, QUrl documentUri = QUrl())`
*   `bool load (self, QByteArray data, QUrl documentUri = QUrl())`
*   `QAbstractMessageHandler messageHandler (self)`
*   `QXmlNamePool namePool (self)`
*   `QNetworkAccessManager networkAccessManager (self)`
*   `setMessageHandler (self, QAbstractMessageHandler handler)`
*   `setNetworkAccessManager (self, QNetworkAccessManager networkmanager)`
*   `setUriResolver (self, QAbstractUriResolver resolver)`
*   `QAbstractUriResolver uriResolver (self)`

* * *

## Detailed Description

该QXmlSchema类提供了一个W3C XML模式的加载和验证。

该QXmlSchema类加载，编译和验证，可以进一步通过用于XML实例文档验证的W3C XML Schema文件[QXmlSchemaValidator](qxmlschemavalidator.html)。

下面的示例演示如何从网络加载一个XML Schema文件，并测试它是否是一个有效的架构文档：

```
     [QUrl](qurl.html) url("http://www.schema-example.org/myschema.xsd");

     QXmlSchema schema;
     if (schema.load(url) == true)
         qDebug() << "schema is valid";
     else
         qDebug() << "schema is invalid";

```

### XML Schema Version

这个类是用来表示符合的模式[XML Schema](http://www.w3.org/XML/Schema)1.0规范。

* * *

## Method Documentation

```
QXmlSchema.__init__ (self)
```

构造不能使用，直到无效，空架构[load](qxmlschema.html#load)（）被调用。

```
QUrl QXmlSchema.documentUri (self)
```

[

返回架构的文档URI或空的URI ，如果没有模式已定。

```
bool QXmlSchema.isValid (self)
```

返回True如果这个模式是有效的。失效模式的例子是那些包含语法错误或不符合W3C的XML Schema规范。

```
bool QXmlSchema.load (self, QUrl source)
```

](qurl.html)

[此套](qurl.html)[QXmlSchema](qxmlschema.html)以从加载的模式_source_URI。

如果架构[is invalid](qxmlschema.html#isValid)，`false`返回和行为是未定义的。

例如：

```
     [QUrl](qurl.html) url("http://www.schema-example.org/myschema.xsd");

     [QXmlSchema](qxmlschema.html) schema;
     if (schema.load(url) == true)
         qDebug() << "schema is valid";
     else
         qDebug() << "schema is invalid";

```

**See also** [isValid](qxmlschema.html#isValid)（ ） 。

```
bool QXmlSchema.load (self, QIODevice source, QUrl documentUri = QUrl())
```

此套[QXmlSchema](qxmlschema.html)从读取架构_source_设备。该设备必须已经打开了至少[QIODevice.ReadOnly](qiodevice.html#OpenModeFlag-enum)。

_documentUri_表示从所获得的模式_source_设备。它是架构的基础URI，它在内部使用，以解决出现在架构相对URI ，以及消息的报告。

If _source_ is `null`或无法读取，或者如果_documentUri_是不是一个有效的URI ，行为是未定义的。

如果架构[is invalid](qxmlschema.html#isValid)，`false`返回和行为是未定义的。

例如：

```
     [QFile](qfile.html) file("myschema.xsd");
     file.open([QIODevice](qiodevice.html).ReadOnly);

     [QXmlSchema](qxmlschema.html) schema;
     schema.load(&file, [QUrl](qurl.html).fromLocalFile(file.fileName()));

     if (schema.isValid())
         qDebug() << "schema is valid";
     else
         qDebug() << "schema is invalid";

```

**See also** [isValid](qxmlschema.html#isValid)（ ） 。

```
bool QXmlSchema.load (self, QByteArray data, QUrl documentUri = QUrl())
```

此套[QXmlSchema](qxmlschema.html)从读取架构_data_

_documentUri_表示从所获得的模式_data_。它是架构的基础URI，它在内部使用，以解决出现在架构相对URI ，以及消息的报告。

If _documentUri_是不是一个有效的URI ，行为是未定义的。

如果架构[is invalid](qxmlschema.html#isValid)，`false`返回和行为是未定义的。

例如：

```
     [QByteArray](qbytearray.html) data( "<?xml version=\"1.0\" encoding=\"UTF-8\"?>"
                      "<xsd:schema"
                      "        xmlns:xsd=\"http://www.w3.org/2001/XMLSchema\""
                      "        xmlns=\"http://qt.nokia.com/xmlschematest\""
                      "        targetNamespace=\"http://qt.nokia.com/xmlschematest\""
                      "        version=\"1.0\""
                      "        elementFormDefault=\"qualified\">"
                      "</xsd:schema>" );

     [QXmlSchema](qxmlschema.html) schema;
     schema.load(data);

     if (schema.isValid())
         qDebug() << "schema is valid";
     else
         qDebug() << "schema is invalid";

```

**See also** [isValid](qxmlschema.html#isValid)（）和[isValid](qxmlschema.html#isValid)（ ） 。

```
QAbstractMessageHandler QXmlSchema.messageHandler (self)
```

[](qabstractmessagehandler.html)

[返回处理这个编译和验证消息的消息处理程序](qabstractmessagehandler.html)[QXmlSchema](qxmlschema.html)。

**See also** [setMessageHandler](qxmlschema.html#setMessageHandler)（ ） 。

```
QXmlNamePool QXmlSchema.namePool (self)
```

[](qxmlnamepool.html)

[返回此名称池](qxmlnamepool.html)[QXmlSchema](qxmlschema.html)构建[names](qxmlname.html)。有没有setter的名字池，因为混合池的名称会导致错误，由于名称的混乱。

```
QNetworkAccessManager QXmlSchema.networkAccessManager (self)
```

[

返回该网络管理器，或0 ，如果它没有被设置。

](qnetworkaccessmanager.html)

[**See also**](qnetworkaccessmanager.html) [setNetworkAccessManager](qxmlschema.html#setNetworkAccessManager)（ ） 。

```
QXmlSchema.setMessageHandler (self, QAbstractMessageHandler handler)
```

更改[message handler](qabstractmessagehandler.html)这[QXmlSchema](qxmlschema.html)至_handler_。该架构将所有的编译和验证消息，此消息处理程序。[QXmlSchema](qxmlschema.html)不采取所有权_handler_。

通常情况下，默认的消息处理就足够了。它写的编译和验证消息的_stderr_。默认的消息处理程序，包括颜色代码，如果_stderr_可以使色彩。

When [QXmlSchema](qxmlschema.html)电话[QAbstractMessageHandler.message](qabstractmessagehandler.html#message)（ ） ，参数如下：

| message() argument | Semantics |
| --- | --- |
| [QtMsgType](index.htm#QtMsgType-enum) type | Only [QtWarningMsg](index.htm#QtMsgType-enum) and [QtFatalMsg](index.htm#QtMsgType-enum) are used. The former identifies a warning, while the latter identifies an error. |
| const [QString](qstring.html) & description | An XHTML document which is the actual message. It is translated into the current language. |
| const [QUrl](qurl.html) &identifier | Identifies the error with a URI, where the fragment is the error code, and the rest of the URI is the error namespace. |
| const [QSourceLocation](qsourcelocation.html) & sourceLocation | Identifies where the error occurred. |

**See also** [messageHandler](qxmlschema.html#messageHandler)（ ） 。

```
QXmlSchema.setNetworkAccessManager (self, QNetworkAccessManager networkmanager)
```

设置网络管理员_manager_。[QXmlSchema](qxmlschema.html)不采取所有权_manager_。

**See also** [networkAccessManager](qxmlschema.html#networkAccessManager)（ ） 。

```
QXmlSchema.setUriResolver (self, QAbstractUriResolver resolver)
```

设置的URI解析器_resolver_。[QXmlSchema](qxmlschema.html)不采取所有权_resolver_。

**See also** [uriResolver](qxmlschema.html#uriResolver)（ ） 。

```
QAbstractUriResolver QXmlSchema.uriResolver (self)
```

[](qabstracturiresolver.html)

[返回架构的URI解析器。如果没有的URI解析器已定，](qabstracturiresolver.html)[QtXmlPatterns](index.htm)将使用的URI的模式，因为它们。

这个URI解析器提供了一个抽象层，或_polymorphic URIs_。解析器可以重写_logical_URI与物理的，或者它可以翻译过时的或无效的URI来有效的。

When [QtXmlPatterns](index.htm)电话[QAbstractUriResolver.resolve](qabstracturiresolver.html#resolve)（ ）的绝对URI是由架构规范规定的URI和相对URI是由用户指定的URI。

**See also** [setUriResolver](qxmlschema.html#setUriResolver)（ ） 。