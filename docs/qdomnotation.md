# QDomNotation Class Reference

## [[QtXml](index.htm) module]

该QDomNotation类表示一个XML标记。[More...](#details)

继承[QDomNode](qdomnode.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDomNotation x)`
*   `QDomNode.NodeType nodeType (self)`
*   `QString publicId (self)`
*   `QString systemId (self)`

* * *

## Detailed Description

该QDomNotation类表示一个XML标记。

一个符号或者声明，按名称，一个未析实体的格式（参见XML 1.0规范的第4.7节） ，或者是用于处理指令目标的正式声明（见XML 1.0规范的第2.6节） 。

DOM不支持编辑符号的节点，它们是​​因此只读。

一个符号节点没有任何父。

You can retrieve the [publicId](qdomnotation.html#publicId)() and [systemId](qdomnotation.html#systemId)() from a notation node.

关于文档对象模型有进一步的信息[Level 1](http://www.w3.org/TR/REC-DOM-Level-1/)和[Level 2 Core](http://www.w3.org/TR/DOM-Level-2-Core/)。对于更一般介绍的DOM实现的见[QDomDocument](qdomdocument.html)文档。

* * *

## Method Documentation

```
QDomNotation.__init__ (self)
```

构造函数。

```
QDomNotation.__init__ (self, QDomNotation x)
```

构造的副本_x_。

副本的数据是共享的（浅拷贝） ：修改一个节点也将改变其他。如果你想使一个深拷贝，使用[cloneNode](qdomnode.html#cloneNode)（ ） 。

```
QDomNode.NodeType QDomNotation.nodeType (self)
```

[

Returns `NotationNode`。

```
QString QDomNotation.publicId (self)
```

返回此符号的公共标识符。

```
QString QDomNotation.systemId (self)
```

返回此标记的系统标识符。

](qdomnode.html#NodeType-enum)