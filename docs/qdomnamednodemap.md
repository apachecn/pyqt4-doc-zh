# QDomNamedNodeMap Class Reference

## [[QtXml](index.htm) module]

该QDomNamedNodeMap类包含了可以通过名称访问的节点的集合。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDomNamedNodeMap)`
*   `bool contains (self, QString name)`
*   `int count (self)`
*   `bool isEmpty (self)`
*   `QDomNode item (self, int index)`
*   `int length (self)`
*   `QDomNode namedItem (self, QString name)`
*   `QDomNode namedItemNS (self, QString nsURI, QString localName)`
*   `QDomNode removeNamedItem (self, QString name)`
*   `QDomNode removeNamedItemNS (self, QString nsURI, QString localName)`
*   `QDomNode setNamedItem (self, QDomNode newNode)`
*   `QDomNode setNamedItemNS (self, QDomNode newNode)`
*   `int size (self)`

### Special Methods

*   `bool __eq__ (self, QDomNamedNodeMap)`
*   `__len__ (self)`
*   `bool __ne__ (self, QDomNamedNodeMap)`

* * *

## Detailed Description

该QDomNamedNodeMap类包含了可以通过名称访问的节点的集合。

需要注意的是QDomNamedNodeMap不从继承[QDomNodeList](qdomnodelist.html)。 QDomNamedNodeMaps不提供任何特定的节点的顺序。虽然在QDomNamedNodeMap节点可以按序号索引访问，这简直是允许的QDomNamedNodeMap的内容，方便枚举，并不意味着DOM指定节点的排序。

该QDomNamedNodeMap是用在三个地方：

1.  [QDomDocumentType.entities](qdomdocumenttype.html#entities)（）返回在DTD中描述的所有实体的地图。
2.  [QDomDocumentType.notations](qdomdocumenttype.html#notations)（）返回在DTD中描述的所有符号的地图。
3.  [QDomNode.attributes](qdomnode.html#attributes)（）返回一个元素的所有属性的地图。

在地图上项目，确定哪些QDomNode.name （）返回的名称。节点使用检索[namedItem](qdomnamednodemap.html#namedItem)（ ）[namedItemNS](qdomnamednodemap.html#namedItemNS)（）或[item](qdomnamednodemap.html#item)（ ） 。新节点插入[setNamedItem](qdomnamednodemap.html#setNamedItem)（）或[setNamedItemNS](qdomnamednodemap.html#setNamedItemNS)（ ）中，用去除[removeNamedItem](qdomnamednodemap.html#removeNamedItem)（）或[removeNamedItemNS](qdomnamednodemap.html#removeNamedItemNS)（ ） 。使用[contains](qdomnamednodemap.html#contains)（ ），看看是否具有给定名称的产品在命名节点图。项的数目被返回[length](qdomnamednodemap.html#length)（ ） 。

术语：在这个类中我们使用“项目”和“节点”可以互换。

* * *

## Method Documentation

```
QDomNamedNodeMap.__init__ (self)
```

构造一个空的命名节点图。

```
QDomNamedNodeMap.__init__ (self, QDomNamedNodeMap)
```

构造的副本_n_。

```
bool QDomNamedNodeMap.contains (self, QString name)
```

如果地图包含称为一个节点，则返回True_name_否则返回False 。

**Note:**这个功能并不需要命名空间的存在考虑。使用[namedItemNS](qdomnamednodemap.html#namedItemNS)（ ）来测试地图是否包含与特定的命名空间URI和名称的节点。

```
int QDomNamedNodeMap.count (self)
```

这个功能是为Qt API的一致性。它相当于[length](qdomnamednodemap.html#length)（ ） 。

```
bool QDomNamedNodeMap.isEmpty (self)
```

返回True如果该映射为空，否则返回False 。这个功能是为Qt API的一致性。

```
QDomNode QDomNamedNodeMap.item (self, int index)
```

[

检索位置的节点_index_。

这可以用来遍历图。请注意，在图中的节点被任意排列。

](qdomnode.html)

[**See also**](qdomnode.html) [length](qdomnamednodemap.html#length)（ ） 。

```
int QDomNamedNodeMap.length (self)
```

返回节点的地图数。

**See also** [item](qdomnamednodemap.html#item)（ ） 。

```
QDomNode QDomNamedNodeMap.namedItem (self, QString name)
```

[

返回称为节点_name_。

](qdomnode.html)

[如果指定的节点映射不包含这样的节点，](qdomnode.html)[null node](qdomnode.html#isNull)返回。节点的名称是返回的名称[QDomNode.nodeName](qdomnode.html#nodeName)（ ） 。

**See also** [setNamedItem](qdomnamednodemap.html#setNamedItem)（）和[namedItemNS](qdomnamednodemap.html#namedItemNS)（ ） 。

```
QDomNode QDomNamedNodeMap.namedItemNS (self, QString nsURI, QString localName)
```

[

返回与本地名称相关联的节点_localName_和命名空间URI_nsURI_。

](qdomnode.html)

[如果地图不包含这样一个节点，](qdomnode.html)[null node](qdomnode.html#isNull)返回。

**See also** [setNamedItemNS](qdomnamednodemap.html#setNamedItemNS)（）和[namedItem](qdomnamednodemap.html#namedItem)（ ） 。

```
QDomNode QDomNamedNodeMap.removeNamedItem (self, QString name)
```

[

所谓的删除节点_name_从地图。

](qdomnode.html)

[该函数返回删除节点或](qdomnode.html)[null node](qdomnode.html#isNull)如果映射不包含称为节点_name_。

**See also** [setNamedItem](qdomnamednodemap.html#setNamedItem)（ ）[namedItem](qdomnamednodemap.html#namedItem)（）和[removeNamedItemNS](qdomnamednodemap.html#removeNamedItemNS)（ ） 。

```
QDomNode QDomNamedNodeMap.removeNamedItemNS (self, QString nsURI, QString localName)
```

[

删除与本地名称的节点_localName_和命名空间URI_nsURI_从地图。

](qdomnode.html)

[该函数返回删除节点或](qdomnode.html)[null node](qdomnode.html#isNull)如果地图没有包含与本地名称的节点_localName_和命名空间URI_nsURI_。

**See also** [setNamedItemNS](qdomnamednodemap.html#setNamedItemNS)（ ）[namedItemNS](qdomnamednodemap.html#namedItemNS)（）和[removeNamedItem](qdomnamednodemap.html#removeNamedItem)（ ） 。

```
QDomNode QDomNamedNodeMap.setNamedItem (self, QDomNode newNode)
```

[](qdomnode.html)

[插入节点_newNode_放到指定的节点图。所使用的地图名称为的节点名称_newNode_所返回](qdomnode.html)[QDomNode.nodeName](qdomnode.html#nodeName)（ ） 。

如果新节点替换现有节点，即在地图包含具有相同名称的节点，则返回被替换节点。

**See also** [namedItem](qdomnamednodemap.html#namedItem)（ ）[removeNamedItem](qdomnamednodemap.html#removeNamedItem)（）和[setNamedItemNS](qdomnamednodemap.html#setNamedItemNS)（ ） 。

```
QDomNode QDomNamedNodeMap.setNamedItemNS (self, QDomNode newNode)
```

[

插入节点_newNode_在地图上。如果具有相同的命名空间URI和本地相同名称的节点已经存在于地图上，它被替换_newNode_。如果新节点替换现有节点，则返回被替换节点。

](qdomnode.html)

[**See also**](qdomnode.html) [namedItemNS](qdomnamednodemap.html#namedItemNS)（ ）[removeNamedItemNS](qdomnamednodemap.html#removeNamedItemNS)（）和[setNamedItem](qdomnamednodemap.html#setNamedItem)（ ） 。

```
int QDomNamedNodeMap.size (self)
```

这个功能是为Qt API的一致性。它相当于[length](qdomnamednodemap.html#length)（ ） 。

```
bool QDomNamedNodeMap.__eq__ (self, QDomNamedNodeMap)
```

```
 QDomNamedNodeMap.__len__ (self)
```

```
bool QDomNamedNodeMap.__ne__ (self, QDomNamedNodeMap)
```