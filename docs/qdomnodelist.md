# QDomNodeList Class Reference

## [[QtXml](index.htm) module]

该QDomNodeList类是列表[QDomNode](qdomnode.html)对象。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDomNodeList)`
*   `QDomNode at (self, int index)`
*   `int count (self)`
*   `bool isEmpty (self)`
*   `QDomNode item (self, int index)`
*   `int length (self)`
*   `int size (self)`

### Special Methods

*   `bool __eq__ (self, QDomNodeList)`
*   `__len__ (self)`
*   `bool __ne__ (self, QDomNodeList)`

* * *

## Detailed Description

该QDomNodeList类是列表[QDomNode](qdomnode.html)对象。

列表可以通过以下方式获得[QDomDocument.elementsByTagName](qdomdocument.html#elementsByTagName)（）和[QDomNode.childNodes](qdomnode.html#childNodes)（ ） 。文档对象模型（DOM ） ，需要这些列表是“活” ：每当你改变了相关文档，列表中的内容将得到更新。

你可以得到一个特定节点的列表[item](qdomnodelist.html#item)（ ） 。项目的列表中的号码由返回[length](qdomnodelist.html#length)（ ） 。

关于文档对象模型有进一步的信息[Level 1](http://www.w3.org/TR/REC-DOM-Level-1/)和[Level 2 Core](http://www.w3.org/TR/DOM-Level-2-Core/)。对于更一般介绍的DOM实现的见[QDomDocument](qdomdocument.html)文档。

* * *

## Method Documentation

```
QDomNodeList.__init__ (self)
```

创建一个空的节点列表。

```
QDomNodeList.__init__ (self, QDomNodeList)
```

构造的副本_n_。

```
QDomNode QDomNodeList.at (self, int index)
```

[](qdomnode.html)

[这个功能是为Qt API的一致性。它相当于](qdomnode.html)[item](qdomnodelist.html#item)（ ） 。

If _index_为负，或者如果_index_\u003e =[length](qdomnodelist.html#length)（ ），那么一个空节点则返回（即节点的[QDomNode.isNull](qdomnode.html#isNull)（ ）返回True ） 。

```
int QDomNodeList.count (self)
```

这个功能是为Qt API的一致性。它相当于[length](qdomnodelist.html#length)（ ） 。

```
bool QDomNodeList.isEmpty (self)
```

返回True如果列表中没有的项目，否则返回False 。这个功能是为Qt API的一致性。

```
QDomNode QDomNodeList.item (self, int index)
```

[

返回节点的位置_index_。

](qdomnode.html)

[If _index_为负，或者如果_index_\u003e =](qdomnode.html)[length](qdomnodelist.html#length)（ ），那么一个空节点则返回（即节点的[QDomNode.isNull](qdomnode.html#isNull)（ ）返回True ） 。

**See also** [length](qdomnodelist.html#length)（ ） 。

```
int QDomNodeList.length (self)
```

返回节点的列表中的号码。

```
int QDomNodeList.size (self)
```

这个功能是为Qt API的一致性。它相当于[length](qdomnodelist.html#length)（ ） 。

```
bool QDomNodeList.__eq__ (self, QDomNodeList)
```

```
 QDomNodeList.__len__ (self)
```

```
bool QDomNodeList.__ne__ (self, QDomNodeList)
```