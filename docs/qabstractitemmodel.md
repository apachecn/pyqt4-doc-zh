# QAbstractItemModel Class Reference

## [[QtCore](index.htm) module]

该化QAbstractItemModel类提供抽象接口项目模型类。[More...](#details)

继承[QObject](qobject.html)。

通过继承[QAbstractListModel](qabstractlistmodel.html)，[QAbstractProxyModel](qabstractproxymodel.html)，[QAbstractTableModel](qabstracttablemodel.html)，[QDirModel](qdirmodel.html)，[QFileSystemModel](qfilesystemmodel.html)，[QHelpContentModel](qhelpcontentmodel.html)，[QProxyModel](qproxymodel.html)和[QStandardItemModel](qstandarditemmodel.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `beginInsertColumns (self, QModelIndex parent, int first, int last)`
*   `beginInsertRows (self, QModelIndex parent, int first, int last)`
*   `bool beginMoveColumns (self, QModelIndex sourceParent, int sourceFirst, int sourceLast, QModelIndex destinationParent, int destinationColumn)`
*   `bool beginMoveRows (self, QModelIndex sourceParent, int sourceFirst, int sourceLast, QModelIndex destinationParent, int destinationRow)`
*   `beginRemoveColumns (self, QModelIndex parent, int first, int last)`
*   `beginRemoveRows (self, QModelIndex parent, int first, int last)`
*   `beginResetModel (self)`
*   `QModelIndex buddy (self, QModelIndex index)`
*   `bool canFetchMore (self, QModelIndex parent)`
*   `changePersistentIndex (self, QModelIndex from, QModelIndex to)`
*   `changePersistentIndexList (self, list-of-QModelIndex from, list-of-QModelIndex to)`
*   `int columnCount (self, QModelIndex parent = QModelIndex())`
*   `QModelIndex createIndex (self, int row, int column, object object = 0)`
*   `QVariant data (self, QModelIndex index, int role = Qt.DisplayRole)`
*   `bool decodeData (self, int row, int column, QModelIndex parent, QDataStream stream)`
*   `bool dropMimeData (self, QMimeData data, Qt.DropAction action, int row, int column, QModelIndex parent)`
*   `encodeData (self, list-of-QModelIndex indexes, QDataStream stream)`
*   `endInsertColumns (self)`
*   `endInsertRows (self)`
*   `endMoveColumns (self)`
*   `endMoveRows (self)`
*   `endRemoveColumns (self)`
*   `endRemoveRows (self)`
*   `endResetModel (self)`
*   `fetchMore (self, QModelIndex parent)`
*   `Qt.ItemFlags flags (self, QModelIndex index)`
*   `bool hasChildren (self, QModelIndex parent = QModelIndex())`
*   `bool hasIndex (self, int row, int column, QModelIndex parent = QModelIndex())`
*   `QVariant headerData (self, int section, Qt.Orientation orientation, int role = Qt.DisplayRole)`
*   `QModelIndex index (self, int row, int column, QModelIndex parent = QModelIndex())`
*   `bool insertColumn (self, int column, QModelIndex parent = QModelIndex())`
*   `bool insertColumns (self, int column, int count, QModelIndex parent = QModelIndex())`
*   `bool insertRow (self, int row, QModelIndex parent = QModelIndex())`
*   `bool insertRows (self, int row, int count, QModelIndex parent = QModelIndex())`
*   `dict-of-int-QVariant itemData (self, QModelIndex index)`
*   `list-of-QModelIndex match (self, QModelIndex start, int role, QVariant value, int hits = 1, Qt.MatchFlags flags = Qt.MatchStartsWith|Qt.MatchWrap)`
*   `QMimeData mimeData (self, list-of-QModelIndex indexes)`
*   `QStringList mimeTypes (self)`
*   `QModelIndex parent (self, QModelIndex child)`
*   `QObject parent (self)`
*   `list-of-QModelIndex persistentIndexList (self)`
*   `bool removeColumn (self, int column, QModelIndex parent = QModelIndex())`
*   `bool removeColumns (self, int column, int count, QModelIndex parent = QModelIndex())`
*   `bool removeRow (self, int row, QModelIndex parent = QModelIndex())`
*   `bool removeRows (self, int row, int count, QModelIndex parent = QModelIndex())`
*   `reset (self)`
*   `resetInternalData (self)`
*   `revert (self)`
*   `dict-of-int-QByteArray roleNames (self)`
*   `int rowCount (self, QModelIndex parent = QModelIndex())`
*   `bool setData (self, QModelIndex index, QVariant value, int role = Qt.EditRole)`
*   `bool setHeaderData (self, int section, Qt.Orientation orientation, QVariant value, int role = Qt.EditRole)`
*   `bool setItemData (self, QModelIndex index, dict-of-int-QVariant roles)`
*   `setRoleNames (self, dict-of-int-QByteArray roleNames)`
*   `setSupportedDragActions (self, Qt.DropActions)`
*   `QModelIndex sibling (self, int row, int column, QModelIndex idx)`
*   `sort (self, int column, Qt.SortOrder order = Qt.AscendingOrder)`
*   `QSize span (self, QModelIndex index)`
*   `bool submit (self)`
*   `Qt.DropActions supportedDragActions (self)`
*   `Qt.DropActions supportedDropActions (self)`

### Qt Signals

*   `void columnsAboutToBeInserted (const QModelIndex&,int,int)`
*   `void columnsAboutToBeMoved (const QModelIndex&,int,int,const QModelIndex&,int)`
*   `void columnsAboutToBeRemoved (const QModelIndex&,int,int)`
*   `void columnsInserted (const QModelIndex&,int,int)`
*   `void columnsMoved (const QModelIndex&,int,int,const QModelIndex&,int)`
*   `void columnsRemoved (const QModelIndex&,int,int)`
*   `void dataChanged (const QModelIndex&,const QModelIndex&)`
*   `void headerDataChanged (Qt::Orientation,int,int)`
*   `void layoutAboutToBeChanged ()`
*   `void layoutChanged ()`
*   `void modelAboutToBeReset ()`
*   `void modelReset ()`
*   `void rowsAboutToBeInserted (const QModelIndex&,int,int)`
*   `void rowsAboutToBeMoved (const QModelIndex&,int,int,const QModelIndex&,int)`
*   `void rowsAboutToBeRemoved (const QModelIndex&,int,int)`
*   `void rowsInserted (const QModelIndex&,int,int)`
*   `void rowsMoved (const QModelIndex&,int,int,const QModelIndex&,int)`
*   `void rowsRemoved (const QModelIndex&,int,int)`

* * *

## Detailed Description

该化QAbstractItemModel类提供抽象接口项目模型类。

在化QAbstractItemModel类定义了项目模型必须使用能够与互操作在模型/视图结构的其他组件的标准接口。它不应该被直接实例化。相反，你应该继承它来创建新的模型。

该化QAbstractItemModel类是一个[Model/View Classes](index.htm)并且是Qt的一部分[model/view framework](index.htm)。

如果你需要一个模型与使用[QListView](qlistview.html)或[QTableView](qtableview.html)，你应该考虑创建子类[QAbstractListModel](qabstractlistmodel.html) or [QAbstractTableModel](qabstracttablemodel.html)而不是这个类。

底层数据模型暴露的意见和代表作为表的层次结构。如果你不利用层次结构的，那么该模型是行和列的一个简单的表。每个项目都有一个指定的唯一索引[QModelIndex](qmodelindex.html)。

![](../img/modelindex-no-parent.png)

数据的每一个项目，可以通过一个模型来访问具有相关联的模型索引。您可以使用获得此模型的指数[index](qabstractitemmodel.html#index)（）函数。每个索引可以具有[sibling](qabstractitemmodel.html#sibling)（ ）指数;子项有[parent](qabstractitemmodel.html#parent)（ ）指数。

每一个项目都有一个数字与它相关的数据元素，它们可以通过指定一个角色进行检索（见[Qt.ItemDataRole](qt.html#ItemDataRole-enum)）到模型的[data](qabstractitemmodel.html#data)（）函数。可用于所有角色数据可以在同一时间使用获得的[itemData](qabstractitemmodel.html#itemData)（）函数。

每个角色数据是使用一个特定的设置[Qt.ItemDataRole](qt.html#ItemDataRole-enum)。对于个人角色数据被单独设置[setData](qabstractitemmodel.html#setData)（ ） ，或者它们可以为所有角色设定[setItemData](qabstractitemmodel.html#setItemData)（ ） 。

项目可以与查询[flags](qabstractitemmodel.html#flags)（ ） （见[Qt.ItemFlag](qt.html#ItemFlag-enum)） ，看看他们是否可以选择，拖动，或者以其它方式处理。

如果项目具有子对象，[hasChildren](qabstractitemmodel.html#hasChildren)（ ）为相应的索引返回True 。

该模型具有[rowCount](qabstractitemmodel.html#rowCount)（）和一个[columnCount](qabstractitemmodel.html#columnCount)（）的层次结构的各个层次。行和列可以被插入和移除[insertRows](qabstractitemmodel.html#insertRows)（ ）[insertColumns](qabstractitemmodel.html#insertColumns)（ ）[removeRows](qabstractitemmodel.html#removeRows)（）和[removeColumns](qabstractitemmodel.html#removeColumns)（ ） 。

该模型发出的信号来表示变化。例如，[dataChanged](qabstractitemmodel.html#dataChanged)（ ）被发射时由模型提供的数据项被改变。改变由模型事业提供的头文件[headerDataChanged](qabstractitemmodel.html#headerDataChanged)（）被发射。如果基础数据的变化的结构中，该模型可发射[layoutChanged](qabstractitemmodel.html#layoutChanged)（ ）来表示任何附加意见，他们应该重新显示出任何物品，采取新的结构考虑。

可通过模型中的项目可以使用来搜索特定的数据[match](qabstractitemmodel.html#match)（）函数。

对模型进行排序，可以使用[sort](qabstractitemmodel.html#sort)（ ） 。

### Subclassing

**Note:**可在子类化模型的一些通用准则[Model Subclassing Reference](index.htm#model-subclassing-reference)。

当子类化QAbstractItemModel ，最起码必须实现[index](qabstractitemmodel.html#index)（ ）[parent](qabstractitemmodel.html#parent)（ ）[rowCount](qabstractitemmodel.html#rowCount)（ ）[columnCount](qabstractitemmodel.html#columnCount)（）和[data](qabstractitemmodel.html#data)（ ） 。这些功能全部采用只读模式，并形成可编辑模型的基础。

您也可以重新实现[hasChildren](qabstractitemmodel.html#hasChildren)（ ）提供模型的特殊行为，其中实施[rowCount](qabstractitemmodel.html#rowCount)（）是昂贵的。这使得可以为模型，以限制由视图请求的数据量，并且可以作为一种方法来实现的模型数据的懒惰人口。

为了使编辑在模型中，你还必须实现[setData](qabstractitemmodel.html#setData)（ ） ，并重新实现[flags](qabstractitemmodel.html#flags)（） ，以确保`ItemIsEditable`返回。您也可以重新实现[headerData](qabstractitemmodel.html#headerData)（）和[setHeaderData](qabstractitemmodel.html#setHeaderData)（ ）来控制标题为您的模型呈现的方式。

该[dataChanged](qabstractitemmodel.html#dataChanged)（）和[headerDataChanged](qabstractitemmodel.html#headerDataChanged)（ ）信号必须明确地重新实现时所发出的[setData](qabstractitemmodel.html#setData)（）和[setHeaderData](qabstractitemmodel.html#setHeaderData)（ ）函数，分别为。

定制机型需要建立索引模型为其他组件使用。要做到这一点，请致电[createIndex](qabstractitemmodel.html#createIndex)（ ）与合适的行号和列号的项目，和一个标识符它，无论是作为一个指针或作为一个整数值。这些值的组合必须是唯一的每个项目。定制机型通常使用于其他函数重新实现这些唯一标识符来检索项目数据和访问有关该项目的家长和孩子的信息。请参阅[Simple Tree Model Example](index.htm)关于唯一标识符的详细信息。

这是没有必要的，以支持在每个定义的角色[Qt.ItemDataRole](qt.html#ItemDataRole-enum)。根据包含在一个模型内的数据的类型，它可能只实施是有用的[data](qabstractitemmodel.html#data)（）函数返回有效信息的一些更常见的角色。大多数模型提供数据项的用于所述至少一个文本表示[Qt.DisplayRole](qt.html#ItemDataRole-enum)，乖巧的车型也应该提供有效的信息为[Qt.ToolTipRole](qt.html#ItemDataRole-enum)和[Qt.WhatsThisRole](qt.html#ItemDataRole-enum)。支持这些角色使模型能与Qt的标准视图中使用。然而，对于某些型号的处理高度专业化的数据，也可能是适当的，以提供数据仅用于用户定义的角色。

模型，提供接口来调整大小的数据结构可以提供的实现[insertRows](qabstractitemmodel.html#insertRows)（ ）[removeRows](qabstractitemmodel.html#removeRows)（ ）[insertColumns](qabstractitemmodel.html#insertColumns)（）和[removeColumns](qabstractitemmodel.html#removeColumns)（ ） 。当实现这些功能，它通知有关更改模型的尺寸连接任何意见都是很重要_before_和_after_发生：

*   An [insertRows](qabstractitemmodel.html#insertRows)() implementation must call [beginInsertRows](qabstractitemmodel.html#beginInsertRows)() _before_ inserting new rows into the data structure, and [endInsertRows](qabstractitemmodel.html#endInsertRows)() _immediately afterwards_.
*   An [insertColumns](qabstractitemmodel.html#insertColumns)() implementation must call [beginInsertColumns](qabstractitemmodel.html#beginInsertColumns)() _before_ inserting new columns into the data structure, and [endInsertColumns](qabstractitemmodel.html#endInsertColumns)() _immediately afterwards_.
*   A [removeRows](qabstractitemmodel.html#removeRows)() implementation must call [beginRemoveRows](qabstractitemmodel.html#beginRemoveRows)() _before_ the rows are removed from the data structure, and [endRemoveRows](qabstractitemmodel.html#endRemoveRows)() _immediately afterwards_.
*   A [removeColumns](qabstractitemmodel.html#removeColumns)() implementation must call [beginRemoveColumns](qabstractitemmodel.html#beginRemoveColumns)() _before_ the columns are removed from the data structure, and [endRemoveColumns](qabstractitemmodel.html#endRemoveColumns)() _immediately afterwards_.

该_private_这些函数发出给连接组件的机会之前，任何数据采取行动的信号变得不可用。所述插入件的封装和除去这些操作的开始和结束的功能还可以使模型的管理[persistent model indexes](qpersistentmodelindex.html)正确。**If you want selections to be handled properly, you must ensure that you call these functions.**如果你插入或删除一个项目有孩子，你不需要调用这些函数的子项。换句话说，父项将其子项的照顾。

要创建填充增量模型，你可以重新实现[fetchMore](qabstractitemmodel.html#fetchMore)（）和[canFetchMore](qabstractitemmodel.html#canFetchMore)（ ） 。如果重新实现[fetchMore](qabstractitemmodel.html#fetchMore)（ ）添加行的模式，[beginInsertRows()](qabstractitemmodel.html#beginInsertRows)和[endInsertRows()](qabstractitemmodel.html#endInsertRows)必须被调用。

* * *

## Method Documentation

```
QAbstractItemModel.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个抽象的概念模型与给定_parent_。

```
QAbstractItemModel.beginInsertColumns (self, QModelIndex parent, int first, int last)
```

开始一个列的插入操作。

当重新实现[insertColumns](qabstractitemmodel.html#insertColumns)（ ）的一个子类，则必须调用此函数_before_将数据插入到模型的底层数据存储。

该_parent_索引对应于被插入的新列的父;_first_和_last_是新列的列号将有被插入后，他们。

| ![Inserting columns](../img/modelview-begin-insert-columns.png) | Specify the first and last column numbers for the span of columns you want to insert into an item in a model.例如，如该图所示，我们插入3列第4列之前，所以_first_是4和_last_是6 ：

```
 beginInsertColumns(parent, 4, 6);

```

这会插入三个新列的列4 ， 5 ，和6 。 |
| ![Appending columns](../img/modelview-begin-append-columns.png) | To append columns, insert them after the last column.例如，如图所示，我们追加三列六个现有列（第5列结束）的集合，所以_first_是6和_last_8 ：

```
 beginInsertColumns(parent, 6, 8);

```

这追加了两个新列作为列6 ， 7 ，和8。 |

**Note:**此功能会发出[columnsAboutToBeInserted](qabstractitemmodel.html#columnsAboutToBeInserted)（），它连接视图（或股东代理人）信号必须处理插入数据之前。否则，意见最终可能会处于无效状态。

**See also** [endInsertColumns](qabstractitemmodel.html#endInsertColumns)（ ） 。

```
QAbstractItemModel.beginInsertRows (self, QModelIndex parent, int first, int last)
```

开始的行插入操作。

当重新实现[insertRows](qabstractitemmodel.html#insertRows)（ ）的一个子类，则必须调用此函数_before_将数据插入到模型的底层数据存储。

该_parent_索引对应于被插入新行的父;_first_和_last_是行号，新行将有被插入后，他们。

| ![Inserting rows](../img/modelview-begin-insert-rows.png) | Specify the first and last row numbers for the span of rows you want to insert into an item in a model.例如，如该图所示，我们插入3行第2列之前，所以_first_是2和_last_是4 ：

```
 beginInsertRows(parent, 2, 4);

```

这会插入三个新行作为行2 ， 3 ，和4 。 |
| ![Appending rows](../img/modelview-begin-append-rows.png) | To append rows, insert them after the last row.例如，如该图所示，我们追加两行的4现有的行（第3行结束）的集合，所以_first_是4和_last_是5 ：

```
 beginInsertRows(parent, 4, 5);

```

这追加两个新行的行4和5 。 |

**Note:**此功能会发出[rowsAboutToBeInserted](qabstractitemmodel.html#rowsAboutToBeInserted)（），它连接视图（或股东代理人）信号必须处理插入数据之前。否则，意见最终可能会处于无效状态。

**See also** [endInsertRows](qabstractitemmodel.html#endInsertRows)（ ） 。

```
bool QAbstractItemModel.beginMoveColumns (self, QModelIndex sourceParent, int sourceFirst, int sourceLast, QModelIndex destinationParent, int destinationColumn)
```

开始一列移动操作。

当重新实现一个子类，这种方法在你的模型简化移动实体。这个方法是负责移动持久指标在模型中，它，否则你会被要求做自己。使用beginMoveRows和endMoveRows是替代发光layoutAboutToBeChanged和layoutChanged直接随着changePersistentIndexes 。 layoutAboutToBeChanged通过该方法出于兼容性原因射出。

该_sourceParent_索引对应于从该列移动的母公司;_sourceFirst_和_sourceLast_是该列的第一列和最后一列数字移动。该_destinationParent_索引对应于所述父到其中的那些列被移动。该_destinationChild_是该组将被移到该列。即，在列中的索引_sourceFirst_在_sourceParent_将成为列_destinationChild_在_destinationParent_，然后是所有其他列达_sourceLast_。

然而，在相同的父（移动列下来的时候_sourceParent_和_destinationParent_是相等的），则columnss将放置前的_destinationChild_索引。也就是说，如果你想移动列0和1，因此他们将成为列1和2 ，_destinationChild_应该是3 。在这种情况下，用于源列的新索引`i`（这是间_sourceFirst_和_sourceLast_）等于`(destinationChild-sourceLast-1+i)`。

注意，如果_sourceParent_和_destinationParent_都是一样的，你必须确保_destinationChild_不是的范围内_sourceFirst_和_sourceLast_+1。您还必须确保您不要尝试将列移动到其自己的孩子或祖先之一。此方法返回False，如果任一条件为真，在这种情况下，你应该放弃你的移动操作。

此功能被引入Qt的4.6 。

**See also** [endMoveColumns](qabstractitemmodel.html#endMoveColumns)（ ） 。

```
bool QAbstractItemModel.beginMoveRows (self, QModelIndex sourceParent, int sourceFirst, int sourceLast, QModelIndex destinationParent, int destinationRow)
```

开始连续移动操作。

当重新实现一个子类，这种方法在你的模型简化移动实体。这个方法是负责移动持久指标在模型中，它，否则你会被要求做自己。使用beginMoveRows和endMoveRows是替代发光layoutAboutToBeChanged和layoutChanged直接随着changePersistentIndexes 。 layoutAboutToBeChanged通过该方法出于兼容性原因射出。

该_sourceParent_索引对应于从该行的移动母公司;_sourceFirst_和_sourceLast_是行的第一行和最后一行的数字移动。该_destinationParent_索引对应于所述父到其中的那些行被移动。该_destinationChild_是行，这些行会被感动。即，该指数在排_sourceFirst_在_sourceParent_将成为排_destinationChild_在_destinationParent_，接着所有其他行到_sourceLast_。

然而，在相同的父（移动排下来的时候_sourceParent_和_destinationParent_是相等的） ，这些行会被放置前的_destinationChild_索引。也就是说，如果你要移动的行0和1，因此他们将成为行1和2 ，_destinationChild_应该是3 。在这种情况下，用于源行新的索引`i`（这是间_sourceFirst_和_sourceLast_）等于`(destinationChild-sourceLast-1+i)`。

注意，如果_sourceParent_和_destinationParent_都是一样的，你必须确保_destinationChild_不是的范围内_sourceFirst_和_sourceLast_+1。您还必须确保您不要尝试将行移动到其自己的孩子或祖先之一。此方法返回False，如果任一条件为真，在这种情况下，你应该放弃你的移动操作。

| ![Moving rows to another parent](../img/modelview-move-rows-1.png) | Specify the first and last row numbers for the span of rows in the source parent you want to move in the model. Also specify the row in the destination parent to move the span to.例如，如该图所示，我们将3行从行2至4中的源中，所以_sourceFirst_是2和_sourceLast_是4。我们将这些物品上面第2行的目的地，所以_destinationChild_是2。

```
 beginMoveRows(sourceParent, 2, 4, destinationParent, 2);

```

这将移动源中的3行的行2 ，3和4 ，成为2 ，3和4中的目的地。其他受影响的兄弟姐妹都相应地偏移。 |
| ![Moving rows to append to another parent](../img/modelview-move-rows-2.png) | To append rows to another parent, move them to after the last row.例如，如图所示，我们把三排的6现有的行（在第5行结束）的集合，所以_destinationChild_是6 ：

```
 beginMoveRows(sourceParent, 2, 4, destinationParent, 6);

```

这将移动目标的行到目标父的末端为6,7和8 。 |
| ![Moving rows in the same parent up](../img/modelview-move-rows-3.png) | To move rows within the same parent, specify the row to move them to.例如，如该图所示，我们将一个项目从第2行到第0行，所以_sourceFirst_和_sourceLast_是2和_destinationChild_为0。

```
 beginMoveRows(parent, 2, 2, parent, 0);

```

注意，其它行可以相应地移动。还要注意的是移动的同一个父内物品时，你不应该试图无效或无操作动作。在上面的例子中，第2项是在移动之前排2 ，所以它不能被移动到第2行（其中，这已经是）或行3 （无操作如第3行的手段上述第3行，其中它已经是） |
| ![Moving rows in the same parent down](../img/modelview-move-rows-4.png) | To move rows within the same parent, specify the row to move them to.例如，如该图所示，我们将一个项目从第2行到第4行，所以_sourceFirst_和_sourceLast_是2和_destinationChild_是4。

```
 beginMoveRows(parent, 2, 2, parent, 4);

```

注意，其它行可以相应地移动。 |

此功能被引入Qt的4.6 。

**See also** [endMoveRows](qabstractitemmodel.html#endMoveRows)（ ） 。

```
QAbstractItemModel.beginRemoveColumns (self, QModelIndex parent, int first, int last)
```

开始的列删除操作。

当重新实现[removeColumns](qabstractitemmodel.html#removeColumns)（ ）的一个子类，则必须调用此函数_before_去除模型的底层数据存储的数据。

该_parent_索引对应于从该新的列被删除父;_first_和_last_是要移除的第一个和最后一列的列号。

| ![Removing columns](../img/modelview-begin-remove-columns.png) | Specify the first and last column numbers for the span of columns you want to remove from an item in a model.例如，如该图所示，我们从柱4取出3列至第6列，所以_first_是4和_last_是6 ：

```
 beginRemoveColumns(parent, 4, 6);

```

 |

**Note:**此功能会发出[columnsAboutToBeRemoved](qabstractitemmodel.html#columnsAboutToBeRemoved)（），它连接视图（或股东代理人）信号必须处理的数据被删除之前。否则，意见最终可能会处于无效状态。

**See also** [endRemoveColumns](qabstractitemmodel.html#endRemoveColumns)（ ） 。

```
QAbstractItemModel.beginRemoveRows (self, QModelIndex parent, int first, int last)
```

开始的行删除操作。

当重新实现[removeRows](qabstractitemmodel.html#removeRows)（ ）的一个子类，则必须调用此函数_before_去除模型的底层数据存储的数据。

该_parent_索引对应于从该新行被删除的父;_first_和_last_将被删除的行的行号。

| ![Removing rows](../img/modelview-begin-remove-rows.png) | Specify the first and last row numbers for the span of rows you want to remove from an item in a model.例如，如该图所示，我们从第2行取出两排至3行中，所以_first_是2和_last_是3：

```
 beginRemoveRows(parent, 2, 3);

```

 |

**Note:**此功能会发出[rowsAboutToBeRemoved](qabstractitemmodel.html#rowsAboutToBeRemoved)（），它连接视图（或股东代理人）信号必须处理的数据被删除之前。否则，意见最终可能会处于无效状态。

**See also** [endRemoveRows](qabstractitemmodel.html#endRemoveRows)（ ） 。

```
QAbstractItemModel.beginResetModel (self)
```

开始一个模型复位操作。

复位操作模式重置为它的当前状态在任何附加的看法。

**Note:**连接到这个模型中的任何意见都会被重置为好。

当一个模型被复位就意味着从模型报告的任何先前的数据现在是无效的，并且必须再次查询的。这也意味着，目前的项目和任何选定的项目将变得无效。

当一个模型从根本上改变它的数据它有时是容易只是调用这个函数，而不是发出[dataChanged](qabstractitemmodel.html#dataChanged)（ ）当基础数据源，或者它的结构，改变通知其他组件。

重置所有的内部数据结构中的模型或代理模型之前，必须调用此函数。

此功能被引入Qt的4.6 。

**See also** [modelAboutToBeReset](qabstractitemmodel.html#modelAboutToBeReset)（ ）[modelReset](qabstractitemmodel.html#modelReset)（）和[endResetModel](qabstractitemmodel.html#endResetModel)（ ） 。

```
QModelIndex QAbstractItemModel.buddy (self, QModelIndex index)
```

[

返回由代表该项目的哥们一个模型索引_index_。当用户希望编辑某个项目，视图将调用这个函数来检查模型中的另一个项目是否应该被编辑来代替。然后，视图将使用由哥们项目返回的模型索引构造一个委讬。

此函数的默认实现每个项目作为自己的哥们。

```
bool QAbstractItemModel.canFetchMore (self, QModelIndex parent)
```

返回True如果没有可用于更多的数据_parent_否则返回False 。

默认的实现始终返回False 。

](qmodelindex.html)

[如果canFetchMore （ ）返回True ，](qmodelindex.html)[QAbstractItemView](qabstractitemview.html)将调用[fetchMore](qabstractitemmodel.html#fetchMore)（ ） 。然而，本[fetchMore](qabstractitemmodel.html#fetchMore)当模型被填充增量（ ）函数只被调用。

**See also** [fetchMore](qabstractitemmodel.html#fetchMore)（ ） 。

```
QAbstractItemModel.changePersistentIndex (self, QModelIndex from, QModelIndex to)
```

更改[QPersistentModelIndex](qpersistentmodelindex.html)也就是等于给定_from_模型索引为给定的_to_模型索引。

如果没有持续性模型指数等于给定_from_模型索引被发现，没有什么改变。

**See also** [persistentIndexList](qabstractitemmodel.html#persistentIndexList)（）和[changePersistentIndexList](qabstractitemmodel.html#changePersistentIndexList)（ ） 。

```
QAbstractItemModel.changePersistentIndexList (self, list-of-QModelIndex from, list-of-QModelIndex to)
```

变化，它等于该索引中给出的QPersistentModelIndexes_from_模型索引列表，以给定的_to_模型索引列表。

如果没有持久化模型的索引等于该指标在给定的_from_模型索引列表被发现，没有什么改变。

这个函数是Qt 4.1中引入。

**See also** [persistentIndexList](qabstractitemmodel.html#persistentIndexList)（）和[changePersistentIndex](qabstractitemmodel.html#changePersistentIndex)（ ） 。

```
int QAbstractItemModel.columnCount (self, QModelIndex parent = QModelIndex())
```

这种方法是抽象的，应在任何子类中重新实现。

返回列的数目为给定的子_parent_。

在大多数的子类，列数是独立的_parent_。

例如：

```
 int DomModel.columnCount(const [QModelIndex](qmodelindex.html) &/*parent*/) const
 {
     return 3;
 }

```

**Note:**当实现一个基于表的模型，列数（）应该返回0当父是有效的。

**See also** [rowCount](qabstractitemmodel.html#rowCount)（ ） 。

```
QModelIndex QAbstractItemModel.createIndex (self, int row, int column, object object = 0)
```

[

创建用于给定一个模型索引_row_和_column_与内部指针_ptr_。

](qmodelindex.html)

[当使用一个](qmodelindex.html)[QSortFilterProxyModel](qsortfilterproxymodel.html)，其指标有自己的内部指针。这是不可取的访问此内部指针模型的外侧。使用[data](qabstractitemmodel.html#data)（ ）函数来代替。

此功能提供了该模型的子类必须使用它来创建模型的索引一致的接口。

```
QVariant QAbstractItemModel.data (self, QModelIndex index, int role = Qt.DisplayRole)
```

这种方法是抽象的，应在任何子类中重新实现。

返回下指定存储的数据_role_由所提及的项目_index_。

**Note:**如果你没有一个值返回，返回**invalid** [QVariant](qvariant.html)而不是返回0 。

**See also** [Qt.ItemDataRole](qt.html#ItemDataRole-enum)，[setData](qabstractitemmodel.html#setData)（）和[headerData](qabstractitemmodel.html#headerData)（ ） 。

```
bool QAbstractItemModel.decodeData (self, int row, int column, QModelIndex parent, QDataStream stream)
```

```
bool QAbstractItemModel.dropMimeData (self, QMimeData data, Qt.DropAction action, int row, int column, QModelIndex parent)
```

处理_data_通过拖放操作，与给定的供给结束_action_。

返回True如果数据和动作可以通过模型来处理，否则返回False 。

指定_row_，_column_和_parent_表明在该操作结束，其中模型项的位置。它是该模型的责任完成动作在正确的位置。

例如，在一个上一个项目一个放置操作[QTreeView](qtreeview.html)可能导致要么被插入的项目由指定儿童的新项目_row_，_column_和_parent_，或作为该项目的兄弟姐妹。

When _row_和_column_是-1则表示放置的数据应被视为直接丢弃在_parent_。通常，这将意味着追加数据的子项_parent_。如果_row_和列都大于或等于零，则意味着降刚刚指定之前发生_row_和_column_在指定的_parent_。

**See also** [supportedDropActions](qabstractitemmodel.html#supportedDropActions)（）和[Using drag and drop with item views](index.htm#using-drag-and-drop-with-item-views)。

```
QAbstractItemModel.encodeData (self, list-of-QModelIndex indexes, QDataStream stream)
```

```
QAbstractItemModel.endInsertColumns (self)
```

完一列的插入操作。

当重新实现[insertColumns](qabstractitemmodel.html#insertColumns)（ ）的一个子类，则必须调用此函数_after_将数据插入到模型的底层数据存储。

**See also** [beginInsertColumns](qabstractitemmodel.html#beginInsertColumns)（ ） 。

```
QAbstractItemModel.endInsertRows (self)
```

结尾的行插入操作。

当重新实现[insertRows](qabstractitemmodel.html#insertRows)（ ）的一个子类，则必须调用此函数_after_将数据插入到模型的底层数据存储。

**See also** [beginInsertRows](qabstractitemmodel.html#beginInsertRows)（ ） 。

```
QAbstractItemModel.endMoveColumns (self)
```

完一列移动操作。

当实现一个子类，则必须调用此函数_after_模型的底层数据存储中移动数据。

layoutChanged通过该方法出于兼容性原因射出。

此功能被引入Qt的4.6 。

**See also** [beginMoveColumns](qabstractitemmodel.html#beginMoveColumns)（ ） 。

```
QAbstractItemModel.endMoveRows (self)
```

完一排移动操作。

当实现一个子类，则必须调用此函数_after_模型的底层数据存储中移动数据。

layoutChanged通过该方法出于兼容性原因射出。

此功能被引入Qt的4.6 。

**See also** [beginMoveRows](qabstractitemmodel.html#beginMoveRows)（ ） 。

```
QAbstractItemModel.endRemoveColumns (self)
```

完一列删除操作。

当重新实现[removeColumns](qabstractitemmodel.html#removeColumns)（ ）的一个子类，则必须调用此函数_after_去除模型的底层数据存储的数据。

**See also** [beginRemoveColumns](qabstractitemmodel.html#beginRemoveColumns)（ ） 。

```
QAbstractItemModel.endRemoveRows (self)
```

结束连续切除手术。

当重新实现[removeRows](qabstractitemmodel.html#removeRows)（ ）的一个子类，则必须调用此函数_after_去除模型的底层数据存储的数据。

**See also** [beginRemoveRows](qabstractitemmodel.html#beginRemoveRows)（ ） 。

```
QAbstractItemModel.endResetModel (self)
```

完成一个模型复位操作。

你必须在你的模型或代理模型重置任何内部数据结构之后，调用此函数。

此功能被引入Qt的4.6 。

**See also** [beginResetModel](qabstractitemmodel.html#beginResetModel)（ ） 。

```
QAbstractItemModel.fetchMore (self, QModelIndex parent)
```

获取由指定的项目与父任何可用的数据_parent_索引。

重新实现这一点，如果你是填充模型增量。

默认实现不执行任何操作。

**See also** [canFetchMore](qabstractitemmodel.html#canFetchMore)（ ） 。

```
Qt.ItemFlags QAbstractItemModel.flags (self, QModelIndex index)
```

[

返回项标志为给定的_index_。

基类实现返回标志的组合，使该项目（`ItemIsEnabled`） ，并允许它被选中（`ItemIsSelectable`） 。

](index.htm)

[**See also**](index.htm) [Qt.ItemFlags](qt.html#ItemFlag-enum)。

```
bool QAbstractItemModel.hasChildren (self, QModelIndex parent = QModelIndex())
```

返回True如果_parent_有任何子女;否则返回False。

使用[rowCount](qabstractitemmodel.html#rowCount)（ ）父，找出孩子的数量。

**See also** [parent](qabstractitemmodel.html#parent)（）和[index](qabstractitemmodel.html#index)（ ） 。

```
bool QAbstractItemModel.hasIndex (self, int row, int column, QModelIndex parent = QModelIndex())
```

返回True如果模型返回一个有效的[QModelIndex](qmodelindex.html)为_row_和_column_同_parent_，否则返回False 。

```
QVariant QAbstractItemModel.headerData (self, int section, Qt.Orientation orientation, int role = Qt.DisplayRole)
```

返回数据为给定的_role_和_section_在用指定的标头_orientation_。

水平标头，把该分区编号相对应的列数。类似地，对于垂直标题，章节号对应的行号。

**See also** [Qt.ItemDataRole](qt.html#ItemDataRole-enum)，[setHeaderData](qabstractitemmodel.html#setHeaderData)（）和[QHeaderView](qheaderview.html)。

```
QModelIndex QAbstractItemModel.index (self, int row, int column, QModelIndex parent = QModelIndex())
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回由给定指定的模型项的索引_row_，_column_和_parent_索引。

](qmodelindex.html)

[当重新实现在子类中这个函数，调用](qmodelindex.html)[createIndex](qabstractitemmodel.html#createIndex)（）来生成其他组件可以用来参考的项目模型中的模型索引。

**See also** [createIndex](qabstractitemmodel.html#createIndex)（ ） 。

```
bool QAbstractItemModel.insertColumn (self, int column, QModelIndex parent = QModelIndex())
```

给定前插入一列_column_中的子项_parent_规定。

返回True如果插入的列，否则返回False 。

**See also** [insertColumns](qabstractitemmodel.html#insertColumns)（ ）[insertRow](qabstractitemmodel.html#insertRow)（）和[removeColumn](qabstractitemmodel.html#removeColumn)（ ） 。

```
bool QAbstractItemModel.insertColumns (self, int column, int count, QModelIndex parent = QModelIndex())
```

在支持此模式，插入_count_新列到模型中给定的前_column_。在每个新列中的项目将成为该项目由儿童代表_parent_模型索引。

If _column_为0时，列追加到任何现有的列。

If _column_ is [columnCount](qabstractitemmodel.html#columnCount)（）中，列被附加到任何现有的列。

If _parent_没有孩子，一个单列带_count_列被插入。

返回True如果成功插入的列，否则返回False 。

基类的实现不执行任何操作并返回False 。

如果你实现了自己的模型，你可以，如果你想支持插入重新实现此功能。或者，您也可以提供自己的API，用于改变数据。

**See also** [insertRows](qabstractitemmodel.html#insertRows)（ ）[removeColumns](qabstractitemmodel.html#removeColumns)（ ）[beginInsertColumns](qabstractitemmodel.html#beginInsertColumns)（）和[endInsertColumns](qabstractitemmodel.html#endInsertColumns)（ ） 。

```
bool QAbstractItemModel.insertRow (self, int row, QModelIndex parent = QModelIndex())
```

**Note:**基类实现这个功能不执行任何操作并返回False 。

给定前插入一个单行_row_中的子项_parent_规定。

返回True如果被插入的行，否则返回False 。

**See also** [insertRows](qabstractitemmodel.html#insertRows)（ ）[insertColumn](qabstractitemmodel.html#insertColumn)（）和[removeRow](qabstractitemmodel.html#removeRow)（ ） 。

```
bool QAbstractItemModel.insertRows (self, int row, int count, QModelIndex parent = QModelIndex())
```

**Note:**基类实现这个功能不执行任何操作并返回False 。

在支持此模式，插入_count_行插入到模型中给定前_row_。在新行项目将成为该项目由儿童代表_parent_模型索引。

If _row_为0时，行前加上父的任何现有行。

If _row_ is [rowCount](qabstractitemmodel.html#rowCount)（ ） ，该行被追加到父任何现有行。

If _parent_没有孩子，与一列_count_行插入。

返回True如果成功插入的行，否则返回False 。

如果你实现了自己的模型，你可以，如果你想支持插入重新实现此功能。或者，您也可以提供自己的API，用于改变数据。在这两种情况下，你将需要调用[beginInsertRows](qabstractitemmodel.html#beginInsertRows)（）和[endInsertRows](qabstractitemmodel.html#endInsertRows)（） ，用于通知该模型已经改变其他组件。

**See also** [insertColumns](qabstractitemmodel.html#insertColumns)（ ）[removeRows](qabstractitemmodel.html#removeRows)（ ）[beginInsertRows](qabstractitemmodel.html#beginInsertRows)（）和[endInsertRows](qabstractitemmodel.html#endInsertRows)（ ） 。

```
dict-of-int-QVariant QAbstractItemModel.itemData (self, QModelIndex index)
```

返回一个值模型对项目的所有预定义角色一个地图上的指定_index_。

如果你想扩展这个功能的默认行为，包括在地图上自定义角色重新实现这个函数。

**See also** [setItemData](qabstractitemmodel.html#setItemData)（ ）[Qt.ItemDataRole](qt.html#ItemDataRole-enum)和[data](qabstractitemmodel.html#data)（ ） 。

```
list-of-QModelIndex QAbstractItemModel.match (self, QModelIndex start, int role, QVariant value, int hits = 1, Qt.MatchFlags flags = Qt.MatchStartsWith|Qt.MatchWrap)
```

返回索引中的列中的项目清单_start_如根据给定的存储的数据索引_role_匹配指定_value_。搜索的执行方式是由定义_flags_给出。返回的列表可能是空的。

搜索开始从_start_指数，并继续进行，直到匹配的数据项的数目等于_hits_，搜索到达最后一排，或者搜索到达_start_再次 - 这取决于是否`MatchWrap`在被指定_flags_。如果你想搜索所有匹配的项，请使用_hits_= -1 。

默认情况下，该功能将执行对所有项目的包装，基于字符串的比较，寻找开头所指定的搜索条件的项目_value_。

**Note:**这个函数的默认实现只搜索列。重新实现此功能可包括不同的搜索行为。

```
QMimeData QAbstractItemModel.mimeData (self, list-of-QModelIndex indexes)
```

[

该_QMimeData_结果

](qmimedata.html)

[返回一个对象，它包含的数据序列化的项对应列表_indexes_规定。用于描述编码数据的格式是从所获得的](qmimedata.html)[mimeTypes](qabstractitemmodel.html#mimeTypes)（）函数。

如果索引列表是空的，或者没有支持的MIME类型，则返回0 ，而不是一个序列化的空单。

**See also** [mimeTypes](qabstractitemmodel.html#mimeTypes)（）和[dropMimeData](qabstractitemmodel.html#dropMimeData)（ ） 。

```
QStringList QAbstractItemModel.mimeTypes (self)
```

返回可用于描述模型索引的列表的MIME类型的列表。

**See also** [mimeData](qabstractitemmodel.html#mimeData)（ ） 。

```
QModelIndex QAbstractItemModel.parent (self, QModelIndex child)
```

[

这种方法是抽象的，应在任何子类中重新实现。

](qmodelindex.html)

[返回模型项目的父与给定_index_。如果该项目没有父，无效](qmodelindex.html)[QModelIndex](qmodelindex.html)返回。

，揭露树数据结构模型中使用一个共同的约定是，在第一列的项目只生孩子。对于这种情况，在子类中重新实现此功能，当返回的列[QModelIndex](qmodelindex.html)将是0 。

当重新实现在子类中这个功能，要小心避免调用[QModelIndex](qmodelindex.html)构件的功能，如[QModelIndex.parent](qmodelindex.html#parent)（ ） ，因为属于你的模型索引可以简单的叫你的实现，从而导致无限递归。

**See also** [createIndex](qabstractitemmodel.html#createIndex)（ ） 。

```
QObject QAbstractItemModel.parent (self)
```

[

```
list-of-QModelIndex QAbstractItemModel.persistentIndexList (self)
```

返回作为模型中的持久性索引的存储的索引列表。

这个函数中引入了Qt 4.2中。

```
bool QAbstractItemModel.removeColumn (self, int column, QModelIndex parent = QModelIndex())
```

删除给定的_column_从该子项_parent_规定。

Returns true if the column is removed; otherwise returns false.

](qobject.html)

[**See also**](qobject.html) [removeColumns](qabstractitemmodel.html#removeColumns)（ ）[removeRow](qabstractitemmodel.html#removeRow)（）和[insertColumn](qabstractitemmodel.html#insertColumn)（ ） 。

```
bool QAbstractItemModel.removeColumns (self, int column, int count, QModelIndex parent = QModelIndex())
```

在支持此模式，会删除_count_从给定的列_column_在父_parent_从模型。

返回True如果列被成功删除，否则返回False 。

基类的实现不执行任何操作并返回False 。

如果你实现了自己的模型，你可以，如果你想支持删除重新实现此功能。或者，您也可以提供自己的API，用于改变数据。

**See also** [removeColumn](qabstractitemmodel.html#removeColumn)（ ）[removeRows](qabstractitemmodel.html#removeRows)（ ）[insertColumns](qabstractitemmodel.html#insertColumns)（ ）[beginRemoveColumns](qabstractitemmodel.html#beginRemoveColumns)（）和[endRemoveColumns](qabstractitemmodel.html#endRemoveColumns)（ ） 。

```
bool QAbstractItemModel.removeRow (self, int row, QModelIndex parent = QModelIndex())
```

删除给定的_row_从该子项_parent_规定。

返回True如果该行被删除，否则返回False 。

这是一个方便的功能调用[removeRows](qabstractitemmodel.html#removeRows)（ ） 。该[QAbstractItemModel](qabstractitemmodel.html)实施[removeRows](qabstractitemmodel.html#removeRows)（ ）什么也不做。

**See also** [removeRows](qabstractitemmodel.html#removeRows)（ ）[removeColumn](qabstractitemmodel.html#removeColumn)（）和[insertRow](qabstractitemmodel.html#insertRow)（ ） 。

```
bool QAbstractItemModel.removeRows (self, int row, int count, QModelIndex parent = QModelIndex())
```

在支持此模式，会删除_count_从给定的行_row_在父_parent_从模型。

返回True如果行被成功取出，否则返回False 。

基类的实现不执行任何操作并返回False 。

如果你实现了自己的模型，你可以，如果你想支持删除重新实现此功能。或者，您也可以提供自己的API，用于改变数据。

**See also** [removeRow](qabstractitemmodel.html#removeRow)（ ）[removeColumns](qabstractitemmodel.html#removeColumns)（ ）[insertColumns](qabstractitemmodel.html#insertColumns)（ ）[beginRemoveRows](qabstractitemmodel.html#beginRemoveRows)（）和[endRemoveRows](qabstractitemmodel.html#endRemoveRows)（ ） 。

```
QAbstractItemModel.reset (self)
```

该模式重置为在任何连接的观点其原始状态。

**Note:**使用[beginResetModel](qabstractitemmodel.html#beginResetModel)（）和[endResetModel](qabstractitemmodel.html#endResetModel)（ ），而不是只要有可能。使用此方法只有在没有办法来调用[beginResetModel](qabstractitemmodel.html#beginResetModel)（ ）无效的模型前。否则，可能会导致意外的行为，与代理模式使用时尤其如此。

```
QAbstractItemModel.resetInternalData (self)
```

这种方法也是一个Qt槽与C + +的签名`void resetInternalData()`。

这个槽被调用后只是一个模型的内部数据，而它被复位清零。

该槽设置的混凝土代理模型的子类的便利性，例如子类[QSortFilterProxyModel](qsortfilterproxymodel.html)它保持额外的数据。

```
 class CustomDataProxy : public [QSortFilterProxyModel](qsortfilterproxymodel.html)
 {
     Q_OBJECT
 public:
     CustomDataProxy([QObject](qobject.html) *parent)
       : [QSortFilterProxyModel](qsortfilterproxymodel.html)(parent)
     {
     }

     ...

     [QVariant](qvariant.html) data(const [QModelIndex](qmodelindex.html) &index, int role)
     {
         if (role != [Qt](qt.html).BackgroundRole)
             return [QSortFilterProxyModel](qsortfilterproxymodel.html).data(index, role);

         if (m_customData.contains(index.row()))
             return m_customData.value(index.row());
         return [QSortFilterProxyModel](qsortfilterproxymodel.html).data(index, role);
     }

 private slots:
     void resetInternalData()
     {
         m_customData.clear();
     }

 private:
   [QHash](index.htm)<int, [QVariant](qvariant.html)> m_customData;
 };

```

此功能被引入Qt的4.8 。

**See also** [modelAboutToBeReset](qabstractitemmodel.html#modelAboutToBeReset)（）和[modelReset](qabstractitemmodel.html#modelReset)（ ） 。

```
QAbstractItemModel.revert (self)
```

这种方法也是一个Qt槽与C + +的签名`void revert()`。

让模型知道它应该丢弃缓存信息。此功能通常用于行编辑。

**See also** [submit](qabstractitemmodel.html#submit)（ ） 。

```
dict-of-int-QByteArray QAbstractItemModel.roleNames (self)
```

返回模型的角色名称。

此功能被引入Qt的4.6 。

**See also** [setRoleNames](qabstractitemmodel.html#setRoleNames)（ ） 。

```
int QAbstractItemModel.rowCount (self, QModelIndex parent = QModelIndex())
```

这种方法是抽象的，应在任何子类中重新实现。

返回下给定的行数_parent_。当父是有效则表示rowCount等是返回父孩子的数量。

**Note:**当实现一个基于表的模型， rowCount等（）应该返回0当父是有效的。

**See also** [columnCount](qabstractitemmodel.html#columnCount)（ ） 。

```
bool QAbstractItemModel.setData (self, QModelIndex index, QVariant value, int role = Qt.EditRole)
```

设置_role_对于在项目数据_index_至_value_。

成功返回True ，否则返回False 。

该[dataChanged](qabstractitemmodel.html#dataChanged)（）信号应被发射，如果数据被成功设置。

基类实现返回False 。此功能与[data](qabstractitemmodel.html#data)（ ）必须被重新实现可编辑的模型。

**See also** [Qt.ItemDataRole](qt.html#ItemDataRole-enum)，[data](qabstractitemmodel.html#data)（）和[itemData](qabstractitemmodel.html#itemData)（ ） 。

```
bool QAbstractItemModel.setHeaderData (self, int section, Qt.Orientation orientation, QVariant value, int role = Qt.EditRole)
```

设置数据为给定的_role_和_section_在用指定的标头_orientation_到_value_提供。

返回True如果标头的数据进行了更新，否则返回False 。

当重新实现此功能，[headerDataChanged](qabstractitemmodel.html#headerDataChanged)（）信号必须被明确地射出。

**See also** [Qt.ItemDataRole](qt.html#ItemDataRole-enum)和[headerData](qabstractitemmodel.html#headerData)（ ） 。

```
bool QAbstractItemModel.setItemData (self, QModelIndex index, dict-of-int-QVariant roles)
```

设置角色数据，该项目在_index_在相关联的值_roles_，对于每[Qt.ItemDataRole](qt.html#ItemDataRole-enum)。

成功返回True ，否则返回False 。

角色不在_roles_将不会被修改。

**See also** [setData](qabstractitemmodel.html#setData)（ ）[data](qabstractitemmodel.html#data)（）和[itemData](qabstractitemmodel.html#itemData)（ ） 。

```
QAbstractItemModel.setRoleNames (self, dict-of-int-QByteArray roleNames)
```

设置模型的角色名_roleNames_。

此功能允许在声明式UI角色，属性名角色标识符的映射。该模型使用之前这个函数必须被调用。该模型已被设置后，修改角色名，可能会导致未定义的行为。

此功能被引入Qt的4.6 。

**See also** [roleNames](qabstractitemmodel.html#roleNames)（ ） 。

```
QAbstractItemModel.setSupportedDragActions (self, Qt.DropActions)
```

设置支持拖放_actions_为模型中的项。

这个函数中引入了Qt 4.2中。

**See also** [supportedDragActions](qabstractitemmodel.html#supportedDragActions)（）和[Using drag and drop with item views](index.htm#using-drag-and-drop-with-item-views)。

```
QModelIndex QAbstractItemModel.sibling (self, int row, int column, QModelIndex idx)
```

[](qmodelindex.html)

[返回在同级_row_和_column_对于在项目_index_，或无效](qmodelindex.html)[QModelIndex](qmodelindex.html)如果没有兄弟在该位置。

兄弟（ ）只是一个方便的功能，发现该项目的父，并使用它来检索指定的子项的索引_row_和_column_。

**See also** [index](qabstractitemmodel.html#index)（ ）[QModelIndex.row](qmodelindex.html#row)（）和[QModelIndex.column](qmodelindex.html#column)（ ） 。

```
QAbstractItemModel.sort (self, int column, Qt.SortOrder order = Qt.AscendingOrder)
```

通过排序模型_column_在给定的_order_。

基类的实现不执行任何操作。

```
QSize QAbstractItemModel.span (self, QModelIndex index)
```

[

返回由所代表的项目的行和列跨度_index_。

**Note:**目前，不使用跨度。

```
bool QAbstractItemModel.submit (self)
```

这种方法也是一个Qt槽与C + +的签名`bool submit()`。

让模型知道它应该提交缓存信息到永久存储。此功能通常用于行编辑。

返回True如果没有错误，否则返回False 。

](qsize.html)

[**See also**](qsize.html) [revert](qabstractitemmodel.html#revert)（ ） 。

```
Qt.DropActions QAbstractItemModel.supportedDragActions (self)
```

[

返回通过此模型中的数据所支持的行动。

](index.htm)

[默认实现返回](index.htm)[supportedDropActions](qabstractitemmodel.html#supportedDropActions)（ ），除非特定的值被设置[setSupportedDragActions](qabstractitemmodel.html#setSupportedDragActions)（ ） 。

supportedDragActions （ ）是用来通过[QAbstractItemView.startDrag](qabstractitemview.html#startDrag)（）作为当发生拖拽时的默认值。

**See also** [setSupportedDragActions](qabstractitemmodel.html#setSupportedDragActions)（ ）[Qt.DropActions](qt.html#DropAction-enum)和[Using drag and drop with item views](index.htm#using-drag-and-drop-with-item-views)。

```
Qt.DropActions QAbstractItemModel.supportedDropActions (self)
```

[

返回此模型所支持的放置动作。

](index.htm)

[默认实现返回](index.htm)[Qt.CopyAction](qt.html#DropAction-enum)。如果你想支持额外的动作重新实现这个函数。您还必须重新实现[dropMimeData](qabstractitemmodel.html#dropMimeData)（ ）函数来处理额外的操作。

这个函数中引入了Qt 4.2中。

**See also** [dropMimeData](qabstractitemmodel.html#dropMimeData)（ ）[Qt.DropActions](qt.html#DropAction-enum)和[Using drag and drop with item views](index.htm#using-drag-and-drop-with-item-views)。

* * *

## Qt Signal Documentation

```
void columnsAboutToBeInserted (const QModelIndex&,int,int)
```

这是该信号的默认超载。

这个信号被发射列被插入到模型之前。新项目将被定位之间_start_和_end_包容性，在给定的_parent_项目。

**Note:**连接到该信号成分用它来适应变化的模型的尺寸。它只能由发射[QAbstractItemModel](qabstractitemmodel.html)实现，并且不能明确地在子码发射。

**See also** [insertColumns](qabstractitemmodel.html#insertColumns)（）和[beginInsertColumns](qabstractitemmodel.html#beginInsertColumns)（ ） 。

```
void columnsAboutToBeMoved (const QModelIndex&,int,int,const QModelIndex&,int)
```

这是该信号的默认超载。

这个信号被发射之前列模型内移动。将要移动的项目是那些之间_sourceStart_和_sourceEnd_包容性，在给定的_sourceParent_项目。他们将被移动到_destinationParent_开始在列_destinationColumn_。

**Note:**连接到该信号成分用它来适应变化的模型的尺寸。它只能由发射[QAbstractItemModel](qabstractitemmodel.html)实现，并且不能明确地在子码发射。

此功能被引入Qt的4.6 。

**See also** [beginMoveRows](qabstractitemmodel.html#beginMoveRows)（ ） 。

```
void columnsAboutToBeRemoved (const QModelIndex&,int,int)
```

这是该信号的默认超载。

这个信号被发射列被从模型中移除之前。要删除的项目是指之间_start_和_end_包容性，在给定的_parent_项目。

**Note:**连接到该信号成分用它来适应变化的模型的尺寸。它只能由发射[QAbstractItemModel](qabstractitemmodel.html)实现，并且不能明确地在子码发射。

**See also** [removeColumns](qabstractitemmodel.html#removeColumns)（）和[beginRemoveColumns](qabstractitemmodel.html#beginRemoveColumns)（ ） 。

```
void columnsInserted (const QModelIndex&,int,int)
```

这是该信号的默认超载。

列被插入到模型中后，此信号被发射。新项目是指之间_start_和_end_包容性，在给定的_parent_项目。

**Note:**连接到该信号成分用它来适应变化的模型的尺寸。它只能由发射[QAbstractItemModel](qabstractitemmodel.html)实现，并且不能明确地在子码发射。

**See also** [insertColumns](qabstractitemmodel.html#insertColumns)（）和[beginInsertColumns](qabstractitemmodel.html#beginInsertColumns)（ ） 。

```
void columnsMoved (const QModelIndex&,int,int,const QModelIndex&,int)
```

这是该信号的默认超载。

这个信号被发射的模型内的列已被移动之后。之间的项目_sourceStart_和_sourceEnd_包容性，在给定的_sourceParent_项目已移至_destinationParent_开始在列_destinationColumn_。

**Note:**连接到该信号成分用它来适应变化的模型的尺寸。它只能由发射[QAbstractItemModel](qabstractitemmodel.html)实现，并且不能明确地在子码发射。

此功能被引入Qt的4.6 。

**See also** [beginMoveRows](qabstractitemmodel.html#beginMoveRows)（ ） 。

```
void columnsRemoved (const QModelIndex&,int,int)
```

这是该信号的默认超载。

列已被从模型中移除之后，这个信号被发射。拆下的项目是那些之间_start_和_end_包容性，在给定的_parent_项目。

**Note:**连接到该信号成分用它来适应变化的模型的尺寸。它只能由发射[QAbstractItemModel](qabstractitemmodel.html)实现，并且不能明确地在子码发射。

**See also** [removeColumns](qabstractitemmodel.html#removeColumns)（）和[beginRemoveColumns](qabstractitemmodel.html#beginRemoveColumns)（ ） 。

```
void dataChanged (const QModelIndex&,const QModelIndex&)
```

这是该信号的默认超载。

这个信号被发射时在现有项目中的数据更改。

如果项目是相同的母公司，受影响的是那些之间_topLeft_和_bottomRight_包容性。如果该项目不具有相同的父，其行为是未定义的。

当重新实现[setData](qabstractitemmodel.html#setData)（）函数，该信号必须被明确地射出。

**See also** [headerDataChanged](qabstractitemmodel.html#headerDataChanged)（ ）[setData](qabstractitemmodel.html#setData)（）和[layoutChanged](qabstractitemmodel.html#layoutChanged)（ ） 。

```
void headerDataChanged (Qt::Orientation,int,int)
```

这是该信号的默认超载。

这个信号被发射时的报头被改变。该_orientation_表示水平或垂直头是否已改变。在从标题中的章节_first_到_last_需要被更新。

当重新实现[setHeaderData](qabstractitemmodel.html#setHeaderData)（）函数，该信号必须被明确地射出。

如果要更改的行或列数你不需要发出这个信号，但使用开始/结束功能（指在子类上一节[QAbstractItemModel](qabstractitemmodel.html)类描述详情） 。

**See also** [headerData](qabstractitemmodel.html#headerData)（ ）[setHeaderData](qabstractitemmodel.html#setHeaderData)（）和[dataChanged](qabstractitemmodel.html#dataChanged)（ ） 。

```
void layoutAboutToBeChanged ()
```

这是该信号的默认超载。

这个信号被发射一个模型的布局被改变之前。连接到该信号成分用它来适应变化的模型的布局。

子类应发光layoutAboutToBeChanged （ ）后更新任何持久性模型索引。

这个函数中引入了Qt 4.2中。

**See also** [layoutChanged](qabstractitemmodel.html#layoutChanged)（）和[changePersistentIndex](qabstractitemmodel.html#changePersistentIndex)（ ） 。

```
void layoutChanged ()
```

这是该信号的默认超载。

这个信号被发射时通过模型暴露项的布局改变了，例如，当该模型已排序。当收到一个针对这一信号，它应更新项目的布局，以反映这一变化。

当子类[QAbstractItemModel](qabstractitemmodel.html) or [QAbstractProxyModel](qabstractproxymodel.html)，请确保您发出[layoutAboutToBeChanged](qabstractitemmodel.html#layoutAboutToBeChanged)（ ）改变项目的顺序或改变你面对的看法，改变布局后发出layoutChanged （ ）的数据结构之前。

子类应发光layoutChanged （ ）之前更新任何持久性模型索引。换句话说，该结构变化时：

*   emit layoutAboutToBeChanged
*   Remember the [QModelIndex](qmodelindex.html) that will change
*   Update your internal data
*   Call [changePersistentIndex](qabstractitemmodel.html#changePersistentIndex)()
*   emit layoutChanged

**See also** [layoutAboutToBeChanged](qabstractitemmodel.html#layoutAboutToBeChanged)（ ）[dataChanged](qabstractitemmodel.html#dataChanged)（ ）[headerDataChanged](qabstractitemmodel.html#headerDataChanged)（ ）[modelReset](qabstractitemmodel.html#modelReset)（）和[changePersistentIndex](qabstractitemmodel.html#changePersistentIndex)（ ） 。

```
void modelAboutToBeReset ()
```

这是该信号的默认超载。

这个信号被发射时[reset](qabstractitemmodel.html#reset)（ ）被调用时，模型的内部状态（例如持久化模型指标）已经失效之前。

这个函数中引入了Qt 4.2中。

**See also** [beginResetModel](qabstractitemmodel.html#beginResetModel)（）和[modelReset](qabstractitemmodel.html#modelReset)（ ） 。

```
void modelReset ()
```

这是该信号的默认超载。

这个信号被发射时[reset](qabstractitemmodel.html#reset)（ ）被调用时，模型的内部状态（例如持久化模型指标）已经无效后。

这个函数是Qt 4.1中引入。

**See also** [endResetModel](qabstractitemmodel.html#endResetModel)（）和[modelAboutToBeReset](qabstractitemmodel.html#modelAboutToBeReset)（ ） 。

```
void rowsAboutToBeInserted (const QModelIndex&,int,int)
```

这是该信号的默认超载。

这个信号被发射的行被插入到模型之前。新项目将被定位之间_start_和_end_包容性，在给定的_parent_项目。

**Note:**连接到该信号成分用它来适应变化的模型的尺寸。它只能由发射[QAbstractItemModel](qabstractitemmodel.html)实现，并且不能明确地在子码发射。

**See also** [insertRows](qabstractitemmodel.html#insertRows)（）和[beginInsertRows](qabstractitemmodel.html#beginInsertRows)（ ） 。

```
void rowsAboutToBeMoved (const QModelIndex&,int,int,const QModelIndex&,int)
```

这是该信号的默认超载。

这个信号被发射之前的行的模型内移动。将要移动的项目是那些之间_sourceStart_和_sourceEnd_包容性，在给定的_sourceParent_项目。他们将被移动到_destinationParent_开始于行_destinationRow_。

**Note:**连接到该信号成分用它来适应变化的模型的尺寸。它只能由发射[QAbstractItemModel](qabstractitemmodel.html)实现，并且不能明确地在子码发射。

此功能被引入Qt的4.6 。

**See also** [beginMoveRows](qabstractitemmodel.html#beginMoveRows)（ ） 。

```
void rowsAboutToBeRemoved (const QModelIndex&,int,int)
```

这是该信号的默认超载。

这个信号被发射行从模型中删除之前。将要删除的项目是那些之间_start_和_end_包容性，在给定的_parent_项目。

**Note:**连接到该信号成分用它来适应变化的模型的尺寸。它只能由发射[QAbstractItemModel](qabstractitemmodel.html)实现，并且不能明确地在子码发射。

**See also** [removeRows](qabstractitemmodel.html#removeRows)（）和[beginRemoveRows](qabstractitemmodel.html#beginRemoveRows)（ ） 。

```
void rowsInserted (const QModelIndex&,int,int)
```

这是该信号的默认超载。

行被插入该模型之后，这个信号被发射。新项目是指之间_start_和_end_包容性，在给定的_parent_项目。

**Note:**连接到该信号成分用它来适应变化的模型的尺寸。它只能由发射[QAbstractItemModel](qabstractitemmodel.html)实现，并且不能明确地在子码发射。

**See also** [insertRows](qabstractitemmodel.html#insertRows)（）和[beginInsertRows](qabstractitemmodel.html#beginInsertRows)（ ） 。

```
void rowsMoved (const QModelIndex&,int,int,const QModelIndex&,int)
```

这是该信号的默认超载。

这个信号被发射的模型内的行已被移动之后。之间的项目_sourceStart_和_sourceEnd_包容性，在给定的_sourceParent_项目已移至_destinationParent_开始于行_destinationRow_。

**Note:**连接到该信号成分用它来适应变化的模型的尺寸。它只能由发射[QAbstractItemModel](qabstractitemmodel.html)实现，并且不能明确地在子码发射。

此功能被引入Qt的4.6 。

**See also** [beginMoveRows](qabstractitemmodel.html#beginMoveRows)（ ） 。

```
void rowsRemoved (const QModelIndex&,int,int)
```

这是该信号的默认超载。

行已被从模型中移除之后，这个信号被发射。拆下的项目是那些之间_start_和_end_包容性，在给定的_parent_项目。

**Note:**连接到该信号成分用它来适应变化的模型的尺寸。它只能由发射[QAbstractItemModel](qabstractitemmodel.html)实现，并且不能明确地在子码发射。

**See also** [removeRows](qabstractitemmodel.html#removeRows)（）和[beginRemoveRows](qabstractitemmodel.html#beginRemoveRows)（ ） 。