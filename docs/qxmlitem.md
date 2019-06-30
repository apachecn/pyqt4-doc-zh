# QXmlItem Class Reference

## [[QtXmlPatterns](index.htm) module]

该QXmlItem类包含一个XML节点或者原子值。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QXmlItem other)`
*   `__init__ (self, QXmlNodeModelIndex node)`
*   `__init__ (self, QVariant atomicValue)`
*   `bool isAtomicValue (self)`
*   `bool isNode (self)`
*   `bool isNull (self)`
*   `QVariant toAtomicValue (self)`
*   `QXmlNodeModelIndex toNodeModelIndex (self)`

* * *

## Detailed Description

该QXmlItem类包含一个XML节点或者原子值。

In [XQuery](index.htm)，所有的表达式求项目，其中每个项目是一个XML节点或者原子值的序列。下面的代码片段的查询结果为五个项目序列。

```
 <aNode/>,
 xs:base64Binary("FFFF"),
 current-date(),
 3e3, (: A floating point value :)
 attribute {"name"} {()}

```

这五个项目是：元素，原子值（以base64编码的二进制数据） ，一个日期，一个float和一个属性。

QXmlItem是代表这些阶级[XQuery](index.htm)中的项目[QtXmlPatterns](index.htm)API。 QXmlItem的非空实例可以是一个节点或者原子值。调用[isNode](qxmlitem.html#isNode)（）或[isAtomicValue](qxmlitem.html#isAtomicValue)（）告诉你它是。原子值是Qt的API，在其他地方表示为实例[QVariant](qvariant.html)和QXmlItem的一个实例，它表示一个原子值可以被转换为一个[QVariant](qvariant.html)通过调用[toAtomicValue](qxmlitem.html#toAtomicValue)（ ） 。一个封装了节点A QXmlItem在别处表示为实例[QXmlNodeModelIndex](qxmlnodemodelindex.html)。一个节点QXmlItem可以转换为一[QXmlNodeModelIndex](qxmlnodemodelindex.html)通过调用[toNodeModelIndex](qxmlitem.html#toNodeModelIndex)（ ） 。

一个默认的构造QXmlItem实例既不是一个节点，也不是一个原子值。它被认为是零，在这种情况[isNull](qxmlitem.html#isNull)（ ）返回True 。

QXmlItem的实例将留给晃来晃去，如果[XML node model](qabstractxmlnodemodel.html)它是指被删除时，如果它是一个[QXmlNodeModelIndex](qxmlnodemodelindex.html)。

* * *

## Method Documentation

```
QXmlItem.__init__ (self)
```

构造一个空[QXmlItem](qxmlitem.html)既不是一个节点，也不是一个原子值。[isNull](qxmlitem.html#isNull)（）为一个默认的构造实例返回True。

```
QXmlItem.__init__ (self, QXmlItem other)
```

拷贝构造函数构造的一个副本_other_。

```
QXmlItem.__init__ (self, QXmlNodeModelIndex node)
```

构造一个节点[QXmlItem](qxmlitem.html)即副本_node_。

**See also** [isNode](qxmlitem.html#isNode)（ ） 。

```
QXmlItem.__init__ (self, QVariant atomicValue)
```

构造一个原子值[QXmlItem](qxmlitem.html)同_atomicValue_。

**See also** [isAtomicValue](qxmlitem.html#isAtomicValue)（ ） 。

```
bool QXmlItem.isAtomicValue (self)
```

返回True如果这个项目是原子值。则返回False ，如果它是一个节点或空。

**See also** [isNull](qxmlitem.html#isNull)（）和[isNode](qxmlitem.html#isNode)（ ） 。

```
bool QXmlItem.isNode (self)
```

返回True如果这个项目是一个节点。则返回False ，如果它是一个原子值或空值。

**See also** [isNull](qxmlitem.html#isNull)（）和[isAtomicValue](qxmlitem.html#isAtomicValue)（ ） 。

```
bool QXmlItem.isNull (self)
```

返回True如果[QXmlItem](qxmlitem.html)既不是一个节点，也不是一个原子值。建造默认实例[QXmlItem](qxmlitem.html)为空。

```
QVariant QXmlItem.toAtomicValue (self)
```

如果这[QXmlItem](qxmlitem.html)表示原子值时，它被转换为一个适当的[QVariant](qvariant.html)并返回。如果这[QXmlItem](qxmlitem.html)是不是一个原子值，返回值是构造一个默认的[QVariant](qvariant.html)。您可以致电[isAtomicValue](qxmlitem.html#isAtomicValue)（ ）测试项目是否是一个原子值。

**See also** [isAtomicValue](qxmlitem.html#isAtomicValue)（ ） 。

```
QXmlNodeModelIndex QXmlItem.toNodeModelIndex (self)
```

[](qxmlnodemodelindex.html)

[如果这](qxmlnodemodelindex.html)[QXmlItem](qxmlitem.html)代表一个节点，它返回的项目作为[QXmlNodeModelIndex](qxmlnodemodelindex.html)。如果这[QXmlItem](qxmlitem.html)是不是一个节点，返回值是不确定的。您可以致电[isNode](qxmlitem.html#isNode)（ ）测试项目是否是一个节点。

**See also** [isNode](qxmlitem.html#isNode)（ ） 。