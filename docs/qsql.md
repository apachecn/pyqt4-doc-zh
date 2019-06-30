# QSql Class Reference

## [[QtSql](index.htm) module]

该QSQL命名空间包含了整个Qt的SQL库二手其他标识符。[More...](#details)

### Types

*   `enum Location { BeforeFirstRow, AfterLastRow }`
*   `enum NumericalPrecisionPolicy { LowPrecisionInt32, LowPrecisionInt64, LowPrecisionDouble, HighPrecision }`
*   `class **[ParamType](index.htm)**`
*   `enum ParamTypeFlag { In, Out, InOut, Binary }`
*   `enum TableType { Tables, SystemTables, Views, AllTables }`

* * *

## Detailed Description

该QSQL命名空间包含了整个Qt的SQL库二手其他标识符。

* * *

## Type Documentation

```
QSql.Location
```

该枚举类型描述特殊的SQL导航的位置：

| Constant | Value | Description |
| --- | --- | --- |
| `QSql.BeforeFirstRow` | `-1` | 第一条记录之前。 |
| `QSql.AfterLastRow` | `-2` | 最后一个记录之后。 |

**See also** [QSqlQuery.at](qsqlquery.html#at)（ ） 。

```
QSql.NumericalPrecisionPolicy
```

在一个数据库中的数值可以具有精度大于它们相应的C + +类型。这个枚举列出了代表在申请这些值的策略。

| Constant | Value | Description |
| --- | --- | --- |
| `QSql.LowPrecisionInt32` | `0x01` | 强制32位整数值。如遇浮点数，小数部分被丢弃。 |
| `QSql.LowPrecisionInt64` | `0x02` | 强制64位整数值。如遇浮点数，小数部分被丢弃。 |
| `QSql.LowPrecisionDouble` | `0x04` | 力`double`值。这是默认的策略。 |
| `QSql.HighPrecision` | `0` | 字符串将被用来保存精度。 |

注：实际的行为，如果发生溢出是驱动程序特定的。 Oracle数据库只返回在这种情况下，一个错误。

```
QSql.ParamTypeFlag
```

此枚举用于指定绑定参数的类型。

| Constant | Value | Description |
| --- | --- | --- |
| `QSql.In` | `0x00000001` | 绑定参数用于将数据放入数据库中。 |
| `QSql.Out` | `0x00000002` | 绑定参数用于从数据库接收数据。 |
| `QSql.InOut` | `In &#124; Out` | 绑定参数是用来把数据放到数据库中，它会与执行查询的输出数据被复盖。 |
| `QSql.Binary` | `0x00000004` | 这必须与其他标志之一，如果你想以表明正在传送的数据是原始二进制数据进行逻辑或运算。 |

该ParamType类型是一个typedef为[QFlags](index.htm)\u003cParamTypeFlag\u003e 。它存储ParamTypeFlag值的或组合。

```
QSql.TableType
```

该枚举类型描述类型的SQL表。

| Constant | Value | Description |
| --- | --- | --- |
| `QSql.Tables` | `0x01` | 所有的表对用户可见。 |
| `QSql.SystemTables` | `0x02` | 数据库使用的内部表。 |
| `QSql.Views` | `0x04` | 所有用户可见的意见。 |
| `QSql.AllTables` | `0xff` | 以上所有的。 |