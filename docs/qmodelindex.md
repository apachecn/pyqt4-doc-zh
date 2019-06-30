# QModelIndex Class Reference

## [[QtCore](index.htm) module]

该QModelIndex类用于定位数据的数据模型。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QModelIndex other)`
*   `__init__ (self, QPersistentModelIndex)`
*   `QModelIndex child (self, int arow, int acolumn)`
*   `int column (self)`
*   `QVariant data (self, int role = Qt.DisplayRole)`
*   `Qt.ItemFlags flags (self)`
*   `int internalId (self)`
*   `object internalPointer (self)`
*   `bool isValid (self)`
*   `QAbstractItemModel model (self)`
*   `QModelIndex parent (self)`
*   `int row (self)`
*   `QModelIndex sibling (self, int arow, int acolumn)`

### Special Methods

*   `bool __eq__ (self, QModelIndex other)`
*   `bool __ge__ (self, QModelIndex other)`
*   `int __hash__ (self)`
*   `bool __lt__ (self, QModelIndex other)`
*   `bool __ne__ (self, QModelIndex other)`

* * *

## Detailed Description

该QModelIndex类用于定位数据的数据模型。

这个类被用作源自一个索引项的模型[QAbstractItemModel](qabstractitemmodel.html)。该指数是由项目的意见，委讬和选择模型来定位模型中的项目。

新QModelIndex目的是通过使用模型创建的[QAbstractItemModel.createIndex](qabstractitemmodel.html#createIndex)（）函数。一个_invalid_模型索引可以用QModelIndex构造函数来构造。参考模型中的顶级项目时无效索引经常被用作父索引。

型号索引参考模型中的项目，并包含所有需要指定在这些模型及其位置的信息。每个索引位于一个给定行和列中，并且可以具有一个父索引;使用[row](qmodelindex.html#row)（ ）[column](qmodelindex.html#column)（）和[parent](qmodelindex.html#parent)（ ）来获取这些信息。模型中的每个顶级项目是由不具有父指数模型指数表示 - 在这种情况下，[parent](qmodelindex.html#parent)（ ）将返回一个无效的模型索引，相当于用的零参数的形式构建的指数[QModelIndex](qmodelindex.html#QModelIndex)（ ）构造函数。

要获取是指在模型中的现有项目的模型索引，调用[QAbstractItemModel.index](qabstractitemmodel.html#index)（ ）所要求的行和列的值，与母公司的模型索引。当提到​​在一个模型中，供应顶级项目[QModelIndex](qmodelindex.html#QModelIndex)（ ）作为主指数。

该[model](qmodelindex.html#model)（ ）函数返回模型的索引引用作为[QAbstractItemModel](qabstractitemmodel.html)。该[child](qmodelindex.html#child)（ ）函数用于检查模型中的指数下举行的项目。该[sibling](qmodelindex.html#sibling)（ ）函数允许您遍历在同一水平作为指标在模型中的项目。

**Note:**型号索引应立即再丢弃使用。你不应该依赖于索引调用该改变模型的结构或删除项目模型函数后仍然有效。如果你需要保持一个模型索引随着时间的推移使用[QPersistentModelIndex](qpersistentmodelindex.html)。

* * *

## Method Documentation

```
QModelIndex.__init__ (self)
```

创建一个新的空模型索引。这种类型的模型索引被用来表示模型中的位置是无效的。

**See also** [isValid](qmodelindex.html#isValid)（）和[QAbstractItemModel](qabstractitemmodel.html)。

```
QModelIndex.__init__ (self, QModelIndex other)
```

创建一个新的模型索引是的副本_other_模型索引。

```
QModelIndex.__init__ (self, QPersistentModelIndex)
```

```
QModelIndex QModelIndex.child (self, int arow, int acolumn)
```

[

返回该模型索引被存储在给定的子_row_和_column_。

**Note:**此功能不适用于其经常被用来作为根索引无效的模型索引工作。

](qmodelindex.html)

[**See also**](qmodelindex.html) [parent](qmodelindex.html#parent)（）和[sibling](qmodelindex.html#sibling)（ ） 。

```
int QModelIndex.column (self)
```

返回此模型索引是指该列。

```
QVariant QModelIndex.data (self, int role = Qt.DisplayRole)
```

返回数据为给定的_role_该项目由索引引用。

```
Qt.ItemFlags QModelIndex.flags (self)
```

[

返回该标志由索引所指的项目。

这个函数中引入了Qt 4.2中。

```
int QModelIndex.internalId (self)
```

返回`long`所使用的模型的索引与内部数据结构相关联。

](index.htm)

[**See also**](index.htm) [QAbstractItemModel.createIndex](qabstractitemmodel.html#createIndex)（ ） 。

```
object QModelIndex.internalPointer (self)
```

返回`void` `*`指针所使用的模型，以该指数与内部数据结构相关联。

**See also** [QAbstractItemModel.createIndex](qabstractitemmodel.html#createIndex)（ ） 。

```
bool QModelIndex.isValid (self)
```

返回True如果这个模型索引是有效的，否则返回False 。

一个有效的指标属于一个模型，并具有非负的行数和列数。

**See also** [model](qmodelindex.html#model)（ ）[row](qmodelindex.html#row)（）和[column](qmodelindex.html#column)（ ） 。

```
QAbstractItemModel QModelIndex.model (self)
```

[

返回一个指向包含该指标是指项目的模型。

的常量指针模型返回，因为调用模型的非const函数可能失效模型索引，并可能引起程序崩溃。

](qabstractitemmodel.html)

```
QModelIndex QModelIndex.parent (self)
```

[](qmodelindex.html)

[返回模型索引的父母，或](qmodelindex.html)[QModelIndex](qmodelindex.html#QModelIndex)（ ） ，如果它没有父。

**See also** [child](qmodelindex.html#child)（ ）[sibling](qmodelindex.html#sibling)（）和[model](qmodelindex.html#model)（ ） 。

```
int QModelIndex.row (self)
```

返回此模型索引是指该行。

```
QModelIndex QModelIndex.sibling (self, int arow, int acolumn)
```

[](qmodelindex.html)

[返回在同级_row_和_column_。如果没有兄弟在这个位置上，​​一个无效的](qmodelindex.html)[QModelIndex](qmodelindex.html)返回。

**See also** [parent](qmodelindex.html#parent)（）和[child](qmodelindex.html#child)（ ） 。

```
bool QModelIndex.__eq__ (self, QModelIndex other)
```

```
bool QModelIndex.__ge__ (self, QModelIndex other)
```

```
int QModelIndex.__hash__ (self)
```

```
bool QModelIndex.__lt__ (self, QModelIndex other)
```

```
bool QModelIndex.__ne__ (self, QModelIndex other)
```