# QDomNode Class Reference

## [[QtXml](index.htm) module]

该QDomNode类是在DOM树中所有节点的基类。[More...](#details)

通过继承[QDomAttr](qdomattr.html)，[QDomCharacterData](qdomcharacterdata.html)，[QDomDocument](qdomdocument.html)，[QDomDocumentFragment](qdomdocumentfragment.html)，[QDomDocumentType](qdomdocumenttype.html)，[QDomElement](qdomelement.html)，[QDomEntity](qdomentity.html)，[QDomEntityReference](qdomentityreference.html)，[QDomNotation](qdomnotation.html)和[QDomProcessingInstruction](qdomprocessinginstruction.html)。

### Types

*   `enum EncodingPolicy { EncodingFromDocument, EncodingFromTextStream }`
*   `enum NodeType { ElementNode, AttributeNode, TextNode, CDATASectionNode, ..., CharacterDataNode }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDomNode)`
*   `QDomNode appendChild (self, QDomNode newChild)`
*   `QDomNamedNodeMap attributes (self)`
*   `QDomNodeList childNodes (self)`
*   `clear (self)`
*   `QDomNode cloneNode (self, bool deep = True)`
*   `int columnNumber (self)`
*   `QDomNode firstChild (self)`
*   `QDomElement firstChildElement (self, QString tagName = QString())`
*   `bool hasAttributes (self)`
*   `bool hasChildNodes (self)`
*   `QDomNode insertAfter (self, QDomNode newChild, QDomNode refChild)`
*   `QDomNode insertBefore (self, QDomNode newChild, QDomNode refChild)`
*   `bool isAttr (self)`
*   `bool isCDATASection (self)`
*   `bool isCharacterData (self)`
*   `bool isComment (self)`
*   `bool isDocument (self)`
*   `bool isDocumentFragment (self)`
*   `bool isDocumentType (self)`
*   `bool isElement (self)`
*   `bool isEntity (self)`
*   `bool isEntityReference (self)`
*   `bool isNotation (self)`
*   `bool isNull (self)`
*   `bool isProcessingInstruction (self)`
*   `bool isSupported (self, QString feature, QString version)`
*   `bool isText (self)`
*   `QDomNode lastChild (self)`
*   `QDomElement lastChildElement (self, QString tagName = QString())`
*   `int lineNumber (self)`
*   `QString localName (self)`
*   `QDomNode namedItem (self, QString name)`
*   `QString namespaceURI (self)`
*   `QDomNode nextSibling (self)`
*   `QDomElement nextSiblingElement (self, QString tagName = QString())`
*   `QString nodeName (self)`
*   `NodeType nodeType (self)`
*   `QString nodeValue (self)`
*   `normalize (self)`
*   `QDomDocument ownerDocument (self)`
*   `QDomNode parentNode (self)`
*   `QString prefix (self)`
*   `QDomNode previousSibling (self)`
*   `QDomElement previousSiblingElement (self, QString tagName = QString())`
*   `QDomNode removeChild (self, QDomNode oldChild)`
*   `QDomNode replaceChild (self, QDomNode newChild, QDomNode oldChild)`
*   `save (self, QTextStream, int)`
*   `save (self, QTextStream, int, EncodingPolicy)`
*   `setNodeValue (self, QString)`
*   `setPrefix (self, QString pre)`
*   `QDomAttr toAttr (self)`
*   `QDomCDATASection toCDATASection (self)`
*   `QDomCharacterData toCharacterData (self)`
*   `QDomComment toComment (self)`
*   `QDomDocument toDocument (self)`
*   `QDomDocumentFragment toDocumentFragment (self)`
*   `QDomDocumentType toDocumentType (self)`
*   `QDomElement toElement (self)`
*   `QDomEntity toEntity (self)`
*   `QDomEntityReference toEntityReference (self)`
*   `QDomNotation toNotation (self)`
*   `QDomProcessingInstruction toProcessingInstruction (self)`
*   `QDomText toText (self)`

### Special Methods

*   `bool __eq__ (self, QDomNode)`
*   `bool __ne__ (self, QDomNode)`

* * *

## Detailed Description

该QDomNode类是在DOM树中所有节点的基类。

DOM中的许多函数返回一个QDomNode 。

你可以找出使用节点的类型[isAttr](qdomnode.html#isAttr)（ ）[isCDATASection](qdomnode.html#isCDATASection)（ ）[isDocumentFragment](qdomnode.html#isDocumentFragment)（ ）[isDocument](qdomnode.html#isDocument)（ ）[isDocumentType](qdomnode.html#isDocumentType)（ ）[isElement](qdomnode.html#isElement)（ ）[isEntityReference](qdomnode.html#isEntityReference)（ ）[isText](qdomnode.html#isText)（ ）[isEntity](qdomnode.html#isEntity)（ ）[isNotation](qdomnode.html#isNotation)（ ）[isProcessingInstruction](qdomnode.html#isProcessingInstruction)（ ）[isCharacterData](qdomnode.html#isCharacterData)（）和[isComment](qdomnode.html#isComment)（ ） 。

一个QDomNode可以使用转换成它的子类[toAttr](qdomnode.html#toAttr)（ ）[toCDATASection](qdomnode.html#toCDATASection)（ ）[toDocumentFragment](qdomnode.html#toDocumentFragment)（ ）[toDocument](qdomnode.html#toDocument)（ ）[toDocumentType](qdomnode.html#toDocumentType)（ ）[toElement](qdomnode.html#toElement)（ ）[toEntityReference](qdomnode.html#toEntityReference)（ ）[toText](qdomnode.html#toText)（ ）[toEntity](qdomnode.html#toEntity)（ ）[toNotation](qdomnode.html#toNotation)（ ）[toProcessingInstruction](qdomnode.html#toProcessingInstruction)（ ）[toCharacterData](qdomnode.html#toCharacterData)（）或[toComment](qdomnode.html#toComment)（ ） 。您可以将节点转换为一个空节点[clear](qdomnode.html#clear)（ ） 。

使用显式共享QDomNode类的副本共享他们的数据。这意味着修改一个节点会改变所有副本。这是结合特别有用，其职能返回QDomNode ，如[firstChild](qdomnode.html#firstChild)（ ） 。你可以使节点的独立（深）副本[cloneNode](qdomnode.html#cloneNode)（ ） 。

一个QDomNode可以为null ，很像一个空指针。创建一个空节点结果的副本在另一个空节点。这是不可能修改一个空节点，但也可以指定其他的，可能是非空节点到它。在这种情况下，空节点的拷贝将保持为空。您可以检查是否有QDomNode为null调用[isNull](qdomnode.html#isNull)（ ） 。一个QDomNode （或任何派生类）的空的构造函数创建一个空节点。

节点插入[insertBefore](qdomnode.html#insertBefore)（ ）[insertAfter](qdomnode.html#insertAfter)（）或[appendChild](qdomnode.html#appendChild)（ ） 。你可以用另一个替换一个节点使用[replaceChild](qdomnode.html#replaceChild)（ ）并删除与节点[removeChild](qdomnode.html#removeChild)（ ） 。

遍历节点使用[firstChild](qdomnode.html#firstChild)（）来获取一个节点的第一个孩子（如果有的话） ，并[nextSibling](qdomnode.html#nextSibling)（ ）遍历。 QDomNode还提供[lastChild](qdomnode.html#lastChild)（ ）[previousSibling](qdomnode.html#previousSibling)（）和[parentNode](qdomnode.html#parentNode)（ ） 。为了找到与特定节点名称使用的第一个子节点[namedItem](qdomnode.html#namedItem)（ ） 。

要找出如果一个节点有子使用[hasChildNodes](qdomnode.html#hasChildNodes)（ ），并得到所有的节点的子节点列表使用[childNodes](qdomnode.html#childNodes)（ ） 。

节点的名称和值（这取决于它的类型而变化的意思）被返回[nodeName](qdomnode.html#nodeName)（）和[nodeValue](qdomnode.html#nodeValue)（ ）分别。节点的类型是由返回[nodeType](qdomnode.html#nodeType)（ ） 。该节点的值可以与设置[setNodeValue](qdomnode.html#setNodeValue)（ ） 。

到节点所属的文档是由返回[ownerDocument](qdomnode.html#ownerDocument)（ ） 。

邻[QDomText](qdomtext.html)节点可以被合并成一个单一的节点[normalize](qdomnode.html#normalize)（ ） 。

[QDomElement](qdomelement.html)节点都可以被检索到的属性[attributes](qdomnode.html#attributes)（ ） 。

[QDomElement](qdomelement.html)和[QDomAttr](qdomattr.html)节点可以有哪些可以检索与命名空间[namespaceURI](qdomnode.html#namespaceURIx)（ ） 。他们的本地名称与检索[localName](qdomnode.html#localName)（） ，以及它们与前缀[prefix](qdomnode.html#prefix)（ ） 。前缀可以被设置[setPrefix](qdomnode.html#setPrefix)（ ） 。

您可以写节点的XML表示文本流[save](qdomnode.html#save)（ ） 。

下面的例子查找XML文档中的第一个元素，并打印所有属于它的直接子元素的名称。

```
 [QDomDocument](qdomdocument.html) d;
 d.setContent(someXML);
 QDomNode n = d.firstChild();
 while (!n.isNull()) {
     if (n.isElement()) {
         [QDomElement](qdomelement.html) e = n.toElement();
         cout << "Element name: " << e.tagName() << endl;
         break;
     }
     n = n.nextSibling();
 }

```

关于文档对象模型有进一步的信息[Level 1](http://www.w3.org/TR/REC-DOM-Level-1/)和[Level 2 Core](http://www.w3.org/TR/DOM-Level-2-Core/)。对于更一般介绍的DOM实现的见[QDomDocument](qdomdocument.html)文档。

* * *

## Type Documentation

```
QDomNode.EncodingPolicy
```

此枚举指定如何[QDomNode.save](qdomnode.html#save)（）确定序列化时使用何种编码。

| Constant | Value | Description |
| --- | --- | --- |
| `QDomNode.EncodingFromDocument` | `1` | 该编码是从文件中取出。 |
| `QDomNode.EncodingFromTextStream` | `2` | 该编码是从取出[QTextStream](qtextstream.html)。 |

另见的过载[save](qdomnode.html#save)（ ）函数，它接受一个EncodingPolicy 。

这个枚举被引入或修改的Qt 4.3 。

```
QDomNode.NodeType
```

这个枚举变量定义了节点的类型：

| Constant | Value | Description |
| --- | --- | --- |
| `QDomNode.ElementNode` | `1` |   |
| `QDomNode.AttributeNode` | `2` |   |
| `QDomNode.TextNode` | `3` |   |
| `QDomNode.CDATASectionNode` | `4` |   |
| `QDomNode.EntityReferenceNode` | `5` |   |
| `QDomNode.EntityNode` | `6` |   |
| `QDomNode.ProcessingInstructionNode` | `7` |   |
| `QDomNode.CommentNode` | `8` |   |
| `QDomNode.DocumentNode` | `9` |   |
| `QDomNode.DocumentTypeNode` | `10` |   |
| `QDomNode.DocumentFragmentNode` | `11` |   |
| `QDomNode.NotationNode` | `12` |   |
| `QDomNode.BaseNode` | `21` | A [QDomNode](qdomnode.html)对象，即，不是一个[QDomNode](qdomnode.html)子类。 |
| `QDomNode.CharacterDataNode` | `22` |   |

* * *

## Method Documentation

```
QDomNode.__init__ (self)
```

构造一个[null](qdomnode.html#isNull)节点。

```
QDomNode.__init__ (self, QDomNode)
```

构造的副本_n_。

副本的数据是共享的（浅拷贝） ：修改一个节点也将改变其他。如果你想使一个深拷贝，使用[cloneNode](qdomnode.html#cloneNode)（ ） 。

```
QDomNode QDomNode.appendChild (self, QDomNode newChild)
```

[

追加可_newChild_作为节点的最后一个子。

If _newChild_是另一个节点的子节点，它被重设父到该节点。如果_newChild_是这个节点的子节点，然后其在儿童中的列表中的位置被改变。

](qdomnode.html)

[If _newChild_是](qdomnode.html)[QDomDocumentFragment](qdomdocumentfragment.html)，然后该片段的孩子从片段取出并追加。

If _newChild_是[QDomElement](qdomelement.html)与该节点是[QDomDocument](qdomdocument.html)已经有一个元素节点作为一个孩子，_newChild_不添加作为一个孩子，一个空节点返回。

返回一个新的参考_newChild_成功或[null node](qdomnode.html#isNull)失败。

一个空节点（创建，例如，使用默认构造函数）在调用该函数不执行任何操作，并返回一个[null node](qdomnode.html#isNull)。

DOM规范不允许插入属性节点，但由于历史的原因， QDom接受他们无论如何。

**See also** [insertBefore](qdomnode.html#insertBefore)（ ）[insertAfter](qdomnode.html#insertAfter)（ ）[replaceChild](qdomnode.html#replaceChild)（）和[removeChild](qdomnode.html#removeChild)（ ） 。

```
QDomNamedNodeMap QDomNode.attributes (self)
```

[](qdomnamednodemap.html)

[将返回所有属性的命名节点图。仅提供了属性](qdomnamednodemap.html)[QDomElement](qdomelement.html)秒。

变更的属性的映射也将改变这个属性[QDomNode](qdomnode.html)。

```
QDomNodeList QDomNode.childNodes (self)
```

[

将返回所有直接子节点的列表。

](qdomnodelist.html)

[大多数情况下你都会调用这个函数的](qdomnodelist.html)[QDomElement](qdomelement.html)对象。

例如，如果XML文件看起来像这样：

```
 <body>
 <h1>Heading</h1>
 <p>Hello <b>you</b></p>
 </body>

```

那么对于“身体”元素的子节点列表将包含由\u003ch1\u003e标记，并由\u003cp\u003e标籤创建的节点创建的节点。

在列表中的节点不会被复制，所以改变列表中的节点也将改变这个节点的子节点。

**See also** [firstChild](qdomnode.html#firstChild)（）和[lastChild](qdomnode.html#lastChild)（ ） 。

```
QDomNode.clear (self)
```

转换节点，进入一个空节点，如果它不是一个空节点之前，它的类型和内容将被删除。

**See also** [isNull](qdomnode.html#isNull)（ ） 。

```
QDomNode QDomNode.cloneNode (self, bool deep = True)
```

[](qdomnode.html)

[创建的一个深（不浅）副本](qdomnode.html)[QDomNode](qdomnode.html)。

If _deep_是真的，那么克隆完成递归这意味着所有节点的子节点是深复制了。如果_deep_是假的只有节点本身被复制，并且复制将没有子节点。

```
int QDomNode.columnNumber (self)
```

对于由创建节点[QDomDocument.setContent](qdomdocument.html#setContent)（ ） ，这个函数返回的节点被解析的XML文档中的列数。否则，返回-1 。

这个函数是Qt 4.1中引入。

**See also** [lineNumber](qdomnode.html#lineNumber)（）和[QDomDocument.setContent](qdomdocument.html#setContent)（ ） 。

```
QDomNode QDomNode.firstChild (self)
```

[](qdomnode.html)

[返回节点的第一个孩子。如果不存在子节点时，一](qdomnode.html)[null node](qdomnode.html#isNull)返回。更改返回的节点也将改变在文档树中的节点。

**See also** [lastChild](qdomnode.html#lastChild)（）和[childNodes](qdomnode.html#childNodes)（ ） 。

```
QDomElement QDomNode.firstChildElement (self, QString tagName = QString())
```

[

返回与标记名称的第一个子元素_tagName_如果标记名非空，否则返回第一个子元素。返回如果没有这样的孩子存在一个空元素。

](qdomelement.html)

[**See also**](qdomelement.html) [lastChildElement](qdomnode.html#lastChildElement)（ ）[previousSiblingElement](qdomnode.html#previousSiblingElement)（）和[nextSiblingElement](qdomnode.html#nextSiblingElement)（ ） 。

```
bool QDomNode.hasAttributes (self)
```

返回True如果节点有属性，否则返回False 。

**See also** [attributes](qdomnode.html#attributes)（ ） 。

```
bool QDomNode.hasChildNodes (self)
```

返回True如果节点有一个或更多的孩子，否则返回False 。

```
QDomNode QDomNode.insertAfter (self, QDomNode newChild, QDomNode refChild)
```

[](qdomnode.html)

[插入节点_newChild_子节点之后_refChild_。_refChild_必须是此节点的直接子。如果_refChild_ is](qdomnode.html) [null](qdomnode.html#isNull)然后_newChild_被追加为这个节点的最后一个子节点。

If _newChild_是另一个节点的子节点，它被重设父到该节点。如果_newChild_是这个节点的子节点，然后其在儿童中的列表中的位置被改变。

If _newChild_是[QDomDocumentFragment](qdomdocumentfragment.html)，然后该片段的孩子从片段除去后插入_refChild_。

返回一个新的参考_newChild_成功或[null node](qdomnode.html#isNull)失败。

DOM规范不允许插入属性节点，但由于历史的原因QDom接受他们不过。

**See also** [insertBefore](qdomnode.html#insertBefore)（ ）[replaceChild](qdomnode.html#replaceChild)（ ）[removeChild](qdomnode.html#removeChild)（）和[appendChild](qdomnode.html#appendChild)（ ） 。

```
QDomNode QDomNode.insertBefore (self, QDomNode newChild, QDomNode refChild)
```

[](qdomnode.html)

[插入节点_newChild_该子节点之前_refChild_。_refChild_必须是此节点的直接子。如果_refChild_ is](qdomnode.html) [null](qdomnode.html#isNull)然后_newChild_插入为节点的第一个孩子。

If _newChild_是另一个节点的子节点，它被重设父到该节点。如果_newChild_是这个节点的子节点，然后其在儿童中的列表中的位置被改变。

If _newChild_是[QDomDocumentFragment](qdomdocumentfragment.html)，然后该片段的孩子从片段取出并插入前_refChild_。

返回一个新的参考_newChild_成功或[null node](qdomnode.html#isNull)失败。

DOM规范不允许插入属性节点，但由于历史的原因QDom接受他们不过。

**See also** [insertAfter](qdomnode.html#insertAfter)（ ）[replaceChild](qdomnode.html#replaceChild)（ ）[removeChild](qdomnode.html#removeChild)（）和[appendChild](qdomnode.html#appendChild)（ ） 。

```
bool QDomNode.isAttr (self)
```

返回True如果该节点是一个属性，否则返回False 。

如果这个函数返回True ，这并不意味着该对象是一个QDomAttribute ，你可以得到QDomAttribute与toAttribute （ ） 。

**See also** [toAttr](qdomnode.html#toAttr)（ ） 。

```
bool QDomNode.isCDATASection (self)
```

返回True如果该节点是一个CDATA部分，否则返回False 。

如果这个函数返回True ，这并不意味着该对象是一个[QDomCDATASection](qdomcdatasection.html)，你可以得到[QDomCDATASection](qdomcdatasection.html)同[toCDATASection](qdomnode.html#toCDATASection)（ ） 。

**See also** [toCDATASection](qdomnode.html#toCDATASection)（ ） 。

```
bool QDomNode.isCharacterData (self)
```

返回True如果该节点是一个字符数据节点，否则返回False 。

如果这个函数返回True ，这并不意味着该对象是一个[QDomCharacterData](qdomcharacterdata.html)，你可以得到[QDomCharacterData](qdomcharacterdata.html)同[toCharacterData](qdomnode.html#toCharacterData)（ ） 。

**See also** [toCharacterData](qdomnode.html#toCharacterData)（ ） 。

```
bool QDomNode.isComment (self)
```

返回True如果该节点是注释，否则返回False 。

如果这个函数返回True ，这并不意味着该对象是一个[QDomComment](qdomcomment.html)，你可以得到[QDomComment](qdomcomment.html)同[toComment](qdomnode.html#toComment)（ ） 。

**See also** [toComment](qdomnode.html#toComment)（ ） 。

```
bool QDomNode.isDocument (self)
```

返回True如果该节点是一个文件，否则返回False 。

如果这个函数返回True ，这并不意味着该对象是一个[QDomDocument](qdomdocument.html)，你可以得到[QDomDocument](qdomdocument.html)同[toDocument](qdomnode.html#toDocument)（ ） 。

**See also** [toDocument](qdomnode.html#toDocument)（ ） 。

```
bool QDomNode.isDocumentFragment (self)
```

返回True如果该节点是文档片段，否则返回False 。

如果这个函数返回True ，这并不意味着该对象是一个[QDomDocumentFragment](qdomdocumentfragment.html)，你可以得到[QDomDocumentFragment](qdomdocumentfragment.html)同[toDocumentFragment](qdomnode.html#toDocumentFragment)（ ） 。

**See also** [toDocumentFragment](qdomnode.html#toDocumentFragment)（ ） 。

```
bool QDomNode.isDocumentType (self)
```

返回True如果该节点是一个文档类型，否则返回False 。

如果这个函数返回True ，这并不意味着该对象是一个[QDomDocumentType](qdomdocumenttype.html)，你可以得到[QDomDocumentType](qdomdocumenttype.html)同[toDocumentType](qdomnode.html#toDocumentType)（ ） 。

**See also** [toDocumentType](qdomnode.html#toDocumentType)（ ） 。

```
bool QDomNode.isElement (self)
```

返回True如果该节点是一个元素，否则返回False 。

如果这个函数返回True ，这并不意味着该对象是一个[QDomElement](qdomelement.html)，你可以得到[QDomElement](qdomelement.html)同[toElement](qdomnode.html#toElement)（ ） 。

**See also** [toElement](qdomnode.html#toElement)（ ） 。

```
bool QDomNode.isEntity (self)
```

返回True如果该节点是一个实体，否则返回False 。

如果这个函数返回True ，这并不意味着该对象是一个[QDomEntity](qdomentity.html)，你可以得到[QDomEntity](qdomentity.html)同[toEntity](qdomnode.html#toEntity)（ ） 。

**See also** [toEntity](qdomnode.html#toEntity)（ ） 。

```
bool QDomNode.isEntityReference (self)
```

返回True如果该节点是一个实体引用，否则返回False 。

如果这个函数返回True ，这并不意味着该对象是一个[QDomEntityReference](qdomentityreference.html)，你可以得到[QDomEntityReference](qdomentityreference.html)同[toEntityReference](qdomnode.html#toEntityReference)（ ） 。

**See also** [toEntityReference](qdomnode.html#toEntityReference)（ ） 。

```
bool QDomNode.isNotation (self)
```

返回True如果该节点是一个符号，否则返回False 。

如果这个函数返回True ，这并不意味着该对象是一个[QDomNotation](qdomnotation.html)，你可以得到[QDomNotation](qdomnotation.html)同[toNotation](qdomnode.html#toNotation)（ ） 。

**See also** [toNotation](qdomnode.html#toNotation)（ ） 。

```
bool QDomNode.isNull (self)
```

如果此节点为空，则返回True （即，如果它没有类型或内容），否则返回False 。

```
bool QDomNode.isProcessingInstruction (self)
```

返回True如果该节点是一个处理指令，否则返回False 。

如果这个函数返回True ，这并不意味着该对象是一个[QDomProcessingInstruction](qdomprocessinginstruction.html)，你可以得到QProcessingInstruction与[toProcessingInstruction](qdomnode.html#toProcessingInstruction)（ ） 。

**See also** [toProcessingInstruction](qdomnode.html#toProcessingInstruction)（ ） 。

```
bool QDomNode.isSupported (self, QString feature, QString version)
```

DOM实现是否实现该功能，则返回True_feature_而这个功能是支持在版本这个节点_version_否则返回False 。

**See also** [QDomImplementation.hasFeature](qdomimplementation.html#hasFeature)（ ） 。

```
bool QDomNode.isText (self)
```

返回True如果该节点是一个文本节点，否则返回False 。

如果这个函数返回True ，这并不意味着该对象是一个[QDomText](qdomtext.html)，你可以得到[QDomText](qdomtext.html)同[toText](qdomnode.html#toText)（ ） 。

**See also** [toText](qdomnode.html#toText)（ ） 。

```
QDomNode QDomNode.lastChild (self)
```

[](qdomnode.html)

[返回节点的最后一个子。如果不存在子节点时，一](qdomnode.html)[null node](qdomnode.html#isNull)返回。更改返回的节点也将改变在文档树中的节点。

**See also** [firstChild](qdomnode.html#firstChild)（）和[childNodes](qdomnode.html#childNodes)（ ） 。

```
QDomElement QDomNode.lastChildElement (self, QString tagName = QString())
```

[

返回最后一个子元素与标籤名_tagName_如果标记名非空，否则返回最后一个子元素。返回如果没有这样的孩子存在一个空元素。

](qdomelement.html)

[**See also**](qdomelement.html) [firstChildElement](qdomnode.html#firstChildElement)（ ）[previousSiblingElement](qdomnode.html#previousSiblingElement)（）和[nextSiblingElement](qdomnode.html#nextSiblingElement)（ ） 。

```
int QDomNode.lineNumber (self)
```

对于由创建节点[QDomDocument.setContent](qdomdocument.html#setContent)（ ） ，这个函数返回的节点被解析的XML文档中的行号。否则，返回-1 。

这个函数是Qt 4.1中引入。

**See also** [columnNumber](qdomnode.html#columnNumber)（）和[QDomDocument.setContent](qdomdocument.html#setContent)（ ） 。

```
QString QDomNode.localName (self)
```

如果节点使用命名空间，这个函数返回节点的本地名称，否则返回一个空字符串。

类型的唯一节点[ElementNode](qdomnode.html#NodeType-enum) or [AttributeNode](qdomnode.html#NodeType-enum)可以有命名空间。命名空间必须被指定在创建时，它是不可能事后添加的命名空间。

[QDomDocument.createAttributeNS](qdomdocument.html#createAttributeNS)（ ）

**See also** [prefix](qdomnode.html#prefix)（ ）[namespaceURI](qdomnode.html#namespaceURIx)（）和[QDomDocument.createElementNS](qdomdocument.html#createElementNS)（ ） 。

```
QDomNode QDomNode.namedItem (self, QString name)
```

[](qdomnode.html)

[返回的第一个直接子节点](qdomnode.html)[nodeName](qdomnode.html#nodeName)（ ）等于_name_。

如果没有这样的直接子存在，一[null node](qdomnode.html#isNull)返回。

**See also** [nodeName](qdomnode.html#nodeName)（ ） 。

```
QString QDomNode.namespaceURI (self)
```

```
QDomNode QDomNode.nextSibling (self)
```

[

返回在文档树中的下一个同级。更改返回的节点也将改变在文档树中的节点。

如果你有这样的XML ：

```
 <h1>Heading</h1>
 <p>The text...</p>
 <h2>Next heading</h2>

```

](qdomnode.html)

[这](qdomnode.html)[QDomNode](qdomnode.html)代表\u003cp\u003e标籤， nextSibling （ ）将返回一个代表该\u003cH2\u003e标籤的节点。

**See also** [previousSibling](qdomnode.html#previousSibling)（ ） 。

```
QDomElement QDomNode.nextSiblingElement (self, QString tagName = QString())
```

[

返回下一个同级元素与标籤名_tagName_如果_tagName_非空，否则返回任何一个同级元素。返回如果没有这样的兄弟姐妹存在一个空元素。

](qdomelement.html)

[**See also**](qdomelement.html) [firstChildElement](qdomnode.html#firstChildElement)（ ）[previousSiblingElement](qdomnode.html#previousSiblingElement)（）和[lastChildElement](qdomnode.html#lastChildElement)（ ） 。

```
QString QDomNode.nodeName (self)
```

返回节点的名称。

这个名字的含义依赖于子类：

| Name | Meaning |
| --- | --- |
| [QDomAttr](qdomattr.html) | The name of the attribute |
| [QDomCDATASection](qdomcdatasection.html) | The string "#cdata-section" |
| [QDomComment](qdomcomment.html) | The string "#comment" |
| [QDomDocument](qdomdocument.html) | The string "#document" |
| [QDomDocumentFragment](qdomdocumentfragment.html) | The string "#document-fragment" |
| [QDomDocumentType](qdomdocumenttype.html) | The name of the document type |
| [QDomElement](qdomelement.html) | The tag name |
| [QDomEntity](qdomentity.html) | The name of the entity |
| [QDomEntityReference](qdomentityreference.html) | The name of the referenced entity |
| [QDomNotation](qdomnotation.html) | The name of the notation |
| [QDomProcessingInstruction](qdomprocessinginstruction.html) | The target of the processing instruction |
| [QDomText](qdomtext.html) | The string "#text" |

**Note:**处理元素和属性节点的名称时，此功能不采取命名空间的存在考虑。因此，返回的名称可以包含任何命名空间前缀可能存在。为了获得一个元素或属性的节点名，使用[localName](qdomnode.html#localName)（）;获得命名空间前缀，使用[namespaceURI](qdomnode.html#namespaceURIx)（ ） 。

**See also** [nodeValue](qdomnode.html#nodeValue)（ ） 。

```
NodeType QDomNode.nodeType (self)
```

[

返回节点的类型。

](qdomnode.html#NodeType-enum)

[**See also**](qdomnode.html#NodeType-enum) [toAttr](qdomnode.html#toAttr)（ ）[toCDATASection](qdomnode.html#toCDATASection)（ ）[toDocumentFragment](qdomnode.html#toDocumentFragment)（ ）[toDocument](qdomnode.html#toDocument)（ ）[toDocumentType](qdomnode.html#toDocumentType)（ ）[toElement](qdomnode.html#toElement)（ ）[toEntityReference](qdomnode.html#toEntityReference)（ ）[toText](qdomnode.html#toText)（ ）[toEntity](qdomnode.html#toEntity)（ ）[toNotation](qdomnode.html#toNotation)（ ）[toProcessingInstruction](qdomnode.html#toProcessingInstruction)（ ）[toCharacterData](qdomnode.html#toCharacterData)（）和[toComment](qdomnode.html#toComment)（ ） 。

```
QString QDomNode.nodeValue (self)
```

返回节点的值。

该值的含义依赖于子类：

| Name | Meaning |
| --- | --- |
| [QDomAttr](qdomattr.html) | The attribute value |
| [QDomCDATASection](qdomcdatasection.html) | The content of the CDATA section |
| [QDomComment](qdomcomment.html) | The comment |
| [QDomProcessingInstruction](qdomprocessinginstruction.html) | The data of the processing instruction |
| [QDomText](qdomtext.html) | The text |

所有其他子类没有一个节点值，将返回一个空字符串。

**See also** [setNodeValue](qdomnode.html#setNodeValue)（）和[nodeName](qdomnode.html#nodeName)（ ） 。

```
QDomNode.normalize (self)
```

调用正常化（ ）的元素及其所有子转换成标准格式。这意味着相邻的[QDomText](qdomtext.html)对象将被合并成一个单一的文本对象（[QDomCDATASection](qdomcdatasection.html)节点未合并） 。

```
QDomDocument QDomNode.ownerDocument (self)
```

[

返回此节点所属的文档。

](qdomdocument.html)

```
QDomNode QDomNode.parentNode (self)
```

[](qdomnode.html)

[返回父节点。如果该节点没有父级，则返回一个空节点（即该节点](qdomnode.html)[isNull](qdomnode.html#isNull)（ ）返回True ） 。

```
QString QDomNode.prefix (self)
```

返回节点或空字符串的命名空间前缀，如果该节点没有命名空间前缀。

类型的唯一节点[ElementNode](qdomnode.html#NodeType-enum) or [AttributeNode](qdomnode.html#NodeType-enum)可以有命名空间。命名空间前缀必须在创建时指定。如果一个节点是用命名空间前缀创建的，则可以在以后改变它[setPrefix](qdomnode.html#setPrefix)（ ） 。

如果您创建一个元素或属性[QDomDocument.createElement](qdomdocument.html#createElement)（）或[QDomDocument.createAttribute](qdomdocument.html#createAttribute)（ ） ，前缀将是一个空字符串。如果你使用[QDomDocument.createElementNS](qdomdocument.html#createElementNS)（）或[QDomDocument.createAttributeNS](qdomdocument.html#createAttributeNS)（）代替，前缀不会是一个空字符串，但它可能是一个空字符串，如果该名称没有前缀。

[QDomDocument.createElementNS](qdomdocument.html#createElementNS)（ ）[QDomDocument.createAttributeNS](qdomdocument.html#createAttributeNS)（ ）

**See also** [setPrefix](qdomnode.html#setPrefix)（ ）[localName](qdomnode.html#localName)（）和[namespaceURI](qdomnode.html#namespaceURIx)（ ） 。

```
QDomNode QDomNode.previousSibling (self)
```

[

返回在文档树中的前一个同级。更改返回的节点也将改变在文档树中的节点。

例如，如果你有这样的XML ：

```
 <h1>Heading</h1>
 <p>The text...</p>
 <h2>Next heading</h2>

```

](qdomnode.html)

[这](qdomnode.html)[QDomNode](qdomnode.html)代表\u003cp\u003e标籤， previousSibling （ ）将返回一个代表该\u003ch1\u003e标记的节点。

**See also** [nextSibling](qdomnode.html#nextSibling)（ ） 。

```
QDomElement QDomNode.previousSiblingElement (self, QString tagName = QString())
```

[

返回前sibilng元素与标籤名_tagName_如果_tagName_非空，否则返回任何一个同级元素。返回如果没有这样的兄弟姐妹存在一个空元素。

](qdomelement.html)

[**See also**](qdomelement.html) [firstChildElement](qdomnode.html#firstChildElement)（ ）[nextSiblingElement](qdomnode.html#nextSiblingElement)（）和[lastChildElement](qdomnode.html#lastChildElement)（ ） 。

```
QDomNode QDomNode.removeChild (self, QDomNode oldChild)
```

[

移除_oldChild_从孩子的列表。_oldChild_必须是此节点的直接子。

](qdomnode.html)

[返回一个新的参考_oldChild_成功或](qdomnode.html)[null node](qdomnode.html#isNull)失败。

**See also** [insertBefore](qdomnode.html#insertBefore)（ ）[insertAfter](qdomnode.html#insertAfter)（ ）[replaceChild](qdomnode.html#replaceChild)（）和[appendChild](qdomnode.html#appendChild)（ ） 。

```
QDomNode QDomNode.replaceChild (self, QDomNode newChild, QDomNode oldChild)
```

[

替换_oldChild_同_newChild_。_oldChild_必须是此节点的直接子。

If _newChild_是另一个节点的子节点，它被重设父到该节点。如果_newChild_是这个节点的子节点，然后其在儿童中的列表中的位置被改变。

](qdomnode.html)

[If _newChild_是](qdomnode.html)[QDomDocumentFragment](qdomdocumentfragment.html)，然后_oldChild_被替换的所有片段的孩子。

返回一个新的参考_oldChild_成功或[null node](qdomnode.html#isNull)一个失败。

**See also** [insertBefore](qdomnode.html#insertBefore)（ ）[insertAfter](qdomnode.html#insertAfter)（ ）[removeChild](qdomnode.html#removeChild)（）和[appendChild](qdomnode.html#appendChild)（ ） 。

```
QDomNode.save (self, QTextStream, int)
```

写入节点的XML表示形式及其所有子到流_str_。此函数使用_indent_作为空间缩进量的节点。

如果这个节点是一个文档节点，文本流的编码_str_的编码是由名为“ xml”的治疗处理指令的XML声明，如果这样的人存在，否则默认为UTF - 8设置。 XML声明不是处理指令，但存在由于历史原因，这个行为。如果这个节点不是一个文档节点，文本流的编码。

如果文档中包含无效的XML字符或不能在给定的编码进行编码的字符，结果和行为是不确定的。

```
QDomNode.save (self, QTextStream, int, EncodingPolicy)
```

If _encodingPolicy_ is [QDomNode.EncodingFromDocument](qdomnode.html#EncodingPolicy-enum)这个函数的作用是保存（[QTextStream](qtextstream.html)＆海峡，诠释缩进） 。

If _encodingPolicy_ is [EncodingFromTextStream](qdomnode.html#EncodingPolicy-enum)而这个节点是一个文档节点，这个函数的行为就像保存（[QTextStream](qtextstream.html)＆海峡，诠释缩进）除了在文本流中指定的编码_str_被使用。

如果文档中包含无效的XML字符或不能在给定的编码进行编码的字符，结果和行为是不确定的。

这个函数中引入了Qt 4.2中。

```
QDomNode.setNodeValue (self, QString)
```

设置节点的值_v_。

**See also** [nodeValue](qdomnode.html#nodeValue)（ ） 。

```
QDomNode.setPrefix (self, QString pre)
```

如果该节点有一个命名空间前缀，这个功能改变了节点的命名空间前缀_pre_。否则，这个函数不执行任何操作。

类型的唯一节点[ElementNode](qdomnode.html#NodeType-enum) or [AttributeNode](qdomnode.html#NodeType-enum)可以有命名空间。命名空间前缀必须要在创建时指定的，它是不可能添加一个命名空间前缀之后。

[QDomDocument.createElementNS](qdomdocument.html#createElementNS)（ ）[QDomDocument.createAttributeNS](qdomdocument.html#createAttributeNS)（ ）

**See also** [prefix](qdomnode.html#prefix)（ ）[localName](qdomnode.html#localName)（）和[namespaceURI](qdomnode.html#namespaceURIx)（ ） 。

```
QDomAttr QDomNode.toAttr (self)
```

[](qdomattr.html)

[将一个](qdomattr.html)[QDomNode](qdomnode.html)成[QDomAttr](qdomattr.html)。如果节点不是一个属性，返回的对象将是[null](qdomnode.html#isNull)。

**See also** [isAttr](qdomnode.html#isAttr)（ ） 。

```
QDomCDATASection QDomNode.toCDATASection (self)
```

[](qdomcdatasection.html)

[将一个](qdomcdatasection.html)[QDomNode](qdomnode.html)成[QDomCDATASection](qdomcdatasection.html)。如果该节点不是一个CDATA节，返回的对象将是[null](qdomnode.html#isNull)。

**See also** [isCDATASection](qdomnode.html#isCDATASection)（ ） 。

```
QDomCharacterData QDomNode.toCharacterData (self)
```

[](qdomcharacterdata.html)

[将一个](qdomcharacterdata.html)[QDomNode](qdomnode.html)成[QDomCharacterData](qdomcharacterdata.html)。如果该节点不是一个字符数据节点返回的对象将是[null](qdomnode.html#isNull)。

**See also** [isCharacterData](qdomnode.html#isCharacterData)（ ） 。

```
QDomComment QDomNode.toComment (self)
```

[](qdomcomment.html)

[将一个](qdomcomment.html)[QDomNode](qdomnode.html)成[QDomComment](qdomcomment.html)。如果该节点是不是注释返回的对象将是[null](qdomnode.html#isNull)。

**See also** [isComment](qdomnode.html#isComment)（ ） 。

```
QDomDocument QDomNode.toDocument (self)
```

[](qdomdocument.html)

[将一个](qdomdocument.html)[QDomNode](qdomnode.html)成[QDomDocument](qdomdocument.html)。如果该节点不是文档返回的对象将是[null](qdomnode.html#isNull)。

**See also** [isDocument](qdomnode.html#isDocument)（ ） 。

```
QDomDocumentFragment QDomNode.toDocumentFragment (self)
```

[](qdomdocumentfragment.html)

[将一个](qdomdocumentfragment.html)[QDomNode](qdomnode.html)成[QDomDocumentFragment](qdomdocumentfragment.html)。如果该节点不是一个文档片段返回的对象将是[null](qdomnode.html#isNull)。

**See also** [isDocumentFragment](qdomnode.html#isDocumentFragment)（ ） 。

```
QDomDocumentType QDomNode.toDocumentType (self)
```

[](qdomdocumenttype.html)

[将一个](qdomdocumenttype.html)[QDomNode](qdomnode.html)成[QDomDocumentType](qdomdocumenttype.html)。如果该节点不是文档类型返回的对象将是[null](qdomnode.html#isNull)。

**See also** [isDocumentType](qdomnode.html#isDocumentType)（ ） 。

```
QDomElement QDomNode.toElement (self)
```

[](qdomelement.html)

[将一个](qdomelement.html)[QDomNode](qdomnode.html)成[QDomElement](qdomelement.html)。如果节点不是元素返回的对象将是[null](qdomnode.html#isNull)。

**See also** [isElement](qdomnode.html#isElement)（ ） 。

```
QDomEntity QDomNode.toEntity (self)
```

[](qdomentity.html)

[将一个](qdomentity.html)[QDomNode](qdomnode.html)成[QDomEntity](qdomentity.html)。如果节点不是一个实体返回的对象将是[null](qdomnode.html#isNull)。

**See also** [isEntity](qdomnode.html#isEntity)（ ） 。

```
QDomEntityReference QDomNode.toEntityReference (self)
```

[](qdomentityreference.html)

[将一个](qdomentityreference.html)[QDomNode](qdomnode.html)成[QDomEntityReference](qdomentityreference.html)。如果节点不是一个实体引用，返回的对象将是[null](qdomnode.html#isNull)。

**See also** [isEntityReference](qdomnode.html#isEntityReference)（ ） 。

```
QDomNotation QDomNode.toNotation (self)
```

[](qdomnotation.html)

[将一个](qdomnotation.html)[QDomNode](qdomnode.html)成[QDomNotation](qdomnotation.html)。如果该节点不是一个符号返回的对象将是[null](qdomnode.html#isNull)。

**See also** [isNotation](qdomnode.html#isNotation)（ ） 。

```
QDomProcessingInstruction QDomNode.toProcessingInstruction (self)
```

[](qdomprocessinginstruction.html)

[将一个](qdomprocessinginstruction.html)[QDomNode](qdomnode.html)成[QDomProcessingInstruction](qdomprocessinginstruction.html)。如果节点不是处理指令返回的对象将是[null](qdomnode.html#isNull)。

**See also** [isProcessingInstruction](qdomnode.html#isProcessingInstruction)（ ） 。

```
QDomText QDomNode.toText (self)
```

[](qdomtext.html)

[将一个](qdomtext.html)[QDomNode](qdomnode.html)成[QDomText](qdomtext.html)。如果该节点不是文本，返回的对象将是[null](qdomnode.html#isNull)。

**See also** [isText](qdomnode.html#isText)（ ） 。

```
bool QDomNode.__eq__ (self, QDomNode)
```

```
bool QDomNode.__ne__ (self, QDomNode)
```