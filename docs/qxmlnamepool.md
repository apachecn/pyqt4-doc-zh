# QXmlNamePool Class Reference

## [[QtXmlPatterns](index.htm) module]

该QXmlNamePool类是通过实例引用的共享字符串表[QXmlName](qxmlname.html)。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QXmlNamePool other)`

* * *

## Detailed Description

该QXmlNamePool类是通过实例引用的共享字符串表[QXmlName](qxmlname.html)。

QXmlNamePool用于优化操作的实例[QXmlName](qxmlname.html)。实例[QXmlName](qxmlname.html)代表的方式，允许进行比较，有效地绕过该XML名称的XML名称。的效率是通过存储包括在QXmlNamePool ，在那里它们被映射到二进制标识符，然后将其填充入被存储在一个键的一个实例的XML名称的字符串来实现[QXmlName](qxmlname.html)。

这意味着它们的每个实例[QXmlName](qxmlname.html)连接到它与创建名池，这个名字池应保持在范围和用于创建的所有实例[QXmlName](qxmlname.html)可能进行比较。还需要注意的是，如果你必须重构的名字池所需的[QXmlName](qxmlname.html)为文本，或者如果你必须访问其任何组件串，所以虽然实例[QXmlName](qxmlname.html)可以未经名字池相比，名义池必须保持在范围内，如果该名称的字符串必须在稍后访问。

* * *

## Method Documentation

```
QXmlNamePool.__init__ (self)
```

构造一个空名称池。

```
QXmlNamePool.__init__ (self, QXmlNamePool other)
```

构造的一个副本_other_命名池。