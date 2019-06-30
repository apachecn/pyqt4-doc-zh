# QNetworkDiskCache Class Reference

## [[QtNetwork](index.htm) module]

该QNetworkDiskCache类提供了一个非常基本的磁盘缓存。[More...](#details)

继承[QAbstractNetworkCache](qabstractnetworkcache.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `QString cacheDirectory (self)`
*   `int cacheSize (self)`
*   `clear (self)`
*   `QIODevice data (self, QUrl url)`
*   `int expire (self)`
*   `QNetworkCacheMetaData fileMetaData (self, QString fileName)`
*   `insert (self, QIODevice device)`
*   `int maximumCacheSize (self)`
*   `QNetworkCacheMetaData metaData (self, QUrl url)`
*   `QIODevice prepare (self, QNetworkCacheMetaData metaData)`
*   `bool remove (self, QUrl url)`
*   `setCacheDirectory (self, QString cacheDir)`
*   `setMaximumCacheSize (self, int size)`
*   `updateMetaData (self, QNetworkCacheMetaData metaData)`

* * *

## Detailed Description

该QNetworkDiskCache类提供了一个非常基本的磁盘缓存。

QNetworkDiskCache使用存储在它自己的文件中cacheDirectory里面每个URL[QDataStream](qdatastream.html)。文件与文本源MimeType使用qCompress压缩。每个缓存文件以“[cache_](index.htm#cache)。高速缓存“和结束” “ 。数据被写入到磁盘中只[insert](qnetworkdiskcache.html#insert)（）和[updateMetaData](qnetworkdiskcache.html#updateMetaData)（ ） 。

目前，您不能使用一个以上的磁盘缓存共享相同的缓存文件。

QNetworkDiskCache默认情况下限制了缓存将在系统上使用了50MB的空间量。

注意：你必须设置缓存目录之前它会工作。

：网络磁盘缓存可以通过启用

```
 [QNetworkAccessManager](qnetworkaccessmanager.html) *manager = new [QNetworkAccessManager](qnetworkaccessmanager.html)(this);
 QNetworkDiskCache *diskCache = new QNetworkDiskCache(this);
 diskCache->setCacheDirectory("cacheDir");
 manager->setCache(diskCache);

```

当发送请求，来控制何时使用缓存以及何时使用网络的偏好，考虑以下几点：

```
 // do a normal request (preferred from network, as this is the default)
 [QNetworkRequest](qnetworkrequest.html) request([QUrl](qurl.html)([QString](qstring.html)("http://qt.nokia.com")));
 manager->get(request);

 // do a request preferred from cache
 [QNetworkRequest](qnetworkrequest.html) request2([QUrl](qurl.html)([QString](qstring.html)("http://qt.nokia.com")));
 request2.setAttribute([QNetworkRequest](qnetworkrequest.html).CacheLoadControlAttribute, [QNetworkRequest](qnetworkrequest.html).PreferCache);
 manager->get(request2);

```

要检查是否响应从缓存或从网络传来，下面可以应用：

```
 void replyFinished([QNetworkReply](qnetworkreply.html) *reply) {
     [QVariant](qvariant.html) fromCache = reply->attribute([QNetworkRequest](qnetworkrequest.html).SourceIsFromCacheAttribute);
     qDebug() << "page from cache?" << fromCache.toBool();
 }

```

* * *

## Method Documentation

```
QNetworkDiskCache.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建一个新的磁盘缓存。该_parent_参数被传递给[QAbstractNetworkCache](qabstractnetworkcache.html)的构造。

```
QString QNetworkDiskCache.cacheDirectory (self)
```

返回在缓存文件将被存储的位置。

**See also** [setCacheDirectory](qnetworkdiskcache.html#setCacheDirectory)（ ） 。

```
int QNetworkDiskCache.cacheSize (self)
```

从重新实现[QAbstractNetworkCache.cacheSize](qabstractnetworkcache.html#cacheSize)（ ） 。

```
QNetworkDiskCache.clear (self)
```

这种方法也是一个Qt槽与C + +的签名`void clear()`。

从重新实现[QAbstractNetworkCache.clear](qabstractnetworkcache.html#clear)（ ） 。

```
QIODevice QNetworkDiskCache.data (self, QUrl url)
```

[](qiodevice.html)

[从重新实现](qiodevice.html)[QAbstractNetworkCache.data](qabstractnetworkcache.html#data)（ ） 。

```
int QNetworkDiskCache.expire (self)
```

清除高速缓存中，这样它的大小是根据最大高速缓存大小。返回高速缓存的当前大小。

当缓存的当前大小大于[maximumCacheSize](qnetworkdiskcache.html#maximumCacheSize)（ ）旧的缓存文件将被删除，直到总大小小于90％[maximumCacheSize](qnetworkdiskcache.html#maximumCacheSize)（ ）开始的最早的第一个使用该文件的创建日期，以确定如何旧缓存文件。

子类可以重新实现这个函数来改变缓存文件将被删除并考虑到信息的应用程序的顺序知道了[QNetworkDiskCache](qnetworkdiskcache.html)没有，例如的次数的高速缓存访问。

注意：[cacheSize](qnetworkdiskcache.html#cacheSize)（ ）调用过期如果当前缓存大小是未知的。

**See also** [maximumCacheSize](qnetworkdiskcache.html#maximumCacheSize)（）和[fileMetaData](qnetworkdiskcache.html#fileMetaData)（ ） 。

```
QNetworkCacheMetaData QNetworkDiskCache.fileMetaData (self, QString fileName)
```

[](qnetworkcachemetadata.html)

[返回](qnetworkcachemetadata.html)[QNetworkCacheMetaData](qnetworkcachemetadata.html)对于缓存文件_fileName_。

If _fileName_是不是一个缓存文件[QNetworkCacheMetaData](qnetworkcachemetadata.html)将是无效的。

```
QNetworkDiskCache.insert (self, QIODevice device)
```

从重新实现[QAbstractNetworkCache.insert](qabstractnetworkcache.html#insert)（ ） 。

```
int QNetworkDiskCache.maximumCacheSize (self)
```

返回磁盘缓存字节当前的最大大小。

**See also** [setMaximumCacheSize](qnetworkdiskcache.html#setMaximumCacheSize)（ ） 。

```
QNetworkCacheMetaData QNetworkDiskCache.metaData (self, QUrl url)
```

[](qnetworkcachemetadata.html)

[从重新实现](qnetworkcachemetadata.html)[QAbstractNetworkCache.metaData](qabstractnetworkcache.html#metaData)（ ） 。

```
QIODevice QNetworkDiskCache.prepare (self, QNetworkCacheMetaData metaData)
```

[](qiodevice.html)

[从重新实现](qiodevice.html)[QAbstractNetworkCache.prepare](qabstractnetworkcache.html#prepare)（ ） 。

```
bool QNetworkDiskCache.remove (self, QUrl url)
```

从重新实现[QAbstractNetworkCache.remove](qabstractnetworkcache.html#remove)（ ） 。

```
QNetworkDiskCache.setCacheDirectory (self, QString cacheDir)
```

在那里设置缓存文件将被存储到目录_cacheDir_

[QNetworkDiskCache](qnetworkdiskcache.html)将创建这个目录，如果它不存在。

制备的缓存项目将被保存在新的高速缓存目录被插入时。

**See also** [cacheDirectory](qnetworkdiskcache.html#cacheDirectory)（）和[QDesktopServices.CacheLocation](qdesktopservices.html#StandardLocation-enum)。

```
QNetworkDiskCache.setMaximumCacheSize (self, int size)
```

设置磁盘缓存是最大尺寸_size_以字节为单位。

如果新的尺寸越小则当前缓存大小，则缓存将调用[expire](qnetworkdiskcache.html#expire)（ ） 。

**See also** [maximumCacheSize](qnetworkdiskcache.html#maximumCacheSize)（ ） 。

```
QNetworkDiskCache.updateMetaData (self, QNetworkCacheMetaData metaData)
```

从重新实现[QAbstractNetworkCache.updateMetaData](qabstractnetworkcache.html#updateMetaData)（ ） 。