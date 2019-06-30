# QSqlDriver Class Reference

## [[QtSql](index.htm) module]

该QSqlDriver类是用于访问特定的SQL数据库的抽象基类。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum DriverFeature { Transactions, QuerySize, BLOB, Unicode, ..., MultipleResultSets }`
*   `enum IdentifierType { FieldName, TableName }`
*   `enum StatementType { WhereStatement, SelectStatement, UpdateStatement, InsertStatement, DeleteStatement }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `bool beginTransaction (self)`
*   `close (self)`
*   `bool commitTransaction (self)`
*   `QSqlResult createResult (self)`
*   `QString escapeIdentifier (self, QString identifier, IdentifierType type)`
*   `QString formatValue (self, QSqlField field, bool trimStrings = False)`
*   `QVariant handle (self)`
*   `bool hasFeature (self, DriverFeature f)`
*   `bool isIdentifierEscaped (self, QString identifier, IdentifierType type)`
*   `bool isIdentifierEscapedImplementation (self, QString identifier, IdentifierType type)`
*   `bool isOpen (self)`
*   `bool isOpenError (self)`
*   `QSqlError lastError (self)`
*   `QSql.NumericalPrecisionPolicy numericalPrecisionPolicy (self)`
*   `bool open (self, QString db, QString user = QString(), QString password = QString(), QString host = QString(), int port = -1, QString options = QString())`
*   `QSqlIndex primaryIndex (self, QString tableName)`
*   `QSqlRecord record (self, QString tableName)`
*   `bool rollbackTransaction (self)`
*   `setLastError (self, QSqlError e)`
*   `setNumericalPrecisionPolicy (self, QSql.NumericalPrecisionPolicy precisionPolicy)`
*   `setOpen (self, bool o)`
*   `setOpenError (self, bool e)`
*   `QString sqlStatement (self, StatementType type, QString tableName, QSqlRecord rec, bool preparedStatement)`
*   `QString stripDelimiters (self, QString identifier, IdentifierType type)`
*   `QString stripDelimitersImplementation (self, QString identifier, IdentifierType type)`
*   `QStringList subscribedToNotifications (self)`
*   `QStringList subscribedToNotificationsImplementation (self)`
*   `bool subscribeToNotification (self, QString name)`
*   `bool subscribeToNotificationImplementation (self, QString name)`
*   `QStringList tables (self, QSql.TableType tableType)`
*   `bool unsubscribeFromNotification (self, QString name)`
*   `bool unsubscribeFromNotificationImplementation (self, QString name)`

### Qt Signals

*   `void notification (const QString&)`

* * *

## Detailed Description

该QSqlDriver类是用于访问特定的SQL数据库的抽象基类。

这个类不应该直接使用。使用[QSqlDatabase](qsqldatabase.html)代替。

如果你想创建自己的SQL驱动程序，你可以继承这个类，并重新实现它的纯虚函数，而且你需要那些虚函数。看[How to Write Your Own Database Driver](index.htm#how-to-write-your-own-database-driver)了解更多信息。

* * *

## Type Documentation

```
QSqlDriver.DriverFeature
```

此枚举包含的功能驱动程序可能支持的列表。使用[hasFeature](qsqldriver.html#hasFeature)（ ）来查询功能是否支持与否。

| Constant | Value | Description |
| --- | --- | --- |
| `QSqlDriver.Transactions` | `0` | 驱动程序是否支持SQL交易。 |
| `QSqlDriver.QuerySize` | `1` | 数据库是否能够报告一个查询的大小。请注意，某些数据库不支持返回查询的大小（即返回的行数） ，在这种情况下，[QSqlQuery.size](qsqlquery.html#size)（ ）将返回-1 。 |
| `QSqlDriver.BLOB` | `2` | 驱动程序是否支持二进制大对象字段。 |
| `QSqlDriver.Unicode` | `3` | 驱动程序是否支持Unicode字符串，如果数据库服务器一样。 |
| `QSqlDriver.PreparedQueries` | `4` | 驱动程序是否支持准备好的查询执行。 |
| `QSqlDriver.NamedPlaceholders` | `5` | 驱动程序是否支持使用命名佔位符。 |
| `QSqlDriver.PositionalPlaceholders` | `6` | 驱动程序是否支持使用位置佔位符。 |
| `QSqlDriver.LastInsertId` | `7` | 驱动程序是否支持返回的最后一行感动的Id 。 |
| `QSqlDriver.BatchOperations` | `8` | 无论是驱动程序支持批处理操作，请参阅[QSqlQuery.execBatch](qsqlquery.html#execBatch)（ ） |
| `QSqlDriver.SimpleLocking` | `9` | 无论是驾驶者不允许在表上写锁，而其他的查询有它的读锁。 |
| `QSqlDriver.LowPrecisionNumbers` | `10` | 驱动程序是否允许使用低精度取数值。 |
| `QSqlDriver.EventNotifications` | `11` | 驱动程序是否支持数据库事件通知。 |
| `QSqlDriver.FinishQuery` | `12` | 该驱动程序是否可以做任何低级别的资源清理时[QSqlQuery.finish](qsqlquery.html#finish)（）被调用。 |
| `QSqlDriver.MultipleResultSets` | `13` | 该驱动程序是否可以访问批处理语句或存储过程返回多个结果集。 |

有关支持的功能的详细信息可以在被发现[Qt SQL driver](index.htm)文档。

**See also** [hasFeature](qsqldriver.html#hasFeature)（ ） 。

```
QSqlDriver.IdentifierType
```

此枚举包含的SQL标识符类型的列表。

| Constant | Value | Description |
| --- | --- | --- |
| `QSqlDriver.FieldName` | `0` | 一个SQL字段名 |
| `QSqlDriver.TableName` | `1` | 一个SQL表名 |

```
QSqlDriver.StatementType
```

此枚举包含SQL语句（或语句）的列表类型的驱动程序可以创建。

| Constant | Value | Description |
| --- | --- | --- |
| `QSqlDriver.WhereStatement` | `0` | 一个SQL`WHERE`语句（例如，`WHERE f = 5`） 。 |
| `QSqlDriver.SelectStatement` | `1` | 一个SQL`SELECT`语句（例如，`SELECT f FROM t`） 。 |
| `QSqlDriver.UpdateStatement` | `2` | 一个SQL`UPDATE`语句（例如，`UPDATE TABLE t set f = 1`） 。 |
| `QSqlDriver.InsertStatement` | `3` | 一个SQL`INSERT`语句（例如，`INSERT INTO t (f) values (1)`） 。 |
| `QSqlDriver.DeleteStatement` | `4` | 一个SQL`DELETE`语句（例如，`DELETE FROM t`） 。 |

**See also** [sqlStatement](qsqldriver.html#sqlStatement)（ ） 。

* * *

## Method Documentation

```
QSqlDriver.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的驱动程序给定的_parent_。

```
bool QSqlDriver.beginTransaction (self)
```

这个函数被调用来开始一个事务。如果成功，则返回True，否则返回False 。默认实现不执行任何操作并返回False 。

**See also** [commitTransaction](qsqldriver.html#commitTransaction)（）和[rollbackTransaction](qsqldriver.html#rollbackTransaction)（ ） 。

```
QSqlDriver.close (self)
```

这种方法是抽象的，应在任何子类中重新实现。

派生类必须以关闭数据库连接重新实现这个纯虚函数。返回成功，假的真失败。

**See also** [open](qsqldriver.html#open)（）和[setOpen](qsqldriver.html#setOpen)（ ） 。

```
bool QSqlDriver.commitTransaction (self)
```

这个函数被调用来提交事务。如果成功，则返回True，否则返回False 。默认实现不执行任何操作并返回False 。

**See also** [beginTransaction](qsqldriver.html#beginTransaction)（）和[rollbackTransaction](qsqldriver.html#rollbackTransaction)（ ） 。

```
QSqlResult QSqlDriver.createResult (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

](qsqlresult.html)

[创建数据库在一个空的SQL结果。派生类必须重新实现这个函数，并返回一个](qsqlresult.html)[QSqlResult](qsqlresult.html)对象适合自己的数据库给调用者。

```
QString QSqlDriver.escapeIdentifier (self, QString identifier, IdentifierType type)
```

返回_identifier_根据数据库的规则逃过一劫。_identifier_可以是一个表名或字段名，依赖于_type_。

默认实现不执行任何操作。

**See also** [isIdentifierEscaped](qsqldriver.html#isIdentifierEscaped)（ ） 。

```
QString QSqlDriver.formatValue (self, QSqlField field, bool trimStrings = False)
```

返回的字符串表示形式_field_值的数据库。这被使用，例如，建设INSERT和UPDATE语句时。

缺省的实现返回格式化为根据以下规则的字符串的值：

*   If _field_ is character data, the value is returned enclosed in single quotation marks, which is appropriate for many SQL databases. Any embedded single-quote characters are escaped (replaced with two single-quote characters). If _trimStrings_ is true (the default is false), all trailing whitespace is trimmed from the field.
*   If _field_ is date/time data, the value is formatted in ISO format and enclosed in single quotation marks. If the date/time data is invalid, "NULL" is returned.
*   If _field_ is [bytearray](qbytearray.html) data, and the driver can edit binary fields, the value is formatted as a hexadecimal string.
*   For any other field type, toString() is called on its value and the result of this is returned.

**See also** [QVariant.toString](qvariant.html#toString)（ ） 。

```
QVariant QSqlDriver.handle (self)
```

返回低水平数据库句柄包裹在一个[QVariant](qvariant.html)或无效的变体，如果没有手柄。

**Warning:**使用这种具有极处的照顾和只有当你知道你在做什么。

**Warning:**这里返回的句柄可以成为一个过时的指针，如果连接被修改（例如，如果您关闭了连接） 。

**Warning:**手柄可以是NULL如果连接尚未打开。

这里返回的句柄是依赖于数据库的，你应该访问它之前，查询变量的类型名称。

本示例检索句柄到sqlite的连接：

```
 [QSqlDatabase](qsqldatabase.html) db = ...;
 [QVariant](qvariant.html) v = db.driver()->handle();
 if (v.isValid() && qstrcmp(v.typeName(), "sqlite3*") == 0) {
     // v.data() returns a pointer to the handle
     sqlite3 *handle = *static_cast<sqlite3 **>(v.data());
     if (handle != 0) { // check that it is not NULL
         ...
     }
 }

```

这段代码返回的句柄PostgreSQL或MySQL ：

```
 if (qstrcmp(v.typeName(), "PGconn*") == 0) {
     PGconn *handle = *static_cast<PGconn **>(v.data());
     if (handle != 0) ...
 }

 if (qstrcmp(v.typeName(), "MYSQL*") == 0) {
     MYSQL *handle = *static_cast<MYSQL **>(v.data());
     if (handle != 0) ...
 }

```

**See also** [QSqlResult.handle](qsqlresult.html#handle)（ ） 。

```
bool QSqlDriver.hasFeature (self, DriverFeature f)
```

这种方法是抽象的，应在任何子类中重新实现。

如果驱动程序支持功能，则返回True_feature_否则返回False 。

请注意，某些数据库需[open](qsqldriver.html#open)（ ）在此之前才能确定。

**See also** [DriverFeature](qsqldriver.html#DriverFeature-enum)。

```
bool QSqlDriver.isIdentifierEscaped (self, QString identifier, IdentifierType type)
```

返回是否_identifier_根据该数据库的规则逃脱。_identifier_可以是一个表名或字段名，依赖于_type_。

**Warning:**因为二进制兼容性的限制，这个功能是不是虚拟的。如果你想提供自己的实现在你的[QSqlDriver](qsqldriver.html)子类，重新实现[isIdentifierEscapedImplementation](qsqldriver.html#isIdentifierEscapedImplementation)（）槽在你的子类来代替。该isIdentifierEscapedFunction （ ）会动态侦测插槽，并调用它。

**See also** [stripDelimiters](qsqldriver.html#stripDelimiters)（）和[escapeIdentifier](qsqldriver.html#escapeIdentifier)（ ） 。

```
bool QSqlDriver.isIdentifierEscapedImplementation (self, QString identifier, IdentifierType type)
```

这种方法也是一个Qt槽与C + +的签名`bool isIdentifierEscapedImplementation(const QString&,QSqlDriver::IdentifierType) const`。

此插槽是否返回_identifier_根据该数据库的规则逃脱。_identifier_可以是一个表名或字段名，依赖于_type_。

因为二进制兼容性的限制，[isIdentifierEscaped](qsqldriver.html#isIdentifierEscaped)（ ）函数（在Qt的4.5中引入）是不是虚拟的。相反，[isIdentifierEscaped](qsqldriver.html#isIdentifierEscaped)（ ）将动态检测并调用_this_插槽。默认实现假设转义/分隔符是双引号。重新实现这个插槽在自己的[QSqlDriver](qsqldriver.html)如果您的数据库引擎使用不同的分隔符。

此功能被引入Qt的4.6 。

**See also** [isIdentifierEscaped](qsqldriver.html#isIdentifierEscaped)（ ） 。

```
bool QSqlDriver.isOpen (self)
```

返回True如果数据库连接处于打开状态，否则返回False 。

```
bool QSqlDriver.isOpenError (self)
```

返回True如果有一个错误打开数据库连接，否则返回False 。

```
QSqlError QSqlDriver.lastError (self)
```

[](qsqlerror.html)

[返回](qsqlerror.html)[QSqlError](qsqlerror.html)对象，该对象包含有关数据库上发生的最后一个错误信息。

**See also** [setLastError](qsqldriver.html#setLastError)（ ） 。

```
QSql.NumericalPrecisionPolicy QSqlDriver.numericalPrecisionPolicy (self)
```

[

返回数据库连接的当前默认精度的政策。

此功能被引入Qt的4.6 。

](qsql.html#NumericalPrecisionPolicy-enum)

[**See also**](qsql.html#NumericalPrecisionPolicy-enum) [QSql.NumericalPrecisionPolicy](qsql.html#NumericalPrecisionPolicy-enum)，[setNumericalPrecisionPolicy](qsqldriver.html#setNumericalPrecisionPolicy)（ ）[QSqlQuery.numericalPrecisionPolicy](qsqlquery.html#numericalPrecisionPolicy)（）和[QSqlQuery.setNumericalPrecisionPolicy](qsqlquery.html#setNumericalPrecisionPolicy)（ ） 。

```
bool QSqlDriver.open (self, QString db, QString user = QString(), QString password = QString(), QString host = QString(), int port = -1, QString options = QString())
```

这种方法是抽象的，应在任何子类中重新实现。

派生类必须重新实现这个纯虚函数打开的数据库的数据库连接_db_，使用的用户名_user_，密码_password_，主机_host_，端口_port_和连接选项_options_。

该函数必须返回成功，假的真失败。

**See also** [setOpen](qsqldriver.html#setOpen)（ ） 。

```
QSqlIndex QSqlDriver.primaryIndex (self, QString tableName)
```

[](qsqlindex.html)

[返回表的主索引_tableName_。返回一个空](qsqlindex.html)[QSqlIndex](qsqlindex.html)如果表没有主索引。默认实现返回一个空的索引。

```
QSqlRecord QSqlDriver.record (self, QString tableName)
```

[](qsqlrecord.html)

[返回](qsqlrecord.html)[QSqlRecord](qsqlrecord.html)填充在表中的字段的名称_tableName_。如果没有这样的表存在，则返回一个空的记录。默认实现返回一个空的记录。

```
bool QSqlDriver.rollbackTransaction (self)
```

这个函数被调用来回滚事务。如果成功，则返回True，否则返回False 。默认实现不执行任何操作并返回False 。

**See also** [beginTransaction](qsqldriver.html#beginTransaction)（）和[commitTransaction](qsqldriver.html#commitTransaction)（ ） 。

```
QSqlDriver.setLastError (self, QSqlError e)
```

这个函数是用来设置的最后一个错误的值，_error_，发生在数据库上。

**See also** [lastError](qsqldriver.html#lastError)（ ） 。

```
QSqlDriver.setNumericalPrecisionPolicy (self, QSql.NumericalPrecisionPolicy precisionPolicy)
```

设置使用此驱动程序来创建查询的默认数值精度的政策_precisionPolicy_。

注意：默认精度策略设置来_precisionPolicy_不影响任何当前活动的查询。

此功能被引入Qt的4.6 。

**See also** [QSql.NumericalPrecisionPolicy](qsql.html#NumericalPrecisionPolicy-enum)，[numericalPrecisionPolicy](qsqldriver.html#numericalPrecisionPolicy)（ ）[QSqlQuery.setNumericalPrecisionPolicy](qsqlquery.html#setNumericalPrecisionPolicy)（）和[QSqlQuery.numericalPrecisionPolicy](qsqlquery.html#numericalPrecisionPolicy)（ ） 。

```
QSqlDriver.setOpen (self, bool o)
```

这个函数设置数据库的打开状态以_open_。派生类可以使用此功能来报告的状态[open](qsqldriver.html#open)（ ） 。

**See also** [open](qsqldriver.html#open)（）和[setOpenError](qsqldriver.html#setOpenError)（ ） 。

```
QSqlDriver.setOpenError (self, bool e)
```

这个函数设置数据库的打开错误状态_error_。派生类可以使用此功能来报告的状态[open](qsqldriver.html#open)（ ） 。注意，如果_error_是真正的数据库的打开状态设置为关闭（即，[isOpen](qsqldriver.html#isOpen)（ ）返回False ） 。

**See also** [isOpenError](qsqldriver.html#isOpenError)（ ）[open](qsqldriver.html#open)（）和[setOpen](qsqldriver.html#setOpen)（ ） 。

```
QString QSqlDriver.sqlStatement (self, StatementType type, QString tableName, QSqlRecord rec, bool preparedStatement)
```

返回类型的SQL语句_type_为表_tableName_从数值_rec_。如果_preparedStatement_为True，则字符串将包含佔位符，而不是价值。

这种方法可以用来处理表，而不必担心依赖于数据库的SQL方言。对于非预处理语句，该值将被正确地转义。

```
QString QSqlDriver.stripDelimiters (self, QString identifier, IdentifierType type)
```

返回_identifier_带的前缘和后分隔符取出，_identifier_可以是一个表名或字段名，依赖于_type_。如果_identifier_没有开头和结尾的分隔符，_identifier_无需修改被返回。

**Warning:**因为二进制兼容性的限制，这个功能是不是虚拟的，如果你想提供自己的实现在你的[QSqlDriver](qsqldriver.html)子类，重新实现[stripDelimitersImplementation](qsqldriver.html#stripDelimitersImplementation)（）槽在你的子类来代替。该stripDelimiters （ ）函数将动态检测插槽，并调用它。

此功能被引入Qt的4.5 。

**See also** [isIdentifierEscaped](qsqldriver.html#isIdentifierEscaped)（ ） 。

```
QString QSqlDriver.stripDelimitersImplementation (self, QString identifier, IdentifierType type)
```

这种方法也是一个Qt槽与C + +的签名`QString stripDelimitersImplementation(const QString&,QSqlDriver::IdentifierType) const`。

这个插槽回报_identifier_带的前缘和后分隔符取出，_identifier_可以是一个表名或字段名，依赖于_type_。如果_identifier_没有开头和结尾的分隔符，_identifier_无需修改被返回。

因为二进制兼容性的限制，在[stripDelimiters](qsqldriver.html#stripDelimiters)（ ）函数（在Qt的4.5中引入）是不是虚拟的。相反，[stripDelimiters](qsqldriver.html#stripDelimiters)（ ）将动态检测并调用_this_插槽。它通常不需要重新实现此插槽。

此功能被引入Qt的4.6 。

**See also** [stripDelimiters](qsqldriver.html#stripDelimiters)（ ） 。

```
QStringList QSqlDriver.subscribedToNotifications (self)
```

返回当前订阅的事件通知的名称列表。

**Warning:**因为二进制兼容性的限制，这个功能是不是虚拟的。如果您想提供事件通知的支持在自己的[QSqlDriver](qsqldriver.html)子类，重新实现[subscribedToNotificationsImplementation](qsqldriver.html#subscribedToNotificationsImplementation)（）槽在你的子类来代替。该subscribedToNotifications （ ）函数将动态检测插槽，并调用它。

此功能被引入Qt的4.4 。

**See also** [subscribeToNotification](qsqldriver.html#subscribeToNotification)（）和[unsubscribeFromNotification](qsqldriver.html#unsubscribeFromNotification)（ ） 。

```
QStringList QSqlDriver.subscribedToNotificationsImplementation (self)
```

这种方法也是一个Qt槽与C + +的签名`QStringList subscribedToNotificationsImplementation() const`。

返回当前订阅的事件通知的名称列表。

重新实现这个插槽来提供自己的[QSqlDriver](qsqldriver.html)继承与事件通知的支持，因为二进制兼容性的限制，[subscribedToNotifications](qsqldriver.html#subscribedToNotifications)（ ）函数（在Qt的4.4中引入）是不是虚拟的。相反，[subscribedToNotifications](qsqldriver.html#subscribedToNotifications)（ ）将动态检测并调用_this_插槽。默认实现返回一个空[QStringList](qstringlist.html)。

此功能被引入Qt的4.4 。

**See also** [subscribedToNotifications](qsqldriver.html#subscribedToNotifications)（ ） 。

```
bool QSqlDriver.subscribeToNotification (self, QString name)
```

调用此函数来订阅事件通知从数据库中。_name_标识事件的通知。

如果成功，则返回True，否则返回False 。

该数据库必须处于打开状态时，此函数被调用。当数据库是通过调用关闭[close](qsqldriver.html#close)（ ）所有订阅事件通知将自动取消订阅。请注意，调用[open](qsqldriver.html#open)（ ）在一个已经打开的数据库可能会导致隐[close](qsqldriver.html#close)（ ）被调用，这将导致驱动程序的所有事件通知退订。

当一个事件通知确定_name_张贴由数据库的[notification](qsqldriver.html#notification)（）信号被发射。

**Warning:**因为二进制兼容性的限制，这个功能是不是虚拟的。如果您想提供事件通知的支持在自己的[QSqlDriver](qsqldriver.html)子类，重新实现[subscribeToNotificationImplementation](qsqldriver.html#subscribeToNotificationImplementation)（）槽在你的子类来代替。该subscribeToNotification （ ）函数将动态检测插槽，并调用它。

此功能被引入Qt的4.4 。

**See also** [unsubscribeFromNotification](qsqldriver.html#unsubscribeFromNotification)（ ）[subscribedToNotifications](qsqldriver.html#subscribedToNotifications)（）和[QSqlDriver.hasFeature](qsqldriver.html#hasFeature)（ ） 。

```
bool QSqlDriver.subscribeToNotificationImplementation (self, QString name)
```

这种方法也是一个Qt槽与C + +的签名`bool subscribeToNotificationImplementation(const QString&)`。

这个槽被调用来订阅事件通知从数据库中。_name_标识事件的通知。

如果成功，则返回True，否则返回False 。

该数据库必须在此公开_slot_被调用。当数据库是通过调用关闭[close](qsqldriver.html#close)（ ）所有订阅事件通知将自动取消订阅。请注意，调用[open](qsqldriver.html#open)（ ）在一个已经打开的数据库可能会导致隐[close](qsqldriver.html#close)（ ）被调用，这将导致驱动程序的所有事件通知退订。

当一个事件通知确定_name_张贴由数据库的[notification](qsqldriver.html#notification)（）信号被发射。

重新实现这个插槽来提供自己的[QSqlDriver](qsqldriver.html)继承与事件通知的支持，因为二进制兼容性的限制，[subscribeToNotification](qsqldriver.html#subscribeToNotification)（ ）函数（在Qt的4.4中引入）是不是虚拟的。相反，[subscribeToNotification](qsqldriver.html#subscribeToNotification)（ ）将动态检测并调用_this_插槽。默认实现不执行任何操作并返回False 。

此功能被引入Qt的4.4 。

**See also** [subscribeToNotification](qsqldriver.html#subscribeToNotification)（ ） 。

```
QStringList QSqlDriver.tables (self, QSql.TableType tableType)
```

返回该数据库中的表的名称的列表。默认实现返回一个空列表。

该_tableType_参数说明什么类型的表应该返回。由于二进制兼容性，该字符串包含枚举QSql.TableTypes作为文本的价值。一个空字符串应被视为[QSql.Tables](qsql.html#TableType-enum)为了向后兼容。

```
bool QSqlDriver.unsubscribeFromNotification (self, QString name)
```

此功能称为从数据库事件通知退订。_name_标识事件的通知。

如果成功，则返回True，否则返回False 。

该数据库必须处于打开状态时，此函数被调用。所有订阅的事件通知是从时自动取消订阅的[close](qsqldriver.html#close)（ ）函数被调用。

后调用_this_功能[notification](qsqldriver.html#notification)（）信号将不再当一个事件通知确定了发射_name_张贴由数据库。

**Warning:**因为二进制兼容性的限制，这个功能是不是虚拟的。如果您想提供事件通知的支持在自己的[QSqlDriver](qsqldriver.html)子类，重新实现[unsubscribeFromNotificationImplementation](qsqldriver.html#unsubscribeFromNotificationImplementation)（）槽在你的子类来代替。该unsubscribeFromNotification （ ）函数将动态检测插槽，并调用它。

此功能被引入Qt的4.4 。

**See also** [subscribeToNotification](qsqldriver.html#subscribeToNotification)（）和[subscribedToNotifications](qsqldriver.html#subscribedToNotifications)（ ） 。

```
bool QSqlDriver.unsubscribeFromNotificationImplementation (self, QString name)
```

这种方法也是一个Qt槽与C + +的签名`bool unsubscribeFromNotificationImplementation(const QString&)`。

这个槽被调用从数据库事件通知退订。_name_标识事件的通知。

如果成功，则返回True，否则返回False 。

该数据库时，必须打开_this_槽被调用。所有订阅的事件通知是从时自动取消订阅的[close](qsqldriver.html#close)（ ）函数被调用。

后调用_this_在插槽[notification](qsqldriver.html#notification)（）信号将不再当一个事件通知确定了发射_name_张贴由数据库。

重新实现这个插槽来提供自己的[QSqlDriver](qsqldriver.html)继承与事件通知的支持，因为二进制兼容性的限制，[unsubscribeFromNotification](qsqldriver.html#unsubscribeFromNotification)（ ）函数（在Qt的4.4中引入）是不是虚拟的。相反，[unsubscribeFromNotification](qsqldriver.html#unsubscribeFromNotification)（ ）将动态检测并调用_this_插槽。默认实现不执行任何操作并返回False 。

此功能被引入Qt的4.4 。

**See also** [unsubscribeFromNotification](qsqldriver.html#unsubscribeFromNotification)（ ） 。

* * *

## Qt Signal Documentation

```
void notification (const QString&)
```

这是该信号的默认超载。

这个信号被发射时的数据库职位为驾驶员所预订的事件通知。_name_标识事件的通知。

此功能被引入Qt的4.4 。

**See also** [subscribeToNotification](qsqldriver.html#subscribeToNotification)（ ） 。