# QFocusEvent Class Reference

## [[QtGui](index.htm) module]

该QFocusEvent类包含事件参数的部件焦点事件。[More...](#details)

继承[QEvent](qevent.html)。

### Methods

*   `__init__ (self, QEvent.Type type, Qt.FocusReason reason = Qt.OtherFocusReason)`
*   `__init__ (self, QFocusEvent)`
*   `bool gotFocus (self)`
*   `bool lostFocus (self)`
*   `Qt.FocusReason reason (self)`

* * *

## Detailed Description

该QFocusEvent类包含事件参数的部件焦点事件。

焦点事件发送到窗口部件的键盘输入焦点的变化时。焦点事件，由于鼠标操作，按键（如发生**Tab** or **Backtab**） ，窗口系统，弹出菜单，键盘快捷键，或其他应用程序特定的原因。之所以特别关注事件被返回[reason](qfocusevent.html#reason)（ ）在适当的事件处理程序。

该事件处理程序[QWidget.focusInEvent](qwidget.html#focusInEvent)（ ）[QWidget.focusOutEvent](qwidget.html#focusOutEvent)（ ） ， QGraphicsItem.focusInEvent和[QGraphicsItem.focusOutEvent](qgraphicsitem.html#focusOutEvent)（ ）获得焦点事件。

* * *

## Method Documentation

```
QFocusEvent.__init__ (self, QEvent.Type type, Qt.FocusReason reason = Qt.OtherFocusReason)
```

构造一个焦点事件的对象。

该_type_参数必须是[QEvent.FocusIn](qevent.html#Type-enum) or [QEvent.FocusOut](qevent.html#Type-enum)。该_reason_描述了焦点变化的原因。

```
QFocusEvent.__init__ (self, QFocusEvent)
```

```
bool QFocusEvent.gotFocus (self)
```

返回True如果[type](qevent.html#type)（）是[QEvent.FocusIn](qevent.html#Type-enum)否则返回False 。

```
bool QFocusEvent.lostFocus (self)
```

返回True如果[type](qevent.html#type)（）是[QEvent.FocusOut](qevent.html#Type-enum)否则返回False 。

```
Qt.FocusReason QFocusEvent.reason (self)
```

[

返回此焦点事件的原因。

](qt.html#FocusReason-enum)