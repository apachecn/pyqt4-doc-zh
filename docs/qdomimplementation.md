# QDomImplementation Class Reference

## [[QtXml](index.htm) module]

该QDomImplementation类提供有关DOM实现的功能的信息。[More...](#details)

### Types

*   `enum InvalidDataPolicy { AcceptInvalidChars, DropInvalidChars, ReturnNullNode }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDomImplementation)`
*   `QDomDocument createDocument (self, QString nsURI, QString qName, QDomDocumentType doctype)`
*   `QDomDocumentType createDocumentType (self, QString qName, QString publicId, QString systemId)`
*   `bool hasFeature (self, QString feature, QString version)`
*   `bool isNull (self)`

### Static Methods

*   `InvalidDataPolicy invalidDataPolicy ()`
*   `setInvalidDataPolicy (InvalidDataPolicy policy)`

### Special Methods

*   `bool __eq__ (self, QDomImplementation)`
*   `bool __ne__ (self, QDomImplementation)`

* * *

## Detailed Description

该QDomImplementation类提供有关DOM实现的功能的信息。

本课程介绍了由DOM实现所支持的功能。目前DOM级别1和DOM Level 2核心的XML的子集的支持。

通常你会使用的功能[QDomDocument.implementation](qdomdocument.html#implementation)（ ）来得到实现对象。

您可以创建一个新的文档类型[createDocumentType](qdomimplementation.html#createDocumentType)（ ）中，用一个新的文档[createDocument](qdomimplementation.html#createDocument)（ ） 。

关于文档对象模型有进一步的信息[Level 1](http://www.w3.org/TR/REC-DOM-Level-1/)和[Level 2 Core](http://www.w3.org/TR/DOM-Level-2-Core/)。对于更一般介绍的DOM实现的见[QDomDocument](qdomdocument.html)文档。

该QDom类有到不符合XML规范而不破坏向后兼容性，不能固定的Qt 4的几个问题。该[QtXmlPatterns](index.htm)模块和[QXmlStreamReader](qxmlstreamreader.html)和[QXmlStreamWriter](qxmlstreamwriter.html)类有较高程度的一致性的。

* * *

## Type Documentation

```
QDomImplementation.InvalidDataPolicy
```

此枚举指定应该做什么的时候一个工厂函数[QDomDocument](qdomdocument.html)被称为无效的数据。

| Constant | Value | Description |
| --- | --- | --- |
| `QDomImplementation.AcceptInvalidChars` | `0` | 数据应被无论如何存储在DOM对象。在这种情况下所得到的XML文档可能不正确。这是默认值， QDom的Qt中\u003c 4.1的行为。 |
| `QDomImplementation.DropInvalidChars` | `1` | 无效字符应该从数据中删除。 |
| `QDomImplementation.ReturnNullNode` | `2` | 工厂函数应该返回一个空节点。 |

**See also** [setInvalidDataPolicy](qdomimplementation.html#setInvalidDataPolicy)（）和[invalidDataPolicy](qdomimplementation.html#invalidDataPolicy)（ ） 。

* * *

## Method Documentation

```
QDomImplementation.__init__ (self)
```

构造一个[QDomImplementation](qdomimplementation.html)对象。

```
QDomImplementation.__init__ (self, QDomImplementation)
```

构造的副本_x_。

```
QDomDocument QDomImplementation.createDocument (self, QString nsURI, QString qName, QDomDocumentType doctype)
```

[

创建具有文档类型DOM文档_doctype_。此功能还增加了与限定名的根元素节点_qName_和命名空间URI_nsURI_。

](qdomdocument.html)

```
QDomDocumentType QDomImplementation.createDocumentType (self, QString qName, QString publicId, QString systemId)
```

[

会在该名称的文档类型节点_qName_。

_publicId_指定外部子集的公共标识符。如果你指定一个空字符串（的QString （ ） ）作为_publicId_，这意味着该文件类型没有公共标识符。

_systemId_指定外部子集的系统标识符。如果你指定一个空字符串作为_systemId_中，这意味着该文件类型没有系统标识符。

因为你不能有一个公共的标识符没有一个系统标识符，公共标识符被设置为空字符串，如果没有系统标识符。

DOM Level 2中不支持任何其他的文档类型声明的功能。

](qdomdocumenttype.html)

[您可以使用已创建这样一个文件类型的唯一方法，就是与组合](qdomdocumenttype.html)[createDocument](qdomimplementation.html#createDocument)（ ）函数创建一个[QDomDocument](qdomdocument.html)与此文件类型。

在DOM规范，这是创建一个非空的文件的唯一途径。由于历史原因， Qt还允许创建使用默认的空构造函数的文档。由此产生的文件是空的，但变成非空时，一个工厂函数，例如[QDomDocument.createElement](qdomdocument.html#createElement)（ ）被调用。该文件还成为非空时使用setContent （ ）被调用。

**See also** [createDocument](qdomimplementation.html#createDocument)（ ） 。

```
bool QDomImplementation.hasFeature (self, QString feature, QString version)
```

如果QDom实现了所要求的函数返回True_version_一_feature_否则返回False 。

目前支持的功能和它们的版本：

| Feature | Version |
| --- | --- |
| XML | 1.0 |

```
InvalidDataPolicy QDomImplementation.invalidDataPolicy ()
```

[](qdomimplementation.html#InvalidDataPolicy-enum)

[返回无效数据的政策，它指定应该做什么的时候一个工厂函数](qdomimplementation.html#InvalidDataPolicy-enum)[QDomDocument](qdomdocument.html)传递无效数据。

**Warning:**此功能不[reentrant](index.htm#reentrant)。

这个函数是Qt 4.1中引入。

**See also** [setInvalidDataPolicy](qdomimplementation.html#setInvalidDataPolicy)（）和[InvalidDataPolicy](qdomimplementation.html#InvalidDataPolicy-enum)。

```
bool QDomImplementation.isNull (self)
```

如果该对象被创建，则返回False[QDomDocument.implementation](qdomdocument.html#implementation)（ ），否则返回True 。

```
QDomImplementation.setInvalidDataPolicy (InvalidDataPolicy policy)
```

设置无效数据的政策，它指定应该做什么的时候一个工厂函数[QDomDocument](qdomdocument.html)传递无效数据。

该_policy_设置为所有实例[QDomDocument](qdomdocument.html)它已经存在，并且这将在以后被创建。

```
 [QDomDocument](qdomdocument.html) doc;
 [QDomImplementation](qdomimplementation.html) impl;

 // This will create the element, but the resulting XML document will
 // be invalid, because '~' is not a valid character in a tag name.
 impl.setInvalidDataPolicy([QDomImplementation](qdomimplementation.html).AcceptInvalidData);
 [QDomElement](qdomelement.html) elt1 = doc.createElement("foo~bar");

 // This will create an element with the tag name "foobar".
 impl.setInvalidDataPolicy([QDomImplementation](qdomimplementation.html).DropInvalidData);
 [QDomElement](qdomelement.html) elt2 = doc.createElement("foo~bar");

 // This will create a null element.
 impl.setInvalidDataPolicy([QDomImplementation](qdomimplementation.html).ReturnNullNode);
 [QDomElement](qdomelement.html) elt3 = doc.createElement("foo~bar");

```

**Warning:**此功能不[reentrant](index.htm#reentrant)。

这个函数是Qt 4.1中引入。

**See also** [invalidDataPolicy](qdomimplementation.html#invalidDataPolicy)（）和[InvalidDataPolicy](qdomimplementation.html#InvalidDataPolicy-enum)。

```
bool QDomImplementation.__eq__ (self, QDomImplementation)
```

```
bool QDomImplementation.__ne__ (self, QDomImplementation)
```