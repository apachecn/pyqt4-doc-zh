# QAbstractTableModel Class Reference

## [[QtCore](index.htm) module]

该QAbstractTableModel类提供了可以被子类来创建表款的抽象模型。[More...](#details)

继承[QAbstractItemModel](qabstractitemmodel.html)。

通过继承[QSqlQueryModel](qsqlquerymodel.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `bool dropMimeData (self, QMimeData data, Qt.DropAction action, int row, int column, QModelIndex parent)`
*   `QModelIndex index (self, int row, int column, QModelIndex parent = QModelIndex())`

* * *

## Detailed Description

该QAbstractTableModel类提供了可以被子类来创建表款的抽象模型。

QAbstractTableModel为表示它们的数据作为二维件阵列模型的标准接口。它不能直接使用，但必须被继承。

由于该模型提供了一个更专门的接口比[QAbstractItemModel](qabstractitemmodel.html)，它不适合于用树视图的使用，虽然它可以被用于提供数据给一个[QListView](qlistview.html)。如果你需要表示项目的简单列表，只需要一个模型来包含数据的单个列，子类化[QAbstractListModel](qabstractlistmodel.html)可能更合适。

该[rowCount](qabstractitemmodel.html#rowCount)（）和[columnCount](qabstractitemmodel.html#columnCount)（ ）函数返回的表的尺寸。撷取对应到模型中的项目的模型索引，请使用[index](qabstracttablemodel.html#index)（ ），并提供唯一的行号和列号。

### Subclassing

当子类QAbstractTableModel ，必须实现[rowCount](qabstractitemmodel.html#rowCount)（ ）[columnCount](qabstractitemmodel.html#columnCount)（）和[data](qabstractitemmodel.html#data)（ ） 。的默认实现[index](qabstracttablemodel.html#index)（）和[parent](qabstractitemmodel.html#parent)（）函数是将QAbstractTableModel提供。表现良好的车型也将实施[headerData](qabstractitemmodel.html#headerData)（ ） 。

可编辑的模型需要实现[setData](qabstractitemmodel.html#setData)（ ） ，并实施[flags](qabstractitemmodel.html#flags)（ ）返回一个包含一个值[Qt.ItemIsEditable](qt.html#ItemFlag-enum)。

模型，提供接口来调整大小的数据结构可以提供的实现[insertRows](qabstractitemmodel.html#insertRows)（ ）[removeRows](qabstractitemmodel.html#removeRows)（ ）[insertColumns](qabstractitemmodel.html#insertColumns)（）和[removeColumns](qabstractitemmodel.html#removeColumns)（ ） 。当实现这些功能，它调用相应的功能很重要，这样所有连接的看法是知悉有任何变化：

*   An [insertRows](qabstractitemmodel.html#insertRows)() implementation must call [beginInsertRows](qabstractitemmodel.html#beginInsertRows)() _before_ inserting new rows into the data structure, and it must call [endInsertRows](qabstractitemmodel.html#endInsertRows)() _immediately afterwards_.
*   An [insertColumns](qabstractitemmodel.html#insertColumns)() implementation must call [beginInsertColumns](qabstractitemmodel.html#beginInsertColumns)() _before_ inserting new columns into the data structure, and it must call [endInsertColumns](qabstractitemmodel.html#endInsertColumns)() _immediately afterwards_.
*   A [removeRows](qabstractitemmodel.html#removeRows)() implementation must call [beginRemoveRows](qabstractitemmodel.html#beginRemoveRows)() _before_ the rows are removed from the data structure, and it must call [endRemoveRows](qabstractitemmodel.html#endRemoveRows)() _immediately afterwards_.
*   A [removeColumns](qabstractitemmodel.html#removeColumns)() implementation must call [beginRemoveColumns](qabstractitemmodel.html#beginRemoveColumns)() _before_ the columns are removed from the data structure, and it must call [endRemoveColumns](qabstractitemmodel.html#endRemoveColumns)() _immediately afterwards_.

**Note:**可在子类化模型的一些通用准则[Model Subclassing Reference](index.htm#model-subclassing-reference)。

**Note:**

* * *

## Method Documentation

```
QAbstractTableModel.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造为给定的抽象表模型_parent_。

```
bool QAbstractTableModel.dropMimeData (self, QMimeData data, Qt.DropAction action, int row, int column, QModelIndex parent)
```

从重新实现[QAbstractItemModel.dropMimeData](qabstractitemmodel.html#dropMimeData)（ ） 。

```
QModelIndex QAbstractTableModel.index (self, int row, int column, QModelIndex parent = QModelIndex())
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemModel.index](qabstractitemmodel.html#index)（ ） 。

返回的数据的索引_row_和_column_同_parent_。

**See also** [parent](qabstractitemmodel.html#parent)（ ） 。