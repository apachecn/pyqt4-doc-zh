# QGraphicsWebView Class Reference

## [[QtWebKit](index.htm) module]

该QGraphicsWebView类允许Web内容被添加到一个[GraphicsView](index.htm#graphicsview)。[More...](#details)

继承[QGraphicsWidget](qgraphicswidget.html)。

### Methods

*   `__init__ (self, QGraphicsItem parent = None)`
*   `back (self)`
*   `contextMenuEvent (self, QGraphicsSceneContextMenuEvent)`
*   `dragEnterEvent (self, QGraphicsSceneDragDropEvent)`
*   `dragLeaveEvent (self, QGraphicsSceneDragDropEvent)`
*   `dragMoveEvent (self, QGraphicsSceneDragDropEvent)`
*   `dropEvent (self, QGraphicsSceneDragDropEvent)`
*   `bool event (self, QEvent)`
*   `bool findText (self, QString subString, QWebPage.FindFlags options = 0)`
*   `focusInEvent (self, QFocusEvent)`
*   `bool focusNextPrevChild (self, bool next)`
*   `focusOutEvent (self, QFocusEvent)`
*   `forward (self)`
*   `QWebHistory history (self)`
*   `hoverLeaveEvent (self, QGraphicsSceneHoverEvent)`
*   `hoverMoveEvent (self, QGraphicsSceneHoverEvent)`
*   `QIcon icon (self)`
*   `inputMethodEvent (self, QInputMethodEvent)`
*   `QVariant inputMethodQuery (self, Qt.InputMethodQuery query)`
*   `bool isModified (self)`
*   `bool isTiledBackingStoreFrozen (self)`
*   `QVariant itemChange (self, QGraphicsItem.GraphicsItemChange change, QVariant value)`
*   `keyPressEvent (self, QKeyEvent)`
*   `keyReleaseEvent (self, QKeyEvent)`
*   `load (self, QUrl url)`
*   `load (self, QNetworkRequest request, QNetworkAccessManager.Operation operation = QNetworkAccessManager.GetOperation, QByteArray body = QByteArray())`
*   `mouseDoubleClickEvent (self, QGraphicsSceneMouseEvent)`
*   `mouseMoveEvent (self, QGraphicsSceneMouseEvent)`
*   `mousePressEvent (self, QGraphicsSceneMouseEvent)`
*   `mouseReleaseEvent (self, QGraphicsSceneMouseEvent)`
*   `QWebPage page (self)`
*   `QAction pageAction (self, QWebPage.WebAction action)`
*   `paint (self, QPainter painter, QStyleOptionGraphicsItem option, QWidget widget = None)`
*   `reload (self)`
*   `QPainter.RenderHints renderHints (self)`
*   `bool resizesToContents (self)`
*   `bool sceneEvent (self, QEvent)`
*   `setContent (self, QByteArray data, QString mimeType = QString(), QUrl baseUrl = QUrl())`
*   `setGeometry (self, QRectF rect)`
*   `setHtml (self, QString html, QUrl baseUrl = QUrl())`
*   `setPage (self, QWebPage)`
*   `setRenderHint (self, QPainter.RenderHint hint, bool enabled = True)`
*   `setRenderHints (self, QPainter.RenderHints hints)`
*   `setResizesToContents (self, bool enabled)`
*   `setTiledBackingStoreFrozen (self, bool frozen)`
*   `QWebSettings settings (self)`
*   `setUrl (self, QUrl)`
*   `setZoomFactor (self, float)`
*   `QSizeF sizeHint (self, Qt.SizeHint which, QSizeF constraint)`
*   `stop (self)`
*   `QString title (self)`
*   `triggerPageAction (self, QWebPage.WebAction action, bool checked = False)`
*   `updateGeometry (self)`
*   `QUrl url (self)`
*   `wheelEvent (self, QGraphicsSceneWheelEvent)`
*   `float zoomFactor (self)`

### Qt Signals

*   `void iconChanged ()`
*   `void linkClicked (const QUrl&)`
*   `void loadFinished (bool)`
*   `void loadProgress (int)`
*   `void loadStarted ()`
*   `void statusBarMessage (const QString&)`
*   `void titleChanged (const QString&)`
*   `void urlChanged (const QUrl&)`

* * *

## Detailed Description

该QGraphicsWebView类允许Web内容被添加到一个[GraphicsView](index.htm#graphicsview)。

这个类的一个实例呈现从URL网页内容或提供的数据，使用的功能[QtWebKit](index.htm)模块。

如果该项目的宽度和高度都没有设置，它们将默认为800和600 ，分别为。如果网页内容比越大，滚动条，如果没有明确禁止将被显示。

### Browser Features

许多所提供的功能，信号和属性[QWebView](qwebview.html)也可用于这一项目，使其成为简单，适应现有的代码使用QGraphicsWebView代替[QWebView](qwebview.html)。

该项目采用的是[QWebPage](qwebpage.html)反对执行Web内容的呈现，这样就可以用得到[page](qgraphicswebview.html#page)（）函数，使文档本身进行访问和修改。

与[QWebView](qwebview.html)使用项目记录浏览历史记录[QWebHistory](qwebhistory.html)对象，访问使用[history](qgraphicswebview.html#history)（）函数。该[QWebSettings](qwebsettings.html)对象，定义了浏览器的配置可以用以下方式获得[settings](qgraphicswebview.html#settings)（ ）函数，使像插件支持自定义每个项目的功能。

* * *

## Method Documentation

```
QGraphicsWebView.__init__ (self, QGraphicsItem parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个空[QGraphicsWebView](qgraphicswebview.html)与父_parent_。

**See also** [load](qgraphicswebview.html#load)（ ） 。

```
QGraphicsWebView.back (self)
```

这种方法也是一个Qt槽与C + +的签名`void back()`。

便利插槽加载以前的文档中通过导航链接建立文件清单。什么都不做，如果没有以前的文档。

**See also** [forward](qgraphicswebview.html#forward)（ ） 。

```
QGraphicsWebView.contextMenuEvent (self, QGraphicsSceneContextMenuEvent)
```

从重新实现[QGraphicsItem.contextMenuEvent](qgraphicsitem.html#contextMenuEvent)（ ） 。

```
QGraphicsWebView.dragEnterEvent (self, QGraphicsSceneDragDropEvent)
```

从重新实现[QGraphicsItem.dragEnterEvent](qgraphicsitem.html#dragEnterEvent)（ ） 。

```
QGraphicsWebView.dragLeaveEvent (self, QGraphicsSceneDragDropEvent)
```

从重新实现[QGraphicsItem.dragLeaveEvent](qgraphicsitem.html#dragLeaveEvent)（ ） 。

```
QGraphicsWebView.dragMoveEvent (self, QGraphicsSceneDragDropEvent)
```

从重新实现[QGraphicsItem.dragMoveEvent](qgraphicsitem.html#dragMoveEvent)（ ） 。

```
QGraphicsWebView.dropEvent (self, QGraphicsSceneDragDropEvent)
```

从重新实现[QGraphicsItem.dropEvent](qgraphicsitem.html#dropEvent)（ ） 。

```
bool QGraphicsWebView.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
bool QGraphicsWebView.findText (self, QString subString, QWebPage.FindFlags options = 0)
```

查找指定的字符串，_subString_在该页面中，使用给定的_options_。

如果HighlightAllOccurrences标志传递，函数将突出存在于页面中的所有事件。所有后续调用将延长的亮点，而不是取代它，以出现新的字符串。

如果HighlightAllOccurrences标志不通过，该函数将选择的发生，所有后续调用将取代目前出现的下一个。

要清除选择，只传递一个空字符串。

返回True如果_subString_结果发现，否则返回False 。

**See also** [QWebPage.selectedText](qwebpage.html#selectedText-prop)（）和[QWebPage.selectionChanged](qwebpage.html#selectionChanged)（ ） 。

```
QGraphicsWebView.focusInEvent (self, QFocusEvent)
```

从重新实现[QGraphicsItem.focusInEvent](qgraphicsitem.html#focusInEvent)（ ） 。

```
bool QGraphicsWebView.focusNextPrevChild (self, bool next)
```

从重新实现[QGraphicsWidget.focusNextPrevChild](qgraphicswidget.html#focusNextPrevChild)（ ） 。

```
QGraphicsWebView.focusOutEvent (self, QFocusEvent)
```

从重新实现[QGraphicsItem.focusOutEvent](qgraphicsitem.html#focusOutEvent)（ ） 。

```
QGraphicsWebView.forward (self)
```

这种方法也是一个Qt槽与C + +的签名`void forward()`。

便利插槽，加载下一个文档中通过导航链接建立文件清单。什么都不做，如果没有下一个文件。

**See also** [back](qgraphicswebview.html#back)（ ） 。

```
QWebHistory QGraphicsWebView.history (self)
```

[

返回一个指针，指向的导航网页视图的历史。

它相当于

```
     view->page()->history();

```

```
QGraphicsWebView.hoverLeaveEvent (self, QGraphicsSceneHoverEvent)
```

](qwebhistory.html)

[从重新实现](qwebhistory.html)[QGraphicsItem.hoverLeaveEvent](qgraphicsitem.html#hoverLeaveEvent)（ ） 。

```
QGraphicsWebView.hoverMoveEvent (self, QGraphicsSceneHoverEvent)
```

从重新实现[QGraphicsItem.hoverMoveEvent](qgraphicsitem.html#hoverMoveEvent)（ ） 。

```
QIcon QGraphicsWebView.icon (self)
```

[

```
QGraphicsWebView.inputMethodEvent (self, QInputMethodEvent)
```

](qicon.html)

[从重新实现](qicon.html)[QGraphicsItem.inputMethodEvent](qgraphicsitem.html#inputMethodEvent)（ ） 。

```
QVariant QGraphicsWebView.inputMethodQuery (self, Qt.InputMethodQuery query)
```

从重新实现[QGraphicsItem.inputMethodQuery](qgraphicsitem.html#inputMethodQuery)（ ） 。

```
bool QGraphicsWebView.isModified (self)
```

```
bool QGraphicsWebView.isTiledBackingStoreFrozen (self)
```

```
QVariant QGraphicsWebView.itemChange (self, QGraphicsItem.GraphicsItemChange change, QVariant value)
```

从重新实现[QGraphicsItem.itemChange](qgraphicsitem.html#itemChange)（ ） 。

```
QGraphicsWebView.keyPressEvent (self, QKeyEvent)
```

从重新实现[QGraphicsItem.keyPressEvent](qgraphicsitem.html#keyPressEvent)（ ） 。

```
QGraphicsWebView.keyReleaseEvent (self, QKeyEvent)
```

从重新实现[QGraphicsItem.keyReleaseEvent](qgraphicsitem.html#keyReleaseEvent)（ ） 。

```
QGraphicsWebView.load (self, QUrl url)
```

指定的负载_url_并显示它。

**Note:**该视图保持不变，直到足够的数据已经到达，以显示新_url_。

**See also** [setUrl](qgraphicswebview.html#url-prop)（ ）[url](qgraphicswebview.html#url-prop)（）和[urlChanged](qgraphicswebview.html#urlChanged)（ ） 。

```
QGraphicsWebView.load (self, QNetworkRequest request, QNetworkAccessManager.Operation operation = QNetworkAccessManager.GetOperation, QByteArray body = QByteArray())
```

加载一个网络请求，_request_使用中规定的方法_operation_。

_body_是可选的，并且仅用于POST操作。

**Note:**该视图保持不变，直到足够的数据已经到达，以显示新的URL。

**See also** [url](qgraphicswebview.html#url-prop)（）和[urlChanged](qgraphicswebview.html#urlChanged)（ ） 。

```
QGraphicsWebView.mouseDoubleClickEvent (self, QGraphicsSceneMouseEvent)
```

从重新实现[QGraphicsItem.mouseDoubleClickEvent](qgraphicsitem.html#mouseDoubleClickEvent)（ ） 。

```
QGraphicsWebView.mouseMoveEvent (self, QGraphicsSceneMouseEvent)
```

从重新实现[QGraphicsItem.mouseMoveEvent](qgraphicsitem.html#mouseMoveEvent)（ ） 。

```
QGraphicsWebView.mousePressEvent (self, QGraphicsSceneMouseEvent)
```

从重新实现[QGraphicsItem.mousePressEvent](qgraphicsitem.html#mousePressEvent)（ ） 。

```
QGraphicsWebView.mouseReleaseEvent (self, QGraphicsSceneMouseEvent)
```

从重新实现[QGraphicsItem.mouseReleaseEvent](qgraphicsitem.html#mouseReleaseEvent)（ ） 。

```
QWebPage QGraphicsWebView.page (self)
```

[

返回一个指针，指向底层的网页。

](qwebpage.html)

[**See also**](qwebpage.html) [setPage](qgraphicswebview.html#setPage)（ ） 。

```
QAction QGraphicsWebView.pageAction (self, QWebPage.WebAction action)
```

[](qaction.html)

[返回一个指针，指向一个](qaction.html)[QAction](qaction.html)封装指定网络行动_action_。

```
QGraphicsWebView.paint (self, QPainter painter, QStyleOptionGraphicsItem option, QWidget widget = None)
```

从重新实现[QGraphicsItem.paint](qgraphicsitem.html#paint)（ ） 。

```
QGraphicsWebView.reload (self)
```

这种方法也是一个Qt槽与C + +的签名`void reload()`。

重新加载当前文档。

**See also** [stop](qgraphicswebview.html#stop)（）和[loadStarted](qgraphicswebview.html#loadStarted)（ ） 。

```
QPainter.RenderHints QGraphicsWebView.renderHints (self)
```

[

```
bool QGraphicsWebView.resizesToContents (self)
```

```
bool QGraphicsWebView.sceneEvent (self, QEvent)
```

](index.htm)

[从重新实现](index.htm)[QGraphicsItem.sceneEvent](qgraphicsitem.html#sceneEvent)（ ） 。

```
QGraphicsWebView.setContent (self, QByteArray data, QString mimeType = QString(), QUrl baseUrl = QUrl())
```

设置捲筒纸graphicsitem的内容以指定的内容_data_。如果_mimeType_参数为空它是目前假设内容是HTML，但在未来的版本中，我们可能会引入自动检测。

在内容引用的外部对象的位置相对_baseUrl_。

该_data_立即加载;外部对象异步加载。

**See also** [load](qgraphicswebview.html#load)（ ）[setHtml](qgraphicswebview.html#setHtml)（）和[QWebFrame.toHtml](qwebframe.html#toHtml)（ ） 。

```
QGraphicsWebView.setGeometry (self, QRectF rect)
```

从重新实现[QGraphicsLayoutItem.setGeometry](qgraphicslayoutitem.html#setGeometry)（ ） 。

```
QGraphicsWebView.setHtml (self, QString html, QUrl baseUrl = QUrl())
```

设置Web视图的内容的指定_html_。

外部对象，如样式表或HTML文档中引用的图片的位置相对于_baseUrl_。

该_html_立即加载;外部对象异步加载。

使用此方法时， WebKit的假定外部资源，例如JavaScript程序或样式表，除非另有规定被编码为UTF -8 。例如，外部脚本的编码可以通过HTML脚本标记的charset属性来指定。备选地，编码也可以由Web服务器指定。

这相当于一个方便的功能，使用setContent （ HTML ， “为text / html ” ， baseURL即可） 。

**Warning:**此功能仅用于HTML ，为其他MIME类型（即XHTML ， SVG ）[setContent](qgraphicswebview.html#setContent)（ ）应该使用。

**See also** [load](qgraphicswebview.html#load)（ ）[setContent](qgraphicswebview.html#setContent)（ ）[QWebFrame.toHtml](qwebframe.html#toHtml)（）和[QWebFrame.setContent](qwebframe.html#setContent)（ ） 。

```
QGraphicsWebView.setPage (self, QWebPage)
```

品牌_page_网页graphicsitem的新网页。

父[QObject](qobject.html)该页面提供的仍然是对象的所有者。如果当前文档是Web视图的孩子，它会被删除。

**See also** [page](qgraphicswebview.html#page)（ ） 。

```
QGraphicsWebView.setRenderHint (self, QPainter.RenderHint hint, bool enabled = True)
```

If _enabled_诚然，启用指定的渲染_hint_否则禁用它。

此功能被引入Qt的4.8 。

**See also** [renderHints](qgraphicswebview.html#renderHints-prop)和[QPainter.renderHints](qpainter.html#renderHints)（ ） 。

```
QGraphicsWebView.setRenderHints (self, QPainter.RenderHints hints)
```

```
QGraphicsWebView.setResizesToContents (self, bool enabled)
```

```
QGraphicsWebView.setTiledBackingStoreFrozen (self, bool frozen)
```

```
QWebSettings QGraphicsWebView.settings (self)
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
QGraphicsWebView.setUrl (self, QUrl)
```

```
QGraphicsWebView.setZoomFactor (self, float)
```

```
QSizeF QGraphicsWebView.sizeHint (self, Qt.SizeHint which, QSizeF constraint)
```

[](qsizef.html)

[从重新实现](qsizef.html)[QGraphicsLayoutItem.sizeHint](qgraphicslayoutitem.html#sizeHint)（ ） 。

```
QGraphicsWebView.stop (self)
```

这种方法也是一个Qt槽与C + +的签名`void stop()`。

便利插槽，停止加载该文件。

**See also** [reload](qgraphicswebview.html#reload)（）和[loadFinished](qgraphicswebview.html#loadFinished)（ ） 。

```
QString QGraphicsWebView.title (self)
```

```
QGraphicsWebView.triggerPageAction (self, QWebPage.WebAction action, bool checked = False)
```

触发指定的_action_。如果是指定了辨认的动作_checked_假定状态。

**See also** [pageAction](qgraphicswebview.html#pageAction)（ ） 。

```
QGraphicsWebView.updateGeometry (self)
```

从重新实现[QGraphicsLayoutItem.updateGeometry](qgraphicslayoutitem.html#updateGeometry)（ ） 。

```
QUrl QGraphicsWebView.url (self)
```

[

```
QGraphicsWebView.wheelEvent (self, QGraphicsSceneWheelEvent)
```

](qurl.html)

[从重新实现](qurl.html)[QGraphicsItem.wheelEvent](qgraphicsitem.html#wheelEvent)（ ） 。

```
float QGraphicsWebView.zoomFactor (self)
```

* * *

## Qt Signal Documentation

```
void iconChanged ()
```

这是该信号的默认超载。

这个信号时页面的图标被加载或改变被发射。

为了让图标加载，则需要使用设置一个图标数据库路径[QWebSettings.setIconDatabasePath](qwebsettings.html#setIconDatabasePath)（ ） 。

**See also** [icon](qgraphicswebview.html#icon-prop)（）和[QWebSettings.setIconDatabasePath](qwebsettings.html#setIconDatabasePath)（ ） 。

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

**See also** [loadStarted](qgraphicswebview.html#loadStarted)（ ） 。

```
void loadProgress (int)
```

这是该信号的默认超载。

每个网页中的元素完成加载和整体加载进度前进时，这个信号被发射。

这个信号可以跟踪所有子帧的进展。

电流值是由所提供_progress_和秤从0到100 ，这是默认范围[QProgressBar](qprogressbar.html)。

**See also** [loadStarted](qgraphicswebview.html#loadStarted)（）和[loadFinished](qgraphicswebview.html#loadFinished)（ ） 。

```
void loadStarted ()
```

这是该信号的默认超载。

当开始页面的新负载，这个信号被发射。

**See also** [loadProgress](qgraphicswebview.html#loadProgress)（）和[loadFinished](qgraphicswebview.html#loadFinished)（ ） 。

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

**See also** [title](qgraphicswebview.html#title-prop)（ ） 。

```
void urlChanged (const QUrl&)
```

这是该信号的默认超载。

这个信号被发射时的_url_的观点变化。

**See also** [url](qgraphicswebview.html#url-prop)（）和[load](qgraphicswebview.html#load)（ ） 。