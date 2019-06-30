# QFSFileEngine Class Reference

## [[QtCore](index.htm) module]

该QFSFileEngine类实现Qt的默认文件引擎。[More...](#details)

继承[QAbstractFileEngine](qabstractfileengine.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QString file)`
*   `bool caseSensitive (self)`
*   `bool close (self)`
*   `bool copy (self, QString newName)`
*   `QStringList entryList (self, QDir.Filters filters, QStringList filterNames)`
*   `QAbstractFileEngine.FileFlags fileFlags (self, QAbstractFileEngine.FileFlags type)`
*   `QString fileName (self, QAbstractFileEngine.FileName file)`
*   `QDateTime fileTime (self, QAbstractFileEngine.FileTime time)`
*   `bool flush (self)`
*   `int handle (self)`
*   `bool isRelativePath (self)`
*   `bool isSequential (self)`
*   `bool link (self, QString newName)`
*   `bool mkdir (self, QString dirName, bool createParentDirectories)`
*   `bool open (self, QIODevice.OpenMode openMode)`
*   `bool open (self, QIODevice.OpenMode openMode, int fd, QFile.FileHandleFlags handleFlags)`
*   `bool open (self, QIODevice.OpenMode flags, int fd)`
*   `QString owner (self, QAbstractFileEngine.FileOwner)`
*   `int ownerId (self, QAbstractFileEngine.FileOwner)`
*   `int pos (self)`
*   `str read (self, int maxlen)`
*   `str readLine (self, int maxlen)`
*   `bool remove (self)`
*   `bool rename (self, QString newName)`
*   `bool rmdir (self, QString dirName, bool recurseParentDirectories)`
*   `bool seek (self, int)`
*   `setFileName (self, QString file)`
*   `bool setPermissions (self, int perms)`
*   `bool setSize (self, int size)`
*   `int size (self)`
*   `int write (self, str data)`

### Static Methods

*   `QString currentPath (QString fileName = QString())`
*   `list-of-QFileInfo drives ()`
*   `QString homePath ()`
*   `QString rootPath ()`
*   `bool setCurrentPath (QString path)`
*   `QString tempPath ()`

* * *

## Detailed Description

该QFSFileEngine类实现Qt的默认文件引擎。

这个类是文件引擎框架Qt中的一部分。如果只想访问文件或目录，请使用[QFile](qfile.html)，[QFileInfo](qfileinfo.html) or [QDir](qdir.html)代替。

QFSFileEngine是默认的文件引擎，访问普通文件。它是提供了方便;通过继承这个类，你可以稍微改变它的行为，而无需编写一个完整的[QAbstractFileEngine](qabstractfileengine.html)子类。要安装自定义文件引擎，你也必须继承[QAbstractFileEngineHandler](qabstractfileenginehandler.html)并创建处理程序的实例。

它也可以是有用的，直接创建一个QFSFileEngine对象，如果你需要使用内部的本地文件系统[QAbstractFileEngine.create](qabstractfileengine.html#create)（） ，以避免递归（如更高层次的类往往称之为[QAbstractFileEngine.create](qabstractfileengine.html#create)（））。

* * *

## Method Documentation

```
QFSFileEngine.__init__ (self)
```

构造一个[QFSFileEngine](qfsfileengine.html)。

```
QFSFileEngine.__init__ (self, QString file)
```

构造一个[QFSFileEngine](qfsfileengine.html)为文件名_file_。

```
bool QFSFileEngine.caseSensitive (self)
```

从重新实现[QAbstractFileEngine.caseSensitive](qabstractfileengine.html#caseSensitive)（ ） 。

适用于Windows ，假为Unix ，则返回True 。

```
bool QFSFileEngine.close (self)
```

从重新实现[QAbstractFileEngine.close](qabstractfileengine.html#close)（ ） 。

```
bool QFSFileEngine.copy (self, QString newName)
```

从重新实现[QAbstractFileEngine.copy](qabstractfileengine.html#copy)（ ） 。

对于Windows，将文件复制到文件_copyName_。

未实现为Unix 。

```
QString QFSFileEngine.currentPath (QString fileName = QString())
```

对于Unix ，返回文件引擎的当前工作目录。

对于Windows ，返回当前路径由指定的驱动器所使用的文件引擎的规范化形式_fileName_。在Windows中，每个驱动器都有自己的当前目录，因此不同的路径返回的文件名，包括不同的驱动器名称（如A ：或C :) 。

**See also** [setCurrentPath](qfsfileengine.html#setCurrentPath)（ ） 。

```
list-of-QFileInfo QFSFileEngine.drives ()
```

对于Windows ，返回文件系统的驱动器列表作为列表[QFileInfo](qfileinfo.html)对象。在UNIX上， Mac OS X和Windows CE中，只返回根路径。在Windows中，该函数返回所有驱动器（A ： ， C：，D ：等） 。

对于Unix ，该列表仅包含根路径“ / ” 。

```
QStringList QFSFileEngine.entryList (self, QDir.Filters filters, QStringList filterNames)
```

```
QAbstractFileEngine.FileFlags QFSFileEngine.fileFlags (self, QAbstractFileEngine.FileFlags type)
```

[](index.htm)

[从重新实现](index.htm)[QAbstractFileEngine.fileFlags](qabstractfileengine.html#fileFlags)（ ） 。

```
QString QFSFileEngine.fileName (self, QAbstractFileEngine.FileName file)
```

从重新实现[QAbstractFileEngine.fileName](qabstractfileengine.html#fileName)（ ） 。

**See also** [setFileName](qfsfileengine.html#setFileName)（ ） 。

```
QDateTime QFSFileEngine.fileTime (self, QAbstractFileEngine.FileTime time)
```

[](qdatetime.html)

[从重新实现](qdatetime.html)[QAbstractFileEngine.fileTime](qabstractfileengine.html#fileTime)（ ） 。

```
bool QFSFileEngine.flush (self)
```

从重新实现[QAbstractFileEngine.flush](qabstractfileengine.html#flush)（ ） 。

```
int QFSFileEngine.handle (self)
```

从重新实现[QAbstractFileEngine.handle](qabstractfileengine.html#handle)（ ） 。

```
QString QFSFileEngine.homePath ()
```

返回当前用户的主目录路径。

**See also** [rootPath](qfsfileengine.html#rootPath)（ ） 。

```
bool QFSFileEngine.isRelativePath (self)
```

从重新实现[QAbstractFileEngine.isRelativePath](qabstractfileengine.html#isRelativePath)（ ） 。

```
bool QFSFileEngine.isSequential (self)
```

从重新实现[QAbstractFileEngine.isSequential](qabstractfileengine.html#isSequential)（ ） 。

```
bool QFSFileEngine.link (self, QString newName)
```

从重新实现[QAbstractFileEngine.link](qabstractfileengine.html#link)（ ） 。

从创建该文件目前由指定的链接[fileName](qfsfileengine.html#fileName)（）来_newName_。什么链接是依赖于底层的文件系统（无论是在Windows还是Unix上符号链接的快捷方式）上。成功返回True ，否则返回False 。

```
bool QFSFileEngine.mkdir (self, QString dirName, bool createParentDirectories)
```

从重新实现[QAbstractFileEngine.mkdir](qabstractfileengine.html#mkdir)（ ） 。

```
bool QFSFileEngine.open (self, QIODevice.OpenMode openMode)
```

从重新实现[QAbstractFileEngine.open](qabstractfileengine.html#open)（ ） 。

```
bool QFSFileEngine.open (self, QIODevice.OpenMode openMode, int fd, QFile.FileHandleFlags handleFlags)
```

打开文件句柄_fh_在_openMode_模式。成功时返回TRUE ，否则返回False 。

```
bool QFSFileEngine.open (self, QIODevice.OpenMode flags, int fd)
```

打开文件描述符_fd_在_openMode_模式。成功时返回TRUE ，否则返回False 。

```
QString QFSFileEngine.owner (self, QAbstractFileEngine.FileOwner)
```

从重新实现[QAbstractFileEngine.owner](qabstractfileengine.html#owner)（ ） 。

```
int QFSFileEngine.ownerId (self, QAbstractFileEngine.FileOwner)
```

从重新实现[QAbstractFileEngine.ownerId](qabstractfileengine.html#ownerId)（ ） 。

在Unix中，如果统计（ ）是成功的，`uid`如果返回_own_是所有者。否则，`gid`返回。如果统计（ ）不成功，-2是reuturned 。

对于Windows ，总是返回-2 。

```
int QFSFileEngine.pos (self)
```

从重新实现[QAbstractFileEngine.pos](qabstractfileengine.html#pos)（ ） 。

```
str QFSFileEngine.read (self, int maxlen)
```

从重新实现[QAbstractFileEngine.read](qabstractfileengine.html#read)（ ） 。

```
str QFSFileEngine.readLine (self, int maxlen)
```

从重新实现[QAbstractFileEngine.readLine](qabstractfileengine.html#readLine)（ ） 。

```
bool QFSFileEngine.remove (self)
```

从重新实现[QAbstractFileEngine.remove](qabstractfileengine.html#remove)（ ） 。

```
bool QFSFileEngine.rename (self, QString newName)
```

从重新实现[QAbstractFileEngine.rename](qabstractfileengine.html#rename)（ ） 。

```
bool QFSFileEngine.rmdir (self, QString dirName, bool recurseParentDirectories)
```

从重新实现[QAbstractFileEngine.rmdir](qabstractfileengine.html#rmdir)（ ） 。

```
QString QFSFileEngine.rootPath ()
```

返回根路径。

**See also** [homePath](qfsfileengine.html#homePath)（ ） 。

```
bool QFSFileEngine.seek (self, int)
```

从重新实现[QAbstractFileEngine.seek](qabstractfileengine.html#seek)（ ） 。

```
bool QFSFileEngine.setCurrentPath (QString path)
```

设置当前路径（例如，用于[QDir](qdir.html)） ，以_path_。返回True如果新的路径存在，否则这个函数不执行任何操作，并返回False 。

**See also** [currentPath](qfsfileengine.html#currentPath)（ ） 。

```
QFSFileEngine.setFileName (self, QString file)
```

从重新实现[QAbstractFileEngine.setFileName](qabstractfileengine.html#setFileName)（ ） 。

**See also** [fileName](qfsfileengine.html#fileName)（ ） 。

```
bool QFSFileEngine.setPermissions (self, int perms)
```

从重新实现[QAbstractFileEngine.setPermissions](qabstractfileengine.html#setPermissions)（ ） 。

```
bool QFSFileEngine.setSize (self, int size)
```

从重新实现[QAbstractFileEngine.setSize](qabstractfileengine.html#setSize)（ ） 。

**See also** [size](qfsfileengine.html#size)（ ） 。

```
int QFSFileEngine.size (self)
```

从重新实现[QAbstractFileEngine.size](qabstractfileengine.html#size)（ ） 。

**See also** [setSize](qfsfileengine.html#setSize)（ ） 。

```
QString QFSFileEngine.tempPath ()
```

返回临时路径（即在它是安全的存储临时文件的路径） 。

```
int QFSFileEngine.write (self, str data)
```

从重新实现[QAbstractFileEngine.write](qabstractfileengine.html#write)（ ） 。