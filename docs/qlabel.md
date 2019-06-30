# QLabel Class Reference

## [[QtGui](index.htm) module]

该QLABEL小部件提供了一个文本或图像的显示。[More...](#details)

继承[QFrame](qframe.html)。

### Methods

*   `__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)`
*   `__init__ (self, QString text, QWidget parent = None, Qt.WindowFlags flags = 0)`
*   `Qt.Alignment alignment (self)`
*   `QWidget buddy (self)`
*   `changeEvent (self, QEvent)`
*   `clear (self)`
*   `contextMenuEvent (self, QContextMenuEvent ev)`
*   `bool event (self, QEvent e)`
*   `focusInEvent (self, QFocusEvent ev)`
*   `bool focusNextPrevChild (self, bool next)`
*   `focusOutEvent (self, QFocusEvent ev)`
*   `bool hasScaledContents (self)`
*   `bool hasSelectedText (self)`
*   `int heightForWidth (self, int)`
*   `int indent (self)`
*   `keyPressEvent (self, QKeyEvent ev)`
*   `int margin (self)`
*   `QSize minimumSizeHint (self)`
*   `mouseMoveEvent (self, QMouseEvent ev)`
*   `mousePressEvent (self, QMouseEvent ev)`
*   `mouseReleaseEvent (self, QMouseEvent ev)`
*   `QMovie movie (self)`
*   `bool openExternalLinks (self)`
*   `paintEvent (self, QPaintEvent)`
*   `QPicture picture (self)`
*   `QPixmap pixmap (self)`
*   `QString selectedText (self)`
*   `int selectionStart (self)`
*   `setAlignment (self, Qt.Alignment)`
*   `setBuddy (self, QWidget)`
*   `setIndent (self, int)`
*   `setMargin (self, int)`
*   `setMovie (self, QMovie movie)`
*   `setNum (self, float)`
*   `setNum (self, int)`
*   `setOpenExternalLinks (self, bool open)`
*   `setPicture (self, QPicture)`
*   `setPixmap (self, QPixmap)`
*   `setScaledContents (self, bool)`
*   `setSelection (self, int, int)`
*   `setText (self, QString)`
*   `setTextFormat (self, Qt.TextFormat)`
*   `setTextInteractionFlags (self, Qt.TextInteractionFlags flags)`
*   `setWordWrap (self, bool on)`
*   `QSize sizeHint (self)`
*   `QString text (self)`
*   `Qt.TextFormat textFormat (self)`
*   `Qt.TextInteractionFlags textInteractionFlags (self)`
*   `bool wordWrap (self)`

### Qt Signals

*   `void linkActivated (const QString&)`
*   `void linkHovered (const QString&)`

* * *

## Detailed Description

该QLABEL小部件提供了一个文本或图像的显示。

QLABEL用于显示文本或图像。没有提供用户交互功能。标籤的视觉外观可以以各种方式来配置，并且它可以用于指定一个焦点助记键另一小窗口。

一个QLABEL可以包含以下任一内容类型：

| Content | Setting |
| --- | --- |
| Plain text | Pass a [QString](qstring.html) to [setText](qlabel.html#text-prop)(). |
| Rich text | Pass a [QString](qstring.html) that contains rich text to [setText](qlabel.html#text-prop)(). |
| A pixmap | Pass a [QPixmap](qpixmap.html) to [setPixmap](qlabel.html#pixmap-prop)(). |
| A movie | Pass a [QMovie](qmovie.html) to [setMovie](qlabel.html#setMovie)(). |
| A number | Pass an _int_ or a _double_ to [setNum](qlabel.html#setNum)(), which converts the number to plain text. |
| Nothing | The same as an empty plain text. This is the default. Set by [clear](qlabel.html#clear)(). |

**Warning:**当传递[QString](qstring.html)在构造函数或调用[setText](qlabel.html#text-prop)（ ） ，一定要净化你的输入， QLABEL试图猜测它是否显示文本为纯文本或富文本。你可能需要调用[setTextFormat](qlabel.html#textFormat-prop)（ ）明确，例如如果你期望的文本是在平原的格式，但（显示从Web加载数据时，例如）无法控制文本源。

当内容被任意使用这些功能的改变，以前的任何内容被清除。

默认情况下，标籤显示[left-aligned, vertically-centered](qlabel.html#alignment-prop)文本和图像，其中要显示在文本的任何选项卡[automatically expanded](qt.html#TextFlag-enum)。然而， QLABEL的外观可以调节和微调在几个方面。

在QLABEL插件区域内的内容的定位可以与调谐[setAlignment](qlabel.html#alignment-prop)（）和[setIndent](qlabel.html#indent-prop)（ ） 。文本内容也可以沿包裹单词边界线[setWordWrap](qlabel.html#wordWrap-prop)（ ） 。例如，此代码设置一个下沉式面板的右下角（这两条线是用右侧的标籤冲洗）两行文字：

```
 QLabel *label = new QLabel(this);
 label->setFrameStyle([QFrame](qframe.html).Panel | [QFrame](qframe.html).Sunken);
 label->setText("first line\nsecond line");
 label->setAlignment([Qt](qt.html).AlignBottom | [Qt](qt.html).AlignRight);

```

的性质和功能QLABEL从继承[QFrame](qframe.html)也可用于指定要用于任何给定的标籤的小窗口框。

甲QLABEL常被用作用于交互式窗口小部件的标籤。对于这种使用QLABEL提供用于添加助记符一个有用的机制（见[QKeySequence](qkeysequence.html)） ，将设置键盘焦点到其它部件（称为QLABEL的“夥伴” ） 。例如：

```
 [QLineEdit](qlineedit.html)* phoneEdit = new [QLineEdit](qlineedit.html)(this);
 QLabel* phoneLabel = new QLabel("&Phone:", this);
 phoneLabel->setBuddy(phoneEdit);

```

在该示例中，键盘焦点转移到标籤的夥伴（在[QLineEdit](qlineedit.html)）当用户按下ALT + P。如果好友是一个按钮（继承[QAbstractButton](qabstractbutton.html)） ，触发记忆会模拟一个按钮的点击。

| ![Screenshot of a Macintosh style label](../img/macintosh-label.png) | A label shown in the [Macintosh widget style](index.htm). |
| ![Screenshot of a Plastique style label](../img/plastique-label.png) | A label shown in the [Plastique widget style](index.htm). |
| ![Screenshot of a Windows XP style label](../img/windowsxp-label.png) | A label shown in the [Windows XP widget style](index.htm). |

* * *

## Method Documentation

```
QLabel.__init__ (self, QWidget parent = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个空标籤。

该_parent_和widget标志_f_，参数被传递到[QFrame](qframe.html)构造函数。

**See also** [setAlignment](qlabel.html#alignment-prop)（ ）[setFrameStyle](qframe.html#setFrameStyle)（）和[setIndent](qlabel.html#indent-prop)（ ） 。

```
QLabel.__init__ (self, QString text, QWidget parent = None, Qt.WindowFlags flags = 0)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个显示文本标籤，_text_。

该_parent_和widget标志_f_，参数被传递到[QFrame](qframe.html)构造函数。

**See also** [setText](qlabel.html#text-prop)（ ）[setAlignment](qlabel.html#alignment-prop)（ ）[setFrameStyle](qframe.html#setFrameStyle)（）和[setIndent](qlabel.html#indent-prop)（ ） 。

```
Qt.Alignment QLabel.alignment (self)
```

[](index.htm)

```
QWidget QLabel.buddy (self)
```

[

返回此标籤的哥们，或者0 ，如果没有好友当前设置。

](qwidget.html)

[**See also**](qwidget.html) [setBuddy](qlabel.html#setBuddy)（ ） 。

```
QLabel.changeEvent (self, QEvent)
```

从重新实现[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
QLabel.clear (self)
```

这种方法也是一个Qt槽与C + +的签名`void clear()`。

清除任何标籤的内容。

```
QLabel.contextMenuEvent (self, QContextMenuEvent ev)
```

从重新实现[QWidget.contextMenuEvent](qwidget.html#contextMenuEvent)（ ） 。

```
bool QLabel.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QLabel.focusInEvent (self, QFocusEvent ev)
```

从重新实现[QWidget.focusInEvent](qwidget.html#focusInEvent)（ ） 。

```
bool QLabel.focusNextPrevChild (self, bool next)
```

从重新实现[QWidget.focusNextPrevChild](qwidget.html#focusNextPrevChild)（ ） 。

```
QLabel.focusOutEvent (self, QFocusEvent ev)
```

从重新实现[QWidget.focusOutEvent](qwidget.html#focusOutEvent)（ ） 。

```
bool QLabel.hasScaledContents (self)
```

```
bool QLabel.hasSelectedText (self)
```

```
int QLabel.heightForWidth (self, int)
```

从重新实现[QWidget.heightForWidth](qwidget.html#heightForWidth)（ ） 。

```
int QLabel.indent (self)
```

```
QLabel.keyPressEvent (self, QKeyEvent ev)
```

从重新实现[QWidget.keyPressEvent](qwidget.html#keyPressEvent)（ ） 。

```
int QLabel.margin (self)
```

```
QSize QLabel.minimumSizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.minimumSizeHint](qwidget.html#minimumSizeHint-prop)（ ） 。

```
QLabel.mouseMoveEvent (self, QMouseEvent ev)
```

从重新实现[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

```
QLabel.mousePressEvent (self, QMouseEvent ev)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

```
QLabel.mouseReleaseEvent (self, QMouseEvent ev)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

```
QMovie QLabel.movie (self)
```

[

返回一个指向标籤的电影，或者0，如果没有电影已定。

](qmovie.html)

[**See also**](qmovie.html) [setMovie](qlabel.html#setMovie)（ ） 。

```
bool QLabel.openExternalLinks (self)
```

```
QLabel.paintEvent (self, QPaintEvent)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QPicture QLabel.picture (self)
```

[

返回该标籤的头像或0，如果标籤没有图片。

](qpicture.html)

[**See also**](qpicture.html) [setPicture](qlabel.html#setPicture)（ ） 。

```
QPixmap QLabel.pixmap (self)
```

[

```
QString QLabel.selectedText (self)
```

```
int QLabel.selectionStart (self)
```

selectionStart （）返回在标籤中第一个选定字符或-1的索引，如果没有选定的文本。

](qpixmap.html)

[**Note:**该](qpixmap.html)[textInteractionFlags](qlabel.html#textInteractionFlags-prop)标籤上的设置需要包含两种TextSelectableByMouse或TextSelectableByKeyboard 。

此功能被引入Qt的4.7 。

**See also** [selectedText](qlabel.html#selectedText-prop)（ ） 。

```
QLabel.setAlignment (self, Qt.Alignment)
```

```
QLabel.setBuddy (self, QWidget)
```

设置这个标籤的哥们_buddy_。

当用户按下这个标籤所指示的快捷键，键盘焦点转移到标籤的哥们部件。

哥们机制仅适用于包含在其中一个字符的前缀与符号文字QLabels ， '＆' 。此字符设置为快捷键。请参阅[QKeySequence.mnemonic](qkeysequence.html#mnemonic)（ ）文档的详细信息（显示的实际符号，使用“\u0026\u0026” ） 。

在对话框中，可以创建两个数据输入部件，并为每个标籤，并设置了几何布局，每个标籤就是它的数据输入控件（它的“夥伴” ） ，例如左：

```
 [QLineEdit](qlineedit.html) *nameEd  = new [QLineEdit](qlineedit.html)(this);
 [QLabel](qlabel.html)    *nameLb  = new [QLabel](qlabel.html)("&Name:", this);
 nameLb->setBuddy(nameEd);
 [QLineEdit](qlineedit.html) *phoneEd = new [QLineEdit](qlineedit.html)(this);
 [QLabel](qlabel.html)    *phoneLb = new [QLabel](qlabel.html)("&Phone:", this);
 phoneLb->setBuddy(phoneEd);
 // (layout setup not shown)

```

与上面的代码中，重点跳转到Name字段，当用户按下ALT + N，和电话字段，当用户按下ALT + P。

来取消以前设置的哥们，调用该函数_buddy_设置为0。

**See also** [buddy](qlabel.html#buddy)（ ）[setText](qlabel.html#text-prop)（ ）[QShortcut](qshortcut.html)和[setAlignment](qlabel.html#alignment-prop)（ ） 。

```
QLabel.setIndent (self, int)
```

```
QLabel.setMargin (self, int)
```

```
QLabel.setMovie (self, QMovie movie)
```

这种方法也是一个Qt槽与C + +的签名`void setMovie(QMovie *)`。

设置标籤内容_movie_。任何以前的内容将被清除。标籤不走电影的所有权。

的哥们快捷方式，如果有的话，将被禁用。

**See also** [movie](qlabel.html#movie)（）和[setBuddy](qlabel.html#setBuddy)（ ） 。

```
QLabel.setNum (self, float)
```

这种方法也是一个Qt槽与C + +的签名`void setNum(double)`。

设置标籤内容包含整数的文本表示纯文本_num_。任何以前的内容将被清除。什么都不做，如果整数的字符串表示形式是相同的标籤的当前内容。

的哥们快捷方式，如果有的话，将被禁用。

**See also** [setText](qlabel.html#text-prop)（ ）[QString.setNum](qstring.html#setNum)（）和[setBuddy](qlabel.html#setBuddy)（ ） 。

```
QLabel.setNum (self, int)
```

这种方法也是一个Qt槽与C + +的签名`void setNum(int)`。

这是一个重载函数。

设置标籤内容包含双重的文字表述纯文本_num_。任何以前的内容将被清除。请问咱这双的字符串表示形式是相同的标籤的当前内容。

的哥们快捷方式，如果有的话，将被禁用。

**See also** [setText](qlabel.html#text-prop)（ ）[QString.setNum](qstring.html#setNum)（）和[setBuddy](qlabel.html#setBuddy)（ ） 。

```
QLabel.setOpenExternalLinks (self, bool open)
```

```
QLabel.setPicture (self, QPicture)
```

这种方法也是一个Qt槽与C + +的签名`void setPicture(const QPicture&)`。

设置标籤内容_picture_。任何以前的内容将被清除。

的哥们快捷方式，如果有的话，将被禁用。

**See also** [picture](qlabel.html#picture)（）和[setBuddy](qlabel.html#setBuddy)（ ） 。

```
QLabel.setPixmap (self, QPixmap)
```

这种方法也是一个Qt槽与C + +的签名`void setPixmap(const QPixmap&)`。

```
QLabel.setScaledContents (self, bool)
```

```
QLabel.setSelection (self, int, int)
```

从位置选择文本_start_和_length_字符。

**Note:**该[textInteractionFlags](qlabel.html#textInteractionFlags-prop)标籤上的设置需要包含两种TextSelectableByMouse或TextSelectableByKeyboard 。

此功能被引入Qt的4.7 。

**See also** [selectedText](qlabel.html#selectedText-prop)（ ） 。

```
QLabel.setText (self, QString)
```

这种方法也是一个Qt槽与C + +的签名`void setText(const QString&)`。

```
QLabel.setTextFormat (self, Qt.TextFormat)
```

```
QLabel.setTextInteractionFlags (self, Qt.TextInteractionFlags flags)
```

```
QLabel.setWordWrap (self, bool on)
```

```
QSize QLabel.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

```
QString QLabel.text (self)
```

```
Qt.TextFormat QLabel.textFormat (self)
```

[](qt.html#TextFormat-enum)

```
Qt.TextInteractionFlags QLabel.textInteractionFlags (self)
```

[

```
bool QLabel.wordWrap (self)
```

* * *

## Qt Signal Documentation

```
void linkActivated (const QString&)
```

这是该信号的默认超载。

当用户点击一个链接这个信号被发射。由锚所指的URL传递中_link_。

这个函数中引入了Qt 4.2中。

](index.htm)

[**See also**](index.htm) [linkHovered](qlabel.html#linkHovered)（ ） 。

```
void linkHovered (const QString&)
```

这是该信号的默认超载。

当用户将鼠标悬停在一个链接这个信号被发射。由锚所指的URL传递中_link_。

这个函数中引入了Qt 4.2中。

**See also** [linkActivated](qlabel.html#linkActivated)（ ） 。