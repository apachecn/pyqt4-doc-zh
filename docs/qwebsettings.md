# QWebSettings Class Reference

## [[QtWebKit](index.htm) module]

该QWebSettings类提供了一个对象来存储所使用的设置[QWebPage](qwebpage.html)和[QWebFrame](qwebframe.html)。[More...](#details)

### Types

*   `enum FontFamily { StandardFont, FixedFont, SerifFont, SansSerifFont, CursiveFont, FantasyFont }`
*   `enum FontSize { MinimumFontSize, MinimumLogicalFontSize, DefaultFontSize, DefaultFixedFontSize }`
*   `enum WebAttribute { AutoLoadImages, JavascriptEnabled, JavaEnabled, PluginsEnabled, ..., HyperlinkAuditingEnabled }`
*   `enum WebGraphic { MissingImageGraphic, MissingPluginGraphic, DefaultFrameIconGraphic, TextAreaSizeGripCornerGraphic, ..., SearchCancelButtonPressedGraphic }`

### Methods

*   `QString defaultTextEncoding (self)`
*   `QString fontFamily (self, FontFamily which)`
*   `int fontSize (self, FontSize type)`
*   `QString localStoragePath (self)`
*   `resetAttribute (self, WebAttribute attr)`
*   `resetFontFamily (self, FontFamily which)`
*   `resetFontSize (self, FontSize type)`
*   `setAttribute (self, WebAttribute attr, bool on)`
*   `setDefaultTextEncoding (self, QString encoding)`
*   `setFontFamily (self, FontFamily which, QString family)`
*   `setFontSize (self, FontSize type, int size)`
*   `setLocalStoragePath (self, QString path)`
*   `setUserStyleSheetUrl (self, QUrl location)`
*   `bool testAttribute (self, WebAttribute attr)`
*   `QUrl userStyleSheetUrl (self)`

### Static Methods

*   `clearIconDatabase ()`
*   `clearMemoryCaches ()`
*   `enablePersistentStorage (QString path = QString())`
*   `QWebSettings globalSettings ()`
*   `QString iconDatabasePath ()`
*   `QIcon iconForUrl (QUrl url)`
*   `int maximumPagesInCache ()`
*   `int offlineStorageDefaultQuota ()`
*   `QString offlineStoragePath ()`
*   `QString offlineWebApplicationCachePath ()`
*   `int offlineWebApplicationCacheQuota ()`
*   `setIconDatabasePath (QString location)`
*   `setMaximumPagesInCache (int pages)`
*   `setObjectCacheCapacities (int cacheMinDeadCapacity, int cacheMaxDead, int totalCapacity)`
*   `setOfflineStorageDefaultQuota (int maximumSize)`
*   `setOfflineStoragePath (QString path)`
*   `setOfflineWebApplicationCachePath (QString path)`
*   `setOfflineWebApplicationCacheQuota (int maximumSize)`
*   `setWebGraphic (WebGraphic type, QPixmap graphic)`
*   `QPixmap webGraphic (WebGraphic type)`

* * *

## Detailed Description

该QWebSettings类提供了一个对象来存储所使用的设置[QWebPage](qwebpage.html)和[QWebFrame](qwebframe.html)。

Each [QWebPage](qwebpage.html)对象都有自己的QWebSettings对象，它配置该页面的设置。如果未配置设置，那么就抬头在全局设置对象，可以使用访问[globalSettings](qwebsettings.html#globalSettings)（ ） 。

QWebSettings允许浏览器属性，如字体大小和家庭，自定义样式表的位置，如JavaScript和插件的通用属性配置。各个属性使用设置[setAttribute](qwebsettings.html#setAttribute)（）函数。该[WebAttribute](qwebsettings.html#WebAttribute-enum)枚举进一步描述了每个属性。

QWebSettings还配置全局属性，如网页的内存缓存，图标数据库，本地数据库存储和离线应用程序存储。

### Enabling Plugins

支持浏览器插件可以通过设置启用[PluginsEnabled](qwebsettings.html#WebAttribute-enum)属性。对于许多应用来说，这个属性是启用所有的网页通过在设置它[global settings object](qwebsettings.html#globalSettings)。[QtWebKit](index.htm)将处理Qt的插件时，总是忽略此设置。允许决定一个Qt插件在其重新实现由客户端[QWebPage.createPlugin](qwebpage.html#createPlugin)（ ） 。

### Web Application Support

WebKit的规定在指定功能的支持[HTML 5](http://www.w3.org/TR/html5/)能够提高Web应用程序的性能和功能。其中包括客户端（离线）的存储和使用Web应用程序缓存。

客户端（离线）存储是经过改良的使用Cookie来存储持久数据的Web应用程序。应用程序可以配置并启用通过调用使用离线存储数据库的[setOfflineStoragePath](qwebsettings.html#setOfflineStoragePath)（）以适当的文件路径，并且可以通过调用限制配额为每个应用程序[setOfflineStorageDefaultQuota](qwebsettings.html#setOfflineStorageDefaultQuota)（ ） 。

* * *

## Type Documentation

```
QWebSettings.FontFamily
```

这个枚举描述由CSS 2中定义的通用字体家族。欲了解更多信息，请参阅[CSS standard](http://www.w3.org/TR/REC-CSS2/fonts.html#generic-font-families)。

| Constant | Value |
| --- | --- |
| `QWebSettings.StandardFont` | `0` |
| `QWebSettings.FixedFont` | `1` |
| `QWebSettings.SerifFont` | `2` |
| `QWebSettings.SansSerifFont` | `3` |
| `QWebSettings.CursiveFont` | `4` |
| `QWebSettings.FantasyFont` | `5` |

```
QWebSettings.FontSize
```

这个枚举变量描述字体大小，通过配置[QWebSettings](qwebsettings.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QWebSettings.MinimumFontSize` | `0` | 硬盘最小字体大小。 |
| `QWebSettings.MinimumLogicalFontSize` | `1` | 与缩小时所采用的最小的逻辑字体大小[QWebFrame.setTextSizeMultiplier](qwebframe.html#setTextSizeMultiplier)（ ） 。 |
| `QWebSettings.DefaultFontSize` | `2` | 默认字体大小为普通文字。 |
| `QWebSettings.DefaultFixedFontSize` | `3` | 默认字体大小为固定间距的文字。 |

```
QWebSettings.WebAttribute
```

这个枚举变量描述了通过配置各种属性[QWebSettings](qwebsettings.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QWebSettings.AutoLoadImages` | `0` | 指定图像是否在网页中自动加载。这是默认启用的。 |
| `QWebSettings.DnsPrefetchEnabled` | ？ | 指定QtWebKit的是否会尝试预取的DNS条目，以加快浏览。这只能作为一个全球性的属性。只为Qt 4.6和更高版本。这是默认情况下禁用。 |
| `QWebSettings.JavascriptEnabled` | `1` | 启用或禁用JavaScript程序的运行。这是默认启用 |
| `QWebSettings.JavaEnabled` | `2` | 启用或禁用Java小程序。目前不支持Java小程序。 |
| `QWebSettings.PluginsEnabled` | `3` | 启用或禁用网页中的插件（例如，使用NPAPI ） 。 Qt的插件有一个MIME类型，如“应用程序/ x - QT-插件”不受此设置。这是默认情况下禁用。 |
| `QWebSettings.PrivateBrowsingEnabled` | `4` | 私人浏览功能可以防止从WebKit的记录在历史上访问过的网页和存储网页的图标。这是默认情况下禁用。 |
| `QWebSettings.JavascriptCanOpenWindows` | `5` | 指定的JavaScript程序是否可以打开新窗口。这是默认情况下禁用。 |
| `QWebSettings.JavascriptCanCloseWindows` | ？ | 指定的JavaScript程序是否可以关闭窗口。这是默认情况下禁用。 |
| `QWebSettings.JavascriptCanAccessClipboard` | `6` | 指定的JavaScript程序是否可以读取或写入剪贴板。这是默认情况下禁用。 |
| `QWebSettings.DeveloperExtrasEnabled` | `7` | 启用额外的Web开发工具。目前，这使得在上下文菜单中的“检查”元素，以及使用[QWebInspector](qwebinspector.html)它控制着Web检查器对网站进行调试。这是默认情况下禁用。 |
| `QWebSettings.SpatialNavigationEnabled` | ？ | 启用或禁用空间导航的功能，其中包括在通过左，右，上和下箭头键在网页中可聚焦元素，如超链接和窗体控件之间进行导航的能力。例如，如果用户按下右键，启发式判断是否有他可能会试图达成朝着正确的，哪些元素是他想的元素。这是默认情况下禁用。 |
| `QWebSettings.LinksIncludedInFocusChain` | `8` | 指定的超链接是否应该包括在键盘焦点链。这是默认启用的。 |
| `QWebSettings.ZoomTextOnly` | `9` | 指定是否在框架上的变焦倍率仅适用于文本或全部内容。这是默认情况下禁用。 |
| `QWebSettings.PrintElementBackgrounds` | `10` | 指定背景颜色和图像是否也招来当页面被打印。这是默认启用的。 |
| `QWebSettings.OfflineStorageDatabaseEnabled` | `11` | 指定了HTML 5的离线存储功能的支持是否启用与否。这是默认情况下禁用。 |
| `QWebSettings.OfflineWebApplicationCacheEnabled` | `12` | 指定为HTML 5 Web应用程序的缓存功能的支持是否启用与否。这是默认情况下禁用。 |
| `QWebSettings.LocalStorageEnabled` | `13` | 指定了HTML 5的本地存储功能支持是否启用与否。这是默认情况下禁用。 （这个值被引入4.6 。 ） |
| `QWebSettings.LocalStorageDatabaseEnabled` | `LocalStorageEnabled` | _This enum value is deprecated._使用QWebSettings.LocalStorageEnabled代替。 |
| `QWebSettings.LocalContentCanAccessRemoteUrls` | ？ | 指定本地加载的文件是否被允许访问远程URL 。这是默认情况下禁用。有关安全性的起源和本地与远程内容查看详细信息[QWebSecurityOrigin](qwebsecurityorigin.html)。 （这个值被引入4.6 。 ） |
| `QWebSettings.LocalContentCanAccessFileUrls` | ？ | 指定本地加载的文件是否被允许访问其他地方的URL。这是默认启用的。有关安全性的起源和本地与远程内容查看详细信息[QWebSecurityOrigin](qwebsecurityorigin.html)。 |
| `QWebSettings.XSSAuditingEnabled` | ？ | 指定是否负荷要求应为跨站点脚本尝试进行监控。可疑的脚本将被阻止并报告在检查的JavaScript控制台。启用此功能可能会对性能产生影响，它默认是禁用的。 |
| `QWebSettings.AcceleratedCompositingEnabled` | ？ | 这个特点，配合使用时[QGraphicsWebView](qgraphicswebview.html)，加速Web内容的动画。变换和不透明性质的CSS动画将构成动画元素的缓存内容进行渲染。这是默认启用的。 |
| `QWebSettings.TiledBackingStoreEnabled` | ？ | 此设置使瓷砖后备存储功能的[QGraphicsWebView](qgraphicswebview.html)。与平铺的后备存储使能，以及当前可见区域周围的网页内容被推测为缓存位图的瓷砖。瓦片被自动保持同步的网页，因为它改变。启用平铺可以显着加快油画般滚动沉重的作业。启用该功能会增加内存消耗。使用CSS固定定位与内容，它不能很好地工作（参见[resizesToContents](qgraphicswebview.html#resizesToContents-prop)属性）。[tiledBackingStoreFrozen](qgraphicswebview.html#tiledBackingStoreFrozen-prop)属性允许应用程序暂时冻结后备存储的内容。这是默认情况下禁用。 |
| `QWebSettings.FrameFlatteningEnabled` | ？ | 与此设置每个子帧被扩展为它的内容。在触摸设备，它是理想的没有页面的任何可滚动的子部件，因为它会导致一个混乱的用户体验，带滚动有时滚动的子部件，并在其他时间滚动页面本身。出于这个原因，内置页框和框架都在触摸设备几乎无法使用。这将压扁的所有帧成为一体滚动页面。这是默认情况下禁用。 |
| `QWebSettings.SiteSpecificQuirksEnabled` | ？ | 此设置使WebKit的解决方法打破的网站。它是默认启用的。 |

```
QWebSettings.WebGraphic
```

此枚举描述网页中使用的标准图形元素。

| Constant | Value | Description |
| --- | --- | --- |
| `QWebSettings.MissingImageGraphic` | `0` | 所示的替换图形图像时无法加载。 |
| `QWebSettings.MissingPluginGraphic` | `1` | 所示的替换图形时，插件无法加载。 |
| `QWebSettings.DefaultFrameIconGraphic` | `2` | 为默认图标[QWebFrame.icon](qwebframe.html#icon-prop)（ ） 。 |
| `QWebSettings.TextAreaSizeGripCornerGraphic` | `3` | 用于显示文本区域的大小手柄的图形。 |
| `QWebSettings.DeleteButtonGraphic` | `4` | 所示为WebKit的 - 编辑 - 删除 - 按钮在删除用户界面的图形。 |
| `QWebSettings.InputSpeechButtonGraphic` | `5` | 支持语音识别输入字段中显示的图形。 |
| `QWebSettings.SearchCancelButtonGraphic` | `6` | 为显示在搜索字段中清除文本图形。 |
| `QWebSettings.SearchCancelButtonPressedGraphic` | `7` | 当SearchCancelButtonGraphic按下所示的图形。 |

* * *

## Method Documentation

```
QWebSettings.clearIconDatabase ()
```

清除图标库。

```
QWebSettings.clearMemoryCaches ()
```

将释放尽可能多的内存可以通过清理所有的内存高速缓存，如页面，对象和字体缓存。

此功能被引入Qt的4.6 。

```
QString QWebSettings.defaultTextEncoding (self)
```

返回默认文本编码。

此功能被引入Qt的4.6 。

**See also** [setDefaultTextEncoding](qwebsettings.html#setDefaultTextEncoding)（ ） 。

```
QWebSettings.enablePersistentStorage (QString path = QString())
```

启用WebKit的数据持久化，并设置为路径_path_。如果_path_是空的，由指定的用户特定数据的位置[DataLocation](qdesktopservices.html#StandardLocation-enum)将被代替使用。

此方法将同时设置并启用[iconDatabasePath](qwebsettings.html#iconDatabasePath)（ ）[localStoragePath](qwebsettings.html#localStoragePath)（ ）[offlineStoragePath](qwebsettings.html#offlineStoragePath)（）和[offlineWebApplicationCachePath](qwebsettings.html#offlineWebApplicationCachePath)（ ） 。

此功能被引入Qt的4.6 。

**See also** [localStoragePath](qwebsettings.html#localStoragePath)（ ） 。

```
QString QWebSettings.fontFamily (self, FontFamily which)
```

返回实际的字体系列指定通用字体家族，_which_。

**See also** [setFontFamily](qwebsettings.html#setFontFamily)（ ） 。

```
int QWebSettings.fontSize (self, FontSize type)
```

返回默认的字体大小_type_。

**See also** [setFontSize](qwebsettings.html#setFontSize)（ ） 。

```
QWebSettings QWebSettings.globalSettings ()
```

[

返回全局设置对象。

](qwebsettings.html)

[改变默认的对象的任何设置将自动应用于所有](qwebsettings.html)[QWebPage](qwebpage.html)倘或特定的设置尚未复盖。

```
QString QWebSettings.iconDatabasePath ()
```

如果返回的图标数据库被禁用的图标库或空字符串的路径。

**See also** [setIconDatabasePath](qwebsettings.html#setIconDatabasePath)（）和[clearIconDatabase](qwebsettings.html#clearIconDatabase)（ ） 。

```
QIcon QWebSettings.iconForUrl (QUrl url)
```

[

返回该网站的图标_url_。

](qicon.html)

[如果网站不指定图标**OR**如果图标是不是在数据库中，空](qicon.html)[QIcon](qicon.html)返回。

**Note:**返回图标的大小是任意的。

**See also** [setIconDatabasePath](qwebsettings.html#setIconDatabasePath)（ ） 。

```
QString QWebSettings.localStoragePath (self)
```

返回HTML5的本地存储路径。

此功能被引入Qt的4.6 。

**See also** [setLocalStoragePath](qwebsettings.html#setLocalStoragePath)（ ） 。

```
int QWebSettings.maximumPagesInCache ()
```

返回的网页被保存在内存中缓存的最大数量。

**See also** [setMaximumPagesInCache](qwebsettings.html#setMaximumPagesInCache)（ ） 。

```
int QWebSettings.offlineStorageDefaultQuota ()
```

返回默认配额为新的离线存储数据库中的值。

此功能被引入Qt的4.5 。

**See also** [setOfflineStorageDefaultQuota](qwebsettings.html#setOfflineStorageDefaultQuota)（ ） 。

```
QString QWebSettings.offlineStoragePath ()
```

返回的功能，如果禁用了HTML5的客户端数据库存储或空字符串的路径。

此功能被引入Qt的4.5 。

**See also** [setOfflineStoragePath](qwebsettings.html#setOfflineStoragePath)（ ） 。

```
QString QWebSettings.offlineWebApplicationCachePath ()
```

返回的功能，如果禁用了HTML5离线Web应用程序的缓存存储或空字符串的路径。

此功能被引入Qt的4.6 。

**See also** [setOfflineWebApplicationCachePath](qwebsettings.html#setOfflineWebApplicationCachePath)（ ） 。

```
int QWebSettings.offlineWebApplicationCacheQuota ()
```

返回配额的离线网络应用程序缓存的值。

此功能被引入Qt的4.6 。

**See also** [setOfflineWebApplicationCacheQuota](qwebsettings.html#setOfflineWebApplicationCacheQuota)（ ） 。

```
QWebSettings.resetAttribute (self, WebAttribute attr)
```

复位的设置_attribute_在全球指定的值[QWebSettings](qwebsettings.html)实例。

此功能对全球无影响[QWebSettings](qwebsettings.html)实例。

**See also** [globalSettings](qwebsettings.html#globalSettings)（ ） 。

```
QWebSettings.resetFontFamily (self, FontFamily which)
```

通过复位指定的实际字体系列_which_到所述一个全局设置[QWebSettings](qwebsettings.html)实例。

此功能对全球无影响[QWebSettings](qwebsettings.html)实例。

```
QWebSettings.resetFontSize (self, FontSize type)
```

复位时的字体大小_type_在指定的大小的全局设置对象。

此功能对全球无影响[QWebSettings](qwebsettings.html)实例。

```
QWebSettings.setAttribute (self, WebAttribute attr, bool on)
```

启用或禁用指定_attribute_功能取决于价值_on_。

```
QWebSettings.setDefaultTextEncoding (self, QString encoding)
```

指定默认的文字编码系统。

该_encoding_，必须描述的编码，如“ UTF-8”的字符串， “ISO-8859 -1”等，如果为空的默认值将被使用。对于更广泛的编码名称的列表，请参阅[QTextCodec](qtextcodec.html)

此功能被引入Qt的4.6 。

**See also** [defaultTextEncoding](qwebsettings.html#defaultTextEncoding)（ ） 。

```
QWebSettings.setFontFamily (self, FontFamily which, QString family)
```

将实际的字体家族_family_指定通用系列，_which_。

**See also** [fontFamily](qwebsettings.html#fontFamily)（ ） 。

```
QWebSettings.setFontSize (self, FontSize type, int size)
```

设置字体大小_type_至_size_。

**See also** [fontSize](qwebsettings.html#fontSize)（ ） 。

```
QWebSettings.setIconDatabasePath (QString location)
```

设置的图标数据库的路径_path_。图标数据库，用于存储与网站相关联的“收藏夹图标” 。

_path_必须指向现有的目录。

设置一个空的路径禁用图标库。

**See also** [iconDatabasePath](qwebsettings.html#iconDatabasePath)（）和[clearIconDatabase](qwebsettings.html#clearIconDatabase)（ ） 。

```
QWebSettings.setLocalStoragePath (self, QString path)
```

设置为HTML5的本地存储路径_path_。

有关HTML5的本地存储更多的信息，请参阅[Web Storage standard](http://www.w3.org/TR/webstorage/#the-localstorage-attribute)。

支持本地存储可以通过设置启用[LocalStorageEnabled](qwebsettings.html#WebAttribute-enum)属性。

此功能被引入Qt的4.6 。

**See also** [localStoragePath](qwebsettings.html#localStoragePath)（ ） 。

```
QWebSettings.setMaximumPagesInCache (int pages)
```

设置的最大页数，以保持在内存中页面缓存到_pages_。

页面缓存使得导航时提出，或返回到前进/后退历史记录页面，通过暂停和恢复到一个更好的用户体验_pages_。

有关该功能的更多信息，请参考：

http://webkit.org/blog/427/webkit-page-cache-i-the-basics/

**See also** [maximumPagesInCache](qwebsettings.html#maximumPagesInCache)（ ） 。

```
QWebSettings.setObjectCacheCapacities (int cacheMinDeadCapacity, int cacheMaxDead, int totalCapacity)
```

指定容量的死对象，如样式表或脚本的内存缓存。

该_cacheMinDeadCapacity_指定_minimum_字节死对象应该消耗在缓存处于压力下的人数。

_cacheMaxDead_是_maximum_字节数是死对象要消耗当缓存**not**下压力。

_totalCapacity_指定_maximum_该高速缓存应该消耗的字节数**overall**。

高速缓存是默认启用的。调用setObjectCacheCapacities （ 0 ， 0 ， 0 ）将禁用缓存。用一个非零调用它再次启用它。

```
QWebSettings.setOfflineStorageDefaultQuota (int maximumSize)
```

设置默认配额的价值，新的离线存储数据库_maximumSize_。

此功能被引入Qt的4.5 。

**See also** [offlineStorageDefaultQuota](qwebsettings.html#offlineStorageDefaultQuota)（ ） 。

```
QWebSettings.setOfflineStoragePath (QString path)
```

Sets _path_作为保存位置HTML5的客户端数据库存储数据。

_path_必须指向现有的目录。

设置一个空的路径禁用该功能。

支持客户端的数据库可以通过设置启用[OfflineStorageDatabaseEnabled](qwebsettings.html#WebAttribute-enum)属性。

此功能被引入Qt的4.5 。

**See also** [offlineStoragePath](qwebsettings.html#offlineStoragePath)（ ） 。

```
QWebSettings.setOfflineWebApplicationCachePath (QString path)
```

设置为HTML5离线Web应用程序的缓存存储的路径_path_。

一个应用程序的缓存就像在某些意义上的HTTP缓存。对于使用通过JavaScript的应用程序缓存文件，装载机发动机将首先要求的内容的应用程序缓存，接触网络之前。

http://dev.w3.org/html5/spec/Overview.html ＃ appcache ：该功能在细节处描述

_path_必须指向现有的目录。

设置一个空的路径禁用该功能。

支持离线Web应用程序的缓存存储可以通过设置启用[OfflineWebApplicationCacheEnabled](qwebsettings.html#WebAttribute-enum)属性。

此功能被引入Qt的4.6 。

**See also** [offlineWebApplicationCachePath](qwebsettings.html#offlineWebApplicationCachePath)（ ） 。

```
QWebSettings.setOfflineWebApplicationCacheQuota (int maximumSize)
```

设置配额的离线网络应用程序缓存的值_maximumSize_。

此功能被引入Qt的4.6 。

**See also** [offlineWebApplicationCacheQuota](qwebsettings.html#offlineWebApplicationCacheQuota)（ ） 。

```
QWebSettings.setUserStyleSheetUrl (self, QUrl location)
```

指定用户样式表的位置来加载与每个网页。

该_location_必须是在本地文件系统的路径，或使用UTF-8和Base64编码的数据，如数据的URL ：

“数据：文本/ CSS ;字符集= UTF -8;的base64 ， cCB7IGJhY2tncm91bmQtY29sb3I6IHJlZCB9Ow ==”

**Note:**如果base64的数据是无效的，该样式将不会被应用。

**See also** [userStyleSheetUrl](qwebsettings.html#userStyleSheetUrl)（ ） 。

```
QWebSettings.setWebGraphic (WebGraphic type, QPixmap graphic)
```

Sets _graphic_要绘制时[QtWebKit](index.htm)需要借鉴的给定的图像_type_。

例如，当图像不能被加载，像素映像指定由[MissingImageGraphic](qwebsettings.html#WebGraphic-enum)绘制代替。

**See also** [webGraphic](qwebsettings.html#webGraphic)（ ） 。

```
bool QWebSettings.testAttribute (self, WebAttribute attr)
```

返回True如果_attribute_被启用，否则返回False 。

```
QUrl QWebSettings.userStyleSheetUrl (self)
```

[

返回用户样式表的位置。

](qurl.html)

[**See also**](qurl.html) [setUserStyleSheetUrl](qwebsettings.html#setUserStyleSheetUrl)（ ） 。

```
QPixmap QWebSettings.webGraphic (WebGraphic type)
```

[

返回用来绘制指定的图形置换预先设定的像素图_type_。

](qpixmap.html)

[**See also**](qpixmap.html) [setWebGraphic](qwebsettings.html#setWebGraphic)（ ） 。