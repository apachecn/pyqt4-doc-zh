# QTextCursor Class Reference

## [[QtGui](index.htm) module]

该QTextCursor类提供了一个API来访问和修改QTextDocuments 。[More...](#details)

### Types

*   `enum MoveMode { MoveAnchor, KeepAnchor }`
*   `enum MoveOperation { NoMove, Start, Up, StartOfLine, ..., PreviousRow }`
*   `enum SelectionType { WordUnderCursor, LineUnderCursor, BlockUnderCursor, Document }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QTextDocument document)`
*   `__init__ (self, QTextFrame frame)`
*   `__init__ (self, QTextBlock block)`
*   `__init__ (self, QTextCursor cursor)`
*   `int anchor (self)`
*   `bool atBlockEnd (self)`
*   `bool atBlockStart (self)`
*   `bool atEnd (self)`
*   `bool atStart (self)`
*   `beginEditBlock (self)`
*   `QTextBlock block (self)`
*   `QTextCharFormat blockCharFormat (self)`
*   `QTextBlockFormat blockFormat (self)`
*   `int blockNumber (self)`
*   `QTextCharFormat charFormat (self)`
*   `clearSelection (self)`
*   `int columnNumber (self)`
*   `QTextList createList (self, QTextListFormat format)`
*   `QTextList createList (self, QTextListFormat.Style style)`
*   `QTextFrame currentFrame (self)`
*   `QTextList currentList (self)`
*   `QTextTable currentTable (self)`
*   `deleteChar (self)`
*   `deletePreviousChar (self)`
*   `QTextDocument document (self)`
*   `endEditBlock (self)`
*   `bool hasComplexSelection (self)`
*   `bool hasSelection (self)`
*   `insertBlock (self)`
*   `insertBlock (self, QTextBlockFormat format)`
*   `insertBlock (self, QTextBlockFormat format, QTextCharFormat charFormat)`
*   `insertFragment (self, QTextDocumentFragment fragment)`
*   `QTextFrame insertFrame (self, QTextFrameFormat format)`
*   `insertHtml (self, QString html)`
*   `insertImage (self, QTextImageFormat format)`
*   `insertImage (self, QTextImageFormat format, QTextFrameFormat.Position alignment)`
*   `insertImage (self, QString name)`
*   `insertImage (self, QImage image, QString name = QString())`
*   `QTextList insertList (self, QTextListFormat format)`
*   `QTextList insertList (self, QTextListFormat.Style style)`
*   `QTextTable insertTable (self, int rows, int cols, QTextTableFormat format)`
*   `QTextTable insertTable (self, int rows, int cols)`
*   `insertText (self, QString text)`
*   `insertText (self, QString text, QTextCharFormat format)`
*   `bool isCopyOf (self, QTextCursor other)`
*   `bool isNull (self)`
*   `joinPreviousEditBlock (self)`
*   `bool keepPositionOnInsert (self)`
*   `mergeBlockCharFormat (self, QTextCharFormat modifier)`
*   `mergeBlockFormat (self, QTextBlockFormat modifier)`
*   `mergeCharFormat (self, QTextCharFormat modifier)`
*   `bool movePosition (self, MoveOperation op, MoveMode mode = QTextCursor.MoveAnchor, int n = 1)`
*   `int position (self)`
*   `int positionInBlock (self)`
*   `removeSelectedText (self)`
*   `select (self, SelectionType selection)`
*   `(int firstRow, int numRows, int firstColumn, int numColumns) selectedTableCells (self)`
*   `QString selectedText (self)`
*   `QTextDocumentFragment selection (self)`
*   `int selectionEnd (self)`
*   `int selectionStart (self)`
*   `setBlockCharFormat (self, QTextCharFormat format)`
*   `setBlockFormat (self, QTextBlockFormat format)`
*   `setCharFormat (self, QTextCharFormat format)`
*   `setKeepPositionOnInsert (self, bool b)`
*   `setPosition (self, int pos, MoveMode mode = QTextCursor.MoveAnchor)`
*   `setVerticalMovementX (self, int x)`
*   `setVisualNavigation (self, bool b)`
*   `int verticalMovementX (self)`
*   `bool visualNavigation (self)`

### Special Methods

*   `bool __eq__ (self, QTextCursor rhs)`
*   `bool __ge__ (self, QTextCursor rhs)`
*   `bool __gt__ (self, QTextCursor rhs)`
*   `bool __le__ (self, QTextCursor rhs)`
*   `bool __lt__ (self, QTextCursor rhs)`
*   `bool __ne__ (self, QTextCursor rhs)`

* * *

## Detailed Description

该QTextCursor类提供了一个API来访问和修改QTextDocuments 。

文字游标是用来通过模仿光标在文本编辑器的行为的编程接口来访问和修改的内容及相关文本文档的结构对象。 QTextCursor包含内两个光标的位置信息[QTextDocument](qtextdocument.html)而任何选择，它已经做。

QTextCursor是仿照文本光标的行为在文本编辑器的方式，通过提供用户界面执行标准操作的编程方法。一个文档可以被看作是字符的字符串。光标的当前[position](qtextcursor.html#position)（ ）则始终为_between_两个连续字符的字符串，否则_before_的第一个字符或_after_在最后一个字符的字符串。文件还可以包含表格，列表，图像和其他对象除了文字，但是，从开发者的角度来看，该文件可以被视为一个长字符串。该串中的某些部分可以被认为在于特定块（例如段落）中，或一个表的单元格或列表的项目，或其它结构元件内。当我们提到“当前字符”我们立即指的是字符_before_光标[position](qtextcursor.html#position)（ ）在文档中。同样，“当前块”是一个包含光标块[position](qtextcursor.html#position)（ ） 。

一个QTextCursor也有一个[anchor](qtextcursor.html#anchor)（）位置。这是之间的文本[anchor](qtextcursor.html#anchor)（ ）和[position](qtextcursor.html#position)（）是该选择。如果[anchor](qtextcursor.html#anchor)（）==[position](qtextcursor.html#position)（ ）没有选择。

光标位置可以通过编程方式使用改变[setPosition](qtextcursor.html#setPosition)（）和[movePosition](qtextcursor.html#movePosition)（） ，后者也可以被用来选择文本。对于选择看[selectionStart](qtextcursor.html#selectionStart)（ ）[selectionEnd](qtextcursor.html#selectionEnd)（ ）[hasSelection](qtextcursor.html#hasSelection)（ ）[clearSelection](qtextcursor.html#clearSelection)（）和[removeSelectedText](qtextcursor.html#removeSelectedText)（ ） 。

如果[position](qtextcursor.html#position)（）是在一个块的开始[atBlockStart](qtextcursor.html#atBlockStart)（ ）返回True ，如果它是在一个块结束[atBlockEnd](qtextcursor.html#atBlockEnd)（ ）返回True 。当前字符的格式由返回[charFormat](qtextcursor.html#charFormat)（）和当前块的格式是由返回[blockFormat](qtextcursor.html#blockFormat)（ ） 。

格式化可以使用适用于当前文本文档[setCharFormat](qtextcursor.html#setCharFormat)（ ）[mergeCharFormat](qtextcursor.html#mergeCharFormat)（ ）[setBlockFormat](qtextcursor.html#setBlockFormat)（）和[mergeBlockFormat](qtextcursor.html#mergeBlockFormat)（）函数。在'设置'功能将取代光标的当前字符或块格式，而“合并”功能添加给定的格式属性光标的当前格式。如果光标有一个选择给定的格式应用到当前的选择。请注意，当被选择的块的唯一部件的块格式被应用到整个块。在当前字符位置的文本可以使用变成一个列表[createList](qtextcursor.html#createList)（ ） 。

缺失可以使用可以实现[deleteChar](qtextcursor.html#deleteChar)（ ）[deletePreviousChar](qtextcursor.html#deletePreviousChar)（）和[removeSelectedText](qtextcursor.html#removeSelectedText)（ ） 。

文本串可以被插入到与该文件[insertText](qtextcursor.html#insertText)（）函数，块（即新段落）可以插入与[insertBlock](qtextcursor.html#insertBlock)（ ） 。

现有的文本片段可被插入与[insertFragment](qtextcursor.html#insertFragment)（ ），但是，如果你要插入文本块的各种格式，通常还是更容易使用[insertText](qtextcursor.html#insertText)（） ，并提供一个字符的格式。

各种类型的较高级别的结构中，也可以插入到光标的文件：

*   Lists are ordered sequences of block elements that are decorated with bullet points or symbols. These are inserted in a specified format with [insertList](qtextcursor.html#insertList)().
*   Tables are inserted with the [insertTable](qtextcursor.html#insertTable)() function, and can be given an optional format. These contain an array of cells that can be traversed using the cursor.
*   Inline images are inserted with [insertImage](qtextcursor.html#insertImage)(). The image to be used can be specified in an image format, or by name.
*   Frames are inserted by calling [insertFrame](qtextcursor.html#insertFrame)() with a specified format.

操作可以分组（即视作撤销/重做一个动作）使用[beginEditBlock](qtextcursor.html#beginEditBlock)（）和[endEditBlock](qtextcursor.html#endEditBlock)（ ） 。

光标移动仅限于有效的光标位置。在拉丁语写作，这是任何两个连续字符的文本之间，第一个字符之前，或之后的最后一个字符。在其他一些书写系统的光标移动仅限于“集群” （如一个音节在梵文，或基字母加变音符号） 。功能，如[movePosition](qtextcursor.html#movePosition)（）和[deleteChar](qtextcursor.html#deleteChar)（ ）限制光标移动到这些有效的位置。

* * *

## Type Documentation

```
QTextCursor.MoveMode
```

| Constant | Value | Description |
| --- | --- | --- |
| `QTextCursor.MoveAnchor` | `0` | 移动锚定至相同的位置的光标本身。 |
| `QTextCursor.KeepAnchor` | `1` | 保持锚在哪里。 |

如果[anchor](qtextcursor.html#anchor)（）被保持在那里它是与[position](qtextcursor.html#position)（ ）移动，在之间的文本将被选中。

```
QTextCursor.MoveOperation
```

| Constant | Value | Description |
| --- | --- | --- |
| `QTextCursor.NoMove` | `0` | 保持光标的地方是 |
| `QTextCursor.Start` | `1` | 移动到文档的开始。 |
| `QTextCursor.StartOfLine` | `3` | 移动到当前行的开始。 |
| `QTextCursor.StartOfBlock` | `4` | 移动到当前块的开始。 |
| `QTextCursor.StartOfWord` | `5` | 移动到当前单词的开头。 |
| `QTextCursor.PreviousBlock` | `6` | 移动到前一个块的开始。 |
| `QTextCursor.PreviousCharacter` | `7` | 移动到前一个字符。 |
| `QTextCursor.PreviousWord` | `8` | 移动到前一个单词的起始处。 |
| `QTextCursor.Up` | `2` | 向上移动一行。 |
| `QTextCursor.Left` | `9` | 向左移动一个字符。 |
| `QTextCursor.WordLeft` | `10` | 向左移动一个词。 |
| `QTextCursor.End` | `11` | 移动到文档的末尾。 |
| `QTextCursor.EndOfLine` | `13` | 移动到当前行的结尾。 |
| `QTextCursor.EndOfWord` | `14` | 移动到当前字的结尾。 |
| `QTextCursor.EndOfBlock` | `15` | 移动到当前块的结尾。 |
| `QTextCursor.NextBlock` | `16` | 移动到下一个块的开始。 |
| `QTextCursor.NextCharacter` | `17` | 移动到下一个字符。 |
| `QTextCursor.NextWord` | `18` | 移动到下一个单词。 |
| `QTextCursor.Down` | `12` | 向下移动一行。 |
| `QTextCursor.Right` | `19` | 向右移动一个字符。 |
| `QTextCursor.WordRight` | `20` | 向右移动一个词。 |
| `QTextCursor.NextCell` | `21` | 移动到下一个表格单元格的开头当前表内。如果当前单元格是行中的最后一个单元格，将光标移动到下一行的第一个单元格。 |
| `QTextCursor.PreviousCell` | `22` | 移动到前一个表格单元格的开头当前表内。如果当前单元格是行中的第一个单元格，将光标移动到前一行的最后一个单元格。 |
| `QTextCursor.NextRow` | `23` | 移动到下一行的当前表中的第一个新小区。 |
| `QTextCursor.PreviousRow` | `24` | 移动到上一行在当前表中的最后一个单元格。 |

**See also** [movePosition](qtextcursor.html#movePosition)（ ） 。

```
QTextCursor.SelectionType
```

该枚举描述可以与应用于所选内容的类型[select](qtextcursor.html#select)（）函数。

| Constant | Value | Description |
| --- | --- | --- |
| `QTextCursor.Document` | `3` | 选择整个文档。 |
| `QTextCursor.BlockUnderCursor` | `2` | 选择光标下的文本块。 |
| `QTextCursor.LineUnderCursor` | `1` | 选择光标下的文本行。 |
| `QTextCursor.WordUnderCursor` | `0` | 选择光标下的单词。如果游标未定位的可选字符的字符串中，没有文本被选中。 |

* * *

## Method Documentation

```
QTextCursor.__init__ (self)
```

构造一个空指针。

```
QTextCursor.__init__ (self, QTextDocument document)
```

构造一个游标指向的开始_document_。

```
QTextCursor.__init__ (self, QTextFrame frame)
```

```
QTextCursor.__init__ (self, QTextBlock block)
```

构造一个游标指向的开始_frame_。

```
QTextCursor.__init__ (self, QTextCursor cursor)
```

构造一个游标指向的开始_block_。

```
int QTextCursor.anchor (self)
```

返回的锚定位置，这是相同的[position](qtextcursor.html#position)（） ，除非在此情况下，选择[position](qtextcursor.html#position)（）标记的选择和锚的一端（）马克的另一端。就像光标位置，支撑点位是字符之间。

**See also** [position](qtextcursor.html#position)（ ）[setPosition](qtextcursor.html#setPosition)（ ）[movePosition](qtextcursor.html#movePosition)（ ）[selectionStart](qtextcursor.html#selectionStart)（）和[selectionEnd](qtextcursor.html#selectionEnd)（ ） 。

```
bool QTextCursor.atBlockEnd (self)
```

返回True如果光标在一个块结束，否则返回False 。

**See also** [atBlockStart](qtextcursor.html#atBlockStart)（）和[atEnd](qtextcursor.html#atEnd)（ ） 。

```
bool QTextCursor.atBlockStart (self)
```

返回True如果光标在一个块的开始，否则返回False 。

**See also** [atBlockEnd](qtextcursor.html#atBlockEnd)（）和[atStart](qtextcursor.html#atStart)（ ） 。

```
bool QTextCursor.atEnd (self)
```

返回True如果光标在文档的末尾，否则返回False 。

此功能被引入Qt的4.6 。

**See also** [atStart](qtextcursor.html#atStart)（）和[atBlockEnd](qtextcursor.html#atBlockEnd)（ ） 。

```
bool QTextCursor.atStart (self)
```

返回True如果光标在文件的开头，否则返回False 。

**See also** [atBlockStart](qtextcursor.html#atBlockStart)（）和[atEnd](qtextcursor.html#atEnd)（ ） 。

```
QTextCursor.beginEditBlock (self)
```

表示编辑操作上应显示为一个单一的操作从视图中撤消/重做点的文件块的开始。

例如：

```
 [QTextCursor](qtextcursor.html) cursor(textDocument);
 cursor.beginEditBlock();
 cursor.insertText("Hello");
 cursor.insertText("World");
 cursor.endEditBlock();

 textDocument->undo();

```

撤消（）的调用会导致两个插入到被撤消，造成两个“世界”和“你好”被删除。

它也可以嵌套调用beginEditBlock和endEditBlock 。最上面的一对将决定撤消/重做操作的范围。

**See also** [endEditBlock](qtextcursor.html#endEditBlock)（ ） 。

```
QTextBlock QTextCursor.block (self)
```

[

返回包含光标块。

](qtextblock.html)

```
QTextCharFormat QTextCursor.blockCharFormat (self)
```

[

返回光标所在的块的块的字符格式

块char格式是一个空块的开头插入文本时所使用的格式。

](qtextcharformat.html)

[**See also**](qtextcharformat.html) [setBlockCharFormat](qtextcursor.html#setBlockCharFormat)（ ） 。

```
QTextBlockFormat QTextCursor.blockFormat (self)
```

[

返回光标所在的块的块格式

](qtextblockformat.html)

[**See also**](qtextblockformat.html) [setBlockFormat](qtextcursor.html#setBlockFormat)（）和[charFormat](qtextcursor.html#charFormat)（ ） 。

```
int QTextCursor.blockNumber (self)
```

返回光标在，或0，如果光标是无效的块的数目。

请注意，此功能才有意义的文件而无需复杂的对象，如表格或框架。

这个函数中引入了Qt 4.2中。

```
QTextCharFormat QTextCursor.charFormat (self)
```

[](qtextcharformat.html)

[立即光标前返回字符的格式](qtextcharformat.html)[position](qtextcursor.html#position)（ ） 。如果光标被定位在一个文本块，它是不是空的开头，然后该字符的光标之后的格式被返回。

**See also** [setCharFormat](qtextcursor.html#setCharFormat)（ ）[insertText](qtextcursor.html#insertText)（）和[blockFormat](qtextcursor.html#blockFormat)（ ） 。

```
QTextCursor.clearSelection (self)
```

通过锚设置到光标位置清除当前的选择。

需要注意的是它**not**删除选定的文本。

**See also** [removeSelectedText](qtextcursor.html#removeSelectedText)（）和[hasSelection](qtextcursor.html#hasSelection)（ ） 。

```
int QTextCursor.columnNumber (self)
```

返回其包含的行内光标的位置。

注意，这是列数相对于一个缠绕线，而不是相对于该块（即段落）。

你可能想打电话[positionInBlock](qtextcursor.html#positionInBlock)（ ）来代替。

这个函数中引入了Qt 4.2中。

**See also** [positionInBlock](qtextcursor.html#positionInBlock)（ ） 。

```
QTextList QTextCursor.createList (self, QTextListFormat format)
```

[

创建并返回一个新的列表给定的_format_，并使得当前段落光标在第一个列表项。

](qtextlist.html)

[**See also**](qtextlist.html) [insertList](qtextcursor.html#insertList)（）和[currentList](qtextcursor.html#currentList)（ ） 。

```
QTextList QTextCursor.createList (self, QTextListFormat.Style style)
```

[

这是一个重载函数。

创建并返回一个新的列表给定的_style_，使得光标的当前段落的第一个列表项。

](qtextlist.html)

[要使用的样式被定义](qtextlist.html)[QTextListFormat.Style](qtextlistformat.html#Style-enum)枚举。

**See also** [insertList](qtextcursor.html#insertList)（）和[currentList](qtextcursor.html#currentList)（ ） 。

```
QTextFrame QTextCursor.currentFrame (self)
```

[

将指针返回到当前帧。返回0，如果游标是无效的。

](qtextframe.html)

[**See also**](qtextframe.html) [insertFrame](qtextcursor.html#insertFrame)（ ） 。

```
QTextList QTextCursor.currentList (self)
```

[](qtextlist.html)

[返回当前列表中，如果光标](qtextlist.html)[position](qtextcursor.html#position)（ ）是一个块是列表的一部分里面，否则返回0 。

**See also** [insertList](qtextcursor.html#insertList)（）和[createList](qtextcursor.html#createList)（ ） 。

```
QTextTable QTextCursor.currentTable (self)
```

[](qtexttable.html)

[返回一个指针，指向当前表如果光标](qtexttable.html)[position](qtextcursor.html#position)（）是一个块，它是一个表中的部分内，否则返回0 。

**See also** [insertTable](qtextcursor.html#insertTable)（ ） 。

```
QTextCursor.deleteChar (self)
```

如果没有选定的文本，删除字符_at_当前光标位置，否则将删除选定的文本。

**See also** [deletePreviousChar](qtextcursor.html#deletePreviousChar)（ ）[hasSelection](qtextcursor.html#hasSelection)（）和[clearSelection](qtextcursor.html#clearSelection)（ ） 。

```
QTextCursor.deletePreviousChar (self)
```

如果没有选定的文本，删除字符_before_当前光标位置，否则将删除选定的文本。

**See also** [deleteChar](qtextcursor.html#deleteChar)（ ）[hasSelection](qtextcursor.html#hasSelection)（）和[clearSelection](qtextcursor.html#clearSelection)（ ） 。

```
QTextDocument QTextCursor.document (self)
```

[

返回此光标关联的文件。

此功能被引入Qt的4.5 。

```
QTextCursor.endEditBlock (self)
```

表示编辑操作上应显示为一个单一的操作从视图中撤消/重做点的文件块的结尾。

](qtextdocument.html)

[**See also**](qtextdocument.html) [beginEditBlock](qtextcursor.html#beginEditBlock)（ ） 。

```
bool QTextCursor.hasComplexSelection (self)
```

如果光标包含一个选择，是不是只是一个范围，则返回True[selectionStart](qtextcursor.html#selectionStart)（）来[selectionEnd](qtextcursor.html#selectionEnd)（ ），否则返回False 。

复杂的选择是那些跨越至少两个小区中的表格;他们的程度是通过指定[selectedTableCells](qtextcursor.html#selectedTableCells)（ ） 。

```
bool QTextCursor.hasSelection (self)
```

返回True如果光标包含一个选择，否则返回False 。

```
QTextCursor.insertBlock (self)
```

在游标位置插入一个新的空块[position](qtextcursor.html#position)（）与当前[blockFormat](qtextcursor.html#blockFormat)（）和[charFormat](qtextcursor.html#charFormat)（ ） 。

**See also** [setBlockFormat](qtextcursor.html#setBlockFormat)（ ） 。

```
QTextCursor.insertBlock (self, QTextBlockFormat format)
```

这是一个重载函数。

在游标位置插入一个新的空块[position](qtextcursor.html#position)（ ）与块格式_format_和电流[charFormat](qtextcursor.html#charFormat)（ ）为块字符格式。

**See also** [setBlockFormat](qtextcursor.html#setBlockFormat)（ ） 。

```
QTextCursor.insertBlock (self, QTextBlockFormat format, QTextCharFormat charFormat)
```

这是一个重载函数。

在游标位置插入一个新的空块[position](qtextcursor.html#position)（ ）与块格式_format_和_charFormat_为块字符格式。

**See also** [setBlockFormat](qtextcursor.html#setBlockFormat)（ ） 。

```
QTextCursor.insertFragment (self, QTextDocumentFragment fragment)
```

插入文本_fragment_在当前[position](qtextcursor.html#position)（ ） 。

```
QTextFrame QTextCursor.insertFrame (self, QTextFrameFormat format)
```

[](qtextframe.html)

[插入一个框架给定的_format_在当前光标](qtextframe.html)[position](qtextcursor.html#position)（ ） ，移动光标[position](qtextcursor.html#position)（）的框架内，并返回该帧。

如果光标持有的选择，整机选用移动的框架内。

**See also** [hasSelection](qtextcursor.html#hasSelection)（ ） 。

```
QTextCursor.insertHtml (self, QString html)
```

插入文本_html_在当前[position](qtextcursor.html#position)（ ） 。该文本被解释为HTML 。

**Note:**使用此功能时使用样式表，样式表只适用于文档中的当前块。为了对整个文档应用样式表，使用[QTextDocument.setDefaultStyleSheet](qtextdocument.html#defaultStyleSheet-prop)（ ）来代替。

这个函数中引入了Qt 4.2中。

```
QTextCursor.insertImage (self, QTextImageFormat format)
```

插入由所定义的图像_format_在当前[position](qtextcursor.html#position)（ ） 。

```
QTextCursor.insertImage (self, QTextImageFormat format, QTextFrameFormat.Position alignment)
```

这是一个重载函数。

，将图像由给定的定义_format_在光标的当前位置与指定的_alignment_。

这个函数中引入了Qt 4.2中。

**See also** [position](qtextcursor.html#position)（ ） 。

```
QTextCursor.insertImage (self, QString name)
```

这是一个重载函数。

便利的方法与给定插入图像_name_在当前[position](qtextcursor.html#position)（ ） 。

```
 [QImage](qimage.html) img = ...
 textDocument->addResource([QTextDocument](qtextdocument.html).ImageResource, [QUrl](qurl.html)("myimage"), img);
 cursor.insertImage("myimage");

```

```
QTextCursor.insertImage (self, QImage image, QString name = QString())
```

这是一个重载函数。

便利功能用于插入给定的_image_具有可选_name_在当前[position](qtextcursor.html#position)（ ） 。

此功能被引入Qt的4.5 。

```
QTextList QTextCursor.insertList (self, QTextListFormat format)
```

[

插入一个新块的当前位置，并使它成为一个新创建的列表中给出的第一个列表项_format_。返回创建的列表。

](qtextlist.html)

[**See also**](qtextlist.html) [currentList](qtextcursor.html#currentList)（ ）[createList](qtextcursor.html#createList)（）和[insertBlock](qtextcursor.html#insertBlock)（ ） 。

```
QTextList QTextCursor.insertList (self, QTextListFormat.Style style)
```

[

这是一个重载函数。

插入一个新块的当前位置，并使它成为一个新创建的列表中给出的第一个列表项_style_。返回创建的列表。

](qtextlist.html)

[**See also**](qtextlist.html) [currentList](qtextcursor.html#currentList)（ ）[createList](qtextcursor.html#createList)（）和[insertBlock](qtextcursor.html#insertBlock)（ ） 。

```
QTextTable QTextCursor.insertTable (self, int rows, int cols, QTextTableFormat format)
```

[](qtexttable.html)

[创建一个具有给定数量的新表_rows_和_columns_在指定的_format_，将其插入到当前光标](qtexttable.html)[position](qtextcursor.html#position)（ ）在文件中，并返回表对象。将光标移动到第一小区的开头。

必须有在表中的至少一行和一列。

**See also** [currentTable](qtextcursor.html#currentTable)（ ） 。

```
QTextTable QTextCursor.insertTable (self, int rows, int cols)
```

[

这是一个重载函数。

](qtexttable.html)

[创建一个具有给定数量的新表_rows_和_columns_，将其插入到当前光标](qtexttable.html)[position](qtextcursor.html#position)（ ）在文件中，并返回表对象。将光标移动到第一小区的开头。

必须有在表中的至少一行和一列。

**See also** [currentTable](qtextcursor.html#currentTable)（ ） 。

```
QTextCursor.insertText (self, QString text)
```

Inserts _text_在当前位置，使用当前的字符格式。

如果有选择，选择被删除，取而代之的是_text_例如：

```
 cursor.clearSelection();
 cursor.movePosition([QTextCursor](qtextcursor.html).NextWord, [QTextCursor](qtextcursor.html).KeepAnchor);
 cursor.insertText("Hello World");

```

这将清除任何现有的选择，选择这个词在光标（即[position](qtextcursor.html#position)（ ）向前） ，并替换选择的短语的“Hello World ” 。

在插入的文本任何ASCII换行符（ \ n）被转换成Unicode块分隔符，对应[insertBlock](qtextcursor.html#insertBlock)（ ）调用。

**See also** [charFormat](qtextcursor.html#charFormat)（）和[hasSelection](qtextcursor.html#hasSelection)（ ） 。

```
QTextCursor.insertText (self, QString text, QTextCharFormat format)
```

这是一个重载函数。

Inserts _text_在当前位置与给定的_format_。

```
bool QTextCursor.isCopyOf (self, QTextCursor other)
```

返回True如果光标和_other_是彼此的副本，即它们中的一个被创建为其它和因为无论已移动的一个副本。这比平等更严格的。

**See also** [operator=](qtextcursor.html#operator-eq)（）和[operator==](qtextcursor.html#operator-eq-eq)（ ） 。

```
bool QTextCursor.isNull (self)
```

返回True如果光标为空，否则返回False 。一个空指针被默认构造函数创建的。

```
QTextCursor.joinPreviousEditBlock (self)
```

喜欢[beginEditBlock](qtextcursor.html#beginEditBlock)（ ）表示编辑操作的块应显示为撤消/重做一个操作的开始。然而不同[beginEditBlock](qtextcursor.html#beginEditBlock)（ ）它不会启动一个新的块，但反转以前调用[endEditBlock](qtextcursor.html#endEditBlock)（ ），因此使得下面创建的前一个编辑数据块的操作部分。

例如：

```
 [QTextCursor](qtextcursor.html) cursor(textDocument);
 cursor.beginEditBlock();
 cursor.insertText("Hello");
 cursor.insertText("World");
 cursor.endEditBlock();

 ...

 cursor.joinPreviousEditBlock();
 cursor.insertText("Hey");
 cursor.endEditBlock();

 textDocument->undo();

```

撤消（）的调用会导致所有三个插入到被撤消。

**See also** [beginEditBlock](qtextcursor.html#beginEditBlock)（）和[endEditBlock](qtextcursor.html#endEditBlock)（ ） 。

```
bool QTextCursor.keepPositionOnInsert (self)
```

返回游标是否应保持其目前的位置，当文本被插入到光标的位置。

默认值为False ;

此功能被引入Qt的4.7 。

**See also** [setKeepPositionOnInsert](qtextcursor.html#setKeepPositionOnInsert)（ ） 。

```
QTextCursor.mergeBlockCharFormat (self, QTextCharFormat modifier)
```

修改当前块的块char格式（或包含在选区中的所有块）由指定的程序段格式_modifier_。

**See also** [setBlockCharFormat](qtextcursor.html#setBlockCharFormat)（ ） 。

```
QTextCursor.mergeBlockFormat (self, QTextBlockFormat modifier)
```

修改当前块的块格式（或包含在选择的所有块）与所指定的数据块格式_modifier_。

**See also** [setBlockFormat](qtextcursor.html#setBlockFormat)（）和[blockFormat](qtextcursor.html#blockFormat)（ ） 。

```
QTextCursor.mergeCharFormat (self, QTextCharFormat modifier)
```

合并光标的与格式描述的属性当前字符格式_modifier_。如果光标有一个选择，这个功能适用于所有设置属性_modifier_所有的字符格式，是选择的一部分。

**See also** [hasSelection](qtextcursor.html#hasSelection)（）和[setCharFormat](qtextcursor.html#setCharFormat)（ ） 。

```
bool QTextCursor.movePosition (self, MoveOperation op, MoveMode mode = QTextCursor.MoveAnchor, int n = 1)
```

通过执行给定的移动光标_operation_ _n_次，使用指定的_mode_，并返回True，如果所有操作都成功完成，否则返回False 。

例如，如果这个功能被反复使用以寻求到下一个字的结尾，它最终将当达到文件结尾的失败。

默认情况下，执行移动操作一次（_n_= 1）。

If _mode_ is `KeepAnchor`，光标选择它移动到文本上。这是当他们按住Shift键并移动光标，光标键，用户达到相同的效果。

**See also** [setVisualNavigation](qtextcursor.html#setVisualNavigation)（ ） 。

```
int QTextCursor.position (self)
```

返回文档内的光标的绝对位置。将光标定位字符之间。

**See also** [setPosition](qtextcursor.html#setPosition)（ ）[movePosition](qtextcursor.html#movePosition)（ ）[anchor](qtextcursor.html#anchor)（）和[positionInBlock](qtextcursor.html#positionInBlock)（ ） 。

```
int QTextCursor.positionInBlock (self)
```

返回块内的光标的相对位置。将光标定位字符之间。

这等效于`position() - block().position()`。

此功能被引入Qt的4.7 。

**See also** [position](qtextcursor.html#position)（ ） 。

```
QTextCursor.removeSelectedText (self)
```

如果有选择，它的内容将被删除，否则什么都不做。

**See also** [hasSelection](qtextcursor.html#hasSelection)（ ） 。

```
QTextCursor.select (self, SelectionType selection)
```

根据给定的选择文档中的文本_selection_。

```
(int firstRow, int numRows, int firstColumn, int numColumns) QTextCursor.selectedTableCells (self)
```

如果选择跨越表格单元格，_firstRow_填入第一行中选择的数量，_firstColumn_以在选择第一列的数目，并_numRows_和_numColumns_以行和列的选择数目。如果选择不跨越任何表格单元格的结果是无害的，但不确定。

```
QString QTextCursor.selectedText (self)
```

返回当前选择的文本（可能为空） 。这只能返回文本，没有丰富的文本格式的信息。如果你想有一个文档片段（即格式化的富文本）的使用[selection](qtextcursor.html#selection)（ ）来代替。

**Note:**如果从编辑获得的选择跨越一个换行符，文本将包含一个Unicode ü 2029段分隔符，而不是一个换行符`\n`字符。使用[QString.replace](qstring.html#replace)（）与换行符替换这些字符。

```
QTextDocumentFragment QTextCursor.selection (self)
```

[](qtextdocumentfragment.html)

[返回当前的选择（可能为空） ，其所有的格式化信息。如果你只是想选定的文本（即纯文本）的使用](qtextdocumentfragment.html)[selectedText](qtextcursor.html#selectedText)（ ）来代替。

**Note:**不像[QTextDocumentFragment.toPlainText](qtextdocumentfragment.html#toPlainText)（ ）[selectedText](qtextcursor.html#selectedText)（ ）可能包括特殊的Unicode字符，如[QChar.ParagraphSeparator](qchar.html#SpecialCharacter-enum)。

**See also** [QTextDocumentFragment.toPlainText](qtextdocumentfragment.html#toPlainText)（ ） 。

```
int QTextCursor.selectionEnd (self)
```

返回所选内容的末尾或[position](qtextcursor.html#position)（）如果光标没有选择。

**See also** [selectionStart](qtextcursor.html#selectionStart)（ ）[position](qtextcursor.html#position)（）和[anchor](qtextcursor.html#anchor)（ ） 。

```
int QTextCursor.selectionStart (self)
```

返回所选内容的开始或[position](qtextcursor.html#position)（）如果光标没有选择。

**See also** [selectionEnd](qtextcursor.html#selectionEnd)（ ）[position](qtextcursor.html#position)（）和[anchor](qtextcursor.html#anchor)（ ） 。

```
QTextCursor.setBlockCharFormat (self, QTextCharFormat format)
```

设置当前块的块char格式（或包含在选区中的所有块） ，以_format_。

**See also** [blockCharFormat](qtextcursor.html#blockCharFormat)（ ） 。

```
QTextCursor.setBlockFormat (self, QTextBlockFormat format)
```

将当前块的块格式（或包含在选择的所有块），以_format_。

**See also** [blockFormat](qtextcursor.html#blockFormat)（）和[mergeBlockFormat](qtextcursor.html#mergeBlockFormat)（ ） 。

```
QTextCursor.setCharFormat (self, QTextCharFormat format)
```

设置光标的当前字符格式到给定_format_。如果光标有一个选择，给定的_format_应用到当前的选择。

**See also** [charFormat](qtextcursor.html#charFormat)（ ）[hasSelection](qtextcursor.html#hasSelection)（）和[mergeCharFormat](qtextcursor.html#mergeCharFormat)（ ） 。

```
QTextCursor.setKeepPositionOnInsert (self, bool b)
```

定义游标是否应保持其目前的位置，当文本被插入到光标的当前位置。

If _b_诚然，光标保持其当前位置，当文字被插入到光标的：放置。如果_b_是假的，光标移动随插入的文本。

默认值为False 。

请注意，光标移动始终文本时，光标的当前位置之前插入，并且始终保持其位置时，文本光标的当前位置后插入。

此功能被引入Qt的4.7 。

**See also** [keepPositionOnInsert](qtextcursor.html#keepPositionOnInsert)（ ） 。

```
QTextCursor.setPosition (self, int pos, MoveMode mode = QTextCursor.MoveAnchor)
```

将光标移动到所指定的文件中的绝对位置_pos_使用`MoveMode`通过指定_m_。将光标定位字符之间。

**See also** [position](qtextcursor.html#position)（ ）[movePosition](qtextcursor.html#movePosition)（）和[anchor](qtextcursor.html#anchor)（ ） 。

```
QTextCursor.setVerticalMovementX (self, int x)
```

设置为垂直光标运动的视觉x位置，以_x_。

垂直运动x位置自动清零当光标水平移动，并保持不变，当光标上下移动。该机制允许光标上下移动以与比例字体在视觉上的直线，并轻轻地“跳”过短的线路。

值-1表示没有预定义的x位置。然后，它会自动在下一次光标向上或向下移动设置。

此功能被引入Qt的4.7 。

**See also** [verticalMovementX](qtextcursor.html#verticalMovementX)（ ） 。

```
QTextCursor.setVisualNavigation (self, bool b)
```

设置视觉导航到_b_。

视觉导航是指跳过隐藏的文本pragraphs 。默认值为False 。

此功能被引入Qt的4.4 。

**See also** [visualNavigation](qtextcursor.html#visualNavigation)（）和[movePosition](qtextcursor.html#movePosition)（ ） 。

```
int QTextCursor.verticalMovementX (self)
```

返回垂直光标运动的视觉x位置。

值-1表示没有预定义的x位置。然后，它会自动在下一次光标向上或向下移动设置。

此功能被引入Qt的4.7 。

**See also** [setVerticalMovementX](qtextcursor.html#setVerticalMovementX)（ ） 。

```
bool QTextCursor.visualNavigation (self)
```

返回True如果光标做视觉导航;否则返回False。

视觉导航是指跳过隐藏的文本pragraphs 。默认值为False 。

此功能被引入Qt的4.4 。

**See also** [setVisualNavigation](qtextcursor.html#setVisualNavigation)（）和[movePosition](qtextcursor.html#movePosition)（ ） 。

```
bool QTextCursor.__eq__ (self, QTextCursor rhs)
```

```
bool QTextCursor.__ge__ (self, QTextCursor rhs)
```

```
bool QTextCursor.__gt__ (self, QTextCursor rhs)
```

```
bool QTextCursor.__le__ (self, QTextCursor rhs)
```

```
bool QTextCursor.__lt__ (self, QTextCursor rhs)
```

```
bool QTextCursor.__ne__ (self, QTextCursor rhs)
```