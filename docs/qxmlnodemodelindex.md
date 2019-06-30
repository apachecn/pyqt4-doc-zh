# QXmlNodeModelIndex Class Reference

## [[QtXmlPatterns](index.htm) module]

该QXmlNodeModelIndex类标识从子类中的XML节点模型的节点[QAbstractXmlNodeModel](qabstractxmlnodemodel.html)。[More...](#details)

### Types

*   `enum DocumentOrder { Precedes, Is, Follows }`
*   `enum NodeKind { Attribute, Comment, Document, Element, ..., Text }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QXmlNodeModelIndex other)`
*   `int additionalData (self)`
*   `int data (self)`
*   `object internalPointer (self)`
*   `bool isNull (self)`
*   `QAbstractXmlNodeModel model (self)`

### Special Methods

*   `bool __eq__ (self, QXmlNodeModelIndex other)`
*   `int __hash__ (self)`
*   `bool __ne__ (self, QXmlNodeModelIndex other)`

* * *

## Detailed Description

该QXmlNodeModelIndex类标识从子类中的XML节点模型的节点[QAbstractXmlNodeModel](qabstractxmlnodemodel.html)。

QXmlNodeModelIndex是一个索引到一个[XML node model](qabstractxmlnodemodel.html)。它包含：

*   A pointer to an [XML node model](qabstractxmlnodemodel.html), which is returned by [model](qxmlnodemodelindex.html#model)(), and
*   Some data, which is returned by [data](qxmlnodemodelindex.html#data)(), [internalPointer](qxmlnodemodelindex.html#internalPointer)(), and [additionalData](qxmlnodemodelindex.html#additionalData)().

因为QXmlNodeModelIndex是故意一个简单的类，它没有成员函数来访问节点的属性。例如，它不具有用于获取节点的名称或属性或子节点的列表的功能。如果你发现你需要找回这种从查询结果的信息，有两种方法来进行。

*   Send the output of your [XQuery](index.htm) to an [XML receiver](qabstractxmlreceiver.html), or
*   Let your [XQuery](index.htm) do all the work to produce the desired result.

第二个案例是通过例子来说明。假设你要填充列表控件与一组结果元素的某些属性的值。你可以写一个[XQuery](index.htm)返回元素集合，然后你会写遍历结果元素，得到他们的属性，并提取所需的字符串值的代码。但更简单的办法，那就是增加你的[XQuery](index.htm)寻找所需的属性值。然后，所有你所要做的就是评估[XQuery](index.htm)使用的版本[QXmlQuery.evaluateTo](qxmlquery.html#evaluateTo)（）为填充[QStringList](qstringlist.html)，您可以直接发送到您的Widget 。

QXmlNodeModelIndex不强加任何限制`data`看重的QXmlNodeModelIndex应包含的内容。数据的含义左到相关的[node model](qabstractxmlnodemodel.html)。因为QXmlNodeModelIndex依赖于特定的子类[QAbstractXmlNodeModel](qabstractxmlnodemodel.html)它的存在，你可以创建QXmlNodeModelIndex的一个实例的唯一方法是通过询问节点模型与为您创建一个[QAbstractXmlNodeModel.createIndex](qabstractxmlnodemodel.html#createIndex)（ ） 。由于该功能是受保护的，它通常是一个好主意，写一个公共函数，从参数是适合您的特定节点的模型创建一个QXmlNodeModelIndex 。

一个默认的构造节点索引据说是空，即，[isNull](qxmlnodemodelindex.html#isNull)（ ）返回True 。

QXmlNodeModelIndex和[QAbstractXmlNodeModel](qabstractxmlnodemodel.html)遵循用于相同的设计图案[QModelIndex](qmodelindex.html)和[QAbstractItemModel](qabstractitemmodel.html)。

* * *

## Type Documentation

```
QXmlNodeModelIndex.DocumentOrder
```

标识特定的节点比较运算符，应使用。

| Constant | Value | Description |
| --- | --- | --- |
| `QXmlNodeModelIndex.Precedes` | `-1` | 标志着`\&lt;\&lt;`运营商。测试第一个操作数是否优先于第二个文件中。 |
| `QXmlNodeModelIndex.Follows` | `1` | 标志着`\&gt;\&gt;`运营商。测试第一个操作数是否遵循第二文档中。 |
| `QXmlNodeModelIndex.Is` | `0` | 标志着`is`运营商。测试两个节点是否有相同的节点标识。 |

```
QXmlNodeModelIndex.NodeKind
```

确定了一种节点。

| Constant | Value | Description |
| --- | --- | --- |
| `QXmlNodeModelIndex.Attribute` | `1` | 标识属性节点 |
| `QXmlNodeModelIndex.Text` | `64` | 识别文本节点 |
| `QXmlNodeModelIndex.Comment` | `2` | 标识一个注释节点 |
| `QXmlNodeModelIndex.Document` | `4` | 标识一个文档节点 |
| `QXmlNodeModelIndex.Element` | `8` | 标识一个元素节点 |
| `QXmlNodeModelIndex.Namespace` | `16` | 标识一个命名空间节点 |
| `QXmlNodeModelIndex.ProcessingInstruction` | `32` | 识别处理指令。 |

请注意，可选的XML声明的XML文档的最开始并不是一个处理指令

**See also** [QAbstractXmlNodeModel.kind](qabstractxmlnodemodel.html#kind)（ ） 。

* * *

## Method Documentation

```
QXmlNodeModelIndex.__init__ (self)
```

默认构造函数。创建一个项目，是`null`。

**See also** [isNull](qxmlnodemodelindex.html#isNull)（ ） 。

```
QXmlNodeModelIndex.__init__ (self, QXmlNodeModelIndex other)
```

标准的拷贝构造函数。创建[QXmlNodeModelIndex](qxmlnodemodelindex.html)例如，它是一个拷贝_other_。

```
int QXmlNodeModelIndex.additionalData (self)
```

返回第二数据值。该节点的索引保存两个数据值。[data](qxmlnodemodelindex.html#data)（ ）返回第一个。

**See also** [data](qxmlnodemodelindex.html#data)（ ） 。

```
int QXmlNodeModelIndex.data (self)
```

返回第一个数据值。该节点的索引保存两个数据值。[additionalData](qxmlnodemodelindex.html#additionalData)（ ）返回第二个。

**See also** [additionalData](qxmlnodemodelindex.html#additionalData)（ ） 。

```
object QXmlNodeModelIndex.internalPointer (self)
```

返回第一个数据值作为一个void *指针。

**See also** [additionalData](qxmlnodemodelindex.html#additionalData)（ ） 。

```
bool QXmlNodeModelIndex.isNull (self)
```

返回True如果[QXmlNodeModelIndex](qxmlnodemodelindex.html)是一个默认的构造值，否则返回False 。

空[QXmlNodeModelIndex](qxmlnodemodelindex.html)不代表任何节点，并且可以与同时使用[QAbstractXmlNodeModel](qabstractxmlnodemodel.html)。

```
QAbstractXmlNodeModel QXmlNodeModelIndex.model (self)
```

[](qabstractxmlnodemodel.html)

[返回](qabstractxmlnodemodel.html)[QAbstractXmlNodeModel](qabstractxmlnodemodel.html)该节点的索引指。[QXmlNodeModelIndex](qxmlnodemodelindex.html)不拥有[QAbstractXmlNodeModel](qabstractxmlnodemodel.html)并没有保持其一生的轨迹，因此这个指针将吊着如果[QAbstractXmlNodeModel](qabstractxmlnodemodel.html)首先释放。

有实例的，因为没有setter的节点模型[QXmlNodeModelIndex](qxmlnodemodelindex.html)实例仅创建[QAbstractXmlNodeModel.createIndex](qabstractxmlnodemodel.html#createIndex)（ ） 。

```
bool QXmlNodeModelIndex.__eq__ (self, QXmlNodeModelIndex other)
```

```
int QXmlNodeModelIndex.__hash__ (self)
```

```
bool QXmlNodeModelIndex.__ne__ (self, QXmlNodeModelIndex other)
```