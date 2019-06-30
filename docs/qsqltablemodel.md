# QSqlTableModel Class Reference

## [[QtSql](index.htm) module]

在与QSqlTableModel类提供了一个单一的数据库表中的可编辑的数据模型。[More...](#details)

继承[QSqlQueryModel](qsqlquerymodel.html)。

通过继承[QSqlRelationalTableModel](qsqlrelationaltablemodel.html)。

### Types

*   `enum EditStrategy { OnFieldChange, OnRowChange, OnManualSubmit }`

### Methods

*   `__init__ (self, QObject parent = None, QSqlDatabase db = QSqlDatabase())`
*   `clear (self)`
*   `QVariant data (self, QModelIndex index, int role = Qt.DisplayRole)`
*   `QSqlDatabase database (self)`
*   `bool deleteRowFromTable (self, int row)`
*   `EditStrategy editStrategy (self)`
*   `int fieldIndex (self, QString fieldName)`
*   `QString filter (self)`
*   `Qt.ItemFlags flags (self, QModelIndex index)`
*   `QVariant headerData (self, int section, Qt.Orientation orientation, int role = Qt.DisplayRole)`
*   `QModelIndex indexInQuery (self, QModelIndex item)`
*   `bool insertRecord (self, int row, QSqlRecord record)`
*   `bool insertRowIntoTable (self, QSqlRecord values)`
*   `bool insertRows (self, int row, int count, QModelIndex parent = QModelIndex())`
*   `bool isDirty (self, QModelIndex index)`
*   `QString orderByClause (self)`
*   `QSqlIndex primaryKey (self)`
*   `bool removeColumns (self, int column, int count, QModelIndex parent = QModelIndex())`
*   `bool removeRows (self, int row, int count, QModelIndex parent = QModelIndex())`
*   `revert (self)`
*   `revertAll (self)`
*   `revertRow (self, int row)`
*   `int rowCount (self, QModelIndex parent = QModelIndex())`
*   `bool select (self)`
*   `QString selectStatement (self)`
*   `bool setData (self, QModelIndex index, QVariant value, int role = Qt.EditRole)`
*   `setEditStrategy (self, EditStrategy strategy)`
*   `setFilter (self, QString filter)`
*   `setPrimaryKey (self, QSqlIndex key)`
*   `setQuery (self, QSqlQuery query)`
*   `bool setRecord (self, int row, QSqlRecord record)`
*   `setSort (self, int column, Qt.SortOrder order)`
*   `setTable (self, QString tableName)`
*   `sort (self, int column, Qt.SortOrder order)`
*   `bool submit (self)`
*   `bool submitAll (self)`
*   `QString tableName (self)`
*   `bool updateRowInTable (self, int row, QSqlRecord values)`

### Qt Signals

*   `void beforeDelete (int)`
*   `void beforeInsert (QSqlRecord&)`
*   `void beforeUpdate (int,QSqlRecord&)`
*   `void primeInsert (int,QSqlRecord&)`

* * *

## Detailed Description

在与QSqlTableModel类提供了一个单一的数据库表中的可编辑的数据模型。

QSqlTableModel的功能是从一个单一的表中读取和写入数据库记录的高层次的接口。它是建立在较低级别的顶[QSqlQuery](qsqlquery.html)并且可以用来提供数据可以看到类如[QTableView](qtableview.html)。例如：

```
     QSqlTableModel *model = new QSqlTableModel(parentObject, database);
     model->setTable("employee");
     model->setEditStrategy(QSqlTableModel.OnManualSubmit);
     model->select();
     model->setHeaderData(0, [Qt](qt.html).Horizontal, tr("Name"));
     model->setHeaderData(1, [Qt](qt.html).Horizontal, tr("Salary"));

     [QTableView](qtableview.html) *view = new [QTableView](qtableview.html);
     view->setModel(model);
     view->hideColumn(0); // don't show the ID
     view->show();

```

我们设置SQL表的名称和编辑策略，然后我们设置视图中的标题显示的标籤。编辑策略决定时由用户在视图中所做的更改实际应用到数据库。可能的值是[OnFieldChange](qsqltablemodel.html#EditStrategy-enum)，[OnRowChange](qsqltablemodel.html#EditStrategy-enum)和[OnManualSubmit](qsqltablemodel.html#EditStrategy-enum)。

QSqlTableModel的功能也可以用来访问数据库编程，不绑定到一个视图：

```
     [QSqlQueryModel](qsqlquerymodel.html) model;
     model.setQuery("SELECT * FROM employee");
     int salary = model.record(4).value("salary").toInt();

```

上面的代码片段中提取`salary`从查询的结果集记录4场`SELECT * from employee`。

它可以用来设置过滤器[setFilter](qsqltablemodel.html#setFilter)（ ），或使用修改排序顺序[setSort](qsqltablemodel.html#setSort)（ ） 。最后，你必须调用[select](qsqltablemodel.html#select)（ ）来填充模型数据。

该[sql/tablemodel](index.htm)示例说明了如何使用与QSqlTableModel作为数据源的[QTableView](qtableview.html)。

QSqlTableModel为外键没有直接的支持。使用[QSqlRelationalTableModel](qsqlrelationaltablemodel.html)和[QSqlRelationalDelegate](qsqlrelationaldelegate.html)如果你想解决的外键。

* * *

## Type Documentation

```
QSqlTableModel.EditStrategy
```

该枚举类型描述编辑数据库中的值时，选择哪个策略。

| Constant | Value | Description |
| --- | --- | --- |
| `QSqlTableModel.OnFieldChange` | `0` | 所有更改模型将被立即应用到数据库。 |
| `QSqlTableModel.OnRowChange` | `1` | 当用户选择不同的行改变为一行将被应用。 |
| `QSqlTableModel.OnManualSubmit` | `2` | 所有更改都将被缓存在模型中，直至[submitAll](qsqltablemodel.html#submitAll)（）或[revertAll](qsqltablemodel.html#revertAll)（）被调用。 |

注意：为了防止插入只有部分初始化行插入到数据库中，`OnFieldChange`会像`OnRowChange`对于新插入的行。

**See also** [setEditStrategy](qsqltablemodel.html#setEditStrategy)（ ） 。

* * *

## Method Documentation

```
QSqlTableModel.__init__ (self, QObject parent = None, QSqlDatabase db = QSqlDatabase())
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建一个空的[QSqlTableModel](qsqltablemodel.html)并设置父_parent_与数据库连接_db_。如果_db_是无效的，默认的数据库连接将被使用。

默认的编辑策略[OnRowChange](qsqltablemodel.html#EditStrategy-enum)。

```
QSqlTableModel.clear (self)
```

从重新实现[QSqlQueryModel.clear](qsqlquerymodel.html#clear)（ ） 。

```
QVariant QSqlTableModel.data (self, QModelIndex index, int role = Qt.DisplayRole)
```

从重新实现[QAbstractItemModel.data](qabstractitemmodel.html#data)（ ） 。

**See also** [setData](qsqltablemodel.html#setData)（ ） 。

```
QSqlDatabase QSqlTableModel.database (self)
```

[](qsqldatabase.html)

[返回一个指向所使用的](qsqldatabase.html)[QSqlDatabase](qsqldatabase.html)或者0，如果没有数据库设置。

```
bool QSqlTableModel.deleteRowFromTable (self, int row)
```

删除给定的_row_从当前活动的数据库表。

这是一种直接操作的数据库上，不应该被直接调用低级别的方法。使用[removeRow](qabstractitemmodel.html#removeRow)（）或[removeRows](qsqltablemodel.html#removeRows)（）来删除值。该模型将取决于它的编辑策略，决定何时修改数据库。

返回True如果该行被删除，否则返回False 。

**See also** [removeRow](qabstractitemmodel.html#removeRow)（）和[removeRows](qsqltablemodel.html#removeRows)（ ） 。

```
EditStrategy QSqlTableModel.editStrategy (self)
```

[

返回当前的编辑策略。

](qsqltablemodel.html#EditStrategy-enum)

[**See also**](qsqltablemodel.html#EditStrategy-enum) [setEditStrategy](qsqltablemodel.html#setEditStrategy)（ ） 。

```
int QSqlTableModel.fieldIndex (self, QString fieldName)
```

返回字段的索引_fieldName_，或-1，如果没有相应的字段存在于模型中。

```
QString QSqlTableModel.filter (self)
```

返回当前设置的过滤器。

**See also** [setFilter](qsqltablemodel.html#setFilter)（）和[select](qsqltablemodel.html#select)（ ） 。

```
Qt.ItemFlags QSqlTableModel.flags (self, QModelIndex index)
```

[](index.htm)

[从重新实现](index.htm)[QAbstractItemModel.flags](qabstractitemmodel.html#flags)（ ） 。

```
QVariant QSqlTableModel.headerData (self, int section, Qt.Orientation orientation, int role = Qt.DisplayRole)
```

从重新实现[QAbstractItemModel.headerData](qabstractitemmodel.html#headerData)（ ） 。

```
QModelIndex QSqlTableModel.indexInQuery (self, QModelIndex item)
```

[

返回在给定的数据库中的结果集的值的索引_item_在模型中。

返回值是相同的_item_如果已经插入任何行或列，删除或移动了。

返回一个无效的模型索引，如果_item_超出范围或_item_不指向结果集中的值。

](qmodelindex.html)

[**See also**](qmodelindex.html) [QSqlQueryModel.indexInQuery](qsqlquerymodel.html#indexInQuery)（ ） 。

```
bool QSqlTableModel.insertRecord (self, int row, QSqlRecord record)
```

插入_record_后_row_。如果_row_为负，该记录将被追加到末尾。电话[insertRows](qsqltablemodel.html#insertRows)（）和[setRecord](qsqltablemodel.html#setRecord)（内部） 。

返回True如果可以插入该行，否则为False。

**See also** [insertRows](qsqltablemodel.html#insertRows)（）和[removeRows](qsqltablemodel.html#removeRows)（ ） 。

```
bool QSqlTableModel.insertRowIntoTable (self, QSqlRecord values)
```

插入的值_values_到当前活动的数据库表。

这是一种直接操作的数据库上，不应该被直接调用低级别的方法。使用[insertRow](qabstractitemmodel.html#insertRow)（）和[setData](qsqltablemodel.html#setData)（）来插入值。该模型将取决于它的编辑策略，决定何时修改数据库。

返回True如果该值可以被插入，否则为False。错误信息可以检索与[lastError](qsqlquerymodel.html#lastError)（ ） 。

**See also** [lastError](qsqlquerymodel.html#lastError)（ ）[insertRow](qabstractitemmodel.html#insertRow)（）和[insertRows](qsqltablemodel.html#insertRows)（ ） 。

```
bool QSqlTableModel.insertRows (self, int row, int count, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.insertRows](qabstractitemmodel.html#insertRows)（ ） 。

Inserts _count_在位置空行_row_。需要注意的是_parent_必须是无效的，因为这种模式不支持父子关系。

仅1行的时间可以在使用被插入的[OnFieldChange](qsqltablemodel.html#EditStrategy-enum) or [OnRowChange](qsqltablemodel.html#EditStrategy-enum)更新策略。

该[primeInsert](qsqltablemodel.html#primeInsert)（）信号将被发射的每一个新行。连接到它，如果你想用默认值初始化的新行。

返回False如果参数超出范围，否则返回True 。

**See also** [primeInsert](qsqltablemodel.html#primeInsert)（）和[insertRecord](qsqltablemodel.html#insertRecord)（ ） 。

```
bool QSqlTableModel.isDirty (self, QModelIndex index)
```

返回True如果该索引处的值_index_脏，否则为False 。脏值是进行了修改，在模型中，但尚未写入到数据库中的值。

If _index_无效或指向一个不存在的列，则返回False。

```
QString QSqlTableModel.orderByClause (self)
```

返回一个SQL`ORDER BY`基于条当前设置的排序顺序。

**See also** [setSort](qsqltablemodel.html#setSort)（）和[selectStatement](qsqltablemodel.html#selectStatement)（ ） 。

```
QSqlIndex QSqlTableModel.primaryKey (self)
```

[](qsqlindex.html)

[返回主键为当前表，或空](qsqlindex.html)[QSqlIndex](qsqlindex.html)如果表没有设置或没有主键。

**See also** [setTable](qsqltablemodel.html#setTable)（ ）[setPrimaryKey](qsqltablemodel.html#setPrimaryKey)（）和[QSqlDatabase.primaryIndex](qsqldatabase.html#primaryIndex)（ ） 。

```
bool QSqlTableModel.removeColumns (self, int column, int count, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.removeColumns](qabstractitemmodel.html#removeColumns)（ ） 。

移除_count_从列_parent_模型，从索引_column_。

如果返回的列被成功删除，否则返回False 。

**See also** [removeRows](qsqltablemodel.html#removeRows)（ ） 。

```
bool QSqlTableModel.removeRows (self, int row, int count, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.removeRows](qabstractitemmodel.html#removeRows)（ ） 。

移除_count_行开始_row_。由于此型号不支持的层次结构，_parent_必须是一个无效的模型索引。

放出[beforeDelete](qsqltablemodel.html#beforeDelete)（一排之前）信号被删除。当编辑策略[OnManualSubmit](qsqltablemodel.html#EditStrategy-enum)信号发射被延迟，直到[submitAll](qsqltablemodel.html#submitAll)（）被调用。

返回True如果所有行会被移除，否则返回False 。详细的错误信息可以使用检索[lastError](qsqlquerymodel.html#lastError)（ ） 。

**See also** [removeColumns](qsqltablemodel.html#removeColumns)（）和[insertRows](qsqltablemodel.html#insertRows)（ ） 。

```
QSqlTableModel.revert (self)
```

这种方法也是一个Qt槽与C + +的签名`void revert()`。

从重新实现[QAbstractItemModel.revert](qabstractitemmodel.html#revert)（ ） 。

这个重新实现槽是由所谓的项目代表，当用户取消了编辑当前行。

恢复的变化，如果模型的策略设置为[OnRowChange](qsqltablemodel.html#EditStrategy-enum)。什么都不做的其他的编辑策略。

使用[revertAll](qsqltablemodel.html#revertAll)（）恢复为所有挂起的更改[OnManualSubmit](qsqltablemodel.html#EditStrategy-enum)策略或[revertRow](qsqltablemodel.html#revertRow)（）来恢复一个特定的行。

**See also** [submit](qsqltablemodel.html#submit)（ ）[submitAll](qsqltablemodel.html#submitAll)（ ）[revertRow](qsqltablemodel.html#revertRow)（）和[revertAll](qsqltablemodel.html#revertAll)（ ） 。

```
QSqlTableModel.revertAll (self)
```

这种方法也是一个Qt槽与C + +的签名`void revertAll()`。

恢复所有挂起的更改。

**See also** [revert](qsqltablemodel.html#revert)（ ）[revertRow](qsqltablemodel.html#revertRow)（）和[submitAll](qsqltablemodel.html#submitAll)（ ） 。

```
QSqlTableModel.revertRow (self, int row)
```

恢复为指定的所有变化_row_。

**See also** [revert](qsqltablemodel.html#revert)（ ）[revertAll](qsqltablemodel.html#revertAll)（ ）[submit](qsqltablemodel.html#submit)（）和[submitAll](qsqltablemodel.html#submitAll)（ ） 。

```
int QSqlTableModel.rowCount (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.rowCount](qabstractitemmodel.html#rowCount)（ ） 。

```
bool QSqlTableModel.select (self)
```

填充模型从表中的数据是通过设置[setTable](qsqltablemodel.html#setTable)（ ） ，使用指定的过滤和排序条件，如果成功返回True，否则返回False 。

**Note:**调用select （ ）将返回任何未提交的更改并删除任何插入的列。

**See also** [setTable](qsqltablemodel.html#setTable)（ ）[setFilter](qsqltablemodel.html#setFilter)（）和[selectStatement](qsqltablemodel.html#selectStatement)（ ） 。

```
QString QSqlTableModel.selectStatement (self)
```

返回SQL`SELECT`语句内部使用的填充模式。该表包括过滤器和`ORDER BY`子句。

**See also** [filter](qsqltablemodel.html#filter)（）和[orderByClause](qsqltablemodel.html#orderByClause)（ ） 。

```
bool QSqlTableModel.setData (self, QModelIndex index, QVariant value, int role = Qt.EditRole)
```

从重新实现[QAbstractItemModel.setData](qabstractitemmodel.html#setData)（ ） 。

设置数据的项_index_为角色_role_至_value_。取决于编辑策略，则该值可能被应用到数据库一次或缓存在模型中。

返回True如果该值可以设置或虚假的错误，例如，如果_index_是出界。

**See also** [editStrategy](qsqltablemodel.html#editStrategy)（ ）[data](qsqltablemodel.html#data)（ ）[submit](qsqltablemodel.html#submit)（ ）[submitAll](qsqltablemodel.html#submitAll)（）和[revertRow](qsqltablemodel.html#revertRow)（ ） 。

```
QSqlTableModel.setEditStrategy (self, EditStrategy strategy)
```

设置的策略对数据库中的值编辑_strategy_。

这将恢复所有挂起的更改。

**See also** [editStrategy](qsqltablemodel.html#editStrategy)（）和[revertAll](qsqltablemodel.html#revertAll)（ ） 。

```
QSqlTableModel.setFilter (self, QString filter)
```

设置当前过滤器_filter_。

该滤波器是一个SQL`WHERE`没有关键字条款`WHERE`（例如，`name='Josephine')`。

如果已填充模型与数据库中的数据，该机型配备了新的过滤器重新选择它。否则，过滤器会在下一次应用[select](qsqltablemodel.html#select)（）被调用。

**See also** [filter](qsqltablemodel.html#filter)（ ）[select](qsqltablemodel.html#select)（ ）[selectStatement](qsqltablemodel.html#selectStatement)（）和[orderByClause](qsqltablemodel.html#orderByClause)（ ） 。

```
QSqlTableModel.setPrimaryKey (self, QSqlIndex key)
```

受保护的方法，让子类来设置主键_key_。

通常情况下，只要您拨打的主索引会自动设置[setTable](qsqltablemodel.html#setTable)（ ） 。

**See also** [primaryKey](qsqltablemodel.html#primaryKey)（）和[QSqlDatabase.primaryIndex](qsqldatabase.html#primaryIndex)（ ） 。

```
QSqlTableModel.setQuery (self, QSqlQuery query)
```

这个函数简单地调用QSqlQueryModel.setQuery （_query_） 。在你通常应该不叫[QSqlTableModel](qsqltablemodel.html)。相反，使用[setTable](qsqltablemodel.html#setTable)（ ）[setSort](qsqltablemodel.html#setSort)（ ）[setFilter](qsqltablemodel.html#setFilter)（ ）等，来设置该查询。

**See also** [selectStatement](qsqltablemodel.html#selectStatement)（ ） 。

```
bool QSqlTableModel.setRecord (self, int row, QSqlRecord record)
```

在指定的设定值_row_到的值_record_。返回True如果所有的值可以被置位，否则返回False 。

**See also** [record](qsqlquerymodel.html#record)（ ） 。

```
QSqlTableModel.setSort (self, int column, Qt.SortOrder order)
```

设置排序顺序_column_至_order_。这不影响当前数据，使用新的排序顺序，调用刷新数据[select](qsqltablemodel.html#select)（ ） 。

**See also** [sort](qsqltablemodel.html#sort)（ ）[select](qsqltablemodel.html#select)（）和[orderByClause](qsqltablemodel.html#orderByClause)（ ） 。

```
QSqlTableModel.setTable (self, QString tableName)
```

对这样的模式操作到数据库表_tableName_。不从表中选择数据，但其获取字段信息。

要填充模型与表的数据，调用[select](qsqltablemodel.html#select)（ ） 。

错误信息可以检索与[lastError](qsqlquerymodel.html#lastError)（ ） 。

**See also** [select](qsqltablemodel.html#select)（ ）[setFilter](qsqltablemodel.html#setFilter)（）和[lastError](qsqlquerymodel.html#lastError)（ ） 。

```
QSqlTableModel.sort (self, int column, Qt.SortOrder order)
```

从重新实现[QAbstractItemModel.sort](qabstractitemmodel.html#sort)（ ） 。

通过对数据进行排序_column_与排序顺序_order_。这将立即选择数据，使用[setSort](qsqltablemodel.html#setSort)（ ）来设置排序顺序不填充模型数据。

**See also** [setSort](qsqltablemodel.html#setSort)（ ）[select](qsqltablemodel.html#select)（）和[orderByClause](qsqltablemodel.html#orderByClause)（ ） 。

```
bool QSqlTableModel.submit (self)
```

这种方法也是一个Qt槽与C + +的签名`bool submit()`。

从重新实现[QAbstractItemModel.submit](qabstractitemmodel.html#submit)（ ） 。

这个重新实现槽是由所谓的项目代表，当用户停止编辑当前行。

提交当前编辑的行，如果该模型的策略设置为[OnRowChange](qsqltablemodel.html#EditStrategy-enum) or [OnFieldChange](qsqltablemodel.html#EditStrategy-enum)。什么都不做的[OnManualSubmit](qsqltablemodel.html#EditStrategy-enum)战略。

使用[submitAll](qsqltablemodel.html#submitAll)（ ）提交的所有挂起的更改[OnManualSubmit](qsqltablemodel.html#EditStrategy-enum)战略。

成功时返回TRUE ，否则返回False 。使用[lastError](qsqlquerymodel.html#lastError)（ ）来查询详细的错误信息。

成功模型将被重新填充。任何提出它的意见将失去他们的选择。

**See also** [revert](qsqltablemodel.html#revert)（ ）[revertRow](qsqltablemodel.html#revertRow)（ ）[submitAll](qsqltablemodel.html#submitAll)（ ）[revertAll](qsqltablemodel.html#revertAll)（）和[lastError](qsqlquerymodel.html#lastError)（ ） 。

```
bool QSqlTableModel.submitAll (self)
```

这种方法也是一个Qt槽与C + +的签名`bool submitAll()`。

提交所有挂起的更改，并成功返回True 。返回False的错误，详细的错误信息，可以得到[lastError](qsqlquerymodel.html#lastError)（ ） 。

成功模型将被重新填充。任何提出它的意见将失去他们的选择。

注意：在[OnManualSubmit](qsqltablemodel.html#EditStrategy-enum)模式，已经提交的变更将不会从什么时候submitAll （）失败的缓存中清除。这允许事务被回滚，并再次重新提交，而不会丢失数据。

**See also** [revertAll](qsqltablemodel.html#revertAll)（）和[lastError](qsqlquerymodel.html#lastError)（ ） 。

```
QString QSqlTableModel.tableName (self)
```

返回当前选定的表的名称。

```
bool QSqlTableModel.updateRowInTable (self, int row, QSqlRecord values)
```

更新给定的_row_在与指定当前活动的数据库表_values_。成功返回True ，否则返回False 。

这是一种直接操作的数据库上，不应该被直接调用低级别的方法。使用[setData](qsqltablemodel.html#setData)（）来更新值。该模型将取决于它的编辑策略，决定何时修改数据库。

请注意，只有具有所生成的标志设定值被更新。所生成的标志可与设置[QSqlRecord.setGenerated](qsqlrecord.html#setGenerated)（ ）中，用测试[QSqlRecord.isGenerated](qsqlrecord.html#isGenerated)（ ） 。

**See also** [QSqlRecord.isGenerated](qsqlrecord.html#isGenerated)（）和[setData](qsqltablemodel.html#setData)（ ） 。

* * *

## Qt Signal Documentation

```
void beforeDelete (int)
```

这是该信号的默认超载。

这个信号是由发射[deleteRowFromTable](qsqltablemodel.html#deleteRowFromTable)（ ）之前，_row_从当前活动的数据库表中删除。

```
void beforeInsert (QSqlRecord&)
```

这是该信号的默认超载。

这个信号是由发射[insertRowIntoTable](qsqltablemodel.html#insertRowIntoTable)（ ）一个新行插入到当前活动的数据库表之前。这是将要被插入的值被存储在_record_并且可以进行修改将被插入之前，他们。

```
void beforeUpdate (int,QSqlRecord&)
```

这是该信号的默认超载。

这个信号是由发射[updateRowInTable](qsqltablemodel.html#updateRowInTable)（ ）之前，_row_在当前活动的数据库表从值更新_record_。

请注意，只有被标记为生成的值将被更新。所生成的标记可与设置[QSqlRecord.setGenerated](qsqlrecord.html#setGenerated)（） ，并检查与[QSqlRecord.isGenerated](qsqlrecord.html#isGenerated)（ ） 。

**See also** [QSqlRecord.isGenerated](qsqlrecord.html#isGenerated)（ ） 。

```
void primeInsert (int,QSqlRecord&)
```

这是该信号的默认超载。

这个信号是由发射[insertRows](qsqltablemodel.html#insertRows)（ ）中，当在给定的开始插入_row_当前活动的数据库表。该_record_参数可以被写入（因为它是一个参考），例如，以使用默认值的字段。