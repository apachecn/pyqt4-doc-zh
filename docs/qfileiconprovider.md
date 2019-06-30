# QFileIconProvider Class Reference

## [[QtGui](index.htm) module]

该QFileIconProvider类提供文件图标为[QDirModel(obsolete)](qdirmodel.html)和[QFileSystemModel](qfilesystemmodel.html)类。[More...](#details)

### Types

*   `enum IconType { Computer, Desktop, Trashcan, Network, ..., File }`

### Methods

*   `__init__ (self)`
*   `QIcon icon (self, IconType type)`
*   `QIcon icon (self, QFileInfo info)`
*   `QString type (self, QFileInfo info)`

* * *

## Detailed Description

该QFileIconProvider类提供文件图标为[QDirModel(obsolete)](qdirmodel.html)和[QFileSystemModel](qfilesystemmodel.html)类。

* * *

## Type Documentation

```
QFileIconProvider.IconType
```

| Constant | Value |
| --- | --- |
| `QFileIconProvider.Computer` | `0` |
| `QFileIconProvider.Desktop` | `1` |
| `QFileIconProvider.Trashcan` | `2` |
| `QFileIconProvider.Network` | `3` |
| `QFileIconProvider.Drive` | `4` |
| `QFileIconProvider.Folder` | `5` |
| `QFileIconProvider.File` | `6` |

* * *

## Method Documentation

```
QFileIconProvider.__init__ (self)
```

构造一个文件图标提供商。

```
QIcon QFileIconProvider.icon (self, IconType type)
```

[

返回一个图标为给定的设置_type_。

](qicon.html)

```
QIcon QFileIconProvider.icon (self, QFileInfo info)
```

[

返回由所描述的文件的图标_info_。

```
QString QFileIconProvider.type (self, QFileInfo info)
```

返回由所描述的文件的类型_info_。

](qicon.html)