# QXmlLexicalHandler Class Reference

## [[QtXml](index.htm) module]

该QXmlLexicalHandler类提供了一个接口来报告XML数据的词汇内容。[More...](#details)

通过继承[QXmlDefaultHandler](qxmldefaulthandler.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QXmlLexicalHandler)`
*   `bool comment (self, QString ch)`
*   `bool endCDATA (self)`
*   `bool endDTD (self)`
*   `bool endEntity (self, QString name)`
*   `QString errorString (self)`
*   `bool startCDATA (self)`
*   `bool startDTD (self, QString name, QString publicId, QString systemId)`
*   `bool startEntity (self, QString name)`

* * *

## Detailed Description

该QXmlLexicalHandler类提供了一个接口来报告XML数据的词汇内容。

在词法处理程序的事件适用于整个文件，而不仅仅是文档元素，并且所有的词法处理事件的内容处理程序的startDocument和endDocument事件之间出现。

您可以设置词法处理程序[QXmlReader.setLexicalHandler](qxmlreader.html#setLexicalHandler)（ ） 。

此接口的设计是基于SAX2扩展LexicalHandler 。

该接口提供了[startDTD](qxmllexicalhandler.html#startDTD)（ ）[endDTD](qxmllexicalhandler.html#endDTD)（ ）[startEntity](qxmllexicalhandler.html#startEntity)（ ）[endEntity](qxmllexicalhandler.html#endEntity)（ ）[startCDATA](qxmllexicalhandler.html#startCDATA)（ ）[endCDATA](qxmllexicalhandler.html#endCDATA)（）和[comment](qxmllexicalhandler.html#comment)（）函数。

* * *

## Method Documentation

```
QXmlLexicalHandler.__init__ (self)
```

```
QXmlLexicalHandler.__init__ (self, QXmlLexicalHandler)
```

```
bool QXmlLexicalHandler.comment (self, QString ch)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用这个函数的文档中的任意位置报告一个XML注释。它报告的注释文本_ch_。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmllexicalhandler.html#errorString)（ ）来获得错误信息。

```
bool QXmlLexicalHandler.endCDATA (self)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用这个函数来报告CDATA节的结尾。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmllexicalhandler.html#errorString)（ ）来获得错误信息。

**See also** [startCDATA](qxmllexicalhandler.html#startCDATA)（）和[QXmlContentHandler.characters](qxmlcontenthandler.html#characters)（ ） 。

```
bool QXmlLexicalHandler.endDTD (self)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用这个函数来报告的DTD声明的末尾，如果有的话。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmllexicalhandler.html#errorString)（ ）来获得错误信息。

**See also** [startDTD](qxmllexicalhandler.html#startDTD)（ ） 。

```
bool QXmlLexicalHandler.endEntity (self, QString name)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用这个函数来报告称为实体的结束_name_。

对于每一个[startEntity](qxmllexicalhandler.html#startEntity)（ ）调用，有相应endEntity （ ）调用。该呼叫[startEntity](qxmllexicalhandler.html#startEntity)（）和endEntity （ ）是正确嵌套。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmllexicalhandler.html#errorString)（ ）来获得错误信息。

**See also** [startEntity](qxmllexicalhandler.html#startEntity)（ ）[QXmlContentHandler.skippedEntity](qxmlcontenthandler.html#skippedEntity)（）和[QXmlSimpleReader.setFeature](qxmlsimplereader.html#setFeature)（ ） 。

```
QString QXmlLexicalHandler.errorString (self)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用这个函数来得到一个错误字符串，如果任何的处理函数返回False 。

```
bool QXmlLexicalHandler.startCDATA (self)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用这个函数来报告CDATA节的开始。 CDATA节的内容是通过报导[QXmlContentHandler.characters](qxmlcontenthandler.html#characters)（）函数。此功能仅用于报告的边界。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmllexicalhandler.html#errorString)（ ）来获得错误信息。

**See also** [endCDATA](qxmllexicalhandler.html#endCDATA)（ ） 。

```
bool QXmlLexicalHandler.startDTD (self, QString name, QString publicId, QString systemId)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用这个函数来报告的DTD声明的开始，如果有的话。它报告中的文档类型的名称_name_在公共标识符_publicId_和在系统中的标识符_systemId_。

如果公共标识缺失，_publicId_被设置为空字符串。如果系统标识符丢失，_systemId_被设置为空字符串。请注意，这不是有效的XML有一个公共的标识符，但没有系统标识符，在这种情况下，会发生解析错误。

通过报告的所有声明[QXmlDTDHandler](qxmldtdhandler.html) or [QXmlDeclHandler](qxmldeclhandler.html)该startDTD （）之间出现[endDTD](qxmllexicalhandler.html#endDTD)（ ）调用。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmllexicalhandler.html#errorString)（ ）来获得错误信息。

**See also** [endDTD](qxmllexicalhandler.html#endDTD)（ ） 。

```
bool QXmlLexicalHandler.startEntity (self, QString name)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用这个函数来报告称为实体的开始_name_。

请注意，如果该实体是未知的，读者通过它的报告[QXmlContentHandler.skippedEntity](qxmlcontenthandler.html#skippedEntity)（） ，而不是通过这个功能。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmllexicalhandler.html#errorString)（ ）来获得错误信息。

**See also** [endEntity](qxmllexicalhandler.html#endEntity)（）和[QXmlSimpleReader.setFeature](qxmlsimplereader.html#setFeature)（ ） 。