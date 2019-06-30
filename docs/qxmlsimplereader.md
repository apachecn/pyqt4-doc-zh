# QXmlSimpleReader Class Reference

## [[QtXml](index.htm) module]

该QXmlSimpleReader类提供了一个简单的XML解析器的实现。[More...](#details)

继承[QXmlReader](qxmlreader.html)。

### Methods

*   `__init__ (self)`
*   `QXmlContentHandler contentHandler (self)`
*   `QXmlDeclHandler declHandler (self)`
*   `QXmlDTDHandler DTDHandler (self)`
*   `QXmlEntityResolver entityResolver (self)`
*   `QXmlErrorHandler errorHandler (self)`
*   `(bool, bool ok) feature (self, QString name)`
*   `bool hasFeature (self, QString name)`
*   `bool hasProperty (self, QString name)`
*   `QXmlLexicalHandler lexicalHandler (self)`
*   `bool parse (self, QXmlInputSource input)`
*   `bool parse (self, QXmlInputSource input, bool incremental)`
*   `bool parseContinue (self)`
*   `(sip.voidptr, bool ok) property (self, QString name)`
*   `setContentHandler (self, QXmlContentHandler handler)`
*   `setDeclHandler (self, QXmlDeclHandler handler)`
*   `setDTDHandler (self, QXmlDTDHandler handler)`
*   `setEntityResolver (self, QXmlEntityResolver handler)`
*   `setErrorHandler (self, QXmlErrorHandler handler)`
*   `setFeature (self, QString name, bool value)`
*   `setLexicalHandler (self, QXmlLexicalHandler handler)`
*   `setProperty (self, QString name, sip.voidptr value)`

* * *

## Detailed Description

该QXmlSimpleReader类提供了一个简单的XML解析器的实现。

这个XML阅读器是适用于广泛的应用范围。它能够解析格式良好的XML ，并可以报告元素的命名空间的内容处理程序，但是，它不解析任何外部实体。由于历史的原因，属性值规范化和最终的线在不执行1.0规范的XML描述的处理。

使用这个类的最简单的模式是创建一个读取器实例，定义一个输入源，指定要使用的阅读器的处理程序，并解析数据。

例如，我们可以使用一个[QFile](qfile.html)提供输入。这里，我们创建了一个阅读器，并定义要使用的读取器输入源：

```
     QXmlSimpleReader xmlReader;
     [QXmlInputSource](qxmlinputsource.html) *source = new [QXmlInputSource](qxmlinputsource.html)(file);

```

处理程序可以让我们执行操作时，读写器遇到某些类型的内容，或者如果被发现的输入错误。读者必须被告知要使用的每种类型的事件的处理程序。对于许多常见的应用，我们可以通过继承创建一个自定义处理程序[QXmlDefaultHandler](qxmldefaulthandler.html)，并以此来处理错误和内容的事件：

```
     Handler *handler = new Handler;
     xmlReader.setContentHandler(handler);
     xmlReader.setErrorHandler(handler);

```

如果你不至少设置的内容和错误处理程序，解析器会回到属于它的默认行为---并不会做任何事。

最方便的方法来处理输入是用来阅读它在一个单一的通行证[parse](qxmlsimplereader.html#parse)（有一个参数，指定输入源）函数：

```
     bool ok = xmlReader.parse(source);

     if (!ok)
         std.cout << "Parsing failed." << std.endl;

```

如果您无法解析整个输入一次过（例如，它是巨大的，或者被传递通过网络连接） ，数据可以在块被送入分析器。这是通过告诉实现[parse](qxmlsimplereader.html#parse)（ ）以增量方式工作，使得后续调用[parseContinue](qxmlsimplereader.html#parseContinue)（）函数，直到所有的数据已经被处理。

执行增量分析的一种常用方法是连接`readyRead()`的一个信号[network reply](qnetworkreply.html)一个时隙，并且有处理接收的数据。看[QNetworkAccessManager](qnetworkaccessmanager.html)。

解析行为的某些方面可以用适应[setFeature](qxmlsimplereader.html#setFeature)（）和[setProperty](qxmlsimplereader.html#setProperty)（ ） 。

```
 xmlReader.setFeature("http://xml.org/sax/features/namespace-prefixes", true);

```

QXmlSimpleReader是不可重入的。如果你想使用这个类在线程代码，使用QXmlSimpleReader具有锁定机构，如锁码[QMutex](qmutex.html)。

* * *

## Method Documentation

```
QXmlSimpleReader.__init__ (self)
```

构造一个简单的XML阅读器。

```
QXmlContentHandler QXmlSimpleReader.contentHandler (self)
```

[](qxmlcontenthandler.html)

[从重新实现](qxmlcontenthandler.html)[QXmlReader.contentHandler](qxmlreader.html#contentHandler)（ ） 。

**See also** [setContentHandler](qxmlsimplereader.html#setContentHandler)（ ） 。

```
QXmlDeclHandler QXmlSimpleReader.declHandler (self)
```

[](qxmldeclhandler.html)

[从重新实现](qxmldeclhandler.html)[QXmlReader.declHandler](qxmlreader.html#declHandler)（ ） 。

**See also** [setDeclHandler](qxmlsimplereader.html#setDeclHandler)（ ） 。

```
QXmlDTDHandler QXmlSimpleReader.DTDHandler (self)
```

[](qxmldtdhandler.html)

[从重新实现](qxmldtdhandler.html)[QXmlReader.DTDHandler](qxmlreader.html#DTDHandler)（ ） 。

**See also** [setDTDHandler](qxmlsimplereader.html#setDTDHandler)（ ） 。

```
QXmlEntityResolver QXmlSimpleReader.entityResolver (self)
```

[](qxmlentityresolver.html)

[从重新实现](qxmlentityresolver.html)[QXmlReader.entityResolver](qxmlreader.html#entityResolver)（ ） 。

**See also** [setEntityResolver](qxmlsimplereader.html#setEntityResolver)（ ） 。

```
QXmlErrorHandler QXmlSimpleReader.errorHandler (self)
```

[](qxmlerrorhandler.html)

[从重新实现](qxmlerrorhandler.html)[QXmlReader.errorHandler](qxmlreader.html#errorHandler)（ ） 。

**See also** [setErrorHandler](qxmlsimplereader.html#setErrorHandler)（ ） 。

```
(bool, bool ok) QXmlSimpleReader.feature (self, QString name)
```

从重新实现[QXmlReader.feature](qxmlreader.html#feature)（ ） 。

**See also** [setFeature](qxmlsimplereader.html#setFeature)（ ） 。

```
bool QXmlSimpleReader.hasFeature (self, QString name)
```

从重新实现[QXmlReader.hasFeature](qxmlreader.html#hasFeature)（ ） 。

```
bool QXmlSimpleReader.hasProperty (self, QString name)
```

从重新实现[QXmlReader.hasProperty](qxmlreader.html#hasProperty)（ ） 。

```
QXmlLexicalHandler QXmlSimpleReader.lexicalHandler (self)
```

[](qxmllexicalhandler.html)

[从重新实现](qxmllexicalhandler.html)[QXmlReader.lexicalHandler](qxmlreader.html#lexicalHandler)（ ） 。

**See also** [setLexicalHandler](qxmlsimplereader.html#setLexicalHandler)（ ） 。

```
bool QXmlSimpleReader.parse (self, QXmlInputSource input)
```

从重新实现[QXmlReader.parse](index.htm#parse-2)（ ） 。

```
bool QXmlSimpleReader.parse (self, QXmlInputSource input, bool incremental)
```

从重新实现[QXmlReader.parse](qxmlreader.html#parse)（ ） 。

读取从XML文档_input_并分析它在一次通过（非增量） 。返回True如果解析成功，否则返回False 。

```
bool QXmlSimpleReader.parseContinue (self)
```

继续增量分析，从获取输入[QXmlInputSource](qxmlinputsource.html)这是与最近一次调用中指定[parse](qxmlsimplereader.html#parse)（ ） 。要使用此功能，您_must_呼吁[parse](qxmlsimplereader.html#parse)（）设置为True增量参数。

如果发生解析错误，则返回False ，否则返回True ，即使XML文件的结尾还没有达到。您可以通过再次调用这个函数当有可用来分析更多的数据继续分析在后一阶段。

调用此函数时，有一个在输入源中没有数据表明该XML文件的末尾已到达读者。如果提供了该点的输入是没有很好地形成则发生解析错误，并返回False 。如果提供的输入是良好的，则返回True 。它结束的输入以这种方式，因为它允许您重用读者解析其他XML文件是很重要的。

调用此函数文件的末尾已到达之后，但没有可用的数据会导致错误要返回前一个输入是否是格式良好的或没有。

**See also** [parse](qxmlsimplereader.html#parse)（ ）[QXmlInputSource.data](qxmlinputsource.html#data)（）和[QXmlInputSource.next](qxmlinputsource.html#next)（ ） 。

```
(sip.voidptr, bool ok) QXmlSimpleReader.property (self, QString name)
```

从重新实现[QXmlReader.property](qxmlreader.html#property)（ ） 。

**See also** [setProperty](qxmlsimplereader.html#setProperty)（ ） 。

```
QXmlSimpleReader.setContentHandler (self, QXmlContentHandler handler)
```

从重新实现[QXmlReader.setContentHandler](qxmlreader.html#setContentHandler)（ ） 。

**See also** [contentHandler](qxmlsimplereader.html#contentHandler)（ ） 。

```
QXmlSimpleReader.setDeclHandler (self, QXmlDeclHandler handler)
```

从重新实现[QXmlReader.setDeclHandler](qxmlreader.html#setDeclHandler)（ ） 。

**See also** [declHandler](qxmlsimplereader.html#declHandler)（ ） 。

```
QXmlSimpleReader.setDTDHandler (self, QXmlDTDHandler handler)
```

从重新实现[QXmlReader.setDTDHandler](qxmlreader.html#setDTDHandler)（ ） 。

```
QXmlSimpleReader.setEntityResolver (self, QXmlEntityResolver handler)
```

从重新实现[QXmlReader.setEntityResolver](qxmlreader.html#setEntityResolver)（ ） 。

**See also** [entityResolver](qxmlsimplereader.html#entityResolver)（ ） 。

```
QXmlSimpleReader.setErrorHandler (self, QXmlErrorHandler handler)
```

从重新实现[QXmlReader.setErrorHandler](qxmlreader.html#setErrorHandler)（ ） 。

**See also** [errorHandler](qxmlsimplereader.html#errorHandler)（ ） 。

```
QXmlSimpleReader.setFeature (self, QString name, bool value)
```

从重新实现[QXmlReader.setFeature](qxmlreader.html#setFeature)（ ） 。

打开该功能_name_如果_enable_为True，否则将其关闭。

该_name_参数必须是下列字符串之一：

| Feature | Default | Notes |
| --- | --- | --- |
| _http://xml.org/sax/features/namespaces_ | true | If enabled, namespaces are reported to the content handler. |
| _http://xml.org/sax/features/namespace-prefixes_ | false | If enabled, the original prefixed names and attributes used for namespace declarations are reported. |
| _http://trolltech.com/xml/features/report-whitespace-only-CharData_ | true | If enabled, CharData that consist of only whitespace characters are reported using [QXmlContentHandler.characters](qxmlcontenthandler.html#characters)(). If disabled, whitespace is silently discarded. |
| _http://trolltech.com/xml/features/report-start-end-entity_ | false | If enabled, the parser reports QXmlContentHandler.startEntity() and QXmlContentHandler.endEntity() events, so character data might be reported in chunks. If disabled, the parser does not report these events, but silently substitutes the entities, and reports the character data in one chunk. |

**See also** [feature](qxmlsimplereader.html#feature)（ ）[hasFeature](qxmlsimplereader.html#hasFeature)（）和[SAX2 Features](index.htm#sax2-features)。

```
QXmlSimpleReader.setLexicalHandler (self, QXmlLexicalHandler handler)
```

从重新实现[QXmlReader.setLexicalHandler](qxmlreader.html#setLexicalHandler)（ ） 。

**See also** [lexicalHandler](qxmlsimplereader.html#lexicalHandler)（ ） 。

```
QXmlSimpleReader.setProperty (self, QString name, sip.voidptr value)
```

从重新实现[QXmlReader.setProperty](qxmlreader.html#setProperty)（ ） 。

**See also** [property](qxmlsimplereader.html#property)（ ） 。