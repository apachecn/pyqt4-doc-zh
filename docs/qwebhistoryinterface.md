# QWebHistoryInterface Class Reference

## [[QtWebKit](index.htm) module]

该QWebHistoryInterface类提供了实现链路史上的一个接口。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `addHistoryEntry (self, QString url)`
*   `bool historyContains (self, QString url)`

### Static Methods

*   `QWebHistoryInterface defaultInterface ()`
*   `setDefaultInterface (QWebHistoryInterface defaultInterface)`

* * *

## Detailed Description

该QWebHistoryInterface类提供了实现链路史上的一个接口。

该QWebHistoryInterface是可以用来跟踪访问链接的接口。它包含了由WebKit引擎叫了两个纯虚方法：[addHistoryEntry](qwebhistoryinterface.html#addHistoryEntry)（）是用来添加已访问过的URL的界面，而[historyContains](qwebhistoryinterface.html#historyContains)（）用于查询给定的URL是否已经访问过的用户。默认情况下， QWebHistoryInterface没有设置，所以WebKit的不跟踪访问过的链接的。

**Note:**通过QWebHistoryInterface跟踪历史是不特定的实例[QWebPage](qwebpage.html)而是适用于所有页面。

* * *

## Method Documentation

```
QWebHistoryInterface.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的[QWebHistoryInterface](qwebhistoryinterface.html)与父_parent_。

```
QWebHistoryInterface.addHistoryEntry (self, QString url)
```

这种方法是抽象的，应在任何子类中重新实现。

通过所谓的WebKit增加另一个_url_要访问的页面的列表。

```
QWebHistoryInterface QWebHistoryInterface.defaultInterface ()
```

[

返回将使用的WebKit的默认界面。如果没有默认的界面已定， WebKit的不会让访问过的链接的跟踪和一个空指针将被返回。

](qwebhistoryinterface.html)

[**See also**](qwebhistoryinterface.html) [setDefaultInterface](qwebhistoryinterface.html#setDefaultInterface)（ ） 。

```
bool QWebHistoryInterface.historyContains (self, QString url)
```

这种方法是抽象的，应在任何子类中重新实现。

由WebKit引擎打电话来查询是否有一定_url_已访问的用户了。返回True如果_url_是访问过的链接的历史的一部分，否则返回False 。

```
QWebHistoryInterface.setDefaultInterface (QWebHistoryInterface defaultInterface)
```

设置新的默认界面，_defaultInterface_，将被所有的WebKit来跟踪访问过的链接的。

如果没有父的接口已经被设置，旧的接口将被删除。当存在该应用程序[QWebHistoryInterface](qwebhistoryinterface.html)会自动删除_defaultInterface_如果它不具有父。

**See also** [defaultInterface](qwebhistoryinterface.html#defaultInterface)（ ） 。