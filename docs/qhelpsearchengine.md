# QHelpSearchEngine Class Reference

## [[QtHelp](index.htm) module]

该QHelpSearchEngine类提供​​可重复使用的部件来集成全文搜索，以及索引和搜索文档。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QHelpEngineCore helpEngine, QObject parent = None)`
*   `cancelIndexing (self)`
*   `cancelSearching (self)`
*   `int hitCount (self)`
*   `list-of-tuple-of-QString-QString hits (self, int start, int end)`
*   `int hitsCount (self)`
*   `list-of-QHelpSearchQuery query (self)`
*   `QHelpSearchQueryWidget queryWidget (self)`
*   `reindexDocumentation (self)`
*   `QHelpSearchResultWidget resultWidget (self)`
*   `search (self, list-of-QHelpSearchQuery queryList)`

### Qt Signals

*   `void indexingFinished ()`
*   `void indexingStarted ()`
*   `void searchingFinished (int)`
*   `void searchingStarted ()`

* * *

## Detailed Description

该QHelpSearchEngine类提供​​可重复使用的部件来集成全文搜索，以及索引和搜索文档。

之前的搜索引擎，可以使用1具有实例化至少一个[QHelpEngineCore](qhelpenginecore.html)对象需要被传递给搜索引擎的构造。这是必需的作为搜索引擎需要连接到setupFinished帮助引擎（）信号知道它何时可以开始索引文件。

起始索引过程的信号后[indexingStarted](qhelpsearchengine.html#indexingStarted)（）被发射和在索引过程结束时[indexingFinished](qhelpsearchengine.html#indexingFinished)（）被发射。要停止索引可以调用[cancelIndexing](qhelpsearchengine.html#cancelIndexing)（ ） 。

而索引过程完成后，搜索引擎现在可以用来进行搜索直通其索引为一个给定的术语。要做到这一点人们可以使用创建的可能性[QHelpSearchQuery](qhelpsearchquery.html)通过自我列出或重用[QHelpSearchQueryWidget](qhelpsearchquerywidget.html)它具有inbuild功能设置的得到传递给搜索引擎一个适当的搜索查询列表[search](qhelpsearchengine.html#search)（）函数。

经过查询列表中已经传递给搜索引擎，信号[searchingStarted](qhelpsearchengine.html#searchingStarted)（）被发射，并在搜索完成后[searchingFinished](qhelpsearchengine.html#searchingFinished)（）信号被发射。搜索过程可以通过调用停止[cancelSearching](qhelpsearchengine.html#cancelSearching)（ ） 。

如果搜索成功，则[searchingFinished](qhelpsearchengine.html#searchingFinished)（ ）将被调用的搜索命中计数，可重复使用来获取搜索点击来自搜索引擎。调用[hits](qhelpsearchengine.html#hits)点击与您希望得到的range（）函数将返回请求SearchHits列表。他们基本上constist在对字符串如该对的值是文档文件的路径和页面标题的那一刻。

要显示给定的命中使用[QHelpSearchResultWidget](qhelpsearchresultwidget.html)或者如果您需要更高级的功能，建立自己的之一。注意，这个[QHelpSearchResultWidget](qhelpsearchresultwidget.html)不能直接实例化，必须从搜索引擎检索的部件在使用中的所有连接将被小部件本身建立适合你。

* * *

## Method Documentation

```
QHelpSearchEngine.__init__ (self, QHelpEngineCore helpEngine, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的搜索引擎与给定_parent_。该搜索引擎使用给定的_helpEngine_访问需要被索引的文档。该[QHelpEngine](qhelpengine.html)的setupFinished （ ）信号被自动连接到[QHelpSearchEngine](qhelpsearchengine.html)的索引函数，从而使信号被发射之后，新的文件将被编入索引。

```
QHelpSearchEngine.cancelIndexing (self)
```

这种方法也是一个Qt槽与C + +的签名`void cancelIndexing()`。

停止索引过程。

```
QHelpSearchEngine.cancelSearching (self)
```

这种方法也是一个Qt槽与C + +的签名`void cancelSearching()`。

停止搜索过程。

```
int QHelpSearchEngine.hitCount (self)
```

返回的搜索引擎找到的点击量。

此功能被引入Qt的4.6 。

```
list-of-tuple-of-QString-QString QHelpSearchEngine.hits (self, int start, int end)
```

返回范围内的搜索命中列表_start_ _end_。

```
int QHelpSearchEngine.hitsCount (self)
```

```
list-of-QHelpSearchQuery QHelpSearchEngine.query (self)
```

返回查询列表中最后一个被搜索的。

此功能被引入Qt的4.5 。

```
QHelpSearchQueryWidget QHelpSearchEngine.queryWidget (self)
```

[

返回一个widget作为输入部件使用。根据您的搜索引擎的配置，你会得到一个不同的小部件或多或少subwidgets 。

```
QHelpSearchEngine.reindexDocumentation (self)
```

这种方法也是一个Qt槽与C + +的签名`void reindexDocumentation()`。

迫使搜索引擎重新索引所有的文档文件。

](qhelpsearchquerywidget.html)

```
QHelpSearchResultWidget QHelpSearchEngine.resultWidget (self)
```

[

返回一个小工具，可以容纳并显示搜索结果。

```
QHelpSearchEngine.search (self, list-of-QHelpSearchQuery queryList)
```

这种方法也是一个Qt槽与C + +的签名`void search(const QList&lt;QHelpSearchQuery&gt;&)`。

使用查询的给定列表开始搜索过程_queryList_构建由搜索字段名称和值来搜索。

* * *

## Qt Signal Documentation

```
void indexingFinished ()
```

这是该信号的默认超载。

当索引过程完成后，这个信号被发射。

```
void indexingStarted ()
```

这是该信号的默认超载。

当开始索引过程中这个信号被发射。

```
void searchingFinished (int)
```

这是该信号的默认超载。

当搜索过程就完成了这个信号被发射。命中计数存储在_hits_。

```
void searchingStarted ()
```

这是该信号的默认超载。

当开始搜索处理这个信号被发射。

](qhelpsearchresultwidget.html)