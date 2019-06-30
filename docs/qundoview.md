# QUndoView Class Reference

## [[QtGui](index.htm) module]

该QUndoView类显示的内容[QUndoStack](qundostack.html)。[More...](#details)

继承[QListView](qlistview.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `__init__ (self, QUndoStack stack, QWidget parent = None)`
*   `__init__ (self, QUndoGroup group, QWidget parent = None)`
*   `QIcon cleanIcon (self)`
*   `QString emptyLabel (self)`
*   `QUndoGroup group (self)`
*   `setCleanIcon (self, QIcon icon)`
*   `setEmptyLabel (self, QString label)`
*   `setGroup (self, QUndoGroup group)`
*   `setStack (self, QUndoStack stack)`
*   `QUndoStack stack (self)`

* * *

## Detailed Description

该QUndoView类显示的内容[QUndoStack](qundostack.html)。

QUndoView是[QListView](qlistview.html)其中显示命令的列表上推撤消堆栈。最近执行的命令总是选择。选择在通话中不同的命令结果[QUndoStack.setIndex](qundostack.html#setIndex)（ ） ，滚动文档的状态向后或向前的新命令。

该协议栈可以显式设置[setStack](qundoview.html#setStack)（ ） 。另外，一个[QUndoGroup](qundogroup.html)对象可以与设置[setGroup](qundoview.html#setGroup)（ ） 。那么该视图会自动更新每当小组的活动堆栈变化。

![](../img/qundoview.png)

* * *

## Method Documentation

```
QUndoView.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个父一个新的视图_parent_。

```
QUndoView.__init__ (self, QUndoStack stack, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个父一个新的视图_parent_与所观察到的堆栈设置到_stack_。

```
QUndoView.__init__ (self, QUndoGroup group, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个父一个新的视图_parent_而观察组设置为_group_。

该视图会自动更新autmiatically每当组的活动堆栈变化。

```
QIcon QUndoView.cleanIcon (self)
```

[

```
QString QUndoView.emptyLabel (self)
```

](qicon.html)

```
QUndoGroup QUndoView.group (self)
```

[

返回此视图中显示的组。

如果视图不看组，这个函数返回0 。

](qundogroup.html)

[**See also**](qundogroup.html) [setGroup](qundoview.html#setGroup)（）和[setStack](qundoview.html#setStack)（ ） 。

```
QUndoView.setCleanIcon (self, QIcon icon)
```

```
QUndoView.setEmptyLabel (self, QString label)
```

```
QUndoView.setGroup (self, QUndoGroup group)
```

这种方法也是一个Qt槽与C + +的签名`void setGroup(QUndoGroup *)`。

设置此视图中显示的组_group_。如果_group_为0时，显示将是空的。

该视图会自动更新autmiatically每当组的活动堆栈变化。

**See also** [group](qundoview.html#group)（）和[setStack](qundoview.html#setStack)（ ） 。

```
QUndoView.setStack (self, QUndoStack stack)
```

这种方法也是一个Qt槽与C + +的签名`void setStack(QUndoStack *)`。

设置此视图中显示的栈_stack_。如果_stack_为0时，显示将是空的。

如果认为以前一直在寻找一个[QUndoGroup](qundogroup.html)的组被设置为0 。

**See also** [stack](qundoview.html#stack)（）和[setGroup](qundoview.html#setGroup)（ ） 。

```
QUndoStack QUndoView.stack (self)
```

[](qundostack.html)

[返回当前此视图中显示的堆栈。如果视图是在看](qundostack.html)[QUndoGroup](qundogroup.html)这个小组的活动堆栈。

**See also** [setStack](qundoview.html#setStack)（）和[setGroup](qundoview.html#setGroup)（ ） 。