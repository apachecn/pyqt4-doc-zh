# QDomDocumentFragment Class Reference

## [[QtXml](index.htm) module]

该QDomDocumentFragment类是QDomNodes的树，通常不是一个完整的[QDomDocument](qdomdocument.html)。[More...](#details)

继承[QDomNode](qdomnode.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDomDocumentFragment x)`
*   `QDomNode.NodeType nodeType (self)`

* * *

## Detailed Description

该QDomDocumentFragment类是QDomNodes的树，通常不是一个完整的[QDomDocument](qdomdocument.html)。

如果你想要做复杂的树操作有一个轻量级的类来存储节点和他们的关系是有用的。 QDomDocumentFragment存储这并不一定表示一个格式良好的XML文档的文档的子树。

QDomDocumentFragment也是有用的，如果你想在一个列表组的几个节点，并插入他们都在一起，一些节点的子节点。在这些情况下QDomDocumentFragment可以作为一个临时的容器，用于儿童的当前列表。

QDomDocumentFragment的最重要的特点是，它是由处理以特殊的方式[QDomNode.insertAfter](qdomnode.html#insertAfter)（ ）[QDomNode.insertBefore](qdomnode.html#insertBefore)（ ）[QDomNode.replaceChild](qdomnode.html#replaceChild)（）和[QDomNode.appendChild](qdomnode.html#appendChild)（ ）而不是插入片段本身，所有的片段的孩子被插入。

* * *

## Method Documentation

```
QDomDocumentFragment.__init__ (self)
```

构造一个空文档片段。

```
QDomDocumentFragment.__init__ (self, QDomDocumentFragment x)
```

构造的副本_x_。

副本的数据是共享的（浅拷贝） ：修改一个节点也将改变其他。如果你想使一个深拷贝，使用[cloneNode](qdomnode.html#cloneNode)（ ） 。

```
QDomNode.NodeType QDomDocumentFragment.nodeType (self)
```

[

Returns `DocumentFragment`。

](qdomnode.html#NodeType-enum)

[**See also**](qdomnode.html#NodeType-enum) [isDocumentFragment](qdomnode.html#isDocumentFragment)（）和[QDomNode.toDocumentFragment](qdomnode.html#toDocumentFragment)（ ） 。