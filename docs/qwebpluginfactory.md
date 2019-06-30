# QWebPluginFactory Class Reference

## [[QtWebKit](index.htm) module]

该QWebPluginFactory类用于嵌入在网页中自定义数据类型。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum Extension { }`
*   `class **[ExtensionOption](index.htm)**`
*   `class **[ExtensionReturn](index.htm)**`
*   `class **[MimeType](index.htm)**`
*   `class **[Plugin](index.htm)**`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `QObject create (self, QString mimeType, QUrl url, QStringList argumentNames, QStringList argumentValues)`
*   `bool extension (self, Extension extension, ExtensionOption option = None, ExtensionReturn output = None)`
*   `list-of-QWebPluginFactory.Plugin plugins (self)`
*   `refreshPlugins (self)`
*   `bool supportsExtension (self, Extension extension)`

* * *

## Detailed Description

该QWebPluginFactory类用于嵌入在网页中自定义数据类型。

在HTML`&lt;object&gt;`标籤被用来嵌入任意内容到网页中，例如：

```
 <object type="application/x-pdf" data="http://qt.nokia.com/document.pdf" width="500" height="400"></object>

```

QtWebKit的将本地处理像最基本的数据类型`text/html`和`image/jpeg`，但对于任何先进的或自定义的数据类型，你需要给自己提供一个处理程序。

QWebPluginFactory是一个工厂，用于创建插件[QWebPage](qwebpage.html)，其中每个插件提供对一个或多个数据类型的支持。一个插件工厂可以在安装[QWebPage](qwebpage.html) using [QWebPage.setPluginFactory](qwebpage.html#setPluginFactory)（ ） 。

**Note:**如果插件是通过启用该插件工厂仅用于[QWebSettings](qwebsettings.html)。

你通过实施提供QWebPluginFactory的[plugins](qwebpluginfactory.html#plugins)（ ）和[create](qwebpluginfactory.html#create)（）方法。为[plugins](qwebpluginfactory.html#plugins)（ ）有必要说明的插件工厂可以创建，包括描述和支持的MIME类型。该MIME类型的每个插件可以处理应与在HTML中指定的那些`&lt;object&gt;`标记您的内容。

该[create](qwebpluginfactory.html#create)（）方法，如果支持所请求的MIME类型调用。该实现必须返回请求给定MIME类型和指定的URL插件的新实例。

该插件本身的子类[QObject](qobject.html)，但目前仅插件的基础上无论是[QWidget](qwidget.html) or [QGraphicsWidget](qgraphicswidget.html)被支持。

* * *

## Type Documentation

```
QWebPluginFactory.Extension
```

* * *

## Method Documentation

```
QWebPluginFactory.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QWebPluginFactory](qwebpluginfactory.html)与父_parent_。

```
QObject QWebPluginFactory.create (self, QString mimeType, QUrl url, QStringList argumentNames, QStringList argumentValues)
```

[

这种方法是抽象的，应在任何子类中重新实现。

](qobject.html)

[在子类中实现，以创建一个新的插件，可以显示给定MIME类型的内容_mimeType_。在被提供的内容的URL_url_。返回的对象应该是一个](qobject.html)[QWidget](qwidget.html)。

HTML object元素可以通过提供参数`&lt;param&gt;`标记。这些变量的名称和值的属性被指定_argumentNames_和_argumentValues_字符串列表。

例如：

```
 <object type="application/x-pdf" data="http://qt.nokia.com/document.pdf" width="500" height="400">
     <param name="showTableOfContents" value="true" />
     <param name="hideThumbnails" value="false" />
 </object>

```

上述对象元素将导致调用来创建（ ）使用以下参数：

| Parameter | Value |
| --- | --- |
| mimeType | "application/x-pdf" |
| url | "http://qt.nokia.com/document.pdf" |
| argumentNames | "showTableOfContents" "hideThumbnails" |
| argumentVaues | "true" "false" |

**Note:**返回的对象的所有权将转移给调用者。

```
bool QWebPluginFactory.extension (self, Extension extension, ExtensionOption option = None, ExtensionReturn output = None)
```

```
list-of-QWebPluginFactory.Plugin QWebPluginFactory.plugins (self)
```

这种方法是抽象的，应在任何子类中重新实现。

这个函数重新实现在子类中返回支持的插件工厂可以创建一个列表。

**Note:**目前，此功能只调用时JavaScript程序访问全局`plugins` or `mimetypes`对象。

```
QWebPluginFactory.refreshPlugins (self)
```

这个函数被调用以刷新支持的插件列表中。后一个新的插件已经安装在系统中可能被调用。

```
bool QWebPluginFactory.supportsExtension (self, Extension extension)
```