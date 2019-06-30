# QTextEdit Class Reference

## [[QtGui](index.htm) module]

该的QTextEdit类提供用于编辑和显示两个平原和丰富的文本控件。[More...](#details)

继承[QAbstractScrollArea](qabstractscrollarea.html)。

通过继承[QTextBrowser](qtextbrowser.html)。

### Types

*   `class **[AutoFormatting](index.htm)**`
*   `enum AutoFormattingFlag { AutoNone, AutoBulletList, AutoAll }`
*   `class **[ExtraSelection](index.htm)**`
*   `enum LineWrapMode { NoWrap, WidgetWidth, FixedPixelWidth, FixedColumnWidth }`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `__init__ (self, QString text, QWidget parent = None)`
*   `bool acceptRichText (self)`
*   `Qt.Alignment alignment (self)`
*   `QString anchorAt (self, QPoint pos)`
*   `append (self, QString text)`
*   `AutoFormatting autoFormatting (self)`
*   `bool canInsertFromMimeData (self, QMimeData source)`
*   `bool canPaste (self)`
*   `changeEvent (self, QEvent e)`
*   `clear (self)`
*   `contextMenuEvent (self, QContextMenuEvent e)`
*   `copy (self)`
*   `QMimeData createMimeDataFromSelection (self)`
*   `QMenu createStandardContextMenu (self)`
*   `QMenu createStandardContextMenu (self, QPoint position)`
*   `QTextCharFormat currentCharFormat (self)`
*   `QFont currentFont (self)`
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
*   `focusInEvent (self, QFocusEvent e)`
*   `bool focusNextPrevChild (self, bool next)`
*   `focusOutEvent (self, QFocusEvent e)`
*   `QString fontFamily (self)`
*   `bool fontItalic (self)`
*   `float fontPointSize (self)`
*   `bool fontUnderline (self)`
*   `int fontWeight (self)`
*   `inputMethodEvent (self, QInputMethodEvent)`
*   `QVariant inputMethodQuery (self, Qt.InputMethodQuery property)`
*   `insertFromMimeData (self, QMimeData source)`
*   `insertHtml (self, QString text)`
*   `insertPlainText (self, QString text)`
*   `bool isReadOnly (self)`
*   `bool isUndoRedoEnabled (self)`
*   `keyPressEvent (self, QKeyEvent e)`
*   `keyReleaseEvent (self, QKeyEvent e)`
*   `int lineWrapColumnOrWidth (self)`
*   `LineWrapMode lineWrapMode (self)`
*   `QVariant loadResource (self, int type, QUrl name)`
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
*   `resizeEvent (self, QResizeEvent)`
*   `scrollContentsBy (self, int dx, int dy)`
*   `scrollToAnchor (self, QString name)`
*   `selectAll (self)`
*   `setAcceptRichText (self, bool accept)`
*   `setAlignment (self, Qt.Alignment a)`
*   `setAutoFormatting (self, AutoFormatting features)`
*   `setCurrentCharFormat (self, QTextCharFormat format)`
*   `setCurrentFont (self, QFont f)`
*   `setCursorWidth (self, int width)`
*   `setDocument (self, QTextDocument document)`
*   `setDocumentTitle (self, QString title)`
*   `setExtraSelections (self, list-of-QTextEdit.ExtraSelection selections)`
*   `setFontFamily (self, QString fontFamily)`
*   `setFontItalic (self, bool b)`
*   `setFontPointSize (self, float s)`
*   `setFontUnderline (self, bool b)`
*   `setFontWeight (self, int w)`
*   `setHtml (self, QString text)`
*   `setLineWrapColumnOrWidth (self, int w)`
*   `setLineWrapMode (self, LineWrapMode mode)`
*   `setOverwriteMode (self, bool overwrite)`
*   `setPlainText (self, QString text)`
*   `setReadOnly (self, bool ro)`
*   `setTabChangesFocus (self, bool b)`
*   `setTabStopWidth (self, int width)`
*   `setText (self, QString text)`
*   `setTextBackgroundColor (self, QColor c)`
*   `setTextColor (self, QColor c)`
*   `setTextCursor (self, QTextCursor cursor)`
*   `setTextInteractionFlags (self, Qt.TextInteractionFlags flags)`
*   `setUndoRedoEnabled (self, bool enable)`
*   `setWordWrapMode (self, QTextOption.WrapMode policy)`
*   `showEvent (self, QShowEvent)`
*   `bool tabChangesFocus (self)`
*   `int tabStopWidth (self)`
*   `QColor textBackgroundColor (self)`
*   `QColor textColor (self)`
*   `QTextCursor textCursor (self)`
*   `Qt.TextInteractionFlags textInteractionFlags (self)`
*   `timerEvent (self, QTimerEvent e)`
*   `QString toHtml (self)`
*   `QString toPlainText (self)`
*   `undo (self)`
*   `wheelEvent (self, QWheelEvent e)`
*   `QTextOption.WrapMode wordWrapMode (self)`
*   `zoomIn (self, int range = 1)`
*   `zoomOut (self, int range = 1)`

### Qt Signals

*   `void copyAvailable (bool)`
*   `void currentCharFormatChanged (const QTextCharFormat&)`
*   `void cursorPositionChanged ()`
*   `void redoAvailable (bool)`
*   `void selectionChanged ()`
*   `void textChanged ()`
*   `void undoAvailable (bool)`

* * *

## Detailed Description

该的QTextEdit类提供用于编辑和显示两个平原和丰富的文本控件。

### Introduction and Concepts

的QTextEdit是一种先进的所见即所得的浏览器/编辑器，支持丰富的文本格式使用HTML风格的标籤。这是优化处理大型文件，并快速响应用户输入。

QTextEdit一起工作的段落和字符。一个段落是一个格式化字符串，它是自动换行以适应窗口部件的宽度。通过阅读纯文本时，默认情况下，有一个换行符表示一个段落。文档包含零个或多个段落。段落中的单词排列按照段落的对齐方式。段落是由硬换行符分隔。一个段内的每个字符具有其自己的属性，例如，字体和颜色。

的QTextEdit可以显示图像，列表和表格。如果文本太大无法查看文本编辑的视口内，滚动条就会出现。文本编辑可以加载纯文本和HTML文件（ HTML 3.2的子集和4 ） 。

如果你只是需要显示一小块富文本使用[QLabel](qlabel.html)。

在Qt的富文本支持旨在提供一种快速，便携，高效的方式来合理的在线帮助工具添加到应用程序，并提供丰富的文本编辑器的基础。如果您发现该HTML支持不足，为您的需求，您可以考虑使用[QtWebKit](index.htm)，它提供了一个全功能的Web浏览器控件。

鼠标光标的上一个的QTextEdit的形状是[Qt.IBeamCursor](qt.html#CursorShape-enum)在默认情况下。它可以通过改变该[viewport](qabstractscrollarea.html#viewport)（ ）的游标属性。

### Using QTextEdit as a Display Widget

的QTextEdit可以显示一个大的HTML子集，包括表格和图像。

全文载或更换使用[setHtml](qtextedit.html#html-prop)（），它会删除任何现有文本，并与所传递的文本替换它[setHtml](qtextedit.html#html-prop)（ ）调用。如果你打电话[setHtml](qtextedit.html#html-prop)（ ）与传统的HTML ，然后调用[toHtml](qtextedit.html#html-prop)（ ） ，返回的文本可能有不同的标记，但会呈现相同的。整个文本可以被删除[clear](qtextedit.html#clear)（ ） 。

文本本身可以使用插入的[QTextCursor](qtextcursor.html)类或者使用的方便功能[insertHtml](qtextedit.html#insertHtml)（ ）[insertPlainText](qtextedit.html#insertPlainText)（ ）[append](qtextedit.html#append)（）或[paste](qtextedit.html#paste)（ ） 。[QTextCursor](qtextcursor.html)也能像插入表格或列表的复杂对象插入到文档中，它处理创建的选择和应用更改选定的文本。

默认情况下，文本编辑换行的空白，以适应文本编辑窗口部件。该[setLineWrapMode](qtextedit.html#lineWrapMode-prop)（ ）函数是用来指定你想要的那种换行的，或[NoWrap](qtextedit.html#LineWrapMode-enum)如果你不希望任何包装。通话[setLineWrapMode](qtextedit.html#lineWrapMode-prop)（ ）来设置一个固定像素宽度[FixedPixelWidth](qtextedit.html#LineWrapMode-enum)，或字符列（例如80列）[FixedColumnWidth](qtextedit.html#LineWrapMode-enum)与指定的像素或列[setLineWrapColumnOrWidth](qtextedit.html#lineWrapColumnOrWidth-prop)（ ） 。如果您使用自动换行到Widget的宽度[WidgetWidth](qtextedit.html#LineWrapMode-enum)，您可以指定是否要与打破空白或任何地方[setWordWrapMode](qtextedit.html#wordWrapMode-prop)（ ） 。

该[find](qtextedit.html#find)（ ）函数可以用来查找和选择文本中给定的字符串。

如果你想限制在一个的QTextEdit段的总数，例如它往往是在日志查看器有用，那么你可以使用[QTextDocument](qtextdocument.html)的maximumBlockCount属性的。

#### Read-only Key Bindings

当QTextEdit一起使用只读的键绑定仅限于导航和文字可能只用鼠标进行选择：

| Keypresses | Action |
| --- | --- |
| Up | Moves one line up. |
| Down | Moves one line down. |
| Left | Moves one character to the left. |
| Right | Moves one character to the right. |
| PageUp | Moves one (viewport) page up. |
| PageDown | Moves one (viewport) page down. |
| Home | Moves to the beginning of the text. |
| End | Moves to the end of the text. |
| Alt+Wheel | Scrolls the page horizontally (the Wheel is the mouse wheel). |
| Ctrl+Wheel | Zooms the text. |
| Ctrl+A | Selects all text. |

文本编辑可能能够提供一些元信息。例如，本[documentTitle](qtextedit.html#documentTitle-prop)（ ）函数将来自内部的HTML返回文本`&lt;title&gt;`标籤。

### Using QTextEdit as an Editor

所有有关使用的QTextEdit作为一个显示插件的信息也适用于这里。

目前char格式的属性设置[setFontItalic](qtextedit.html#setFontItalic)（ ）[setFontWeight](qtextedit.html#setFontWeight)（ ）[setFontUnderline](qtextedit.html#setFontUnderline)（ ）[setFontFamily](qtextedit.html#setFontFamily)（ ）[setFontPointSize](qtextedit.html#setFontPointSize)（ ）[setTextColor](qtextedit.html#setTextColor)（）和[setCurrentFont](qtextedit.html#setCurrentFont)（ ） 。当前段落的对齐方式设置与[setAlignment](qtextedit.html#setAlignment)（ ） 。

选择文本是由处理[QTextCursor](qtextcursor.html)类，它用于创建选择，检索的文本内容或删除选项提供的功能。你可以检索与用户可见的光标使用相对应的对象[textCursor](qtextedit.html#textCursor)（）方法。如果你想设置一个选择使用QTextEdit只需要建立一个上一个[QTextCursor](qtextcursor.html)对象，然后使该游标使用游标可见[setTextCursor](qtextedit.html#setTextCursor)（ ） 。选择可以复制到剪贴板[copy](qtextedit.html#copy)（ ） ，或剪切到剪贴板[cut](qtextedit.html#cut)（ ） 。整个文本可以使用选择[selectAll](qtextedit.html#selectAll)（ ） 。

当光标被移动和底层的格式属性的变化，[currentCharFormatChanged](qtextedit.html#currentCharFormatChanged)（）信号被发射，以反映新的光标位置处的新的属性。

的QTextEdit持有[QTextDocument](qtextdocument.html)这可以使用被检索对象的[document](qtextedit.html#document)（）方法。您也可以使用设置自己的文档对象[setDocument](qtextedit.html#setDocument)（ ） 。[QTextDocument](qtextdocument.html)发出[textChanged](qtextedit.html#textChanged)（ ）信号，如果文本的变化，它也提供了一个[isModified](index.htm#isModified)（ ）函数，如果文本已经被修改，因为它是在加载或自上次调用SetModified之用False作为参数，该参数将返回True 。此外，它还提供了撤销和重做的方法。

#### Drag and Drop

的QTextEdit还支持自定义拖放行为。默认情况下，会的QTextEdit当用户删除这些MIME类型的数据到一个文档中插入纯文本， HTML和RTF 。重新实现[canInsertFromMimeData](qtextedit.html#canInsertFromMimeData)（）和[insertFromMimeData](qtextedit.html#insertFromMimeData)（）来添加额外的MIME类型的支持。

例如，为了允许用户拖放图像投影到的QTextEdit ，你可以在以下面的方式实现这些功能：

```
 bool TextEdit.canInsertFromMimeData( const [QMimeData](qmimedata.html) *source ) const
 {
     if (source->hasImage())
         return true;
     else
         return QTextEdit.canInsertFromMimeData(source);
 }

```

我们通过返回True添加图像的MIME类型的支持。对于所有其他的MIME类型，我们使用默认的实现。

```
 void TextEdit.insertFromMimeData( const [QMimeData](qmimedata.html) *source )
 {
     if (source->hasImage())
     {
         [QImage](qimage.html) image = qvariant_cast<[QImage](qimage.html)>(source->imageData());
         [QTextCursor](qtextcursor.html) cursor = this->textCursor();
         [QTextDocument](qtextdocument.html) *document = this->document();
         document->addResource([QTextDocument](qtextdocument.html).ImageResource, [QUrl](qurl.html)("image"), image);
         cursor.insertImage("image");
     }
 }

```

我们解压缩图像从[QVariant](qvariant.html)由MIME源举行，并将其插入到文档中作为一个资源。

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
| Left | Moves the cursor one character to the left. |
| Ctrl+Left | Moves the cursor one word to the left. |
| Right | Moves the cursor one character to the right. |
| Ctrl+Right | Moves the cursor one word to the right. |
| Up | Moves the cursor one line up. |
| Down | Moves the cursor one line down. |
| PageUp | Moves the cursor one page up. |
| PageDown | Moves the cursor one page down. |
| Home | Moves the cursor to the beginning of the line. |
| Ctrl+Home | Moves the cursor to the beginning of the text. |
| End | Moves the cursor to the end of the line. |
| Ctrl+End | Moves the cursor to the end of the text. |
| Alt+Wheel | Scrolls the page horizontally (the Wheel is the mouse wheel). |

选择（标记）的文本按住Shift键的同时按下按键的运动之一，例如，_Shift+Right_将选择的字符的权利，_Shift+Ctrl+Right_将选择字的右边，等。

* * *

## Type Documentation

```
QTextEdit.AutoFormattingFlag
```

| Constant | Value | Description |
| --- | --- | --- |
| `QTextEdit.AutoNone` | `0` | 不要做任何自动格式化。 |
| `QTextEdit.AutoBulletList` | `0x00000001` | 自动创建项目符号列表（例如，当用户输入一个星号（ “*” ）在最左边的列，或压在现有列表项中输入。 |
| `QTextEdit.AutoAll` | `0xffffffff` | 适用于所有的自动格式化。目前只有自动符号列表的支持。 |

该自动格式化类型是一个typedef为[QFlags](index.htm)\u003cAutoFormattingFlag\u003e 。它存储AutoFormattingFlag值的或组合。

```
QTextEdit.LineWrapMode
```

| Constant | Value |
| --- | --- |
| `QTextEdit.NoWrap` | `0` |
| `QTextEdit.WidgetWidth` | `1` |
| `QTextEdit.FixedPixelWidth` | `2` |
| `QTextEdit.FixedColumnWidth` | `3` |

* * *

## Method Documentation

```
QTextEdit.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个空[QTextEdit](qtextedit.html)与父_parent_。

```
QTextEdit.__init__ (self, QString text, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QTextEdit](qtextedit.html)与父_parent_。文本编辑将显示的文本_text_。该文本被解释为HTML 。

```
bool QTextEdit.acceptRichText (self)
```

```
Qt.Alignment QTextEdit.alignment (self)
```

[

返回当前段落的对齐方式。

](index.htm)

[**See also**](index.htm) [setAlignment](qtextedit.html#setAlignment)（ ） 。

```
QString QTextEdit.anchorAt (self, QPoint pos)
```

返回锚的位置处的参考_pos_，或者如果没有锚存在于该点一个空字符串。

```
QTextEdit.append (self, QString text)
```

追加一个新的段落_text_到文本编辑的末尾。

**Note:**追加了新的段落将具有相同的字符格式和块格式作为当前段中，光标的位置确定。

**See also** [currentCharFormat](qtextedit.html#currentCharFormat)（）和[QTextCursor.blockFormat](qtextcursor.html#blockFormat)（ ） 。

```
AutoFormatting QTextEdit.autoFormatting (self)
```

[

```
bool QTextEdit.canInsertFromMimeData (self, QMimeData source)
```

这个函数返回True，如果MIME数据对象，由指定的内容_source_，可以被解码并插入到文档中。它被称为例如，当拖动操作期间鼠标进入这个小部件，并确定是否可以接受该拖放操作是必要的。

重新实现这项功能，让拖放额外的MIME类型的支持。

```
bool QTextEdit.canPaste (self)
```

返回是否文本可以从剪贴板粘贴到文本编辑。

这个函数中引入了Qt 4.2中。

```
QTextEdit.changeEvent (self, QEvent e)
```

](index.htm)

[从重新实现](index.htm)[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
QTextEdit.clear (self)
```

这种方法也是一个Qt槽与C + +的签名`void clear()`。

删除文本编辑中的所有文本。

请注意，撤消/重做历史是由这个函数清除。

**See also** [cut](qtextedit.html#cut)（ ）[setPlainText](qtextedit.html#plainText-prop)（）和[setHtml](qtextedit.html#html-prop)（ ） 。

```
QTextEdit.contextMenuEvent (self, QContextMenuEvent e)
```

从重新实现[QWidget.contextMenuEvent](qwidget.html#contextMenuEvent)（ ） 。

显示与标准上下文菜单创建[createStandardContextMenu](qtextedit.html#createStandardContextMenu)（ ） 。

如果您不希望文本编辑有个上下文菜单，可以设置其[contextMenuPolicy](qwidget.html#contextMenuPolicy-prop)至[Qt.NoContextMenu](qt.html#ContextMenuPolicy-enum)。如果你想自定义右键菜单，重新实现这个函数。如果你想扩展标准上下文菜单，重新实现这个函数，调用[createStandardContextMenu](qtextedit.html#createStandardContextMenu)（）和extend菜单返回。

有关事件的信息传递中_event_对象。

```
 void MyTextEdit.contextMenuEvent([QContextMenuEvent](qcontextmenuevent.html) *event)
 {
     [QMenu](qmenu.html) *menu = createStandardContextMenu();
     menu->addAction(tr("My Menu Item"));
     //...
     menu->exec(event->globalPos());
     delete menu;
 }

```

```
QTextEdit.copy (self)
```

这种方法也是一个Qt槽与C + +的签名`void copy()`。

副本中的任何选定的文本复制到剪贴板。

**See also** [copyAvailable](qtextedit.html#copyAvailable)（ ） 。

```
QMimeData QTextEdit.createMimeDataFromSelection (self)
```

[](qmimedata.html)

[这个函数返回一个新的MIME数据对象来表示文本编辑的当前选择的内容。当选择需要被封装到一个新的被称为](qmimedata.html)[QMimeData](qmimedata.html)对象，例如，当启动一个拖放操作，或当数据被copyied到剪贴板。

如果重新实现此功能，请注意，返回的所有权[QMimeData](qmimedata.html)对象被传递给调用者。的选择可以通过使用检索到的[textCursor](qtextedit.html#textCursor)（）函数。

```
QMenu QTextEdit.createStandardContextMenu (self)
```

[](qmenu.html)

[这个函数创建当用户点击文本编辑用鼠标右键其显示在标准上下文菜单。它是从默认称为](qmenu.html)[contextMenuEvent](qtextedit.html#contextMenuEvent)（）处理。在弹出菜单的所有权被传递给调用者。

我们建议您使用createStandardContextMenu （[QPoint](qpoint.html)）版本而不是这将使那些到用户点击敏感的动作。

```
QMenu QTextEdit.createStandardContextMenu (self, QPoint position)
```

[](qmenu.html)

[这个函数创建当用户点击文本编辑用鼠标右键其显示在标准上下文菜单。它是从默认称为](qmenu.html)[contextMenuEvent](qtextedit.html#contextMenuEvent)（ ）处理程序，它需要的_position_哪里的鼠标点击是。这可以使那些到用户点击的位置敏感的动作。在弹出菜单的所有权被传递给调用者。

此功能被引入Qt的4.4 。

```
QTextCharFormat QTextEdit.currentCharFormat (self)
```

[

返回被插入新文本时所使用的字符格式。

](qtextcharformat.html)

[**See also**](qtextcharformat.html) [setCurrentCharFormat](qtextedit.html#setCurrentCharFormat)（ ） 。

```
QFont QTextEdit.currentFont (self)
```

[

返回当前格式的字体。

](qfont.html)

[**See also**](qfont.html) [setCurrentFont](qtextedit.html#setCurrentFont)（ ）[setFontFamily](qtextedit.html#setFontFamily)（）和[setFontPointSize](qtextedit.html#setFontPointSize)（ ） 。

```
QTextCursor QTextEdit.cursorForPosition (self, QPoint pos)
```

[](qtextcursor.html)

[返回](qtextcursor.html)[QTextCursor](qtextcursor.html)在位置_pos_（在视口坐标） 。

```
QRect QTextEdit.cursorRect (self, QTextCursor cursor)
```

[

返回一个矩形（在视区坐标） ，其中包括_cursor_。

](qrect.html)

```
QRect QTextEdit.cursorRect (self)
```

[

返回一个矩形（在视口中坐标） ，其中包括文本编辑的光标。

```
int QTextEdit.cursorWidth (self)
```

```
QTextEdit.cut (self)
```

这种方法也是一个Qt槽与C + +的签名`void cut()`。

将所选文本复制到剪贴板，并从文本编辑删除它。

如果没有选中的文本没有任何反应。

](qrect.html)

[**See also**](qrect.html) [copy](qtextedit.html#copy)（）和[paste](qtextedit.html#paste)（ ） 。

```
QTextDocument QTextEdit.document (self)
```

[

返回一个指针，指向底层的文件。

](qtextdocument.html)

[**See also**](qtextdocument.html) [setDocument](qtextedit.html#setDocument)（ ） 。

```
QString QTextEdit.documentTitle (self)
```

```
QTextEdit.dragEnterEvent (self, QDragEnterEvent e)
```

从重新实现[QWidget.dragEnterEvent](qwidget.html#dragEnterEvent)（ ） 。

```
QTextEdit.dragLeaveEvent (self, QDragLeaveEvent e)
```

从重新实现[QWidget.dragLeaveEvent](qwidget.html#dragLeaveEvent)（ ） 。

```
QTextEdit.dragMoveEvent (self, QDragMoveEvent e)
```

从重新实现[QWidget.dragMoveEvent](qwidget.html#dragMoveEvent)（ ） 。

```
QTextEdit.dropEvent (self, QDropEvent e)
```

从重新实现[QWidget.dropEvent](qwidget.html#dropEvent)（ ） 。

```
QTextEdit.ensureCursorVisible (self)
```

确保光标是在必要时滚动文本编辑可见。

```
bool QTextEdit.event (self, QEvent e)
```

```
list-of-QTextEdit.ExtraSelection QTextEdit.extraSelections (self)
```

返回以前设置额外的选择。

这个函数中引入了Qt 4.2中。

**See also** [setExtraSelections](qtextedit.html#setExtraSelections)（ ） 。

```
bool QTextEdit.find (self, QString exp, QTextDocument.FindFlags options = 0)
```

查找字符串的下一个出现，_exp_，使用给定的_options_。返回True如果_exp_被发现并改变光标选择匹配，否则返回False 。

```
QTextEdit.focusInEvent (self, QFocusEvent e)
```

从重新实现[QWidget.focusInEvent](qwidget.html#focusInEvent)（ ） 。

```
bool QTextEdit.focusNextPrevChild (self, bool next)
```

从重新实现[QWidget.focusNextPrevChild](qwidget.html#focusNextPrevChild)（ ） 。

```
QTextEdit.focusOutEvent (self, QFocusEvent e)
```

从重新实现[QWidget.focusOutEvent](qwidget.html#focusOutEvent)（ ） 。

```
QString QTextEdit.fontFamily (self)
```

返回当前格式的字体系列。

**See also** [setFontFamily](qtextedit.html#setFontFamily)（ ）[setCurrentFont](qtextedit.html#setCurrentFont)（）和[setFontPointSize](qtextedit.html#setFontPointSize)（ ） 。

```
bool QTextEdit.fontItalic (self)
```

返回True如果当前格式的字体是斜体，否则返回False 。

**See also** [setFontItalic](qtextedit.html#setFontItalic)（ ） 。

```
float QTextEdit.fontPointSize (self)
```

返回当前格式的字体的磅值。

**See also** [setFontFamily](qtextedit.html#setFontFamily)（ ）[setCurrentFont](qtextedit.html#setCurrentFont)（）和[setFontPointSize](qtextedit.html#setFontPointSize)（ ） 。

```
bool QTextEdit.fontUnderline (self)
```

返回True如果当前格式的字体底线，否则返回False 。

**See also** [setFontUnderline](qtextedit.html#setFontUnderline)（ ） 。

```
int QTextEdit.fontWeight (self)
```

返回当前格式的字体粗细。

**See also** [setFontWeight](qtextedit.html#setFontWeight)（ ）[setCurrentFont](qtextedit.html#setCurrentFont)（ ）[setFontPointSize](qtextedit.html#setFontPointSize)（）和[QFont.Weight](qfont.html#Weight-enum)。

```
QTextEdit.inputMethodEvent (self, QInputMethodEvent)
```

从重新实现[QWidget.inputMethodEvent](qwidget.html#inputMethodEvent)（ ） 。

```
QVariant QTextEdit.inputMethodQuery (self, Qt.InputMethodQuery property)
```

从重新实现[QWidget.inputMethodQuery](qwidget.html#inputMethodQuery)（ ） 。

```
QTextEdit.insertFromMimeData (self, QMimeData source)
```

该功能可以插入的MIME数据对象的内容，由指定的_source_，到在当前光标位置的文本编辑。它被调用时插入文本作为一个剪贴板粘贴操作的结果，或者当文本编辑接受来自拖拽数据和拖放操作。

重新实现这项功能，让拖放额外的MIME类型的支持。

```
QTextEdit.insertHtml (self, QString text)
```

这种方法也是一个Qt槽与C + +的签名`void insertHtml(const QString&)`。

便利的插槽，插入_text_这被认为是HTML格式在当前光标位置。

它等价于：

```
 edit->textCursor().insertHtml(fragment);

```

**Note:**使用此功能时使用样式表，样式表只适用于文档中的当前块。为了对整个文档应用样式表，使用[QTextDocument.setDefaultStyleSheet](qtextdocument.html#defaultStyleSheet-prop)（ ）来代替。

```
QTextEdit.insertPlainText (self, QString text)
```

这种方法也是一个Qt槽与C + +的签名`void insertPlainText(const QString&)`。

便利的插槽，插入_text_在当前光标位置。

它相当于

```
 edit->textCursor().insertText(text);

```

```
bool QTextEdit.isReadOnly (self)
```

```
bool QTextEdit.isUndoRedoEnabled (self)
```

```
QTextEdit.keyPressEvent (self, QKeyEvent e)
```

从重新实现[QWidget.keyPressEvent](qwidget.html#keyPressEvent)（ ） 。

```
QTextEdit.keyReleaseEvent (self, QKeyEvent e)
```

从重新实现[QWidget.keyReleaseEvent](qwidget.html#keyReleaseEvent)（ ） 。

```
int QTextEdit.lineWrapColumnOrWidth (self)
```

```
LineWrapMode QTextEdit.lineWrapMode (self)
```

[

```
QVariant QTextEdit.loadResource (self, int type, QUrl name)
```

加载给定指定的资源_type_和_name_。

](qtextedit.html#LineWrapMode-enum)

[这个函数是一个扩展](qtextedit.html#LineWrapMode-enum)[QTextDocument.loadResource](qtextdocument.html#loadResource)（ ） 。

**See also** [QTextDocument.loadResource](qtextdocument.html#loadResource)（ ） 。

```
QTextEdit.mergeCurrentCharFormat (self, QTextCharFormat modifier)
```

在合并中指定的属性_modifier_成通过在编辑器的光标调用QTextCursor.mergeCharFormat当前字符格式。如果编辑器有一个选择了属性_modifier_直接施加到选择。

**See also** [QTextCursor.mergeCharFormat](qtextcursor.html#mergeCharFormat)（ ） 。

```
QTextEdit.mouseDoubleClickEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mouseDoubleClickEvent](qwidget.html#mouseDoubleClickEvent)（ ） 。

```
QTextEdit.mouseMoveEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

```
QTextEdit.mousePressEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

```
QTextEdit.mouseReleaseEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

```
QTextEdit.moveCursor (self, QTextCursor.MoveOperation operation, QTextCursor.MoveMode mode = QTextCursor.MoveAnchor)
```

通过执行给定的移动光标_operation_。

If _mode_ is [QTextCursor.KeepAnchor](qtextcursor.html#MoveMode-enum)，光标选择它移动到文本上。这是当他们按住Shift键并移动光标，光标键，用户达到相同的效果。

这个函数中引入了Qt 4.2中。

**See also** [QTextCursor.movePosition](qtextcursor.html#movePosition)（ ） 。

```
bool QTextEdit.overwriteMode (self)
```

```
QTextEdit.paintEvent (self, QPaintEvent e)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

此事件处理程序可以在子类来接收传入paint事件重新实现_event_。它通常是不必要的重写本函数中的一个子类[QTextEdit](qtextedit.html)。

**Warning:**相关文本文档不能从这个函数的重新实现中修改。

```
QTextEdit.paste (self)
```

这种方法也是一个Qt槽与C + +的签名`void paste()`。

从剪贴板粘贴文本到文本编辑的当前光标位置。

如果在剪贴板中没有文本没有任何反应。

要更改此函数的行为，即要修改什么[QTextEdit](qtextedit.html)可以粘贴以及它是如何被粘贴，重新实现虚[canInsertFromMimeData](qtextedit.html#canInsertFromMimeData)（）和[insertFromMimeData](qtextedit.html#insertFromMimeData)（）函数。

**See also** [cut](qtextedit.html#cut)（）和[copy](qtextedit.html#copy)（ ） 。

```
QTextEdit.print (self, QPrinter printer)
```

方便的功能，文本编辑的文档打印到指定的_printer_。这等同于调用print方法上的文件直接，除了这个功能也支持[QPrinter.Selection](qprinter.html#PrintRange-enum)作为打印范围。

此功能被引入Qt的4.3 。

**See also** [QTextDocument.print](qtextdocument.html#print)（ ） 。

```
QTextEdit.print_ (self, QPrinter printer)
```

方便的功能，文本编辑的文档打印到指定的_printer_。这等同于调用print方法上的文件直接，除了这个功能也支持[QPrinter.Selection](qprinter.html#PrintRange-enum)作为打印范围。

此功能被引入Qt的4.3 。

**See also** [QTextDocument.print](qtextdocument.html#print)（ ） 。

```
QTextEdit.redo (self)
```

这种方法也是一个Qt槽与C + +的签名`void redo()`。

重做上次操作。

如果没有操作可以恢复，也就是说，在撤消/重做历史没有恢复步骤，没有任何反应。

这个函数中引入了Qt 4.2中。

**See also** [undo](qtextedit.html#undo)（ ） 。

```
QTextEdit.resizeEvent (self, QResizeEvent)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
QTextEdit.scrollContentsBy (self, int dx, int dy)
```

从重新实现[QAbstractScrollArea.scrollContentsBy](qabstractscrollarea.html#scrollContentsBy)（ ） 。

```
QTextEdit.scrollToAnchor (self, QString name)
```

这种方法也是一个Qt槽与C + +的签名`void scrollToAnchor(const QString&)`。

滚动文本编辑，以便与锚定_name_可见，什么也不做，如果_name_是空的，或者已经是可见的，或者是没有找到。

```
QTextEdit.selectAll (self)
```

这种方法也是一个Qt槽与C + +的签名`void selectAll()`。

选择所有文本。

**See also** [copy](qtextedit.html#copy)（ ）[cut](qtextedit.html#cut)（）和[textCursor](qtextedit.html#textCursor)（ ） 。

```
QTextEdit.setAcceptRichText (self, bool accept)
```

```
QTextEdit.setAlignment (self, Qt.Alignment a)
```

这种方法也是一个Qt槽与C + +的签名`void setAlignment(Qt::Alignment)`。

设置当前段落的对齐方式_a_。有效的路线是[Qt.AlignLeft](qt.html#AlignmentFlag-enum)，[Qt.AlignRight](qt.html#AlignmentFlag-enum)，[Qt.AlignJustify](qt.html#AlignmentFlag-enum)和[Qt.AlignCenter](qt.html#AlignmentFlag-enum)（其中中心水平方向）。

**See also** [alignment](qtextedit.html#alignment)（ ） 。

```
QTextEdit.setAutoFormatting (self, AutoFormatting features)
```

```
QTextEdit.setCurrentCharFormat (self, QTextCharFormat format)
```

设置要插入新的文本时可以使用的字符格式_format_通过调用[QTextCursor.setCharFormat](qtextcursor.html#setCharFormat)（ ）在编辑器的光标。如果编辑器有一个选择，则该字符格式被直接施加到选择。

**See also** [currentCharFormat](qtextedit.html#currentCharFormat)（ ） 。

```
QTextEdit.setCurrentFont (self, QFont f)
```

这种方法也是一个Qt槽与C + +的签名`void setCurrentFont(const QFont&)`。

设置当前格式的字体_f_。

**See also** [currentFont](qtextedit.html#currentFont)（ ）[setFontPointSize](qtextedit.html#setFontPointSize)（）和[setFontFamily](qtextedit.html#setFontFamily)（ ） 。

```
QTextEdit.setCursorWidth (self, int width)
```

```
QTextEdit.setDocument (self, QTextDocument document)
```

品牌_document_在文本编辑器中的新文件。

**Note:**编辑器_does not take ownership of the document_除非它是文档的父对象。所提供的文档的父对象仍然是对象的所有者。

该编辑器不会删除当前文件，哪怕是编辑器的一个孩子。

**See also** [document](qtextedit.html#document)（ ） 。

```
QTextEdit.setDocumentTitle (self, QString title)
```

```
QTextEdit.setExtraSelections (self, list-of-QTextEdit.ExtraSelection selections)
```

此功能允许暂时标记文档中的某些区域用给定的颜色，指定为_selections_。这可以是有用的，例如在一个节目的编辑器来标记文本的一整行与给定的背景颜色来表示一个断点的存在。

这个函数中引入了Qt 4.2中。

**See also** [QTextEdit.ExtraSelection](index.htm)和[extraSelections](qtextedit.html#extraSelections)（ ） 。

```
QTextEdit.setFontFamily (self, QString fontFamily)
```

这种方法也是一个Qt槽与C + +的签名`void setFontFamily(const QString&)`。

设置当前格式的字体家族_fontFamily_。

**See also** [fontFamily](qtextedit.html#fontFamily)（）和[setCurrentFont](qtextedit.html#setCurrentFont)（ ） 。

```
QTextEdit.setFontItalic (self, bool b)
```

这种方法也是一个Qt槽与C + +的签名`void setFontItalic(bool)`。

If _italic_诚然，设置当前格式为斜体，否则设置当前格式为非斜体。

**See also** [fontItalic](qtextedit.html#fontItalic)（ ） 。

```
QTextEdit.setFontPointSize (self, float s)
```

这种方法也是一个Qt槽与C + +的签名`void setFontPointSize(qreal)`。

设置当前格式的点大小为_s_。

注意，如果_s_是零或负数，此函数的行为没有定义。

**See also** [fontPointSize](qtextedit.html#fontPointSize)（ ）[setCurrentFont](qtextedit.html#setCurrentFont)（）和[setFontFamily](qtextedit.html#setFontFamily)（ ） 。

```
QTextEdit.setFontUnderline (self, bool b)
```

这种方法也是一个Qt槽与C + +的签名`void setFontUnderline(bool)`。

If _underline_诚然，设置当前格式强调，否则设置当前格式是没有下划线。

**See also** [fontUnderline](qtextedit.html#fontUnderline)（ ） 。

```
QTextEdit.setFontWeight (self, int w)
```

这种方法也是一个Qt槽与C + +的签名`void setFontWeight(int)`。

设置当前格式的字体粗细来定_weight_其中使用的值是在由规定的范围[QFont.Weight](qfont.html#Weight-enum)枚举。

**See also** [fontWeight](qtextedit.html#fontWeight)（ ）[setCurrentFont](qtextedit.html#setCurrentFont)（）和[setFontFamily](qtextedit.html#setFontFamily)（ ） 。

```
QTextEdit.setHtml (self, QString text)
```

这种方法也是一个Qt槽与C + +的签名`void setHtml(const QString&)`。

```
QTextEdit.setLineWrapColumnOrWidth (self, int w)
```

```
QTextEdit.setLineWrapMode (self, LineWrapMode mode)
```

```
QTextEdit.setOverwriteMode (self, bool overwrite)
```

```
QTextEdit.setPlainText (self, QString text)
```

这种方法也是一个Qt槽与C + +的签名`void setPlainText(const QString&)`。

```
QTextEdit.setReadOnly (self, bool ro)
```

```
QTextEdit.setTabChangesFocus (self, bool b)
```

```
QTextEdit.setTabStopWidth (self, int width)
```

```
QTextEdit.setText (self, QString text)
```

这种方法也是一个Qt槽与C + +的签名`void setText(const QString&)`。

设置文本编辑的_text_。该文本可以是纯文本或HTML和文本编辑会尝试猜测正确的格式。

使用[setHtml](qtextedit.html#html-prop)（）或[setPlainText](qtextedit.html#plainText-prop)（ ）直接以避免文本编辑的猜测。

这个函数中引入了Qt 4.2中。

**See also** [text](index.htm#text)（ ）[toPlainText](qtextedit.html#plainText-prop)（）和[toHtml](qtextedit.html#html-prop)（ ） 。

```
QTextEdit.setTextBackgroundColor (self, QColor c)
```

这种方法也是一个Qt槽与C + +的签名`void setTextBackgroundColor(const QColor&)`。

设置当前格式的文本背景颜色_c_。

此功能被引入Qt的4.4 。

**See also** [textBackgroundColor](qtextedit.html#textBackgroundColor)（ ） 。

```
QTextEdit.setTextColor (self, QColor c)
```

这种方法也是一个Qt槽与C + +的签名`void setTextColor(const QColor&)`。

设置当前格式的文本颜色_c_。

**See also** [textColor](qtextedit.html#textColor)（ ） 。

```
QTextEdit.setTextCursor (self, QTextCursor cursor)
```

设置可见_cursor_。

**See also** [textCursor](qtextedit.html#textCursor)（ ） 。

```
QTextEdit.setTextInteractionFlags (self, Qt.TextInteractionFlags flags)
```

```
QTextEdit.setUndoRedoEnabled (self, bool enable)
```

```
QTextEdit.setWordWrapMode (self, QTextOption.WrapMode policy)
```

```
QTextEdit.showEvent (self, QShowEvent)
```

从重新实现[QWidget.showEvent](qwidget.html#showEvent)（ ） 。

```
bool QTextEdit.tabChangesFocus (self)
```

```
int QTextEdit.tabStopWidth (self)
```

```
QColor QTextEdit.textBackgroundColor (self)
```

[

返回当前格式的文本背景颜色。

此功能被引入Qt的4.4 。

](qcolor.html)

[**See also**](qcolor.html) [setTextBackgroundColor](qtextedit.html#setTextBackgroundColor)（ ） 。

```
QColor QTextEdit.textColor (self)
```

[

返回当前格式的文本颜色。

](qcolor.html)

[**See also**](qcolor.html) [setTextColor](qtextedit.html#setTextColor)（ ） 。

```
QTextCursor QTextEdit.textCursor (self)
```

[](qtextcursor.html)

[返回的副本](qtextcursor.html)[QTextCursor](qtextcursor.html)表示当前可见的光标。请注意，在返回的指针变化不影响[QTextEdit](qtextedit.html)的游标;使用[setTextCursor](qtextedit.html#setTextCursor)（ ）来更新可见的光标。

**See also** [setTextCursor](qtextedit.html#setTextCursor)（ ） 。

```
Qt.TextInteractionFlags QTextEdit.textInteractionFlags (self)
```

[

```
QTextEdit.timerEvent (self, QTimerEvent e)
```

```
QString QTextEdit.toHtml (self)
```

```
QString QTextEdit.toPlainText (self)
```

```
QTextEdit.undo (self)
```

这种方法也是一个Qt槽与C + +的签名`void undo()`。

撤消上一个操作。

如果没有操作可以撤销，也就是说，在撤消/恢复历史中没有撤销一步，没有任何反应。

这个函数中引入了Qt 4.2中。

](index.htm)

[**See also**](index.htm) [redo](qtextedit.html#redo)（ ） 。

```
QTextEdit.wheelEvent (self, QWheelEvent e)
```

从重新实现[QWidget.wheelEvent](qwidget.html#wheelEvent)（ ） 。

```
QTextOption.WrapMode QTextEdit.wordWrapMode (self)
```

[

```
QTextEdit.zoomIn (self, int range = 1)
```

这种方法也是一个Qt槽与C + +的签名`void zoomIn(int = 1)`。

放大了的文本通过把基本字体大小_range_大点并且重新计算所有字体大小是新的大小。这不会改变任何图片的大小。

](qtextoption.html#WrapMode-enum)

[**See also**](qtextoption.html#WrapMode-enum) [zoomOut](qtextedit.html#zoomOut)（ ） 。

```
QTextEdit.zoomOut (self, int range = 1)
```

这种方法也是一个Qt槽与C + +的签名`void zoomOut(int = 1)`。

这是一个重载函数。

缩小上通过把基本字体大小的文本_range_小点并且重新计算所有字体大小是新的大小。这不会改变任何图片的大小。

**See also** [zoomIn](qtextedit.html#zoomIn)（ ） 。

* * *

## Qt Signal Documentation

```
void copyAvailable (bool)
```

这是该信号的默认超载。

当选择文本或文本编辑取消选择，这个信号被发射。

当选择文本这个信号将被发射_yes_设置为True 。如果没有文本被选中，或者如果选定的文本被取消选择这个信号被发射与_yes_设置为False 。

If _yes_是真的，那么[copy](qtextedit.html#copy)（ ）可以用来选择复制到剪贴板。如果_yes_为False，则[copy](qtextedit.html#copy)（ ）什么也不做。

**See also** [selectionChanged](qtextedit.html#selectionChanged)（ ） 。

```
void currentCharFormatChanged (const QTextCharFormat&)
```

这是该信号的默认超载。

这个信号被发射，如果当前字符格式发生了变化，例如所造成的光标位置的改变。

新格式_f_。

**See also** [setCurrentCharFormat](qtextedit.html#setCurrentCharFormat)（ ） 。

```
void cursorPositionChanged ()
```

这是该信号的默认超载。

这个信号被发射时的光标的位置改变。

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

**See also** [copyAvailable](qtextedit.html#copyAvailable)（ ） 。

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