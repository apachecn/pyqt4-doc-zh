# QXmlStreamReader Class Reference

## [[QtCore](index.htm) module]

该QXmlStreamReader类提供了一种快速分析器通过一个简单的流API读取格式良好的XML 。[More...](#details)

### Types

*   `enum Error { NoError, UnexpectedElementError, CustomError, NotWellFormedError, PrematureEndOfDocumentError }`
*   `enum ReadElementTextBehaviour { ErrorOnUnexpectedElement, IncludeChildElements, SkipChildElements }`
*   `enum TokenType { NoToken, Invalid, StartDocument, EndDocument, ..., ProcessingInstruction }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QIODevice device)`
*   `__init__ (self, QByteArray data)`
*   `__init__ (self, QString data)`
*   `addData (self, QByteArray data)`
*   `addData (self, QString data)`
*   `addExtraNamespaceDeclaration (self, QXmlStreamNamespaceDeclaration extraNamespaceDeclaraction)`
*   `addExtraNamespaceDeclarations (self, list-of-QXmlStreamNamespaceDeclaration extraNamespaceDeclaractions)`
*   `bool atEnd (self)`
*   `QXmlStreamAttributes attributes (self)`
*   `int characterOffset (self)`
*   `clear (self)`
*   `int columnNumber (self)`
*   `QIODevice device (self)`
*   `QStringRef documentEncoding (self)`
*   `QStringRef documentVersion (self)`
*   `QStringRef dtdName (self)`
*   `QStringRef dtdPublicId (self)`
*   `QStringRef dtdSystemId (self)`
*   `list-of-QXmlStreamEntityDeclaration entityDeclarations (self)`
*   `QXmlStreamEntityResolver entityResolver (self)`
*   `Error error (self)`
*   `QString errorString (self)`
*   `bool hasError (self)`
*   `bool isCDATA (self)`
*   `bool isCharacters (self)`
*   `bool isComment (self)`
*   `bool isDTD (self)`
*   `bool isEndDocument (self)`
*   `bool isEndElement (self)`
*   `bool isEntityReference (self)`
*   `bool isProcessingInstruction (self)`
*   `bool isStandaloneDocument (self)`
*   `bool isStartDocument (self)`
*   `bool isStartElement (self)`
*   `bool isWhitespace (self)`
*   `int lineNumber (self)`
*   `QStringRef name (self)`
*   `list-of-QXmlStreamNamespaceDeclaration namespaceDeclarations (self)`
*   `bool namespaceProcessing (self)`
*   `QStringRef namespaceUri (self)`
*   `list-of-QXmlStreamNotationDeclaration notationDeclarations (self)`
*   `QStringRef prefix (self)`
*   `QStringRef processingInstructionData (self)`
*   `QStringRef processingInstructionTarget (self)`
*   `QStringRef qualifiedName (self)`
*   `raiseError (self, QString message = QString())`
*   `QString readElementText (self)`
*   `QString readElementText (self, ReadElementTextBehaviour behaviour)`
*   `TokenType readNext (self)`
*   `bool readNextStartElement (self)`
*   `setDevice (self, QIODevice device)`
*   `setEntityResolver (self, QXmlStreamEntityResolver resolver)`
*   `setNamespaceProcessing (self, bool)`
*   `skipCurrentElement (self)`
*   `QStringRef text (self)`
*   `QString tokenString (self)`
*   `TokenType tokenType (self)`

* * *

## Detailed Description

该QXmlStreamReader类提供了一种快速分析器通过一个简单的流API读取格式良好的XML 。

QXmlStreamReader是更快，更方便的替代Qt自己的SAX解析器（见[QXmlSimpleReader](qxmlsimplereader.html)） 。在某些情况下它也可能用于，否则将使用DOM树的应用程序更快，更方便的选择（见[QDomDocument](qdomdocument.html)） 。 QXmlStreamReader读取无论是从数据[QIODevice](qiodevice.html)（见[setDevice](qxmlstreamreader.html#setDevice)（）），或者从一个原[QByteArray](qbytearray.html)（见[addData](qxmlstreamreader.html#addData)（））。

Qt提供[QXmlStreamWriter](qxmlstreamwriter.html)用于编写XML 。

流读取器的基本概念是报告一个XML文档作为标记，类似于SAX流。 QXmlStreamReader和SAX之间的主要区别在于_how_这些XML标记的报告。使用SAX ，应用程序必须提供处理程序（回调函数）接受所谓的XML_events_从解析器在解析器的便利性。与QXmlStreamReader ，应用程序代码本身驱动环路和拉_tokens_从阅读器，一个接一个，因为它需要他们。这是通过调用完成[readNext](qxmlstreamreader.html#readNext)（ ） ，那里的读者从输入流中读取，直到它完成下一个标记，此时它返回[tokenType](qxmlstreamreader.html#tokenType)（ ） 。一组方便的功能，包括[isStartElement](qxmlstreamreader.html#isStartElement)（）和[text](qxmlstreamreader.html#text)（ ）然后可以用于检查令牌以获取有关什么已被读取的信息。这样做的好处大_pulling_方法是建立递归下降解析器与它，这意味着你可以很容易地分割你的XML解析代码分成不同的方法或类的可能性。这可以很容易地解析XML时，跟踪应用程序自身的状态。

一个典型的循环与QXmlStreamReader看起来像这样：

```
   QXmlStreamReader xml;
   ...
   while (!xml.atEnd()) {
         xml.readNext();
         ... // do processing
   }
   if (xml.hasError()) {
         ... // do error handling
   }

```

QXmlStreamReader是一个格式良好的XML解析器1.0 ，做_not_包括外部解析实体。只要不发生错误，应用程序代码可以因此放心，用流读取器提供的数据符合W3C的标准格式良好的XML 。例如，你可以肯定，所有的标籤确实嵌套和正确关闭，即引用内部实体已被替换为正确的替换文本，并根据DTD的内部子集的属性已归或添加。

如果在解析出现错误，[atEnd](qxmlstreamreader.html#atEnd)（）和[hasError](qxmlstreamreader.html#hasError)（ ）返回True ，并且[error](qxmlstreamreader.html#error)（）返回所发生的错误。该功能[errorString](qxmlstreamreader.html#errorString)（ ）[lineNumber](qxmlstreamreader.html#lineNumber)（ ）[columnNumber](qxmlstreamreader.html#columnNumber)（）和[characterOffset](qxmlstreamreader.html#characterOffset)（ ）是构造一个适当的错误或警告消息。为了简化应用程序代码， QXmlStreamReader包含一个[raiseError](qxmlstreamreader.html#raiseError)（）机制，可以让你提高触发描述的相同的错误处理自定义错误。

该[QXmlStream Bookmarks Example](index.htm)说明如何使用递归下降方法读取XML文件的书籤（ XBEL ）用流读取器。

### Namespaces

QXmlStream理解和解决XML命名空间。例如在壳体的[StartElement](qxmlstreamreader.html#TokenType-enum)，[namespaceUri](qxmlstreamreader.html#namespaceUri)（ ）返回的元素是在命名空间中，[name](qxmlstreamreader.html#name)（ ）返回元素的_local_名称。则namespaceURI和名称的组合唯一地标识一个元素。如果一个命名空间前缀由读者解析的XML实体未声明，则namespaceURI是空的。

如果您解析XML数据，不使用命名空间，根据XML规范或根本不使用命名空间，可以使用元素的[qualifiedName](qxmlstreamreader.html#qualifiedName)（ ）来代替。一个合格的名称是元素的[prefix](qxmlstreamreader.html#prefix)（ ），其次是冒号后面元素的地方[name](qxmlstreamreader.html#name)（ ） - 完全一样的元素出现在原始的XML数据。由于映射的namespaceURI前缀既不是唯一也不是万能，[qualifiedName](qxmlstreamreader.html#qualifiedName)（ ）应避免命名空间兼容的XML数据。

为了解析独立文档确实使用未声明的命名空间前缀，你可以完全关闭名称空间处理与[namespaceProcessing](qxmlstreamreader.html#namespaceProcessing-prop)属性。

### Incremental parsing

QXmlStreamReader是一个渐进的解析器。它可以处理其中的文件不能被解析一次全部，因为它在块到达（例如，从多个文件，或通过网络连接）的情况下。当读写器运行的数据完整的文档被解析之前，它会报告[PrematureEndOfDocumentError](qxmlstreamreader.html#Error-enum)。当更多的数据到达，或者是因为一个电话来[addData](qxmlstreamreader.html#addData)（ ）或者是因为更多的数据可通过网络[device](qxmlstreamreader.html#device)（）时，阅读器从恢复[PrematureEndOfDocumentError](qxmlstreamreader.html#Error-enum)错误并继续与下一个调用解析新数据[readNext](qxmlstreamreader.html#readNext)（ ） 。

例如，如果你的应用程序从网络读取数据使用[network access manager](qnetworkaccessmanager.html)，你会发出[network request](qnetworkrequest.html)给经理，并获得[network reply](qnetworkreply.html)作为回报。由于[QNetworkReply](qnetworkreply.html)是[QIODevice](qiodevice.html)，您连接其[readyRead()](qiodevice.html#readyRead)信号到一个自定义的插槽，如`slotReadyRead()`在为讨论的代码段[QNetworkAccessManager](qnetworkaccessmanager.html)。在此插槽，可以读取所有可用的数据与[readAll()](qiodevice.html#readAll)并利用它传递给XML流读取器[addData](qxmlstreamreader.html#addData)（ ） 。然后你打电话给你的自定义分析功能，读取从读者的XML事件。

### Performance and memory consumption

QXmlStreamReader是内存保守的设计，因为它并不存储整个XML文档树在内存中，但只有在当时的当前令牌有报导。此外， QXmlStreamReader避免了许多小的串分配，它通常需要将XML文档映射到一个方便和Qt十岁上下的API 。它通过报告所有的字符串数据作为执行此操作[QStringRef](qstringref.html)而不是真正的[QString](qstring.html)对象。[QStringRef](qstringref.html)是一个简单包装的[QString](qstring.html)子，它提供的一个子集[QString](qstring.html)API，而内存分配和引用计数的开销。调用[toString()](qstringref.html#toString)在任何这些对象返回一个等价的真实[QString](qstring.html)对象。

* * *

## Type Documentation

```
QXmlStreamReader.Error
```

此枚举指定不同的错误情况

| Constant | Value | Description |
| --- | --- | --- |
| `QXmlStreamReader.NoError` | `0` | 没有发生错误。 |
| `QXmlStreamReader.CustomError` | `2` | 一个自定义的错误已被提出与[raiseError](qxmlstreamreader.html#raiseError)（ ） |
| `QXmlStreamReader.NotWellFormedError` | `3` | 解析器内部，由于读取XML并非良好的引发错误。 |
| `QXmlStreamReader.PrematureEndOfDocumentError` | `4` | 输入流结束一个格式良好的XML文档被解析之前。恢复从这个错误是可能的，如果更多的XML到达流中，通过调用[addData](qxmlstreamreader.html#addData)（ ）或等待它的到来[device](qxmlstreamreader.html#device)（ ） 。 |
| `QXmlStreamReader.UnexpectedElementError` | `1` | 解析器遇到了有别于其预期的元素。 |

```
QXmlStreamReader.ReadElementTextBehaviour
```

这个枚举指定的不同的行为[readElementText](qxmlstreamreader.html#readElementText)（ ） 。

| Constant | Value | Description |
| --- | --- | --- |
| `QXmlStreamReader.ErrorOnUnexpectedElement` | `0` | 引发[UnexpectedElementError](qxmlstreamreader.html#Error-enum)并返回什么，到目前为止的子元素时遇到被读取。 |
| `QXmlStreamReader.IncludeChildElements` | `1` | 递归包括子元素的文本。 |
| `QXmlStreamReader.SkipChildElements` | `2` | 跳过子元素。 |

这个枚举被引入或修改的Qt 4.6 。

```
QXmlStreamReader.TokenType
```

此枚举指定刚读标记阅读器的类型。

| Constant | Value | Description |
| --- | --- | --- |
| `QXmlStreamReader.NoToken` | `0` | 读者还没有读什么。 |
| `QXmlStreamReader.Invalid` | `1` | 发生错误，报告[error](qxmlstreamreader.html#error)（）和[errorString](qxmlstreamreader.html#errorString)（ ） 。 |
| `QXmlStreamReader.StartDocument` | `2` | 读者报告中的XML版本号[documentVersion](qxmlstreamreader.html#documentVersion)（） ，和在XML文档中指定的编码[documentEncoding](qxmlstreamreader.html#documentEncoding)（ ） 。如果文档被宣告独立，[isStandaloneDocument](qxmlstreamreader.html#isStandaloneDocument)（ ）返回True ，否则返回False 。 |
| `QXmlStreamReader.EndDocument` | `3` | 读者报告文件的末尾。 |
| `QXmlStreamReader.StartElement` | `4` | 读者报告与元素的起始[namespaceUri](qxmlstreamreader.html#namespaceUri)（）和[name](qxmlstreamreader.html#name)（ ） 。空的元素也报导的StartElement ，直接跟着的EndElement 。便利的功能[readElementText](qxmlstreamreader.html#readElementText)（ ）可以调用来连接所有的内容，直到相应的endElement 。属性报告[attributes](qxmlstreamreader.html#attributes)（ ） ，命名空间声明[namespaceDeclarations](qxmlstreamreader.html#namespaceDeclarations)（ ） 。 |
| `QXmlStreamReader.EndElement` | `5` | 读者报告用元件的端部[namespaceUri](qxmlstreamreader.html#namespaceUri)（）和[name](qxmlstreamreader.html#name)（ ） 。 |
| `QXmlStreamReader.Characters` | `6` | 读者报告中的字符[text](qxmlstreamreader.html#text)（ ） 。如果字符都是空白，[isWhitespace](qxmlstreamreader.html#isWhitespace)（ ）返回True 。如果字符CDATA节茎，[isCDATA](qxmlstreamreader.html#isCDATA)（ ）返回True 。 |
| `QXmlStreamReader.Comment` | `7` | 读者报告的意见[text](qxmlstreamreader.html#text)（ ） 。 |
| `QXmlStreamReader.DTD` | `8` | 读者报告在DTD[text](qxmlstreamreader.html#text)（ ） ，表示法声明[notationDeclarations](qxmlstreamreader.html#notationDeclarations)在（ ） ，和实体声明[entityDeclarations](qxmlstreamreader.html#entityDeclarations)（ ） 。 DTD的声明的详细报告中[dtdName](qxmlstreamreader.html#dtdName)（ ）[dtdPublicId](qxmlstreamreader.html#dtdPublicId)（）和[dtdSystemId](qxmlstreamreader.html#dtdSystemId)（ ） 。 |
| `QXmlStreamReader.EntityReference` | `9` | 读者报告一个实体引用不能被解决。引用的名称是报告[name](qxmlstreamreader.html#name)（ ） ，在替换文本[text](qxmlstreamreader.html#text)（ ） 。 |
| `QXmlStreamReader.ProcessingInstruction` | `10` | 读者报告在一个处理指令[processingInstructionTarget](qxmlstreamreader.html#processingInstructionTarget)（）和[processingInstructionData](qxmlstreamreader.html#processingInstructionData)（ ） 。 |

* * *

## Method Documentation

```
QXmlStreamReader.__init__ (self)
```

构造一个流读取器。

**See also** [setDevice](qxmlstreamreader.html#setDevice)（）和[addData](qxmlstreamreader.html#addData)（ ） 。

```
QXmlStreamReader.__init__ (self, QIODevice device)
```

创建一个新的流读取器的读取_device_。

**See also** [setDevice](qxmlstreamreader.html#setDevice)（）和[clear](qxmlstreamreader.html#clear)（ ） 。

```
QXmlStreamReader.__init__ (self, QByteArray data)
```

创建一个新的流读取器的读取_data_。

**See also** [addData](qxmlstreamreader.html#addData)（ ）[clear](qxmlstreamreader.html#clear)（）和[setDevice](qxmlstreamreader.html#setDevice)（ ） 。

```
QXmlStreamReader.__init__ (self, QString data)
```

创建一个新的流读取器的读取_data_。

**See also** [addData](qxmlstreamreader.html#addData)（ ）[clear](qxmlstreamreader.html#clear)（）和[setDevice](qxmlstreamreader.html#setDevice)（ ） 。

```
QXmlStreamReader.addData (self, QByteArray data)
```

增加了更多的_data_为读者阅读。这个函数做什么，如果读者有一个[device](qxmlstreamreader.html#device)（ ） 。

**See also** [readNext](qxmlstreamreader.html#readNext)（）和[clear](qxmlstreamreader.html#clear)（ ） 。

```
QXmlStreamReader.addData (self, QString data)
```

增加了更多的_data_为读者阅读。这个函数做什么，如果读者有一个[device](qxmlstreamreader.html#device)（ ） 。

**See also** [readNext](qxmlstreamreader.html#readNext)（）和[clear](qxmlstreamreader.html#clear)（ ） 。

```
QXmlStreamReader.addExtraNamespaceDeclaration (self, QXmlStreamNamespaceDeclaration extraNamespaceDeclaraction)
```

增加了一个_extraNamespaceDeclaration_。该声明的有效期为当前元素的子元素，或者 - 应函数被调用读取任何元素之前 - 对整个XML文档。

此功能被引入Qt的4.4 。

**See also** [namespaceDeclarations](qxmlstreamreader.html#namespaceDeclarations)（ ）[addExtraNamespaceDeclarations](qxmlstreamreader.html#addExtraNamespaceDeclarations)（）和[setNamespaceProcessing](qxmlstreamreader.html#namespaceProcessing-prop)（ ） 。

```
QXmlStreamReader.addExtraNamespaceDeclarations (self, list-of-QXmlStreamNamespaceDeclaration extraNamespaceDeclaractions)
```

添加的声明由指定的向量_extraNamespaceDeclarations_。

此功能被引入Qt的4.4 。

**See also** [namespaceDeclarations](qxmlstreamreader.html#namespaceDeclarations)（）和[addExtraNamespaceDeclaration](qxmlstreamreader.html#addExtraNamespaceDeclaration)（ ） 。

```
bool QXmlStreamReader.atEnd (self)
```

返回True如果读者已阅读，直到XML文档的末尾，或者如果[error](qxmlstreamreader.html#error)（ ）已经发生和阅读已经中止。否则，返回False 。

当了atEnd （）和[hasError](qxmlstreamreader.html#hasError)（ ）返回True和[error](qxmlstreamreader.html#error)（）返回[PrematureEndOfDocumentError](qxmlstreamreader.html#Error-enum)，这意味着XML得到了很好的形成，到目前为止，而是一个完整的XML文档还没有被解析。 XML的下一组块可以被添加[addData](qxmlstreamreader.html#addData)（） ，如果XML正在从读[QByteArray](qbytearray.html)，或通过等待更多的数据到达如果XML正在从读[QIODevice](qiodevice.html)。无论哪种方式，了atEnd （）一次以上数据可将返回False 。

**See also** [hasError](qxmlstreamreader.html#hasError)（ ）[error](qxmlstreamreader.html#error)（ ）[device](qxmlstreamreader.html#device)（）和[QIODevice.atEnd](qiodevice.html#atEnd)（ ） 。

```
QXmlStreamAttributes QXmlStreamReader.attributes (self)
```

[](qxmlstreamattributes.html)

[返回一个属性](qxmlstreamattributes.html)[StartElement](qxmlstreamreader.html#TokenType-enum)。

```
int QXmlStreamReader.characterOffset (self)
```

返回当前字符的偏移，从0开始。

**See also** [lineNumber](qxmlstreamreader.html#lineNumber)（）和[columnNumber](qxmlstreamreader.html#columnNumber)（ ） 。

```
QXmlStreamReader.clear (self)
```

删除任何[device](qxmlstreamreader.html#device)（）或来自读出器的数据和复位它的内部状态为初始状态。

**See also** [addData](qxmlstreamreader.html#addData)（ ） 。

```
int QXmlStreamReader.columnNumber (self)
```

返回当前列号，从0开始。

**See also** [lineNumber](qxmlstreamreader.html#lineNumber)（）和[characterOffset](qxmlstreamreader.html#characterOffset)（ ） 。

```
QIODevice QXmlStreamReader.device (self)
```

[](qiodevice.html)

[返回与关联的当前设备](qiodevice.html)[QXmlStreamReader](qxmlstreamreader.html)，或者0，如果没有设备已经被分配。

**See also** [setDevice](qxmlstreamreader.html#setDevice)（ ） 。

```
QStringRef QXmlStreamReader.documentEncoding (self)
```

如果状态（ ）是[StartDocument](qxmlstreamreader.html#TokenType-enum)，这个函数返回的XML声明中指定的编码字符串。否则返回空字符串。

此功能被引入Qt的4.4 。

```
QStringRef QXmlStreamReader.documentVersion (self)
```

如果状态（ ）是[StartDocument](qxmlstreamreader.html#TokenType-enum)，这个函数返回的XML声明中指定的版本字符串。否则返回空字符串。

此功能被引入Qt的4.4 。

```
QStringRef QXmlStreamReader.dtdName (self)
```

如果状态（ ）是[DTD](qxmlstreamreader.html#TokenType-enum)，这个函数返回的DTD的名字。否则返回空字符串。

此功能被引入Qt的4.4 。

```
QStringRef QXmlStreamReader.dtdPublicId (self)
```

如果状态（ ）是[DTD](qxmlstreamreader.html#TokenType-enum)，这个函数返回的DTD的公共标识符。否则返回空字符串。

此功能被引入Qt的4.4 。

```
QStringRef QXmlStreamReader.dtdSystemId (self)
```

如果状态（ ）是[DTD](qxmlstreamreader.html#TokenType-enum)，这个函数返回的DTD的系统标识符。否则返回空字符串。

此功能被引入Qt的4.4 。

```
list-of-QXmlStreamEntityDeclaration QXmlStreamReader.entityDeclarations (self)
```

如果状态（ ）是[DTD](qxmlstreamreader.html#TokenType-enum)，这个函数返回的DTD的非解析（外部）实体声明。否则，一个空向量被返回。

该 [QXmlStreamEntityDeclarations](qxmlstreamentitydeclaration.html#QXmlStreamEntityDeclarations-typedef)类被定义为一个[QVector](index.htm)的[QXmlStreamEntityDeclaration](qxmlstreamentitydeclaration.html)。

```
QXmlStreamEntityResolver QXmlStreamReader.entityResolver (self)
```

[

返回的实体解析器，或者0 ，如果没有实体解析器。

此功能被引入Qt的4.4 。

](qxmlstreamentityresolver.html)

[**See also**](qxmlstreamentityresolver.html) [setEntityResolver](qxmlstreamreader.html#setEntityResolver)（ ） 。

```
Error QXmlStreamReader.error (self)
```

[](qxmlstreamreader.html#Error-enum)

[返回当前错误的类型，或者](qxmlstreamreader.html#Error-enum)[NoError](qxmlstreamreader.html#Error-enum)如果没有发生错误。

**See also** [errorString](qxmlstreamreader.html#errorString)（）和[raiseError](qxmlstreamreader.html#raiseError)（ ） 。

```
QString QXmlStreamReader.errorString (self)
```

返回设置并显示错误消息[raiseError](qxmlstreamreader.html#raiseError)（ ） 。

**See also** [error](qxmlstreamreader.html#error)（ ）[lineNumber](qxmlstreamreader.html#lineNumber)（ ）[columnNumber](qxmlstreamreader.html#columnNumber)（）和[characterOffset](qxmlstreamreader.html#characterOffset)（ ） 。

```
bool QXmlStreamReader.hasError (self)
```

Returns `true`如果发生了错误，否则`false`。

**See also** [errorString](qxmlstreamreader.html#errorString)（）和[error](qxmlstreamreader.html#error)（ ） 。

```
bool QXmlStreamReader.isCDATA (self)
```

返回True如果读者报导说， CDATA节茎字符，否则返回False 。

**See also** [isCharacters](qxmlstreamreader.html#isCharacters)（）和[text](qxmlstreamreader.html#text)（ ） 。

```
bool QXmlStreamReader.isCharacters (self)
```

返回True如果[tokenType](qxmlstreamreader.html#tokenType)（ ）等于[Characters](qxmlstreamreader.html#TokenType-enum)否则返回False 。

**See also** [isWhitespace](qxmlstreamreader.html#isWhitespace)（）和[isCDATA](qxmlstreamreader.html#isCDATA)（ ） 。

```
bool QXmlStreamReader.isComment (self)
```

返回True如果[tokenType](qxmlstreamreader.html#tokenType)（ ）等于[Comment](qxmlstreamreader.html#TokenType-enum)否则返回False 。

```
bool QXmlStreamReader.isDTD (self)
```

返回True如果[tokenType](qxmlstreamreader.html#tokenType)（ ）等于[DTD](qxmlstreamreader.html#TokenType-enum)否则返回False 。

```
bool QXmlStreamReader.isEndDocument (self)
```

返回True如果[tokenType](qxmlstreamreader.html#tokenType)（ ）等于[EndDocument](qxmlstreamreader.html#TokenType-enum)否则返回False 。

```
bool QXmlStreamReader.isEndElement (self)
```

返回True如果[tokenType](qxmlstreamreader.html#tokenType)（ ）等于[EndElement](qxmlstreamreader.html#TokenType-enum)否则返回False 。

```
bool QXmlStreamReader.isEntityReference (self)
```

返回True如果[tokenType](qxmlstreamreader.html#tokenType)（ ）等于[EntityReference](qxmlstreamreader.html#TokenType-enum)否则返回False 。

```
bool QXmlStreamReader.isProcessingInstruction (self)
```

返回True如果[tokenType](qxmlstreamreader.html#tokenType)（ ）等于[ProcessingInstruction](qxmlstreamreader.html#TokenType-enum)否则返回False 。

```
bool QXmlStreamReader.isStandaloneDocument (self)
```

返回True如果该文档已被宣布为独立的XML声明，否则返回False 。

如果没有XML声明被解析，这个函数返回False 。

```
bool QXmlStreamReader.isStartDocument (self)
```

返回True如果[tokenType](qxmlstreamreader.html#tokenType)（ ）等于[StartDocument](qxmlstreamreader.html#TokenType-enum)否则返回False 。

```
bool QXmlStreamReader.isStartElement (self)
```

返回True如果[tokenType](qxmlstreamreader.html#tokenType)（ ）等于[StartElement](qxmlstreamreader.html#TokenType-enum)否则返回False 。

```
bool QXmlStreamReader.isWhitespace (self)
```

返回True如果读者报导的字符，只包含空格，否则返回False 。

**See also** [isCharacters](qxmlstreamreader.html#isCharacters)（）和[text](qxmlstreamreader.html#text)（ ） 。

```
int QXmlStreamReader.lineNumber (self)
```

返回当前行号，从1开始。

**See also** [columnNumber](qxmlstreamreader.html#columnNumber)（）和[characterOffset](qxmlstreamreader.html#characterOffset)（ ） 。

```
QStringRef QXmlStreamReader.name (self)
```

返回的本地名称[StartElement](qxmlstreamreader.html#TokenType-enum)，[EndElement](qxmlstreamreader.html#TokenType-enum)，或[EntityReference](qxmlstreamreader.html#TokenType-enum)。

**See also** [namespaceUri](qxmlstreamreader.html#namespaceUri)（）和[qualifiedName](qxmlstreamreader.html#qualifiedName)（ ） 。

```
list-of-QXmlStreamNamespaceDeclaration QXmlStreamReader.namespaceDeclarations (self)
```

如果状态（ ）是[StartElement](qxmlstreamreader.html#TokenType-enum)，这个函数返回元素的命名空间声明。否则，一个空向量被返回。

该[QXmlStreamNamespaceDeclaration](qxmlstreamnamespacedeclaration.html)类被定义为一个[QVector](index.htm)的[QXmlStreamNamespaceDeclaration](qxmlstreamnamespacedeclaration.html)。

**See also** [addExtraNamespaceDeclaration](qxmlstreamreader.html#addExtraNamespaceDeclaration)（）和[addExtraNamespaceDeclarations](qxmlstreamreader.html#addExtraNamespaceDeclarations)（ ） 。

```
bool QXmlStreamReader.namespaceProcessing (self)
```

```
QStringRef QXmlStreamReader.namespaceUri (self)
```

返回的则namespaceURI[StartElement](qxmlstreamreader.html#TokenType-enum) or [EndElement](qxmlstreamreader.html#TokenType-enum)。

**See also** [name](qxmlstreamreader.html#name)（）和[qualifiedName](qxmlstreamreader.html#qualifiedName)（ ） 。

```
list-of-QXmlStreamNotationDeclaration QXmlStreamReader.notationDeclarations (self)
```

如果状态（ ）是[DTD](qxmlstreamreader.html#TokenType-enum)，这个函数返回的DTD的符号声明。否则，一个空向量被返回。

该 [QXmlStreamNotationDeclarations](qxmlstreamnotationdeclaration.html#QXmlStreamNotationDeclarations-typedef)类被定义为一个[QVector](index.htm)的[QXmlStreamNotationDeclaration](qxmlstreamnotationdeclaration.html)。

```
QStringRef QXmlStreamReader.prefix (self)
```

返回一个前缀[StartElement](qxmlstreamreader.html#TokenType-enum) or [EndElement](qxmlstreamreader.html#TokenType-enum)。

此功能被引入Qt的4.4 。

**See also** [name](qxmlstreamreader.html#name)（）和[qualifiedName](qxmlstreamreader.html#qualifiedName)（ ） 。

```
QStringRef QXmlStreamReader.processingInstructionData (self)
```

返回的数据[ProcessingInstruction](qxmlstreamreader.html#TokenType-enum)。

```
QStringRef QXmlStreamReader.processingInstructionTarget (self)
```

返回一个目标[ProcessingInstruction](qxmlstreamreader.html#TokenType-enum)。

```
QStringRef QXmlStreamReader.qualifiedName (self)
```

返回一个合格的名称[StartElement](qxmlstreamreader.html#TokenType-enum) or [EndElement](qxmlstreamreader.html#TokenType-enum);

一个合格的名称是XML数据元素的原始名称。它由一个命名空间前缀，后跟冒号，然后是元素的本地名称。由于命名空间前缀不是唯一的（相同的前缀可以指向不同的命名空间和不同的前缀可以指向同一个命名空间） ，你不应该使用qualifiedName中（ ） ，而解析[namespaceUri](qxmlstreamreader.html#namespaceUri)（ ）和属性的本地[name](qxmlstreamreader.html#name)（ ） 。

**See also** [name](qxmlstreamreader.html#name)（ ）[prefix](qxmlstreamreader.html#prefix)（）和[namespaceUri](qxmlstreamreader.html#namespaceUri)（ ） 。

```
QXmlStreamReader.raiseError (self, QString message = QString())
```

引发自定义错误有一个可选的错误_message_。

**See also** [error](qxmlstreamreader.html#error)（）和[errorString](qxmlstreamreader.html#errorString)（ ） 。

```
QString QXmlStreamReader.readElementText (self)
```

便利函数被调用的情况下，[StartElement](qxmlstreamreader.html#TokenType-enum)被读取。读取，直到相应的[EndElement](qxmlstreamreader.html#TokenType-enum)并返回两者之间的所有文本。在案件没有错误，则当前的标记（见[tokenType](qxmlstreamreader.html#tokenType)（ ） ）已调用该函数后[EndElement](qxmlstreamreader.html#TokenType-enum)。

该函数将[text](qxmlstreamreader.html#text)（ ）时，它读取要么[Characters](qxmlstreamreader.html#TokenType-enum) or [EntityReference](qxmlstreamreader.html#TokenType-enum)令牌，但跳过[ProcessingInstruction](qxmlstreamreader.html#TokenType-enum)和[Comment](qxmlstreamreader.html#TokenType-enum)。如果当前标记是不是[StartElement](qxmlstreamreader.html#TokenType-enum)，则返回一个空字符串。

该_behaviour_定义的情况下会发生什么别的到达之前被读取[EndElement](qxmlstreamreader.html#TokenType-enum)。该函数可以从子元素（例如用于HTML有用）包括文本，忽略子元素，或引发[UnexpectedElementError](qxmlstreamreader.html#Error-enum)并返回什么，到目前为止被读取。

此功能被引入Qt的4.6 。

```
QString QXmlStreamReader.readElementText (self, ReadElementTextBehaviour behaviour)
```

这个函数的重载[readElementText](qxmlstreamreader.html#readElementText)（ ） 。

调用此函数相当于调用readElementText （[ErrorOnUnexpectedElement](qxmlstreamreader.html#ReadElementTextBehaviour-enum)） 。

```
TokenType QXmlStreamReader.readNext (self)
```

[

读取下一个标记，并返回它的类型。

](qxmlstreamreader.html#TokenType-enum)

[但有一个例外，一旦](qxmlstreamreader.html#TokenType-enum)[error](qxmlstreamreader.html#error)（ ）据悉，由readNext （ ） ，进一步阅读的XML流是不可能的。然后[atEnd](qxmlstreamreader.html#atEnd)（ ）返回True ，[hasError](qxmlstreamreader.html#hasError)（ ）返回True ，并且该函数返回[QXmlStreamReader.Invalid](qxmlstreamreader.html#TokenType-enum)。

唯一的例外是当[error](qxmlstreamreader.html#error)（）返回[PrematureEndOfDocumentError](qxmlstreamreader.html#Error-enum)。报告该错误，当达到的XML的其他良好的组块的结尾，但组块不表示一个完整的XML文档。在这种情况下，语法分析_can_通过调用恢复[addData](qxmlstreamreader.html#addData)（）添加XML中，为下一个块时，流被从读[QByteArray](qbytearray.html)或通过等待更多数据时，该数据流是从一个读到达[device](qxmlstreamreader.html#device)（ ） 。

**See also** [tokenType](qxmlstreamreader.html#tokenType)（）和[tokenString](qxmlstreamreader.html#tokenString)（ ） 。

```
bool QXmlStreamReader.readNextStartElement (self)
```

直到读取当前元素内的下一个开始元素。当开始元素达成，则返回True 。当结束元素达到或发生错误时，则返回False。

当前元素是匹配的，其中一个匹配端元件尚未达到最新分析的开始元素的元素。当解析器已经走到了尽头元素，当前元素变为父元素。

你可以通过重复调用这个函数，同时确保数据流的读者是不是在文档的末尾遍历一个文件：

```
 [QXmlStreamReader](qxmlstreamreader.html) xs(&file);
 while (!xs.atEnd()) {
     if (xs.readNextStartElement())
         std.cout << qPrintable(xs.name().toString()) << std.endl;
 }

```

这是一个方便的功能，当你只关注与解析XML元素。该[QXmlStream Bookmarks Example](index.htm)大量使用此功能。

此功能被引入Qt的4.6 。

**See also** [readNext](qxmlstreamreader.html#readNext)（ ） 。

```
QXmlStreamReader.setDevice (self, QIODevice device)
```

设置当前设备_device_。设置设备重置流至其初始状态。

**See also** [device](qxmlstreamreader.html#device)（）和[clear](qxmlstreamreader.html#clear)（ ） 。

```
QXmlStreamReader.setEntityResolver (self, QXmlStreamEntityResolver resolver)
```

品牌_resolver_新[entityResolver](qxmlstreamreader.html#entityResolver)（ ） 。

该流读取器呢_not_采取解析器的所有权。这是调用者的责任，以确保解析器是有效的在流读取器对象的整个生命时间，或直到另一个解析器或设定为0 。

此功能被引入Qt的4.4 。

**See also** [entityResolver](qxmlstreamreader.html#entityResolver)（ ） 。

```
QXmlStreamReader.setNamespaceProcessing (self, bool)
```

```
QXmlStreamReader.skipCurrentElement (self)
```

读取，直到当前元素的结尾，跳跃任何子节点。此功能可用于跳过未知的元素非常有用。

当前元素是匹配的，其中一个匹配端元件尚未达到最新分析的开始元素的元素。当解析器已经走到了尽头元素，当前元素变为父元素。

此功能被引入Qt的4.6 。

```
QStringRef QXmlStreamReader.text (self)
```

返回的文本[Characters](qxmlstreamreader.html#TokenType-enum)，[Comment](qxmlstreamreader.html#TokenType-enum)，[DTD](qxmlstreamreader.html#TokenType-enum)或[EntityReference](qxmlstreamreader.html#TokenType-enum)。

```
QString QXmlStreamReader.tokenString (self)
```

返回读写器的当前令牌为字符串。

**See also** [tokenType](qxmlstreamreader.html#tokenType)（ ） 。

```
TokenType QXmlStreamReader.tokenType (self)
```

[

返回当前标记的类型。

](qxmlstreamreader.html#TokenType-enum)

[当前令牌也可以查询的便利功能](qxmlstreamreader.html#TokenType-enum)[isStartDocument](qxmlstreamreader.html#isStartDocument)（ ）[isEndDocument](qxmlstreamreader.html#isEndDocument)（ ）[isStartElement](qxmlstreamreader.html#isStartElement)（ ）[isEndElement](qxmlstreamreader.html#isEndElement)（ ）[isCharacters](qxmlstreamreader.html#isCharacters)（ ）[isComment](qxmlstreamreader.html#isComment)（ ）[isDTD](qxmlstreamreader.html#isDTD)（ ）[isEntityReference](qxmlstreamreader.html#isEntityReference)（）和[isProcessingInstruction](qxmlstreamreader.html#isProcessingInstruction)（ ） 。

**See also** [tokenString](qxmlstreamreader.html#tokenString)（ ） 。