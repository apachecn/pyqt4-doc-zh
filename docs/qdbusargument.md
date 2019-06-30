# QDBusArgument Class Reference

## [[QtDBus](index.htm) module]

该QDBusArgument类用于马歇尔和demarshall D-Bus的参数。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDBusArgument other)`
*   `__init__ (self, object arg, int id = QMetaType.Int)`
*   `add (self, object arg, int id = QMetaType.Int)`
*   `beginArray (self, int id)`
*   `beginMap (self, int kid, int vid)`
*   `beginMapEntry (self)`
*   `beginStructure (self)`
*   `endArray (self)`
*   `endMap (self)`
*   `endMapEntry (self)`
*   `endStructure (self)`

* * *

## Detailed Description

在C + +中QDBusArgument类用于马歇尔和demarshall乌思集合类型，如数组，结构和地图。在PyQt的值会自动取消编组和QDBusArgument仅用于马歇尔值。在C + +编组是使用重载的左移运算符。在PyQt的单add（）函数的使用。

* * *

## Method Documentation

```
QDBusArgument.__init__ (self)
```

构造一个空[QDBusArgument](qdbusargument.html)的说法。

空[QDBusArgument](qdbusargument.html)对象不允许进行读取或写入。

```
QDBusArgument.__init__ (self, QDBusArgument other)
```

构造的一个副本_other_ [QDBusArgument](qdbusargument.html)对象。

因此，这两个对象将从该点包含相同的状态前进。 QDBusArguments被明确共享的，因此，任何修改或拷贝将影响其它1太。

```
QDBusArgument.__init__ (self, object arg, int id = QMetaType.Int)
```

```
 QDBusArgument.add (self, object arg, int id = QMetaType.Int)
```

```
QDBusArgument.beginArray (self, int id)
```

打开适用于附加的元类型的元素的新D-Bus的阵列_id_。

这个功能通常是用在`operator&lt;&lt;`流媒体运营商，如下面的例子：

```
 // append an array of MyElement types
 [QDBusArgument](qdbusargument.html) &operator<<([QDBusArgument](qdbusargument.html) &argument, const MyArray &myarray)
 {
     argument.beginArray( qMetaTypeId<MyElement>() );
     for ( int i = 0; i < myarray.length; ++i )
         argument << myarray.elements[i];
     argument.endArray();
     return argument;
 }

```

如果你想马歇尔的类型是[QList](index.htm)，[QVector](index.htm)或任何Qt的[Container Classes](index.htm)这需要一个模板参数，你不必声明`operator&lt;&lt;`正常吧，因为[QtDBus](index.htm)提供通用模板做编组数据的工作。这同样适用于STL的序列容器，如`std.list`，`std.vector`等。

**See also** [endArray](qdbusargument.html#endArray)（ ）[beginStructure](qdbusargument.html#beginStructure)（）和[beginMap](qdbusargument.html#beginMap)（ ） 。

```
QDBusArgument.beginMap (self, int kid, int vid)
```

打开适用于附加元素的新D-Bus的地图。地图是容器相关联的一个条目（关键）到另一个（的价值） ，如Qt的[QMap](index.htm) or [QHash](index.htm)。地图上的键和值的元类型的ID必须在传递_kid_和_vid_分别。

这个功能通常是用在`operator&lt;&lt;`流媒体运营商，如下面的例子：

```
 // append a dictionary that associates ints to MyValue types
 [QDBusArgument](qdbusargument.html) &operator<<([QDBusArgument](qdbusargument.html) &argument, const MyDictionary &mydict)
 {
     argument.beginMap( [QVariant](qvariant.html).Int, qMetaTypeId<MyValue>() );
     for ( int i = 0; i < mydict.length; ++i ) {
         argument.beginMapEntry();
         argument << mydict.data[i].key << mydict.data[i].value;
         argument.endMapEntry();
     }
     argument.endMap();
     return argument;
 }

```

如果你想马歇尔的类型是[QMap](index.htm) or [QHash](index.htm)，你不必声明`operator&lt;&lt;`正常吧，因为[QtDBus](index.htm)提供通用模板做编组数据的工作。

**See also** [endMap](qdbusargument.html#endMap)（ ）[beginStructure](qdbusargument.html#beginStructure)（ ）[beginArray](qdbusargument.html#beginArray)（）和[beginMapEntry](qdbusargument.html#beginMapEntry)（ ） 。

```
QDBusArgument.beginMapEntry (self)
```

打开适合的附加键和值条目的D-Bus的映射项。当一个图是打开此功能仅适用[beginMap](qdbusargument.html#beginMap)（ ） 。

See [beginMap](qdbusargument.html#beginMap)（）该函数的使用情况的一个例子。

**See also** [endMapEntry](qdbusargument.html#endMapEntry)（）和[beginMap](qdbusargument.html#beginMap)（ ） 。

```
QDBusArgument.beginStructure (self)
```

打开适合追加新的论据了新的D-Bus的结构。

这个功能通常是用在`operator&lt;&lt;`流媒体运营商，如下面的例子：

```
 [QDBusArgument](qdbusargument.html) &operator<<([QDBusArgument](qdbusargument.html) &argument, const MyStructure &mystruct)
 {
     argument.beginStructure();
     argument << mystruct.member1 << mystruct.member2 << ... ;
     argument.endStructure();
     return argument;
 }

```

结构可以包含其他结构，所以下面的代码是有效的：

```
 [QDBusArgument](qdbusargument.html) &operator<<([QDBusArgument](qdbusargument.html) &argument, const MyStructure &mystruct)
 {
     argument.beginStructure();
     argument << mystruct.member1 << mystruct.member2;

     argument.beginStructure();
     argument << mystruct.member3.subMember1 << mystruct.member3.subMember2;
     argument.endStructure();

     argument << mystruct.member4;
     argument.endStructure();
     return argument;
 }

```

**See also** [endStructure](qdbusargument.html#endStructure)（ ）[beginArray](qdbusargument.html#beginArray)（）和[beginMap](qdbusargument.html#beginMap)（ ） 。

```
QDBusArgument.endArray (self)
```

关闭一个D-Bus的数组开[beginArray](qdbusargument.html#beginArray)（ ） 。这个函数必须被调用的次数相同数量的[beginArray](qdbusargument.html#beginArray)（）被调用。

**See also** [beginArray](qdbusargument.html#beginArray)（ ）[endStructure](qdbusargument.html#endStructure)（）和[endMap](qdbusargument.html#endMap)（ ） 。

```
QDBusArgument.endMap (self)
```

关闭一个D-Bus的地图开[beginMap](qdbusargument.html#beginMap)（ ） 。这个函数必须被调用的次数相同数量的[beginMap](qdbusargument.html#beginMap)（）被调用。

**See also** [beginMap](qdbusargument.html#beginMap)（ ）[endStructure](qdbusargument.html#endStructure)（）和[endArray](qdbusargument.html#endArray)（ ） 。

```
QDBusArgument.endMapEntry (self)
```

关闭开了一个D-Bus的映射项[beginMapEntry](qdbusargument.html#beginMapEntry)（ ） 。这个函数必须被调用的次数相同数量的[beginMapEntry](qdbusargument.html#beginMapEntry)（）被调用。

**See also** [beginMapEntry](qdbusargument.html#beginMapEntry)（ ） 。

```
QDBusArgument.endStructure (self)
```

关闭一个D-Bus的结构与开[beginStructure](qdbusargument.html#beginStructure)（ ） 。这个函数必须被调用的次数相同数量的[beginStructure](qdbusargument.html#beginStructure)（）被调用。

**See also** [beginStructure](qdbusargument.html#beginStructure)（ ）[endArray](qdbusargument.html#endArray)（）和[endMap](qdbusargument.html#endMap)（ ） 。