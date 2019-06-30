# QResource Class Reference

## [[QtCore](index.htm) module]

该QResource类提供​​一个接口，用于直接从资源阅读。[More...](#details)

### Methods

*   `__init__ (self, QString fileName = QString(), QLocale locale = QLocale())`
*   `QString absoluteFilePath (self)`
*   `QStringList children (self)`
*   `str data (self)`
*   `QString fileName (self)`
*   `bool isCompressed (self)`
*   `bool isDir (self)`
*   `bool isFile (self)`
*   `bool isValid (self)`
*   `QLocale locale (self)`
*   `setFileName (self, QString file)`
*   `setLocale (self, QLocale locale)`
*   `int size (self)`

### Static Methods

*   `addSearchPath (QString path)`
*   `bool registerResource (QString rccFileName, QString mapRoot = QString())`
*   `bool registerResourceData (str rccData, QString mapRoot = QString())`
*   `QStringList searchPaths ()`
*   `bool unregisterResource (QString rccFileName, QString mapRoot = QString())`
*   `bool unregisterResourceData (str rccData, QString mapRoot = QString())`

* * *

## Detailed Description

该QResource类提供​​一个接口，用于直接从资源阅读。

QResource是一个对象，它表示与一个单一的资源实体的一组数据（和可能的儿童）。 QResource提供直接访问其原始格式的字节。通过这种方式直接访问允许读取数据，而无需缓冲复制或间接。间接常常是有用的资源实体进行交互，就好像它是一个文件时，这可以实现与[QFile](qfile.html)。数据和子后面的QResource通常编译成一个应用程序/库，但是，也可以装入一个资源在运行时。当在运行时的资源文件将通过引用到资源树被加载为一个大的数据集，然后在片给出了加载。

一个QResource既可以装载一个绝对路径，要么被视为植根与文件系统`/`字符，或紮根与资源符号`:`字符。相对资源也可以打开，将在由返回路径的列表中找到[QDir.searchPaths](qdir.html#searchPaths)（ ） 。

这是代表一个文件中的QResource将有数据支持它，这些数据都不可能被压缩，在这种情况下，[qUncompress](index.htm#qUncompress)（）必须被用于访问实际数据;这种情况发生隐式通过一个访问时[QFile](qfile.html)。这是代表一个目录中的QResource将只有孩子和没有数据。

### Dynamic Resource Loading

资源可以被排除应用程序的二进制文件，当它需要在运行时使用的加载[registerResource](qresource.html#registerResource)（）函数。传递到资源文件[registerResource](qresource.html#registerResource)（ ）必须是一个二进制资源由RCC所创建。有关二进制资源的更多信息可参见[The Qt Resource System](index.htm)文档。

这个加载一大组的基础上设置了可以改变应用图标时，或者可以由用户进行编辑和重新购买是非常有用。该资源被立即加载到内存中，无论是作为一个单独的文件读取操作的结果，或者作为内存映射文件。

这种方法可以被证明是一个显着的性能提升，因为只有一个单一的文件将被加载，数据块将通过所要求的路径给出了[setFileName](qresource.html#setFileName)（ ） 。

该[unregisterResource](qresource.html#unregisterResource)（ ）函数删除一个引用到一个特定的文件。如果有QResources目前引用涉及到未登记的文件的资源，它们将继续是有效的，但在资源文件本身将来自资源根部除去，因而没有进一步QResource可以创建指向到该资源的数据。资源本身会从什么时候指向它的最后QResource被破坏内存中映射。

* * *

## Method Documentation

```
QResource.__init__ (self, QString fileName = QString(), QLocale locale = QLocale())
```

构造一个[QResource](qresource.html)指着_file_。_locale_用于加载一个资源的数据的具体定位。

**See also** [QFileInfo](qfileinfo.html)，[QDir.searchPaths](qdir.html#searchPaths)（ ）[setFileName](qresource.html#setFileName)（）和[setLocale](qresource.html#setLocale)（ ） 。

```
QString QResource.absoluteFilePath (self)
```

返回的真实路径，这[QResource](qresource.html)表示，如果资源是通过发现[QDir.searchPaths](qdir.html#searchPaths)（）将被显示在路径中。

**See also** [fileName](qresource.html#fileName)（ ） 。

```
QResource.addSearchPath (QString path)
```

```
QStringList QResource.children (self)
```

返回所有资源的列表在此目录中，如果资源表示一个文件列表将是空的。

**See also** [isDir](qresource.html#isDir)（ ） 。

```
str QResource.data (self)
```

返回直接访问只读数据段的该资源代表。如果资源被压缩的数据返回被压缩，并[qUncompress](index.htm#qUncompress)（）必须被用来访问数据。如果该资源是一个目录，则返回0 。

**See also** [size](qresource.html#size)（ ）[isCompressed](qresource.html#isCompressed)（）和[isFile](qresource.html#isFile)（ ） 。

```
QString QResource.fileName (self)
```

返回完整的文件路径，这[QResource](qresource.html)代表，因为它获得通过。

**See also** [setFileName](qresource.html#setFileName)（）和[absoluteFilePath](qresource.html#absoluteFilePath)（ ） 。

```
bool QResource.isCompressed (self)
```

返回True如果资源表示一个文件，并支持它是一种压缩格式，否则返回False的数据。

**See also** [data](qresource.html#data)（）和[isFile](qresource.html#isFile)（ ） 。

```
bool QResource.isDir (self)
```

如果资源表示一个目录，因此可能有，则返回True[children](qresource.html#children)（ ）在里面， False，如果它代表一个文件。

**See also** [isFile](qresource.html#isFile)（ ） 。

```
bool QResource.isFile (self)
```

返回True如果资源表示一个文件，因此有数据支持的，虚假的，如果它表示一个目录。

**See also** [isDir](qresource.html#isDir)（ ） 。

```
bool QResource.isValid (self)
```

返回True如果资源在资源层次，假确实存在，否则。

```
QLocale QResource.locale (self)
```

[](qlocale.html)

[返回用于查找数据的区域设置](qlocale.html)[QResource](qresource.html)。

**See also** [setLocale](qresource.html#setLocale)（ ） 。

```
bool QResource.registerResource (QString rccFileName, QString mapRoot = QString())
```

寄存器的资源与给定的_rccFileName_在由指定的资源树中的位置_mapRoot_，并返回True，如果该文件被成功打开，否则返回False 。

**See also** [unregisterResource](qresource.html#unregisterResource)（ ） 。

```
bool QResource.registerResourceData (str rccData, QString mapRoot = QString())
```

```
QStringList QResource.searchPaths ()
```

```
QResource.setFileName (self, QString file)
```

设置[QResource](qresource.html)指向_file_。_file_可以是绝对的，在这种情况下，它直接打开，如果相对则该文件将尝试在被发现[QDir.searchPaths](qdir.html#searchPaths)（ ） 。

**See also** [fileName](qresource.html#fileName)（）和[absoluteFilePath](qresource.html#absoluteFilePath)（ ） 。

```
QResource.setLocale (self, QLocale locale)
```

设置[QResource](qresource.html)仅加载资源的本地化，为_locale_。如果没有找到针对特定语言环境的资源，然后在C语言环境使用。

**See also** [locale](qresource.html#locale)（）和[setFileName](qresource.html#setFileName)（ ） 。

```
int QResource.size (self)
```

返回备份的资源数据的大小。

**See also** [data](qresource.html#data)（）和[isFile](qresource.html#isFile)（ ） 。

```
bool QResource.unregisterResource (QString rccFileName, QString mapRoot = QString())
```

注销资源与给定_rccFileName_在由指定的资源树中的位置_mapRoot_，并返回True，如果该资源被成功卸载，并没有引用的资源存在，否则返回False 。

**See also** [registerResource](qresource.html#registerResource)（ ） 。

```
bool QResource.unregisterResourceData (str rccData, QString mapRoot = QString())
```