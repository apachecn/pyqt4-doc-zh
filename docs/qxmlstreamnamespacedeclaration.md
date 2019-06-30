# QXmlStreamNamespaceDeclaration Class Reference

## [[QtCore](index.htm) module]

该QXmlStreamNamespaceDeclaration类表示一个命名空间声明。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QXmlStreamNamespaceDeclaration)`
*   `__init__ (self, QString prefix, QString namespaceUri)`
*   `QStringRef namespaceUri (self)`
*   `QStringRef prefix (self)`

### Special Methods

*   `bool __eq__ (self, QXmlStreamNamespaceDeclaration other)`
*   `bool __ne__ (self, QXmlStreamNamespaceDeclaration other)`

* * *

## Detailed Description

该QXmlStreamNamespaceDeclaration类表示一个命名空间声明。

一个命名空间声明包含一个[prefix](qxmlstreamnamespacedeclaration.html#prefix)（）和一个[namespaceUri](qxmlstreamnamespacedeclaration.html#namespaceUri)（ ） 。

* * *

## Method Documentation

```
QXmlStreamNamespaceDeclaration.__init__ (self)
```

创建一个空的命名空间声明。

```
QXmlStreamNamespaceDeclaration.__init__ (self, QXmlStreamNamespaceDeclaration)
```

创建副本_other_。

```
QXmlStreamNamespaceDeclaration.__init__ (self, QString prefix, QString namespaceUri)
```

创建一个命名空间声明与_prefix_和_namespaceUri_。

此功能被引入Qt的4.4 。

```
QStringRef QXmlStreamNamespaceDeclaration.namespaceUri (self)
```

返回的namespaceURI 。

```
QStringRef QXmlStreamNamespaceDeclaration.prefix (self)
```

返回前缀。

```
bool QXmlStreamNamespaceDeclaration.__eq__ (self, QXmlStreamNamespaceDeclaration other)
```

```
bool QXmlStreamNamespaceDeclaration.__ne__ (self, QXmlStreamNamespaceDeclaration other)
```