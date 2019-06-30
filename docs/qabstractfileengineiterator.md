# QAbstractFileEngineIterator Class Reference

## [[QtCore](index.htm) module]

该QAbstractFileEngineIterator类提供一个迭代器接口，用于自定义文件引擎。[More...](#details)

### Methods

*   `__init__ (self, QDir.Filters filters, QStringList nameFilters)`
*   `QFileInfo currentFileInfo (self)`
*   `QString currentFileName (self)`
*   `QString currentFilePath (self)`
*   `QDir.Filters filters (self)`
*   `bool hasNext (self)`
*   `QStringList nameFilters (self)`
*   `QString next (self)`
*   `QString path (self)`

* * *

## Detailed Description

该QAbstractFileEngineIterator类提供一个迭代器接口，用于自定义文件引擎。

如果你想要的是遍历条目目录，请参见[QDirIterator](qdiriterator.html)代替。这个类是仅适用于自定义文件引擎的作者。

QAbstractFileEngineIterator是一个单向单次使用的虚拟迭代器，可插入[QDirIterator](qdiriterator.html)，支持自定义文件引擎提供透明代理迭代。

你可以继承QAbstractFileEngineIterator编写自己的文件引擎时提供一个迭代器。堵塞迭代器到你的文件系统，您只需从一个重新实现返回这个子类的实例[QAbstractFileEngine.beginEntryList](qabstractfileengine.html#beginEntryList)（ ） 。

例如：

```
 QAbstractFileEngineIterator *
 CustomFileEngine.beginEntryList([QDir](qdir.html).Filters filters, const [QStringList](qstringlist.html) &filterNames)
 {
     return new CustomFileEngineIterator(filters, filterNames);
 }

```

QAbstractFileEngineIterator是一个路径，名称的过滤器，并进入过滤器相关联。该路径是提供文件的发动机，可以在迭代器级别（例如，需要最大限度地减少网络流量的网络文件系统）优化目录列表迭代器列表中的条目英寸的名字过滤器和过滤器进入该目录，但它们也可以由迭代子类可以忽略; QAbstractFileEngineIterator已经提供了所需的过滤逻辑的matchesFilters （ ）函数。你可以调用目录名（ ）来获得目录名，[nameFilters](qabstractfileengineiterator.html#nameFilters)（）来获取的名称过滤器的StringList ，并[filters](qabstractfileengineiterator.html#filters)（ ）来获得进入过滤器。

纯虚函数[hasNext](qabstractfileengineiterator.html#hasNext)如果当前目录中有至少一个以上的项目（即目录名称是有效的和可访问的，我们还没有达到参赛名单的末尾） ，否则返回False （）返回True 。重新实现[next](qabstractfileengineiterator.html#next)（）寻求下一个条目。

纯虚函数[currentFileName](qabstractfileengineiterator.html#currentFileName)（ ）返回当前条目的名称，而不推进迭代器。该[currentFilePath](qabstractfileengineiterator.html#currentFilePath)（ ）函数提供了方便，它返回当前项的完整路径。

下面是如何实现返回每个三个固定条目的序列的迭代器的例子。

```
 class CustomIterator : public QAbstractFileEngineIterator
 {
 public:
     CustomIterator(const [QStringList](qstringlist.html) &nameFilters, [QDir](qdir.html).Filters filters)
         : QAbstractFileEngineIterator(nameFilters, filters), index(0)
     {
         // In a real iterator, these entries are fetched from the
         // file system based on the value of path().
         entries << "entry1" << "entry2" << "entry3";
     }

     bool hasNext() const
     {
         return index < entries.size() - 1;
     }

     [QString](qstring.html) next()
     {
        if (!hasNext())
            return [QString](qstring.html)();
        ++index;
        return currentFilePath();
     }

     [QString](qstring.html) currentFileName()
     {
         return entries.at(index);
     }

 private:
     [QStringList](qstringlist.html) entries;
     int index;
 };

```

注： QAbstractFileEngineIterator不处理QDir.IteratorFlags ，它只是返回的条目为一个单一的目录。

* * *

## Method Documentation

```
QAbstractFileEngineIterator.__init__ (self, QDir.Filters filters, QStringList nameFilters)
```

构造一个[QAbstractFileEngineIterator](qabstractfileengineiterator.html)使用过滤器入口_filters_和通配符名称的过滤器_nameFilters_。

```
QFileInfo QAbstractFileEngineIterator.currentFileInfo (self)
```

[](qfileinfo.html)

[虚函数返回一个](qfileinfo.html)[QFileInfo](qfileinfo.html)当前目录项。此功能提供了方便。它也可以是比创建一个稍快[QFileInfo](qfileinfo.html)反对自己，因为这个函数返回的对象可能包含缓存信息[QFileInfo](qfileinfo.html)否则将有通过文件引擎来访问。

**See also** [currentFileName](qabstractfileengineiterator.html#currentFileName)（ ） 。

```
QString QAbstractFileEngineIterator.currentFileName (self)
```

这种方法是抽象的，应在任何子类中重新实现。

这个纯虚函数返回当前目录条目的名称，不包括路径。

**See also** [currentFilePath](qabstractfileengineiterator.html#currentFilePath)（ ） 。

```
QString QAbstractFileEngineIterator.currentFilePath (self)
```

返回路径到当前目录条目。这是一样的前面加上[path](qabstractfileengineiterator.html#pathx)（ ）的返回值[currentFileName](qabstractfileengineiterator.html#currentFileName)（ ） 。

**See also** [currentFileName](qabstractfileengineiterator.html#currentFileName)（ ） 。

```
QDir.Filters QAbstractFileEngineIterator.filters (self)
```

[

返回入口过滤器这个迭代器。

](index.htm)

[**See also**](index.htm) [QDir.filter](qdir.html#filter)（ ）[nameFilters](qabstractfileengineiterator.html#nameFilters)（）和[path](qabstractfileengineiterator.html#pathx)（ ） 。

```
bool QAbstractFileEngineIterator.hasNext (self)
```

这种方法是抽象的，应在任何子类中重新实现。

如果在当前目录中至少有一个以上的项目（例如，迭代器路径是有效的和可访问和迭代器还没有达到参赛名单的末尾）这个纯虚函数返回True。

**See also** [QDirIterator.hasNext](qdiriterator.html#hasNext)（ ） 。

```
QStringList QAbstractFileEngineIterator.nameFilters (self)
```

返回名称的过滤器为这个迭代器。

**See also** [QDir.nameFilters](qdir.html#nameFilters)（ ）[filters](qabstractfileengineiterator.html#filters)（）和[path](qabstractfileengineiterator.html#pathx)（ ） 。

```
QString QAbstractFileEngineIterator.next (self)
```

这种方法是抽象的，应在任何子类中重新实现。

这个纯虚函数前进迭代到下一个目录项，并返回文件路径到当前项目。

此功能可以选择使使用[nameFilters](qabstractfileengineiterator.html#nameFilters)（）和[filters](qabstractfileengineiterator.html#filters)（ ）以优化其性能。

重新实现这个函数在子类中推进迭代器。

**See also** [QDirIterator.next](qdiriterator.html#next)（ ） 。

```
QString QAbstractFileEngineIterator.path (self)
```