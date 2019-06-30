# QIdentityProxyModel Class Reference

## [[QtGui](index.htm) module]

该QIdentityProxyModel类以代理其源模型未修改[More...](#details)

继承[QAbstractProxyModel](qabstractproxymodel.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `int columnCount (self, QModelIndex parent = QModelIndex())`
*   `bool dropMimeData (self, QMimeData data, Qt.DropAction action, int row, int column, QModelIndex parent)`
*   `QModelIndex index (self, int row, int column, QModelIndex parent = QModelIndex())`
*   `bool insertColumns (self, int column, int count, QModelIndex parent = QModelIndex())`
*   `bool insertRows (self, int row, int count, QModelIndex parent = QModelIndex())`
*   `QModelIndex mapFromSource (self, QModelIndex sourceIndex)`
*   `QItemSelection mapSelectionFromSource (self, QItemSelection selection)`
*   `QItemSelection mapSelectionToSource (self, QItemSelection selection)`
*   `QModelIndex mapToSource (self, QModelIndex proxyIndex)`
*   `list-of-QModelIndex match (self, QModelIndex start, int role, QVariant value, int hits = 1, Qt.MatchFlags flags = Qt.MatchStartsWith|Qt.MatchWrap)`
*   `QModelIndex parent (self, QModelIndex child)`
*   `bool removeColumns (self, int column, int count, QModelIndex parent = QModelIndex())`
*   `bool removeRows (self, int row, int count, QModelIndex parent = QModelIndex())`
*   `int rowCount (self, QModelIndex parent = QModelIndex())`
*   `setSourceModel (self, QAbstractItemModel sourceModel)`

* * *

## Detailed Description

该QIdentityProxyModel类以代理其源模型未修改

QIdentityProxyModel可以用来转发源模型的结构完全相同，没有排序，过滤或其它变换。这类似于在概念上单位矩阵其中AI = A。

因为它确实没有任何排序或筛选，这个类是代理模式的变换最适合的[data](qabstractproxymodel.html#data)源模型的（ ） 。例如，代理模型可以被创建来定义所使用的字体，或背景色，或工具提示等，这消除了需要执行的处理中创建的模型的结构相同的类别中的所有数据，并且也可以是用于创建可重用的组件。

这也提供了一种方法来改变在其中一个源模型是由第三者不能修改的供给的情况下的数据。

```
 class DateFormatProxyModel : public QIdentityProxyModel
 {
   // ...

   void setDateFormatString(const [QString](qstring.html) &formatString)
   {
     m_formatString = formatString;
   }

   [QVariant](qvariant.html) data(const [QModelIndex](qmodelindex.html) &index, int role)
   {
     if (role != [Qt](qt.html).DisplayRole)
       return QIdentityProxyModel.data(index, role);

     const [QDateTime](qdatetime.html) dateTime = sourceModel()->data(SourceClass.DateRole).toDateTime();

     return dateTime.toString(m_formatString);
   }

 private:
   [QString](qstring.html) m_formatString;
 };

```

* * *

## Method Documentation

```
QIdentityProxyModel.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个身份模型与给定_parent_。

```
int QIdentityProxyModel.columnCount (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.columnCount](qabstractitemmodel.html#columnCount)（ ） 。

```
bool QIdentityProxyModel.dropMimeData (self, QMimeData data, Qt.DropAction action, int row, int column, QModelIndex parent)
```

从重新实现[QAbstractItemModel.dropMimeData](qabstractitemmodel.html#dropMimeData)（ ） 。

```
QModelIndex QIdentityProxyModel.index (self, int row, int column, QModelIndex parent = QModelIndex())
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemModel.index](qabstractitemmodel.html#index)（ ） 。

```
bool QIdentityProxyModel.insertColumns (self, int column, int count, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.insertColumns](qabstractitemmodel.html#insertColumns)（ ） 。

```
bool QIdentityProxyModel.insertRows (self, int row, int count, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.insertRows](qabstractitemmodel.html#insertRows)（ ） 。

```
QModelIndex QIdentityProxyModel.mapFromSource (self, QModelIndex sourceIndex)
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractProxyModel.mapFromSource](qabstractproxymodel.html#mapFromSource)（ ） 。

```
QItemSelection QIdentityProxyModel.mapSelectionFromSource (self, QItemSelection selection)
```

[](qitemselection.html)

[从重新实现](qitemselection.html)[QAbstractProxyModel.mapSelectionFromSource](qabstractproxymodel.html#mapSelectionFromSource)（ ） 。

```
QItemSelection QIdentityProxyModel.mapSelectionToSource (self, QItemSelection selection)
```

[](qitemselection.html)

[从重新实现](qitemselection.html)[QAbstractProxyModel.mapSelectionToSource](qabstractproxymodel.html#mapSelectionToSource)（ ） 。

```
QModelIndex QIdentityProxyModel.mapToSource (self, QModelIndex proxyIndex)
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractProxyModel.mapToSource](qabstractproxymodel.html#mapToSource)（ ） 。

```
list-of-QModelIndex QIdentityProxyModel.match (self, QModelIndex start, int role, QVariant value, int hits = 1, Qt.MatchFlags flags = Qt.MatchStartsWith|Qt.MatchWrap)
```

从重新实现[QAbstractItemModel.match](qabstractitemmodel.html#match)（ ） 。

```
QModelIndex QIdentityProxyModel.parent (self, QModelIndex child)
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemModel.parent](qabstractitemmodel.html#parent)（ ） 。

```
bool QIdentityProxyModel.removeColumns (self, int column, int count, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.removeColumns](qabstractitemmodel.html#removeColumns)（ ） 。

```
bool QIdentityProxyModel.removeRows (self, int row, int count, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.removeRows](qabstractitemmodel.html#removeRows)（ ） 。

```
int QIdentityProxyModel.rowCount (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.rowCount](qabstractitemmodel.html#rowCount)（ ） 。

```
QIdentityProxyModel.setSourceModel (self, QAbstractItemModel sourceModel)
```

从重新实现[QAbstractProxyModel.setSourceModel](qabstractproxymodel.html#setSourceModel)（ ） 。