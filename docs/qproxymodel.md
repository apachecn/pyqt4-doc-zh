# QProxyModel Class Reference

## [[QtGui](index.htm) module]

该QProxyModel类提供了另一个模型和视图之间传递的数据处理支持。[More...](#details)

继承[QAbstractItemModel](qabstractitemmodel.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `int columnCount (self, QModelIndex parent = QModelIndex())`
*   `QVariant data (self, QModelIndex index, int role = Qt.DisplayRole)`
*   `bool dropMimeData (self, QMimeData data, Qt.DropAction action, int row, int column, QModelIndex parent)`
*   `fetchMore (self, QModelIndex parent)`
*   `Qt.ItemFlags flags (self, QModelIndex index)`
*   `bool hasChildren (self, QModelIndex parent = QModelIndex())`
*   `QVariant headerData (self, int section, Qt.Orientation orientation, int role = Qt.DisplayRole)`
*   `QModelIndex index (self, int row, int column, QModelIndex parent = QModelIndex())`
*   `bool insertColumns (self, int column, int count, QModelIndex parent = QModelIndex())`
*   `bool insertRows (self, int row, int count, QModelIndex parent = QModelIndex())`
*   `list-of-QModelIndex match (self, QModelIndex start, int role, QVariant value, int hits = 1, Qt.MatchFlags flags = Qt.MatchFlags(Qt.MatchStartsWith|Qt.MatchWrap))`
*   `QMimeData mimeData (self, list-of-QModelIndex indexes)`
*   `QStringList mimeTypes (self)`
*   `QAbstractItemModel model (self)`
*   `QModelIndex parent (self, QModelIndex child)`
*   `QObject parent (self)`
*   `revert (self)`
*   `int rowCount (self, QModelIndex parent = QModelIndex())`
*   `bool setData (self, QModelIndex index, QVariant value, int role = Qt.EditRole)`
*   `bool setHeaderData (self, int section, Qt.Orientation orientation, QVariant value, int role = Qt.EditRole)`
*   `setModel (self, QAbstractItemModel model)`
*   `sort (self, int column, Qt.SortOrder order = Qt.AscendingOrder)`
*   `QSize span (self, QModelIndex index)`
*   `bool submit (self)`
*   `Qt.DropActions supportedDropActions (self)`

* * *

## Detailed Description

该QProxyModel类提供了另一个模型和视图之间传递的数据处理支持。

如果你想要做筛选和排序，请参阅[QSortFilterProxyModel](qsortfilterproxymodel.html)。

代理模型提供了可用于操纵通过一个基本的模型中检索到的数据的标准模型接口。它们可以被用来执行操作，例如排序，并在不改变模型的内容而获得的数据滤波。

正如的子类[QAbstractItemView](qabstractitemview.html)， QProxyModel提供[setModel](qproxymodel.html#setModel)（）函数，用于指定要由代理将作用于模型。视图可以连接到任何底层模型或所述代理模型与[QAbstractItemView.setModel](qabstractitemview.html#setModel)（ ） 。

由于意见依赖所提供的模型索引来标识数据项的模型，并在一些可视化表示定位这些物品的信息，代理模式必须建立，而不是从它们的底层模型提供模型索引自己的模型索引。

* * *

## Method Documentation

```
QProxyModel.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个代理模型与给定_parent_。

```
int QProxyModel.columnCount (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.columnCount](qabstractitemmodel.html#columnCount)（ ） 。

返回列的数目为给定的_parent_。

**See also** [QAbstractItemModel.columnCount](qabstractitemmodel.html#columnCount)（ ） 。

```
QVariant QProxyModel.data (self, QModelIndex index, int role = Qt.DisplayRole)
```

从重新实现[QAbstractItemModel.data](qabstractitemmodel.html#data)（ ） 。

返回存储在该项目中的数据与给定_index_指定下_role_。

**See also** [setData](qproxymodel.html#setData)（ ） 。

```
bool QProxyModel.dropMimeData (self, QMimeData data, Qt.DropAction action, int row, int column, QModelIndex parent)
```

从重新实现[QAbstractItemModel.dropMimeData](qabstractitemmodel.html#dropMimeData)（ ） 。

如果模型接受返回True_data_滴到用于指定附加的视图_action_否则返回False 。

该_parent_，_row_和_column_细节可以被用于控制当通过拖放系统接收的MIME类型是可以接受的一个模型的不同部分。

```
QProxyModel.fetchMore (self, QModelIndex parent)
```

从重新实现[QAbstractItemModel.fetchMore](qabstractitemmodel.html#fetchMore)（ ） 。

获取给定的多个子项_parent_。此功能用于通过视图来告诉他们可以显示比模型提供了更多的数据模型。

**See also** [QAbstractItemModel.fetchMore](qabstractitemmodel.html#fetchMore)（ ） 。

```
Qt.ItemFlags QProxyModel.flags (self, QModelIndex index)
```

[](index.htm)

[从重新实现](index.htm)[QAbstractItemModel.flags](qabstractitemmodel.html#flags)（ ） 。

返回项标志为给定的_index_。

```
bool QProxyModel.hasChildren (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.hasChildren](qabstractitemmodel.html#hasChildren)（ ） 。

返回True ，如果该项目对应的_parent_指数有子项，否则返回False 。

**See also** [QAbstractItemModel.hasChildren](qabstractitemmodel.html#hasChildren)（ ） 。

```
QVariant QProxyModel.headerData (self, int section, Qt.Orientation orientation, int role = Qt.DisplayRole)
```

从重新实现[QAbstractItemModel.headerData](qabstractitemmodel.html#headerData)（ ） 。

返回存储在数据_section_与所指定的报头的_orientation_根据给定的_role_。

**See also** [setHeaderData](qproxymodel.html#setHeaderData)（ ） 。

```
QModelIndex QProxyModel.index (self, int row, int column, QModelIndex parent = QModelIndex())
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemModel.index](qabstractitemmodel.html#index)（ ） 。

返回模型指数与给定_row_，_column_和_parent_。

**See also** [QAbstractItemModel.index](qabstractitemmodel.html#index)（ ） 。

```
bool QProxyModel.insertColumns (self, int column, int count, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.insertColumns](qabstractitemmodel.html#insertColumns)（ ） 。

Inserts _count_列到模型中，创建新项目，给定的儿童_parent_。新列前插入_column_规定。如果_parent_项目有没有孩子，单行创建包含列的所需数量。

返回True如果成功插入的列，否则返回False 。

**See also** [QAbstractItemModel.insertColumns](qabstractitemmodel.html#insertColumns)（ ） 。

```
bool QProxyModel.insertRows (self, int row, int count, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.insertRows](qabstractitemmodel.html#insertRows)（ ） 。

Inserts _count_行到模型中，创建新项目，给定的儿童_parent_。新行前插入_row_规定。如果_parent_项目有没有孩子，一列是创建包含的行规定的数量。

返回True如果成功插入的行，否则返回False 。

**See also** [QAbstractItemModel.insertRows](qabstractitemmodel.html#insertRows)（ ） 。

```
list-of-QModelIndex QProxyModel.match (self, QModelIndex start, int role, QVariant value, int hits = 1, Qt.MatchFlags flags = Qt.MatchFlags(Qt.MatchStartsWith|Qt.MatchWrap))
```

从重新实现[QAbstractItemModel.match](qabstractitemmodel.html#match)（ ） 。

返回每一个包含给定模型索引的列表_value_为_role_规定。搜索开始于_start_指数，并根据指定的执行_flags_。搜索继续进行，直到匹配的数据项的数目等于_hits_，最后一行为止，或者搜索到达_start_再次，这取决于是否`MatchWrap`在被指定_flags_。

**See also** [QAbstractItemModel.match](qabstractitemmodel.html#match)（ ） 。

```
QMimeData QProxyModel.mimeData (self, list-of-QModelIndex indexes)
```

[

该_QMimeData_结果

](qmimedata.html)

[从重新实现](qmimedata.html)[QAbstractItemModel.mimeData](qabstractitemmodel.html#mimeData)（ ） 。

返回MIME数据为指定的_indexes_在模型中。

```
QStringList QProxyModel.mimeTypes (self)
```

从重新实现[QAbstractItemModel.mimeTypes](qabstractitemmodel.html#mimeTypes)（ ） 。

返回由该模型支持的MIME类型的列表。

```
QAbstractItemModel QProxyModel.model (self)
```

[

返回包含可通过代理服务器模型的数据模型。

](qabstractitemmodel.html)

[**See also**](qabstractitemmodel.html) [setModel](qproxymodel.html#setModel)（ ） 。

```
QModelIndex QProxyModel.parent (self, QModelIndex child)
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemModel.parent](qabstractitemmodel.html#parent)（ ） 。

返回对应于给定的父模型索引_child_索引。

```
QObject QProxyModel.parent (self)
```

[

```
QProxyModel.revert (self)
```

](qobject.html)

[从重新实现](qobject.html)[QAbstractItemModel.revert](qabstractitemmodel.html#revert)（ ） 。

```
int QProxyModel.rowCount (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.rowCount](qabstractitemmodel.html#rowCount)（ ） 。

返回的行数为给定的_parent_。

**See also** [QAbstractItemModel.rowCount](qabstractitemmodel.html#rowCount)（ ） 。

```
bool QProxyModel.setData (self, QModelIndex index, QVariant value, int role = Qt.EditRole)
```

从重新实现[QAbstractItemModel.setData](qabstractitemmodel.html#setData)（ ） 。

设置_role_对于在项目数据_index_至_value_。成功返回True ，否则返回False 。

基类实现返回False 。此功能与[data](qproxymodel.html#data)（ ）必须被重新实现可编辑的模型。

**See also** [data](qproxymodel.html#data)（ ）[itemData](qabstractitemmodel.html#itemData)（）和[QAbstractItemModel.setData](qabstractitemmodel.html#setData)（ ） 。

```
bool QProxyModel.setHeaderData (self, int section, Qt.Orientation orientation, QVariant value, int role = Qt.EditRole)
```

从重新实现[QAbstractItemModel.setHeaderData](qabstractitemmodel.html#setHeaderData)（ ） 。

设置_role_在数据_section_用指定的标头_orientation_到_value_给出。

**See also** [headerData](qproxymodel.html#headerData)（）和[QAbstractItemModel.setHeaderData](qabstractitemmodel.html#setHeaderData)（ ） 。

```
QProxyModel.setModel (self, QAbstractItemModel model)
```

设置给定_model_到由所述代理模型进行处理。

**See also** [model](qproxymodel.html#model)（ ） 。

```
QProxyModel.sort (self, int column, Qt.SortOrder order = Qt.AscendingOrder)
```

从重新实现[QAbstractItemModel.sort](qabstractitemmodel.html#sort)（ ） 。

排序在指定的子项_column_根据所定义的排序顺序_order_。

**See also** [QAbstractItemModel.sort](qabstractitemmodel.html#sort)（ ） 。

```
QSize QProxyModel.span (self, QModelIndex index)
```

[](qsize.html)

[从重新实现](qsize.html)[QAbstractItemModel.span](qabstractitemmodel.html#span)（ ） 。

返回对应于所指定的项的大小_index_。

```
bool QProxyModel.submit (self)
```

从重新实现[QAbstractItemModel.submit](qabstractitemmodel.html#submit)（ ） 。

```
Qt.DropActions QProxyModel.supportedDropActions (self)
```

[](index.htm)

[从重新实现](index.htm)[QAbstractItemModel.supportedDropActions](qabstractitemmodel.html#supportedDropActions)（ ） 。

返回由该模型所支持的放置动作，这是中定义的个人行动相结合[Qt.DropActions](qt.html#DropAction-enum)。

由模型提供的放置动作的选择将影响该开始拖放操作的组件的行为。

**See also** [Drag and Drop](index.htm)。