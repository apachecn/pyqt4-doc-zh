# QDateEdit Class Reference

## [[QtGui](index.htm) module]

The QDateEdit class provides a widget for editing dates based on the [QDateTimeEdit](qdatetimeedit.html) widget. [More...](#details)

继承[QDateTimeEdit](qdatetimeedit.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `__init__ (self, QDate date, QWidget parent = None)`

* * *

## Detailed Description

该QDateEdit类提供的基础上，进行编辑日期的小部件[QDateTimeEdit](qdatetimeedit.html)小工具。

许多由QDateEdit提供的性能和功能都在实施[QDateTimeEdit](qdatetimeedit.html)。下列属性是最相关与这个类的用户：

*   [date](qdatetimeedit.html#date-prop) holds the date displayed by the widget.
*   [minimumDate](qdatetimeedit.html#minimumDate-prop) defines the minimum (earliest) date that can be set by the user.
*   [maximumDate](qdatetimeedit.html#maximumDate-prop) defines the maximum (latest) date that can be set by the user.
*   [displayFormat](qdatetimeedit.html#displayFormat-prop) contains a string that is used to format the date displayed in the widget.

| ![Screenshot of a Windows XP style date editing widget](../img/windowsxp-dateedit.png) | A date editing widget shown in the [Windows XP widget style](index.htm). |
| ![Screenshot of a Macintosh style date editing widget](../img/macintosh-dateedit.png) | A date editing widget shown in the [Macintosh widget style](index.htm). |
| ![Screenshot of a Plastique style date editing widget](../img/plastique-dateedit.png) | A date editing widget shown in the [Plastique widget style](index.htm). |

* * *

## Method Documentation

```
QDateEdit.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个空的日期编辑器与_parent_。

```
QDateEdit.__init__ (self, QDate date, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个空的日期编辑器与_parent_。日期设置为_date_。