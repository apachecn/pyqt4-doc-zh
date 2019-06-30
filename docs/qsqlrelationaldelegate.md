# QSqlRelationalDelegate Class Reference

## [[QtSql](index.htm) module]

该QSqlRelationalDelegate类提供了用于显示和编辑从数据委讬[QSqlRelationalTableModel](qsqlrelationaltablemodel.html)。[More...](#details)

继承[QItemDelegate](qitemdelegate.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `QWidget createEditor (self, QWidget parent, QStyleOptionViewItem option, QModelIndex index)`
*   `setEditorData (self, QWidget editor, QModelIndex index)`
*   `setModelData (self, QWidget editor, QAbstractItemModel model, QModelIndex index)`

* * *

## Detailed Description

该QSqlRelationalDelegate类提供了用于显示和编辑从数据委讬[QSqlRelationalTableModel](qsqlrelationaltablemodel.html)。

不同的是默认的委讬， QSqlRelationalDelegate提供了一个组合框是外键到其他表中的字段。使用类，只需调用[QAbstractItemView.setItemDelegate](qabstractitemview.html#setItemDelegate)（ ）与QSqlRelationalDelegate的一个实例的视图：

```
     [QTableView](qtableview.html) *view = new [QTableView](qtableview.html);
     view->setModel(model);
     view->setItemDelegate(new QSqlRelationalDelegate(view));

```

该[Relational Table Model](index.htm)例如（如下图所示）说明如何使用QSqlRelationalDelegate与配合[QSqlRelationalTableModel](qsqlrelationaltablemodel.html)提供表外键的支持。

![](../img/relationaltable.png)

* * *

## Method Documentation

```
QSqlRelationalDelegate.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QSqlRelationalDelegate](qsqlrelationaldelegate.html)与给定对象_parent_。

```
QWidget QSqlRelationalDelegate.createEditor (self, QWidget parent, QStyleOptionViewItem option, QModelIndex index)
```

[

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

](qwidget.html)

[从重新实现](qwidget.html)[QAbstractItemDelegate.createEditor](qabstractitemdelegate.html#createEditor)（ ） 。

```
QSqlRelationalDelegate.setEditorData (self, QWidget editor, QModelIndex index)
```

从重新实现[QAbstractItemDelegate.setEditorData](qabstractitemdelegate.html#setEditorData)（ ） 。

```
QSqlRelationalDelegate.setModelData (self, QWidget editor, QAbstractItemModel model, QModelIndex index)
```

从重新实现[QAbstractItemDelegate.setModelData](qabstractitemdelegate.html#setModelData)（ ） 。