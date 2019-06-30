# QTimeEdit Class Reference

## [[QtGui](index.htm) module]

该QTimeEdit类提供了基于编辑时间窗口小部件[QDateTimeEdit](qdatetimeedit.html)小工具。[More...](#details)

继承[QDateTimeEdit](qdatetimeedit.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `__init__ (self, QTime time, QWidget parent = None)`

* * *

## Detailed Description

该QTimeEdit类提供了基于编辑时间窗口小部件[QDateTimeEdit](qdatetimeedit.html)小工具。

许多由QTimeEdit提供的性能和功能都在实施[QDateTimeEdit](qdatetimeedit.html)。下列属性是最相关与这个类的用户：

*   [time](qdatetimeedit.html#time-prop) holds the date displayed by the widget.
*   [minimumTime](qdatetimeedit.html#minimumTime-prop) defines the minimum (earliest) time that can be set by the user.
*   [maximumTime](qdatetimeedit.html#maximumTime-prop) defines the maximum (latest) time that can be set by the user.
*   [displayFormat](qdatetimeedit.html#displayFormat-prop) contains a string that is used to format the time displayed in the widget.

| ![Screenshot of a Windows XP style time editing widget](../img/windowsxp-timeedit.png) | A time editing widget shown in the [Windows XP widget style](index.htm). |
| ![Screenshot of a Macintosh style time editing widget](../img/macintosh-timeedit.png) | A time editing widget shown in the [Macintosh widget style](index.htm). |
| ![Screenshot of a Plastique style time editing widget](../img/plastique-timeedit.png) | A time editing widget shown in the [Plastique widget style](index.htm). |

* * *

## Method Documentation

```
QTimeEdit.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个空的时间编辑器_parent_。

```
QTimeEdit.__init__ (self, QTime time, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个空的时间编辑器_parent_。的时间设定为_time_。