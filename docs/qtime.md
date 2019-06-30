# QTime Class Reference

## [[QtCore](index.htm) module]

该QTIME类提供时钟时间的功能。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, int h, int m, int second = 0, int msec = 0)`
*   `__init__ (self, QTime)`
*   `QTime addMSecs (self, int ms)`
*   `QTime addSecs (self, int secs)`
*   `int elapsed (self)`
*   `int hour (self)`
*   `bool isNull (self)`
*   `bool isValid (self)`
*   `int minute (self)`
*   `int msec (self)`
*   `int msecsTo (self, QTime)`
*   `int restart (self)`
*   `int second (self)`
*   `int secsTo (self, QTime)`
*   `bool setHMS (self, int h, int m, int s, int msec = 0)`
*   `start (self)`
*   `datetime.time toPyTime (self)`
*   `QString toString (self, Qt.DateFormat format = Qt.TextDate)`
*   `QString toString (self, QString format)`

### Static Methods

*   `QTime currentTime ()`
*   `QTime fromString (QString string, Qt.DateFormat format = Qt.TextDate)`
*   `QTime fromString (QString s, QString format)`
*   `bool isValid (int h, int m, int s, int msec = 0)`

### Special Methods

*   `int __bool__ (self)`
*   `bool __eq__ (self, QTime other)`
*   `bool __ge__ (self, QTime other)`
*   `bool __gt__ (self, QTime other)`
*   `int __hash__ (self)`
*   `bool __le__ (self, QTime other)`
*   `bool __lt__ (self, QTime other)`
*   `bool __ne__ (self, QTime other)`
*   `str __repr__ (self)`

* * *

## Detailed Description

这个类可以醃制。

也可以使用一个Python的datetime对象，每当一个[QTime](qtime.html)预计。

该QTIME类提供时钟时间的功能。

一个QTIME对象包含一个时钟时间，即小时，分钟，秒和毫秒自午夜数。它可以从系统时钟读取当前时间，并测量经过的时间跨度。它提供的功能，用于比较时间和用于通过将一个数毫秒的操作时间。

QTIME使用24小时时钟格式，它具有AM / PM的概念。不像[QDateTime](qdatetime.html)， QTIME一无所知时区或日光节约时间（DST ） 。

一个QTIME对象通常是通过给小时，分钟，秒和毫秒数显式，或使用静态函数创建[currentTime](qtime.html#currentTime)（ ） ，它会创建一个包含系统的本地时间QTIME对象。请注意，精度依赖于底层操作系统的准确性;不是所有的系统都提供1毫秒的精度。

该[hour](qtime.html#hour)（ ）[minute](qtime.html#minute)（ ）[second](qtime.html#second)（）和[msec](qtime.html#msec)（ ）函数可以访问的时，分，秒和时间的毫秒数。相同的信息被提供以文本格式[toString](qtime.html#toString)（）函数。

QTIME提供了一整套的运营商来比较两个QTIME对象。一时间被认为比另一个更小，如果它是早于其他。

的时间的秒或毫秒的给定数量超过一个给定的时间可以用找到的[addSecs](qtime.html#addSecs)（）或[addMSecs](qtime.html#addMSecs)（）函数。与此相对应，几秒钟或两个时间之间的毫秒数可以使用被发现[secsTo](qtime.html#secsTo)（）或[msecsTo](qtime.html#msecsTo)（ ） 。

QTIME可用于使用测量的经过时间跨度的[start](qtime.html#start)（ ）[restart](qtime.html#restart)（）和[elapsed](qtime.html#elapsed)（）函数。

* * *

## Method Documentation

```
QTime.__init__ (self)
```

构造一个空的时间对象。空时间可[QTime](qtime.html)（0，0 ，0，0 ）（即，午夜）对象，不同的是[isNull](qtime.html#isNull)（ ）返回True，[isValid](qtime.html#isValid)（ ）返回False 。

**See also** [isNull](qtime.html#isNull)（）和[isValid](qtime.html#isValid)（ ） 。

```
QTime.__init__ (self, int h, int m, int second = 0, int msec = 0)
```

构造一个时间小时_h_，分_m_，秒_s_和毫秒_ms_。

_h_必须在范围0〜23，_m_和_s_必须在范围0 〜59，_ms_必须在范围0到999 。

**See also** [isValid](qtime.html#isValid)（ ） 。

```
QTime.__init__ (self, QTime)
```

```
QTime QTime.addMSecs (self, int ms)
```

[](qtime.html)

[返回](qtime.html)[QTime](qtime.html)对象包含时间_ms_毫秒迟于该对象的时间（或更早版本，如果_ms_是负的） 。

需要注意的是，如果它通过午夜的时候会换行。看[addSecs](qtime.html#addSecs)（ ）的一个例子。

**See also** [addSecs](qtime.html#addSecs)（ ）[msecsTo](qtime.html#msecsTo)（）和[QDateTime.addMSecs](qdatetime.html#addMSecs)（ ） 。

```
QTime QTime.addSecs (self, int secs)
```

[](qtime.html)

[返回](qtime.html)[QTime](qtime.html)对象包含时间_s_秒迟于该对象的时间（或更早版本，如果_s_是负的） 。

需要注意的是，如果它通过午夜的时候会换行。

例如：

```
 [QTime](qtime.html) n(14, 0, 0);                // n == 14:00:00
 [QTime](qtime.html) t;
 t = n.addSecs(70);                // t == 14:01:10
 t = n.addSecs(-70);               // t == 13:58:50
 t = n.addSecs(10 * 60 * 60 + 5);  // t == 00:00:05
 t = n.addSecs(-15 * 60 * 60);     // t == 23:00:00

```

**See also** [addMSecs](qtime.html#addMSecs)（ ）[secsTo](qtime.html#secsTo)（）和[QDateTime.addSecs](qdatetime.html#addSecs)（ ） 。

```
QTime QTime.currentTime ()
```

[

返回当前时间所报告的系统时钟。

请注意，精度依赖于底层操作系统的准确性;不是所有的系统都提供1毫秒的精度。

```
int QTime.elapsed (self)
```

](qtime.html)

[返回自上一次已经过的毫秒数](qtime.html)[start](qtime.html#start)（）或[restart](qtime.html#restart)（ ）被调用。

请注意，计数器回到零24小时内的最后一次通话后，[start](qtime.html#start)（）或重启。

请注意，精度依赖于底层操作系统的准确性;不是所有的系统都提供1毫秒的精度。

**Warning:**如果系统的时钟设置已自最后一次修改[start](qtime.html#start)（）或[restart](qtime.html#restart)（ ）被调用，结果是不确定的。日光节约时间开启或关闭可能发生这种情况。

**See also** [start](qtime.html#start)（）和[restart](qtime.html#restart)（ ） 。

```
QTime QTime.fromString (QString string, Qt.DateFormat format = Qt.TextDate)
```

[](qtime.html)

[传回所代表的时间_string_作为](qtime.html)[QTime](qtime.html)使用_format_给予，或无效的时间，如果这是不可能的。

需要注意的是fromString （ ）使用“ C”语言环境编码的字符串，以毫秒为单位转换为float值。如果默认locale是不是“ C” ，这可能会导致两个转换的尝试（如果转换失败的默认语言环境） 。这应该被视为一个实现细节。

```
QTime QTime.fromString (QString s, QString format)
```

[](qtime.html)

[返回](qtime.html)[QTime](qtime.html)由表示_string_使用_format_给予，或者如果字符串不能解析一个无效的时间。

这些表达式可以用于格式：

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
| AP | interpret as an AM/PM time. _AP_ must be either "AM" or "PM". |
| ap | Interpret as an AM/PM time. _ap_ must be either "am" or "pm". |

所有其他输入的字符将被视为文本。括在单引号中的任何字符序列也将被视为文本，而不是作为一个表达式。

```
 [QTime](qtime.html) time = [QTime](qtime.html).fromString("1mm12car00", "m'mm'hcarss");
 // time is 12:01.00

```

如果该格式不被满足的无效[QTime](qtime.html)返回。不指望前导零应给予（H ， M，S和z ）表达式是贪婪的。这意味着它们将使用两个数字，即使这使他们接受的值的范围外，叶太少位数为其他部分。例如，下面的字符串可能意味着0时07分10秒，但米将抓住两个数字，从而导致无效时间：

```
 [QTime](qtime.html) time = [QTime](qtime.html).fromString("00:710", "hh:ms"); // invalid

```

未在该格式表示的任何字段将被设置为零。例如：

```
 [QTime](qtime.html) time = [QTime](qtime.html).fromString("1.30", "m.s");
 // time is 00:01:30.000

```

[QDateTime.toString](qdatetime.html#toString)（ ）[QTime.toString](qtime.html#toString)（ ）

**See also** [QDateTime.fromString](qdatetime.html#fromString)（ ）[QDate.fromString](qdate.html#fromString)（）和[QDate.toString](qdate.html#toString)（ ） 。

```
int QTime.hour (self)
```

返回时间的小时部分（ 0到23） 。

**See also** [minute](qtime.html#minute)（ ）[second](qtime.html#second)（）和[msec](qtime.html#msec)（ ） 。

```
bool QTime.isNull (self)
```

返回True如果时间为null （即，[QTime](qtime.html)使用默认构造函数）构造分布，否则返回False 。一个空的时间也是无效的时间。

**See also** [isValid](qtime.html#isValid)（ ） 。

```
bool QTime.isValid (self)
```

返回True如果时间是有效的，否则返回False 。例如，时间23:30:55.746是有效的，但24:12:30是无效的。

**See also** [isNull](qtime.html#isNull)（ ） 。

```
bool QTime.isValid (int h, int m, int s, int msec = 0)
```

这是一个重载函数。

返回True如果指定的时间是有效的，否则返回False 。

时间是有效的，如果_h_取值范围为0〜23，_m_和_s_的范围是0 〜59，_ms_的范围是从0到999 。

例如：

```
 [QTime](qtime.html).isValid(21, 10, 30); // returns true
 [QTime](qtime.html).isValid(22, 5,  62); // returns false

```

```
int QTime.minute (self)
```

返回时间的分钟部分（ 0到59） 。

**See also** [hour](qtime.html#hour)（ ）[second](qtime.html#second)（）和[msec](qtime.html#msec)（ ） 。

```
int QTime.msec (self)
```

返回时间的毫秒部分（ 0到999 ） 。

**See also** [hour](qtime.html#hour)（ ）[minute](qtime.html#minute)（）和[second](qtime.html#second)（ ） 。

```
int QTime.msecsTo (self, QTime)
```

返回的毫秒数从这个时候_t_。如果_t_早于当前时间，返回的毫秒数是负的。

因为[QTime](qtime.html)测量时间在一天之内，并有86400秒，一天的结果总是之间-86400000和86400000毫秒。

**See also** [secsTo](qtime.html#secsTo)（ ）[addMSecs](qtime.html#addMSecs)（）和[QDateTime.msecsTo](qdatetime.html#msecsTo)（ ） 。

```
int QTime.restart (self)
```

设置此时间为当前时间，并返回自上一次已经过的毫秒数[start](qtime.html#start)（ ）或重新启动（）被调用。

此功能保证是原子的，因此是非常方便的重复测量。通话[start](qtime.html#start)（ ） ，开始第一次测量，并重新启动（ ）为每个后来的测量。

请注意，计数器回到零24小时内的最后一次通话后，[start](qtime.html#start)（ ）或重新启动（ ） 。

**Warning:**如果系统的时钟设置已自最后一次修改[start](qtime.html#start)（ ）或重新启动（ ）被调用，结果是不确定的。日光节约时间开启或关闭可能发生这种情况。

**See also** [start](qtime.html#start)（ ）[elapsed](qtime.html#elapsed)（）和[currentTime](qtime.html#currentTime)（ ） 。

```
int QTime.second (self)
```

返回的时间的第二部分（0到59）。

**See also** [hour](qtime.html#hour)（ ）[minute](qtime.html#minute)（）和[msec](qtime.html#msec)（ ） 。

```
int QTime.secsTo (self, QTime)
```

返回的秒数从这个时候_t_。如果_t_早于当前时间，返回的秒数为负。

因为[QTime](qtime.html)测量时间在一天之内，并有一天86400秒，结果总是-86400和86400之间。

secsTo （）不考虑任何毫秒。

**See also** [addSecs](qtime.html#addSecs)（）和[QDateTime.secsTo](qdatetime.html#secsTo)（ ） 。

```
bool QTime.setHMS (self, int h, int m, int s, int msec = 0)
```

设置时间小时_h_，分_m_，秒_s_和毫秒_ms_。

_h_必须在范围0〜23，_m_和_s_必须在范围0 〜59，_ms_必须在范围0到999 。返回True如果设定的时间是有效的，否则返回False 。

**See also** [isValid](qtime.html#isValid)（ ） 。

```
QTime.start (self)
```

设置这个时间设置为当前时间。这是不切实际的时机：

```
 [QTime](qtime.html) t;
 t.start();
 some_lengthy_task();
 qDebug("Time elapsed: %d ms", t.elapsed());

```

**See also** [restart](qtime.html#restart)（ ）[elapsed](qtime.html#elapsed)（）和[currentTime](qtime.html#currentTime)（ ） 。

```
datetime.time QTime.toPyTime (self)
```

```
QString QTime.toString (self, Qt.DateFormat format = Qt.TextDate)
```

返回时间为一个字符串。该_format_参数决定了结果字符串的格式。

这些表达式可用于：

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
| AP or A | use AM/PM display. _AP_ will be replaced by either "AM" or "PM". |
| ap or a | use am/pm display. _ap_ will be replaced by either "am" or "pm". |
| t | the timezone (for example "CEST") |

所有其它输入的字符将被忽略。括在singlequotes任何字符序列将被视为文本，而不是被用作表达。连续两singlequotes （ “''” ）是由singlequote输出所取代。

例如格式字符串（假设[QTime](qtime.html)是14:13:09.042 ）

| Format | Result |
| --- | --- |
| hh:mm:ss.zzz | 14:13:09.042 |
| h:m:s ap | 2:13:9 pm |
| H:m:s a | 14:13:9 pm |

如果日期时间是无效的，空字符串将被返回。如果_format_是空的，默认的格式为“ HH ： MM：SS ”一词。

**See also** [QDate.toString](qdate.html#toString)（）和[QDateTime.toString](qdatetime.html#toString)（ ） 。

```
QString QTime.toString (self, QString format)
```

这是一个重载函数。

返回时间为一个字符串。毫秒不包括在内。该_format_参数确定字符串的格式。

If _format_ is [Qt.TextDate](qt.html#DateFormat-enum)，字符串格式为HH ： MM：SS ;例如午夜在1秒将是“ 23:59:59 ” 。

If _format_ is [Qt.ISODate](qt.html#DateFormat-enum)，字符串格式对应于ISO 8601扩展规格的日期，这也是HH的表示： MM：SS 。 （然而，与ISO 8601 ，日期1582年10月15日之前为Julian日期，而不是公历日期的处理方式。见[Use of Gregorian and Julian Calendars](qdate.html#qdate-g-and-j)。这可能会改变的Qt的未来版本。 ）

如果_format_ is [Qt.SystemLocaleShortDate](qt.html#DateFormat-enum) or [Qt.SystemLocaleLongDate](qt.html#DateFormat-enum)，字符串格式取决于系统的区域设置。相同的调用[QLocale.system](qlocale.html#system)（ ） 。的toString （时间，[QLocale.ShortFormat](qlocale.html#FormatType-enum)）或[QLocale.system](qlocale.html#system)（ ） 。的toString （时间，[QLocale.LongFormat](qlocale.html#FormatType-enum)） 。

如果_format_ is [Qt.DefaultLocaleShortDate](qt.html#DateFormat-enum) or [Qt.DefaultLocaleLongDate](qt.html#DateFormat-enum)，字符串格式依赖于默认应用程序的语言环境。这就是语言环境设置[QLocale.setDefault](qlocale.html#setDefault)（ ）或系统区域设置，如果没有默认区域设置已定。相同的调用QLocale （ ） 。的toString （时间，[QLocale.ShortFormat](qlocale.html#FormatType-enum)）或QLocale （ ） 。的toString （时间，[QLocale.LongFormat](qlocale.html#FormatType-enum)） 。

如果时间是无效的，空字符串将被返回。

```
int QTime.__bool__ (self)
```

```
bool QTime.__eq__ (self, QTime other)
```

```
bool QTime.__ge__ (self, QTime other)
```

```
bool QTime.__gt__ (self, QTime other)
```

```
int QTime.__hash__ (self)
```

```
bool QTime.__le__ (self, QTime other)
```

```
bool QTime.__lt__ (self, QTime other)
```

```
bool QTime.__ne__ (self, QTime other)
```

```
str QTime.__repr__ (self)
```