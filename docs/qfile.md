# QFile Class Reference

## [[QtCore](index.htm) module]

QFile类提供了读取和写入文件的接口。[More...](#details)

继承[QIODevice](qiodevice.html)。

通过继承[QTemporaryFile](qtemporaryfile.html)。

### Types

*   `enum FileError { NoError, ReadError, WriteError, FatalError, ..., CopyError }`
*   `enum FileHandleFlag { AutoCloseHandle, DontCloseHandle }`
*   `class **[FileHandleFlags](index.htm)**`
*   `enum MemoryMapFlags { NoOptions }`
*   `enum Permission { ReadOwner, WriteOwner, ExeOwner, ReadUser, ..., ExeOther }`
*   `class **[Permissions](index.htm)**`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QString name)`
*   `__init__ (self, QObject parent)`
*   `__init__ (self, QString name, QObject parent)`
*   `bool atEnd (self)`
*   `close (self)`
*   `bool copy (self, QString newName)`
*   `FileError error (self)`
*   `bool exists (self)`
*   `QAbstractFileEngine fileEngine (self)`
*   `QString fileName (self)`
*   `bool flush (self)`
*   `int handle (self)`
*   `bool isSequential (self)`
*   `bool link (self, QString newName)`
*   `sip.voidptr map (self, int offset, int size, MemoryMapFlags flags = QFile.NoOptions)`
*   `bool open (self, QIODevice.OpenMode flags)`
*   `bool open (self, int fd, QIODevice.OpenMode flags)`
*   `bool open (self, int fd, QIODevice.OpenMode flags, FileHandleFlags handleFlags)`
*   `Permissions permissions (self)`
*   `int pos (self)`
*   `str readData (self, int maxlen)`
*   `str readLineData (self, int maxlen)`
*   `QString readLink (self)`
*   `bool remove (self)`
*   `bool rename (self, QString newName)`
*   `bool resize (self, int sz)`
*   `bool seek (self, int offset)`
*   `setFileName (self, QString name)`
*   `bool setPermissions (self, Permissions permissionSpec)`
*   `int size (self)`
*   `QString symLinkTarget (self)`
*   `bool unmap (self, sip.voidptr address)`
*   `unsetError (self)`
*   `int writeData (self, str data)`

### Static Methods

*   `bool copy (QString fileName, QString newName)`
*   `QString decodeName (QByteArray localFileName)`
*   `QString decodeName (str localFileName)`
*   `QByteArray encodeName (QString fileName)`
*   `bool exists (QString fileName)`
*   `bool link (QString oldname, QString newName)`
*   `Permissions permissions (QString filename)`
*   `QString readLink (QString fileName)`
*   `bool remove (QString fileName)`
*   `bool rename (QString oldName, QString newName)`
*   `bool resize (QString filename, int sz)`
*   `bool setPermissions (QString filename, Permissions permissionSpec)`
*   `QString symLinkTarget (QString fileName)`

* * *

## Detailed Description

QFile类提供了读取和写入文件的接口。

的QFile是用于读取和写入文本文件和二进制文件的I / O设备和[resources](index.htm)。一个QFile时可能会或单独使用，更方便，用[QTextStream](qtextstream.html) or [QDataStream](qdatastream.html)。

文件名通常是通过在构造函数，但它可以被设置在任何时候使用[setFileName](qfile.html#setFileName)（ ） 。 QFile时预计，文件分隔符是' /' ，无论操作系统。不支持使用其他分隔符（比如，' \ '）的。

您可以检查一个文件是否存在使用[exists](qfile.html#exists)（ ） ，并删除使用文件[remove](qfile.html#remove)（ ） 。通过提供（更先进的文件系统相关的操作[QFileInfo](qfileinfo.html)和[QDir](qdir.html)。 ）

该文件被打开[open](qfile.html#open)（ ） ，关闭了与[close](qfile.html#close)（ ） ，并用冲洗[flush](qfile.html#flush)（ ） 。数据通常是读取和写入使用[QDataStream](qdatastream.html) or [QTextStream](qtextstream.html)，但你也可以致电[QIODevice](qiodevice.html)继承功能[read](qiodevice.html#read)（ ）[readLine](qiodevice.html#readLine)（ ）[readAll](qiodevice.html#readAll)（ ）[write](qiodevice.html#write)（ ） 。 QFile时也继承[getChar](qiodevice.html#getChar)（ ）[putChar](qiodevice.html#putChar)（）和[ungetChar](qiodevice.html#ungetChar)（），它在工作时一个字符。

该文件的大小是由返回[size](qfile.html#size)（ ） 。您可以使用获取当前文件位置[pos](qfile.html#pos)（ ） ，或者移动到使用新的文件位置[seek](qfile.html#seek)（ ） 。如果你已经达到了文件的末尾，[atEnd](qfile.html#atEnd)（ ）返回True 。

### Reading Files Directly

下面的例子逐行读取文本文件中的行：

```
     QFile file("in.txt");
     if (!file.open([QIODevice](qiodevice.html).ReadOnly | [QIODevice](qiodevice.html).Text))
         return;

     while (!file.atEnd()) {
         [QByteArray](qbytearray.html) line = file.readLine();
         process_line(line);
     }

```

该[QIODevice.Text](qiodevice.html#OpenModeFlag-enum)标志传递给[open](qfile.html#open)（ ）告诉Qt转换的Windows风格的行结束符（ “ \ r \ n ” ）为C + +风格的终结符（ “\ N” ） 。默认情况下， QFile时假定二进制，即它不存储在文件中的字节执行任何转换。

### Using Streams to Read Files

下面的示例使用[QTextStream](qtextstream.html)按行读取文本文件中的行：

```
     QFile file("in.txt");
     if (!file.open([QIODevice](qiodevice.html).ReadOnly | [QIODevice](qiodevice.html).Text))
         return;

     [QTextStream](qtextstream.html) in(&file);
     while (!in.atEnd()) {
         [QString](qstring.html) line = in.readLine();
         process_line(line);
     }

```

[QTextStream](qtextstream.html)需要将存储在磁盘上的8位数据转换成16位的Unicode的护理[QString](qstring.html)。默认情况下，它假定用户系统的本地8位编码被使用（例如， ISO 8859-1欧洲大部分地区;见[QTextCodec.codecForLocale](qtextcodec.html#codecForLocale)（ ）了解详情） 。这可以通过使用setCodec （ ）来改变。

写文字，我们可以使用操作符\u003c\u003c （ ） ，这是重载采取[QTextStream](qtextstream.html)在左侧和各种数据类型（包括[QString](qstring.html)）右侧：

```
     QFile file("out.txt");
     if (!file.open([QIODevice](qiodevice.html).WriteOnly | [QIODevice](qiodevice.html).Text))
         return;

     [QTextStream](qtextstream.html) out(&file);
     out << "The magic number is: " << 49 << "\n";

```

[QDataStream](qdatastream.html)是相似的，你可以使用操作符\u003c\u003c （）写数据和操作员\u003e\u003e （）来读取它。请参阅类文档。

当您使用QFile时，[QFileInfo](qfileinfo.html)和[QDir](qdir.html)访问与Qt的文件系统，可以使用Unicode文件名。在Unix上，这些文件名转换为8位编码。如果你想使用标准C + +的API （`&lt;cstdio&gt;` or `&lt;iostream&gt;`）或特定于平台的API来访问文件，而不是QFile时，您可以使用[encodeName](qfile.html#encodeName)（）和[decodeName](qfile.html#decodeName)（ ）函数来Unicode文件名和8位文件名之间转换。

在Unix中，有一些特殊的系统文件（例如，在`/proc`）索取[size](qfile.html#size)（ ）将总是返回0 ，但你仍然可以从这样一个文件中读取更多的数据，该数据被直接回应你的呼唤​​产生[read](qiodevice.html#read)（ ） 。在这种情况下，但是，你不能使用[atEnd](qfile.html#atEnd)（） ，以确定是否有更多的数据读取（自[atEnd](qfile.html#atEnd)（ ）将返回True ，声称有大小为0的文件） 。相反，你应该调用[readAll](qiodevice.html#readAll)（ ） ，或致电[read](qiodevice.html#read)（）或[readLine](qiodevice.html#readLine)（ ）直到没有更多的数据可以被读取。下面的示例使用[QTextStream](qtextstream.html) to read `/proc/modules`一行一行：

```
     QFile file("/proc/modules");
     if (!file.open([QIODevice](qiodevice.html).ReadOnly | [QIODevice](qiodevice.html).Text))
         return;

     [QTextStream](qtextstream.html) in(&file);
     [QString](qstring.html) line = in.readLine();
     while (!line.isNull()) {
         process_line(line);
         line = in.readLine();
     }

```

### Signals

不像其他的[QIODevice](qiodevice.html)实现方式中，如[QTcpSocket](qtcpsocket.html)， QFile时不发出[aboutToClose](qiodevice.html#aboutToClose)（ ）[bytesWritten](qiodevice.html#bytesWritten)（） ，或[readyRead](qiodevice.html#readyRead)（ ）信号。这实现细节意味着的QFile是不适合读，写某些类型的文件，比如在Unix平台上的设备文件。

### Platform Specific Issues

文件权限在Linux / Mac的OS X和Windows不同的处理。在一个非[writable](qiodevice.html#isWritable)在Linux目录，不能创建文件。这并不总是在Windows上，在那里，比如， “我的文档”目录通常是不可写的，但它还是有可能在其中创建文件的情况下。

* * *

## Type Documentation

```
QFile.FileError
```

该枚举描述了可以通过返回的错误[error](qfile.html#error)（）函数。

| Constant | Value | Description |
| --- | --- | --- |
| `QFile.NoError` | `0` | 未发生错误。 |
| `QFile.ReadError` | `1` | 从文件中读取数据时发生错误。 |
| `QFile.WriteError` | `2` | 写入文件时发生错误。 |
| `QFile.FatalError` | `3` | 发生致命错误。 |
| `QFile.ResourceError` | `4` |   |
| `QFile.OpenError` | `5` | 该文件无法打开。 |
| `QFile.AbortError` | `6` | 该操作被中止。 |
| `QFile.TimeOutError` | `7` | 发生超时。 |
| `QFile.UnspecifiedError` | `8` | 发生未指定的错误。 |
| `QFile.RemoveError` | `9` | 该文件不能被删除。 |
| `QFile.RenameError` | `10` | 该文件无法重命名。 |
| `QFile.PositionError` | `11` | 在文件中的位置不能改变。 |
| `QFile.ResizeError` | `12` | 该文件不能被调整大小。 |
| `QFile.PermissionsError` | `13` | 该文件无法访问。 |
| `QFile.CopyError` | `14` | 该文件不能被复制。 |

```
QFile.FileHandleFlag
```

打开一个文件来指定仅适用于文件，而不是一个通用的附加选项时，此枚举使用[QIODevice](qiodevice.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QFile.AutoCloseHandle` | `0x0001` | 传入的文件句柄[open](qfile.html#open)（ ）应当由被关闭[close](qfile.html#close)（ ） ，默认的行为是密切刚刚刷新的文件和应用程序负责关闭文件句柄。当打开一个文件的名字，这个标志被忽略，因为Qt的总是“拥有”的文件句柄，并且必须关闭它。 |
| `QFile.DontCloseHandle` | `0` | 传入的文件句柄[open](qfile.html#open)（）将不会被Qt封闭。该应用程序必须确保[close](qfile.html#close)（）被调用。 |

这个枚举被引入或修改的Qt 4.8 。

该FileHandleFlags类型是一个typedef为[QFlags](index.htm)\u003cFileHandleFlag\u003e 。它存储FileHandleFlag值的或组合。

```
QFile.MemoryMapFlags
```

该枚举描述了可以使用的特殊选项[map](qfile.html#map)（）函数。

| Constant | Value | Description |
| --- | --- | --- |
| `QFile.NoOptions` | `0` | 没有选项。 |

这个枚举被引入或修改的Qt 4.4 。

```
QFile.Permission
```

此枚举所使用的许可（ ）函数来报告的权限和文件的所有权。该值可以是或的结果一起测试多个权限和所有权值。

| Constant | Value | Description |
| --- | --- | --- |
| `QFile.ReadOwner` | `0x4000` | 该文件是由文件的所有者可读。 |
| `QFile.WriteOwner` | `0x2000` | 该文件是可写的文件的所有者。 |
| `QFile.ExeOwner` | `0x1000` | 该文件是由文件的所有者可执行文件。 |
| `QFile.ReadUser` | `0x0400` | 该文件是由用户可读。 |
| `QFile.WriteUser` | `0x0200` | 该文件是可写的用户。 |
| `QFile.ExeUser` | `0x0100` | 该文件是可执行的用户。 |
| `QFile.ReadGroup` | `0x0040` | 该文件是由组读取。 |
| `QFile.WriteGroup` | `0x0020` | 该文件是可写的组。 |
| `QFile.ExeGroup` | `0x0010` | 该文件是由集团的可执行文件。 |
| `QFile.ReadOther` | `0x0004` | 该文件可以被任何人读取。 |
| `QFile.WriteOther` | `0x0002` | 该文件是可写的权限。 |
| `QFile.ExeOther` | `0x0001` | 该文件是由人执行。 |

**Warning:**因为在Qt所支持的平台不同， ReadUser ， WriteUser和ExeUser的语义是与平台相关的：在Unix上，返回该文件的所有者的权利和Windows是返回当前用户的权限。这种行为可能会改变在未来的Qt版本。

注意Qt默认不检查NTFS文件系统权限，因为这可能会降低文件处理相当的性能。它可以强制许可通过在源下面的代码检查在NTFS ：

```
 extern Q_CORE_EXPORT int qt_ntfs_permission_lookup;

```

权限检查，然后开启和关闭由递增和递减`qt_ntfs_permission_lookup`通过1 。

```
 qt_ntfs_permission_lookup++; // turn checking on
 qt_ntfs_permission_lookup--; // turn it off again

```

权限类型是一个typedef为[QFlags](index.htm)\u003cPermission\u003e 。它存储权限值的或组合。

* * *

## Method Documentation

```
QFile.__init__ (self)
```

构造一个新的文件对象来表示文件给定的_name_。

```
QFile.__init__ (self, QString name)
```

```
QFile.__init__ (self, QObject parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的文件对象与给定_parent_。

```
QFile.__init__ (self, QString name, QObject parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的文件对象与给定_parent_来表示该文件具有指定的_name_。

```
bool QFile.atEnd (self)
```

从重新实现[QIODevice.atEnd](qiodevice.html#atEnd)（ ） 。

返回True如果文件的末尾已经达到，否则返回False 。

对于UNIX上的（例如那些在常规空文件`/proc`） ，这个函数返回True ，因为文件系统报告，这样的文件的大小为0 。因此，您不应该依赖于了atEnd （）从这些文件中读取数据时，而是调用[read](qiodevice.html#read)（），直到没有更多的数据可以被读取。

```
QFile.close (self)
```

从重新实现[QIODevice.close](qiodevice.html#close)（ ） 。

电话[QFile.flush](qfile.html#flush)（）和关闭该文件。从齐平的错误被忽略。

**See also** [QIODevice.close](qiodevice.html#close)（ ） 。

```
bool QFile.copy (self, QString newName)
```

目前由指定将文件复制[fileName](qfile.html#fileName)（ ）到一个名为_newName_。成功返回True ，否则返回False 。

请注意，如果有名称的文件_newName_已经存在，复制（ ）返回FALSE（即[QFile](qfile.html)不会复盖它）。

源文件被关闭之前，它被复制。

**See also** [setFileName](qfile.html#setFileName)（ ） 。

```
bool QFile.copy (QString fileName, QString newName)
```

这是一个重载函数。

复制文件_fileName_至_newName_。成功返回True ，否则返回False 。

如果有名称的文件_newName_已经存在，则[copy](qfile.html#copy)（ ）返回False （即，[QFile](qfile.html)不会复盖它）。

**See also** [rename](qfile.html#rename)（ ） 。

```
QString QFile.decodeName (QByteArray localFileName)
```

这样做的逆[QFile.encodeName](qfile.html#encodeName)（ ）使用_localFileName_。

**See also** [setDecodingFunction](qfile.html#setDecodingFunction)（）和[encodeName](qfile.html#encodeName)（ ） 。

```
QString QFile.decodeName (str localFileName)
```

这是一个重载函数。

返回Unicode版本的给定_localFileName_。看[encodeName](qfile.html#encodeName)（ ）了解详情。

```
QByteArray QFile.encodeName (QString fileName)
```

[

默认情况下，此功能将_fileName_通过用户的语言环境来确定本地8位编码。这足以让用户选择的文件名。文件名硬编码到应用程序中应该只使用7位ASCII字符的文件名。

](qbytearray.html)

[**See also**](qbytearray.html) [decodeName](qfile.html#decodeName)（）和[setEncodingFunction](qfile.html#setEncodingFunction)（ ） 。

```
FileError QFile.error (self)
```

[

返回文件的错误状态。

](qfile.html#FileError-enum)

[在I / O设备的状态返回一个错误代码。例如，如果](qfile.html#FileError-enum)[open](qfile.html#open)（ ）返回False ，或读/写操作返回-1 ，该函数可以被调用来找出原因操作失败的原因。

**See also** [unsetError](qfile.html#unsetError)（ ） 。

```
bool QFile.exists (self)
```

返回True如果指定的文件_fileName_存在，否则返回False 。

```
bool QFile.exists (QString fileName)
```

这是一个重载函数。

返回True如果指定的文件[fileName](qfile.html#fileName)（ ）存在，否则返回False 。

**See also** [fileName](qfile.html#fileName)（）和[setFileName](qfile.html#setFileName)（ ） 。

```
QAbstractFileEngine QFile.fileEngine (self)
```

[

```
QString QFile.fileName (self)
```

](qabstractfileengine.html)

[返回名称按设定](qabstractfileengine.html)[setFileName](qfile.html#setFileName)（ ）或向[QFile](qfile.html)构造函数。

**See also** [setFileName](qfile.html#setFileName)（）和[QFileInfo.fileName](qfileinfo.html#fileName)（ ） 。

```
bool QFile.flush (self)
```

刷新所有缓冲的数据文件。成功返回True ，否则返回False 。

```
int QFile.handle (self)
```

返回文件的文件句柄。

这是一个小的正整数，适合与C库函数，如fdopen （ ）和fcntl （ ）的使用。在使用文件描述符的套接字（即Unix系统，而不是Windows）中的句柄可以被使用的系统[QSocketNotifier](qsocketnotifier.html)为好。

如果文件没有打开，或者有错误，手柄（ ）返回-1 。

此功能不支持Windows CE 。

在Symbian ，这个函数返回-1，如果该文件被正常开启，为基于Symbian操作系统的文件句柄不适合在一个int ，并与该手柄将用于C库函数不兼容。如果文件是使用采取开放的C库文件句柄/文件描述符重载打开，那么这个函数返回相同的句柄。

**See also** [QSocketNotifier](qsocketnotifier.html)。

```
bool QFile.isSequential (self)
```

从重新实现[QIODevice.isSequential](qiodevice.html#isSequential)（ ） 。

返回True如果该文件只能按顺序操作，否则返回False 。

大多数文件支持随机访问，但一些特殊的文件可能不会。

**See also** [QIODevice.isSequential](qiodevice.html#isSequential)（ ） 。

```
bool QFile.link (self, QString newName)
```

创建一个名为链接_linkName_指向当前所指定的文件[fileName](qfile.html#fileName)（ ） 。什么链接是依赖于底层的文件系统（无论是在Windows还是Unix上符号链接的快捷方式）上。成功返回True ，否则返回False 。

此功能不会复盖已经存在的实体在文件系统中，在这种情况下，`link()`将返回False ，并设置[error()](qfile.html#error) to return [RenameError](qfile.html#FileError-enum)。

**Note:**要创建在Windows上的有效链接，_linkName_必须有一个`.lnk`文件扩展名。

**Note:**Symbian的文件系统不支持链接。

**See also** [setFileName](qfile.html#setFileName)（ ） 。

```
bool QFile.link (QString oldname, QString newName)
```

这是一个重载函数。

创建一个名为链接_linkName_指向该文件_fileName_。什么链接是依赖于底层的文件系统（无论是在Windows还是Unix上符号链接的快捷方式）上。成功返回True ，否则返回False 。

**See also** [link](qfile.html#link)（ ） 。

```
sip.voidptr QFile.map (self, int offset, int size, MemoryMapFlags flags = QFile.NoOptions)
```

地图_size_该文件的字节到存储器中，起始_offset_。一个文件应该是开放的地图成功，但该文件并不需要保持开放的内存被映射后。当[QFile](qfile.html)被破坏或一个新的文件打开与该对象，还没有被映射任何地图将自动被取消映射。

任何映射选项可以通过传递_flags_。

返回一个指针，该存储器或0，如果存在错误。

**Note:**在Windows CE 5.0的映射发生前的文件将被关闭。

此功能被引入Qt的4.4 。

**See also** [unmap](qfile.html#unmap)（）和[QAbstractFileEngine.supportsExtension](qabstractfileengine.html#supportsExtension)（ ） 。

```
bool QFile.open (self, QIODevice.OpenMode flags)
```

从重新实现[QIODevice.open](qiodevice.html#open)（ ） 。

打开使用文件[OpenMode](qiodevice.html#OpenModeFlag-enum) _mode_如果成功，则返回True ，否则返回False 。

该_mode_必须是[QIODevice.ReadOnly](qiodevice.html#OpenModeFlag-enum)，[QIODevice.WriteOnly](qiodevice.html#OpenModeFlag-enum)或[QIODevice.ReadWrite](qiodevice.html#OpenModeFlag-enum)。它也可能有额外的标记，如[QIODevice.Text](qiodevice.html#OpenModeFlag-enum)和[QIODevice.Unbuffered](qiodevice.html#OpenModeFlag-enum)。

**Note:** In [WriteOnly](qiodevice.html#OpenModeFlag-enum) or [ReadWrite](qiodevice.html#OpenModeFlag-enum)模式下，如果相关的文件不存在，该函数将尝试打开它之前，创建一个新的文件。

**See also** [QIODevice.OpenMode](qiodevice.html#OpenModeFlag-enum)和[setFileName](qfile.html#setFileName)（ ） 。

```
bool QFile.open (self, int fd, QIODevice.OpenMode flags)
```

```
bool QFile.open (self, int fd, QIODevice.OpenMode flags, FileHandleFlags handleFlags)
```

```
Permissions QFile.permissions (self)
```

[](index.htm)

[返回的完整或的结果组合在一起](index.htm)[QFile.Permission](qfile.html#Permission-enum)对于该文件。

**See also** [setPermissions](qfile.html#setPermissions)（）和[setFileName](qfile.html#setFileName)（ ） 。

```
Permissions QFile.permissions (QString filename)
```

[

这是一个重载函数。

](index.htm)

[返回的完整或的结果组合在一起](index.htm)[QFile.Permission](qfile.html#Permission-enum)为_fileName_。

```
int QFile.pos (self)
```

从重新实现[QIODevice.pos](qiodevice.html#pos)（ ） 。

```
str QFile.readData (self, int maxlen)
```

从重新实现[QIODevice.readData](qiodevice.html#readData)（ ） 。

```
str QFile.readLineData (self, int maxlen)
```

从重新实现[QIODevice.readLineData](qiodevice.html#readLineData)（ ） 。

```
QString QFile.readLink (self)
```

```
QString QFile.readLink (QString fileName)
```

```
bool QFile.remove (self)
```

通过删除指定的文件[fileName](qfile.html#fileName)（ ） 。成功返回True ，否则返回False 。

它被删除之前，该文件被关闭。

**See also** [setFileName](qfile.html#setFileName)（ ） 。

```
bool QFile.remove (QString fileName)
```

这是一个重载函数。

移除由指定的文件_fileName_给出。

成功返回True ，否则返回False 。

**See also** [remove](qfile.html#remove)（ ） 。

```
bool QFile.rename (self, QString newName)
```

重命名当前由指定的文件[fileName](qfile.html#fileName)（）来_newName_。成功返回True ，否则返回False 。

如果有名称的文件_newName_已经存在，重命名（ ）返回FALSE（即，[QFile](qfile.html)不会复盖它）。

该文件被关闭它将被重命名之前。

**See also** [setFileName](qfile.html#setFileName)（ ） 。

```
bool QFile.rename (QString oldName, QString newName)
```

这是一个重载函数。

重命名文件_oldName_至_newName_。成功返回True ，否则返回False 。

如果有名称的文件_newName_已经存在，则[rename](qfile.html#rename)（ ）返回False （即，[QFile](qfile.html)不会复盖它）。

**See also** [rename](qfile.html#rename)（ ） 。

```
bool QFile.resize (self, int sz)
```

设置文件的大小（以字节为单位）_sz_。返回True如果该文件，如果大小调整成功，否则返回False 。如果_sz_比文件大目前是新的字节将被设置为0，如果_sz_较小的文件被简单地截断。

**See also** [size](qfile.html#size)（）和[setFileName](qfile.html#setFileName)（ ） 。

```
bool QFile.resize (QString filename, int sz)
```

这是一个重载函数。

Sets _fileName_大小（以字节为单位）_sz_。返回True如果该文件，如果大小调整成功，否则返回False 。如果_sz_大于_fileName_目前是新的字节将被设置为0，如果_sz_较小的文件被简单地截断。

**See also** [resize](qfile.html#resize)（ ） 。

```
bool QFile.seek (self, int offset)
```

从重新实现[QIODevice.seek](qiodevice.html#seek)（ ） 。

对于随机存取设备，此函数设置当前位置_pos_，返回True表示成功，或False，如果发生了错误。对于顺序的设备，默认的行为是什么都不做，返回False 。

寻求超越一个文件的结尾：如果位置超出了文件的末尾，再求（ ）不得立即扩展文件。如果写在这个位置上进行，那么该文件将被延长。该文件的文件的前端部和新写入的数据之间的内容是不确定的，平台和文件系统之间的不同而不同。

```
QFile.setFileName (self, QString name)
```

设置_name_该文件的。该名称可以没有路径，相对路径或绝对路径。

不要调用这个函数，如果该文件已经被打开。

如果文件名没有路径或相对路径，使用的路径将是应用程序的当前目录路径_at the time of the [open](qfile.html#open)()_打电话。

例如：

```
 [QFile](qfile.html) file;
 [QDir](qdir.html).setCurrent("/tmp");
 file.setFileName("readme.txt");
 [QDir](qdir.html).setCurrent("/home");
 file.open([QIODevice](qiodevice.html).ReadOnly);      // opens "/home/readme.txt" under Unix

```

请注意目录分隔符“/”适用于Qt所支持的所有操作系统。

**See also** [fileName](qfile.html#fileName)（ ）[QFileInfo](qfileinfo.html)和[QDir](qdir.html)。

```
bool QFile.setPermissions (self, Permissions permissionSpec)
```

设置权限的文件到_permissions_规定。返回True，如果成功，则返回False的权限不能被修改。

**See also** [permissions](qfile.html#permissions)（）和[setFileName](qfile.html#setFileName)（ ） 。

```
bool QFile.setPermissions (QString filename, Permissions permissionSpec)
```

这是一个重载函数。

设置权限_fileName_文件以_permissions_。

```
int QFile.size (self)
```

从重新实现[QIODevice.size](qiodevice.html#size)（ ） 。

返回文件的大小。

对于UNIX上的（例如那些在常规空文件`/proc`） ，该函数返回0;这样一个文件的内容按要求在响应你的呼唤​​产生[read](qiodevice.html#read)（ ） 。

```
QString QFile.symLinkTarget (self)
```

返回由符号链接（或快捷方式在Windows上）所指的文件或目录被指定的绝对路径_fileName_，或者返回一个空字符串，如果_fileName_没有对应的符号链接。

这个名字可能并不代表现有的文件，它只是一个字符串。[QFile.exists](qfile.html#exists)（ ）返回True ，如果符号链接指向现有的文件。

这个函数中引入了Qt 4.2中。

```
QString QFile.symLinkTarget (QString fileName)
```

这是一个重载函数。

返回文件或目录的符号链接的绝对路径（或快捷方式在Windows上）指向，或者如果对象不是一个符号链接一个空字符串。

这个名字可能并不代表现有的文件，它只是一个字符串。[QFile.exists](qfile.html#exists)（ ）返回True ，如果符号链接指向现有的文件。

这个函数中引入了Qt 4.2中。

**See also** [fileName](qfile.html#fileName)（）和[setFileName](qfile.html#setFileName)（ ） 。

```
bool QFile.unmap (self, sip.voidptr address)
```

取消映射的内存_address_。

返回True如果取消映射成功，否则返回False 。

此功能被引入Qt的4.4 。

**See also** [map](qfile.html#map)（）和[QAbstractFileEngine.supportsExtension](qabstractfileengine.html#supportsExtension)（ ） 。

```
QFile.unsetError (self)
```

设置文件的错误[QFile.NoError](qfile.html#FileError-enum)。

**See also** [error](qfile.html#error)（ ） 。

```
int QFile.writeData (self, str data)
```

从重新实现[QIODevice.writeData](qiodevice.html#writeData)（ ） 。