# QFileInfo Class Reference

## [[QtCore](index.htm) module]

该QFileInfo类提供了与系统无关的文件信息。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QString file)`
*   `__init__ (self, QFile file)`
*   `__init__ (self, QDir dir, QString file)`
*   `__init__ (self, QFileInfo fileinfo)`
*   `QDir absoluteDir (self)`
*   `QString absoluteFilePath (self)`
*   `QString absolutePath (self)`
*   `QString baseName (self)`
*   `QString bundleName (self)`
*   `bool caching (self)`
*   `QString canonicalFilePath (self)`
*   `QString canonicalPath (self)`
*   `QString completeBaseName (self)`
*   `QString completeSuffix (self)`
*   `QDateTime created (self)`
*   `QDir dir (self)`
*   `bool exists (self)`
*   `QString fileName (self)`
*   `QString filePath (self)`
*   `QString group (self)`
*   `int groupId (self)`
*   `bool isAbsolute (self)`
*   `bool isBundle (self)`
*   `bool isDir (self)`
*   `bool isExecutable (self)`
*   `bool isFile (self)`
*   `bool isHidden (self)`
*   `bool isReadable (self)`
*   `bool isRelative (self)`
*   `bool isRoot (self)`
*   `bool isSymLink (self)`
*   `bool isWritable (self)`
*   `QDateTime lastModified (self)`
*   `QDateTime lastRead (self)`
*   `bool makeAbsolute (self)`
*   `QString owner (self)`
*   `int ownerId (self)`
*   `QString path (self)`
*   `bool permission (self, QFile.Permissions permissions)`
*   `QFile.Permissions permissions (self)`
*   `QString readLink (self)`
*   `refresh (self)`
*   `setCaching (self, bool on)`
*   `setFile (self, QString file)`
*   `setFile (self, QFile file)`
*   `setFile (self, QDir dir, QString file)`
*   `int size (self)`
*   `QString suffix (self)`
*   `QString symLinkTarget (self)`

### Special Methods

*   `bool __eq__ (self, QFileInfo fileinfo)`
*   `bool __ne__ (self, QFileInfo fileinfo)`

* * *

## Detailed Description

该QFileInfo类提供了与系统无关的文件信息。

QFileInfo提供有关在文件系统中，其访问权限的文件的名称和位置（路径），以及它是否是一个目录或符号链接等，该文件的大小和最后修改/读取时间也可提供信息。 QFileInfo也可用于获得关于一个Qt信息[resource](index.htm#resource-system)。

一个QFileInfo可以指向一个文件，相对或绝对文件路径。绝对文件路径开头的目录分隔符“/” （或在Windows的驱动器规格） 。相对文件名开头的目录名或文件名和路径指定一个相对于当前工作目录。绝对路径的一个例子是字符串“ / tmp目录/石英” 。相对路径可能看起来像“的src / fatlib ” 。您可以使用该功能[isRelative](qfileinfo.html#isRelative)（）来检查一个QFileInfo是否使用相对或绝对文件路径。你可以调用函数[makeAbsolute](qfileinfo.html#makeAbsolute)（ ）为相对QFileInfo的路径转换为绝对路径。

该QFileInfo工程对文件设置在构造函数或更高版本[setFile](qfileinfo.html#setFile)（ ） 。使用[exists](qfileinfo.html#exists)（）来查看文件是否存在和[size](qfileinfo.html#size)（）来获取它的大小。

该文件的类型与获得[isFile](qfileinfo.html#isFile)（ ）[isDir](qfileinfo.html#isDir)（）和[isSymLink](qfileinfo.html#isSymLink)（ ） 。该[symLinkTarget](qfileinfo.html#symLinkTarget)（）函数提供的文件名称的符号链接指向。

在Unix系统（包括Mac OS X ） ，符号链接具有相同的[size](qfileinfo.html#size)（ ）有它指向的文件，因为Unix的处理符号链接透明，同样，使用打开一个符号链接[QFile](qfile.html)有效地打开链接的目标。例如：

```
 #ifdef Q_OS_UNIX

 QFileInfo info1("/home/bob/bin/untabify");
 info1.isSymLink();          // returns true
 info1.absoluteFilePath();   // returns "/home/bob/bin/untabify"
 info1.size();               // returns 56201
 info1.symLinkTarget();      // returns "/opt/pretty++/bin/untabify"

 QFileInfo info2(info1.symLinkTarget());
 info2.isSymLink();          // returns false
 info2.absoluteFilePath();   // returns "/opt/pretty++/bin/untabify"
 info2.size();               // returns 56201

 #endif

```

在Windows中，符号链接（快捷方式）是`.lnk`文件。报导[size](qfileinfo.html#size)（ ）是符号链接（而不是链接的目标） ，并用打开一个符号链接[QFile](qfile.html)打开`.lnk`文件中。例如：

```
 #ifdef Q_OS_WIN

 QFileInfo info1("C:\\Documents and Settings\\Bob\\untabify.lnk");
 info1.isSymLink();          // returns true
 info1.absoluteFilePath();   // returns "C:/Documents and Settings/Bob/untabify.lnk"
 info1.size();               // returns 743
 info1.symLinkTarget();      // returns "C:/Pretty++/untabify"

 QFileInfo info2(info1.symLinkTarget());
 info2.isSymLink();          // returns false
 info2.absoluteFilePath();   // returns "C:/Pretty++/untabify"
 info2.size();               // returns 63942

 #endif

```

该文件的名称的元素可以与被提取[path](qfileinfo.html#pathx)（）和[fileName](qfileinfo.html#fileName)（ ） 。该[fileName](qfileinfo.html#fileName)（）的部分可以与要提取[baseName](qfileinfo.html#baseName)（ ）[suffix](qfileinfo.html#suffix)（）或[completeSuffix](qfileinfo.html#completeSuffix)（ ） 。 QFileInfo对象由Qt类创建的目录不会有拖尾文件分隔符。如果您想使用尾随分隔符在自己的文件信息对象，只是附加一个以提供给构造函数的文件名或[setFile](qfileinfo.html#setFile)（ ） 。

该文件的日期被退回[created](qfileinfo.html#created)（ ）[lastModified](qfileinfo.html#lastModified)（）和[lastRead](qfileinfo.html#lastRead)（ ） 。对文件的访问权限的信息与获得[isReadable](qfileinfo.html#isReadable)（ ）[isWritable](qfileinfo.html#isWritable)（）和[isExecutable](qfileinfo.html#isExecutable)（ ） 。该文件的所有权可从[owner](qfileinfo.html#owner)（ ）[ownerId](qfileinfo.html#ownerId)（ ）[group](qfileinfo.html#group)（）和[groupId](qfileinfo.html#groupId)（ ） 。您可以检查使用单个语句的文件的权限和所有权[permission](qfileinfo.html#permission)（）函数。

### Performance Issues

一些QFileInfo的功能查询文件系统，但由于性能原因，一些功能只对文件名本身运作。例如：要返回一个相对的文件名的绝对路径，[absolutePath](qfileinfo.html#absolutePath)（ ）具有查询的文件系统。该[path](qfileinfo.html#pathx)（）函数，但是，可以在文件名直接工作，所以它比较快。

**Note:**为了提高性能， QFileInfo缓存有关文件的信息。

为了提高性能， QFileInfo缓存有关文件的信息。因为文件可以由其他用户或程序，甚至由同一程序的其他部分被改变，有一个函数，刷新该文件的信息：[refresh](qfileinfo.html#refresh)（ ） 。如果你想关掉一个QFileInfo的缓存，并迫使它每次请求来自它的信息，请拨打setCaching （假）的时间来访问文件系统。

* * *

## Method Documentation

```
QFileInfo.__init__ (self)
```

构造一个空[QFileInfo](qfileinfo.html)对象。

注意，空[QFileInfo](qfileinfo.html)对象不包含任何文件的引用。

**See also** [setFile](qfileinfo.html#setFile)（ ） 。

```
QFileInfo.__init__ (self, QString file)
```

```
QFileInfo.__init__ (self, QFile file)
```

构造一个新的[QFileInfo](qfileinfo.html)，提供有关给定文件的信息。该_file_还可以包括绝对或相对路径。

**See also** [setFile](qfileinfo.html#setFile)（ ）[isRelative](qfileinfo.html#isRelative)（ ）[QDir.setCurrent](qdir.html#setCurrent)（）和[QDir.isRelativePath](qdir.html#isRelativePath)（ ） 。

```
QFileInfo.__init__ (self, QDir dir, QString file)
```

构造一个新的[QFileInfo](qfileinfo.html)，提供有关文件的信息_file_。

如果_file_有一个相对路径，[QFileInfo](qfileinfo.html)也将有一个相对路径。

**See also** [isRelative](qfileinfo.html#isRelative)（ ） 。

```
QFileInfo.__init__ (self, QFileInfo fileinfo)
```

构造一个新的[QFileInfo](qfileinfo.html)这提供了有关提供信息_file_在目录_dir_。

If _dir_有一个相对路径，[QFileInfo](qfileinfo.html)也将有一个相对路径。

If _file_是一个绝对路径，然后将目录指定_dir_将被忽略。

**See also** [isRelative](qfileinfo.html#isRelative)（ ） 。

```
QDir QFileInfo.absoluteDir (self)
```

[](qdir.html)

[返回文件的绝对路径作为](qdir.html)[QDir](qdir.html)对象。

**See also** [dir](qfileinfo.html#dir)（ ）[filePath](qfileinfo.html#filePath)（ ）[fileName](qfileinfo.html#fileName)（）和[isRelative](qfileinfo.html#isRelative)（ ） 。

```
QString QFileInfo.absoluteFilePath (self)
```

返回包含文件名的绝对路径。

绝对路径名包含完整路径和文件名。在Unix上，这将始终以根， '/' ，目录中。在Windows中，这将总是从'D :/ '，其中D是一个驱动器盘符，惟未映射到一个驱动器盘符，在这种情况下，路径将开始“ / /共享名/ ”网络共享。[QFileInfo](qfileinfo.html)将大写的驱动器号。需要注意的是[QDir](qdir.html)不这样做。下面的代码片段显示了这一点。

```
     [QFileInfo](qfileinfo.html) fi("c:/temp/foo"); => fi.absoluteFilePath() => "C:/temp/foo"

```

该函数返回相同[filePath](qfileinfo.html#filePath)（ ） ，除非[isRelative](qfileinfo.html#isRelative)（）是真实的。在对比[canonicalFilePath](qfileinfo.html#canonicalFilePath)（ ） ，符号链接或多馀的“ 。 ”或“..”的元件不一定除去。

如果[QFileInfo](qfileinfo.html)是空的，返回[QDir.currentPath](qdir.html#currentPath)（ ） 。

**See also** [filePath](qfileinfo.html#filePath)（ ）[canonicalFilePath](qfileinfo.html#canonicalFilePath)（）和[isRelative](qfileinfo.html#isRelative)（ ） 。

```
QString QFileInfo.absolutePath (self)
```

返回一个文件的路径，绝对路径。这不包括文件名。

在Unix上的绝对路径将始终以根， '/' ，目录中。在Windows中，这将总是从'D :/ '，其中D是一个驱动器盘符，惟未映射到一个驱动器盘符，在这种情况下，路径将开始“ / /共享名/ ”网络共享。

在对比[canonicalPath](qfileinfo.html#canonicalPath)（ ）符号链接或多馀的“ 。 ”或“..”的元件不一定除去。

**Warning:**如果[QFileInfo](qfileinfo.html)对象是一个空的创建[QString](qstring.html)，这个函数的行为是未定义的。

**See also** [absoluteFilePath](qfileinfo.html#absoluteFilePath)（ ）[path](qfileinfo.html#pathx)（ ）[canonicalPath](qfileinfo.html#canonicalPath)（ ）[fileName](qfileinfo.html#fileName)（）和[isRelative](qfileinfo.html#isRelative)（ ） 。

```
QString QFileInfo.baseName (self)
```

返回文件的基本名不带路径。

基本名称组成，在该文件的所有字符（但不包括）_first_'。'字符。

例如：

```
 [QFileInfo](qfileinfo.html) fi("/tmp/archive.tar.gz");
 [QString](qstring.html) base = fi.baseName();  // base = "archive"

```

文件的基本名称在所有平台上，独立的文件命名约定的同样计算（例如，“ 。 bashrc中”在Unix上有一个空基地名称，后缀是“ bashrc中” ） 。

**See also** [fileName](qfileinfo.html#fileName)（ ）[suffix](qfileinfo.html#suffix)（ ）[completeSuffix](qfileinfo.html#completeSuffix)（）和[completeBaseName](qfileinfo.html#completeBaseName)（ ） 。

```
QString QFileInfo.bundleName (self)
```

返回包的名称。

在Mac OS X这个返回正确的本地化名称的包，如果路径[isBundle](qfileinfo.html#isBundle)（ ） 。在所有其他平台的空[QString](qstring.html)返回。

例如：

```
 [QFileInfo](qfileinfo.html) fi("/Applications/Safari.app");
 [QString](qstring.html) bundle = fi.bundleName();                // name = "Safari"

```

此功能被引入Qt的4.3 。

**See also** [isBundle](qfileinfo.html#isBundle)（ ）[filePath](qfileinfo.html#filePath)（ ）[baseName](qfileinfo.html#baseName)（）和[extension](index.htm#extension)（ ） 。

```
bool QFileInfo.caching (self)
```

返回True如果缓存被启用，否则返回False 。

**See also** [setCaching](qfileinfo.html#setCaching)（）和[refresh](qfileinfo.html#refresh)（ ） 。

```
QString QFileInfo.canonicalFilePath (self)
```

返回规范路径包括文件名，不带符号链接或冗馀，即绝对路径“ 。 ”或“..”元素。

如果文件不存在， canonicalFilePath （ ）返回一个空字符串。

**See also** [filePath](qfileinfo.html#filePath)（ ）[absoluteFilePath](qfileinfo.html#absoluteFilePath)（）和[dir](qfileinfo.html#dir)（ ） 。

```
QString QFileInfo.canonicalPath (self)
```

返回文件的路径规范的路径（不包括文件名） ，即一个绝对路径，而符号链接或多馀的“ 。 ”或“..”元素。

如果文件不存在， canonicalPath （ ）返回一个空字符串。

**See also** [path](qfileinfo.html#pathx)（）和[absolutePath](qfileinfo.html#absolutePath)（ ） 。

```
QString QFileInfo.completeBaseName (self)
```

返回文件的完整的基本名称不包含路径。

完整的基本名称包含在该文件的所有字符（但不包括）_last_'。'字符。

例如：

```
 [QFileInfo](qfileinfo.html) fi("/tmp/archive.tar.gz");
 [QString](qstring.html) base = fi.completeBaseName();  // base = "archive.tar"

```

**See also** [fileName](qfileinfo.html#fileName)（ ）[suffix](qfileinfo.html#suffix)（ ）[completeSuffix](qfileinfo.html#completeSuffix)（）和[baseName](qfileinfo.html#baseName)（ ） 。

```
QString QFileInfo.completeSuffix (self)
```

返回文件的完整的后缀。

完整的后缀由文件中的所有字符后（但不包括）第一个'。' 。

例如：

```
 [QFileInfo](qfileinfo.html) fi("/tmp/archive.tar.gz");
 [QString](qstring.html) ext = fi.completeSuffix();  // ext = "tar.gz"

```

**See also** [fileName](qfileinfo.html#fileName)（ ）[suffix](qfileinfo.html#suffix)（ ）[baseName](qfileinfo.html#baseName)（）和[completeBaseName](qfileinfo.html#completeBaseName)（ ） 。

```
QDateTime QFileInfo.created (self)
```

[

返回创建文件时的日期和时间。

在大多数Unix系统中，这个函数返回的最后一个状态改变的时间。在创建文件时，会出现一个状态的变化，但每当用户写入或设置inode信息（例如，更改文件的权限），它也发生。

](qdatetime.html)

[如果没有创建时间，也不是“最后的状态改变”的时间不可用，则返回相同](qdatetime.html)[lastModified](qfileinfo.html#lastModified)（ ） 。

**See also** [lastModified](qfileinfo.html#lastModified)（）和[lastRead](qfileinfo.html#lastRead)（ ） 。

```
QDir QFileInfo.dir (self)
```

[](qdir.html)

[返回该对象的父目录的路径作为](qdir.html)[QDir](qdir.html)对象。

**Note:**该[QDir](qdir.html)总是返回对应于该对象的父目录，即使[QFileInfo](qfileinfo.html)表示一个目录。

对于每个下面，目录中（ ）返回一个[QDir](qdir.html)为`"~/examples/191697"`。

```
     [QFileInfo](qfileinfo.html) fileInfo1("~/examples/191697/.");
     [QFileInfo](qfileinfo.html) fileInfo2("~/examples/191697/..");
     [QFileInfo](qfileinfo.html) fileInfo3("~/examples/191697/main.cpp");

```

对于每个下面，目录中（ ）返回一个[QDir](qdir.html)为`"."`。

```
     [QFileInfo](qfileinfo.html) fileInfo4(".");
     [QFileInfo](qfileinfo.html) fileInfo5("..");
     [QFileInfo](qfileinfo.html) fileInfo6("main.cpp");

```

**See also** [absolutePath](qfileinfo.html#absolutePath)（ ）[filePath](qfileinfo.html#filePath)（ ）[fileName](qfileinfo.html#fileName)（ ）[isRelative](qfileinfo.html#isRelative)（）和[absoluteDir](qfileinfo.html#absoluteDir)（ ） 。

```
bool QFileInfo.exists (self)
```

返回True如果该文件存在，否则返回False 。

**Note:**如果该文件是一个符号链接指向一个不存在的文件，则返回False。

```
QString QFileInfo.fileName (self)
```

返回该文件的名称，但不包括路径。

例如：

```
 [QFileInfo](qfileinfo.html) fi("/tmp/archive.tar.gz");
 [QString](qstring.html) name = fi.fileName();                // name = "archive.tar.gz"

```

需要注意的是，如果此[QFileInfo](qfileinfo.html)对象是由于在斜线结束路径，文件名被认为是空的。

**See also** [isRelative](qfileinfo.html#isRelative)（ ）[filePath](qfileinfo.html#filePath)（ ）[baseName](qfileinfo.html#baseName)（）和[extension](index.htm#extension)（ ） 。

```
QString QFileInfo.filePath (self)
```

返回文件名，包括路径（其可以是绝对的或相对的） 。

**See also** [absoluteFilePath](qfileinfo.html#absoluteFilePath)（ ）[canonicalFilePath](qfileinfo.html#canonicalFilePath)（）和[isRelative](qfileinfo.html#isRelative)（ ） 。

```
QString QFileInfo.group (self)
```

返回该文件的组。在Windows上，在那里的文件并没有团体系统，或者如果发生错误，则返回一个空字符串。

这个功能可以一次Unix下消耗（以毫秒为单位的顺序） 。

**See also** [groupId](qfileinfo.html#groupId)（ ）[owner](qfileinfo.html#owner)（）和[ownerId](qfileinfo.html#ownerId)（ ） 。

```
int QFileInfo.groupId (self)
```

返回文件所属的组的id 。

在Windows和地方文件没有组此功能的系统总是返回（ UINT ）-2 。

**See also** [group](qfileinfo.html#group)（ ）[owner](qfileinfo.html#owner)（）和[ownerId](qfileinfo.html#ownerId)（ ） 。

```
bool QFileInfo.isAbsolute (self)
```

返回True如果文件路径名是绝对的，否则，如果是相对路径返回False 。

**See also** [isRelative](qfileinfo.html#isRelative)（ ） 。

```
bool QFileInfo.isBundle (self)
```

返回True如果该对象指向一个包，或在Mac OS X上捆绑一个符号链接，否则返回False 。

此功能被引入Qt的4.3 。

**See also** [isDir](qfileinfo.html#isDir)（ ）[isSymLink](qfileinfo.html#isSymLink)（）和[isFile](qfileinfo.html#isFile)（ ） 。

```
bool QFileInfo.isDir (self)
```

返回True如果该对象指向一个目录或一个目录的符号链接，否则返回False 。

**See also** [isFile](qfileinfo.html#isFile)（ ）[isSymLink](qfileinfo.html#isSymLink)（）和[isBundle](qfileinfo.html#isBundle)（ ） 。

```
bool QFileInfo.isExecutable (self)
```

返回True如果文件是可执行文件，否则返回False 。

**See also** [isReadable](qfileinfo.html#isReadable)（ ）[isWritable](qfileinfo.html#isWritable)（）和[permission](qfileinfo.html#permission)（ ） 。

```
bool QFileInfo.isFile (self)
```

返回True如果该对象指向一个文件或一个文件的符号链接。返回False如果对象指向的东西是不是一个文件，如目录。

**See also** [isDir](qfileinfo.html#isDir)（ ）[isSymLink](qfileinfo.html#isSymLink)（）和[isBundle](qfileinfo.html#isBundle)（ ） 。

```
bool QFileInfo.isHidden (self)
```

返回True如果这是一个'隐藏'的文件，否则返回False 。

**Note:**对于特殊条目此函数返回True “ 。 ”在Unix和“..” ，即使QDir.entryList威胁他们，如图所示。

```
bool QFileInfo.isReadable (self)
```

返回True ，如果用户可以读取该文件，否则返回False 。

**See also** [isWritable](qfileinfo.html#isWritable)（ ）[isExecutable](qfileinfo.html#isExecutable)（）和[permission](qfileinfo.html#permission)（ ） 。

```
bool QFileInfo.isRelative (self)
```

返回True如果文件路径名是相对的，否则返回False，如果是绝对路径（ Unix下如一个路径是绝对的，如果它始于一个“/”） 。

**See also** [isAbsolute](qfileinfo.html#isAbsolute)（ ） 。

```
bool QFileInfo.isRoot (self)
```

返回True如果对象指向一个目录或一个符号链接到一个目录，该目录是根目录，否则返回False 。

```
bool QFileInfo.isSymLink (self)
```

返回True如果该对象指向一个符号链接（或在Windows上的快捷方式），否则返回False 。

在Unix系统（包括Mac OS X ） ，打开一个符号链接有效打开[link's target](qfileinfo.html#symLinkTarget)。在Windows上，它打开`.lnk`文件本身。

例如：

```
 [QFileInfo](qfileinfo.html) info(fileName);
 if (info.isSymLink())
     fileName = info.symLinkTarget();

```

**Note:**如果符号链接指向一个不存在的文件，[exists](qfileinfo.html#exists)（ ）返回False 。

**See also** [isFile](qfileinfo.html#isFile)（ ）[isDir](qfileinfo.html#isDir)（）和[symLinkTarget](qfileinfo.html#symLinkTarget)（ ） 。

```
bool QFileInfo.isWritable (self)
```

返回True如果用户可以写入文件，否则返回False 。

**See also** [isReadable](qfileinfo.html#isReadable)（ ）[isExecutable](qfileinfo.html#isExecutable)（）和[permission](qfileinfo.html#permission)（ ） 。

```
QDateTime QFileInfo.lastModified (self)
```

[

返回时，该文件最后修改的日期和时间。

](qdatetime.html)

[**See also**](qdatetime.html) [created](qfileinfo.html#created)（）和[lastRead](qfileinfo.html#lastRead)（ ） 。

```
QDateTime QFileInfo.lastRead (self)
```

[

返回的日期和时间当文件上次读取（访问） 。

](qdatetime.html)

[在平台上，其中该信息不可用，则返回相同](qdatetime.html)[lastModified](qfileinfo.html#lastModified)（ ） 。

**See also** [created](qfileinfo.html#created)（）和[lastModified](qfileinfo.html#lastModified)（ ） 。

```
bool QFileInfo.makeAbsolute (self)
```

该文件的路径，以绝对路径转换，如果它不是已以这样的形式。返回True表示该路径被转换，否则返回False，表示该路径已经是绝对的。

**See also** [filePath](qfileinfo.html#filePath)（）和[isRelative](qfileinfo.html#isRelative)（ ） 。

```
QString QFileInfo.owner (self)
```

返回文件的所有者。对其中的文件没有所有者的系统，或者如果发生错误，则返回一个空字符串。

这个功能可以一次Unix下消耗（以毫秒为单位的顺序） 。

**See also** [ownerId](qfileinfo.html#ownerId)（ ）[group](qfileinfo.html#group)（）和[groupId](qfileinfo.html#groupId)（ ） 。

```
int QFileInfo.ownerId (self)
```

返回文件的所有者的ID。

在Windows和文件的地方没有业主该函数返回系统（ （ UINT ） -2） 。

**See also** [owner](qfileinfo.html#owner)（ ）[group](qfileinfo.html#group)（）和[groupId](qfileinfo.html#groupId)（ ） 。

```
QString QFileInfo.path (self)
```

```
bool QFileInfo.permission (self, QFile.Permissions permissions)
```

测试文件的权限。该_permissions_参数可以是类型的几个标志[QFile.Permissions](qfile.html#Permission-enum)或 - 编在一起来检查权限的组合。

对其中的文件没有权限这个功能系统总是返回True 。

例如：

```
 [QFileInfo](qfileinfo.html) fi("/tmp/archive.tar.gz");
 if (fi.permission([QFile](qfile.html).WriteUser | [QFile](qfile.html).ReadGroup))
     qWarning("I can change the file; my group can read the file");
 if (fi.permission([QFile](qfile.html).WriteGroup | [QFile](qfile.html).WriteOther))
     qWarning("The group or others can change the file");

```

**See also** [isReadable](qfileinfo.html#isReadable)（ ）[isWritable](qfileinfo.html#isWritable)（）和[isExecutable](qfileinfo.html#isExecutable)（ ） 。

```
QFile.Permissions QFileInfo.permissions (self)
```

[](index.htm)

[返回的完整或的结果组合在一起](index.htm)[QFile.Permissions](qfile.html#Permission-enum)对于该文件。

```
QString QFileInfo.readLink (self)
```

```
QFileInfo.refresh (self)
```

刷新有关该文件的信息，即信息从文件系统中读取下一个时间缓存的属性是牵强。

**Note:**在Windows CE上，有可能会有延迟的文件系统驱动程序来检测文件的变化。

```
QFileInfo.setCaching (self, bool on)
```

If _enable_为True，则启用文件信息缓存。如果_enable_是假的缓存被禁用。

当启用缓存，[QFileInfo](qfileinfo.html)从第一次需要它的文件系统读取文件信息，但一般不晚。

缓存是默认启用的。

**See also** [refresh](qfileinfo.html#refresh)（）和[caching](qfileinfo.html#caching)（ ） 。

```
QFileInfo.setFile (self, QString file)
```

设置文件的[QFileInfo](qfileinfo.html)提供有关信息_file_。

该_file_还可以包括绝对或相对文件路径。绝对路径开头的目录分隔符（如“/”在Unix下）或驱动器规范（ Windows下） 。相对文件名开头的目录名或文件名和路径指定一个相对于当前目录。

例如：

```
 [QString](qstring.html) absolute = "/local/bin";
 [QString](qstring.html) relative = "local/bin";
 [QFileInfo](qfileinfo.html) absFile(absolute);
 [QFileInfo](qfileinfo.html) relFile(relative);

 [QDir](qdir.html).setCurrent([QDir](qdir.html).rootPath());
 // absFile and relFile now point to the same file

 [QDir](qdir.html).setCurrent("/tmp");
 // absFile now points to "/local/bin",
 // while relFile points to "/tmp/local/bin"

```

**See also** [isFile](qfileinfo.html#isFile)（ ）[isRelative](qfileinfo.html#isRelative)（ ）[QDir.setCurrent](qdir.html#setCurrent)（）和[QDir.isRelativePath](qdir.html#isRelativePath)（ ） 。

```
QFileInfo.setFile (self, QFile file)
```

这是一个重载函数。

设置文件的[QFileInfo](qfileinfo.html)提供有关信息_file_。

If _file_包含相对路径，[QFileInfo](qfileinfo.html)也将有一个相对路径。

**See also** [isRelative](qfileinfo.html#isRelative)（ ） 。

```
QFileInfo.setFile (self, QDir dir, QString file)
```

这是一个重载函数。

设置文件的[QFileInfo](qfileinfo.html)提供有关信息_file_目录_dir_。

If _file_包含相对路径，[QFileInfo](qfileinfo.html)也将有一个相对路径。

**See also** [isRelative](qfileinfo.html#isRelative)（ ） 。

```
int QFileInfo.size (self)
```

返回以字节为单位的文件大小。如果文件不存在或无法获取的，则返回0 。

**See also** [exists](qfileinfo.html#exists)（ ） 。

```
QString QFileInfo.suffix (self)
```

返回文件的后缀。

后缀组成的文件中的所有字符后（但不包括）最后一个'。' 。

例如：

```
 [QFileInfo](qfileinfo.html) fi("/tmp/archive.tar.gz");
 [QString](qstring.html) ext = fi.suffix();  // ext = "gz"

```

文件的后缀在所有平台上，独立的文件命名约定的同样计算（例如，“ 。 bashrc中”在Unix上有一个空基地名称，后缀是“ bashrc中” ） 。

**See also** [fileName](qfileinfo.html#fileName)（ ）[completeSuffix](qfileinfo.html#completeSuffix)（ ）[baseName](qfileinfo.html#baseName)（）和[completeBaseName](qfileinfo.html#completeBaseName)（ ） 。

```
QString QFileInfo.symLinkTarget (self)
```

返回绝对路径的文件或目录的符号链接（或快捷方式在Windows上）指向，或者一个空字符串，如果该对象不是一个符号链接。

这个名字可能并不代表现有的文件，它只是一个字符串。[QFileInfo.exists](qfileinfo.html#exists)（ ）返回True ，如果符号链接指向现有的文件。

这个函数中引入了Qt 4.2中。

**See also** [exists](qfileinfo.html#exists)（ ）[isSymLink](qfileinfo.html#isSymLink)（ ）[isDir](qfileinfo.html#isDir)（）和[isFile](qfileinfo.html#isFile)（ ） 。

```
bool QFileInfo.__eq__ (self, QFileInfo fileinfo)
```

```
bool QFileInfo.__ne__ (self, QFileInfo fileinfo)
```