# QDomEntityReference Class Reference

## [[QtXml](index.htm) module]

该QDomEntityReference类表示一个XML实体引用。[More...](#details)

继承[QDomNode](qdomnode.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDomEntityReference x)`
*   `QDomNode.NodeType nodeType (self)`

* * *

## Detailed Description

该QDomEntityReference类表示一个XML实体引用。

一个QDomEntityReference对象可以被插入到DOM树当实体引用是源文件中，或者当用户希望将一个实体引用。

请注意，字符引用和引用预定义的实体是由XML处理器，使字符由它们的Unicode等效，而不是由一个实体引用表示扩大。

此外， XML处理器可以完全展开，而不是提供QDomEntityReference对象实体的引用，同时建立DOM树。

如果它确实提供了这样的对象，那么对于一个给定的实体引用节点，它可能是有代表引用的实体无实体节点，但如果这样的实体存在，那么实体引用节点的子级列表是一样的实体节点。由于与实体节点，实体引用的所有后代都是只读的。

关于文档对象模型有进一步的信息[Level 1](http://www.w3.org/TR/REC-DOM-Level-1/)和[Level 2 Core](http://www.w3.org/TR/DOM-Level-2-Core/)。对于更一般介绍的DOM实现的见[QDomDocument](qdomdocument.html)文档。

* * *

## Method Documentation

```
QDomEntityReference.__init__ (self)
```

构造一个空实体引用。使用[QDomDocument.createEntityReference](qdomdocument.html#createEntityReference)（）来创建内容的实体引用。

```
QDomEntityReference.__init__ (self, QDomEntityReference x)
```

构造的副本_x_。

副本的数据是共享的（浅拷贝） ：修改一个节点也将改变其他。如果你想使一个深拷贝，使用[cloneNode](qdomnode.html#cloneNode)（ ） 。

```
QDomNode.NodeType QDomEntityReference.nodeType (self)
```

[

Returns `EntityReference`。

](qdomnode.html#NodeType-enum)