# QXmlAttributes Class Reference

## [[QtXml](index.htm) module]

该QXmlAttributes类提供XML属性。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QXmlAttributes)`
*   `append (self, QString qName, QString uri, QString localPart, QString value)`
*   `clear (self)`
*   `int count (self)`
*   `int index (self, QString qName)`
*   `int index (self, QString uri, QString localPart)`
*   `int length (self)`
*   `QString localName (self, int index)`
*   `QString qName (self, int index)`
*   `QString type (self, int index)`
*   `QString type (self, QString qName)`
*   `QString type (self, QString uri, QString localName)`
*   `QString uri (self, int index)`
*   `QString value (self, int index)`
*   `QString value (self, QString qName)`
*   `QString value (self, QString uri, QString localName)`

### Special Methods

*   `__len__ (self)`

* * *

## Detailed Description

该QXmlAttributes类提供XML属性。

如果属性报告[QXmlContentHandler.startElement](qxmlcontenthandler.html#startElement)（ ）这个类是用来传递属性值。

使用[index](qxmlattributes.html#index)（）以在列表中找到的属性的位置，[count](qxmlattributes.html#count)（）来检索属性的数量，并[clear](qxmlattributes.html#clear)（）删除的属性。新的属性可以被添加[append](qxmlattributes.html#append)（ ） 。使用[type](qxmlattributes.html#type)（）来获取一个属性的类型和[value](qxmlattributes.html#value)（）来获取它的值。属性的名称可以从[localName](qxmlattributes.html#localName)（）或[qName](qxmlattributes.html#qName)（ ），并从它的命名空间URI[uri](qxmlattributes.html#uri)（ ） 。

* * *

## Method Documentation

```
QXmlAttributes.__init__ (self)
```

构造一个空属性列表。

```
QXmlAttributes.__init__ (self, QXmlAttributes)
```

```
QXmlAttributes.append (self, QString qName, QString uri, QString localPart, QString value)
```

附加一个新的属性条目的属性列表。该属性的限定名是_qName_，命名空间URI为_uri_和本地名称是_localPart_。该属性的值是_value_。

**See also** [qName](qxmlattributes.html#qName)（ ）[uri](qxmlattributes.html#uri)（ ）[localName](qxmlattributes.html#localName)（）和[value](qxmlattributes.html#value)（ ） 。

```
QXmlAttributes.clear (self)
```

清除属性的列表。

**See also** [append](qxmlattributes.html#append)（ ） 。

```
int QXmlAttributes.count (self)
```

返回的属性列表中的号码。此功能相当于[length](qxmlattributes.html#length)（ ） 。

```
int QXmlAttributes.index (self, QString qName)
```

查找属性的索引的限定名_qName_。

如果它没有被发现返回属性或-1的索引。

**See also** [Namespace Support via Features](index.htm#namespace-support-via-features)。

```
int QXmlAttributes.index (self, QString uri, QString localPart)
```

这是一个重载函数。

```
int QXmlAttributes.length (self)
```

返回的属性列表中的号码。

**See also** [count](qxmlattributes.html#count)（ ） 。

```
QString QXmlAttributes.localName (self, int index)
```

查找的位置属性的属性的本地名称_index_。如果没有命名空间的处理完成后，本地名称是空字符串。

**See also** [Namespace Support via Features](index.htm#namespace-support-via-features)。

```
QString QXmlAttributes.qName (self, int index)
```

查找属性的XML 1.0的位置属性限定名称_index_。

**See also** [Namespace Support via Features](index.htm#namespace-support-via-features)。

```
QString QXmlAttributes.type (self, int index)
```

查找一个属性的类型，位置属性_index_。

目前，只有“ CDATA ”返回。

```
QString QXmlAttributes.type (self, QString qName)
```

这是一个重载函数。

查找一个属性的类型为限定名_qName_。

目前，只有“ CDATA ”返回。

```
QString QXmlAttributes.type (self, QString uri, QString localName)
```

这是一个重载函数。

通过命名空间名称查找属性的类型。

_uri_指定命名空间URI和_localName_指定本地名称。如果该名称没有名称空间URI ，使用空字符串_uri_。

目前，只有“ CDATA ”返回。

```
QString QXmlAttributes.uri (self, int index)
```

查找的位置属性的属性的命名空间URI_index_。如果没有命名空间的处理完成，或者如果属性没有命名空间，命名空间URI为空字符串。

**See also** [Namespace Support via Features](index.htm#namespace-support-via-features)。

```
QString QXmlAttributes.value (self, int index)
```

返回在位置属性的属性值_index_。索引必须是一个有效的位置（即0 \u003c =_index_\u003c[count](qxmlattributes.html#count)（））。

```
QString QXmlAttributes.value (self, QString qName)
```

这是一个重载函数。

返回限定名称的属性的值_qName_，或者如果没有属性存在给定名称为空字符串。

**See also** [Namespace Support via Features](index.htm#namespace-support-via-features)。

```
QString QXmlAttributes.value (self, QString uri, QString localName)
```

这是一个重载函数。

返回限定名称的属性的值_qName_，或者如果没有属性存在给定名称为空字符串。

**See also** [Namespace Support via Features](index.htm#namespace-support-via-features)。

```
 QXmlAttributes.__len__ (self)
```