# QDirIterator Class Reference

## [[QtCore](index.htm) module]

该QDirIterator类提供了一个迭代器目录entrylists 。[More...](#details)

### Types

*   `enum IteratorFlag { NoIteratorFlags, FollowSymlinks, Subdirectories }`
*   `class **[IteratorFlags](index.htm)**`

### Methods

*   `__init__ (self, QDir dir, IteratorFlags flags = QDirIterator.NoIteratorFlags)`
*   `__init__ (self, QString path, IteratorFlags flags = QDirIterator.NoIteratorFlags)`
*   `__init__ (self, QString path, QDir.Filters filters, IteratorFlags flags = QDirIterator.NoIteratorFlags)`
*   `__init__ (self, QString path, QStringList nameFilters, QDir.Filters filters = QDir.NoFilter, IteratorFlags flags = QDirIterator.NoIteratorFlags)`
*   `QFileInfo fileInfo (self)`
*   `QString fileName (self)`
*   `QString filePath (self)`
*   `bool hasNext (self)`
*   `QString next (self)`
*   `QString path (self)`

* * *

## Detailed Description

该QDirIterator类提供了一个迭代器目录entrylists 。

您可以使用QDirIterator来浏览一个目录的一个条目的时间。它类似于[QDir.entryList](qdir.html#entryList)（）和[QDir.entryInfoList](qdir.html#entryInfoList)（ ） ，而是因为它会列出在一次项目，而不是所有的一次，它扩展更好，更适合大型目录。它还支持列表目录内容递归，和下面的符号链接。不像[QDir.entryList](qdir.html#entryList)（ ） ， QDirIterator不支持排序。

该QDirIterator构造函数接受一个[QDir](qdir.html)或一个目录作为参数。施工完毕后，迭代器所在的第一个目录条目之前。以下是如何遍历所有的条目顺序：

```
 QDirIterator it("/etc", QDirIterator.Subdirectories);
 while (it.hasNext()) {
     qDebug() << it.next();

     // /etc/.
     // /etc/..
     // /etc/X11
     // /etc/X11/fs
     // ...
 }

```

该[next](qdiriterator.html#next)（ ）函数返回路径的下一个目录项及垫款的迭代器。您也可以拨打[filePath](qdiriterator.html#filePath)（ ）来得到当前文件的路径，而不推进迭代器。该[fileName](qdiriterator.html#fileName)（ ）函数返回文件的唯一的名称，类似于如何[QDir.entryList](qdir.html#entryList)（ ）的作品。您也可以拨打[fileInfo](qdiriterator.html#fileInfo)（ ）来获取[QFileInfo](qfileinfo.html)当前条目。

不同于Qt的容器迭代器， QDirIterator是单向的（也就是说，你不能遍历目录，以相反的顺序），并不允许随机访问。

QDirIterator适用于所有支持的文件引擎，并使用实施[QAbstractFileEngineIterator](qabstractfileengineiterator.html)。

* * *

## Type Documentation

```
QDirIterator.IteratorFlag
```

这个枚举变量描述的标志，你可以结合配置的行为[QDirIterator](qdiriterator.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QDirIterator.NoIteratorFlags` | `0x0` | 默认值，表示没有任何标志。迭代器将返回条目指定路径。 |
| `QDirIterator.Subdirectories` | `0x2` | 所有子目录里面的列表条目。 |
| `QDirIterator.FollowSymlinks` | `0x1` | 当与子目录结合，这个标志能够循环访问指定路径下的所有子目录，下面所有的符号链接。符号链接循环（例如， “链接” = \u003e “ 。 ”或“链接” = \u003e “..” ）会自动检测和忽略。 |

该IteratorFlags类型是一个typedef为[QFlags](index.htm)\u003cIteratorFlag\u003e 。它存储IteratorFlag值的或组合。

* * *

## Method Documentation

```
QDirIterator.__init__ (self, QDir dir, IteratorFlags flags = QDirIterator.NoIteratorFlags)
```

构造一个[QDirIterator](qdiriterator.html)可以遍历_dir_的entrylist ，使用_dir_的名字过滤器和常规过滤器。你可以通过传递选项_flags_决定如何在目录应该被重复。

默认情况下，_flags_ is [NoIteratorFlags](qdiriterator.html#IteratorFlag-enum)，它提供了相同的行为[QDir.entryList](qdir.html#entryList)（ ） 。

在分选_dir_被忽略。

**Note:**要列出指向不存在的文件的符号链接，[QDir.System](qdir.html#Filter-enum)必须被传递给标记。

**See also** [hasNext](qdiriterator.html#hasNext)（ ）[next](qdiriterator.html#next)（）和[IteratorFlags](qdiriterator.html#IteratorFlag-enum)。

```
QDirIterator.__init__ (self, QString path, IteratorFlags flags = QDirIterator.NoIteratorFlags)
```

构造一个[QDirIterator](qdiriterator.html)可以遍历_path_。你可以通过传递选项_flags_决定如何在目录应该被重复。

默认情况下，_flags_ is [NoIteratorFlags](qdiriterator.html#IteratorFlag-enum)，它提供了相同的行为[QDir.entryList](qdir.html#entryList)（ ） 。

**Note:**要列出指向不存在的文件的符号链接，[QDir.System](qdir.html#Filter-enum)必须被传递给标记。

**See also** [hasNext](qdiriterator.html#hasNext)（ ）[next](qdiriterator.html#next)（）和[IteratorFlags](qdiriterator.html#IteratorFlag-enum)。

```
QDirIterator.__init__ (self, QString path, QDir.Filters filters, IteratorFlags flags = QDirIterator.NoIteratorFlags)
```

构造一个[QDirIterator](qdiriterator.html)可以遍历_path_，没有名字过滤和_filters_入门过滤。你可以通过传递选项_flags_决定如何在目录应该被重复。

默认情况下，_filters_ is [QDir.NoFilter](qdir.html#Filter-enum)和_flags_ is [NoIteratorFlags](qdiriterator.html#IteratorFlag-enum)，它提供了相同的行为[QDir.entryList](qdir.html#entryList)（ ） 。

**Note:**要列出指向不存在的文件的符号链接，[QDir.System](qdir.html#Filter-enum)必须被传递给标记。

**See also** [hasNext](qdiriterator.html#hasNext)（ ）[next](qdiriterator.html#next)（）和[IteratorFlags](qdiriterator.html#IteratorFlag-enum)。

```
QDirIterator.__init__ (self, QString path, QStringList nameFilters, QDir.Filters filters = QDir.NoFilter, IteratorFlags flags = QDirIterator.NoIteratorFlags)
```

构造一个[QDirIterator](qdiriterator.html)可以遍历_path_，使用_nameFilters_和_filters_。你可以通过传递选项_flags_决定如何在目录应该被重复。

默认情况下，_flags_ is [NoIteratorFlags](qdiriterator.html#IteratorFlag-enum)，它提供了相同的行为，[QDir.entryList](qdir.html#entryList)（ ） 。

**Note:**要列出指向不存在的文件的符号链接，[QDir.System](qdir.html#Filter-enum)必须被传递给标记。

**See also** [hasNext](qdiriterator.html#hasNext)（ ）[next](qdiriterator.html#next)（）和[IteratorFlags](qdiriterator.html#IteratorFlag-enum)。

```
QFileInfo QDirIterator.fileInfo (self)
```

[](qfileinfo.html)

[返回](qfileinfo.html)[QFileInfo](qfileinfo.html)当前目录项。

**See also** [filePath](qdiriterator.html#filePath)（）和[fileName](qdiriterator.html#fileName)（ ） 。

```
QString QDirIterator.fileName (self)
```

返回当前目录项的文件名，不带前缀的路径。

遍历一个目录时，此功能非常方便。当使用[QDirIterator.Subdirectories](qdiriterator.html#IteratorFlag-enum)标志，你可以使用[filePath](qdiriterator.html#filePath)（ ）来得到完整的路径。

**See also** [filePath](qdiriterator.html#filePath)（）和[fileInfo](qdiriterator.html#fileInfo)（ ） 。

```
QString QDirIterator.filePath (self)
```

返回当前目录项的完整文件路径。

**See also** [fileInfo](qdiriterator.html#fileInfo)（）和[fileName](qdiriterator.html#fileName)（ ） 。

```
bool QDirIterator.hasNext (self)
```

返回True如果没有在目录中至少有一个以上的项目，否则，则返回False。

**See also** [next](qdiriterator.html#next)（ ）[fileName](qdiriterator.html#fileName)（ ）[filePath](qdiriterator.html#filePath)（）和[fileInfo](qdiriterator.html#fileInfo)（ ） 。

```
QString QDirIterator.next (self)
```

前进迭代到下一个条目，并返回该新条目的文件路径。如果[hasNext](qdiriterator.html#hasNext)（ ）返回False ，这个函数不执行任何操作，并返回一个空[QString](qstring.html)。

您可以致电[fileName](qdiriterator.html#fileName)（）或[filePath](qdiriterator.html#filePath)（ ）来获得当前的输入文件名或路径，或[fileInfo](qdiriterator.html#fileInfo)（ ）来获取[QFileInfo](qfileinfo.html)当前条目。

**See also** [hasNext](qdiriterator.html#hasNext)（ ）[fileName](qdiriterator.html#fileName)（ ）[filePath](qdiriterator.html#filePath)（）和[fileInfo](qdiriterator.html#fileInfo)（ ） 。

```
QString QDirIterator.path (self)
```