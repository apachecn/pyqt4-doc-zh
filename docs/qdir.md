# QDir Class Reference

## [[QtCore](index.htm) module]

归QDir类提供了访问目录结构和它们的内容。[More...](#details)

### Types

*   `enum Filter { Dirs, Files, Drives, NoSymLinks, ..., NoDotDot }`
*   `class **[Filters](index.htm)**`
*   `enum SortFlag { Name, Time, Size, Unsorted, ..., NoSort }`
*   `class **[SortFlags](index.htm)**`

### Methods

*   `__init__ (self, QDir)`
*   `__init__ (self, QString path = QString())`
*   `__init__ (self, QString path, QString nameFilter, SortFlags sort = QDir.Name|QDir.IgnoreCase, Filters filters = QDir.AllEntries)`
*   `QString absoluteFilePath (self, QString fileName)`
*   `QString absolutePath (self)`
*   `QString canonicalPath (self)`
*   `bool cd (self, QString dirName)`
*   `bool cdUp (self)`
*   `int count (self)`
*   `QString dirName (self)`
*   `list-of-QFileInfo entryInfoList (self, Filters filters = QDir.NoFilter, SortFlags sort = QDir.NoSort)`
*   `list-of-QFileInfo entryInfoList (self, QStringList nameFilters, Filters filters = QDir.NoFilter, SortFlags sort = QDir.NoSort)`
*   `QStringList entryList (self, Filters filters = QDir.NoFilter, SortFlags sort = QDir.NoSort)`
*   `QStringList entryList (self, QStringList nameFilters, Filters filters = QDir.NoFilter, SortFlags sort = QDir.NoSort)`
*   `bool exists (self)`
*   `bool exists (self, QString name)`
*   `QString filePath (self, QString fileName)`
*   `Filters filter (self)`
*   `bool isAbsolute (self)`
*   `bool isReadable (self)`
*   `bool isRelative (self)`
*   `bool isRoot (self)`
*   `bool makeAbsolute (self)`
*   `bool mkdir (self, QString dirName)`
*   `bool mkpath (self, QString dirPath)`
*   `QStringList nameFilters (self)`
*   `QString path (self)`
*   `refresh (self)`
*   `QString relativeFilePath (self, QString fileName)`
*   `bool remove (self, QString fileName)`
*   `bool rename (self, QString oldName, QString newName)`
*   `bool rmdir (self, QString dirName)`
*   `bool rmpath (self, QString dirPath)`
*   `setFilter (self, Filters filter)`
*   `setNameFilters (self, QStringList nameFilters)`
*   `setPath (self, QString path)`
*   `setSorting (self, SortFlags sort)`
*   `SortFlags sorting (self)`

### Static Methods

*   `addResourceSearchPath (QString path)`
*   `addSearchPath (QString prefix, QString path)`
*   `QString cleanPath (QString path)`
*   `QString convertSeparators (QString pathName)`
*   `QDir current ()`
*   `QString currentPath ()`
*   `list-of-QFileInfo drives ()`
*   `QString fromNativeSeparators (QString pathName)`
*   `QDir home ()`
*   `QString homePath ()`
*   `bool isAbsolutePath (QString path)`
*   `bool isRelativePath (QString path)`
*   `bool match (QStringList filters, QString fileName)`
*   `bool match (QString filter, QString fileName)`
*   `QStringList nameFiltersFromString (QString nameFilter)`
*   `QDir root ()`
*   `QString rootPath ()`
*   `QStringList searchPaths (QString prefix)`
*   `QChar separator ()`
*   `bool setCurrent (QString path)`
*   `setSearchPaths (QString prefix, QStringList searchPaths)`
*   `QDir temp ()`
*   `QString tempPath ()`
*   `QString toNativeSeparators (QString pathName)`

### Special Methods

*   `int __contains__ (self, QString)`
*   `bool __eq__ (self, QDir dir)`
*   `QString __getitem__ (self, int)`
*   `QStringList __getitem__ (self, slice)`
*   `__len__ (self)`
*   `bool __ne__ (self, QDir dir)`

* * *

## Detailed Description

归QDir类提供了访问目录结构和它们的内容。

一个的QDir用来操作路径名称，访问有关的路径和文件的信息，并操作底层文件系统。它也可以被用来访问Qt的[resource system](index.htm#resource-system)。

Qt使用“/”作为以同样的方式， “ / ”作为URL中的路径分隔符的通用目录分隔符。如果你总是使用“ / ”作为目录分隔符， Qt将会把你的路径，以符合底层操作系统。

一个的QDir可以指向使用相对或绝对路径的文件。绝对路径开头的目录分隔符（前面可以在Windows下的驱动器规格） 。相对文件名开头的目录名或文件名和路径指定一个相对于当前目录。

绝对路径的例子：

```
 QDir("/home/user/Documents")
 QDir("C:/Documents and Settings")

```

在Windows上，上述第二个例子将被转换为`C:\Documents and Settings`用于访问文件时。

相对路径的例子：

```
 QDir("../img/landscape.png")

```

您可以使用[isRelative](qdir.html#isRelative)（）或[isAbsolute](qdir.html#isAbsolute)（ ）函数，如果一个的QDir使用相对或绝对文件路径来检查。通话[makeAbsolute](qdir.html#makeAbsolute)（ ）到一个相对的QDir转化为绝对的。

### Navigation and Directory Operations

一个目录的路径可以用得到[path](qdir.html#pathx)（ ）函数，并设置了一个新的路径[setPath](qdir.html#setPath)（）函数。的绝对路径的目录是通过调用发现[absolutePath](qdir.html#absolutePath)（ ） 。

目录的名称使用中发现的[dirName](qdir.html#dirName)（）函数。这通常返回指定的目录的位置的绝对路径中的最后一个元素。然而，它也可以返回“ 。 ”如果的QDir表示当前目录。

```
 QDir("Documents/Letters/Applications").dirName() // "Applications"
 QDir().dirName()                                 // "."

```

对目录的路径，也可以用改变[cd](qdir.html#cd)（）和[cdUp](qdir.html#cdUp)这两者（ ）函数，操作就像熟悉shell命令。何时[cd](qdir.html#cd)（ ）被调用现有的目录的名称，归QDir对象改变目录，它表示该目录代替。该[cdUp](qdir.html#cdUp)（ ）函数改变的QDir对象的目录，以便它指的是它的父目录，即CD（ “..” ）等价于[cdUp](qdir.html#cdUp)（ ） 。

目录可以使用以下命令创建[mkdir](qdir.html#mkdir)（ ） ，重命名[rename](qdir.html#rename)（ ）中，用去除[rmdir](qdir.html#rmdir)（ ） 。

您可以通过使用测试具有给定名称的目录存在[exists](qdir.html#exists)（ ）和目录的属性可以与被测试[isReadable](qdir.html#isReadable)（ ）[isAbsolute](qdir.html#isAbsolute)（ ）[isRelative](qdir.html#isRelative)（）和[isRoot](qdir.html#isRoot)（ ） 。

该[refresh](qdir.html#refresh)（ ）函数再从磁盘读取该目录的数据。

### Files and Directory Contents

目录包含多个条目，代表文件，目录和符号链接。条目中的目录数被返回[count](qdir.html#count)（ ） 。可以得到在一个目录中的所有条目的名称的字符串列表[entryList](qdir.html#entryList)（ ） 。如果您需要了解每一个项目的信息，请使用[entryInfoList](qdir.html#entryInfoList)（）获得的一个列表[QFileInfo](qfileinfo.html)对象。

路径文件和一个目录下的目录可以使用构造[filePath](qdir.html#filePath)（）和[absoluteFilePath](qdir.html#absoluteFilePath)（ ） 。该[filePath](qdir.html#filePath)（ ）函数返回一个路径指定的文件或目录相对的QDir对象的路径;[absoluteFilePath](qdir.html#absoluteFilePath)（ ）返回一个绝对路径指定的文件或目录。无论这些函数会检查文件或目录是否存在，他们只是构建路径。

```
 QDir directory("Documents/Letters");
 [QString](qstring.html) path = directory.filePath("contents.txt");
 [QString](qstring.html) absolutePath = directory.absoluteFilePath("contents.txt");

```

文件可以通过使用可移除的[remove](qdir.html#remove)（）函数。目录不能以同样的方式作为文件被删除;使用[rmdir](qdir.html#rmdir)（）来代替删除它们。

它能够减少由返回的条目的数量[entryList](qdir.html#entryList)（）和[entryInfoList](qdir.html#entryInfoList)（ ）通过应用过滤器到的QDir对象。你可以申请一个名字过滤器来指定使用通配符模式的文件名需要匹配，属性过滤器的选择项的属性和文件和目录可以区分，和排序顺序。

名称过滤器的字符串传递给该列表[setNameFilters](qdir.html#setNameFilters)（ ） 。属性过滤器由一个过滤器按位或组合，而这些都是调用时指定[setFilter](qdir.html#setFilter)（ ） 。使用指定的排序顺序[setSorting](qdir.html#setSorting)（ ）用按位或组合[SortFlags](qdir.html#SortFlag-enum)。

你可以测试一下，看有没有使用的文件名匹配的过滤器[match](qdir.html#match)（）函数。

筛选和排序顺序标志也可能被调用时指定[entryList](qdir.html#entryList)（）和[entryInfoList](qdir.html#entryInfoList)（）以复盖先前定义的行为。

### The Current Directory and Other Special Paths

访问一些常见的目录设置有若干静态函数返回的QDir对象。还有这些返回字符串对应的功能：

| QDir | [QString](qstring.html) | Return Value |
| --- | --- | --- |
| [current](qdir.html#current)() | [currentPath](qdir.html#currentPath)() | The application's working directory |
| [home](qdir.html#home)() | [homePath](qdir.html#homePath)() | The user's home directory |
| [root](qdir.html#root)() | [rootPath](qdir.html#rootPath)() | The root directory |
| [temp](qdir.html#temp)() | [tempPath](qdir.html#tempPath)() | The system's temporary directory |

该[setCurrent](qdir.html#setCurrent)（ ）静态函数也可以用于设置应用程序的工作目录。

如果你想找到包含应用程序的可执行文件的目录，请参见[QCoreApplication.applicationDirPath](qcoreapplication.html#applicationDirPath)（ ） 。

该[drives](qdir.html#drives)（）静态函数提供为每个包含一个归档系统设备根目录的列表。在Unix系统中，这会返回一个包含单个根目录“ / ”的列表;在Windows上的列表通常包含`C:/`，以及其他可能的驱动器号，如`D:/`，这取决于用户的系统的配置。

### Path Manipulation and Strings

路径包含“ 。 ”引用当前目录在路径点的元素， “..”元素引用的父目录和符号链接可以使用减少到规范形式的[canonicalPath](qdir.html#canonicalPath)（）函数。

路径也可以通过使用简化的[cleanPath](qdir.html#cleanPath)（）删除多馀的“ / ”和“..”元素。

它有时需要能够显示在本机表示一个路径为用户的平台。静[toNativeSeparators](qdir.html#toNativeSeparators)（ ）函数返回，其中每个目录分隔符替换为适当的分隔符底层操作系统的指定路径的一个副本。

### Examples

检查目录是否存在：

```
 QDir dir("example");
 if (!dir.exists())
     qWarning("Cannot find the example directory");

```

（我们也可以使用静态的便利功能[QFile.exists](qfile.html#exists)（ ） 。 ）

遍历目录和读取文件：

```
 QDir dir = QDir.root();                 // "/"
 if (!dir.cd("tmp")) {                    // "/tmp"
     qWarning("Cannot find the \"/tmp\" directory");
 } else {
     [QFile](qfile.html) file(dir.filePath("ex1.txt")); // "/tmp/ex1.txt"
     if (!file.open([QIODevice](qiodevice.html).ReadWrite))
         qWarning("Cannot create the file %s", file.name());
 }

```

一个程序，列出当前目录下的所有文件（不包括符号链接） ，按大小排序，最小的第一：

```
 #include <QDir>
 #include <iostream>

 int main(int argc, char *argv[])
 {
     [QCoreApplication](qcoreapplication.html) app(argc, argv);
     QDir dir;
     dir.setFilter(QDir.Files | QDir.Hidden | QDir.NoSymLinks);
     dir.setSorting(QDir.Size | QDir.Reversed);

     [QFileInfoList](qfileinfo.html#QFileInfoList-typedef) list = dir.entryInfoList();
     std.cout << "     Bytes Filename" << std.endl;
     for (int i = 0; i < list.size(); ++i) {
         [QFileInfo](qfileinfo.html) fileInfo = list.at(i);
         std.cout << qPrintable([QString](qstring.html)("%1 %2").arg(fileInfo.size(), 10)
                                                 .arg(fileInfo.fileName()));
         std.cout << std.endl;
     }
     return 0;
 }

```

* * *

## Type Documentation

```
QDir.Filter
```

这个枚举描述提供给过滤选项[QDir](qdir.html);如为[entryList](qdir.html#entryList)（）和[entryInfoList](qdir.html#entryInfoList)（ ） 。指定通过使用按位OR运算符下面的列表值相结合的过滤器值：

| Constant | Value | Description |
| --- | --- | --- |
| `QDir.Dirs` | `0x001` | 相匹配的过滤器列表目录。 |
| `QDir.AllDirs` | `0x400` | 列出所有的目录，即不过滤器不适用于目录名。 |
| `QDir.Files` | `0x002` | 列表文件。 |
| `QDir.Drives` | `0x004` | 列表磁盘驱动器（在Unix下被忽略） 。 |
| `QDir.NoSymLinks` | `0x008` | 不要列出符号链接（由不支持符号连接的操作系统忽略不计） 。 |
| `QDir.NoDotAndDotDot` | `0x1000` | 不要列出特殊项目“ 。 ”和“..”。 |
| `QDir.NoDot` | `0x2000` | 不要列出的特殊条目“ 。” |
| `QDir.NoDotDot` | `0x4000` | 不要列出特殊的入口“..” 。 |
| `QDir.AllEntries` | `Dirs &#124; Files &#124; Drives` | 列出目录，文件，驱动器和符号链接（这并不列出破碎的符号链接，除非您指定系统） 。 |
| `QDir.Readable` | `0x010` | 列表文件的应用程序有读权限。可读值需要与显示目录或文件相结合。 |
| `QDir.Writable` | `0x020` | 列出文件该申请写访问。可写值需要与显示目录或文件相结合。 |
| `QDir.Executable` | `0x040` | 列出文件该应用程序具有执行权限。可执行值需要与显示目录或文件相结合。 |
| `QDir.Modified` | `0x080` | 仅列出已修改（忽略在Unix ）文件。 |
| `QDir.Hidden` | `0x100` | 列出隐藏文件（在Unix上，文件开头的“。”） 。 |
| `QDir.System` | `0x200` | 列表的系统文件（在Unix上， FIFO的，插座和设备文件都包括在内;在Windows上，`.lnk`文件都包括在内） |
| `QDir.CaseSensitive` | `0x800` | 该过滤器应区分大小写。 |

使用过滤器枚举值来过滤文件和目录列表的功能将包括符号链接文件和目录，除非你设置NoSymLinks值。

构造一个默认的[QDir](qdir.html)不会过滤出基于其权限的文件，所以[entryList](qdir.html#entryList)（）和[entryInfoList](qdir.html#entryInfoList)（ ）将返回一个可读的所有文件，可写，可执行，或三者的任意组合。这使得默认容易编写，并在同一时间是有用的。

例如，设置`Readable`，`Writable`和`Files`标志允许该应用程序有读权限被列出的所有文件，写访问或两者兼而有之。如果`Dirs`和`Drives`标志也包含在这个组合则所有的驱动器，目录，该应用程序可以读，写或执行所有文件，符号链接到这些文件/目录可以上市。

检索PERMISSONS的目录，使用[entryInfoList](qdir.html#entryInfoList)（ ）函数来获取相关的[QFileInfo](qfileinfo.html)对象，然后使用QFileInfo.permissons （ ）来获取权限和所有权的每个文件。

该过滤器类型是一个typedef为[QFlags](index.htm)的\u003cfilter\u003e 。它存储滤波值的或组合。

```
QDir.SortFlag
```

这个枚举介绍可用于排序选项[QDir](qdir.html)如为[entryList](qdir.html#entryList)（）和[entryInfoList](qdir.html#entryInfoList)（ ） 。指定由从以下列表中的OR-ing合值的排序值：

| Constant | Value | Description |
| --- | --- | --- |
| `QDir.Name` | `0x00` | 按名称排序。 |
| `QDir.Time` | `0x01` | 按时间排序（修改时间） 。 |
| `QDir.Size` | `0x02` | 排序按文件大小。 |
| `QDir.Type` | `0x80` | 排序文件类型（扩展名） 。 |
| `QDir.Unsorted` | `0x03` | 不排序。 |
| `QDir.NoSort` | `-1` | 没有排序默认。 |
| `QDir.DirsFirst` | `0x04` | 把该目录，然后是文件。 |
| `QDir.DirsLast` | `0x20` | 把文件先，然后是目录。 |
| `QDir.Reversed` | `0x08` | 反向排序。 |
| `QDir.IgnoreCase` | `0x10` | 排序不区分大小写。 |
| `QDir.LocaleAware` | `0x40` | 适当地使用当前区域设置项进行排序。 |

您只能指定前四个中的一个。

如果同时指定DirsFirst和反转，目录还是把第一，但以相反的顺序，该文件会以相反的顺序被列出的目录后，再次。

该SortFlags类型是一个typedef为[QFlags](index.htm)\u003cSortFlag\u003e 。它存储SortFlag值的或组合。

* * *

## Method Documentation

```
QDir.__init__ (self, QDir)
```

构造一个[QDir](qdir.html)对象，它是的一个副本[QDir](qdir.html)反对的目录_dir_。

**See also** [operator=](qdir.html#operator-eq)（ ） 。

```
QDir.__init__ (self, QString path = QString())
```

构造一个[QDir](qdir.html)指向给定目录_path_。如果path是空的程序的工作目录（ “。”） ，被使用。

**See also** [currentPath](qdir.html#currentPath)（ ） 。

```
QDir.__init__ (self, QString path, QString nameFilter, SortFlags sort = QDir.Name|QDir.IgnoreCase, Filters filters = QDir.AllEntries)
```

构造一个[QDir](qdir.html)与路径_path_，通过名称使用的过滤条目_nameFilter_并且通过使用属性_filters_。它还使用排序的名字_sort_。

默认_nameFilter_是一个空字符串，不包括什么，默认_filters_ is [AllEntries](qdir.html#Filter-enum)，这也意味着排除无关。默认_sort_ is [Name](qdir.html#SortFlag-enum)|[IgnoreCase](qdir.html#SortFlag-enum)，即按名称排序不区分大小写。

If _path_是一个空字符串，[QDir](qdir.html)使用“ 。 ” （当前目录） 。如果_nameFilter_是一个空字符串，[QDir](qdir.html)使用名称过滤器“ * ” （所有文件） 。

需要注意的是_path_不需要存在。

**See also** [exists](qdir.html#exists)（ ）[setPath](qdir.html#setPath)（ ）[setNameFilter](index.htm#setNameFilter)（ ）[setFilter](qdir.html#setFilter)（）和[setSorting](qdir.html#setSorting)（ ） 。

```
QString QDir.absoluteFilePath (self, QString fileName)
```

返回目录中的文件的绝对路径名。是否_not_检查文件是否确实存在于目录，但看[exists](qdir.html#exists)（ ） 。冗馀的多个隔板或“。 ”中和“..”的目录_fileName_不会被删除（见[cleanPath](qdir.html#cleanPath)（））。

**See also** [relativeFilePath](qdir.html#relativeFilePath)（ ）[filePath](qdir.html#filePath)（）和[canonicalPath](qdir.html#canonicalPath)（ ） 。

```
QString QDir.absolutePath (self)
```

返回绝对路径（以“ / ”或驱动器规格开始的路径） ，其中可能包含符号链接，但不会包含多馀的“ 。 ” ， “..”或多个分隔符。

**See also** [setPath](qdir.html#setPath)（ ）[canonicalPath](qdir.html#canonicalPath)（ ）[exists](qdir.html#exists)（ ）[cleanPath](qdir.html#cleanPath)（ ）[dirName](qdir.html#dirName)（）和[absoluteFilePath](qdir.html#absoluteFilePath)（ ） 。

```
QDir.addResourceSearchPath (QString path)
```

```
QDir.addSearchPath (QString prefix, QString path)
```

添加_path_为搜索路径_prefix_。

此功能被引入Qt的4.3 。

**See also** [setSearchPaths](qdir.html#setSearchPaths)（ ） 。

```
QString QDir.canonicalPath (self)
```

返回规范的路径，即路径没有符号链接或多馀的“ 。 ”或“..”元素。

对不具有符号链接此功能的系统将始终返回相同的字符串[absolutePath](qdir.html#absolutePath)（ ）返回。如果规范的路径不存在（通常是由于悬空符号链接） canonicalPath （ ）返回一个空字符串。

例如：

```
 [QString](qstring.html) bin = "/local/bin";         // where /local/bin is a symlink to /usr/bin
 [QDir](qdir.html) binDir(bin);
 [QString](qstring.html) canonicalBin = binDir.canonicalPath();
 // canonicalBin now equals "/usr/bin"

 [QString](qstring.html) ls = "/local/bin/ls";       // where ls is the executable "ls"
 [QDir](qdir.html) lsDir(ls);
 [QString](qstring.html) canonicalLs = lsDir.canonicalPath();
 // canonicalLS now equals "/usr/bin/ls".

```

**See also** [path](qdir.html#pathx)（ ）[absolutePath](qdir.html#absolutePath)（ ）[exists](qdir.html#exists)（ ）[cleanPath](qdir.html#cleanPath)（ ）[dirName](qdir.html#dirName)（）和[absoluteFilePath](qdir.html#absoluteFilePath)（ ） 。

```
bool QDir.cd (self, QString dirName)
```

更改[QDir](qdir.html)的目录_dirName_。

返回True如果新的目录存在并且可读，否则返回False 。请注意，如果新的目录不存在，不进行逻辑CD （）操作。

调用CD（ “..”）等同于调用[cdUp](qdir.html#cdUp)（ ） 。

**See also** [cdUp](qdir.html#cdUp)（ ）[isReadable](qdir.html#isReadable)（ ）[exists](qdir.html#exists)（）和[path](qdir.html#pathx)（ ） 。

```
bool QDir.cdUp (self)
```

通过移动一个目录从该目录的变化[QDir](qdir.html)目前的目录。

返回True如果新的目录存在并且可读，否则返回False 。请注意，如果新的目录不存在，不进行逻辑CDUP （）操作。

**See also** [cd](qdir.html#cd)（ ）[isReadable](qdir.html#isReadable)（ ）[exists](qdir.html#exists)（）和[path](qdir.html#pathx)（ ） 。

```
QString QDir.cleanPath (QString path)
```

移除所有多个目录分隔符“ / ” ，并解决在路径中找到任何“ ，” s或“..” S，_path_。

符号链接将被保留。这个函数不返回规范路径，而是将输入的简单版本。例如， “ /本地”变成了“本地” ， “本地/ 。 。 / bin”就会变成“垃圾桶”和“ /本地/ usr / 。 。 / bin”就会变成“ / local / bin目录” 。

**See also** [absolutePath](qdir.html#absolutePath)（）和[canonicalPath](qdir.html#canonicalPath)（ ） 。

```
QString QDir.convertSeparators (QString pathName)
```

```
int QDir.count (self)
```

返回目录和文件的目录总数。

相当于[entryList](qdir.html#entryList)（ ） ， COUNT（ ） 。

**See also** [operator[]](qdir.html#operator-5b-5d)（）和[entryList](qdir.html#entryList)（ ） 。

```
QDir QDir.current ()
```

[

返回应用程序的当前目录。

](qdir.html)

[该目录是使用当前目录的绝对路径，确保构建其](qdir.html)[path](qdir.html#pathx)（）将是相同的其[absolutePath](qdir.html#absolutePath)（ ） 。

**See also** [currentPath](qdir.html#currentPath)（ ）[setCurrent](qdir.html#setCurrent)（ ）[home](qdir.html#home)（ ）[root](qdir.html#root)（）和[temp](qdir.html#temp)（ ） 。

```
QString QDir.currentPath ()
```

返回应用程序的当前目录的绝对路径。

**See also** [current](qdir.html#current)（ ）[setCurrent](qdir.html#setCurrent)（ ）[homePath](qdir.html#homePath)（ ）[rootPath](qdir.html#rootPath)（）和[tempPath](qdir.html#tempPath)（ ） 。

```
QString QDir.dirName (self)
```

返回目录的名称，这是_not_相同的路径，例如名称为“邮件”的目录，可能有路径“的/ var / spool / mail中” 。如果目录没有名称（例如，它是根目录）一个空字符串返回。

没有检查，以确保与此名称的目录确实存在，但看[exists](qdir.html#exists)（ ） 。

**See also** [path](qdir.html#pathx)（ ）[filePath](qdir.html#filePath)（ ）[absolutePath](qdir.html#absolutePath)（）和[absoluteFilePath](qdir.html#absoluteFilePath)（ ） 。

```
list-of-QFileInfo QDir.drives ()
```

返回此系统的根目录的列表。

在Windows中，此方法返回列表[QFileInfo](qfileinfo.html)包含对象的“C :/ ” ， “D ​​:/ ”等在其他操作系统上，它返回一个包含只有一个根目录（即“/”）的列表。

**See also** [root](qdir.html#root)（）和[rootPath](qdir.html#rootPath)（ ） 。

```
list-of-QFileInfo QDir.entryInfoList (self, Filters filters = QDir.NoFilter, SortFlags sort = QDir.NoSort)
```

返回列表[QFileInfo](qfileinfo.html)在目录中的所有文件和目录对象，根据名称和属性序滤事先用[setNameFilters](qdir.html#setNameFilters)（）和[setFilter](qdir.html#setFilter)（ ） ，并排序按设定的标志[setSorting](qdir.html#setSorting)（ ） 。

该名过滤器，文件属性过滤和排序规范可以使用被复盖的_nameFilters_，_filters_和_sort_参数。

返回空列表，如果该目录是不可读的，不存在，或者如果没有的规格相匹配。

**See also** [entryList](qdir.html#entryList)（ ）[setNameFilters](qdir.html#setNameFilters)（ ）[setSorting](qdir.html#setSorting)（ ）[setFilter](qdir.html#setFilter)（ ）[isReadable](qdir.html#isReadable)（）和[exists](qdir.html#exists)（ ） 。

```
list-of-QFileInfo QDir.entryInfoList (self, QStringList nameFilters, Filters filters = QDir.NoFilter, SortFlags sort = QDir.NoSort)
```

这是一个重载函数。

返回列表[QFileInfo](qfileinfo.html)在目录中的所有文件和目录对象，根据名称和属性序滤事先用[setNameFilters](qdir.html#setNameFilters)（）和[setFilter](qdir.html#setFilter)（ ） ，并排序按设定的标志[setSorting](qdir.html#setSorting)（ ） 。

该属性过滤和排序的规定可以使用被复盖的_filters_和_sort_参数。

返回空列表，如果该目录是不可读的，不存在，或者如果没有的规格相匹配。

**See also** [entryList](qdir.html#entryList)（ ）[setNameFilters](qdir.html#setNameFilters)（ ）[setSorting](qdir.html#setSorting)（ ）[setFilter](qdir.html#setFilter)（ ）[isReadable](qdir.html#isReadable)（）和[exists](qdir.html#exists)（ ） 。

```
QStringList QDir.entryList (self, Filters filters = QDir.NoFilter, SortFlags sort = QDir.NoSort)
```

返回目录中的所有文件和目录的名称列表，责令按照名称和属性之前设置过滤器[setNameFilters](qdir.html#setNameFilters)（）和[setFilter](qdir.html#setFilter)（ ） ，并排序按设定的标志[setSorting](qdir.html#setSorting)（ ） 。

该名过滤器，文件属性过滤和排序规范可以使用被复盖的_nameFilters_，_filters_和_sort_参数。

返回空列表，如果该目录是不可读的，不存在，或者如果没有的规格相匹配。

**See also** [entryInfoList](qdir.html#entryInfoList)（ ）[setNameFilters](qdir.html#setNameFilters)（ ）[setSorting](qdir.html#setSorting)（）和[setFilter](qdir.html#setFilter)（ ） 。

```
QStringList QDir.entryList (self, QStringList nameFilters, Filters filters = QDir.NoFilter, SortFlags sort = QDir.NoSort)
```

这是一个重载函数。

返回目录中的所有文件和目录的名称列表，责令按照名称和属性之前设置过滤器[setNameFilters](qdir.html#setNameFilters)（）和[setFilter](qdir.html#setFilter)（ ） ，并排序按设定的标志[setSorting](qdir.html#setSorting)（ ） 。

该属性过滤和排序的规定可以使用被复盖的_filters_和_sort_参数。

返回空列表，如果该目录是不可读的，不存在，或者如果没有的规格相匹配。

**Note:**要列出指向不存在的文件的符号链接，[System](qdir.html#Filter-enum)必须被传递到过滤器。

**See also** [entryInfoList](qdir.html#entryInfoList)（ ）[setNameFilters](qdir.html#setNameFilters)（ ）[setSorting](qdir.html#setSorting)（）和[setFilter](qdir.html#setFilter)（ ） 。

```
bool QDir.exists (self)
```

返回True如果调用的文件_name_存在，否则返回False 。

除非_name_包含一个绝对文件路径，文件名被假定为是相对于目录本身，所以这个功能通常用于检查文件的目录中存在。

**See also** [QFileInfo.exists](qfileinfo.html#exists)（）和[QFile.exists](qfile.html#exists)（ ） 。

```
bool QDir.exists (self, QString name)
```

这是一个重载函数。

返回True如果该目录存在，否则返回False 。 （如果找到具有相同名称的文件此函数将返回False ） 。

这个函数接受一个参数的重载是用来测试文件和目录的目录中存在。

**See also** [QFileInfo.exists](qfileinfo.html#exists)（）和[QFile.exists](qfile.html#exists)（ ） 。

```
QString QDir.filePath (self, QString fileName)
```

返回目录中的文件的路径名。是否_not_检查文件是否确实存在于目录，但看[exists](qdir.html#exists)（ ） 。如果[QDir](qdir.html)相对于返回的路径名称也将是相对的。冗馀的多个隔板或“。 ”中和“..”的目录_fileName_不会被删除（见[cleanPath](qdir.html#cleanPath)（））。

**See also** [dirName](qdir.html#dirName)（ ）[absoluteFilePath](qdir.html#absoluteFilePath)（ ）[isRelative](qdir.html#isRelative)（）和[canonicalPath](qdir.html#canonicalPath)（ ） 。

```
Filters QDir.filter (self)
```

[](index.htm)

[返回由设置的值](index.htm)[setFilter](qdir.html#setFilter)（ ）

**See also** [setFilter](qdir.html#setFilter)（ ） 。

```
QString QDir.fromNativeSeparators (QString pathName)
```

Returns _pathName_用'/'作为文件分隔符。在Windows上，例如， fromNativeSeparators （ “`c:\\winnt\\system32`“）返回” C :/在winnt/system32 “ 。

返回的字符串可能是相同的说法在某些操作系统上，例如在Unix上。

这个函数中引入了Qt 4.2中。

**See also** [toNativeSeparators](qdir.html#toNativeSeparators)（）和[separator](qdir.html#separator)（ ） 。

```
QDir QDir.home ()
```

[

返回用户的主目录。

](qdir.html)

[该目录是使用主目录的绝对路径，确保构建其](qdir.html)[path](qdir.html#pathx)（）将是相同的其[absolutePath](qdir.html#absolutePath)（ ） 。

See [homePath](qdir.html#homePath)（ ）了解详情。

**See also** [drives](qdir.html#drives)（ ）[current](qdir.html#current)（ ）[root](qdir.html#root)（）和[temp](qdir.html#temp)（ ） 。

```
QString QDir.homePath ()
```

返回用户的主目录的绝对路径。

在Windows下这个函数会返回当前用户的配置文件的目录。典型地，这是：

```
 C:/Documents and Settings/Username

```

使用[toNativeSeparators](qdir.html#toNativeSeparators)（ ）函数的分隔符转换为那些适用于底层的操作系统。

如果当前用户的配置文件的目录不存在或无法检索，下面的替代品将被选中（在给定的顺序），直到现有的和可用的路径中找到：

1.  由指定的路径`USERPROFILE`环境变量。
2.  通过连接形成的路径`HOMEDRIVE`和`HOMEPATH`环境变量。
3.  由指定的路径`HOME`环境变量。
4.  在返回的路径[rootPath](qdir.html#rootPath)（）函数（它使用`SystemDrive`环境变量）
5.  该`C:/`目录。

在非Windows操作系统`HOME`环境变量用于如果存在的话，否则路径的返回[rootPath](qdir.html#rootPath)（ ） 。

在Symbian这通常会返回“C :/数据”，即同本地PathInfo.PhoneMemoryRootPath （ ） 。

**See also** [home](qdir.html#home)（ ）[currentPath](qdir.html#currentPath)（ ）[rootPath](qdir.html#rootPath)（）和[tempPath](qdir.html#tempPath)（ ） 。

```
bool QDir.isAbsolute (self)
```

返回True如果该目录的路径是绝对的，否则返回False 。看[isAbsolutePath](qdir.html#isAbsolutePath)（ ） 。

**See also** [isRelative](qdir.html#isRelative)（ ）[makeAbsolute](qdir.html#makeAbsolute)（）和[cleanPath](qdir.html#cleanPath)（ ） 。

```
bool QDir.isAbsolutePath (QString path)
```

返回True如果_path_是绝对的，如果它是相对于返回False 。

**See also** [isAbsolute](qdir.html#isAbsolute)（ ）[isRelativePath](qdir.html#isRelativePath)（ ）[makeAbsolute](qdir.html#makeAbsolute)（）和[cleanPath](qdir.html#cleanPath)（ ） 。

```
bool QDir.isReadable (self)
```

返回True如果该目录是可读的_and_我们可以通过名字打开文件，否则返回False 。

**Warning:**从这个函数值为False并不保证该目录中的文件无法访问。

**See also** [QFileInfo.isReadable](qfileinfo.html#isReadable)（ ） 。

```
bool QDir.isRelative (self)
```

返回True如果该目录是相对路径，否则返回False 。 （在Unix下的路径是相对的，如果它不是以一个“/”） 。

**See also** [makeAbsolute](qdir.html#makeAbsolute)（ ）[isAbsolute](qdir.html#isAbsolute)（ ）[isAbsolutePath](qdir.html#isAbsolutePath)（）和[cleanPath](qdir.html#cleanPath)（ ） 。

```
bool QDir.isRelativePath (QString path)
```

返回True如果_path_是相对的，如果它是绝对的返回False 。

**See also** [isRelative](qdir.html#isRelative)（ ）[isAbsolutePath](qdir.html#isAbsolutePath)（）和[makeAbsolute](qdir.html#makeAbsolute)（ ） 。

```
bool QDir.isRoot (self)
```

返回True如果该目录是根目录，否则返回False 。

注：如果该目录是根目录下的符号链接这个函数返回False 。如果你想测试这个使用[canonicalPath](qdir.html#canonicalPath)（ ），例如

```
 [QDir](qdir.html) dir("/tmp/root_link");
 dir = dir.canonicalPath();
 if (dir.isRoot())
     qWarning("It is a root link");

```

**See also** [root](qdir.html#root)（）和[rootPath](qdir.html#rootPath)（ ） 。

```
bool QDir.makeAbsolute (self)
```

目录路径为绝对路径转换。如果它已经绝对没有任何反应。返回True如果转换成功，否则返回False 。

**See also** [isAbsolute](qdir.html#isAbsolute)（ ）[isAbsolutePath](qdir.html#isAbsolutePath)（ ）[isRelative](qdir.html#isRelative)（）和[cleanPath](qdir.html#cleanPath)（ ） 。

```
bool QDir.match (QStringList filters, QString fileName)
```

返回True如果_fileName_匹配通配符（ GLOB ）模式_filter_否则返回False 。该_filter_可能包含由空格或分号分隔的多个模式。匹配不区分大小写。

**See also** [QRegExp wildcard matching](qregexp.html#qregexp-wildcard-matching)，[QRegExp.exactMatch](qregexp.html#exactMatch)（ ）[entryList](qdir.html#entryList)（）和[entryInfoList](qdir.html#entryInfoList)（ ） 。

```
bool QDir.match (QString filter, QString fileName)
```

这是一个重载函数。

返回True如果_fileName_匹配任何通配符的（水珠）模式中的列表_filters_否则返回False 。匹配不区分大小写。

**See also** [QRegExp wildcard matching](qregexp.html#qregexp-wildcard-matching)，[QRegExp.exactMatch](qregexp.html#exactMatch)（ ）[entryList](qdir.html#entryList)（）和[entryInfoList](qdir.html#entryInfoList)（ ） 。

```
bool QDir.mkdir (self, QString dirName)
```

创建一个子目录名为_dirName_。

成功时返回TRUE ，否则返回False 。

如果该目录已经存在时，这个函数被调用时，它会返回False 。

**See also** [rmdir](qdir.html#rmdir)（ ） 。

```
bool QDir.mkpath (self, QString dirPath)
```

创建该目录路径_dirPath_。

该函数将创建需要创建该目录下所有的父目录。

成功返回True ，否则返回False 。

如果路径已经存在时，这个函数被调用时，它会返回True 。

**See also** [rmpath](qdir.html#rmpath)（ ） 。

```
QStringList QDir.nameFilters (self)
```

返回字符串列表进行设置[setNameFilters](qdir.html#setNameFilters)（ ）

**See also** [setNameFilters](qdir.html#setNameFilters)（ ） 。

```
QStringList QDir.nameFiltersFromString (QString nameFilter)
```

```
QString QDir.path (self)
```

```
QDir.refresh (self)
```

刷新的目录信息。

```
QString QDir.relativeFilePath (self, QString fileName)
```

返回的路径_fileName_相对于该目录。

```
 [QDir](qdir.html) dir("/home/bob");
 [QString](qstring.html) s;

 s = dir.relativeFilePath("../img/file.jpg");     // s is "../img/file.jpg"
 s = dir.relativeFilePath("/home/mary/file.txt"); // s is "../mary/file.txt"

```

**See also** [absoluteFilePath](qdir.html#absoluteFilePath)（ ）[filePath](qdir.html#filePath)（）和[canonicalPath](qdir.html#canonicalPath)（ ） 。

```
bool QDir.remove (self, QString fileName)
```

删除该文件，_fileName_。

返回True如果文件被成功删除，否则返回False 。

```
bool QDir.rename (self, QString oldName, QString newName)
```

重命名一个文件或目录_oldName_至_newName_，并成功返回True ，否则返回False 。

在大多数的文件系统，重新命名（）失败仅当_oldName_不存在，如果_newName_和_oldName_不在同一个分区，或者使用新名称的文件已经存在。然而，也有其他原因，重命名（ ）可能会失败。例如，在至少一个文件系统命名（）将失败，如果_newName_指向一个打开的文件。

```
bool QDir.rmdir (self, QString dirName)
```

通过移除指定的目录_dirName_。

该目录必须是空的命令rmdir （）来取得成功。

成功返回True ，否则返回False 。

**See also** [mkdir](qdir.html#mkdir)（ ） 。

```
bool QDir.rmpath (self, QString dirPath)
```

删除的目录路径_dirPath_。

该功能将删除所有父目录中_dirPath_，只要它们是空的。这是mkpath （ dirPath ）的对面。

成功返回True ，否则返回False 。

**See also** [mkpath](qdir.html#mkpath)（ ） 。

```
QDir QDir.root ()
```

[

返回根目录。

](qdir.html)

[该目录是使用根目录的绝对路径，确保构造，其](qdir.html)[path](qdir.html#pathx)（）将是相同的其[absolutePath](qdir.html#absolutePath)（ ） 。

See [rootPath](qdir.html#rootPath)（ ）了解详情。

**See also** [drives](qdir.html#drives)（ ）[current](qdir.html#current)（ ）[home](qdir.html#home)（）和[temp](qdir.html#temp)().

```
QString QDir.rootPath ()
```

返回根目录的绝对路径。

对于Unix操作系统这将返回“ / ” 。对于Windows和Symbian的文件系统中，这通常会返回“C :/ ” 。 I.E.在系统驱动器的根目录。

**See also** [root](qdir.html#root)（ ）[drives](qdir.html#drives)（ ）[currentPath](qdir.html#currentPath)（ ）[homePath](qdir.html#homePath)（）和[tempPath](qdir.html#tempPath)（ ） 。

```
QStringList QDir.searchPaths (QString prefix)
```

返回的搜索路径_prefix_。

此功能被引入Qt的4.3 。

**See also** [setSearchPaths](qdir.html#setSearchPaths)（）和[addSearchPath](qdir.html#addSearchPath)（ ） 。

```
QChar QDir.separator ()
```

返回本机目录分隔符“ / ”的Unix （包括Mac OS X ）根据与“\” Windows下。

你不需要使用这个功能来构建文件路径。如果你总是使用“ / ” ， Qt将会把你的路径，以符合底层操作系统。如果你想使用自己的操作系统的分隔符使用，以显示给用户的路径[toNativeSeparators](qdir.html#toNativeSeparators)（ ） 。

```
bool QDir.setCurrent (QString path)
```

设置应用程序的当前工作目录_path_。返回True如果该目录已成功更改，否则返回False 。

**See also** [current](qdir.html#current)（ ）[currentPath](qdir.html#currentPath)（ ）[home](qdir.html#home)（ ）[root](qdir.html#root)（）和[temp](qdir.html#temp)（ ） 。

```
QDir.setFilter (self, Filters filter)
```

设置所使用的过滤器[entryList](qdir.html#entryList)（）和[entryInfoList](qdir.html#entryInfoList)（）来_filters_。该过滤器是用于指定类型的文件，应当由被返回[entryList](qdir.html#entryList)（）和[entryInfoList](qdir.html#entryInfoList)（ ） 。看[QDir.Filter](qdir.html#Filter-enum)。

**See also** [filter](qdir.html#filter)（）和[setNameFilters](qdir.html#setNameFilters)（ ） 。

```
QDir.setNameFilters (self, QStringList nameFilters)
```

设置所使用的过滤器名称[entryList](qdir.html#entryList)（）和[entryInfoList](qdir.html#entryInfoList)（ ）到由指定的过滤器列表_nameFilters_。

每名过滤器是一个通配符（通配符）过滤器能够理解`*`和`?`通配符。 （见[QRegExp wildcard matching](qregexp.html#qregexp-wildcard-matching)。 ）

例如，下面的代码设置在三名过滤器[QDir](qdir.html)以确保与扩展通常用于C + +源文件只有文件被列出：

```
     [QStringList](qstringlist.html) filters;
     filters << "*.cpp" << "*.cxx" << "*.cc";
     dir.setNameFilters(filters);

```

**See also** [nameFilters](qdir.html#nameFilters)（）和[setFilter](qdir.html#setFilter)（ ） 。

```
QDir.setPath (self, QString path)
```

载到目录的路径_path_。的路径被清除多馀的“...”， “...”和多个隔板。没有检查，看看这个路径中的目录是否真的存在，但你可以检查自己使用[exists](qdir.html#exists)（ ） 。

该路径可以是绝对的或相对的。绝对路径开头的目录分隔符“ / ” （前面可以在Windows下的驱动器规格） 。相对文件名开头的目录名或文件名和路径指定一个相对于当前目录。绝对路径的一个例子是字符串“ / tmp目录/石英” ，相对路径可能看起来像“的src / fatlib ” 。

**See also** [path](qdir.html#pathx)（ ）[absolutePath](qdir.html#absolutePath)（ ）[exists](qdir.html#exists)（ ）[cleanPath](qdir.html#cleanPath)（ ）[dirName](qdir.html#dirName)（ ）[absoluteFilePath](qdir.html#absoluteFilePath)（ ）[isRelative](qdir.html#isRelative)（）和[makeAbsolute](qdir.html#makeAbsolute)（ ） 。

```
QDir.setSearchPaths (QString prefix, QStringList searchPaths)
```

设置或替换文件名Qt的搜索路径的前缀_prefix_至_searchPaths_。

要指定一个前缀的文件名，前面加上前缀后跟一个冒号（例如， “图片： undo.png ” ， “ xmldocs ： books.xml”文件） 。_prefix_只能包含字母或数字（例如，它不能包含一个冒号，也没有斜线） 。

Qt使用这个搜索路径来定位文件与已知的前缀。搜索路径条目，以便进行测试，从第一个项目。

```
 [QDir](qdir.html).setSearchPaths("icons", [QStringList](qstringlist.html)([QDir](qdir.html).homePath() + "/images"));
 [QDir](qdir.html).setSearchPaths("docs", [QStringList](qstringlist.html)(":/embeddedDocuments"));
 ...
 [QPixmap](qpixmap.html) pixmap("icons:undo.png"); // will look for undo.png in QDir.homePath() + "/images"
 [QFile](qfile.html) file("docs:design.odf"); // will look in the :/embeddedDocuments resource path

```

文件名前缀必须至少为2个字符，以避免与Windows驱动器盘符冲突。

搜索路径可能包含为路径[The Qt Resource System](index.htm)。

此功能被引入Qt的4.3 。

**See also** [searchPaths](qdir.html#searchPaths)（ ） 。

```
QDir.setSorting (self, SortFlags sort)
```

设置使用的排序顺序[entryList](qdir.html#entryList)（）和[entryInfoList](qdir.html#entryInfoList)（ ） 。

该_sort_从枚举指定的OR-ing值[QDir.SortFlag](qdir.html#SortFlag-enum)。

**See also** [sorting](qdir.html#sorting)（）和[SortFlag](qdir.html#SortFlag-enum)。

```
SortFlags QDir.sorting (self)
```

[](index.htm)

[返回由设置的值](index.htm)[setSorting](qdir.html#setSorting)（ ）

**See also** [setSorting](qdir.html#setSorting)（）和[SortFlag](qdir.html#SortFlag-enum)。

```
QDir QDir.temp ()
```

[

返回系统的临时目录。

](qdir.html)

[该目录是使用临时目录的绝对路径，确保构建其](qdir.html)[path](qdir.html#pathx)（）将是相同的其[absolutePath](qdir.html#absolutePath)（ ） 。

See [tempPath](qdir.html#tempPath)（ ）了解详情。

**See also** [drives](qdir.html#drives)（ ）[current](qdir.html#current)（ ）[home](qdir.html#home)（）和[root](qdir.html#root)（ ） 。

```
QString QDir.tempPath ()
```

返回系统的临时目录的绝对路径。

在Unix / Linux系统中，这是在路径`TMPDIR`环境变量或`/tmp`如果`TMPDIR`没有定义。在Windows上，这是通常在路径`TEMP` or `TMP`环境变量。目录分隔符是否被添加到末尾与否，取决于操作系统。

**See also** [temp](qdir.html#temp)（ ）[currentPath](qdir.html#currentPath)（ ）[homePath](qdir.html#homePath)（）和[rootPath](qdir.html#rootPath)（ ） 。

```
QString QDir.toNativeSeparators (QString pathName)
```

Returns _pathName_用'/'分隔符转换为分隔符是适用于底层的操作系统。

在Windows上， toNativeSeparators （ “C :/在winnt/system32 ”）返回“C ： \ WINNT \ SYSTEM32 ” 。

返回的字符串可能是相同的说法在某些操作系统上，例如在Unix上。

这个函数中引入了Qt 4.2中。

**See also** [fromNativeSeparators](qdir.html#fromNativeSeparators)（）和[separator](qdir.html#separator)（ ） 。

```
int QDir.__contains__ (self, QString)
```

```
bool QDir.__eq__ (self, QDir dir)
```

```
QString QDir.__getitem__ (self, int)
```

```
QStringList QDir.__getitem__ (self, slice)
```

```
 QDir.__len__ (self)
```

```
bool QDir.__ne__ (self, QDir dir)
```