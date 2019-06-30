# QSqlRecord Class Reference

## [[QtSql](index.htm) module]

该QSqlRecord类封装了数据库记录。[More...](#details)

通过继承[QSqlIndex](qsqlindex.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QSqlRecord other)`
*   `append (self, QSqlField field)`
*   `clear (self)`
*   `clearValues (self)`
*   `bool contains (self, QString name)`
*   `int count (self)`
*   `QSqlField field (self, int i)`
*   `QSqlField field (self, QString name)`
*   `QString fieldName (self, int i)`
*   `int indexOf (self, QString name)`
*   `insert (self, int pos, QSqlField field)`
*   `bool isEmpty (self)`
*   `bool isGenerated (self, int i)`
*   `bool isGenerated (self, QString name)`
*   `bool isNull (self, int i)`
*   `bool isNull (self, QString name)`
*   `remove (self, int pos)`
*   `replace (self, int pos, QSqlField field)`
*   `setGenerated (self, QString name, bool generated)`
*   `setGenerated (self, int i, bool generated)`
*   `setNull (self, int i)`
*   `setNull (self, QString name)`
*   `setValue (self, int i, QVariant val)`
*   `setValue (self, QString name, QVariant val)`
*   `QVariant value (self, int i)`
*   `QVariant value (self, QString name)`

### Special Methods

*   `bool __eq__ (self, QSqlRecord other)`
*   `__len__ (self)`
*   `bool __ne__ (self, QSqlRecord other)`

* * *

## Detailed Description

该QSqlRecord类封装了数据库记录。

该QSqlRecord类封装了数据库记录（通常是排在数据库中的表或视图）的功能和特点。 QSqlRecord支持添加和删除字段，以及设置和检索的字段值。

的记录的字段“的值可以按名称或位置与设置[setValue](qsqlrecord.html#setValue)（ ），如果你想设置一个字段设置为null的使用[setNull](qsqlrecord.html#setNull)（ ） 。要通过名称找到使用的字段的位置[indexOf](qsqlrecord.html#indexOf)（ ） ，并找到一个字段的名称在一个特定的位置，用[fieldName](qsqlrecord.html#fieldName)（ ） 。使用[field](qsqlrecord.html#field)（）来检索一个[QSqlField](qsqlfield.html)反对给定字段。使用[contains](qsqlrecord.html#contains)（） ，以查看是否记录中包含一个特定的字段名称。

当生成的查询数据库只有那些字段上执行的量[isGenerated](qsqlrecord.html#isGenerated)（ ）为真都包含在生成的SQL 。

A记录可以添加与领域[append](qsqlrecord.html#append)（）或[insert](qsqlrecord.html#insert)（ ） ，替换为[replace](qsqlrecord.html#replace)（ ）中，用去除[remove](qsqlrecord.html#remove)（ ） 。所有字段都可以与被删除[clear](qsqlrecord.html#clear)（ ） 。字段的数目由下式给出[count](qsqlrecord.html#count)（ ） ;他们所有的值可以使用被清零（空）[clearValues](qsqlrecord.html#clearValues)（ ） 。

* * *

## Method Documentation

```
QSqlRecord.__init__ (self)
```

构造一个空的记录。

**See also** [isEmpty](qsqlrecord.html#isEmpty)（ ）[append](qsqlrecord.html#append)（）和[insert](qsqlrecord.html#insert)（ ） 。

```
QSqlRecord.__init__ (self, QSqlRecord other)
```

构造的副本_other_。

[QSqlRecord](qsqlrecord.html) is [implicitly shared](index.htm#implicitly-shared)。这意味着你可以做一个记录的副本，[constant time](index.htm#constant-time)。

```
QSqlRecord.append (self, QSqlField field)
```

附加字段的拷贝_field_到记录的末尾。

**See also** [insert](qsqlrecord.html#insert)（ ）[replace](qsqlrecord.html#replace)（）和[remove](qsqlrecord.html#remove)（ ） 。

```
QSqlRecord.clear (self)
```

删除所有记录的字段。

**See also** [clearValues](qsqlrecord.html#clearValues)（）和[isEmpty](qsqlrecord.html#isEmpty)（ ） 。

```
QSqlRecord.clearValues (self)
```

清除记录中的所有字段的值，并设置每个字段设置为null 。

**See also** [setValue](qsqlrecord.html#setValue)（ ） 。

```
bool QSqlRecord.contains (self, QString name)
```

返回True如果在称为记录的字段_name_否则返回False 。

```
int QSqlRecord.count (self)
```

返回值的记录中的字段的数目。

**See also** [isEmpty](qsqlrecord.html#isEmpty)（ ） 。

```
QSqlField QSqlRecord.field (self, int i)
```

[](qsqlfield.html)

[返回字段的位置_index_。如果_index_超出范围，函数返回一个](qsqlfield.html)[default-constructed value](index.htm#default-constructed-values)。

```
QSqlField QSqlRecord.field (self, QString name)
```

[

这是一个重载函数。

返回称为领域_name_。

```
QString QSqlRecord.fieldName (self, int i)
```

返回字段的名称位置_index_。如果该字段不存在，则返回一个空字符串。

](qsqlfield.html)

[**See also**](qsqlfield.html) [indexOf](qsqlrecord.html#indexOf)（ ） 。

```
int QSqlRecord.indexOf (self, QString name)
```

返回字段的调用位置_name_在记录中，或-1，如果它不能被发现。字段名不区分大小写。如果多于一个字段相匹配，则返回第一个。

**See also** [fieldName](qsqlrecord.html#fieldName)（ ） 。

```
QSqlRecord.insert (self, int pos, QSqlField field)
```

插入场_field_在位置_pos_在记录中。

**See also** [append](qsqlrecord.html#append)（ ）[replace](qsqlrecord.html#replace)（）和[remove](qsqlrecord.html#remove)（ ） 。

```
bool QSqlRecord.isEmpty (self)
```

返回True如果有记录中的任何字段，否则返回False 。

**See also** [append](qsqlrecord.html#append)（ ）[insert](qsqlrecord.html#insert)（）和[clear](qsqlrecord.html#clear)（ ） 。

```
bool QSqlRecord.isGenerated (self, int i)
```

如果记录有一个名为场，则返回True_name_而这一领域是要生成（默认），否则返回False 。

**See also** [setGenerated](qsqlrecord.html#setGenerated)（ ） 。

```
bool QSqlRecord.isGenerated (self, QString name)
```

这是一个重载函数。

如果记录有一个字段位置，则返回True_index_而这一领域是要生成（默认），否则返回False 。

**See also** [setGenerated](qsqlrecord.html#setGenerated)（ ） 。

```
bool QSqlRecord.isNull (self, int i)
```

返回True如果调用该领域_name_为空或如果没有所谓的场_name_否则返回False 。

**See also** [setNull](qsqlrecord.html#setNull)（ ） 。

```
bool QSqlRecord.isNull (self, QString name)
```

这是一个重载函数。

返回True如果字段_index_为null ，或者如果没有字段位置_index_否则返回False 。

```
QSqlRecord.remove (self, int pos)
```

删除该领域的地位_pos_。如果_pos_超出范围，没有任何反应。

**See also** [append](qsqlrecord.html#append)（ ）[insert](qsqlrecord.html#insert)（）和[replace](qsqlrecord.html#replace)（ ） 。

```
QSqlRecord.replace (self, int pos, QSqlField field)
```

取代了场位置_pos_用给定的_field_。如果_pos_超出范围，没有任何反应。

**See also** [append](qsqlrecord.html#append)（ ）[insert](qsqlrecord.html#insert)（）和[remove](qsqlrecord.html#remove)（ ） 。

```
QSqlRecord.setGenerated (self, QString name, bool generated)
```

设置生成的标志字段称为_name_至_generated_。如果该字段不存在，则什么也不会发生。只有具有领域_generated_设置为真包含在由生成的SQL[QSqlQueryModel](qsqlquerymodel.html)例如。

**See also** [isGenerated](qsqlrecord.html#isGenerated)（ ） 。

```
QSqlRecord.setGenerated (self, int i, bool generated)
```

这是一个重载函数。

设置所生成的标志字段_index_至_generated_。

**See also** [isGenerated](qsqlrecord.html#isGenerated)（ ） 。

```
QSqlRecord.setNull (self, int i)
```

设置字段的值_index_为null。如果该字段不存在，则什么也不会发生。

**See also** [isNull](qsqlrecord.html#isNull)（）和[setValue](qsqlrecord.html#setValue)（ ） 。

```
QSqlRecord.setNull (self, QString name)
```

这是一个重载函数。

设置字段中称为值_name_为null。如果该字段不存在，则什么也不会发生。

```
QSqlRecord.setValue (self, int i, QVariant val)
```

设置在位置字段的值_index_至_val_。如果该字段不存在，则什么也不会发生。

**See also** [value](qsqlrecord.html#value)（）和[setNull](qsqlrecord.html#setNull)（ ） 。

```
QSqlRecord.setValue (self, QString name, QVariant val)
```

这是一个重载函数。

设置字段中称为值_name_至_val_。如果该字段不存在，则什么也不会发生。

```
QVariant QSqlRecord.value (self, int i)
```

返回位于位置字段的值_index_在记录中。如果_index_是出界，无效[QVariant](qvariant.html)返回。

**See also** [setValue](qsqlrecord.html#setValue)（ ）[fieldName](qsqlrecord.html#fieldName)（）和[isNull](qsqlrecord.html#isNull)（ ） 。

```
QVariant QSqlRecord.value (self, QString name)
```

这是一个重载函数。

返回字段的所谓的值_name_在记录中。如果场_name_不存在一个无效的变体将被返回。

**See also** [indexOf](qsqlrecord.html#indexOf)（ ） 。

```
bool QSqlRecord.__eq__ (self, QSqlRecord other)
```

```
 QSqlRecord.__len__ (self)
```

```
bool QSqlRecord.__ne__ (self, QSqlRecord other)
```