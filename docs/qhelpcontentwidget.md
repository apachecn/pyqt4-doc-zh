# QHelpContentWidget Class Reference

## [[QtHelp](index.htm) module]

该QHelpContentWidget类提供了一个树视图，用于显示帮助内容模型项目。[More...](#details)

继承[QTreeView](qtreeview.html)。

### Methods

*   `QModelIndex indexOf (self, QUrl link)`

### Qt Signals

*   `void linkActivated (const QUrl&)`

* * *

## Detailed Description

该QHelpContentWidget类提供了一个树视图，用于显示帮助内容模型项目。

* * *

## Method Documentation

```
QModelIndex QHelpContentWidget.indexOf (self, QUrl link)
```

[

返回与该内容项的索引_link_。如果没有这样的项目存在一个无效的索引返回。

* * *

## Qt Signal Documentation

```
void linkActivated (const QUrl&)
```

这是该信号的默认超载。

这个信号被发射时的内容项被激活和其相关联的_link_应该显示。

](qmodelindex.html)