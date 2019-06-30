# QLineEdit Class Reference

## [[QtGui](index.htm) module]

在QLineEdit中widget是一个单行的文本编辑器。[More...](#details)

继承[QWidget](qwidget.html)。

### Types

*   `enum EchoMode { Normal, NoEcho, Password, PasswordEchoOnEdit }`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `__init__ (self, QString contents, QWidget parent = None)`
*   `Qt.Alignment alignment (self)`
*   `backspace (self)`
*   `changeEvent (self, QEvent)`
*   `clear (self)`
*   `QCompleter completer (self)`
*   `contextMenuEvent (self, QContextMenuEvent)`
*   `copy (self)`
*   `QMenu createStandardContextMenu (self)`
*   `cursorBackward (self, bool mark, int steps = 1)`
*   `cursorForward (self, bool mark, int steps = 1)`
*   `Qt.CursorMoveStyle cursorMoveStyle (self)`
*   `int cursorPosition (self)`
*   `int cursorPositionAt (self, QPoint pos)`
*   `QRect cursorRect (self)`
*   `cursorWordBackward (self, bool mark)`
*   `cursorWordForward (self, bool mark)`
*   `cut (self)`
*   `del_ (self)`
*   `deselect (self)`
*   `QString displayText (self)`
*   `bool dragEnabled (self)`
*   `dragEnterEvent (self, QDragEnterEvent)`
*   `dragLeaveEvent (self, QDragLeaveEvent e)`
*   `dragMoveEvent (self, QDragMoveEvent e)`
*   `dropEvent (self, QDropEvent)`
*   `EchoMode echoMode (self)`
*   `end (self, bool mark)`
*   `bool event (self, QEvent)`
*   `focusInEvent (self, QFocusEvent)`
*   `focusOutEvent (self, QFocusEvent)`
*   `(int left, int top, int right, int bottom) getTextMargins (self)`
*   `bool hasAcceptableInput (self)`
*   `bool hasFrame (self)`
*   `bool hasSelectedText (self)`
*   `home (self, bool mark)`
*   `initStyleOption (self, QStyleOptionFrame option)`
*   `QString inputMask (self)`
*   `inputMethodEvent (self, QInputMethodEvent)`
*   `QVariant inputMethodQuery (self, Qt.InputMethodQuery)`
*   `insert (self, QString)`
*   `bool isModified (self)`
*   `bool isReadOnly (self)`
*   `bool isRedoAvailable (self)`
*   `bool isUndoAvailable (self)`
*   `keyPressEvent (self, QKeyEvent)`
*   `int maxLength (self)`
*   `QSize minimumSizeHint (self)`
*   `mouseDoubleClickEvent (self, QMouseEvent)`
*   `mouseMoveEvent (self, QMouseEvent)`
*   `mousePressEvent (self, QMouseEvent)`
*   `mouseReleaseEvent (self, QMouseEvent)`
*   `paintEvent (self, QPaintEvent)`
*   `paste (self)`
*   `QString placeholderText (self)`
*   `redo (self)`
*   `selectAll (self)`
*   `QString selectedText (self)`
*   `int selectionStart (self)`
*   `setAlignment (self, Qt.Alignment flag)`
*   `setCompleter (self, QCompleter completer)`
*   `setCursorMoveStyle (self, Qt.CursorMoveStyle style)`
*   `setCursorPosition (self, int)`
*   `setDragEnabled (self, bool b)`
*   `setEchoMode (self, EchoMode)`
*   `setFrame (self, bool)`
*   `setInputMask (self, QString inputMask)`
*   `setMaxLength (self, int)`
*   `setModified (self, bool)`
*   `setPlaceholderText (self, QString)`
*   `setReadOnly (self, bool)`
*   `setSelection (self, int, int)`
*   `setText (self, QString)`
*   `setTextMargins (self, int left, int top, int right, int bottom)`
*   `setTextMargins (self, QMargins margins)`
*   `setValidator (self, QValidator)`
*   `QSize sizeHint (self)`
*   `QString text (self)`
*   `QMargins textMargins (self)`
*   `undo (self)`
*   `QValidator validator (self)`

### Qt Signals

*   `void cursorPositionChanged (int,int)`
*   `void editingFinished ()`
*   `void returnPressed ()`
*   `void selectionChanged ()`
*   `void textChanged (const QString&)`
*   `void textEdited (const QString&)`

* * *

## Detailed Description

在QLineEdit中widget是一个单行的文本编辑器。

A线编辑允许用户输入和编辑纯文本单行与编辑功能，包括撤销和重做，剪切和粘贴，拖放一个有用的集合。

通过改变[echoMode](qlineedit.html#echoMode-prop)（）一个行编辑的，它也可以被用来作为“只写”字段，用于输入密码等。

的文本的长度可被约束到[maxLength](qlineedit.html#maxLength-prop)（ ） 。该文本可以使用任意的限制[validator](qlineedit.html#validator)（）或[inputMask](qlineedit.html#inputMask-prop)（） ，或两者兼而有之。当在同一行上编辑一个验证器和输入掩码之间切换时，最好清除验证或输入掩码，以防止未定义的行为。

一个相关的类是[QTextEdit](qtextedit.html)它允许多行，富文本编辑。

您可以更改文本[setText](qlineedit.html#text-prop)（）或[insert](qlineedit.html#insert)（ ） 。全文检索与[text](qlineedit.html#text-prop)（）;显示的文本（其可以是不同的，见[EchoMode](qlineedit.html#EchoMode-enum)）检索与[displayText](qlineedit.html#displayText-prop)（ ） 。文本可以与被选择[setSelection](qlineedit.html#setSelection)（）或[selectAll](qlineedit.html#selectAll)（） ，并且选择可以是[cut](qlineedit.html#cut)（ ）[copy](qlineedit.html#copy)（ ）灭蝇灯和[paste](qlineedit.html#paste)（ ）D 。文本可与对齐[setAlignment](qlineedit.html#alignment-prop)（ ） 。

当文本改变[textChanged](qlineedit.html#textChanged)（ ）信号被发射，当文本的变化快于通过呼叫其他[setText](qlineedit.html#text-prop)（ ）的[textEdited](qlineedit.html#textEdited)（）信号被发射，当光标被移动的[cursorPositionChanged](qlineedit.html#cursorPositionChanged)（ ）信号被发射，而当回车键按下[returnPressed](qlineedit.html#returnPressed)（）信号被发射。

当编辑完成，要么是因为该行的编辑失去焦点或Return / Enter键被按下[editingFinished](qlineedit.html#editingFinished)（）信号被发射。

需要注意的是，如果有一个验证器就行了编辑设置，[returnPressed](qlineedit.html#returnPressed)（）/[editingFinished](qlineedit.html#editingFinished)（）信号将只被发射，如果验证器返回[QValidator.Acceptable](qvalidator.html#State-enum)。

默认情况下， QLineEdits必须由指定的Windows和Motif风格指南的框架，你可以通过调用的setFrame （假）将其关闭。

默认键绑定描述如下。该行编辑亦规定，提出了一些的这些编辑选项的上下文菜单（通常由单击鼠标右键调用）。

| Keypress | Action |
| --- | --- |
| Left Arrow | Moves the cursor one character to the left. |
| Shift+Left Arrow | Moves and selects text one character to the left. |
| Right Arrow | Moves the cursor one character to the right. |
| Shift+Right Arrow | Moves and selects text one character to the right. |
| Home | Moves the cursor to the beginning of the line. |
| End | Moves the cursor to the end of the line. |
| Backspace | Deletes the character to the left of the cursor. |
| Ctrl+Backspace | Deletes the word to the left of the cursor. |
| Delete | Deletes the character to the right of the cursor. |
| Ctrl+Delete | Deletes the word to the right of the cursor. |
| Ctrl+A | Select all. |
| Ctrl+C | Copies the selected text to the clipboard. |
| Ctrl+Insert | Copies the selected text to the clipboard. |
| Ctrl+K | Deletes to the end of the line. |
| Ctrl+V | Pastes the clipboard text into line edit. |
| Shift+Insert | Pastes the clipboard text into line edit. |
| Ctrl+X | Deletes the selected text and copies it to the clipboard. |
| Shift+Delete | Deletes the selected text and copies it to the clipboard. |
| Ctrl+Z | Undoes the last operation. |
| Ctrl+Y | Redoes the last undone operation. |

一个表示有效字符的任何其他键序列，将导致该字符将被插入到该行编辑。

| ![Screenshot of a Macintosh style line edit](../img/macintosh-lineedit.png) | A line edit shown in the [Macintosh widget style](index.htm). |
| ![Screenshot of a Windows XP style line edit](../img/windows-lineedit.png) | A line edit shown in the [Windows XP widget style](index.htm). |
| ![Screenshot of a Plastique style line edit](../img/plastique-lineedit.png) | A line edit shown in the [Plastique widget style](index.htm). |

* * *

## Type Documentation

```
QLineEdit.EchoMode
```

该枚举类型描述了一个行编辑应该如何显示其内容。

| Constant | Value | Description |
| --- | --- | --- |
| `QLineEdit.Normal` | `0` | 显示字符以它们输入。这是默认的。 |
| `QLineEdit.NoEcho` | `1` | 不显示任何信息。这可能是适当的密码，其中的密码，即使是长度应当保密。 |
| `QLineEdit.Password` | `2` | 显示星号而不是实际输入的字符。 |
| `QLineEdit.PasswordEchoOnEdit` | `3` | 因为他们进入编辑时，否则显示星号显示字符。 |

**See also** [setEchoMode](qlineedit.html#echoMode-prop)（）和[echoMode](qlineedit.html#echoMode-prop)（ ） 。

* * *

## Method Documentation

```
QLineEdit.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个行编辑，没有文字。

最大文本长度设置为32767个字符。

该_parent_参数被发送到[QWidget](qwidget.html)构造函数。

**See also** [setText](qlineedit.html#text-prop)（）和[setMaxLength](qlineedit.html#maxLength-prop)（ ） 。

```
QLineEdit.__init__ (self, QString contents, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个包含文本行编辑_contents_。

光标的位置被设置为一行的末尾和最大文本长度，以32767个字符。

该_parent_和参数发送到[QWidget](qwidget.html)构造函数。

**See also** [text](qlineedit.html#text-prop)（）和[setMaxLength](qlineedit.html#maxLength-prop)（ ） 。

```
Qt.Alignment QLineEdit.alignment (self)
```

[

```
QLineEdit.backspace (self)
```

如果没有文本被选中，删除的字符文本光标的左边，光标移动一个位置到左边。如果有任何文字被选中，将光标移动到所选文本的开头和选定的文本被删除。

](index.htm)

[**See also**](index.htm) [del_](qlineedit.html#del)（ ） 。

```
QLineEdit.changeEvent (self, QEvent)
```

从重新实现[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
QLineEdit.clear (self)
```

清除行编辑的内容。

**See also** [setText](qlineedit.html#text-prop)（）和[insert](qlineedit.html#insert)（ ） 。

```
QCompleter QLineEdit.completer (self)
```

[](qcompleter.html)

[返回当前](qcompleter.html)[QCompleter](qcompleter.html)提供完井。

这个函数中引入了Qt 4.2中。

**See also** [setCompleter](qlineedit.html#setCompleter)（ ） 。

```
QLineEdit.contextMenuEvent (self, QContextMenuEvent)
```

从重新实现[QWidget.contextMenuEvent](qwidget.html#contextMenuEvent)（ ） 。

显示与标准上下文菜单创建[createStandardContextMenu](qlineedit.html#createStandardContextMenu)（ ） 。

如果你不想要的行编辑有一个上下文菜单，可以设置其[contextMenuPolicy](qwidget.html#contextMenuPolicy-prop)至[Qt.NoContextMenu](qt.html#ContextMenuPolicy-enum)。如果你想自定义右键菜单，重新实现这个函数。如果你想扩展标准上下文菜单，重新实现这个函数，调用[createStandardContextMenu](qlineedit.html#createStandardContextMenu)（）和extend菜单返回。

```
 void LineEdit.contextMenuEvent([QContextMenuEvent](qcontextmenuevent.html) *event)
 {
     [QMenu](qmenu.html) *menu = createStandardContextMenu();
     menu->addAction(tr("My Menu Item"));
     //...
     menu->exec(event->globalPos());
     delete menu;
 }

```

该_event_参数用于获得该鼠标光标是产生事件时的位置。

**See also** [setContextMenuPolicy](qwidget.html#contextMenuPolicy-prop)（ ） 。

```
QLineEdit.copy (self)
```

将所选文本复制到剪贴板，如果有任何的，如果[echoMode](qlineedit.html#echoMode-prop)（）是[Normal](qlineedit.html#EchoMode-enum)。

**See also** [cut](qlineedit.html#cut)（）和[paste](qlineedit.html#paste)（ ） 。

```
QMenu QLineEdit.createStandardContextMenu (self)
```

[](qmenu.html)

[这个函数创建当用户点击该行编辑用鼠标右键其显示在标准上下文菜单。它是从默认称为](qmenu.html)[contextMenuEvent](qlineedit.html#contextMenuEvent)（）处理。在弹出菜单的所有权被传递给调用者。

```
QLineEdit.cursorBackward (self, bool mark, int steps = 1)
```

使光标向后移动_steps_字符。如果_mark_是真正的每个字符移到被添加到选择，如果_mark_是假的选择被清除。

**See also** [cursorForward](qlineedit.html#cursorForward)（ ） 。

```
QLineEdit.cursorForward (self, bool mark, int steps = 1)
```

使光标向前移动_steps_字符。如果_mark_是真正的每个字符移到被添加到选择，如果_mark_是假的选择被清除。

**See also** [cursorBackward](qlineedit.html#cursorBackward)（ ） 。

```
Qt.CursorMoveStyle QLineEdit.cursorMoveStyle (self)
```

[

```
int QLineEdit.cursorPosition (self)
```

```
int QLineEdit.cursorPositionAt (self, QPoint pos)
```

返回点下的光标位置_pos_。

](qt.html#CursorMoveStyle-enum)

```
QRect QLineEdit.cursorRect (self)
```

[

返回包含lineedit光标的矩形。

此功能被引入Qt的4.4 。

```
QLineEdit.cursorWordBackward (self, bool mark)
```

向后移动光标一个字。如果_mark_是真的，这个词也被选中。

](qrect.html)

[**See also**](qrect.html) [cursorWordForward](qlineedit.html#cursorWordForward)（ ） 。

```
QLineEdit.cursorWordForward (self, bool mark)
```

向前移动光标一个字。如果_mark_是真的，这个词也被选中。

**See also** [cursorWordBackward](qlineedit.html#cursorWordBackward)（ ） 。

```
QLineEdit.cut (self)
```

将所选文本复制到剪贴板，然后将其删除，如果有任何的，如果[echoMode](qlineedit.html#echoMode-prop)（）是[Normal](qlineedit.html#EchoMode-enum)。

如果当前的验证程序不允许删除选定的文本，切（ ）将复制而不删除。

**See also** [copy](qlineedit.html#copy)（ ）[paste](qlineedit.html#paste)（）和[setValidator](qlineedit.html#setValidator)（ ） 。

```
QLineEdit.del_ (self)
```

如果没有文本被选中，删除的字符文本光标的右侧。如果有任何文字被选中，将光标移动到所选文本的开头和选定的文本被删除。

**See also** [backspace](qlineedit.html#backspace)（ ） 。

```
QLineEdit.deselect (self)
```

取消选择任何选定的文本。

**See also** [setSelection](qlineedit.html#setSelection)（）和[selectAll](qlineedit.html#selectAll)（ ） 。

```
QString QLineEdit.displayText (self)
```

```
bool QLineEdit.dragEnabled (self)
```

```
QLineEdit.dragEnterEvent (self, QDragEnterEvent)
```

从重新实现[QWidget.dragEnterEvent](qwidget.html#dragEnterEvent)（ ） 。

```
QLineEdit.dragLeaveEvent (self, QDragLeaveEvent e)
```

从重新实现[QWidget.dragLeaveEvent](qwidget.html#dragLeaveEvent)（ ） 。

```
QLineEdit.dragMoveEvent (self, QDragMoveEvent e)
```

从重新实现[QWidget.dragMoveEvent](qwidget.html#dragMoveEvent)（ ） 。

```
QLineEdit.dropEvent (self, QDropEvent)
```

从重新实现[QWidget.dropEvent](qwidget.html#dropEvent)（ ） 。

```
EchoMode QLineEdit.echoMode (self)
```

[

```
QLineEdit.end (self, bool mark)
```

将文本光标移动到该行的末尾，除非它已经存在。如果_mark_诚然，选择文本朝着最后一个位置，否则，任何选定的文本都被取消，如果光标移动。

](qlineedit.html#EchoMode-enum)

[**See also**](qlineedit.html#EchoMode-enum) [home](qlineedit.html#home)（ ） 。

```
bool QLineEdit.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QLineEdit.focusInEvent (self, QFocusEvent)
```

从重新实现[QWidget.focusInEvent](qwidget.html#focusInEvent)（ ） 。

```
QLineEdit.focusOutEvent (self, QFocusEvent)
```

从重新实现[QWidget.focusOutEvent](qwidget.html#focusOutEvent)（ ） 。

```
(int left, int top, int right, int bottom) QLineEdit.getTextMargins (self)
```

返回小部件的文本边距_left_，_top_，_right_和_bottom_。

此功能被引入Qt的4.5 。

**See also** [setTextMargins](qlineedit.html#setTextMargins)（ ） 。

```
bool QLineEdit.hasAcceptableInput (self)
```

```
bool QLineEdit.hasFrame (self)
```

```
bool QLineEdit.hasSelectedText (self)
```

```
QLineEdit.home (self, bool mark)
```

将文本光标移动到行的开头，除非它已经存在。如果_mark_诚然，文本被选中向第一位置，否则，任何选定的文本都被取消，如果光标移动。

**See also** [end](qlineedit.html#end)（ ） 。

```
QLineEdit.initStyleOption (self, QStyleOptionFrame option)
```

初始化_option_与其它的值[QLineEdit](qlineedit.html)。当他们需要一个这种方法是有用的子类[QStyleOptionFrame](qstyleoptionframe.html) or [QStyleOptionFrameV2](qstyleoptionframev2.html)，但不希望在所有的信息填写自己。此功能将检查的版本[QStyleOptionFrame](qstyleoptionframe.html)并填写了附加价值[QStyleOptionFrameV2](qstyleoptionframev2.html)。

**See also** [QStyleOption.initFrom](qstyleoption.html#initFrom)（ ） 。

```
QString QLineEdit.inputMask (self)
```

```
QLineEdit.inputMethodEvent (self, QInputMethodEvent)
```

从重新实现[QWidget.inputMethodEvent](qwidget.html#inputMethodEvent)（ ） 。

```
QVariant QLineEdit.inputMethodQuery (self, Qt.InputMethodQuery)
```

从重新实现[QWidget.inputMethodQuery](qwidget.html#inputMethodQuery)（ ） 。

```
QLineEdit.insert (self, QString)
```

删除任何选定的文本，插入_newText_，并验证其结果。如果它是有效的，但将其设置为行编辑的新内容。

**See also** [setText](qlineedit.html#text-prop)（）和[clear](qlineedit.html#clear)（ ） 。

```
bool QLineEdit.isModified (self)
```

```
bool QLineEdit.isReadOnly (self)
```

```
bool QLineEdit.isRedoAvailable (self)
```

```
bool QLineEdit.isUndoAvailable (self)
```

```
QLineEdit.keyPressEvent (self, QKeyEvent)
```

从重新实现[QWidget.keyPressEvent](qwidget.html#keyPressEvent)（ ） 。

给定的按键转换_event_成一条线编辑操作。

如果Return或Enter键被按下和当前文本是有效的（或可[made valid](qvalidator.html#fixup)由验证器） ，所述信号[returnPressed](qlineedit.html#returnPressed)（）被发射。

默认的键绑定列在类的详细说明。

```
int QLineEdit.maxLength (self)
```

```
QSize QLineEdit.minimumSizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.minimumSizeHint](qwidget.html#minimumSizeHint-prop)（ ） 。

返回一个最小尺寸的行编辑。

返回的宽度是足够的至少一个字符。

```
QLineEdit.mouseDoubleClickEvent (self, QMouseEvent)
```

从重新实现[QWidget.mouseDoubleClickEvent](qwidget.html#mouseDoubleClickEvent)（ ） 。

```
QLineEdit.mouseMoveEvent (self, QMouseEvent)
```

从重新实现[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

```
QLineEdit.mousePressEvent (self, QMouseEvent)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

```
QLineEdit.mouseReleaseEvent (self, QMouseEvent)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

```
QLineEdit.paintEvent (self, QPaintEvent)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QLineEdit.paste (self)
```

在光标位置插入剪贴板中的文本，删除任何选定的文本，提供线路的编辑是不是[read-only](qlineedit.html#readOnly-prop)。

如果最终的结果是不能接受的电流[validator](qlineedit.html#setValidator)，没有任何反应。

**See also** [copy](qlineedit.html#copy)（）和[cut](qlineedit.html#cut)（ ） 。

```
QString QLineEdit.placeholderText (self)
```

```
QLineEdit.redo (self)
```

重做上次操作，如果是重做[available](qlineedit.html#redoAvailable-prop)。

```
QLineEdit.selectAll (self)
```

选择所有文本（即突出了它），将光标移动到最后。此时的默认值已经被插入，因为如果用户键入点击插件之前，所选的文本将被删除是有用的。

**See also** [setSelection](qlineedit.html#setSelection)（）和[deselect](qlineedit.html#deselect)（ ） 。

```
QString QLineEdit.selectedText (self)
```

```
int QLineEdit.selectionStart (self)
```

selectionStart （ ）返回行编辑所选的第一个字符或-1的索引，如果没有选定的文本。

**See also** [selectedText](qlineedit.html#selectedText-prop)（ ） 。

```
QLineEdit.setAlignment (self, Qt.Alignment flag)
```

```
QLineEdit.setCompleter (self, QCompleter completer)
```

设置此行编辑从完成者提供自动补全，_c_。完成模式设置使用[QCompleter.setCompletionMode](qcompleter.html#completionMode-prop)（ ） 。

要使用[QCompleter](qcompleter.html)与[QValidator](qvalidator.html) or [QLineEdit.inputMask](qlineedit.html#inputMask-prop)，你需要确保该模型提供[QCompleter](qcompleter.html)包含有效的条目。您可以使用[QSortFilterProxyModel](qsortfilterproxymodel.html)以确保该[QCompleter](qcompleter.html)的模型只包含有效的条目。

If _c_== 0 ， setCompleter （）删除当前的完成者，有效地禁用自动完成。

这个函数中引入了Qt 4.2中。

**See also** [completer](qlineedit.html#completer)（）和[QCompleter](qcompleter.html)。

```
QLineEdit.setCursorMoveStyle (self, Qt.CursorMoveStyle style)
```

```
QLineEdit.setCursorPosition (self, int)
```

```
QLineEdit.setDragEnabled (self, bool b)
```

```
QLineEdit.setEchoMode (self, EchoMode)
```

```
QLineEdit.setFrame (self, bool)
```

```
QLineEdit.setInputMask (self, QString inputMask)
```

```
QLineEdit.setMaxLength (self, int)
```

```
QLineEdit.setModified (self, bool)
```

```
QLineEdit.setPlaceholderText (self, QString)
```

```
QLineEdit.setReadOnly (self, bool)
```

```
QLineEdit.setSelection (self, int, int)
```

从位置选择文本_start_和_length_字符。消极的长度是允许的。

**See also** [deselect](qlineedit.html#deselect)（ ）[selectAll](qlineedit.html#selectAll)（）和[selectedText](qlineedit.html#selectedText-prop)（ ） 。

```
QLineEdit.setText (self, QString)
```

```
QLineEdit.setTextMargins (self, int left, int top, int right, int bottom)
```

围绕设置在框架内的文字边缘有大小_left_，_top_，_right_和_bottom_。

另请参阅[getTextMargins](qlineedit.html#getTextMargins)（ ） 。

此功能被引入Qt的4.5 。

**See also** [textMargins](qlineedit.html#textMargins)（ ） 。

```
QLineEdit.setTextMargins (self, QMargins margins)
```

设置_margins_周围的边框内的文字。

另请参阅[textMargins](qlineedit.html#textMargins)（ ） 。

此功能被引入Qt的4.6 。

```
QLineEdit.setValidator (self, QValidator)
```

设置此行编辑只接受输入验证器，_v_，会接受。这使您可以放置在可输入的文字任意的限制。

If _v_== 0 ， setValidator将（）删除当前输入验证器。初始设置是有没有输入验证器（即任何输入被接受最多[maxLength](qlineedit.html#maxLength-prop)（））。

**See also** [validator](qlineedit.html#validator)（ ）[QIntValidator](qintvalidator.html)，[QDoubleValidator](qdoublevalidator.html)和[QRegExpValidator](qregexpvalidator.html)。

```
QSize QLineEdit.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

返回推荐大小小部件。

宽度回来，以像素为单位，通常是足够的大约15到20个字符。

```
QString QLineEdit.text (self)
```

```
QMargins QLineEdit.textMargins (self)
```

[

返回小部件的文本利润。

此功能被引入Qt的4.6 。

](qmargins.html)

[**See also**](qmargins.html) [setTextMargins](qlineedit.html#setTextMargins)（ ） 。

```
QLineEdit.undo (self)
```

撤消上一个操作，如果是撤销[available](qlineedit.html#undoAvailable-prop)。取消选择当前的选择，并更新选择的开始到当前光标位置。

```
QValidator QLineEdit.validator (self)
```

[

返回一个指针，指向当前输入验证器，或者0 ，如果没有验证已定。

](qvalidator.html)

[**See also**](qvalidator.html) [setValidator](qlineedit.html#setValidator)（ ） 。

* * *

## Qt Signal Documentation

```
void cursorPositionChanged (int,int)
```

这是该信号的默认超载。

这个信号被发射时的光标移动。先前的位置由下式给出_old_，并通过新的位置_new_。

**See also** [setCursorPosition](qlineedit.html#cursorPosition-prop)（）和[cursorPosition](qlineedit.html#cursorPosition-prop)（ ） 。

```
void editingFinished ()
```

这是该信号的默认超载。

这个信号时，回车键被按下或发出的行编辑失去焦点。需要注意的是，如果有一个[validator](qlineedit.html#validator)（）或[inputMask](qlineedit.html#inputMask-prop)（）设定就行编辑和输入/返回键时， editingFinished （）​​信号将只被发射，如果输入如下的[inputMask](qlineedit.html#inputMask-prop)（ ）和[validator](qlineedit.html#validator)（）返回[QValidator.Acceptable](qvalidator.html#State-enum)。

```
void returnPressed ()
```

这是该信号的默认超载。

当回车键被按下时，这个信号被发射。需要注意的是，如果有一个[validator](qlineedit.html#validator)（）或[inputMask](qlineedit.html#inputMask-prop)（ ）设置就行了编辑，该returnPressed （ ）信号将只如果输入如下发出的[inputMask](qlineedit.html#inputMask-prop)（ ）和[validator](qlineedit.html#validator)（）返回[QValidator.Acceptable](qvalidator.html#State-enum)。

```
void selectionChanged ()
```

这是该信号的默认超载。

这个信号被发射时的选择改变。

**See also** [hasSelectedText](qlineedit.html#hasSelectedText-prop)（）和[selectedText](qlineedit.html#selectedText-prop)（ ） 。

```
void textChanged (const QString&)
```

这是该信号的默认超载。

这个信号被发射时的文本改变。该_text_参数是新的文本。

不像[textEdited](qlineedit.html#textEdited)（ ） ，这个信号也时发出的文本编程方式改变，例如，通过调用[setText](qlineedit.html#text-prop)（ ） 。

```
void textEdited (const QString&)
```

这是该信号的默认超载。

这个信号被发射时的文本编辑。该_text_参数是新的文本。

不像[textChanged](qlineedit.html#textChanged)（ ） ，这个信号没有发出时，文本编程方式改变，例如，通过调用[setText](qlineedit.html#text-prop)（ ） 。