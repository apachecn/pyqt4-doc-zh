# QXmlStreamNotationDeclaration Class Reference

## [[QtCore](index.htm) module]

该QXmlStreamNotationDeclaration类表示一个DTD符号声明。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QXmlStreamNotationDeclaration)`
*   `QStringRef name (self)`
*   `QStringRef publicId (self)`
*   `QStringRef systemId (self)`

### Special Methods

*   `bool __eq__ (self, QXmlStreamNotationDeclaration other)`
*   `bool __ne__ (self, QXmlStreamNotationDeclaration other)`

* * *

## Detailed Description

该QXmlStreamNotationDeclaration类表示一个DTD符号声明。

一个符号声明包含一个[name](qxmlstreamnotationdeclaration.html#name)（）的一个[systemId](qxmlstreamnotationdeclaration.html#systemId)（） ，和一个[publicId](qxmlstreamnotationdeclaration.html#publicId)（ ） 。

* * *

## Method Documentation

```
QXmlStreamNotationDeclaration.__init__ (self)
```

创建一个空符号声明。

```
QXmlStreamNotationDeclaration.__init__ (self, QXmlStreamNotationDeclaration)
```

创建副本_other_。

```
QStringRef QXmlStreamNotationDeclaration.name (self)
```

返回符号名。

```
QStringRef QXmlStreamNotationDeclaration.publicId (self)
```

返回公共标识符。

```
QStringRef QXmlStreamNotationDeclaration.systemId (self)
```

返回系统标识符。

```
bool QXmlStreamNotationDeclaration.__eq__ (self, QXmlStreamNotationDeclaration other)
```

```
bool QXmlStreamNotationDeclaration.__ne__ (self, QXmlStreamNotationDeclaration other)
```