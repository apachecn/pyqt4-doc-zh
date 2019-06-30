# QChildEvent Class Reference

## [[QtCore](index.htm) module]

该QChildEvent类包含事件参数的子对象的事件。[More...](#details)

继承[QEvent](qevent.html)。

### Methods

*   `__init__ (self, QEvent.Type type, QObject child)`
*   `__init__ (self, QChildEvent)`
*   `bool added (self)`
*   `QObject child (self)`
*   `bool polished (self)`
*   `bool removed (self)`

* * *

## Detailed Description

该QChildEvent类包含事件参数的子对象的事件。

孩子的事件会立即发送到对象时，孩子们被添加或删除。

在这两种情况下，你只能依靠孩子作为一个[QObject](qobject.html)（或者，如果[QObject.isWidgetType](qobject.html#isWidgetType)（ ）返回True ，一[QWidget](qwidget.html)） 。这是因为在[QEvent.ChildAdded](qevent.html#Type-enum)区分孩子还没有完全建成，而在[QEvent.ChildRemoved](qevent.html#Type-enum)情况下，它可能已被破坏。

该处理器为这些事件是[QObject.childEvent](qobject.html#childEvent)（ ） 。

* * *

## Method Documentation

```
QChildEvent.__init__ (self, QEvent.Type type, QObject child)
```

构建了一个特定的子事件对象_type_为_child_。

_type_可以[QEvent.ChildAdded](qevent.html#Type-enum)，[QEvent.ChildRemoved](qevent.html#Type-enum)，[QEvent.ChildPolished](qevent.html#Type-enum)或[QEvent.ChildRemoved](qevent.html#Type-enum)。

**See also** [child](qchildevent.html#child)（ ） 。

```
QChildEvent.__init__ (self, QChildEvent)
```

```
bool QChildEvent.added (self)
```

返回True如果[type](qevent.html#type)（）是[QEvent.ChildAdded](qevent.html#Type-enum)否则返回False 。

```
QObject QChildEvent.child (self)
```

[

返回已添加或删除的子对象。

```
bool QChildEvent.polished (self)
```

](qobject.html)

[返回True如果](qobject.html)[type](qevent.html#type)（）是[QEvent.ChildPolished](qevent.html#Type-enum)否则返回False 。

```
bool QChildEvent.removed (self)
```

返回True如果[type](qevent.html#type)（）是[QEvent.ChildRemoved](qevent.html#Type-enum)否则返回False 。