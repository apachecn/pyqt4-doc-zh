# QXmlFormatter Class Reference

## [[QtXmlPatterns](index.htm) module]

该QXmlFormatter类是一个实现[QXmlSerializer](qxmlserializer.html)转化[XQuery](index.htm)输出成XML格式。[More...](#details)

继承[QXmlSerializer](qxmlserializer.html)。

### Methods

*   `__init__ (self, QXmlQuery query, QIODevice outputDevice)`
*   `atomicValue (self, QVariant value)`
*   `attribute (self, QXmlName name, QStringRef value)`
*   `characters (self, QStringRef value)`
*   `comment (self, QString value)`
*   `endDocument (self)`
*   `endElement (self)`
*   `endOfSequence (self)`
*   `int indentationDepth (self)`
*   `processingInstruction (self, QXmlName name, QString value)`
*   `setIndentationDepth (self, int depth)`
*   `startDocument (self)`
*   `startElement (self, QXmlName name)`
*   `startOfSequence (self)`

* * *

## Detailed Description

该QXmlFormatter类是一个实现[QXmlSerializer](qxmlserializer.html)转化[XQuery](index.htm)输出成XML格式。

QXmlFormatter是的一个子类[QXmlSerializer](qxmlserializer.html)该格式化XML输出，以方便人们阅读。

[QXmlSerializer](qxmlserializer.html)输出的XML无需增加不必要的空格。特别是，它不加_newlines_和缩进。为了使XML输出更易于阅读， QXmlFormatter增加_newlines_和缩进通过添加，删除和修改[sequence nodes](qabstractxmlreceiver.html#xquery-sequence)仅包含空白的。它还会修改空格在其他地方是不显着，例如，属性之间以及在文档序幕。

例如，其中基类[QXmlSerializer](qxmlserializer.html)将输出这样的：

```
 <a><b/><c/><p>Some Text</p></a>

```

QXmlFormatter输出这样的：

```
 <a>
    <b/>
    <c/>
    <p>Some Text</p>
 </a>

```

如果你只是想在一个人类可读的格式序列化的XML ，使用QXmlFormatter因为它是。默认的缩进级别为4个空格，但你可以设置你自己的缩进值[setIndentationDepth](qxmlformatter.html#setIndentationDepth)（ ） 。

该_newlines_和缩进由QXmlFormatter加入适用于常见的格式，如XHTML ，SVG或Docbook的，空白的地方不显着。但是，如果你的XML将被用作输入空白的地方是显着，那么你必须编写自己的子类[QXmlSerializer](qxmlserializer.html) or [QAbstractXmlReceiver](qabstractxmlreceiver.html)。

请注意，使用QXmlFormatter代替[QXmlSerializer](qxmlserializer.html)会增加计算开销和存储文件大小，由于空白的插入。

另请注意，缩进风格采用QXmlFormatter保持松散定义和Qt中的未来版本可能会改变。如果一个特定的缩进风格需要那么无论使用基类[QXmlSerializer](qxmlserializer.html)直接，或编写自己的子类[QXmlSerializer](qxmlserializer.html) or [QAbstractXmlReceiver](qabstractxmlreceiver.html)。或者，你可以继承QXmlFormatter和重新实现回调那里。

```
 [QXmlQuery](qxmlquery.html) query;
 query.setQuery("doc('index.html')/html/body/p[1]");

 QXmlFormatter formatter(query, myOutputDevice);
 formatter.setIndentationDepth(2);
 query.evaluateTo(&formatter);

```

* * *

## Method Documentation

```
QXmlFormatter.__init__ (self, QXmlQuery query, QIODevice outputDevice)
```

构造一个使用的名称游泳池和消息处理程序格式化_query_，并把结果写入_outputDevice_作为格式化的XML 。

_outputDevice_被直接传递到[QXmlSerializer](qxmlserializer.html)的构造。

**See also** [QXmlSerializer](qxmlserializer.html)。

```
QXmlFormatter.atomicValue (self, QVariant value)
```

从重新实现[QAbstractXmlReceiver.atomicValue](qabstractxmlreceiver.html#atomicValue)（ ） 。

```
QXmlFormatter.attribute (self, QXmlName name, QStringRef value)
```

```
QXmlFormatter.characters (self, QStringRef value)
```

从重新实现[QAbstractXmlReceiver.characters](qabstractxmlreceiver.html#characters)（ ） 。

```
QXmlFormatter.comment (self, QString value)
```

从重新实现[QAbstractXmlReceiver.comment](qabstractxmlreceiver.html#comment)（ ） 。

```
QXmlFormatter.endDocument (self)
```

从重新实现[QAbstractXmlReceiver.endDocument](qabstractxmlreceiver.html#endDocument)（ ） 。

```
QXmlFormatter.endElement (self)
```

从重新实现[QAbstractXmlReceiver.endElement](qabstractxmlreceiver.html#endElement)（ ） 。

```
QXmlFormatter.endOfSequence (self)
```

从重新实现[QAbstractXmlReceiver.endOfSequence](qabstractxmlreceiver.html#endOfSequence)（ ） 。

```
int QXmlFormatter.indentationDepth (self)
```

返回的空格数[QXmlFormatter](qxmlformatter.html)将输出每个缩进级别。默认值是4 。

**See also** [setIndentationDepth](qxmlformatter.html#setIndentationDepth)（ ） 。

```
QXmlFormatter.processingInstruction (self, QXmlName name, QString value)
```

从重新实现[QAbstractXmlReceiver.processingInstruction](qabstractxmlreceiver.html#processingInstruction)（ ） 。

```
QXmlFormatter.setIndentationDepth (self, int depth)
```

Sets _depth_是的空格数[QXmlFormatter](qxmlformatter.html)将输出缩进的水平。默认值是4 。

**See also** [indentationDepth](qxmlformatter.html#indentationDepth)（ ） 。

```
QXmlFormatter.startDocument (self)
```

从重新实现[QAbstractXmlReceiver.startDocument](qabstractxmlreceiver.html#startDocument)（ ） 。

```
QXmlFormatter.startElement (self, QXmlName name)
```

从重新实现[QAbstractXmlReceiver.startElement](qabstractxmlreceiver.html#startElement)（ ） 。

```
QXmlFormatter.startOfSequence (self)
```

从重新实现[QAbstractXmlReceiver.startOfSequence](qabstractxmlreceiver.html#startOfSequence)（ ） 。