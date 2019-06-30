# QFileSystemWatcher Class Reference

## [[QtCore](index.htm) module]

该QFileSystemWatcher类提供用于监视文件和目录进行修改的接口。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `__init__ (self, QStringList paths, QObject parent = None)`
*   `addPath (self, QString file)`
*   `addPaths (self, QStringList files)`
*   `QStringList directories (self)`
*   `QStringList files (self)`
*   `removePath (self, QString file)`
*   `removePaths (self, QStringList files)`

### Qt Signals

*   `void directoryChanged (const QString&)`
*   `void fileChanged (const QString&)`

* * *

## Detailed Description

该QFileSystemWatcher类提供用于监视文件和目录进行修改的接口。

QFileSystemWatcher监控通过观看指定的路径列表的修改文件和目录的文件系统。

Call [addPath](qfilesystemwatcher.html#addPath)（）来观看特定的文件或目录。多条路径可以使用添加的[addPaths](qfilesystemwatcher.html#addPaths)（）函数。现有的路径可以通过使用可移除的[removePath](qfilesystemwatcher.html#removePath)（）和[removePaths](qfilesystemwatcher.html#removePaths)（）函数。

QFileSystemWatcher检查添加到它的每个路径。已经添加到QFileSystemWatcher文件可以使用被访问的[files](qfilesystemwatcher.html#files)（）函数，并使用目录中的[directories](qfilesystemwatcher.html#directories)（）函数。

该[fileChanged](qfilesystemwatcher.html#fileChanged)当一个文件被修改，重命名或从磁盘删除（ ）信号被发射。类似地，[directoryChanged](qfilesystemwatcher.html#directoryChanged)当一个目录或其内容被修改或删除（ ）信号被发射。需要注意的是QFileSystemWatcher停止监控的文件，一旦他们被改名或删除的磁盘和目录，一旦他们被从磁盘中删除。

**Note:**在运行Linux内核没有inotify的支持系统，包含看了路径文件系统不能被卸载。

**Note:**Windows CE不支持目录监视默认情况下，因为这取决于所安装的文件系统驱动程序。

**Note:**监控文件和目录的修改行为会消耗系统资源。这意味着有一个限度的文件和目录的过程中可以同时监控数。在Mac OS X 10.4和所有的BSD变体，例如，打开的文件描述符是需要为每个监视的文件。一些系统在默认情况下打开的文件描述符的数量限制为256 。这意味着[addPath](qfilesystemwatcher.html#addPath)（）和[addPaths](qfilesystemwatcher.html#addPaths)（ ）会在你的进程试图超过256个文件或目录添加到文件系统监视器失败。另外请注意，你的程序可能有其他文件描述符，除了为那些被监视文件的打开，而这些其他打开的描述符也算在总。的Mac OS X 10.5及以上版本使用不同的后端，并没有从这个问题受到影响。

* * *

## Method Documentation

```
QFileSystemWatcher.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的文件系统观察的对象与给定_parent_。

```
QFileSystemWatcher.__init__ (self, QStringList paths, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的文件系统观察的对象与给定_parent_它监视指定的_paths_列表。

```
QFileSystemWatcher.addPath (self, QString file)
```

添加_path_该文件系统观察，如果_path_存在。如果它不存在的路径不被添加，或者如果它已经由文件系统观察监测。

If _path_指定一个目录，该[directoryChanged](qfilesystemwatcher.html#directoryChanged)（在）信号将被发射时_path_被修改或从磁盘中删除，否则[fileChanged](qfilesystemwatcher.html#fileChanged)（）信号被发射时_path_被修改，重命名或删除。

**Note:**有一个依赖于系统的限制，可以同时进行监视的文件和目录的数目。如果已达到极限，_path_不会被添加到文件系统观察，并警告信息将被打印到_stderr_。

**See also** [addPaths](qfilesystemwatcher.html#addPaths)（）和[removePath](qfilesystemwatcher.html#removePath)（ ） 。

```
QFileSystemWatcher.addPaths (self, QStringList files)
```

将每个路径_paths_该文件系统观察。如果它们不存在，不会添加路径，或者如果他们已经由文件系统观察监测。

如果路径指定一个目录，[directoryChanged](qfilesystemwatcher.html#directoryChanged)（在）信号将在路径从磁盘修改或删除被发射，否则[fileChanged](qfilesystemwatcher.html#fileChanged)当路径被修改，重命名或删除（ ）信号被发射。

**Note:**有一个依赖于系统的限制，可以同时进行监视的文件和目录的数目。如果已达到限制，多馀的_paths_不会被添加到文件系统观察，并警告信息将被打印到_stderr_对于无法加入的每个路径。

**See also** [addPath](qfilesystemwatcher.html#addPath)（）和[removePaths](qfilesystemwatcher.html#removePaths)（ ） 。

```
QStringList QFileSystemWatcher.directories (self)
```

返回的路径列表到被监视的目录。

**See also** [files](qfilesystemwatcher.html#files)（ ） 。

```
QStringList QFileSystemWatcher.files (self)
```

返回的路径列表到被监视的文件。

**See also** [directories](qfilesystemwatcher.html#directories)（ ） 。

```
QFileSystemWatcher.removePath (self, QString file)
```

删除指定的_path_从文件系统观察。

**See also** [removePaths](qfilesystemwatcher.html#removePaths)（）和[addPath](qfilesystemwatcher.html#addPath)（ ） 。

```
QFileSystemWatcher.removePaths (self, QStringList files)
```

删除指定的_paths_从文件系统观察。

**See also** [removePath](qfilesystemwatcher.html#removePath)（）和[addPaths](qfilesystemwatcher.html#addPaths)（ ） 。

* * *

## Qt Signal Documentation

```
void directoryChanged (const QString&)
```

这是该信号的默认超载。

当指定在一个目录中这个信号被发射_path_，被修改（例如，当一个文件被添加，修改或删除），或从磁盘上删除。需要注意的是，如果有在很短的时间内一些变化，一些变化可能不会发出这个信号。然而，变化的序列中的最后变化总是会生成这个信号。

**See also** [fileChanged](qfilesystemwatcher.html#fileChanged)（ ） 。

```
void fileChanged (const QString&)
```

这是该信号的默认超载。

当指定的文件这个信号被发射_path_被修改，重命名或从磁盘中删除。

**See also** [directoryChanged](qfilesystemwatcher.html#directoryChanged)（ ） 。