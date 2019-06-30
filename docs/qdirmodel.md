# QDirModel Class Reference

## [[QtGui](index.htm) module]

该QDirModel类提供了在本地文件系统的数据模型。[More...](#details)

继承[QAbstractItemModel](qabstractitemmodel.html)。

### Types

*   `enum Roles { FileIconRole, FilePathRole, FileNameRole }`

### Methods

*   `__init__ (self, QStringList nameFilters, QDir.Filters filters, QDir.SortFlags sort, QObject parent = None)`
*   `__init__ (self, QObject parent = None)`
*   `int columnCount (self, QModelIndex parent = QModelIndex())`
*   `QVariant data (self, QModelIndex index, int role = Qt.DisplayRole)`
*   `bool dropMimeData (self, QMimeData data, Qt.DropAction action, int row, int column, QModelIndex parent)`
*   `QIcon fileIcon (self, QModelIndex index)`
*   `QFileInfo fileInfo (self, QModelIndex index)`
*   `QString fileName (self, QModelIndex index)`
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
*   `bool lazyChildCount (self)`
*   `QMimeData mimeData (self, list-of-QModelIndex indexes)`
*   `QStringList mimeTypes (self)`
*   `QModelIndex mkdir (self, QModelIndex parent, QString name)`
*   `QStringList nameFilters (self)`
*   `QModelIndex parent (self, QModelIndex child)`
*   `QObject parent (self)`
*   `refresh (self, QModelIndex parent = QModelIndex())`
*   `bool remove (self, QModelIndex index)`
*   `bool resolveSymlinks (self)`
*   `bool rmdir (self, QModelIndex index)`
*   `int rowCount (self, QModelIndex parent = QModelIndex())`
*   `bool setData (self, QModelIndex index, QVariant value, int role = Qt.EditRole)`
*   `setFilter (self, QDir.Filters filters)`
*   `setIconProvider (self, QFileIconProvider provider)`
*   `setLazyChildCount (self, bool enable)`
*   `setNameFilters (self, QStringList filters)`
*   `setReadOnly (self, bool enable)`
*   `setResolveSymlinks (self, bool enable)`
*   `setSorting (self, QDir.SortFlags sort)`
*   `sort (self, int column, Qt.SortOrder order = Qt.AscendingOrder)`
*   `QDir.SortFlags sorting (self)`
*   `Qt.DropActions supportedDropActions (self)`

* * *

## Detailed Description

该QDirModel类提供了在本地文件系统的数据模型。

QDirModel的使用是不推荐了。该[QFileSystemModel](qfilesystemmodel.html)类是一个更高性能的替代方案。

这个类提供了访问本地文件系统，提供了功能重命名和删除文件和目录，并创建新的目录。在最简单的情况下，它可以用于与合适的显示部件作为一个浏览器或者文件管理器的一部分。

QDirModel保持与文件信息的高速缓存。缓存需要与被更新[refresh](qdirmodel.html#refresh)（ ） 。

QDirModel可以使用所提供的标准接口来访问[QAbstractItemModel](qabstractitemmodel.html)的，但它也提供了一些方便的功能所特有的一个目录模型。该[fileInfo](qdirmodel.html#fileInfo)（）和[isDir](qdirmodel.html#isDir)（ ）函数提供了有关与模型中的项目相关的文件和目录信息。

目录中可以创建和删除使用[mkdir](qdirmodel.html#mkdir)（ ）[rmdir](qdirmodel.html#rmdir)（ ） ，模型会自动更新，以变化考虑在内。

**Note:**QDirModel需要一个GUI应用程序的一个实例。

* * *

## Type Documentation

```
QDirModel.Roles
```

| Constant | Value |
| --- | --- |
| `QDirModel.FileIconRole` | `Qt.DecorationRole` |
| `QDirModel.FilePathRole` | `Qt.UserRole + 1` |
| `QDirModel.FileNameRole` | ？ |

* * *

## Method Documentation

```
QDirModel.__init__ (self, QStringList nameFilters, QDir.Filters filters, QDir.SortFlags sort, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的目录模式与给定_parent_。只有那些匹配的文件_nameFilters_和_filters_被包括在模型中。排序顺序是由给定_sort_标志。

```
QDirModel.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个目录模式与给定_parent_。

```
int QDirModel.columnCount (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.columnCount](qabstractitemmodel.html#columnCount)（ ） 。

返回列中的数_parent_模型项目。

```
QVariant QDirModel.data (self, QModelIndex index, int role = Qt.DisplayRole)
```

从重新实现[QAbstractItemModel.data](qabstractitemmodel.html#data)（ ） 。

返回的数据为模型项目_index_用给定的_role_。

**See also** [setData](qdirmodel.html#setData)（ ） 。

```
bool QDirModel.dropMimeData (self, QMimeData data, Qt.DropAction action, int row, int column, QModelIndex parent)
```

从重新实现[QAbstractItemModel.dropMimeData](qabstractitemmodel.html#dropMimeData)（ ） 。

处理_data_通过拖放操作，与给定的供给结束_action_过在由指定的模型中的行_row_和_column_以及由_parent_索引。

**See also** [supportedDropActions](qdirmodel.html#supportedDropActions)（ ） 。

```
QIcon QDirModel.fileIcon (self, QModelIndex index)
```

[

返回根据给定的存储在模型中的图标的项_index_。

](qicon.html)

```
QFileInfo QDirModel.fileInfo (self, QModelIndex index)
```

[

返回文件信息指定模型_index_。

](qfileinfo.html)

[**Note:**如果模型指数代表了底层的文件系统的符号链接时，返回的文件信息，将包含有关符号链接本身的信息，而不管是否](qfileinfo.html)[resolveSymlinks](qdirmodel.html#resolveSymlinks-prop)启用与否。

**See also** [QFileInfo.symLinkTarget](qfileinfo.html#symLinkTarget)（ ） 。

```
QString QDirModel.fileName (self, QModelIndex index)
```

返回根据存储在模型中的项的名称_index_给出。

```
QString QDirModel.filePath (self, QModelIndex index)
```

返回根据存储在模型中的项的路径_index_给出。

```
QDir.Filters QDirModel.filter (self)
```

[

返回过滤器规格为目录模式。

](index.htm)

[**See also**](index.htm) [setFilter](qdirmodel.html#setFilter)（）和[QDir.Filters](qdir.html#Filter-enum)。

```
Qt.ItemFlags QDirModel.flags (self, QModelIndex index)
```

[](index.htm)

[从重新实现](index.htm)[QAbstractItemModel.flags](qabstractitemmodel.html#flags)（ ） 。

返回项标志为给定的_index_在模型中。

**See also** [Qt.ItemFlags](qt.html#ItemFlag-enum)。

```
bool QDirModel.hasChildren (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.hasChildren](qabstractitemmodel.html#hasChildren)（ ） 。

返回True如果_parent_模型项目有孩子，否则返回False 。

```
QVariant QDirModel.headerData (self, int section, Qt.Orientation orientation, int role = Qt.DisplayRole)
```

从重新实现[QAbstractItemModel.headerData](qabstractitemmodel.html#headerData)（ ） 。

返回下指定存储的数据_role_为指定的_section_与给定的标头_orientation_。

```
QFileIconProvider QDirModel.iconProvider (self)
```

[

返回文件的图标提供商此目录的模式。

](qfileiconprovider.html)

[**See also**](qfileiconprovider.html) [setIconProvider](qdirmodel.html#setIconProvider)（ ） 。

```
QModelIndex QDirModel.index (self, int row, int column, QModelIndex parent = QModelIndex())
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemModel.index](qabstractitemmodel.html#index)（ ） 。

返回在模型项目索引项_parent_用给定的_row_和_column_。

```
QModelIndex QDirModel.index (self, QString path, int column = 0)
```

[

这是一个重载函数。

返回模型项指数为给定的_path_。

```
bool QDirModel.isDir (self, QModelIndex index)
```

返回True如果模型项目_index_表示一个目录，否则返回False 。

```
bool QDirModel.isReadOnly (self)
```

```
bool QDirModel.lazyChildCount (self)
```

](qmodelindex.html)

```
QMimeData QDirModel.mimeData (self, list-of-QModelIndex indexes)
```

[

该_QMimeData_结果

](qmimedata.html)

[从重新实现](qmimedata.html)[QAbstractItemModel.mimeData](qabstractitemmodel.html#mimeData)（ ） 。

返回一个对象，该对象包含指定的序列化描述_indexes_。用于描述对应于该索引的项的格式是从所获得的[mimeTypes](qdirmodel.html#mimeTypes)（）函数。

如果索引的列表为空，则返回0 ，而不是一个序列化的空单。

```
QStringList QDirModel.mimeTypes (self)
```

从重新实现[QAbstractItemModel.mimeTypes](qabstractitemmodel.html#mimeTypes)（ ） 。

返回可用于描述在模型中的项列表的MIME类型的列表。

```
QModelIndex QDirModel.mkdir (self, QModelIndex parent, QString name)
```

[

创建具有一个目录_name_在_parent_模型项目。

```
QStringList QDirModel.nameFilters (self)
```

返回应用到该模型中的名称的过滤器列表。

](qmodelindex.html)

[**See also**](qmodelindex.html) [setNameFilters](qdirmodel.html#setNameFilters)（ ） 。

```
QModelIndex QDirModel.parent (self, QModelIndex child)
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemModel.parent](qabstractitemmodel.html#parent)（ ） 。

返回给定的父_child_模型项目。

```
QObject QDirModel.parent (self)
```

[

```
QDirModel.refresh (self, QModelIndex parent = QModelIndex())
```

](qobject.html)

[](qobject.html)[QDirModel](qdirmodel.html)缓存文件信息。这个函数更新缓存。该_parent_参数是从该模型被更新的目录中，默认值将更新从文件系统（整个模型）的根目录中的模型。

```
bool QDirModel.remove (self, QModelIndex index)
```

删除模型项目_index_从目录模型和**deletes the corresponding file from the file system**，返回True，如果成功的。如果该项目不能被删除，则返回False。

**Warning:**此函数删除从文件系统中的文件，它**not**它们移动到那里他们可以恢复的位置。

**See also** [rmdir](qdirmodel.html#rmdir)（ ） 。

```
bool QDirModel.resolveSymlinks (self)
```

```
bool QDirModel.rmdir (self, QModelIndex index)
```

删除对应的模型项目的目录_index_在目录中的模型和**deletes the corresponding directory from the file system**，返回True，如果成功的。如果目录不能被删除，则返回False。

**Warning:**此函数删除目录的文件系统;它**not**它们移动到那里他们可以恢复的位置。

**See also** [remove](qdirmodel.html#remove)（ ） 。

```
int QDirModel.rowCount (self, QModelIndex parent = QModelIndex())
```

从重新实现[QAbstractItemModel.rowCount](qabstractitemmodel.html#rowCount)（ ） 。

返回行的数目_parent_模型项目。

```
bool QDirModel.setData (self, QModelIndex index, QVariant value, int role = Qt.EditRole)
```

从重新实现[QAbstractItemModel.setData](qabstractitemmodel.html#setData)（ ） 。

设置数据模型项目_index_用给定的_role_由所引用的数据_value_。成功返回True ，否则返回False 。

**See also** [data](qdirmodel.html#data)（）和[Qt.ItemDataRole](qt.html#ItemDataRole-enum)。

```
QDirModel.setFilter (self, QDir.Filters filters)
```

设置目录型号的过滤器，通过指定_filters_。

请注意，您设置的过滤器应始终包含[QDir.AllDirs](qdir.html#Filter-enum)枚举值，否则[QDirModel](qdirmodel.html)将无法读取的目录结构。

**See also** [filter](qdirmodel.html#filter)（）和[QDir.Filters](qdir.html#Filter-enum)。

```
QDirModel.setIconProvider (self, QFileIconProvider provider)
```

设置_provider_文件图标的目录模式。

**See also** [iconProvider](qdirmodel.html#iconProvider)（ ） 。

```
QDirModel.setLazyChildCount (self, bool enable)
```

```
QDirModel.setNameFilters (self, QStringList filters)
```

设置名称_filters_该目录模型。

**See also** [nameFilters](qdirmodel.html#nameFilters)（ ） 。

```
QDirModel.setReadOnly (self, bool enable)
```

```
QDirModel.setResolveSymlinks (self, bool enable)
```

```
QDirModel.setSorting (self, QDir.SortFlags sort)
```

设置目录模式的排序顺序，通过指定_sort_。

**See also** [sorting](qdirmodel.html#sorting)（）和[QDir.SortFlags](qdir.html#SortFlag-enum)。

```
QDirModel.sort (self, int column, Qt.SortOrder order = Qt.AscendingOrder)
```

从重新实现[QAbstractItemModel.sort](qabstractitemmodel.html#sort)（ ） 。

排序的模型项目_column_使用_order_给出。该命令是在定义的值[Qt.SortOrder](qt.html#SortOrder-enum)。

```
QDir.SortFlags QDirModel.sorting (self)
```

[

返回用于目录模型的排序方法。

](index.htm)

[**See also**](index.htm) [setSorting](qdirmodel.html#setSorting)（）和[QDir.SortFlags](qdir.html#SortFlag-enum)。

```
Qt.DropActions QDirModel.supportedDropActions (self)
```

[](index.htm)

[从重新实现](index.htm)[QAbstractItemModel.supportedDropActions](qabstractitemmodel.html#supportedDropActions)（ ） 。

返回此模型所支持的放置动作。

**See also** [Qt.DropActions](qt.html#DropAction-enum)。