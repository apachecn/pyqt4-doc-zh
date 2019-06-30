# QSqlDriverCreatorBase Class Reference

## [[QtSql](index.htm) module]

该QSqlDriverCreatorBase类是SQL驱动程序工厂的基类。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QSqlDriverCreatorBase)`
*   `QSqlDriver createObject (self)`

* * *

## Detailed Description

该QSqlDriverCreatorBase类是SQL驱动程序工厂的基类。

重新实现[createObject](qsqldrivercreatorbase.html#createObject)（ ）返回的具体实例[QSqlDriver](qsqldriver.html)要提供子类。

See [QSqlDatabase.registerSqlDriver](qsqldatabase.html#registerSqlDriver)（ ）了解详情。

* * *

## Method Documentation

```
QSqlDriverCreatorBase.__init__ (self)
```

```
QSqlDriverCreatorBase.__init__ (self, QSqlDriverCreatorBase)
```

```
QSqlDriver QSqlDriverCreatorBase.createObject (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

](qsqldriver.html)

[重新实现这个函数返回一个新实例](qsqldriver.html)[QSqlDriver](qsqldriver.html)子类。