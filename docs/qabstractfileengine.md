# QAbstractFileEngine Class Reference

## [[QtCore](index.htm) module]

该QAbstractFileEngine类提供了访问文件系统的抽象。[More...](#details)

通过继承[QFSFileEngine](qfsfileengine.html)。

### Types

*   `enum FileFlag { ReadOwnerPerm, WriteOwnerPerm, ExeOwnerPerm, ReadUserPerm, ..., Refresh }`
*   `class **[FileFlags](index.htm)**`
*   `enum FileName { DefaultName, BaseName, PathName, AbsoluteName, ..., BundleName }`
*   `enum FileOwner { OwnerUser, OwnerGroup }`
*   `enum FileTime { CreationTime, ModificationTime, AccessTime }`

### Methods

*   `__init__ (self)`
*   `bool atEnd (self)`
*   `QAbstractFileEngineIterator beginEntryList (self, QDir.Filters filters, QStringList filterNames)`
*   `bool caseSensitive (self)`
*   `bool close (self)`
*   `bool copy (self, QString newName)`
*   `QStringList entryList (self, QDir.Filters filters, QStringList filterNames)`
*   `QFile.FileError error (self)`
*   `QString errorString (self)`
*   `FileFlags fileFlags (self, FileFlags type = QAbstractFileEngine.FileInfoAll)`
*   `QString fileName (self, FileName file = QAbstractFileEngine.DefaultName)`
*   `QDateTime fileTime (self, FileTime time)`
*   `bool flush (self)`
*   `int handle (self)`
*   `bool isRelativePath (self)`
*   `bool isSequential (self)`
*   `bool link (self, QString newName)`
*   `sip.voidptr map (self, int offset, int size, QFile.MemoryMapFlags flags)`
*   `bool mkdir (self, QString dirName, bool createParentDirectories)`
*   `bool open (self, QIODevice.OpenMode openMode)`
*   `QString owner (self, FileOwner)`
*   `int ownerId (self, FileOwner)`
*   `int pos (self)`
*   `str read (self, int maxlen)`
*   `str readLine (self, int maxlen)`
*   `bool remove (self)`
*   `bool rename (self, QString newName)`
*   `bool rmdir (self, QString dirName, bool recurseParentDirectories)`
*   `bool seek (self, int pos)`
*   `setError (self, QFile.FileError error, QString str)`
*   `setFileName (self, QString file)`
*   `bool setPermissions (self, int perms)`
*   `bool setSize (self, int size)`
*   `int size (self)`
*   `bool unmap (self, sip.voidptr ptr)`
*   `int write (self, str data)`

### Static Methods

*   `QAbstractFileEngine create (QString fileName)`

* * *

## Detailed Description

该QAbstractFileEngine类提供了访问文件系统的抽象。

该[QDir](qdir.html)，[QFile](qfile.html)和[QFileInfo](qfileinfo.html)类中的所有使用内部一个QAbstractFileEngine的。如果您创建自己的QAbstractFileEngine子类（和使用Qt创建一个注册它[QAbstractFileEngineHandler](qabstractfileenginehandler.html)子类） ，当路径是指你的文件引擎处理您的文件引擎将被使用。

一个QAbstractFileEngine是指一个文件或一个目录。如果所指的是一个文件时，[setFileName](qabstractfileengine.html#setFileName)（ ）[rename](qabstractfileengine.html#rename)（）和[remove](qabstractfileengine.html#remove)（）函数是适用的。如果所指的是一个目录[mkdir](qabstractfileengine.html#mkdir)（ ）[rmdir](qabstractfileengine.html#rmdir)（）和[entryList](qabstractfileengine.html#entryList)（）函数是适用的。在所有情况下[caseSensitive](qabstractfileengine.html#caseSensitive)（ ）[isRelativePath](qabstractfileengine.html#isRelativePath)（ ）[fileFlags](qabstractfileengine.html#fileFlags)（ ）[ownerId](qabstractfileengine.html#ownerId)（ ）[owner](qabstractfileengine.html#owner)（）和[fileTime](qabstractfileengine.html#fileTime)（）函数是适用的。

一个QAbstractFileEngine子类可以被创建来做到同步网络I / O的文件系统操作，本地文件系统操作，或作为一个系统资源的访问基于文件的资源。

* * *

## Type Documentation

```
QAbstractFileEngine.FileFlag
```

的权限和类型的文件，适于中用OR在一起。

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractFileEngine.ReadOwnerPerm` | `0x4000` | 该文件的所有者有权读取它。 |
| `QAbstractFileEngine.WriteOwnerPerm` | `0x2000` | 该文件的所有者具有写权限了。 |
| `QAbstractFileEngine.ExeOwnerPerm` | `0x1000` | 该文件的所有者有权执行它的权限。 |
| `QAbstractFileEngine.ReadUserPerm` | `0x0400` | 当前用户有权限读取该文件。 |
| `QAbstractFileEngine.WriteUserPerm` | `0x0200` | 当前用户有权限写入到文件中。 |
| `QAbstractFileEngine.ExeUserPerm` | `0x0100` | 当前用户拥有执行该文件的权限。 |
| `QAbstractFileEngine.ReadGroupPerm` | `0x0040` | 当前用户组的成员有权限读取的文件。 |
| `QAbstractFileEngine.WriteGroupPerm` | `0x0020` | 当前用户组的成员具有写权限的文件。 |
| `QAbstractFileEngine.ExeGroupPerm` | `0x0010` | 当前用户组的成员具有执行该文件的权限。 |
| `QAbstractFileEngine.ReadOtherPerm` | `0x0004` | 所有用户有权限读取的文件。 |
| `QAbstractFileEngine.WriteOtherPerm` | `0x0002` | 所有用户都具有写权限的文件。 |
| `QAbstractFileEngine.ExeOtherPerm` | `0x0001` | 所有的用户都具有执行该文件的权限。 |
| `QAbstractFileEngine.LinkType` | `0x10000` | 该文件是在文件系统（即不是一个文件或目录）链接到另一个文件（或链接） 。 |
| `QAbstractFileEngine.FileType` | `0x20000` | 该文件是一个普通文件到文件系统（即不是链接或目录） |
| `QAbstractFileEngine.BundleType` | `0x80000` | 该文件是一个Mac OS X的包意味着DirectoryType |
| `QAbstractFileEngine.DirectoryType` | `0x40000` | 该文件是在文件系统（即不是链接或文件）的目录。 |
| `QAbstractFileEngine.HiddenFlag` | `0x0100000` | 该文件是隐藏的。 |
| `QAbstractFileEngine.ExistsFlag` | `0x0400000` | 该文件实际上存在于文件系统中。 |
| `QAbstractFileEngine.RootFlag` | `0x0800000` | 该文件或文件指向的是文件系统的根。 |
| `QAbstractFileEngine.LocalDiskFlag` | `0x0200000` | 该文件驻留在本地磁盘上，并且可以通过标准的文件的功能。 |
| `QAbstractFileEngine.Refresh` | `0x1000000` | 传递此标志将强制文件引擎刷新所有标志。 |

该FileFlags类型是一个typedef为[QFlags](index.htm)\u003cFileFlag\u003e 。它存储FileFlag值的或组合。

**See also** [fileFlags](qabstractfileengine.html#fileFlags)（）和[setFileName](qabstractfileengine.html#setFileName)（ ） 。

```
QAbstractFileEngine.FileName
```

这些值被用来以特定的格式要求一个文件名。

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractFileEngine.DefaultName` | `0` | 传递给了相同的文件名[QAbstractFileEngine](qabstractfileengine.html)。 |
| `QAbstractFileEngine.BaseName` | `1` | 不包括路径中的文件的名称。 |
| `QAbstractFileEngine.PathName` | `2` | 的路径，不包括基本名称的文件。 |
| `QAbstractFileEngine.AbsoluteName` | `3` | 绝对路径文件（包括基本名称） 。 |
| `QAbstractFileEngine.AbsolutePathName` | `4` | 绝对路径文件（不包括基本名称） 。 |
| `QAbstractFileEngine.LinkName` | `5` | 该文件是一个链接到该文件的完整文件名。 （这将是空的，如果这个文件是不是链接。 ） |
| `QAbstractFileEngine.CanonicalName` | `6` | 往往很相似，链接名称。将返回真正的文件路径。 |
| `QAbstractFileEngine.CanonicalPathName` | `7` | 同CanonicalName ，不包括基本名称。 |
| `QAbstractFileEngine.BundleName` | `8` | 返回该包的名称所暗示[BundleType](qabstractfileengine.html#FileFlag-enum)被设置。 |

**See also** [fileName](qabstractfileengine.html#fileName)（）和[setFileName](qabstractfileengine.html#setFileName)（ ） 。

```
QAbstractFileEngine.FileOwner
```

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractFileEngine.OwnerUser` | `0` | 谁拥有该文件的用户。 |
| `QAbstractFileEngine.OwnerGroup` | `1` | 谁拥有该文件的组。 |

**See also** [owner](qabstractfileengine.html#owner)（ ）[ownerId](qabstractfileengine.html#ownerId)（）和[setFileName](qabstractfileengine.html#setFileName)（ ） 。

```
QAbstractFileEngine.FileTime
```

这些被使用的[fileTime](qabstractfileengine.html#fileTime)（）函数。

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractFileEngine.CreationTime` | `0` | 当创建该文件。 |
| `QAbstractFileEngine.ModificationTime` | `1` | 当文件最近被修改。 |
| `QAbstractFileEngine.AccessTime` | `2` | 当最近被访问的文件（例如，读取或写入） 。 |

**See also** [setFileName](qabstractfileengine.html#setFileName)（ ） 。

* * *

## Method Documentation

```
QAbstractFileEngine.__init__ (self)
```

构造一个新的[QAbstractFileEngine](qabstractfileengine.html)这并不是指任何文件或目录。

**See also** [setFileName](qabstractfileengine.html#setFileName)（ ） 。

```
bool QAbstractFileEngine.atEnd (self)
```

返回True如果当前位置是在文件的末尾，否则返回False 。

该功能立足于调用它的行为[extension](qabstractfileengine.html#extension)（ ）与[AtEndExtension](qabstractfileengine.html#Extension-enum)。如果引擎不支持此扩展，则返回False。

此功能被引入Qt的4.3 。

**See also** [extension](qabstractfileengine.html#extension)（ ）[supportsExtension](qabstractfileengine.html#supportsExtension)（）和[QFile.atEnd](qfile.html#atEnd)（ ） 。

```
QAbstractFileEngineIterator QAbstractFileEngine.beginEntryList (self, QDir.Filters filters, QStringList filterNames)
```

[](qabstractfileengineiterator.html)

[返回一个实例](qabstractfileengineiterator.html)[QAbstractFileEngineIterator](qabstractfileengineiterator.html) using _filters_入门过滤和_filterNames_对于名称的过滤。调用此函数由[QDirIterator](qdiriterator.html)启动目录迭代。

[QDirIterator](qdiriterator.html)需要返回的实例的所有权，并删除它时，它的完成。

**See also** [QDirIterator](qdiriterator.html)。

```
bool QAbstractFileEngine.caseSensitive (self)
```

应返回True如果底层文件系统是大小写敏感的，否则返回False 。

这个虚函数必须在子类中重新实现。

```
bool QAbstractFileEngine.close (self)
```

关闭文件，返回True，如果成功，否则返回False 。

默认的实现始终返回False 。

```
bool QAbstractFileEngine.copy (self, QString newName)
```

复制这个文件的内容与名称的文件_newName_。成功时返回TRUE ，否则返回False 。

```
QAbstractFileEngine QAbstractFileEngine.create (QString fileName)
```

[](qabstractfileengine.html)

[创建并返回一个](qabstractfileengine.html)[QAbstractFileEngine](qabstractfileengine.html)适于处理_fileName_。

你不应该需要调用这个函数;使用[QFile](qfile.html)，[QFileInfo](qfileinfo.html) or [QDir](qdir.html)直接代替。

如果您reimplemnt这个功能，它应该只返回一个知道如何处理文件引擎_fileName_否则，它应该返回0 。

**See also** [QAbstractFileEngineHandler](qabstractfileenginehandler.html)。

```
QStringList QAbstractFileEngine.entryList (self, QDir.Filters filters, QStringList filterNames)
```

请所有文件的列表匹配_filters_基于所述列表_filterNames_在文件引擎的目录中返回。

应该返回一个空列表，如果该文件引擎指的是文件，而不是一个目录，或者目录是不可读的或者不存在，或者如果没有相匹配的规格。

这个虚函数必须在子类中重新实现。

**See also** [setFileName](qabstractfileengine.html#setFileName)（ ） 。

```
QFile.FileError QAbstractFileEngine.error (self)
```

[](qfile.html#FileError-enum)

[返回](qfile.html#FileError-enum)[QFile.FileError](qfile.html#FileError-enum)这是由于过去失败的操作。如果[QFile.UnspecifiedError](qfile.html#FileError-enum)返回，[QFile](qfile.html)将利用自身的错误状态的想法。

**See also** [setError](qabstractfileengine.html#setError)（ ）[QFile.FileError](qfile.html#FileError-enum)和[errorString](qabstractfileengine.html#errorString)（ ） 。

```
QString QAbstractFileEngine.errorString (self)
```

返回人类可读的消息恰当报告的当前错误[error](qabstractfileengine.html#error)（ ） 。如果没有合适的字符串是可用的，则返回一个空字符串。

**See also** [error](qabstractfileengine.html#error)（ ） 。

```
FileFlags QAbstractFileEngine.fileFlags (self, FileFlags type = QAbstractFileEngine.FileInfoAll)
```

[

这个函数应该返回一组逻辑与的标志，是真实的文件引擎的文件，那是在_type_的逻辑与的成员。

在你重新实现可以使用_type_参数作为优化提示，并只返回或运算组成员是真实的和那场比赛中的那些_type_换句话说，您可以忽略不提及任何成员_type_，从而避免一些潜在的昂贵的查找或系统调用。

这个虚函数必须在子类中重新实现。

](index.htm)

[**See also**](index.htm) [setFileName](qabstractfileengine.html#setFileName)（ ） 。

```
QString QAbstractFileEngine.fileName (self, FileName file = QAbstractFileEngine.DefaultName)
```

返回由指定格式的文件引擎的当前文件名_file_。

如果不处理某些`FileName`可能性，返回文件名设置[setFileName](qabstractfileengine.html#setFileName)（ ）当未处理的格式要求。

这个虚函数必须在子类中重新实现。

**See also** [setFileName](qabstractfileengine.html#setFileName)（）和[FileName](qabstractfileengine.html#FileName-enum)。

```
QDateTime QAbstractFileEngine.fileTime (self, FileTime time)
```

[

If _time_ is `CreationTime`，创建文件时返回。如果_time_ is `ModificationTime`，返回当文件最近被修改。如果_time_ is `AccessTime`，返回时被最近访问的文件（如读或写） 。如果时间无法确定返回QDateTime （ ） （一个无效的日期时间） 。

这个虚函数必须在子类中重新实现。

](qdatetime.html)

[**See also**](qdatetime.html) [setFileName](qabstractfileengine.html#setFileName)（ ）[QDateTime](qdatetime.html)，[QDateTime.isValid](qdatetime.html#isValid)（）和[FileTime](qabstractfileengine.html#FileTime-enum)。

```
bool QAbstractFileEngine.flush (self)
```

刷新打开文件，返回True，如果成功，否则返回False 。

默认的实现始终返回False 。

```
int QAbstractFileEngine.handle (self)
```

返回本机文件句柄这个文件引擎。此句柄必须小心使用，它的价值和类型是特定的平台，并利用它很可能会导致不可移植的代码。

```
bool QAbstractFileEngine.isRelativePath (self)
```

返回True，如果该文件引擎所指的文件有一个相对路径，否则返回False 。

这个虚函数必须在子类中重新实现。

**See also** [setFileName](qabstractfileengine.html#setFileName)（ ） 。

```
bool QAbstractFileEngine.isSequential (self)
```

返回True如果该文件是一个顺序存取设备，如果该文件是一个直接存取设备返回False。

涉及业务[size](qabstractfileengine.html#size)（ ）和seek（ INT）是不是在连续的设备有效。

```
bool QAbstractFileEngine.link (self, QString newName)
```

从创建该文件目前由指定的链接[fileName](qabstractfileengine.html#fileName)（）来_newName_。什么链接是依赖于底层的文件系统（无论是在Windows还是Unix上符号链接的快捷方式）上。成功返回True ，否则返回False 。

```
sip.voidptr QAbstractFileEngine.map (self, int offset, int size, QFile.MemoryMapFlags flags)
```

地图_size_该文件的字节到存储器中，起始_offset_。返回一个指向内存的指针，如果成功，如果，例如，发生错误，否则返回False 。

该功能立足于调用它的行为[extension](qabstractfileengine.html#extension)（ ）与[MapExtensionOption](index.htm)。如果引擎不支持此扩展，则返回0 。

_flags_目前没有使用，但可能在将来被使用。

此功能被引入Qt的4.4 。

**See also** [unmap](qabstractfileengine.html#unmap)（）和[supportsExtension](qabstractfileengine.html#supportsExtension)（ ） 。

```
bool QAbstractFileEngine.mkdir (self, QString dirName, bool createParentDirectories)
```

请求的目录_dirName_被创建。如果_createParentDirectories_是真的，那么在任何子目录_dirName_不存在必须被创建。如果_createParentDirectories_为False，则在任何子目录_dirName_必须已经为函数成功存在。如果操作成功，返回True ，否则返回False 。

这个虚函数必须在子类中重新实现。

**See also** [setFileName](qabstractfileengine.html#setFileName)（ ）[rmdir](qabstractfileengine.html#rmdir)（）和[isRelativePath](qabstractfileengine.html#isRelativePath)（ ） 。

```
bool QAbstractFileEngine.open (self, QIODevice.OpenMode openMode)
```

打开文件在指定的_mode_。返回True如果文件被成功打开，否则返回False 。

该_mode_是一个OR组合[QIODevice.OpenMode](qiodevice.html#OpenModeFlag-enum)和QIODevice.HandlingMode值。

```
QString QAbstractFileEngine.owner (self, FileOwner)
```

If _owner_ is `OwnerUser`返回谁拥有该文件的用户的名称。如果_owner_ is `OwnerGroup`返回拥有该文件的组的名称。如果你不能确定业主回报的QString （ ） 。

这个虚函数必须在子类中重新实现。

**See also** [ownerId](qabstractfileengine.html#ownerId)（ ）[setFileName](qabstractfileengine.html#setFileName)（）和[FileOwner](qabstractfileengine.html#FileOwner-enum)。

```
int QAbstractFileEngine.ownerId (self, FileOwner)
```

If _owner_ is `OwnerUser`返回谁拥有该文件的用户的ID 。如果_owner_ is `OwnerGroup`返回拥有该文件的组ID 。如果你不能确定业主返回-2 。

这个虚函数必须在子类中重新实现。

**See also** [owner](qabstractfileengine.html#owner)（ ）[setFileName](qabstractfileengine.html#setFileName)（）和[FileOwner](qabstractfileengine.html#FileOwner-enum)。

```
int QAbstractFileEngine.pos (self)
```

返回当前文件位置。

这是读出的文件/写头中的数据的位置。

```
str QAbstractFileEngine.read (self, int maxlen)
```

读取的字符数从文件导入_data_。最多_maxlen_字符将被读取。

如果发生致命错误，或者0，如果没有要读取的字节，则返回-1 。

```
str QAbstractFileEngine.readLine (self, int maxlen)
```

该函数读取一行，由一个'\ n“字符终止，从文件信息_data_。最多_maxlen_字符将被读取。行尾的字符被包括在内。

```
bool QAbstractFileEngine.remove (self)
```

该文件从文件系统中删除请求。如果操作成功，返回True ，否则返回False 。

这个虚函数必须在子类中重新实现。

**See also** [setFileName](qabstractfileengine.html#setFileName)（）和[rmdir](qabstractfileengine.html#rmdir)（ ） 。

```
bool QAbstractFileEngine.rename (self, QString newName)
```

请求该文件被重命名为_newName_在文件系统中。如果操作成功，返回True ，否则返回False 。

这个虚函数必须在子类中重新实现。

**See also** [setFileName](qabstractfileengine.html#setFileName)（ ） 。

```
bool QAbstractFileEngine.rmdir (self, QString dirName, bool recurseParentDirectories)
```

请求的目录_dirName_从文件系统中删除。何时_recurseParentDirectories_是真的，那么任何空的父目录中_dirName_也必须删除。如果_recurseParentDirectories_是假的，只有_dirName_叶节点应予删除。在大多数文件系统的目录中不能使用该功能，如果它是一个非空被删除。如果操作成功，返回True ，否则返回False 。

这个虚函数必须在子类中重新实现。

**See also** [setFileName](qabstractfileengine.html#setFileName)（ ）[remove](qabstractfileengine.html#remove)（ ）[mkdir](qabstractfileengine.html#mkdir)（）和[isRelativePath](qabstractfileengine.html#isRelativePath)（ ） 。

```
bool QAbstractFileEngine.seek (self, int pos)
```

设置文件位置为给定的_offset_。返回True如果该位置被成功设置，否则返回False 。

偏移量是从文件的开始处，除非该文件是连续的。

**See also** [isSequential](qabstractfileengine.html#isSequential)（ ） 。

```
QAbstractFileEngine.setError (self, QFile.FileError error, QString str)
```

设置错误类型_error_和错误字符串_errorString_。调用此函数来设置由更高级别的课程返回错误值。

**See also** [QFile.error](qfile.html#error)（ ）[QIODevice.errorString](qiodevice.html#errorString)（）和[QIODevice.setErrorString](qiodevice.html#setErrorString)（ ） 。

```
QAbstractFileEngine.setFileName (self, QString file)
```

设置文件引擎的文件名_file_。这个文件名是虚函数，其馀将要操作的文件。

这个虚函数必须在子类中重新实现。

**See also** [fileName](qabstractfileengine.html#fileName)（）和[rename](qabstractfileengine.html#rename)（ ） 。

```
bool QAbstractFileEngine.setPermissions (self, int perms)
```

该文件的权限设置为请求_perms_。该参数烫发将被设置为QAbstractFileEngine.FileInfo的或的结果结合在一起，只有[QAbstractFileEngine.PermsMask](qabstractfileengine.html#FileFlag-enum)的荣幸。如果操作succceeds返回True ，否则返回False ;

这个虚函数必须在子类中重新实现。

**See also** [size](qabstractfileengine.html#size)（ ） 。

```
bool QAbstractFileEngine.setSize (self, int size)
```

该文件被设置为请求的大小_size_。如果_size_比当前文件则填0的，如果小它只是截断较大。如果操作succceeds返回True ，否则返回False ;

这个虚函数必须在子类中重新实现。

**See also** [size](qabstractfileengine.html#size)（ ） 。

```
int QAbstractFileEngine.size (self)
```

返回文件的大小。

**See also** [setSize](qabstractfileengine.html#setSize)（ ） 。

```
bool QAbstractFileEngine.unmap (self, sip.voidptr ptr)
```

取消映射的内存_address_。返回True如果取消映射成功，否则返回False 。

该功能立足于调用它的行为[extension](qabstractfileengine.html#extension)（ ）与[UnMapExtensionOption](index.htm)。如果引擎不支持此扩展，则返回False。

此功能被引入Qt的4.4 。

**See also** [map](qabstractfileengine.html#map)（）和[supportsExtension](qabstractfileengine.html#supportsExtension)（ ） 。

```
int QAbstractFileEngine.write (self, str data)
```

Writes _len_从字节_data_到文件中。返回写入成功的字符数，否则返回-1 。