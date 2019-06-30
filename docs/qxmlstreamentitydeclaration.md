# QXmlStreamEntityDeclaration Class Reference

## [[QtCore](index.htm) module]

该QXmlStreamEntityDeclaration类表示一个DTD实体声明。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QXmlStreamEntityDeclaration)`
*   `QStringRef name (self)`
*   `QStringRef notationName (self)`
*   `QStringRef publicId (self)`
*   `QStringRef systemId (self)`
*   `QStringRef value (self)`

### Special Methods

*   `bool __eq__ (self, QXmlStreamEntityDeclaration other)`
*   `bool __ne__ (self, QXmlStreamEntityDeclaration other)`

* * *

## Detailed Description

该QXmlStreamEntityDeclaration类表示一个DTD实体声明。

实体声明由一个[name](qxmlstreamentitydeclaration.html#name)（）的一个[notationName](qxmlstreamentitydeclaration.html#notationName)（）的一个[systemId](qxmlstreamentitydeclaration.html#systemId)（）的一个[publicId](qxmlstreamentitydeclaration.html#publicId)（） ，和一个[value](qxmlstreamentitydeclaration.html#value)（ ） 。

* * *

## Method Documentation

```
QXmlStreamEntityDeclaration.__init__ (self)
```

创建一个空的实体声明。

```
QXmlStreamEntityDeclaration.__init__ (self, QXmlStreamEntityDeclaration)
```

创建副本_other_。

```
QStringRef QXmlStreamEntityDeclaration.name (self)
```

返回实体的名称。

```
QStringRef QXmlStreamEntityDeclaration.notationName (self)
```

返回符号名。

```
QStringRef QXmlStreamEntityDeclaration.publicId (self)
```

返回公共标识符。

```
QStringRef QXmlStreamEntityDeclaration.systemId (self)
```

返回系统标识符。

```
QStringRef QXmlStreamEntityDeclaration.value (self)
```

返回实体的价值。

```
bool QXmlStreamEntityDeclaration.__eq__ (self, QXmlStreamEntityDeclaration other)
```

```
bool QXmlStreamEntityDeclaration.__ne__ (self, QXmlStreamEntityDeclaration other)
```