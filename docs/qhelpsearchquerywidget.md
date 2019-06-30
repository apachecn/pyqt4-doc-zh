# QHelpSearchQueryWidget Class Reference

## [[QtHelp](index.htm) module]

该QHelpSearchQueryWidget类提供了一个简单的行编辑或先进的小工具，让用户输入一个搜索词在一个标准化的输入掩码。[More...](#details)

继承[QWidget](qwidget.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `collapseExtendedSearch (self)`
*   `expandExtendedSearch (self)`
*   `list-of-QHelpSearchQuery query (self)`
*   `setQuery (self, list-of-QHelpSearchQuery queryList)`

### Qt Signals

*   `void search ()`

* * *

## Detailed Description

该QHelpSearchQueryWidget类提供了一个简单的行编辑或先进的小工具，让用户输入一个搜索词在一个标准化的输入掩码。

* * *

## Method Documentation

```
QHelpSearchQueryWidget.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的搜索查询小部件与给定_parent_。

```
QHelpSearchQueryWidget.collapseExtendedSearch (self)
```

折叠的搜索查询小工具，这样只有默认的搜索栏显示。

此功能被引入Qt的4.8 。

```
QHelpSearchQueryWidget.expandExtendedSearch (self)
```

扩展搜索查询的插件，使得该扩展的搜索字段被示出。

此功能被引入Qt的4.8 。

```
list-of-QHelpSearchQuery QHelpSearchQueryWidget.query (self)
```

返回到用结合使用的搜索引擎的搜索（查询列表[QList](index.htm)\u003c[QHelpSearchQuery](qhelpsearchquery.html)\u003e＆ queryList ）函数。

**See also** [setQuery](qhelpsearchquerywidget.html#setQuery)（ ） 。

```
QHelpSearchQueryWidget.setQuery (self, list-of-QHelpSearchQuery queryList)
```

设置[QHelpSearchQueryWidget](qhelpsearchquerywidget.html)输入字段通过指定的值_queryList_搜寻栏位名称。请注意，一要调用搜索引擎的搜索（[QList](index.htm)\u003c[QHelpSearchQuery](qhelpsearchquery.html)\u003e＆ queryList ）函数来执行实际的搜索。

此功能被引入Qt的4.8 。

**See also** [query](qhelpsearchquerywidget.html#query)（ ） 。

* * *

## Qt Signal Documentation

```
void search ()
```

这是该信号的默认超载。

当一个用户有调用的搜索按钮这个信号被发射。 reciving信号之后你可以问[QHelpSearchQueryWidget](qhelpsearchquerywidget.html)为构建列表[QHelpSearchQuery](qhelpsearchquery.html)的，你可能会传递到[QHelpSearchEngine](qhelpsearchengine.html)的search（）函数。