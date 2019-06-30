# QPixmapCache Class Reference

## [[QtGui](index.htm) module]

该QPixmapCache类为像素图的应用范围的缓存。[More...](#details)

### Types

*   `class **[Key](index.htm)**`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QPixmapCache)`

### Static Methods

*   `int cacheLimit ()`
*   `clear ()`
*   `QPixmap find (QString key)`
*   `bool find (QString key, QPixmap pixmap)`
*   `bool find (Key key, QPixmap pixmap)`
*   `bool insert (QString key, QPixmap)`
*   `Key insert (QPixmap pixmap)`
*   `remove (QString key)`
*   `remove (Key key)`
*   `bool replace (Key key, QPixmap pixmap)`
*   `setCacheLimit (int)`

* * *

## Detailed Description

该QPixmapCache类为像素图的应用范围的缓存。

这个类是最优化的绘图工具[QPixmap](qpixmap.html)。你可以用它来存储临时像素图是昂贵的生成，而无需使用比更多的存储空间[cacheLimit](qpixmapcache.html#cacheLimit)（ ） 。使用[insert](qpixmapcache.html#insert)（ ）来插入像素图，[find](qpixmapcache.html#find)（）找到他们，[clear](qpixmapcache.html#clear)（）来清空缓存。

QPixmapCache不包含成员数据，只有静态函数来访问全局像素图缓存。它创建了一个内部[QCache](index.htm)对象用于缓存的像素图。

高速缓存关联一个像素映像与用户提供的字符串作为密钥，或与[QPixmapCache.Key](index.htm)高速缓存生成。运用[QPixmapCache.Key](index.htm)钥匙比使用字符串快。该字符串的API是复杂的键很方便，但[QPixmapCache.Key](index.htm)API将是非常有效和方便的一到一个对象到像素图绘制 - 在这种情况下，你可以存储密钥作为一个对象的成员。

如果两个像素图被插入到使用相等的键缓存，那么最后的pixmap将替代缓存中的第一个像素图。在此之前的行为[QHash](index.htm)和[QCache](index.htm)类。

当所有的像素图中的高速缓存的总大小超过缓存已满[cacheLimit](qpixmapcache.html#cacheLimit)（ ） 。初始高速缓存限制为2048 KB桌面平台（ 2 MB ）的嵌入式平台， 10240 KB （ 10 MB） ，你可以通过调用改变这个[setCacheLimit](qpixmapcache.html#setCacheLimit)（ ）与所需的值。一个像素图大致需要（_width_*_height_*_depth_） / 8字节的内存。

该_Qt Quarterly_文章[Optimizing with QPixmapCache](http://qt.nokia.com/doc/qq/qq12-qpixmapcache.html)解释如何使用QPixmapCache通过缓存绘画的结果，以加快应用程序。

* * *

## Method Documentation

```
QPixmapCache.__init__ (self)
```

```
QPixmapCache.__init__ (self, QPixmapCache)
```

```
int QPixmapCache.cacheLimit ()
```

返回高速缓存的限制（以KB为单位） 。

默认的缓存限制为2048 KB的嵌入式平台， 10240 KB桌面平台。

**See also** [setCacheLimit](qpixmapcache.html#setCacheLimit)（ ） 。

```
QPixmapCache.clear ()
```

删除所有像素图从缓存。

```
QPixmap QPixmapCache.find (QString key)
```

[

查找与给定关联的缓存像素图_key_在缓存中。如果找到了像素图，函数集_pixmap_到像素图，并返回True，否则它的叶子_pixmap_独自返回False 。

例如：

](qpixmap.html)

```
 QPixmap pm;
 if (![QPixmapCache](qpixmapcache.html).find("my_big_image", &pm)) {
     pm.load("bigimage.png");
     [QPixmapCache](qpixmapcache.html).insert("my_big_image", pm);
 }
 painter->drawPixmap(0, 0, pm);

```

此功能被引入Qt的4.6 。

```
bool QPixmapCache.find (QString key, QPixmap pixmap)
```

```
bool QPixmapCache.find (Key key, QPixmap pixmap)
```

查找与给定关联的缓存像素图_key_在缓存中。如果找到了像素图，函数集_pixmap_到像素图，并返回True，否则它的叶子_pixmap_独自返回False 。如果未找到该像素图，它表示该_key_不再有效，因此它会被释放下一个插入。

此功能被引入Qt的4.6 。

```
bool QPixmapCache.insert (QString key, QPixmap)
```

插入的像素图的副本_pixmap_与相关联的_key_到缓存中。

通过Qt库中插入的所有像素映射有一个主要的出发用“ $ QT” ，所以你自己的像素映射的键应该永远不会开始“$ QT” 。

当一个像素映射插入和缓存将要超过它的极限，它消除了像素图，直到有足够的空间将被插入的像素图。

当需要更多空间的最古老的像素图（最近最少在缓存中访问）都将被删除。

如果该对象被插入到缓存中的函数返回True，否则返回False 。

**See also** [setCacheLimit](qpixmapcache.html#setCacheLimit)（ ） 。

```
Key QPixmapCache.insert (QPixmap pixmap)
```

[

插入给定的一个副本_pixmap_到缓存中，并返回可用于对其进行检索的密钥。

当一个像素映射插入和缓存将要超过它的极限，它消除了像素图，直到有足够的空间将被插入的像素图。

当需要更多空间的最古老的像素图（最近最少在缓存中访问）都将被删除。

此功能被引入Qt的4.6 。

](index.htm)

[**See also**](index.htm) [setCacheLimit](qpixmapcache.html#setCacheLimit)（）和[replace](qpixmapcache.html#replace)（ ） 。

```
QPixmapCache.remove (QString key)
```

删除关联的像素图_key_从高速缓存中。

```
QPixmapCache.remove (Key key)
```

删除关联的像素图_key_从高速缓存中，并释放键为未来的插入。

此功能被引入Qt的4.6 。

```
bool QPixmapCache.replace (Key key, QPixmap pixmap)
```

替换与给定关联的像素图_key_与_pixmap_规定。返回True如果_pixmap_已正确插入到缓存中，否则返回False 。

此功能被引入Qt的4.6 。

**See also** [setCacheLimit](qpixmapcache.html#setCacheLimit)（）和[insert](qpixmapcache.html#insert)（ ） 。

```
QPixmapCache.setCacheLimit (int)
```

设置缓存的限制_n_千字节。

默认设置为2048 KB的嵌入式平台， 10240 KB桌面平台。

**See also** [cacheLimit](qpixmapcache.html#cacheLimit)（ ） 。