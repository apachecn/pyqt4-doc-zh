# QSqlRelation Class Reference

## [[QtSql](index.htm) module]

关于一个SQL外键的QSqlRelation类存储信息。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QString aTableName, QString indexCol, QString displayCol)`
*   `__init__ (self, QSqlRelation)`
*   `QString displayColumn (self)`
*   `QString indexColumn (self)`
*   `bool isValid (self)`
*   `QString tableName (self)`

* * *

## Detailed Description

关于一个SQL外键的QSqlRelation类存储信息。

QSqlRelation是一个辅助类[QSqlRelationalTableModel](qsqlrelationaltablemodel.html)。看[QSqlRelationalTableModel.setRelation](qsqlrelationaltablemodel.html#setRelation)（）和[QSqlRelationalTableModel.relation](qsqlrelationaltablemodel.html#relation)（ ）了解详情。

* * *

## Method Documentation

```
QSqlRelation.__init__ (self)
```

构造一个无效的[QSqlRelation](qsqlrelation.html)对象。

对于这样一个对象，该[tableName](qsqlrelation.html#tableName)（ ）[indexColumn](qsqlrelation.html#indexColumn)（）和[displayColumn](qsqlrelation.html#displayColumn)（ ）函数返回一个空字符串。

**See also** [isValid](qsqlrelation.html#isValid)（ ） 。

```
QSqlRelation.__init__ (self, QString aTableName, QString indexCol, QString displayCol)
```

构造一个[QSqlRelation](qsqlrelation.html)对象，其中_tableName_是指为一个外键引用的SQL表名，_indexColumn_是外键，和_displayColumn_是应该被呈现给用户的字段。

**See also** [tableName](qsqlrelation.html#tableName)（ ）[indexColumn](qsqlrelation.html#indexColumn)（）和[displayColumn](qsqlrelation.html#displayColumn)（ ） 。

```
QSqlRelation.__init__ (self, QSqlRelation)
```

```
QString QSqlRelation.displayColumn (self)
```

从表中返回列[tableName](qsqlrelation.html#tableName)（）应该被呈现给用户，而不是一个外键。

```
QString QSqlRelation.indexColumn (self)
```

从表中返回索引列[tableName](qsqlrelation.html#tableName)（）到一个外键引用。

```
bool QSqlRelation.isValid (self)
```

返回True如果[QSqlRelation](qsqlrelation.html)对象是有效的，否则返回False 。

```
QString QSqlRelation.tableName (self)
```

返回表中，以其中一个外键引用的名称。