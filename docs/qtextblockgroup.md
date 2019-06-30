# QTextBlockGroup Class Reference

## [[QtGui](index.htm) module]

该QTextBlockGroup类提供一个容器内的文本块[QTextDocument](qtextdocument.html)。[More...](#details)

继承[QTextObject](qtextobject.html)。

通过继承[QTextList](qtextlist.html)。

### Methods

*   `__init__ (self, QTextDocument doc)`
*   `blockFormatChanged (self, QTextBlock block)`
*   `blockInserted (self, QTextBlock block)`
*   `list-of-QTextBlock blockList (self)`
*   `blockRemoved (self, QTextBlock block)`

* * *

## Detailed Description

该QTextBlockGroup类提供一个容器内的文本块[QTextDocument](qtextdocument.html)。

块组可以被用来在文档内组织的文本块。他们认为属于他们的文本块的一个最新的最新列表，甚至当文本块被编辑。

每个组都有其当组构造指定的父文档。

文本块可以被插入到一组具有[blockInserted](qtextblockgroup.html#blockInserted)（ ）中，用去除[blockRemoved](qtextblockgroup.html#blockRemoved)（ ） 。如果一个块的格式改变，[blockFormatChanged](qtextblockgroup.html#blockFormatChanged)（）被调用。

该组中的块列表是由返回[blockList](qtextblockgroup.html#blockList)（ ） 。请注意，列表中的块不一定在文件中相邻元素，例如，在一个多级列表中的顶级项目将由项目列表中较低水平的分离。

* * *

## Method Documentation

```
QTextBlockGroup.__init__ (self, QTextDocument doc)
```

创建一个新的新的块组给定的_document_。

**Warning:**此功能只能由被称为[QTextDocument.createObject](qtextdocument.html#createObject)（ ） 。

```
QTextBlockGroup.blockFormatChanged (self, QTextBlock block)
```

这个函数被调用时指定的_block_的文本被改变。文本块是该组的成员。

基类的实现不执行任何操作。

```
QTextBlockGroup.blockInserted (self, QTextBlock block)
```

添加给定的_block_该组的结尾。

**Warning:**如果你重新实现这个函数必须调用基类的实现。

```
list-of-QTextBlock QTextBlockGroup.blockList (self)
```

返回所有的块组的一部分的块（可能为空）列表。

```
QTextBlockGroup.blockRemoved (self, QTextBlock block)
```

删除给定的_block_从组;块本身并没有被删除，那根本不是这个组的成员了。