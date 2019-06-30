# QWebSecurityOrigin Class Reference

## [[QtWebKit](index.htm) module]

该QWebSecurityOrigin类定义了网站安全边界。[More...](#details)

### Methods

*   `__init__ (self, QWebSecurityOrigin other)`
*   `int databaseQuota (self)`
*   `list-of-QWebDatabase databases (self)`
*   `int databaseUsage (self)`
*   `QString host (self)`
*   `int port (self)`
*   `QString scheme (self)`
*   `setApplicationCacheQuota (self, int quota)`
*   `setDatabaseQuota (self, int quota)`

### Static Methods

*   `addLocalScheme (QString scheme)`
*   `list-of-QWebSecurityOrigin allOrigins ()`
*   `QStringList localSchemes ()`
*   `removeLocalScheme (QString scheme)`

* * *

## Detailed Description

该QWebSecurityOrigin类定义了网站安全边界。

QWebSecurityOrigin提供访问由网站定义的安全域。原点由一个主机名，一个方案，一个端口号。 Web站点具有相同的安全性起源可以访问对方的资源，客户端脚本或数据库。

例如在网站上`http://www.example.com/my/page.html`允许共享同一个数据库`http://www.example.com/my/overview.html`或访问对方的文件， HTML框架集和JavaScript的使用时。在同一时间它可以防止`http://www.malicious.com/evil.html`访问`http://www.example.com/`的资源，因为它们是不同的安全来源。

由像默认的本地计划`file://`和`qrc://`被concidered是在相同的安全性起源，并且可以访问对方的资源。您可以通过使用添加额外的本地计划[QWebSecurityOrigin.addLocalScheme](qwebsecurityorigin.html#addLocalScheme)（ ） ，或复盖通过设置默认的相同来源的行为[QWebSettings.LocalContentCanAccessFileUrls](qwebsettings.html#WebAttribute-enum)至`false`。

**Note:**本地资源默认情况下访问远程内容的限制，这意味着你的`file://`将不能够访问`http://domain.com/foo.html`。您可以通过设置放宽这个限制[QWebSettings.LocalContentCanAccessRemoteUrls](qwebsettings.html#WebAttribute-enum)至`true`。

Call [QWebFrame.securityOrigin](qwebframe.html#securityOrigin)（ ）来获取QWebSecurityOrigin在网页中的框架，并使用[host](qwebsecurityorigin.html#host)（ ）[scheme](qwebsecurityorigin.html#scheme)（）和[port](qwebsecurityorigin.html#port)（ ）来识别安全原点。

使用[databases](qwebsecurityorigin.html#databases)（）来访问一个安全原点内定义的数据库。原点的数据库的磁盘使用情况可以被限制[setDatabaseQuota](qwebsecurityorigin.html#setDatabaseQuota)（ ） 。[databaseQuota](qwebsecurityorigin.html#databaseQuota)（）和[databaseUsage](qwebsecurityorigin.html#databaseUsage)（ ）报告该电流限制，以及在当前的使用情况。

欲了解更多信息，请参阅["Same origin policy" Wikipedia Article](http://en.wikipedia.org/wiki/Same_origin_policy)。

* * *

## Method Documentation

```
QWebSecurityOrigin.__init__ (self, QWebSecurityOrigin other)
```

构造一个安全的来历_other_。

```
QWebSecurityOrigin.addLocalScheme (QString scheme)
```

将给定_scheme_到计划被认为等同于清单`file`：计划。

跨域限制取决于两个网络设置[QWebSettings.LocalContentCanAccessFileUrls](qwebsettings.html#WebAttribute-enum)和[QWebSettings.LocalContentCanAccessFileUrls](qwebsettings.html#WebAttribute-enum)。默认情况下，所有的本地计划是concidered是在相同的安全血统，和当地的计划不能访问远程内容。

此功能被引入Qt的4.6 。

```
list-of-QWebSecurityOrigin QWebSecurityOrigin.allOrigins ()
```

将返回所有安全起源与定义的数据库配额的列表。

```
int QWebSecurityOrigin.databaseQuota (self)
```

返回配额在安全原点的数据库。

**See also** [setDatabaseQuota](qwebsecurityorigin.html#setDatabaseQuota)（ ） 。

```
list-of-QWebDatabase QWebSecurityOrigin.databases (self)
```

返回安全原点定义的所有数据库的列表。

```
int QWebSecurityOrigin.databaseUsage (self)
```

返回字节的所有数据库在磁盘上的安全使用原产地的数量。

```
QString QWebSecurityOrigin.host (self)
```

返回的主机名定义安全原点。

```
QStringList QWebSecurityOrigin.localSchemes ()
```

返回所有concidered是本地的方案的列表。

默认情况下，这是`file://`和`qrc://`。

此功能被引入Qt的4.6 。

**See also** [addLocalScheme](qwebsecurityorigin.html#addLocalScheme)（）和[removeLocalScheme](qwebsecurityorigin.html#removeLocalScheme)（ ） 。

```
int QWebSecurityOrigin.port (self)
```

返回定义的安全性起源的端口号。

```
QWebSecurityOrigin.removeLocalScheme (QString scheme)
```

删除给定的_scheme_从本地方案的列表。

**Note:**你不能删除`file://`计划从本地方案的列表。

此功能被引入Qt的4.6 。

**See also** [addLocalScheme](qwebsecurityorigin.html#addLocalScheme)（ ） 。

```
QString QWebSecurityOrigin.scheme (self)
```

返回该计划定义的安全性起源。

```
QWebSecurityOrigin.setApplicationCacheQuota (self, int quota)
```

```
QWebSecurityOrigin.setDatabaseQuota (self, int quota)
```

设置配额在安全原点到数据库_quota_字节。

如果配额设定为一个值小于当前使用情况，配额将维持，没有数据将被清除，以满足新的配额。然而，没有新的数据可被添加到该原点的数据库。

**See also** [databaseQuota](qwebsecurityorigin.html#databaseQuota)（ ） 。