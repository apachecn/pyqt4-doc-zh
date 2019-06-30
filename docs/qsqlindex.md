# QSqlIndex Class Reference

## [[QtSql](index.htm) module]

该QSqlIndex类提供的功能来处理和描述数据库中的索引。[More...](#details)

继承[QSqlRecord](qsqlrecord.html)。

### Methods

*   `__init__ (self, QString cursorName = QString(), QString name = QString())`
*   `__init__ (self, QSqlIndex other)`
*   `append (self, QSqlField field)`
*   `append (self, QSqlField field, bool desc)`
*   `QString cursorName (self)`
*   `bool isDescending (self, int i)`
*   `QString name (self)`
*   `setCursorName (self, QString cursorName)`
*   `setDescending (self, int i, bool desc)`
*   `setName (self, QString name)`

* * *

## Detailed Description

该QSqlIndex类提供的功能来处理和描述数据库中的索引。

一个_index_指的是一个单一的表或视图中的数据库。关于构成该索引的字段的信息可以被用来生成SQL语句。

* * *

## Method Documentation

```
QSqlIndex.__init__ (self, QString cursorName = QString(), QString name = QString())
```

构造使用游标名称的空索引_cursorname_和索引名_name_。

```
QSqlIndex.__init__ (self, QSqlIndex other)
```

构造的副本_other_。

```
QSqlIndex.append (self, QSqlField field)
```

附加领域_field_对索引字段的列表。本区又追加了一个升序排列。

```
QSqlIndex.append (self, QSqlField field, bool desc)
```

这是一个重载函数。

附加领域_field_对索引字段的列表。该字段追加升序排序顺序，除非_desc_是真实的。

```
QString QSqlIndex.cursorName (self)
```

返回该索引相关联的光标的名称。

**See also** [setCursorName](qsqlindex.html#setCursorName)（ ） 。

```
bool QSqlIndex.isDescending (self, int i)
```

返回True如果场_i_该指数是按降序排序，否则返回False 。

```
QString QSqlIndex.name (self)
```

返回的索引的名字。

**See also** [setName](qsqlindex.html#setName)（ ） 。

```
QSqlIndex.setCursorName (self, QString cursorName)
```

设置该指数与对关联的游标的名称_cursorName_。

**See also** [cursorName](qsqlindex.html#cursorName)（ ） 。

```
QSqlIndex.setDescending (self, int i, bool desc)
```

If _desc_是真的，场_i_是按降序排序。否则，场_i_按升序排序（缺省值） 。如果该字段不存在，则什么也不会发生。

**See also** [isDescending](qsqlindex.html#isDescending)（ ） 。

```
QSqlIndex.setName (self, QString name)
```

集的索引的名字_name_。

**See also** [name](qsqlindex.html#name)（ ） 。