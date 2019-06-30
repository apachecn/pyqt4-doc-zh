# QHelpIndexWidget Class Reference

## [[QtHelp](index.htm) module]

该QHelpIndexWidget类提供了一个列表视图显示[QHelpIndexModel](qhelpindexmodel.html)。[More...](#details)

继承[QListView](qlistview.html)。

### Methods

*   `activateCurrentItem (self)`
*   `filterIndices (self, QString filter, QString wildcard = QString())`

### Qt Signals

*   `void linkActivated (const QUrl&,const QString&)`
*   `void linksActivated (const QMap&lt;QString,QUrl&gt;&,const QString&)`

* * *

## Detailed Description

该QHelpIndexWidget类提供了一个列表视图显示[QHelpIndexModel](qhelpindexmodel.html)。

* * *

## Method Documentation

```
QHelpIndexWidget.activateCurrentItem (self)
```

这种方法也是一个Qt槽与C + +的签名`void activateCurrentItem()`。

激活当前的项目，这将导致在最终的发光[linkActivated](qhelpindexwidget.html#linkActivated)（）或[linksActivated](qhelpindexwidget.html#linksActivated)（）信号。

```
QHelpIndexWidget.filterIndices (self, QString filter, QString wildcard = QString())
```

这种方法也是一个Qt槽与C + +的签名`void filterIndices(const QString&,const QString& = QString())`。

根据筛选的指标_filter_ or _wildcard_。与最佳匹配的项目设置为当前项目。

**See also** [QHelpIndexModel.filter](qhelpindexmodel.html#filter)（ ） 。

* * *

## Qt Signal Documentation

```
void linkActivated (const QUrl&,const QString&)
```

这是该信号的默认超载。

当一个项目被激活，并且其相关联的这个信号被发射_link_应该显示。知道在哪里的链接属于中，_keyword_被给定为一个第二paremeter 。

```
void linksActivated (const QMap<QString,QUrl>&,const QString&)
```

这是该信号的默认超载。

当项目表示该信号被发射的_keyword_被激活，且该项目具有多个相关联的链路。该_links_包括文档标题和网址。