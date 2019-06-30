# QWebFrame Class Reference

## [[QtWebKit](index.htm) module]

该QWebFrame类表示一个web页面的框架。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum RenderLayer { ContentsLayer, ScrollBarLayer, PanIconLayer, AllLayers }`

### Methods

*   `addToJavaScriptWindowObject (self, QString name, QObject object)`
*   `QUrl baseUrl (self)`
*   `list-of-QWebFrame childFrames (self)`
*   `QSize contentsSize (self)`
*   `QWebElement documentElement (self)`
*   `QVariant evaluateJavaScript (self, QString scriptSource)`
*   `bool event (self, QEvent)`
*   `QWebElementCollection findAllElements (self, QString selectorQuery)`
*   `QWebElement findFirstElement (self, QString selectorQuery)`
*   `QString frameName (self)`
*   `QRect geometry (self)`
*   `bool hasFocus (self)`
*   `QWebHitTestResult hitTestContent (self, QPoint pos)`
*   `QIcon icon (self)`
*   `load (self, QUrl url)`
*   `load (self, QNetworkRequest request, QNetworkAccessManager.Operation operation = QNetworkAccessManager.GetOperation, QByteArray body = QByteArray())`
*   `dict-of-QString-list-of-QString metaData (self)`
*   `QWebPage page (self)`
*   `QWebFrame parentFrame (self)`
*   `QPoint pos (self)`
*   `print (self, QPrinter printer)`
*   `print_ (self, QPrinter printer)`
*   `render (self, QPainter painter, QRegion clip)`
*   `render (self, QPainter painter)`
*   `render (self, QPainter, RenderLayer layer, QRegion clip = QRegion())`
*   `QString renderTreeDump (self)`
*   `QUrl requestedUrl (self)`
*   `scroll (self, int, int)`
*   `QRect scrollBarGeometry (self, Qt.Orientation orientation)`
*   `int scrollBarMaximum (self, Qt.Orientation orientation)`
*   `int scrollBarMinimum (self, Qt.Orientation orientation)`
*   `Qt.ScrollBarPolicy scrollBarPolicy (self, Qt.Orientation orientation)`
*   `int scrollBarValue (self, Qt.Orientation orientation)`
*   `QPoint scrollPosition (self)`
*   `scrollToAnchor (self, QString anchor)`
*   `QWebSecurityOrigin securityOrigin (self)`
*   `setContent (self, QByteArray data, QString mimeType = QString(), QUrl baseUrl = QUrl())`
*   `setFocus (self)`
*   `setHtml (self, QString html, QUrl baseUrl = QUrl())`
*   `setScrollBarPolicy (self, Qt.Orientation orientation, Qt.ScrollBarPolicy policy)`
*   `setScrollBarValue (self, Qt.Orientation orientation, int value)`
*   `setScrollPosition (self, QPoint pos)`
*   `setTextSizeMultiplier (self, float factor)`
*   `setUrl (self, QUrl url)`
*   `setZoomFactor (self, float factor)`
*   `float textSizeMultiplier (self)`
*   `QString title (self)`
*   `QString toHtml (self)`
*   `QString toPlainText (self)`
*   `QUrl url (self)`
*   `float zoomFactor (self)`

### Qt Signals

*   `void contentsSizeChanged (const QSize&)`
*   `void iconChanged ()`
*   `void initialLayoutCompleted ()`
*   `void javaScriptWindowObjectCleared ()`
*   `void loadFinished (bool)`
*   `void loadStarted ()`
*   `void pageChanged ()`
*   `void titleChanged (const QString&)`
*   `void urlChanged (const QUrl&)`

* * *

## Detailed Description

该QWebFrame类表示一个web页面的框架。

QWebFrame表示内部网页中的帧。每[QWebPage](qwebpage.html)对象中包含的至少一个帧，在主框架，得到用[QWebPage.mainFrame](qwebpage.html#mainFrame)（ ） 。额外的帧将用于HTML创建`&lt;frame&gt;` or `&lt;iframe&gt;`元素。

一个框架可以使用被加载[load](qwebframe.html#load)（）或[setUrl](qwebframe.html#url-prop)（ ） 。另外，如果你有HTML内容一应俱全，您可以使用[setHtml](qwebframe.html#setHtml)（ ）来代替。

该[page](qwebframe.html#page)（ ）函数返回一个指向该网页的对象。看[Elements of QWebView](qwebview.html)对于如何肋骨都涉及到一个网页和Web视图的解释。

该QWebFrame类还提供了方法来检索现时由框架加载的URL（请参阅[url](qwebframe.html#url-prop)（））以及最初请求要加载的URL（见[requestedUrl](qwebframe.html#requestedUrl-prop)（））。这些方法使得有可能在URL之前和之后的DNS解析或重定向检索在加载过程中发生。该[requestedUrl](qwebframe.html#requestedUrl-prop)（）也匹配到添加到帧历史的URL（[QWebHistory](qwebhistory.html)） ，如果加载成功。

一个HTML帧的标题可以通过访问[title](qwebframe.html#title-prop)（）属性。此外，一个帧也可以利用指定一个图标，它可被访问的[icon](qwebframe.html#icon-prop)（）属性。如果标题或图标的变化，相应的[titleChanged](qwebframe.html#titleChanged)（）和[iconChanged](qwebframe.html#iconChanged)（）信号将被发射。该[zoomFactor](qwebframe.html#zoomFactor-prop)（）属性可以被用来改变在帧中显示的内容的总体尺寸。

由网页创建和控制QWebFrame对象。您可以连接到该网页的[frameCreated()](qwebpage.html#frameCreated)信号创建一个新的框架时得到通知。

有多种方法以编程方式检查一个帧的内容。该[hitTestContent](qwebframe.html#hitTestContent)（）函数可以被用来找到由坐标元素。用于访问底层DOM树，有[documentElement](qwebframe.html#documentElement)（ ）[findAllElements](qwebframe.html#findAllElements)（）和[findFirstElement](qwebframe.html#findFirstElement)（ ） 。

一个QWebFrame可以打印到[QPrinter](qprinter.html)使用[print_](qwebframe.html#print)（）函数。这个功能被标记为一个时隙，并且可以方便地连接到[QPrintPreviewDialog](qprintpreviewdialog.html)的[paintRequested()](qprintpreviewdialog.html#paintRequested)信号。

* * *

## Type Documentation

```
QWebFrame.RenderLayer
```

这个枚举说明适用于使用渲染层[render()](qwebframe.html#render)。该层可以是或的结果一起从下面的列表：

| Constant | Value | Description |
| --- | --- | --- |
| `QWebFrame.ContentsLayer` | `0x10` | 框架的网页内容 |
| `QWebFrame.ScrollBarLayer` | `0x20` | 框架的滚动条 |
| `QWebFrame.PanIconLayer` | `0x40` | 平移框架时使用的图标 |
| `QWebFrame.AllLayers` | `0xff` | 包括上述所有层 |

* * *

## Method Documentation

```
QWebFrame.addToJavaScriptWindowObject (self, QString name, QObject object)
```

使_object_可下_name_从框架的JavaScript的范围内。该_object_将插入作为框架的window对象的子对象。

Qt的属性将被暴露成JavaScript的性能和插槽的JavaScript方法。 C + +和JavaScript之间的交互的文档中解释[QtWebKit bridge](index.htm)。

如果你想确保你的[QObjects](index.htm#qobjects)仍可以访问加载一个新的URL之后，您应该将它们添加在连接到一个槽[javaScriptWindowObjectCleared](qwebframe.html#javaScriptWindowObjectCleared)（）信号。

如果未启用此页面的Javascript ，则此方法不执行任何操作。

该_object_永远不会被显式删除[QtWebKit](index.htm)。

```
QUrl QWebFrame.baseUrl (self)
```

[

```
list-of-QWebFrame QWebFrame.childFrames (self)
```

返回是这个框架的直接子所有帧的列表。

](qurl.html)

[**See also**](qurl.html) [parentFrame](qwebframe.html#parentFrame)（ ） 。

```
QSize QWebFrame.contentsSize (self)
```

[](qsize.html)

```
QWebElement QWebFrame.documentElement (self)
```

[

返回该框架的文档元素。

文档元素可以访问该帧的整个结构化内容。

此功能被引入Qt的4.6 。

```
QVariant QWebFrame.evaluateJavaScript (self, QString scriptSource)
```

这种方法也是一个Qt槽与C + +的签名`QVariant evaluateJavaScript(const QString&)`。

评估的JavaScript定义为_scriptSource_使用这个框架作为背景，并返回最后执行的语句的结果。

](qwebelement.html)

[**See also**](qwebelement.html) [addToJavaScriptWindowObject](qwebframe.html#addToJavaScriptWindowObject)（）和[javaScriptWindowObjectCleared](qwebframe.html#javaScriptWindowObjectCleared)（ ） 。

```
bool QWebFrame.event (self, QEvent)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QWebElementCollection QWebFrame.findAllElements (self, QString selectorQuery)
```

[

返回元素匹配给定的CSS选择一个新的列表_selectorQuery_。如果没有匹配的元素，则返回一个空列表。

](qwebelementcollection.html)

[](qwebelementcollection.html)[Standard CSS2 selector](http://www.w3.org/TR/REC-CSS2/selector.html#q1)语法用于查询。

此功能被引入Qt的4.6 。

**See also** [QWebElement.findAll](qwebelement.html#findAll)（ ） 。

```
QWebElement QWebFrame.findFirstElement (self, QString selectorQuery)
```

[

返回匹配给定的CSS选择器框架的文档中的第一个元素_selectorQuery_。如果没有匹配的元素，则返回一个空元素。

](qwebelement.html)

[](qwebelement.html)[Standard CSS2 selector](http://www.w3.org/TR/REC-CSS2/selector.html#q1)语法用于查询。

此功能被引入Qt的4.6 。

**See also** [QWebElement.findFirst](qwebelement.html#findFirst)（ ） 。

```
QString QWebFrame.frameName (self)
```

这个帧的父帧所定义的名称。

```
QRect QWebFrame.geometry (self)
```

[

返回帧相对的几何形状给它的父框架。

```
bool QWebFrame.hasFocus (self)
```

](qrect.html)

```
QWebHitTestResult QWebFrame.hitTestContent (self, QPoint pos)
```

[

执行在给定位置上的帧内容的命中测试_pos_并返回命中测试结果。

](qwebhittestresult.html)

```
QIcon QWebFrame.icon (self)
```

[

```
QWebFrame.load (self, QUrl url)
```

负载_url_这个框架。

**Note:**该视图保持不变，直到足够的数据已经到达，以显示新_url_。

](qicon.html)

[**See also**](qicon.html) [setUrl](qwebframe.html#url-prop)（ ）[setHtml](qwebframe.html#setHtml)（）和[setContent](qwebframe.html#setContent)（ ） 。

```
QWebFrame.load (self, QNetworkRequest request, QNetworkAccessManager.Operation operation = QNetworkAccessManager.GetOperation, QByteArray body = QByteArray())
```

加载一个网络请求，_req_，到这个帧时，使用指定的方法_operation_。

_body_是可选的，并且仅用于POST操作。

**Note:**该视图保持不变，直到足够的数据已经到达，以显示新的内容。

**See also** [setUrl](qwebframe.html#url-prop)（ ） 。

```
dict-of-QString-list-of-QString QWebFrame.metaData (self)
```

返回此框架的元数据作为[QMultiMap](index.htm)

所述元数据包含的的名称和内容属性的`&lt;meta&gt;`标籤在HTML文档中。

例如：

```
 <html>
     <head>
         <meta name="description" content="This document is a tutorial about Qt development">
         <meta name="keywords" content="Qt, WebKit, Programming">
     </head>
     ...
 </html>

```

鑑于上面的HTML代码中的元数据（ ）函数将返回两个条目的地图：

| Key | Value |
| --- | --- |
| "description" | "This document is a tutorial about Qt development" |
| "keywords" | "Qt, WebKit, Programming" |

这个函数返回一个多地图，支持多种meta标籤具有相同属性的名称。

此功能被引入Qt的4.5 。

```
QWebPage QWebFrame.page (self)
```

[

该网页包含这个框架。

](qwebpage.html)

[**See also**](qwebpage.html) [pageChanged](qwebframe.html#pageChanged)（ ） 。

```
QWebFrame QWebFrame.parentFrame (self)
```

[

返回该框架的父框架，或者0，如果该帧是网页主要框架。

](qwebframe.html)

[这相当于qobject_cast \u003c](qwebframe.html)[QWebFrame](qwebframe.html)* \u003e （帧\u003e[parent](qobject.html#parent)（））。

**See also** [childFrames](qwebframe.html#childFrames)（ ） 。

```
QPoint QWebFrame.pos (self)
```

[

返回帧相对的位置，它的父框架。

```
QWebFrame.print (self, QPrinter printer)
```

这种方法也是一个Qt槽与C + +的签名`void print(QPrinter *) const`。

打印该帧为给定的_printer_。

](qpoint.html)

[**See also**](qpoint.html) [render](qwebframe.html#render)（ ） 。

```
QWebFrame.print_ (self, QPrinter printer)
```

这种方法也是一个Qt槽与C + +的签名`void print(QPrinter *) const`。

打印该帧为给定的_printer_。

**See also** [render](qwebframe.html#render)（ ） 。

```
QWebFrame.render (self, QPainter painter, QRegion clip)
```

帧渲染成_painter_。

```
QWebFrame.render (self, QPainter painter)
```

帧渲染成_painter_削波_clip_。

```
QWebFrame.render (self, QPainter, RenderLayer layer, QRegion clip = QRegion())
```

渲染_layer_使用帧的_painter_削波_clip_。

此功能被引入Qt的4.6 。

**See also** [print_](qwebframe.html#print)（ ） 。

```
QString QWebFrame.renderTreeDump (self)
```

返回渲染树的转储。这主要是用于调试HTML有用。

```
QUrl QWebFrame.requestedUrl (self)
```

[

```
QWebFrame.scroll (self, int, int)
```

滚动框_dx_像素向右和_dy_向下像素。两_dx_和_dy_可能是负的。

此功能被引入Qt的4.5 。

](qurl.html)

[**See also**](qurl.html) [QWebFrame.scrollPosition](qwebframe.html#scrollPosition-prop)。

```
QRect QWebFrame.scrollBarGeometry (self, Qt.Orientation orientation)
```

[

返回与方向滚动条的几何形状_orientation_。

如果滚动条不存在的空矩形被返回。

此功能被引入Qt的4.6 。

```
int QWebFrame.scrollBarMaximum (self, Qt.Orientation orientation)
```

返回最大值与方向的滚动条_orientation_，或者0，如果没有滚动条找到的_orientation_。

](qrect.html)

[**See also**](qrect.html) [scrollBarMinimum](qwebframe.html#scrollBarMinimum)（ ） 。

```
int QWebFrame.scrollBarMinimum (self, Qt.Orientation orientation)
```

返回最小值与方向的滚动条_orientation_。

最低值始终为0。

**See also** [scrollBarMaximum](qwebframe.html#scrollBarMaximum)（ ） 。

```
Qt.ScrollBarPolicy QWebFrame.scrollBarPolicy (self, Qt.Orientation orientation)
```

[

返回由定义的滚动条的滚动条政策_orientation_。

](qt.html#ScrollBarPolicy-enum)

[**See also**](qt.html#ScrollBarPolicy-enum) [setScrollBarPolicy](qwebframe.html#setScrollBarPolicy)（ ） 。

```
int QWebFrame.scrollBarValue (self, Qt.Orientation orientation)
```

返回当前值与方向的滚动条_orientation_，或者0，如果没有滚动条找到的_orientation_。

**See also** [setScrollBarValue](qwebframe.html#setScrollBarValue)（ ）[scrollBarMinimum](qwebframe.html#scrollBarMinimum)（）和[scrollBarMaximum](qwebframe.html#scrollBarMaximum)（ ） 。

```
QPoint QWebFrame.scrollPosition (self)
```

[

```
QWebFrame.scrollToAnchor (self, QString anchor)
```

帧滚动到给定_anchor_名称。

此功能被引入Qt的4.7 。

](qpoint.html)

```
QWebSecurityOrigin QWebFrame.securityOrigin (self)
```

[

返回框架的安全性起源。

此功能被引入Qt的4.5 。

```
QWebFrame.setContent (self, QByteArray data, QString mimeType = QString(), QUrl baseUrl = QUrl())
```

设置该帧的内容来指定的内容_data_。如果_mimeType_参数为空它是目前假设内容是HTML，但在未来的版本中，我们可能会引入自动检测。

在内容引用的外部对象的位置相对_baseUrl_。

该_data_立即加载;外部对象异步加载。

**Note:**这种方法不会影响会话或世界历史的框架。

](qwebsecurityorigin.html)

[**See also**](qwebsecurityorigin.html) [toHtml](qwebframe.html#toHtml)（）和[setHtml](qwebframe.html#setHtml)（ ） 。

```
QWebFrame.setFocus (self)
```

使键盘输入焦点到这个框架。

此功能被引入Qt的4.6 。

**See also** [hasFocus](qwebframe.html#focus-prop)（ ） 。

```
QWebFrame.setHtml (self, QString html, QUrl baseUrl = QUrl())
```

设置此帧的内容来_html_。_baseUrl_是可选的，用来解析文档中的相对URL ，如引用的图片或样式表。

该_html_立即加载;外部对象异步加载。

如果在一个脚本_html_由于被封锁的模态JavaScript警告对话框的运行时间比默认的脚本超时（目前为10秒） ，例如，此方法将超时和任何后续后尽快返回_html_将异步加载。

当使用这种方法的WebKit假定外部资源，例如JavaScript程序或样式表，除非另有规定被编码为UTF -8 。例如，外部脚本的编码可以通过HTML脚本标记的charset属性来指定。另外，也可以对由Web服务器被指定的编码。

这相当于一个方便的功能，使用setContent （ HTML ， “为text / html ” ，[baseUrl](qwebframe.html#baseUrl-prop)） 。

**Note:**这种方法不会影响会话或世界历史的框架。

**Warning:**此功能仅用于HTML ，为其他MIME类型（即XHTML ， SVG ）[setContent](qwebframe.html#setContent)（ ）应该使用。

**See also** [toHtml](qwebframe.html#toHtml)（ ）[setContent](qwebframe.html#setContent)（）和[load](qwebframe.html#load)（ ） 。

```
QWebFrame.setScrollBarPolicy (self, Qt.Orientation orientation, Qt.ScrollBarPolicy policy)
```

设置为定义的滚动条的滚动条政策_orientation_至_policy_。

**See also** [scrollBarPolicy](qwebframe.html#scrollBarPolicy)（ ） 。

```
QWebFrame.setScrollBarValue (self, Qt.Orientation orientation, int value)
```

设置当前_value_与方向滚动条_orientation_。

滚动条强制_value_要在法律的范围内：最小值\u003c =值\u003c =最大值。

更改该值也会更新拇指的位置。

**See also** [scrollBarValue](qwebframe.html#scrollBarValue)（ ）[scrollBarMinimum](qwebframe.html#scrollBarMinimum)（）和[scrollBarMaximum](qwebframe.html#scrollBarMaximum)（ ） 。

```
QWebFrame.setScrollPosition (self, QPoint pos)
```

```
QWebFrame.setTextSizeMultiplier (self, float factor)
```

设置用于扩展在Web框架的文本乘数的值_factor_规定。

**See also** [textSizeMultiplier](qwebframe.html#textSizeMultiplier)（ ） 。

```
QWebFrame.setUrl (self, QUrl url)
```

```
QWebFrame.setZoomFactor (self, float factor)
```

```
float QWebFrame.textSizeMultiplier (self)
```

返回用于扩展在Web框架中的文字乘数的值。

**See also** [setTextSizeMultiplier](qwebframe.html#setTextSizeMultiplier)（ ） 。

```
QString QWebFrame.title (self)
```

```
QString QWebFrame.toHtml (self)
```

返回框架的内容为HTML ，包含在HTML和BODY标记。

**See also** [setHtml](qwebframe.html#setHtml)（）和[toPlainText](qwebframe.html#toPlainText)（ ） 。

```
QString QWebFrame.toPlainText (self)
```

返回该框架的内容转换为纯文本，完全剥夺了所有的HTML格式的。

**See also** [toHtml](qwebframe.html#toHtml)（ ） 。

```
QUrl QWebFrame.url (self)
```

[

```
float QWebFrame.zoomFactor (self)
```

* * *

## Qt Signal Documentation

```
void contentsSizeChanged (const QSize&)
```

这是该信号的默认超载。

这个信号被发射时，帧的内容大小变化_size_。

此功能被引入Qt的4.6 。

](qurl.html)

[**See also**](qurl.html) [contentsSize](qwebframe.html#contentsSize-prop)（ ） 。

```
void iconChanged ()
```

这是该信号的默认超载。

这个信号时的图标（ “的favicon ” ）与该帧相关联的已加载射出。

**See also** [icon](qwebframe.html#icon-prop)（ ） 。

```
void initialLayoutCompleted ()
```

这是该信号的默认超载。

当帧被在第一时间布局这个信号被发射。这是第一次，你会看到画面上显示的内容。

**Note:**一个框架可以进行布局多次。

```
void javaScriptWindowObjectCleared ()
```

这是该信号的默认超载。

这个信号被发射时的JavaScript环境的全局的window对象被清除，例如，开始一个新的前负荷。

如果您打算添加[QObjects](index.htm#qobjects)到[QWebFrame](qwebframe.html) using [addToJavaScriptWindowObject](qwebframe.html#addToJavaScriptWindowObject)（ ），你应该将它们添加在连接到该信号的槽。这将确保你的对象加载新的URL时，仍然可以访问。

```
void loadFinished (bool)
```

这是该信号的默认超载。

当该帧的负载被完成这个信号被发射。_ok_将指示负载是否成功，或发生任何错误。

此功能被引入Qt的4.6 。

**See also** [loadStarted](qwebframe.html#loadStarted)（ ） 。

```
void loadStarted ()
```

这是该信号的默认超载。

当开始该帧的一个新的负载，这个信号被发射。

此功能被引入Qt的4.6 。

**See also** [loadFinished](qwebframe.html#loadFinished)（ ） 。

```
void pageChanged ()
```

这是该信号的默认超载。

当此帧已被移动到一个不同的这个信号被发射[QWebPage](qwebpage.html)。

此功能被引入Qt的4.7 。

**See also** [page](qwebframe.html#page)（ ） 。

```
void titleChanged (const QString&)
```

这是该信号的默认超载。

这个信号被发射时的帧变化的称号。该_title_字符串指定新的标题。

**See also** [title](qwebframe.html#title-prop)（ ） 。

```
void urlChanged (const QUrl&)
```

这是该信号的默认超载。

这个信号被发射与接收到帧的标题时，帧的URL 。新的URL被指定_url_。

**See also** [url](qwebframe.html#url-prop)（ ） 。