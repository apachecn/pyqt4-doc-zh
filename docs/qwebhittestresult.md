# QWebHitTestResult Class Reference

## [[QtWebKit](index.htm) module]

该QWebHitTestResult类提供有关碰撞测试后的网页内容信息。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QWebHitTestResult other)`
*   `QString alternateText (self)`
*   `QRect boundingRect (self)`
*   `QWebElement element (self)`
*   `QWebElement enclosingBlockElement (self)`
*   `QWebFrame frame (self)`
*   `QUrl imageUrl (self)`
*   `bool isContentEditable (self)`
*   `bool isContentSelected (self)`
*   `bool isNull (self)`
*   `QWebElement linkElement (self)`
*   `QWebFrame linkTargetFrame (self)`
*   `QString linkText (self)`
*   `QUrl linkTitle (self)`
*   `QUrl linkUrl (self)`
*   `QPixmap pixmap (self)`
*   `QPoint pos (self)`
*   `QString title (self)`

* * *

## Detailed Description

该QWebHitTestResult类提供有关碰撞测试后的网页内容信息。

QWebHitTestResult被退回[QWebFrame.hitTestContent](qwebframe.html#hitTestContent)（）提供有关网页的指定位置处的内容的信息。

* * *

## Method Documentation

```
QWebHitTestResult.__init__ (self)
```

构造一个空的命中测试结果。

```
QWebHitTestResult.__init__ (self, QWebHitTestResult other)
```

构造一个命中测试结果从_other_。

```
QString QWebHitTestResult.alternateText (self)
```

返回元素的替代文本。这对应于HTML alt属性。

```
QRect QWebHitTestResult.boundingRect (self)
```

[

返回元素的边界矩形。

此功能被引入Qt的4.5 。

](qrect.html)

```
QWebElement QWebHitTestResult.element (self)
```

[](qwebelement.html)

[返回底层的DOM元素作为](qwebelement.html)[QWebElement](qwebelement.html)。

此功能被引入Qt的4.6 。

```
QWebElement QWebHitTestResult.enclosingBlockElement (self)
```

[

返回一个封装元素撞块元素。

块元素是使用CSS的“块”的风格呈现的元素。这包括例如文本段落。

此功能被引入Qt的4.6 。

](qwebelement.html)

```
QWebFrame QWebHitTestResult.frame (self)
```

[

返回命中测试被执行英寸机架

](qwebframe.html)

```
QUrl QWebHitTestResult.imageUrl (self)
```

[

返回的图像的URL 。

```
bool QWebHitTestResult.isContentEditable (self)
```

返回True如果内容是由用户编辑的，否则返回False 。

```
bool QWebHitTestResult.isContentSelected (self)
```

返回True如果测试的内容是选择的一部分，否则返回False 。

```
bool QWebHitTestResult.isNull (self)
```

返回True如果命中测试结果为空，否则返回False 。

](qurl.html)

```
QWebElement QWebHitTestResult.linkElement (self)
```

[

返回表示链接的元素。

此功能被引入Qt的4.6 。

](qwebelement.html)

[**See also**](qwebelement.html) [linkTargetFrame](qwebhittestresult.html#linkTargetFrame)（ ） 。

```
QWebFrame QWebHitTestResult.linkTargetFrame (self)
```

[

返回将载入该链接，如果它被激活的框架。

](qwebframe.html)

[**See also**](qwebframe.html) [linkElement](qwebhittestresult.html#linkElement)（ ） 。

```
QString QWebHitTestResult.linkText (self)
```

返回链接的文本。

```
QUrl QWebHitTestResult.linkTitle (self)
```

[

返回链接的标题。

](qurl.html)

```
QUrl QWebHitTestResult.linkUrl (self)
```

[

返回的URL，即链接指向。

](qurl.html)

```
QPixmap QWebHitTestResult.pixmap (self)
```

[](qpixmap.html)

[返回](qpixmap.html)[QPixmap](qpixmap.html)包含图像。如果被测试的元素是不是一个图像空像素映射返回。

```
QPoint QWebHitTestResult.pos (self)
```

[

返回在点击测试发生的位置。

```
QString QWebHitTestResult.title (self)
```

返回最近的封闭的HTML元素的标题。

](qpoint.html)