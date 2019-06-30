# QTextDocument Class Reference

## [[QtGui](index.htm) module]

该另外，QTextDocument类认为，可以查看和编辑使用格式化的文本[QTextEdit](qtextedit.html)。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum FindFlag { FindBackward, FindCaseSensitively, FindWholeWords }`
*   `class **[FindFlags](index.htm)**`
*   `enum MetaInformation { DocumentTitle, DocumentUrl }`
*   `enum ResourceType { HtmlResource, ImageResource, StyleSheetResource, UserResource }`
*   `enum Stacks { UndoStack, RedoStack, UndoAndRedoStacks }`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `__init__ (self, QString text, QObject parent = None)`
*   `addResource (self, int type, QUrl name, QVariant resource)`
*   `adjustSize (self)`
*   `list-of-QTextFormat allFormats (self)`
*   `int availableRedoSteps (self)`
*   `int availableUndoSteps (self)`
*   `QTextBlock begin (self)`
*   `int blockCount (self)`
*   `QChar characterAt (self, int pos)`
*   `int characterCount (self)`
*   `clear (self)`
*   `clearUndoRedoStacks (self, Stacks stacks = QTextDocument.UndoAndRedoStacks)`
*   `QTextDocument clone (self, QObject parent = None)`
*   `QTextObject createObject (self, QTextFormat f)`
*   `Qt.CursorMoveStyle defaultCursorMoveStyle (self)`
*   `QFont defaultFont (self)`
*   `QString defaultStyleSheet (self)`
*   `QTextOption defaultTextOption (self)`
*   `QAbstractTextDocumentLayout documentLayout (self)`
*   `float documentMargin (self)`
*   `drawContents (self, QPainter p, QRectF rect = QRectF())`
*   `QTextBlock end (self)`
*   `QTextCursor find (self, QString subString, int position = 0, FindFlags options = 0)`
*   `QTextCursor find (self, QRegExp expr, int position = 0, FindFlags options = 0)`
*   `QTextCursor find (self, QString subString, QTextCursor cursor, FindFlags options = 0)`
*   `QTextCursor find (self, QRegExp expr, QTextCursor cursor, FindFlags options = 0)`
*   `QTextBlock findBlock (self, int pos)`
*   `QTextBlock findBlockByLineNumber (self, int blockNumber)`
*   `QTextBlock findBlockByNumber (self, int blockNumber)`
*   `QTextBlock firstBlock (self)`
*   `float idealWidth (self)`
*   `float indentWidth (self)`
*   `bool isEmpty (self)`
*   `bool isModified (self)`
*   `bool isRedoAvailable (self)`
*   `bool isUndoAvailable (self)`
*   `bool isUndoRedoEnabled (self)`
*   `QTextBlock lastBlock (self)`
*   `int lineCount (self)`
*   `QVariant loadResource (self, int type, QUrl name)`
*   `markContentsDirty (self, int from, int length)`
*   `int maximumBlockCount (self)`
*   `QString metaInformation (self, MetaInformation info)`
*   `QTextObject object (self, int objectIndex)`
*   `QTextObject objectForFormat (self, QTextFormat)`
*   `int pageCount (self)`
*   `QSizeF pageSize (self)`
*   `print (self, QPrinter printer)`
*   `print_ (self, QPrinter printer)`
*   `redo (self)`
*   `redo (self, QTextCursor cursor)`
*   `QVariant resource (self, int type, QUrl name)`
*   `int revision (self)`
*   `QTextFrame rootFrame (self)`
*   `setDefaultCursorMoveStyle (self, Qt.CursorMoveStyle style)`
*   `setDefaultFont (self, QFont font)`
*   `setDefaultStyleSheet (self, QString sheet)`
*   `setDefaultTextOption (self, QTextOption option)`
*   `setDocumentLayout (self, QAbstractTextDocumentLayout layout)`
*   `setDocumentMargin (self, float margin)`
*   `setHtml (self, QString html)`
*   `setIndentWidth (self, float width)`
*   `setMaximumBlockCount (self, int maximum)`
*   `setMetaInformation (self, MetaInformation info, QString)`
*   `setModified (self, bool on = True)`
*   `setPageSize (self, QSizeF size)`
*   `setPlainText (self, QString text)`
*   `setTextWidth (self, float width)`
*   `setUndoRedoEnabled (self, bool enable)`
*   `setUseDesignMetrics (self, bool b)`
*   `QSizeF size (self)`
*   `float textWidth (self)`
*   `QString toHtml (self, QByteArray encoding = QByteArray())`
*   `QString toPlainText (self)`
*   `undo (self)`
*   `undo (self, QTextCursor cursor)`
*   `bool useDesignMetrics (self)`

### Qt Signals

*   `void blockCountChanged (int)`
*   `void contentsChange (int,int,int)`
*   `void contentsChanged ()`
*   `void cursorPositionChanged (const QTextCursor&)`
*   `void documentLayoutChanged ()`
*   `void modificationChanged (bool)`
*   `void redoAvailable (bool)`
*   `void undoAvailable (bool)`
*   `void undoCommandAdded ()`

* * *

## Detailed Description

该另外，QTextDocument类认为，可以查看和编辑使用格式化的文本[QTextEdit](qtextedit.html)。

另外，QTextDocument是一个容器的结构化富文本文档，提供了样式的文本和各类文档元素，例如列表，表格，框架和图像的支持。它们可以用在被创建[QTextEdit](qtextedit.html)或独立使用。

每个文档元素是由一个相关的格式对象描述。每种格式的对象被视为由QTextDocuments一个唯一的对象，并且可以被传递到[objectForFormat](qtextdocument.html#objectForFormat)（）来获得，它被应用到文档元素。

一个另外，QTextDocument可以通过编程使用进行编辑[QTextCursor](qtextcursor.html)的，其内容可以通过遍历文档结构进行检查。整个文档结构被存储为根框架之下文档元素的层次结构，发现了与[rootFrame](qtextdocument.html#rootFrame)（）函数。另外，如果你只是想遍历文档的文本内容，您可以使用[begin](qtextdocument.html#begin)（ ）[end](qtextdocument.html#end)（）和[findBlock](qtextdocument.html#findBlock)（ ）来检索文本块，你可以检查和遍历。

一个文件的布局是由确定的[documentLayout](qtextdocument.html#documentLayout)（ ） ，你可以创建自己的[QAbstractTextDocumentLayout](qabstracttextdocumentlayout.html)子类并使用它设置[setDocumentLayout](qtextdocument.html#setDocumentLayout)（ ）如果你想使用自己的布局逻辑。文档的标题和其他元信息可以通过调用来获得[metaInformation](qtextdocument.html#metaInformation)（）函数。对于通过向用户公开文件[QTextEdit](qtextedit.html)类，文档标题也可通过[QTextEdit.documentTitle](qtextedit.html#documentTitle-prop)（）函数。

该[toPlainText](qtextdocument.html#toPlainText)（）和[toHtml](qtextdocument.html#toHtml)（ ）的便利功能允许您检索文件的内容为纯文本和HTML 。该文件的文本，可使用搜索的[find](qtextdocument.html#find)（）函数。

对文档进行操作的撤消/重做可使用控制[setUndoRedoEnabled](qtextdocument.html#undoRedoEnabled-prop)（）函数。撤消/重做系统可以由一个编辑控件通过被控制的[undo](qtextdocument.html#undo)（）和[redo](qtextdocument.html#redo)（ ）插槽，该文件还提供了[contentsChanged](qtextdocument.html#contentsChanged)（ ）[undoAvailable](qtextdocument.html#undoAvailable)（）和[redoAvailable](qtextdocument.html#redoAvailable)（ ）是通知连接编辑器部件有关撤消/重做系统的状态信号。下面是一个另外，QTextDocument的撤消/重做操作：

*   Insertion or removal of characters. A sequence of insertions or removals within the same text block are regarded as a single undo/redo operation.
*   Insertion or removal of text blocks. Sequences of insertion or removals in a single operation (e.g., by selecting and then deleting text) are regarded as a single undo/redo operation.
*   Text character format changes.
*   Text block format changes.
*   Text block group format changes.

* * *

## Type Documentation

```
QTextDocument.FindFlag
```

这个枚举说明可供选择[QTextDocument](qtextdocument.html)的发现功能。该选项可以是或的结果一起从下面的列表：

| Constant | Value | Description |
| --- | --- | --- |
| `QTextDocument.FindBackward` | `0x00001` | 向后搜索，而不是向前。 |
| `QTextDocument.FindCaseSensitively` | `0x00002` | 默认情况下找到工作不区分大小写。指定此选项改变行为，以区分大小写的查找操作。 |
| `QTextDocument.FindWholeWords` | `0x00004` | 使得找到匹配的唯一完整的话。 |

该FindFlags类型是一个typedef为[QFlags](index.htm)\u003cFindFlag\u003e 。它存储FindFlag值的或组合。

```
QTextDocument.MetaInformation
```

该枚举描述了不同类型的元数据信息可以被添加到文档中。

| Constant | Value | Description |
| --- | --- | --- |
| `QTextDocument.DocumentTitle` | `0` | 文档的标题。 |
| `QTextDocument.DocumentUrl` | `1` | 该文档的URL 。该[loadResource](qtextdocument.html#loadResource)相对于加载资源时（ ）函数使用这个URL为基础。 |

**See also** [metaInformation](qtextdocument.html#metaInformation)（）和[setMetaInformation](qtextdocument.html#setMetaInformation)（ ） 。

```
QTextDocument.ResourceType
```

该枚举描述了可以通过以下方式加载的资源类型[QTextDocument](qtextdocument.html)的[loadResource](qtextdocument.html#loadResource)（）函数。

| Constant | Value | Description |
| --- | --- | --- |
| `QTextDocument.HtmlResource` | `1` | 资源包含HTML 。 |
| `QTextDocument.ImageResource` | `2` | 该资源包含图像数据。目前支持的数据类型[QVariant.Pixmap](qvariant.html#Type-enum)和[QVariant.Image](qvariant.html#Type-enum)。如果相应的变量的类型是[QVariant.ByteArray](qvariant.html#Type-enum)然后Qt的尝试使用QImage.loadFromData加载图像。[QVariant.Icon](qvariant.html#Type-enum)目前不支持。需要的图标转换为支持的类型之一第一，例如使用QIcon.pixmap 。 |
| `QTextDocument.StyleSheetResource` | `3` | 该资源包含CSS 。 |
| `QTextDocument.UserResource` | `100` | 用户定义资源类型的第一个可用值。 |

**See also** [loadResource](qtextdocument.html#loadResource)（ ） 。

```
QTextDocument.Stacks
```

| Constant | Value | Description |
| --- | --- | --- |
| `QTextDocument.UndoStack` | `0x01` | 撤消堆栈。 |
| `QTextDocument.RedoStack` | `0x02` | 重做堆栈。 |
| `QTextDocument.UndoAndRedoStacks` | `UndoStack &#124; RedoStack` | 无论是撤销和重做堆栈。 |

* * *

## Method Documentation

```
QTextDocument.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个空[QTextDocument](qtextdocument.html)用给定的_parent_。

```
QTextDocument.__init__ (self, QString text, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QTextDocument](qtextdocument.html)含有纯（未格式化）_text_指定，并与给定的_parent_。

```
QTextDocument.addResource (self, int type, QUrl name, QVariant resource)
```

添加资源_resource_到资源高速缓存，用_type_和_name_作为标识符。_type_应该是从一个值[QTextDocument.ResourceType](qtextdocument.html#ResourceType-enum)。

例如，您可以以从文档中引用它添加一个图像作为一个资源：

```
     document->addResource([QTextDocument](qtextdocument.html).ImageResource,
         [QUrl](qurl.html)("mydata://image.png"), [QVariant](qvariant.html)(image));

```

该图像可以通过被插入到文档中的[QTextCursor](qtextcursor.html)API ：

```
     [QTextImageFormat](qtextimageformat.html) imageFormat;
     imageFormat.setName("mydata://image.png");
     cursor.insertImage(imageFormat);

```

或者，您可以使用HTML中插入图像`img`标籤：

```
     editor->append("<img src=\"mydata://image.png\" />");

```

```
QTextDocument.adjustSize (self)
```

调整文件到一个合理的规模。

这个函数中引入了Qt 4.2中。

**See also** [idealWidth](qtextdocument.html#idealWidth)（ ）[textWidth](qtextdocument.html#textWidth-prop)和[size](qtextdocument.html#size-prop)。

```
list-of-QTextFormat QTextDocument.allFormats (self)
```

返回的文本格式的所有文档中使用的格式的向量。

```
int QTextDocument.availableRedoSteps (self)
```

返回可用的重做步骤的数目。

此功能被引入Qt的4.6 。

**See also** [isRedoAvailable](qtextdocument.html#isRedoAvailable)（ ） 。

```
int QTextDocument.availableUndoSteps (self)
```

返回可用撤消的步骤数。

此功能被引入Qt的4.6 。

**See also** [isUndoAvailable](qtextdocument.html#isUndoAvailable)（ ） 。

```
QTextBlock QTextDocument.begin (self)
```

[

返回文档的第一个文本块。

](qtextblock.html)

[**See also**](qtextblock.html) [firstBlock](qtextdocument.html#firstBlock)（ ） 。

```
int QTextDocument.blockCount (self)
```

```
QChar QTextDocument.characterAt (self, int pos)
```

返回字符的位置_pos_，或者一个空字符，如果该位置超出了范围。

此功能被引入Qt的4.5 。

**See also** [characterCount](qtextdocument.html#characterCount)（ ） 。

```
int QTextDocument.characterCount (self)
```

返回本文件中的字符数。

此功能被引入Qt的4.5 。

**See also** [blockCount](qtextdocument.html#blockCount-prop)（）和[characterAt](qtextdocument.html#characterAt)（ ） 。

```
QTextDocument.clear (self)
```

清除文件。

```
QTextDocument.clearUndoRedoStacks (self, Stacks stacks = QTextDocument.UndoAndRedoStacks)
```

清除由指定的堆栈_stacksToClear_。

此方法清除撤消堆栈，重做堆栈，或者两者都有（默认值）的任何命令。如果命令被清除时，适当的信号被发射，[QTextDocument.undoAvailable](qtextdocument.html#undoAvailable)（）或[QTextDocument.redoAvailable](qtextdocument.html#redoAvailable)（ ） 。

此功能被引入Qt的4.7 。

**See also** [QTextDocument.undoAvailable](qtextdocument.html#undoAvailable)（）和[QTextDocument.redoAvailable](qtextdocument.html#redoAvailable)（ ） 。

```
QTextDocument QTextDocument.clone (self, QObject parent = None)
```

[

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

](qtextdocument.html)

[创建一个新的](qtextdocument.html)[QTextDocument](qtextdocument.html)即这个文本文件的一个副本。_parent_是返回文本文档的父。

```
QTextObject QTextDocument.createObject (self, QTextFormat f)
```

[](qtextobject.html)

[创建并返回一个新的文档对象（一](qtextobject.html)[QTextObject](qtextobject.html)） ，根据给定的_format_。

QTextObjects总是会得到通过这种方法创建的，所以如果你使用自定义的文本对象文档里面你必须重新实现它。

```
Qt.CursorMoveStyle QTextDocument.defaultCursorMoveStyle (self)
```

[](qt.html#CursorMoveStyle-enum)

[默认光标的运动风格被用于所有](qt.html#CursorMoveStyle-enum)[QTextCursor](qtextcursor.html)从文档中创建的对象。默认值是[Qt.LogicalMoveStyle](qt.html#CursorMoveStyle-enum)。

此功能被引入Qt的4.8 。

**See also** [setDefaultCursorMoveStyle](qtextdocument.html#setDefaultCursorMoveStyle)（ ） 。

```
QFont QTextDocument.defaultFont (self)
```

[

```
QString QTextDocument.defaultStyleSheet (self)
```

](qfont.html)

```
QTextOption QTextDocument.defaultTextOption (self)
```

[](qtextoption.html)

```
QAbstractTextDocumentLayout QTextDocument.documentLayout (self)
```

[

返回此文档的文档布局。

](qabstracttextdocumentlayout.html)

[**See also**](qabstracttextdocumentlayout.html) [setDocumentLayout](qtextdocument.html#setDocumentLayout)（ ） 。

```
float QTextDocument.documentMargin (self)
```

```
QTextDocument.drawContents (self, QPainter p, QRectF rect = QRectF())
```

绘制与画家文档的内容_p_，夹在_rect_。如果_rect_是一个空矩形（默认），则该文件被涂别夹子。

这个函数中引入了Qt 4.2中。

```
QTextBlock QTextDocument.end (self)
```

[

这个函数返回一个块来测试该文档的末尾，同时遍历它。

](qtextblock.html)

```
 for (QTextBlock it = doc->begin(); it != doc->end(); it = it.next())
         cout << it.text().toStdString() << endl;

```

返回的块是无效的，并表示文档中的最后一个块后，该块。您可以使用[lastBlock](qtextdocument.html#lastBlock)（）来检索该文件的最后一个有效的块。

**See also** [lastBlock](qtextdocument.html#lastBlock)（ ） 。

```
QTextCursor QTextDocument.find (self, QString subString, int position = 0, FindFlags options = 0)
```

[

查找字符串的下一个出现，_subString_，在文档中。搜索从给定的位置_cursor_，并进行转发通过文件，除非在搜索选项另有规定。该_options_控制执行的搜索类型。

返回一个游标，如果选择的匹配_subString_被发现，否则返回空指针。

如果给定的_cursor_有一个选择，开始搜索选择之后，否则它开始在光标所在的位置。

默认情况下，搜索是区分大小写的，并且可以在文档中的任意位置匹配的文本。

](qtextcursor.html)

```
QTextCursor QTextDocument.find (self, QRegExp expr, int position = 0, FindFlags options = 0)
```

[](qtextcursor.html)

[查找下一个出现的匹配正则表达式，_expr_，在文档中。搜索从给定的位置_cursor_，并进行转发通过文件，除非在搜索选项另有规定。该_options_控制执行的搜索类型。该](qtextcursor.html)[FindCaseSensitively](qtextdocument.html#FindFlag-enum)选项被忽略这个过载，使用QRegExp.caseSensitivity代替。

返回一个游标，如果找到匹配选择的匹配，否则返回空指针。

如果给定的_cursor_有一个选择，开始搜索选择之后，否则它开始在光标所在的位置。

默认情况下，搜索是区分大小写的，并且可以在文档中的任意位置匹配的文本。

```
QTextCursor QTextDocument.find (self, QString subString, QTextCursor cursor, FindFlags options = 0)
```

[

这是一个重载函数。

查找字符串的下一个出现，_subString_，在文档中。搜索从给定的_position_，并进行转发通过文件，除非在搜索选项另有规定。该_options_控制执行的搜索类型。

返回一个游标，如果选择的匹配_subString_被发现，否则返回空指针。

如果_position_为0 （默认） ，搜索将从该文档的开头，否则它开始在指定的位置。

](qtextcursor.html)

```
QTextCursor QTextDocument.find (self, QRegExp expr, QTextCursor cursor, FindFlags options = 0)
```

[

这是一个重载函数。

](qtextcursor.html)

[查找下一个出现的匹配正则表达式，_expr_，在文档中。搜索从给定的_position_，并进行转发通过文件，除非在搜索选项另有规定。该_options_控制执行的搜索类型。该](qtextcursor.html)[FindCaseSensitively](qtextdocument.html#FindFlag-enum)选项被忽略这个过载，使用QRegExp.caseSensitivity代替。

返回一个游标，如果找到匹配选择的匹配，否则返回空指针。

如果_position_为0 （默认） ，搜索将从该文档的开头，否则它开始在指定的位置。

```
QTextBlock QTextDocument.findBlock (self, int pos)
```

[

返回包含文本块_pos_个字符。

](qtextblock.html)

```
QTextBlock QTextDocument.findBlockByLineNumber (self, int blockNumber)
```

[

返回包含指定的文本块_lineNumber_。

此功能被引入Qt的4.5 。

](qtextblock.html)

[**See also**](qtextblock.html) [QTextBlock.firstLineNumber](qtextblock.html#firstLineNumber)（ ） 。

```
QTextBlock QTextDocument.findBlockByNumber (self, int blockNumber)
```

[

具有指定返回文本块_blockNumber_。

此功能被引入Qt的4.4 。

](qtextblock.html)

[**See also**](qtextblock.html) [QTextBlock.blockNumber](qtextblock.html#blockNumber)（ ） 。

```
QTextBlock QTextDocument.firstBlock (self)
```

[

返回文档的第一个文本块。

此功能被引入Qt的4.4 。

```
float QTextDocument.idealWidth (self)
```

](qtextblock.html)

[返回文本文档的理想宽度。的理想宽度是该文件的实际使用宽度不考虑可选的路线。它始终是\u003c=](qtextblock.html)[size](qtextdocument.html#size-prop)（ ） ，宽（ ） 。

这个函数中引入了Qt 4.2中。

**See also** [adjustSize](qtextdocument.html#adjustSize)（）和[textWidth](qtextdocument.html#textWidth-prop)。

```
float QTextDocument.indentWidth (self)
```

```
bool QTextDocument.isEmpty (self)
```

返回True如果该文件是空的，否则返回False 。

```
bool QTextDocument.isModified (self)
```

```
bool QTextDocument.isRedoAvailable (self)
```

返回True如果重做可用;否则返回False。

**See also** [isUndoAvailable](qtextdocument.html#isUndoAvailable)（）和[availableRedoSteps](qtextdocument.html#availableRedoSteps)（ ） 。

```
bool QTextDocument.isUndoAvailable (self)
```

返回True如果撤消可用;否则返回False。

**See also** [isRedoAvailable](qtextdocument.html#isRedoAvailable)（）和[availableUndoSteps](qtextdocument.html#availableUndoSteps)（ ） 。

```
bool QTextDocument.isUndoRedoEnabled (self)
```

```
QTextBlock QTextDocument.lastBlock (self)
```

[

返回文档的最后一个（有效）的文本块。

此功能被引入Qt的4.4 。

```
int QTextDocument.lineCount (self)
```

返回该文件的行数（如果布局支持）。否则，这是相同的块的数目。

此功能被引入Qt的4.5 。

](qtextblock.html)

[**See also**](qtextblock.html) [blockCount](qtextdocument.html#blockCount-prop)（）和[characterCount](qtextdocument.html#characterCount)（ ） 。

```
QVariant QTextDocument.loadResource (self, int type, QUrl name)
```

将指定的数据加载_type_从具有给定的资源_name_。

这个功能是由所谓的富文本引擎不直接通过存储请求数据[QTextDocument](qtextdocument.html)的，但仍与它相关联。例如，图像是将一个名称属性间接引用[QTextImageFormat](qtextimageformat.html)对象。

当被Qt调用，_type_是的值中的一个[QTextDocument.ResourceType](qtextdocument.html#ResourceType-enum)。

如果[QTextDocument](qtextdocument.html)是的一个子对象[QTextEdit](qtextedit.html)，[QTextBrowser](qtextbrowser.html)或[QTextDocument](qtextdocument.html)本身则默认实现尝试检索从父数据。

```
QTextDocument.markContentsDirty (self, int from, int length)
```

标志着由给定的指定的内容_position_和_length_为“脏” ，通知它需要被重新布置的文档。

```
int QTextDocument.maximumBlockCount (self)
```

```
QString QTextDocument.metaInformation (self, MetaInformation info)
```

返回有关指定类型的文件元信息_info_。

**See also** [setMetaInformation](qtextdocument.html#setMetaInformation)（ ） 。

```
QTextObject QTextDocument.object (self, int objectIndex)
```

[

返回与给定关联的文本对象_objectIndex_。

](qtextobject.html)

```
QTextObject QTextDocument.objectForFormat (self, QTextFormat)
```

[

返回与格式相关联的文本对象_f_。

```
int QTextDocument.pageCount (self)
```

返回本文件中的页面的数量。

](qtextobject.html)

```
QSizeF QTextDocument.pageSize (self)
```

[

```
QTextDocument.print (self, QPrinter printer)
```

](qsizef.html)

[打印文档给定的_printer_。该](qsizef.html)[QPrinter](qprinter.html)必须设置正与该函数使用之前。

这仅仅是一个方便的方法来整份文件打印到打印机。

如果该文件是通过在一个特定的高度已经分页[pageSize](qtextdocument.html#pageSize-prop)（）属性在打印原样。

如果该文件不分页，例如像在使用一个文件[QTextEdit](qtextedit.html)，那么该文件的临时副本被创建和复制是根据的大小分成多个页面[QPrinter](qprinter.html)的paperRect （ ） 。默认情况下2厘米页边距设置在文档中的内容。此外，当前页码印在每一页的底部。

需要注意的是[QPrinter.Selection](qprinter.html#PrintRange-enum)不支持的打印范围使用此功能，因为选择是一个属性[QTextCursor](qtextcursor.html)。如果你有一个[QTextEdit](qtextedit.html)与您相关[QTextDocument](qtextdocument.html)那么你可以使用[QTextEdit](qtextedit.html)的print （ ）函数，因为[QTextEdit](qtextedit.html)有权访问用户的选择。

**See also** [QTextEdit.print](qtextedit.html#print)（ ） 。

```
QTextDocument.print_ (self, QPrinter printer)
```

打印文档给定的_printer_。该[QPrinter](qprinter.html)必须设置正与该函数使用之前。

这仅仅是一个方便的方法来整份文件打印到打印机。

如果该文件是通过在一个特定的高度已经分页[pageSize](qtextdocument.html#pageSize-prop)（）属性在打印原样。

如果该文件不分页，例如像在使用一个文件[QTextEdit](qtextedit.html)，那么该文件的临时副本被创建和复制是根据的大小分成多个页面[QPrinter](qprinter.html)的paperRect （ ） 。默认情况下2厘米页边距设置在文档中的内容。此外，当前页码印在每一页的底部。

需要注意的是[QPrinter.Selection](qprinter.html#PrintRange-enum)不支持的打印范围使用此功能，因为选择是一个属性[QTextCursor](qtextcursor.html)。如果你有一个[QTextEdit](qtextedit.html)与您相关[QTextDocument](qtextdocument.html)那么你可以使用[QTextEdit](qtextedit.html)的print （ ）函数，因为[QTextEdit](qtextedit.html)有权访问用户的选择。

**See also** [QTextEdit.print](qtextedit.html#print)（ ） 。

```
QTextDocument.redo (self)
```

这种方法也是一个Qt槽与C + +的签名`void redo()`。

重做上的文档上一次编辑操作，如果[redo is available](qtextdocument.html#isRedoAvailable)。

提供_cursor_定位在其中的出版操作被重做的位置的末端。

这个函数中引入了Qt 4.2中。

```
QTextDocument.redo (self, QTextCursor cursor)
```

这是一个重载函数。

重做上的文档上一次编辑操作，如果[redo is available](qtextdocument.html#isRedoAvailable)。

```
QVariant QTextDocument.resource (self, int type, QUrl name)
```

指定的返回数据_type_从具有给定的资源_name_。

这个功能是由所谓的富文本引擎不直接通过存储请求数据[QTextDocument](qtextdocument.html)的，但仍与它相关联。例如，图像是将一个名称属性间接引用[QTextImageFormat](qtextimageformat.html)对象。

资源文件中的内部缓存。如果资源不能在高速缓存中找到， loadResource叫尝试装载该资源。 loadResource应该那么请使用addResource将资源添加到缓存中。

**See also** [QTextDocument.ResourceType](qtextdocument.html#ResourceType-enum)。

```
int QTextDocument.revision (self)
```

返回文档的版本（如果撤消已启用） 。

修改是保证增加时不修改的文档进行编辑。

此功能被引入Qt的4.4 。

**See also** [QTextBlock.revision](qtextblock.html#revision)（）和[isModified](qtextdocument.html#modified-prop)（ ） 。

```
QTextFrame QTextDocument.rootFrame (self)
```

[

返回文档的根框架。

```
QTextDocument.setDefaultCursorMoveStyle (self, Qt.CursorMoveStyle style)
```

设置默认光标的运动风格，以给定的_style_。

此功能被引入Qt的4.8 。

](qtextframe.html)

[**See also**](qtextframe.html) [defaultCursorMoveStyle](qtextdocument.html#defaultCursorMoveStyle)（ ） 。

```
QTextDocument.setDefaultFont (self, QFont font)
```

```
QTextDocument.setDefaultStyleSheet (self, QString sheet)
```

```
QTextDocument.setDefaultTextOption (self, QTextOption option)
```

```
QTextDocument.setDocumentLayout (self, QAbstractTextDocumentLayout layout)
```

该_layout_说法有它的所有权转移给Qt的。

设置要使用的特定文件_layout_。以前的布局将被删除。

**See also** [documentLayoutChanged](qtextdocument.html#documentLayoutChanged)（ ） 。

```
QTextDocument.setDocumentMargin (self, float margin)
```

```
QTextDocument.setHtml (self, QString html)
```

替换该文件的全部内容以在给定的HTML格式的文本_html_字符串。

在HTML格式的尊重，尽可能，例如， “ \u003cb\u003e粗体\u003c / B\u003e正文”将产生的文本，其中第一个字有一个字体的粗细，给它一个大胆的外观： “**bold**文本“ 。

**Note:**它是调用者的责任，以确保文本正确解码时，[QString](qstring.html)包含HTML创建并传递给setHtml （ ） 。

**See also** [setPlainText](qtextdocument.html#setPlainText)（）和[Supported HTML Subset](index.htm)。

```
QTextDocument.setIndentWidth (self, float width)
```

```
QTextDocument.setMaximumBlockCount (self, int maximum)
```

```
QTextDocument.setMetaInformation (self, MetaInformation info, QString)
```

设置由指定类型的文件的元数据信息_info_为给定的_string_。

**See also** [metaInformation](qtextdocument.html#metaInformation)（ ） 。

```
QTextDocument.setModified (self, bool on = True)
```

这种方法也是一个Qt槽与C + +的签名`void setModified(bool = 1)`。

```
QTextDocument.setPageSize (self, QSizeF size)
```

```
QTextDocument.setPlainText (self, QString text)
```

替换该文件的整个内容与给定的纯_text_。

**See also** [setHtml](qtextdocument.html#setHtml)（ ） 。

```
QTextDocument.setTextWidth (self, float width)
```

```
QTextDocument.setUndoRedoEnabled (self, bool enable)
```

```
QTextDocument.setUseDesignMetrics (self, bool b)
```

```
QSizeF QTextDocument.size (self)
```

[

```
float QTextDocument.textWidth (self)
```

```
QString QTextDocument.toHtml (self, QByteArray encoding = QByteArray())
```

返回一个包含文档的HTML表示形式的字符串。

该_encoding_参数指定用于在HTML头中的charset属性的值。例如，如果指定'UTF - 8' ，然后将生成的HTML的开始看起来像这样：

```
 <html><head><meta http-equiv="Content-Type" content="text/html; charset=utf-8"></head><body>...

```

如果没有指定编码，然后不产生这样的元信息。

如果您以后在返回的HTML字符串转换成字节数组传输通过网络或保存到磁盘时，你应该指定编码你要在这里为转换为字节数组使用。

](qsizef.html)

[**See also**](qsizef.html) [Supported HTML Subset](index.htm)。

```
QString QTextDocument.toPlainText (self)
```

返回包含在文档中的纯文本。如果你想格式化信息使用[QTextCursor](qtextcursor.html)代替。

**See also** [toHtml](qtextdocument.html#toHtml)（ ） 。

```
QTextDocument.undo (self)
```

这种方法也是一个Qt槽与C + +的签名`void undo()`。

撤消对文档的最后一个编辑操作，如果撤消可用。提供_cursor_定位在其中的出版操作已撤消的位置的末端。

请参阅[Qt Undo Framework](index.htm)文档。

这个函数中引入了Qt 4.2中。

**See also** [undoAvailable](qtextdocument.html#undoAvailable)（）和[isUndoRedoEnabled](qtextdocument.html#undoRedoEnabled-prop)（ ） 。

```
QTextDocument.undo (self, QTextCursor cursor)
```

这是一个重载函数。

```
bool QTextDocument.useDesignMetrics (self)
```

* * *

## Qt Signal Documentation

```
void blockCountChanged (int)
```

这是该信号的默认超载。

这个信号被发射时的文本块中的文件的修改的总数。在传递的值_newBlockCount_是新的总和。

此功能被引入Qt的4.3 。

```
void contentsChange (int,int,int)
```

这是该信号的默认超载。

这个信号被发射时该文档的内容更改，例如，当文本被插入或删除，或格式化时被应用。

信息提供有关_position_字符的变化发生的位置在文件中的，字符数去除（_charsRemoved_），以及字符数加（_charsAdded_） 。

该信号发出之前，该文档的布局管理器会通知有关更改。这个钩子可以让你实现语法高亮显示的文档。

**See also** [QAbstractTextDocumentLayout.documentChanged](qabstracttextdocumentlayout.html#documentChanged)（）和[contentsChanged](qtextdocument.html#contentsChanged)（ ） 。

```
void contentsChanged ()
```

这是该信号的默认超载。

这个信号被发射时该文档的内容更改，例如，当文本被插入或删除，或格式化时被应用。

**See also** [contentsChange](qtextdocument.html#contentsChange)（ ） 。

```
void cursorPositionChanged (const QTextCursor&)
```

这是该信号的默认超载。

这个信号被发射时的光标的位置改变了由于编辑操作。改变了光标在传递_cursor_。如果你需要一个信号，当光标移动的箭头键，您可以使用[cursorPositionChanged()](qtextedit.html#cursorPositionChanged)在信号[QTextEdit](qtextedit.html)。

```
void documentLayoutChanged ()
```

这是该信号的默认超载。

当一个新的文档布局设置这个信号被发射。

此功能被引入Qt的4.4 。

**See also** [setDocumentLayout](qtextdocument.html#setDocumentLayout)（ ） 。

```
void modificationChanged (bool)
```

这是该信号的默认超载。

这个信号被发射时在文档的内容改变了，影响到修改状态的方法。如果_changed_诚然，该文件已被修改，否则为假。

例如，调用SetModified之（假）上的文档，然后插入文本引起来获得所发出的信号。如果撤消操作，使所述的文件返回到其原始未修饰的状态下，信号将得到再次发射。

```
void redoAvailable (bool)
```

这是该信号的默认超载。

这个信号被发射时重做操作变得可用（_available_为True）或不可用（_available_是假的） 。

```
void undoAvailable (bool)
```

这是该信号的默认超载。

这个信号被发射时撤销操作变得可用（_available_为True）或不可用（_available_是假的） 。

请参阅[Qt Undo Framework](index.htm)文档。

**See also** [undo](qtextdocument.html#undo)（）和[isUndoRedoEnabled](qtextdocument.html#undoRedoEnabled-prop)（ ） 。

```
void undoCommandAdded ()
```

这是该信号的默认超载。

每撤消一个新的水平被添加到时间这个信号被发射[QTextDocument](qtextdocument.html)。

此功能被引入Qt的4.4 。