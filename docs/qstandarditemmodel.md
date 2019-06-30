# QStandardItemModel Class Reference

## [[QtGui](index.htm) module]

该QStandardItemModel类提供用于存储自定义数据的通用模型。[More...](#details)

继承[QAbstractItemModel](qabstractitemmodel.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `__init__ (self, int rows, int columns, QObject parent = None)`
*   `appendColumn (self, list-of-QStandardItem items)`
*   `appendRow (self, list-of-QStandardItem items)`
*   `appendRow (self, QStandardItem aitem)`
*   `clear (self)`
*   `int columnCount (self, QModelIndex parent = QModelIndex())`
*   `QVariant data (self, QModelIndex index, int role = Qt.DisplayRole)`
*   `bool dropMimeData (self, QMimeData data, Qt.DropAction action, int row, int column, QModelIndex parent)`
*   `list-of-QStandardItem findItems (self, QString text, Qt.MatchFlags flags = Qt.MatchExactly, int column = 0)`
*   `Qt.ItemFlags flags (self, QModelIndex index)`
*   `bool hasChildren (self, QModelIndex parent = QModelIndex())`
*   `QVariant headerData (self, int section, Qt.Orientation orientation, int role = Qt.DisplayRole)`
*   `QStandardItem horizontalHeaderItem (self, int column)`
*   `QModelIndex index (self, int row, int column, QModelIndex parent = QModelIndex())`
*   `QModelIndex indexFromItem (self, QStandardItem item)`
*   `insertColumn (self, int column, list-of-QStandardItem items)`
*   `bool insertColumn (self, int column, QModelIndex parent = QModelIndex())`
*   `bool insertColumns (self, int column, int count, QModelIndex parent = QModelIndex())`
*   `insertRow (self, int row, list-of-QStandardItem items)`
*   `insertRow (self, int arow, QStandardItem aitem)`
*   `bool insertRow (self, int row, QModelIndex parent = QModelIndex())`
*   `bool insertRows (self, int row, int count, QModelIndex parent = QModelIndex())`
*   `QStandardItem invisibleRootItem (self)`
*   `QStandardItem item (self, int row, int column = 0)`
*   `dict-of-int-QVariant itemData (self, QModelIndex index)`
*   `QStandardItem itemFromIndex (self, QModelIndex index)`
*   `QStandardItem itemPrototype (self)`
*   `QMimeData mimeData (self, list-of-QModelIndex indexes)`
*   `QStringList mimeTypes (self)`
*   `QModelIndex parent (self, QModelIndex child)`
*   `QObject parent (self)`
*   `bool removeColumns (self, int column, int count, QModelIndex parent = QModelIndex())`
*   `bool removeRows (self, int row, int count, QModelIndex parent = QModelIndex())`
*   `int rowCount (self, QModelIndex parent = QModelIndex())`
*   `setColumnCount (self, int columns)`
*   `bool setData (self, QModelIndex index, QVariant value, int role = Qt.EditRole)`
*   `bool setHeaderData (self, int section, Qt.Orientation orientation, QVariant value, int role = Qt.EditRole)`
*   `setHorizontalHeaderItem (self, int column, QStandardItem item)`
*   `setHorizontalHeaderLabels (self, QStringList labels)`
*   `setItem (self, int row, int column, QStandardItem item)`
*   `setItem (self, int arow, QStandardItem aitem)`
*   `bool setItemData (self, QModelIndex index, dict-of-int-QVariant roles)`
*   `setItemPrototype (self, QStandardItem item)`
*   `setRowCount (self, int rows)`
*   `setSortRole (self, int role)`
*   `setVerticalHeaderItem (self, int row, QStandardItem item)`
*   `setVerticalHeaderLabels (self, QStringList labels)`
*   `sort (self, int column, Qt.SortOrder order = Qt.AscendingOrder)`
*   `int sortRole (self)`
*   `Qt.DropActions supportedDropActions (self)`
*   `list-of-QStandardItem takeColumn (self, int column)`
*   `QStandardItem takeHorizontalHeaderItem (self, int column)`
*   `QStandardItem takeItem (self, int row, int column = 0)`
*   `list-of-QStandardItem takeRow (self, int row)`
*   `QStandardItem takeVerticalHeaderItem (self, int row)`
*   `QStandardItem verticalHeaderItem (self, int row)`

### Qt Signals

*   `void itemChanged (QStandardItem *)`

* * *

## Detailed Description

该QStandardItemModel类提供用于存储自定义数据的通用模型。

QStandardItemModel可以作为标准的Qt数据类型的存储库。它是一[Model/View Classes](index.htm)并且是Qt的一部分[model/view](index.htm)框架。

QStandardItemModel提供了一个典型的项目为基础的方法与模型的工作。在QStandardItemModel的项目是由提供[QStandardItem](qstandarditem.html)。

QStandardItemModel实现[QAbstractItemModel](qabstractitemmodel.html)接口，这意味着，该模型可以用来提供数据支持该接口（如任何视图[QListView](qlistview.html)，[QTableView](qtableview.html)和[QTreeView](qtreeview.html)，和你自己的自定义视图） 。对于性能和灵活性，你可能要继承[QAbstractItemModel](qabstractitemmodel.html)提供不同类型的数据存储库的支持。例如，本[QDirModel(obsolete)](qdirmodel.html)提供了一个模型界面到底层的文件系统。

当你想要一个列表或树，你可以创建一个空的QStandardItemModel和使用[appendRow](qstandarditemmodel.html#appendRow)（ ）将项目添加到模型中，并[item](qstandarditemmodel.html#item)（）来存取项目。如果你的模型是一个表，通常需要传递的表的尺寸的QStandardItemModel的构造和使用[setItem](qstandarditemmodel.html#setItem)（ ）来定位的项目到表中。您也可以使用[setRowCount](qstandarditemmodel.html#setRowCount)（）和[setColumnCount](qstandarditemmodel.html#setColumnCount)（）来改变模型的尺寸。要插入的项目，使用[insertRow](qstandarditemmodel.html#insertRow)（）或[insertColumn](qstandarditemmodel.html#insertColumn)（ ） ，并删除项目，使用[removeRow](qabstractitemmodel.html#removeRow)（）或[removeColumn](qabstractitemmodel.html#removeColumn)（ ） 。

你可以设置你的模型的标题与标籤[setHorizontalHeaderLabels](qstandarditemmodel.html#setHorizontalHeaderLabels)（）和[setVerticalHeaderLabels](qstandarditemmodel.html#setVerticalHeaderLabels)（ ） 。

您可以在模型中的项目与搜索[findItems](qstandarditemmodel.html#findItems)（） ，并且模型通过调用排序[sort](qstandarditemmodel.html#sort)（ ） 。

Call [clear](qstandarditemmodel.html#clear)（）从模型中删除所有项目。

QStandardItemModel的使用示例创建一个表：

```
 QStandardItemModel model(4, 4);
 for (int row = 0; row < 4; ++row) {
     for (int column = 0; column < 4; ++column) {
         [QStandardItem](qstandarditem.html) *item = new [QStandardItem](qstandarditem.html)([QString](qstring.html)("row %0, column %1").arg(row).arg(column));
         model.setItem(row, column, item);
     }
 }

```

QStandardItemModel的使用示例创建树：

```
 QStandardItemModel model;
 [QStandardItem](qstandarditem.html) *parentItem = model.invisibleRootItem();
 for (int i = 0; i < 4; ++i) {
     [QStandardItem](qstandarditem.html) *item = new [QStandardItem](qstandarditem.html)([QString](qstring.html)("item %0").arg(i));
     parentItem->appendRow(item);
     parentItem = item;
 }

```

设置模型的视图后，你通常需要响应用户操作，如被点击的项目。由于[QAbstractItemView](qabstractitemview.html)提供[QModelIndex](qmodelindex.html)为基础的信号和功能，你需要一种方法来获得[QStandardItem](qstandarditem.html)对应于一个给定的[QModelIndex](qmodelindex.html)，反之亦然。[itemFromIndex](qstandarditemmodel.html#itemFromIndex)（）和[indexFromItem](qstandarditemmodel.html#indexFromItem)（ ）提供这种映射。典型的用法[itemFromIndex](qstandarditemmodel.html#itemFromIndex)（）包括：获取该项目的当前索引处的一个视图，并获得对应于由一个执行一个索引的资料[QAbstractItemView](qabstractitemview.html)信号，如[QAbstractItemView.clicked](qabstractitemview.html#clicked)（ ） 。首先，你的观点的信号连接到您的班级插槽：

```
 [QTreeView](qtreeview.html) *treeView = new [QTreeView](qtreeview.html)(this);
 treeView->setModel(myStandardItemModel);
 connect(treeView, SIGNAL(clicked([QModelIndex](qmodelindex.html))),
         this, SLOT(clicked([QModelIndex](qmodelindex.html))));

```

当您收到信号，你叫[itemFromIndex](qstandarditemmodel.html#itemFromIndex)（ ）在给定的模型索引来获得一个指向文件：

```
 void MyWidget.clicked(const [QModelIndex](qmodelindex.html) &index)
 {
     [QStandardItem](qstandarditem.html) *item = myStandardItemModel->itemFromIndex(index);
     // Do stuff with the item ...
 }

```

相反，你必须获得[QModelIndex](qmodelindex.html)当你要调用一个模型/视图函数，它接受一个索引作为参数的项目。您可以使用该模型的两种获取索引[indexFromItem](qstandarditemmodel.html#indexFromItem)（）函数，或等价地，通过调用[QStandardItem.index](qstandarditem.html#index)（）：

```
 treeView->scrollTo(item->index());

```

你当然不需要使用的项目为基础的方法，你可以代替完全依赖[QAbstractItemModel](qabstractitemmodel.html)接口与模型的工作，或者在两者的组合中适当的时候。

* * *

## Method Documentation

```
QStandardItemModel.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的项目模型，给定_parent_。

```
QStandardItemModel.__init__ (self, int rows, int columns, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的项目模型，最初有_rows_行和_columns_列，并且具有给定_parent_。

```
QStandardItemModel.appendColumn (self, list-of-QStandardItem items)
```

该_items_说法有它的所有权转移给Qt的。

含追加一列_items_。如果有必要，该行数将增加至大小_items_。

这个函数中引入了Qt 4.2中。

**See also** [insertColumn](qstandarditemmodel.html#insertColumn)（）和[appendRow](qstandarditemmodel.html#appendRow)（ ） 。

```
QStandardItemModel.appendRow (self, list-of-QStandardItem items)
```

该_items_说法有它的所有权转移给Qt的。

含追加的行_items_。如果需要的话，列计数值增加到的大小_items_。

这个函数中引入了Qt 4.2中。

**See also** [insertRow](qstandarditemmodel.html#insertRow)（）和[appendColumn](qstandarditemmodel.html#appendColumn)（ ） 。

```
QStandardItemModel.appendRow (self, QStandardItem aitem)
```

该_aitem_说法有它的所有权转移给Qt的。

这是一个重载函数。

当建立一个列表，或者只有一列树，该功能提供了一种方便的方式来追加一个新_item_。

这个函数中引入了Qt 4.2中。

```
QStandardItemModel.clear (self)
```

从模型中删除所有项目（包括头项） ，并设置行数和列数为零。

**See also** [removeColumns](qstandarditemmodel.html#removeColumns)（）和[removeRows](qstandarditemmodel.html#removeRows)（ ） 。

```
int QStandardItemModel.columnCount (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.columnCount](qabstractitemmodel.html#columnCount)（ ） 。

**See also** [setColumnCount](qstandarditemmodel.html#setColumnCount)（ ） 。

```
QVariant QStandardItemModel.data (self, QModelIndex index, int role = Qt.DisplayRole)
```

从重新实现[QAbstractItemModel.data](qabstractitemmodel.html#data)（ ） 。

**See also** [setData](qstandarditemmodel.html#setData)（ ） 。

```
bool QStandardItemModel.dropMimeData (self, QMimeData data, Qt.DropAction action, int row, int column, QModelIndex parent)
```

从重新实现[QAbstractItemModel.dropMimeData](qabstractitemmodel.html#dropMimeData)（ ） 。

```
list-of-QStandardItem QStandardItemModel.findItems (self, QString text, Qt.MatchFlags flags = Qt.MatchExactly, int column = 0)
```

返回匹配给定的项目清单_text_，使用给定的_flags_在给定的_column_。

这个函数中引入了Qt 4.2中。

```
Qt.ItemFlags QStandardItemModel.flags (self, QModelIndex index)
```

[](index.htm)

[从重新实现](index.htm)[QAbstractItemModel.flags](qabstractitemmodel.html#flags)（ ） 。

```
bool QStandardItemModel.hasChildren (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.hasChildren](qabstractitemmodel.html#hasChildren)（ ） 。

```
QVariant QStandardItemModel.headerData (self, int section, Qt.Orientation orientation, int role = Qt.DisplayRole)
```

从重新实现[QAbstractItemModel.headerData](qabstractitemmodel.html#headerData)（ ） 。

**See also** [setHeaderData](qstandarditemmodel.html#setHeaderData)（ ） 。

```
QStandardItem QStandardItemModel.horizontalHeaderItem (self, int column)
```

[

返回水平标题项为_column_如果已经设置，否则返回0 。

这个函数中引入了Qt 4.2中。

](qstandarditem.html)

[**See also**](qstandarditem.html) [setHorizontalHeaderItem](qstandarditemmodel.html#setHorizontalHeaderItem)（）和[verticalHeaderItem](qstandarditemmodel.html#verticalHeaderItem)（ ） 。

```
QModelIndex QStandardItemModel.index (self, int row, int column, QModelIndex parent = QModelIndex())
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemModel.index](qabstractitemmodel.html#index)（ ） 。

```
QModelIndex QStandardItemModel.indexFromItem (self, QStandardItem item)
```

[](qmodelindex.html)

[返回](qmodelindex.html)[QModelIndex](qmodelindex.html)用给定的相关联_item_。

当您要执行需要的操作使用此功能[QModelIndex](qmodelindex.html)该项目时，如[QAbstractItemView.scrollTo](qabstractitemview.html#scrollTo)（ ） 。[QStandardItem.index](qstandarditem.html#index)（ ）是作为方便，它等效于调用这个函数。

这个函数中引入了Qt 4.2中。

**See also** [itemFromIndex](qstandarditemmodel.html#itemFromIndex)（）和[QStandardItem.index](qstandarditem.html#index)（ ） 。

```
QStandardItemModel.insertColumn (self, int column, list-of-QStandardItem items)
```

该_items_说法有它的所有权转移给Qt的。

在插入一列_column_ containing _items_。如果有必要，该行数将增加至大小_items_。

这个函数中引入了Qt 4.2中。

**See also** [takeColumn](qstandarditemmodel.html#takeColumn)（ ）[appendColumn](qstandarditemmodel.html#appendColumn)（）和[insertRow](qstandarditemmodel.html#insertRow)（ ） 。

```
bool QStandardItemModel.insertColumn (self, int column, QModelIndex parent = QModelIndex())
```

给定前插入一列_column_中的子项_parent_规定。返回True如果插入的列，否则返回False 。

**See also** [insertColumns](qstandarditemmodel.html#insertColumns)（ ）[insertRow](qstandarditemmodel.html#insertRow)（）和[removeColumn](qabstractitemmodel.html#removeColumn)（ ） 。

```
bool QStandardItemModel.insertColumns (self, int column, int count, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.insertColumns](qabstractitemmodel.html#insertColumns)（ ） 。

```
QStandardItemModel.insertRow (self, int row, list-of-QStandardItem items)
```

该_items_说法有它的所有权转移给Qt的。

插入一个一行_row_ containing _items_。如果需要的话，列计数值增加到的大小_items_。

这个函数中引入了Qt 4.2中。

**See also** [takeRow](qstandarditemmodel.html#takeRow)（ ）[appendRow](qstandarditemmodel.html#appendRow)（）和[insertColumn](qstandarditemmodel.html#insertColumn)（ ） 。

```
QStandardItemModel.insertRow (self, int arow, QStandardItem aitem)
```

该_aitem_说法有它的所有权转移给Qt的。

给定前插入一个单行_row_中的子项_parent_规定。返回True如果被插入的行，否则返回False 。

**See also** [insertRows](qstandarditemmodel.html#insertRows)（ ）[insertColumn](qstandarditemmodel.html#insertColumn)（）和[removeRow](qabstractitemmodel.html#removeRow)（ ） 。

```
bool QStandardItemModel.insertRow (self, int row, QModelIndex parent = QModelIndex())
```

这是一个重载函数。

插入一个一行_row_ containing _item_。

当建立一个列表，或者只有一列树，该功能提供了一种方便的方式来追加新的单一项目。

这个函数中引入了Qt 4.2中。

```
bool QStandardItemModel.insertRows (self, int row, int count, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.insertRows](qabstractitemmodel.html#insertRows)（ ） 。

```
QStandardItem QStandardItemModel.invisibleRootItem (self)
```

[

返回模型的无形之根项目。

](qstandarditem.html)

[看不见的根项目，通过提供对模型的顶层项目](qstandarditem.html)[QStandardItem](qstandarditem.html)的API ，从而可以写，可以治疗以统一的方式顶级项目及其子女的功能，例如，涉及树模型递归函数。

**Note:**调用[index()](qabstractitemmodel.html#index)在[QStandardItem](qstandarditem.html)从这个功能检索的对象是无效的。

这个函数中引入了Qt 4.2中。

```
QStandardItem QStandardItemModel.item (self, int row, int column = 0)
```

[

返回的项目为给定的_row_和_column_如果已经设置，否则返回0 。

这个函数中引入了Qt 4.2中。

](qstandarditem.html)

[**See also**](qstandarditem.html) [setItem](qstandarditemmodel.html#setItem)（ ）[takeItem](qstandarditemmodel.html#takeItem)（）和[itemFromIndex](qstandarditemmodel.html#itemFromIndex)（ ） 。

```
dict-of-int-QVariant QStandardItemModel.itemData (self, QModelIndex index)
```

从重新实现[QAbstractItemModel.itemData](qabstractitemmodel.html#itemData)（ ） 。

**See also** [setItemData](qstandarditemmodel.html#setItemData)（ ） 。

```
QStandardItem QStandardItemModel.itemFromIndex (self, QModelIndex index)
```

[](qstandarditem.html)

[返回一个指针](qstandarditem.html)[QStandardItem](qstandarditem.html)用给定的相关联_index_。

调用此函数通常是最初的一步处理时，[QModelIndex](qmodelindex.html)从一个基于视图的信号，如[QAbstractItemView.activated](qabstractitemview.html#activated)（ ） 。在您的插槽，你叫itemFromIndex （ ） ，与[QModelIndex](qmodelindex.html)由信号作为参数进行，得到一个指向相应[QStandardItem](qstandarditem.html)。

注意，这个函数会懒洋洋地创建索引项（使用[itemPrototype](qstandarditemmodel.html#itemPrototype)（ ） ） ，并将其设置在父项的子表，如果没有项目已经存在该索引。

If _index_是一个无效的指标，这个函数返回0 。

这个函数中引入了Qt 4.2中。

**See also** [indexFromItem](qstandarditemmodel.html#indexFromItem)（ ） 。

```
QStandardItem QStandardItemModel.itemPrototype (self)
```

[](qstandarditem.html)

[返回产品原型所使用的模型。该模型使用的项目原型作为项目的工厂时，它需要构建随需应变的新项目（例如，当一个视图或项目委讬调用](qstandarditem.html)[setData](qstandarditemmodel.html#setData)（））。

这个函数中引入了Qt 4.2中。

**See also** [setItemPrototype](qstandarditemmodel.html#setItemPrototype)（ ） 。

```
QMimeData QStandardItemModel.mimeData (self, list-of-QModelIndex indexes)
```

[

该_QMimeData_结果

](qmimedata.html)

[从重新实现](qmimedata.html)[QAbstractItemModel.mimeData](qabstractitemmodel.html#mimeData)（ ） 。

```
QStringList QStandardItemModel.mimeTypes (self)
```

从重新实现[QAbstractItemModel.mimeTypes](qabstractitemmodel.html#mimeTypes)（ ） 。

```
QModelIndex QStandardItemModel.parent (self, QModelIndex child)
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemModel.parent](qabstractitemmodel.html#parent)（ ） 。

```
QObject QStandardItemModel.parent (self)
```

[

```
bool QStandardItemModel.removeColumns (self, int column, int count, QModelIndex parent = QModelIndex())
```

](qobject.html)

[从重新实现](qobject.html)[QAbstractItemModel.removeColumns](qabstractitemmodel.html#removeColumns)（ ） 。

```
bool QStandardItemModel.removeRows (self, int row, int count, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.removeRows](qabstractitemmodel.html#removeRows)（ ） 。

```
int QStandardItemModel.rowCount (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.rowCount](qabstractitemmodel.html#rowCount)（ ） 。

**See also** [setRowCount](qstandarditemmodel.html#setRowCount)（ ） 。

```
QStandardItemModel.setColumnCount (self, int columns)
```

载列在这个模型数_columns_。如果它小于[columnCount](qstandarditemmodel.html#columnCount)（） ，在不需要的列中的数据将被丢弃。

这个函数中引入了Qt 4.2中。

**See also** [columnCount](qstandarditemmodel.html#columnCount)（）和[setRowCount](qstandarditemmodel.html#setRowCount)（ ） 。

```
bool QStandardItemModel.setData (self, QModelIndex index, QVariant value, int role = Qt.EditRole)
```

从重新实现[QAbstractItemModel.setData](qabstractitemmodel.html#setData)（ ） 。

**See also** [data](qstandarditemmodel.html#data)（ ） 。

```
bool QStandardItemModel.setHeaderData (self, int section, Qt.Orientation orientation, QVariant value, int role = Qt.EditRole)
```

从重新实现[QAbstractItemModel.setHeaderData](qabstractitemmodel.html#setHeaderData)（ ） 。

**See also** [headerData](qstandarditemmodel.html#headerData)（ ） 。

```
QStandardItemModel.setHorizontalHeaderItem (self, int column, QStandardItem item)
```

该_item_说法有它的所有权转移给Qt的。

设置水平标题项为_column_至_item_。该模型考虑了项目的所有权。如果需要的话，列计数增加，以适应产品。以前的标题项（如果有的话）将被删除。

这个函数中引入了Qt 4.2中。

**See also** [horizontalHeaderItem](qstandarditemmodel.html#horizontalHeaderItem)（ ）[setHorizontalHeaderLabels](qstandarditemmodel.html#setHorizontalHeaderLabels)（）和[setVerticalHeaderItem](qstandarditemmodel.html#setVerticalHeaderItem)（ ） 。

```
QStandardItemModel.setHorizontalHeaderLabels (self, QStringList labels)
```

设置使用水平标题标籤_labels_。如果需要的话，列计数值增加到的大小_labels_。

这个函数中引入了Qt 4.2中。

**See also** [setHorizontalHeaderItem](qstandarditemmodel.html#setHorizontalHeaderItem)（ ） 。

```
QStandardItemModel.setItem (self, int row, int column, QStandardItem item)
```

该_item_说法有它的所有权转移给Qt的。

设置项对于给定的_row_和_column_至_item_。该模型考虑了项目的所有权。如果必要，行数和列数都增加，以适应产品。在给定位置（如果有的话）上一个项目被删除。

这个函数中引入了Qt 4.2中。

**See also** [item](qstandarditemmodel.html#item)（ ） 。

```
QStandardItemModel.setItem (self, int arow, QStandardItem aitem)
```

该_aitem_说法有它的所有权转移给Qt的。

这是一个重载函数。

```
bool QStandardItemModel.setItemData (self, QModelIndex index, dict-of-int-QVariant roles)
```

从重新实现[QAbstractItemModel.setItemData](qabstractitemmodel.html#setItemData)（ ） 。

**See also** [itemData](qstandarditemmodel.html#itemData)（ ） 。

```
QStandardItemModel.setItemPrototype (self, QStandardItem item)
```

该_item_说法有它的所有权转移给Qt的。

设置项的原型模型的指定的_item_。该模型采用原型的所有权。

该项目的原型作为一个[QStandardItem](qstandarditem.html)工厂，所依托的[QStandardItem.clone](qstandarditem.html#clone)（）函数。提供自己的原型，子类[QStandardItem](qstandarditem.html)，重新实现[QStandardItem.clone](qstandarditem.html#clone)（）和set原型是您的自定义类的实例。每当[QStandardItemModel](qstandarditemmodel.html)需要按需创建一个项目（例如，视图或项目委讬呼叫时[setData](qstandarditemmodel.html#setData)（ ） ） ） ，该新项目将是你的自定义类的实例。

这个函数中引入了Qt 4.2中。

**See also** [itemPrototype](qstandarditemmodel.html#itemPrototype)（）和[QStandardItem.clone](qstandarditem.html#clone)（ ） 。

```
QStandardItemModel.setRowCount (self, int rows)
```

设定排在这个模型数_rows_。如果它小于[rowCount](qstandarditemmodel.html#rowCount)（） ，在不需要的行中的数据将被丢弃。

这个函数中引入了Qt 4.2中。

**See also** [rowCount](qstandarditemmodel.html#rowCount)（）和[setColumnCount](qstandarditemmodel.html#setColumnCount)（ ） 。

```
QStandardItemModel.setSortRole (self, int role)
```

```
QStandardItemModel.setVerticalHeaderItem (self, int row, QStandardItem item)
```

该_item_说法有它的所有权转移给Qt的。

设置垂直标题项为_row_至_item_。该模型考虑了项目的所有权。如果必要，行计数增加，以适应产品。以前的标题项（如果有的话）将被删除。

这个函数中引入了Qt 4.2中。

**See also** [verticalHeaderItem](qstandarditemmodel.html#verticalHeaderItem)（ ）[setVerticalHeaderLabels](qstandarditemmodel.html#setVerticalHeaderLabels)（）和[setHorizontalHeaderItem](qstandarditemmodel.html#setHorizontalHeaderItem)（ ） 。

```
QStandardItemModel.setVerticalHeaderLabels (self, QStringList labels)
```

设置使用垂直标题标籤_labels_。如果有必要，该行数将增加至大小_labels_。

这个函数中引入了Qt 4.2中。

**See also** [setVerticalHeaderItem](qstandarditemmodel.html#setVerticalHeaderItem)（ ） 。

```
QStandardItemModel.sort (self, int column, Qt.SortOrder order = Qt.AscendingOrder)
```

从重新实现[QAbstractItemModel.sort](qabstractitemmodel.html#sort)（ ） 。

```
int QStandardItemModel.sortRole (self)
```

```
Qt.DropActions QStandardItemModel.supportedDropActions (self)
```

[](index.htm)

[从重新实现](index.htm)[QAbstractItemModel.supportedDropActions](qabstractitemmodel.html#supportedDropActions)（ ） 。

[QStandardItemModel](qstandarditemmodel.html)支持复制和移动两种。

```
list-of-QStandardItem QStandardItemModel.takeColumn (self, int column)
```

该_list-of-QStandardItem_结果

删除给定的_column_不删除的列项，并返回指针列表的删除的项。该模型释放的物品的所有权。在尚未设定的列项，列表中的相应指针将是0 。

这个函数中引入了Qt 4.2中。

**See also** [takeRow](qstandarditemmodel.html#takeRow)（ ） 。

```
QStandardItem QStandardItemModel.takeHorizontalHeaderItem (self, int column)
```

[

该_QStandardItem_结果

删除在水平标题项_column_从标题而不删除它，并返回一个指向的项目。该模型发布该项目的所有权。

这个函数中引入了Qt 4.2中。

](qstandarditem.html)

[**See also**](qstandarditem.html) [horizontalHeaderItem](qstandarditemmodel.html#horizontalHeaderItem)（）和[takeVerticalHeaderItem](qstandarditemmodel.html#takeVerticalHeaderItem)（ ） 。

```
QStandardItem QStandardItemModel.takeItem (self, int row, int column = 0)
```

[

该_QStandardItem_结果

删除的项目（_row_，_column_）而不删除它。该模型发布该项目的所有权。

这个函数中引入了Qt 4.2中。

](qstandarditem.html)

[**See also**](qstandarditem.html) [item](qstandarditemmodel.html#item)（ ）[takeRow](qstandarditemmodel.html#takeRow)（）和[takeColumn](qstandarditemmodel.html#takeColumn)（ ） 。

```
list-of-QStandardItem QStandardItemModel.takeRow (self, int row)
```

该_list-of-QStandardItem_结果

删除给定的_row_不删除的行项目，并返回指针列表的删除的项目。该模型释放的物品的所有权。对于没有被设置的行中的项目，列表中的相应指针将是0 。

这个函数中引入了Qt 4.2中。

**See also** [takeColumn](qstandarditemmodel.html#takeColumn)（ ） 。

```
QStandardItem QStandardItemModel.takeVerticalHeaderItem (self, int row)
```

[

该_QStandardItem_结果

删除在垂直标题项_row_从标题而不删除它，并返回一个指向的项目。该模型发布该项目的所有权。

这个函数中引入了Qt 4.2中。

](qstandarditem.html)

[**See also**](qstandarditem.html) [verticalHeaderItem](qstandarditemmodel.html#verticalHeaderItem)（）和[takeHorizontalHeaderItem](qstandarditemmodel.html#takeHorizontalHeaderItem)（ ） 。

```
QStandardItem QStandardItemModel.verticalHeaderItem (self, int row)
```

[

返回行的垂直标题项_row_如果已经设置，否则返回0 。

这个函数中引入了Qt 4.2中。

](qstandarditem.html)

[**See also**](qstandarditem.html) [setVerticalHeaderItem](qstandarditemmodel.html#setVerticalHeaderItem)（）和[horizontalHeaderItem](qstandarditemmodel.html#horizontalHeaderItem)（ ） 。

* * *

## Qt Signal Documentation

```
void itemChanged (QStandardItem *)
```

这是该信号的默认超载。

这个信号被发射时的数据_item_已经改变。

这个函数中引入了Qt 4.2中。