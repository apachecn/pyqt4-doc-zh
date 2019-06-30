# QWebHistoryItem Class Reference

## [[QtWebKit](index.htm) module]

该QWebHistoryItem类代表了一个历史上一个项目[QWebPage](qwebpage.html) [More...](#details)

### Methods

*   `__init__ (self, QWebHistoryItem other)`
*   `QIcon icon (self)`
*   `bool isValid (self)`
*   `QDateTime lastVisited (self)`
*   `QUrl originalUrl (self)`
*   `setUserData (self, QVariant userData)`
*   `QString title (self)`
*   `QUrl url (self)`
*   `QVariant userData (self)`

* * *

## Detailed Description

该QWebHistoryItem类代表了一个历史上一个项目[QWebPage](qwebpage.html)

每个QWebHistoryItem实例代表一个网页的历史堆栈中删除条目，包含关于页面的信息，它的位置，并且当它是最后一次访问。

下面的表显示了由历史资料保持的页的属性，和所用的函数来访问它们。

| Function | Description |
| --- | --- |
| [title](qwebhistoryitem.html#title)() | The page title. |
| [url](qwebhistoryitem.html#url)() | The location of the page. |
| [originalUrl](qwebhistoryitem.html#originalUrl)() | The URL used to access the page. |
| [lastVisited](qwebhistoryitem.html#lastVisited)() | The date and time of the user's last visit to the page. |
| [icon](qwebhistoryitem.html#icon)() | The icon associated with the page that was provided by the server. |
| [userData](qwebhistoryitem.html#userData)() | The user specific data that was stored with the history item. |

**Note:**QWebHistoryItem对象是基础值，但_explicitly shared_。通过调用更改QWebHistoryItem实例[setUserData](qwebhistoryitem.html#setUserData)（ ）将改变该实例的所有副本。

* * *

## Method Documentation

```
QWebHistoryItem.__init__ (self, QWebHistoryItem other)
```

从构造一个历史项_other_。新的项目，_other_将分享他们的数据，并修改任何资料或_other_将修改两个实例。

```
QIcon QWebHistoryItem.icon (self)
```

[

返回与历史记录项关联的图标。

](qicon.html)

[**See also**](qicon.html) [title](qwebhistoryitem.html#title)（ ）[url](qwebhistoryitem.html#url)（）和[lastVisited](qwebhistoryitem.html#lastVisited)（ ） 。

```
bool QWebHistoryItem.isValid (self)
```

返回这是否是一个有效的历史记录项。

此功能被引入Qt的4.5 。

```
QDateTime QWebHistoryItem.lastVisited (self)
```

[

返回的日期和时间与该项目相关的页面是最后一次访问。

](qdatetime.html)

[**See also**](qdatetime.html) [title](qwebhistoryitem.html#title)（ ）[icon](qwebhistoryitem.html#icon)（）和[url](qwebhistoryitem.html#url)（ ） 。

```
QUrl QWebHistoryItem.originalUrl (self)
```

[

返回与历史项目相关的原始URL 。

](qurl.html)

[**See also**](qurl.html) [url](qwebhistoryitem.html#url)（ ） 。

```
QWebHistoryItem.setUserData (self, QVariant userData)
```

存储用户特定的数据_userData_与历史项目。

**Note:**这个项目的所有副本将被修改。

此功能被引入Qt的4.5 。

**See also** [userData](qwebhistoryitem.html#userData)（ ） 。

```
QString QWebHistoryItem.title (self)
```

返回与历史项目相关的页面的标题。

**See also** [icon](qwebhistoryitem.html#icon)（ ）[url](qwebhistoryitem.html#url)（）和[lastVisited](qwebhistoryitem.html#lastVisited)（ ） 。

```
QUrl QWebHistoryItem.url (self)
```

[

返回与历史项目关联的URL 。

](qurl.html)

[**See also**](qurl.html) [originalUrl](qwebhistoryitem.html#originalUrl)（ ）[title](qwebhistoryitem.html#title)（）和[lastVisited](qwebhistoryitem.html#lastVisited)（ ） 。

```
QVariant QWebHistoryItem.userData (self)
```

返回存储与历史项目的用户特定数据。

此功能被引入Qt的4.5 。

**See also** [setUserData](qwebhistoryitem.html#setUserData)（ ） 。