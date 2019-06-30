# QDomDocument Class Reference

## [[QtXml](index.htm) module]

该QDomDocument类表示XML文档。[More...](#details)

继承[QDomNode](qdomnode.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QString name)`
*   `__init__ (self, QDomDocumentType doctype)`
*   `__init__ (self, QDomDocument x)`
*   `QDomAttr createAttribute (self, QString name)`
*   `QDomAttr createAttributeNS (self, QString nsURI, QString qName)`
*   `QDomCDATASection createCDATASection (self, QString data)`
*   `QDomComment createComment (self, QString data)`
*   `QDomDocumentFragment createDocumentFragment (self)`
*   `QDomElement createElement (self, QString tagName)`
*   `QDomElement createElementNS (self, QString nsURI, QString qName)`
*   `QDomEntityReference createEntityReference (self, QString name)`
*   `QDomProcessingInstruction createProcessingInstruction (self, QString target, QString data)`
*   `QDomText createTextNode (self, QString data)`
*   `QDomDocumentType doctype (self)`
*   `QDomElement documentElement (self)`
*   `QDomElement elementById (self, QString elementId)`
*   `QDomNodeList elementsByTagName (self, QString tagname)`
*   `QDomNodeList elementsByTagNameNS (self, QString nsURI, QString localName)`
*   `QDomImplementation implementation (self)`
*   `QDomNode importNode (self, QDomNode importedNode, bool deep)`
*   `QDomNode.NodeType nodeType (self)`
*   `(bool, QString errorMsg, int errorLine, int errorColumn) setContent (self, QByteArray data, bool namespaceProcessing)`
*   `(bool, QString errorMsg, int errorLine, int errorColumn) setContent (self, QString text, bool namespaceProcessing)`
*   `(bool, QString errorMsg, int errorLine, int errorColumn) setContent (self, QIODevice dev, bool namespaceProcessing)`
*   `(bool, QString errorMsg, int errorLine, int errorColumn) setContent (self, QXmlInputSource source, bool namespaceProcessing)`
*   `(bool, QString errorMsg, int errorLine, int errorColumn) setContent (self, QByteArray buffer)`
*   `(bool, QString errorMsg, int errorLine, int errorColumn) setContent (self, QString text)`
*   `(bool, QString errorMsg, int errorLine, int errorColumn) setContent (self, QIODevice dev)`
*   `(bool, QString errorMsg, int errorLine, int errorColumn) setContent (self, QXmlInputSource source, QXmlReader reader)`
*   `QByteArray toByteArray (self, int indent = 1)`
*   `QString toString (self, int indent = 1)`

* * *

## Detailed Description

该QDomDocument类表示XML文档。

该QDomDocument类代表整个XML文档。从概念上讲，它是文档树的根，并提供主要访问到文档的数据。

由于元素，文本节点，注释，处理指令等，不能在文档的上下文之外存在，文件类还包含创建这些对象所需的工厂函数。创建节点对象有一个[ownerDocument](qdomnode.html#ownerDocument)（ ）函数并将它们与在文档的背景下，他们创建的。将使用DOM类最经常是[QDomNode](qdomnode.html)， QDomDocument ，[QDomElement](qdomelement.html)和[QDomText](qdomtext.html)。

解析后的XML是由可以使用各种QDom类访问对象树内部表示。只有所有QDom类_reference_在内部树的对象。一旦引用他们和QDomDocument本身最后QDom对象被删除在DOM树中的内部对象会被删除。

完成创作元素，文本节点等的使用在这个类中提供的各种工厂的功能。使用QDom类的默认构造函数只会造成无法操纵或插入到文档中的空对象。

该QDomDocument类有多种功能，用于创建文件的数据，例如，[createElement](qdomdocument.html#createElement)（ ）[createTextNode](qdomdocument.html#createTextNode)（ ）[createComment](qdomdocument.html#createComment)（ ）[createCDATASection](qdomdocument.html#createCDATASection)（ ）[createProcessingInstruction](qdomdocument.html#createProcessingInstruction)（ ）[createAttribute](qdomdocument.html#createAttribute)（）和[createEntityReference](qdomdocument.html#createEntityReference)（ ） 。其中的一些功能有支持命名空间的版本，即[createElementNS](qdomdocument.html#createElementNS)（）和[createAttributeNS](qdomdocument.html#createAttributeNS)（ ） 。该[createDocumentFragment](qdomdocument.html#createDocumentFragment)（）函数是用于保存文件的部分，这是用于操作复杂的文件是有用的。

该文件的整个内容设置与[setContent](qdomdocument.html#setContent)（ ） 。这个函数解析它通过为XML文档的字符串，并创建DOM树，代表该文件。使用根元素可用[documentElement](qdomdocument.html#documentElement)（ ） 。可使用获得的文件的文字表述[toString](qdomdocument.html#toString)（ ） 。

**Note:**DOM树可能最终保留了大量的内存，如果XML文档是很大的。对于大的XML文档，[QXmlStreamReader](qxmlstreamreader.html)或[QXmlQuery](qxmlquery.html)类可能是更好的解决方案。

它可以使用插入来自另一个文档中的节点插入到文档中[importNode](qdomdocument.html#importNode)（ ） 。

可以得到所有具有带有特定标记的元素的列表[elementsByTagName](qdomdocument.html#elementsByTagName)（）或与[elementsByTagNameNS](qdomdocument.html#elementsByTagNameNS)（ ） 。

该QDom类通常使用如下：

```
 QDomDocument doc("mydocument");
 [QFile](qfile.html) file("mydocument.xml");
 if (!file.open([QIODevice](qiodevice.html).ReadOnly))
     return;
 if (!doc.setContent(&file)) {
     file.close();
     return;
 }
 file.close();

 // print out the element names of all elements that are direct children
 // of the outermost element.
 [QDomElement](qdomelement.html) docElem = doc.documentElement();

 [QDomNode](qdomnode.html) n = docElem.firstChild();
 while(!n.isNull()) {
     [QDomElement](qdomelement.html) e = n.toElement(); // try to convert the node to an element.
     if(!e.isNull()) {
         cout << qPrintable(e.tagName()) << endl; // the node really is an element.
     }
     n = n.nextSibling();
 }

 // Here we append a new element to the end of the document
 [QDomElement](qdomelement.html) elem = doc.createElement("img");
 elem.setAttribute("src", "myimage.png");
 docElem.appendChild(elem);

```

一旦`doc`和`elem`走出去的范围，表示XML文档的整个内部树被删除。

若要使用这样的DOM代码使用的文件：

```
 QDomDocument doc("MyML");
 [QDomElement](qdomelement.html) root = doc.createElement("MyML");
 doc.appendChild(root);

 [QDomElement](qdomelement.html) tag = doc.createElement("Greeting");
 root.appendChild(tag);

 [QDomText](qdomtext.html) t = doc.createTextNode("Hello World");
 tag.appendChild(t);

 [QString](qstring.html) xml = doc.toString();

```

关于文档对象模型更多信息，请参阅文档对象模型（DOM ）[Level 1](http://www.w3.org/TR/REC-DOM-Level-1/)和[Level 2 Core](http://www.w3.org/TR/DOM-Level-2-Core/)规格。

* * *

## Method Documentation

```
QDomDocument.__init__ (self)
```

构造一个空文档。

```
QDomDocument.__init__ (self, QString name)
```

创建文档并设置文档类型的名称_name_。

```
QDomDocument.__init__ (self, QDomDocumentType doctype)
```

创建具有文档类型的文档_doctype_。

**See also** [QDomImplementation.createDocumentType](qdomimplementation.html#createDocumentType)（ ） 。

```
QDomDocument.__init__ (self, QDomDocument x)
```

构造的副本_x_。

副本的数据是共享的（浅拷贝） ：修改一个节点也将改变其他。如果你想使一个深拷贝，使用[cloneNode](qdomnode.html#cloneNode)（ ） 。

```
QDomAttr QDomDocument.createAttribute (self, QString name)
```

[](qdomattr.html)

[创建一个名为新的属性_name_该可插入一个元素，例如运用](qdomattr.html)[QDomElement.setAttributeNode](qdomelement.html#setAttributeNode)（ ） 。

If _name_是不是一个有效的XML名称，这个函数的行为受约束[QDomImplementation.InvalidDataPolicy](qdomimplementation.html#InvalidDataPolicy-enum)。

**See also** [createAttributeNS](qdomdocument.html#createAttributeNS)（ ） 。

```
QDomAttr QDomDocument.createAttributeNS (self, QString nsURI, QString qName)
```

[](qdomattr.html)

[创建一个具有可插入一个元素的命名空间支持一个新的属性。该属性的名称是_qName_和命名空间URI为_nsURI_。该功能还将](qdomattr.html)[QDomNode.prefix](qdomnode.html#prefix)（）和[QDomNode.localName](qdomnode.html#localName)（ ）为适当的值（取决于_qName_） 。

If _qName_是不是一个有效的XML名称，这个函数的行为受约束[QDomImplementation.InvalidDataPolicy](qdomimplementation.html#InvalidDataPolicy-enum)。

**See also** [createAttribute](qdomdocument.html#createAttribute)（ ） 。

```
QDomCDATASection QDomDocument.createCDATASection (self, QString data)
```

[](qdomcdatasection.html)

[创建字符串一个新的CDATA节_value_能够被插入到文档中，例如运用](qdomcdatasection.html)[QDomNode.appendChild](qdomnode.html#appendChild)（ ） 。

If _value_包含不能被存储在一个CDATA节的字符，这个函数的行为受约束[QDomImplementation.InvalidDataPolicy](qdomimplementation.html#InvalidDataPolicy-enum)。

**See also** [QDomNode.appendChild](qdomnode.html#appendChild)（ ）[QDomNode.insertBefore](qdomnode.html#insertBefore)（）和[QDomNode.insertAfter](qdomnode.html#insertAfter)（ ） 。

```
QDomComment QDomDocument.createComment (self, QString data)
```

[](qdomcomment.html)

[创建字符串新评论_value_能够被插入到文档中，例如运用](qdomcomment.html)[QDomNode.appendChild](qdomnode.html#appendChild)（ ） 。

If _value_包含不能被存储在XML注释字符，这个函数的行为受约束[QDomImplementation.InvalidDataPolicy](qdomimplementation.html#InvalidDataPolicy-enum)。

**See also** [QDomNode.appendChild](qdomnode.html#appendChild)（ ）[QDomNode.insertBefore](qdomnode.html#insertBefore)（）和[QDomNode.insertAfter](qdomnode.html#insertAfter)（ ） 。

```
QDomDocumentFragment QDomDocument.createDocumentFragment (self)
```

[

创建一个新的文档片段，可用于保存文件的部分，例如做文档树的复杂的操作时。

](qdomdocumentfragment.html)

```
QDomElement QDomDocument.createElement (self, QString tagName)
```

[](qdomelement.html)

[创建一个名为新元素_tagName_能够被插入到DOM树中，例如运用](qdomelement.html)[QDomNode.appendChild](qdomnode.html#appendChild)（ ） 。

If _tagName_是不是一个有效的XML名称，这个函数的行为受约束[QDomImplementation.InvalidDataPolicy](qdomimplementation.html#InvalidDataPolicy-enum)。

[QDomNode.insertAfter](qdomnode.html#insertAfter)（ ）

**See also** [createElementNS](qdomdocument.html#createElementNS)（ ）[QDomNode.appendChild](qdomnode.html#appendChild)（）和[QDomNode.insertBefore](qdomnode.html#insertBefore)（ ） 。

```
QDomElement QDomDocument.createElementNS (self, QString nsURI, QString qName)
```

[](qdomelement.html)

[创建一个具有可插入到DOM树中的命名空间支持的新元素。元素的名称是_qName_和命名空间URI为_nsURI_。该功能还将](qdomelement.html)[QDomNode.prefix](qdomnode.html#prefix)（）和[QDomNode.localName](qdomnode.html#localName)（ ）为适当的值（取决于_qName_） 。

If _qName_是一个空字符串，返回一个空元素不管无效的数据策略是否被设置。

**See also** [createElement](qdomdocument.html#createElement)（ ） 。

```
QDomEntityReference QDomDocument.createEntityReference (self, QString name)
```

[](qdomentityreference.html)

[创建一个名为一个新的实体引用_name_能够被插入到文档中，例如运用](qdomentityreference.html)[QDomNode.appendChild](qdomnode.html#appendChild)（ ） 。

If _name_是不是一个有效的XML名称，这个函数的行为受约束[QDomImplementation.InvalidDataPolicy](qdomimplementation.html#InvalidDataPolicy-enum)。

**See also** [QDomNode.appendChild](qdomnode.html#appendChild)（ ）[QDomNode.insertBefore](qdomnode.html#insertBefore)（）和[QDomNode.insertAfter](qdomnode.html#insertAfter)（ ） 。

```
QDomProcessingInstruction QDomDocument.createProcessingInstruction (self, QString target, QString data)
```

[](qdomprocessinginstruction.html)

[创建一个新的处理指令可以被插入到文档中，例如运用](qdomprocessinginstruction.html)[QDomNode.appendChild](qdomnode.html#appendChild)（ ） 。此功能设置为处理指令的目标_target_以及将数据_data_。

If _target_是不是一个有效的XML名称，或者数据，如果包含不能出现在一个处理指令字符，这个函数的行为受约束[QDomImplementation.InvalidDataPolicy](qdomimplementation.html#InvalidDataPolicy-enum)。

**See also** [QDomNode.appendChild](qdomnode.html#appendChild)（ ）[QDomNode.insertBefore](qdomnode.html#insertBefore)（）和[QDomNode.insertAfter](qdomnode.html#insertAfter)（ ） 。

```
QDomText QDomDocument.createTextNode (self, QString data)
```

[](qdomtext.html)

[创建字符串的文本节点_value_能够被插入到文档树，例如运用](qdomtext.html)[QDomNode.appendChild](qdomnode.html#appendChild)（ ） 。

If _value_包含不能被保存为一个XML文档（即使在字符引用的形式）的字符数据的字符，这个函数的行为受约束[QDomImplementation.InvalidDataPolicy](qdomimplementation.html#InvalidDataPolicy-enum)。

**See also** [QDomNode.appendChild](qdomnode.html#appendChild)（ ）[QDomNode.insertBefore](qdomnode.html#insertBefore)（）和[QDomNode.insertAfter](qdomnode.html#insertAfter)（ ） 。

```
QDomDocumentType QDomDocument.doctype (self)
```

[

返回此文件的文件类型。

](qdomdocumenttype.html)

```
QDomElement QDomDocument.documentElement (self)
```

[

返回文档的根元素。

](qdomelement.html)

```
QDomElement QDomDocument.elementById (self, QString elementId)
```

[](qdomelement.html)

[返回其ID等于元件_elementId_。如果被发现与ID号的元素，这个函数返回一个](qdomelement.html)[null element](qdomnode.html#isNull)。

由于QDomClasses不知道哪个属性是元素的ID ，这个函数返回一个永远[null element](qdomnode.html#isNull)。这可能会改变在未来的版本。

```
QDomNodeList QDomDocument.elementsByTagName (self, QString tagname)
```

[](qdomnodelist.html)

[返回](qdomnodelist.html)[QDomNodeList](qdomnodelist.html)，包含所有文件中的名称元素_tagname_。节点列表的顺序是它们在元素树的先序遍历出现的顺序。

**See also** [elementsByTagNameNS](qdomdocument.html#elementsByTagNameNS)（）和[QDomElement.elementsByTagName](qdomelement.html#elementsByTagName)（ ） 。

```
QDomNodeList QDomDocument.elementsByTagNameNS (self, QString nsURI, QString localName)
```

[](qdomnodelist.html)

[返回](qdomnodelist.html)[QDomNodeList](qdomnodelist.html)包含所有的文件与本地名称的元素_localName_和命名空间的URI_nsURI_。节点列表的顺序是它们在元素树的先序遍历出现的顺序。

**See also** [elementsByTagName](qdomdocument.html#elementsByTagName)（）和[QDomElement.elementsByTagNameNS](qdomelement.html#elementsByTagNameNS)（ ） 。

```
QDomImplementation QDomDocument.implementation (self)
```

[](qdomimplementation.html)

[返回](qdomimplementation.html)[QDomImplementation](qdomimplementation.html)对象。

```
QDomNode QDomDocument.importNode (self, QDomNode importedNode, bool deep)
```

[

进口的节点_importedNode_从另一个文件于本文件。_importedNode_仍然在原始文档中，该函数创建一个可以在此文档中使用的副本。

](qdomnode.html)

[该函数返回输入节点属于这个文件。返回的节点没有父。这是不可能的导入](qdomnode.html)[QDomDocument](qdomdocument.html)和[QDomDocumentType](qdomdocumenttype.html)节点。在这种情况下，该函数返回一个[null node](qdomnode.html#isNull)。

If _deep_诚然，这个功能的进口不仅节点_importedNode_但它的整个子树，如果它是假的，只有_importedNode_是进口的。这个论点_deep_有对无影响[QDomAttr](qdomattr.html)和[QDomEntityReference](qdomentityreference.html)节点，因为的后代[QDomAttr](qdomattr.html)节点总是进口和那些[QDomEntityReference](qdomentityreference.html)节点永远不会进口。

此函数的行为是稍有不同，这取决于节点类型：

| Node Type | Behavior |
| --- | --- |
| [QDomAttr](qdomattr.html) | The owner element is set to 0 and the specified flag is set to true in the generated attribute. The whole subtree of _importedNode_ is always imported for attribute nodes: _deep_ has no effect. |
| [QDomDocument](qdomdocument.html) | Document nodes cannot be imported. |
| [QDomDocumentFragment](qdomdocumentfragment.html) | If _deep_ is true, this function imports the whole document fragment; otherwise it only generates an empty document fragment. |
| [QDomDocumentType](qdomdocumenttype.html) | Document type nodes cannot be imported. |
| [QDomElement](qdomelement.html) | Attributes for which [QDomAttr.specified](qdomattr.html#specified)() is true are also imported, other attributes are not imported. If _deep_ is true, this function also imports the subtree of _importedNode_; otherwise it imports only the element node (and some attributes, see above). |
| [QDomEntity](qdomentity.html) | Entity nodes can be imported, but at the moment there is no way to use them since the document type is read-only in DOM level 2. |
| [QDomEntityReference](qdomentityreference.html) | Descendants of entity reference nodes are never imported: _deep_ has no effect. |
| [QDomNotation](qdomnotation.html) | Notation nodes can be imported, but at the moment there is no way to use them since the document type is read-only in DOM level 2. |
| [QDomProcessingInstruction](qdomprocessinginstruction.html) | The target and value of the processing instruction is copied to the new node. |
| [QDomText](qdomtext.html) | The text is copied to the new node. |
| [QDomCDATASection](qdomcdatasection.html) | The text is copied to the new node. |
| [QDomComment](qdomcomment.html) | The text is copied to the new node. |

[QDomNode.insertAfter](qdomnode.html#insertAfter)（ ）[QDomNode.replaceChild](qdomnode.html#replaceChild)（ ）[QDomNode.removeChild](qdomnode.html#removeChild)（ ）[QDomNode.appendChild](qdomnode.html#appendChild)（ ）

**See also** [QDomElement.setAttribute](qdomelement.html#setAttribute)（）和[QDomNode.insertBefore](qdomnode.html#insertBefore)（ ） 。

```
QDomNode.NodeType QDomDocument.nodeType (self)
```

[

Returns `DocumentNode`。

```
(bool, QString errorMsg, int errorLine, int errorColumn) QDomDocument.setContent (self, QByteArray data, bool namespaceProcessing)
```

该函数从字节数组解析XML文档_data_并且将其设置为文件的内容。它会尝试检测文件的编码所要求的XML规范。

If _namespaceProcessing_诚然，解析器识别命名空间的XML文件中，并设置前缀名，本地名称和命名空间URI为适当的值。如果_namespaceProcessing_是假的，解析器确实没有命名空间的处理时，它读取XML文件。

](qdomnode.html#NodeType-enum)

[如果出现语法错误，这个函数返回False ，并且错误信息被放置在`*`_errorMsg_中的行号`*`_errorLine_并且在列号`*`_errorColumn_（除非相关指针设置为0 ） ，否则该函数返回True。各种错误信息的描述](qdomnode.html#NodeType-enum)[QXmlParseException](qxmlparseexception.html)类文档。需要注意的是，如果你想显示这些错误信息到您的应用程序的用户，他们将，除非他们明确地翻译英文显示。

If _namespaceProcessing_为真时，函数[QDomNode.prefix](qdomnode.html#prefix)（ ）返回一个字符串的所有元素和属性。它返回一个空字符串，如果该元素或属性没有前缀。

空白只包括文本节点被剥离，而不会出现在[QDomDocument](qdomdocument.html)。如果这种行为是不是需要，可以使用使用setContent （）重载，允许[QXmlReader](qxmlreader.html)要被提供。

If _namespaceProcessing_是假的，功能[QDomNode.prefix](qdomnode.html#prefix)（ ）[QDomNode.localName](qdomnode.html#localName)（）和[QDomNode.namespaceURI](qdomnode.html#namespaceURIx)（ ）返回一个空字符串。

实体引用的处理方式如下：

*   References to internal general entities and character entities occurring in the content are included. The result is a [QDomText](qdomtext.html) node with the references replaced by their corresponding entity values.
*   References to parameter entities occurring in the internal subset are included. The result is a [QDomDocumentType](qdomdocumenttype.html) node which contains entity and notation declarations with the references replaced by their corresponding entity values.
*   Any general parsed entity reference which is not defined in the internal subset and which occurs in the content is represented as a [QDomEntityReference](qdomentityreference.html) node.
*   Any parsed entity reference which is not defined in the internal subset and which occurs outside of the content is replaced with an empty string.
*   Any unparsed entity reference is replaced with an empty string.

[QDomNode.prefix](qdomnode.html#prefix)（ ）[QString.isNull](qstring.html#isNull)（ ）[QString.isEmpty](qstring.html#isEmpty)（ ）

**Warning:**此功能不[reentrant](index.htm#reentrant)。

**See also** [QDomNode.namespaceURI](qdomnode.html#namespaceURIx)（）和[QDomNode.localName](qdomnode.html#localName)（ ） 。

```
(bool, QString errorMsg, int errorLine, int errorColumn) QDomDocument.setContent (self, QString text, bool namespaceProcessing)
```

这是一个重载函数。

该函数从字符串读取XML文档_text_，返回True，如果内容被成功解析，否则返回False 。自_text_已经是一个Unicode字符串，没有编码检测完成。

```
(bool, QString errorMsg, int errorLine, int errorColumn) QDomDocument.setContent (self, QIODevice dev, bool namespaceProcessing)
```

这是一个重载函数。

该函数读取从IO设备的XML文档_dev_，返回True，如果内容被成功解析，否则返回False 。

```
(bool, QString errorMsg, int errorLine, int errorColumn) QDomDocument.setContent (self, QXmlInputSource source, bool namespaceProcessing)
```

这是一个重载函数。

该函数从XML文档[QXmlInputSource](qxmlinputsource.html) _source_，返回True，如果内容被成功解析，否则返回False 。

此功能被引入Qt的4.5 。

```
(bool, QString errorMsg, int errorLine, int errorColumn) QDomDocument.setContent (self, QByteArray buffer)
```

这是一个重载函数。

该函数从字符串读取XML文档_text_，返回True，如果内容被成功解析，否则返回False 。自_text_已经是一个Unicode字符串，不进行任何编码检测。

不执行任何命名空间的处理要么。

```
(bool, QString errorMsg, int errorLine, int errorColumn) QDomDocument.setContent (self, QString text)
```

这是一个重载函数。

该函数读取从字节数组的XML文档_buffer_，返回True，如果内容被成功解析，否则返回False 。

不执行任何命名空间的处理。

```
(bool, QString errorMsg, int errorLine, int errorColumn) QDomDocument.setContent (self, QIODevice dev)
```

这是一个重载函数。

该函数读取从IO设备的XML文档_dev_，返回True，如果内容被成功解析，否则返回False 。

不执行任何命名空间的处理。

```
(bool, QString errorMsg, int errorLine, int errorColumn) QDomDocument.setContent (self, QXmlInputSource source, QXmlReader reader)
```

这是一个重载函数。

该函数从XML文档[QXmlInputSource](qxmlinputsource.html) _source_并与解析它[QXmlReader](qxmlreader.html) _reader_，返回True，如果内容被成功解析，否则返回False 。

此功能不会改变的特点_reader_。如果你想使用某些功能解析您可以使用此功能来设立适当的读者。

**See also** [QXmlSimpleReader](qxmlsimplereader.html)。

```
QByteArray QDomDocument.toByteArray (self, int indent = 1)
```

[](qbytearray.html)

[解析后的文档转换回其文字表述，并返回一个](qbytearray.html)[QByteArray](qbytearray.html)含有编码为UTF- 8的数据。

此函数使用_indent_由于空间的子元素缩进量。

**See also** [toString](qdomdocument.html#toString)（ ） 。

```
QString QDomDocument.toString (self, int indent = 1)
```

解析后的文档转换回其文字表述。

此函数使用_indent_由于空间的子元素缩进量。

If _indent_为-1 ，任何空白都被添加。