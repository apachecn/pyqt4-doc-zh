# QSimpleXmlNodeModel Class Reference

## [[QtXmlPatterns](index.htm) module]

该QSimpleXmlNodeModel类是一个实现[QAbstractXmlNodeModel](qabstractxmlnodemodel.html)足以满足许多常见的情况。[More...](#details)

继承[QAbstractXmlNodeModel](qabstractxmlnodemodel.html)。

### Methods

*   `__init__ (self, QXmlNamePool namePool)`
*   `QUrl baseUri (self, QXmlNodeModelIndex node)`
*   `QXmlNodeModelIndex elementById (self, QXmlName id)`
*   `QXmlNamePool namePool (self)`
*   `list-of-QXmlName namespaceBindings (self, QXmlNodeModelIndex)`
*   `list-of-QXmlNodeModelIndex nodesByIdref (self, QXmlName idref)`
*   `QString stringValue (self, QXmlNodeModelIndex node)`

* * *

## Detailed Description

该QSimpleXmlNodeModel类是一个实现[QAbstractXmlNodeModel](qabstractxmlnodemodel.html)足以满足许多常见的情况。

子类化[QAbstractXmlNodeModel](qabstractxmlnodemodel.html)可以是一个显着的任务，因为它需要实现一些复杂的成员函数。 QSimpleXmlNodeModel提供这些成员函数，适合在多种节点模型的默认实现。

QSimpleXmlNodeModel的子类必须是线程安全的。

* * *

## Method Documentation

```
QSimpleXmlNodeModel.__init__ (self, QXmlNamePool namePool)
```

构造一个[QSimpleXmlNodeModel](qsimplexmlnodemodel.html)用于与具有指定使用_namePool_。

```
QUrl QSimpleXmlNodeModel.baseUri (self, QXmlNodeModelIndex node)
```

[](qurl.html)

[从重新实现](qurl.html)[QAbstractXmlNodeModel.baseUri](qabstractxmlnodemodel.html#baseUri)（ ） 。

返回的基URI_node_。这始终是文档的URI 。

**See also** [documentUri](qabstractxmlnodemodel.html#documentUri)（ ） 。

```
QXmlNodeModelIndex QSimpleXmlNodeModel.elementById (self, QXmlName id)
```

[](qxmlnodemodelindex.html)

[从重新实现](qxmlnodemodelindex.html)[QAbstractXmlNodeModel.elementById](qabstractxmlnodemodel.html#elementById)（ ） 。

总是返回构造一个默认的[QXmlNodeModelIndex](qxmlnodemodelindex.html)比如，不管_id_。

这实际上意味着该模型没有说有一个id的元素。

```
QXmlNamePool QSimpleXmlNodeModel.namePool (self)
```

[](qxmlnamepool.html)

[返回与此模式相关联的名称池。实施](qxmlnamepool.html)[name](qabstractxmlnodemodel.html#name)（ ）将使用此名称池创建名称。

```
list-of-QXmlName QSimpleXmlNodeModel.namespaceBindings (self, QXmlNodeModelIndex)
```

从重新实现[QAbstractXmlNodeModel.namespaceBindings](qabstractxmlnodemodel.html#namespaceBindings)（ ） 。

总是返回一个空[QVector](index.htm)。这预示着，没有命名空间绑定的范围_node_。

```
list-of-QXmlNodeModelIndex QSimpleXmlNodeModel.nodesByIdref (self, QXmlName idref)
```

从重新实现[QAbstractXmlNodeModel.nodesByIdref](qabstractxmlnodemodel.html#nodesByIdref)（ ） 。

总是返回一个空向量，无论_idref_。

这实际上意味着，该模型具有类型的任何元素或属性`IDREF`。

```
QString QSimpleXmlNodeModel.stringValue (self, QXmlNodeModelIndex node)
```

从重新实现[QAbstractXmlNodeModel.stringValue](qabstractxmlnodemodel.html#stringValue)（ ） 。

If _node_是一个元素或属性，[typedValue](qabstractxmlnodemodel.html#typedValue)（）被调用，并返回值转换成字符串，按[XQuery](index.htm)的规则。

If _node_是另一种类型的节点，则返回空字符串。

如果此功能用于注释或处理指令中被重写时，要记得把它（为元素是重要的，属性有类型的值不`xs:string`），以确保按照该值的格式[XQuery](index.htm)。