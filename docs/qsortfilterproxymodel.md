# QSortFilterProxyModel Class Reference

## [[QtGui](index.htm) module]

该QSortFilterProxyModel类提供用于排序和另一个模型和视图之间通过过滤数据的支持。[More...](#details)

继承[QAbstractProxyModel](qabstractproxymodel.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `QModelIndex buddy (self, QModelIndex index)`
*   `bool canFetchMore (self, QModelIndex parent)`
*   `clear (self)`
*   `int columnCount (self, QModelIndex parent = QModelIndex())`
*   `QVariant data (self, QModelIndex index, int role = Qt.DisplayRole)`
*   `bool dropMimeData (self, QMimeData data, Qt.DropAction action, int row, int column, QModelIndex parent)`
*   `bool dynamicSortFilter (self)`
*   `fetchMore (self, QModelIndex parent)`
*   `bool filterAcceptsColumn (self, int source_column, QModelIndex source_parent)`
*   `bool filterAcceptsRow (self, int source_row, QModelIndex source_parent)`
*   `Qt.CaseSensitivity filterCaseSensitivity (self)`
*   `filterChanged (self)`
*   `int filterKeyColumn (self)`
*   `QRegExp filterRegExp (self)`
*   `int filterRole (self)`
*   `Qt.ItemFlags flags (self, QModelIndex index)`
*   `bool hasChildren (self, QModelIndex parent = QModelIndex())`
*   `QVariant headerData (self, int section, Qt.Orientation orientation, int role = Qt.EditRole)`
*   `QModelIndex index (self, int row, int column, QModelIndex parent = QModelIndex())`
*   `bool insertColumns (self, int column, int count, QModelIndex parent = QModelIndex())`
*   `bool insertRows (self, int row, int count, QModelIndex parent = QModelIndex())`
*   `invalidate (self)`
*   `invalidateFilter (self)`
*   `bool isSortLocaleAware (self)`
*   `bool lessThan (self, QModelIndex left, QModelIndex right)`
*   `QModelIndex mapFromSource (self, QModelIndex sourceIndex)`
*   `QItemSelection mapSelectionFromSource (self, QItemSelection sourceSelection)`
*   `QItemSelection mapSelectionToSource (self, QItemSelection proxySelection)`
*   `QModelIndex mapToSource (self, QModelIndex proxyIndex)`
*   `list-of-QModelIndex match (self, QModelIndex start, int role, QVariant value, int hits = 1, Qt.MatchFlags flags = Qt.MatchStartsWith|Qt.MatchWrap)`
*   `QMimeData mimeData (self, list-of-QModelIndex indexes)`
*   `QStringList mimeTypes (self)`
*   `QModelIndex parent (self, QModelIndex child)`
*   `QObject parent (self)`
*   `bool removeColumns (self, int column, int count, QModelIndex parent = QModelIndex())`
*   `bool removeRows (self, int row, int count, QModelIndex parent = QModelIndex())`
*   `int rowCount (self, QModelIndex parent = QModelIndex())`
*   `bool setData (self, QModelIndex index, QVariant value, int role = Qt.EditRole)`
*   `setDynamicSortFilter (self, bool enable)`
*   `setFilterCaseSensitivity (self, Qt.CaseSensitivity cs)`
*   `setFilterFixedString (self, QString pattern)`
*   `setFilterKeyColumn (self, int column)`
*   `setFilterRegExp (self, QRegExp regExp)`
*   `setFilterRegExp (self, QString pattern)`
*   `setFilterRole (self, int role)`
*   `setFilterWildcard (self, QString pattern)`
*   `bool setHeaderData (self, int section, Qt.Orientation orientation, QVariant value, int role = Qt.EditRole)`
*   `setSortCaseSensitivity (self, Qt.CaseSensitivity cs)`
*   `setSortLocaleAware (self, bool on)`
*   `setSortRole (self, int role)`
*   `setSourceModel (self, QAbstractItemModel sourceModel)`
*   `sort (self, int column, Qt.SortOrder order = Qt.AscendingOrder)`
*   `Qt.CaseSensitivity sortCaseSensitivity (self)`
*   `int sortColumn (self)`
*   `Qt.SortOrder sortOrder (self)`
*   `int sortRole (self)`
*   `QSize span (self, QModelIndex index)`
*   `Qt.DropActions supportedDropActions (self)`

* * *

## Detailed Description

该QSortFilterProxyModel类提供用于排序和另一个模型和视图之间通过过滤数据的支持。

QSortFilterProxyModel可用于排序的项目，滤出产品，或两者兼而有之。该模型转换源模型的结构通过映射把它提供给新的索引，对应于不同地点的模型索引，视图使用。这种方法允许一个给定的源模型被尽可能的观点而言，无需对基础数据的任何转换，并没有复制在内存中的数据重组。

让我们假设我们想通过排序和筛选的自定义模型提供的项目。该代码来设置的模型和视图，_without_排序和过滤，看起来像这样：

```
         [QTreeView](qtreeview.html) *treeView = new [QTreeView](qtreeview.html);
         MyItemModel *model = new MyItemModel(this);

         treeView->setModel(model);

```

要添加排序和筛选支持`MyItemModel`，我们需要创建一个QSortFilterProxyModel ，呼叫[setSourceModel](qsortfilterproxymodel.html#setSourceModel)（）与`MyItemModel`作为参数，并在视图安装QSortFilterProxyModel ：

```
         [QTreeView](qtreeview.html) *treeView = new [QTreeView](qtreeview.html);
         MyItemModel *sourceModel = new MyItemModel(this);
         QSortFilterProxyModel *proxyModel = new QSortFilterProxyModel(this);

         proxyModel->setSourceModel(sourceModel);
         treeView->setModel(proxyModel);

```

在这一点上，既不排序也不过滤功能，原始数据被显示在视图中。通过QSortFilterProxyModel所做的任何更改应用到原始模型。

该QSortFilterProxyModel作为一个包装器的原始模型。如果你需要转换的源[QModelIndex](qmodelindex.html)上课要排序/筛选模型的索引，反之亦然，使用[mapToSource](qsortfilterproxymodel.html#mapToSource)（ ）[mapFromSource](qsortfilterproxymodel.html#mapFromSource)（ ）[mapSelectionToSource](qsortfilterproxymodel.html#mapSelectionToSource)（）和[mapSelectionFromSource](qsortfilterproxymodel.html#mapSelectionFromSource)（ ） 。

**Note:**默认情况下，该模型没有动态重新排序和重新过滤数据时的原始模型的变化。这种行为可以通过设置改变[dynamicSortFilter](qsortfilterproxymodel.html#dynamicSortFilter-prop)属性。

该[Basic Sort/Filter Model](index.htm)和[Custom Sort/Filter Model](index.htm)示例说明了如何使用QSortFilterProxyModel执行基本分类和过滤，以及如何它的子类来实现自定义的行为。

### Sorting

[QTableView](qtableview.html)和[QTreeView](qtreeview.html)有[sortingEnabled](qtreeview.html#sortingEnabled-prop)属性控制用户是否可以通过单击视图的水平标题排序的视图。例如：

```
         treeView->setSortingEnabled(true);

```

当此功能开启（默认是关闭的） ，点击标题部分按照该列进行排序的项目。通过点击多次，用户可以在升序和降序之间交替。

![A sorted QTreeView](../img/qsortfilterproxymodel-sorting.png)

幕后，视图调用[sort](qsortfilterproxymodel.html#sort)（）的模型来重新排列在该模型中的数据的虚拟功能。为了使您的数据排序，你可以实现[sort](qsortfilterproxymodel.html#sort)（ ）在你的模型，或使用QSortFilterProxyModel来包装你的模型 - QSortFilterProxyModel提供了一个通用[sort](qsortfilterproxymodel.html#sort)（）的重新实现该操作的[sortRole](qsortfilterproxymodel.html#sortRole-prop)（ ） （[Qt.DisplayRole](qt.html#ItemDataRole-enum)默认情况下）的项目，并能够理解多种数据类型，包括`int`，[QString](qstring.html)和[QDateTime](qdatetime.html)。对于分层模型，排序是递归应用到所有子项。比较字符串时默认情况下，敏感的，这可以通过设置改变[sortCaseSensitivity](qsortfilterproxymodel.html#sortCaseSensitivity-prop)属性。

自定义排序行为是通过继承QSortFilterProxyModel和重新实现实现[lessThan](qsortfilterproxymodel.html#lessThan)（），它是用于比较的商品。例如：

```
 bool MySortFilterProxyModel.lessThan(const [QModelIndex](qmodelindex.html) &left,
                                       const [QModelIndex](qmodelindex.html) &right) const
 {
     [QVariant](qvariant.html) leftData = sourceModel()->data(left);
     [QVariant](qvariant.html) rightData = sourceModel()->data(right);

     if (leftData.type() == [QVariant](qvariant.html).DateTime) {
         return leftData.toDateTime() < rightData.toDateTime();
     } else {
         [QRegExp](qregexp.html) *emailPattern = new [QRegExp](qregexp.html)("([\\w\\.]*@[\\w\\.]*)");

         [QString](qstring.html) leftString = leftData.toString();
         if(left.column() == 1 && emailPattern->indexIn(leftString) != -1)
             leftString = emailPattern->cap(1);

         [QString](qstring.html) rightString = rightData.toString();
         if(right.column() == 1 && emailPattern->indexIn(rightString) != -1)
             rightString = emailPattern->cap(1);

         return [QString](qstring.html).localeAwareCompare(leftString, rightString) < 0;
     }
 }

```

（此代码片段来自[Custom Sort/Filter Model](index.htm)例子）。

另一种方法来排序是禁用的视图排序并施以一定的顺序给用户。这是通过显式调用完成[sort](qsortfilterproxymodel.html#sort)（ ）与所需的列和顺序上的QSortFilterProxyModel参数（或原始模型，如果它实现[sort](qsortfilterproxymodel.html#sort)（））。例如：

```
         proxyModel->sort(2, [Qt](qt.html).AscendingOrder);

```

QSortFilterProxyModel可以通过柱-1进行排序，在这种情况下它返回到底层源模型的排序顺序。

### Filtering

除了排序， QSortFilterProxyModel可以用来隐藏不匹配有一定的过滤项。使用指定的过滤器被[QRegExp](qregexp.html)对象和被施加到[filterRole](qsortfilterproxymodel.html#filterRole-prop)（ ） （[Qt.DisplayRole](qt.html#ItemDataRole-enum)默认情况下）各项目时，对于给定的列中。该[QRegExp](qregexp.html)对象可以用来匹配一个正则表达式，通配符模式，或一个固定的字符串。例如：

```
         proxyModel->setFilterRegExp([QRegExp](qregexp.html)(".png", [Qt](qt.html).CaseInsensitive,
                                             [QRegExp](qregexp.html).FixedString));
         proxyModel->setFilterKeyColumn(1);

```

对于分层模型，过滤器被递归应用到所有的孩子。如果父项不匹配滤波器，将显示其没有孩子。

一个常见的用例是让用户指定一个过滤器正则表达式，通配符模式，或固定字符串[QLineEdit](qlineedit.html)和连接[textChanged()](qlineedit.html#textChanged)信号到[setFilterRegExp](qsortfilterproxymodel.html#filterRegExp-prop)（ ）[setFilterWildcard](qsortfilterproxymodel.html#setFilterWildcard)（） ，或[setFilterFixedString](qsortfilterproxymodel.html#setFilterFixedString)（ ）重新应用筛选器。

自定义过滤行为可以通过重新实现来实现的[filterAcceptsRow](qsortfilterproxymodel.html#filterAcceptsRow)（）和[filterAcceptsColumn](qsortfilterproxymodel.html#filterAcceptsColumn)（）函数。例如（从[Custom Sort/Filter Model](index.htm)例子） ，下面的实现会忽略[filterKeyColumn](qsortfilterproxymodel.html#filterKeyColumn-prop)财产和执行对列0 ， 1 ​​，和2过滤：

```
 bool MySortFilterProxyModel.filterAcceptsRow(int sourceRow,
         const [QModelIndex](qmodelindex.html) &sourceParent) const
 {
     [QModelIndex](qmodelindex.html) index0 = sourceModel()->index(sourceRow, 0, sourceParent);
     [QModelIndex](qmodelindex.html) index1 = sourceModel()->index(sourceRow, 1, sourceParent);
     [QModelIndex](qmodelindex.html) index2 = sourceModel()->index(sourceRow, 2, sourceParent);

     return (sourceModel()->data(index0).toString().contains(filterRegExp())
             || sourceModel()->data(index1).toString().contains(filterRegExp()))
            && dateInRange(sourceModel()->data(index2).toDate());
 }

```

（此代码片段来自[Custom Sort/Filter Model](index.htm)例子）。

如果您正在使用大量的滤波，并有调用[invalidateFilter](qsortfilterproxymodel.html#invalidateFilter)（ ）反复使用[reset](qabstractitemmodel.html#reset)（ ）可能更有效，这取决于你的模型的实现。但是，[reset](qabstractitemmodel.html#reset)（）返回的代理模型到其原始状态，失去了选择信息，并且将导致要重新填充所述代理模型。

### Subclassing

自[QAbstractProxyModel](qabstractproxymodel.html)和它的子类都源自[QAbstractItemModel](qabstractitemmodel.html)，许多关于继承正常模式相同的建议也适用于代理模型。此外，值得一提的是，许多在这个类函数的默认实现是这么写的，他们在程序中调用相关的源模型的等效功能。这个简单的代理机制，可能需要对源模型更复杂的行为被重写，例如，如果源模型提供了一个自定义的[hasChildren](qsortfilterproxymodel.html#hasChildren)（）实现，你也应该提供一个在代理模型。

**Note:**可在子类化模型的一些通用准则[Model Subclassing Reference](index.htm#model-subclassing-reference)。

* * *

## Method Documentation

```
QSortFilterProxyModel.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个排序滤波器模型与给定_parent_。

```
QModelIndex QSortFilterProxyModel.buddy (self, QModelIndex index)
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemModel.buddy](qabstractitemmodel.html#buddy)（ ） 。

```
bool QSortFilterProxyModel.canFetchMore (self, QModelIndex parent)
```

从重新实现[QAbstractItemModel.canFetchMore](qabstractitemmodel.html#canFetchMore)（ ） 。

```
QSortFilterProxyModel.clear (self)
```

这种方法也是一个Qt槽与C + +的签名`void clear()`。

```
int QSortFilterProxyModel.columnCount (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.columnCount](qabstractitemmodel.html#columnCount)（ ） 。

```
QVariant QSortFilterProxyModel.data (self, QModelIndex index, int role = Qt.DisplayRole)
```

从重新实现[QAbstractItemModel.data](qabstractitemmodel.html#data)（ ） 。

**See also** [setData](qsortfilterproxymodel.html#setData)（ ） 。

```
bool QSortFilterProxyModel.dropMimeData (self, QMimeData data, Qt.DropAction action, int row, int column, QModelIndex parent)
```

从重新实现[QAbstractItemModel.dropMimeData](qabstractitemmodel.html#dropMimeData)（ ） 。

```
bool QSortFilterProxyModel.dynamicSortFilter (self)
```

```
QSortFilterProxyModel.fetchMore (self, QModelIndex parent)
```

从重新实现[QAbstractItemModel.fetchMore](qabstractitemmodel.html#fetchMore)（ ） 。

```
bool QSortFilterProxyModel.filterAcceptsColumn (self, int source_column, QModelIndex source_parent)
```

返回True如果该列中的项表示在给定的_source_column_和_source_parent_应包括在模型中，否则返回False 。

如果有关项目中保存的值过滤字符串，字符串通配符或正则表达式匹配的默认实现返回True 。

**Note:**默认情况下，[Qt.DisplayRole](qt.html#ItemDataRole-enum)用于确定是否该行应该被接受或没有。这可以通过设置来改变该[filterRole](qsortfilterproxymodel.html#filterRole-prop)属性。

**See also** [filterAcceptsRow](qsortfilterproxymodel.html#filterAcceptsRow)（ ）[setFilterFixedString](qsortfilterproxymodel.html#setFilterFixedString)（ ）[setFilterRegExp](qsortfilterproxymodel.html#filterRegExp-prop)（）和[setFilterWildcard](qsortfilterproxymodel.html#setFilterWildcard)（ ） 。

```
bool QSortFilterProxyModel.filterAcceptsRow (self, int source_row, QModelIndex source_parent)
```

返回True如果该行中的项目表示在给定的_source_row_和_source_parent_应包括在模型中，否则返回False 。

如果有关项目中保存的值过滤字符串，字符串通配符或正则表达式匹配的默认实现返回True 。

**Note:**默认情况下，[Qt.DisplayRole](qt.html#ItemDataRole-enum)用于确定是否该行应该被接受或没有。这可以通过设置来改变该[filterRole](qsortfilterproxymodel.html#filterRole-prop)属性。

**See also** [filterAcceptsColumn](qsortfilterproxymodel.html#filterAcceptsColumn)（ ）[setFilterFixedString](qsortfilterproxymodel.html#setFilterFixedString)（ ）[setFilterRegExp](qsortfilterproxymodel.html#filterRegExp-prop)（）和[setFilterWildcard](qsortfilterproxymodel.html#setFilterWildcard)（ ） 。

```
Qt.CaseSensitivity QSortFilterProxyModel.filterCaseSensitivity (self)
```

[

```
QSortFilterProxyModel.filterChanged (self)
```

```
int QSortFilterProxyModel.filterKeyColumn (self)
```

](qt.html#CaseSensitivity-enum)

```
QRegExp QSortFilterProxyModel.filterRegExp (self)
```

[

```
int QSortFilterProxyModel.filterRole (self)
```

](qregexp.html)

```
Qt.ItemFlags QSortFilterProxyModel.flags (self, QModelIndex index)
```

[](index.htm)

[从重新实现](index.htm)[QAbstractItemModel.flags](qabstractitemmodel.html#flags)（ ） 。

```
bool QSortFilterProxyModel.hasChildren (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.hasChildren](qabstractitemmodel.html#hasChildren)（ ） 。

```
QVariant QSortFilterProxyModel.headerData (self, int section, Qt.Orientation orientation, int role = Qt.EditRole)
```

从重新实现[QAbstractItemModel.headerData](qabstractitemmodel.html#headerData)（ ） 。

**See also** [setHeaderData](qsortfilterproxymodel.html#setHeaderData)（ ） 。

```
QModelIndex QSortFilterProxyModel.index (self, int row, int column, QModelIndex parent = QModelIndex())
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemModel.index](qabstractitemmodel.html#index)（ ） 。

```
bool QSortFilterProxyModel.insertColumns (self, int column, int count, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.insertColumns](qabstractitemmodel.html#insertColumns)（ ） 。

```
bool QSortFilterProxyModel.insertRows (self, int row, int count, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.insertRows](qabstractitemmodel.html#insertRows)（ ） 。

```
QSortFilterProxyModel.invalidate (self)
```

这种方法也是一个Qt槽与C + +的签名`void invalidate()`。

无效的当前排序和过滤。

此功能被引入Qt的4.3 。

**See also** [invalidateFilter](qsortfilterproxymodel.html#invalidateFilter)（ ） 。

```
QSortFilterProxyModel.invalidateFilter (self)
```

无效的电流滤波。

这个功能应该如果要实现自定义的过滤（被称为例如：[filterAcceptsRow](qsortfilterproxymodel.html#filterAcceptsRow)（ ） ） ，以及您的滤波器参数发生了变化。

此功能被引入Qt的4.3 。

**See also** [invalidate](qsortfilterproxymodel.html#invalidate)（ ） 。

```
bool QSortFilterProxyModel.isSortLocaleAware (self)
```

```
bool QSortFilterProxyModel.lessThan (self, QModelIndex left, QModelIndex right)
```

返回True如果该项目的值称为给定索引_left_由给定的索引小于该项目的值称为_right_，否则返回False 。

在排序时，此功能是用来作为\u003c操作符，和处理以下[QVariant](qvariant.html)类型：

*   [QVariant.Int](qvariant.html#Type-enum)
*   [QVariant.UInt](qvariant.html#Type-enum)
*   [QVariant.LongLong](qvariant.html#Type-enum)
*   [QVariant.ULongLong](qvariant.html#Type-enum)
*   [QVariant.Double](qvariant.html#Type-enum)
*   [QVariant.Char](qvariant.html#Type-enum)
*   [QVariant.Date](qvariant.html#Type-enum)
*   [QVariant.Time](qvariant.html#Type-enum)
*   [QVariant.DateTime](qvariant.html#Type-enum)
*   [QVariant.String](qvariant.html#Type-enum)

任何其他类型将被转换为一个[QString](qstring.html) using [QVariant.toString](qvariant.html#toString)（ ） 。

比较[QString](qstring.html)s的情况下，默认情况下，敏感，这可以通过使用被改变[sortCaseSensitivity](qsortfilterproxymodel.html#sortCaseSensitivity-prop)属性。

默认情况下，[Qt.DisplayRole](qt.html#ItemDataRole-enum)与相关联的[QModelIndex](qmodelindex.html)ES是用于比较。这可以通过设置来改变该[sortRole](qsortfilterproxymodel.html#sortRole-prop)属性。

**Note:**通过在对应于源模型中的指标。

**See also** [sortRole](qsortfilterproxymodel.html#sortRole-prop)，[sortCaseSensitivity](qsortfilterproxymodel.html#sortCaseSensitivity-prop)和[dynamicSortFilter](qsortfilterproxymodel.html#dynamicSortFilter-prop)。

```
QModelIndex QSortFilterProxyModel.mapFromSource (self, QModelIndex sourceIndex)
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractProxyModel.mapFromSource](qabstractproxymodel.html#mapFromSource)（ ） 。

返回模型指数在[QSortFilterProxyModel](qsortfilterproxymodel.html)考虑到_sourceIndex_从源模型。

**See also** [mapToSource](qsortfilterproxymodel.html#mapToSource)（ ） 。

```
QItemSelection QSortFilterProxyModel.mapSelectionFromSource (self, QItemSelection sourceSelection)
```

[](qitemselection.html)

[从重新实现](qitemselection.html)[QAbstractProxyModel.mapSelectionFromSource](qabstractproxymodel.html#mapSelectionFromSource)（ ） 。

```
QItemSelection QSortFilterProxyModel.mapSelectionToSource (self, QItemSelection proxySelection)
```

[](qitemselection.html)

[从重新实现](qitemselection.html)[QAbstractProxyModel.mapSelectionToSource](qabstractproxymodel.html#mapSelectionToSource)（ ） 。

```
QModelIndex QSortFilterProxyModel.mapToSource (self, QModelIndex proxyIndex)
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractProxyModel.mapToSource](qabstractproxymodel.html#mapToSource)（ ） 。

返回对应于给定的源模型指数_proxyIndex_从分类筛选模型。

**See also** [mapFromSource](qsortfilterproxymodel.html#mapFromSource)（ ） 。

```
list-of-QModelIndex QSortFilterProxyModel.match (self, QModelIndex start, int role, QVariant value, int hits = 1, Qt.MatchFlags flags = Qt.MatchStartsWith|Qt.MatchWrap)
```

从重新实现[QAbstractItemModel.match](qabstractitemmodel.html#match)（ ） 。

```
QMimeData QSortFilterProxyModel.mimeData (self, list-of-QModelIndex indexes)
```

[

该_QMimeData_结果

](qmimedata.html)

[从重新实现](qmimedata.html)[QAbstractItemModel.mimeData](qabstractitemmodel.html#mimeData)（ ） 。

```
QStringList QSortFilterProxyModel.mimeTypes (self)
```

从重新实现[QAbstractItemModel.mimeTypes](qabstractitemmodel.html#mimeTypes)（ ） 。

```
QModelIndex QSortFilterProxyModel.parent (self, QModelIndex child)
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemModel.parent](qabstractitemmodel.html#parent)（ ） 。

```
QObject QSortFilterProxyModel.parent (self)
```

[

```
bool QSortFilterProxyModel.removeColumns (self, int column, int count, QModelIndex parent = QModelIndex())
```

](qobject.html)

[从重新实现](qobject.html)[QAbstractItemModel.removeColumns](qabstractitemmodel.html#removeColumns)（ ） 。

```
bool QSortFilterProxyModel.removeRows (self, int row, int count, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.removeRows](qabstractitemmodel.html#removeRows)（ ） 。

```
int QSortFilterProxyModel.rowCount (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.rowCount](qabstractitemmodel.html#rowCount)（ ） 。

```
bool QSortFilterProxyModel.setData (self, QModelIndex index, QVariant value, int role = Qt.EditRole)
```

从重新实现[QAbstractItemModel.setData](qabstractitemmodel.html#setData)（ ） 。

**See also** [data](qsortfilterproxymodel.html#data)（ ） 。

```
QSortFilterProxyModel.setDynamicSortFilter (self, bool enable)
```

```
QSortFilterProxyModel.setFilterCaseSensitivity (self, Qt.CaseSensitivity cs)
```

```
QSortFilterProxyModel.setFilterFixedString (self, QString pattern)
```

这种方法也是一个Qt槽与C + +的签名`void setFilterFixedString(const QString&)`。

设置用于对源模型的内容进行筛选，以给定的固定字符串_pattern_。

**See also** [setFilterCaseSensitivity](qsortfilterproxymodel.html#filterCaseSensitivity-prop)（ ）[setFilterRegExp](qsortfilterproxymodel.html#filterRegExp-prop)（ ）[setFilterWildcard](qsortfilterproxymodel.html#setFilterWildcard)（）和[filterRegExp](qsortfilterproxymodel.html#filterRegExp-prop)（ ） 。

```
QSortFilterProxyModel.setFilterKeyColumn (self, int column)
```

```
QSortFilterProxyModel.setFilterRegExp (self, QRegExp regExp)
```

```
QSortFilterProxyModel.setFilterRegExp (self, QString pattern)
```

这种方法也是一个Qt槽与C + +的签名`void setFilterRegExp(const QString&)`。

```
QSortFilterProxyModel.setFilterRole (self, int role)
```

```
QSortFilterProxyModel.setFilterWildcard (self, QString pattern)
```

这种方法也是一个Qt槽与C + +的签名`void setFilterWildcard(const QString&)`。

设置用于对源模型的内容进行筛选，以给定的通配符表达式_pattern_。

**See also** [setFilterCaseSensitivity](qsortfilterproxymodel.html#filterCaseSensitivity-prop)（ ）[setFilterRegExp](qsortfilterproxymodel.html#filterRegExp-prop)（ ）[setFilterFixedString](qsortfilterproxymodel.html#setFilterFixedString)（）和[filterRegExp](qsortfilterproxymodel.html#filterRegExp-prop)（ ） 。

```
bool QSortFilterProxyModel.setHeaderData (self, int section, Qt.Orientation orientation, QVariant value, int role = Qt.EditRole)
```

从重新实现[QAbstractItemModel.setHeaderData](qabstractitemmodel.html#setHeaderData)（ ） 。

**See also** [headerData](qsortfilterproxymodel.html#headerData)（ ） 。

```
QSortFilterProxyModel.setSortCaseSensitivity (self, Qt.CaseSensitivity cs)
```

```
QSortFilterProxyModel.setSortLocaleAware (self, bool on)
```

```
QSortFilterProxyModel.setSortRole (self, int role)
```

```
QSortFilterProxyModel.setSourceModel (self, QAbstractItemModel sourceModel)
```

从重新实现[QAbstractProxyModel.setSourceModel](qabstractproxymodel.html#setSourceModel)（ ） 。

```
QSortFilterProxyModel.sort (self, int column, Qt.SortOrder order = Qt.AscendingOrder)
```

从重新实现[QAbstractItemModel.sort](qabstractitemmodel.html#sort)（ ） 。

```
Qt.CaseSensitivity QSortFilterProxyModel.sortCaseSensitivity (self)
```

[

```
int QSortFilterProxyModel.sortColumn (self)
```

目前用于排序的列

这将返回最近使用的排序列。

此功能被引入Qt的4.5 。

](qt.html#CaseSensitivity-enum)

```
Qt.SortOrder QSortFilterProxyModel.sortOrder (self)
```

[

目前用于排序的顺序

这将返回最近使用的排序顺序。

此功能被引入Qt的4.5 。

```
int QSortFilterProxyModel.sortRole (self)
```

](qt.html#SortOrder-enum)

```
QSize QSortFilterProxyModel.span (self, QModelIndex index)
```

[](qsize.html)

[从重新实现](qsize.html)[QAbstractItemModel.span](qabstractitemmodel.html#span)（ ） 。

```
Qt.DropActions QSortFilterProxyModel.supportedDropActions (self)
```

[](index.htm)

[从重新实现](index.htm)[QAbstractItemModel.supportedDropActions](qabstractitemmodel.html#supportedDropActions)（ ） 。