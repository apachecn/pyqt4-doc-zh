# QUrlInfo Class Reference

## [[QtNetwork](index.htm) module]

关于URL的QUrlInfo类存储信息。[More...](#details)

### Types

*   `enum PermissionSpec { ReadOwner, WriteOwner, ExeOwner, ReadGroup, ..., ExeOther }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QUrlInfo ui)`
*   `__init__ (self, QString name, int permissions, QString owner, QString group, int size, QDateTime lastModified, QDateTime lastRead, bool isDir, bool isFile, bool isSymLink, bool isWritable, bool isReadable, bool isExecutable)`
*   `__init__ (self, QUrl url, int permissions, QString owner, QString group, int size, QDateTime lastModified, QDateTime lastRead, bool isDir, bool isFile, bool isSymLink, bool isWritable, bool isReadable, bool isExecutable)`
*   `QString group (self)`
*   `bool isDir (self)`
*   `bool isExecutable (self)`
*   `bool isFile (self)`
*   `bool isReadable (self)`
*   `bool isSymLink (self)`
*   `bool isValid (self)`
*   `bool isWritable (self)`
*   `QDateTime lastModified (self)`
*   `QDateTime lastRead (self)`
*   `QString name (self)`
*   `QString owner (self)`
*   `int permissions (self)`
*   `setDir (self, bool b)`
*   `setFile (self, bool b)`
*   `setGroup (self, QString s)`
*   `setLastModified (self, QDateTime dt)`
*   `setLastRead (self, QDateTime dt)`
*   `setName (self, QString name)`
*   `setOwner (self, QString s)`
*   `setPermissions (self, int p)`
*   `setReadable (self, bool b)`
*   `setSize (self, int size)`
*   `setSymLink (self, bool b)`
*   `setWritable (self, bool b)`
*   `int size (self)`

### Static Methods

*   `bool equal (QUrlInfo i1, QUrlInfo i2, int sortBy)`
*   `bool greaterThan (QUrlInfo i1, QUrlInfo i2, int sortBy)`
*   `bool lessThan (QUrlInfo i1, QUrlInfo i2, int sortBy)`

### Special Methods

*   `bool __eq__ (self, QUrlInfo i)`
*   `bool __ne__ (self, QUrlInfo i)`

* * *

## Detailed Description

关于URL的QUrlInfo类存储信息。

关于可检索的URL的信息包括[name](qurlinfo.html#name)（ ）[permissions](qurlinfo.html#permissions)（ ）[owner](qurlinfo.html#owner)（ ）[group](qurlinfo.html#group)（ ）[size](qurlinfo.html#size)（ ）[lastModified](qurlinfo.html#lastModified)（ ）[lastRead](qurlinfo.html#lastRead)（ ）[isDir](qurlinfo.html#isDir)（ ）[isFile](qurlinfo.html#isFile)（ ）[isSymLink](qurlinfo.html#isSymLink)（ ）[isWritable](qurlinfo.html#isWritable)（ ）[isReadable](qurlinfo.html#isReadable)（）和[isExecutable](qurlinfo.html#isExecutable)（ ） 。

您可以创建通过在构造函数中的所有相关信息你自己QUrlInfo对象，你可以修改QUrlInfo ，因为上面提到的每个吸气有同等的制定者。请注意，设置值不会影响该QUrlInfo提供有关信息的基础资源，例如，如果你调用setWritable （真）的只读资源唯一改变的是QUrlInfo对象，而不是资源。

* * *

## Type Documentation

```
QUrlInfo.PermissionSpec
```

该枚举是所使用的[permissions](qurlinfo.html#permissions)（ ）函数来报告文件的权限。

| Constant | Value | Description |
| --- | --- | --- |
| `QUrlInfo.ReadOwner` | `00400` | 该文件是由文件的所有者可读。 |
| `QUrlInfo.WriteOwner` | `00200` | 该文件是可写的文件的所有者。 |
| `QUrlInfo.ExeOwner` | `00100` | 该文件是由文件的所有者可执行文件。 |
| `QUrlInfo.ReadGroup` | `00040` | 该文件是由组读取。 |
| `QUrlInfo.WriteGroup` | `00020` | 该文件是可写的组。 |
| `QUrlInfo.ExeGroup` | `00010` | 该文件是由集团的可执行文件。 |
| `QUrlInfo.ReadOther` | `00004` | 该文件可以被任何人读取。 |
| `QUrlInfo.WriteOther` | `00002` | 该文件是可写的权限。 |
| `QUrlInfo.ExeOther` | `00001` | 该文件是由人执行。 |

* * *

## Method Documentation

```
QUrlInfo.__init__ (self)
```

构造一个无效的[QUrlInfo](qurlinfo.html)反对使用默认值。

**See also** [isValid](qurlinfo.html#isValid)（ ） 。

```
QUrlInfo.__init__ (self, QUrlInfo ui)
```

复制构造函数，拷贝_ui_此URL信息的对象。

```
QUrlInfo.__init__ (self, QString name, int permissions, QString owner, QString group, int size, QDateTime lastModified, QDateTime lastRead, bool isDir, bool isFile, bool isSymLink, bool isWritable, bool isReadable, bool isExecutable)
```

构造一个[QUrlInfo](qurlinfo.html)通过指定所有的URL的信息对象。

传递的信息是_name_，文件_permissions_，_owner_和_group_和文件的_size_。还通过为_lastModified_日期/时间和_lastRead_日期/时间。标志也通过了，具体地，_isDir_，_isFile_，_isSymLink_，_isWritable_，_isReadable_和_isExecutable_。

```
QUrlInfo.__init__ (self, QUrl url, int permissions, QString owner, QString group, int size, QDateTime lastModified, QDateTime lastRead, bool isDir, bool isFile, bool isSymLink, bool isWritable, bool isReadable, bool isExecutable)
```

构造一个[QUrlInfo](qurlinfo.html)通过指定所有的URL的信息对象。

传递的信息是_url_，文件_permissions_，_owner_和_group_和文件的_size_。还通过为_lastModified_日期/时间和_lastRead_日期/时间。标志也通过了，具体地，_isDir_，_isFile_，_isSymLink_，_isWritable_，_isReadable_和_isExecutable_。

```
bool QUrlInfo.equal (QUrlInfo i1, QUrlInfo i2, int sortBy)
```

返回True如果_i1_等于_i2_否则返回False 。该目的是通过该值，这是由指定的比较_sortBy_。这必须是一个[QDir.Name](qdir.html#SortFlag-enum)，[QDir.Time](qdir.html#SortFlag-enum) or [QDir.Size](qdir.html#SortFlag-enum)。

```
bool QUrlInfo.greaterThan (QUrlInfo i1, QUrlInfo i2, int sortBy)
```

返回True如果_i1_大于_i2_否则返回False 。该目的是通过该值，这是由指定的比较_sortBy_。这必须是一个[QDir.Name](qdir.html#SortFlag-enum)，[QDir.Time](qdir.html#SortFlag-enum) or [QDir.Size](qdir.html#SortFlag-enum)。

```
QString QUrlInfo.group (self)
```

返回组的URL 。

**See also** [setGroup](qurlinfo.html#setGroup)（）和[isValid](qurlinfo.html#isValid)（ ） 。

```
bool QUrlInfo.isDir (self)
```

返回True如果该URL是一个目录，否则返回False 。

**See also** [isValid](qurlinfo.html#isValid)（ ） 。

```
bool QUrlInfo.isExecutable (self)
```

返回True如果该URL是可执行的;否则返回False。

**See also** [isValid](qurlinfo.html#isValid)（ ） 。

```
bool QUrlInfo.isFile (self)
```

返回True如果URL是一个文件，否则返回False 。

**See also** [isValid](qurlinfo.html#isValid)（ ） 。

```
bool QUrlInfo.isReadable (self)
```

返回True如果该URL是可读的，否则返回False 。

**See also** [isValid](qurlinfo.html#isValid)（ ） 。

```
bool QUrlInfo.isSymLink (self)
```

返回True如果该URL是一个符号链接，否则返回False 。

**See also** [isValid](qurlinfo.html#isValid)（ ） 。

```
bool QUrlInfo.isValid (self)
```

返回True如果该URL的信息是有效的，否则返回False 。有效意味着该[QUrlInfo](qurlinfo.html)包含了真实的信息。

您应经常检查，如果该URL的信息是有效依托值之前。

```
bool QUrlInfo.isWritable (self)
```

返回True如果该URL是可写的，否则返回False 。

**See also** [isValid](qurlinfo.html#isValid)（ ） 。

```
QDateTime QUrlInfo.lastModified (self)
```

[

返回URL的最后修改日期。

](qdatetime.html)

[**See also**](qdatetime.html) [setLastModified](qurlinfo.html#setLastModified)（）和[isValid](qurlinfo.html#isValid)（ ） 。

```
QDateTime QUrlInfo.lastRead (self)
```

[

当返回的URL上次读取日期。

](qdatetime.html)

[**See also**](qdatetime.html) [setLastRead](qurlinfo.html#setLastRead)（）和[isValid](qurlinfo.html#isValid)（ ） 。

```
bool QUrlInfo.lessThan (QUrlInfo i1, QUrlInfo i2, int sortBy)
```

返回True如果_i1_小于_i2_否则返回False 。该目的是通过该值，这是由指定的比较_sortBy_。这必须是一个[QDir.Name](qdir.html#SortFlag-enum)，[QDir.Time](qdir.html#SortFlag-enum) or [QDir.Size](qdir.html#SortFlag-enum)。

```
QString QUrlInfo.name (self)
```

返回URL的文件名。

**See also** [setName](qurlinfo.html#setName)（）和[isValid](qurlinfo.html#isValid)（ ） 。

```
QString QUrlInfo.owner (self)
```

返回URL的所有者。

**See also** [setOwner](qurlinfo.html#setOwner)（）和[isValid](qurlinfo.html#isValid)（ ） 。

```
int QUrlInfo.permissions (self)
```

返回URL的权限。您可以使用`PermissionSpec`标志来测试某些权限。

**See also** [setPermissions](qurlinfo.html#setPermissions)（）和[isValid](qurlinfo.html#isValid)（ ） 。

```
QUrlInfo.setDir (self, bool b)
```

If _b_为真，则该URL被设定为一个目录;如果_b_为False，则该URL被设置为不为目录（通常意味着它是一个文件） 。 （请注意，一个URL可以参考这两个文件，即使大多数文件系统不支持此目录。 ）

如果调用此函数无效的URL信息，这个功能把它变成一个有效的。

**See also** [isDir](qurlinfo.html#isDir)（）和[isValid](qurlinfo.html#isValid)（ ） 。

```
QUrlInfo.setFile (self, bool b)
```

If _b_为真，那么该URL被设置为一个文件，如果\ b是False，则URL被设置不是一个文件（这通常意味着它是一个目录） 。 （请注意，一个URL可以参考这两个文件，即使大多数文件系统不支持此目录。 ）

如果调用此函数无效的URL信息，这个功能把它变成一个有效的。

**See also** [isFile](qurlinfo.html#isFile)（）和[isValid](qurlinfo.html#isValid)（ ） 。

```
QUrlInfo.setGroup (self, QString s)
```

指定所属组的网址被称为_s_。

如果调用此函数无效的URL信息，这个功能把它变成一个有效的。

**See also** [group](qurlinfo.html#group)（）和[isValid](qurlinfo.html#isValid)（ ） 。

```
QUrlInfo.setLastModified (self, QDateTime dt)
```

指定URL指向的对象最后修改于_dt_。

如果调用此函数无效的URL信息，这个功能把它变成一个有效的。

**See also** [lastModified](qurlinfo.html#lastModified)（）和[isValid](qurlinfo.html#isValid)（ ） 。

```
QUrlInfo.setLastRead (self, QDateTime dt)
```

指定的URL指的是对象的上次在读_dt_。

如果调用此函数无效的URL信息，这个功能把它变成一个有效的。

此功能被引入Qt的4.4 。

**See also** [lastRead](qurlinfo.html#lastRead)（）和[isValid](qurlinfo.html#isValid)（ ） 。

```
QUrlInfo.setName (self, QString name)
```

设定URL的名称_name_。这个名字是完整的文字，例如， “ http://qt.nokia.com/doc/qurlinfo.html ” 。

如果调用此函数无效的URL信息，这个功能把它变成一个有效的。

**See also** [name](qurlinfo.html#name)（）和[isValid](qurlinfo.html#isValid)（ ） 。

```
QUrlInfo.setOwner (self, QString s)
```

指定网址的拥有者被称为_s_。

如果调用此函数无效的URL信息，这个功能把它变成一个有效的。

**See also** [owner](qurlinfo.html#owner)（）和[isValid](qurlinfo.html#isValid)（ ） 。

```
QUrlInfo.setPermissions (self, int p)
```

指定的URL访问权限_p_。

如果调用此函数无效的URL信息，这个功能把它变成一个有效的。

**See also** [permissions](qurlinfo.html#permissions)（）和[isValid](qurlinfo.html#isValid)（ ） 。

```
QUrlInfo.setReadable (self, bool b)
```

指定的URL是可读的，如果_b_是真的，不是可读的，如果_b_是假的。

如果调用此函数无效的URL信息，这个功能把它变成一个有效的。

**See also** [isReadable](qurlinfo.html#isReadable)（）和[isValid](qurlinfo.html#isValid)（ ） 。

```
QUrlInfo.setSize (self, int size)
```

指定_size_URL的。

如果调用此函数无效的URL信息，这个功能把它变成一个有效的。

**See also** [size](qurlinfo.html#size)（）和[isValid](qurlinfo.html#isValid)（ ） 。

```
QUrlInfo.setSymLink (self, bool b)
```

指定的URL是指如果一个符号链接_b_是真实，它并不重要，如果_b_是假的。

如果调用此函数无效的URL信息，这个功能把它变成一个有效的。

**See also** [isSymLink](qurlinfo.html#isSymLink)（）和[isValid](qurlinfo.html#isValid)（ ） 。

```
QUrlInfo.setWritable (self, bool b)
```

指定的URL是可写的，如果_b_真实，不可写，如果_b_是假的。

如果调用此函数无效的URL信息，这个功能把它变成一个有效的。

**See also** [isWritable](qurlinfo.html#isWritable)（）和[isValid](qurlinfo.html#isValid)（ ） 。

```
int QUrlInfo.size (self)
```

返回URL的大小。

**See also** [setSize](qurlinfo.html#setSize)（）和[isValid](qurlinfo.html#isValid)（ ） 。

```
bool QUrlInfo.__eq__ (self, QUrlInfo i)
```

```
bool QUrlInfo.__ne__ (self, QUrlInfo i)
```