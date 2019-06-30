# QActionEvent Class Reference

## [[QtGui](index.htm) module]

该QActionEvent类提供了产生一个事件时，[QAction](qaction.html)添加，删除或更改。[More...](#details)

继承[QEvent](qevent.html)。

### Methods

*   `__init__ (self, int type, QAction action, QAction before = None)`
*   `__init__ (self, QActionEvent)`
*   `QAction action (self)`
*   `QAction before (self)`

* * *

## Detailed Description

该QActionEvent类提供了产生一个事件时，[QAction](qaction.html)添加，删除或更改。

操作可以使用被添加到小部件[QWidget.addAction](qwidget.html#addAction)（ ） 。这将生成一个[ActionAdded](qevent.html#Type-enum)事件，您可以处理，以提供自定义行为。例如，[QToolBar](qtoolbar.html)重新实现[QWidget.actionEvent](qwidget.html#actionEvent)（ ）来创建[QToolButton](qtoolbutton.html)S为行动。

* * *

## Method Documentation

```
QActionEvent.__init__ (self, int type, QAction action, QAction before = None)
```

构造一个动作事件。该_type_可以[ActionChanged](qevent.html#Type-enum)，[ActionAdded](qevent.html#Type-enum)或[ActionRemoved](qevent.html#Type-enum)。

_action_是改变的动作，添加或删除。如果_type_ is [ActionAdded](qevent.html#Type-enum)，动作是动作之前插入_before_。如果_before_为0时，动作被追加。

```
QActionEvent.__init__ (self, QActionEvent)
```

```
QAction QActionEvent.action (self)
```

[

返回更改，添加或删除的动作。

](qaction.html)

[**See also**](qaction.html) [before](qactionevent.html#before)（ ） 。

```
QAction QActionEvent.before (self)
```

[](qaction.html)

[If](qaction.html) [type](qevent.html#type)（）是[ActionAdded](qevent.html#Type-enum)，返回应该出现在这之前的动作[action](qactionevent.html#action)（ ） 。如果这个函数返回0时，动作应被追加到已有的同一部件的动作。

**See also** [action](qactionevent.html#action)（）和[QWidget.actions](qwidget.html#actions)（ ） 。