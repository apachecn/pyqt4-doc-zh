# QAbstractListModel Class Reference

## [[QtCore](index.htm) module]

该QAbstractListModel类提供了可以被子类来创建一维列表模型的抽象模型。[More...](#details)

继承[QAbstractItemModel](qabstractitemmodel.html)。

通过继承[AudioOutputDeviceModel](index.htm)，[EffectDescriptionModel](index.htm)和[QStringListModel](qstringlistmodel.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `bool dropMimeData (self, QMimeData data, Qt.DropAction action, int row, int column, QModelIndex parent)`
*   `QModelIndex index (self, int row, int column = 0, QModelIndex parent = QModelIndex())`

* * *

## Detailed Description

该QAbstractListModel类提供了可以被子类来创建一维列表模型的抽象模型。

QAbstractListModel为代表的数据项的一个简单的非分层序列模型的标准接口。它不能直接使用，但必须被继承。

由于该模型提供了一个更专门的接口比[QAbstractItemModel](qabstractitemmodel.html)，它是不适合与树视图的使用，你将需要继承[QAbstractItemModel](qabstractitemmodel.html)如果你想提供一个模型用于这一目的。如果你需要使用一个号码列表模式来管理数据，它可能是比较合适的子类[QAbstractTableModel](qabstracttablemodel.html)类代替。

简单的模型可以通过继承这个类并实现所需功能的最小数目来创建。例如，我们可以实现一个简单的只读[QStringList](qstringlist.html)为基础的模型，它提供的字符串到列表[QListView](qlistview.html)小工具。在这种情况下，我们只需要实现[rowCount](qabstractitemmodel.html#rowCount)（）函数返回的项目的列表中的号码，并[data](qabstractitemmodel.html#data)（ ）函数来从列表中检索项目。

因为该模型代表一个一维结构，该[rowCount](qabstractitemmodel.html#rowCount)（）函数返回的项目中的模型的总数。该[columnCount](qabstractitemmodel.html#columnCount)（ ）函数用于实现互操作性与各种意见，但默认情况下，通知的意见，该模型只包含一列。

### Subclassing

当子类QAbstractListModel ，您必须提供的实现[rowCount](qabstractitemmodel.html#rowCount)（）和[data](qabstractitemmodel.html#data)（）函数。表现良好的机型还提供了[headerData](qabstractitemmodel.html#headerData)（）实现。

对于可编辑列表的机型，您还必须提供的一个实现[setData](qabstractitemmodel.html#setData)（ ） ，实施[flags](qabstractitemmodel.html#flags)（ ）函数，以便它返回一个包含一个值[Qt.ItemIsEditable](qt.html#ItemFlag-enum)。

需要注意的是QAbstractListModel提供的默认实现[columnCount](qabstractitemmodel.html#columnCount)（ ） ，通知的意见，有项目在这个模型只有一个列。

模型，提供接口来调整大小与列表类似的数据结构可以提供的实现[insertRows](qabstractitemmodel.html#insertRows)（）和[removeRows](qabstractitemmodel.html#removeRows)（ ） 。当实现这些功能，它调用相应的功能很重要，这样所有连接的看法是知悉有任何变化：

*   An [insertRows](qabstractitemmodel.html#insertRows)() implementation must call [beginInsertRows](qabstractitemmodel.html#beginInsertRows)() _before_ inserting new rows into the data structure, and it must call [endInsertRows](qabstractitemmodel.html#endInsertRows)() _immediately afterwards_.
*   A [removeRows](qabstractitemmodel.html#removeRows)() implementation must call [beginRemoveRows](qabstractitemmodel.html#beginRemoveRows)() _before_ the rows are removed from the data structure, and it must call [endRemoveRows](qabstractitemmodel.html#endRemoveRows)() _immediately afterwards_.

**Note:**可在子类化模型的一些通用准则[Model Subclassing Reference](index.htm#model-subclassing-reference)。

* * *

## Method Documentation

```
QAbstractListModel.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个抽象的列表模式与给定_parent_。

```
bool QAbstractListModel.dropMimeData (self, QMimeData data, Qt.DropAction action, int row, int column, QModelIndex parent)
```

从重新实现[QAbstractItemModel.dropMimeData](qabstractitemmodel.html#dropMimeData)（ ） 。

```
QModelIndex QAbstractListModel.index (self, int row, int column = 0, QModelIndex parent = QModelIndex())
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemModel.index](qabstractitemmodel.html#index)（ ） 。

返回的数据的索引_row_和_column_同_parent_。

**See also** [parent](qabstractitemmodel.html#parent)（ ） 。