# QXmlName Class Reference

## [[QtXmlPatterns](index.htm) module]

该QXmlName类表示一个XML节点的名称，以高效，名称空间感知的方式。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QXmlNamePool namePool, QString localName, QString namespaceUri = QString(), QString prefix = QString())`
*   `__init__ (self, QXmlName)`
*   `bool isNull (self)`
*   `QString localName (self, QXmlNamePool query)`
*   `QString namespaceUri (self, QXmlNamePool query)`
*   `QString prefix (self, QXmlNamePool query)`
*   `QString toClarkName (self, QXmlNamePool query)`

### Static Methods

*   `QXmlName fromClarkName (QString clarkName, QXmlNamePool namePool)`
*   `bool isNCName (QString candidate)`

### Special Methods

*   `bool __eq__ (self, QXmlName other)`
*   `int __hash__ (self)`
*   `bool __ne__ (self, QXmlName other)`

* * *

## Detailed Description

该QXmlName类表示一个XML节点的名称，以高效，名称空间感知的方式。

QXmlName代表的方式，是既有效又安全的比较名称的XML节点的名称。通常情况下，一个XML节点表示一个XML元素或属性，但QXmlName还可以代表其它类型的节点，例如的名称，[QAbstractXmlReceiver.processingInstruction](qabstractxmlreceiver.html#processingInstruction)（）和[QAbstractXmlReceiver.namespaceBinding](qabstractxmlreceiver.html#namespaceBinding)（ ） 。

一个XML节点的名称有三个组件：_namespace URI_时，_local name_和_prefix_。要查看这些是指在XML中，考虑下面的代码片断。

```
 <book xmlns:dc='http://purl.org/dc/elements/1.1'
       xmlns='http://example.com/MyDefault'>
     <dc:title>Mobey Dick</dc:title> ...
 </book>

```

对于指定的元素_book_，[localName](qxmlname.html#localName)（）返回_book_，[namespaceUri](qxmlname.html#namespaceUri)（）返回_http://example.com/MyDefault_和[prefix](qxmlname.html#prefix)（ ）返回一个空字符串。对于指定的元素_title_，[localName](qxmlname.html#localName)（）返回_title_，[namespaceUri](qxmlname.html#namespaceUri)（）返回_http://purl.org/dc/elements/1.1_和[prefix](qxmlname.html#prefix)（）返回_dc_。

以确保与QXmlName操作是有效的，例如，复印机的名称和比较它们， QXmlName的每个实例都与一个相关联的[name pool](qxmlnamepool.html)，必须在QXmlName施工时指定。该QXmlName的三个组成部分，即命名空间URI ，本地名称，前缀，存储在名称池映射到标识符，使他们能够共享。出于这个原因，创建QXmlName的有效实例的唯一方法是使用类的构造函数，其中[name pool](qxmlnamepool.html)，本地名称，命名空间URI和前缀必须全部指定。

需要注意的是QXmlName的默认构造函数构造一个空实例。它通常用于在QXmlName集合分配未使用的条目。

QXmlName的每个实例有一个相关联的副作用[name pool](qxmlnamepool.html)是QXmlName的每个实例是联系在一起的[QXmlNamePool](qxmlnamepool.html)与创建它。然而， QXmlName类不跟踪名称池的，所以所有的存取功能，例如，[namespaceUri](qxmlname.html#namespaceUri)（ ）[prefix](qxmlname.html#prefix)（ ）[localName](qxmlname.html#localName)（）和[toClarkName](qxmlname.html#toClarkName)（ ）要求的正确名称池被传递给他们。未能提供正确的名称池这些访问函数将导致不确定的行为。

请注意，一个[name pool](qxmlnamepool.html) is _not_XML命名空间。一[name pool](qxmlnamepool.html)可以代表从不同的XML命名空间QXmlName的实例， QXmlName从一个XML命名空间的实例可以被分布在多个[name pools](qxmlnamepool.html)。

### Comparing QXmlNames

要确定什么是QXmlName指的是，在_namespace URI_和_local name_被使用。该_prefix_不使用，因为前缀只是一种替代通常更长的命名空间URI的使用简写名称。也不是名字比较中使用的前缀。例如，下面的两个元素节点代表相同的元件，并比较相等。

```
 <svg xmlns="http://www.w3.org/2000/svg"/>

```

```
 <x:svg xmlns:x="http://www.w3.org/2000/svg"/>

```

虽然第二名称的前缀_x_，这两个名字比较相等的QXmlName的实例，因为该前缀未在比较中使用。

本地名不能为空字符串，虽然前缀和命名空间URI即可。如果前缀不为空，命名空间URI不能为空。本地名称和前缀必须是有效的[NCNames](http://www.w3.org/TR/REC-xml-names/#NT-NCName)例如_abc.def_ or _abc123_。

QXmlName表示有时被称为一个_expanded QName_，或者干脆一个QName 。

* * *

## Method Documentation

```
QXmlName.__init__ (self)
```

构造未初始化[QXmlName](qxmlname.html)。为了建立一个有效的[QXmlName](qxmlname.html)，您通常使用的其他构造函数，它接受一个[name pool](qxmlnamepool.html)，命名空间URI ，本地名称和前缀作为参数。但你也可以使用这个构造函数来建立一个空[QXmlName](qxmlname.html)然后指定一个现有[QXmlName](qxmlname.html)到它。

**See also** [isNull](qxmlname.html#isNull)（ ） 。

```
QXmlName.__init__ (self, QXmlNamePool namePool, QString localName, QString namespaceUri = QString(), QString prefix = QString())
```

构造一个[QXmlName](qxmlname.html)实例插入_localName_，_namespaceURI_和_prefix_成_namePool_如果它们不存在。的访问函数[namespaceUri](qxmlname.html#namespaceUri)（ ）[prefix](qxmlname.html#prefix)（ ）[localName](qxmlname.html#localName)（）和[toClarkName](qxmlname.html#toClarkName)（ ）必须通过_namePool_这里所用的，所以_namePool_必须保持在范围内同时访问函数可以被使用。然而，两种情况可以与被比较_==_ or _!=_和复制无_namePool_。

用户保证该字符串组件的有效期为一个QName 。特别地，本地名称和前缀（如果有的话） ，必须有效[NCNames](http://www.w3.org/TR/REC-xml-names/#NT-NCName)。该功能[isNCName](qxmlname.html#isNCName)（）可以被用来测试这些名称的有效性。命名空间URI应该是一个绝对URI 。[QUrl.isRelative](qurl.html#isRelative)（ ）可以被用来测试的命名空间URI是否是相对或绝对。最后，提供了一个前缀无效没有命名空间URI提供时。

_namePool_不被复制。也不是参照它保留在该实例。这个构造函数插入三个字符串成_namePool_。

```
QXmlName.__init__ (self, QXmlName)
```

```
QXmlName QXmlName.fromClarkName (QString clarkName, QXmlNamePool namePool)
```

[](qxmlname.html)

[皈依_clarkName_成](qxmlname.html)[QXmlName](qxmlname.html)，插入到_namePool_，并将其返回。

克拉克的名字是一个方式来呈现一个完整的QName只有一个字符串，其中的命名空间不能包含括号。下面是几个例子：

| Clark Name | Description |
| --- | --- |
| `html` | The local name `html`, in no namespace |
| `http://www.w3.org/1999/xhtml`html | The local name `html`, in the XHTML namespace |
| `http://www.w3.org/1999/xhtml`my:html | The local name `html`, in the XHTML namespace, with the prefix `my` |

如果命名空间包含括号，则返回值是无效或有不确定的内容。

If _clarkName_是无效的名称，构造一个默认的[QXmlName](qxmlname.html)返回。

此功能被引入Qt的4.5 。

**See also** [toClarkName](qxmlname.html#toClarkName)（ ） 。

```
bool QXmlName.isNCName (QString candidate)
```

返回True如果_candidate_是`NCName`。一个`NCName`是，可以作为XML中的名称和一个串[XQuery](index.htm)，例如，在一个元素或属性，或一个变量的名称的前缀或本地名称。

**See also** [Namespaces in XML 1.0 (Second Edition), [4] NCName](http://www.w3.org/TR/REC-xml-names/#NT-NCName)。

```
bool QXmlName.isNull (self)
```

返回True如果[QXmlName](qxmlname.html)不具有有效的组合进行初始化_namespace URI_，_local name_和_prefix_。

一个有效的本地名称始终是必需的。前缀和命名空间URI可以是空的，但如果前缀不为空，命名空间URI不能为空。本地名称和前缀必须是有效的[NCNames](http://www.w3.org/TR/REC-xml-names/#NT-NCName)例如_abc.def_ or _abc123_。

```
QString QXmlName.localName (self, QXmlNamePool query)
```

返回的本地名称。

注意，为了提高效率，本地名称字符串没有存储在[QXmlName](qxmlname.html)但在[QXmlNamePool](qxmlnamepool.html)被传递给构造函数。因此，同样的_namePool_必须被传递给这个函数，因此它可以用于查找本地名称。

```
QString QXmlName.namespaceUri (self, QXmlNamePool query)
```

返回的命名空间URI 。

注意，为了提高效率，命名空间URI字符串没有存储在[QXmlName](qxmlname.html)但在[QXmlNamePool](qxmlnamepool.html)被传递给构造函数。因此，同样的_namePool_必须被传递给这个函数，因此它可以用于查找命名空间URI 。

```
QString QXmlName.prefix (self, QXmlNamePool query)
```

返回前缀。

注意，为了提高效率，前缀字符串没有存储在[QXmlName](qxmlname.html)但在[QXmlNamePool](qxmlnamepool.html)被传递给构造函数。因此，同样的_namePool_必须被传递给该函数，因此它可用于查找的前缀。

```
QString QXmlName.toClarkName (self, QXmlNamePool query)
```

返回此[QXmlName](qxmlname.html)格式化为一个克拉克名称。举例来说，如果本地名称是`html`，前缀是`x`和命名空间URI为`http://www.w3.org/1999/xhtml/`，那么返回的克拉克的名字是：

```
 {http://www.w3.org/1999/xhtml/}x:html.

```

如果本地名称是_MyWidget_和命名空间为空，则返回的克拉克的名字是：

```
 MyWidget

```

需要注意的是为提高效率，命名空间URI ，本地名称和前缀字符串不存储在[QXmlName](qxmlname.html)但在[QXmlNamePool](qxmlnamepool.html)被传递给构造函数。因此，同样的_namePool_必须被传递给该函数，因此它可用于查找三个字符串组成。

此功能可用于调试。

**See also** [XML Namespaces, James Clark](http://www.jclark.com/xml/xmlns.htm)和[fromClarkName](qxmlname.html#fromClarkName)（ ） 。

```
bool QXmlName.__eq__ (self, QXmlName other)
```

```
int QXmlName.__hash__ (self)
```

```
bool QXmlName.__ne__ (self, QXmlName other)
```