# QXmlStreamAttribute Class Reference

## [[QtCore](index.htm) module]

该QXmlStreamAttribute类表示一个单一的XML属性[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QString qualifiedName, QString value)`
*   `__init__ (self, QString namespaceUri, QString name, QString value)`
*   `__init__ (self, QXmlStreamAttribute)`
*   `bool isDefault (self)`
*   `QStringRef name (self)`
*   `QStringRef namespaceUri (self)`
*   `QStringRef prefix (self)`
*   `QStringRef qualifiedName (self)`
*   `QStringRef value (self)`

### Special Methods

*   `bool __eq__ (self, QXmlStreamAttribute other)`
*   `bool __ne__ (self, QXmlStreamAttribute other)`

* * *

## Detailed Description

该QXmlStreamAttribute类表示一个单一的XML属性

属性包含一个可选的空[namespaceUri](qxmlstreamattribute.html#namespaceUri)（）的一个[name](qxmlstreamattribute.html#name)（）的一个[value](qxmlstreamattribute.html#value)（） ，和一个[isDefault](qxmlstreamattribute.html#isDefault)（ ）属性。

原始的XML属性名称作为返回[qualifiedName](qxmlstreamattribute.html#qualifiedName)（ ） 。

* * *

## Method Documentation

```
QXmlStreamAttribute.__init__ (self)
```

创建一个空的属性。

```
QXmlStreamAttribute.__init__ (self, QString qualifiedName, QString value)
```

构造具有限定名称的属性_qualifiedName_和值_value_。

```
QXmlStreamAttribute.__init__ (self, QString namespaceUri, QString name, QString value)
```

构造一个属性与所描述的命名空间_namespaceUri_同_name_和值_value_。

```
QXmlStreamAttribute.__init__ (self, QXmlStreamAttribute)
```

创建副本_other_。

```
bool QXmlStreamAttribute.isDefault (self)
```

返回True如果分析器添加了这个属性有一个默认值以下的ATTLIST声明在DTD ，否则返回False 。

```
QStringRef QXmlStreamAttribute.name (self)
```

返回属性的本地名称。

```
QStringRef QXmlStreamAttribute.namespaceUri (self)
```

返回属性的解决的namespaceURI ，或空字符串引用，如果该属性没有定义的命名空间。

```
QStringRef QXmlStreamAttribute.prefix (self)
```

返回属性的命名空间前缀。

此功能被引入Qt的4.4 。

**See also** [name](qxmlstreamattribute.html#name)（）和[qualifiedName](qxmlstreamattribute.html#qualifiedName)（ ） 。

```
QStringRef QXmlStreamAttribute.qualifiedName (self)
```

返回属性的限定名称。

一个合格的名称是XML数据的属性的原始名称。它由命名空间[prefix](qxmlstreamattribute.html#prefix)（ ），其次是冒号，然后是属性的本地[name](qxmlstreamattribute.html#name)（ ） 。由于命名空间前缀不是唯一的（相同的前缀可以指向不同的命名空间和不同的前缀可以指向同一个命名空间） ，你不应该使用qualifiedName中（ ） ，而解析[namespaceUri](qxmlstreamattribute.html#namespaceUri)（ ）和属性的本地[name](qxmlstreamattribute.html#name)（ ） 。

```
QStringRef QXmlStreamAttribute.value (self)
```

返回属性的值。

```
bool QXmlStreamAttribute.__eq__ (self, QXmlStreamAttribute other)
```

```
bool QXmlStreamAttribute.__ne__ (self, QXmlStreamAttribute other)
```