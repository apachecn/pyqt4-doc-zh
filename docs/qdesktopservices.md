# QDesktopServices Class Reference

## [[QtGui](index.htm) module]

该QDesktopServices类提供了访问常用的桌面服务的方法。[More...](#details)

### Types

*   `enum StandardLocation { DesktopLocation, DocumentsLocation, FontsLocation, ApplicationsLocation, ..., CacheLocation }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDesktopServices)`

### Static Methods

*   `QString displayName (StandardLocation type)`
*   `bool openUrl (QUrl url)`
*   `setUrlHandler (QString scheme, QObject receiver, str method)`
*   `setUrlHandler (QString scheme, callable method)`
*   `QString storageLocation (StandardLocation type)`
*   `unsetUrlHandler (QString scheme)`

* * *

## Detailed Description

该QDesktopServices类提供了访问常用的桌面服务的方法。

许多桌面环境提供了可以被应用程序用于执行常见任务，如打开一个网页，在某种程度上，既一致，并考虑到了用户的应用程序首选项的服务。

这个类包含的功能，提供简单的界面使用这些服务，表明他们是成功还是失败。

该[openUrl](qdesktopservices.html#openUrl)（ ）函数用于打开位于在外部应用程序中的任意文件的URL 。对于对应的资源在本地的文件系统（其中的URL方案“文件” ）上的URL ，一个合适的应用程序将被用来打开文件，否则， Web浏览器将被用来获取和显示文件。

用户的桌面设置控制某些类型的可执行文件是否被打开进行浏览，或者如果他们转而执行。一些桌面环境配置为防止执行来自非本地URL获得文件的用户，或者要求用户的权限才这样做。

### URL Handlers

的行为[openUrl](qdesktopservices.html#openUrl)（ ）函数可以定制个人的URL方案，允许应用程序复盖默认的处理行为对于某些类型的URL 。

调度机制允许将用于每个URL方案只有一个自定义处理程序，这是使用设置[setUrlHandler](qdesktopservices.html#setUrlHandler)（）函数。每个处理程序被实现为只接受一个单一的插槽[QUrl](qurl.html)的说法。

每个计划的现有处理程序可以与被删除[unsetUrlHandler](qdesktopservices.html#unsetUrlHandler)（）函数。这将返回给定的方案的默认行为的处理行为。

这个系统可以很容易地实现一个帮助系统，例如。说明可以使用标籤和文本浏览器提供**help://myapplication/mytopic**网址，并通过注册一个处理程序就能够在应用程序中显示的说明文字：

```
 class MyHelpHandler : public [QObject](qobject.html)
 {
     Q_OBJECT
 public:
     ...
 public slots:
     void showHelp(const [QUrl](qurl.html) &url);
 };

 QDesktopServices.setUrlHandler("help", helpInstance, "showHelp");

```

如果处理程序中你决定，你无法打开请求的URL ，你可以直接调用[QDesktopServices.openUrl](qdesktopservices.html#openUrl)（ ）再次使用相同的参数，它会尝试使用适当的机制，使用户的桌面环境打开URL 。

* * *

## Type Documentation

```
QDesktopServices.StandardLocation
```

该枚举描述可由QDesktopServices.storageLocation和QDesktopServices.displayName要查询的不同的位置。

| Constant | Value | Description |
| --- | --- | --- |
| `QDesktopServices.DesktopLocation` | `0` | 返回用户的桌面目录。 |
| `QDesktopServices.DocumentsLocation` | `1` | 返回用户的文档。 |
| `QDesktopServices.FontsLocation` | `2` | 返回用户的字体。 |
| `QDesktopServices.ApplicationsLocation` | `3` | 返回用户的应用程序。 |
| `QDesktopServices.MusicLocation` | `4` | 返回用户的音乐。 |
| `QDesktopServices.MoviesLocation` | `5` | 返回用户的电影。 |
| `QDesktopServices.PicturesLocation` | `6` | 返回用户的图片。 |
| `QDesktopServices.TempLocation` | `7` | 返回系统的临时目录。 |
| `QDesktopServices.HomeLocation` | `8` | 返回用户的主目录。 |
| `QDesktopServices.DataLocation` | `9` | 返回在持久应用程序数据可以被存储的目录位置。[QCoreApplication.applicationName](qcoreapplication.html#applicationName-prop)和[QCoreApplication.organizationName](qcoreapplication.html#organizationName-prop)应该在所有平台上。 |
| `QDesktopServices.CacheLocation` | `10` | 返回在用户特定的非必要（缓存）的数据应该写入的目录位置。 |

这个枚举被引入或修改的Qt 4.4 。

**See also** [storageLocation](qdesktopservices.html#storageLocation)（）和[displayName](qdesktopservices.html#displayName)（ ） 。

* * *

## Method Documentation

```
QDesktopServices.__init__ (self)
```

```
QDesktopServices.__init__ (self, QDesktopServices)
```

```
QString QDesktopServices.displayName (StandardLocation type)
```

返回给定位置的本地化显示名称_type_或空[QString](qstring.html)如果没有相关的位置可以找到。

```
bool QDesktopServices.openUrl (QUrl url)
```

打开给定的_url_在真实的，如果成功了适当的Web浏览器为用户的桌面环境，并返回，否则返回False 。

如果URL是参考到本地文件（例如， URL模式是“文件” ），然后将它开了一个合适的应用程序，而不是一个Web浏览器。

下面的示例打开一个文件驻留在包含空格的路径上的Windows文件系统：

```
 [QDesktopServices](qdesktopservices.html).openUrl([QUrl](qurl.html)("file:///C:/Documents and Settings/All Users/Desktop", [QUrl](qurl.html).TolerantMode));

```

如果`mailto`被指定的URL ，用户的电子邮件客户端将用于打开包含在URL中，类似的方式指定的选项作曲家窗口`mailto`该书是由Web浏览器处理。

例如，下面的URL包含收件人（`user@foo.com`） ，一个主体（`Test`）和消息体（`Just a test`） ：

```
 mailto:user@foo.com?subject=Test&body=Just a test

```

**Warning:**虽然许多电子邮件客户端可以发送附件和识别Unicode ，用户可能没有这些功能配置他们的客户。此外，某些电子邮件客户端（如Lotus Notes）的有问题，长的URL。

**Note:**基于Symbian操作系统，`SwEvent`能力是必需的打开给定_url_如果Web浏览器已经在运行。

**See also** [setUrlHandler](qdesktopservices.html#setUrlHandler)（ ） 。

```
QDesktopServices.setUrlHandler (QString scheme, QObject receiver, str method)
```

设置处理程序给定的_scheme_成为该处理程序_method_通过提供_receiver_对象。

此功能提供了一种方法来定制行为[openUrl](qdesktopservices.html#openUrl)（ ） 。如果[openUrl](qdesktopservices.html#openUrl)（ ）被调用与指定的URL_scheme_那么给定的_method_在_receiver_对象被调用，而不是[QDesktopServices](qdesktopservices.html)启动外部应用程序。

所提供的方法必须被实现为一个时隙只接受单一[QUrl](qurl.html)的说法。

如果setUrlHandler （ ）用来设置上已经有一个处理一个方案一个新的处理程序，现有的处理程序简单地替换成新的。自[QDesktopServices](qdesktopservices.html)不采取处理程序的所有权，当一个处理器被替换任何对象都将被删除。

请注意，处理程序将总是从调用同一个线程中调用[QDesktopServices.openUrl](qdesktopservices.html#openUrl)（ ） 。

**See also** [openUrl](qdesktopservices.html#openUrl)（）和[unsetUrlHandler](qdesktopservices.html#unsetUrlHandler)（ ） 。

```
QDesktopServices.setUrlHandler (QString scheme, callable method)
```

```
QString QDesktopServices.storageLocation (StandardLocation type)
```

返回默认的系统目录下的文件_type_属于，或空字符串，如果该位置不能确定。

**Note:**返回的存储位置可以是不存在的目录，也就是说，它可能需要由系统或用户创建的。

**Note:**基于Symbian操作系统，[ApplicationsLocation](qdesktopservices.html#StandardLocation-enum)总是相同的驱动器上的可执行文件指向的/ sys / bin文件夹中。[FontsLocation](qdesktopservices.html#StandardLocation-enum)总是指向ROM驱动器上的文件夹中。 Symbian操作系统没有桌面的概念，[DesktopLocation](qdesktopservices.html#StandardLocation-enum)返回相同的路径[DocumentsLocation](qdesktopservices.html#StandardLocation-enum)。的标准位置休息指向同一个驱动器上的文件夹具有可执行，但如果可执行文件是在ROM中从C盘的文件夹被返回。

此功能被引入Qt的4.4 。

```
QDesktopServices.unsetUrlHandler (QString scheme)
```

移除先前设置的URL处理程序规定_scheme_。

**See also** [setUrlHandler](qdesktopservices.html#setUrlHandler)（ ） 。