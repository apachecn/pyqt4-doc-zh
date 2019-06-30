# QXmlSerializer Class Reference

## [[QtXmlPatterns](index.htm) module]

该QXmlSerializer类是一个实现[QAbstractXmlReceiver](qabstractxmlreceiver.html)转化[XQuery](index.htm)输出为未格式化的XML 。[More...](#details)

继承[QAbstractXmlReceiver](qabstractxmlreceiver.html)。

通过继承[QXmlFormatter](qxmlformatter.html)。

### Methods

*   `__init__ (self, QXmlQuery query, QIODevice outputDevice)`
*   `atomicValue (self, QVariant value)`
*   `attribute (self, QXmlName name, QStringRef value)`
*   `characters (self, QStringRef value)`
*   `QTextCodec codec (self)`
*   `comment (self, QString value)`
*   `endDocument (self)`
*   `endElement (self)`
*   `endOfSequence (self)`
*   `namespaceBinding (self, QXmlName nb)`
*   `QIODevice outputDevice (self)`
*   `processingInstruction (self, QXmlName name, QString value)`
*   `setCodec (self, QTextCodec codec)`
*   `startDocument (self)`
*   `startElement (self, QXmlName name)`
*   `startOfSequence (self)`

* * *

## Detailed Description

该QXmlSerializer类是一个实现[QAbstractXmlReceiver](qabstractxmlreceiver.html)转化[XQuery](index.htm)输出为未格式化的XML 。

QXmlSerializer的翻译[XQuery sequence](qabstractxmlreceiver.html#xquery-sequence)，一个通常的输出[QXmlQuery](qxmlquery.html)，转换成XML 。考虑例子：

```
 [QXmlQuery](qxmlquery.html) query;
 query.setQuery("doc('index.html')/html/body/p[1]");

 QXmlSerializer serializer(query, myOutputDevice);
 query.evaluateTo(&serializer);

```

首先它构造一个[query](qxmlquery.html)这会从文档的第一段`index.html`。然后，它会构造这个类的一个实例与[query](qxmlquery.html)和[myOutputDevice](qiodevice.html)。最后，它[evaluates](qxmlquery.html#evaluateTo)该[query](qxmlquery.html)，产生呼叫到串行器的回调函数的有序序列。回调的序列转换查询输出到XML ，并将其写入到[myOutputDevice](qiodevice.html)。

QXmlSerializer将：

*   Declare namespaces when needed,
*   Use appropriate escaping, when characters can't be represented in the XML,
*   Handle line endings appropriately,
*   Report errors, when it can't serialize the content, e.g., when asked to serialize an attribute that is a top-level node, or when more than one top-level element is encountered.

如果序列化过程中发生错误，结果是不确定的，除非该串行器通过调用驱动[QXmlQuery.evaluateTo](qxmlquery.html#evaluateTo)（ ） 。

如果生成的XML应当缩进和格式化的阅读，使用[QXmlFormatter](qxmlformatter.html)。

* * *

## Method Documentation

```
QXmlSerializer.__init__ (self, QXmlQuery query, QIODevice outputDevice)
```

构造一个使用的名称游泳池和消息处理程序序列化_query_，并写入到输出_outputDevice_。

_outputDevice_必须是有效的，非空的设备处于写模式打开，否则行为是未定义的。

_outputDevice_不得开[QIODevice.Text](qiodevice.html#OpenModeFlag-enum)因为这将导致输出不正确。本课程将确保行结束被序列化为符合XML规范。[QXmlSerializer](qxmlserializer.html)不采取所有权_outputDevice_。

```
QXmlSerializer.atomicValue (self, QVariant value)
```

从重新实现[QAbstractXmlReceiver.atomicValue](qabstractxmlreceiver.html#atomicValue)（ ） 。

```
QXmlSerializer.attribute (self, QXmlName name, QStringRef value)
```

```
QXmlSerializer.characters (self, QStringRef value)
```

从重新实现[QAbstractXmlReceiver.characters](qabstractxmlreceiver.html#characters)（ ） 。

```
QTextCodec QXmlSerializer.codec (self)
```

[

返回正在使用的序列，它的XML输出编码的编解码器。

](qtextcodec.html)

[**See also**](qtextcodec.html) [setCodec](qxmlserializer.html#setCodec)（ ） 。

```
QXmlSerializer.comment (self, QString value)
```

从重新实现[QAbstractXmlReceiver.comment](qabstractxmlreceiver.html#comment)（ ） 。

```
QXmlSerializer.endDocument (self)
```

从重新实现[QAbstractXmlReceiver.endDocument](qabstractxmlreceiver.html#endDocument)（ ） 。

```
QXmlSerializer.endElement (self)
```

从重新实现[QAbstractXmlReceiver.endElement](qabstractxmlreceiver.html#endElement)（ ） 。

```
QXmlSerializer.endOfSequence (self)
```

从重新实现[QAbstractXmlReceiver.endOfSequence](qabstractxmlreceiver.html#endOfSequence)（ ） 。

```
QXmlSerializer.namespaceBinding (self, QXmlName nb)
```

从重新实现[QAbstractXmlReceiver.namespaceBinding](qabstractxmlreceiver.html#namespaceBinding)（ ） 。

```
QIODevice QXmlSerializer.outputDevice (self)
```

[

将指针返回到输出设备。没有相应的功能，以_set_输出设备，因为输出设备必须传递给构造函数。该串行器并不需要它的IO设备的所有权。

```
QXmlSerializer.processingInstruction (self, QXmlName name, QString value)
```

](qiodevice.html)

[从重新实现](qiodevice.html)[QAbstractXmlReceiver.processingInstruction](qabstractxmlreceiver.html#processingInstruction)（ ） 。

```
QXmlSerializer.setCodec (self, QTextCodec codec)
```

设置编解码器串行器将用于其XML输出编码。输出的编解码器被设置为_outputCodec_。默认情况下，输出的编解码器被设置为一个用于`UTF-8`。该串行器并不需要编解码器的所有权。

**See also** [codec](qxmlserializer.html#codec)（ ） 。

```
QXmlSerializer.startDocument (self)
```

从重新实现[QAbstractXmlReceiver.startDocument](qabstractxmlreceiver.html#startDocument)（ ） 。

```
QXmlSerializer.startElement (self, QXmlName name)
```

从重新实现[QAbstractXmlReceiver.startElement](qabstractxmlreceiver.html#startElement)（ ） 。

```
QXmlSerializer.startOfSequence (self)
```

从重新实现[QAbstractXmlReceiver.startOfSequence](qabstractxmlreceiver.html#startOfSequence)（ ） 。