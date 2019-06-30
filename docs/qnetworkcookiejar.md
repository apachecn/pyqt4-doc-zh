# QNetworkCookieJar Class Reference

## [[QtNetwork](index.htm) module]

该QNetworkCookieJar类实现的一个简单的罐子[QNetworkCookie](qnetworkcookie.html)对象[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `list-of-QNetworkCookie allCookies (self)`
*   `list-of-QNetworkCookie cookiesForUrl (self, QUrl url)`
*   `setAllCookies (self, list-of-QNetworkCookie cookieList)`
*   `bool setCookiesFromUrl (self, list-of-QNetworkCookie cookieList, QUrl url)`

* * *

## Detailed Description

该QNetworkCookieJar类实现的一个简单的罐子[QNetworkCookie](qnetworkcookie.html)对象

Cookies是少量的信息，像HTTP中使用无状态的协议，以保持在要求的一些持久信息。

一个cookie是由远程服务器设置，当它回复到一个请求，它预计在相同的cookie被发送回来的时候再发送请求。

饼干罐是保存在以前的请求设置的所有Cookie对象。 Web浏览器保存他们的饼干罐到磁盘，以便在应用程序的调用保存永久的cookie 。

QNetworkCookieJar没有实现永久存储：它不仅保持了饼干在内存中。一旦QNetworkCookieJar对象被删除时，其所持有的所有cookie将被丢弃，以及。如果你想保存的cookies，您应该从这个类并实现其保存到磁盘到自己的存储格式。

这个类只实现推荐的cookie规范的基本安全和不执行任何Cookie接受策略（它接受任何请求设置的所有Cookie ） 。为了复盖这些规则，你应该重新实现[cookiesForUrl](qnetworkcookiejar.html#cookiesForUrl)（）和[setCookiesFromUrl](qnetworkcookiejar.html#setCookiesFromUrl)（ ）虚函数。它们被称为[QNetworkReply](qnetworkreply.html)和[QNetworkAccessManager](qnetworkaccessmanager.html)当他们发现新的cookies ，当他们需要cookie 。

* * *

## Method Documentation

```
QNetworkCookieJar.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建[QNetworkCookieJar](qnetworkcookiejar.html)对象，并将成为父对象_parent_。

饼干罐被初始化为空。

```
list-of-QNetworkCookie QNetworkCookieJar.allCookies (self)
```

返回存储在这个饼干罐的所有Cookie。此功能适用于派生类对cookie保存到磁盘，以及实施cookie的过期和其他政策。

**See also** [setAllCookies](qnetworkcookiejar.html#setAllCookies)（）和[cookiesForUrl](qnetworkcookiejar.html#cookiesForUrl)（ ） 。

```
list-of-QNetworkCookie QNetworkCookieJar.cookiesForUrl (self, QUrl url)
```

返回的cookie被添加到当一个请求被发送到_url_。调用此函数由默认[QNetworkAccessManager.createRequest](qnetworkaccessmanager.html#createRequest)（ ） ，它增加了这个功能来发送请求返回的Cookie 。

如果找到多个cookie名称相同，但具有不同的路径，一个较长的路径是一个更短的路径之前返回。换句话说，该函数返回的cookie排序按递减的路径长度。

默认[QNetworkCookieJar](qnetworkcookiejar.html)类只实现一个非常基本的安全策略（它确保了饼干'域和路径匹配答复的） 。为加强与自己的算法的安全策略，复盖cookiesForUrl （ ） 。

**See also** [setCookiesFromUrl](qnetworkcookiejar.html#setCookiesFromUrl)（）和[QNetworkAccessManager.setCookieJar](qnetworkaccessmanager.html#setCookieJar)（ ） 。

```
QNetworkCookieJar.setAllCookies (self, list-of-QNetworkCookie cookieList)
```

设置由这个饼干罐认为是Cookie的内部列表_cookieList_。此功能适用于派生类通过重新实现来实现从永久存储，或者自己接受cookie政策加载饼干[setCookiesFromUrl](qnetworkcookiejar.html#setCookiesFromUrl)（ ） 。

**See also** [allCookies](qnetworkcookiejar.html#allCookies)（）和[setCookiesFromUrl](qnetworkcookiejar.html#setCookiesFromUrl)（ ） 。

```
bool QNetworkCookieJar.setCookiesFromUrl (self, list-of-QNetworkCookie cookieList, QUrl url)
```

添加饼干列表_cookieList_这个饼干罐。对于路径和域的默认值是从拍摄_url_对象。

返回True如果一个或多个cookie被设置为_url_，否则为False 。

如果一个cookie已经存在于饼干罐，它会被那些在被复盖_cookieList_。

默认[QNetworkCookieJar](qnetworkcookiejar.html)类只实现一个非常基本的安全策略（它确保了饼干'域和路径匹配答复的） 。为加强与自己的算法的安全策略，复盖setCookiesFromUrl （ ） 。

另外，[QNetworkCookieJar](qnetworkcookiejar.html)不会有一个最大的饼干桶的大小。重新实现这个函数会丢弃较早的cookie创建为新的空间。

**See also** [cookiesForUrl](qnetworkcookiejar.html#cookiesForUrl)（）和[QNetworkAccessManager.setCookieJar](qnetworkaccessmanager.html#setCookieJar)（ ） 。