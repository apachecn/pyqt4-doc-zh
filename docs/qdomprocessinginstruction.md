# QDomProcessingInstruction Class Reference

## [[QtXml](index.htm) module]

该QDomProcessingInstruction类表示一个XML处理指令。[More...](#details)

继承[QDomNode](qdomnode.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDomProcessingInstruction x)`
*   `QString data (self)`
*   `QDomNode.NodeType nodeType (self)`
*   `setData (self, QString d)`
*   `QString target (self)`

* * *

## Detailed Description

该QDomProcessingInstruction类表示一个XML处理指令。

处理指令中使用XML来保持处理器特定信息的文件的文本。

出现在XML文档的顶部，通常XML声明`&lt;?xml version='1.0' encoding='UTF-8'?&gt;`，由QDom视为一个处理指令。这是不幸的，因为XML声明是不是一个处理指令;之间的其他差异，但不能在任何地方，但在第一行插入到文档中。

请不要使用此函数来创建一个XML声明，因为尽管它具有相同的语法处理指令，它不是，而且可能不是由QDom如此对待。

处理指令的内容被检索到[data](qdomprocessinginstruction.html#data)（ ），并设置用[setData](qdomprocessinginstruction.html#setData)（ ） 。处理指令的目标与检索[target](qdomprocessinginstruction.html#target)（ ） 。

关于文档对象模型有进一步的信息[Level 1](http://www.w3.org/TR/REC-DOM-Level-1/)和[Level 2 Core](http://www.w3.org/TR/DOM-Level-2-Core/)。对于更一般介绍的DOM实现的见[QDomDocument](qdomdocument.html)文档。

* * *

## Method Documentation

```
QDomProcessingInstruction.__init__ (self)
```

构造一个空的处理指令。使用[QDomDocument.createProcessingInstruction](qdomdocument.html#createProcessingInstruction)（）来创建内容的处理指令。

```
QDomProcessingInstruction.__init__ (self, QDomProcessingInstruction x)
```

构造的副本_x_。

副本的数据是共享的（浅拷贝） ：修改一个节点也将改变其他。如果你想使一个深拷贝，使用[cloneNode](qdomnode.html#cloneNode)（ ） 。

```
QString QDomProcessingInstruction.data (self)
```

返回此处理指令的内容。

**See also** [setData](qdomprocessinginstruction.html#setData)（）和[target](qdomprocessinginstruction.html#target)（ ） 。

```
QDomNode.NodeType QDomProcessingInstruction.nodeType (self)
```

[

Returns `ProcessingInstructionNode`。

```
QDomProcessingInstruction.setData (self, QString d)
```

包含在处理指令的数据集，以_d_。

](qdomnode.html#NodeType-enum)

[**See also**](qdomnode.html#NodeType-enum) [data](qdomprocessinginstruction.html#data)（ ） 。

```
QString QDomProcessingInstruction.target (self)
```

返回此处理指令的目标。

**See also** [data](qdomprocessinginstruction.html#data)（ ） 。