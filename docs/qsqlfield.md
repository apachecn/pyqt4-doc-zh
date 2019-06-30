# QSqlField Class Reference

## [[QtSql](index.htm) module]

该QSqlField类操纵在SQL数据库中的表和视图中的字段。[More...](#details)

### Types

*   `enum RequiredStatus { Unknown, Optional, Required }`

### Methods

*   `__init__ (self, QString fieldName = QString(), Type type = QVariant.Invalid)`
*   `__init__ (self, QSqlField other)`
*   `clear (self)`
*   `QVariant defaultValue (self)`
*   `bool isAutoValue (self)`
*   `bool isGenerated (self)`
*   `bool isNull (self)`
*   `bool isReadOnly (self)`
*   `bool isValid (self)`
*   `int length (self)`
*   `QString name (self)`
*   `int precision (self)`
*   `RequiredStatus requiredStatus (self)`
*   `setAutoValue (self, bool autoVal)`
*   `setDefaultValue (self, QVariant value)`
*   `setGenerated (self, bool gen)`
*   `setLength (self, int fieldLength)`
*   `setName (self, QString name)`
*   `setPrecision (self, int precision)`
*   `setReadOnly (self, bool readOnly)`
*   `setRequired (self, bool required)`
*   `setRequiredStatus (self, RequiredStatus status)`
*   `setSqlType (self, int type)`
*   `setType (self, Type type)`
*   `setValue (self, QVariant value)`
*   `Type type (self)`
*   `int typeID (self)`
*   `QVariant value (self)`

### Special Methods

*   `bool __eq__ (self, QSqlField other)`
*   `bool __ne__ (self, QSqlField other)`

* * *

## Detailed Description

该QSqlField类操纵在SQL数据库中的表和视图中的字段。

QSqlField表示单个列在数据库中的表或视图的特性，诸如数据类型和列名。字段也包含了数据库列，可以查看或更改的值。

字段数据值被存储为[QVariants](index.htm#qvariants)。使用不兼容的类型是不允许的。例如：

```
     QSqlField field("age", [QVariant](qvariant.html).Int);
     field.setValue([QPixmap](qpixmap.html)());  // WRONG

```

然而，该领域将尝试施放某些数据类型的字段的数据类型的地方可能：

```
     QSqlField field("age", [QVariant](qvariant.html).Int);
     field.setValue([QString](qstring.html)("123"));  // casts QString to int

```

QSqlField对象很少在应用程序代码中显式创建。它们通常是通过间接访问[QSqlRecord](qsqlrecord.html)s表示已经包含字段的列表。例如：

```
     [QSqlQuery](qsqlquery.html) query;
     ...
     [QSqlRecord](qsqlrecord.html) record = query.record();
     QSqlField field = record.field("country");

```

一个QSqlField对象可以提供一些元数据有关的领域，例如，其[name](qsqlfield.html#name)（ ） ，变异[type](qsqlfield.html#type)（ ）[length](qsqlfield.html#length)（ ）[precision](qsqlfield.html#precision)（ ）[defaultValue](qsqlfield.html#defaultValue)（） ， typeid的（） ，并且它的[requiredStatus](qsqlfield.html#requiredStatus)（ ）[isGenerated](qsqlfield.html#isGenerated)（）和[isReadOnly](qsqlfield.html#isReadOnly)（ ） 。该字段的数据可以被检查，看它是否[isNull](qsqlfield.html#isNull)（） ，和其[value](qsqlfield.html#value)（ ）检索。当编辑数据可以与设置[setValue](qsqlfield.html#setValue)（）或设置为NULL与[clear](qsqlfield.html#clear)（ ） 。

* * *

## Type Documentation

```
QSqlField.RequiredStatus
```

指定字段是必需的还是可选的。

| Constant | Value | Description |
| --- | --- | --- |
| `QSqlField.Required` | `1` | 插入记录时，该字段必须被指定。 |
| `QSqlField.Optional` | `0` | 该字段没有插入记录时指定。 |
| `QSqlField.Unknown` | `-1` | 数据库驱动程序无法确定该字段是否是必需的或可选的。 |

**See also** [requiredStatus](qsqlfield.html#requiredStatus)（ ） 。

* * *

## Method Documentation

```
QSqlField.__init__ (self, QString fieldName = QString(), Type type = QVariant.Invalid)
```

构造一个空字段称为_fieldName_变异型_type_。

**See also** [setRequiredStatus](qsqlfield.html#setRequiredStatus)（ ）[setLength](qsqlfield.html#setLength)（ ）[setPrecision](qsqlfield.html#setPrecision)（ ）[setDefaultValue](qsqlfield.html#setDefaultValue)（ ）[setGenerated](qsqlfield.html#setGenerated)（）和[setReadOnly](qsqlfield.html#setReadOnly)（ ） 。

```
QSqlField.__init__ (self, QSqlField other)
```

构造的副本_other_。

```
QSqlField.clear (self)
```

清除字段的值，并将其设置为NULL 。如果该字段是只读的，什么也没有发生。

**See also** [setValue](qsqlfield.html#setValue)（ ）[isReadOnly](qsqlfield.html#isReadOnly)（）和[requiredStatus](qsqlfield.html#requiredStatus)（ ） 。

```
QVariant QSqlField.defaultValue (self)
```

返回字段的默认值（可能为空） 。

**See also** [setDefaultValue](qsqlfield.html#setDefaultValue)（ ）[type](qsqlfield.html#type)（ ）[requiredStatus](qsqlfield.html#requiredStatus)（ ）[length](qsqlfield.html#length)（ ）[precision](qsqlfield.html#precision)（）和[isGenerated](qsqlfield.html#isGenerated)（ ） 。

```
bool QSqlField.isAutoValue (self)
```

返回True如果该值是由数据库自动生成，例如自动递增的主键值。

**See also** [setAutoValue](qsqlfield.html#setAutoValue)（ ） 。

```
bool QSqlField.isGenerated (self)
```

返回True如果生成的字段，否则返回False 。

**See also** [setGenerated](qsqlfield.html#setGenerated)（ ）[type](qsqlfield.html#type)（ ）[requiredStatus](qsqlfield.html#requiredStatus)（ ）[length](qsqlfield.html#length)（ ）[precision](qsqlfield.html#precision)（）和[defaultValue](qsqlfield.html#defaultValue)（ ） 。

```
bool QSqlField.isNull (self)
```

返回True如果该字段的值为NULL ，否则返回False 。

**See also** [value](qsqlfield.html#value)（ ） 。

```
bool QSqlField.isReadOnly (self)
```

返回True，如果该字段的值是只读的，否则返回False 。

**See also** [setReadOnly](qsqlfield.html#setReadOnly)（ ）[type](qsqlfield.html#type)（ ）[requiredStatus](qsqlfield.html#requiredStatus)（ ）[length](qsqlfield.html#length)（ ）[precision](qsqlfield.html#precision)（ ）[defaultValue](qsqlfield.html#defaultValue)（）和[isGenerated](qsqlfield.html#isGenerated)（ ） 。

```
bool QSqlField.isValid (self)
```

返回True如果该字段的变量类型是有效的，否则返回False 。

```
int QSqlField.length (self)
```

返回字段的长度。

如果返回的值是负的，这意味着该信息不可用，从数据库中。

**See also** [setLength](qsqlfield.html#setLength)（ ）[type](qsqlfield.html#type)（ ）[requiredStatus](qsqlfield.html#requiredStatus)（ ）[precision](qsqlfield.html#precision)（ ）[defaultValue](qsqlfield.html#defaultValue)（）和[isGenerated](qsqlfield.html#isGenerated)（ ） 。

```
QString QSqlField.name (self)
```

返回字段的名称。

**See also** [setName](qsqlfield.html#setName)（ ） 。

```
int QSqlField.precision (self)
```

返回字段的精度，这是唯一有意义的数值类型。

如果返回的值是负的，这意味着该信息不可用，从数据库中。

**See also** [setPrecision](qsqlfield.html#setPrecision)（ ）[type](qsqlfield.html#type)（ ）[requiredStatus](qsqlfield.html#requiredStatus)（ ）[length](qsqlfield.html#length)（ ）[defaultValue](qsqlfield.html#defaultValue)（）和[isGenerated](qsqlfield.html#isGenerated)（ ） 。

```
RequiredStatus QSqlField.requiredStatus (self)
```

[

返回True如果这是一个必需的字段，否则返回False 。一个`INSERT`如果一个必填字段没有值将会失败。

](qsqlfield.html#RequiredStatus-enum)

[**See also**](qsqlfield.html#RequiredStatus-enum) [setRequiredStatus](qsqlfield.html#setRequiredStatus)（ ）[type](qsqlfield.html#type)（ ）[length](qsqlfield.html#length)（ ）[precision](qsqlfield.html#precision)（ ）[defaultValue](qsqlfield.html#defaultValue)（）和[isGenerated](qsqlfield.html#isGenerated)（ ） 。

```
QSqlField.setAutoValue (self, bool autoVal)
```

标志着字段自动生成的值，如果_autoVal_是真实的。

**See also** [isAutoValue](qsqlfield.html#isAutoValue)（ ） 。

```
QSqlField.setDefaultValue (self, QVariant value)
```

设置用于此字段的默认值_value_。

**See also** [defaultValue](qsqlfield.html#defaultValue)（ ）[value](qsqlfield.html#value)（ ）[setType](qsqlfield.html#setType)（ ）[setRequiredStatus](qsqlfield.html#setRequiredStatus)（ ）[setLength](qsqlfield.html#setLength)（ ）[setPrecision](qsqlfield.html#setPrecision)（ ）[setGenerated](qsqlfield.html#setGenerated)（）和[setReadOnly](qsqlfield.html#setReadOnly)（ ） 。

```
QSqlField.setGenerated (self, bool gen)
```

设置生成的状态。如果_gen_是假的，没有SQL将这个字段来产生，否则， Qt类如[QSqlQueryModel](qsqlquerymodel.html)和[QSqlTableModel](qsqltablemodel.html)将生成的SQL这一领域。

**See also** [isGenerated](qsqlfield.html#isGenerated)（ ）[setType](qsqlfield.html#setType)（ ）[setRequiredStatus](qsqlfield.html#setRequiredStatus)（ ）[setLength](qsqlfield.html#setLength)（ ）[setPrecision](qsqlfield.html#setPrecision)（ ）[setDefaultValue](qsqlfield.html#setDefaultValue)（）和[setReadOnly](qsqlfield.html#setReadOnly)（ ） 。

```
QSqlField.setLength (self, int fieldLength)
```

设置字段的长度_fieldLength_。对于字符串是字符的字符串可以容纳的最大人数;对于其它类型的含义各不相同。

**See also** [length](qsqlfield.html#length)（ ）[setType](qsqlfield.html#setType)（ ）[setRequiredStatus](qsqlfield.html#setRequiredStatus)（ ）[setPrecision](qsqlfield.html#setPrecision)（ ）[setDefaultValue](qsqlfield.html#setDefaultValue)（ ）[setGenerated](qsqlfield.html#setGenerated)（）和[setReadOnly](qsqlfield.html#setReadOnly)（ ） 。

```
QSqlField.setName (self, QString name)
```

设置字段的名称_name_。

**See also** [name](qsqlfield.html#name)（ ） 。

```
QSqlField.setPrecision (self, int precision)
```

设置字段的_precision_。这只会影响数字字段。

**See also** [precision](qsqlfield.html#precision)（ ）[setType](qsqlfield.html#setType)（ ）[setRequiredStatus](qsqlfield.html#setRequiredStatus)（ ）[setLength](qsqlfield.html#setLength)（ ）[setDefaultValue](qsqlfield.html#setDefaultValue)（ ）[setGenerated](qsqlfield.html#setGenerated)（）和[setReadOnly](qsqlfield.html#setReadOnly)（ ） 。

```
QSqlField.setReadOnly (self, bool readOnly)
```

设置只读标志字段的值来_readOnly_。只读字段不能有其值设置与[setValue](qsqlfield.html#setValue)（ ），并不能清除为NULL与[clear](qsqlfield.html#clear)（ ） 。

**See also** [isReadOnly](qsqlfield.html#isReadOnly)（ ） 。

```
QSqlField.setRequired (self, bool required)
```

设置这个字段所需要的状态[Required](qsqlfield.html#RequiredStatus-enum)如果_required_为True，否则设置为[Optional](qsqlfield.html#RequiredStatus-enum)。

**See also** [setRequiredStatus](qsqlfield.html#setRequiredStatus)（）和[requiredStatus](qsqlfield.html#requiredStatus)（ ） 。

```
QSqlField.setRequiredStatus (self, RequiredStatus status)
```

设置这个字段所需要的状态_required_。

**See also** [requiredStatus](qsqlfield.html#requiredStatus)（ ）[setType](qsqlfield.html#setType)（ ）[setLength](qsqlfield.html#setLength)（ ）[setPrecision](qsqlfield.html#setPrecision)（ ）[setDefaultValue](qsqlfield.html#setDefaultValue)（ ）[setGenerated](qsqlfield.html#setGenerated)（）和[setReadOnly](qsqlfield.html#setReadOnly)（ ） 。

```
QSqlField.setSqlType (self, int type)
```

```
QSqlField.setType (self, Type type)
```

集的字段的变量类型_type_。

**See also** [type](qsqlfield.html#type)（ ）[setRequiredStatus](qsqlfield.html#setRequiredStatus)（ ）[setLength](qsqlfield.html#setLength)（ ）[setPrecision](qsqlfield.html#setPrecision)（ ）[setDefaultValue](qsqlfield.html#setDefaultValue)（ ）[setGenerated](qsqlfield.html#setGenerated)（）和[setReadOnly](qsqlfield.html#setReadOnly)（ ） 。

```
QSqlField.setValue (self, QVariant value)
```

设置该字段的值，以_value_。如果该字段是只读的（[isReadOnly](qsqlfield.html#isReadOnly)（ ）返回True ） ，没有任何反应。

如果数据类型_value_不同于字段的当前数据类型，试图将其转换为适当的类型。这将保留字段的数据类型的赋值，如案件一[QString](qstring.html)为整数数据类型。

将值设置为NULL ，使用[clear](qsqlfield.html#clear)（ ） 。

**See also** [value](qsqlfield.html#value)（ ）[isReadOnly](qsqlfield.html#isReadOnly)（）和[defaultValue](qsqlfield.html#defaultValue)（ ） 。

```
Type QSqlField.type (self)
```

[

返回字段的类型与存储在数据库中。请注意，实际值可能有不同的类型，即是太大，无法存储在一个长整型或双通常被存储为字符串，以防止丢失精度的数值。

](index.htm#Type-enum)

[**See also**](index.htm#Type-enum) [setType](qsqlfield.html#setType)（ ） 。

```
int QSqlField.typeID (self)
```

```
QVariant QSqlField.value (self)
```

返回该字段的值作为[QVariant](qvariant.html)。

使用[isNull](qsqlfield.html#isNull)（ ）来检查该字段的值是NULL 。

**See also** [setValue](qsqlfield.html#setValue)（ ） 。

```
bool QSqlField.__eq__ (self, QSqlField other)
```

```
bool QSqlField.__ne__ (self, QSqlField other)
```