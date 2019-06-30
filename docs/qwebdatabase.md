# QWebDatabase Class Reference

## [[QtWebKit](index.htm) module]

该QWebDatabase类提供了访问的HTML与JavaScript的创建5个数据库。[More...](#details)

### Methods

*   `__init__ (self, QWebDatabase other)`
*   `QString displayName (self)`
*   `int expectedSize (self)`
*   `QString fileName (self)`
*   `QString name (self)`
*   `QWebSecurityOrigin origin (self)`
*   `int size (self)`

### Static Methods

*   `removeAllDatabases ()`
*   `removeDatabase (QWebDatabase db)`

* * *

## Detailed Description

该QWebDatabase类提供了访问的HTML与JavaScript的创建5个数据库。

即将到来的HTML 5标准包括SQL数据库的网站可以通过JavaScript创建并在本地计算机上访问的支持。 QWebDatabase是C + +的接口这些数据库。

数据库都集中在安全性的起源。要访问一个安全原点定义的所有数据库，使用[QWebSecurityOrigin.databases](qwebsecurityorigin.html#databases)（ ） 。每个数据库都有一个内部[name](qwebdatabase.html#name)（ ） ，以及一个用户友好的名称，所提供[displayName](qwebdatabase.html#displayName)（ ） 。这些名称在创建JavaScript代码数据库时指定。

WebKit中使用SQLite创建和访问本地SQL数据库。在本地文件系统中的数据库文件的位置由返回[fileName](qwebdatabase.html#fileName)（ ） 。您可以通过直接访问数据库[QtSql](index.htm)数据库模块。

对于每一个数据库的网站可以定义[expectedSize](qwebdatabase.html#expectedSize)（ ） 。以字节为单位的数据库的当前大小由返回[size](qwebdatabase.html#size)（ ） 。

欲了解更多信息，请参阅[HTML5 Web SQL Database Draft Standard](http://dev.w3.org/html5/webdatabase/)。

* * *

## Method Documentation

```
QWebDatabase.__init__ (self, QWebDatabase other)
```

从构造一个Web数据库_other_。

```
QString QWebDatabase.displayName (self)
```

返回的格式适合于向用户显示的数据库的名称。

```
int QWebDatabase.expectedSize (self)
```

返回数据库的预期大小（字节）由Web作者定义的那样。

```
QString QWebDatabase.fileName (self)
```

返回Web数据库的文件名。

该名称可用于访问数据库通过[QtSql](index.htm)数据库模块，例如：

```
 [QWebDatabase](qwebdatabase.html) webdb = ...
 [QSqlDatabase](qsqldatabase.html) sqldb = [QSqlDatabase](qsqldatabase.html).addDatabase("QSQLITE", "myconnection");
 sqldb.setDatabaseName(webdb.fileName());
 if (sqldb.open()) {
     [QStringList](qstringlist.html) tables = sqldb.tables();
     ...
 }

```

**Note:**从多个线程或进程同时访问一个数据库不是很有效，因为SQLite是作为WebKit的数据库后端。

```
QString QWebDatabase.name (self)
```

返回数据库的名称。

```
QWebSecurityOrigin QWebDatabase.origin (self)
```

[

返回数据库的安全性起源。

```
QWebDatabase.removeAllDatabases ()
```

删除配置的离线存储路径中的所有网络数据库。

此功能被引入Qt的4.6 。

](qwebsecurityorigin.html)

[**See also**](qwebsecurityorigin.html) [QWebSettings.setOfflineStoragePath](qwebsettings.html#setOfflineStoragePath)（ ） 。

```
QWebDatabase.removeDatabase (QWebDatabase db)
```

删除数据库_db_从它的安全性的起源。存储在数据库中的所有数据_db_将被销毁。

```
int QWebDatabase.size (self)
```

返回以字节为单位的数据库的当前大小。