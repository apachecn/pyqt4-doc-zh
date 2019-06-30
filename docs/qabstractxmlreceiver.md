# QAbstractXmlReceiver Class Reference

## [[QtXmlPatterns](index.htm) module]

该QAbstractXmlReceiver类提供了一个回调接口，用于将一个输出[QXmlQuery](qxmlquery.html)。[More...](#details)

通过继承[QXmlSerializer](qxmlserializer.html)。

### Methods

*   `__init__ (self)`
*   `atomicValue (self, QVariant value)`
*   `attribute (self, QXmlName name, QStringRef value)`
*   `characters (self, QStringRef value)`
*   `comment (self, QString value)`
*   `endDocument (self)`
*   `endElement (self)`
*   `endOfSequence (self)`
*   `namespaceBinding (self, QXmlName name)`
*   `processingInstruction (self, QXmlName target, QString value)`
*   `startDocument (self)`
*   `startElement (self, QXmlName name)`
*   `startOfSequence (self)`

* * *

## Detailed Description

该QAbstractXmlReceiver类提供了一个回调接口，用于将一个输出[QXmlQuery](qxmlquery.html)。

QAbstractXmlReceiver是提供一个回调接口的抽象基类，用于接收[XQuery sequence](#xquery-sequence)，一个通常的输出[QXmlQuery](qxmlquery.html)和转化的顺序为您选择，通常是XML的结构。考虑例子：

```
 [QXmlQuery](qxmlquery.html) query;
 query.setQuery("doc('index.html')/html/body/p[1]");

 [QXmlSerializer](qxmlserializer.html) serializer(query, myOutputDevice);
 query.evaluateTo(&serializer);

```

首先它构造一个[query](qxmlquery.html)这会从文档的第一段`index.html`。然后，它构造了一个[XML serializer](qxmlserializer.html)与[query](qxmlquery.html)和[myOutputDevice](qiodevice.html)（请注意[serializer](qxmlserializer.html)是_XML receiver_，即QAbstractXmlReceiver的一个子类） 。最后，它[evaluates](qxmlquery.html#evaluateTo)该[query](qxmlquery.html)，生产调用的有序序列[serializer's](qxmlserializer.html)回调函数。回调的序列转换查询输出到XML ，并将其写入到[myOutputDevice](qiodevice.html)。

虽然该示例使用[QXmlQuery](qxmlquery.html)产生回调到QAbstractXmlReceiver功能的序列，可以直接，只要你的电话的序列代表一个有效的调用回调函数[XQuery sequence](#xquery-sequence)。

### XQuery Sequences

一个[XQuery](index.htm) _sequence_是零的有序集合，一个或多个_items_。每_item_或者是一个_atomic value_或_node_。一个_atomic value_是一个简单的数据值。

有6种_nodes_。

*   An _Element Node_ represents an XML element.
*   An _Attribute Node_ represents an XML attribute.
*   A _Document Node_ represents an entire XML document.
*   A _Text Node_ represents character data (element content).
*   A _Processing Instruction Node_ represents an XML processing instruction, which is used in an XML document to tell the application reading the document to perform some action. A typical example is to use a processing instruction to tell the application to use a particular XSLT stylesheet to display the document.
*   And a _Comment node_ represents an XML comment.

该_sequence_的_nodes_和_atomic values_遵循以下规则。需要注意的是_Namespace Node_指的是一种特殊的_Attribute Node_与名_xmlns_。

*   Each _node_ appears in the _sequence_ before its children and their descendants appear.
*   A _node_'s descendants appear in the _sequence_ before any of its siblings appear.
*   A _Document Node_ represents an entire document. Zero or more _Document Nodes_ can appear in a _sequence_, but they can only be top level items (i.e., a _Document Node_ can't be a child of another _node_.
*   _Namespace Nodes_ immediately follow the _Element Node_ with which they are associated.
*   _Attribute Nodes_ immediately follow the _Namespace Nodes_ of the element with which they are associated, or...
*   If there are no _Namespace Nodes_ following an element, then the _Attribute Nodes_ immediately follow the element.
*   An _atomic value_ can only appear as a top level _item_, i.e., it can't appear as a child of a _node_.
*   _Processing Instruction Nodes_ do not have children, and their parent is either a _Document Node_ or an _Element Node_.
*   _Comment Nodes_ do not have children, and their parent is either a _Document Node_ or an _Element Node_.

该_sequence_的_nodes_和_atomic values_被发送到一个QAbstractXmlReceiver （[QXmlSerializer](qxmlserializer.html)在上面的例子）作为呼叫接收器的回调函数的序列。的回调函数序列的项目的映射如下。

*   [startDocument](qabstractxmlreceiver.html#startDocument)() and [endDocument](qabstractxmlreceiver.html#endDocument)() are called for each _Document Node_ in the _sequence_. [endDocument](qabstractxmlreceiver.html#endDocument)() is not called until all the _Document Node's_ children have appeared in the _sequence_.
*   [startElement](qabstractxmlreceiver.html#startElement)() and [endElement](qabstractxmlreceiver.html#endElement)() are called for each _Element Node_. [endElement](qabstractxmlreceiver.html#endElement)() is not called until all the _Element Node's_ children have appeared in the _sequence_.
*   [attribute](qabstractxmlreceiver.html#attributex)() is called for each _Attribute Node_.
*   [comment](qabstractxmlreceiver.html#comment)() is called for each _Comment Node_.
*   [characters](qabstractxmlreceiver.html#characters)() is called for each _Text Node_.
*   [processingInstruction](qabstractxmlreceiver.html#processingInstruction)() is called for each _Processing Instruction Node_.
*   [namespaceBinding](qabstractxmlreceiver.html#namespaceBinding)() is called for each _Namespace Node_.
*   [atomicValue](qabstractxmlreceiver.html#atomicValue)() is called for each _atomic value_.

对于一个完整的解释[XQuery](index.htm)序列，请访问[XQuery Data Model](http://www.w3.org/TR/xpath-datamodel/)。

* * *

## Method Documentation

```
QAbstractXmlReceiver.__init__ (self)
```

构造一个抽象的XML接收器。

```
QAbstractXmlReceiver.atomicValue (self, QVariant value)
```

这种方法是抽象的，应在任何子类中重新实现。

当一个原子值出现在这个回调函数被调用[sequence](qabstractxmlreceiver.html#xquery-sequence)。该_value_是一个简单的[data value](qvariant.html)。它是保证[valid](qvariant.html#isValid)。

```
QAbstractXmlReceiver.attribute (self, QXmlName name, QStringRef value)
```

这种方法是抽象的，应在任何子类中重新实现。

```
QAbstractXmlReceiver.characters (self, QStringRef value)
```

这种方法是抽象的，应在任何子类中重新实现。

当一个文本节点会出现在这个回调函数被调用[sequence](qabstractxmlreceiver.html#xquery-sequence)。该_value_包含的文本。相邻的文本节点可能不会出现在[sequence](qabstractxmlreceiver.html#xquery-sequence)，也就是说，这个回调不能说是连续两次。

```
QAbstractXmlReceiver.comment (self, QString value)
```

这种方法是抽象的，应在任何子类中重新实现。

当一个注释节点会出现在这个回调函数被调用[sequence](qabstractxmlreceiver.html#xquery-sequence)。该_value_是注释文本，其中不得包含字符串“ - ” 。

```
QAbstractXmlReceiver.endDocument (self)
```

这种方法是抽象的，应在任何子类中重新实现。

当一个文档节点的末尾会出现在这个回调函数被调用[sequence](qabstractxmlreceiver.html#xquery-sequence)。

```
QAbstractXmlReceiver.endElement (self)
```

这种方法是抽象的，应在任何子类中重新实现。

当一个元素节点的结尾会出现在这个回调函数被调用[sequence](qabstractxmlreceiver.html#xquery-sequence)。

```
QAbstractXmlReceiver.endOfSequence (self)
```

这种方法是抽象的，应在任何子类中重新实现。

此回调被调用一次只，右后[sequence](qabstractxmlreceiver.html#xquery-sequence)结束。

```
QAbstractXmlReceiver.namespaceBinding (self, QXmlName name)
```

这种方法是抽象的，应在任何子类中重新实现。

此回调被调用时，一个命名空间绑定在元素的范围。命名空间是由一个URI来定义。在[QXmlName](qxmlname.html) _name_，的值[QXmlName.namespaceUri](qxmlname.html#namespaceUri)（）是URI。价值[QXmlName.prefix](qxmlname.html#prefix)（）是该URI被绑定到前缀。本地名称是微不足道的，可以是任意值。

```
QAbstractXmlReceiver.processingInstruction (self, QXmlName target, QString value)
```

这种方法是抽象的，应在任何子类中重新实现。

当一个处理指令出现在此回调被调用[sequence](qabstractxmlreceiver.html#xquery-sequence)。处理指令用于在XML文档中告诉应用程序读取文件执行某些操作。一个典型的例子是使用处理指令来告诉应用程序使用特定的XSLT样式表来处理文档。

```
 <?xml-stylesheet type="test/xsl" href="formatter.xsl"?>

```

_target_是[name](qxmlname.html)的处理指令。其_prefix_和_namespace URI_必须都是空的。其_local name_是目标。在上面的例子中，域名是_xml-stylesheet_。

该_value_指定要采取的行动。注意，这个_value_不得包含字符串“ \u003e ” 。在上面的例子中，_value_ is _type="test/xsl" href="formatter.xsl_。

一般情况下，应避免使用处理指令，因为他们没有意识到命名空间和在许多情况下被剥离出来呢。处理指令通常可以替换为一个自定义的命名空间的元素。

```
QAbstractXmlReceiver.startDocument (self)
```

这种方法是抽象的，应在任何子类中重新实现。

当一个文档节点出现在这个回调函数被调用[sequence](qabstractxmlreceiver.html#xquery-sequence)。

```
QAbstractXmlReceiver.startElement (self, QXmlName name)
```

这种方法是抽象的，应在任何子类中重新实现。

当一个新的元素节点出现在这个回调函数被调用[sequence](qabstractxmlreceiver.html#xquery-sequence)。_name_是有效[name](qxmlname.html)该节点的元素。

```
QAbstractXmlReceiver.startOfSequence (self)
```

这种方法是抽象的，应在任何子类中重新实现。

此回调被调用一次而已，正确的前[sequence](qabstractxmlreceiver.html#xquery-sequence)开始。