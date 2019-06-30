# QXmlStreamEntityResolver Class Reference

## [[QtCore](index.htm) module]

该QXmlStreamEntityResolver类提供了一个实体解析器的[QXmlStreamReader](qxmlstreamreader.html)。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QXmlStreamEntityResolver)`
*   `QString resolveUndeclaredEntity (self, QString name)`

* * *

## Detailed Description

该QXmlStreamEntityResolver类提供了一个实体解析器的[QXmlStreamReader](qxmlstreamreader.html)。

* * *

## Method Documentation

```
QXmlStreamEntityResolver.__init__ (self)
```

```
QXmlStreamEntityResolver.__init__ (self, QXmlStreamEntityResolver)
```

```
QString QXmlStreamEntityResolver.resolveUndeclaredEntity (self, QString name)
```

解决了未声明的实体_name_并返回其替换文本。如果实体也是未知的实体解析器，则返回一个空字符串。

默认的实现始终返回一个空字符串。