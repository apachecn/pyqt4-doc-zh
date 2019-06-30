# QXmlStreamAttributes Class Reference

## [[QtCore](index.htm) module]

The QXmlStreamAttributes class represents a vector of [QXmlStreamAttribute](qxmlstreamattribute.html). [More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QXmlStreamAttributes)`
*   `append (self, QString namespaceUri, QString name, QString value)`
*   `append (self, QString qualifiedName, QString value)`
*   `append (self, QXmlStreamAttribute attribute)`
*   `QXmlStreamAttribute at (self, int i)`
*   `clear (self)`
*   `bool contains (self, QXmlStreamAttribute value)`
*   `int count (self, QXmlStreamAttribute value)`
*   `int count (self)`
*   `sip.voidptr data (self)`
*   `fill (self, QXmlStreamAttribute value, int size = -1)`
*   `QXmlStreamAttribute first (self)`
*   `bool hasAttribute (self, QString qualifiedName)`
*   `bool hasAttribute (self, QString namespaceUri, QString name)`
*   `int indexOf (self, QXmlStreamAttribute value, int from = 0)`
*   `insert (self, int i, QXmlStreamAttribute value)`
*   `bool isEmpty (self)`
*   `QXmlStreamAttribute last (self)`
*   `int lastIndexOf (self, QXmlStreamAttribute value, int from = -1)`
*   `prepend (self, QXmlStreamAttribute value)`
*   `remove (self, int i)`
*   `remove (self, int i, int count)`
*   `replace (self, int i, QXmlStreamAttribute value)`
*   `int size (self)`
*   `QStringRef value (self, QString namespaceUri, QString name)`
*   `QStringRef value (self, QString qualifiedName)`

### Special Methods

*   `int __contains__ (self, QXmlStreamAttribute value)`
*   `__delitem__ (self, int i)`
*   `__delitem__ (self, slice slice)`
*   `bool __eq__ (self, QXmlStreamAttributes other)`
*   `QXmlStreamAttribute __getitem__ (self, int i)`
*   `QXmlStreamAttributes __getitem__ (self, slice slice)`
*   `QXmlStreamAttributes __iadd__ (self, QXmlStreamAttributes other)`
*   `QXmlStreamAttributes __iadd__ (self, QXmlStreamAttribute value)`
*   `__len__ (self)`
*   `bool __ne__ (self, QXmlStreamAttributes other)`
*   `__setitem__ (self, int i, QXmlStreamAttribute value)`
*   `__setitem__ (self, slice slice, QXmlStreamAttributes list)`

* * *

## Detailed Description

The QXmlStreamAttributes class represents a vector of [QXmlStreamAttribute](qxmlstreamattribute.html).

Attributes are returned by a [QXmlStreamReader](qxmlstreamreader.html) in [attributes()](qxmlstreamreader.html#attributes) when the reader reports a [start element](qxmlstreamreader.html#TokenType-enum). The class can also be used with a [QXmlStreamWriter](qxmlstreamwriter.html) as an argument to [writeAttributes()](qxmlstreamwriter.html#writeAttributes).

The convenience function [value](qxmlstreamattributes.html#value)() loops over the vector and returns an attribute value for a given namespaceUri and an attribute's name.

新的属性可以被添加[append](qxmlstreamattributes.html#append)（ ） 。

* * *

## Method Documentation

```
QXmlStreamAttributes.__init__ (self)
```

```
QXmlStreamAttributes.__init__ (self, QXmlStreamAttributes)
```

```
QXmlStreamAttributes.append (self, QString namespaceUri, QString name, QString value)
```

附加一个新的属性_name_在与所描述的命名空间_namespaceUri_和值_value_。该_namespaceUri_可以为空。

```
QXmlStreamAttributes.append (self, QString qualifiedName, QString value)
```

添加给定的_attribute_向矢量的末端。

**See also** [QVector.append](index.htm#append)（ ） 。

```
QXmlStreamAttributes.append (self, QXmlStreamAttribute attribute)
```

这是一个重载函数。

与追加限定名的新属性_qualifiedName_和值_value_。

```
QXmlStreamAttribute QXmlStreamAttributes.at (self, int i)
```

[

```
QXmlStreamAttributes.clear (self)
```

```
bool QXmlStreamAttributes.contains (self, QXmlStreamAttribute value)
```

```
int QXmlStreamAttributes.count (self, QXmlStreamAttribute value)
```

```
int QXmlStreamAttributes.count (self)
```

```
sip.voidptr QXmlStreamAttributes.data (self)
```

```
QXmlStreamAttributes.fill (self, QXmlStreamAttribute value, int size = -1)
```

](qxmlstreamattribute.html)

```
QXmlStreamAttribute QXmlStreamAttributes.first (self)
```

[

```
bool QXmlStreamAttributes.hasAttribute (self, QString qualifiedName)
```

](qxmlstreamattribute.html)

[返回True如果](qxmlstreamattribute.html)[QXmlStreamAttributes](qxmlstreamattributes.html)有一个属性的限定名是_qualifiedName_否则返回False 。

请注意，这不是名称空间感知。举例来说，如果此[QXmlStreamAttributes](qxmlstreamattributes.html)包含一个属性，它的词汇叫“ XLINK ： HREF ”这不告诉一个名为属性`href`在XLink的命名空间不存在，因为`xlink`前缀可以绑定到任何命名空间。使用采用命名空间URI和本地名称作为参数，名称空间感知的代码超载。

此功能被引入Qt的4.5 。

```
bool QXmlStreamAttributes.hasAttribute (self, QString namespaceUri, QString name)
```

这是一个重载函数。

此功能被引入Qt的4.5 。

```
int QXmlStreamAttributes.indexOf (self, QXmlStreamAttribute value, int from = 0)
```

```
QXmlStreamAttributes.insert (self, int i, QXmlStreamAttribute value)
```

```
bool QXmlStreamAttributes.isEmpty (self)
```

```
QXmlStreamAttribute QXmlStreamAttributes.last (self)
```

[

```
int QXmlStreamAttributes.lastIndexOf (self, QXmlStreamAttribute value, int from = -1)
```

```
QXmlStreamAttributes.prepend (self, QXmlStreamAttribute value)
```

```
QXmlStreamAttributes.remove (self, int i)
```

```
QXmlStreamAttributes.remove (self, int i, int count)
```

```
QXmlStreamAttributes.replace (self, int i, QXmlStreamAttribute value)
```

```
int QXmlStreamAttributes.size (self)
```

```
QStringRef QXmlStreamAttributes.value (self, QString namespaceUri, QString name)
```

返回属性的值_name_在与所描述的命名空间_namespaceUri_，或一个空字符串引用，如果该属性没有定义。该_namespaceUri_可以为空。

```
QStringRef QXmlStreamAttributes.value (self, QString qualifiedName)
```

这是一个重载函数。

返回属性的值_name_在与所描述的命名空间_namespaceUri_，或一个空字符串引用，如果该属性没有定义。该_namespaceUri_可以为空。

```
int QXmlStreamAttributes.__contains__ (self, QXmlStreamAttribute value)
```

```
QXmlStreamAttributes.__delitem__ (self, int i)
```

```
QXmlStreamAttributes.__delitem__ (self, slice slice)
```

```
bool QXmlStreamAttributes.__eq__ (self, QXmlStreamAttributes other)
```

](qxmlstreamattribute.html)

```
QXmlStreamAttribute QXmlStreamAttributes.__getitem__ (self, int i)
```

[](qxmlstreamattribute.html)

```
QXmlStreamAttributes QXmlStreamAttributes.__getitem__ (self, slice slice)
```

[](qxmlstreamattributes.html)

```
QXmlStreamAttributes QXmlStreamAttributes.__iadd__ (self, QXmlStreamAttributes other)
```

[](qxmlstreamattributes.html)

```
QXmlStreamAttributes QXmlStreamAttributes.__iadd__ (self, QXmlStreamAttribute value)
```

[

```
 QXmlStreamAttributes.__len__ (self)
```

```
bool QXmlStreamAttributes.__ne__ (self, QXmlStreamAttributes other)
```

```
QXmlStreamAttributes.__setitem__ (self, int i, QXmlStreamAttribute value)
```

```
QXmlStreamAttributes.__setitem__ (self, slice slice, QXmlStreamAttributes list)
```

](qxmlstreamattributes.html)