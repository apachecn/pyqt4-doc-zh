# QSqlResult Class Reference

## [[QtSql](index.htm) module]

该QSqlResult类提供了一个抽象的接口，用于从特定的SQL数据库访问数据。[More...](#details)

### Types

*   `enum BindingSyntax { PositionalBinding, NamedBinding }`

### Methods

*   `__init__ (self, QSqlDriver db)`
*   `addBindValue (self, QVariant val, QSql.ParamType type)`
*   `int at (self)`
*   `BindingSyntax bindingSyntax (self)`
*   `bindValue (self, int pos, QVariant val, QSql.ParamType type)`
*   `bindValue (self, QString placeholder, QVariant val, QSql.ParamType type)`
*   `QSql.ParamType bindValueType (self, QString placeholder)`
*   `QSql.ParamType bindValueType (self, int pos)`
*   `QVariant boundValue (self, QString placeholder)`
*   `QVariant boundValue (self, int pos)`
*   `int boundValueCount (self)`
*   `QString boundValueName (self, int pos)`
*   `list-of-QVariant boundValues (self)`
*   `clear (self)`
*   `QVariant data (self, int i)`
*   `QSqlDriver driver (self)`
*   `bool exec_ (self)`
*   `QString executedQuery (self)`
*   `bool fetch (self, int i)`
*   `bool fetchFirst (self)`
*   `bool fetchLast (self)`
*   `bool fetchNext (self)`
*   `bool fetchPrevious (self)`
*   `QVariant handle (self)`
*   `bool hasOutValues (self)`
*   `bool isActive (self)`
*   `bool isForwardOnly (self)`
*   `bool isNull (self, int i)`
*   `bool isSelect (self)`
*   `bool isValid (self)`
*   `QSqlError lastError (self)`
*   `QVariant lastInsertId (self)`
*   `QString lastQuery (self)`
*   `int numRowsAffected (self)`
*   `bool prepare (self, QString query)`
*   `QSqlRecord record (self)`
*   `bool reset (self, QString sqlquery)`
*   `bool savePrepare (self, QString sqlquery)`
*   `setActive (self, bool a)`
*   `setAt (self, int at)`
*   `setForwardOnly (self, bool forward)`
*   `setLastError (self, QSqlError e)`
*   `setQuery (self, QString query)`
*   `setSelect (self, bool s)`
*   `int size (self)`

* * *

## Detailed Description

该QSqlResult类提供了一个抽象的接口，用于从特定的SQL数据库访问数据。

通常情况下，您可以使用[QSqlQuery](qsqlquery.html)而不是QSqlResult ，因为[QSqlQuery](qsqlquery.html)提供了一个通用的包装器QSqlResult的数据库特定的实现。

如果要实现自己的SQL驱动程序（通过继承[QSqlDriver](qsqldriver.html)） ，您将需要提供自己的QSqlResult子类，它实现了所有你所需要的纯虚函数和其他虚函数。

* * *

## Type Documentation

```
QSqlResult.BindingSyntax
```

该枚举类型指定不同的语法在准备好的查询中指定佔位符。

| Constant | Value | Description |
| --- | --- | --- |
| `QSqlResult.PositionalBinding` | `0` | 使用ODBC风格的语法位置，用“ ？ ”作为佔位符。 |
| `QSqlResult.NamedBinding` | `1` | 使用Oracle风格的语法与命名佔位符（例如“ ： ID” ） |

**See also** [bindingSyntax](qsqlresult.html#bindingSyntax)（ ） 。

* * *

## Method Documentation

```
QSqlResult.__init__ (self, QSqlDriver db)
```

创建[QSqlResult](qsqlresult.html)使用数据库驱动程序_db_。该对象被初始化为无效状态。

**See also** [isActive](qsqlresult.html#isActive)（）和[driver](qsqlresult.html#driver)（ ） 。

```
QSqlResult.addBindValue (self, QVariant val, QSql.ParamType type)
```

绑定值_val_参数类型_paramType_在当前记录（行）的下一个可用位置。

**See also** [bindValue](qsqlresult.html#bindValue)（ ） 。

```
int QSqlResult.at (self)
```

返回结果的电流（从零开始）行的位置。可能返回的特殊值[QSql.BeforeFirstRow](qsql.html#Location-enum) or [QSql.AfterLastRow](qsql.html#Location-enum)。

**See also** [setAt](qsqlresult.html#setAt)（）和[isValid](qsqlresult.html#isValid)（ ） 。

```
BindingSyntax QSqlResult.bindingSyntax (self)
```

[

返回使用准备好的查询的绑定语法。

```
QSqlResult.bindValue (self, int pos, QVariant val, QSql.ParamType type)
```

绑定值_val_参数类型_paramType_到位置_index_当前记录（行）中。

](qsqlresult.html#BindingSyntax-enum)

[**See also**](qsqlresult.html#BindingSyntax-enum) [addBindValue](qsqlresult.html#addBindValue)（ ） 。

```
QSqlResult.bindValue (self, QString placeholder, QVariant val, QSql.ParamType type)
```

这是一个重载函数。

绑定值_val_参数类型_paramType_到_placeholder_在当前记录（行）的名字。

值不能绑定到多个位置的查询，例如：

```
 INSERT INTO testtable (id, name, samename) VALUES (:id, :name, :name)

```

绑定到名称将绑定到第一：名字，但没有第二个。

**Note:**绑定一个未定义的佔位符，将导致不确定的行为。

**See also** [QSqlQuery.bindValue](qsqlquery.html#bindValue)（ ） 。

```
QSql.ParamType QSqlResult.bindValueType (self, QString placeholder)
```

[

返回绑定在位置值的参数类型_index_。

](index.htm)

[**See also**](index.htm) [boundValue](qsqlresult.html#boundValue)（ ） 。

```
QSql.ParamType QSqlResult.bindValueType (self, int pos)
```

[

这是一个重载函数。

返回绑定与给定值的参数类型_placeholder_名称。

```
QVariant QSqlResult.boundValue (self, QString placeholder)
```

返回绑定在位置的值_index_当前记录（行）中。

](index.htm)

[**See also**](index.htm) [bindValue](qsqlresult.html#bindValue)（）和[boundValues](qsqlresult.html#boundValues)（ ） 。

```
QVariant QSqlResult.boundValue (self, int pos)
```

这是一个重载函数。

返回绑定在给定的值_placeholder_在当前记录（行）的名字。

**See also** [bindValueType](qsqlresult.html#bindValueType)（ ） 。

```
int QSqlResult.boundValueCount (self)
```

返回结果绑定的值的数目。

**See also** [boundValues](qsqlresult.html#boundValues)（ ） 。

```
QString QSqlResult.boundValueName (self, int pos)
```

返回绑定的值的名称的位置_index_当前记录（行）中。

**See also** [boundValue](qsqlresult.html#boundValue)（ ） 。

```
list-of-QVariant QSqlResult.boundValues (self)
```

返回当前记录（行）结果的绑定值的向量。

**See also** [boundValueCount](qsqlresult.html#boundValueCount)（ ） 。

```
QSqlResult.clear (self)
```

清除整个结果集，并释放所有相关资源。

```
QVariant QSqlResult.data (self, int i)
```

这种方法是抽象的，应在任何子类中重新实现。

返回的数据为场_index_当前行中的[QVariant](qvariant.html)。如果结果是在活动状态并且被定位于一个有效的记录和该功能仅称为_index_是非负的。派生类必须重新实现这个函数，返回字段的值_index_或的QVariant （） ，如果它不能确定。

```
QSqlDriver QSqlResult.driver (self)
```

[

返回与结果相关的驱动程序。这是传递给构造函数的对象。

```
bool QSqlResult.exec_ (self)
```

执行查询，返回True，如果成功，否则返回False 。

](qsqldriver.html)

[**See also**](qsqldriver.html) [prepare](qsqlresult.html#prepare)（ ） 。

```
QString QSqlResult.executedQuery (self)
```

返回实际执行的查询。这可能与被传递的查询，例如，如果绑定值被用来用一备查询和底层数据库不支持预编译查询。

**See also** [exec_](qsqlresult.html#exec)（）和[setQuery](qsqlresult.html#setQuery)（ ） 。

```
bool QSqlResult.fetch (self, int i)
```

这种方法是抽象的，应在任何子类中重新实现。

定位结果到任意（从零开始）排_index_。

如果结果是在活跃状态，此功能仅被调用。派生类必须重新实现这个功能，结果定位到该行_index_，和呼叫[setAt](qsqlresult.html#setAt)（）具有一个适当的值。返回True表示成功，或假来表示失败。

**See also** [isActive](qsqlresult.html#isActive)（ ）[fetchFirst](qsqlresult.html#fetchFirst)（ ）[fetchLast](qsqlresult.html#fetchLast)（ ）[fetchNext](qsqlresult.html#fetchNext)（）和[fetchPrevious](qsqlresult.html#fetchPrevious)（ ） 。

```
bool QSqlResult.fetchFirst (self)
```

这种方法是抽象的，应在任何子类中重新实现。

定位结果到结果的第一条记录（第0行） 。

如果结果是在活跃状态，此功能仅被调用。派生类必须重新实现这个功能，结果定位到第一条记录，并调用[setAt](qsqlresult.html#setAt)（）具有一个适当的值。返回True表示成功，或假来表示失败。

**See also** [fetch](qsqlresult.html#fetch)（）和[fetchLast](qsqlresult.html#fetchLast)（ ） 。

```
bool QSqlResult.fetchLast (self)
```

这种方法是抽象的，应在任何子类中重新实现。

定位结果到最后一个记录（最后一排）的结果。

如果结果是在活跃状态，此功能仅被调用。派生类必须重新实现这个功能，结果定位到最后一个记录，并调用[setAt](qsqlresult.html#setAt)（）具有一个适当的值。返回True表示成功，或假来表示失败。

**See also** [fetch](qsqlresult.html#fetch)（）和[fetchFirst](qsqlresult.html#fetchFirst)（ ） 。

```
bool QSqlResult.fetchNext (self)
```

定位结果到下一个可用的记录（行）中的结果。

如果结果是在活跃状态，此功能仅被调用。默认实现调用[fetch](qsqlresult.html#fetch)（ ）与下一个索引。派生类可以重新实现这个功能，结果定位到以其他方式下一条记录，并调用[setAt](qsqlresult.html#setAt)（）具有一个适当的值。返回True表示成功，或假来表示失败。

**See also** [fetch](qsqlresult.html#fetch)（）和[fetchPrevious](qsqlresult.html#fetchPrevious)（ ） 。

```
bool QSqlResult.fetchPrevious (self)
```

定位结果到以前的记录（行）的结果。

如果结果是在活跃状态，此功能仅被调用。默认实现调用[fetch](qsqlresult.html#fetch)（ ）与以前的指数。派生类可以重新实现这个功能，结果定位到以其他方式下一条记录，并调用[setAt](qsqlresult.html#setAt)（）具有一个适当的值。返回True表示成功，或假来表示失败。

```
QVariant QSqlResult.handle (self)
```

返回低级别的数据库句柄包裹在这个结果集[QVariant](qvariant.html)或无效的[QVariant](qvariant.html)如果没有手柄。

**Warning:**使用这种具有极处的照顾和只有当你知道你在做什么。

**Warning:**这里返回的句柄可以成为一个过时的指针，如果结果被修改（例如，如果您清除它） 。

**Warning:**手柄可以为NULL ，如果没有执行的结果呢。

这里返回的句柄是依赖于数据库的，你应该访问它之前，查询变量的类型名称。

本示例检索手柄的sqlite的结果：

```
 [QSqlQuery](qsqlquery.html) query = ...
 [QVariant](qvariant.html) v = query.result()->handle();
 if (v.isValid() && qstrcmp(v.typeName(), "sqlite3_stmt*")) {
     // v.data() returns a pointer to the handle
     sqlite3_stmt *handle = *static_cast<sqlite3_stmt **>(v.data());
     if (handle != 0) { // check that it is not NULL
         ...
     }
 }

```

这段代码返回的句柄PostgreSQL或MySQL ：

```
 if (v.typeName() == "PGresult*") {
     PGresult *handle = *static_cast<PGresult **>(v.data());
     if (handle != 0) ...
 }

 if (v.typeName() == "MYSQL_STMT*") {
     MYSQL_STMT *handle = *static_cast<MYSQL_STMT **>(v.data());
     if (handle != 0) ...
 }

```

**See also** [QSqlDriver.handle](qsqldriver.html#handle)（ ） 。

```
bool QSqlResult.hasOutValues (self)
```

返回True如果查询的绑定值中至少有一个是一个`QSql.Out`或[QSql.InOut](qsql.html#ParamTypeFlag-enum)否则返回False 。

**See also** [bindValueType](qsqlresult.html#bindValueType)（ ） 。

```
bool QSqlResult.isActive (self)
```

返回True如果结果已被检索的记录，否则返回False 。

```
bool QSqlResult.isForwardOnly (self)
```

返回True如果你只能通过结果集中向前滚动，否则返回False 。

**See also** [setForwardOnly](qsqlresult.html#setForwardOnly)（ ） 。

```
bool QSqlResult.isNull (self, int i)
```

这种方法是抽象的，应在任何子类中重新实现。

返回True如果在位置字段_index_当前行中为空，否则返回False 。

```
bool QSqlResult.isSelect (self)
```

返回True如果当前的结果是从`SELECT`声明，否则返回False 。

**See also** [setSelect](qsqlresult.html#setSelect)（ ） 。

```
bool QSqlResult.isValid (self)
```

返回True如果结果是定位在一个有效的记录（即，结果前的第一个或最后一个记录之后，是不是定位） ，否则返回False 。

**See also** [at](qsqlresult.html#at)（ ） 。

```
QSqlError QSqlResult.lastError (self)
```

[

返回与结果相关联的最后一个错误。

](qsqlerror.html)

[**See also**](qsqlerror.html) [setLastError](qsqlresult.html#setLastError)（ ） 。

```
QVariant QSqlResult.lastInsertId (self)
```

返回最近插入的行的对象ID ，如果数据库支持它。无效的[QVariant](qvariant.html)将被退回，如果查询没有插入任何值，或者如果数据库没有报告ID后面。如果不止一个行被感动的插入，该行为是未定义的。

请注意，对于Oracle数据库的行的ROWID将被退回，而对于MySQL数据库行的自动递增字段将被退回。

**See also** [QSqlDriver.hasFeature](qsqldriver.html#hasFeature)（ ） 。

```
QString QSqlResult.lastQuery (self)
```

如果没有一个返回当前的SQL查询文本，或空字符串。

**See also** [setQuery](qsqlresult.html#setQuery)（ ） 。

```
int QSqlResult.numRowsAffected (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回受执行的最后一次查询的行数，或-1，如果它不能确定，或者如果该查询是`SELECT`声明。

**See also** [size](qsqlresult.html#size)（ ） 。

```
bool QSqlResult.prepare (self, QString query)
```

准备给定的_query_执行;查询将通常使用的佔位符，以便它可以被重复地执行。返回True如果查询成功制备，否则返回False 。

**See also** [exec_](qsqlresult.html#exec)（ ） 。

```
QSqlRecord QSqlResult.record (self)
```

[](qsqlrecord.html)

[返回当前记录，如果查询是积极的，否则返回一个空](qsqlrecord.html)[QSqlRecord](qsqlrecord.html)。

默认的实现始终返回一个空[QSqlRecord](qsqlrecord.html)。

**See also** [isActive](qsqlresult.html#isActive)（ ） 。

```
bool QSqlResult.reset (self, QString sqlquery)
```

这种方法是抽象的，应在任何子类中重新实现。

将结果用SQL语句_query_用于随后的数据检索。

派生类必须重写本函数和应用_query_到数据库中。之后的结果被设置为无效状态和定位的新结果的第一条记录之前此功能仅调用。派生类应返回True，如果查询成功，并准备使用，否则返回False。

**See also** [setQuery](qsqlresult.html#setQuery)（ ） 。

```
bool QSqlResult.savePrepare (self, QString sqlquery)
```

准备给定的_query_，使用底层数据库功能在可能的情况。返回True如果查询成功制备，否则返回False 。

**See also** [prepare](qsqlresult.html#prepare)（ ） 。

```
QSqlResult.setActive (self, bool a)
```

此功能是为派生类来设置内部有源状态_active_。

**See also** [isActive](qsqlresult.html#isActive)（ ） 。

```
QSqlResult.setAt (self, int at)
```

此功能是为派生类的内部（从零开始）行位置设置为_index_。

**See also** [at](qsqlresult.html#at)（ ） 。

```
QSqlResult.setForwardOnly (self, bool forward)
```

设置只进模式_forward_。如果_forward_是真的，只[fetchNext](qsqlresult.html#fetchNext)（ ）是允许的用于导航的结果。只正向模式需要更少的内存，因为结果没有被缓存。默认情况下，此功能被禁用。

前冲只为False是一个建议的数据库引擎，它拥有最终决定权在结果集是否是只向前或滚动。[isForwardOnly](qsqlresult.html#isForwardOnly)（ ）将总是返回结果集的正确状态。

**Note:**调用setForwardOnly后执行的查询会导致意想不到的结果充其量和崩溃在最坏的情况。

**See also** [isForwardOnly](qsqlresult.html#isForwardOnly)（ ）[fetchNext](qsqlresult.html#fetchNext)（）和[QSqlQuery.setForwardOnly](qsqlquery.html#setForwardOnly)（ ） 。

```
QSqlResult.setLastError (self, QSqlError e)
```

此功能是为派生类设置的最后一个错误_error_。

**See also** [lastError](qsqlresult.html#lastError)（ ） 。

```
QSqlResult.setQuery (self, QString query)
```

设置当前查询的结果_query_。你必须调用[reset](qsqlresult.html#reset)（）来执行对数据库的查询。

**See also** [reset](qsqlresult.html#reset)（）和[lastQuery](qsqlresult.html#lastQuery)（ ） 。

```
QSqlResult.setSelect (self, bool s)
```

此功能是为派生类来表示当前的语句是否是一个SQL`SELECT`声明。该_select_参数应该是真实的，如果语句是`SELECT`声明，否则它应该是假的。

**See also** [isSelect](qsqlresult.html#isSelect)（ ） 。

```
int QSqlResult.size (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回的大小`SELECT`结果，或-1，如果它不能确定，或者如果该查询是不是一个`SELECT`声明。

**See also** [numRowsAffected](qsqlresult.html#numRowsAffected)（ ） 。