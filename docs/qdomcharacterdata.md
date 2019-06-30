# QDomCharacterData Class Reference

## [[QtXml](index.htm) module]

该QDomCharacterData类表示在DOM中一个通用的字符串。[More...](#details)

继承[QDomNode](qdomnode.html)。

通过继承[QDomComment](qdomcomment.html)和[QDomText](qdomtext.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDomCharacterData x)`
*   `appendData (self, QString arg)`
*   `QString data (self)`
*   `deleteData (self, int offset, int count)`
*   `insertData (self, int offset, QString arg)`
*   `int length (self)`
*   `QDomNode.NodeType nodeType (self)`
*   `replaceData (self, int offset, int count, QString arg)`
*   `setData (self, QString)`
*   `QString substringData (self, int offset, int count)`

* * *

## Detailed Description

该QDomCharacterData类表示在DOM中一个通用的字符串。

在XML中使用的字符数据指定一个通用的数据串。这个类的更专门的版本[QDomText](qdomtext.html)，[QDomComment](qdomcomment.html)和[QDomCDATASection](qdomcdatasection.html)。

的数据串设定的[setData](qdomcharacterdata.html#setData)（）和检索与[data](qdomcharacterdata.html#data)（ ） 。可以检索数据串的使用部[substringData](qdomcharacterdata.html#substringData)（ ） 。额外的数据可以与附加[appendData](qdomcharacterdata.html#appendData)（） ，或通过插入的[insertData](qdomcharacterdata.html#insertData)（ ） 。数据串的部分可以与被删除[deleteData](qdomcharacterdata.html#deleteData)（ ）或更换[replaceData](qdomcharacterdata.html#replaceData)（ ） 。数据串的长度是由返回[length](qdomcharacterdata.html#length)（ ） 。

包含该文字数据的节点的节点类型是由返回[nodeType](qdomcharacterdata.html#nodeType)（ ） 。

* * *

## Method Documentation

```
QDomCharacterData.__init__ (self)
```

构造一个空字符数据的对象。

```
QDomCharacterData.__init__ (self, QDomCharacterData x)
```

构造的副本_x_。

副本的数据是共享的（浅拷贝） ：修改一个节点也将改变其他。如果你想使一个深拷贝，使用[cloneNode](qdomnode.html#cloneNode)（ ） 。

```
QDomCharacterData.appendData (self, QString arg)
```

附加字符串_arg_所存储的字符串。

```
QString QDomCharacterData.data (self)
```

返回存储在该对象的字符串。

如果该节点是一个[null node](qdomnode.html#isNull)，它会返回一个空字符串。

**See also** [setData](qdomcharacterdata.html#setData)（ ） 。

```
QDomCharacterData.deleteData (self, int offset, int count)
```

删除长度的子串_count_从位置_offset_。

```
QDomCharacterData.insertData (self, int offset, QString arg)
```

插入字符串_arg_为按位置存储的字符串_offset_。

```
int QDomCharacterData.length (self)
```

返回所存储的字符串的长度。

```
QDomNode.NodeType QDomCharacterData.nodeType (self)
```

[](qdomnode.html#NodeType-enum)

[返回此对象是指（即节点的类型`TextNode`，`CDATASectionNode`，`CommentNode` or `CharacterDataNode`） 。对于](qdomnode.html#NodeType-enum)[null node](qdomnode.html#isNull)，退货`CharacterDataNode`。

```
QDomCharacterData.replaceData (self, int offset, int count, QString arg)
```

替换长度的子串_count_起始位置_offset_与串_arg_。

```
QDomCharacterData.setData (self, QString)
```

设置此对象的字符串_v_。

**See also** [data](qdomcharacterdata.html#data)（ ） 。

```
QString QDomCharacterData.substringData (self, int offset, int count)
```

返回长度的子串_count_从位置_offset_。