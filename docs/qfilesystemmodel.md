# QFileSystemModel Class Reference

## [[QtGui](index.htm) module]

该QFileSystemModel类提供了在本地文件系统的数据模型。[More...](#details)

继承[QAbstractItemModel](qabstractitemmodel.html)。

### Types

*   `enum Roles { FileIconRole, FilePathRole, FileNameRole, FilePermissions }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `bool canFetchMore (self, QModelIndex parent)`
*   `int columnCount (self, QModelIndex parent = QModelIndex())`
*   `QVariant data (self, QModelIndex index, int role = Qt.DisplayRole)`
*   `bool dropMimeData (self, QMimeData data, Qt.DropAction action, int row, int column, QModelIndex parent)`
*   `bool event (self, QEvent event)`
*   `fetchMore (self, QModelIndex parent)`
*   `QIcon fileIcon (self, QModelIndex aindex)`
*   `QFileInfo fileInfo (self, QModelIndex aindex)`
*   `QString fileName (self, QModelIndex aindex)`
*   `QString filePath (self, QModelIndex index)`
*   `QDir.Filters filter (self)`
*   `Qt.ItemFlags flags (self, QModelIndex index)`
*   `bool hasChildren (self, QModelIndex parent = QModelIndex())`
*   `QVariant headerData (self, int section, Qt.Orientation orientation, int role = Qt.DisplayRole)`
*   `QFileIconProvider iconProvider (self)`
*   `QModelIndex index (self, int row, int column, QModelIndex parent = QModelIndex())`
*   `QModelIndex index (self, QString path, int column = 0)`
*   `bool isDir (self, QModelIndex index)`
*   `bool isReadOnly (self)`
*   `QDateTime lastModified (self, QModelIndex index)`
*   `QMimeData mimeData (self, list-of-QModelIndex indexes)`
*   `QStringList mimeTypes (self)`
*   `QModelIndex mkdir (self, QModelIndex parent, QString name)`
*   `QVariant myComputer (self, int role = Qt.DisplayRole)`
*   `bool nameFilterDisables (self)`
*   `QStringList nameFilters (self)`
*   `QModelIndex parent (self, QModelIndex child)`
*   `QFile.Permissions permissions (self, QModelIndex index)`
*   `bool remove (self, QModelIndex aindex)`
*   `bool resolveSymlinks (self)`
*   `bool rmdir (self, QModelIndex aindex)`
*   `QDir rootDirectory (self)`
*   `QString rootPath (self)`
*   `int rowCount (self, QModelIndex parent = QModelIndex())`
*   `bool setData (self, QModelIndex idx, QVariant value, int role = Qt.EditRole)`
*   `setFilter (self, QDir.Filters filters)`
*   `setIconProvider (self, QFileIconProvider provider)`
*   `setNameFilterDisables (self, bool enable)`
*   `setNameFilters (self, QStringList filters)`
*   `setReadOnly (self, bool enable)`
*   `setResolveSymlinks (self, bool enable)`
*   `QModelIndex setRootPath (self, QString path)`
*   `int size (self, QModelIndex index)`
*   `sort (self, int column, Qt.SortOrder order = Qt.AscendingOrder)`
*   `Qt.DropActions supportedDropActions (self)`
*   `timerEvent (self, QTimerEvent event)`
*   `QString type (self, QModelIndex index)`

### Qt Signals

*   `void directoryLoaded (const QString&)`
*   `void fileRenamed (const QString&,const QString&,const QString&)`
*   `void rootPathChanged (const QString&)`

* * *

## Detailed Description

该QFileSystemModel类提供了在本地文件系统的数据模型。

这个类提供了访问本地文件系统，提供了功能重命名和删除文件和目录，并创建新的目录。在最简单的情况下，它可以用于与合适的显示部件作为一个浏览器或过滤器的一部分。

QFileSystemModel可以使用所提供的标准接口来访问[QAbstractItemModel](qabstractitemmodel.html)的，但它也提供了一些方便的功能所特有的一个目录模型。该[fileInfo](qfilesystemmodel.html#fileInfo)（ ）[isDir](qfilesystemmodel.html#isDir)（ ）[name](index.htm#name)（ ）和路径（ ）函数提供了有关与模型中的项目相关的文件和目录信息。目录中可以创建和删除使用[mkdir](qfilesystemmodel.html#mkdir)（ ）[rmdir](qfilesystemmodel.html#rmdir)（ ） 。

**Note:**QFileSystemModel需要一个GUI应用程序的一个实例。

### Example Usage

通常是构造一个父对象，显示一个默认目录中的内容的目录型号：

```
     QFileSystemModel *model = new QFileSystemModel;
     model->setRootPath([QDir](qdir.html).currentPath());

```

树视图可用于显示模型的内容

```
     [QTreeView](qtreeview.html) *tree = new [QTreeView](qtreeview.html)(splitter);
     tree->setModel(model);

```

和一个特定的目录中的内容可以显示通过将树视图的根指数：

```
     tree->setRootIndex(model->index([QDir](qdir.html).currentPath()));

```

视图的根指数，可用于控制如何分层模型的多显示。[QDirModel(obsolete)](qdirmodel.html)提供了一个方便的功能，用于返回一个路径模型中的一个目录一个合适的模型索引。

### Caching and Performance

QFileSystemModel不会获取任何文件或目录，直到[setRootPath](qfilesystemmodel.html#setRootPath)（）被调用。这将防止在文件系统上的任何不必要的查询，直到这一点，如清单上的Windows的驱动器。

不像[QDirModel(obsolete)](qdirmodel.html)， QFileSystemModel使用单独的线程来填充自身，所以它不会造成主线程挂起的文件系统受到质疑。调用[rowCount](qfilesystemmodel.html#rowCount)（ ）将返回0 ，直到模型填充的目录。

QFileSystemModel保持与文件信息的高速缓存。高速缓存是使用自动保持更新的[QFileSystemWatcher](qfilesystemwatcher.html)。

* * *

## Type Documentation

```
QFileSystemModel.Roles
```

| Constant | Value |
| --- | --- |
| `QFileSystemModel.FileIconRole` | `Qt.DecorationRole` |
| `QFileSystemModel.FilePathRole` | `Qt.UserRole + 1` |
| `QFileSystemModel.FileNameRole` | `Qt.UserRole + 2` |
| `QFileSystemModel.FilePermissions` | `Qt.UserRole + 3` |

* * *

## Method Documentation

```
QFileSystemModel.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个文件系统模型与给定的_parent_。

```
bool QFileSystemModel.canFetchMore (self, QModelIndex parent)
```

从重新实现[QAbstractItemModel.canFetchMore](qabstractitemmodel.html#canFetchMore)（ ） 。

```
int QFileSystemModel.columnCount (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.columnCount](qabstractitemmodel.html#columnCount)（ ） 。

```
QVariant QFileSystemModel.data (self, QModelIndex index, int role = Qt.DisplayRole)
```

从重新实现[QAbstractItemModel.data](qabstractitemmodel.html#data)（ ） 。

**See also** [setData](qfilesystemmodel.html#setData)（ ） 。

```
bool QFileSystemModel.dropMimeData (self, QMimeData data, Qt.DropAction action, int row, int column, QModelIndex parent)
```

从重新实现[QAbstractItemModel.dropMimeData](qabstractitemmodel.html#dropMimeData)（ ） 。

处理_data_通过拖放操作，与给定的供给结束_action_过在由指定的模型中的行_row_和_column_以及由_parent_索引。

**See also** [supportedDropActions](qfilesystemmodel.html#supportedDropActions)（ ） 。

```
bool QFileSystemModel.event (self, QEvent event)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QFileSystemModel.fetchMore (self, QModelIndex parent)
```

从重新实现[QAbstractItemModel.fetchMore](qabstractitemmodel.html#fetchMore)（ ） 。

```
QIcon QFileSystemModel.fileIcon (self, QModelIndex aindex)
```

[

根据给定的返回存储在模型中的项的图标_index_。

](qicon.html)

```
QFileInfo QFileSystemModel.fileInfo (self, QModelIndex aindex)
```

[](qfileinfo.html)

[返回](qfileinfo.html)[QFileInfo](qfileinfo.html)根据给定的存储在模型中的项_index_。

```
QString QFileSystemModel.fileName (self, QModelIndex aindex)
```

返回根据给定的存储在模型中的项目的文件名_index_。

```
QString QFileSystemModel.filePath (self, QModelIndex index)
```

返回根据存储在模型中的项的路径_index_给出。

```
QDir.Filters QFileSystemModel.filter (self)
```

[

返回目录模型中指定的过滤器。

](index.htm)

[如果一个过滤器没有被设置，则默认过滤器是](index.htm)[QDir.AllEntries](qdir.html#Filter-enum)|[QDir.NoDotAndDotDot](qdir.html#Filter-enum)|[QDir.AllDirs](qdir.html#Filter-enum)。

**See also** [setFilter](qfilesystemmodel.html#setFilter)（）和[QDir.Filters](qdir.html#Filter-enum)。

```
Qt.ItemFlags QFileSystemModel.flags (self, QModelIndex index)
```

[](index.htm)

[从重新实现](index.htm)[QAbstractItemModel.flags](qabstractitemmodel.html#flags)（ ） 。

```
bool QFileSystemModel.hasChildren (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.hasChildren](qabstractitemmodel.html#hasChildren)（ ） 。

```
QVariant QFileSystemModel.headerData (self, int section, Qt.Orientation orientation, int role = Qt.DisplayRole)
```

从重新实现[QAbstractItemModel.headerData](qabstractitemmodel.html#headerData)（ ） 。

```
QFileIconProvider QFileSystemModel.iconProvider (self)
```

[

返回文件的图标提供商此目录的模式。

](qfileiconprovider.html)

[**See also**](qfileiconprovider.html) [setIconProvider](qfilesystemmodel.html#setIconProvider)（ ） 。

```
QModelIndex QFileSystemModel.index (self, int row, int column, QModelIndex parent = QModelIndex())
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemModel.index](qabstractitemmodel.html#index)（ ） 。

```
QModelIndex QFileSystemModel.index (self, QString path, int column = 0)
```

[

这是一个重载函数。

返回模型项指数为给定的_path_和_column_。

```
bool QFileSystemModel.isDir (self, QModelIndex index)
```

返回True如果模型项目_index_表示一个目录，否则返回False 。

```
bool QFileSystemModel.isReadOnly (self)
```

](qmodelindex.html)

```
QDateTime QFileSystemModel.lastModified (self, QModelIndex index)
```

[

返回的日期和时间时_index_最后修订。

](qdatetime.html)

```
QMimeData QFileSystemModel.mimeData (self, list-of-QModelIndex indexes)
```

[](qmimedata.html)

[从重新实现](qmimedata.html)[QAbstractItemModel.mimeData](qabstractitemmodel.html#mimeData)（ ） 。

返回一个对象，该对象包含指定的序列化描述_indexes_。用于描述对应于该索引的项的格式是从所获得的[mimeTypes](qfilesystemmodel.html#mimeTypes)（）函数。

如果索引的列表为空，则返回0 ，而不是一个序列化的空单。

```
QStringList QFileSystemModel.mimeTypes (self)
```

从重新实现[QAbstractItemModel.mimeTypes](qabstractitemmodel.html#mimeTypes)（ ） 。

返回可用于描述在模型中的项列表的MIME类型的列表。

```
QModelIndex QFileSystemModel.mkdir (self, QModelIndex parent, QString name)
```

[

创建具有一个目录_name_在_parent_模型索引。

```
QVariant QFileSystemModel.myComputer (self, int role = Qt.DisplayRole)
```

返回下指定存储的数据_role_该项目“我的电脑” 。

](qmodelindex.html)

[**See also**](qmodelindex.html) [Qt.ItemDataRole](qt.html#ItemDataRole-enum)。

```
bool QFileSystemModel.nameFilterDisables (self)
```

```
QStringList QFileSystemModel.nameFilters (self)
```

返回应用到该模型中的名称的过滤器列表。

**See also** [setNameFilters](qfilesystemmodel.html#setNameFilters)（ ） 。

```
QModelIndex QFileSystemModel.parent (self, QModelIndex child)
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemModel.parent](qabstractitemmodel.html#parent)（ ） 。

```
QFile.Permissions QFileSystemModel.permissions (self, QModelIndex index)
```

[](index.htm)

[返回的完整或的结果组合在一起](index.htm)[QFile.Permission](qfile.html#Permission-enum)为_index_。

```
bool QFileSystemModel.remove (self, QModelIndex aindex)
```

删除模型项目_index_从文件系统模型和**deletes the corresponding file from the file system**，返回True，如果成功的。如果该项目不能被删除，则返回False。

**Warning:**此函数删除从文件系统中的文件，它**not**它们移动到那里他们可以恢复的位置。

**See also** [rmdir](qfilesystemmodel.html#rmdir)（ ） 。

```
bool QFileSystemModel.resolveSymlinks (self)
```

```
bool QFileSystemModel.rmdir (self, QModelIndex aindex)
```

删除对应的模型项目的目录_index_在文件系统模型和**deletes the corresponding directory from the file system**，返回True，如果成功的。如果目录不能被删除，则返回False。

**Warning:**此函数删除目录的文件系统;它**not**它们移动到那里他们可以恢复的位置。

**See also** [remove](qfilesystemmodel.html#remove)（ ） 。

```
QDir QFileSystemModel.rootDirectory (self)
```

[

当前设置的目录

](qdir.html)

[**See also**](qdir.html) [rootPath](qfilesystemmodel.html#rootPath)（ ） 。

```
QString QFileSystemModel.rootPath (self)
```

当前设置的根路径

**See also** [setRootPath](qfilesystemmodel.html#setRootPath)（）和[rootDirectory](qfilesystemmodel.html#rootDirectory)（ ） 。

```
int QFileSystemModel.rowCount (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.rowCount](qabstractitemmodel.html#rowCount)（ ） 。

```
bool QFileSystemModel.setData (self, QModelIndex idx, QVariant value, int role = Qt.EditRole)
```

从重新实现[QAbstractItemModel.setData](qabstractitemmodel.html#setData)（ ） 。

**See also** [data](qfilesystemmodel.html#data)（ ） 。

```
QFileSystemModel.setFilter (self, QDir.Filters filters)
```

设置目录型号的过滤器，通过指定_filters_。

请注意，您设置的过滤器应始终包含[QDir.AllDirs](qdir.html#Filter-enum)枚举值，否则[QFileSystemModel](qfilesystemmodel.html)将无法读取的目录结构。

**See also** [filter](qfilesystemmodel.html#filter)（）和[QDir.Filters](qdir.html#Filter-enum)。

```
QFileSystemModel.setIconProvider (self, QFileIconProvider provider)
```

设置_provider_文件图标的目录模式。

**See also** [iconProvider](qfilesystemmodel.html#iconProvider)（ ） 。

```
QFileSystemModel.setNameFilterDisables (self, bool enable)
```

```
QFileSystemModel.setNameFilters (self, QStringList filters)
```

设置名称_filters_应用对现有的文件。

**See also** [nameFilters](qfilesystemmodel.html#nameFilters)（ ） 。

```
QFileSystemModel.setReadOnly (self, bool enable)
```

```
QFileSystemModel.setResolveSymlinks (self, bool enable)
```

```
QModelIndex QFileSystemModel.setRootPath (self, QString path)
```

[](qmodelindex.html)

[设置被观看了该模型的目录_newPath_通过安装](qmodelindex.html)[file system watcher](qfilesystemwatcher.html)就可以了。任何更改的文件和该目录下的目录将反映在模型中。

如果该路径被改变，[rootPathChanged](qfilesystemmodel.html#rootPathChanged)（）信号将被发射。

**Note:**此函数不改变模型的结构或修改提供给视图的数据。换句话说，本模型的“根”是_not_更改为包含所指定的目录中唯一的文件和目录_newPath_在文件系统中。

**See also** [rootPath](qfilesystemmodel.html#rootPath)（ ） 。

```
int QFileSystemModel.size (self, QModelIndex index)
```

返回该尺寸中的字节_index_。如果文件不存在，则返回0 。

```
QFileSystemModel.sort (self, int column, Qt.SortOrder order = Qt.AscendingOrder)
```

从重新实现[QAbstractItemModel.sort](qabstractitemmodel.html#sort)（ ） 。

```
Qt.DropActions QFileSystemModel.supportedDropActions (self)
```

[](index.htm)

[从重新实现](index.htm)[QAbstractItemModel.supportedDropActions](qabstractitemmodel.html#supportedDropActions)（ ） 。

```
QFileSystemModel.timerEvent (self, QTimerEvent event)
```

从重新实现[QObject.timerEvent](qobject.html#timerEvent)（ ） 。

```
QString QFileSystemModel.type (self, QModelIndex index)
```

返回文件的类型_index_如“目录”或“ JPEG文件” 。

* * *

## Qt Signal Documentation

```
void directoryLoaded (const QString&)
```

这是该信号的默认超载。

当采集线程完成加载这个信号被发射的_path_。

此功能被引入Qt的4.7 。

```
void fileRenamed (const QString&,const QString&,const QString&)
```

这是该信号的默认超载。

这个信号被发射时与一个文件_oldName_成功更名为_newName_。该文件位于目录_path_。

```
void rootPathChanged (const QString&)
```

这是该信号的默认超载。

这个信号被发射时的根路径已被更改为一个_newPath_。