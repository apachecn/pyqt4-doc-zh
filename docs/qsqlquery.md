# QSqlQuery Class Reference

## [[QtSql](index.htm) module]

该QSqlQuery类提供执行和操作的SQL语句的方法。[More...](#details)

### Types

*   `enum BatchExecutionMode { ValuesAsRows, ValuesAsColumns }`

### Methods

*   `__init__ (self, QSqlResult r)`
*   `__init__ (self, QString query = QString(), QSqlDatabase db = QSqlDatabase())`
*   `__init__ (self, QSqlDatabase db)`
*   `__init__ (self, QSqlQuery other)`
*   `addBindValue (self, QVariant val, QSql.ParamType type = QSql.In)`
*   `int at (self)`
*   `bindValue (self, QString placeholder, QVariant val, QSql.ParamType type = QSql.In)`
*   `bindValue (self, int pos, QVariant val, QSql.ParamType type = QSql.In)`
*   `QVariant boundValue (self, QString placeholder)`
*   `QVariant boundValue (self, int pos)`
*   `dict-of-QString-QVariant boundValues (self)`
*   `clear (self)`
*   `QSqlDriver driver (self)`
*   `bool exec_ (self, QString query)`
*   `bool exec_ (self)`
*   `bool execBatch (self, BatchExecutionMode mode = QSqlQuery.ValuesAsRows)`
*   `QString executedQuery (self)`
*   `finish (self)`
*   `bool first (self)`
*   `bool isActive (self)`
*   `bool isForwardOnly (self)`
*   `bool isNull (self, int field)`
*   `bool isSelect (self)`
*   `bool isValid (self)`
*   `bool last (self)`
*   `QSqlError lastError (self)`
*   `QVariant lastInsertId (self)`
*   `QString lastQuery (self)`
*   `bool next (self)`
*   `bool nextResult (self)`
*   `QSql.NumericalPrecisionPolicy numericalPrecisionPolicy (self)`
*   `int numRowsAffected (self)`
*   `bool prepare (self, QString query)`
*   `bool previous (self)`
*   `QSqlRecord record (self)`
*   `QSqlResult result (self)`
*   `bool seek (self, int index, bool relative = False)`
*   `setForwardOnly (self, bool forward)`
*   `setNumericalPrecisionPolicy (self, QSql.NumericalPrecisionPolicy precisionPolicy)`
*   `int size (self)`
*   `QVariant value (self, int i)`

* * *

## Detailed Description

该QSqlQuery类提供执行和操作的SQL语句的方法。

QSqlQuery封装这是在执行涉及从SQL查询创建，浏览和检索数据的功能[QSqlDatabase](qsqldatabase.html)。它可以被用来执行DML （数据操纵语言）语句，如`SELECT`，`INSERT`，`UPDATE`和`DELETE`，以及DDL （数据定义语言）语句，如`CREATE` `TABLE`。它也可以被用来执行特定于数据库的命令而不是标准的SQL （例如`SET DATESTYLE=ISO`PostgreSQL的） 。

成功执行的SQL语句设置查询的状态为主动，使[isActive](qsqlquery.html#isActive)（ ）返回True 。否则，查询的状态设置为无效。在任一情况下，执行一个新的SQL语句时，查询被定位在一个无效的记录。一个活跃的查询必须被导航到一个有效的记录（使[isValid](qsqlquery.html#isValid)（ ）值可以被检索之前返回True ） 。

对于某些数据库，如果积极的查询，它是一个`SELECT`当你调用语句存在[commit()](qsqldatabase.html#commit) or [rollback()](qsqldatabase.html#rollback)，在提交或回滚将失败。看[isActive](qsqlquery.html#isActive)（ ）了解详情。

导航记录的是具有以下功能进行：

*   [next](qsqlquery.html#next)()
*   [previous](qsqlquery.html#previous)()
*   [first](qsqlquery.html#first)()
*   [last](qsqlquery.html#last)()
*   [seek](qsqlquery.html#seek)()

这些功能使程序员可以前进，后退或者擅自通过查询返回的记录。如果你只需要向前移动的结果（例如，通过使用[next](qsqlquery.html#next)（ ） ） ，则可以使用[setForwardOnly](qsqlquery.html#setForwardOnly)（ ） ，这将节省一个显着的内存开销，提高对某些数据库的性能。一旦活动查询被定位在一个有效的记录，数据可以使用检索[value](qsqlquery.html#value)（ ） 。所有数据从SQL后端使用转[QVariants](index.htm#qvariants)。

例如：

```
     QSqlQuery query("SELECT country FROM artist");
     while (query.next()) {
         [QString](qstring.html) country = query.value(0).toString();
         doSomething(country);
     }

```

要访问查询返回的数据，使用值（整数）。在由返回的数据中的每个字段`SELECT`声明是通过传递该领域的地位在声明中，从0开始访问的。这使得使用`SELECT *`查询不可取的，因为返回的字段的顺序是不确定的。

为了提高效率，有没有函数通过名字来访问一个字段（除非你使用预编译查询的姓名，解释见下文） 。若要将字段名成一个索引，使用[record](qsqlquery.html#record)（ ） 。[indexOf()](qsqlrecord.html#indexOf)例如：

```
     QSqlQuery query("SELECT * FROM artist");
     int fieldNo = query.record().indexOf("country");
     while (query.next()) {
         [QString](qstring.html) country = query.value(fieldNo).toString();
         doSomething(country);
     }

```

QSqlQuery支持准备好的查询执行和参数值来佔位符绑定。有些数据库不支持这些功能，所以对于那些， Qt的模拟所需的功能。例如， Oracle和ODBC驱动程序已准备妥当查询支持，和Qt使得它的使用，但对于那些没有这种支持的数据库， Qt的实现了功能本身，如通过执行一个查询时用实际值替换的佔位符。使用[numRowsAffected](qsqlquery.html#numRowsAffected)（ ）来找出多少行受到非`SELECT`查询，并[size](qsqlquery.html#size)（）找到多少被检索由`SELECT`。

Oracle数据库通过使用一个冒号名称的语法，如查明佔位符`:name`。 ODBC只是使用`?`字符。 Qt支持这两种语法，用，你不能将它们混合在同一个查询的限制。

您可以使用检索所有单个变量的字段的值（地图）[boundValues](qsqlquery.html#boundValues)（ ） 。

### Approaches to Binding Values

下面，我们提出使用每四个不同的结合方式，以及结合值到存储过程的一个例子相同的例子。

**Named binding using named placeholders:**

```
     QSqlQuery query;
     query.prepare("INSERT INTO person (id, forename, surname) "
                   "VALUES (:id, :forename, :surname)");
     query.bindValue(":id", 1001);
     query.bindValue(":forename", "Bart");
     query.bindValue(":surname", "Simpson");
     query.exec();

```

**Positional binding using named placeholders:**

```
     QSqlQuery query;
     query.prepare("INSERT INTO person (id, forename, surname) "
                   "VALUES (:id, :forename, :surname)");
     query.bindValue(0, 1001);
     query.bindValue(1, "Bart");
     query.bindValue(2, "Simpson");
     query.exec();

```

**Binding values using positional placeholders (version 1):**

```
     QSqlQuery query;
     query.prepare("INSERT INTO person (id, forename, surname) "
                   "VALUES (?, ?, ?)");
     query.bindValue(0, 1001);
     query.bindValue(1, "Bart");
     query.bindValue(2, "Simpson");
     query.exec();

```

**Binding values using positional placeholders (version 2):**

```
     QSqlQuery query;
     query.prepare("INSERT INTO person (id, forename, surname) "
                   "VALUES (?, ?, ?)");
     query.addBindValue(1001);
     query.addBindValue("Bart");
     query.addBindValue("Simpson");
     query.exec();

```

**Binding values to a stored procedure:**

此代码调用一个存储过程调用`AsciiToInt()`在参数传递给它一个字符通过，并考虑其结果的输出参数。

```
     QSqlQuery query;
     query.prepare("CALL AsciiToInt(?, ?)");
     query.bindValue(0, "A");
     query.bindValue(1, 0, [QSql](qsql.html).Out);
     query.exec();
     int i = query.boundValue(1).toInt(); // i is 65

```

需要注意的是未绑定的参数将保留它们的值。

使用return语句返回值或返回多个结果集的存储过程，不完全支持。对于具体细节见[SQL Database Drivers](index.htm)。

**Warning:**你必须载入SQL驱动程序并创建一个QSqlQuery之前打开连接。此外，该连接必须保持开放，而存在的查询，否则， QSqlQuery的行为是未定义的。

* * *

## Type Documentation

```
QSqlQuery.BatchExecutionMode
```

| Constant | Value | Description |
| --- | --- | --- |
| `QSqlQuery.ValuesAsRows` | `0` | - 更新多行。黄柏中的每个条目[QVariantList](qvariant.html#QVariantList-typedef)作为用于更新的下一行的值。 |
| `QSqlQuery.ValuesAsColumns` | `1` | - 更新一行。黄柏中的每个条目[QVariantList](qvariant.html#QVariantList-typedef)作为数组类型的单个值。 |

* * *

## Method Documentation

```
QSqlQuery.__init__ (self, QSqlResult r)
```

构造一个[QSqlQuery](qsqlquery.html)对象，它使用了[QSqlResult](qsqlresult.html) _result_与数据库进行通信。

```
QSqlQuery.__init__ (self, QString query = QString(), QSqlDatabase db = QSqlDatabase())
```

构造一个[QSqlQuery](qsqlquery.html)使用SQL对象_query_和数据库_db_。如果_db_如果未指定，或者是无效的，应用程序的默认数据库被使用。如果_query_是不是空字符串，它就会被执行。

**See also** [QSqlDatabase](qsqldatabase.html)。

```
QSqlQuery.__init__ (self, QSqlDatabase db)
```

构造一个[QSqlQuery](qsqlquery.html)使用数据库对象_db_。如果_db_是无效的，应用程序的默认数据库将被使用。

**See also** [QSqlDatabase](qsqldatabase.html)。

```
QSqlQuery.__init__ (self, QSqlQuery other)
```

构造的副本_other_。

```
QSqlQuery.addBindValue (self, QVariant val, QSql.ParamType type = QSql.In)
```

增加值_val_使用位置值绑定时的值列表。该addBindValue （ ）调用的顺序确定哪个佔位符的值将在准备好的查询绑定到。如果_paramType_ is [QSql.Out](qsql.html#ParamTypeFlag-enum) or [QSql.InOut](qsql.html#ParamTypeFlag-enum)，佔位符将与后从数据库中的数据复盖[exec_](qsqlquery.html#exec)（ ）调用。

要绑定一个NULL值，使用空[QVariant](qvariant.html)，例如，使用`QVariant(QVariant.String)`如果要绑定的字符串。

**See also** [bindValue](qsqlquery.html#bindValue)（ ）[prepare](qsqlquery.html#prepare)（ ）[exec_](qsqlquery.html#exec)（ ）[boundValue](qsqlquery.html#boundValue)（）和[boundValues](qsqlquery.html#boundValues)（ ） 。

```
int QSqlQuery.at (self)
```

返回查询的当前内部位置。第一个记录是在位置0 。如果位置是无效的，则函数返回[QSql.BeforeFirstRow](qsql.html#Location-enum) or [QSql.AfterLastRow](qsql.html#Location-enum)，这是特殊的负值。

**See also** [previous](qsqlquery.html#previous)（ ）[next](qsqlquery.html#next)（ ）[first](qsqlquery.html#first)（ ）[last](qsqlquery.html#last)（ ）[seek](qsqlquery.html#seek)（ ）[isActive](qsqlquery.html#isActive)（）和[isValid](qsqlquery.html#isValid)（ ） 。

```
QSqlQuery.bindValue (self, QString placeholder, QVariant val, QSql.ParamType type = QSql.In)
```

设置佔位符_placeholder_绑定到值_val_在准备好的语句。注意，佔位符标记（例如`:`）必须指定佔位符的名称时，必须包括在内。如果_paramType_ is [QSql.Out](qsql.html#ParamTypeFlag-enum) or [QSql.InOut](qsql.html#ParamTypeFlag-enum)，佔位符将与后从数据库中的数据复盖[exec_](qsqlquery.html#exec)（ ）调用。在这种情况下，有足够的空间必须被预先分配给的结果存储到。

要绑定一个NULL值，使用空[QVariant](qvariant.html)，例如，使用`QVariant(QVariant.String)`如果要绑定的字符串。

值不能绑定到多个位置的查询，例如：

```
 INSERT INTO testtable (id, name, samename) VALUES (:id, :name, :name)

```

绑定到名称将绑定到第一：名字，但没有第二个。

**See also** [addBindValue](qsqlquery.html#addBindValue)（ ）[prepare](qsqlquery.html#prepare)（ ）[exec_](qsqlquery.html#exec)（ ）[boundValue](qsqlquery.html#boundValue)（）和[boundValues](qsqlquery.html#boundValues)（ ） 。

```
QSqlQuery.bindValue (self, int pos, QVariant val, QSql.ParamType type = QSql.In)
```

设置佔位符的位置_pos_绑定到值_val_在准备好的语句。字段编号从0开始。如果_paramType_ is [QSql.Out](qsql.html#ParamTypeFlag-enum) or [QSql.InOut](qsql.html#ParamTypeFlag-enum)，佔位符将与后从数据库中的数据复盖[exec_](qsqlquery.html#exec)（ ）调用。

```
QVariant QSqlQuery.boundValue (self, QString placeholder)
```

传回值_placeholder_。

**See also** [boundValues](qsqlquery.html#boundValues)（ ）[bindValue](qsqlquery.html#bindValue)（）和[addBindValue](qsqlquery.html#addBindValue)（ ） 。

```
QVariant QSqlQuery.boundValue (self, int pos)
```

返回在位置的佔位符的值_pos_。

```
dict-of-QString-QVariant QSqlQuery.boundValues (self)
```

返回绑定值的地图。

与名为绑定，绑定的值可以检查以下方面：

```
     [QMapIterator](index.htm)<[QString](qstring.html), [QVariant](qvariant.html)> i(query.boundValues());
     while (i.hasNext()) {
         i.next();
         cout << i.key().toAscii().data() << ": "
              << i.value().toString().toAscii().data() << endl;
     }

```

与位置绑定，代码变为：

```
     [QList](index.htm)<[QVariant](qvariant.html)> list = query.boundValues().values();
     for (int i = 0; i < list.size(); ++i)
         cout << i << ": " << list.at(i).toString().toAscii().data() << endl;

```

**See also** [boundValue](qsqlquery.html#boundValue)（ ）[bindValue](qsqlquery.html#bindValue)（）和[addBindValue](qsqlquery.html#addBindValue)（ ） 。

```
QSqlQuery.clear (self)
```

清除结果集，并释放该查询持有的任何资源。设置查询状态为无效。你应该很少，如果需要调用这个函数。

```
QSqlDriver QSqlQuery.driver (self)
```

[

返回与查询相关联的数据库驱动程序。

```
bool QSqlQuery.exec_ (self, QString query)
```

](qsqldriver.html)

[执行SQL中_query_。返回True ，并设置查询状态](qsqldriver.html)[active](qsqlquery.html#isActive)如果查询成功，否则返回False 。该_query_字符串必须使用适当的语法为被查询（例如，标准的SQL ）的SQL数据库。

查询被执行后，查询被定位在一个_invalid_记录，并且必须被导航到一个有效记录的数据值可以被检索（例如，在使用前[next](qsqlquery.html#next)（））。

请注意，此查询的最后一个错误，当执行exec（ ）被调用复位。

对SQLite的查询字符串可以一次只包含一个语句。如果多于一个语句被放弃，该函数返回False 。

例如：

```
     [QSqlQuery](qsqlquery.html) query;
     query.exec("INSERT INTO employee (id, name, salary) "
                "VALUES (1001, 'Thad Beaumont', 65000)");

```

**See also** [isActive](qsqlquery.html#isActive)（ ）[isValid](qsqlquery.html#isValid)（ ）[next](qsqlquery.html#next)（ ）[previous](qsqlquery.html#previous)（ ）[first](qsqlquery.html#first)（ ）[last](qsqlquery.html#last)（）和[seek](qsqlquery.html#seek)（ ） 。

```
bool QSqlQuery.exec_ (self)
```

执行先前准备的SQL查询。返回True如果成功执行该查询，否则返回False 。

请注意，此查询的最后一个错误是，当复位[exec_](qsqlquery.html#exec)（）被调用。

**See also** [prepare](qsqlquery.html#prepare)（ ）[bindValue](qsqlquery.html#bindValue)（ ）[addBindValue](qsqlquery.html#addBindValue)（ ）[boundValue](qsqlquery.html#boundValue)（）和[boundValues](qsqlquery.html#boundValues)（ ） 。

```
bool QSqlQuery.execBatch (self, BatchExecutionMode mode = QSqlQuery.ValuesAsRows)
```

执行先前准备的SQL查询中的批次。所有绑定参数必须是变种列表。如果数据库不支持批量处决，驱动程序将使用传统的模拟它[exec_](qsqlquery.html#exec)（ ）调用。

返回True如果查询成功执行，否则返回False 。

例如：

```
 [QSqlQuery](qsqlquery.html) q;
 q.prepare("insert into myTable values (?, ?)");

 [QVariantList](qvariant.html#QVariantList-typedef) ints;
 ints << 1 << 2 << 3 << 4;
 q.addBindValue(ints);

 [QVariantList](qvariant.html#QVariantList-typedef) names;
 names << "Harald" << "Boris" << "Trond" << [QVariant](qvariant.html)([QVariant](qvariant.html).String);
 q.addBindValue(names);

 if (!q.execBatch())
     qDebug() << q.lastError();

```

上面的例子中插入四个新行插入`myTable`：

```
 1  Harald
 2  Boris
 3  Trond
 4  NULL

```

要绑定NULL值，空[QVariant](qvariant.html)相关类型的已被添加到绑定[QVariantList](qvariant.html#QVariantList-typedef)，例如，`QVariant(QVariant.String)`应该如果您使用的是字符串中使用。

**Note:**每一个绑定[QVariantList](qvariant.html#QVariantList-typedef)必须包含的变体是相同的。

**Note:**的类型[QVariants](index.htm#qvariants)在列表中不能改变。例如，您不能在一个混合整数和字符串变量[QVariantList](qvariant.html#QVariantList-typedef)。

该_mode_参数指示如何绑定[QVariantList](qvariant.html#QVariantList-typedef)将被解释。如果_mode_ is `ValuesAsRows`，内部的每一个变种[QVariantList](qvariant.html#QVariantList-typedef)将被解释为一个新的行的值。`ValuesAsColumns`对于Oracle驱动程序的一个特例。在这种模式下，在一个每条目[QVariantList](qvariant.html#QVariantList-typedef)将被解释为一个存储过程中的IN或OUT值的数组值。请注意，这只会工作，如果IN或OUT值是一个表型组成的基本型只有一列，例如`TYPE myType IS TABLE OF VARCHAR(64) INDEX BY BINARY_INTEGER;`

这个函数中引入了Qt 4.2中。

**See also** [prepare](qsqlquery.html#prepare)（ ）[bindValue](qsqlquery.html#bindValue)（）和[addBindValue](qsqlquery.html#addBindValue)（ ） 。

```
QString QSqlQuery.executedQuery (self)
```

返回成功执行的最后一个查询。

在大多数情况下，这个函数返回相同的字符串[lastQuery](qsqlquery.html#lastQuery)（ ） 。如果有一个佔位符编写的查询上不支持它的DBMS执行，这个查询的制备效仿。在原始查询中的佔位符替换为它们的绑定值，形成一个新的查询。该函数返回修改后的查询。它是用于调试目的大多是有用的。

**See also** [lastQuery](qsqlquery.html#lastQuery)（ ） 。

```
QSqlQuery.finish (self)
```

指示没有更多的数据将从这个查询被取出，直到重新执行它的数据库驱动程序。通常没有必要调用这个函数，但它可能会有所帮助，以免费资源，例如锁或游标，如果你打算重新使用查询在以后的时间。

设置查询为无效。绑定值保留它们的值。

此功能被引入Qt的4.3.2 。

**See also** [prepare](qsqlquery.html#prepare)（ ）[exec_](qsqlquery.html#exec)（）和[isActive](qsqlquery.html#isActive)（ ） 。

```
bool QSqlQuery.first (self)
```

获取第一条记录的结果，如果有的话，和对检索到的记录位置的查询。请注意，其结果必然是在[active](qsqlquery.html#isActive)状态[isSelect](qsqlquery.html#isSelect)（）必须调用这个函数，否则将什么都不做，返回False才返回True。如果成功，则返回True 。如果不成功查询位置被设置为无效位置，返回False 。

**See also** [next](qsqlquery.html#next)（ ）[previous](qsqlquery.html#previous)（ ）[last](qsqlquery.html#last)（ ）[seek](qsqlquery.html#seek)（ ）[at](qsqlquery.html#at)（ ）[isActive](qsqlquery.html#isActive)（）和[isValid](qsqlquery.html#isValid)（ ） 。

```
bool QSqlQuery.isActive (self)
```

返回True如果查询_active_。一个活跃[QSqlQuery](qsqlquery.html)是一个已经[exec()'d](qsqlquery.html#exec)成功但尚未完成。当你完成了一个活跃的查询，可以使使查询无效的调用[finish](qsqlquery.html#finish)（）或[clear](qsqlquery.html#clear)（ ） ，或者你可以删除[QSqlQuery](qsqlquery.html)实例。

**Note:**特别感兴趣的是一种主动查询，它是一个`SELECT`声明。对于支持事务的一些数据库，积极查询，它是一个`SELECT`语句可以导致[commit()](qsqldatabase.html#commit)或[rollback()](qsqldatabase.html#rollback)失败，因此提交或回滚之前，你应该让你活跃`SELECT`语句查询无效使用上面列出的方法之一。

**See also** [isSelect](qsqlquery.html#isSelect)（ ） 。

```
bool QSqlQuery.isForwardOnly (self)
```

返回True如果你只能通过一个结果集向前滚动，否则返回False 。

**See also** [setForwardOnly](qsqlquery.html#setForwardOnly)（）和[next](qsqlquery.html#next)（ ） 。

```
bool QSqlQuery.isNull (self, int field)
```

返回True如果查询[active](qsqlquery.html#isActive)和定位在一个有效的记录和_field_为NULL ，否则返回False 。请注意，对于某些驱动程序， ISNULL（ ）将不会返回准确的信息后，才试图检索数据。

**See also** [isActive](qsqlquery.html#isActive)（ ）[isValid](qsqlquery.html#isValid)（）和[value](qsqlquery.html#value)（ ） 。

```
bool QSqlQuery.isSelect (self)
```

返回True如果当前的查询是`SELECT`声明，否则返回False 。

```
bool QSqlQuery.isValid (self)
```

返回True如果查询是目前定位在一个有效的记录，否则返回False 。

```
bool QSqlQuery.last (self)
```

检索记录集中的最后结果，如果有的话，和对检索到的记录位置的查询。请注意，其结果必然是在[active](qsqlquery.html#isActive)状态[isSelect](qsqlquery.html#isSelect)（）必须调用这个函数，否则将什么都不做，返回False才返回True。如果成功，则返回True 。如果不成功查询位置被设置为无效位置，返回False 。

**See also** [next](qsqlquery.html#next)（ ）[previous](qsqlquery.html#previous)（ ）[first](qsqlquery.html#first)（ ）[seek](qsqlquery.html#seek)（ ）[at](qsqlquery.html#at)（ ）[isActive](qsqlquery.html#isActive)（）和[isValid](qsqlquery.html#isValid)（ ） 。

```
QSqlError QSqlQuery.lastError (self)
```

[

返回有关最后一个错误（如果有的话） ，与此查询时发生的错误信息。

](qsqlerror.html)

[**See also**](qsqlerror.html) [QSqlError](qsqlerror.html)和[QSqlDatabase.lastError](qsqldatabase.html#lastError)（ ） 。

```
QVariant QSqlQuery.lastInsertId (self)
```

返回最近插入的行的对象ID ，如果数据库支持它。无效的[QVariant](qvariant.html)将被退回，如果查询没有插入任何值，或者如果数据库没有报告ID后面。如果不止一个行被感动的插入，该行为是未定义的。

对于MySQL数据库行的自动递增字段将被退回。

**Note:**对于这个功能在PSQL工作，该表的表必须包含的OID ，它可能没有被创建的默认。检查`default_with_oids`配置变量来确定。

**See also** [QSqlDriver.hasFeature](qsqldriver.html#hasFeature)（ ） 。

```
QString QSqlQuery.lastQuery (self)
```

如果没有当前的查询文本返回当前查询所使用的文字，或空字符串。

**See also** [executedQuery](qsqlquery.html#executedQuery)（ ） 。

```
bool QSqlQuery.next (self)
```

检索下一条记录中的结果，如果有的话，和对检索到的记录位置的查询。请注意，其结果必然是在[active](qsqlquery.html#isActive)状态[isSelect](qsqlquery.html#isSelect)（）必须调用这个函数，否则将什么都不做，返回False才返回True。

以下规则适用：

*   If the result is currently located before the first record, e.g. immediately after a query is executed, an attempt is made to retrieve the first record.
*   If the result is currently located after the last record, there is no change and false is returned.
*   If the result is located somewhere in the middle, an attempt is made to retrieve the next record.

如果不能被检索的记录，结果是最后一条记录并返回False后定位。如果记录被成功取出，则返回True 。

**See also** [previous](qsqlquery.html#previous)（ ）[first](qsqlquery.html#first)（ ）[last](qsqlquery.html#last)（ ）[seek](qsqlquery.html#seek)（ ）[at](qsqlquery.html#at)（ ）[isActive](qsqlquery.html#isActive)（）和[isValid](qsqlquery.html#isValid)（ ） 。

```
bool QSqlQuery.nextResult (self)
```

丢弃当前的结果集，并导航到下一个（如果可用） 。

有些数据库是可以返回多个结果集的存储过程或SQL批处理（包含多个语句的查询字符串）的。如果在执行一个查询此功能可用于导航到下一个结果集（次）后，多个结果集可用。

如果一个新的结果集是可用此函数将返回True 。该查询将在一个重新定位_invalid_在新的结果集的记录，必须导航到一个有效的记录数据值可以被检索之前。如果一个新的结果集是不可用的函数返回False ，并且查询被设置为无效。在任何情况下，旧的结果集合将被丢弃。

当语句之一是一个非select语句影响的行计数可能，而不是一个结果集可用。

需要注意的是一些数据库，如微软的SQL Server ，要求非滚动游标与多个结果集时。有些数据库可以一次执行所有语句，而其他人可能会推迟执行，直到实际访问的结果集，以及一些数据库可能对哪些语句被允许在SQL批处理中使用的限制。

此功能被引入Qt的4.4 。

**See also** [QSqlDriver.hasFeature](qsqldriver.html#hasFeature)（ ）[setForwardOnly](qsqlquery.html#setForwardOnly)（ ）[next](qsqlquery.html#next)（ ）[isSelect](qsqlquery.html#isSelect)（ ）[numRowsAffected](qsqlquery.html#numRowsAffected)（ ）[isActive](qsqlquery.html#isActive)（）和[lastError](qsqlquery.html#lastError)（ ） 。

```
QSql.NumericalPrecisionPolicy QSqlQuery.numericalPrecisionPolicy (self)
```

[

返回当前的精度政策。

](qsql.html#NumericalPrecisionPolicy-enum)

[**See also**](qsql.html#NumericalPrecisionPolicy-enum) [QSql.NumericalPrecisionPolicy](qsql.html#NumericalPrecisionPolicy-enum)和[setNumericalPrecisionPolicy](qsqlquery.html#setNumericalPrecisionPolicy)（ ） 。

```
int QSqlQuery.numRowsAffected (self)
```

返回受影响的结果的SQL语句，或者-1 ，如果它不能确定的行数。请注意，对于`SELECT`语句，该值是不确定的;使用[size](qsqlquery.html#size)（ ）来代替。如果该查询是不[active](qsqlquery.html#isActive)，则返回-1。

**See also** [size](qsqlquery.html#size)（）和[QSqlDriver.hasFeature](qsqldriver.html#hasFeature)（ ） 。

```
bool QSqlQuery.prepare (self, QString query)
```

准备SQL查询_query_用于执行。返回True如果查询成功制备，否则返回False 。

该查询可以包含佔位符绑定的值。这两个Oracle风格冒号名称（例如，`:surname`） ，和ODBC风格（`?`）佔位符的支持，但他们不能在同一查询中混用。请参阅[Detailed Description](qsqlquery.html#qsqlquery-examples)为例子。

可移植性注：有些数据库选择延迟准备的查询，直到它被执行的第一次。在这种情况下，准备一个语法错误的查询成功，但每一个连续的[exec_](qsqlquery.html#exec)（ ）将失败。

对SQLite的查询字符串可以一次只包含一个语句。如果一个以上的语句给，函数返回False 。

例如：

```
     [QSqlQuery](qsqlquery.html) query;
     query.prepare("INSERT INTO person (id, forename, surname) "
                   "VALUES (:id, :forename, :surname)");
     query.bindValue(":id", 1001);
     query.bindValue(":forename", "Bart");
     query.bindValue(":surname", "Simpson");
     query.exec();

```

**See also** [exec_](qsqlquery.html#exec)（ ）[bindValue](qsqlquery.html#bindValue)（）和[addBindValue](qsqlquery.html#addBindValue)（ ） 。

```
bool QSqlQuery.previous (self)
```

检索以前的记录结果中，如果有的话，以及对检索到的记录位置的查询。请注意，其结果必然是在[active](qsqlquery.html#isActive)状态[isSelect](qsqlquery.html#isSelect)（）必须调用这个函数，否则将什么都不做，返回False才返回True。

以下规则适用：

*   If the result is currently located before the first record, there is no change and false is returned.
*   If the result is currently located after the last record, an attempt is made to retrieve the last record.
*   If the result is somewhere in the middle, an attempt is made to retrieve the previous record.

如果不能被检索的记录，结果被定位在第一个记录并返回False之前。如果记录被成功取出，则返回True 。

**See also** [next](qsqlquery.html#next)（ ）[first](qsqlquery.html#first)（ ）[last](qsqlquery.html#last)（ ）[seek](qsqlquery.html#seek)（ ）[at](qsqlquery.html#at)（ ）[isActive](qsqlquery.html#isActive)（）和[isValid](qsqlquery.html#isValid)（ ） 。

```
QSqlRecord QSqlQuery.record (self)
```

[](qsqlrecord.html)

[返回](qsqlrecord.html)[QSqlRecord](qsqlrecord.html)包含域信息的当前查询。如果查询指向一个有效的行（[isValid](qsqlquery.html#isValid)（ ）返回True ） ，该记录被填充了该行的值。当没有主动查询一个空的记录，则返回（[isActive](qsqlquery.html#isActive)（ ）返回False ） 。

从查询中检索值，[value](qsqlquery.html#value)（ ）应该被使用，因为它的基于索引的查找速度更快。

在下面的示例中，`SELECT * FROM`执行查询。由于列的顺序没有被定义，[QSqlRecord.indexOf](qsqlrecord.html#indexOf)（）是用来获取的列的索引。

```
 [QSqlQuery](qsqlquery.html) q("select * from employees");
 [QSqlRecord](qsqlrecord.html) rec = q.record();

 qDebug() << "Number of columns: " << rec.count();

 int nameCol = rec.indexOf("name"); // index of the field "name"
 while (q.next())
     qDebug() << q.value(nameCol).toString(); // output all names

```

**See also** [value](qsqlquery.html#value)（ ） 。

```
QSqlResult QSqlQuery.result (self)
```

[

返回与查询相关的结果。

```
bool QSqlQuery.seek (self, int index, bool relative = False)
```

](qsqlresult.html)

[检索记录位置_index_如果有的话，和立场上所检索的记录的查询。第一个记录是在位置0 。请注意，查询必须是在](qsqlresult.html)[active](qsqlquery.html#isActive)状态[isSelect](qsqlquery.html#isSelect)（ ）必须在调用这个函数之前返回True。

If _relative_为False（默认值） ，则适用以下规则：

*   If _index_ is negative, the result is positioned before the first record and false is returned.
*   Otherwise, an attempt is made to move to the record at position _index_. If the record at position _index_ could not be retrieved, the result is positioned after the last record and false is returned. If the record is successfully retrieved, true is returned.

If _relative_是真的，应遵守下列规则：

*   If the result is currently positioned before the first record or on the first record, and _index_ is negative, there is no change, and false is returned.
*   If the result is currently located after the last record, and _index_ is positive, there is no change, and false is returned.
*   If the result is currently located somewhere in the middle, and the relative offset _index_ moves the result below zero, the result is positioned before the first record and false is returned.
*   Otherwise, an attempt is made to move to the record _index_ records ahead of the current record (or _index_ records behind the current record if _index_ is negative). If the record at offset _index_ could not be retrieved, the result is positioned after the last record if _index_ &gt;= 0, (or before the first record if _index_ is negative), and false is returned. If the record is successfully retrieved, true is returned.

**See also** [next](qsqlquery.html#next)（ ）[previous](qsqlquery.html#previous)（ ）[first](qsqlquery.html#first)（ ）[last](qsqlquery.html#last)（ ）[at](qsqlquery.html#at)（ ）[isActive](qsqlquery.html#isActive)（）和[isValid](qsqlquery.html#isValid)（ ） 。

```
QSqlQuery.setForwardOnly (self, bool forward)
```

设置只进模式_forward_。如果_forward_是真的，只[next](qsqlquery.html#next)（）和[seek](qsqlquery.html#seek)（ ）与正面的价值观，是允许的导航结果。

只正向模式即可（这取决于驱动程序）更多的内存效率，因为结果并不需要被缓存。它也将提高某些数据库的性能。对于这是真的，你必须调用`setForwardOnly()`查询准备或执行之前。需要注意的是，需要一个查询和数据库的构造函数可以执行查询。

只正向模式默认是关闭的。

前冲只为False是一个建议的数据库引擎，它拥有最终决定权在结果集是否是只向前或滚动。[isForwardOnly](qsqlquery.html#isForwardOnly)（ ）将总是返回结果集的正确状态。

**Note:**调用setForwardOnly后执行的查询会导致意想不到的结果充其量和崩溃在最坏的情况。

**See also** [isForwardOnly](qsqlquery.html#isForwardOnly)（ ）[next](qsqlquery.html#next)（ ）[seek](qsqlquery.html#seek)（）和[QSqlResult.setForwardOnly](qsqlresult.html#setForwardOnly)（ ） 。

```
QSqlQuery.setNumericalPrecisionPolicy (self, QSql.NumericalPrecisionPolicy precisionPolicy)
```

指示数据库驱动程序返回的数值由指定的精度_precisionPolicy_。

Oracle驱动程序，例如，可以检索数字值作为字符串来防止精度损失。如果精度高不要紧，使用此方法绕过字符串转换来提高执行速度。

注意：不支持用低精度取数值的驱动程序将忽略精度政策。您可以使用[QSqlDriver.hasFeature](qsqldriver.html#hasFeature)（ ）来找出驱动程序是否支持此功能。

注意：设置精度策略不影响当前活动的查询。通话[exec_](qsqlquery.html#exec)（[QString](qstring.html)）或[prepare](qsqlquery.html#prepare)（） ，以激活该策略。

**See also** [QSql.NumericalPrecisionPolicy](qsql.html#NumericalPrecisionPolicy-enum)和[numericalPrecisionPolicy](qsqlquery.html#numericalPrecisionPolicy)（ ） 。

```
int QSqlQuery.size (self)
```

返回结果的大小（返回的行数） ，或-1，如果大小无法确定，或者如果数据库不支持报告有关查询大小的信息。请注意，对于非`SELECT`报表（[isSelect](qsqlquery.html#isSelect)（ ）返回False ） ，大小（ ）将返回-1 。如果查询不活跃（[isActive](qsqlquery.html#isActive)（ ）返回False ） ，则返回-1。

要确定一个非受影响的行数`SELECT`声明中，使用[numRowsAffected](qsqlquery.html#numRowsAffected)（ ） 。

**See also** [isActive](qsqlquery.html#isActive)（ ）[numRowsAffected](qsqlquery.html#numRowsAffected)（）和[QSqlDriver.hasFeature](qsqldriver.html#hasFeature)（ ） 。

```
QVariant QSqlQuery.value (self, int i)
```

返回字段的值_index_在当前的记录。

该字段使用的文本编号从左至右`SELECT`声明中，例如在

```
 SELECT forename, surname FROM people;

```

场0`forename`和现场1`surname`。运用`SELECT *`不建议，因为在查询中字段的顺序是不确定的。

无效的[QVariant](qvariant.html)返回如果场_index_不存在，如果查询是无效的，或者如果该查询被定位在一个无效的记录。

**See also** [previous](qsqlquery.html#previous)（ ）[next](qsqlquery.html#next)（ ）[first](qsqlquery.html#first)（ ）[last](qsqlquery.html#last)（ ）[seek](qsqlquery.html#seek)（ ）[isActive](qsqlquery.html#isActive)（）和[isValid](qsqlquery.html#isValid)（ ） 。