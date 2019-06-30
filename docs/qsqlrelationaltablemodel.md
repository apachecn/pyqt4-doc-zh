# QSqlRelationalTableModel Class Reference

## [[QtSql](index.htm) module]

该QSqlRelationalTableModel类提供了一个可编辑的数据模型为单个数据库表，与外键的支持。[More...](#details)

继承[QSqlTableModel](qsqltablemodel.html)。

### Types

*   `enum JoinMode { InnerJoin, LeftJoin }`

### Methods

*   `__init__ (self, QObject parent = None, QSqlDatabase db = QSqlDatabase())`
*   `clear (self)`
*   `QVariant data (self, QModelIndex index, int role = Qt.DisplayRole)`
*   `bool insertRowIntoTable (self, QSqlRecord values)`
*   `QString orderByClause (self)`
*   `QSqlRelation relation (self, int column)`
*   `QSqlTableModel relationModel (self, int column)`
*   `bool removeColumns (self, int column, int count, QModelIndex parent = QModelIndex())`
*   `revertRow (self, int row)`
*   `bool select (self)`
*   `QString selectStatement (self)`
*   `bool setData (self, QModelIndex index, QVariant value, int role = Qt.EditRole)`
*   `setJoinMode (self, JoinMode joinMode)`
*   `setRelation (self, int column, QSqlRelation relation)`
*   `setTable (self, QString tableName)`
*   `bool updateRowInTable (self, int row, QSqlRecord values)`

* * *

## Detailed Description

该QSqlRelationalTableModel类提供了一个可编辑的数据模型为单个数据库表，与外键的支持。

QSqlRelationalTableModel就像[QSqlTableModel](qsqltablemodel.html)，但允许列要被设置为外键成其他数据库表。

| ![](../img/noforeignkeys.png) | ![](../img/foreignkeys.png) |

左边的屏幕截图显示了纯[QSqlTableModel](qsqltablemodel.html)在[QTableView](qtableview.html)。外键（`city`和`country`）不会被解析为可读价值。右边的屏幕截图显示了QSqlRelationalTableModel ，与外键分解成可读的文本字符串。

下面的代码片段显示了QSqlRelationalTableModel是如何设置：

```
     model->setTable("employee");

     model->setRelation(2, [QSqlRelation](qsqlrelation.html)("city", "id", "name"));
     model->setRelation(3, [QSqlRelation](qsqlrelation.html)("country", "id", "name"));

```

该[setRelation](qsqlrelationaltablemodel.html#setRelation)（ ）函数调用建立两个表之间的关系。第一次调用指定表2列`employee`是，与字段映射外键`id`表`city`，而认为应该提出的`city`的`name`字段给用户。第二次调用是否与第3列类似的东西。

如果你使用一个读写QSqlRelationalTableModel ，你可能想使用[QSqlRelationalDelegate](qsqlrelationaldelegate.html)在视图上。不同的是默认的委讬，[QSqlRelationalDelegate](qsqlrelationaldelegate.html)提供了一个组合框是外键到其他表中的字段。使用类，只需调用[QAbstractItemView.setItemDelegate](qabstractitemview.html#setItemDelegate)（ ）与实例的视图[QSqlRelationalDelegate](qsqlrelationaldelegate.html)：

```
     [QTableView](qtableview.html) *view = new [QTableView](qtableview.html);
     view->setModel(model);
     view->setItemDelegate(new [QSqlRelationalDelegate](qsqlrelationaldelegate.html)(view));

```

该[sql/relationaltablemodel](index.htm)示例说明了如何使用QSqlRelationalTableModel与配合[QSqlRelationalDelegate](qsqlrelationaldelegate.html)提供表外键的支持。

![](../img/relationaltable.png)

注意事项：

*   The table must have a primary key declared.
*   The table's primary key may not contain a relation to another table.
*   If a relational table contains keys that refer to non-existent rows in the referenced table, the rows containing the invalid keys will not be exposed through the model. The user or the database is responsible for keeping referential integrity.
*   If a relation's display column name is also used as a column name in the main table, or if it is used as display column name in more than one relation it will be aliased. The alias is is the relation's table name and display column name joined by an underscore (e.g. tablename_columnname). All occurrences of the duplicate display column name are aliased when duplication is detected, but no aliasing is done to the column names in the main table. The aliasing doesn't affect [QSqlRelation](qsqlrelation.html), so [QSqlRelation.displayColumn](qsqlrelation.html#displayColumn)() will return the original display column name, but [QSqlRecord.fieldName](qsqlrecord.html#fieldName)() will return aliases.
*   When using [setData](qsqlrelationaltablemodel.html#setData)() the role should always be [Qt.EditRole](qt.html#ItemDataRole-enum), and when using [data](qsqlrelationaltablemodel.html#data)() the role should always be [Qt.DisplayRole](qt.html#ItemDataRole-enum).

* * *

## Type Documentation

```
QSqlRelationalTableModel.JoinMode
```

此枚举指定的模式连接两个表时要使用的类型。

| Constant | Value | Description |
| --- | --- | --- |
| `QSqlRelationalTableModel.InnerJoin` | `0` | 内部联接模式，返回行的时候，至少有一个匹配两个表中。 |
| `QSqlRelationalTableModel.LeftJoin` | `1` | LEFT JOIN模式，返回左表（ table_name1 ）的所有行，即使在右表（ table_name2 ）的结果。 |

这个枚举被引入或修改的Qt 4.8 。

**See also** [QSqlRelationalTableModel.setJoinMode](qsqlrelationaltablemodel.html#setJoinMode)（ ） 。

* * *

## Method Documentation

```
QSqlRelationalTableModel.__init__ (self, QObject parent = None, QSqlDatabase db = QSqlDatabase())
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建一个空的[QSqlRelationalTableModel](qsqlrelationaltablemodel.html)并设置父_parent_与数据库连接_db_。如果_db_是无效的，默认的数据库连接将被使用。

```
QSqlRelationalTableModel.clear (self)
```

从重新实现[QSqlQueryModel.clear](qsqlquerymodel.html#clear)（ ） 。

```
QVariant QSqlRelationalTableModel.data (self, QModelIndex index, int role = Qt.DisplayRole)
```

从重新实现[QAbstractItemModel.data](qabstractitemmodel.html#data)（ ） 。

**See also** [setData](qsqlrelationaltablemodel.html#setData)（ ） 。

```
bool QSqlRelationalTableModel.insertRowIntoTable (self, QSqlRecord values)
```

从重新实现[QSqlTableModel.insertRowIntoTable](qsqltablemodel.html#insertRowIntoTable)（ ） 。

```
QString QSqlRelationalTableModel.orderByClause (self)
```

从重新实现[QSqlTableModel.orderByClause](qsqltablemodel.html#orderByClause)（ ） 。

```
QSqlRelation QSqlRelationalTableModel.relation (self, int column)
```

[

返回列的关系_column_或无效的关系，如果没有关系设定。

](qsqlrelation.html)

[**See also**](qsqlrelation.html) [setRelation](qsqlrelationaltablemodel.html#setRelation)（）和[QSqlRelation.isValid](qsqlrelation.html#isValid)（ ） 。

```
QSqlTableModel QSqlRelationalTableModel.relationModel (self, int column)
```

[](qsqltablemodel.html)

[返回](qsqltablemodel.html)[QSqlTableModel](qsqltablemodel.html)对象，用于访问表的量_column_是外键，或者0，如果没有为给定的没有关系_column_。

返回的对象是由资[QSqlRelationalTableModel](qsqlrelationaltablemodel.html)。

**See also** [setRelation](qsqlrelationaltablemodel.html#setRelation)（）和[relation](qsqlrelationaltablemodel.html#relation)（ ） 。

```
bool QSqlRelationalTableModel.removeColumns (self, int column, int count, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.removeColumns](qabstractitemmodel.html#removeColumns)（ ） 。

```
QSqlRelationalTableModel.revertRow (self, int row)
```

从重新实现[QSqlTableModel.revertRow](qsqltablemodel.html#revertRow)（ ） 。

```
bool QSqlRelationalTableModel.select (self)
```

从重新实现[QSqlTableModel.select](qsqltablemodel.html#select)（ ） 。

```
QString QSqlRelationalTableModel.selectStatement (self)
```

从重新实现[QSqlTableModel.selectStatement](qsqltablemodel.html#selectStatement)（ ） 。

```
bool QSqlRelationalTableModel.setData (self, QModelIndex index, QVariant value, int role = Qt.EditRole)
```

从重新实现[QAbstractItemModel.setData](qabstractitemmodel.html#setData)（ ） 。

设置数据的_role_在用指定的项_index_到_value_给出。取决于编辑策略，则该值可能被应用到数据库一次，或者它可以在模型中被缓存。

返回True如果该值可以设置，或虚假的错误（例如，如果_index_是出界） 。

对于关系栏目，_value_必须是索引，而不是显示值。该指数还必须存在于被引用表，否则返回False 。

**See also** [editStrategy](qsqltablemodel.html#editStrategy)（ ）[data](qsqlrelationaltablemodel.html#data)（ ）[submit](qsqltablemodel.html#submit)（）和[revertRow](qsqlrelationaltablemodel.html#revertRow)（ ） 。

```
QSqlRelationalTableModel.setJoinMode (self, JoinMode joinMode)
```

设置SQL加盟模式由给定的值_joinMode_要显示或隐藏与NULL外键的行。

In [InnerJoin](qsqlrelationaltablemodel.html#JoinMode-enum)模式（默认）这些行不会被显示;使用[LeftJoin](qsqlrelationaltablemodel.html#JoinMode-enum)模式下，如果你想向他们展示。

此功能被引入Qt的4.8 。

**See also** [QSqlRelationalTableModel.JoinMode](qsqlrelationaltablemodel.html#JoinMode-enum)。

```
QSqlRelationalTableModel.setRelation (self, int column, QSqlRelation relation)
```

让指定的_column_可以通过指定的外国指数_relation_。

例如：

```
     model->setTable("employee");

     model->setRelation(2, [QSqlRelation](qsqlrelation.html)("city", "id", "name"));

```

该setRelation （ ）调用指定表2列`employee`是，与字段映射外键`id`表`city`，而认为应该提出的`city`的`name`字段给用户。

注：表中的主键可能不包含关系到另一个表。

**See also** [relation](qsqlrelationaltablemodel.html#relation)（ ） 。

```
QSqlRelationalTableModel.setTable (self, QString tableName)
```

从重新实现[QSqlTableModel.setTable](qsqltablemodel.html#setTable)（ ） 。

```
bool QSqlRelationalTableModel.updateRowInTable (self, int row, QSqlRecord values)
```

从重新实现[QSqlTableModel.updateRowInTable](qsqltablemodel.html#updateRowInTable)（ ） 。