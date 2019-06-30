# QTextBrowser Class Reference

## [[QtGui](index.htm) module]

中，QTextBrowser类提供了超文本浏览丰富的文本浏览器。[More...](#details)

继承[QTextEdit](qtextedit.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `backward (self)`
*   `int backwardHistoryCount (self)`
*   `clearHistory (self)`
*   `bool event (self, QEvent e)`
*   `bool focusNextPrevChild (self, bool next)`
*   `focusOutEvent (self, QFocusEvent ev)`
*   `forward (self)`
*   `int forwardHistoryCount (self)`
*   `QString historyTitle (self, int)`
*   `QUrl historyUrl (self, int)`
*   `home (self)`
*   `bool isBackwardAvailable (self)`
*   `bool isForwardAvailable (self)`
*   `keyPressEvent (self, QKeyEvent ev)`
*   `QVariant loadResource (self, int type, QUrl name)`
*   `mouseMoveEvent (self, QMouseEvent ev)`
*   `mousePressEvent (self, QMouseEvent ev)`
*   `mouseReleaseEvent (self, QMouseEvent ev)`
*   `bool openExternalLinks (self)`
*   `bool openLinks (self)`
*   `paintEvent (self, QPaintEvent e)`
*   `reload (self)`
*   `QStringList searchPaths (self)`
*   `setOpenExternalLinks (self, bool open)`
*   `setOpenLinks (self, bool open)`
*   `setSearchPaths (self, QStringList paths)`
*   `setSource (self, QUrl name)`
*   `QUrl source (self)`

### Qt Signals

*   `void anchorClicked (const QUrl&)`
*   `void backwardAvailable (bool)`
*   `void forwardAvailable (bool)`
*   `void highlighted (const QUrl&)`
*   `void highlighted (const QString&)`
*   `void historyChanged ()`
*   `void sourceChanged (const QUrl&)`

* * *

## Detailed Description

中，QTextBrowser类提供了超文本浏览丰富的文本浏览器。

此类扩展[QTextEdit](qtextedit.html)（在只读模式下） ，添加一些导航功能，以便用户可以按照超文本文件的链接。

如果您想为您的用户提供了一个可编辑的富文本编辑器，使用[QTextEdit](qtextedit.html)。如果你想不超文本导航使用文本浏览器[QTextEdit](qtextedit.html)和使用[QTextEdit.setReadOnly](qtextedit.html#readOnly-prop)（ ）禁用编辑。如果你只是需要显示一小块富文本使用[QLabel](qlabel.html)。

### Document Source and Contents

的内容[QTextEdit](qtextedit.html)设置与[setHtml](qtextedit.html#html-prop)（）或[setPlainText](qtextedit.html#plainText-prop)（ ） ，但QTextBrowser也实现了[setSource](qtextbrowser.html#source-prop)（）函数，使得可以使用命名文件的源文本。该名称抬头的搜索路径列表，并在当前文档工厂的目录。

如果一个文件名与一个锚（例如， “结束`#anchor"`） ，文本浏览器会自动滚动到该位置（使用[scrollToAnchor](qtextedit.html#scrollToAnchor)（））。当用户点击一个超链接时，浏览器会调用[setSource](qtextbrowser.html#source-prop)（ ）本身带有链接的`href`值作为参数。您可以通过连接到跟踪电流源[sourceChanged](qtextbrowser.html#sourceChanged)（）信号。

### Navigation

QTextBrowser提供[backward](qtextbrowser.html#backward)（）和[forward](qtextbrowser.html#forward)（ ）插槽，你可以用它来实现后退和前进按钮。该[home](qtextbrowser.html#home)（）槽设置文本显示的第一个文件。该[anchorClicked](qtextbrowser.html#anchorClicked)当用户点击一个锚（ ）信号被发射。要复盖浏览器的默认导航行为，请拨打[setSource](qtextbrowser.html#source-prop)（ ）函数在连接到该信号插槽提供新的文档中的文本。

如果要加载存储在Qt的资源系统中使用的文件`qrc`作为URL的方式来加载。例如，对于文件资源路径`:/docs/index.html`使用`qrc:/docs/index.html`作为与URL[setSource](qtextbrowser.html#source-prop)（ ） 。要访问本地文件，使用`file`作为URL的方案。

* * *

## Method Documentation

```
QTextBrowser.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个空[QTextBrowser](qtextbrowser.html)与父_parent_。

```
QTextBrowser.backward (self)
```

这种方法也是一个Qt槽与C + +的签名`void backward()`。

变化的通过导航链接建立文件列表中显示先前的文档的文档。什么都不做，如果没有以前的文档。

**See also** [forward](qtextbrowser.html#forward)（）和[backwardAvailable](qtextbrowser.html#backwardAvailable)（ ） 。

```
int QTextBrowser.backwardHistoryCount (self)
```

返回的位置数落后的历史。

此功能被引入Qt的4.4 。

```
QTextBrowser.clearHistory (self)
```

清除访问了文件的历史和禁用向前和向后导航。

这个函数中引入了Qt 4.2中。

**See also** [backward](qtextbrowser.html#backward)（）和[forward](qtextbrowser.html#forward)（ ） 。

```
bool QTextBrowser.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
bool QTextBrowser.focusNextPrevChild (self, bool next)
```

从重新实现[QWidget.focusNextPrevChild](qwidget.html#focusNextPrevChild)（ ） 。

```
QTextBrowser.focusOutEvent (self, QFocusEvent ev)
```

从重新实现[QWidget.focusOutEvent](qwidget.html#focusOutEvent)（ ） 。

```
QTextBrowser.forward (self)
```

这种方法也是一个Qt槽与C + +的签名`void forward()`。

更改显示在通过导航链接建立文件列表中的下一个文档的文档。什么都不做，如果没有下一个文件。

**See also** [backward](qtextbrowser.html#backward)（）和[forwardAvailable](qtextbrowser.html#forwardAvailable)（ ） 。

```
int QTextBrowser.forwardHistoryCount (self)
```

返回的位置数前进的历史。

此功能被引入Qt的4.4 。

```
QString QTextBrowser.historyTitle (self, int)
```

返回[documentTitle](qtextedit.html#documentTitle-prop)该HistoryItem的（ ） 。

| Input | Return |
| --- | --- |
| _i_ &lt; 0 | [backward](qtextbrowser.html#backward)() history |
| _i_ == 0 | current, see [QTextBrowser.source](qtextbrowser.html#source-prop)() |
| _i_ &gt; 0 | [forward](qtextbrowser.html#forward)() history |

```
 backaction.setToolTip(browser.historyTitle(-1));
 forwardaction.setToolTip(browser.historyTitle(+1));

```

此功能被引入Qt的4.4 。

```
QUrl QTextBrowser.historyUrl (self, int)
```

[

返回HistoryItem的url 。

| Input | Return |
| --- | --- |
| _i_ &lt; 0 | [backward](qtextbrowser.html#backward)() history |
| _i_ == 0 | current, see [QTextBrowser.source](qtextbrowser.html#source-prop)() |
| _i_ &gt; 0 | [forward](qtextbrowser.html#forward)() history |

此功能被引入Qt的4.4 。

```
QTextBrowser.home (self)
```

这种方法也是一个Qt槽与C + +的签名`void home()`。

改变显示的是从历史中第一个文档的文档。

```
bool QTextBrowser.isBackwardAvailable (self)
```

](qurl.html)

[返回True如果文本浏览器可以向后走在历史文件使用](qurl.html)[backward](qtextbrowser.html#backward)（ ） 。

这个函数中引入了Qt 4.2中。

**See also** [backwardAvailable](qtextbrowser.html#backwardAvailable)（）和[backward](qtextbrowser.html#backward)（ ） 。

```
bool QTextBrowser.isForwardAvailable (self)
```

返回True如果文本浏览器可以前进中的文档历史记录使用[forward](qtextbrowser.html#forward)（ ） 。

这个函数中引入了Qt 4.2中。

**See also** [forwardAvailable](qtextbrowser.html#forwardAvailable)（）和[forward](qtextbrowser.html#forward)（ ） 。

```
QTextBrowser.keyPressEvent (self, QKeyEvent ev)
```

从重新实现[QWidget.keyPressEvent](qwidget.html#keyPressEvent)（ ） 。

本次活动_ev_用于提供以下键盘快捷键：

| Keypress | Action |
| --- | --- |
| Alt+Left Arrow | [backward](qtextbrowser.html#backward)() |
| Alt+Right Arrow | [forward](qtextbrowser.html#forward)() |
| Alt+Up Arrow | [home](qtextbrowser.html#home)() |

```
QVariant QTextBrowser.loadResource (self, int type, QUrl name)
```

从重新实现[QTextEdit.loadResource](qtextedit.html#loadResource)（ ） 。

这个函数在文件被加载时被调用，并且对文档中的每个图像。该_type_表示要加载的资源的类型。无效的[QVariant](qvariant.html)如果无法加载该资源将被返回。

默认实现忽略_type_并试图通过解释来定位资源_name_作为文件名。如果它不是一个绝对路径，它试图找到文件中的路径[searchPaths](qtextbrowser.html#searchPaths-prop)属性，并在相同的目录中的电流源。如果成功，则结果为一[QVariant](qvariant.html)其存储[QByteArray](qbytearray.html)与该文件的内容。

如果你重新实现这个功能，你可以返回其他[QVariant](qvariant.html)类型。下面哪一个变量的类型是根据资源的类型支持表所示：

| ResourceType | [QVariant.Type](qvariant.html#Type-enum) |
| --- | --- |
| [QTextDocument.HtmlResource](qtextdocument.html#ResourceType-enum) | [QString](qstring.html) or [QByteArray](qbytearray.html) |
| [QTextDocument.ImageResource](qtextdocument.html#ResourceType-enum) | [QImage](qimage.html), [QPixmap](qpixmap.html) or [QByteArray](qbytearray.html) |
| [QTextDocument.StyleSheetResource](qtextdocument.html#ResourceType-enum) | [QString](qstring.html) or [QByteArray](qbytearray.html) |

```
QTextBrowser.mouseMoveEvent (self, QMouseEvent ev)
```

从重新实现[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

```
QTextBrowser.mousePressEvent (self, QMouseEvent ev)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

```
QTextBrowser.mouseReleaseEvent (self, QMouseEvent ev)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

```
bool QTextBrowser.openExternalLinks (self)
```

```
bool QTextBrowser.openLinks (self)
```

```
QTextBrowser.paintEvent (self, QPaintEvent e)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QTextBrowser.reload (self)
```

这种方法也是一个Qt槽与C + +的签名`void reload()`。

重新加载当前组源。

```
QStringList QTextBrowser.searchPaths (self)
```

```
QTextBrowser.setOpenExternalLinks (self, bool open)
```

```
QTextBrowser.setOpenLinks (self, bool open)
```

```
QTextBrowser.setSearchPaths (self, QStringList paths)
```

```
QTextBrowser.setSource (self, QUrl name)
```

这种方法也是一个Qt槽与C + +的签名`void setSource(const QUrl&)`。

```
QUrl QTextBrowser.source (self)
```

[

* * *

## Qt Signal Documentation

```
void anchorClicked (const QUrl&)
```

这是该信号的默认超载。

当用户点击一个锚这个信号被发射。由锚所指的URL传递中_link_。

](qurl.html)

[请注意，浏览器会自动处理导航到所指定的位置_link_除非](qurl.html)[openLinks](qtextbrowser.html#openLinks-prop)属性设置为False ，或者您致电[setSource](qtextbrowser.html#source-prop)（ ）在连接的插槽。这种机制被用于重写浏览器的默认导航功能。

```
void backwardAvailable (bool)
```

这是该信号的默认超载。

这个信号被发射时的可用性的[backward](qtextbrowser.html#backward)（）的变化。_available_为假，当用户是在[home](qtextbrowser.html#home)（ ），否则它是真实的。

```
void forwardAvailable (bool)
```

这是该信号的默认超载。

这个信号被发射时的可用性的[forward](qtextbrowser.html#forward)（）的变化。_available_是真实的用户浏览后[backward](qtextbrowser.html#backward)（ ），当用户浏览或为假[forward](qtextbrowser.html#forward)（ ） 。

```
void highlighted (const QUrl&)
```

这是该信号的默认超载。

当用户已选择但尚未激活的锚定文档中的这个信号被发射。由锚所指的URL传递中_link_。

```
void highlighted (const QString&)
```

这是一个重载函数。

允许连接到一个插槽，只需要在便利信号[QString](qstring.html)，例如像[QStatusBar](qstatusbar.html)的消息（ ） 。

```
void historyChanged ()
```

这是该信号的默认超载。

当历史改变这个信号被发射。

此功能被引入Qt的4.4 。

**See also** [historyTitle](qtextbrowser.html#historyTitle)（）和[historyUrl](qtextbrowser.html#historyUrl)（ ） 。

```
void sourceChanged (const QUrl&)
```

这是该信号的默认超载。

这个信号被发射时在源发生了变化，_src_作为新来源。

来源发生变化既编程方式调用时，[setSource](qtextbrowser.html#source-prop)（ ）[forward](qtextbrowser.html#forward)（） ，退后（）或[home](qtextbrowser.html#home)（ ），或者当用户点击链接或按压等效键序列。