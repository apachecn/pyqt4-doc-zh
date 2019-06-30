# QDate Class Reference

## [[QtCore](index.htm) module]

该的QDate类提供​​的日期函数。[More...](#details)

### Types

*   `enum MonthNameType { DateFormat, StandaloneFormat }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, int y, int m, int d)`
*   `__init__ (self, QDate)`
*   `QDate addDays (self, int days)`
*   `QDate addMonths (self, int months)`
*   `QDate addYears (self, int years)`
*   `int day (self)`
*   `int dayOfWeek (self)`
*   `int dayOfYear (self)`
*   `int daysInMonth (self)`
*   `int daysInYear (self)`
*   `int daysTo (self, QDate)`
*   `(int year, int month, int day) getDate (self)`
*   `bool isNull (self)`
*   `bool isValid (self)`
*   `int month (self)`
*   `bool setDate (self, int year, int month, int date)`
*   `bool setYMD (self, int y, int m, int d)`
*   `int toJulianDay (self)`
*   `datetime.date toPyDate (self)`
*   `QString toString (self, Qt.DateFormat format = Qt.TextDate)`
*   `QString toString (self, QString format)`
*   `(int, int yearNumber) weekNumber (self)`
*   `int year (self)`

### Static Methods

*   `QDate currentDate ()`
*   `QDate fromJulianDay (int jd)`
*   `QDate fromString (QString string, Qt.DateFormat format = Qt.TextDate)`
*   `QDate fromString (QString s, QString format)`
*   `int gregorianToJulian (int y, int m, int d)`
*   `bool isLeapYear (int year)`
*   `bool isValid (int y, int m, int d)`
*   `(int y, int m, int d) julianToGregorian (int jd)`
*   `QString longDayName (int weekday)`
*   `QString longDayName (int weekday, MonthNameType type)`
*   `QString longMonthName (int month)`
*   `QString longMonthName (int month, MonthNameType type)`
*   `QString shortDayName (int weekday)`
*   `QString shortDayName (int weekday, MonthNameType type)`
*   `QString shortMonthName (int month)`
*   `QString shortMonthName (int month, MonthNameType type)`

### Special Methods

*   `int __bool__ (self)`
*   `bool __eq__ (self, QDate other)`
*   `bool __ge__ (self, QDate other)`
*   `bool __gt__ (self, QDate other)`
*   `int __hash__ (self)`
*   `bool __le__ (self, QDate other)`
*   `bool __lt__ (self, QDate other)`
*   `bool __ne__ (self, QDate other)`
*   `str __repr__ (self)`

* * *

## Detailed Description

这个类可以醃制。

可以使用Python的日期对象，每当一个[QDate](qdate.html)预计。

该的QDate类提供​​的日期函数。

一个的QDate对象包含一个日历日期，即年，月和日的数字，在公历。 （见[Use of Gregorian and Julian Calendars](#qdate-g-and-j)对于之前的日期10月15日1582年） 。它可以从系统时钟读取当前的日期。它提供的功能来比较日期和操作日期。例如，它可以添加和减去天，月和年的日期。

一个的QDate对象通常是通过明确给出的年，月和日的数字创造。注意的QDate解释两位数字的年份原样，即年0 - 99 。一个的QDate也可以与静态构造函数[currentDate](qdate.html#currentDate)（），它创建一个包含系统时钟的日期的QDate对象。一个明确的日期，也可以使用设置[setDate](qdate.html#setDate)（ ） 。该[fromString](qdate.html#fromString)（ ）函数返回给定一个字符串，它用于在字符串中解释日期的日期格式的QDate 。

该[year](qdate.html#year)（ ）[month](qdate.html#month)（）和[day](qdate.html#day)（ ）函数提供访问年，月和日的数字。另外，[dayOfWeek](qdate.html#dayOfWeek)（）和[dayOfYear](qdate.html#dayOfYear)（ ）函数提供的。相同的信息被提供以文本格式[toString](qdate.html#toString)（ ）[shortDayName](qdate.html#shortDayName)（ ）[longDayName](qdate.html#longDayName)（ ）[shortMonthName](qdate.html#shortMonthName)（）和[longMonthName](qdate.html#longMonthName)（）函数。

的QDate提供了一整套运营商来比较两个的QDate对象，其中较小的手段更早和更大的手段更高版本。

你可以递增（或递减）的日期的天使用给定的数[addDays](qdate.html#addDays)（ ） 。同样，您可以使用[addMonths](qdate.html#addMonths)（）和[addYears](qdate.html#addYears)（ ） 。该[daysTo](qdate.html#daysTo)（ ）函数返回两个日期之间的天数。

该[daysInMonth](qdate.html#daysInMonth)（）和[daysInYear](qdate.html#daysInYear)（ ）函数返回多少天有在此日期的月和年，分别。该[isLeapYear](qdate.html#isLeapYear)（ ）函数表示的日期是否是闰年。

#### Use of Gregorian and Julian Calendars

的QDate使用公历中的所有语言环境， 1582年10月开始的日期15 。对于日期截至及包括1582年10月4日，儒略历被使用。这意味着有一个10天的差距在1582年10月4日和15日之间的内部日历。当您使用[QDateTime](qdatetime.html)的日期在那个时代， 1582年10月4日之后的一天是1582年10月15日，和日期的差距是无效的。

朱利安在这里使用的公历转换日期是首次引入公历，由罗马教皇格里高利十三日。这变化是没有被普遍接受，一些地方只执行它在稍后的日期（如果有的话） 。[QDateTime](qdatetime.html)不采取任何这些历史事实考虑在内。如果应用程序必须支持区域设置特定的约会系统，它必须这样做对自己，记住要转换使用儒略日的日期。

#### No Year 0

没有0年。在这一年的日期将被视为无效。当年-1是今年“ 1基督之前”或“ 1日前电流的时代。 ” 0001-01-01前一天是12月31日， 1 BCE 。

#### Range of Valid Dates

有效的日期范围是从1月2日， 4713 BCE ，到某个时候在今年1100万CE认证。儒略日传回[QDate.toJulianDay](qdate.html#toJulianDay)（）是一个数字，在连续的范围从1到_overflow_，甚至跨越[QDateTime](qdatetime.html)的“日漏洞” 。它适合于使用在应用程序必须将一个[QDateTime](qdatetime.html)在另一个日历系统，例如，希伯来文，伊斯兰教还是中国的日期。

* * *

## Type Documentation

```
QDate.MonthNameType
```

这个枚举变量描述了用于月份名称的字符串表示的类型。

| Constant | Value | Description |
| --- | --- | --- |
| `QDate.DateFormat` | `0` | 这种类型的名称，可用于日期到字符串的格式。 |
| `QDate.StandaloneFormat` | `1` | 当你需要枚举数月或平日使用此类型。通常是独立的名称代表单数形式用大写第一个字母。 |

这个枚举被引入或修改的Qt 4.5 。

* * *

## Method Documentation

```
QDate.__init__ (self)
```

构造一个空的日期。空日期是无效的。

**See also** [isNull](qdate.html#isNull)（）和[isValid](qdate.html#isValid)（ ） 。

```
QDate.__init__ (self, int y, int m, int d)
```

构造一个日期与年份_y_，月_m_和日_d_。

如果指定的日期无效，未设定日期和[isValid](qdate.html#isValid)（ ）返回False 。之前， 1月2日公元前4713一个日期被视为无效。

**Warning:**年0〜99被解释为是，即年0-99 。

**See also** [isValid](qdate.html#isValid)（ ） 。

```
QDate.__init__ (self, QDate)
```

```
QDate QDate.addDays (self, int days)
```

[](qdate.html)

[返回](qdate.html)[QDate](qdate.html)对象包含日期_ndays_迟于该对象的日期（或更早版本，如果_ndays_是负的） 。

**See also** [addMonths](qdate.html#addMonths)（ ）[addYears](qdate.html#addYears)（）和[daysTo](qdate.html#daysTo)（ ） 。

```
QDate QDate.addMonths (self, int months)
```

[](qdate.html)

[返回](qdate.html)[QDate](qdate.html)对象包含日期_nmonths_迟于该对象的日期（或更早版本，如果_nmonths_是负的） 。

**Note:**如果结束日/月组合不在所产生的月/年存在，该函数将返回是最新的有效日期的日期。

**Warning:** [QDate](qdate.html)周围有天推出公历日期穴（工作日5 1582年10月14日（含） ，不存在） 。如果计算当年的一端，[QDate](qdate.html)将返回无论是10月4日或10月15日。

**See also** [addDays](qdate.html#addDays)（）和[addYears](qdate.html#addYears)（ ） 。

```
QDate QDate.addYears (self, int years)
```

[](qdate.html)

[返回](qdate.html)[QDate](qdate.html)对象包含日期_nyears_迟于该对象的日期（或更早版本，如果_nyears_是负的） 。

**Note:**如果结束日/月组合不在所产生的年存在（即，如果日期是2月29日及最后一年是不是闰年） ，该函数将返回是最新的有效日期的日期（即， 2月28日） 。

**See also** [addDays](qdate.html#addDays)（）和[addMonths](qdate.html#addMonths)（ ） 。

```
QDate QDate.currentDate ()
```

[

返回当前日期，所报告的系统时钟。

](qdate.html)

[**See also**](qdate.html) [QTime.currentTime](qtime.html#currentTime)（）和[QDateTime.currentDateTime](qdatetime.html#currentDateTime)（ ） 。

```
int QDate.day (self)
```

返回此日期的月份的天（ 1到31） 。

**See also** [year](qdate.html#year)（ ）[month](qdate.html#month)（）和[dayOfWeek](qdate.html#dayOfWeek)（ ） 。

```
int QDate.dayOfWeek (self)
```

返回工作日（ 1 =周一到7 =星期日）为这个日期。

**See also** [day](qdate.html#day)（ ）[dayOfYear](qdate.html#dayOfYear)（）和[Qt.DayOfWeek](qt.html#DayOfWeek-enum)。

```
int QDate.dayOfYear (self)
```

返回一年中的天（1到365或366的闰年）这个日期。

**See also** [day](qdate.html#day)（）和[dayOfWeek](qdate.html#dayOfWeek)（ ） 。

```
int QDate.daysInMonth (self)
```

返回天的月份数（ 28 〜31）这个日期。

**See also** [day](qdate.html#day)（）和[daysInYear](qdate.html#daysInYear)（ ） 。

```
int QDate.daysInYear (self)
```

返回天在该年的数字（ 365或366 ），这个日期。

**See also** [day](qdate.html#day)（）和[daysInMonth](qdate.html#daysInMonth)（ ） 。

```
int QDate.daysTo (self, QDate)
```

返回从这个日期的天数来_d_（这是否定的，如果_d_早于这个日期） 。

例如：

```
 [QDate](qdate.html) d1(1995, 5, 17);  // May 17, 1995
 [QDate](qdate.html) d2(1995, 5, 20);  // May 20, 1995
 d1.daysTo(d2);          // returns 3
 d2.daysTo(d1);          // returns -3

```

**See also** [addDays](qdate.html#addDays)（ ） 。

```
QDate QDate.fromJulianDay (int jd)
```

[](qdate.html)

[儒略日转换_jd_到](qdate.html)[QDate](qdate.html)。

**See also** [toJulianDay](qdate.html#toJulianDay)（ ） 。

```
QDate QDate.fromString (QString string, Qt.DateFormat format = Qt.TextDate)
```

[](qdate.html)

[返回](qdate.html)[QDate](qdate.html)由表示_string_使用_format_给予，或者如果该字符串无法解析无效的日期。

注意事项[Qt.TextDate](qt.html#DateFormat-enum)：建议您使用英文短的月份名称（例如“扬” ） 。虽然本地化月名也可以使用，它们依赖于用户的区域设置。

```
QDate QDate.fromString (QString s, QString format)
```

[](qdate.html)

[返回](qdate.html)[QDate](qdate.html)由表示_string_使用_format_给予，或者如果该字符串无法解析无效的日期。

这些表达式可以用于格式：

| Expression | Output |
| --- | --- |
| d | The day as a number without a leading zero (1 to 31) |
| dd | The day as a number with a leading zero (01 to 31) |
| ddd | The abbreviated localized day name (e.g. 'Mon' to 'Sun'). Uses [QDate.shortDayName](qdate.html#shortDayName)(). |
| dddd | The long localized day name (e.g. 'Monday' to 'Sunday'). Uses [QDate.longDayName](qdate.html#longDayName)(). |
| M | The month as a number without a leading zero (1 to 12) |
| MM | The month as a number with a leading zero (01 to 12) |
| MMM | The abbreviated localized month name (e.g. 'Jan' to 'Dec'). Uses [QDate.shortMonthName](qdate.html#shortMonthName)(). |
| MMMM | The long localized month name (e.g. 'January' to 'December'). Uses [QDate.longMonthName](qdate.html#longMonthName)(). |
| yy | The year as two digit number (00 to 99) |
| yyyy | The year as four digit number. If the year is negative, a minus sign is prepended in addition. |

所有其他输入的字符将被视为文本。括在单引号中的任何字符序列也将被视为文本，不会被用作表达式。例如：

```
 [QDate](qdate.html) date = [QDate](qdate.html).fromString("1MM12car2003", "d'MM'MMcaryyyy");
 // date is 1 December 2003

```

如果格式不符合，无效[QDate](qdate.html)返回。不指望前导零（ D，M ）中的表达式将是贪婪的。这意味着，他们将使用两个数字，即使这会放到屋外，价值观的接受范围，并留下了几个数字的其他部分。例如，下面的格式字符串可能意味着1月30日，但对M将抓住两个数字，从而导致无效的日期：

```
 [QDate](qdate.html) date = [QDate](qdate.html).fromString("130", "Md"); // invalid

```

对于未在格式表示任何领域使用以下缺省值：

| Field | Default value |
| --- | --- |
| Year | 1900 |
| Month | 1 |
| Day | 1 |

下面的例子演示了默认值：

```
 [QDate](qdate.html).fromString("1.30", "M.d");           // January 30 1900
 [QDate](qdate.html).fromString("20000110", "yyyyMMdd");  // January 10, 2000
 [QDate](qdate.html).fromString("20000110", "yyyyMd");    // January 10, 2000

```

**See also** [QDateTime.fromString](qdatetime.html#fromString)（ ）[QTime.fromString](qtime.html#fromString)（ ）[QDate.toString](qdate.html#toString)（ ）[QDateTime.toString](qdatetime.html#toString)（）和[QTime.toString](qtime.html#toString)（ ） 。

```
(int year, int month, int day) QDate.getDate (self)
```

提取日期的年，月，日，并为它们分配到*_year_*_month_和*_day_。指针可以为null 。

此功能被引入Qt的4.5 。

**See also** [year](qdate.html#year)（ ）[month](qdate.html#month)（ ）[day](qdate.html#day)（）和[isValid](qdate.html#isValid)（ ） 。

```
int QDate.gregorianToJulian (int y, int m, int d)
```

```
bool QDate.isLeapYear (int year)
```

返回True如果指定的_year_为闰年，否则返回False 。

```
bool QDate.isNull (self)
```

返回True如果date为空，否则返回False 。一个空的日期是无效的。

**Note:**此函数的行为等同于[isValid](qdate.html#isValid)（ ） 。

**See also** [isValid](qdate.html#isValid)（ ） 。

```
bool QDate.isValid (self)
```

返回True如果这个日期是有效的，否则返回False 。

**See also** [isNull](qdate.html#isNull)（ ） 。

```
bool QDate.isValid (int y, int m, int d)
```

这是一个重载函数。

返回True如果指定的日期（_year_，_month_和_day_）是有效的，否则返回False 。

例如：

```
 [QDate](qdate.html).isValid(2002, 5, 17);  // true
 [QDate](qdate.html).isValid(2002, 2, 30);  // false (Feb 30 does not exist)
 [QDate](qdate.html).isValid(2004, 2, 29);  // true (2004 is a leap year)
 [QDate](qdate.html).isValid(2000, 2, 29);  // true (2000 is a leap year)
 [QDate](qdate.html).isValid(2006, 2, 29);  // false (2006 is not a leap year)
 [QDate](qdate.html).isValid(2100, 2, 29);  // false (2100 is not a leap year)
 [QDate](qdate.html).isValid(1202, 6, 6);   // true (even though 1202 is pre-Gregorian)

```

**See also** [isNull](qdate.html#isNull)（）和[setDate](qdate.html#setDate)（ ） 。

```
(int y, int m, int d) QDate.julianToGregorian (int jd)
```

```
QString QDate.longDayName (int weekday)
```

返回长版的名称_weekday_。返回的名字是在正常的类型，它可以用于日期格式。

**See also** [toString](qdate.html#toString)（ ）[shortDayName](qdate.html#shortDayName)（ ）[shortMonthName](qdate.html#shortMonthName)（）和[longMonthName](qdate.html#longMonthName)（ ） 。

```
QString QDate.longDayName (int weekday, MonthNameType type)
```

返回的长名称_weekday_用于通过指定的代表性_type_。

天都使用以下约定列举：

*   1 = "Monday"
*   2 = "Tuesday"
*   3 = "Wednesday"
*   4 = "Thursday"
*   5 = "Friday"
*   6 = "Saturday"
*   7 = "Sunday"

各天的名称将根据系统的默认区域设置进行本地化。

此功能被引入Qt的4.5 。

**See also** [toString](qdate.html#toString)（ ）[shortDayName](qdate.html#shortDayName)（ ）[shortMonthName](qdate.html#shortMonthName)（）和[longMonthName](qdate.html#longMonthName)（ ） 。

```
QString QDate.longMonthName (int month)
```

返回长版的名称_month_。返回的名字是在正常的类型，它可以用于日期格式。

**See also** [toString](qdate.html#toString)（ ）[shortMonthName](qdate.html#shortMonthName)（ ）[shortDayName](qdate.html#shortDayName)（）和[longDayName](qdate.html#longDayName)（ ） 。

```
QString QDate.longMonthName (int month, MonthNameType type)
```

返回的长名称_month_用于通过指定的代表性_type_。

月均使用以下约定列举：

*   1 = "January"
*   2 = "February"
*   3 = "March"
*   4 = "April"
*   5 = "May"
*   6 = "June"
*   7 = "July"
*   8 = "August"
*   9 = "September"
*   10 = "October"
*   11 = "November"
*   12 = "December"

月份名称将根据系统的默认区域设置进行本地化。

此功能被引入Qt的4.5 。

**See also** [toString](qdate.html#toString)（ ）[shortMonthName](qdate.html#shortMonthName)（ ）[shortDayName](qdate.html#shortDayName)（）和[longDayName](qdate.html#longDayName)（ ） 。

```
int QDate.month (self)
```

返回对应于该日期的月份，使用以下约定数量：

*   1 = "January"
*   2 = "February"
*   3 = "March"
*   4 = "April"
*   5 = "May"
*   6 = "June"
*   7 = "July"
*   8 = "August"
*   9 = "September"
*   10 = "October"
*   11 = "November"
*   12 = "December"

**See also** [year](qdate.html#year)（）和[day](qdate.html#day)（ ） 。

```
bool QDate.setDate (self, int year, int month, int date)
```

设定日期的_year_，_month_和_day_。返回True如果日期是有效的，否则返回False 。

如果指定的日期是无效的，[QDate](qdate.html)对象被设置为无效。之前， 1月2日公元前4713的任何日期被视为无效。

这个函数中引入了Qt 4.2中。

**See also** [isValid](qdate.html#isValid)（ ） 。

```
bool QDate.setYMD (self, int y, int m, int d)
```

```
QString QDate.shortDayName (int weekday)
```

返回的是短版的名称_weekday_。返回的名字是在正常的类型，它可以用于日期格式。

**See also** [toString](qdate.html#toString)（ ）[longDayName](qdate.html#longDayName)（ ）[shortMonthName](qdate.html#shortMonthName)（）和[longMonthName](qdate.html#longMonthName)（ ） 。

```
QString QDate.shortDayName (int weekday, MonthNameType type)
```

返回的短名称_weekday_用于通过指定的代表性_type_。

天都使用以下约定列举：

*   1 = "Mon"
*   2 = "Tue"
*   3 = "Wed"
*   4 = "Thu"
*   5 = "Fri"
*   6 = "Sat"
*   7 = "Sun"

各天的名称将根据系统的默认区域设置进行本地化。

此功能被引入Qt的4.5 。

**See also** [toString](qdate.html#toString)（ ）[shortMonthName](qdate.html#shortMonthName)（ ）[longMonthName](qdate.html#longMonthName)（）和[longDayName](qdate.html#longDayName)（ ） 。

```
QString QDate.shortMonthName (int month)
```

返回的是短版的名称_month_。返回的名字是在正常的类型，它可以用于日期格式。

**See also** [toString](qdate.html#toString)（ ）[longMonthName](qdate.html#longMonthName)（ ）[shortDayName](qdate.html#shortDayName)（）和[longDayName](qdate.html#longDayName)（ ） 。

```
QString QDate.shortMonthName (int month, MonthNameType type)
```

返回的短名称_month_用于通过指定的代表性_type_。

月均使用以下约定列举：

*   1 = "Jan"
*   2 = "Feb"
*   3 = "Mar"
*   4 = "Apr"
*   5 = "May"
*   6 = "Jun"
*   7 = "Jul"
*   8 = "Aug"
*   9 = "Sep"
*   10 = "Oct"
*   11 = "Nov"
*   12 = "Dec"

月份名称将根据系统的默认区域设置进行本地化。

此功能被引入Qt的4.5 。

**See also** [toString](qdate.html#toString)（ ）[longMonthName](qdate.html#longMonthName)（ ）[shortDayName](qdate.html#shortDayName)（）和[longDayName](qdate.html#longDayName)（ ） 。

```
int QDate.toJulianDay (self)
```

日期转换为儒略日。

**See also** [fromJulianDay](qdate.html#fromJulianDay)（ ） 。

```
datetime.date QDate.toPyDate (self)
```

```
QString QDate.toString (self, Qt.DateFormat format = Qt.TextDate)
```

返回的日期字符串。该_format_参数决定了结果字符串的格式。

这些表达式可用于：

| Expression | Output |
| --- | --- |
| d | the day as number without a leading zero (1 to 31) |
| dd | the day as number with a leading zero (01 to 31) |
| ddd | the abbreviated localized day name (e.g. 'Mon' to 'Sun'). Uses [QDate.shortDayName](qdate.html#shortDayName)(). |
| dddd | the long localized day name (e.g. 'Monday' to 'Sunday'). Uses [QDate.longDayName](qdate.html#longDayName)(). |
| M | the month as number without a leading zero (1 to 12) |
| MM | the month as number with a leading zero (01 to 12) |
| MMM | the abbreviated localized month name (e.g. 'Jan' to 'Dec'). Uses [QDate.shortMonthName](qdate.html#shortMonthName)(). |
| MMMM | the long localized month name (e.g. 'January' to 'December'). Uses [QDate.longMonthName](qdate.html#longMonthName)(). |
| yy | the year as two digit number (00 to 99) |
| yyyy | the year as four digit number. If the year is negative, a minus sign is prepended in addition. |

所有其它输入的字符将被忽略。括在singlequotes任何字符序列将被视为文本，而不是被用作表达。连续两singlequotes （ “''” ）是由singlequote输出所取代。

例如格式字符串（假设[QDate](qdate.html)是1969年7月20日） ：

| Format | Result |
| --- | --- |
| dd.MM.yyyy | 20.07.1969 |
| ddd MMMM d yy | Sun July 20 69 |
| 'The day is' dddd | The day is Sunday |

如果日期时间是无效的，空字符串将被返回。

**Warning:**该[Qt.ISODate](qt.html#DateFormat-enum)格式仅适用于年范围为0 〜9999 。这种限制可能适用于区域设置的格式为好，这取决于区域设置。

**See also** [QDateTime.toString](qdatetime.html#toString)（）和[QTime.toString](qtime.html#toString)（ ） 。

```
QString QDate.toString (self, QString format)
```

这是一个重载函数。

返回的日期字符串。该_format_参数确定字符串的格式。

如果_format_ is [Qt.TextDate](qt.html#DateFormat-enum)，该字符串被格式化的默认方式。[QDate.shortDayName](qdate.html#shortDayName)（）和[QDate.shortMonthName](qdate.html#shortMonthName)（ ）用于生成字符串，所以日期和月份名称将使用默认语言环境从系统中本地化的名称。这种格式的一个例子是“星期六1995年5月20日” 。

如果_format_ is [Qt.ISODate](qt.html#DateFormat-enum)，字符串格式对应于ISO 8601扩展规格的日期和时间的表示，采取的形式为YYYY- MM- DD，其中YYYY是年， MM是一年中的月份（ 01〜 12 ） ，而DD是本月01到31之间的一天。

如果_format_ is [Qt.SystemLocaleShortDate](qt.html#DateFormat-enum) or [Qt.SystemLocaleLongDate](qt.html#DateFormat-enum)，字符串格式取决于系统的区域设置。相同的调用[QLocale.system](qlocale.html#system)（ ） 。的toString （日期，[QLocale.ShortFormat](qlocale.html#FormatType-enum)）或[QLocale.system](qlocale.html#system)（ ） 。的toString （日期，[QLocale.LongFormat](qlocale.html#FormatType-enum)） 。

如果_format_ is [Qt.DefaultLocaleShortDate](qt.html#DateFormat-enum) or [Qt.DefaultLocaleLongDate](qt.html#DateFormat-enum)，字符串格式依赖于默认应用程序的语言环境。这就是语言环境设置[QLocale.setDefault](qlocale.html#setDefault)（ ）或系统区域设置，如果没有默认区域设置已定。相同的调用QLocale （ ） 。的toString （日期，[QLocale.ShortFormat](qlocale.html#FormatType-enum)）或QLocale （ ） 。的toString （日期，[QLocale.LongFormat](qlocale.html#FormatType-enum)） 。

如果日期是无效的，空字符串将被返回。

**Warning:**该[Qt.ISODate](qt.html#DateFormat-enum)格式仅适用于年范围为0 〜9999 。这种限制可能适用于区域设置的格式为好，这取决于区域设置。

**See also** [shortDayName](qdate.html#shortDayName)（）和[shortMonthName](qdate.html#shortMonthName)（ ） 。

```
(int, int yearNumber) QDate.weekNumber (self)
```

返回的周数（ 1到53 ） ，并在今年存储在*_yearNumber_除非_yearNumber_为null （默认值） 。

返回0，如果日期是无效的。

按照ISO 8601 ，周从星期一开始，一年的第一个星期四是永远在那年的1周。大多数年份有52周，但有些53 。

*_yearNumber_并不总是相同[year](qdate.html#year)（ ） 。例如， 2000年1月1日在1999年的周数52 ，与二零零二年十二月在2003年的周数1 。

版权所有（c ）1989加州大学董事会。保留所有权利。

再分配和在源代码和二进制形式的使用是允许的前提是上述版权声明和本段是重复在所有这些形式和任何文件，广告材料，以及与这种分配并使用承认，该软件是由开发的其他材料加州大学伯克利分校。该大学的名称不得用于认可或推广源自此软件，而无需事先书面许可的产品。本软件提供的“原样”，没有任何明示或暗示的担保，包括但不限于适销性和适用性的暗示担保针对特定用途。

**See also** [isValid](qdate.html#isValid)（ ） 。

```
int QDate.year (self)
```

返回此日期的年份。负数表示几年前1 AD = 1 CE认证，例如当年-44是公元前44年

**See also** [month](qdate.html#month)（）和[day](qdate.html#day)（ ） 。

```
int QDate.__bool__ (self)
```

```
bool QDate.__eq__ (self, QDate other)
```

```
bool QDate.__ge__ (self, QDate other)
```

```
bool QDate.__gt__ (self, QDate other)
```

```
int QDate.__hash__ (self)
```

```
bool QDate.__le__ (self, QDate other)
```

```
bool QDate.__lt__ (self, QDate other)
```

```
bool QDate.__ne__ (self, QDate other)
```

```
str QDate.__repr__ (self)
```