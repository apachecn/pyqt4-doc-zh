# QAbstractXmlNodeModel Class Reference

## [[QtXmlPatterns](index.htm) module]

该QAbstractXmlNodeModel类是模拟非XML数据看起来像XML作为一个抽象基类[QXmlQuery](qxmlquery.html)。[More...](#details)

通过继承[QSimpleXmlNodeModel](qsimplexmlnodemodel.html)。

### Types

*   `enum SimpleAxis { Parent, FirstChild, PreviousSibling, NextSibling }`

### Methods

*   `__init__ (self)`
*   `list-of-QXmlNodeModelIndex attributes (self, QXmlNodeModelIndex element)`
*   `QUrl baseUri (self, QXmlNodeModelIndex ni)`
*   `QXmlNodeModelIndex.DocumentOrder compareOrder (self, QXmlNodeModelIndex ni1, QXmlNodeModelIndex ni2)`
*   `QXmlNodeModelIndex createIndex (self, int data)`
*   `QXmlNodeModelIndex createIndex (self, int data, int additionalData)`
*   `QXmlNodeModelIndex createIndex (self, object pointer, int additionalData = 0)`
*   `QUrl documentUri (self, QXmlNodeModelIndex ni)`
*   `QXmlNodeModelIndex elementById (self, QXmlName NCName)`
*   `QXmlNodeModelIndex.NodeKind kind (self, QXmlNodeModelIndex ni)`
*   `QXmlName name (self, QXmlNodeModelIndex ni)`
*   `list-of-QXmlName namespaceBindings (self, QXmlNodeModelIndex n)`
*   `QXmlNodeModelIndex nextFromSimpleAxis (self, SimpleAxis axis, QXmlNodeModelIndex origin)`
*   `list-of-QXmlNodeModelIndex nodesByIdref (self, QXmlName NCName)`
*   `QXmlNodeModelIndex root (self, QXmlNodeModelIndex n)`
*   `QSourceLocation sourceLocation (self, QXmlNodeModelIndex index)`
*   `QString stringValue (self, QXmlNodeModelIndex n)`
*   `QVariant typedValue (self, QXmlNodeModelIndex n)`

* * *

## Detailed Description

该QAbstractXmlNodeModel类是模拟非XML数据看起来像XML作为一个抽象基类[QXmlQuery](qxmlquery.html)。

该QAbstractXmlNodeModel指定一个节点模型必须实现该节点模型的接口可以访问用于处理查询引擎[XQuery](index.htm)查询。一个节点的模型数据表示为可查询，就好像数据是XML的结构。

通过QAbstractXmlNodeModel的子类表示的节点模型是指由被访问[QtXmlPatterns](index.htm)查询引擎。如果API似乎有点怪在一些地方，这是因为成员函数是由查询引擎称为它的评估[XQuery](index.htm)。它们并不意味着被编程使用。

### Usage

QAbstractXmlNodeModel桥樑要查询的非XML数据的任意的结构和良好定义的由理解的XML数据的结构之间的间隙[QXmlQuery](qxmlquery.html)。

想想看，读取文件中的化学中的应用`chemistryData`，其中包含代表分子和原子组成的化学结构非XML数据。该应用程序将查询该化学数据与[XQuery](index.htm)它从文件中读取`queryFile`。我们写QAbstractXmlNodeModel的自定义子类（`ChemistryNodeModel`）读取`chemistryData`并建立一个数据结构，也许是由我们自己的类的对象`molecule`和`atom`。显然，这种数据结构是不是XML。我们的自定义子类就知道如何遍历这个非XML结构，并通过展示它的[XPath Data Model interface](http://www.w3.org/TR/xpath-datamodel/)。

```
 [QFile](qfile.html) queryFile(argv[1]);
 [QFile](qfile.html) chemistryData(argv[2]);
 [QString](qstring.html) moleculeName = argv[3];

 [QXmlQuery](qxmlquery.html) query;
 query.setQuery(&queryFile, [QUrl](qurl.html).fromLocalFile(queryFile.fileName()));

 ChemistryNodeModel myNodeModel(query.namePool(), chemistryData);
 [QXmlNodeModelIndex](qxmlnodemodelindex.html) startNode = myNodeModel.nodeFor(moleculeName);
 query.bindVariable("queryRoot", startNode);

 [QFile](qfile.html) out;
 out.open(stdout, [QIODevice](qiodevice.html).WriteOnly);

 [QXmlSerializer](qxmlserializer.html) serializer(query, &out);
 query.evaluateTo(&serializer);

```

应用程序首先创建的实例[QXmlQuery](qxmlquery.html)并呼吁[setQuery()](qxmlquery.html#setQuery) to read `queryFile`含[XQuery](index.htm)我们要运行。然后，它创建了我们自定义的节点模型类的实例，`ChemistryNodeModel`，这是QAbstractXmlNodeModel的子类。它的构造函数被调用，[name pool](qxmlnamepool.html)从我们获得的[QXmlQuery](qxmlquery.html)以及与`chemistryFile`含分子和原子的待查询的结构。该[name pool](qxmlnamepool.html)是必需的，因为我们的自定义节点模型具有成员函数[name()](qabstractxmlnodemodel.html#name)，它返回[name](qxmlname.html)的模型中的任何节点。该[query](qxmlquery.html)和自定义节点模型必须使用相同的名称池构造这些[names](qxmlname.html)。该构造函数将改为`chemistryFile`并建立自定义节点模型结构。

连接`query`到自定义节点模型，我们必须绑定在查询中使用到模型中的一个节点的变量名。该变量可以被用来在查询中作为起始节点。首先，将[index](qxmlnodemodelindex.html)为所需的起始节点被检索到通过调用[QAbstractXmlNodeModel.createIndex](qabstractxmlnodemodel.html#createIndex)（ ） 。然后索引绑定到变量名，在此情况下`queryRoot`，通过将名字和索引[QXmlQuery.bindVariable](qxmlquery.html#bindVariable)（ ） 。然后，查询可以使用一个变量引用`$queryRoot`指起始节点。需要注意的是，如果[query](qxmlquery.html)使用多个变量引用，调用[QXmlQuery.bindVariable](qxmlquery.html#bindVariable)（ ）需要在每个不同的变量名称绑定到模型中的一个节点。

当应用程序调用的一个查询被执行[QXmlQuery](qxmlquery.html)评价职能。该应用程序使用QXmlQuery.evaluateTo （[QAbstractXmlReceiver](qabstractxmlreceiver.html)* ） ，因为它然后使用[serializer](qxmlserializer.html)到了查询结果作为XML来`stdout`。我们也可以使用QXmlQuery.evaluateTo （[QXmlResultItems](qxmlresultitems.html)* ）来获取结果的项目，或QXmlQuery.evaluateTo列表（[QStringList](qstringlist.html)* ）如果查询评估，以一序列`xs:string`值。

在查询执行时，引擎遍历节点模型使用[nextFromSimpleAxis](qabstractxmlnodemodel.html#nextFromSimpleAxis)（ ）来获得[index](qxmlnodemodelindex.html)的下一个节点进行访问。该发动机可以通过调用得到一个节点的名称[name](qabstractxmlnodemodel.html#name)（ ）与该节点的[index](qxmlnodemodelindex.html)。[stringValue](qabstractxmlnodemodel.html#stringValue)（ ）[baseUri](qabstractxmlnodemodel.html#baseUri)（ ）[documentUri](qabstractxmlnodemodel.html#documentUri)（）和[kind](qabstractxmlnodemodel.html#kind)（）根据需要与节点也被称为[index](qxmlnodemodelindex.html)。

该示例演示了标准模式使用QAbstractXmlNodeModel的一个子类与组合[QXmlQuery](qxmlquery.html)要执行的[XQuery](index.htm)。

1.  实例[QXmlQuery](qxmlquery.html)并给它[XQuery](index.htm)要运行;
2.  实例QAbstractXmlNodeModel的子类或[QSimpleXmlNodeModel](qsimplexmlnodemodel.html);
3.  检索[QXmlNodeModelIndex](qxmlnodemodelindex.html)对于模型中的节点，其中[QXmlQuery](qxmlquery.html)应开始查询;
4.  使用[QXmlQuery.bindVariable](qxmlquery.html#bindVariable)（）来绑定[QXmlNodeModelIndex](qxmlnodemodelindex.html)至`$variable name`;
5.  呼叫之一[QXmlQuery](qxmlquery.html)评价函数来执行查询。

### Subclassing

因为[XPath Data Model interface](http://www.w3.org/TR/xpath-datamodel/)通过QAbstractXmlNodeModel允许提出[QXmlQuery](qxmlquery.html)对非XML数据进行操作，就好像它是XML ，实施QAbstractXmlNodeModel的子类可以涉及一个显着的工作量。该[QSimpleXmlNodeModel](qsimplexmlnodemodel.html)类提供简化的实施对于许多常见的用例。

### Thread Safety

因为节点模型可以同时通过线程的访问[QtXmlPatterns](index.htm)模块， QAbstractXmlNodeModel的子类必须被编写成[thread-safe](index.htm)。能够简化执行的线程安全类包括[QReadLocker](qreadlocker.html)和[QWriteLocker](qwritelocker.html)。

请参阅示例[File System Example](index.htm)演示。

* * *

## Type Documentation

```
QAbstractXmlNodeModel.SimpleAxis
```

四个轴，每个包含一个节点而已。

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractXmlNodeModel.Parent` | `0` | 上下文节点的父 |
| `QAbstractXmlNodeModel.FirstChild` | `1` | 上下文节点的第一个孩子 |
| `QAbstractXmlNodeModel.PreviousSibling` | `2` | 上下文节点的上一个孩子 |
| `QAbstractXmlNodeModel.NextSibling` | `3` | 上下文节点的下一个子 |

* * *

## Method Documentation

```
QAbstractXmlNodeModel.__init__ (self)
```

默认构造函数。

```
list-of-QXmlNodeModelIndex QAbstractXmlNodeModel.attributes (self, QXmlNodeModelIndex element)
```

这种方法是抽象的，应在任何子类中重新实现。

返回的属性_element_。调用者保证_element_是在该节点模型的元素。

```
QUrl QAbstractXmlNodeModel.baseUri (self, QXmlNodeModelIndex ni)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回其索引节点的基URI_n_。调用者保证_n_不`null`并且，它属于在该节点模型的一个节点。

一个节点的基URI可使用提取出的`fn:base-uri()`功能。基URI通常用于解决出现在节点或它的孩子相对URI 。这是符合标准的，只是返回文档的URI ，尽管这可能无法正确反映基础数据。

这个函数映射到`dm:base-uri`访问器，根据下面的返回一个基URI ：

*   For document nodes, the base URI and the document URI are the same.
*   For elements, the base URI is the URI appearing in the element's `xml:base` attribute, if present, or it is resolved to the parent element's base URI.
*   Namespace nodes have no base URI.
*   The base URI for a processing instruction, comment, attribute, or text node is the base URI of the node's parent element.

](qurl.html)

[实施保证返回一个有效的](qurl.html)[QUrl](qurl.html)或默认构造[QUrl](qurl.html)。如果一个节点没有基URI ，如在注释没有家长的情况下，默认的构造[QUrl](qurl.html)返回。

**See also** [XQuery 1.0 and XPath 2.0 Data Model (XDM), 5.2 base-uri Accessor](http://www.w3.org/TR/xpath-datamodel/#dm-base-uri)。

```
QXmlNodeModelIndex.DocumentOrder QAbstractXmlNodeModel.compareOrder (self, QXmlNodeModelIndex ni1, QXmlNodeModelIndex ni2)
```

[

这种方法是抽象的，应在任何子类中重新实现。

该函数返回由索引节点的相对顺序文件_ni1_和_ni2_。它被用于`Is`运营商和文档顺序排序节点。

调用者保证_ni1_和_ni2_不`null`并且这两个标识在这个节点模型节点。

](qxmlnodemodelindex.html#DocumentOrder-enum)

[If _ni1_是相同的_ni2_，](qxmlnodemodelindex.html#DocumentOrder-enum)[QXmlNodeModelIndex.Is](qxmlnodemodelindex.html#DocumentOrder-enum)返回。如果_ni1_先于_ni2_按文档顺序，[QXmlNodeModelIndex.Precedes](qxmlnodemodelindex.html#DocumentOrder-enum)返回。如果_ni1_ follows _ni2_按文档顺序，[QXmlNodeModelIndex.Follows](qxmlnodemodelindex.html#DocumentOrder-enum)返回。

**See also** [XQuery 1.0 and XPath 2.0 Data Model (XDM), 2.4 Document Order](http://www.w3.org/TR/xpath-datamodel/#document-order)。

```
QXmlNodeModelIndex QAbstractXmlNodeModel.createIndex (self, int data)
```

[

创建一个具有节点索引_data_作为它的内部数据。_data_没有限制。

](qxmlnodemodelindex.html)

```
QXmlNodeModelIndex QAbstractXmlNodeModel.createIndex (self, int data, int additionalData)
```

[

创建一个具有节点索引_pointer_和_additionalData_作为它的内部数据。

什么_pointer_和_additionalData_是，不是限制。

](qxmlnodemodelindex.html)

```
QXmlNodeModelIndex QAbstractXmlNodeModel.createIndex (self, object pointer, int additionalData = 0)
```

[

这是一个重载函数。

](qxmlnodemodelindex.html)

[创建](qxmlnodemodelindex.html)[QXmlNodeModelIndex](qxmlnodemodelindex.html) containing _data_和_additionalData_。

```
QUrl QAbstractXmlNodeModel.documentUri (self, QXmlNodeModelIndex ni)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回的文档URI_n_。该文件的URI标识的是该文件的资源。例如，该文件可能是一个普通文件，例如：`file:/`或者它可以是`http://`一个文件的位置的URL。该文件的URI用于解析URI和简单地知道该文件是。

如果节点模型映射到URI以自然的方式，返回的URI 。否则，返回公司或产品的URI 。文档的URI可以是任意的URI ，只要其有效和绝对的。

](qurl.html)

[调用者保证_n_不`null`并且，它属于本](qurl.html)[QAbstractXmlNodeModel](qabstractxmlnodemodel.html)。

这个函数映射到`dm:document-uri`访问器，根据下面的返回一个文件的URI ：

*   If _n_ is a document node, return an absolute [QUrl](qurl.html) containing the document URI, or a default constructed [QUrl](qurl.html). The latter signals that no document URI is available for the document node.
*   For all other nodes, return a default constructed [QUrl](qurl.html).

**See also** [XQuery 1.0 and XPath 2.0 Data Model (XDM), 5.4 document-uri Accessor](http://www.w3.org/TR/xpath-datamodel/#dm-document-uri)，[QUrl.isValid](qurl.html#isValid)（）和[QUrl.isRelative](qurl.html#isRelative)（ ） 。

```
QXmlNodeModelIndex QAbstractXmlNodeModel.elementById (self, QXmlName NCName)
```

[

这种方法是抽象的，应在任何子类中重新实现。

](qxmlnodemodelindex.html)

[返回标识为元素的索引_id_。](qxmlnodemodelindex.html)[XQuery](index.htm)的`id()`函数调用这个函数。

返回的节点的索引将其值类型的元素节点`ID`和equals_id_，或者这将是一个具有属性，其类型化值的类型的元素节点`ID`和equals_id_。如果不存在这样的元素，一个默认的构造[QXmlNodeModelIndex](qxmlnodemodelindex.html)实例返回。实现者保证，如果返回的节点的索引不为空，它标识元素。

它是不足够的，以只被称为属性或元素`id`。它的值类型也必须是`ID`。然而，保留的名称`xml:id`就足够了。

In _id_时，`namespace URI`和`prefix`是不确定的，并且`local name`是应该抬头的ID。

**See also** [XQuery 1.0 and XPath 2.0 Functions and Operators, 15.5.2 fn:id](http://www.w3.org/TR/xpath-functions/#func-id)。

```
QXmlNodeModelIndex.NodeKind QAbstractXmlNodeModel.kind (self, QXmlNodeModelIndex ni)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回一个值，指示确定了节点的类型_ni_。调用者保证_ni_不为null ，并且它标识了此节点模型的节点。这个函数映射到`dm:node-kind()`访问。

](qxmlnodemodelindex.html#NodeKind-enum)

[**See also**](qxmlnodemodelindex.html#NodeKind-enum) [XQuery 1.0 and XPath 2.0 Data Model (XDM), 5.10 node-kind Accessor](http://www.w3.org/TR/xpath-datamodel/#dm-node-kind)。

```
QXmlName QAbstractXmlNodeModel.name (self, QXmlNodeModelIndex ni)
```

[

这种方法是抽象的，应在任何子类中重新实现。

](qxmlname.html)

[返回的名称_ni_。调用者保证_ni_不`null`并且，它属于本](qxmlname.html)[QAbstractXmlNodeModel](qabstractxmlnodemodel.html)。

如果一个节点没有一个名称，例如，注释节点，空[QXmlName](qxmlname.html)返回。 QXmlNames必须的实例被创建[QXmlQuery](qxmlquery.html)正被用于使用这个评估查询[QAbstractXmlNodeModel](qabstractxmlnodemodel.html)。

这个函数映射到`dm:node-name()`访问。

If _ni_是一个处理指令，一个[QXmlName](qxmlname.html)返回的本地名称作为目标名称和命名空间URI和前缀都为空。

**See also** [XQuery 1.0 and XPath 2.0 Data Model (XDM), 5.11 node-name Accessor](http://www.w3.org/TR/xpath-datamodel/#dm-node-name)和[QXmlName](qxmlname.html)。

```
list-of-QXmlName QAbstractXmlNodeModel.namespaceBindings (self, QXmlNodeModelIndex n)
```

这种方法是抽象的，应在任何子类中重新实现。

返回在范围的命名空间_n_。调用者保证_n_不`null`并且，它属于本[QAbstractXmlNodeModel](qabstractxmlnodemodel.html)。

此功能对应的`dm:namespace-nodes`访问。

命名空间声明的返回向量包括的祖先命名空间_n_。

调用者保证_n_是属于这样的一个元素[QAbstractXmlNodeModel](qabstractxmlnodemodel.html)。

```
QXmlNodeModelIndex QAbstractXmlNodeModel.nextFromSimpleAxis (self, SimpleAxis axis, QXmlNodeModelIndex origin)
```

[

这种方法是抽象的，应在任何子类中重新实现。

](qxmlnodemodelindex.html)

[When](qxmlnodemodelindex.html) [QtXmlPatterns](index.htm)计算路径表达式，它效仿他们通过电话的结合[QSimpleXmlNodeModel.SimpleAxis](qabstractxmlnodemodel.html#SimpleAxis-enum)值。因此，该功能的实现必须返回该节点，如果有的话，就出现_axis_从发出_origin_。

如果没有这样的节点可用，默认的构造[QXmlNodeModelIndex](qxmlnodemodelindex.html)返回。

[QSimpleXmlNodeModel](qsimplexmlnodemodel.html)无需通过保证它永远不会要求来处理多馀的边角情况：

*   Children or siblings for attributes.
*   Children for comments, processing instructions, and text nodes.
*   Siblings or parents for document nodes.

一个典型的实现执行`switch`上的值_axis_：

```
 [QXmlNodeModelIndex](qxmlnodemodelindex.html) MyTreeModel.nextFromSimpleAxis(SimpleAxis axis, const [QXmlNodeModelIndex](qxmlnodemodelindex.html) &origin) const
 {
   // Convert the QXmlNodeModelIndex to a value that is specific to what we represent.
   const MyValue value = toMyValue(ni);

   switch(axis)
   {
       case Parent:
           return toNodeIndex(value.parent());
       case FirstChild:
       case PreviousSibling:
       case NextSibling:
           // and so on
   }
 }

```

```
list-of-QXmlNodeModelIndex QAbstractXmlNodeModel.nodesByIdref (self, QXmlName NCName)
```

这种方法是抽象的，应在任何子类中重新实现。

返回具有一个元素和/或属性`IDREF`值等于_idref_。[XQuery](index.htm)的`idref()`函数调用这个函数。

实现者保证所确定的返回索引节点是元素或属性。

它是不足够的，以只被称为属性或元素`idref`。它也必须是类型`IDREF`。元素必须键入为`xs:IDREF` or `xs:IDREFS`或者，在属性的情况下，如`IDREF` or `IDREFS`在架构中。

In _idref_时，`namespace URI`和`prefix`是不确定的，并且`local name`是应该抬头的ID。

**See also** [XQuery 1.0 and XPath 2.0 Functions and Operators, 15.5.3 fn:idref](http://www.w3.org/TR/xpath-functions/#func-idref)。

```
QXmlNodeModelIndex QAbstractXmlNodeModel.root (self, QXmlNodeModelIndex n)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回该树包含其索引是该节点的根节点_n_。调用者保证_n_不`null`而且它标识了此节点模型的节点。

](qxmlnodemodelindex.html)

[If _n_标识一个节点是根，父母的直接子（ ）将返回相同的](qxmlnodemodelindex.html)[QXmlNodeModelIndex](qxmlnodemodelindex.html)这个函数返回。

```
QSourceLocation QAbstractXmlNodeModel.sourceLocation (self, QXmlNodeModelIndex index)
```

[](qsourcelocation.html)

[与给定返回该对象的源位置_index_或默认构造](qsourcelocation.html)[QSourceLocation](qsourcelocation.html)在任何情况下，位置信息是可用的。

此功能被引入Qt的4.6 。

```
QString QAbstractXmlNodeModel.stringValue (self, QXmlNodeModelIndex n)
```

这种方法是抽象的，应在任何子类中重新实现。

返回节点的字符串值_n_。

调用者保证_n_不`null`而且它属于此[QAbstractXmlNodeModel](qabstractxmlnodemodel.html)实例。

这个函数映射到`dm:string-value()`访问器，其规格完全指定。这里有一个总结：

*   For processing instructions, the string value is the data section(excluding any whitespace appearing between the name and the data).
*   For text nodes, the string value equals the text node.
*   For comments, the content of the comment
*   For elements, the concatenation of all text nodes that are descendants. Note, this is not only the children, but the childrens' childrens' text nodes, and so forth.
*   For document nodes, the concatenation of all text nodes in the document.

**See also** [XQuery 1.0 and XPath 2.0 Data Model (XDM), 5.13 string-value Accessor](http://www.w3.org/TR/xpath-datamodel/#dm-string-value)。

```
QVariant QAbstractXmlNodeModel.typedValue (self, QXmlNodeModelIndex n)
```

这种方法是抽象的，应在任何子类中重新实现。

返回节点的类型值_node_。

类型化值是原子值，该元素或属性包含。

调用者保证_node_或者是一个元素或属性。返回的实施者担保[QVariant](qvariant.html)有被支撑在一个值[XQuery](index.htm)。它不能是任意的[QVariant](qvariant.html)值。实现者也保证[stringValue](qabstractxmlnodemodel.html#stringValue)（）返回的TypedValue的词汇表示（ ） （这是由担保[QSimpleXmlNodeModel.stringValue](qsimplexmlnodemodel.html#stringValue)（））。

如果返回的[QVariant](qvariant.html)是一个默认的构造变形，它预示着，_node_没有类型化值。