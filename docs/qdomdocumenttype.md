# QDomDocumentType Class Reference

## [[QtXml](index.htm) module]

该QDomDocumentType类是DTD的文档树中的代表性。[More...](#details)

继承[QDomNode](qdomnode.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDomDocumentType x)`
*   `QDomNamedNodeMap entities (self)`
*   `QString internalSubset (self)`
*   `QString name (self)`
*   `QDomNode.NodeType nodeType (self)`
*   `QDomNamedNodeMap notations (self)`
*   `QString publicId (self)`
*   `QString systemId (self)`

* * *

## Detailed Description

该QDomDocumentType类是DTD的文档树中的代表性。

该QDomDocumentType类允许在一定的数据结构在DTD的只读访问权限：它可以返回所有的地图[entities](qdomdocumenttype.html#entities)（）和[notations](qdomdocumenttype.html#notations)（ ） 。此外，该函数[name](qdomdocumenttype.html#name)（ ）返回的文档类型的名称，如\u003c ！ DOCTYPE名称\u003e标籤中指定。这个类还提供了[publicId](qdomdocumenttype.html#publicId)（ ）[systemId](qdomdocumenttype.html#systemId)（）和[internalSubset](qdomdocumenttype.html#internalSubset)（）函数。

* * *

## Method Documentation

```
QDomDocumentType.__init__ (self)
```

创建一个空的[QDomDocumentType](qdomdocumenttype.html)对象。

```
QDomDocumentType.__init__ (self, QDomDocumentType x)
```

构造的副本_n_。

副本的数据是共享的（浅拷贝） ：修改一个节点也将改变其他。如果你想使一个深拷贝，使用[cloneNode](qdomnode.html#cloneNode)（ ） 。

```
QDomNamedNodeMap QDomDocumentType.entities (self)
```

[

返回DTD中描述的所有实体的地图。

```
QString QDomDocumentType.internalSubset (self)
```

返回的文档类型或空字符串的内部子集，如果没有内部子集。

](qdomnamednodemap.html)

[**See also**](qdomnamednodemap.html) [publicId](qdomdocumenttype.html#publicId)（）和[systemId](qdomdocumenttype.html#systemId)（ ） 。

```
QString QDomDocumentType.name (self)
```

返回文档类型的名称，如\u003c ！ DOCTYPE名称\u003e标籤中指定。

**See also** [nodeName](qdomnode.html#nodeName)（ ） 。

```
QDomNode.NodeType QDomDocumentType.nodeType (self)
```

[

Returns `DocumentTypeNode`。

](qdomnode.html#NodeType-enum)

[**See also**](qdomnode.html#NodeType-enum) [isDocumentType](qdomnode.html#isDocumentType)（）和[QDomNode.toDocumentType](qdomnode.html#toDocumentType)（ ） 。

```
QDomNamedNodeMap QDomDocumentType.notations (self)
```

[

返回DTD中描述的所有符号的地图。

```
QString QDomDocumentType.publicId (self)
```

返回外部DTD子集或空字符串的公共标识符，如果没有公共标识符。

](qdomnamednodemap.html)

[**See also**](qdomnamednodemap.html) [systemId](qdomdocumenttype.html#systemId)（ ）[internalSubset](qdomdocumenttype.html#internalSubset)（）和[QDomImplementation.createDocumentType](qdomimplementation.html#createDocumentType)（ ） 。

```
QString QDomDocumentType.systemId (self)
```

返回外部DTD子集或空字符串的系统标识符，如果没有系统标识符。

**See also** [publicId](qdomdocumenttype.html#publicId)（ ）[internalSubset](qdomdocumenttype.html#internalSubset)（）和[QDomImplementation.createDocumentType](qdomimplementation.html#createDocumentType)（ ） 。