# QStringListModel Class Reference

## [[QtGui](index.htm) module]

该QStringListModel类提供了一个模型，它提供字符串的看法。[More...](#details)

继承[QAbstractListModel](qabstractlistmodel.html)。

通过继承[QHelpIndexModel](qhelpindexmodel.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `__init__ (self, QStringList strings, QObject parent = None)`
*   `QVariant data (self, QModelIndex index, int role)`
*   `Qt.ItemFlags flags (self, QModelIndex index)`
*   `bool insertRows (self, int row, int count, QModelIndex parent = QModelIndex())`
*   `bool removeRows (self, int row, int count, QModelIndex parent = QModelIndex())`
*   `int rowCount (self, QModelIndex parent = QModelIndex())`
*   `bool setData (self, QModelIndex index, QVariant value, int role = Qt.EditRole)`
*   `setStringList (self, QStringList strings)`
*   `sort (self, int column, Qt.SortOrder order = Qt.AscendingOrder)`
*   `QStringList stringList (self)`
*   `Qt.DropActions supportedDropActions (self)`

* * *

## Detailed Description

该QStringListModel类提供了一个模型，它提供字符串的看法。

QStringListModel是可用于在您需要显示的字符串有多个视图中的小部件，如一个简单的情况下可编辑模式[QListView](qlistview.html)或[QComboBox](qcombobox.html)。

该模型提供了一个可编辑的模型中所有的标准功能，即在字符串列表与一个列和一个行数等于项目的列表中的号码的一个模型中的数据。

对应的项目模型索引以获得[index()](qabstractlistmodel.html#index)功能和项目标志与获得[flags](qstringlistmodel.html#flags)（ ） 。项目数据的读取使用[data](qstringlistmodel.html#data)（）函数和写入[setData](qstringlistmodel.html#setData)（ ） 。行（并在字符串列表项目数）的数量可以与被发现[rowCount](qstringlistmodel.html#rowCount)（）函数。

该模型可以与现有的字符串列表来构建或字符串可以在以后的设置[setStringList](qstringlistmodel.html#setStringList)（ ）的便利功能。串，也可以与通常的方式插入[insertRows](qstringlistmodel.html#insertRows)（）函数，并用除去[removeRows](qstringlistmodel.html#removeRows)（ ） 。字符串列表的内容可以检索与[stringList](qstringlistmodel.html#stringList)（ ）的便利功能。

QStringListModel的使用示例：

```
     QStringListModel *model = new QStringListModel();
     [QStringList](qstringlist.html) list;
     list << "a" << "b" << "c";
     model->setStringList(list);

```

* * *

## Method Documentation

```
QStringListModel.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个字符串列表模型与给定_parent_。

```
QStringListModel.__init__ (self, QStringList strings, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构建了含有指定的字符串列表模型_strings_用给定的_parent_。

```
QVariant QStringListModel.data (self, QModelIndex index, int role)
```

从重新实现[QAbstractItemModel.data](qabstractitemmodel.html#data)（ ） 。

返回数据为指定的_role_从与给定的产品_index_。

如果视图请求一个无效索引，则返回一个无效的变体。

**See also** [setData](qstringlistmodel.html#setData)（ ） 。

```
Qt.ItemFlags QStringListModel.flags (self, QModelIndex index)
```

[](index.htm)

[从重新实现](index.htm)[QAbstractItemModel.flags](qabstractitemmodel.html#flags)（ ） 。

返回该标志的产品与给定的_index_。

有效的项目被启用，可选择，可编辑，拖放启用，启用的下降。

**See also** [QAbstractItemModel.flags](qabstractitemmodel.html#flags)（ ） 。

```
bool QStringListModel.insertRows (self, int row, int count, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.insertRows](qabstractitemmodel.html#insertRows)（ ） 。

Inserts _count_行到模型中，开始在给定的_row_。

该_parent_行的索引是可选的，并且仅用于一致性[QAbstractItemModel](qabstractitemmodel.html)。默认情况下，一个空索引指定，表明行插入到模型的顶层。

**See also** [QAbstractItemModel.insertRows](qabstractitemmodel.html#insertRows)（ ） 。

```
bool QStringListModel.removeRows (self, int row, int count, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.removeRows](qabstractitemmodel.html#removeRows)（ ） 。

移除_count_从模型的行，开始在给定的_row_。

该_parent_行的索引是可选的，并且仅用于一致性[QAbstractItemModel](qabstractitemmodel.html)。默认情况下，空的索引被指定，指示行中的模型的顶层被除去。

**See also** [QAbstractItemModel.removeRows](qabstractitemmodel.html#removeRows)（ ） 。

```
int QStringListModel.rowCount (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.rowCount](qabstractitemmodel.html#rowCount)（ ） 。

返回行的模型数。此值对应于项目中的模型的内部字符串列表的数目。

可选的_parent_理由是，在大多数模型用来指定要计算的行的父。因为这是指定了有效的父清单时，结果将始终为0 。

**See also** [insertRows](qstringlistmodel.html#insertRows)（ ）[removeRows](qstringlistmodel.html#removeRows)（）和[QAbstractItemModel.rowCount](qabstractitemmodel.html#rowCount)（ ） 。

```
bool QStringListModel.setData (self, QModelIndex index, QVariant value, int role = Qt.EditRole)
```

从重新实现[QAbstractItemModel.setData](qabstractitemmodel.html#setData)（ ） 。

设置数据指定的_role_在与给定的产品_index_在该模型中，所提供的_value_。

该[dataChanged](qabstractitemmodel.html#dataChanged)如果该项目发生更改（ ）信号被发射。

**See also** [Qt.ItemDataRole](qt.html#ItemDataRole-enum)和[data](qstringlistmodel.html#data)（ ） 。

```
QStringListModel.setStringList (self, QStringList strings)
```

设置模型的内部字符串列表_strings_。该模型将通知所有已连接的视图，其基础数据已更改。

**See also** [stringList](qstringlistmodel.html#stringList)（）和[dataChanged](qabstractitemmodel.html#dataChanged)（ ） 。

```
QStringListModel.sort (self, int column, Qt.SortOrder order = Qt.AscendingOrder)
```

从重新实现[QAbstractItemModel.sort](qabstractitemmodel.html#sort)（ ） 。

```
QStringList QStringListModel.stringList (self)
```

返回所使用的模型来存储数据的字符串列表。

**See also** [setStringList](qstringlistmodel.html#setStringList)（ ） 。

```
Qt.DropActions QStringListModel.supportedDropActions (self)
```

[](index.htm)

[从重新实现](index.htm)[QAbstractItemModel.supportedDropActions](qabstractitemmodel.html#supportedDropActions)（ ） 。