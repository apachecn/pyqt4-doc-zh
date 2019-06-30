# QAbstractNetworkCache Class Reference

## [[QtNetwork](index.htm) module]

该QAbstractNetworkCache类提供用于缓存实现的接口。[More...](#details)

继承[QObject](qobject.html)。

通过继承[QNetworkDiskCache](qnetworkdiskcache.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `int cacheSize (self)`
*   `clear (self)`
*   `QIODevice data (self, QUrl url)`
*   `insert (self, QIODevice device)`
*   `QNetworkCacheMetaData metaData (self, QUrl url)`
*   `QIODevice prepare (self, QNetworkCacheMetaData metaData)`
*   `bool remove (self, QUrl url)`
*   `updateMetaData (self, QNetworkCacheMetaData metaData)`

* * *

## Detailed Description

该QAbstractNetworkCache类提供用于缓存实现的接口。

QAbstractNetworkCache是为用于在每个标准缓存基类[QNetworkAccessManager](qnetworkaccessmanager.html)。 QAbstractNetworkCache是一个抽象类，不能被实例化。

* * *

## Method Documentation

```
QAbstractNetworkCache.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个抽象的网络高速缓存与给定_parent_。

```
int QAbstractNetworkCache.cacheSize (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回由缓存佔用的电流的大小。根据不同的缓存实现，这可能是磁盘或内存的大小。

在基类中，这是一个纯虚函数。

**See also** [clear](qabstractnetworkcache.html#clear)（ ） 。

```
QAbstractNetworkCache.clear (self)
```

这种方法也是一个Qt槽与C + +的签名`void clear()`。

这种方法是抽象的，应在任何子类中重新实现。

删除所有项目从缓存。除非有故障清除缓存[cacheSize](qabstractnetworkcache.html#cacheSize)（）应该调用清除后返回0 。

在基类中，这是一个纯虚函数。

**See also** [cacheSize](qabstractnetworkcache.html#cacheSize)（）和[remove](qabstractnetworkcache.html#remove)（ ） 。

```
QIODevice QAbstractNetworkCache.data (self, QUrl url)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回具有相关联的数据_url_。

](qiodevice.html)

[它是由请求该数据的应用程序，删除](qiodevice.html)[QIODevice](qiodevice.html)当用它做。

如果没有高速缓存_url_，该URL是无效的，或者如果有一个内部缓存错误则返回0 。

在基类中，这是一个纯虚函数。

**See also** [metaData](qabstractnetworkcache.html#metaData)（）和[prepare](qabstractnetworkcache.html#prepare)（ ） 。

```
QAbstractNetworkCache.insert (self, QIODevice device)
```

这种方法是抽象的，应在任何子类中重新实现。

插入在数据_device_和制备的元数据到高速缓存中。之后调用此函数使用的数据和元数据应该是检索[data](qabstractnetworkcache.html#data)（）和[metaData](qabstractnetworkcache.html#metaData)（ ） 。

要取消一个准备插入的呼叫[remove](qabstractnetworkcache.html#remove)（ ）对元数据的URL 。

在基类中，这是一个纯虚函数。

**See also** [prepare](qabstractnetworkcache.html#prepare)（）和[remove](qabstractnetworkcache.html#remove)（ ） 。

```
QNetworkCacheMetaData QAbstractNetworkCache.metaData (self, QUrl url)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回的元数据的URL_url_。

](qnetworkcachemetadata.html)

[如果url是有效的，缓存包含数据的url，有效](qnetworkcachemetadata.html)[QNetworkCacheMetaData](qnetworkcachemetadata.html)返回。

在基类中，这是一个纯虚函数。

**See also** [updateMetaData](qabstractnetworkcache.html#updateMetaData)（）和[data](qabstractnetworkcache.html#data)（ ） 。

```
QIODevice QAbstractNetworkCache.prepare (self, QNetworkCacheMetaData metaData)
```

[

这种方法是抽象的，应在任何子类中重新实现。

](qiodevice.html)

[返回一个应填入的数据缓存项设备_metaData_。当所有的数据已经被写入](qiodevice.html)[insert](qabstractnetworkcache.html#insert)（ ）被调用。如果元数据是无效的或URL中的元数据是无效的，则返回0 。

高速缓存拥有该设备，并将采取删除它被插入或拔出时的照顾。

要取消一个准备插入的呼叫[remove](qabstractnetworkcache.html#remove)（ ）对元数据的URL 。

在基类中，这是一个纯虚函数。

**See also** [remove](qabstractnetworkcache.html#remove)（ ）[updateMetaData](qabstractnetworkcache.html#updateMetaData)（）和[insert](qabstractnetworkcache.html#insert)（ ） 。

```
bool QAbstractNetworkCache.remove (self, QUrl url)
```

这种方法是抽象的，应在任何子类中重新实现。

删除缓存项_url_，返回True，如果成功，否则为False 。

在基类中，这是一个纯虚函数。

**See also** [clear](qabstractnetworkcache.html#clear)（）和[prepare](qabstractnetworkcache.html#prepare)（ ） 。

```
QAbstractNetworkCache.updateMetaData (self, QNetworkCacheMetaData metaData)
```

这种方法是抽象的，应在任何子类中重新实现。

更新缓存荟萃日期为元数据的URL来_metaData_

如果缓存中不包含一个缓存项的URL ，然后不采取任何行动。

在基类中，这是一个纯虚函数。

**See also** [metaData](qabstractnetworkcache.html#metaData)（）和[prepare](qabstractnetworkcache.html#prepare)（ ） 。