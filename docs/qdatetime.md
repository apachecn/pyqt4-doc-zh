# QDateTime Class Reference

## [[QtCore](index.htm) module]

该QDateTime类提供​​日期和时间函数。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QDateTime other)`
*   `__init__ (self, QDate)`
*   `__init__ (self, QDate date, QTime time, Qt.TimeSpec timeSpec = Qt.LocalTime)`
*   `__init__ (self, int y, int m, int d, int h, int m, int s = 0, int msec = 0, int timeSpec = 0)`
*   `QDateTime addDays (self, int days)`
*   `QDateTime addMonths (self, int months)`
*   `QDateTime addMSecs (self, int msecs)`
*   `QDateTime addSecs (self, int secs)`
*   `QDateTime addYears (self, int years)`
*   `QDate date (self)`
*   `int daysTo (self, QDateTime)`
*   `bool isNull (self)`
*   `bool isValid (self)`
*   `int msecsTo (self, QDateTime)`
*   `int secsTo (self, QDateTime)`
*   `setDate (self, QDate date)`
*   `setMSecsSinceEpoch (self, int msecs)`
*   `setTime (self, QTime time)`
*   `setTime_t (self, int secsSince1Jan1970UTC)`
*   `setTimeSpec (self, Qt.TimeSpec spec)`
*   `QTime time (self)`
*   `Qt.TimeSpec timeSpec (self)`
*   `QDateTime toLocalTime (self)`
*   `int toMSecsSinceEpoch (self)`
*   `datetime.datetime toPyDateTime (self)`
*   `QString toString (self, Qt.DateFormat format = Qt.TextDate)`
*   `QString toString (self, QString format)`
*   `int toTime_t (self)`
*   `QDateTime toTimeSpec (self, Qt.TimeSpec spec)`
*   `QDateTime toUTC (self)`

### Static Methods

*   `QDateTime currentDateTime ()`
*   `QDateTime currentDateTimeUtc ()`
*   `int currentMSecsSinceEpoch ()`
*   `QDateTime fromMSecsSinceEpoch (int msecs)`
*   `QDateTime fromString (QString string, Qt.DateFormat format = Qt.TextDate)`
*   `QDateTime fromString (QString s, QString format)`
*   `QDateTime fromTime_t (int secsSince1Jan1970UTC)`

### Special Methods

*   `int __bool__ (self)`
*   `bool __eq__ (self, QDateTime other)`
*   `bool __ge__ (self, QDateTime other)`
*   `bool __gt__ (self, QDateTime other)`
*   `int __hash__ (self)`
*   `bool __le__ (self, QDateTime other)`
*   `bool __lt__ (self, QDateTime other)`
*   `bool __ne__ (self, QDateTime other)`
*   `str __repr__ (self)`

* * *

## Detailed Description

这个类可以醃制。

也可以使用一个Python的datetime对象，每当一个[QDateTime](qdatetime.html)预计。

该QDateTime类提供​​日期和时间函数。

一个QDateTime对象包含一个日历日期和时钟时间（一个“日期时间” ） 。它是一个组合[QDate](qdate.html)和[QTime](qtime.html)类。它可以从系统时钟读取当前的日期时间。它提供的功能来比较日期时间以及通过增加秒数，天，月或年操纵一个日期时间。

一个QDateTime对象通常创建无论是在构造函数中给出的日期和时间明确，或者使用静态函数[currentDateTime](qdatetime.html#currentDateTime)（ ），返回设定到系统时钟的时间QDateTime对象。的日期和时间可以与被改变[setDate](qdatetime.html#setDate)（）和[setTime](qdatetime.html#setTime)（ ） 。日期时间也可以使用设置[setTime_t](qdatetime.html#setTime_t)（ ）函数，它接受一个符合POSIX标准的“秒数以来00:00:00 1970年1月”的价值。该[fromString](qdatetime.html#fromString)（ ）函数返回一个QDateTime ，给定一个字符串，用于在字符串中解释日期的日期格式。

该[date](qdatetime.html#date)（）和[time](qdatetime.html#time)（ ）函数提供了访问的日期和时间部分的日期时间的。相同的信息被提供以文本格式[toString](qdatetime.html#toString)（）函数。

QDateTime提供了一整套运营商来比较两个QDateTime对象，其中较小的手段更早和更大的手段更高版本。

你可以递增（或递减）日期时间按毫秒的使用给定的数[addMSecs](qdatetime.html#addMSecs)（） ，用秒[addSecs](qdatetime.html#addSecs)（ ） ，或者使用天[addDays](qdatetime.html#addDays)（ ） 。同样，您可以使用[addMonths](qdatetime.html#addMonths)（）和[addYears](qdatetime.html#addYears)（ ） 。该[daysTo](qdatetime.html#daysTo)（ ）函数返回天两个日期时间之间的数，[secsTo](qdatetime.html#secsTo)（ ）返回的秒数2日期时间之间，并[msecsTo](qdatetime.html#msecsTo)（ ）返回两个日期时间之间的毫秒数。

QDateTime日期时间可作为存储[local time](qt.html#TimeSpec-enum)或[UTC](qt.html#TimeSpec-enum)。[QDateTime.currentDateTime](qdatetime.html#currentDateTime)（ ）返回一个QDateTime表示为本地时间;使用[toUTC](qdatetime.html#toUTC)（）将其转换为UTC。您也可以使用[timeSpec](qdatetime.html#timeSpec)（）来找出是否一个QDateTime对象存储UTC时间或本地时间。操作如[addSecs](qdatetime.html#addSecs)（）和[secsTo](qdatetime.html#secsTo)（ ）都知道的日光节约时间（DST ） 。

**Note:**QDateTime不佔闰秒。

#### Use of Gregorian and Julian Calendars

[QDate](qdate.html)使用在所有语言环境公历， 1582年10月开始的日期15 。对于日期截至及包括1582年10月4日，儒略历被使用。这意味着有一个10天的差距在1582年10月4日和15日之间的内部日历。当您使用QDateTime的日期在那个时代， 1582年10月4日之后的一天是1582年10月15日，和日期的差距是无效的。

朱利安在这里使用的公历转换日期是首次引入公历，由罗马教皇格里高利十三日。这变化是没有被普遍接受，一些地方只执行它在稍后的日期（如果有的话） 。 QDateTime不采取任何这些历史事实考虑在内。如果应用程序必须支持区域设置特定的约会系统，它必须这样做对自己，记住要转换使用儒略日的日期。

#### No Year 0

没有0年。在这一年的日期将被视为无效。当年-1是今年“ 1基督之前”或“ 1日前电流的时代。 ” 0001-01-01前一天是12月31日， 1 BCE 。

#### Range of Valid Dates

有效的日期范围是从1月2日， 4713 BCE ，到某个时候在今年1100万CE认证。儒略日传回[QDate.toJulianDay](qdate.html#toJulianDay)（）是一个数字，在连续的范围从1到_overflow_，甚至跨越QDateTime的“日漏洞” 。它适合于应用程序，必须转换QDateTime为日期在另一日历系统，例如，希伯来文，伊斯兰或中国使用。

公历中引入了世界各地不同的地方不同的日期。 QDateTime用途[QDate](qdate.html)存储日期，所以它使用的公历为所有区域设置，开始日期1582年10月15日。对于日期截至及包括1582年10月4日， QDateTime使用儒略历。这意味着有一个10天的差距，在QDateTime历1582年10月4日和15日之间。当您使用QDateTime的日期在那个时代， 1582年10月4日之后的一天是1582年10月15日，和日期的差距是无效的。

#### Use of System Timezone

QDateTime使用系统的时区信息来确定与UTC本地时间的偏移量。如果系统没有正确或不切合最新的配置， QDateTime会给出错误的结果也是如此。

#### Daylight Savings Time (DST)

QDateTime时与夏令时处理考虑到了系统的时区信息。在现代的Unix系统，这意味着它时，应用正确的历史DST数据的可能。在Windows和Windows CE ，那里的系统不支持DST的历史数据，历史精度不能保持相对的DST 。

DST同时考虑到有效的日期范围是1970-01-01到现在，和规则到位正确处理DST ，直到2037年12月31日，但这些可能会改变。对于日期的范围外时， QDateTime使_best guess_使用规则1970或2037年，但我们不能保证准确性。这意味着QDateTime没有考虑到在一个区域的时区帐户更改1970年以前，即使系统的时区数据库支持的信息。

* * *

## Method Documentation

```
QDateTime.__init__ (self)
```

构造一个空的日期时间（即空的日期和空时间） 。一个空的日期时间是无效的，因为日期是无效的。

**See also** [isValid](qdatetime.html#isValid)（ ） 。

```
QDateTime.__init__ (self, QDateTime other)
```

构造一个日期时间与给定_date_时，有效时间（ 00:00:00.000 ） ，并设置[timeSpec](qdatetime.html#timeSpec)（）来[Qt.LocalTime](qt.html#TimeSpec-enum)。

```
QDateTime.__init__ (self, QDate)
```

构造一个日期时间与给定_date_和_time_，通过使用规定的时间规范_spec_。

If _date_是有效的和_time_不，时间将被设置为午夜。

```
QDateTime.__init__ (self, QDate date, QTime time, Qt.TimeSpec timeSpec = Qt.LocalTime)
```

构造的一个副本_other_日期时间。

```
QDateTime.__init__ (self, int y, int m, int d, int h, int m, int s = 0, int msec = 0, int timeSpec = 0)
```

```
QDateTime QDateTime.addDays (self, int days)
```

[](qdatetime.html)

[返回](qdatetime.html)[QDateTime](qdatetime.html)对象包含日期时间_ndays_天迟于该对象的日期时间（或更早，如果_ndays_是负的） 。

**See also** [daysTo](qdatetime.html#daysTo)（ ）[addMonths](qdatetime.html#addMonths)（ ）[addYears](qdatetime.html#addYears)（）和[addSecs](qdatetime.html#addSecs)（ ） 。

```
QDateTime QDateTime.addMonths (self, int months)
```

[](qdatetime.html)

[返回](qdatetime.html)[QDateTime](qdatetime.html)对象包含日期时间_nmonths_个月后比这个对象的日期时间（或更早版本，如果_nmonths_是负的） 。

**See also** [daysTo](qdatetime.html#daysTo)（ ）[addDays](qdatetime.html#addDays)（ ）[addYears](qdatetime.html#addYears)（）和[addSecs](qdatetime.html#addSecs)（ ） 。

```
QDateTime QDateTime.addMSecs (self, int msecs)
```

[](qdatetime.html)

[返回](qdatetime.html)[QDateTime](qdatetime.html)对象包含日期时间_msecs_毫秒迟于该对象的日期时间（或更早版本，如果_msecs_是负的） 。

**See also** [addSecs](qdatetime.html#addSecs)（ ）[msecsTo](qdatetime.html#msecsTo)（ ）[addDays](qdatetime.html#addDays)（ ）[addMonths](qdatetime.html#addMonths)（）和[addYears](qdatetime.html#addYears)（ ） 。

```
QDateTime QDateTime.addSecs (self, int secs)
```

[](qdatetime.html)

[返回](qdatetime.html)[QDateTime](qdatetime.html)对象包含日期时间_s_秒迟于该对象的日期时间（或更早版本，如果_s_是负的） 。

**See also** [addMSecs](qdatetime.html#addMSecs)（ ）[secsTo](qdatetime.html#secsTo)（ ）[addDays](qdatetime.html#addDays)（ ）[addMonths](qdatetime.html#addMonths)（）和[addYears](qdatetime.html#addYears)（ ） 。

```
QDateTime QDateTime.addYears (self, int years)
```

[](qdatetime.html)

[返回](qdatetime.html)[QDateTime](qdatetime.html)对象包含日期时间_nyears_年后比这个对象的日期时间（或更早版本，如果_nyears_是负的） 。

**See also** [daysTo](qdatetime.html#daysTo)（ ）[addDays](qdatetime.html#addDays)（ ）[addMonths](qdatetime.html#addMonths)（）和[addSecs](qdatetime.html#addSecs)（ ） 。

```
QDateTime QDateTime.currentDateTime ()
```

[

返回当前日期时间，所报告的系统时钟，在当地时区。

](qdatetime.html)

[**See also**](qdatetime.html) [currentDateTimeUtc](qdatetime.html#currentDateTimeUtc)（ ）[QDate.currentDate](qdate.html#currentDate)（ ）[QTime.currentTime](qtime.html#currentTime)（）和[toTimeSpec](qdatetime.html#toTimeSpec)（ ） 。

```
QDateTime QDateTime.currentDateTimeUtc ()
```

[

返回当前日期时间，所报告的系统时钟，以UTC 。

此功能被引入Qt的4.7 。

](qdatetime.html)

[**See also**](qdatetime.html) [currentDateTime](qdatetime.html#currentDateTime)（ ）[QDate.currentDate](qdate.html#currentDate)（ ）[QTime.currentTime](qtime.html#currentTime)（）和[toTimeSpec](qdatetime.html#toTimeSpec)（ ） 。

```
int QDateTime.currentMSecsSinceEpoch ()
```

返回毫秒自1970年以来-01- 01T00人数： 00:00世界标准时间。这个数字是像POSIX时间变量，但以毫秒为单位来代替。

此功能被引入Qt的4.7 。

**See also** [currentDateTime](qdatetime.html#currentDateTime)（ ）[currentDateTimeUtc](qdatetime.html#currentDateTimeUtc)（ ）[toTime_t](qdatetime.html#toTime_t)（）和[toTimeSpec](qdatetime.html#toTimeSpec)（ ） 。

```
QDate QDateTime.date (self)
```

[

返回日期时间的日期部分。

](qdate.html)

[**See also**](qdate.html) [setDate](qdatetime.html#setDate)（ ）[time](qdatetime.html#time)（）和[timeSpec](qdatetime.html#timeSpec)（ ） 。

```
int QDateTime.daysTo (self, QDateTime)
```

返回从该日期时间的天数，以本_other_日期时间。如果_other_日期时间早于这个日期，返回的值是负的。

**See also** [addDays](qdatetime.html#addDays)（ ）[secsTo](qdatetime.html#secsTo)（）和[msecsTo](qdatetime.html#msecsTo)（ ） 。

```
QDateTime QDateTime.fromMSecsSinceEpoch (int msecs)
```

[](qdatetime.html)

[返回日期时间的日期和时间的毫秒数，_msecs_，自1970年以来-01- 01T00已通过： 00:00.000 ，协调世界时（](qdatetime.html)[Qt.UTC](qt.html#TimeSpec-enum)） 。在不支持时区的系统，时间将被设置为如果本地时间是[Qt.UTC](qt.html#TimeSpec-enum)。

注意，有可能的值_msecs_这个谎言之外的有效范围[QDateTime](qdatetime.html)，正面和负面的。这个函数的行为是未定义的值。

此功能被引入Qt的4.7 。

**See also** [toTime_t](qdatetime.html#toTime_t)（）和[setTime_t](qdatetime.html#setTime_t)（ ） 。

```
QDateTime QDateTime.fromString (QString string, Qt.DateFormat format = Qt.TextDate)
```

[](qdatetime.html)

[返回](qdatetime.html)[QDateTime](qdatetime.html)由表示_string_使用_format_定，或无效的日期时间，如果这是不可能的。

注意事项[Qt.TextDate](qt.html#DateFormat-enum)：建议您使用英文短的月份名称（例如“扬” ） 。虽然本地化月名也可以使用，它们依赖于用户的区域设置。

```
QDateTime QDateTime.fromString (QString s, QString format)
```

[](qdatetime.html)

[返回](qdatetime.html)[QDateTime](qdatetime.html)由表示_string_使用_format_给予，或无效的日期时间，如果该字符串无法解析。

这些表达式可以用于格式字符串的日期部分：

| Expression | Output |
| --- | --- |
| d | the day as number without a leading zero (1 to 31) |
| dd | the day as number with a leading zero (01 to 31) |
| ddd | the abbreviated localized day name (e.g. 'Mon' to 'Sun'). Uses [QDate.shortDayName](qdate.html#shortDayName)(). |
| dddd | the long localized day name (e.g. 'Monday' to 'Sunday'). Uses [QDate.longDayName](qdate.html#longDayName)(). |
| M | the month as number without a leading zero (1-12) |
| MM | the month as number with a leading zero (01-12) |
| MMM | the abbreviated localized month name (e.g. 'Jan' to 'Dec'). Uses [QDate.shortMonthName](qdate.html#shortMonthName)(). |
| MMMM | the long localized month name (e.g. 'January' to 'December'). Uses [QDate.longMonthName](qdate.html#longMonthName)(). |
| yy | the year as two digit number (00-99) |
| yyyy | the year as four digit number |

**Note:**不同于其他版本的功能，日期和月份名称必须在用户的本地语言来给出。它是唯一可以使用的英文名称，如果用户的语言是英语。

这些表达式可以用于格式字符串的时间部分：

| Expression | Output |
| --- | --- |
| h | the hour without a leading zero (0 to 23 or 1 to 12 if AM/PM display) |
| hh | the hour with a leading zero (00 to 23 or 01 to 12 if AM/PM display) |
| H | the hour without a leading zero (0 to 23, even with AM/PM display) |
| HH | the hour with a leading zero (00 to 23, even with AM/PM display) |
| m | the minute without a leading zero (0 to 59) |
| mm | the minute with a leading zero (00 to 59) |
| s | the second without a leading zero (0 to 59) |
| ss | the second with a leading zero (00 to 59) |
| z | the milliseconds without leading zeroes (0 to 999) |
| zzz | the milliseconds with leading zeroes (000 to 999) |
| AP or A | interpret as an AM/PM time. _AP_ must be either "AM" or "PM". |
| ap or a | Interpret as an AM/PM time. _ap_ must be either "am" or "pm". |

所有其他输入的字符将被视为文本。括在singlequotes任何字符序列也将被视为文本，而不是被用作表达。

```
 [QTime](qtime.html) time1 = [QTime](qtime.html).fromString("131", "HHh");
 // time1 is 13:00:00
 [QTime](qtime.html) time1 = [QTime](qtime.html).fromString("1apA", "1amAM");
 // time1 is 01:00:00

 [QDateTime](qdatetime.html) dateTime2 = [QDateTime](qdatetime.html).fromString("M1d1y9800:01:02",
                                             "'M'M'd'd'y'yyhh:mm:ss");
 // dateTime is 1 January 1998 00:01:02

```

如果该格式不被满足的无效[QDateTime](qdatetime.html)返回。没有前导零（ D， M，H ， M，S ， Z）的表达式将是贪婪的。这意味着，他们将使用两个数字，即使这将使他们的范围之外和/或离开过几位其他部分。

```
 [QDateTime](qdatetime.html) dateTime = [QDateTime](qdatetime.html).fromString("130", "Mm"); // invalid

```

这可能意味着1月1日00:30.50但M将抢两位数。

对于未在格式表示任何领域使用以下缺省值：

| Field | Default value |
| --- | --- |
| Year | 1900 |
| Month | 1 (January) |
| Day | 1 |
| Hour | 0 |
| Minute | 0 |
| Second | 0 |

例如：

```
 [QDateTime](qdatetime.html) dateTime = [QDateTime](qdatetime.html).fromString("1.30.1", "M.d.s");
 // dateTime is January 30 in 1900 at 00:00:01.

```

[QDateTime.toString](qdatetime.html#toString)（ ）[QTime.toString](qtime.html#toString)（ ）

**See also** [QDate.fromString](qdate.html#fromString)（ ）[QTime.fromString](qtime.html#fromString)（）和[QDate.toString](qdate.html#toString)（ ） 。

```
QDateTime QDateTime.fromTime_t (int secsSince1Jan1970UTC)
```

[](qdatetime.html)

[返回日期时间的日期和时间是多少_seconds_自1970年以来-01- 01T00已通过：00:00 ，协调世界时（](qdatetime.html)[Qt.UTC](qt.html#TimeSpec-enum)） 。在不支持时区的系统，时间将被设置为如果本地时间是[Qt.UTC](qt.html#TimeSpec-enum)。

这个函数中引入了Qt 4.2中。

**See also** [toTime_t](qdatetime.html#toTime_t)（）和[setTime_t](qdatetime.html#setTime_t)（ ） 。

```
bool QDateTime.isNull (self)
```

返回True如果这两个日期和时间为空，否则返回False 。一个空的日期时间是无效的。

**See also** [QDate.isNull](qdate.html#isNull)（ ）[QTime.isNull](qtime.html#isNull)（）和[isValid](qdatetime.html#isValid)（ ） 。

```
bool QDateTime.isValid (self)
```

返回True如果这两个日期和时间都是有效的，否则返回False 。

**See also** [QDate.isValid](qdate.html#isValid)（）和[QTime.isValid](qtime.html#isValid)（ ） 。

```
int QDateTime.msecsTo (self, QDateTime)
```

返回的毫秒数从这个日期时间到_other_日期时间。如果_other_日期时间早于这个日期，返回的值是负的。

前执行比较，这两个日期时间转换为[Qt.UTC](qt.html#TimeSpec-enum)以保证结果是正确的，如果两个日期时间中的一个已经日光节约时间（DST ）和其他没有。

此功能被引入Qt的4.7 。

**See also** [addMSecs](qdatetime.html#addMSecs)（ ）[daysTo](qdatetime.html#daysTo)（）和[QTime.msecsTo](qtime.html#msecsTo)（ ） 。

```
int QDateTime.secsTo (self, QDateTime)
```

返回的秒数从这个日期到_other_日期时间。如果_other_日期时间早于这个日期，返回的值是负的。

前执行比较，这两个日期时间转换为[Qt.UTC](qt.html#TimeSpec-enum)以保证结果是正确的，如果两个日期时间中的一个已经日光节约时间（DST ）和其他没有。

例如：

```
 [QDateTime](qdatetime.html) now = [QDateTime](qdatetime.html).currentDateTime();
 [QDateTime](qdatetime.html) xmas([QDate](qdate.html)(now.date().year(), 12, 25), [QTime](qtime.html)(0, 0));
 qDebug("There are %d seconds to Christmas", now.secsTo(xmas));

```

**See also** [addSecs](qdatetime.html#addSecs)（ ）[daysTo](qdatetime.html#daysTo)（）和[QTime.secsTo](qtime.html#secsTo)（ ） 。

```
QDateTime.setDate (self, QDate date)
```

设置此日期时间的日期部分，以_date_。如果没有时间被设置，它被设定为午夜。

**See also** [date](qdatetime.html#date)（ ）[setTime](qdatetime.html#setTime)（）和[setTimeSpec](qdatetime.html#setTimeSpec)（ ） 。

```
QDateTime.setMSecsSinceEpoch (self, int msecs)
```

设置给定的毫秒数的日期和时间，_msecs_，自1970年以来-01- 01T00已通过： 00:00.000 ，协调世界时（[Qt.UTC](qt.html#TimeSpec-enum)） 。在不支持时区，此功能系统的行为就好像本地时间分别为[Qt.UTC](qt.html#TimeSpec-enum)。

注意，有可能的值_msecs_这个谎言之外的有效范围[QDateTime](qdatetime.html)，正面和负面的。这个函数的行为是未定义的值。

此功能被引入Qt的4.7 。

**See also** [toMSecsSinceEpoch](qdatetime.html#toMSecsSinceEpoch)（）和[setTime_t](qdatetime.html#setTime_t)（ ） 。

```
QDateTime.setTime (self, QTime time)
```

设置此日期时间的时间部分_time_。

**See also** [time](qdatetime.html#time)（ ）[setDate](qdatetime.html#setDate)（）和[setTimeSpec](qdatetime.html#setTimeSpec)（ ） 。

```
QDateTime.setTime_t (self, int secsSince1Jan1970UTC)
```

设置给定数量的日期和时间_seconds_自1970年以来-01- 01T00已通过：00:00 ，协调世界时（[Qt.UTC](qt.html#TimeSpec-enum)） 。在不支持时区，此功能系统的行为就好像本地时间分别为[Qt.UTC](qt.html#TimeSpec-enum)。

**See also** [toTime_t](qdatetime.html#toTime_t)（ ） 。

```
QDateTime.setTimeSpec (self, Qt.TimeSpec spec)
```

设定这个日期时间用于时间规范_spec_。

**See also** [timeSpec](qdatetime.html#timeSpec)（ ）[setDate](qdatetime.html#setDate)（ ）[setTime](qdatetime.html#setTime)（）和[Qt.TimeSpec](qt.html#TimeSpec-enum)。

```
QTime QDateTime.time (self)
```

[

返回日期时间的时间部分。

](qtime.html)

[**See also**](qtime.html) [setTime](qdatetime.html#setTime)（ ）[date](qdatetime.html#date)（）和[timeSpec](qdatetime.html#timeSpec)（ ） 。

```
Qt.TimeSpec QDateTime.timeSpec (self)
```

[

返回日期时间的时间规范。

](qt.html#TimeSpec-enum)

[**See also**](qt.html#TimeSpec-enum) [setTimeSpec](qdatetime.html#setTimeSpec)（ ）[date](qdatetime.html#date)（ ）[time](qdatetime.html#time)（）和[Qt.TimeSpec](qt.html#TimeSpec-enum)。

```
QDateTime QDateTime.toLocalTime (self)
```

[](qdatetime.html)

[返回包含此日期时间的日期和时间信息的日期时间，但使用指定的](qdatetime.html)[Qt.LocalTime](qt.html#TimeSpec-enum)的定义。

**See also** [toTimeSpec](qdatetime.html#toTimeSpec)（ ） 。

```
int QDateTime.toMSecsSinceEpoch (self)
```

返回日期时间为自1970年以来-01- 01T00已通过的毫秒数： 00:00.000 ，协调世界时（[Qt.UTC](qt.html#TimeSpec-enum)） 。

在不支持时区的系统，这个功能的行为就好像本地时间分别为[Qt.UTC](qt.html#TimeSpec-enum)。

此函数的行为是不确定的，如果存储在此对象的日期时间是无效的。然而，对于所有有效日期，此函数返回一个唯一的值。

此功能被引入Qt的4.7 。

**See also** [toTime_t](qdatetime.html#toTime_t)（）和[setMSecsSinceEpoch](qdatetime.html#setMSecsSinceEpoch)（ ） 。

```
datetime.datetime QDateTime.toPyDateTime (self)
```

```
QString QDateTime.toString (self, Qt.DateFormat format = Qt.TextDate)
```

返回日期时间为一个字符串。该_format_参数决定了结果字符串的格式。

这些表达式可以用于日期：

| Expression | Output |
| --- | --- |
| d | the day as number without a leading zero (1 to 31) |
| dd | the day as number with a leading zero (01 to 31) |
| ddd | the abbreviated localized day name (e.g. 'Mon' to 'Sun'). Uses [QDate.shortDayName](qdate.html#shortDayName)(). |
| dddd | the long localized day name (e.g. 'Monday' to '[Qt.Sunday](qt.html#DayOfWeek-enum)'). Uses [QDate.longDayName](qdate.html#longDayName)(). |
| M | the month as number without a leading zero (1-12) |
| MM | the month as number with a leading zero (01-12) |
| MMM | the abbreviated localized month name (e.g. 'Jan' to 'Dec'). Uses [QDate.shortMonthName](qdate.html#shortMonthName)(). |
| MMMM | the long localized month name (e.g. 'January' to 'December'). Uses [QDate.longMonthName](qdate.html#longMonthName)(). |
| yy | the year as two digit number (00-99) |
| yyyy | the year as four digit number |

这些表达式可以用于时间：

| Expression | Output |
| --- | --- |
| h | the hour without a leading zero (0 to 23 or 1 to 12 if AM/PM display) |
| hh | the hour with a leading zero (00 to 23 or 01 to 12 if AM/PM display) |
| m | the minute without a leading zero (0 to 59) |
| mm | the minute with a leading zero (00 to 59) |
| s | the second without a leading zero (0 to 59) |
| ss | the second with a leading zero (00 to 59) |
| z | the milliseconds without leading zeroes (0 to 999) |
| zzz | the milliseconds with leading zeroes (000 to 999) |
| AP | use AM/PM display. _AP_ will be replaced by either "AM" or "PM". |
| ap | use am/pm display. _ap_ will be replaced by either "am" or "pm". |

所有其它输入的字符将被忽略。括在singlequotes任何字符序列将被视为文本，而不是被用作表达。连续两singlequotes （ “''” ）是由singlequote输出所取代。

例如格式字符串（假设[QDateTime](qdatetime.html)是2001年5月21日14点13分09秒） ：

| Format | Result |
| --- | --- |
| dd.MM.yyyy | 21.05.2001 |
| ddd MMMM d yy | Tue May 21 01 |
| hh:mm:ss.zzz | 14:13:09.042 |
| h:m:s ap | 2:13:9 pm |

如果日期时间是无效的，空字符串将被返回。

**See also** [QDate.toString](qdate.html#toString)（）和[QTime.toString](qtime.html#toString)（ ） 。

```
QString QDateTime.toString (self, QString format)
```

这是一个重载函数。

返回日期时间的字符串中的_format_给出。

如果_format_ is [Qt.TextDate](qt.html#DateFormat-enum)，该字符串被格式化的默认方式。[QDate.shortDayName](qdate.html#shortDayName)（ ）[QDate.shortMonthName](qdate.html#shortMonthName)（）和[QTime.toString](qtime.html#toString)（）是用来产生该字符串，所以日期和月份名称将本地化的名称。这种格式的一个例子是“周三5月20日03:40:13 1998” 。

如果_format_ is [Qt.ISODate](qt.html#DateFormat-enum)，字符串格式对应于ISO 8601扩展规格的日期和时间的表示，采取的形式为YYYY- MM- DDTHH ： MM：SS [Z | [ + | - ] HH ： MM] ，视[timeSpec](qdatetime.html#timeSpec)（）的[QDateTime](qdatetime.html)。如果[timeSpec](qdatetime.html#timeSpec)（）是[Qt.UTC](qt.html#TimeSpec-enum)，Z将被附加到字符串;如果[timeSpec](qdatetime.html#timeSpec)（）是[Qt.OffsetFromUTC](qt.html#TimeSpec-enum)相对于UTC的偏移，以小时和分钟会被附加到字符串。

如果_format_ is [Qt.SystemLocaleShortDate](qt.html#DateFormat-enum) or [Qt.SystemLocaleLongDate](qt.html#DateFormat-enum)，字符串格式取决于系统的区域设置。相同的调用[QLocale.system](qlocale.html#system)（ ） 。的toString （日期时间，[QLocale.ShortFormat](qlocale.html#FormatType-enum)）或[QLocale.system](qlocale.html#system)（ ） 。的toString （日期时间，[QLocale.LongFormat](qlocale.html#FormatType-enum)） 。

如果_format_ is [Qt.DefaultLocaleShortDate](qt.html#DateFormat-enum) or [Qt.DefaultLocaleLongDate](qt.html#DateFormat-enum)，字符串格式依赖于默认应用程序的语言环境。这就是语言环境设置[QLocale.setDefault](qlocale.html#setDefault)（ ）或系统区域设置，如果没有默认区域设置已定。相同的调用QLocale （ ） 。的toString （日期时间，[QLocale.ShortFormat](qlocale.html#FormatType-enum)）或QLocale （ ） 。的toString （日期时间，[QLocale.LongFormat](qlocale.html#FormatType-enum)） 。

如果日期时间是无效的，空字符串将被返回。

**Warning:**该[Qt.ISODate](qt.html#DateFormat-enum)格式仅适用于年范围为0 〜9999 。这种限制可能适用于区域设置的格式为好，这取决于区域设置。

**See also** [QDate.toString](qdate.html#toString)（ ）[QTime.toString](qtime.html#toString)（）和[Qt.DateFormat](qt.html#DateFormat-enum)。

```
int QDateTime.toTime_t (self)
```

返回日期时间为自1970年以来-01- 01T00已通过秒数：00:00 ，协调世界时（[Qt.UTC](qt.html#TimeSpec-enum)） 。

在不支持时区的系统，这个功能的行为就好像本地时间分别为[Qt.UTC](qt.html#TimeSpec-enum)。

**Note:**这个函数返回一个32位的无符号整数，所以在1970年之前它不支持日期，但它2038- 01 - 19T03后支持日期： 14:06 ，这可能不是有效的time_t值。通过这些time_t的值的系统功能时一定要小心，这可能将其解释为负的日期。

如果日期是输入1970 -01- 01T00外： 00:00至2106 - 02 - 07T06 ： 28:14 ，该函数返回-1转换为一个无符号整数（即0xFFFFFFFF的） 。

为了得到一个扩展量程，使用[toMSecsSinceEpoch](qdatetime.html#toMSecsSinceEpoch)（ ） 。

**See also** [toMSecsSinceEpoch](qdatetime.html#toMSecsSinceEpoch)（）和[setTime_t](qdatetime.html#setTime_t)（ ） 。

```
QDateTime QDateTime.toTimeSpec (self, Qt.TimeSpec spec)
```

[

返回此日期时间的设定为使用给定的时间副本_specification_。

](qdatetime.html)

[**See also**](qdatetime.html) [timeSpec](qdatetime.html#timeSpec)（ ）[toUTC](qdatetime.html#toUTC)（）和[toLocalTime](qdatetime.html#toLocalTime)（ ） 。

```
QDateTime QDateTime.toUTC (self)
```

[](qdatetime.html)

[返回包含此日期时间的日期和时间信息的日期时间，但使用指定的](qdatetime.html)[Qt.UTC](qt.html#TimeSpec-enum)的定义。

**See also** [toTimeSpec](qdatetime.html#toTimeSpec)（ ） 。

```
int QDateTime.__bool__ (self)
```

```
bool QDateTime.__eq__ (self, QDateTime other)
```

```
bool QDateTime.__ge__ (self, QDateTime other)
```

```
bool QDateTime.__gt__ (self, QDateTime other)
```

```
int QDateTime.__hash__ (self)
```

```
bool QDateTime.__le__ (self, QDateTime other)
```

```
bool QDateTime.__lt__ (self, QDateTime other)
```

```
bool QDateTime.__ne__ (self, QDateTime other)
```

```
str QDateTime.__repr__ (self)
```