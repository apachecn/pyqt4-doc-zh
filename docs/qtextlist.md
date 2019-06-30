# QTextList Class Reference

## [[QtGui](index.htm) module]

该QTextList类提供了在一个项目的装修清单[QTextDocument](qtextdocument.html)。[More...](#details)

继承[QTextBlockGroup](qtextblockgroup.html)。

### Methods

*   `__init__ (self, QTextDocument doc)`
*   `add (self, QTextBlock block)`
*   `int count (self)`
*   `QTextListFormat format (self)`
*   `bool isEmpty (self)`
*   `QTextBlock item (self, int i)`
*   `int itemNumber (self, QTextBlock)`
*   `QString itemText (self, QTextBlock)`
*   `remove (self, QTextBlock)`
*   `removeItem (self, int i)`
*   `setFormat (self, QTextListFormat aformat)`

### Special Methods

*   `__len__ (self)`

* * *

## Detailed Description

该QTextList类提供了在一个项目的装修清单[QTextDocument](qtextdocument.html)。

列表中包含的序列的文本块，其中的每一个标有符号点或其他符号。列出的多个层面都可以使用，并自动编号功能提供了有序的数字和字母顺序列出了支持。

列表是通过使用文本光标插入一个空列表在当前位置或移动现有文本转换成一个新的列表创建。该[QTextCursor.insertList](qtextcursor.html#insertList)（ ）函数插入光标所在位置的空块插入到文档中，并使其在列表中的第一个项目。

```
     [QTextListFormat](qtextlistformat.html) listFormat;
     if (list) {
         listFormat = list->format();
         listFormat.setIndent(listFormat.indent() + 1);
     }

     listFormat.setStyle([QTextListFormat](qtextlistformat.html).ListDisc);
     cursor.insertList(listFormat);

```

该[QTextCursor.createList](qtextcursor.html#createList)（ ）函数将光标的当前块的内容，并把它变成一个新的列表中的第一项。

光标的当前列表中找到与[QTextCursor.currentList](qtextcursor.html#currentList)（ ） 。

列表中的项目的数目由下式给出[count](qtextlist.html#count)（ ） 。每个项目都可以通过其索引中的列表中获得[item](qtextlist.html#item)（）函数。类似地，给定的项的索引可以找到[itemNumber](qtextlist.html#itemNumber)（ ） 。每个项的文本可以与被发现[itemText](qtextlist.html#itemText)（）函数。

请注意，列表中的项目可能无法在文件中相邻元素。例如，在一个多级列表中的顶级项目将由项目列表中较低水平的分离。

列表项可以通过索引与删除[removeItem](qtextlist.html#removeItem)（）函数。[remove](qtextlist.html#remove)（ ）删除指定项在列表中。

该列表的格式设置与[setFormat](qtextlist.html#setFormat)（）和read与[format](qtextlist.html#format)（ ） 。该格式描述列表本身的装饰，而不是单个项目。

* * *

## Method Documentation

```
QTextList.__init__ (self, QTextDocument doc)
```

```
QTextList.add (self, QTextBlock block)
```

使给定的_block_列表的一部分。

**See also** [remove](qtextlist.html#remove)（）和[removeItem](qtextlist.html#removeItem)（ ） 。

```
int QTextList.count (self)
```

返回的项目的列表中的号码。

```
QTextListFormat QTextList.format (self)
```

[

返回列表的格式。

](qtextlistformat.html)

[**See also**](qtextlistformat.html) [setFormat](qtextlist.html#setFormat)（ ） 。

```
bool QTextList.isEmpty (self)
```

```
QTextBlock QTextList.item (self, int i)
```

[

返回_i_列表中的第文本块。

](qtextblock.html)

[**See also**](qtextblock.html) [count](qtextlist.html#count)（）和[itemText](qtextlist.html#itemText)（ ） 。

```
int QTextList.itemNumber (self, QTextBlock)
```

返回对应于给定列表项的索引_block_。返回-1，如果块没有出现在清单中。

```
QString QTextList.itemText (self, QTextBlock)
```

返回对应于给定列表项的文本_block_。

```
QTextList.remove (self, QTextBlock)
```

删除给定的_block_从列表中。

**See also** [add](qtextlist.html#add)（）和[removeItem](qtextlist.html#removeItem)（ ） 。

```
QTextList.removeItem (self, int i)
```

在删除项目位置的项目_i_从列表中。当在列表中的最后一个项目被删除，该列表是由自动删除[QTextDocument](qtextdocument.html)拥有它。

**See also** [add](qtextlist.html#add)（）和[remove](qtextlist.html#remove)（ ） 。

```
QTextList.setFormat (self, QTextListFormat aformat)
```

设置列表的格式_format_。

**See also** [format](qtextlist.html#format)（ ） 。

```
 QTextList.__len__ (self)
```