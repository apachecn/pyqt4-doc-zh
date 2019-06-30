# QClipboard Class Reference

## [[QtGui](index.htm) module]

该QClipboard类提供窗口系统剪贴板。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum Mode { Clipboard, Selection, FindBuffer }`

### Methods

*   `clear (self, Mode mode = QClipboard.Clipboard)`
*   `connectNotify (self, SIGNAL())`
*   `bool event (self, QEvent)`
*   `QImage image (self, Mode mode = QClipboard.Clipboard)`
*   `QMimeData mimeData (self, Mode mode = QClipboard.Clipboard)`
*   `bool ownsClipboard (self)`
*   `bool ownsFindBuffer (self)`
*   `bool ownsSelection (self)`
*   `QPixmap pixmap (self, Mode mode = QClipboard.Clipboard)`
*   `setImage (self, QImage, Mode mode = QClipboard.Clipboard)`
*   `setMimeData (self, QMimeData data, Mode mode = QClipboard.Clipboard)`
*   `setPixmap (self, QPixmap, Mode mode = QClipboard.Clipboard)`
*   `setText (self, QString, Mode mode = QClipboard.Clipboard)`
*   `bool supportsFindBuffer (self)`
*   `bool supportsSelection (self)`
*   `QString text (self, Mode mode = QClipboard.Clipboard)`
*   `(QString, QString) text (self, QString subtype, Mode mode = QClipboard.Clipboard)`
*   `QString text (self, QString subtype, Mode mode = QClipboard.Clipboard)`

### Qt Signals

*   `void changed (QClipboard::Mode)`
*   `void dataChanged ()`
*   `void findBufferChanged ()`
*   `void selectionChanged ()`

* * *

## Detailed Description

该QClipboard类提供窗口系统剪贴板。

剪贴板提供复制和粘贴应用程序之间的数据的简单机制。

QClipboard支持相同的数据类型[QDrag](qdrag.html)确实，并采用类似的机制。对于高级剪贴板的使用读[Drag and Drop](index.htm)。

有一个在应用程序中的单个QClipboard对象​​，作为访问[QApplication.clipboard](qapplication.html#clipboard)（ ） 。

例如：

```
 QClipboard *clipboard = [QApplication](qapplication.html).clipboard();
 [QString](qstring.html) originalText = clipboard->text();
 ...
 clipboard->setText(newText);

```

QClipboard具有一些方便的功能来访问常用数据类型：[setText](qclipboard.html#setText)（ ）允许Unicode文本的交换和[setPixmap](qclipboard.html#setPixmap)（）和[setImage](qclipboard.html#setImage)（ ）允许应用程序之间QPixmaps和QImages的交流。该[setMimeData](qclipboard.html#setMimeData)（ ）函数是极大的灵活性：它可以让你添加任何[QMimeData](qmimedata.html)复制到剪贴板中。有相应的getter为每个这些，例如[text](qclipboard.html#text)（ ）[image](qclipboard.html#image)（）和[pixmap](qclipboard.html#pixmap)（ ） 。你可以通过调用清除剪贴板[clear](qclipboard.html#clear)（ ） 。

使用这些功能的一个典型例子如下：

```
 void DropArea.paste()
 {
     const QClipboard *clipboard = [QApplication](qapplication.html).clipboard();
     const [QMimeData](qmimedata.html) *mimeData = clipboard->mimeData();

     if (mimeData->hasImage()) {
         setPixmap(qvariant_cast<[QPixmap](qpixmap.html)>(mimeData->imageData()));
     } else if (mimeData->hasHtml()) {
         setText(mimeData->html());
         setTextFormat([Qt](qt.html).RichText);
     } else if (mimeData->hasText()) {
         setText(mimeData->text());
         setTextFormat([Qt](qt.html).PlainText);
     } else {
         setText(tr("Cannot display data"));
     }

```

### Notes for X11 Users

*   The X11 Window System has the concept of a separate selection and clipboard. When text is selected, it is immediately available as the global mouse selection. The global mouse selection may later be copied to the clipboard. By convention, the middle mouse button is used to paste the global mouse selection.
*   X11 also has the concept of ownership; if you change the selection within a window, X11 will only notify the owner and the previous owner of the change, i.e. it will not notify all applications that the selection or clipboard data changed.
*   Lastly, the X11 clipboard is event driven, i.e. the clipboard will not function properly if the event loop is not running. Similarly, it is recommended that the contents of the clipboard are stored or retrieved in direct response to user-input events, e.g. mouse button or key presses and releases. You should not store or retrieve the clipboard contents in response to timer or non-user-input events.
*   Since there is no standard way to copy and paste files between applications on X11, various MIME types and conventions are currently in use. For instance, Nautilus expects files to be supplied with a `x-special/gnome-copied-files` MIME type with data beginning with the cut/copy action, a newline character, and the URL of the file.

### Notes for Mac OS X Users

Mac OS X支持保存在查找操作的当前搜索字符串单独发现的缓冲区。这一发现剪贴板可以通过指定访问的[FindBuffer](qclipboard.html#Mode-enum)模式。

### Notes for Windows and Mac OS X Users

*   Windows and Mac OS X do not support the global mouse selection; they only supports the global clipboard, i.e. they only add text to the clipboard when an explicit copy or cut is made.
*   Windows and Mac OS X does not have the concept of ownership; the clipboard is a fully global resource so all applications are notified of changes.

* * *

## Type Documentation

```
QClipboard.Mode
```

该枚举类型是用来控制系统剪贴板中的一部分是由[QClipboard.mimeData](qclipboard.html#mimeData)（ ）[QClipboard.setMimeData](qclipboard.html#setMimeData)（ ）和相关函数。

| Constant | Value | Description |
| --- | --- | --- |
| `QClipboard.Clipboard` | `0` | 表示数据应该存储和从全局剪贴板中检索。 |
| `QClipboard.Selection` | `1` | 表示数据应该存储和从全局鼠标选择检索。支持`Selection`是只设置一个全局鼠标选择（例如X11 ）系统。 |
| `QClipboard.FindBuffer` | `2` | 表示数据应该存储和查找缓冲区中检索。此模式用于保持搜索字符串在Mac OS X。 |

**See also** [QClipboard.supportsSelection](qclipboard.html#supportsSelection)（ ） 。

* * *

## Method Documentation

```
QClipboard.clear (self, Mode mode = QClipboard.Clipboard)
```

清除剪贴板内容。

该_mode_参数用来控制哪些系统剪贴板的一部分使用。如果_mode_ is [QClipboard.Clipboard](qclipboard.html#Mode-enum)，此功能清除全局剪贴板中的内容。如果_mode_ is [QClipboard.Selection](qclipboard.html#Mode-enum)这个函数清除全局鼠标选择内容。如果_mode_ is [QClipboard.FindBuffer](qclipboard.html#Mode-enum)这个函数清除搜索字符串缓冲区。

**See also** [QClipboard.Mode](qclipboard.html#Mode-enum)和[supportsSelection](qclipboard.html#supportsSelection)（ ） 。

```
QClipboard.connectNotify (self, SIGNAL())
```

```
bool QClipboard.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QImage QClipboard.image (self, Mode mode = QClipboard.Clipboard)
```

[

返回剪贴板中的图像，或者返回一个空图像，如果剪贴板中不包含的图像，或者如果它包含一个图像中不支持的图像格式。

](qimage.html)

[该_mode_参数用来控制哪些系统剪贴板的一部分使用。如果_mode_ is](qimage.html) [QClipboard.Clipboard](qclipboard.html#Mode-enum)时，图像从全局剪贴板检索。如果_mode_ is [QClipboard.Selection](qclipboard.html#Mode-enum)时，图像从全局鼠标选择检索。

**See also** [setImage](qclipboard.html#setImage)（ ）[pixmap](qclipboard.html#pixmap)（ ）[mimeData](qclipboard.html#mimeData)（）和[QImage.isNull](qimage.html#isNull)（ ） 。

```
QMimeData QClipboard.mimeData (self, Mode mode = QClipboard.Clipboard)
```

[](qmimedata.html)

[返回一个引用](qmimedata.html)[QMimeData](qmimedata.html)当前剪贴板中的数据的代表性。

该_mode_参数用来控制哪些系统剪贴板的一部分使用。如果_mode_ is [QClipboard.Clipboard](qclipboard.html#Mode-enum)时，数据被从全局剪贴板检索。如果_mode_ is [QClipboard.Selection](qclipboard.html#Mode-enum)时，数据被从全局鼠标选择检索。如果_mode_ is [QClipboard.FindBuffer](qclipboard.html#Mode-enum)时，数据被从该搜索字符串缓冲区中检索。

该[text](qclipboard.html#text)（ ）[image](qclipboard.html#image)（）和[pixmap](qclipboard.html#pixmap)（ ）函数用于检索的文本，图像和像素映射数据简单包装。

**See also** [setMimeData](qclipboard.html#setMimeData)（ ） 。

```
bool QClipboard.ownsClipboard (self)
```

返回True如果剪贴板对象拥有的剪贴板数据，否则返回False 。

```
bool QClipboard.ownsFindBuffer (self)
```

返回True如果剪贴板对象拥有的查找缓冲区中的数据，否则返回False 。

这个函数中引入了Qt 4.2中。

```
bool QClipboard.ownsSelection (self)
```

返回True如果剪贴板对象拥有鼠标选择数据，否则返回False 。

```
QPixmap QClipboard.pixmap (self, Mode mode = QClipboard.Clipboard)
```

[

返回剪贴板像素映射，或者null，如果剪贴板中不包含像素图。请注意，这可能会丢失信息。例如，如果图像是24位和显示器是8位，则结果被转换为8位，并且如果图像具有alpha通道，结果正好有一个掩膜。

](qpixmap.html)

[该_mode_参数用来控制哪些系统剪贴板的一部分使用。如果_mode_ is](qpixmap.html) [QClipboard.Clipboard](qclipboard.html#Mode-enum)，像素图是从全局剪贴板中检索。如果_mode_ is [QClipboard.Selection](qclipboard.html#Mode-enum)，像素图是从全局鼠标选择检索。

**See also** [setPixmap](qclipboard.html#setPixmap)（ ）[image](qclipboard.html#image)（ ）[mimeData](qclipboard.html#mimeData)（）和[QPixmap.convertFromImage](qpixmap.html#convertFromImage)（ ） 。

```
QClipboard.setImage (self, QImage, Mode mode = QClipboard.Clipboard)
```

副本_image_复制到剪贴板中。

该_mode_参数用来控制哪些系统剪贴板的一部分使用。如果_mode_ is [QClipboard.Clipboard](qclipboard.html#Mode-enum)中，图像被存储在全局剪贴板。如果_mode_ is [QClipboard.Selection](qclipboard.html#Mode-enum)时，数据被存储在全局鼠标选择。

这是简写：

```
 [QMimeData](qmimedata.html) *data = new [QMimeData](qmimedata.html);
 data->setImageData(image);
 clipboard->setMimeData(data, mode);

```

**See also** [image](qclipboard.html#image)（ ）[setPixmap](qclipboard.html#setPixmap)（）和[setMimeData](qclipboard.html#setMimeData)（ ） 。

```
QClipboard.setMimeData (self, QMimeData data, Mode mode = QClipboard.Clipboard)
```

剪贴板数据集_src_。该数据的所有权转移到剪贴板。如果你想删除数据或者调用[clear](qclipboard.html#clear)（ ）或致电setMimeData （ ）再次与新的数据。

该_mode_参数用来控制哪些系统剪贴板的一部分使用。如果_mode_ is [QClipboard.Clipboard](qclipboard.html#Mode-enum)时，数据被存储在全局剪贴板。如果_mode_ is [QClipboard.Selection](qclipboard.html#Mode-enum)时，数据被存储在全局鼠标选择。如果_mode_ is [QClipboard.FindBuffer](qclipboard.html#Mode-enum)时，数据被存储在搜索字符串缓冲区。

该[setText](qclipboard.html#setText)（ ）[setImage](qclipboard.html#setImage)（）和[setPixmap](qclipboard.html#setPixmap)（ ）函数分别用于设置文本，图像和像素映射数据简单的包装。

**See also** [mimeData](qclipboard.html#mimeData)（ ） 。

```
QClipboard.setPixmap (self, QPixmap, Mode mode = QClipboard.Clipboard)
```

Copies _pixmap_复制到剪贴板中。注意，这是慢[setImage](qclipboard.html#setImage)（） ，因为它需要转换的[QPixmap](qpixmap.html)到[QImage](qimage.html)第一。

该_mode_参数用来控制哪些系统剪贴板的一部分使用。如果_mode_ is [QClipboard.Clipboard](qclipboard.html#Mode-enum)，像素图被存储在全局剪贴板。如果_mode_ is [QClipboard.Selection](qclipboard.html#Mode-enum)，像素图被存储在全局鼠标选择。

**See also** [pixmap](qclipboard.html#pixmap)（ ）[setImage](qclipboard.html#setImage)（）和[setMimeData](qclipboard.html#setMimeData)（ ） 。

```
QClipboard.setText (self, QString, Mode mode = QClipboard.Clipboard)
```

Copies _text_到剪贴板为纯文本。

该_mode_参数用来控制哪些系统剪贴板的一部分使用。如果_mode_ is [QClipboard.Clipboard](qclipboard.html#Mode-enum)，文本被存储在全局剪贴板。如果_mode_ is [QClipboard.Selection](qclipboard.html#Mode-enum)，文本存储在全局鼠标选择。如果_mode_ is [QClipboard.FindBuffer](qclipboard.html#Mode-enum)，文本存储在搜索字符串缓冲区。

**See also** [text](qclipboard.html#text)（）和[setMimeData](qclipboard.html#setMimeData)（ ） 。

```
bool QClipboard.supportsFindBuffer (self)
```

返回True如果剪贴板支持一个单独的搜索缓存，否则返回False 。

```
bool QClipboard.supportsSelection (self)
```

返回True如果剪贴板支持鼠标选择，否则返回False 。

```
QString QClipboard.text (self, Mode mode = QClipboard.Clipboard)
```

返回剪贴板中的文本为纯文本，或者一个空字符串，如果剪贴板中不包含任何文本。

该_mode_参数用来控制哪些系统剪贴板的一部分使用。如果_mode_ is [QClipboard.Clipboard](qclipboard.html#Mode-enum)，文本从全局剪贴板中检索。如果_mode_ is [QClipboard.Selection](qclipboard.html#Mode-enum)，该文本从全局鼠标选择检索。如果_mode_ is [QClipboard.FindBuffer](qclipboard.html#Mode-enum)，该文本从搜索字符串缓冲区中检索。

**See also** [setText](qclipboard.html#setText)（）和[mimeData](qclipboard.html#mimeData)（ ） 。

```
(QString, QString) QClipboard.text (self, QString subtype, Mode mode = QClipboard.Clipboard)
```

这是一个重载函数。

返回亚型剪贴板文本_subtype_，或一个空字符串，如果剪贴板中不包含任何文本。如果_subtype_为null ，任何亚型是可以接受的，并且_subtype_被设置为所选择的子类型。

该_mode_参数用来控制哪些系统剪贴板的一部分使用。如果_mode_ is [QClipboard.Clipboard](qclipboard.html#Mode-enum)，文本从全局剪贴板中检索。如果_mode_ is [QClipboard.Selection](qclipboard.html#Mode-enum)，该文本从全局鼠标选择检索。

为共同的价值观_subtype_是“普通”和“HTML” 。

请注意，多次调用该函数，例如从一个关键的事件处理程序，可能会很慢。在这种情况下，你应该使用`dataChanged()`信号代替。

**See also** [setText](qclipboard.html#setText)（）和[mimeData](qclipboard.html#mimeData)（ ） 。

```
QString QClipboard.text (self, QString subtype, Mode mode = QClipboard.Clipboard)
```

* * *

## Qt Signal Documentation

```
void changed (QClipboard::Mode)
```

这是该信号的默认超载。

这个信号被发射时，对于给定的剪贴板中的数据_mode_被改变。

这个函数中引入了Qt 4.2中。

**See also** [dataChanged](qclipboard.html#dataChanged)（ ）[selectionChanged](qclipboard.html#selectionChanged)（）和[findBufferChanged](qclipboard.html#findBufferChanged)（ ） 。

```
void dataChanged ()
```

这是该信号的默认超载。

当剪贴板中的数据改变这个信号被发射。

在Mac OS X和与Qt版本4.3或更高版本，由其他应用程序所做的剪贴板的变化将只检测时，应用程序被激活。

**See also** [findBufferChanged](qclipboard.html#findBufferChanged)（ ）[selectionChanged](qclipboard.html#selectionChanged)（）和[changed](qclipboard.html#changed)（ ） 。

```
void findBufferChanged ()
```

这是该信号的默认超载。

当发现缓冲区改变这个信号被发射。这仅适用于Mac OS X。

与Qt版本4.3或更高版本，由其他应用程序所做的剪贴板的变化将只检测时，应用程序被激活。

这个函数中引入了Qt 4.2中。

**See also** [dataChanged](qclipboard.html#dataChanged)（ ）[selectionChanged](qclipboard.html#selectionChanged)（）和[changed](qclipboard.html#changed)（ ） 。

```
void selectionChanged ()
```

这是该信号的默认超载。

当选择改变这个信号被发射。这仅适用于支持选项窗口系统，例如X11 。 Windows和Mac OS X不支持选择。

**See also** [dataChanged](qclipboard.html#dataChanged)（ ）[findBufferChanged](qclipboard.html#findBufferChanged)（）和[changed](qclipboard.html#changed)（ ） 。