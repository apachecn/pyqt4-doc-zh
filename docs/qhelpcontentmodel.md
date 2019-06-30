# QHelpContentModel Class Reference

## [[QtHelp](index.htm) module]

该QHelpContentModel类提供了一个模型，它提供内容的意见。[More...](#details)

继承[QAbstractItemModel](qabstractitemmodel.html)。

### Methods

*   `int columnCount (self, QModelIndex parent = QModelIndex())`
*   `QHelpContentItem contentItemAt (self, QModelIndex index)`
*   `createContents (self, QString customFilterName)`
*   `QVariant data (self, QModelIndex index, int role)`
*   `QModelIndex index (self, int row, int column, QModelIndex parent = QModelIndex())`
*   `bool isCreatingContents (self)`
*   `QModelIndex parent (self, QModelIndex index)`
*   `int rowCount (self, QModelIndex parent = QModelIndex())`

### Qt Signals

*   `void contentsCreated ()`
*   `void contentsCreationStarted ()`

* * *

## Detailed Description

该QHelpContentModel类提供了一个模型，它提供内容的意见。

* * *

## Method Documentation

```
int QHelpContentModel.columnCount (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.columnCount](qabstractitemmodel.html#columnCount)（ ） 。

根据返回给定列数_parent_。目前总是返回1 。

```
QHelpContentItem QHelpContentModel.contentItemAt (self, QModelIndex index)
```

[

返回在模型索引位置的说明内容项目_index_。

```
QHelpContentModel.createContents (self, QString customFilterName)
```

通过查询帮助系统指定的内容创建新的内容_customFilterName_。

```
QVariant QHelpContentModel.data (self, QModelIndex index, int role)
```

](qhelpcontentitem.html)

[从重新实现](qhelpcontentitem.html)[QAbstractItemModel.data](qabstractitemmodel.html#data)（ ） 。

返回下指定存储的数据_role_由所提及的项目_index_。

```
QModelIndex QHelpContentModel.index (self, int row, int column, QModelIndex parent = QModelIndex())
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemModel.index](qabstractitemmodel.html#index)（ ） 。

返回由给定指定的模型项的索引_row_，_column_和_parent_索引。

```
bool QHelpContentModel.isCreatingContents (self)
```

如果内容目前正在重建，否则为False ，则返回True 。

```
QModelIndex QHelpContentModel.parent (self, QModelIndex index)
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemModel.parent](qabstractitemmodel.html#parent)（ ） 。

返回模型项目的父与给定_index_或QModelIndex （ ） ，如果它没有父。

```
int QHelpContentModel.rowCount (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.rowCount](qabstractitemmodel.html#rowCount)（ ） 。

返回下给定的行数_parent_。

* * *

## Qt Signal Documentation

```
void contentsCreated ()
```

这是该信号的默认超载。

已创建的内容时，这个信号被发射。

```
void contentsCreationStarted ()
```

这是该信号的默认超载。

当创建的内容已经开始这个信号被发射。当前的内容是从这个点上，直到该信号无效[contentsCreated](qhelpcontentmodel.html#contentsCreated)（）被发射。

**See also** [isCreatingContents](qhelpcontentmodel.html#isCreatingContents)（ ） 。