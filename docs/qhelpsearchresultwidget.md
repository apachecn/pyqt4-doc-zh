# QHelpSearchResultWidget Class Reference

## [[QtHelp](index.htm) module]

该QHelpSearchResultWidget类提供无论是树部件或根据所使用的搜索引擎来显示通过搜索找到了命中的文本浏览器。[More...](#details)

继承[QWidget](qwidget.html)。

### Methods

*   `QUrl linkAt (self, QPoint point)`

### Qt Signals

*   `void requestShowLink (const QUrl&)`

* * *

## Detailed Description

该QHelpSearchResultWidget类提供无论是树部件或根据所使用的搜索引擎来显示通过搜索找到了命中的文本浏览器。

* * *

## Method Documentation

```
QUrl QHelpSearchResultWidget.linkAt (self, QPoint point)
```

[

返回的URL ，该项目的参考在_point_拥有，或一个空的URL ，如果项目不存在，在这一点上。

* * *

## Qt Signal Documentation

```
void requestShowLink (const QUrl&)
```

这是该信号的默认超载。

当一个项目被激活和其相关联的这个信号被发射_link_应该显示。

](qurl.html)