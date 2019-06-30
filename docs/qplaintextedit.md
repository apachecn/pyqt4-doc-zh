# QPlainTextEdit Class Reference

## [[QtGui](index.htm) module]

该QPlainTextEdit类提供用于编辑和显示纯文本的小工具。[More...](#details)

继承[QAbstractScrollArea](qabstractscrollarea.html)。

### Types

*   `enum LineWrapMode { NoWrap, WidgetWidth }`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `__init__ (self, QString text, QWidget parent = None)`
*   `QString anchorAt (self, QPoint pos)`
*   `appendHtml (self, QString html)`
*   `appendPlainText (self, QString text)`
*   `bool backgroundVisible (self)`
*   `QRectF blockBoundingGeometry (self, QTextBlock block)`
*   `QRectF blockBoundingRect (self, QTextBlock block)`
*   `int blockCount (self)`
*   `bool canInsertFromMimeData (self, QMimeData source)`
*   `bool canPaste (self)`
*   `centerCursor (self)`
*   `bool centerOnScroll (self)`
*   `changeEvent (self, QEvent e)`
*   `clear (self)`
*   `QPointF contentOffset (self)`
*   `contextMenuEvent (self, QContextMenuEvent e)`
*   `copy (self)`
*   `QMimeData createMimeDataFromSelection (self)`
*   `QMenu createStandardContextMenu (self)`
*   `QTextCharFormat currentCharFormat (self)`
*   `QTextCursor cursorForPosition (self, QPoint pos)`
*   `QRect cursorRect (self, QTextCursor cursor)`
*   `QRect cursorRect (self)`
*   `int cursorWidth (self)`
*   `cut (self)`
*   `QTextDocument document (self)`
*   `QString documentTitle (self)`
*   `dragEnterEvent (self, QDragEnterEvent e)`
*   `dragLeaveEvent (self, QDragLeaveEvent e)`
*   `dragMoveEvent (self, QDragMoveEvent e)`
*   `dropEvent (self, QDropEvent e)`
*   `ensureCursorVisible (self)`
*   `bool event (self, QEvent e)`
*   `list-of-QTextEdit.ExtraSelection extraSelections (self)`
*   `bool find (self, QString exp, QTextDocument.FindFlags options = 0)`
*   `QTextBlock firstVisibleBlock (self)`
*   `focusInEvent (self, QFocusEvent e)`
*   `bool focusNextPrevChild (self, bool next)`
*   `focusOutEvent (self, QFocusEvent e)`
*   `QAbstractTextDocumentLayout.PaintContext getPaintContext (self)`
*   `inputMethodEvent (self, QInputMethodEvent)`
*   `QVariant inputMethodQuery (self, Qt.InputMethodQuery property)`
*   `insertFromMimeData (self, QMimeData source)`
*   `insertPlainText (self, QString text)`
*   `bool isReadOnly (self)`
*   `bool isUndoRedoEnabled (self)`
*   `keyPressEvent (self, QKeyEvent e)`
*   `keyReleaseEvent (self, QKeyEvent e)`
*   `LineWrapMode lineWrapMode (self)`
*   `QVariant loadResource (self, int type, QUrl name)`
*   `int maximumBlockCount (self)`
*   `mergeCurrentCharFormat (self, QTextCharFormat modifier)`
*   `mouseDoubleClickEvent (self, QMouseEvent e)`
*   `mouseMoveEvent (self, QMouseEvent e)`
*   `mousePressEvent (self, QMouseEvent e)`
*   `mouseReleaseEvent (self, QMouseEvent e)`
*   `moveCursor (self, QTextCursor.MoveOperation operation, QTextCursor.MoveMode mode = QTextCursor.MoveAnchor)`
*   `bool overwriteMode (self)`
*   `paintEvent (self, QPaintEvent e)`
*   `paste (self)`
*   `print (self, QPrinter printer)`
*   `print_ (self, QPrinter printer)`
*   `redo (self)`
*   `resizeEvent (self, QResizeEvent e)`
*   `scrollContentsBy (self, int dx, int dy)`
*   `selectAll (self)`
*   `setBackgroundVisible (self, bool visible)`
*   `setCenterOnScroll (self, bool enabled)`
*   `setCurrentCharFormat (self, QTextCharFormat format)`
*   `setCursorWidth (self, int width)`
*   `setDocument (self, QTextDocument document)`
*   `setDocumentTitle (self, QString title)`
*   `setExtraSelections (self, list-of-QTextEdit.ExtraSelection selections)`
*   `setLineWrapMode (self, LineWrapMode mode)`
*   `setMaximumBlockCount (self, int maximum)`
*   `setOverwriteMode (self, bool overwrite)`
*   `setPlainText (self, QString text)`
*   `setReadOnly (self, bool ro)`
*   `setTabChangesFocus (self, bool b)`
*   `setTabStopWidth (self, int width)`
*   `setTextCursor (self, QTextCursor cursor)`
*   `setTextInteractionFlags (self, Qt.TextInteractionFlags flags)`
*   `setUndoRedoEnabled (self, bool enable)`
*   `setWordWrapMode (self, QTextOption.WrapMode policy)`
*   `showEvent (self, QShowEvent)`
*   `bool tabChangesFocus (self)`
*   `int tabStopWidth (self)`
*   `QTextCursor textCursor (self)`
*   `Qt.TextInteractionFlags textInteractionFlags (self)`
*   `timerEvent (self, QTimerEvent e)`
*   `QString toPlainText (self)`
*   `undo (self)`
*   `wheelEvent (self, QWheelEvent e)`
*   `QTextOption.WrapMode wordWrapMode (self)`

### Qt Signals

*   `void blockCountChanged (int)`
*   `void copyAvailable (bool)`
*   `void cursorPositionChanged ()`
*   `void modificationChanged (bool)`
*   `void redoAvailable (bool)`
*   `void selectionChanged ()`
*   `void textChanged ()`
*   `void undoAvailable (bool)`
*   `void updateRequest (const QRect&,int)`

* * *

## Detailed Description

该QPlainTextEdit类提供用于编辑和显示纯文本的小工具。

### Introduction and Concepts

QPlainTextEdit是一种先进的浏览器/编辑器，支持纯文本。这是优化处理大型文件，并快速响应用户输入。

QPlainText使用非常相同的技术和概念[QTextEdit](qtextedit.html)，但最适用于纯文本的处理。

QPlainTextEdit工程对段落和字符。一个段落是一个格式化字符串，它是自动换行以适应窗口部件的宽度。通过阅读纯文本时，默认情况下，有一个换行符表示一个段落。文档包含零个或多个段落。段落是由硬换行符分隔。一个段内的每个字符具有其自己的属性，例如，字体和颜色。

鼠标光标的上一个QPlainTextEdit的形状是[Qt.IBeamCursor](qt.html#CursorShape-enum)在默认情况下。它可以通过改变该[viewport](qabstractscrollarea.html#viewport)（ ）的游标属性。

### Using QPlainTextEdit as a Display Widget

全文载或更换使用[setPlainText](qplaintextedit.html#plainText-prop)（），它会删除现有的文本和传递给文本替换它[setPlainText](qplaintextedit.html#plainText-prop)（ ） 。

文本可以使用插入的[QTextCursor](qtextcursor.html)类或者使用的方便功能[insertPlainText](qplaintextedit.html#insertPlainText)（ ）[appendPlainText](qplaintextedit.html#appendPlainText)（）或[paste](qplaintextedit.html#paste)（ ） 。

默认情况下，文本编辑换行的空白，以适应文本编辑窗口部件。该[setLineWrapMode](qplaintextedit.html#lineWrapMode-prop)（ ）函数是用来指定你想要的那种线包裹，[WidgetWidth](qplaintextedit.html#LineWrapMode-enum) or [NoWrap](qplaintextedit.html#LineWrapMode-enum)如果你不希望任何包装。如果您使用自动换行到Widget的宽度[WidgetWidth](qplaintextedit.html#LineWrapMode-enum)，您可以指定是否要与打破空白或任何地方[setWordWrapMode](qplaintextedit.html#wordWrapMode-prop)（ ） 。

该[find](qplaintextedit.html#find)（ ）函数可以用来查找和选择文本中给定的字符串。

如果你想限制在一个QPlainTextEdit段的总数，因为它是例如在日志查看器有用，那么你可以使用[maximumBlockCount](qplaintextedit.html#maximumBlockCount-prop)属性。的组合[setMaximumBlockCount](qplaintextedit.html#maximumBlockCount-prop)（）和[appendPlainText](qplaintextedit.html#appendPlainText)（ ）将QPlainTextEdit成一个高效的查看器日志文本。滚动可减少与[centerOnScroll](qplaintextedit.html#centerOnScroll-prop)（）属性，使得日志查看器更快。文字可以以有限的方式进行格式化，或者使用语法高亮显示（见下文） ，或通过添加HTML格式的文本与[appendHtml](qplaintextedit.html#appendHtml)（ ） 。虽然QPlainTextEdit不支持复杂的富文本渲染的表和浮筒，它的确支持，您可能需要在日志查看器有限段落为基础的格式。

#### Read-only Key Bindings

当QPlainTextEdit用于只读的键绑定仅限于导航和文字可能只用鼠标进行选择：

| Keypresses | Action |
| --- | --- |
| [Qt.UpArrow](qt.html#ArrowType-enum) | Moves one line up. |
| [Qt.DownArrow](qt.html#ArrowType-enum) | Moves one line down. |
| [Qt.LeftArrow](qt.html#ArrowType-enum) | Moves one character to the left. |
| [Qt.RightArrow](qt.html#ArrowType-enum) | Moves one character to the right. |
| PageUp | Moves one (viewport) page up. |
| PageDown | Moves one (viewport) page down. |
| Home | Moves to the beginning of the text. |
| End | Moves to the end of the text. |
| Alt+Wheel | Scrolls the page horizontally (the Wheel is the mouse wheel). |
| Ctrl+Wheel | Zooms the text. |
| Ctrl+A | Selects all text. |

### Using QPlainTextEdit as an Editor

关于使用QPlainTextEdit作为显示插件的信息也适用于这里。

选择文本是由处理[QTextCursor](qtextcursor.html)类，它用于创建选择，检索的文本内容或删除选项提供的功能。你可以检索与用户可见的光标使用相对应的对象[textCursor](qplaintextedit.html#textCursor)（）方法。如果你想设置一个选择在QPlainTextEdit只需要建立一个上一个[QTextCursor](qtextcursor.html)对象，然后使该游标使用游标可见[setCursor](qwidget.html#cursor-prop)（ ） 。选择可以复制到剪贴板[copy](qplaintextedit.html#copy)（ ） ，或剪切到剪贴板[cut](qplaintextedit.html#cut)（ ） 。整个文本可以使用选择[selectAll](qplaintextedit.html#selectAll)（ ） 。

QPlainTextEdit持有[QTextDocument](qtextdocument.html)这可以使用被检索对象的[document](qplaintextedit.html#document)（）方法。您也可以使用设置自己的文档对象[setDocument](qplaintextedit.html#setDocument)（ ） 。[QTextDocument](qtextdocument.html)发出[textChanged](qplaintextedit.html#textChanged)（ ）信号，如果文本的变化，它也提供了一个通过isModified （ ）函数，如果文本已经被修改，因为它是在加载或自上次调用SetModified之用False作为参数，该参数将返回True 。此外，它还提供了撤销和重做的方法。

#### Syntax Highlighting

一样[QTextEdit](qtextedit.html)， QPlainTextEdit作品连同[QSyntaxHighlighter](qsyntaxhighlighter.html)。

#### Editing Key Bindings

这是实施进行编辑键绑定列表：

| Keypresses | Action |
| --- | --- |
| Backspace | Deletes the character to the left of the cursor. |
| Delete | Deletes the character to the right of the cursor. |
| Ctrl+C | Copy the selected text to the clipboard. |
| Ctrl+Insert | Copy the selected text to the clipboard. |
| Ctrl+K | Deletes to the end of the line. |
| Ctrl+V | Pastes the clipboard text into text edit. |
| Shift+Insert | Pastes the clipboard text into text edit. |
| Ctrl+X | Deletes the selected text and copies it to the clipboard. |
| Shift+Delete | Deletes the selected text and copies it to the clipboard. |
| Ctrl+Z | Undoes the last operation. |
| Ctrl+Y | Redoes the last operation. |
| LeftArrow | Moves the cursor one character to the left. |
| Ctrl+LeftArrow | Moves the cursor one word to the left. |
| RightArrow | Moves the cursor one character to the right. |
| Ctrl+RightArrow | Moves the cursor one word to the right. |
| UpArrow | Moves the cursor one line up. |
| Ctrl+UpArrow | Moves the cursor one word up. |
| DownArrow | Moves the cursor one line down. |
| Ctrl+Down Arrow | Moves the cursor one word down. |
| PageUp | Moves the cursor one page up. |
| PageDown | Moves the cursor one page down. |
| Home | Moves the cursor to the beginning of the line. |
| Ctrl+Home | Moves the cursor to the beginning of the text. |
| End | Moves the cursor to the end of the line. |
| Ctrl+End | Moves the cursor to the end of the text. |
| Alt+Wheel | Scrolls the page horizontally (the Wheel is the mouse wheel). |
| Ctrl+Wheel | Zooms the text. |

选择（标记）的文本按住Shift键的同时按下按键的运动之一，例如，_Shift+Right Arrow_将选择的字符的权利，_Shift+Ctrl+Right Arrow_将选择字的右边，等。

### Differences to QTextEdit

QPlainTextEdit是很薄的类，使用最是背后的技术实现[QTextEdit](qtextedit.html)和[QTextDocument](qtextdocument.html)。其性能优势比[QTextEdit](qtextedit.html)利用所谓的不同和简化的文本布局大多是干[QPlainTextDocumentLayout](qplaintextdocumentlayout.html)在文本文档（见[QTextDocument.setDocumentLayout](qtextdocument.html#setDocumentLayout)（））。纯文本文档布局不支持表也不嵌入式框架，并_replaces a pixel-exact height calculation with a line-by-line respectively paragraph-by-paragraph scrolling approach_。这使得它可以处理显着较大的文档，而且还调整与实时启用自动换行的编辑器。这也使得快速日志查看器（见[setMaximumBlockCount](qplaintextedit.html#maximumBlockCount-prop)（））。

* * *

## Type Documentation

```
QPlainTextEdit.LineWrapMode
```

| Constant | Value |
| --- | --- |
| `QPlainTextEdit.NoWrap` | `0` |
| `QPlainTextEdit.WidgetWidth` | `1` |

* * *

## Method Documentation

```
QPlainTextEdit.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个空[QPlainTextEdit](qplaintextedit.html)与父_parent_。

```
QPlainTextEdit.__init__ (self, QString text, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QPlainTextEdit](qplaintextedit.html)与父_parent_。文本编辑将显示纯文本_text_。

```
QString QPlainTextEdit.anchorAt (self, QPoint pos)
```

返回锚的位置处的参考_pos_，或者如果没有锚存在于该点一个空字符串。

此功能被引入Qt的4.7 。

```
QPlainTextEdit.appendHtml (self, QString html)
```

这种方法也是一个Qt槽与C + +的签名`void appendHtml(const QString&)`。

追加一个新的段落_html_到文本编辑的末尾。

[appendPlainText](qplaintextedit.html#appendPlainText)（ ）

```
QPlainTextEdit.appendPlainText (self, QString text)
```

这种方法也是一个Qt槽与C + +的签名`void appendPlainText(const QString&)`。

追加一个新的段落_text_到文本编辑的末尾。

**See also** [appendHtml](qplaintextedit.html#appendHtml)（ ） 。

```
bool QPlainTextEdit.backgroundVisible (self)
```

```
QRectF QPlainTextEdit.blockBoundingGeometry (self, QTextBlock block)
```

[](qrectf.html)

[返回文本的边界矩形_block_在内容坐标。翻译与矩形](qrectf.html)[contentOffset](qplaintextedit.html#contentOffset)（）来获取视口的视觉坐标。

**See also** [firstVisibleBlock](qplaintextedit.html#firstVisibleBlock)（）和[blockBoundingRect](qplaintextedit.html#blockBoundingRect)（ ） 。

```
QRectF QPlainTextEdit.blockBoundingRect (self, QTextBlock block)
```

[

返回文本的边界矩形_block_在块自己的坐标。

](qrectf.html)

[**See also**](qrectf.html) [blockBoundingGeometry](qplaintextedit.html#blockBoundingGeometry)（ ） 。

```
int QPlainTextEdit.blockCount (self)
```

```
bool QPlainTextEdit.canInsertFromMimeData (self, QMimeData source)
```

这个函数返回True，如果MIME数据对象，由指定的内容_source_，可以被解码并插入到文档中。它被称为例如，当拖动操作期间鼠标进入这个小部件，并确定它是否能够接受拖动它是必要的。

```
bool QPlainTextEdit.canPaste (self)
```

返回是否文本可以从剪贴板粘贴到文本编辑。

```
QPlainTextEdit.centerCursor (self)
```

这种方法也是一个Qt槽与C + +的签名`void centerCursor()`。

滚动文件，以垂直居中的光标。

**See also** [ensureCursorVisible](qplaintextedit.html#ensureCursorVisible)（）和[centerOnScroll](qplaintextedit.html#centerOnScroll-prop)。

```
bool QPlainTextEdit.centerOnScroll (self)
```

```
QPlainTextEdit.changeEvent (self, QEvent e)
```

从重新实现[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
QPlainTextEdit.clear (self)
```

这种方法也是一个Qt槽与C + +的签名`void clear()`。

删除文本编辑中的所有文本。

请注意，撤消/重做历史是由这个函数清除。

**See also** [cut](qplaintextedit.html#cut)（）和[setPlainText](qplaintextedit.html#plainText-prop)（ ） 。

```
QPointF QPlainTextEdit.contentOffset (self)
```

[

返回视口坐标中的内容的原点。

一个纯文本编辑的内容的来源总是第一个可见的文本块的左上角。内容偏移量是从（0,0）不同的文本时，已滚动水平，或当第一个可见的块已滚动部分关闭屏幕，也就是可见的文本不启动的第一个可见块的第一行，或当第一个可见的块的第一个块和编辑器显示的边距。

](qpointf.html)

[**See also**](qpointf.html) [firstVisibleBlock](qplaintextedit.html#firstVisibleBlock)（ ）[horizontalScrollBar](qabstractscrollarea.html#horizontalScrollBar)（）和[verticalScrollBar](qabstractscrollarea.html#verticalScrollBar)（ ） 。

```
QPlainTextEdit.contextMenuEvent (self, QContextMenuEvent e)
```

从重新实现[QWidget.contextMenuEvent](qwidget.html#contextMenuEvent)（ ） 。

显示与标准上下文菜单创建[createStandardContextMenu](qplaintextedit.html#createStandardContextMenu)（ ） 。

如果您不希望文本编辑有个上下文菜单，可以设置其[contextMenuPolicy](qwidget.html#contextMenuPolicy-prop)至[Qt.NoContextMenu](qt.html#ContextMenuPolicy-enum)。如果你想自定义右键菜单，重新实现这个函数。如果你想扩展标准上下文菜单，重新实现这个函数，调用[createStandardContextMenu](qplaintextedit.html#createStandardContextMenu)（）和extend菜单返回。

有关事件的信息传递中_event_对象。

```
 void MyQPlainTextEdit.contextMenuEvent([QContextMenuEvent](qcontextmenuevent.html) *event)
 {
     [QMenu](qmenu.html) *menu = createStandardContextMenu();
     menu->addAction(tr("My Menu Item"));
     //...
     menu->exec(event->globalPos());
     delete menu;
 }

```

```
QPlainTextEdit.copy (self)
```

这种方法也是一个Qt槽与C + +的签名`void copy()`。

副本中的任何选定的文本复制到剪贴板。

**See also** [copyAvailable](qplaintextedit.html#copyAvailable)（ ） 。

```
QMimeData QPlainTextEdit.createMimeDataFromSelection (self)
```

[](qmimedata.html)

[这个函数返回一个新的MIME数据对象来表示文本编辑的当前选择的内容。当选择需要被封装到一个新的被称为](qmimedata.html)[QMimeData](qmimedata.html)对象，例如，当启动一个拖放操作，或当数据被复制到剪贴板。

如果重新实现此功能，请注意，返回的所有权[QMimeData](qmimedata.html)对象被传递给调用者。的选择可以通过使用检索到的[textCursor](qplaintextedit.html#textCursor)（）函数。

```
QMenu QPlainTextEdit.createStandardContextMenu (self)
```

[](qmenu.html)

[这个函数创建当用户点击该行编辑用鼠标右键其显示在标准上下文菜单。它是从默认称为](qmenu.html)[contextMenuEvent](qplaintextedit.html#contextMenuEvent)（）处理。在弹出菜单的所有权被传递给调用者。

```
QTextCharFormat QPlainTextEdit.currentCharFormat (self)
```

[

返回被插入新文本时所使用的字符格式。

](qtextcharformat.html)

[**See also**](qtextcharformat.html) [setCurrentCharFormat](qplaintextedit.html#setCurrentCharFormat)（ ） 。

```
QTextCursor QPlainTextEdit.cursorForPosition (self, QPoint pos)
```

[](qtextcursor.html)

[返回](qtextcursor.html)[QTextCursor](qtextcursor.html)在位置_pos_（在视口坐标） 。

```
QRect QPlainTextEdit.cursorRect (self, QTextCursor cursor)
```

[

返回一个矩形（在视区坐标） ，其中包括_cursor_。

](qrect.html)

```
QRect QPlainTextEdit.cursorRect (self)
```

[

返回一个矩形（在视口中坐标） ，其中包括文本编辑的光标。

```
int QPlainTextEdit.cursorWidth (self)
```

```
QPlainTextEdit.cut (self)
```

这种方法也是一个Qt槽与C + +的签名`void cut()`。

将所选文本复制到剪贴板，并从文本编辑删除它。

如果没有选中的文本没有任何反应。

](qrect.html)

[**See also**](qrect.html) [copy](qplaintextedit.html#copy)（）和[paste](qplaintextedit.html#paste)（ ） 。

```
QTextDocument QPlainTextEdit.document (self)
```

[

返回一个指针，指向底层的文件。

](qtextdocument.html)

[**See also**](qtextdocument.html) [setDocument](qplaintextedit.html#setDocument)（ ） 。

```
QString QPlainTextEdit.documentTitle (self)
```

```
QPlainTextEdit.dragEnterEvent (self, QDragEnterEvent e)
```

从重新实现[QWidget.dragEnterEvent](qwidget.html#dragEnterEvent)（ ） 。

```
QPlainTextEdit.dragLeaveEvent (self, QDragLeaveEvent e)
```

从重新实现[QWidget.dragLeaveEvent](qwidget.html#dragLeaveEvent)（ ） 。

```
QPlainTextEdit.dragMoveEvent (self, QDragMoveEvent e)
```

从重新实现[QWidget.dragMoveEvent](qwidget.html#dragMoveEvent)（ ） 。

```
QPlainTextEdit.dropEvent (self, QDropEvent e)
```

从重新实现[QWidget.dropEvent](qwidget.html#dropEvent)（ ） 。

```
QPlainTextEdit.ensureCursorVisible (self)
```

确保光标是在必要时滚动文本编辑可见。

**See also** [centerCursor](qplaintextedit.html#centerCursor)（）和[centerOnScroll](qplaintextedit.html#centerOnScroll-prop)。

```
bool QPlainTextEdit.event (self, QEvent e)
```

```
list-of-QTextEdit.ExtraSelection QPlainTextEdit.extraSelections (self)
```

返回以前设置额外的选择。

**See also** [setExtraSelections](qplaintextedit.html#setExtraSelections)（ ） 。

```
bool QPlainTextEdit.find (self, QString exp, QTextDocument.FindFlags options = 0)
```

查找字符串的下一个出现，_exp_，使用给定的_options_。返回True如果_exp_被发现并改变光标选择匹配，否则返回False 。

```
QTextBlock QPlainTextEdit.firstVisibleBlock (self)
```

[

返回第一个可见的块。

](qtextblock.html)

[**See also**](qtextblock.html) [blockBoundingRect](qplaintextedit.html#blockBoundingRect)（ ） 。

```
QPlainTextEdit.focusInEvent (self, QFocusEvent e)
```

从重新实现[QWidget.focusInEvent](qwidget.html#focusInEvent)（ ） 。

```
bool QPlainTextEdit.focusNextPrevChild (self, bool next)
```

从重新实现[QWidget.focusNextPrevChild](qwidget.html#focusNextPrevChild)（ ） 。

```
QPlainTextEdit.focusOutEvent (self, QFocusEvent e)
```

从重新实现[QWidget.focusOutEvent](qwidget.html#focusOutEvent)（ ） 。

```
QAbstractTextDocumentLayout.PaintContext QPlainTextEdit.getPaintContext (self)
```

[](index.htm)

[返回漆上下文](index.htm)[viewport](qabstractscrollarea.html#viewport)（ ） ，重新实现只有当有用[paintEvent](qplaintextedit.html#paintEvent)（ ） 。

```
QPlainTextEdit.inputMethodEvent (self, QInputMethodEvent)
```

从重新实现[QWidget.inputMethodEvent](qwidget.html#inputMethodEvent)（ ） 。

```
QVariant QPlainTextEdit.inputMethodQuery (self, Qt.InputMethodQuery property)
```

从重新实现[QWidget.inputMethodQuery](qwidget.html#inputMethodQuery)（ ） 。

```
QPlainTextEdit.insertFromMimeData (self, QMimeData source)
```

该功能可以插入的MIME数据对象的内容，由指定的_source_，到在当前光标位置的文本编辑。它被调用时插入文本作为一个剪贴板粘贴操作的结果，或者当文本编辑接受来自拖拽数据和拖放操作。

```
QPlainTextEdit.insertPlainText (self, QString text)
```

这种方法也是一个Qt槽与C + +的签名`void insertPlainText(const QString&)`。

便利的插槽，插入_text_在当前光标位置。

它相当于

```
 edit->textCursor().insertText(text);

```

```
bool QPlainTextEdit.isReadOnly (self)
```

```
bool QPlainTextEdit.isUndoRedoEnabled (self)
```

```
QPlainTextEdit.keyPressEvent (self, QKeyEvent e)
```

从重新实现[QWidget.keyPressEvent](qwidget.html#keyPressEvent)（ ） 。

```
QPlainTextEdit.keyReleaseEvent (self, QKeyEvent e)
```

从重新实现[QWidget.keyReleaseEvent](qwidget.html#keyReleaseEvent)（ ） 。

```
LineWrapMode QPlainTextEdit.lineWrapMode (self)
```

[

```
QVariant QPlainTextEdit.loadResource (self, int type, QUrl name)
```

加载给定指定的资源_type_和_name_。

](qplaintextedit.html#LineWrapMode-enum)

[这个函数是一个扩展](qplaintextedit.html#LineWrapMode-enum)[QTextDocument.loadResource](qtextdocument.html#loadResource)（ ） 。

**See also** [QTextDocument.loadResource](qtextdocument.html#loadResource)（ ） 。

```
int QPlainTextEdit.maximumBlockCount (self)
```

```
QPlainTextEdit.mergeCurrentCharFormat (self, QTextCharFormat modifier)
```

在合并中指定的属性_modifier_成通过在编辑器的光标调用QTextCursor.mergeCharFormat当前字符格式。如果编辑器有一个选择了属性_modifier_直接施加到选择。

**See also** [QTextCursor.mergeCharFormat](qtextcursor.html#mergeCharFormat)（ ） 。

```
QPlainTextEdit.mouseDoubleClickEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mouseDoubleClickEvent](qwidget.html#mouseDoubleClickEvent)（ ） 。

```
QPlainTextEdit.mouseMoveEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

```
QPlainTextEdit.mousePressEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

```
QPlainTextEdit.mouseReleaseEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

```
QPlainTextEdit.moveCursor (self, QTextCursor.MoveOperation operation, QTextCursor.MoveMode mode = QTextCursor.MoveAnchor)
```

通过执行给定的移动光标_operation_。

If _mode_ is [QTextCursor.KeepAnchor](qtextcursor.html#MoveMode-enum)，光标选择它移动到文本上。这是当他们按住Shift键并移动光标，光标键，用户达到相同的效果。

**See also** [QTextCursor.movePosition](qtextcursor.html#movePosition)（ ） 。

```
bool QPlainTextEdit.overwriteMode (self)
```

```
QPlainTextEdit.paintEvent (self, QPaintEvent e)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QPlainTextEdit.paste (self)
```

这种方法也是一个Qt槽与C + +的签名`void paste()`。

从剪贴板粘贴文本到文本编辑的当前光标位置。

如果在剪贴板中没有文本没有任何反应。

要更改此函数的行为，即要修改什么[QPlainTextEdit](qplaintextedit.html)可以粘贴以及它是如何被粘贴，重新实现虚[canInsertFromMimeData](qplaintextedit.html#canInsertFromMimeData)（）和[insertFromMimeData](qplaintextedit.html#insertFromMimeData)（）函数。

**See also** [cut](qplaintextedit.html#cut)（）和[copy](qplaintextedit.html#copy)（ ） 。

```
QPlainTextEdit.print (self, QPrinter printer)
```

方便的功能，文本编辑的文档打印到指定的_printer_。这等同于调用print方法上的文件直接，除了这个功能也支持[QPrinter.Selection](qprinter.html#PrintRange-enum)作为打印范围。

**See also** [QTextDocument.print](qtextdocument.html#print)（ ） 。

```
QPlainTextEdit.print_ (self, QPrinter printer)
```

方便的功能，文本编辑的文档打印到指定的_printer_。这等同于调用print方法上的文件直接，除了这个功能也支持[QPrinter.Selection](qprinter.html#PrintRange-enum)作为打印范围。

**See also** [QTextDocument.print](qtextdocument.html#print)（ ） 。

```
QPlainTextEdit.redo (self)
```

这种方法也是一个Qt槽与C + +的签名`void redo()`。

重做上次操作。

如果没有操作可以恢复，也就是说，在撤消/重做历史没有恢复步骤，没有任何反应。

**See also** [undo](qplaintextedit.html#undo)（ ） 。

```
QPlainTextEdit.resizeEvent (self, QResizeEvent e)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
QPlainTextEdit.scrollContentsBy (self, int dx, int dy)
```

从重新实现[QAbstractScrollArea.scrollContentsBy](qabstractscrollarea.html#scrollContentsBy)（ ） 。

```
QPlainTextEdit.selectAll (self)
```

这种方法也是一个Qt槽与C + +的签名`void selectAll()`。

选择所有文本。

**See also** [copy](qplaintextedit.html#copy)（ ）[cut](qplaintextedit.html#cut)（）和[textCursor](qplaintextedit.html#textCursor)（ ） 。

```
QPlainTextEdit.setBackgroundVisible (self, bool visible)
```

```
QPlainTextEdit.setCenterOnScroll (self, bool enabled)
```

```
QPlainTextEdit.setCurrentCharFormat (self, QTextCharFormat format)
```

设置要插入新的文本时可以使用的字符格式_format_通过调用[QTextCursor.setCharFormat](qtextcursor.html#setCharFormat)（ ）在编辑器的光标。如果编辑器有一个选择，则该字符格式被直接施加到选择。

**See also** [currentCharFormat](qplaintextedit.html#currentCharFormat)（ ） 。

```
QPlainTextEdit.setCursorWidth (self, int width)
```

```
QPlainTextEdit.setDocument (self, QTextDocument document)
```

品牌_document_在文本编辑器中的新文件。

父[QObject](qobject.html)所提供的文件仍然是对象的所有者。如果当前文件是文本编辑器的一个孩子，然后被删除。

该文档必须有一个文档的布局继承[QPlainTextDocumentLayout](qplaintextdocumentlayout.html)（见[QTextDocument.setDocumentLayout](qtextdocument.html#setDocumentLayout)（））。

**See also** [document](qplaintextedit.html#document)（ ） 。

```
QPlainTextEdit.setDocumentTitle (self, QString title)
```

```
QPlainTextEdit.setExtraSelections (self, list-of-QTextEdit.ExtraSelection selections)
```

此功能允许暂时标记文档中的某些区域用给定的颜色，指定为_selections_。这可以是有用的，例如在一个节目的编辑器来标记文本的一整行与给定的背景颜色来表示一个断点的存在。

**See also** [QTextEdit.ExtraSelection](index.htm)和[extraSelections](qplaintextedit.html#extraSelections)（ ） 。

```
QPlainTextEdit.setLineWrapMode (self, LineWrapMode mode)
```

```
QPlainTextEdit.setMaximumBlockCount (self, int maximum)
```

```
QPlainTextEdit.setOverwriteMode (self, bool overwrite)
```

```
QPlainTextEdit.setPlainText (self, QString text)
```

这种方法也是一个Qt槽与C + +的签名`void setPlainText(const QString&)`。

```
QPlainTextEdit.setReadOnly (self, bool ro)
```

```
QPlainTextEdit.setTabChangesFocus (self, bool b)
```

```
QPlainTextEdit.setTabStopWidth (self, int width)
```

```
QPlainTextEdit.setTextCursor (self, QTextCursor cursor)
```

设置可见_cursor_。

**See also** [textCursor](qplaintextedit.html#textCursor)（ ） 。

```
QPlainTextEdit.setTextInteractionFlags (self, Qt.TextInteractionFlags flags)
```

```
QPlainTextEdit.setUndoRedoEnabled (self, bool enable)
```

```
QPlainTextEdit.setWordWrapMode (self, QTextOption.WrapMode policy)
```

```
QPlainTextEdit.showEvent (self, QShowEvent)
```

从重新实现[QWidget.showEvent](qwidget.html#showEvent)（ ） 。

```
bool QPlainTextEdit.tabChangesFocus (self)
```

```
int QPlainTextEdit.tabStopWidth (self)
```

```
QTextCursor QPlainTextEdit.textCursor (self)
```

[](qtextcursor.html)

[返回的副本](qtextcursor.html)[QTextCursor](qtextcursor.html)表示当前可见的光标。请注意，在返回的指针变化不影响[QPlainTextEdit](qplaintextedit.html)的游标;使用[setTextCursor](qplaintextedit.html#setTextCursor)（ ）来更新可见的光标。

**See also** [setTextCursor](qplaintextedit.html#setTextCursor)（ ） 。

```
Qt.TextInteractionFlags QPlainTextEdit.textInteractionFlags (self)
```

[

```
QPlainTextEdit.timerEvent (self, QTimerEvent e)
```

```
QString QPlainTextEdit.toPlainText (self)
```

```
QPlainTextEdit.undo (self)
```

这种方法也是一个Qt槽与C + +的签名`void undo()`。

撤消上一个操作。

如果没有操作可以撤销，也就是说，在撤消/恢复历史中没有撤销一步，没有任何反应。

](index.htm)

[**See also**](index.htm) [redo](qplaintextedit.html#redo)（ ） 。

```
QPlainTextEdit.wheelEvent (self, QWheelEvent e)
```

从重新实现[QWidget.wheelEvent](qwidget.html#wheelEvent)（ ） 。

```
QTextOption.WrapMode QPlainTextEdit.wordWrapMode (self)
```

[

* * *

## Qt Signal Documentation

```
void blockCountChanged (int)
```

这是该信号的默认超载。

这个信号被发射时的块数的变化。新的块数被传递_newBlockCount_。

```
void copyAvailable (bool)
```

这是该信号的默认超载。

当选择文本或文本编辑取消选择，这个信号被发射。

当选择文本这个信号将被发射_yes_设置为True 。如果没有文本被选中，或者如果选定的文本被取消选择这个信号被发射与_yes_设置为False 。

](qtextoption.html#WrapMode-enum)

[If _yes_是真的，那么](qtextoption.html#WrapMode-enum)[copy](qplaintextedit.html#copy)（ ）可以用来选择复制到剪贴板。如果_yes_为False，则[copy](qplaintextedit.html#copy)（ ）什么也不做。

**See also** [selectionChanged](qplaintextedit.html#selectionChanged)（ ） 。

```
void cursorPositionChanged ()
```

这是该信号的默认超载。

这个信号被发射时的光标的位置改变。

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
void selectionChanged ()
```

这是该信号的默认超载。

这个信号被发射时的选择改变。

**See also** [copyAvailable](qplaintextedit.html#copyAvailable)（ ） 。

```
void textChanged ()
```

这是该信号的默认超载。

这个信号被发射时该文档的内容更改，例如，当文本被插入或删除，或格式化时被应用。

```
void undoAvailable (bool)
```

这是该信号的默认超载。

这个信号被发射时撤销操作变得可用（_available_为True）或不可用（_available_是假的） 。

```
void updateRequest (const QRect&,int)
```

这是该信号的默认超载。

当文本文档需要指定的更新这个信号被发射_rect_。如果文字滚动，_rect_将复盖整个视口区域。如果文本是垂直滚动，_dy_进行像素的视口已滚动的量。

信号的目的是支持在该如纯文本编辑子类额外的部件显示行号，断点，或其他额外的信息。