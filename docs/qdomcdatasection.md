# QDomCDATASection Class Reference

## [[QtXml](index.htm) module]

该QDomCDATASection类表示一个XML CDATA节。[More...](#details)

继承[QDomText](qdomtext.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDomCDATASection x)`
*   `QDomNode.NodeType nodeType (self)`

* * *

## Detailed Description

该QDomCDATASection类表示一个XML CDATA节。

CDATA节用于转义包含文本字符块，否则将被视为标记。那是在一个CDATA节认可的唯一的分隔符是“ ]]\u003e”字符串终止CDATA节。 CDATA节不能嵌套。他们的主要目的是为包括材料，如XML片段，而无需转义所有的分隔符。

相邻QDomCDATASection节点不被合并的[QDomNode.normalize](qdomnode.html#normalize)（）函数。

关于文档对象模型有进一步的信息[http://www.w3.org/TR/REC-DOM-Level-1/](http://www.w3.org/TR/REC-DOM-Level-1/)和[http://www.w3.org/TR/DOM-Level-2-Core/](http://www.w3.org/TR/DOM-Level-2-Core/)。对于更一般介绍的DOM实现的见[QDomDocument](qdomdocument.html)文档。

* * *

## Method Documentation

```
QDomCDATASection.__init__ (self)
```

构造一个空CDATA节。要创建具有内容CDATA节中，使用[QDomDocument.createCDATASection](qdomdocument.html#createCDATASection)（）函数。

```
QDomCDATASection.__init__ (self, QDomCDATASection x)
```

构造的副本_x_。

副本的数据是共享的（浅拷贝） ：修改一个节点也将改变其他。如果你想使一个深拷贝，使用[cloneNode](qdomnode.html#cloneNode)（ ） 。

```
QDomNode.NodeType QDomCDATASection.nodeType (self)
```

[

Returns `CDATASection`。

](qdomnode.html#NodeType-enum)