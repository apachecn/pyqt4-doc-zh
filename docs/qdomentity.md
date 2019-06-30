# QDomEntity Class Reference

## [[QtXml](index.htm) module]

该QDomEntity类表示一个XML实体。[More...](#details)

继承[QDomNode](qdomnode.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDomEntity x)`
*   `QDomNode.NodeType nodeType (self)`
*   `QString notationName (self)`
*   `QString publicId (self)`
*   `QString systemId (self)`

* * *

## Detailed Description

该QDomEntity类表示一个XML实体。

这个类表示XML文档中的一个实体，解析和未解析。请注意，此模型实体本身不是实体声明。

DOM不支持编辑实体节点，如果用户想更改一个实体的内容，每一个相关的[QDomEntityReference](qdomentityreference.html)节点必须更换在DOM树中通过的实体内容的克隆，然后进行必要的更改必须对每个克隆代替。一个实体节点的所有后代都是只读的。

一个实体节点没有任何父。

您可以访问该公司[publicId](qdomentity.html#publicId)（ ）[systemId](qdomentity.html#systemId)（）和[notationName](qdomentity.html#notationName)（ ）时可用。

关于文档对象模型有进一步的信息[Level 1](http://www.w3.org/TR/REC-DOM-Level-1/)和[Level 2 Core](http://www.w3.org/TR/DOM-Level-2-Core/)。对于更一般介绍的DOM实现的见[QDomDocument](qdomdocument.html)文档。

* * *

## Method Documentation

```
QDomEntity.__init__ (self)
```

构造一个空的实体。

```
QDomEntity.__init__ (self, QDomEntity x)
```

构造的副本_x_。

副本的数据是共享的（浅拷贝） ：修改一个节点也将改变其他。如果你想使一个深拷贝，使用[cloneNode](qdomnode.html#cloneNode)（ ） 。

```
QDomNode.NodeType QDomEntity.nodeType (self)
```

[

Returns `EntityNode`。

```
QString QDomEntity.notationName (self)
```

对于未解析实体这个函数返回的符号的实体的名称。对于已解析实体这个函数返回一个空字符串。

```
QString QDomEntity.publicId (self)
```

返回与此实体相关的公共标识符。如果未指定公共标识符是一个空字符串返回。

```
QString QDomEntity.systemId (self)
```

返回与此实体相关的系统标识符。如果未指定系统标识符是一个空字符串返回。

](qdomnode.html#NodeType-enum)