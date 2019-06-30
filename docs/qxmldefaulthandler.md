# QXmlDefaultHandler Class Reference

## [[QtXml](index.htm) module]

该QXmlDefaultHandler类提供了所有的XML处理程序类的默认实现。[More...](#details)

继承[QXmlContentHandler](qxmlcontenthandler.html)，[QXmlErrorHandler](qxmlerrorhandler.html)，[QXmlDTDHandler](qxmldtdhandler.html)，[QXmlEntityResolver](qxmlentityresolver.html)，[QXmlLexicalHandler](qxmllexicalhandler.html)和[QXmlDeclHandler](qxmldeclhandler.html)。

### Methods

*   `__init__ (self)`
*   `bool attributeDecl (self, QString eName, QString aName, QString type, QString valueDefault, QString value)`
*   `bool characters (self, QString ch)`
*   `bool comment (self, QString ch)`
*   `bool endCDATA (self)`
*   `bool endDocument (self)`
*   `bool endDTD (self)`
*   `bool endElement (self, QString namespaceURI, QString localName, QString qName)`
*   `bool endEntity (self, QString name)`
*   `bool endPrefixMapping (self, QString prefix)`
*   `bool error (self, QXmlParseException exception)`
*   `QString errorString (self)`
*   `bool externalEntityDecl (self, QString name, QString publicId, QString systemId)`
*   `bool fatalError (self, QXmlParseException exception)`
*   `bool ignorableWhitespace (self, QString ch)`
*   `bool internalEntityDecl (self, QString name, QString value)`
*   `bool notationDecl (self, QString name, QString publicId, QString systemId)`
*   `bool processingInstruction (self, QString target, QString data)`
*   `(bool, QXmlInputSource ret) resolveEntity (self, QString publicId, QString systemId)`
*   `setDocumentLocator (self, QXmlLocator locator)`
*   `bool skippedEntity (self, QString name)`
*   `bool startCDATA (self)`
*   `bool startDocument (self)`
*   `bool startDTD (self, QString name, QString publicId, QString systemId)`
*   `bool startElement (self, QString namespaceURI, QString localName, QString qName, QXmlAttributes atts)`
*   `bool startEntity (self, QString name)`
*   `bool startPrefixMapping (self, QString prefix, QString uri)`
*   `bool unparsedEntityDecl (self, QString name, QString publicId, QString systemId, QString notationName)`
*   `bool warning (self, QXmlParseException exception)`

* * *

## Detailed Description

该QXmlDefaultHandler类提供了所有的XML处理程序类的默认实现。

这个类聚拢专门的处理程序类的功能，实现自定义处理程序的子类时，使其成为一个方便的起点[QXmlReader](qxmlreader.html)，特别是[QXmlSimpleReader](qxmlsimplereader.html)。从每一个基类的虚函数重新实现这个类，对于很多常见情况提供合理的默认行为。通过继承这个类，并重写这些功能，你可以专注于实现应用程序相关的处理程序的各个部分。

XML读取器必须被告知在分析过程中使用的不同种类的事件的处理程序。这意味着，虽然QXmlDefaultHandler提供的所有基类继承的函数的默认实现，我们仍然可以使用专门的处理程序为特定类型的事件。

例如， QXmlDefaultHandler两个子类[QXmlContentHandler](qxmlcontenthandler.html)和[QXmlErrorHandler](qxmlerrorhandler.html)，所以通过继承它，我们可以使用相同的处理器为以下两个读卡器功能：

```
     xmlReader.setContentHandler(handler);
     xmlReader.setErrorHandler(handler);

```

由于阅读器将通知解析错误的处理程序中，有必要重新实现[QXmlErrorHandler.fatalError](qxmlerrorhandler.html#fatalError)（ ）如果，例如，我们想停止这样的时候发生错误解析：

```
 bool Handler.fatalError (const [QXmlParseException](qxmlparseexception.html) & exception)
 {
     qWarning() << "Fatal error on line" << exception.lineNumber()
                << ", column" << exception.columnNumber() << ":"
                << exception.message();

     return false;
 }

```

上面的函数返回False ，它告诉读者停止解析。继续使用相同的阅读器，就必须建立新的处理程序实例，并且设置了阅读器把它用在上面描述的方式。

重要的是要研究一些继承QXmlDefaultHandler的功能，并考虑他们为什么会在自定义处理程序来重新实现是非常有用的。自定义处理程序通常会重新实现[QXmlContentHandler.startDocument](qxmlcontenthandler.html#startDocument)（ ）准备处理程序的新内容。文档中的元素和其中的文本可以通过重新实现处理[QXmlContentHandler.startElement](qxmlcontenthandler.html#startElement)（ ）[QXmlContentHandler.endElement](qxmlcontenthandler.html#endElement)（）和[QXmlContentHandler.characters](qxmlcontenthandler.html#characters)（ ） 。您可能需要重新实现[QXmlContentHandler.endDocument](qxmlcontenthandler.html#endDocument)（）来对内容进行一些最后确定或验证，一旦该文件已被完全读取。

* * *

## Method Documentation

```
QXmlDefaultHandler.__init__ (self)
```

构造一个处理程序与子类使用[QXmlReader](qxmlreader.html)。

```
bool QXmlDefaultHandler.attributeDecl (self, QString eName, QString aName, QString type, QString valueDefault, QString value)
```

从重新实现[QXmlDeclHandler.attributeDecl](qxmldeclhandler.html#attributeDecl)（ ） 。

这个重新实现不执行任何操作。

```
bool QXmlDefaultHandler.characters (self, QString ch)
```

从重新实现[QXmlContentHandler.characters](qxmlcontenthandler.html#characters)（ ） 。

这个重新实现不执行任何操作。

```
bool QXmlDefaultHandler.comment (self, QString ch)
```

从重新实现[QXmlLexicalHandler.comment](qxmllexicalhandler.html#comment)（ ） 。

这个重新实现不执行任何操作。

```
bool QXmlDefaultHandler.endCDATA (self)
```

从重新实现[QXmlLexicalHandler.endCDATA](qxmllexicalhandler.html#endCDATA)（ ） 。

这个重新实现不执行任何操作。

```
bool QXmlDefaultHandler.endDocument (self)
```

从重新实现[QXmlContentHandler.endDocument](qxmlcontenthandler.html#endDocument)（ ） 。

这个重新实现不执行任何操作。

```
bool QXmlDefaultHandler.endDTD (self)
```

从重新实现[QXmlLexicalHandler.endDTD](qxmllexicalhandler.html#endDTD)（ ） 。

这个重新实现不执行任何操作。

```
bool QXmlDefaultHandler.endElement (self, QString namespaceURI, QString localName, QString qName)
```

从重新实现[QXmlContentHandler.endElement](qxmlcontenthandler.html#endElement)（ ） 。

这个重新实现不执行任何操作。

```
bool QXmlDefaultHandler.endEntity (self, QString name)
```

从重新实现[QXmlLexicalHandler.endEntity](qxmllexicalhandler.html#endEntity)（ ） 。

这个重新实现不执行任何操作。

```
bool QXmlDefaultHandler.endPrefixMapping (self, QString prefix)
```

从重新实现[QXmlContentHandler.endPrefixMapping](qxmlcontenthandler.html#endPrefixMapping)（ ） 。

这个重新实现不执行任何操作。

```
bool QXmlDefaultHandler.error (self, QXmlParseException exception)
```

从重新实现[QXmlErrorHandler.error](qxmlerrorhandler.html#error)（ ） 。

这个重新实现不执行任何操作。

```
QString QXmlDefaultHandler.errorString (self)
```

从重新实现[QXmlContentHandler.errorString](qxmlcontenthandler.html#errorString)（ ） 。

返回默认的错误字符串。

```
bool QXmlDefaultHandler.externalEntityDecl (self, QString name, QString publicId, QString systemId)
```

从重新实现[QXmlDeclHandler.externalEntityDecl](qxmldeclhandler.html#externalEntityDecl)（ ） 。

这个重新实现不执行任何操作。

```
bool QXmlDefaultHandler.fatalError (self, QXmlParseException exception)
```

从重新实现[QXmlErrorHandler.fatalError](qxmlerrorhandler.html#fatalError)（ ） 。

这个重新实现不执行任何操作。

```
bool QXmlDefaultHandler.ignorableWhitespace (self, QString ch)
```

从重新实现[QXmlContentHandler.ignorableWhitespace](qxmlcontenthandler.html#ignorableWhitespace)（ ） 。

这个重新实现不执行任何操作。

```
bool QXmlDefaultHandler.internalEntityDecl (self, QString name, QString value)
```

从重新实现[QXmlDeclHandler.internalEntityDecl](qxmldeclhandler.html#internalEntityDecl)（ ） 。

这个重新实现不执行任何操作。

```
bool QXmlDefaultHandler.notationDecl (self, QString name, QString publicId, QString systemId)
```

从重新实现[QXmlDTDHandler.notationDecl](qxmldtdhandler.html#notationDecl)（ ） 。

这个重新实现不执行任何操作。

```
bool QXmlDefaultHandler.processingInstruction (self, QString target, QString data)
```

从重新实现[QXmlContentHandler.processingInstruction](qxmlcontenthandler.html#processingInstruction)（ ） 。

这个重新实现不执行任何操作。

```
(bool, QXmlInputSource ret) QXmlDefaultHandler.resolveEntity (self, QString publicId, QString systemId)
```

从重新实现[QXmlEntityResolver.resolveEntity](qxmlentityresolver.html#resolveEntity)（ ） 。

Sets _ret_为0，从而使读取器使用的XML文件中提供的系统标识符。

```
QXmlDefaultHandler.setDocumentLocator (self, QXmlLocator locator)
```

从重新实现[QXmlContentHandler.setDocumentLocator](qxmlcontenthandler.html#setDocumentLocator)（ ） 。

这个重新实现不执行任何操作。

```
bool QXmlDefaultHandler.skippedEntity (self, QString name)
```

从重新实现[QXmlContentHandler.skippedEntity](qxmlcontenthandler.html#skippedEntity)（ ） 。

这个重新实现不执行任何操作。

```
bool QXmlDefaultHandler.startCDATA (self)
```

从重新实现[QXmlLexicalHandler.startCDATA](qxmllexicalhandler.html#startCDATA)（ ） 。

这个重新实现不执行任何操作。

```
bool QXmlDefaultHandler.startDocument (self)
```

从重新实现[QXmlContentHandler.startDocument](qxmlcontenthandler.html#startDocument)（ ） 。

这个重新实现不执行任何操作。

```
bool QXmlDefaultHandler.startDTD (self, QString name, QString publicId, QString systemId)
```

从重新实现[QXmlLexicalHandler.startDTD](qxmllexicalhandler.html#startDTD)（ ） 。

这个重新实现不执行任何操作。

```
bool QXmlDefaultHandler.startElement (self, QString namespaceURI, QString localName, QString qName, QXmlAttributes atts)
```

从重新实现[QXmlContentHandler.startElement](qxmlcontenthandler.html#startElement)（ ） 。

这个重新实现不执行任何操作。

```
bool QXmlDefaultHandler.startEntity (self, QString name)
```

从重新实现[QXmlLexicalHandler.startEntity](qxmllexicalhandler.html#startEntity)（ ） 。

这个重新实现不执行任何操作。

```
bool QXmlDefaultHandler.startPrefixMapping (self, QString prefix, QString uri)
```

从重新实现[QXmlContentHandler.startPrefixMapping](qxmlcontenthandler.html#startPrefixMapping)（ ） 。

这个重新实现不执行任何操作。

```
bool QXmlDefaultHandler.unparsedEntityDecl (self, QString name, QString publicId, QString systemId, QString notationName)
```

从重新实现[QXmlDTDHandler.unparsedEntityDecl](qxmldtdhandler.html#unparsedEntityDecl)（ ） 。

这个重新实现不执行任何操作。

```
bool QXmlDefaultHandler.warning (self, QXmlParseException exception)
```

从重新实现[QXmlErrorHandler.warning](qxmlerrorhandler.html#warning)（ ） 。

这个重新实现不执行任何操作。