# QDomText Class Reference

## [[QtXml](index.htm) module]

该QDomText类表示解析的XML文档中的文本数据。[More...](#details)

继承[QDomCharacterData](qdomcharacterdata.html)。

通过继承[QDomCDATASection](qdomcdatasection.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDomText x)`
*   `QDomNode.NodeType nodeType (self)`
*   `QDomText splitText (self, int offset)`

* * *

## Detailed Description

该QDomText类表示解析的XML文档中的文本数据。

您可以在两个QDomText objecs与分裂的QDomText对象中的文本[splitText](qdomtext.html#splitText)（ ） 。

关于文档对象模型有进一步的信息[Level 1](http://www.w3.org/TR/REC-DOM-Level-1/)和[Level 2 Core](http://www.w3.org/TR/DOM-Level-2-Core/)。对于更一般介绍的DOM实现的见[QDomDocument](qdomdocument.html)文档。

* * *

## Method Documentation

```
QDomText.__init__ (self)
```

构造一个空[QDomText](qdomtext.html)对象。

为了构建一个[QDomText](qdomtext.html)有内容，使用[QDomDocument.createTextNode](qdomdocument.html#createTextNode)（ ） 。

```
QDomText.__init__ (self, QDomText x)
```

构造的副本_x_。

副本的数据是共享的（浅拷贝） ：修改一个节点也将改变其他。如果你想使一个深拷贝，使用[cloneNode](qdomnode.html#cloneNode)（ ） 。

```
QDomNode.NodeType QDomText.nodeType (self)
```

[

Returns `TextNode`。

](qdomnode.html#NodeType-enum)

```
QDomText QDomText.splitText (self, int offset)
```

[](qdomtext.html)

[这个分裂的DOM文本对象分为两](qdomtext.html)[QDomText](qdomtext.html)对象。这个对象保持其第一_offset_字符和第二个（新建）对象被插入到文档树中剩馀的字符这个对象之后。

该函数返回新创建的对象。

**See also** [QDomNode.normalize](qdomnode.html#normalize)（ ） 。