# QPersistentModelIndex Class Reference

## [[QtCore](index.htm) module]

该QPersistentModelIndex类用于定位数据的数据模型。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QModelIndex index)`
*   `__init__ (self, QPersistentModelIndex other)`
*   `QModelIndex child (self, int row, int column)`
*   `int column (self)`
*   `QVariant data (self, int role = Qt.DisplayRole)`
*   `Qt.ItemFlags flags (self)`
*   `bool isValid (self)`
*   `QAbstractItemModel model (self)`
*   `QModelIndex parent (self)`
*   `int row (self)`
*   `QModelIndex sibling (self, int row, int column)`

### Special Methods

*   `bool __eq__ (self, QPersistentModelIndex other)`
*   `bool __eq__ (self, QModelIndex other)`
*   `bool __ge__ (self, QPersistentModelIndex other)`
*   `int __hash__ (self)`
*   `bool __lt__ (self, QPersistentModelIndex other)`
*   `bool __ne__ (self, QPersistentModelIndex other)`
*   `bool __ne__ (self, QModelIndex other)`

* * *

## Detailed Description

该QPersistentModelIndex类用于定位数据的数据模型。

一个QPersistentModelIndex是一个可以由应用程序来存储的，后来用于访问信息模型中的一个模型索引。不同的是[QModelIndex](qmodelindex.html)类，它是安全的存储QPersistentModelIndex因为该模型将确保引用的项目将继续是有效的，只要它们能够由模型来访问。

这是很好的做法，检查持久化模型指标均在使用它们之前有效。

* * *

## Method Documentation

```
QPersistentModelIndex.__init__ (self)
```

创建一个新的[QPersistentModelIndex](qpersistentmodelindex.html)这是该模型的一个拷贝_index_。

```
QPersistentModelIndex.__init__ (self, QModelIndex index)
```

```
QPersistentModelIndex.__init__ (self, QPersistentModelIndex other)
```

创建一个新的[QPersistentModelIndex](qpersistentmodelindex.html)这是的​​一个副本_other_持久化模型索引。

```
QModelIndex QPersistentModelIndex.child (self, int row, int column)
```

[

返回该模型索引被存储在给定的子_row_和_column_。

](qmodelindex.html)

[**See also**](qmodelindex.html) [parent](qpersistentmodelindex.html#parent)（）和[sibling](qpersistentmodelindex.html#sibling)（ ） 。

```
int QPersistentModelIndex.column (self)
```

返回该持久化模型指标指的是列。

```
QVariant QPersistentModelIndex.data (self, int role = Qt.DisplayRole)
```

返回数据为给定的_role_该项目由索引引用。

**See also** [Qt.ItemDataRole](qt.html#ItemDataRole-enum)和[QAbstractItemModel.setData](qabstractitemmodel.html#setData)（ ） 。

```
Qt.ItemFlags QPersistentModelIndex.flags (self)
```

[

返回该标志由索引所指的项目。

这个函数中引入了Qt 4.2中。

```
bool QPersistentModelIndex.isValid (self)
```

返回True如果这个持久化模型的索引是有效的，否则返回False 。

一个有效的指标属于一个模型，并具有非负的行数和列数。

](index.htm)

[**See also**](index.htm) [model](qpersistentmodelindex.html#model)（ ）[row](qpersistentmodelindex.html#row)（）和[column](qpersistentmodelindex.html#column)（ ） 。

```
QAbstractItemModel QPersistentModelIndex.model (self)
```

[

返回该指数属于典型的。

](qabstractitemmodel.html)

```
QModelIndex QPersistentModelIndex.parent (self)
```

[](qmodelindex.html)

[返回父](qmodelindex.html)[QModelIndex](qmodelindex.html)这种持续的指数，或无效[QModelIndex](qmodelindex.html)如果它没有父。

**See also** [child](qpersistentmodelindex.html#child)（ ）[sibling](qpersistentmodelindex.html#sibling)（）和[model](qpersistentmodelindex.html#model)（ ） 。

```
int QPersistentModelIndex.row (self)
```

返回此持续性模型索引是指该行。

```
QModelIndex QPersistentModelIndex.sibling (self, int row, int column)
```

[](qmodelindex.html)

[返回在同级_row_和_column_或无效的](qmodelindex.html)[QModelIndex](qmodelindex.html)如果没有兄弟在这个位置。

**See also** [parent](qpersistentmodelindex.html#parent)（）和[child](qpersistentmodelindex.html#child)（ ） 。

```
bool QPersistentModelIndex.__eq__ (self, QPersistentModelIndex other)
```

```
bool QPersistentModelIndex.__eq__ (self, QModelIndex other)
```

```
bool QPersistentModelIndex.__ge__ (self, QPersistentModelIndex other)
```

```
int QPersistentModelIndex.__hash__ (self)
```

```
bool QPersistentModelIndex.__lt__ (self, QPersistentModelIndex other)
```

```
bool QPersistentModelIndex.__ne__ (self, QPersistentModelIndex other)
```

```
bool QPersistentModelIndex.__ne__ (self, QModelIndex other)
```