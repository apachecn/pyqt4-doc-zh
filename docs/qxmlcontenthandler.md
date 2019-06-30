# QXmlContentHandler Class Reference

## [[QtXml](index.htm) module]

该QXmlContentHandler类提供了一个接口来报告XML数据的逻辑内容。[More...](#details)

通过继承[QXmlDefaultHandler](qxmldefaulthandler.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QXmlContentHandler)`
*   `bool characters (self, QString ch)`
*   `bool endDocument (self)`
*   `bool endElement (self, QString namespaceURI, QString localName, QString qName)`
*   `bool endPrefixMapping (self, QString prefix)`
*   `QString errorString (self)`
*   `bool ignorableWhitespace (self, QString ch)`
*   `bool processingInstruction (self, QString target, QString data)`
*   `setDocumentLocator (self, QXmlLocator locator)`
*   `bool skippedEntity (self, QString name)`
*   `bool startDocument (self)`
*   `bool startElement (self, QString namespaceURI, QString localName, QString qName, QXmlAttributes atts)`
*   `bool startPrefixMapping (self, QString prefix, QString uri)`

* * *

## Detailed Description

该QXmlContentHandler类提供了一个接口来报告XML数据的逻辑内容。

如果应用程序需要被告知基本解析事件，它可以实现此接口，并使用激活[QXmlReader.setContentHandler](qxmlreader.html#setContentHandler)（ ） 。然后，读者可以像报告通过此接口的开始和元素和字符数据的结束基本文档相关的事件。

在此界面中事件的顺序是非常重要的，反映的信息的顺序在文档本身中。例如，所有的元素的内容（字符数据，处理指令，以及子元素）时，按顺序之间的[startElement](qxmlcontenthandler.html#startElement)（）事件和相应的[endElement](qxmlcontenthandler.html#endElement)（）事件。

类[QXmlDefaultHandler](qxmldefaulthandler.html)提供了该接口的默认实现，从子类[QXmlDefaultHandler](qxmldefaulthandler.html)类是非常方便的，如果你只想要获知一些解析事件。

该[startDocument](qxmlcontenthandler.html#startDocument)（ ）函数被调用的文件的开始，并[endDocument](qxmlcontenthandler.html#endDocument)（）被调用时结束。解析开始之前[setDocumentLocator](qxmlcontenthandler.html#setDocumentLocator)（）被调用。对于每个元素[startElement](qxmlcontenthandler.html#startElement)（）被调用，以[endElement](qxmlcontenthandler.html#endElement)（）被调用时各元件的端部。该[characters](qxmlcontenthandler.html#characters)（ ）函数被调用字符的数据块;[ignorableWhitespace](qxmlcontenthandler.html#ignorableWhitespace)（ ）被调用的空白块，[processingInstruction](qxmlcontenthandler.html#processingInstruction)（ ）被调用，处理指令。如果一个实体被跳过[skippedEntity](qxmlcontenthandler.html#skippedEntity)（）被调用。在前缀的URI范围的开始[startPrefixMapping](qxmlcontenthandler.html#startPrefixMapping)（）被调用。

* * *

## Method Documentation

```
QXmlContentHandler.__init__ (self)
```

```
QXmlContentHandler.__init__ (self, QXmlContentHandler)
```

```
bool QXmlContentHandler.characters (self, QString ch)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用该函数时，它已经被解析的字符数据块（在CDATA节无论是正常的字符数据或字符数据，如果您需要这两种类型之间的区别，您必须使用[QXmlLexicalHandler.startCDATA](qxmllexicalhandler.html#startCDATA)（）和[QXmlLexicalHandler.endCDATA](qxmllexicalhandler.html#endCDATA)（））。字符数据中报告_ch_。

有些读者使用空白报告元素内容中的[ignorableWhitespace](qxmlcontenthandler.html#ignorableWhitespace)（ ）函数，而不是使用这一个。

读者可能会报告在一个以上的块元素的字符数据，如读者可能想报导“ A \u003cB ”的三个字符（ ）事件（ “A” ， “ \u003c ”和“b” ） 。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmlcontenthandler.html#errorString)（ ）来获得错误信息。

```
bool QXmlContentHandler.endDocument (self)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用该函数后，它已完成了解析。这就是所谓的只有一次，而且是所谓的最后一个处理函数。这就是所谓的后读者已经阅读所有输入或已经放弃，因为一个致命的错误解析。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmlcontenthandler.html#errorString)（ ）来获得错误信息。

**See also** [startDocument](qxmlcontenthandler.html#startDocument)（ ） 。

```
bool QXmlContentHandler.endElement (self, QString namespaceURI, QString localName, QString qName)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用该函数时，它已经被解析的限定名结束元素标记_qName_，本地名称_localName_和命名空间URI_namespaceURI_。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmlcontenthandler.html#errorString)（ ）来获得错误信息。

**See also** [startElement](qxmlcontenthandler.html#startElement)（）和[Namespace Support via Features](index.htm#namespace-support-via-features)。

```
bool QXmlContentHandler.endPrefixMapping (self, QString prefix)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用这个函数信号前缀映射为前缀的结束_prefix_。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmlcontenthandler.html#errorString)（ ）来获得错误信息。

**See also** [startPrefixMapping](qxmlcontenthandler.html#startPrefixMapping)（）和[Namespace Support via Features](index.htm#namespace-support-via-features)。

```
QString QXmlContentHandler.errorString (self)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用这个函数来得到一个错误字符串，如如有的处理函数返回False 。

```
bool QXmlContentHandler.ignorableWhitespace (self, QString ch)
```

这种方法是抽象的，应在任何子类中重新实现。

有些读者可能会使用这个功能来报告空白的每个块元素内容。的空白报导在_ch_。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmlcontenthandler.html#errorString)（ ）来获得错误信息。

```
bool QXmlContentHandler.processingInstruction (self, QString target, QString data)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用该函数时，它已经解析的处理指令。

_target_作为处理指令的目标名称和_data_在处理指令的数据。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmlcontenthandler.html#errorString)（ ）来获得错误信息。

```
QXmlContentHandler.setDocumentLocator (self, QXmlLocator locator)
```

这种方法是抽象的，应在任何子类中重新实现。

它开始解析文档之前，读者调用这个函数。这个论点_locator_是一个指针，指向[QXmlLocator](qxmllocator.html)它允许应用程序获取文档中的解析位置。

不破坏_locator_;当阅读器被破坏它被破坏。 （请勿使用_locator_之后，读者被破坏） 。

```
bool QXmlContentHandler.skippedEntity (self, QString name)
```

这种方法是抽象的，应在任何子类中重新实现。

有些读者可能会跳过，如果他们还没有看到声明的实体（例如，因为它们是在外部DTD ） 。如果他们这样做，他们报告说，他们跳过称为实体_name_通过调用这个函数。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmlcontenthandler.html#errorString)（ ）来获得错误信息。

```
bool QXmlContentHandler.startDocument (self)
```

这种方法是抽象的，应在任何子类中重新实现。

当它开始解析文档阅读器调用这个函数。读者调用这个函数只有一次，来电后[setDocumentLocator](qxmlcontenthandler.html#setDocumentLocator)（ ） ，和之前在这个类中，或在任何其他职能[QXmlDTDHandler](qxmldtdhandler.html)类调用。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmlcontenthandler.html#errorString)（ ）来获得错误信息。

**See also** [endDocument](qxmlcontenthandler.html#endDocument)（ ） 。

```
bool QXmlContentHandler.startElement (self, QString namespaceURI, QString localName, QString qName, QXmlAttributes atts)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用该函数时，它已经解析的开始元素标记。

有相应的[endElement](qxmlcontenthandler.html#endElement)（ ）调用时，相应的结束元素标籤被读取。在startElement（）中和[endElement](qxmlcontenthandler.html#endElement)（ ）调用总是正确的嵌套。空元素标籤（例如`&lt;x/&gt;`）引起的startElement （ ）调用将紧跟一个[endElement](qxmlcontenthandler.html#endElement)（ ）调用。

所提供的属性列表仅包含显式值的属性。在属性列表中包含用于命名空间声明属性（即属性开始的xmlns ）只有当读者的命名空间前缀属性为True 。

这个论点_namespaceURI_是命名空间URI ，或一个空字符串，如果该元素没有命名空间URI，如果没有命名空间处理完成。_localName_是本地名称（不带前缀） ，或者如果没有命名空间处理完成一个空字符串，_qName_是限定名称（带有前缀）和_atts_顷的属性附加到元素。如果没有属性，_atts_是一个空的属性对象。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmlcontenthandler.html#errorString)（ ）来获得错误信息。

**See also** [endElement](qxmlcontenthandler.html#endElement)（）和[Namespace Support via Features](index.htm#namespace-support-via-features)。

```
bool QXmlContentHandler.startPrefixMapping (self, QString prefix, QString uri)
```

这种方法是抽象的，应在任何子类中重新实现。

读者调用这个函数信号的前缀， URI命名空间的映射范围开始。这些信息是没有必要的正常的命名空间的处理，因为读者会自动替换为前缀的元素和属性的名称。

注意的startPrefixMapping （）和[endPrefixMapping](qxmlcontenthandler.html#endPrefixMapping)（ ）的调用不能保证正确嵌套相对于对方：对应前发生的所有的startPrefixMapping （ ）事件[startElement](qxmlcontenthandler.html#startElement)（）事件，以及所有[endPrefixMapping](qxmlcontenthandler.html#endPrefixMapping)（ ）对应后发生的事件[endElement](qxmlcontenthandler.html#endElement)（ ）事件，但它们的顺序是没有其他保证。

这个论点_prefix_为命名空间前缀被宣布和参数_uri_是命名空间URI的前缀映射到。

如果这个函数返回False读者停止解析和报告错误。读者使用函数[errorString](qxmlcontenthandler.html#errorString)（ ）来获得错误信息。

**See also** [endPrefixMapping](qxmlcontenthandler.html#endPrefixMapping)（）和[Namespace Support via Features](index.htm#namespace-support-via-features)。