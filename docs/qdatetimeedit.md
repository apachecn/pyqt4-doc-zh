# QDateTimeEdit Class Reference

## [[QtGui](index.htm) module]

该QDateTimeEdit类提供了一个部件的编辑日期和时间。[More...](#details)

继承[QAbstractSpinBox](qabstractspinbox.html)。

通过继承[QDateEdit](qdateedit.html)和[QTimeEdit](qtimeedit.html)。

### Types

*   `enum Section { NoSection, AmPmSection, MSecSection, SecondSection, ..., DateSections_Mask }`
*   `class **[Sections](index.htm)**`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `__init__ (self, QDateTime datetime, QWidget parent = None)`
*   `__init__ (self, QDate date, QWidget parent = None)`
*   `__init__ (self, QTime time, QWidget parent = None)`
*   `bool calendarPopup (self)`
*   `QCalendarWidget calendarWidget (self)`
*   `clear (self)`
*   `clearMaximumDate (self)`
*   `clearMaximumDateTime (self)`
*   `clearMaximumTime (self)`
*   `clearMinimumDate (self)`
*   `clearMinimumDateTime (self)`
*   `clearMinimumTime (self)`
*   `Section currentSection (self)`
*   `int currentSectionIndex (self)`
*   `QDate date (self)`
*   `QDateTime dateTime (self)`
*   `QDateTime dateTimeFromText (self, QString text)`
*   `Sections displayedSections (self)`
*   `QString displayFormat (self)`
*   `bool event (self, QEvent e)`
*   `QString input fixup (self, QString input)`
*   `fixup (self, QString input)`
*   `focusInEvent (self, QFocusEvent e)`
*   `bool focusNextPrevChild (self, bool next)`
*   `initStyleOption (self, QStyleOptionSpinBox option)`
*   `keyPressEvent (self, QKeyEvent e)`
*   `QDate maximumDate (self)`
*   `QDateTime maximumDateTime (self)`
*   `QTime maximumTime (self)`
*   `QDate minimumDate (self)`
*   `QDateTime minimumDateTime (self)`
*   `QTime minimumTime (self)`
*   `mousePressEvent (self, QMouseEvent event)`
*   `paintEvent (self, QPaintEvent event)`
*   `Section sectionAt (self, int index)`
*   `int sectionCount (self)`
*   `QString sectionText (self, Section s)`
*   `setCalendarPopup (self, bool enable)`
*   `setCalendarWidget (self, QCalendarWidget calendarWidget)`
*   `setCurrentSection (self, Section section)`
*   `setCurrentSectionIndex (self, int index)`
*   `setDate (self, QDate date)`
*   `setDateRange (self, QDate min, QDate max)`
*   `setDateTime (self, QDateTime dateTime)`
*   `setDateTimeRange (self, QDateTime min, QDateTime max)`
*   `setDisplayFormat (self, QString format)`
*   `setMaximumDate (self, QDate max)`
*   `setMaximumDateTime (self, QDateTime dt)`
*   `setMaximumTime (self, QTime max)`
*   `setMinimumDate (self, QDate min)`
*   `setMinimumDateTime (self, QDateTime dt)`
*   `setMinimumTime (self, QTime min)`
*   `setSelectedSection (self, Section section)`
*   `setTime (self, QTime time)`
*   `setTimeRange (self, QTime min, QTime max)`
*   `setTimeSpec (self, Qt.TimeSpec spec)`
*   `QSize sizeHint (self)`
*   `stepBy (self, int steps)`
*   `QAbstractSpinBox.StepEnabled stepEnabled (self)`
*   `QString textFromDateTime (self, QDateTime dt)`
*   `QTime time (self)`
*   `Qt.TimeSpec timeSpec (self)`
*   `(QValidator.State, QString input, int pos) validate (self, QString input, int pos)`
*   `(QValidator.State, int pos) validate (self, QString input, int pos)`
*   `wheelEvent (self, QWheelEvent e)`

### Qt Signals

*   `void dateChanged (const QDate&)`
*   `void dateTimeChanged (const QDateTime&)`
*   `void timeChanged (const QTime&)`

* * *

## Detailed Description

该QDateTimeEdit类提供了一个部件的编辑日期和时间。

QDateTimeEdit允许用户通过使用键盘或箭头键来增加和减少的日期和时间值进行编辑的日期。箭头键可以用来从部分移动到QDateTimeEdit框内部分。日期和时间出现在按照设定的格式，见[setDisplayFormat](qdatetimeedit.html#displayFormat-prop)（ ） 。

```
 QDateTimeEdit *dateEdit = new QDateTimeEdit([QDate](qdate.html).currentDate());
 dateEdit->setMinimumDate([QDate](qdate.html).currentDate().addDays(-365));
 dateEdit->setMaximumDate([QDate](qdate.html).currentDate().addDays(365));
 dateEdit->setDisplayFormat("yyyy.MM.dd");

```

在这里，我们已经创建了今天的日期初始化的新QDateTimeEdit对象，并制约了有效日期范围到今天正负365天。我们已经设置为月，日，年。

对于QDateTimeEdit最小值为1752年9月14日，和1月2日4713BC的[QDate](qdate.html)。您可以通过调用改变这个[setMinimumDate](qdatetimeedit.html#minimumDate-prop)（ ）[setMaximumDate](qdatetimeedit.html#maximumDate-prop)（ ）[setMinimumTime](qdatetimeedit.html#minimumTime-prop)（）和[setMaximumTime](qdatetimeedit.html#maximumTime-prop)（ ） 。

### Using a Pop-up Calendar Widget

QDateTimeEdit可以被配置为允许[QCalendarWidget](qcalendarwidget.html)将用于选择的日期。这是通过设置启用[calendarPopup](qdatetimeedit.html#calendarPopup-prop)属性。此外，您可以通过调用提供自定义日历组件用作日历弹出[setCalendarWidget](qdatetimeedit.html#setCalendarWidget)（）函数。现有的日历控件可以检索与[calendarWidget](qdatetimeedit.html#calendarWidget)（ ） 。

| ![Screenshot of a Windows XP style date time editing widget](../img/windowsxp-datetimeedit.png) | A date time editing widget shown in the [Windows XP widget style](index.htm). |
| ![Screenshot of a Macintosh style date time editing widget](../img/macintosh-datetimeedit.png) | A date time editing widget shown in the [Macintosh widget style](index.htm). |
| ![Screenshot of a Plastique style date time editing widget](../img/plastique-datetimeedit.png) | A date time editing widget shown in the [Plastique widget style](index.htm). |

* * *

## Type Documentation

```
QDateTimeEdit.Section
```

| Constant | Value |
| --- | --- |
| `QDateTimeEdit.NoSection` | `0x0000` |
| `QDateTimeEdit.AmPmSection` | `0x0001` |
| `QDateTimeEdit.MSecSection` | `0x0002` |
| `QDateTimeEdit.SecondSection` | `0x0004` |
| `QDateTimeEdit.MinuteSection` | `0x0008` |
| `QDateTimeEdit.HourSection` | `0x0010` |
| `QDateTimeEdit.DaySection` | `0x0100` |
| `QDateTimeEdit.MonthSection` | `0x0200` |
| `QDateTimeEdit.YearSection` | `0x0400` |

该部分类型是一个typedef为[QFlags](index.htm)\u003cSECTION\u003e 。它存储段值的或组合。

* * *

## Method Documentation

```
QDateTimeEdit.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个空的日期时间编辑器_parent_。

```
QDateTimeEdit.__init__ (self, QDateTime datetime, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个空的日期时间编辑器_parent_。该值被设置为_datetime_。

```
QDateTimeEdit.__init__ (self, QDate date, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个空的日期时间编辑器_parent_。该值被设置为_date_。

```
QDateTimeEdit.__init__ (self, QTime time, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个空的日期时间编辑器_parent_。该值被设置为_time_。

```
bool QDateTimeEdit.calendarPopup (self)
```

```
QCalendarWidget QDateTimeEdit.calendarWidget (self)
```

[](qcalendarwidget.html)

[返回日历窗口小部件的编辑器，如果](qcalendarwidget.html)[calendarPopup](qdatetimeedit.html#calendarPopup-prop)被设置为True和（[sections](index.htm#sections)（）和[DateSections_Mask](qdatetimeedit.html#Section-enum)！） = 0 。

这个函数创建并返回一个日历组件，如果没有设置。

此功能被引入Qt的4.4 。

**See also** [setCalendarWidget](qdatetimeedit.html#setCalendarWidget)（ ） 。

```
QDateTimeEdit.clear (self)
```

从重新实现[QAbstractSpinBox.clear](qabstractspinbox.html#clear)（ ） 。

```
QDateTimeEdit.clearMaximumDate (self)
```

```
QDateTimeEdit.clearMaximumDateTime (self)
```

```
QDateTimeEdit.clearMaximumTime (self)
```

```
QDateTimeEdit.clearMinimumDate (self)
```

```
QDateTimeEdit.clearMinimumDateTime (self)
```

```
QDateTimeEdit.clearMinimumTime (self)
```

```
Section QDateTimeEdit.currentSection (self)
```

[

```
int QDateTimeEdit.currentSectionIndex (self)
```

](qdatetimeedit.html#Section-enum)

```
QDate QDateTimeEdit.date (self)
```

[](qdate.html)

```
QDateTime QDateTimeEdit.dateTime (self)
```

[](qdatetime.html)

```
QDateTime QDateTimeEdit.dateTimeFromText (self, QString text)
```

[

返回一个适当的日期时间为给定的_text_。

这个虚拟函数是所使用的日期时间编辑时，它需要解释由用户输入的值的文本。

](qdatetime.html)

[**See also**](qdatetime.html) [textFromDateTime](qdatetimeedit.html#textFromDateTime)（）和[validate](qdatetimeedit.html#validate)（ ） 。

```
Sections QDateTimeEdit.displayedSections (self)
```

[

```
QString QDateTimeEdit.displayFormat (self)
```

```
bool QDateTimeEdit.event (self, QEvent e)
```

](index.htm)

[从重新实现](index.htm)[QObject.event](qobject.html#event)（ ） 。

```
QString input QDateTimeEdit.fixup (self, QString input)
```

从重新实现[QAbstractSpinBox.fixup](qabstractspinbox.html#fixup)（ ） 。

```
QDateTimeEdit.fixup (self, QString input)
```

```
QDateTimeEdit.focusInEvent (self, QFocusEvent e)
```

从重新实现[QWidget.focusInEvent](qwidget.html#focusInEvent)（ ） 。

```
bool QDateTimeEdit.focusNextPrevChild (self, bool next)
```

从重新实现[QWidget.focusNextPrevChild](qwidget.html#focusNextPrevChild)（ ） 。

```
QDateTimeEdit.initStyleOption (self, QStyleOptionSpinBox option)
```

初始化_option_与这QDataTimeEdit的值。当他们需要一个这种方法是有用的子类[QStyleOptionSpinBox](qstyleoptionspinbox.html)，但不希望在所有的信息填写自己。

**See also** [QStyleOption.initFrom](qstyleoption.html#initFrom)（ ） 。

```
QDateTimeEdit.keyPressEvent (self, QKeyEvent e)
```

从重新实现[QWidget.keyPressEvent](qwidget.html#keyPressEvent)（ ） 。

```
QDate QDateTimeEdit.maximumDate (self)
```

[](qdate.html)

```
QDateTime QDateTimeEdit.maximumDateTime (self)
```

[](qdatetime.html)

```
QTime QDateTimeEdit.maximumTime (self)
```

[](qtime.html)

```
QDate QDateTimeEdit.minimumDate (self)
```

[](qdate.html)

```
QDateTime QDateTimeEdit.minimumDateTime (self)
```

[](qdatetime.html)

```
QTime QDateTimeEdit.minimumTime (self)
```

[

```
QDateTimeEdit.mousePressEvent (self, QMouseEvent event)
```

](qtime.html)

[从重新实现](qtime.html)[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

```
QDateTimeEdit.paintEvent (self, QPaintEvent event)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
Section QDateTimeEdit.sectionAt (self, int index)
```

[

返回科_index_。

](qdatetimeedit.html#Section-enum)

[如果格式是'YYYY / MM / DD ' ， sectionAt （ 0 ）返回](qdatetimeedit.html#Section-enum)[YearSection](qdatetimeedit.html#Section-enum)， sectionAt （ 1 ）返回[MonthSection](qdatetimeedit.html#Section-enum)和sectionAt （2）返回[YearSection](qdatetimeedit.html#Section-enum)，

此功能被引入Qt的4.3 。

```
int QDateTimeEdit.sectionCount (self)
```

```
QString QDateTimeEdit.sectionText (self, Section s)
```

从给定的返回文本_section_。

**See also** [currentSection](qdatetimeedit.html#currentSection-prop)（ ） 。

```
QDateTimeEdit.setCalendarPopup (self, bool enable)
```

```
QDateTimeEdit.setCalendarWidget (self, QCalendarWidget calendarWidget)
```

该_calendarWidget_说法有它的所有权转移给Qt的。

设置给定_calendarWidget_作为要用于日历弹出的窗口小部件。编辑器不会自动把日历窗口小部件的所有权。

**Note:** [calendarPopup](qdatetimeedit.html#calendarPopup-prop)设置日历控件之前，必须设置为True。

此功能被引入Qt的4.4 。

**See also** [calendarWidget](qdatetimeedit.html#calendarWidget)（）和[calendarPopup](qdatetimeedit.html#calendarPopup-prop)。

```
QDateTimeEdit.setCurrentSection (self, Section section)
```

```
QDateTimeEdit.setCurrentSectionIndex (self, int index)
```

```
QDateTimeEdit.setDate (self, QDate date)
```

这种方法也是一个Qt槽与C + +的签名`void setDate(const QDate&)`。

```
QDateTimeEdit.setDateRange (self, QDate min, QDate max)
```

方便的功能来设置最小和最大日期用一个函数调用。

```
 setDateRange(min, max);

```

类似于：

```
 setMinimumDate(min);
 setMaximumDate(max);

```

如果任_min_ or _max_是无效的，这个函数不执行任何操作。

**See also** [setMinimumDate](qdatetimeedit.html#minimumDate-prop)（ ）[maximumDate](qdatetimeedit.html#maximumDate-prop)（ ）[setMaximumDate](qdatetimeedit.html#maximumDate-prop)（ ）[clearMinimumDate](qdatetimeedit.html#minimumDate-prop)（ ）[setMinimumTime](qdatetimeedit.html#minimumTime-prop)（ ）[maximumTime](qdatetimeedit.html#maximumTime-prop)（ ）[setMaximumTime](qdatetimeedit.html#maximumTime-prop)（ ）[clearMinimumTime](qdatetimeedit.html#minimumTime-prop)（）和[QDate.isValid](qdate.html#isValid)（ ） 。

```
QDateTimeEdit.setDateTime (self, QDateTime dateTime)
```

这种方法也是一个Qt槽与C + +的签名`void setDateTime(const QDateTime&)`。

```
QDateTimeEdit.setDateTimeRange (self, QDateTime min, QDateTime max)
```

方便的功能来设置最小和最大日期与时间一个函数调用。

```
 setDateTimeRange(min, max);

```

类似于：

```
 setMinimumDateTime(min);
 setMaximumDateTime(max);

```

如果任_min_ or _max_是无效的，这个函数不执行任何操作。

此功能被引入Qt的4.4 。

**See also** [setMinimumDate](qdatetimeedit.html#minimumDate-prop)（ ）[maximumDate](qdatetimeedit.html#maximumDate-prop)（ ）[setMaximumDate](qdatetimeedit.html#maximumDate-prop)（ ）[clearMinimumDate](qdatetimeedit.html#minimumDate-prop)（ ）[setMinimumTime](qdatetimeedit.html#minimumTime-prop)（ ）[maximumTime](qdatetimeedit.html#maximumTime-prop)（ ）[setMaximumTime](qdatetimeedit.html#maximumTime-prop)（ ）[clearMinimumTime](qdatetimeedit.html#minimumTime-prop)（）和[QDateTime.isValid](qdatetime.html#isValid)（ ） 。

```
QDateTimeEdit.setDisplayFormat (self, QString format)
```

```
QDateTimeEdit.setMaximumDate (self, QDate max)
```

```
QDateTimeEdit.setMaximumDateTime (self, QDateTime dt)
```

```
QDateTimeEdit.setMaximumTime (self, QTime max)
```

```
QDateTimeEdit.setMinimumDate (self, QDate min)
```

```
QDateTimeEdit.setMinimumDateTime (self, QDateTime dt)
```

```
QDateTimeEdit.setMinimumTime (self, QTime min)
```

```
QDateTimeEdit.setSelectedSection (self, Section section)
```

Selects _section_。如果_section_在当前显示的部分不存在这个函数什么都不做。如果_section_ is [NoSection](qdatetimeedit.html#Section-enum)此功能将取消选择在编辑器中的所有文本。否则，此函数将移动光标和当前部分选定的部分。

这个函数中引入了Qt 4.2中。

**See also** [currentSection](qdatetimeedit.html#currentSection-prop)（ ） 。

```
QDateTimeEdit.setTime (self, QTime time)
```

这种方法也是一个Qt槽与C + +的签名`void setTime(const QTime&)`。

```
QDateTimeEdit.setTimeRange (self, QTime min, QTime max)
```

方便的功能来设置最小和最大时间有一个函数调用。

```
 setTimeRange(min, max);

```

类似于：

```
 setMinimumTime(min);
 setMaximumTime(max);

```

如果任_min_ or _max_是无效的，这个函数不执行任何操作。

**See also** [setMinimumDate](qdatetimeedit.html#minimumDate-prop)（ ）[maximumDate](qdatetimeedit.html#maximumDate-prop)（ ）[setMaximumDate](qdatetimeedit.html#maximumDate-prop)（ ）[clearMinimumDate](qdatetimeedit.html#minimumDate-prop)（ ）[setMinimumTime](qdatetimeedit.html#minimumTime-prop)（ ）[maximumTime](qdatetimeedit.html#maximumTime-prop)（ ）[setMaximumTime](qdatetimeedit.html#maximumTime-prop)（ ）[clearMinimumTime](qdatetimeedit.html#minimumTime-prop)（）和[QTime.isValid](qtime.html#isValid)（ ） 。

```
QDateTimeEdit.setTimeSpec (self, Qt.TimeSpec spec)
```

```
QSize QDateTimeEdit.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

```
QDateTimeEdit.stepBy (self, int steps)
```

从重新实现[QAbstractSpinBox.stepBy](qabstractspinbox.html#stepBy)（ ） 。

```
QAbstractSpinBox.StepEnabled QDateTimeEdit.stepEnabled (self)
```

[](index.htm)

[从重新实现](index.htm)[QAbstractSpinBox.stepEnabled](qabstractspinbox.html#stepEnabled)（ ） 。

```
QString QDateTimeEdit.textFromDateTime (self, QDateTime dt)
```

这个虚函数所使用的日期时间编辑时，它需要显示_dateTime_。

如果你重新实现这一点，您可能还需要重新实现[validate](qdatetimeedit.html#validate)（ ） 。

**See also** [dateTimeFromText](qdatetimeedit.html#dateTimeFromText)（）和[validate](qdatetimeedit.html#validate)（ ） 。

```
QTime QDateTimeEdit.time (self)
```

[](qtime.html)

```
Qt.TimeSpec QDateTimeEdit.timeSpec (self)
```

[

```
(QValidator.State, QString input, int pos) QDateTimeEdit.validate (self, QString input, int pos)
```

](qt.html#TimeSpec-enum)

[从重新实现](qt.html#TimeSpec-enum)[QAbstractSpinBox.validate](qabstractspinbox.html#validate)（ ） 。

```
(QValidator.State, int pos) QDateTimeEdit.validate (self, QString input, int pos)
```

```
QDateTimeEdit.wheelEvent (self, QWheelEvent e)
```

从重新实现[QWidget.wheelEvent](qwidget.html#wheelEvent)（ ） 。

* * *

## Qt Signal Documentation

```
void dateChanged (const QDate&)
```

这是该信号的默认超载。

这个信号被发射时的时间被改变。新的日期是在传递_date_。

```
void dateTimeChanged (const QDateTime&)
```

这是该信号的默认超载。

这个信号被发射时的日期或时间而改变。新的日期和时间被传递_datetime_。

```
void timeChanged (const QTime&)
```

这是该信号的默认超载。

这个信号被发射时的时间被改变。新的时间被传递_time_。