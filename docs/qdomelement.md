# QDomElement Class Reference

## [[QtXml](index.htm) module]

该QDomElement类表示的DOM树中的元素。[More...](#details)

继承[QDomNode](qdomnode.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDomElement x)`
*   `QString attribute (self, QString name, QString defaultValue = QString())`
*   `QDomAttr attributeNode (self, QString name)`
*   `QDomAttr attributeNodeNS (self, QString nsURI, QString localName)`
*   `QString attributeNS (self, QString nsURI, QString localName, QString defaultValue = QString())`
*   `QDomNamedNodeMap attributes (self)`
*   `QDomNodeList elementsByTagName (self, QString tagname)`
*   `QDomNodeList elementsByTagNameNS (self, QString nsURI, QString localName)`
*   `bool hasAttribute (self, QString name)`
*   `bool hasAttributeNS (self, QString nsURI, QString localName)`
*   `QDomNode.NodeType nodeType (self)`
*   `removeAttribute (self, QString name)`
*   `QDomAttr removeAttributeNode (self, QDomAttr oldAttr)`
*   `removeAttributeNS (self, QString nsURI, QString localName)`
*   `setAttribute (self, QString name, QString value)`
*   `setAttribute (self, QString name, int value)`
*   `setAttribute (self, QString name, int value)`
*   `setAttribute (self, QString name, float value)`
*   `setAttribute (self, QString name, int value)`
*   `QDomAttr setAttributeNode (self, QDomAttr newAttr)`
*   `QDomAttr setAttributeNodeNS (self, QDomAttr newAttr)`
*   `setAttributeNS (self, QString nsURI, QString qName, QString value)`
*   `setAttributeNS (self, QString nsURI, QString qName, int value)`
*   `setAttributeNS (self, QString nsURI, QString qName, int value)`
*   `setAttributeNS (self, QString nsURI, QString qName, float value)`
*   `setAttributeNS (self, QString nsURI, QString qName, int value)`
*   `setTagName (self, QString name)`
*   `QString tagName (self)`
*   `QString text (self)`

* * *

## Detailed Description

该QDomElement类表示的DOM树中的元素。

元素有一个[tagName](qdomelement.html#tagName)（）和与它们相关联的零个或多个属性。变量名可以被改变[setTagName](qdomelement.html#setTagName)（ ） 。

元素属性表示为[QDomAttr](qdomattr.html)可以使用查询对象的[attribute](qdomelement.html#attributex)（）和[attributeNode](qdomelement.html#attributeNode)（）函数。您可以设置的属性与[setAttribute](qdomelement.html#setAttribute)（）和[setAttributeNode](qdomelement.html#setAttributeNode)（）函数。属性可以用去除[removeAttribute](qdomelement.html#removeAttribute)（ ） 。有命名空间的等值这些功能，即[setAttributeNS](qdomelement.html#setAttributeNS)（ ）[setAttributeNodeNS](qdomelement.html#setAttributeNodeNS)（）和[removeAttributeNS](qdomelement.html#removeAttributeNS)（ ） 。

如果您要访问的节点使用的文字[text](qdomelement.html#text)（ ），例如

```
 QDomElement e = //...
 //...
 [QString](qstring.html) s = e.text()

```

该[text](qdomelement.html#text)（ ）函数的递归操作要查找的文本（因为不是所有的元素包含文本）。如果你想找到的所有的节点的子节点的所有文字，迭代孩子找[QDomText](qdomtext.html)节点，例如

```
 [QString](qstring.html) text;
 QDomElement element = doc.documentElement();
 for([QDomNode](qdomnode.html) n = element.firstChild(); !n.isNull(); n = n.nextSibling())
 {
     [QDomText](qdomtext.html) t = n.toText();
     if (!t.isNull())
         text += t.data();
 }

```

需要注意的是，我们试图给每个节点转换为文本节点，并使用[text](qdomelement.html#text)（） ，而不是使用[firstChild](qdomnode.html#firstChild)（ ） 。[toText](qdomnode.html#toText)（ ）数据（ ）或n 。[toText](qdomnode.html#toText)（） 。数据（）直接在节点上，因为节点可能不是一个文本元素。

你可以得到一个元素的所有那些与一个指定的标记名称的decendents列表[elementsByTagName](qdomelement.html#elementsByTagName)（）或[elementsByTagNameNS](qdomelement.html#elementsByTagNameNS)（ ） 。

要浏览一个DOM文档使用的元素[firstChildElement](qdomnode.html#firstChildElement)（ ）[lastChildElement](qdomnode.html#lastChildElement)（ ）[nextSiblingElement](qdomnode.html#nextSiblingElement)（）和[previousSiblingElement](qdomnode.html#previousSiblingElement)（ ） 。例如，迭代中被称为“数据库”根元素称为“入口”的所有子元素，你可以使用：

```
 [QDomDocument](qdomdocument.html) doc = // ...
 QDomElement root = doc.firstChildElement("database");
 QDomElement elt = root.firstChildElement("entry");
 for (; !elt.isNull(); elt = elt.nextSiblingElement("entry")) {
     // ...
 }

```

关于文档对象模型有进一步的信息[Level 1](http://www.w3.org/TR/REC-DOM-Level-1/)和[Level 2 Core](http://www.w3.org/TR/DOM-Level-2-Core/)。对于更一般介绍的DOM实现的见[QDomDocument](qdomdocument.html)文档。

* * *

## Method Documentation

```
QDomElement.__init__ (self)
```

构造一个空元素。使用[QDomDocument.createElement](qdomdocument.html#createElement)（ ）函数来构造与内容元素。

```
QDomElement.__init__ (self, QDomElement x)
```

构造的副本_x_。

副本的数据是共享的（浅拷贝） ：修改一个节点也将改变其他。如果你想使一个深拷贝，使用[cloneNode](qdomnode.html#cloneNode)（ ） 。

```
QString QDomElement.attribute (self, QString name, QString defaultValue = QString())
```

```
QDomAttr QDomElement.attributeNode (self, QString name)
```

[](qdomattr.html)

[返回](qdomattr.html)[QDomAttr](qdomattr.html)对应于所谓的属性对象_name_。如果没有这样的属性存在一[null attribute](qdomnode.html#isNull)返回。

**See also** [setAttributeNode](qdomelement.html#setAttributeNode)（ ）[attribute](qdomelement.html#attributex)（ ）[setAttribute](qdomelement.html#setAttribute)（）和[attributeNodeNS](qdomelement.html#attributeNodeNS)（ ） 。

```
QDomAttr QDomElement.attributeNodeNS (self, QString nsURI, QString localName)
```

[](qdomattr.html)

[返回](qdomattr.html)[QDomAttr](qdomattr.html)对应于属性的本地名称对象_localName_和命名空间URI_nsURI_。如果没有这样的属性存在一[null attribute](qdomnode.html#isNull)返回。

**See also** [setAttributeNodeNS](qdomelement.html#setAttributeNodeNS)（ ）[setAttributeNode](qdomelement.html#setAttributeNode)（ ）[attribute](qdomelement.html#attributex)（）和[setAttribute](qdomelement.html#setAttribute)（ ） 。

```
QString QDomElement.attributeNS (self, QString nsURI, QString localName, QString defaultValue = QString())
```

返回与本地名属性_localName_和命名空间URI_nsURI_。如果属性不存在_defValue_返回。

**See also** [setAttributeNS](qdomelement.html#setAttributeNS)（ ）[attributeNodeNS](qdomelement.html#attributeNodeNS)（ ）[setAttributeNodeNS](qdomelement.html#setAttributeNodeNS)（）和[attribute](qdomelement.html#attributex)（ ） 。

```
QDomNamedNodeMap QDomElement.attributes (self)
```

[](qdomnamednodemap.html)

[返回](qdomnamednodemap.html)[QDomNamedNodeMap](qdomnamednodemap.html)包含此元素的所有属性。

**See also** [attribute](qdomelement.html#attributex)（ ）[setAttribute](qdomelement.html#setAttribute)（ ）[attributeNode](qdomelement.html#attributeNode)（）和[setAttributeNode](qdomelement.html#setAttributeNode)（ ） 。

```
QDomNodeList QDomElement.elementsByTagName (self, QString tagname)
```

[](qdomnodelist.html)

[返回](qdomnodelist.html)[QDomNodeList](qdomnodelist.html)含命名该元素的所有后代_tagname_在子树中的元素与此元素为根的前序遍历遇到。在返回列表中的元素的顺序是它们的前序遍历过程中出现的顺序。

**See also** [elementsByTagNameNS](qdomelement.html#elementsByTagNameNS)（）和[QDomDocument.elementsByTagName](qdomdocument.html#elementsByTagName)（ ） 。

```
QDomNodeList QDomElement.elementsByTagNameNS (self, QString nsURI, QString localName)
```

[](qdomnodelist.html)

[返回](qdomnodelist.html)[QDomNodeList](qdomnodelist.html)包含此元素的所有后代与当地名_localName_和命名空间URI_nsURI_在子树中的元素与此元素为根的前序遍历遇到。在返回列表中的元素的顺序是它们的前序遍历过程中出现的顺序。

**See also** [elementsByTagName](qdomelement.html#elementsByTagName)（）和[QDomDocument.elementsByTagNameNS](qdomdocument.html#elementsByTagNameNS)（ ） 。

```
bool QDomElement.hasAttribute (self, QString name)
```

如果此元素有一个名为属性，则返回True_name_否则返回False 。

**Note:**这个功能并不需要命名空间的存在考虑。因此，指定的名称将针对完全合格的属性名，包括任何命名空间前缀可能存在的测试。

使用[hasAttributeNS](qdomelement.html#hasAttributeNS)（）来为特定的命名空间和名称的属性明确地测试。

```
bool QDomElement.hasAttributeNS (self, QString nsURI, QString localName)
```

如果此元素具有与当地名称的属性，则返回True_localName_和命名空间URI_nsURI_否则返回False 。

```
QDomNode.NodeType QDomElement.nodeType (self)
```

[

Returns `ElementNode`。

```
QDomElement.removeAttribute (self, QString name)
```

消除了所谓的属性名称_name_从这个项目。

](qdomnode.html#NodeType-enum)

[**See also**](qdomnode.html#NodeType-enum) [setAttribute](qdomelement.html#setAttribute)（ ）[attribute](qdomelement.html#attributex)（）和[removeAttributeNS](qdomelement.html#removeAttributeNS)（ ） 。

```
QDomAttr QDomElement.removeAttributeNode (self, QDomAttr oldAttr)
```

[

移除属性_oldAttr_从元素并返回它。

](qdomattr.html)

[**See also**](qdomattr.html) [attributeNode](qdomelement.html#attributeNode)（）和[setAttributeNode](qdomelement.html#setAttributeNode)（ ） 。

```
QDomElement.removeAttributeNS (self, QString nsURI, QString localName)
```

删除该属性的本地名称_localName_和命名空间URI_nsURI_从这个项目。

**See also** [setAttributeNS](qdomelement.html#setAttributeNS)（ ）[attributeNS](qdomelement.html#attributeNS)（）和[removeAttribute](qdomelement.html#removeAttribute)（ ） 。

```
QDomElement.setAttribute (self, QString name, QString value)
```

添加称为属性_name_与价值_value_。如果具有相同名称的属性存在，它的值被替换_value_。

**See also** [attribute](qdomelement.html#attributex)（ ）[setAttributeNode](qdomelement.html#setAttributeNode)（）和[setAttributeNS](qdomelement.html#setAttributeNS)（ ） 。

```
QDomElement.setAttribute (self, QString name, int value)
```

这是一个重载函数。

数是根据当前的区域设置。

```
QDomElement.setAttribute (self, QString name, int value)
```

这是一个重载函数。

数是根据当前的区域设置。

```
QDomElement.setAttribute (self, QString name, float value)
```

这是一个重载函数。

数是根据当前的区域设置。

```
QDomElement.setAttribute (self, QString name, int value)
```

这是一个重载函数。

数是根据当前的区域设置。

```
QDomAttr QDomElement.setAttributeNode (self, QDomAttr newAttr)
```

[

添加属性_newAttr_此元素。

](qdomattr.html)

[如果该元件具有一个具有相同名称的另一个属性_newAttr_，这个函数替换该属性并返回它，否则该函数返回一个](qdomattr.html)[null attribute](qdomnode.html#isNull)。

**See also** [attributeNode](qdomelement.html#attributeNode)（ ）[setAttribute](qdomelement.html#setAttribute)（）和[setAttributeNodeNS](qdomelement.html#setAttributeNodeNS)（ ） 。

```
QDomAttr QDomElement.setAttributeNodeNS (self, QDomAttr newAttr)
```

[

添加属性_newAttr_此元素。

](qdomattr.html)

[如果元素具有具有相同的本地名称和命名空间URI作为另一个属性_newAttr_，这个函数替换该属性并返回它，否则该函数返回一个](qdomattr.html)[null attribute](qdomnode.html#isNull)。

**See also** [attributeNodeNS](qdomelement.html#attributeNodeNS)（ ）[setAttributeNS](qdomelement.html#setAttributeNS)（）和[setAttributeNode](qdomelement.html#setAttributeNode)（ ） 。

```
QDomElement.setAttributeNS (self, QString nsURI, QString qName, QString value)
```

添加具有限定名称的属性_qName_和命名空间URI_nsURI_与该值_value_。如果具有相同的本地名称和名称空间URI存在的属性，它的前缀被替换的前缀_qName_其值由repaced_value_。

虽然_qName_是合格的名称，本地名称是用来决定是否将现有属性的值应及时更换。

**See also** [attributeNS](qdomelement.html#attributeNS)（ ）[setAttributeNodeNS](qdomelement.html#setAttributeNodeNS)（）和[setAttribute](qdomelement.html#setAttribute)（ ） 。

```
QDomElement.setAttributeNS (self, QString nsURI, QString qName, int value)
```

这是一个重载函数。

```
QDomElement.setAttributeNS (self, QString nsURI, QString qName, int value)
```

这是一个重载函数。

```
QDomElement.setAttributeNS (self, QString nsURI, QString qName, float value)
```

这是一个重载函数。

```
QDomElement.setAttributeNS (self, QString nsURI, QString qName, int value)
```

这是一个重载函数。

```
QDomElement.setTagName (self, QString name)
```

设置此元素的标籤名_name_。

**See also** [tagName](qdomelement.html#tagName)（ ） 。

```
QString QDomElement.tagName (self)
```

返回此元素的标籤名称。对于这样的一个XML元素：

```
 <img src="myimg.png">

```

标记名会返回“ IMG ” 。

**See also** [setTagName](qdomelement.html#setTagName)（ ） 。

```
QString QDomElement.text (self)
```

返回元素的文本或空字符串。

例如：

```
 <h1>Hello <b>[Qt](qt.html)</b> <![CDATA[<xml is cool>]]></h1>

```

的功能文本（ ）[QDomElement](qdomelement.html)为`&lt;h1&gt;`标籤，将返回以下文本：

```
 Hello [Qt](qt.html) <xml is cool>

```

注释此函数忽略。只计算[QDomText](qdomtext.html)和[QDomCDATASection](qdomcdatasection.html)对象。