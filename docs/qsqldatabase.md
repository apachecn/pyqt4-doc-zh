# QSqlDatabase Class Reference

## [[QtSql](index.htm) module]

该QSqlDatabase类表示一个到数据库的连接。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QSqlDatabase other)`
*   `__init__ (self, QString type)`
*   `__init__ (self, QSqlDriver driver)`
*   `close (self)`
*   `bool commit (self)`
*   `QString connectionName (self)`
*   `QString connectOptions (self)`
*   `QString databaseName (self)`
*   `QSqlDriver driver (self)`
*   `QString driverName (self)`
*   `QSqlQuery exec_ (self, QString query = QString())`
*   `QString hostName (self)`
*   `bool isOpen (self)`
*   `bool isOpenError (self)`
*   `bool isValid (self)`
*   `QSqlError lastError (self)`
*   `QSql.NumericalPrecisionPolicy numericalPrecisionPolicy (self)`
*   `bool open (self)`
*   `bool open (self, QString user, QString password)`
*   `QString password (self)`
*   `int port (self)`
*   `QSqlIndex primaryIndex (self, QString tablename)`
*   `QSqlRecord record (self, QString tablename)`
*   `bool rollback (self)`
*   `setConnectOptions (self, QString options = QString())`
*   `setDatabaseName (self, QString name)`
*   `setHostName (self, QString host)`
*   `setNumericalPrecisionPolicy (self, QSql.NumericalPrecisionPolicy precisionPolicy)`
*   `setPassword (self, QString password)`
*   `setPort (self, int p)`
*   `setUserName (self, QString name)`
*   `QStringList tables (self, QSql.TableType type = QSql.Tables)`
*   `bool transaction (self)`
*   `QString userName (self)`

### Static Methods

*   `QSqlDatabase addDatabase (QString type, QString connectionName = QLatin1String(QSqlDatabase.defaultConnection))`
*   `QSqlDatabase addDatabase (QSqlDriver driver, QString connectionName = QLatin1String(QSqlDatabase.defaultConnection))`
*   `QSqlDatabase cloneDatabase (QSqlDatabase other, QString connectionName)`
*   `QStringList connectionNames ()`
*   `bool contains (QString connectionName = QLatin1String(QSqlDatabase.defaultConnection))`
*   `QSqlDatabase database (QString connectionName = QLatin1String(QSqlDatabase.defaultConnection), bool open = True)`
*   `QStringList drivers ()`
*   `bool isDriverAvailable (QString name)`
*   `registerSqlDriver (QString name, QSqlDriverCreatorBase creator)`
*   `removeDatabase (QString connectionName)`

* * *

## Detailed Description

该QSqlDatabase类表示一个到数据库的连接。

该QSqlDatabase类提供了通过连接访问数据库的接口。 QSqlDatabase的实例代表连接。连接经由一个可访问数据库[supported database drivers](index.htm#supported-databases)，其衍生自[QSqlDriver](qsqldriver.html)。或者，您也可以从继承自己的数据库驱动程序[QSqlDriver](qsqldriver.html)。看[How to Write Your Own Database Driver](index.htm#how-to-write-your-own-database-driver)了解更多信息。

通过调用静态的创建一个连接（即QSqlDatabase的实例）[addDatabase](qsqldatabase.html#addDatabase)（ ）函数，在这里您可以指定[the driver or type of driver](index.htm#supported-databases)使用（比如，你要访问什么样的数据库？ ）和一个连接名称。一个连接是由它自己的名字众所周知，_not_由数据库的名称将其连接到。你可以有多个连接到一个数据库。 QSqlDatabase还支持的概念_default_连接，这是未命名的连接。要创建默认的连接，当你调用不通过连接名称参数[addDatabase](qsqldatabase.html#addDatabase)（ ） 。随后，当你调用任何静态成员函数，它的连接名称的说法，如果你不通过连接名称参数，则假定为默认连接。下面的代码片断显示了如何创建并打开一个默认连接到PostgreSQL数据库：

```
     QSqlDatabase db = QSqlDatabase.addDatabase("QPSQL");
     db.setHostName("acidalia");
     db.setDatabaseName("customdb");
     db.setUserName("mojito");
     db.setPassword("J0a1m8");
     bool ok = db.open();

```

一旦QSqlDatabase对象已经创建，以设置连接参数[setDatabaseName](qsqldatabase.html#setDatabaseName)（ ）[setUserName](qsqldatabase.html#setUserName)（ ）[setPassword](qsqldatabase.html#setPassword)（ ）[setHostName](qsqldatabase.html#setHostName)（ ）[setPort](qsqldatabase.html#setPort)（）和[setConnectOptions](qsqldatabase.html#setConnectOptions)（ ） 。然后调用[open](qsqldatabase.html#open)（ ）来激活到数据库的物理连接。该连接不可用，直到你打开它。

上面定义的连接将是_default_连接，因为我们没有给一个连接名称[addDatabase()](qsqldatabase.html#addDatabase)。随后，您可以通过调用得到的默认连接[database](qsqldatabase.html#database)（ ）无连接名称参数：

```
     QSqlDatabase db = QSqlDatabase.database();

```

QSqlDatabase是一个值类。通过QSqlDatabase的一个实例数据库连接所做的更改将影响QSqlDatabase ，代表相同的连接其他实例。使用[cloneDatabase](qsqldatabase.html#cloneDatabase)（）来创建基于现有一个独立的数据库连接。

如果你创建多个数据库连接，为每一个指定一个唯一的连接名称，当你调用[addDatabase](qsqldatabase.html#addDatabase)（ ） 。使用[database](qsqldatabase.html#database)（ ）有一个连接名称来获取连接。使用[removeDatabase](qsqldatabase.html#removeDatabase)（ ）有一个连接名称删除的连接。如果您尝试删除其他QSqlDatabase对象引用的连接QSqlDatabase输出一个警告。使用[contains](qsqldatabase.html#contains)（ ），看看是否一个给定的连接名称为连接列表。

一旦建立了连接，你可以调用[tables](qsqldatabase.html#tables)（）来获取数据库中，调用表的列表[primaryIndex](qsqldatabase.html#primaryIndex)（）来获取一个表的主索引，并调用[record](qsqldatabase.html#record)（ ）来获取有关表的字段（例如，字段名）的元信息。

**Note:** [QSqlDatabase.exec](qsqldatabase.html#exec)（ ）已过时。使用[QSqlQuery.exec](qsqlquery.html#exec)（ ）来代替。

如果驱动程序支持的交易，使用[transaction](qsqldatabase.html#transaction)（ ）来启动一个事务，[commit](qsqldatabase.html#commit)（）或[rollback](qsqldatabase.html#rollback)（）来完成它。使用[hasFeature()](qsqldriver.html#hasFeature)请问如果驱动程序支持的交易。**Note:**当使用事务时，必须启动该交易在创建查询之前。

如果一个错误发生，[lastError](qsqldatabase.html#lastError)（ ）将返回有关它的信息。

获取可用的SQL驱动程序的名称与[drivers](qsqldatabase.html#drivers)（ ） 。检查与特定驱动程序的存在[isDriverAvailable](qsqldatabase.html#isDriverAvailable)（ ） 。如果您已经创建自己的自定义驱动程序，您必须进行注册[registerSqlDriver](qsqldatabase.html#registerSqlDriver)（ ） 。

* * *

## Method Documentation

```
QSqlDatabase.__init__ (self)
```

创建一个空的，无效的[QSqlDatabase](qsqldatabase.html)对象。使用[addDatabase](qsqldatabase.html#addDatabase)（ ）[removeDatabase](qsqldatabase.html#removeDatabase)（）和[database](qsqldatabase.html#database)（ ）来获取有效的[QSqlDatabase](qsqldatabase.html)对象。

```
QSqlDatabase.__init__ (self, QSqlDatabase other)
```

创建副本_other_。

```
QSqlDatabase.__init__ (self, QString type)
```

这是一个重载函数。

创建[QSqlDatabase](qsqldatabase.html)使用由所述的驱动程序连接_type_。如果_type_无法识别，数据库连接将没有任何功能。

目前可用的驱动器类型有：

| Driver Type | Description |
| --- | --- |
| QDB2 | IBM DB2 |
| QIBASE | Borland InterBase Driver |
| QMYSQL | MySQL Driver |
| QOCI | Oracle Call Interface Driver |
| QODBC | ODBC Driver (includes Microsoft SQL Server) |
| QPSQL | PostgreSQL Driver |
| QSQLITE | SQLite version 3 or above |
| QSQLITE2 | SQLite version 2 |
| QTDS | Sybase Adaptive Server |

额外的第三方驱动程序，包括您自己的自定义驱动程序，可以动态加载。

**See also** [SQL Database Drivers](index.htm)，[registerSqlDriver](qsqldatabase.html#registerSqlDriver)（）和[drivers](qsqldatabase.html#drivers)（ ） 。

```
QSqlDatabase.__init__ (self, QSqlDriver driver)
```

这是一个重载函数。

创建使用给定的数据库连接_driver_。

```
QSqlDatabase QSqlDatabase.addDatabase (QString type, QString connectionName = QLatin1String(QSqlDatabase.defaultConnection))
```

[

增加了一个数据库，以数据库连接使用的驱动程序的列表_type_和连接名称_connectionName_。如果已经存在一个名为数据库连接_connectionName_，则该连接被删除。

数据库连接是通过被称为_connectionName_。返回新添加的数据库连接。

](qsqldatabase.html)

[If _type_不可用或无法加载，](qsqldatabase.html)[isValid](qsqldatabase.html#isValid)（ ）返回False 。

If _connectionName_没有指定，则新的连接成为应用程序的默认连接，并随后调用[database](qsqldatabase.html#database)（ ）无连接名称参数将返回默认的连接。如果_connectionName_这里提供的，使用的数据库（_connectionName_）来检索连接。

**Warning:**如果您添加了具有相同名称的现有连接的连接，新的连接将会取代旧的。如果你调用这个函数一次以上，而无需指定_connectionName_，默认的连接将是一个替代。

使用连接之前，它必须被初始化。例如，调用一些或全部[setDatabaseName](qsqldatabase.html#setDatabaseName)（ ）[setUserName](qsqldatabase.html#setUserName)（ ）[setPassword](qsqldatabase.html#setPassword)（ ）[setHostName](qsqldatabase.html#setHostName)（ ）[setPort](qsqldatabase.html#setPort)（）和[setConnectOptions](qsqldatabase.html#setConnectOptions)（ ） ，最后是[open](qsqldatabase.html#open)（ ） 。

**Note:**这个功能是[thread-safe](index.htm#thread-safe)。

**See also** [database](qsqldatabase.html#database)（ ）[removeDatabase](qsqldatabase.html#removeDatabase)（）和[Threads and the SQL Module](index.htm#threads-and-the-sql-module)。

```
QSqlDatabase QSqlDatabase.addDatabase (QSqlDriver driver, QString connectionName = QLatin1String(QSqlDatabase.defaultConnection))
```

[](qsqldatabase.html)

[当你想创建一个数据库连接此重载很有用](qsqldatabase.html)[driver](qsqldriver.html)你实例化你自己。这可能是你自己的数据库驱动程序，或者你可能只需要自己实例化Qt的驱动力之一。如果你这样做，建议您在您的应用程序的驱动程序代码。例如，您可以创建自己的QPSQL驱动这样一个PostgreSQL连接：

```
 #include "qtdir/src/sql/drivers/psql/qsql_psql.cpp"

 PGconn *con = PQconnectdb("host=server user=bart password=simpson dbname=springfield");
 QPSQLDriver *drv =  new QPSQLDriver(con);
 [QSqlDatabase](qsqldatabase.html) db = [QSqlDatabase](qsqldatabase.html).addDatabase(drv); // becomes the new default connection
 [QSqlQuery](qsqlquery.html) query;
 query.exec_("SELECT NAME, ID FROM STAFF");
 ...

```

上面的代码设置了一个PostgreSQL连接并实例化一个QPSQLDriver对象。接下来，[addDatabase](qsqldatabase.html#addDatabase)（）被调用，以连接添加到已知的连接，这样它可用于通过Qt的SQL类。当驱动程序被实例化一个连接句柄（或一组手柄） ， Qt的假设你已经打开了数据库连接。

**Note:**我们假设`qtdir`是安装Qt的目录。这将拉动中所需要使用的PostgreSQL客户端库和实例化一个QPSQLDriver对象的代码，假设你有PostgreSQL的头放在你的头文件搜索路径。

请记住，你必须链接您的应用程序对数据库客户端库。确保客户端库是在你的链接器的搜索路径，并添加像这些行到你的`.pro`文件：

```
 unix:LIBS += -lpq
 win32:LIBS += libpqdll.lib

```

该方法描述的作品，所有提供的驱动程序。唯一的区别是在驱动程序构造器参数。下面是包含了Qt的驱动程序，其源代码文件，以及它们的构造函数的参数表：

| Driver | Class name | Constructor arguments | File to include |
| --- | --- | --- | --- |
| QPSQL | QPSQLDriver | PGconn *connection | `qsql_psql.cpp` |
| QMYSQL | QMYSQLDriver | MYSQL *connection | `qsql_mysql.cpp` |
| QOCI | QOCIDriver | OCIEnv *environment, OCISvcCtx *serviceContext | `qsql_oci.cpp` |
| QODBC | QODBCDriver | SQLHANDLE environment, SQLHANDLE connection | `qsql_odbc.cpp` |
| QDB2 | QDB2 | SQLHANDLE environment, SQLHANDLE connection | `qsql_db2.cpp` |
| QTDS | QTDSDriver | LOGINREC *loginRecord, DBPROCESS *dbProcess, const [QString](qstring.html) &hostName | `qsql_tds.cpp` |
| QSQLITE | QSQLiteDriver | sqlite *connection | `qsql_sqlite.cpp` |
| QIBASE | QIBaseDriver | isc_db_handle connection | `qsql_ibase.cpp` |

主机名称（或服务名称）正在建设中的QTDSDriver建立内部查询的新连接时需要。这是为了防止阻塞几个时[QSqlQuery](qsqlquery.html)物同时使用。

**Warning:**添加具有相同的连接名称与现有连接的数据库连接，使现有连接被新的所取代。

**Warning:**在SQL框架采用的所有权_driver_。它不能被删除。要删除连接，请使用[removeDatabase](qsqldatabase.html#removeDatabase)（ ） 。

**See also** [drivers](qsqldatabase.html#drivers)（ ） 。

```
QSqlDatabase QSqlDatabase.cloneDatabase (QSqlDatabase other, QString connectionName)
```

[](qsqldatabase.html)

[克隆数据库连接_other_和并将其存储为_connectionName_。所有从原始数据库的设置，例如](qsqldatabase.html)[databaseName](qsqldatabase.html#databaseName)（ ）[hostName](qsqldatabase.html#hostName)（ ）等，被复制的对面。什么都不做，如果_other_是一个无效的数据库。返回新创建的数据库连接。

**Note:**新的连接没有被打开。使用新的连接之前，你必须调用[open](qsqldatabase.html#open)（ ） 。

```
QSqlDatabase.close (self)
```

关闭数据库连接，释放佔用的所有资源和无效的任何现有[QSqlQuery](qsqlquery.html)所使用的数据库对象。

这也将影响到这个份[QSqlDatabase](qsqldatabase.html)对象。

**See also** [removeDatabase](qsqldatabase.html#removeDatabase)（ ） 。

```
bool QSqlDatabase.commit (self)
```

提交事务对数据库如果驱动程序支持事务和[transaction](qsqldatabase.html#transaction)（ ）已经启动。回报`true`如果操作成功。否则返回`false`。

**Note:**对于某些数据库，提交会失败，并返回`false`如果有一个[active query](qsqlquery.html#isActive)使用该数据库的`SELECT`。使查询[inactive](qsqlquery.html#isActive)在做之前提交。

Call [lastError](qsqldatabase.html#lastError)（ ）以获取有关错误的信息。

**See also** [QSqlQuery.isActive](qsqlquery.html#isActive)（ ）[QSqlDriver.hasFeature](qsqldriver.html#hasFeature)（）和[rollback](qsqldatabase.html#rollback)（ ） 。

```
QString QSqlDatabase.connectionName (self)
```

返回连接的名称，这可能是空的。**Note:**连接名称是不[database name](qsqldatabase.html#databaseName)。

此功能被引入Qt的4.4 。

**See also** [addDatabase](qsqldatabase.html#addDatabase)（ ） 。

```
QStringList QSqlDatabase.connectionNames ()
```

返回一个包含所有连接的名称的列表。

**Note:**这个功能是[thread-safe](index.htm#thread-safe)。

**See also** [contains](qsqldatabase.html#contains)（ ）[database](qsqldatabase.html#database)（）和[Threads and the SQL Module](index.htm#threads-and-the-sql-module)。

```
QString QSqlDatabase.connectOptions (self)
```

返回用于该连接的连接选项字符串。该字符串可能是空的。

**See also** [setConnectOptions](qsqldatabase.html#setConnectOptions)（ ） 。

```
bool QSqlDatabase.contains (QString connectionName = QLatin1String(QSqlDatabase.defaultConnection))
```

返回True如果数据库连接的列表中包含_connectionName_否则返回False 。

**Note:**这个功能是[thread-safe](index.htm#thread-safe)。

**See also** [connectionNames](qsqldatabase.html#connectionNames)（ ）[database](qsqldatabase.html#database)（）和[Threads and the SQL Module](index.htm#threads-and-the-sql-module)。

```
QSqlDatabase QSqlDatabase.database (QString connectionName = QLatin1String(QSqlDatabase.defaultConnection), bool open = True)
```

[](qsqldatabase.html)

[返回称为数据库连接_connectionName_。数据库连接必须已经添加了](qsqldatabase.html)[addDatabase](qsqldatabase.html#addDatabase)（ ） 。如果_open_为True（默认值），数据库连接是不是已经打开，现在打开。如果没有_connectionName_是指定使用的默认连接。如果_connectionName_在数据库列表中不存在，则返回一个无效的连接。

**Note:**这个功能是[thread-safe](index.htm#thread-safe)。

**See also** [isOpen](qsqldatabase.html#isOpen)（）和[Threads and the SQL Module](index.htm#threads-and-the-sql-module)。

```
QString QSqlDatabase.databaseName (self)
```

返回连接的数据库名，它可能是空的。**Note:**数据库名是没有连接名称。

**See also** [setDatabaseName](qsqldatabase.html#setDatabaseName)（ ） 。

```
QSqlDriver QSqlDatabase.driver (self)
```

[

返回用于访问数据库连接的数据库驱动程序。

](qsqldriver.html)

[**See also**](qsqldriver.html) [addDatabase](qsqldatabase.html#addDatabase)（）和[drivers](qsqldatabase.html#drivers)（ ） 。

```
QString QSqlDatabase.driverName (self)
```

返回连接的驱动程序名称。

**See also** [addDatabase](qsqldatabase.html#addDatabase)（）和[driver](qsqldatabase.html#driver)（ ） 。

```
QStringList QSqlDatabase.drivers ()
```

返回所有可用的数据库驱动程序的列表。

**See also** [registerSqlDriver](qsqldatabase.html#registerSqlDriver)（ ） 。

```
QSqlQuery QSqlDatabase.exec_ (self, QString query = QString())
```

[](qsqlquery.html)

[执行一条SQL语句在数据库上，并返回一个](qsqlquery.html)[QSqlQuery](qsqlquery.html)对象。使用[lastError](qsqldatabase.html#lastError)（ ）来检索错误信息。如果_query_是空的，空的，无效的查询将返回和[lastError](qsqldatabase.html#lastError)（）不受影响。

**See also** [QSqlQuery](qsqlquery.html)和[lastError](qsqldatabase.html#lastError)（ ） 。

```
QString QSqlDatabase.hostName (self)
```

返回连接的主机名，它可能是空的。

**See also** [setHostName](qsqldatabase.html#setHostName)（ ） 。

```
bool QSqlDatabase.isDriverAvailable (QString name)
```

返回True如果一个叫做驱动程序_name_可用;否则返回False。

**See also** [drivers](qsqldatabase.html#drivers)（ ） 。

```
bool QSqlDatabase.isOpen (self)
```

返回True如果数据库连接是当前打开，否则返回False 。

```
bool QSqlDatabase.isOpenError (self)
```

返回True如果有一个错误打开数据库连接，否则返回False 。错误信息可使用检索到的[lastError](qsqldatabase.html#lastError)（）函数。

```
bool QSqlDatabase.isValid (self)
```

返回True如果[QSqlDatabase](qsqldatabase.html)有一个有效的驱动程序。

例如：

```
 [QSqlDatabase](qsqldatabase.html) db;
 qDebug() << db.isValid();    // Returns false

 db = [QSqlDatabase](qsqldatabase.html).database("sales");
 qDebug() << db.isValid();    // Returns true if "sales" connection exists

 [QSqlDatabase](qsqldatabase.html).removeDatabase("sales");
 qDebug() << db.isValid();    // Returns false

```

```
QSqlError QSqlDatabase.lastError (self)
```

[

返回有关数据库上发生的最后一个错误信息。

](qsqlerror.html)

[发生在与一个单独的查询相结合的故障报告通过](qsqlerror.html)[QSqlQuery.lastError](qsqlquery.html#lastError)（ ） 。

**See also** [QSqlError](qsqlerror.html)和[QSqlQuery.lastError](qsqlquery.html#lastError)（ ） 。

```
QSql.NumericalPrecisionPolicy QSqlDatabase.numericalPrecisionPolicy (self)
```

[

返回数据库连接的当前默认精度的政策。

此功能被引入Qt的4.6 。

](qsql.html#NumericalPrecisionPolicy-enum)

[**See also**](qsql.html#NumericalPrecisionPolicy-enum) [QSql.NumericalPrecisionPolicy](qsql.html#NumericalPrecisionPolicy-enum)，[setNumericalPrecisionPolicy](qsqldatabase.html#setNumericalPrecisionPolicy)（ ）[QSqlQuery.numericalPrecisionPolicy](qsqlquery.html#numericalPrecisionPolicy)（）和[QSqlQuery.setNumericalPrecisionPolicy](qsqlquery.html#setNumericalPrecisionPolicy)（ ） 。

```
bool QSqlDatabase.open (self)
```

打开使用当前连接的值的数据库连接。成功时返回TRUE ，否则返回False 。错误信息可以使用检索[lastError](qsqldatabase.html#lastError)（ ） 。

**See also** [lastError](qsqldatabase.html#lastError)（ ）[setDatabaseName](qsqldatabase.html#setDatabaseName)（ ）[setUserName](qsqldatabase.html#setUserName)（ ）[setPassword](qsqldatabase.html#setPassword)（ ）[setHostName](qsqldatabase.html#setHostName)（ ）[setPort](qsqldatabase.html#setPort)（）和[setConnectOptions](qsqldatabase.html#setConnectOptions)（ ） 。

```
bool QSqlDatabase.open (self, QString user, QString password)
```

这是一个重载函数。

打开使用给定的数据库连接_user_命名并_password_。成功时返回TRUE ，否则返回False 。错误信息可使用检索到的[lastError](qsqldatabase.html#lastError)（）函数。

此功能不能存储它被赋予的密码。相反，该密码被直接传递给驱动程序以打开连接且随后被丢弃。

**See also** [lastError](qsqldatabase.html#lastError)（ ） 。

```
QString QSqlDatabase.password (self)
```

返回连接的密码。如果密码没有被设置[setPassword](qsqldatabase.html#setPassword)（ ），并且如果该密码是在给定的[open](qsqldatabase.html#open)（ ）调用，或者如果没有使用密码，则返回一个空字符串。

**See also** [setPassword](qsqldatabase.html#setPassword)（ ） 。

```
int QSqlDatabase.port (self)
```

返回连接的端口号。该值是不确定的，如果该端口号没有被设置。

**See also** [setPort](qsqldatabase.html#setPort)（ ） 。

```
QSqlIndex QSqlDatabase.primaryIndex (self, QString tablename)
```

[](qsqlindex.html)

[返回表的主索引_tablename_。如果没有主索引存在一个空](qsqlindex.html)[QSqlIndex](qsqlindex.html)返回。

**See also** [tables](qsqldatabase.html#tables)（）和[record](qsqldatabase.html#record)（ ） 。

```
QSqlRecord QSqlDatabase.record (self, QString tablename)
```

[](qsqlrecord.html)

[返回](qsqlrecord.html)[QSqlRecord](qsqlrecord.html)在该表中的所有字段（或视图）的名称叫做填充_tablename_。在该领域出现的记录的顺序是不确定的。如果没有这样的表（或视图）存在，则返回一个空的记录。

```
QSqlDatabase.registerSqlDriver (QString name, QSqlDriverCreatorBase creator)
```

该_creator_说法有它的所有权转移给Qt的。

此功能寄存器称为一个新的SQL驱动程序_name_，内部的SQL框架。如果你有一个自定义的SQL驱动程序，并且不希望将它编译为一个插件，这是很有用的。

例如：

```
 [QSqlDatabase](qsqldatabase.html).registerSqlDriver("MYDRIVER",
                                 new [QSqlDriverCreator](index.htm)<MyDatabaseDriver>);
 [QSqlDatabase](qsqldatabase.html) db = [QSqlDatabase](qsqldatabase.html).addDatabase("MYDRIVER");

```

[QSqlDatabase](qsqldatabase.html)采取所有权_creator_指针，所以你一定不要自己将它删除。

**See also** [drivers](qsqldatabase.html#drivers)（ ） 。

```
QSqlDatabase.removeDatabase (QString connectionName)
```

删除数据库连接_connectionName_从数据库连接列表中。

**Warning:**不应该有开放的查询时，这个函数被调用的数据库连接上，否则会发生资源洩漏。

例如：

```
 // WRONG
 [QSqlDatabase](qsqldatabase.html) db = [QSqlDatabase](qsqldatabase.html).database("sales");
 [QSqlQuery](qsqlquery.html) query("SELECT NAME, DOB FROM EMPLOYEES", db);
 [QSqlDatabase](qsqldatabase.html).removeDatabase("sales"); // will output a warning

 // "db" is now a dangling invalid database connection,
 // "query" contains an invalid result set

```

做正确的方法：

```
 {
     [QSqlDatabase](qsqldatabase.html) db = [QSqlDatabase](qsqldatabase.html).database("sales");
     [QSqlQuery](qsqlquery.html) query("SELECT NAME, DOB FROM EMPLOYEES", db);
 }
 // Both "db" and "query" are destroyed because they are out of scope
 [QSqlDatabase](qsqldatabase.html).removeDatabase("sales"); // correct

```

要删除默认的连接，它可能已经创建了一个调用[addDatabase](qsqldatabase.html#addDatabase)（ ）不指定连接名，你可以通过调用检索默认连接名称[connectionName](qsqldatabase.html#connectionName)（ ）返回的数据库上[database](qsqldatabase.html#database)（ ） 。请注意，如果尚未创建一个默认的数据库无效的数据库将被退回。

**Note:**这个功能是[thread-safe](index.htm#thread-safe)。

**See also** [database](qsqldatabase.html#database)（ ）[connectionName](qsqldatabase.html#connectionName)（）和[Threads and the SQL Module](index.htm#threads-and-the-sql-module)。

```
bool QSqlDatabase.rollback (self)
```

回滚数据库事务，如果驱动程序支持事务和[transaction](qsqldatabase.html#transaction)（ ）已经启动。回报`true`如果操作成功。否则返回`false`。

**Note:**对于某些数据库，回滚将失败，并返回`false`如果有一个[active query](qsqlquery.html#isActive)使用该数据库的`SELECT`。使查询[inactive](qsqlquery.html#isActive)之前做回滚。

Call [lastError](qsqldatabase.html#lastError)（ ）以获取有关错误的信息。

**See also** [QSqlQuery.isActive](qsqlquery.html#isActive)（ ）[QSqlDriver.hasFeature](qsqldriver.html#hasFeature)（）和[commit](qsqldatabase.html#commit)（ ） 。

```
QSqlDatabase.setConnectOptions (self, QString options = QString())
```

设置数据库特定的_options_。这必须是打开连接前或不会有任何效果（或者你可以[close](qsqldatabase.html#close)（ ）的连接，调用这个函数，并[open](qsqldatabase.html#open)（ ）再次连线） 。

的格式_options_字符串是选项名或选项=值对的分号分隔的列表。该选项取决于所使用的数据库客户端上：

| ODBC | MySQL | PostgreSQL |
| --- | --- | --- |
| 

*   SQL_ATTR_ACCESS_MODE
*   SQL_ATTR_LOGIN_TIMEOUT
*   SQL_ATTR_CONNECTION_TIMEOUT
*   SQL_ATTR_CURRENT_CATALOG
*   SQL_ATTR_METADATA_ID
*   SQL_ATTR_PACKET_SIZE
*   SQL_ATTR_TRACEFILE
*   SQL_ATTR_TRACE
*   SQL_ATTR_CONNECTION_POOLING
*   SQL_ATTR_ODBC_VERSION

 | 

*   CLIENT_COMPRESS
*   CLIENT_FOUND_ROWS
*   CLIENT_IGNORE_SPACE
*   CLIENT_SSL
*   CLIENT_ODBC
*   CLIENT_NO_SCHEMA
*   CLIENT_INTERACTIVE
*   UNIX_SOCKET
*   MYSQL_OPT_RECONNECT

 | 

*   connect_timeout
*   options
*   tty
*   requiressl
*   service

 |
| DB2 | OCI | TDS |
| --- | --- | --- |
| 

*   SQL_ATTR_ACCESS_MODE
*   SQL_ATTR_LOGIN_TIMEOUT

 | 

*   OCI_ATTR_PREFETCH_ROWS
*   OCI_ATTR_PREFETCH_MEMORY

 | _none_ |
| SQLite | Interbase |
| --- | --- |
| 

*   QSQLITE_BUSY_TIMEOUT
*   QSQLITE_OPEN_READONLY
*   QSQLITE_ENABLE_SHARED_CACHE

 | 

*   ISC_DPB_LC_CTYPE
*   ISC_DPB_SQL_ROLE_NAME

 |

示例：

```
 ...
 // MySQL connection
 db.setConnectOptions("CLIENT_SSL=1;CLIENT_IGNORE_SPACE=1"); // use an SSL connection to the server
 if (!db.open()) {
     db.setConnectOptions(); // clears the connect option string
     ...
 }
 ...
 // PostgreSQL connection
 db.setConnectOptions("requiressl=1"); // enable PostgreSQL SSL connections
 if (!db.open()) {
     db.setConnectOptions(); // clear options
     ...
 }
 ...
 // ODBC connection
 db.setConnectOptions("SQL_ATTR_ACCESS_MODE=SQL_MODE_READ_ONLY;SQL_ATTR_TRACE=SQL_OPT_TRACE_ON"); // set ODBC options
 if (!db.open()) {
     db.setConnectOptions(); // don't try to set this option
     ...
 }

```

请参阅客户端库文件有关不同选项的详细信息。

**See also** [connectOptions](qsqldatabase.html#connectOptions)（ ） 。

```
QSqlDatabase.setDatabaseName (self, QString name)
```

设置连接的数据库名_name_。有效果，数据库名称必须设置_before_该连接是[opened](qsqldatabase.html#open)。或者，您可以[close](qsqldatabase.html#close)（ ）的连接，设置数据库名，调用[open](qsqldatabase.html#open)（ ）一次。**Note:**该_database name_是不_connection name_。连接名称必须传递给[addDatabase](qsqldatabase.html#addDatabase)（ ）在连接对象创建的时间。

对于QOCI （ Oracle）的驱动程序，数据库名是TNS服务名称。

为QODBC驱动程序，_name_可以是一个DSN ， DSN的一个文件名（在这种情况下，该文件必须有一个`.dsn`扩展名） ，或连接字符串。

例如， Microsoft Access中用户可以使用下面的连接字符串打开一个`.mdb`直接文件，而不必在ODBC管理器创建一个DSN入口， ：

```
 ...
 db = [QSqlDatabase](qsqldatabase.html).addDatabase("QODBC");
 db.setDatabaseName("DRIVER={Microsoft Access Driver (*.mdb)};FIL={MS Access};DBQ=myaccessfile.mdb");
 if (db.open()) {
     // success!
 }
 ...

```

没有默认值。

**See also** [databaseName](qsqldatabase.html#databaseName)（ ）[setUserName](qsqldatabase.html#setUserName)（ ）[setPassword](qsqldatabase.html#setPassword)（ ）[setHostName](qsqldatabase.html#setHostName)（ ）[setPort](qsqldatabase.html#setPort)（ ）[setConnectOptions](qsqldatabase.html#setConnectOptions)（）和[open](qsqldatabase.html#open)（ ） 。

```
QSqlDatabase.setHostName (self, QString host)
```

设置连接的主机名_host_。有效，主机名必须设置_before_该连接是[opened](qsqldatabase.html#open)。或者，您可以[close](qsqldatabase.html#close)（ ）的连接，设置主机名，并调用[open](qsqldatabase.html#open)（ ）一次。

没有默认值。

**See also** [hostName](qsqldatabase.html#hostName)（ ）[setUserName](qsqldatabase.html#setUserName)（ ）[setPassword](qsqldatabase.html#setPassword)（ ）[setDatabaseName](qsqldatabase.html#setDatabaseName)（ ）[setPort](qsqldatabase.html#setPort)（ ）[setConnectOptions](qsqldatabase.html#setConnectOptions)（）和[open](qsqldatabase.html#open)（ ） 。

```
QSqlDatabase.setNumericalPrecisionPolicy (self, QSql.NumericalPrecisionPolicy precisionPolicy)
```

设置使用这个数据库连接创建查询的默认数值精度的政策_precisionPolicy_。

注意：不支持用低精度取数值的驱动程序将忽略精度政策。您可以使用[QSqlDriver.hasFeature](qsqldriver.html#hasFeature)（ ）来找出驱动程序是否支持此功能。

注意：默认精度策略设置来_precisionPolicy_不影响任何当前活动的查询。

此功能被引入Qt的4.6 。

**See also** [QSql.NumericalPrecisionPolicy](qsql.html#NumericalPrecisionPolicy-enum)，[numericalPrecisionPolicy](qsqldatabase.html#numericalPrecisionPolicy)（ ）[QSqlQuery.setNumericalPrecisionPolicy](qsqlquery.html#setNumericalPrecisionPolicy)（）和[QSqlQuery.numericalPrecisionPolicy](qsqlquery.html#numericalPrecisionPolicy)（ ） 。

```
QSqlDatabase.setPassword (self, QString password)
```

设置连接的密码_password_。有效果，必须设置密码_before_该连接是[opened](qsqldatabase.html#open)。或者，您可以[close](qsqldatabase.html#close)（ ）的连接，设置密码，并调用[open](qsqldatabase.html#open)（ ）一次。

没有默认值。

**Warning:**此功能会将密码中的Qt纯文本。使用[open](qsqldatabase.html#open)（ ）调用，需要一个密码作为参数，以避免这种行为。

**See also** [password](qsqldatabase.html#password)（ ）[setUserName](qsqldatabase.html#setUserName)（ ）[setDatabaseName](qsqldatabase.html#setDatabaseName)（ ）[setHostName](qsqldatabase.html#setHostName)（ ）[setPort](qsqldatabase.html#setPort)（ ）[setConnectOptions](qsqldatabase.html#setConnectOptions)（）和[open](qsqldatabase.html#open)（ ） 。

```
QSqlDatabase.setPort (self, int p)
```

设置连接的端口号_port_。有效的端口号必须设置_before_该连接是[opened](qsqldatabase.html#open)。或者，您可以[close](qsqldatabase.html#close)（ ）的连接，设置端口号，并调用[open](qsqldatabase.html#open)（ ）再次..

没有默认值。

**See also** [port](qsqldatabase.html#port)（ ）[setUserName](qsqldatabase.html#setUserName)（ ）[setPassword](qsqldatabase.html#setPassword)（ ）[setHostName](qsqldatabase.html#setHostName)（ ）[setDatabaseName](qsqldatabase.html#setDatabaseName)（ ）[setConnectOptions](qsqldatabase.html#setConnectOptions)（）和[open](qsqldatabase.html#open)（ ） 。

```
QSqlDatabase.setUserName (self, QString name)
```

设置连接的用户名_name_。有效果，用户名必须设置_before_该连接是[opened](qsqldatabase.html#open)。或者，您可以[close](qsqldatabase.html#close)（ ）的连接，设置用户名和调用[open](qsqldatabase.html#open)（ ）一次。

没有默认值。

**See also** [userName](qsqldatabase.html#userName)（ ）[setDatabaseName](qsqldatabase.html#setDatabaseName)（ ）[setPassword](qsqldatabase.html#setPassword)（ ）[setHostName](qsqldatabase.html#setHostName)（ ）[setPort](qsqldatabase.html#setPort)（ ）[setConnectOptions](qsqldatabase.html#setConnectOptions)（）和[open](qsqldatabase.html#open)（ ） 。

```
QStringList QSqlDatabase.tables (self, QSql.TableType type = QSql.Tables)
```

返回数据库的表，系统表和视图的列表，所指定的参数_type_。

**See also** [primaryIndex](qsqldatabase.html#primaryIndex)（）和[record](qsqldatabase.html#record)（ ） 。

```
bool QSqlDatabase.transaction (self)
```

开始一个事务在数据库上，如果驱动程序支持的交易。回报`true`如果操作成功。否则返回`false`。

**See also** [QSqlDriver.hasFeature](qsqldriver.html#hasFeature)（ ）[commit](qsqldatabase.html#commit)（）和[rollback](qsqldatabase.html#rollback)（ ） 。

```
QString QSqlDatabase.userName (self)
```

返回连接的用户名，它可能是空的。

**See also** [setUserName](qsqldatabase.html#setUserName)（ ） 。