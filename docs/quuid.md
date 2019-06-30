# QUuid Class Reference

## [[QtCore](index.htm) module]

该QUuid类存储通用唯一标识符（UUID） 。[More...](#details)

### Types

*   `enum Variant { VarUnknown, NCS, DCE, Microsoft, Reserved }`
*   `enum Version { VerUnknown, Time, EmbeddedPOSIX, Name, Random }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, int l, int w1, int w2, str b1, str b2, str b3, str b4, str b5, str b6, str b7, str b8)`
*   `__init__ (self, QString)`
*   `__init__ (self, QByteArray)`
*   `__init__ (self, QUuid)`
*   `bool isNull (self)`
*   `QByteArray toByteArray (self)`
*   `QByteArray toRfc4122 (self)`
*   `QString toString (self)`
*   `Variant variant (self)`
*   `Version version (self)`

### Static Methods

*   `QUuid createUuid ()`
*   `QUuid fromRfc4122 (QByteArray)`

### Special Methods

*   `bool __eq__ (self, QUuid orig)`
*   `bool __ge__ (self, QUuid other)`
*   `bool __gt__ (self, QUuid other)`
*   `bool __le__ (self, QUuid other)`
*   `bool __lt__ (self, QUuid other)`
*   `bool __ne__ (self, QUuid orig)`
*   `str __repr__ (self)`

* * *

## Detailed Description

该QUuid类存储通用唯一标识符（UUID） 。

Using _U_niversally_U_NIQUE_ID_entifiers （ UUID）是一种标准的方式来唯一地标识在分布式计算环境中的实体。 UUID是一个由一些算法，是为了保证该UUID将是唯一的在那里它被用来在分布式计算环境中产生的16字节（128位）的数目。首字母缩写词的GUID通常用来代替，_G_lobally_U_NIQUE_ID_entifiers ，但它指的是同一件事。

实际上，该GUID是1_variant_的UUID。多个变体都在使用。每个UUID包含一个位域，指定它是UUID的类型（变种） 。通话[variant](quuid.html#variant)（）来发现哪些类型的UUID QUuid的实例包含的内容。它提取的16个字节的字节8的三个最signifcant比特。在QUuid ，字节是8`QUuid.data4[0]`。如果您使用接受所有的数值作为参数的构造函数中创建QUuid的实例，请使用下表来设置参数的三个最显着的位`b1`，成为`QUuid.data4[0]`并包含在它的三个最显着位变体领域。在该表中， “ X”表示_don't care_。

| msb0 | msb1 | msb2 | Variant |
| --- | --- | --- | --- |
| 0 | x | x | NCS (Network Computing System) |
| 1 | 0 | x | DCE (Distributed Computing Environment) |
| 1 | 1 | 0 | Microsoft (GUID) |
| 1 | 1 | 1 | Reserved for future expansion |

If [variant](quuid.html#variant)（）返回[QUuid.DCE](quuid.html#Variant-enum)，的UUID还包含一个_version_中的四个最显着的位场`QUuid.data3`，你可以调用[version](quuid.html#version)（ ）来发现哪个版本的QUuid包含。如果您使用接受所有的数值作为参数的构造函数中创建QUuid的实例，请使用下表来设置参数的四个最显着的位`w2`，成为`QUuid.data3`并包含在其四个最显着位版本字段。

| msb0 | msb1 | msb2 | msb3 | Version |
| --- | --- | --- | --- | --- |
| 0 | 0 | 0 | 1 | Time |
| 0 | 0 | 1 | 0 | Embedded POSIX |
| 0 | 0 | 1 | 1 | Name |
| 0 | 1 | 0 | 0 | Random |

现场布局在表中列出的DCE版本在指定的[Network Working Group UUID Specification](http://www.ietf.org/rfc/rfc4122.txt)。

大多数平台上生成新的UUID ，例如提供一个工具`uuidgen`和`guidgen`。您也可以使用[createUuid](quuid.html#createUuid)（ ） 。所产生的UUID[createUuid](quuid.html#createUuid)（）是随机型。他们的[QUuid.Version](quuid.html#Version-enum)位被设置为[QUuid.Random](quuid.html#Version-enum)，和它们的[QUuid.Variant](quuid.html#Variant-enum)位被设置为[QUuid.DCE](quuid.html#Variant-enum)。的UUID的其馀部分是由随机数。从理论上讲，这意味着有一个UUID，通过产生一个小的机会[createUuid](quuid.html#createUuid)（ ）将不会是唯一的。但它是 [a _very_ small chance](http://en.wikipedia.org/wiki/Universally_Unique_Identifier#Random_UUID_probability_of_duplicates)。

的UUID可以由数值或字符串的构造，或使用静态[createUuid](quuid.html#createUuid)（）函数。它们可以被转换成一个字符串[toString](quuid.html#toString)（ ） 。 UUID的有[variant](quuid.html#variant)（）和一个[version](quuid.html#version)（ ） ，和空的UUID返回True从[isNull](quuid.html#isNull)（ ） 。

* * *

## Type Documentation

```
QUuid.Variant
```

这个枚举变量定义在使用的值[variant field](quuid.html#variant-field)的UUID 。在变型字段中的值决定了128位值的布局。

| Constant | Value | Description |
| --- | --- | --- |
| `QUuid.VarUnknown` | `-1` | Variant是未知 |
| `QUuid.NCS` | `0` | 预留NCS （网络计算系统）的向后兼容性 |
| `QUuid.DCE` | `2` | 分布式计算环境，使用计划[QUuid](quuid.html) |
| `QUuid.Microsoft` | `6` | 保留给微软向后兼容（ GUID ） |
| `QUuid.Reserved` | `7` | 保留为将来之定义 |

```
QUuid.Version
```

这个枚举变量定义在使用的值[version field](quuid.html#version-field)的UUID 。版本字段是有意义的，只有在价值[variant field](quuid.html#variant-field) is [QUuid.DCE](quuid.html#Variant-enum)。

| Constant | Value | Description |
| --- | --- | --- |
| `QUuid.VerUnknown` | `-1` | 版本未知 |
| `QUuid.Time` | `1` | 以时间为基础，通过使用时间戳，时钟序列，和MAC网卡地址（如果有）为节点部分 |
| `QUuid.EmbeddedPOSIX` | `2` | DCE安全的版本，带有嵌入式POSIX的UUID |
| `QUuid.Name` | `3` | 基于名称的，使用的值从一个名进行的所有部分 |
| `QUuid.Random` | `4` | 随机化，通过使用随机数的所有节 |

* * *

## Method Documentation

```
QUuid.__init__ (self)
```

创建空的UUID 。[toString](quuid.html#toString)（ ）将输出空UUID作为“ { 00000000-0000-0000-0000-000000000000 } ” 。

```
QUuid.__init__ (self, int l, int w1, int w2, str b1, str b2, str b3, str b4, str b5, str b6, str b7, str b8)
```

创建一个具有由参数指定的值一个UUID ，_l_，_w1_，_w2_，_b1_，_b2_，_b3_，_b4_，_b5_，_b6_，_b7_，_b8_。

例如：

```
 // {67C8770B-44F1-410A-AB9A-F9B5446F13EE}
 [QUuid](quuid.html) IID_MyInterface(0x67c8770b, 0x44f1, 0x410a, 0xab, 0x9a, 0xf9, 0xb5, 0x44, 0x6f, 0x13, 0xee)

```

```
QUuid.__init__ (self, QString)
```

创建[QUuid](quuid.html)从字符串对象_text_，它必须格式化为相隔5进制领域“ - ” ，如“ { XXXXXXXX - XXXX-XXXX- XXXX-XXXXXXXXXXXX } ”，其中“X”是一个十六进制数字。这里显示的花括号是可选的，但它是正常的，包括他们。如果转换失败，空UUID被创建。看[toString](quuid.html#toString)（ ）对于如何五十六进制字段映射到公共数据成员的解释[QUuid](quuid.html)。

**See also** [toString](quuid.html#toString)（）和[QUuid](quuid.html#QUuid)（ ） 。

```
QUuid.__init__ (self, QByteArray)
```

```
QUuid.__init__ (self, QUuid)
```

创建[QUuid](quuid.html)从对象[QByteArray](qbytearray.html) _text_，它必须格式化为相隔5进制领域“ - ” ，如“ { XXXXXXXX - XXXX-XXXX- XXXX-XXXXXXXXXXXX } ”，其中“X”是一个十六进制数字。这里显示的花括号是可选的，但它是正常的，包括他们。如果转换失败，空UUID被创建。看[toByteArray](quuid.html#toByteArray)（ ）对于如何五十六进制字段映射到公共数据成员的解释[QUuid](quuid.html)。

此功能被引入Qt的4.8 。

**See also** [toByteArray](quuid.html#toByteArray)（）和[QUuid](quuid.html#QUuid)（ ） 。

```
QUuid QUuid.createUuid ()
```

[](quuid.html)

[在Windows以外的任何平台上，这个函数返回一个新的UUID与变异](quuid.html)[QUuid.DCE](quuid.html#Variant-enum)和版本[QUuid.Random](quuid.html#Version-enum)。如果在/ dev / urandom设备存在，则用于构造UUID的号码将加密的质量，这将使得UUID是唯一的。否则，该UUID的号码将被从本地伪随机数发生器（得到[qrand](index.htm#qrand)（ ），它是由接种[qsrand](index.htm#qsrand)（）） ，这是cryptograhic质量通常不是，表示的UUID不能保证是唯一的。

在Windows平台上，一个GUID生成，这几乎肯定_will_是唯一的，在这个或任何其他系统，联网与否。

**See also** [variant](quuid.html#variant)（）和[version](quuid.html#version)（ ） 。

```
QUuid QUuid.fromRfc4122 (QByteArray)
```

[](quuid.html)

[创建](quuid.html)[QUuid](quuid.html)从给定的UUID的二进制表示反对_bytes_，指定由RFC 4122第4.1.2节。看[toRfc4122](quuid.html#toRfc4122)（ ）为所需的字节顺序的进一步解释。

接受字节数组_not_一个人类可读的格式。

如果转换失败，空UUID被创建。

此功能被引入Qt的4.8 。

**See also** [toRfc4122](quuid.html#toRfc4122)（）和[QUuid](quuid.html#QUuid)（ ） 。

```
bool QUuid.isNull (self)
```

返回True如果是空的UUID { 00000000-0000-0000-0000-000000000000 } ，否则返回False 。

```
QByteArray QUuid.toByteArray (self)
```

[](qbytearray.html)

[返回此二进制表示](qbytearray.html)[QUuid](quuid.html)。字节数组的格式为分离五十六场“ - ”和大括号括起来，即“ { XXXXXXXX - XXXX-XXXX- XXXX-XXXXXXXXXXXX } ”，其中“X”是一个十六进制数字。由左到右，五十六进制字段从在四个公共数据成员获得[QUuid](quuid.html)如下：

| Field # | Source |
| --- | --- |
| 1 | data1 |
| 2 | data2 |
| 3 | data3 |
| 4 | data4[0] .. data4[1] |
| 5 | data4[2] .. data4[7] |

此功能被引入Qt的4.8 。

```
QByteArray QUuid.toRfc4122 (self)
```

[](qbytearray.html)

[返回此二进制表示](qbytearray.html)[QUuid](quuid.html)。字节数组是用big endian格式，并根据RFC 4122 ，第4.1.2格式化 - “布局和字节顺序” 。

的顺序如下所示：

| Field # | Source |
| --- | --- |
| 1 | data1 |
| 2 | data2 |
| 3 | data3 |
| 4 | data4[0] .. data4[7] |

此功能被引入Qt的4.8 。

```
QString QUuid.toString (self)
```

返回此字符串表示形式[QUuid](quuid.html)。该字符串的格式为分离五十六场“ - ”和大括号括起来，即“ { XXXXXXXX - XXXX-XXXX- XXXX-XXXXXXXXXXXX } ”，其中“X”是一个十六进制数字。由左到右，五十六进制字段从在四个公共数据成员获得[QUuid](quuid.html)如下：

| Field # | Source |
| --- | --- |
| 1 | data1 |
| 2 | data2 |
| 3 | data3 |
| 4 | data4[0] .. data4[1] |
| 5 | data4[2] .. data4[7] |

```
Variant QUuid.variant (self)
```

[](quuid.html#Variant-enum)

[传回值](quuid.html#Variant-enum)[variant field](quuid.html#variant-field)的UUID 。如果返回值是[QUuid.DCE](quuid.html#Variant-enum)，调用[version](quuid.html#version)（） ，看看哪些布局它使用。空的UUID被认为是一个未知的变体。

**See also** [version](quuid.html#version)（ ） 。

```
Version QUuid.version (self)
```

[](quuid.html#Version-enum)

[返回](quuid.html#Version-enum)[version field](quuid.html#version-field)的UUID的，如果UUID的[variant field](quuid.html#variant-field) is [QUuid.DCE](quuid.html#Variant-enum)。否则返回[QUuid.VerUnknown](quuid.html#Version-enum)。

**See also** [variant](quuid.html#variant)（ ） 。

```
bool QUuid.__eq__ (self, QUuid orig)
```

```
bool QUuid.__ge__ (self, QUuid other)
```

```
bool QUuid.__gt__ (self, QUuid other)
```

```
bool QUuid.__le__ (self, QUuid other)
```

```
bool QUuid.__lt__ (self, QUuid other)
```

```
bool QUuid.__ne__ (self, QUuid orig)
```

```
str QUuid.__repr__ (self)
```