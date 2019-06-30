# QSqlError Class Reference

## [[QtSql](index.htm) module]

该QSqlError类提供了SQL数据库的错误信息。[More...](#details)

### Types

*   `enum ErrorType { NoError, ConnectionError, StatementError, TransactionError, UnknownError }`

### Methods

*   `__init__ (self, QString driverText = QString(), QString databaseText = QString(), ErrorType type = QSqlError.NoError, int number = -1)`
*   `__init__ (self, QSqlError other)`
*   `QString databaseText (self)`
*   `QString driverText (self)`
*   `bool isValid (self)`
*   `int number (self)`
*   `setDatabaseText (self, QString databaseText)`
*   `setDriverText (self, QString driverText)`
*   `setNumber (self, int number)`
*   `setType (self, ErrorType type)`
*   `QString text (self)`
*   `ErrorType type (self)`

* * *

## Detailed Description

该QSqlError类提供了SQL数据库的错误信息。

一个QSqlError对象可以提供数据库特定的错误数据，包括[driverText](qsqlerror.html#driverText)（）和[databaseText](qsqlerror.html#databaseText)（）消息（或两者连接在一起为[text](qsqlerror.html#text)（）），和错误[number](qsqlerror.html#number)（）和[type](qsqlerror.html#type)（ ） 。该功能都有setter方法​​，使您可以创建和从你自己的类返回QSqlError对象，例如，从您自己的SQL驱动程序。

* * *

## Type Documentation

```
QSqlError.ErrorType
```

该枚举类型描述了发生错误的情况下，例如，一个连接错误，语句错误等。

| Constant | Value | Description |
| --- | --- | --- |
| `QSqlError.NoError` | `0` | 未发生错误。 |
| `QSqlError.ConnectionError` | `1` | 连接错误。 |
| `QSqlError.StatementError` | `2` | SQL语句的语法错误。 |
| `QSqlError.TransactionError` | `3` | 交易失败的错误。 |
| `QSqlError.UnknownError` | `4` | 未知错误。 |

* * *

## Method Documentation

```
QSqlError.__init__ (self, QString driverText = QString(), QString databaseText = QString(), ErrorType type = QSqlError.NoError, int number = -1)
```

构造一个包含驱动程序错误文本错误_driverText_，数据库的特定错误文本_databaseText_，类型_type_和可选的错误号_number_。

```
QSqlError.__init__ (self, QSqlError other)
```

创建副本_other_。

```
QString QSqlError.databaseText (self)
```

所报告的数据库返回的错误的文本。这可能包含数据库的特定说明，它可能是空的。

**See also** [setDatabaseText](qsqlerror.html#setDatabaseText)（ ）[driverText](qsqlerror.html#driverText)（）和[text](qsqlerror.html#text)（ ） 。

```
QString QSqlError.driverText (self)
```

所报告的驱动程序返回错误的文本。这可能包含数据库的特定说明。它也可能是空的。

**See also** [setDriverText](qsqlerror.html#setDriverText)（ ）[databaseText](qsqlerror.html#databaseText)（）和[text](qsqlerror.html#text)（ ） 。

```
bool QSqlError.isValid (self)
```

返回True如果设置错误，否则为False 。

例如：

```
 [QSqlQueryModel](qsqlquerymodel.html) model;
 model.setQuery("select * from myTable");
 if (model.lastError().isValid())
     qDebug() << model.lastError();

```

**See also** [type](qsqlerror.html#type)（ ） 。

```
int QSqlError.number (self)
```

返回数据库特定的错误号或-1 ，如果它不能确定。

**See also** [setNumber](qsqlerror.html#setNumber)（ ） 。

```
QSqlError.setDatabaseText (self, QString databaseText)
```

设置数据库错误文本的价值_databaseText_。

**See also** [databaseText](qsqlerror.html#databaseText)（ ）[setDriverText](qsqlerror.html#setDriverText)（）和[text](qsqlerror.html#text)（ ） 。

```
QSqlError.setDriverText (self, QString driverText)
```

设置驱动器的错误文本的价值_driverText_。

**See also** [driverText](qsqlerror.html#driverText)（ ）[setDatabaseText](qsqlerror.html#setDatabaseText)（）和[text](qsqlerror.html#text)（ ） 。

```
QSqlError.setNumber (self, int number)
```

设置数据库特定的错误号码_number_。

**See also** [number](qsqlerror.html#number)（ ） 。

```
QSqlError.setType (self, ErrorType type)
```

设置错误类型的值_type_。

**See also** [type](qsqlerror.html#type)（ ） 。

```
QString QSqlError.text (self)
```

这是一个方便的函数，返回[databaseText](qsqlerror.html#databaseText)（）和[driverText](qsqlerror.html#driverText)（ ）连接成一个字符串。

**See also** [driverText](qsqlerror.html#driverText)（）和[databaseText](qsqlerror.html#databaseText)（ ） 。

```
ErrorType QSqlError.type (self)
```

[

如果返回的类型无法确定错误类型，或-1 。

](qsqlerror.html#ErrorType-enum)

[**See also**](qsqlerror.html#ErrorType-enum) [setType](qsqlerror.html#setType)（ ） 。