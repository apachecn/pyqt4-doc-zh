# QSystemLocale Class Reference

## [[QtCore](index.htm) module]

The QSystemLocale class can be used to finetune the system locale of the user. [More...](#details)

### Types

*   `enum QueryType { LanguageId, ScriptId, CountryId, DecimalPoint, ..., NativeCountryName }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QSystemLocale)`
*   `QLocale fallbackLocale (self)`
*   `QVariant query (self, QueryType type, QVariant in)`

* * *

## Detailed Description

The QSystemLocale class can be used to finetune the system locale of the user.

**Warning:**这个类只有在非常罕见的情况下非常有用。平时[QLocale](qlocale.html)提供了所有必需的应用程序开发的功能。

QSystemLocale允许复盖系统区域设置（提供的值[QLocale.system](qlocale.html#system)（））。

* * *

## Type Documentation

```
QSystemLocale.QueryType
```

指定的信息被查询的类型[query](qsystemlocale.html#query)（ ） 。对于每一个值的信息从返回值的类型[query](qsystemlocale.html#query)（ ）方法被列出。

| Constant | Value | Description |
| --- | --- | --- |
| `QSystemLocale.LanguageId` | `0` | 一个UINT指定的语言。 |
| `QSystemLocale.ScriptId` | `33` | 一个UINT指定的脚本。 |
| `QSystemLocale.CountryId` | `1` | 一个UINT指定的国家。 |
| `QSystemLocale.DecimalPoint` | `2` | 一[QString](qstring.html)指定小数点。 |
| `QSystemLocale.GroupSeparator` | `3` | 一[QString](qstring.html)指定的组分隔符。 |
| `QSystemLocale.ZeroDigit` | `4` | 一[QString](qstring.html)指定零位。 |
| `QSystemLocale.NegativeSign` | `5` | 一[QString](qstring.html)指定减号。 |
| `QSystemLocale.PositiveSign` | `23` | 一[QString](qstring.html)指定加号。 |
| `QSystemLocale.DateFormatLong` | `6` | 一[QString](qstring.html)指定的长日期格式 |
| `QSystemLocale.DateFormatShort` | `7` | 一[QString](qstring.html)指定的短日期格式 |
| `QSystemLocale.TimeFormatLong` | `8` | 一[QString](qstring.html)指定的长时间格式 |
| `QSystemLocale.TimeFormatShort` | `9` | 一[QString](qstring.html)指定的短时间格式 |
| `QSystemLocale.DayNameLong` | `10` | 一[QString](qstring.html)指定工作日的名称。该变种中包含1和7之间的整数（星期一 - 星期日） |
| `QSystemLocale.DayNameShort` | `11` | 一[QString](qstring.html)指定一个工作日的简称。该变种中包含1和7之间的整数（星期一 - 星期日） |
| `QSystemLocale.MonthNameLong` | `12` | 一[QString](qstring.html)指定月份的名称。该变种中包含1到12之间的整数 |
| `QSystemLocale.MonthNameShort` | `13` | 一[QString](qstring.html)指定月份的简称。该变种中包含1到12之间的整数 |
| `QSystemLocale.DateToStringLong` | `14` | 转换[QDate](qdate.html)存储在变量中的[QString](qstring.html)采用长日期格式 |
| `QSystemLocale.DateToStringShort` | `15` | 转换[QDate](qdate.html)存储在变量中的[QString](qstring.html)使用短日期格式 |
| `QSystemLocale.TimeToStringLong` | `16` | 转换[QTime](qtime.html)存储在变量中的[QString](qstring.html)使用长时间格式 |
| `QSystemLocale.TimeToStringShort` | `17` | 转换[QTime](qtime.html)存储在变量中的[QString](qstring.html)用很短的时间格式 |
| `QSystemLocale.DateTimeFormatLong` | `18` | 一[QString](qstring.html)指定的长日期时间格式 |
| `QSystemLocale.DateTimeFormatShort` | `19` | 一[QString](qstring.html)指定的短日期时间格式 |
| `QSystemLocale.DateTimeToStringLong` | `20` | 转换[QDateTime](qdatetime.html)在变型中的[QString](qstring.html)使用长日期时间格式 |
| `QSystemLocale.DateTimeToStringShort` | `21` | 转换[QDateTime](qdatetime.html)在变型中的[QString](qstring.html)使用短日期时间格式 |
| `QSystemLocale.MeasurementSystem` | `22` | 一[QLocale.MeasurementSystem](qlocale.html#MeasurementSystem-enum)枚举指定测量系统 |
| `QSystemLocale.AMText` | `24` | 表示用12小时时钟相关的系统AM指示的字符串。 |
| `QSystemLocale.PMText` | `25` | 表示用12小时时钟相关的系统PM指示的字符串。 |
| `QSystemLocale.FirstDayOfWeek` | `26` | 一[Qt.DayOfWeek](qt.html#DayOfWeek-enum)枚举specifiying一周的第一天 |
| `QSystemLocale.CurrencySymbol` | `28` | 它表示的格式QLocale.CurrencyFormat货币的字符串。 |
| `QSystemLocale.CurrencyToString` | `29` | 一些带有货币符号的本地化字符串表示形式。将一个[QSystemLocale.CurrencyToStringArgument](index.htm)存储在变量中的[QString](qstring.html)。 |
| `QSystemLocale.UILanguages` | `30` | 表示可用于用户界面翻译语言环境名称的字符串列表。 |
| `QSystemLocale.StringToStandardQuotation` | `31` | 一[QString](qstring.html)含有使用标准报价存储在变量中的字符串裁判的引用的版本。 |
| `QSystemLocale.StringToAlternateQuotation` | `32` | 一[QString](qstring.html)含有使用替代引号存储在变量中的字符串裁判的引用的版本。 |
| `QSystemLocale.Weekdays` | `27` | 一[QList](index.htm)\u003c[Qt.DayOfWeek](qt.html#DayOfWeek-enum)\u003e指定正规平日 |
| `QSystemLocale.LocaleChanged` | `35` | 这种类型的查询时系统区域设置被改变。 |
| `QSystemLocale.ListToSeparatedString` | `34` | 一个表示连接的一个给定的一个字符串[QStringList](qstringlist.html)一个语言环境定义的分隔符。 |
| `QSystemLocale.NativeLanguageName` | `36` | 表示本机语言的名称的字符串。 |
| `QSystemLocale.NativeCountryName` | `37` | 代表祖国的名称的字符串。 |

* * *

## Method Documentation

```
QSystemLocale.__init__ (self)
```

构造一个[QSystemLocale](qsystemlocale.html)对象。该构造函数会自动安装这个对象作为系统区域设置和删除任何早期安装的系统语言环境。

```
QSystemLocale.__init__ (self, QSystemLocale)
```

```
QLocale QSystemLocale.fallbackLocale (self)
```

[

返回从系统中获得的回退区域设置。

此功能被引入Qt的4.6 。

```
QVariant QSystemLocale.query (self, QueryType type, QVariant in)
```

通用查询方法语言环境数据。提供间接。表示_type_用查询_in_作为输入数据根据查询。

](qlocale.html)

[**See also**](qlocale.html) [QSystemLocale.QueryType](qsystemlocale.html#QueryType-enum)。