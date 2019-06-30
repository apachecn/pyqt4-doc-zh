# QAbstractProxyModel Class Reference

## [[QtGui](index.htm) module]

该QAbstractProxyModel类提供了代理项目模型，可以做排序，过滤或其他数据处理任务的基类。[More...](#details)

继承[QAbstractItemModel](qabstractitemmodel.html)。

通过继承[QIdentityProxyModel](qidentityproxymodel.html)和[QSortFilterProxyModel](qsortfilterproxymodel.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `QModelIndex buddy (self, QModelIndex index)`
*   `bool canFetchMore (self, QModelIndex parent)`
*   `QVariant data (self, QModelIndex proxyIndex, int role = Qt.DisplayRole)`
*   `fetchMore (self, QModelIndex parent)`
*   `Qt.ItemFlags flags (self, QModelIndex index)`
*   `bool hasChildren (self, QModelIndex parent = QModelIndex())`
*   `QVariant headerData (self, int section, Qt.Orientation orientation, int role)`
*   `dict-of-int-QVariant itemData (self, QModelIndex index)`
*   `QModelIndex mapFromSource (self, QModelIndex sourceIndex)`
*   `QItemSelection mapSelectionFromSource (self, QItemSelection selection)`
*   `QItemSelection mapSelectionToSource (self, QItemSelection selection)`
*   `QModelIndex mapToSource (self, QModelIndex proxyIndex)`
*   `QMimeData mimeData (self, list-of-QModelIndex indexes)`
*   `QStringList mimeTypes (self)`
*   `revert (self)`
*   `bool setData (self, QModelIndex index, QVariant value, int role = Qt.EditRole)`
*   `bool setHeaderData (self, int section, Qt.Orientation orientation, QVariant value, int role = Qt.EditRole)`
*   `bool setItemData (self, QModelIndex index, dict-of-int-QVariant roles)`
*   `setSourceModel (self, QAbstractItemModel sourceModel)`
*   `sort (self, int column, Qt.SortOrder order = Qt.AscendingOrder)`
*   `QAbstractItemModel sourceModel (self)`
*   `QSize span (self, QModelIndex index)`
*   `bool submit (self)`
*   `Qt.DropActions supportedDropActions (self)`

* * *

## Detailed Description

该QAbstractProxyModel类提供了代理项目模型，可以做排序，过滤或其他数据处理任务的基类。

这个类定义了代理模型必须使用能够与其他模型/视图组件正确地互操作的标准接口。它不应该被直接实例化。

所有标准的代理模式都源自于QAbstractProxyModel类。如果你需要创建一个新的代理模型类，它通常是更好的子类，它提供了你想提供一个最接近的行为，现有的类。

该过滤器或排序从源模型数据的项目应通过使用或子类来创建代理模式[QSortFilterProxyModel](qsortfilterproxymodel.html)。

子类QAbstractProxyModel ，你需要实现[mapFromSource](qabstractproxymodel.html#mapFromSource)（）和[mapToSource](qabstractproxymodel.html#mapToSource)（ ） 。该[mapSelectionFromSource](qabstractproxymodel.html#mapSelectionFromSource)（）和[mapSelectionToSource](qabstractproxymodel.html#mapSelectionToSource)（ ）函数只需要如果你需要从默认行为不同的行为来重新实现。

**Note:**如果源模型被删除或没有指定源模式，代理模式运行在一个空的佔位符模型。

* * *

## Method Documentation

```
QAbstractProxyModel.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个代理模型与给定_parent_。

```
QModelIndex QAbstractProxyModel.buddy (self, QModelIndex index)
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemModel.buddy](qabstractitemmodel.html#buddy)（ ） 。

此功能被引入Qt的4.8 。

```
bool QAbstractProxyModel.canFetchMore (self, QModelIndex parent)
```

从重新实现[QAbstractItemModel.canFetchMore](qabstractitemmodel.html#canFetchMore)（ ） 。

此功能被引入Qt的4.8 。

```
QVariant QAbstractProxyModel.data (self, QModelIndex proxyIndex, int role = Qt.DisplayRole)
```

从重新实现[QAbstractItemModel.data](qabstractitemmodel.html#data)（ ） 。

**See also** [setData](qabstractproxymodel.html#setData)（ ） 。

```
QAbstractProxyModel.fetchMore (self, QModelIndex parent)
```

从重新实现[QAbstractItemModel.fetchMore](qabstractitemmodel.html#fetchMore)（ ） 。

此功能被引入Qt的4.8 。

```
Qt.ItemFlags QAbstractProxyModel.flags (self, QModelIndex index)
```

[](index.htm)

[从重新实现](index.htm)[QAbstractItemModel.flags](qabstractitemmodel.html#flags)（ ） 。

```
bool QAbstractProxyModel.hasChildren (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.hasChildren](qabstractitemmodel.html#hasChildren)（ ） 。

此功能被引入Qt的4.8 。

```
QVariant QAbstractProxyModel.headerData (self, int section, Qt.Orientation orientation, int role)
```

从重新实现[QAbstractItemModel.headerData](qabstractitemmodel.html#headerData)（ ） 。

**See also** [setHeaderData](qabstractproxymodel.html#setHeaderData)（ ） 。

```
dict-of-int-QVariant QAbstractProxyModel.itemData (self, QModelIndex index)
```

从重新实现[QAbstractItemModel.itemData](qabstractitemmodel.html#itemData)（ ） 。

**See also** [setItemData](qabstractproxymodel.html#setItemData)（ ） 。

```
QModelIndex QAbstractProxyModel.mapFromSource (self, QModelIndex sourceIndex)
```

[

这种方法是抽象的，应在任何子类中重新实现。

重新实现这个函数返回对应于在代理模型中的模型索引_sourceIndex_从源模型。

](qmodelindex.html)

[**See also**](qmodelindex.html) [mapToSource](qabstractproxymodel.html#mapToSource)（ ） 。

```
QItemSelection QAbstractProxyModel.mapSelectionFromSource (self, QItemSelection selection)
```

[

返回指定映射的代理选择_sourceSelection_。

重新实现此方法以源选择映射到代理服务器的选择。

](qitemselection.html)

```
QItemSelection QAbstractProxyModel.mapSelectionToSource (self, QItemSelection selection)
```

[

返回指定映射的一个源选择_proxySelection_。

重新实现此方法以代理选择映射到源选择。

](qitemselection.html)

```
QModelIndex QAbstractProxyModel.mapToSource (self, QModelIndex proxyIndex)
```

[

这种方法是抽象的，应在任何子类中重新实现。

重新实现这个函数返回对应于源模型中的模型索引_proxyIndex_在代理模型。

](qmodelindex.html)

[**See also**](qmodelindex.html) [mapFromSource](qabstractproxymodel.html#mapFromSource)（ ） 。

```
QMimeData QAbstractProxyModel.mimeData (self, list-of-QModelIndex indexes)
```

[

该_QMimeData_结果

](qmimedata.html)

[从重新实现](qmimedata.html)[QAbstractItemModel.mimeData](qabstractitemmodel.html#mimeData)（ ） 。

此功能被引入Qt的4.8 。

```
QStringList QAbstractProxyModel.mimeTypes (self)
```

从重新实现[QAbstractItemModel.mimeTypes](qabstractitemmodel.html#mimeTypes)（ ） 。

此功能被引入Qt的4.8 。

```
QAbstractProxyModel.revert (self)
```

从重新实现[QAbstractItemModel.revert](qabstractitemmodel.html#revert)（ ） 。

```
bool QAbstractProxyModel.setData (self, QModelIndex index, QVariant value, int role = Qt.EditRole)
```

从重新实现[QAbstractItemModel.setData](qabstractitemmodel.html#setData)（ ） 。

**See also** [data](qabstractproxymodel.html#data)（ ） 。

```
bool QAbstractProxyModel.setHeaderData (self, int section, Qt.Orientation orientation, QVariant value, int role = Qt.EditRole)
```

从重新实现[QAbstractItemModel.setHeaderData](qabstractitemmodel.html#setHeaderData)（ ） 。

**See also** [headerData](qabstractproxymodel.html#headerData)（ ） 。

```
bool QAbstractProxyModel.setItemData (self, QModelIndex index, dict-of-int-QVariant roles)
```

从重新实现[QAbstractItemModel.setItemData](qabstractitemmodel.html#setItemData)（ ） 。

**See also** [itemData](qabstractproxymodel.html#itemData)（ ） 。

```
QAbstractProxyModel.setSourceModel (self, QAbstractItemModel sourceModel)
```

设置给定_sourceModel_到由所述代理模型进行处理。

**See also** [sourceModel](qabstractproxymodel.html#sourceModel)（ ） 。

```
QAbstractProxyModel.sort (self, int column, Qt.SortOrder order = Qt.AscendingOrder)
```

从重新实现[QAbstractItemModel.sort](qabstractitemmodel.html#sort)（ ） 。

此功能被引入Qt的4.8 。

```
QAbstractItemModel QAbstractProxyModel.sourceModel (self)
```

[

返回包含可通过代理服务器模型的数据模型。

](qabstractitemmodel.html)

[**See also**](qabstractitemmodel.html) [setSourceModel](qabstractproxymodel.html#setSourceModel)（ ） 。

```
QSize QAbstractProxyModel.span (self, QModelIndex index)
```

[](qsize.html)

[从重新实现](qsize.html)[QAbstractItemModel.span](qabstractitemmodel.html#span)（ ） 。

此功能被引入Qt的4.8 。

```
bool QAbstractProxyModel.submit (self)
```

从重新实现[QAbstractItemModel.submit](qabstractitemmodel.html#submit)（ ） 。

```
Qt.DropActions QAbstractProxyModel.supportedDropActions (self)
```

[](index.htm)

[从重新实现](index.htm)[QAbstractItemModel.supportedDropActions](qabstractitemmodel.html#supportedDropActions)（ ） 。

此功能被引入Qt的4.8 。