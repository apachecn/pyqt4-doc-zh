# QHelpIndexModel Class Reference

## [[QtHelp](index.htm) module]

该QHelpIndexModel类提供了一个模型，它提供的索引关键字的看法。[More...](#details)

继承[QStringListModel](qstringlistmodel.html)。

### Methods

*   `createIndex (self, QString customFilterName)`
*   `QModelIndex filter (self, QString filter, QString wildcard = QString())`
*   `bool isCreatingIndex (self)`
*   `dict-of-QString-QUrl linksForKeyword (self, QString keyword)`

### Qt Signals

*   `void indexCreated ()`
*   `void indexCreationStarted ()`

* * *

## Detailed Description

该QHelpIndexModel类提供了一个模型，它提供的索引关键字的看法。

* * *

## Method Documentation

```
QHelpIndexModel.createIndex (self, QString customFilterName)
```

通过查询帮助系统关键字指定创建一个新的索引_customFilterName_。

```
QModelIndex QHelpIndexModel.filter (self, QString filter, QString wildcard = QString())
```

[

筛选指标，并返回最匹配的关键字的模型索引。在第一步骤中，仅包含关键字_filter_保持模型的索引列表中。类似地，如果_wildcard_不为空，只有匹配的关键字留在索引列表中。在第二个步骤中，确定最佳匹配，其指数模型返回。当指定一个通配符表达式，_filter_字符串用来搜索最佳匹配。

```
bool QHelpIndexModel.isCreatingIndex (self)
```

如果该指数目前建立起来，否则为False ，则返回True 。

```
dict-of-QString-QUrl QHelpIndexModel.linksForKeyword (self, QString keyword)
```

返回找到的所有点击_keyword_。一击中的包括URL和文档标题。

* * *

## Qt Signal Documentation

```
void indexCreated ()
```

这是该信号的默认超载。

该指数已创建时，这个信号被发射。

```
void indexCreationStarted ()
```

这是该信号的默认超载。

](qmodelindex.html)

[当创建一个新的索引已经开始这个信号被发射。当前索引是无效的，从此刻起，直到信号](qmodelindex.html)[indexCreated](qhelpindexmodel.html#indexCreated)（）被发射。

**See also** [isCreatingIndex](qhelpindexmodel.html#isCreatingIndex)（ ） 。