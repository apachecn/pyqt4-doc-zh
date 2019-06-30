# QSqlQueryModel Class Reference

## [[QtSql](index.htm) module]

该QSqlQueryModel类为SQL结果集的只读数据模型。[More...](#details)

继承[QAbstractTableModel](qabstracttablemodel.html)。

通过继承[QSqlTableModel](qsqltablemodel.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `bool canFetchMore (self, QModelIndex parent = QModelIndex())`
*   `clear (self)`
*   `int columnCount (self, QModelIndex parent = QModelIndex())`
*   `QVariant data (self, QModelIndex item, int role = Qt.DisplayRole)`
*   `fetchMore (self, QModelIndex parent = QModelIndex())`
*   `QVariant headerData (self, int section, Qt.Orientation orientation, int role = Qt.DisplayRole)`
*   `QModelIndex indexInQuery (self, QModelIndex item)`
*   `bool insertColumns (self, int column, int count, QModelIndex parent = QModelIndex())`
*   `QSqlError lastError (self)`
*   `QSqlQuery query (self)`
*   `queryChange (self)`
*   `QSqlRecord record (self, int row)`
*   `QSqlRecord record (self)`
*   `bool removeColumns (self, int column, int count, QModelIndex parent = QModelIndex())`
*   `int rowCount (self, QModelIndex parent = QModelIndex())`
*   `bool setHeaderData (self, int section, Qt.Orientation orientation, QVariant value, int role = Qt.EditRole)`
*   `setLastError (self, QSqlError error)`
*   `setQuery (self, QSqlQuery query)`
*   `setQuery (self, QString query, QSqlDatabase db = QSqlDatabase())`

* * *

## Detailed Description

该QSqlQueryModel类为SQL结果集的只读数据模型。

QSqlQueryModel是用于执行SQL语句并遍历结果集一个高层次的接口。它是建立在较低级别的顶[QSqlQuery](qsqlquery.html)并且可以用来提供数据可以看到类如[QTableView](qtableview.html)。例如：

```
     QSqlQueryModel *model = new QSqlQueryModel;
     model->setQuery("SELECT name, salary FROM employee");
     model->setHeaderData(0, [Qt](qt.html).Horizontal, tr("Name"));
     model->setHeaderData(1, [Qt](qt.html).Horizontal, tr("Salary"));

     [QTableView](qtableview.html) *view = new [QTableView](qtableview.html);
     view->setModel(model);
     view->show();

```

我们建立模型的查询，然后我们设置视图中的标题显示的标籤。

QSqlQueryModel也可以用来访问数据库编程，不绑定到一个视图：

```
     QSqlQueryModel model;
     model.setQuery("SELECT * FROM employee");
     int salary = model.record(4).value("salary").toInt();

```

上面的代码片段中提取`salary`从查询的结果集记录4场`SELECT * from employee`。假设`salary`是第2列，我们可以重写最后一行，如下所示：

```
     int salary = model.data(model.index(4, 2)).toInt();

```

该模型是只读的默认。为了使读写，你必须继承它，并重新实现[setData](qabstractitemmodel.html#setData)（）和[flags](qabstractitemmodel.html#flags)（ ） 。另一个选项是使用[QSqlTableModel](qsqltablemodel.html)，它提供了基于单个数据库表中的读 - 写的模式。

该[sql/querymodel](index.htm)示例说明了如何使用QSqlQueryModel以显示查询的结果。它也显示了如何继承QSqlQueryModel显示给用户之前自定义数据的内容，以及如何创建基于QSqlQueryModel一个读写模式。

如果数据库没有返回在查询中选择的行数，该模型将逐步获取行。看[fetchMore](qsqlquerymodel.html#fetchMore)（ ）获取更多信息。

* * *

## Method Documentation

```
QSqlQueryModel.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建一个空的[QSqlQueryModel](qsqlquerymodel.html)用给定的_parent_。

```
bool QSqlQueryModel.canFetchMore (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.canFetchMore](qabstractitemmodel.html#canFetchMore)（ ） 。

返回True如果有可能从数据库中读取更多的行。这只会影响数据库不报到查询的尺寸（见[QSqlDriver.hasFeature](qsqldriver.html#hasFeature)（））。

_parent_应始终为无效[QModelIndex](qmodelindex.html)。

这个函数是Qt 4.1中引入。

**See also** [fetchMore](qsqlquerymodel.html#fetchMore)（ ） 。

```
QSqlQueryModel.clear (self)
```

清除模型，并释放任何收购资源。

```
int QSqlQueryModel.columnCount (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.columnCount](qabstractitemmodel.html#columnCount)（ ） 。

```
QVariant QSqlQueryModel.data (self, QModelIndex item, int role = Qt.DisplayRole)
```

从重新实现[QAbstractItemModel.data](qabstractitemmodel.html#data)（ ） 。

返回值指定_item_和_role_。

If _item_超出范围，或者如果发生错误，无效的[QVariant](qvariant.html)返回。

**See also** [lastError](qsqlquerymodel.html#lastError)（ ） 。

```
QSqlQueryModel.fetchMore (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.fetchMore](qabstractitemmodel.html#fetchMore)（ ） 。

获取从数据库中多个行。这只会影响数据库不报到查询的尺寸（见[QSqlDriver.hasFeature](qsqldriver.html#hasFeature)（））。

要强制整个结果集的抓取，你可以使用以下命令：

```
 while (myModel->canFetchMore())
     myModel->fetchMore();

```

_parent_应始终为无效[QModelIndex](qmodelindex.html)。

这个函数是Qt 4.1中引入。

**See also** [canFetchMore](qsqlquerymodel.html#canFetchMore)（ ） 。

```
QVariant QSqlQueryModel.headerData (self, int section, Qt.Orientation orientation, int role = Qt.DisplayRole)
```

从重新实现[QAbstractItemModel.headerData](qabstractitemmodel.html#headerData)（ ） 。

返回头数据为给定的_role_在_section_用指定的标头_orientation_。

**See also** [setHeaderData](qsqlquerymodel.html#setHeaderData)（ ） 。

```
QModelIndex QSqlQueryModel.indexInQuery (self, QModelIndex item)
```

[

返回在给定的数据库中的结果集的值的索引_item_在模型中。

返回值是相同的_item_如果已经插入任何行或列，删除或移动了。

返回一个无效的模型索引，如果_item_超出范围或_item_不指向结果集中的值。

](qmodelindex.html)

[**See also**](qmodelindex.html) [QSqlTableModel.indexInQuery](qsqltablemodel.html#indexInQuery)（ ）[insertColumns](qsqlquerymodel.html#insertColumns)（）和[removeColumns](qsqlquerymodel.html#removeColumns)（ ） 。

```
bool QSqlQueryModel.insertColumns (self, int column, int count, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.insertColumns](qabstractitemmodel.html#insertColumns)（ ） 。

Inserts _count_列到模型的位置_column_。该_parent_参数必须始终是一个无效的[QModelIndex](qmodelindex.html)，因为该模型不支持父子关系。

返回True如果_column_是在一定范围内，否则返回False 。

默认情况下，插入的列是空的。为了填补他们的数据，重新实现[data](qsqlquerymodel.html#data)（ ）并单独处理任何插入的列：

```
 [QVariant](qvariant.html) MyModel.data(const [QModelIndex](qmodelindex.html) &item, int role) const
 {
     if (item.column() == m_specialColumnNo) {
         // handle column separately
     }
     return [QSqlQueryModel](qsqlquerymodel.html).data(item, role);
 }

```

**See also** [removeColumns](qsqlquerymodel.html#removeColumns)（ ） 。

```
QSqlError QSqlQueryModel.lastError (self)
```

[

返回有关数据库上发生的最后一个错误信息。

](qsqlerror.html)

[**See also**](qsqlerror.html) [setLastError](qsqlquerymodel.html#setLastError)（）和[query](qsqlquerymodel.html#query)（ ） 。

```
QSqlQuery QSqlQueryModel.query (self)
```

[](qsqlquery.html)

[返回](qsqlquery.html)[QSqlQuery](qsqlquery.html)与此模型相关。

**See also** [setQuery](qsqlquerymodel.html#setQuery)（ ） 。

```
QSqlQueryModel.queryChange (self)
```

这个虚函数被调用时查询改变。默认实现不执行任何操作。

[query](qsqlquerymodel.html#query)（ ）返回新的查询。

**See also** [query](qsqlquerymodel.html#query)（）和[setQuery](qsqlquerymodel.html#setQuery)（ ） 。

```
QSqlRecord QSqlQueryModel.record (self, int row)
```

[

返回有关当前查询的字段包含记录信息。如果_row_是一个有效的行的索引，该记录将被填入该行的值。

如果模型没有被初始化，一个空的记录将被退回。

](qsqlrecord.html)

[**See also**](qsqlrecord.html) [QSqlRecord.isEmpty](qsqlrecord.html#isEmpty)（ ） 。

```
QSqlRecord QSqlQueryModel.record (self)
```

[

这是一个重载函数。

返回有关当前查询的字段为空的记录包含的信息。

如果模型没有被初始化，一个空的记录将被退回。

](qsqlrecord.html)

[**See also**](qsqlrecord.html) [QSqlRecord.isEmpty](qsqlrecord.html#isEmpty)（ ） 。

```
bool QSqlQueryModel.removeColumns (self, int column, int count, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.removeColumns](qabstractitemmodel.html#removeColumns)（ ） 。

移除_count_从模型中的列从位置开始_column_。该_parent_参数必须始终是一个无效的[QModelIndex](qmodelindex.html)，因为该模型不支持父子关系。

删除列有效地隐藏它们。它不影响相关[QSqlQuery](qsqlquery.html)。

返回True如果被删除的列，否则返回False 。

```
int QSqlQueryModel.rowCount (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.rowCount](qabstractitemmodel.html#rowCount)（ ） 。

如果数据库支持返回查询的尺寸（见[QSqlDriver.hasFeature](qsqldriver.html#hasFeature)（））时，返回的行的当前查询的数量。否则，将返回客户端上当前缓存的行数。

_parent_应始终为无效[QModelIndex](qmodelindex.html)。

这个函数是Qt 4.1中引入。

**See also** [canFetchMore](qsqlquerymodel.html#canFetchMore)（）和[QSqlDriver.hasFeature](qsqldriver.html#hasFeature)（ ） 。

```
bool QSqlQueryModel.setHeaderData (self, int section, Qt.Orientation orientation, QVariant value, int role = Qt.EditRole)
```

从重新实现[QAbstractItemModel.setHeaderData](qabstractitemmodel.html#setHeaderData)（ ） 。

设置的标题指定一个水平标题_role_至_value_。如果模型被用来在一个视图中显示的数据（例如这是有用的，[QTableView](qtableview.html)） 。

返回True如果_orientation_ is [Qt.Horizontal](qt.html#Orientation-enum)和_section_指的是一个有效的部分，否则返回False 。

注意，该功能不能用于在数据库中的修改值，因为该模型是只读的。

**See also** [headerData](qsqlquerymodel.html#headerData)（）和[data](qsqlquerymodel.html#data)（ ） 。

```
QSqlQueryModel.setLastError (self, QSqlError error)
```

保护功能，允许派生类对设置在数据库上发生的最后一个错误的值_error_。

**See also** [lastError](qsqlquerymodel.html#lastError)（ ） 。

```
QSqlQueryModel.setQuery (self, QSqlQuery query)
```

重置模型，并将数据提供给被给定的_query_。请注意，查询必须处于活动状态，且不能是isForwardOnly （ ） 。

[lastError](qsqlquerymodel.html#lastError)（ ）可以用来获取详细信息，如果有错误设置查询。

**Note:**调用setQuery （ ）将删除任何插入的列。

**See also** [query](qsqlquerymodel.html#query)（ ）[QSqlQuery.isActive](qsqlquery.html#isActive)（ ）[QSqlQuery.setForwardOnly](qsqlquery.html#setForwardOnly)（）和[lastError](qsqlquerymodel.html#lastError)（ ） 。

```
QSqlQueryModel.setQuery (self, QString query, QSqlDatabase db = QSqlDatabase())
```

这是一个重载函数。

执行查询_query_对于给定的数据库连接_db_。如果没有指定的数据库（或无效的数据库） ，则使用默认连接。

[lastError](qsqlquerymodel.html#lastError)（ ）可以用来获取详细信息，如果有错误设置查询。

例如：

```
 [QSqlQueryModel](qsqlquerymodel.html) model;
 model.setQuery("select * from MyTable");
 if (model.lastError().isValid())
     qDebug() << model.lastError();

```

**See also** [query](qsqlquerymodel.html#query)（ ）[queryChange](qsqlquerymodel.html#queryChange)（）和[lastError](qsqlquerymodel.html#lastError)（ ） 。