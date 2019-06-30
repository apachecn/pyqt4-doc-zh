# QWebView Class Reference

## [[QtWebKit](index.htm) module]

该QWebView类提供了用于查看和编辑网页文件的小工具。[More...](#details)

继承[QWidget](qwidget.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `back (self)`
*   `changeEvent (self, QEvent)`
*   `contextMenuEvent (self, QContextMenuEvent)`
*   `QWebView createWindow (self, QWebPage.WebWindowType type)`
*   `dragEnterEvent (self, QDragEnterEvent)`
*   `dragLeaveEvent (self, QDragLeaveEvent)`
*   `dragMoveEvent (self, QDragMoveEvent)`
*   `dropEvent (self, QDropEvent)`
*   `bool event (self, QEvent)`
*   `bool findText (self, QString subString, QWebPage.FindFlags options = 0)`
*   `focusInEvent (self, QFocusEvent)`
*   `bool focusNextPrevChild (self, bool next)`
*   `focusOutEvent (self, QFocusEvent)`
*   `forward (self)`
*   `bool hasSelection (self)`
*   `QWebHistory history (self)`
*   `QIcon icon (self)`
*   `inputMethodEvent (self, QInputMethodEvent)`
*   `QVariant inputMethodQuery (self, Qt.InputMethodQuery property)`
*   `bool isModified (self)`
*   `keyPressEvent (self, QKeyEvent)`
*   `keyReleaseEvent (self, QKeyEvent)`
*   `load (self, QUrl url)`
*   `load (self, QNetworkRequest request, QNetworkAccessManager.Operation operation = QNetworkAccessManager.GetOperation, QByteArray body = QByteArray())`
*   `mouseDoubleClickEvent (self, QMouseEvent)`
*   `mouseMoveEvent (self, QMouseEvent)`
*   `mousePressEvent (self, QMouseEvent)`
*   `mouseReleaseEvent (self, QMouseEvent)`
*   `QWebPage page (self)`
*   `QAction pageAction (self, QWebPage.WebAction action)`
*   `paintEvent (self, QPaintEvent ev)`
*   `print (self, QPrinter printer)`
*   `print_ (self, QPrinter printer)`
*   `reload (self)`
*   `QPainter.RenderHints renderHints (self)`
*   `resizeEvent (self, QResizeEvent e)`
*   `QString selectedHtml (self)`
*   `QString selectedText (self)`
*   `setContent (self, QByteArray data, QString mimeType = QString(), QUrl baseUrl = QUrl())`
*   `setHtml (self, QString html, QUrl baseUrl = QUrl())`
*   `setPage (self, QWebPage page)`
*   `setRenderHint (self, QPainter.RenderHint hint, bool enabled = True)`
*   `setRenderHints (self, QPainter.RenderHints hints)`
*   `setTextSizeMultiplier (self, float factor)`
*   `QWebSettings settings (self)`
*   `setUrl (self, QUrl url)`
*   `setZoomFactor (self, float factor)`
*   `QSize sizeHint (self)`
*   `stop (self)`
*   `float textSizeMultiplier (self)`
*   `QString title (self)`
*   `triggerPageAction (self, QWebPage.WebAction action, bool checked = False)`
*   `QUrl url (self)`
*   `wheelEvent (self, QWheelEvent)`
*   `float zoomFactor (self)`

### Qt Signals

*   `void iconChanged ()`
*   `void linkClicked (const QUrl&)`
*   `void loadFinished (bool)`
*   `void loadProgress (int)`
*   `void loadStarted ()`
*   `void selectionChanged ()`
*   `void statusBarMessage (const QString&)`
*   `void titleChanged (const QString&)`
*   `void urlChanged (const QUrl&)`

* * *

## Detailed Description

该QWebView类提供了用于查看和编辑网页文件的小工具。

QWebView是其中的主要组成部件[QtWebKit](index.htm)网页浏览模块。它可以用在各种应用中显示从因特网web内容住。

一个网站可以被加载到QWebView与[load](qwebview.html#load)（）函数。像所有的Qt部件，该[show](qwidget.html#show)（）函数必须以显示QWebView被调用。下面的代码段说明了这一点：

```
     QWebView *view = new QWebView(parent);
     view->load([QUrl](qurl.html)("http://qt-project.org"));
     view->show();

```

另外，[setUrl](qwebview.html#url-prop)（）也可以被用于加载一个网站。如果您有HTML内容一应俱全，您可以使用[setHtml](qwebview.html#setHtml)（ ）来代替。

该[loadStarted](qwebview.html#loadStarted)当视图开始加载（ ）信号被发射。该[loadProgress](qwebview.html#loadProgress)（）信号，另一方面，是每当在网络视图中的一个元素完成加载，如嵌入图像，脚本等发出最后，该[loadFinished](qwebview.html#loadFinished)（ ）信号，当视图已经完全加载发出。它的参数 - 无论是`true` or `false` - 表示加载成功或失败。

该[page](qwebview.html#page)（ ）函数返回一个指向该网页的对象。看[Elements of QWebView](#elements-of-qwebview)对于如何网页是有关意见之理由。修改你的web视图的设置，您可以访问[QWebSettings](qwebsettings.html)与对象[settings](qwebview.html#settings)（）函数。同[QWebSettings](qwebsettings.html)，你可以更改默认字体，启用或禁用功能，如JavaScript和插件。

一个HTML文件的标题可以用被访问[title](qwebview.html#title-prop)（）属性。此外，网站也可以使用指定一个图标，它可被访问的[icon](qwebview.html#icon-prop)（）属性。如果标题或图标的变化，相应的[titleChanged](qwebview.html#titleChanged)（）和[iconChanged](qwebview.html#iconChanged)（）信号将被发射。该[textSizeMultiplier](qwebview.html#textSizeMultiplier)（ ）属性可用于改变在网页视图中显示的文本的整体规模。

如果你需要一个自定义上下文菜单，你可以通过重新实现实现它[contextMenuEvent()](qwidget.html#contextMenuEvent)并填充你的[QMenu](qmenu.html)从获得的操作[pageAction](qwebview.html#pageAction)（ ） 。更多的功能，例如重新加载视图，选定的文本复制到剪贴板，或者粘贴到视图，也封装内[QAction](qaction.html)通过返回的对象[pageAction](qwebview.html#pageAction)（ ） 。这些操作可以通过编程方式触发[triggerPageAction](qwebview.html#triggerPageAction)（ ） 。可选地，操作可以被添加到工具栏或直接的菜单。 QWebView维护操作返回的状态，但允许的动作特性，例如修改[text](qaction.html#text-prop) or [icon](qaction.html#icon-prop)。

一个QWebView可以打印到[QPrinter](qprinter.html)使用[print_](qwebview.html#print)（）函数。这个功能被标记为一个时隙，并且可以方便地连接到[QPrintPreviewDialog](qprintpreviewdialog.html)的[paintRequested()](qprintpreviewdialog.html#paintRequested)信号。

如果您想提供的网站，允许用户打开新的窗口，如弹出窗口的支持，你可以继承QWebView和重新实现[createWindow](qwebview.html#createWindow)（）函数。

### Elements of QWebView

QWebView包含其他对象，如[QWebFrame](qwebframe.html)和[QWebPage](qwebpage.html)。下面的流程图显示了这些元素之间的关系。

![](../img/qwebview-diagram.png)

**Note:**它可以使用[QWebPage](qwebpage.html)和[QWebFrame](qwebframe.html)，不使用QWebView ，如果你不要求[QWidget](qwidget.html)属性。尽管如此，[QtWebKit](index.htm)取决于[QtGui](index.htm)，所以你应该使用一个[QApplication](qapplication.html)而不是[QCoreApplication](qcoreapplication.html)。

* * *

## Method Documentation

```
QWebView.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个空[QWebView](qwebview.html)与父_parent_。

**See also** [load](qwebview.html#load)（ ） 。

```
QWebView.back (self)
```

这种方法也是一个Qt槽与C + +的签名`void back()`。

便利插槽加载以前的文档中通过导航链接建立文件清单。什么都不做，如果没有以前的文档。

它相当于

```
     view->page()->triggerPageAction([QWebPage](qwebpage.html).GoBack);

```

**See also** [forward](qwebview.html#forward)（）和[pageAction](qwebview.html#pageAction)（ ） 。

```
QWebView.changeEvent (self, QEvent)
```

从重新实现[QWidget.changeEvent](qwidget.html#changeEvent)（ ） 。

```
QWebView.contextMenuEvent (self, QContextMenuEvent)
```

从重新实现[QWidget.contextMenuEvent](qwidget.html#contextMenuEvent)（ ） 。

```
QWebView QWebView.createWindow (self, QWebPage.WebWindowType type)
```

[](qwebview.html)

[这个功能是从CreateWindow的调用（相关的）方法](qwebview.html)[QWebPage](qwebpage.html)中，每当页想要创建的给定一个新的窗口_type_。这可能是一个JavaScript请求，在新窗口中打开的文档的结果，例如， 。

**Note:**如果相关的页面CreateWindow的（ ）方法被重新实现，这种方法不叫，除非重新实现显式地这样做。

**Note:**在该情况下，当窗口的创建是由JavaScript的触发，除了重新实现此方法的应用程序还必须设置的JavaScriptCanOpenWindows属性[QWebSettings](qwebsettings.html)为True，以便它被调用。

**See also** [QWebPage.createWindow](qwebpage.html#createWindow)（）和[QWebPage.acceptNavigationRequest](qwebpage.html#acceptNavigationRequest)（ ） 。

```
QWebView.dragEnterEvent (self, QDragEnterEvent)
```

从重新实现[QWidget.dragEnterEvent](qwidget.html#dragEnterEvent)（ ） 。

```
QWebView.dragLeaveEvent (self, QDragLeaveEvent)
```

从重新实现[QWidget.dragLeaveEvent](qwidget.html#dragLeaveEvent)（ ） 。

```
QWebView.dragMoveEvent (self, QDragMoveEvent)
```

从重新实现[QWidget.dragMoveEvent](qwidget.html#dragMoveEvent)（ ） 。

```
QWebView.dropEvent (self, QDropEvent)
```

从重新实现[QWidget.dropEvent](qwidget.html#dropEvent)（ ） 。

```
bool QWebView.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
bool QWebView.findText (self, QString subString, QWebPage.FindFlags options = 0)
```

查找指定的字符串，_subString_在该页面中，使用给定的_options_。

如果HighlightAllOccurrences标志传递，函数将突出存在于页面中的所有事件。所有后续调用将延长的亮点，而不是取代它，以出现新的字符串。

如果HighlightAllOccurrences标志不通过，该函数将选择的发生，所有后续调用将取代目前出现的下一个。

要清除选择，只传递一个空字符串。

返回True如果_subString_结果发现，否则返回False 。

**See also** [selectedText](qwebview.html#selectedText-prop)（）和[selectionChanged](qwebview.html#selectionChanged)（ ） 。

```
QWebView.focusInEvent (self, QFocusEvent)
```

从重新实现[QWidget.focusInEvent](qwidget.html#focusInEvent)（ ） 。

```
bool QWebView.focusNextPrevChild (self, bool next)
```

从重新实现[QWidget.focusNextPrevChild](qwidget.html#focusNextPrevChild)（ ） 。

```
QWebView.focusOutEvent (self, QFocusEvent)
```

从重新实现[QWidget.focusOutEvent](qwidget.html#focusOutEvent)（ ） 。

```
QWebView.forward (self)
```

这种方法也是一个Qt槽与C + +的签名`void forward()`。

便利插槽，加载下一个文档中通过导航链接建立文件清单。什么都不做，如果没有下一个文件。

它相当于

```
     view->page()->triggerPageAction([QWebPage](qwebpage.html).GoForward);

```

**See also** [back](qwebview.html#back)（）和[pageAction](qwebview.html#pageAction)（ ） 。

```
bool QWebView.hasSelection (self)
```

```
QWebHistory QWebView.history (self)
```

[

返回一个指针，指向的导航网页视图的历史。

它相当于

```
     view->page()->history();

```

](qwebhistory.html)

```
QIcon QWebView.icon (self)
```

[

```
QWebView.inputMethodEvent (self, QInputMethodEvent)
```

](qicon.html)

[从重新实现](qicon.html)[QWidget.inputMethodEvent](qwidget.html#inputMethodEvent)（ ） 。

```
QVariant QWebView.inputMethodQuery (self, Qt.InputMethodQuery property)
```

从重新实现[QWidget.inputMethodQuery](qwidget.html#inputMethodQuery)（ ） 。

```
bool QWebView.isModified (self)
```

```
QWebView.keyPressEvent (self, QKeyEvent)
```

从重新实现[QWidget.keyPressEvent](qwidget.html#keyPressEvent)（ ） 。

```
QWebView.keyReleaseEvent (self, QKeyEvent)
```

从重新实现[QWidget.keyReleaseEvent](qwidget.html#keyReleaseEvent)（ ） 。

```
QWebView.load (self, QUrl url)
```

指定的负载_url_并显示它。

**Note:**该视图保持不变，直到足够的数据已经到达，以显示新_url_。

**See also** [setUrl](qwebview.html#url-prop)（ ）[url](qwebview.html#url-prop)（ ）[urlChanged](qwebview.html#urlChanged)（）和[QUrl.fromUserInput](qurl.html#fromUserInput)（ ） 。

```
QWebView.load (self, QNetworkRequest request, QNetworkAccessManager.Operation operation = QNetworkAccessManager.GetOperation, QByteArray body = QByteArray())
```

加载一个网络请求，_request_使用中规定的方法_operation_。

_body_是可选的，并且仅用于POST操作。

**Note:**该视图保持不变，直到足够的数据已经到达，以显示新的URL。

**See also** [url](qwebview.html#url-prop)（）和[urlChanged](qwebview.html#urlChanged)（ ） 。

```
QWebView.mouseDoubleClickEvent (self, QMouseEvent)
```

从重新实现[QWidget.mouseDoubleClickEvent](qwidget.html#mouseDoubleClickEvent)（ ） 。

```
QWebView.mouseMoveEvent (self, QMouseEvent)
```

从重新实现[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

```
QWebView.mousePressEvent (self, QMouseEvent)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

```
QWebView.mouseReleaseEvent (self, QMouseEvent)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

```
QWebPage QWebView.page (self)
```

[

返回一个指针，指向底层的网页。

](qwebpage.html)

[**See also**](qwebpage.html) [setPage](qwebview.html#setPage)（ ） 。

```
QAction QWebView.pageAction (self, QWebPage.WebAction action)
```

[](qaction.html)

[返回一个指针，指向一个](qaction.html)[QAction](qaction.html)封装指定网络行动_action_。

```
QWebView.paintEvent (self, QPaintEvent ev)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QWebView.print (self, QPrinter printer)
```

这种方法也是一个Qt槽与C + +的签名`void print(QPrinter *) const`。

打印主框架给定的_printer_。

**See also** [QWebFrame.print](qwebframe.html#print)（）和[QPrintPreviewDialog](qprintpreviewdialog.html)。

```
QWebView.print_ (self, QPrinter printer)
```

这种方法也是一个Qt槽与C + +的签名`void print(QPrinter *) const`。

打印主框架给定的_printer_。

**See also** [QWebFrame.print](qwebframe.html#print)（）和[QPrintPreviewDialog](qprintpreviewdialog.html)。

```
QWebView.reload (self)
```

这种方法也是一个Qt槽与C + +的签名`void reload()`。

重新加载当前文档。

**See also** [stop](qwebview.html#stop)（ ）[pageAction](qwebview.html#pageAction)（）和[loadStarted](qwebview.html#loadStarted)（ ） 。

```
QPainter.RenderHints QWebView.renderHints (self)
```

[

```
QWebView.resizeEvent (self, QResizeEvent e)
```

](index.htm)

[从重新实现](index.htm)[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
QString QWebView.selectedHtml (self)
```

```
QString QWebView.selectedText (self)
```

```
QWebView.setContent (self, QByteArray data, QString mimeType = QString(), QUrl baseUrl = QUrl())
```

设置Web视图中的内容到指定的内容_data_。如果_mimeType_参数为空它是目前假设内容是HTML，但在未来的版本中，我们可能会引入自动检测。

在内容引用的外部对象的位置相对_baseUrl_。

该_data_立即加载;外部对象异步加载。

**See also** [load](qwebview.html#load)（ ）[setHtml](qwebview.html#setHtml)（）和[QWebFrame.toHtml](qwebframe.html#toHtml)（ ） 。

```
QWebView.setHtml (self, QString html, QUrl baseUrl = QUrl())
```

设置Web视图的内容的指定_html_。

外部对象，如样式表或HTML文档中引用的图片的位置相对于_baseUrl_。

该_html_立即加载;外部对象异步加载。

使用此方法时， WebKit的假定外部资源，例如JavaScript程序或样式表，除非另有规定被编码为UTF -8 。例如，外部脚本的编码可以通过HTML脚本标记的charset属性来指定。备选地，编码也可以由Web服务器指定。

这相当于一个方便的功能，使用setContent （ HTML ， “为text / html ” ， baseURL即可） 。

**Warning:**此功能仅用于HTML ，为其他MIME类型（即XHTML ， SVG ）[setContent](qwebview.html#setContent)（ ）应该使用。

**See also** [load](qwebview.html#load)（ ）[setContent](qwebview.html#setContent)（ ）[QWebFrame.toHtml](qwebframe.html#toHtml)（）和[QWebFrame.setContent](qwebframe.html#setContent)（ ） 。

```
QWebView.setPage (self, QWebPage page)
```

品牌_page_Web视图的新网页。

父[QObject](qobject.html)该页面提供的仍然是对象的所有者。如果当前页面是Web视图的孩子，它会被删除。

**See also** [page](qwebview.html#page)（ ） 。

```
QWebView.setRenderHint (self, QPainter.RenderHint hint, bool enabled = True)
```

If _enabled_诚然，启用指定的渲染_hint_否则禁用它。

此功能被引入Qt的4.6 。

**See also** [renderHints](qwebview.html#renderHints-prop)和[QPainter.renderHints](qpainter.html#renderHints)（ ） 。

```
QWebView.setRenderHints (self, QPainter.RenderHints hints)
```

```
QWebView.setTextSizeMultiplier (self, float factor)
```

设置用于缩放网页中的文字乘数的值_factor_规定。

**See also** [textSizeMultiplier](qwebview.html#textSizeMultiplier)（ ） 。

```
QWebSettings QWebView.settings (self)
```

[

返回一个指针，指向视图/页面设置特定对象。

它相当于

```
     view->page()->settings();

```

](qwebsettings.html)

[**See also**](qwebsettings.html) [QWebSettings.globalSettings](qwebsettings.html#globalSettings)（ ） 。

```
QWebView.setUrl (self, QUrl url)
```

```
QWebView.setZoomFactor (self, float factor)
```

```
QSize QWebView.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

```
QWebView.stop (self)
```

这种方法也是一个Qt槽与C + +的签名`void stop()`。

便利插槽，停止加载该文件。

它相当于

```
     view->page()->triggerPageAction([QWebPage](qwebpage.html).Stop);

```

**See also** [reload](qwebview.html#reload)（ ）[pageAction](qwebview.html#pageAction)（）和[loadFinished](qwebview.html#loadFinished)（ ） 。

```
float QWebView.textSizeMultiplier (self)
```

返回用于扩展在Web页面中的文本乘数的值。

**See also** [setTextSizeMultiplier](qwebview.html#setTextSizeMultiplier)（ ） 。

```
QString QWebView.title (self)
```

```
QWebView.triggerPageAction (self, QWebPage.WebAction action, bool checked = False)
```

触发指定的_action_。如果是指定了辨认的动作_checked_假定状态。

下面的例子将触发复制动作，所以副本中的任何选定的文本复制到剪贴板。

```
     view->triggerAction([QWebPage](qwebpage.html).Copy);

```

**See also** [pageAction](qwebview.html#pageAction)（ ） 。

```
QUrl QWebView.url (self)
```

[

```
QWebView.wheelEvent (self, QWheelEvent)
```

](qurl.html)

[从重新实现](qurl.html)[QWidget.wheelEvent](qwidget.html#wheelEvent)（ ） 。

```
float QWebView.zoomFactor (self)
```

* * *

## Qt Signal Documentation

```
void iconChanged ()
```

这是该信号的默认超载。

这个信号时页面的图标被加载或改变被发射。

为了让图标加载，则需要使用设置一个图标数据库路径[QWebSettings.setIconDatabasePath](qwebsettings.html#setIconDatabasePath)（ ） 。

**See also** [icon](qwebview.html#icon-prop)（）和[QWebSettings.setIconDatabasePath](qwebsettings.html#setIconDatabasePath)（ ） 。

```
void linkClicked (const QUrl&)
```

这是该信号的默认超载。

每当用户点击一个链接这个信号被发射以及页面的linkDelegationPolicy属性设置为处理委讬给指定的链接_url_。

**See also** [QWebPage.linkDelegationPolicy](qwebpage.html#linkDelegationPolicy-prop)（ ） 。

```
void loadFinished (bool)
```

这是该信号的默认超载。

当页面的加载完成时，这个信号被发射。_ok_将指示负载是否成功，或发生任何错误。

**See also** [loadStarted](qwebview.html#loadStarted)（ ） 。

```
void loadProgress (int)
```

这是该信号的默认超载。

每个网页中的元素完成加载和整体加载进度前进时，这个信号被发射。

这个信号可以跟踪所有子帧的进展。

电流值是由所提供_progress_和秤从0到100 ，这是默认范围[QProgressBar](qprogressbar.html)。

**See also** [loadStarted](qwebview.html#loadStarted)（）和[loadFinished](qwebview.html#loadFinished)（ ） 。

```
void loadStarted ()
```

这是该信号的默认超载。

当开始页面的新负载，这个信号被发射。

**See also** [loadProgress](qwebview.html#loadProgress)（）和[loadFinished](qwebview.html#loadFinished)（ ） 。

```
void selectionChanged ()
```

这是该信号的默认超载。

这个信号被发射时的选择改变。

**See also** [selectedText](qwebview.html#selectedText-prop)（ ） 。

```
void statusBarMessage (const QString&)
```

这是该信号的默认超载。

这个信号被发射时，状态栏_text_由页改变。

```
void titleChanged (const QString&)
```

这是该信号的默认超载。

这个信号被发射时的_title_的主框架的改变。

**See also** [title](qwebview.html#title-prop)（ ） 。

```
void urlChanged (const QUrl&)
```

这是该信号的默认超载。

这个信号被发射时的_url_的观点变化。

**See also** [url](qwebview.html#url-prop)（）和[load](qwebview.html#load)（ ） 。