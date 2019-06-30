# QDomComment Class Reference

## [[QtXml](index.htm) module]

该QDomComment类表示一个XML注释。[More...](#details)

继承[QDomCharacterData](qdomcharacterdata.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDomComment x)`
*   `QDomNode.NodeType nodeType (self)`

* * *

## Detailed Description

该QDomComment类表示一个XML注释。

在解析XML像这样的注释：

```
 <!-- this is a comment -->

```

通过在所解析的DOM树QDomComment对象表示。

关于文档对象模型有进一步的信息[http://www.w3.org/TR/REC-DOM-Level-1/](http://www.w3.org/TR/REC-DOM-Level-1/)和[http://www.w3.org/TR/DOM-Level-2-Core/](http://www.w3.org/TR/DOM-Level-2-Core/)。对于更一般介绍的DOM实现的见[QDomDocument](qdomdocument.html)文档。

* * *

## Method Documentation

```
QDomComment.__init__ (self)
```

构造一个空的注释。构建与内容的评论，请使用[QDomDocument.createComment](qdomdocument.html#createComment)（）函数。

```
QDomComment.__init__ (self, QDomComment x)
```

构造的副本_x_。

副本的数据是共享的（浅拷贝） ：修改一个节点也将改变其他。如果你想使一个深拷贝，使用[cloneNode](qdomnode.html#cloneNode)（ ） 。

```
QDomNode.NodeType QDomComment.nodeType (self)
```

[

Returns `CommentNode`。

](qdomnode.html#NodeType-enum)