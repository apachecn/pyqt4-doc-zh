# QDomAttr Class Reference

## [[QtXml](index.htm) module]

该QDomAttr类表示的一个属性[QDomElement](qdomelement.html)。[More...](#details)

继承[QDomNode](qdomnode.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDomAttr x)`
*   `QString name (self)`
*   `QDomNode.NodeType nodeType (self)`
*   `QDomElement ownerElement (self)`
*   `setValue (self, QString)`
*   `bool specified (self)`
*   `QString value (self)`

* * *

## Detailed Description

该QDomAttr类表示的一个属性[QDomElement](qdomelement.html)。

例如，下面的XML片段的产生与没有孩子，但两个属性的元素：

```
 <link href="http://qt.nokia.com" color="red" />

```

您可以访问这样的代码元素的属性：

```
 [QDomElement](qdomelement.html) e = //...
 //...
 QDomAttr a = e.attributeNode("href");
 cout << a.value() << endl;                // prints "http://qt.nokia.com"
 a.setValue("http://qt.nokia.com/doc"); // change the node's attribute
 QDomAttr a2 = e.attributeNode("href");
 cout << a2.value() << endl;               // prints "http://qt.nokia.com/doc"

```

这个例子还表明，改变从一个元件接收的属性改变元素的属性。如果您不希望更改元素的属性的值必须使用[cloneNode](qdomnode.html#cloneNode)（ ）来获得属性的独立副本。

QDomAttr可以返回[name](qdomattr.html#name)（）和[value](qdomattr.html#value)一个属性（） 。一个属性的值设置[setValue](qdomattr.html#setValue)（ ） 。如果[specified](qdomattr.html#specified)（ ）返回True值被设置[setValue](qdomattr.html#setValue)（ ） 。该节点将该属性附加到（如果有的话）是由返回[ownerElement](qdomattr.html#ownerElement)（ ） 。

关于文档对象模型有进一步的信息[http://www.w3.org/TR/REC-DOM-Level-1/](http://www.w3.org/TR/REC-DOM-Level-1/)和[http://www.w3.org/TR/DOM-Level-2-Core/](http://www.w3.org/TR/DOM-Level-2-Core/)。对于更一般介绍的DOM实现的见[QDomDocument](qdomdocument.html)文档。

* * *

## Method Documentation

```
QDomAttr.__init__ (self)
```

构造一个空属性。

```
QDomAttr.__init__ (self, QDomAttr x)
```

构造的副本_x_。

副本的数据是共享的（浅拷贝） ：修改一个节点也将改变其他。如果你想使一个深拷贝，使用[cloneNode](qdomnode.html#cloneNode)（ ） 。

```
QString QDomAttr.name (self)
```

返回属性的名称。

```
QDomNode.NodeType QDomAttr.nodeType (self)
```

[](qdomnode.html#NodeType-enum)

[Returns](qdomnode.html#NodeType-enum) [AttributeNode](qdomnode.html#NodeType-enum)。

```
QDomElement QDomAttr.ownerElement (self)
```

[](qdomelement.html)

[返回此属性附加到或元素节点](qdomelement.html)[null node](qdomnode.html#isNull)如果这个属性没有连接到任何元素。

```
QDomAttr.setValue (self, QString)
```

设置该属性的值_v_。

**See also** [value](qdomattr.html#value)（ ） 。

```
bool QDomAttr.specified (self)
```

返回True如果该属性已设置用户使用[setValue](qdomattr.html#setValue)（ ） 。如果未指定或设置该值，则返回False 。

**See also** [setValue](qdomattr.html#setValue)（ ） 。

```
QString QDomAttr.value (self)
```

如果未指定该属性返回属性或空字符串的值。

**See also** [specified](qdomattr.html#specified)（）和[setValue](qdomattr.html#setValue)（ ） 。