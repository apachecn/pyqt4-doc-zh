# QLibraryInfo Class Reference

## [[QtCore](index.htm) module]

该QLibraryInfo类提供有关Qt库的信息。[More...](#details)

### Types

*   `enum LibraryLocation { PrefixPath, DocumentationPath, HeadersPath, LibrariesPath, ..., ImportsPath }`

### Methods

*   `__init__ (self, QLibraryInfo)`

### Static Methods

*   `QDate buildDate ()`
*   `QString buildKey ()`
*   `QString licensedProducts ()`
*   `QString licensee ()`
*   `QString location (LibraryLocation)`

* * *

## Detailed Description

该QLibraryInfo类提供有关Qt库的信息。

多条信息被Qt的配置时建立的。安装路径，许可证信息，甚至是唯一的构建关键。这个类提供了访问这些信息的抽象。

| Function | Return value |
| --- | --- |
| [buildKey](qlibraryinfo.html#buildKey)() | A string that identifies the Qt version and the configuration. This key is used to ensure that [plugins](index.htm) link against the same version of Qt as the application. |
| [location](qlibraryinfo.html#location)() | The path to a certain Qt component (e.g., documentation, header files). |
| [licensee](qlibraryinfo.html#licensee)(), [licensedProducts](qlibraryinfo.html#licensedProducts)() | Licensing information. |

您也可以使用`qt.conf`文件复盖编译到Qt库的硬编码路径。欲了解更多信息，请参阅[Using qt.conf](index.htm)文档。

* * *

## Type Documentation

```
QLibraryInfo.LibraryLocation
```

该枚举类型用于指定一个特定的位置说明：

| Constant | Value | Description |
| --- | --- | --- |
| `QLibraryInfo.PrefixPath` | `0` | 默认前缀的所有路径。 |
| `QLibraryInfo.DocumentationPath` | `1` | 安装时的文件位置。 |
| `QLibraryInfo.HeadersPath` | `2` | 该位置为所有头文件。 |
| `QLibraryInfo.LibrariesPath` | `3` | 安装库的位置。 |
| `QLibraryInfo.BinariesPath` | `4` | 安装了Qt的二进制文件（工具和应用程序）的位置。 |
| `QLibraryInfo.PluginsPath` | `5` | Qt安装插件的位置。 |
| `QLibraryInfo.ImportsPath` | `11` | 安装QML扩展到导入的位置。 |
| `QLibraryInfo.DataPath` | `6` | 一般的Qt数据的位置。 |
| `QLibraryInfo.TranslationsPath` | `7` | 翻译信息为Qt字符串的位置。 |
| `QLibraryInfo.SettingsPath` | `8` | 该位置为Qt设置。 |
| `QLibraryInfo.ExamplesPath` | `10` | 该位置安装时的例子。 |
| `QLibraryInfo.DemosPath` | `9` | 该位置后，安装演示。 |

**See also** [location](qlibraryinfo.html#location)（ ） 。

* * *

## Method Documentation

```
QLibraryInfo.__init__ (self, QLibraryInfo)
```

```
QDate QLibraryInfo.buildDate ()
```

[

返回的安装日期这个版本的Qt 。安装日期通常是最后一次， Qt的来源进行了配置。

此功能被引入Qt的4.6 。

```
QString QLibraryInfo.buildKey ()
```

返回一个唯一的密钥识别此版本的Qt和它的配置。这关键不是全球唯一的，是兼容的，而唯一有用的建立两种配置。这可用于比较`QT_BUILD_KEY`预处理器符号。

](qdate.html)

[**See also**](qdate.html) [location](qlibraryinfo.html#location)（ ） 。

```
QString QLibraryInfo.licensedProducts ()
```

返回的这个版本的Qt的授权可以访问产品。

**See also** [licensee](qlibraryinfo.html#licensee)（ ） 。

```
QString QLibraryInfo.licensee ()
```

返回给谁这个版本的Qt授权的人。

**See also** [licensedProducts](qlibraryinfo.html#licensedProducts)（ ） 。

```
QString QLibraryInfo.location (LibraryLocation)
```

返回由指定的位置_loc_。