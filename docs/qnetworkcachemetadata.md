# QNetworkCacheMetaData Class Reference

## [[QtNetwork](index.htm) module]

该QNetworkCacheMetaData类提供缓存信息。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QNetworkCacheMetaData other)`
*   `dict-of-QNetworkRequest.Attribute-QVariant attributes (self)`
*   `QDateTime expirationDate (self)`
*   `bool isValid (self)`
*   `QDateTime lastModified (self)`
*   `list-of-tuple-of-QByteArray-QByteArray rawHeaders (self)`
*   `bool saveToDisk (self)`
*   `setAttributes (self, dict-of-QNetworkRequest.Attribute-QVariant attributes)`
*   `setExpirationDate (self, QDateTime dateTime)`
*   `setLastModified (self, QDateTime dateTime)`
*   `setRawHeaders (self, list-of-tuple-of-QByteArray-QByteArray headers)`
*   `setSaveToDisk (self, bool allow)`
*   `setUrl (self, QUrl url)`
*   `QUrl url (self)`

### Special Methods

*   `bool __eq__ (self, QNetworkCacheMetaData other)`
*   `bool __ne__ (self, QNetworkCacheMetaData other)`

* * *

## Detailed Description

该QNetworkCacheMetaData类提供缓存信息。

QNetworkCacheMetaData提供了有关一个缓存文件，包括URL信息，当它是最后一次修改，创建缓存文件时，头文件，如果文件应该被保存到磁盘上。

* * *

## Method Documentation

```
QNetworkCacheMetaData.__init__ (self)
```

构造一个无效的网络缓存元数据。

**See also** [isValid](qnetworkcachemetadata.html#isValid)（ ） 。

```
QNetworkCacheMetaData.__init__ (self, QNetworkCacheMetaData other)
```

构造的一个副本_other_ [QNetworkCacheMetaData](qnetworkcachemetadata.html)。

```
dict-of-QNetworkRequest.Attribute-QVariant QNetworkCacheMetaData.attributes (self)
```

将返回所有存储与此缓存项的属性。

此功能被引入Qt的4.6 。

**See also** [setAttributes](qnetworkcachemetadata.html#setAttributes)（）和[QNetworkRequest.Attribute](qnetworkrequest.html#Attribute-enum)。

```
QDateTime QNetworkCacheMetaData.expirationDate (self)
```

[

返回的日期和元数据过期时间。

](qdatetime.html)

[**See also**](qdatetime.html) [setExpirationDate](qnetworkcachemetadata.html#setExpirationDate)（ ） 。

```
bool QNetworkCacheMetaData.isValid (self)
```

如果这个网络高速缓存元数据有已经设置，否则为False的属性，则返回True 。

```
QDateTime QNetworkCacheMetaData.lastModified (self)
```

[

返回时，元数据的最后修改的日期和时间。

](qdatetime.html)

[**See also**](qdatetime.html) [setLastModified](qnetworkcachemetadata.html#setLastModified)（ ） 。

```
list-of-tuple-of-QByteArray-QByteArray QNetworkCacheMetaData.rawHeaders (self)
```

返回在此元数据设置的所有原始标题的列表。该列表是按照相同的顺序，该头被设置了。

**See also** [setRawHeaders](qnetworkcachemetadata.html#setRawHeaders)（ ） 。

```
bool QNetworkCacheMetaData.saveToDisk (self)
```

返回值是这个缓存应允许被存储在磁盘上。

一些缓存实现可以在内存中保留这些缓存中的项目由于性能原因，但出于安全原因，他们不应该被写入磁盘。

特别是与HTTP ，文件标有杂注：无缓存，或者有一个缓存控制设置为无店铺或无缓存或不具有“缓存控制：公众” https的任何文档集将设置saveToDisk到假的。

**See also** [setSaveToDisk](qnetworkcachemetadata.html#setSaveToDisk)（ ） 。

```
QNetworkCacheMetaData.setAttributes (self, dict-of-QNetworkRequest.Attribute-QVariant attributes)
```

设置此缓存项的所有属性是地图_attributes_。

此功能被引入Qt的4.6 。

**See also** [attributes](qnetworkcachemetadata.html#attributes)（）和[QNetworkRequest.setAttribute](qnetworkrequest.html#setAttribute)（ ） 。

```
QNetworkCacheMetaData.setExpirationDate (self, QDateTime dateTime)
```

设定日期和时元数据过期时间_dateTime_。

**See also** [expirationDate](qnetworkcachemetadata.html#expirationDate)（ ） 。

```
QNetworkCacheMetaData.setLastModified (self, QDateTime dateTime)
```

设置当元数据的最后日期和时间修改为_dateTime_。

**See also** [lastModified](qnetworkcachemetadata.html#lastModified)（ ） 。

```
QNetworkCacheMetaData.setRawHeaders (self, list-of-tuple-of-QByteArray-QByteArray headers)
```

设置原始标头_list_。

**See also** [rawHeaders](qnetworkcachemetadata.html#rawHeaders)（ ） 。

```
QNetworkCacheMetaData.setSaveToDisk (self, bool allow)
```

设置这个网络高速缓存元数据和相关的内容是否应该被允许存储在磁盘上，以_allow_。

**See also** [saveToDisk](qnetworkcachemetadata.html#saveToDisk)（ ） 。

```
QNetworkCacheMetaData.setUrl (self, QUrl url)
```

设定URL这个网络高速缓存元数据是_url_。

密码和片段从URL中删除。

**See also** [url](qnetworkcachemetadata.html#url)（ ） 。

```
QUrl QNetworkCacheMetaData.url (self)
```

[

返回此网络缓存元数据是指URL中。

](qurl.html)

[**See also**](qurl.html) [setUrl](qnetworkcachemetadata.html#setUrl)（ ） 。

```
bool QNetworkCacheMetaData.__eq__ (self, QNetworkCacheMetaData other)
```

```
bool QNetworkCacheMetaData.__ne__ (self, QNetworkCacheMetaData other)
```