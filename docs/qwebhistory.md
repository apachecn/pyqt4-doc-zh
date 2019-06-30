# QWebHistory Class Reference

## [[QtWebKit](index.htm) module]

该QWebHistory类代表的历史[QWebPage](qwebpage.html) [More...](#details)

### Methods

*   `back (self)`
*   `QWebHistoryItem backItem (self)`
*   `list-of-QWebHistoryItem backItems (self, int maxItems)`
*   `bool canGoBack (self)`
*   `bool canGoForward (self)`
*   `clear (self)`
*   `int count (self)`
*   `QWebHistoryItem currentItem (self)`
*   `int currentItemIndex (self)`
*   `forward (self)`
*   `QWebHistoryItem forwardItem (self)`
*   `list-of-QWebHistoryItem forwardItems (self, int maxItems)`
*   `goToItem (self, QWebHistoryItem item)`
*   `QWebHistoryItem itemAt (self, int i)`
*   `list-of-QWebHistoryItem items (self)`
*   `int maximumItemCount (self)`
*   `setMaximumItemCount (self, int count)`

### Special Methods

*   `__len__ (self)`

* * *

## Detailed Description

该QWebHistory类代表的历史[QWebPage](qwebpage.html)

Each [QWebPage](qwebpage.html)实例包含了可接访问过的网页的历史记录[QWebPage.history](qwebpage.html#history)（ ） 。 QWebHistory表示这个历史和使得能够浏览它。

历史上使用的概念_current item_，划分为参观那些可以通过导航来访问过的网页_back_和_forward_使用[back](qwebhistory.html#back)（）和[forward](qwebhistory.html#forward)（）函数。目前的项目可以通过调用获得[currentItem](qwebhistory.html#currentItem)（ ） ，并在历史上的任意项目可以通过它传递所进行的当前项目[goToItem](qwebhistory.html#goToItem)（ ） 。

可以通过调用得到描述，可以通过返回被访问过的网页项的列表中[backItems](qwebhistory.html#backItems)（）函数，同样，描述了前面的当前页面的页面中的项目可以用以下方式获得[forwardItems](qwebhistory.html#forwardItems)（）函数。与得到的总项列表[items](qwebhistory.html#items)（）函数。

正如容器，功能可用来检查历史列表中的条款。在历史上任意的项目可以用以下方式获得[itemAt](qwebhistory.html#itemAt)（ ）的总项数由下式给出[count](qwebhistory.html#count)（）和历史可以与清除[clear](qwebhistory.html#clear)（）函数。

QWebHistory的状态可以保存到一个[QDataStream](qdatastream.html)使用\u003e\u003e运算符，并使用\u003c\u003c操作符加载。

* * *

## Method Documentation

```
QWebHistory.back (self)
```

设置当前项目是前一个项目的历史并进入相应的页面，也就是说，可以追溯到1历史项目。

**See also** [forward](qwebhistory.html#forward)（）和[goToItem](qwebhistory.html#goToItem)（ ） 。

```
QWebHistoryItem QWebHistory.backItem (self)
```

[

在历史记录中当前项目之前返回该项目。

```
list-of-QWebHistoryItem QWebHistory.backItems (self, int maxItems)
```

返回向后历史列表项的列表。最多_maxItems_条目返回。

](qwebhistoryitem.html)

[**See also**](qwebhistoryitem.html) [forwardItems](qwebhistory.html#forwardItems)（ ） 。

```
bool QWebHistory.canGoBack (self)
```

返回True如果有一个在历史记录中当前条目前面的项目;否则返回False。

**See also** [canGoForward](qwebhistory.html#canGoForward)（ ） 。

```
bool QWebHistory.canGoForward (self)
```

返回True如果我们有一个项目要往前走，否则返回False 。

**See also** [canGoBack](qwebhistory.html#canGoBack)（ ） 。

```
QWebHistory.clear (self)
```

清除历史。

**See also** [count](qwebhistory.html#count)（）和[items](qwebhistory.html#items)（ ） 。

```
int QWebHistory.count (self)
```

返回的项目在历史的总数。

```
QWebHistoryItem QWebHistory.currentItem (self)
```

[

返回历史上的当前项。

```
int QWebHistory.currentItemIndex (self)
```

返回历史记录中当前项的索引。

此功能被引入Qt的4.5 。

```
QWebHistory.forward (self)
```

设置当前项目是在历史的下一个项目，并进入相应的页面，也就是说，前进1历史项目。

](qwebhistoryitem.html)

[**See also**](qwebhistoryitem.html) [back](qwebhistory.html#back)（）和[goToItem](qwebhistory.html#goToItem)（ ） 。

```
QWebHistoryItem QWebHistory.forwardItem (self)
```

[

在历史上当前项目后返回的项目。

```
list-of-QWebHistoryItem QWebHistory.forwardItems (self, int maxItems)
```

返回在历史前进列表项的列表。最多_maxItems_条目返回。

](qwebhistoryitem.html)

[**See also**](qwebhistoryitem.html) [backItems](qwebhistory.html#backItems)（ ） 。

```
QWebHistory.goToItem (self, QWebHistoryItem item)
```

设置要指定当前项目_item_在历史上，并进入到该页面。

**See also** [back](qwebhistory.html#back)（）和[forward](qwebhistory.html#forward)（ ） 。

```
QWebHistoryItem QWebHistory.itemAt (self, int i)
```

[

返回索引项_i_在历史上。

```
list-of-QWebHistoryItem QWebHistory.items (self)
```

返回的所有项目，目前在历史列表。

](qwebhistoryitem.html)

[**See also**](qwebhistoryitem.html) [count](qwebhistory.html#count)（）和[clear](qwebhistory.html#clear)（ ） 。

```
int QWebHistory.maximumItemCount (self)
```

返回历史上的最大项目数。

此功能被引入Qt的4.5 。

**See also** [setMaximumItemCount](qwebhistory.html#setMaximumItemCount)（ ） 。

```
QWebHistory.setMaximumItemCount (self, int count)
```

设置在历史的最大项目数量_count_。

此功能被引入Qt的4.5 。

**See also** [maximumItemCount](qwebhistory.html#maximumItemCount)（ ） 。

```
 QWebHistory.__len__ (self)
```