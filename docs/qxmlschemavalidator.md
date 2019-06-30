# QXmlSchemaValidator Class Reference

## [[QtXmlPatterns](index.htm) module]

该QXmlSchemaValidator类验证XML实例文档对W3C XML架构。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QXmlSchema schema)`
*   `QAbstractMessageHandler messageHandler (self)`
*   `QXmlNamePool namePool (self)`
*   `QNetworkAccessManager networkAccessManager (self)`
*   `QXmlSchema schema (self)`
*   `setMessageHandler (self, QAbstractMessageHandler handler)`
*   `setNetworkAccessManager (self, QNetworkAccessManager networkmanager)`
*   `setSchema (self, QXmlSchema schema)`
*   `setUriResolver (self, QAbstractUriResolver resolver)`
*   `QAbstractUriResolver uriResolver (self)`
*   `bool validate (self, QUrl source)`
*   `bool validate (self, QIODevice source, QUrl documentUri = QUrl())`
*   `bool validate (self, QByteArray data, QUrl documentUri = QUrl())`

* * *

## Detailed Description

该QXmlSchemaValidator类验证XML实例文档对W3C XML架构。

该QXmlSchemaValidator类加载，解析一个XML实例文档，并对其进行验证已编译与W3C XML模式[QXmlSchema](qxmlschema.html)。

下面的示例演示如何从本地文件中加载XML架构，检查它是否是一个有效的模式文档，并将其用于XML实例文档的验证：

```
     [QUrl](qurl.html) schemaUrl("file:///home/user/schema.xsd");

     [QXmlSchema](qxmlschema.html) schema;
     schema.load(schemaUrl);

     if (schema.isValid()) {
         [QFile](qfile.html) file("test.xml");
         file.open([QIODevice](qiodevice.html).ReadOnly);

         QXmlSchemaValidator validator(schema);
         if (validator.validate(&file, [QUrl](qurl.html).fromLocalFile(file.fileName())))
             qDebug() << "instance document is valid";
         else
             qDebug() << "instance document is invalid";
     }

```

### XML Schema Version

根据这个类实现模式验证[XML Schema](http://www.w3.org/XML/Schema)1.0规范。

* * *

## Method Documentation

```
QXmlSchemaValidator.__init__ (self)
```

构造一个模式验证。用于验证的架构必须在XML实例文档中通过引用`xsi:schemaLocation` or `xsi:noNamespaceSchemaLocation`属性。

```
QXmlSchemaValidator.__init__ (self, QXmlSchema schema)
```

构建将使用模式验证_schema_进行验证。如果空[QXmlSchema](qxmlschema.html)模式被传递给验证器，用于验证的架构，必须在XML实例文档中通过引用`xsi:schemaLocation` or `xsi:noNamespaceSchemaLocation`属性。

```
QAbstractMessageHandler QXmlSchemaValidator.messageHandler (self)
```

[](qabstractmessagehandler.html)

[返回处理这个解析和验证消息的消息处理程序](qabstractmessagehandler.html)[QXmlSchemaValidator](qxmlschemavalidator.html)。

**See also** [setMessageHandler](qxmlschemavalidator.html#setMessageHandler)（ ） 。

```
QXmlNamePool QXmlSchemaValidator.namePool (self)
```

[](qxmlnamepool.html)

[返回此名称池](qxmlnamepool.html)[QXmlSchemaValidator](qxmlschemavalidator.html)构建[names](qxmlname.html)。有没有setter的名字池，因为混合池的名称会导致错误，由于名称的混乱。

```
QNetworkAccessManager QXmlSchemaValidator.networkAccessManager (self)
```

[

返回该网络管理器，或0 ，如果它没有被设置。

](qnetworkaccessmanager.html)

[**See also**](qnetworkaccessmanager.html) [setNetworkAccessManager](qxmlschemavalidator.html#setNetworkAccessManager)（ ） 。

```
QXmlSchema QXmlSchemaValidator.schema (self)
```

[

返回一个用于验证的架构。

](qxmlschema.html)

[**See also**](qxmlschema.html) [setSchema](qxmlschemavalidator.html#setSchema)（ ） 。

```
QXmlSchemaValidator.setMessageHandler (self, QAbstractMessageHandler handler)
```

更改[message handler](qabstractmessagehandler.html)这[QXmlSchemaValidator](qxmlschemavalidator.html)至_handler_。模式验证器将所有解析和验证消息，此消息处理程序。[QXmlSchemaValidator](qxmlschemavalidator.html)不采取所有权_handler_。

通常情况下，默认的消息处理就足够了。它写的编译和验证消息的_stderr_。默认的消息处理程序，包括颜色代码，如果_stderr_可以使色彩。

When [QXmlSchemaValidator](qxmlschemavalidator.html)电话[QAbstractMessageHandler.message](qabstractmessagehandler.html#message)（ ） ，参数如下：

| message() argument | Semantics |
| --- | --- |
| [QtMsgType](index.htm#QtMsgType-enum) type | Only [QtWarningMsg](index.htm#QtMsgType-enum) and [QtFatalMsg](index.htm#QtMsgType-enum) are used. The former identifies a warning, while the latter identifies an error. |
| const [QString](qstring.html) & description | An XHTML document which is the actual message. It is translated into the current language. |
| const [QUrl](qurl.html) &identifier | Identifies the error with a URI, where the fragment is the error code, and the rest of the URI is the error namespace. |
| const [QSourceLocation](qsourcelocation.html) & sourceLocation | Identifies where the error occurred. |

**See also** [messageHandler](qxmlschemavalidator.html#messageHandler)（ ） 。

```
QXmlSchemaValidator.setNetworkAccessManager (self, QNetworkAccessManager networkmanager)
```

设置网络管理员_manager_。[QXmlSchemaValidator](qxmlschemavalidator.html)不采取所有权_manager_。

**See also** [networkAccessManager](qxmlschemavalidator.html#networkAccessManager)（ ） 。

```
QXmlSchemaValidator.setSchema (self, QXmlSchema schema)
```

设置_schema_这将用于进一步的验证。如果架构是空的，用于验证的架构，必须在XML实例文档中通过引用`xsi:schemaLocation` or `xsi:noNamespaceSchemaLocation`属性。

**See also** [schema](qxmlschemavalidator.html#schema)（ ） 。

```
QXmlSchemaValidator.setUriResolver (self, QAbstractUriResolver resolver)
```

设置的URI解析器_resolver_。[QXmlSchemaValidator](qxmlschemavalidator.html)不采取所有权_resolver_。

**See also** [uriResolver](qxmlschemavalidator.html#uriResolver)（ ） 。

```
QAbstractUriResolver QXmlSchemaValidator.uriResolver (self)
```

[](qabstracturiresolver.html)

[返回架构的URI解析器。如果没有的URI解析器已定，](qabstracturiresolver.html)[QtXmlPatterns](index.htm)将使用的URI的实例文档，因为它们。

这个URI解析器提供了一个抽象层，或_polymorphic URIs_。解析器可以重写_logical_URI与物理的，或者它可以翻译过时的或无效的URI来有效的。

When [QtXmlPatterns](index.htm)电话[QAbstractUriResolver.resolve](qabstracturiresolver.html#resolve)（ ）的绝对URI是由架构规范规定的URI和相对URI是由用户指定的URI。

**See also** [setUriResolver](qxmlschemavalidator.html#setUriResolver)（ ） 。

```
bool QXmlSchemaValidator.validate (self, QUrl source)
```

验证读取XML实例文档_source_针对架构。

Returns `true`如果根据模式的XML实例文档是有效的，`false`否则。

例如：

```
     const [QXmlSchema](qxmlschema.html) schema = getSchema();

     const [QUrl](qurl.html) url("http://www.schema-example.org/test.xml");

     [QXmlSchemaValidator](qxmlschemavalidator.html) validator(schema);
     if (validator.validate(url))
         qDebug() << "instance document is valid";
     else
         qDebug() << "instance document is invalid";

```

```
bool QXmlSchemaValidator.validate (self, QIODevice source, QUrl documentUri = QUrl())
```

验证读取XML实例文档_source_用给定的_documentUri_针对架构。

Returns `true`如果根据模式的XML实例文档是有效的，`false`否则。

例如：

```
     const [QXmlSchema](qxmlschema.html) schema = getSchema();

     [QFile](qfile.html) file("test.xml");
     file.open([QIODevice](qiodevice.html).ReadOnly);

     [QXmlSchemaValidator](qxmlschemavalidator.html) validator(schema);
     if (validator.validate(&file, [QUrl](qurl.html).fromLocalFile(file.fileName())))
         qDebug() << "instance document is valid";
     else
         qDebug() << "instance document is invalid";

```

```
bool QXmlSchemaValidator.validate (self, QByteArray data, QUrl documentUri = QUrl())
```

验证读取XML实例文档_data_用给定的_documentUri_针对架构。

Returns `true`如果根据模式的XML实例文档是有效的，`false`否则。

例如：

```
     const [QXmlSchema](qxmlschema.html) schema = getSchema();

     [QByteArray](qbytearray.html) data("<?xml version=\"1.0\" encoding=\"UTF-8\"?>"
                     "<test></test>");

     [QBuffer](qbuffer.html) buffer(&data);
     buffer.open([QIODevice](qiodevice.html).ReadOnly);

     [QXmlSchemaValidator](qxmlschemavalidator.html) validator(schema);
     if (validator.validate(&buffer))
         qDebug() << "instance document is valid";
     else
         qDebug() << "instance document is invalid";

```