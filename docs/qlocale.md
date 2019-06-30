# QLocale Class Reference

## [[QtCore](index.htm) module]

各种语言的数量和它们的字符串表示形式之间的QLocale类转换。[More...](#details)

### Types

*   `enum Country { AnyCountry, Afghanistan, Albania, Algeria, ..., LastCountry }`
*   `enum CurrencySymbolFormat { CurrencyIsoCode, CurrencySymbol, CurrencyDisplayName }`
*   `enum FormatType { LongFormat, ShortFormat, NarrowFormat }`
*   `enum Language { C, Abkhazian, Afan, Afar, ..., AnyLanguage }`
*   `enum MeasurementSystem { MetricSystem, ImperialSystem }`
*   `enum NumberOption { OmitGroupSeparator, RejectGroupSeparator }`
*   `class **[NumberOptions](index.htm)**`
*   `enum QuotationStyle { StandardQuotation, AlternateQuotation }`
*   `enum Script { AnyScript, ArabicScript, CyrillicScript, DeseretScript, ..., TraditionalChineseScript }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QString name)`
*   `__init__ (self, Language language, Country country = QLocale.AnyCountry)`
*   `__init__ (self, QLocale other)`
*   `__init__ (self, Language language, Script script, Country country)`
*   `QString amText (self)`
*   `QString bcp47Name (self)`
*   `Country country (self)`
*   `QString createSeparatedList (self, QStringList list)`
*   `QString currencySymbol (self, CurrencySymbolFormat format = QLocale.CurrencySymbol)`
*   `QString dateFormat (self, FormatType format = QLocale.LongFormat)`
*   `QString dateTimeFormat (self, FormatType format = QLocale.LongFormat)`
*   `QString dayName (self, int, FormatType format = QLocale.LongFormat)`
*   `QChar decimalPoint (self)`
*   `QChar exponential (self)`
*   `Qt.DayOfWeek firstDayOfWeek (self)`
*   `QChar groupSeparator (self)`
*   `Language language (self)`
*   `MeasurementSystem measurementSystem (self)`
*   `QString monthName (self, int, FormatType format = QLocale.LongFormat)`
*   `QString name (self)`
*   `QString nativeCountryName (self)`
*   `QString nativeLanguageName (self)`
*   `QChar negativeSign (self)`
*   `NumberOptions numberOptions (self)`
*   `QChar percent (self)`
*   `QString pmText (self)`
*   `QChar positiveSign (self)`
*   `QString quoteString (self, QString str, QuotationStyle style = QLocale.StandardQuotation)`
*   `Script script (self)`
*   `setNumberOptions (self, NumberOptions options)`
*   `QString standaloneDayName (self, int, FormatType format = QLocale.LongFormat)`
*   `QString standaloneMonthName (self, int, FormatType format = QLocale.LongFormat)`
*   `Qt.LayoutDirection textDirection (self)`
*   `QString timeFormat (self, FormatType format = QLocale.LongFormat)`
*   `QString toCurrencyString (self, int value, QString symbol = QString())`
*   `QString toCurrencyString (self, float value, QString symbol = QString())`
*   `QString toCurrencyString (self, int value, QString symbol = QString())`
*   `QString toCurrencyString (self, int value, QString symbol = QString())`
*   `QDate toDate (self, QString string, FormatType format = QLocale.LongFormat)`
*   `QDate toDate (self, QString string, QString format)`
*   `QDateTime toDateTime (self, QString string, FormatType format = QLocale.LongFormat)`
*   `QDateTime toDateTime (self, QString string, QString format)`
*   `(float, bool ok) toDouble (self, QString s)`
*   `(float, bool ok) toFloat (self, QString s)`
*   `(int, bool ok) toInt (self, QString s, int base = 0)`
*   `(int, bool ok) toLongLong (self, QString s, int base = 0)`
*   `QString toLower (self, QString str)`
*   `(int, bool ok) toShort (self, QString s, int base = 0)`
*   `QString toString (self, int i)`
*   `QString toString (self, float i, str format = 'g', int precision = 6)`
*   `QString toString (self, int i)`
*   `QString toString (self, int i)`
*   `QString toString (self, QDateTime dateTime, QString format)`
*   `QString toString (self, QDateTime dateTime, FormatType format = QLocale.LongFormat)`
*   `QString toString (self, QDate date, QString formatStr)`
*   `QString toString (self, QDate date, FormatType format = QLocale.LongFormat)`
*   `QString toString (self, QTime time, QString formatStr)`
*   `QString toString (self, QTime time, FormatType format = QLocale.LongFormat)`
*   `QTime toTime (self, QString string, FormatType format = QLocale.LongFormat)`
*   `QTime toTime (self, QString string, QString format)`
*   `(int, bool ok) toUInt (self, QString s, int base = 0)`
*   `(int, bool ok) toULongLong (self, QString s, int base = 0)`
*   `QString toUpper (self, QString str)`
*   `(int, bool ok) toUShort (self, QString s, int base = 0)`
*   `QStringList uiLanguages (self)`
*   `list-of-Qt.DayOfWeek weekdays (self)`
*   `QChar zeroDigit (self)`

### Static Methods

*   `QLocale c ()`
*   `list-of-QLocale.Country countriesForLanguage (Language lang)`
*   `QString countryToString (Country country)`
*   `QString languageToString (Language language)`
*   `list-of-QLocale matchingLocales (Language language, Script script, Country country)`
*   `QString scriptToString (Script script)`
*   `setDefault (QLocale locale)`
*   `QLocale system ()`

### Special Methods

*   `bool __eq__ (self, QLocale other)`
*   `bool __ne__ (self, QLocale other)`

* * *

## Detailed Description

各种语言的数量和它们的字符串表示形式之间的QLocale类转换。

QLocale与语言/国家对在其构造函数中初始化，并提供数到字符串和字符串到数字转换功能类似于[QString](qstring.html)。

例如：

```
 QLocale egyptian(QLocale.Arabic, QLocale.Egypt);
 [QString](qstring.html) s1 = egyptian.toString(1.571429E+07, 'e');
 [QString](qstring.html) s2 = egyptian.toString(10);

 double d = egyptian.toDouble(s1);
 int i = egyptian.toInt(s2);

```

QLocale支持默认的语言环境，这是从应用程序启动时系统的区域设置确定的概念。默认的语言环境可以通过调用静态成员被改变[setDefault](qlocale.html#setDefault)（ ） 。设置默认语言环境具有以下效果：

*   If a QLocale object is constructed with the default constructor, it will use the default locale's settings.
*   [QString.toInt](qstring.html#toInt)(), [QString.toDouble](qstring.html#toDouble)(), etc., interpret the string according to the default locale. If this fails, it falls back on the "C" locale.
*   [QString.arg](qstring.html#arg)() uses the default locale to format a number when its position specifier in the format string contains an 'L', e.g. "%L1".

下面的例子演示了如何直接使用QLocale ：

```
 QLocale.setDefault(QLocale(QLocale.Hebrew, QLocale.Israel));
 QLocale hebrew; // Constructs a default QLocale
 [QString](qstring.html) s1 = hebrew.toString(15714.3, 'e');

 bool ok;
 double d;

 QLocale.setDefault(QLocale.C);
 d = [QString](qstring.html)("1234,56").toDouble(&ok);   // ok == false
 d = [QString](qstring.html)("1234.56").toDouble(&ok);   // ok == true, d == 1234.56

 QLocale.setDefault(QLocale.German);
 d = [QString](qstring.html)("1234,56").toDouble(&ok);   // ok == true, d == 1234.56
 d = [QString](qstring.html)("1234.56").toDouble(&ok);   // ok == true, d == 1234.56

 QLocale.setDefault(QLocale(QLocale.English, QLocale.UnitedStates));
 str = [QString](qstring.html)("%1 %L2 %L3")
       .arg(12345).arg(12345).arg(12345, 0, 16);
 // str == "12345 12,345 3039"

```

当在构造函数中指定的语言/国家对，以下三种情况之一发生：

*   If the language/country pair is found in the database, it is used.
*   If the language is found but the country is not, or if the country is `AnyCountry`, the language is used with the most appropriate available country (for example, Germany for German),
*   If neither the language nor the country are found, QLocale defaults to the default locale (see [setDefault](qlocale.html#setDefault)()).

使用[language](qlocale.html#language)（）和[country](qlocale.html#country)（）来确定实际使用的语言和国家价值观。

构建一个QLocale对象的另一种方法是通过指定的语言环境名称。

```
 QLocale korean("ko");
 QLocale swiss("de_CH");

```

此构造函数的语言环境名称转换为语言/国家对;它不使用系统区域设置数据库。

**Note:**对于目前的键盘输入法区域设置来看看[QApplication.keyboardInputLocale](qapplication.html#keyboardInputLocale)（ ） 。

QLocale的数据是基于通用语言环境数据仓库2.0 。

双到字符串和字符串到双转换功能涵盖以下许可证：

版权所有（c ）1991由AT＆ T。

许可使用，复制，修改和分发本软件不费任何目的，现予批准，前提是这整个通知包括在其中是或包括一个复制本软件或修改任何软件的所有副本，并在所有副本支持文件这样的软件。

本软件是“按原样”，没有任何明示或暗示的保证。尤其是，不管是作者还是AT＆T公司不提供任何形式关于本软件或对其适用于任何特定用途的适销性任何声明或保证。

本产品包含由加州大学伯克利分校和它的贡献者开发的软件。

* * *

## Type Documentation

```
QLocale.Country
```

这个枚举类型用于指定一个国家。

| Constant | Value |
| --- | --- |
| `QLocale.AnyCountry` | `0` |
| `QLocale.Afghanistan` | `1` |
| `QLocale.Albania` | `2` |
| `QLocale.Algeria` | `3` |
| `QLocale.AmericanSamoa` | `4` |
| `QLocale.Andorra` | `5` |
| `QLocale.Angola` | `6` |
| `QLocale.Anguilla` | `7` |
| `QLocale.Antarctica` | `8` |
| `QLocale.AntiguaAndBarbuda` | `9` |
| `QLocale.Argentina` | `10` |
| `QLocale.Armenia` | `11` |
| `QLocale.Aruba` | `12` |
| `QLocale.Australia` | `13` |
| `QLocale.Austria` | `14` |
| `QLocale.Azerbaijan` | `15` |
| `QLocale.Bahamas` | `16` |
| `QLocale.Bahrain` | `17` |
| `QLocale.Bangladesh` | `18` |
| `QLocale.Barbados` | `19` |
| `QLocale.Belarus` | `20` |
| `QLocale.Belgium` | `21` |
| `QLocale.Belize` | `22` |
| `QLocale.Benin` | `23` |
| `QLocale.Bermuda` | `24` |
| `QLocale.Bhutan` | `25` |
| `QLocale.Bolivia` | `26` |
| `QLocale.BosniaAndHerzegowina` | `27` |
| `QLocale.Botswana` | `28` |
| `QLocale.BouvetIsland` | `29` |
| `QLocale.Brazil` | `30` |
| `QLocale.BritishIndianOceanTerritory` | `31` |
| `QLocale.BruneiDarussalam` | `32` |
| `QLocale.Bulgaria` | `33` |
| `QLocale.BurkinaFaso` | `34` |
| `QLocale.Burundi` | `35` |
| `QLocale.Cambodia` | `36` |
| `QLocale.Cameroon` | `37` |
| `QLocale.Canada` | `38` |
| `QLocale.CapeVerde` | `39` |
| `QLocale.CaymanIslands` | `40` |
| `QLocale.CentralAfricanRepublic` | `41` |
| `QLocale.Chad` | `42` |
| `QLocale.Chile` | `43` |
| `QLocale.China` | `44` |
| `QLocale.ChristmasIsland` | `45` |
| `QLocale.CocosIslands` | `46` |
| `QLocale.Colombia` | `47` |
| `QLocale.Comoros` | `48` |
| `QLocale.DemocraticRepublicOfCongo` | `49` |
| `QLocale.PeoplesRepublicOfCongo` | `50` |
| `QLocale.CookIslands` | `51` |
| `QLocale.CostaRica` | `52` |
| `QLocale.IvoryCoast` | `53` |
| `QLocale.Croatia` | `54` |
| `QLocale.Cuba` | `55` |
| `QLocale.Cyprus` | `56` |
| `QLocale.CzechRepublic` | `57` |
| `QLocale.Denmark` | `58` |
| `QLocale.Djibouti` | `59` |
| `QLocale.Dominica` | `60` |
| `QLocale.DominicanRepublic` | `61` |
| `QLocale.EastTimor` | `62` |
| `QLocale.Ecuador` | `63` |
| `QLocale.Egypt` | `64` |
| `QLocale.ElSalvador` | `65` |
| `QLocale.EquatorialGuinea` | `66` |
| `QLocale.Eritrea` | `67` |
| `QLocale.Estonia` | `68` |
| `QLocale.Ethiopia` | `69` |
| `QLocale.FalklandIslands` | `70` |
| `QLocale.FaroeIslands` | `71` |
| `QLocale.FijiCountry` | `72` |
| `QLocale.Finland` | `73` |
| `QLocale.France` | `74` |
| `QLocale.MetropolitanFrance` | `75` |
| `QLocale.FrenchGuiana` | `76` |
| `QLocale.FrenchPolynesia` | `77` |
| `QLocale.FrenchSouthernTerritories` | `78` |
| `QLocale.Gabon` | `79` |
| `QLocale.Gambia` | `80` |
| `QLocale.Georgia` | `81` |
| `QLocale.Germany` | `82` |
| `QLocale.Ghana` | `83` |
| `QLocale.Gibraltar` | `84` |
| `QLocale.Greece` | `85` |
| `QLocale.Greenland` | `86` |
| `QLocale.Grenada` | `87` |
| `QLocale.Guadeloupe` | `88` |
| `QLocale.Guam` | `89` |
| `QLocale.Guatemala` | `90` |
| `QLocale.Guinea` | `91` |
| `QLocale.GuineaBissau` | `92` |
| `QLocale.Guyana` | `93` |
| `QLocale.Haiti` | `94` |
| `QLocale.HeardAndMcDonaldIslands` | `95` |
| `QLocale.Honduras` | `96` |
| `QLocale.HongKong` | `97` |
| `QLocale.Hungary` | `98` |
| `QLocale.Iceland` | `99` |
| `QLocale.India` | `100` |
| `QLocale.Indonesia` | `101` |
| `QLocale.Iran` | `102` |
| `QLocale.Iraq` | `103` |
| `QLocale.Ireland` | `104` |
| `QLocale.Israel` | `105` |
| `QLocale.Italy` | `106` |
| `QLocale.Jamaica` | `107` |
| `QLocale.Japan` | `108` |
| `QLocale.Jordan` | `109` |
| `QLocale.Kazakhstan` | `110` |
| `QLocale.Kenya` | `111` |
| `QLocale.Kiribati` | `112` |
| `QLocale.DemocraticRepublicOfKorea` | `113` |
| `QLocale.RepublicOfKorea` | `114` |
| `QLocale.Kuwait` | `115` |
| `QLocale.Kyrgyzstan` | `116` |
| `QLocale.Lao` | `117` |
| `QLocale.Latvia` | `118` |
| `QLocale.Lebanon` | `119` |
| `QLocale.Lesotho` | `120` |
| `QLocale.Liberia` | `121` |
| `QLocale.LibyanArabJamahiriya` | `122` |
| `QLocale.Liechtenstein` | `123` |
| `QLocale.Lithuania` | `124` |
| `QLocale.Luxembourg` | `125` |
| `QLocale.Macau` | `126` |
| `QLocale.Macedonia` | `127` |
| `QLocale.Madagascar` | `128` |
| `QLocale.Malawi` | `129` |
| `QLocale.Malaysia` | `130` |
| `QLocale.Maldives` | `131` |
| `QLocale.Mali` | `132` |
| `QLocale.Malta` | `133` |
| `QLocale.MarshallIslands` | `134` |
| `QLocale.Martinique` | `135` |
| `QLocale.Mauritania` | `136` |
| `QLocale.Mauritius` | `137` |
| `QLocale.Mayotte` | `138` |
| `QLocale.Mexico` | `139` |
| `QLocale.Micronesia` | `140` |
| `QLocale.Moldova` | `141` |
| `QLocale.Monaco` | `142` |
| `QLocale.Mongolia` | `143` |
| `QLocale.Montserrat` | `144` |
| `QLocale.Morocco` | `145` |
| `QLocale.Mozambique` | `146` |
| `QLocale.Myanmar` | `147` |
| `QLocale.Namibia` | `148` |
| `QLocale.NauruCountry` | `149` |
| `QLocale.Nepal` | `150` |
| `QLocale.Netherlands` | `151` |
| `QLocale.NetherlandsAntilles` | `152` |
| `QLocale.NewCaledonia` | `153` |
| `QLocale.NewZealand` | `154` |
| `QLocale.Nicaragua` | `155` |
| `QLocale.Niger` | `156` |
| `QLocale.Nigeria` | `157` |
| `QLocale.Niue` | `158` |
| `QLocale.NorfolkIsland` | `159` |
| `QLocale.NorthernMarianaIslands` | `160` |
| `QLocale.Norway` | `161` |
| `QLocale.Oman` | `162` |
| `QLocale.Pakistan` | `163` |
| `QLocale.Palau` | `164` |
| `QLocale.PalestinianTerritory` | `165` |
| `QLocale.Panama` | `166` |
| `QLocale.PapuaNewGuinea` | `167` |
| `QLocale.Paraguay` | `168` |
| `QLocale.Peru` | `169` |
| `QLocale.Philippines` | `170` |
| `QLocale.Pitcairn` | `171` |
| `QLocale.Poland` | `172` |
| `QLocale.Portugal` | `173` |
| `QLocale.PuertoRico` | `174` |
| `QLocale.Qatar` | `175` |
| `QLocale.Reunion` | `176` |
| `QLocale.Romania` | `177` |
| `QLocale.RussianFederation` | `178` |
| `QLocale.Rwanda` | `179` |
| `QLocale.SaintKittsAndNevis` | `180` |
| `QLocale.StLucia` | `181` |
| `QLocale.StVincentAndTheGrenadines` | `182` |
| `QLocale.Samoa` | `183` |
| `QLocale.SanMarino` | `184` |
| `QLocale.SaoTomeAndPrincipe` | `185` |
| `QLocale.SaudiArabia` | `186` |
| `QLocale.Senegal` | `187` |
| `QLocale.SerbiaAndMontenegro` | `241` |
| `QLocale.Seychelles` | `188` |
| `QLocale.SierraLeone` | `189` |
| `QLocale.Singapore` | `190` |
| `QLocale.Slovakia` | `191` |
| `QLocale.Slovenia` | `192` |
| `QLocale.SolomonIslands` | `193` |
| `QLocale.Somalia` | `194` |
| `QLocale.SouthAfrica` | `195` |
| `QLocale.SouthGeorgiaAndTheSouthSandwichIslands` | `196` |
| `QLocale.Spain` | `197` |
| `QLocale.SriLanka` | `198` |
| `QLocale.StHelena` | `199` |
| `QLocale.StPierreAndMiquelon` | `200` |
| `QLocale.Sudan` | `201` |
| `QLocale.Suriname` | `202` |
| `QLocale.SvalbardAndJanMayenIslands` | `203` |
| `QLocale.Swaziland` | `204` |
| `QLocale.Sweden` | `205` |
| `QLocale.Switzerland` | `206` |
| `QLocale.SyrianArabRepublic` | `207` |
| `QLocale.Taiwan` | `208` |
| `QLocale.Tajikistan` | `209` |
| `QLocale.Tanzania` | `210` |
| `QLocale.Thailand` | `211` |
| `QLocale.Togo` | `212` |
| `QLocale.Tokelau` | `213` |
| `QLocale.TongaCountry` | `214` |
| `QLocale.TrinidadAndTobago` | `215` |
| `QLocale.Tunisia` | `216` |
| `QLocale.Turkey` | `217` |
| `QLocale.Turkmenistan` | `218` |
| `QLocale.TurksAndCaicosIslands` | `219` |
| `QLocale.Tuvalu` | `220` |
| `QLocale.Uganda` | `221` |
| `QLocale.Ukraine` | `222` |
| `QLocale.UnitedArabEmirates` | `223` |
| `QLocale.UnitedKingdom` | `224` |
| `QLocale.UnitedStates` | `225` |
| `QLocale.UnitedStatesMinorOutlyingIslands` | `226` |
| `QLocale.Uruguay` | `227` |
| `QLocale.Uzbekistan` | `228` |
| `QLocale.Vanuatu` | `229` |
| `QLocale.VaticanCityState` | `230` |
| `QLocale.Venezuela` | `231` |
| `QLocale.VietNam` | `232` |
| `QLocale.BritishVirginIslands` | `233` |
| `QLocale.USVirginIslands` | `234` |
| `QLocale.WallisAndFutunaIslands` | `235` |
| `QLocale.WesternSahara` | `236` |
| `QLocale.Yemen` | `237` |
| `QLocale.Yugoslavia` | `238` |
| `QLocale.Zambia` | `239` |
| `QLocale.Zimbabwe` | `240` |
| `QLocale.Montenegro` | `242` |
| `QLocale.Serbia` | `243` |
| `QLocale.SaintBarthelemy` | `244` |
| `QLocale.SaintMartin` | `245` |
| `QLocale.LatinAmericaAndTheCaribbean` | `246` |

**See also** [country](qlocale.html#country)（）和[countryToString](qlocale.html#countryToString)（ ） 。

```
QLocale.CurrencySymbolFormat
```

指定货币符号的格式。

| Constant | Value | Description |
| --- | --- | --- |
| `QLocale.CurrencyIsoCode` | `0` | 一个ISO- 4217代码的货币。 |
| `QLocale.CurrencySymbol` | `1` | 货币符号。 |
| `QLocale.CurrencyDisplayName` | `2` | 货币的用户可读名称。 |

这个枚举被引入或修改的Qt 4.8 。

```
QLocale.FormatType
```

这个枚举变量描述了可以在转换时使用的格式类型[QDate](qdate.html)和[QTime](qtime.html)对象为字符串。

| Constant | Value | Description |
| --- | --- | --- |
| `QLocale.LongFormat` | `0` | 长版的日期和月份名称，例如，返回“月”为月份名称。 |
| `QLocale.ShortFormat` | `1` | 短版的日期和月份名称，例如，返回“月”为月份名称。 |
| `QLocale.NarrowFormat` | `2` | 一个特殊版本的日期和月份名称使用时，空间是有限的，例如，返回“J”为月份名称。需要注意的是狭窄的格式可能包含相同的文本不同的月份和日期，或者甚至可以是一个空字符串，如果语言环境不支持狭窄的名字，所以你应该避免使用它的日期格式。另外，对于系统区域设置这种格式是一样的ShortFormat 。 |

```
QLocale.Language
```

这个枚举类型用于指定语言。

| Constant | Value | Description |
| --- | --- | --- |
| `QLocale.AnyLanguage` | `0` |   |
| `QLocale.C` | `1` | 在“ C”语言环境是相同的行为，以英文/[UnitedStates](qlocale.html#Country-enum)。 |
| `QLocale.Abkhazian` | `2` |   |
| `QLocale.Afan` | `3` |   |
| `QLocale.Afar` | `4` |   |
| `QLocale.Afrikaans` | `5` |   |
| `QLocale.Albanian` | `6` |   |
| `QLocale.Amharic` | `7` |   |
| `QLocale.Arabic` | `8` |   |
| `QLocale.Armenian` | `9` |   |
| `QLocale.Assamese` | `10` |   |
| `QLocale.Aymara` | `11` |   |
| `QLocale.Azerbaijani` | `12` |   |
| `QLocale.Bashkir` | `13` |   |
| `QLocale.Basque` | `14` |   |
| `QLocale.Bengali` | `15` |   |
| `QLocale.Bhutani` | `16` |   |
| `QLocale.Bihari` | `17` |   |
| `QLocale.Bislama` | `18` |   |
| `QLocale.Bosnian` | `142` |   |
| `QLocale.Breton` | `19` |   |
| `QLocale.Bulgarian` | `20` |   |
| `QLocale.Burmese` | `21` |   |
| `QLocale.Byelorussian` | `22` |   |
| `QLocale.Cambodian` | `23` |   |
| `QLocale.Catalan` | `24` |   |
| `QLocale.Chinese` | `25` |   |
| `QLocale.Cornish` | `145` |   |
| `QLocale.Corsican` | `26` |   |
| `QLocale.Croatian` | `27` |   |
| `QLocale.Czech` | `28` |   |
| `QLocale.Danish` | `29` |   |
| `QLocale.Divehi` | `143` |   |
| `QLocale.Dutch` | `30` |   |
| `QLocale.English` | `31` |   |
| `QLocale.Esperanto` | `32` |   |
| `QLocale.Estonian` | `33` |   |
| `QLocale.Faroese` | `34` |   |
| `QLocale.FijiLanguage` | `35` |   |
| `QLocale.Finnish` | `36` |   |
| `QLocale.French` | `37` |   |
| `QLocale.Frisian` | `38` |   |
| `QLocale.Gaelic` | `39` |   |
| `QLocale.Galician` | `40` |   |
| `QLocale.Georgian` | `41` |   |
| `QLocale.German` | `42` |   |
| `QLocale.Greek` | `43` |   |
| `QLocale.Greenlandic` | `44` |   |
| `QLocale.Guarani` | `45` |   |
| `QLocale.Gujarati` | `46` |   |
| `QLocale.Hausa` | `47` |   |
| `QLocale.Hebrew` | `48` |   |
| `QLocale.Hindi` | `49` |   |
| `QLocale.Hungarian` | `50` |   |
| `QLocale.Icelandic` | `51` |   |
| `QLocale.Indonesian` | `52` |   |
| `QLocale.Interlingua` | `53` |   |
| `QLocale.Interlingue` | `54` |   |
| `QLocale.Inuktitut` | `55` |   |
| `QLocale.Inupiak` | `56` |   |
| `QLocale.Irish` | `57` |   |
| `QLocale.Italian` | `58` |   |
| `QLocale.Japanese` | `59` |   |
| `QLocale.Javanese` | `60` |   |
| `QLocale.Kannada` | `61` |   |
| `QLocale.Kashmiri` | `62` |   |
| `QLocale.Kazakh` | `63` |   |
| `QLocale.Kinyarwanda` | `64` |   |
| `QLocale.Kirghiz` | `65` |   |
| `QLocale.Korean` | `66` |   |
| `QLocale.Kurdish` | `67` |   |
| `QLocale.Kurundi` | `Rundi` |   |
| `QLocale.Laothian` | `69` |   |
| `QLocale.Latin` | `70` |   |
| `QLocale.Latvian` | `71` |   |
| `QLocale.Lingala` | `72` |   |
| `QLocale.Lithuanian` | `73` |   |
| `QLocale.Macedonian` | `74` |   |
| `QLocale.Malagasy` | `75` |   |
| `QLocale.Malay` | `76` |   |
| `QLocale.Malayalam` | `77` |   |
| `QLocale.Maltese` | `78` |   |
| `QLocale.Manx` | `144` |   |
| `QLocale.Maori` | `79` |   |
| `QLocale.Marathi` | `80` |   |
| `QLocale.Moldavian` | `81` |   |
| `QLocale.Mongolian` | `82` |   |
| `QLocale.NauruLanguage` | `83` |   |
| `QLocale.Nepali` | `84` |   |
| `QLocale.Norwegian` | `85` |   |
| `QLocale.NorwegianBokmal` | `Norwegian` |   |
| `QLocale.Nynorsk` | `141` | 过时，请使用NorwegianNynorsk |
| `QLocale.NorwegianNynorsk` | `Nynorsk` |   |
| `QLocale.Occitan` | `86` |   |
| `QLocale.Oriya` | `87` |   |
| `QLocale.Pashto` | `88` |   |
| `QLocale.Persian` | `89` |   |
| `QLocale.Polish` | `90` |   |
| `QLocale.Portuguese` | `91` |   |
| `QLocale.Punjabi` | `92` |   |
| `QLocale.Quechua` | `93` |   |
| `QLocale.RhaetoRomance` | `94` |   |
| `QLocale.Romanian` | `95` |   |
| `QLocale.Russian` | `96` |   |
| `QLocale.Samoan` | `97` |   |
| `QLocale.Sangho` | `98` |   |
| `QLocale.Sanskrit` | `99` |   |
| `QLocale.Serbian` | `100` |   |
| `QLocale.SerboCroatian` | `101` |   |
| `QLocale.Sesotho` | `102` |   |
| `QLocale.Setswana` | `103` |   |
| `QLocale.Shona` | `104` |   |
| `QLocale.Sindhi` | `105` |   |
| `QLocale.Singhalese` | `106` |   |
| `QLocale.Siswati` | `107` |   |
| `QLocale.Slovak` | `108` |   |
| `QLocale.Slovenian` | `109` |   |
| `QLocale.Somali` | `110` |   |
| `QLocale.Spanish` | `111` |   |
| `QLocale.Sundanese` | `112` |   |
| `QLocale.Swahili` | `113` |   |
| `QLocale.Swedish` | `114` |   |
| `QLocale.Tagalog` | `115` |   |
| `QLocale.Tajik` | `116` |   |
| `QLocale.Tamil` | `117` |   |
| `QLocale.Tatar` | `118` |   |
| `QLocale.Telugu` | `119` |   |
| `QLocale.Thai` | `120` |   |
| `QLocale.Tibetan` | `121` |   |
| `QLocale.Tigrinya` | `122` |   |
| `QLocale.TongaLanguage` | `123` |   |
| `QLocale.Tsonga` | `124` |   |
| `QLocale.Turkish` | `125` |   |
| `QLocale.Turkmen` | `126` |   |
| `QLocale.Twi` | `127` |   |
| `QLocale.Uigur` | `128` |   |
| `QLocale.Ukrainian` | `129` |   |
| `QLocale.Urdu` | `130` |   |
| `QLocale.Uzbek` | `131` |   |
| `QLocale.Vietnamese` | `132` |   |
| `QLocale.Volapuk` | `133` |   |
| `QLocale.Welsh` | `134` |   |
| `QLocale.Wolof` | `135` |   |
| `QLocale.Xhosa` | `136` |   |
| `QLocale.Yiddish` | `137` |   |
| `QLocale.Yoruba` | `138` |   |
| `QLocale.Zhuang` | `139` |   |
| `QLocale.Zulu` | `140` |   |
| `QLocale.Bosnian` | `142` |   |
| `QLocale.Divehi` | `143` |   |
| `QLocale.Manx` | `144` |   |
| `QLocale.Cornish` | `145` |   |
| `QLocale.Akan` | `146` |   |
| `QLocale.Konkani` | `147` |   |
| `QLocale.Ga` | `148` |   |
| `QLocale.Igbo` | `149` |   |
| `QLocale.Kamba` | `150` |   |
| `QLocale.Syriac` | `151` |   |
| `QLocale.Blin` | `152` |   |
| `QLocale.Geez` | `153` |   |
| `QLocale.Koro` | `154` |   |
| `QLocale.Sidamo` | `155` |   |
| `QLocale.Atsam` | `156` |   |
| `QLocale.Tigre` | `157` |   |
| `QLocale.Jju` | `158` |   |
| `QLocale.Friulian` | `159` |   |
| `QLocale.Venda` | `160` |   |
| `QLocale.Ewe` | `161` |   |
| `QLocale.Walamo` | `162` |   |
| `QLocale.Hawaiian` | `163` |   |
| `QLocale.Tyap` | `164` |   |
| `QLocale.Chewa` | `165` |   |
| `QLocale.Filipino` | `166` |   |
| `QLocale.SwissGerman` | `167` |   |
| `QLocale.SichuanYi` | `168` |   |
| `QLocale.Kpelle` | `169` |   |
| `QLocale.LowGerman` | `170` |   |
| `QLocale.SouthNdebele` | `171` |   |
| `QLocale.NorthernSotho` | `172` |   |
| `QLocale.NorthernSami` | `173` |   |
| `QLocale.Taroko` | `174` |   |
| `QLocale.Gusii` | `175` |   |
| `QLocale.Taita` | `176` |   |
| `QLocale.Fulah` | `177` |   |
| `QLocale.Kikuyu` | `178` |   |
| `QLocale.Samburu` | `179` |   |
| `QLocale.Sena` | `180` |   |
| `QLocale.NorthNdebele` | `181` |   |
| `QLocale.Rombo` | `182` |   |
| `QLocale.Tachelhit` | `183` |   |
| `QLocale.Kabyle` | `184` |   |
| `QLocale.Nyankole` | `185` |   |
| `QLocale.Bena` | `186` |   |
| `QLocale.Vunjo` | `187` |   |
| `QLocale.Bambara` | `188` |   |
| `QLocale.Embu` | `189` |   |
| `QLocale.Cherokee` | `190` |   |
| `QLocale.Morisyen` | `191` |   |
| `QLocale.Makonde` | `192` |   |
| `QLocale.Langi` | `193` |   |
| `QLocale.Ganda` | `194` |   |
| `QLocale.Bemba` | `195` |   |
| `QLocale.Kabuverdianu` | `196` |   |
| `QLocale.Meru` | `197` |   |
| `QLocale.Kalenjin` | `198` |   |
| `QLocale.Nama` | `199` |   |
| `QLocale.Machame` | `200` |   |
| `QLocale.Colognian` | `201` |   |
| `QLocale.Masai` | `202` |   |
| `QLocale.Soga` | `203` |   |
| `QLocale.Luyia` | `204` |   |
| `QLocale.Asu` | `205` |   |
| `QLocale.Teso` | `206` |   |
| `QLocale.Saho` | `207` |   |
| `QLocale.KoyraChiini` | `208` |   |
| `QLocale.Rwa` | `209` |   |
| `QLocale.Luo` | `210` |   |
| `QLocale.Chiga` | `211` |   |
| `QLocale.CentralMoroccoTamazight` | `212` |   |
| `QLocale.KoyraboroSenni` | `213` |   |
| `QLocale.Shambala` | `214` |   |

**See also** [language](qlocale.html#language)（）和[languageToString](qlocale.html#languageToString)（ ） 。

```
QLocale.MeasurementSystem
```

这个枚举定义了单元用于测量。

| Constant | Value | Description |
| --- | --- | --- |
| `QLocale.MetricSystem` | `0` | 此值表示度量单位，如米，厘米和毫米。 |
| `QLocale.ImperialSystem` | `1` | 此值表示的英制单位，如英寸和英里。有几种不同的科举制度在世界上，这个值代表了美国官方英制单位。 |

这个枚举被引入或修改的Qt 4.4 。

```
QLocale.NumberOption
```

这个枚举变量定义了一套数到字符串和字符串到数字的转换选项。它们可以被检索以[numberOptions](qlocale.html#numberOptions)（ ），并设置用[setNumberOptions](qlocale.html#setNumberOptions)（ ） 。

| Constant | Value | Description |
| --- | --- | --- |
| `QLocale.OmitGroupSeparator` | `0x01` | 如果这个选项被设置，这个数字到字符串的函数将不插入组分隔在它们的返回值。默认是插入组分隔符。 |
| `QLocale.RejectGroupSeparator` | `0x02` | 如果这个选项被设置，如果他们遇到组分隔符在输入字符串到数字函数将失败。默认为接受含有正确放置组分隔符的数字。 |

该NumberOptions类型是一个typedef为[QFlags](index.htm)\u003cNumberOption\u003e 。它存储NumberOption值的或组合。

**See also** [setNumberOptions](qlocale.html#setNumberOptions)（）和[numberOptions](qlocale.html#numberOptions)（ ） 。

```
QLocale.QuotationStyle
```

这个枚举定义了一组可能的样式设置特定报价。

| Constant | Value | Description |
| --- | --- | --- |
| `QLocale.StandardQuotation` | `0` | 如果这个选项被设置，标准的引号将被用来引用字符串。 |
| `QLocale.AlternateQuotation` | `1` | 如果这个选项被设置，备用引号将被用来引用字符串。 |

这个枚举被引入或修改的Qt 4.8 。

**See also** [quoteString](qlocale.html#quoteString)（ ） 。

```
QLocale.Script
```

这个枚举类型用于指定一个脚本。

| Constant | Value | Description |
| --- | --- | --- |
| `QLocale.AnyScript` | `0` |   |
| `QLocale.ArabicScript` | `1` |   |
| `QLocale.CyrillicScript` | `2` |   |
| `QLocale.DeseretScript` | `3` |   |
| `QLocale.GurmukhiScript` | `4` |   |
| `QLocale.SimplifiedHanScript` | `5` | 同SimplifiedChineseScript |
| `QLocale.SimplifiedChineseScript` | `SimplifiedHanScript` | 同SimplifiedHanScript |
| `QLocale.TraditionalHanScript` | `6` | 同TraditionalChineseScript |
| `QLocale.TraditionalChineseScript` | `TraditionalHanScript` | 同TraditionalHanScript |
| `QLocale.LatinScript` | `7` |   |
| `QLocale.MongolianScript` | `8` |   |
| `QLocale.TifinaghScript` | `9` |   |

这个枚举被引入或修改的Qt 4.8 。

**See also** [script](qlocale.html#script)（ ）[scriptToString](qlocale.html#scriptToString)（）和[languageToString](qlocale.html#languageToString)（ ） 。

* * *

## Method Documentation

```
QLocale.__init__ (self)
```

构造一个[QLocale](qlocale.html)对象的默认区域设置初始化。如果没有默认的locale使用setDefaultLocale （ ）设置，该区域将是相同的由返回的[system](qlocale.html#system)（ ） 。

**See also** [setDefault](qlocale.html#setDefault)（ ） 。

```
QLocale.__init__ (self, QString name)
```

构造一个[QLocale](qlocale.html)与指定对象_name_，它的格式为“语言[ _script ] [ _公司] [ @修饰符] [代码集。 ]”或“C” ，其中：

*   language is a lowercase, two-letter, ISO 639 language code,
*   script is a titlecase, four-letter, ISO 15924 script code,
*   country is an uppercase, two- or three-letter, ISO 3166 country code (also "419" as defined by United Nations),
*   and codeset and modifier are ignored.

分隔符可以是下划线或减号。

如果字符串违背了语言环境格式或语言不是一个有效的ISO 369的代码中，“ C”语言环境来代替。如果国家不存在，或者不是一个有效的ISO 3166代码，最适当的国家是选择了指定的语言。

语言，脚本和国家代码转换为各自的`Language`，`Script`和`Country`枚举。在完成这一转换的构造函数的功能完全一样[QLocale](qlocale.html)（国家，脚本语言） 。

此构造方法要比慢得多[QLocale](qlocale.html)（国家，脚本语言） 。

**See also** [bcp47Name](qlocale.html#bcp47Name)（ ） 。

```
QLocale.__init__ (self, Language language, Country country = QLocale.AnyCountry)
```

构造一个[QLocale](qlocale.html)与指定对象_language_和_country_。

*   If the language/country pair is found in the database, it is used.
*   If the language is found but the country is not, or if the country is `AnyCountry`, the language is used with the most appropriate available country (for example, Germany for German),
*   If neither the language nor the country are found, [QLocale](qlocale.html) defaults to the default locale (see [setDefault](qlocale.html#setDefault)()).

语言和国家的实际使用可以使用查询[language](qlocale.html#language)（）和[country](qlocale.html#country)（ ） 。

**See also** [setDefault](qlocale.html#setDefault)（ ）[language](qlocale.html#language)（）和[country](qlocale.html#country)（ ） 。

```
QLocale.__init__ (self, QLocale other)
```

构造一个[QLocale](qlocale.html)与指定对象_language_，_script_和_country_。

*   If the language/script/country is found in the database, it is used.
*   If both _script_ is [AnyScript](qlocale.html#Script-enum) and _country_ is [AnyCountry](qlocale.html#Country-enum), the language is used with the most appropriate available script and country (for example, Germany for German),
*   If either _script_ is [AnyScript](qlocale.html#Script-enum) or _country_ is [AnyCountry](qlocale.html#Country-enum), the language is used with the first locale that matches the given _script_ and _country_.
*   If neither the language nor the country are found, [QLocale](qlocale.html) defaults to the default locale (see [setDefault](qlocale.html#setDefault)()).

语言，脚本和国家，实际使用可以使用查询[language](qlocale.html#language)（ ）[script](qlocale.html#script)（）和[country](qlocale.html#country)（ ） 。

此功能被引入Qt的4.8 。

**See also** [setDefault](qlocale.html#setDefault)（ ）[language](qlocale.html#language)（ ）[script](qlocale.html#script)（）和[country](qlocale.html#country)（ ） 。

```
QLocale.__init__ (self, Language language, Script script, Country country)
```

构造一个[QLocale](qlocale.html)作为对象的一个副本_other_。

```
QString QLocale.amText (self)
```

返回“AM ”后缀使用12小时制的惯例指定的时间的本地化名称。

此功能被引入Qt的4.5 。

**See also** [pmText](qlocale.html#pmText)（ ） 。

```
QString QLocale.bcp47Name (self)
```

返回此语言环境的破折号分隔的语言，文字和国家（以及其他可能的BCP47域）作为一个字符串。

不同的是[uiLanguages](qlocale.html#uiLanguages)（ ）的bcp47Name的返回值（ ）代表的语言环境名称[QLocale](qlocale.html)数据而不是语言的用户界面应当英寸

这个函数试图以符合区域设置名称BCP47 。

此功能被引入Qt的4.8 。

**See also** [language](qlocale.html#language)（ ）[country](qlocale.html#country)（ ）[script](qlocale.html#script)（）和[uiLanguages](qlocale.html#uiLanguages)（ ） 。

```
QLocale QLocale.c ()
```

[](qlocale.html)

[返回](qlocale.html)[QLocale](qlocale.html)对象初始化为“ C”语言环境。

**See also** [system](qlocale.html#system)（ ） 。

```
list-of-QLocale.Country QLocale.countriesForLanguage (Language lang)
```

```
Country QLocale.country (self)
```

[

返回此语言环境的国家。

](qlocale.html#Country-enum)

[**See also**](qlocale.html#Country-enum) [language](qlocale.html#language)（ ）[script](qlocale.html#script)（ ）[countryToString](qlocale.html#countryToString)（）和[bcp47Name](qlocale.html#bcp47Name)（ ） 。

```
QString QLocale.countryToString (Country country)
```

返回[QString](qstring.html)含有的名_country_。

**See also** [languageToString](qlocale.html#languageToString)（ ）[scriptToString](qlocale.html#scriptToString)（ ）[country](qlocale.html#country)（）和[bcp47Name](qlocale.html#bcp47Name)（ ） 。

```
QString QLocale.createSeparatedList (self, QStringList list)
```

返回一个代表参加的一个给定的字符串_list_字符串与语言环境定义的分隔符。

此功能被引入Qt的4.8 。

```
QString QLocale.currencySymbol (self, CurrencySymbolFormat format = QLocale.CurrencySymbol)
```

根据返回一个货币符号_format_。

此功能被引入Qt的4.8 。

```
QString QLocale.dateFormat (self, FormatType format = QLocale.LongFormat)
```

返回用于当前语言环境的日期格式。

If _format_ is [LongFormat](qlocale.html#FormatType-enum)该格式将是一个漫长的版本。否则，它采用了较短的版本。

这个函数是Qt 4.1中引入。

**See also** [QDate.toString](qdate.html#toString)（）和[QDate.fromString](qdate.html#fromString)（ ） 。

```
QString QLocale.dateTimeFormat (self, FormatType format = QLocale.LongFormat)
```

返回用于当前区域设置的日期时间格式。

If _format_ is [ShortFormat](qlocale.html#FormatType-enum)该格式将是一个短版。否则，它采用了更长的版本。

此功能被引入Qt的4.4 。

**See also** [QDateTime.toString](qdatetime.html#toString)（）和[QDateTime.fromString](qdatetime.html#fromString)（ ） 。

```
QString QLocale.dayName (self, int, FormatType format = QLocale.LongFormat)
```

返回的本地化名称_day_（其中， 1表示星期一， 2代表星期二等等） ，在由指定的格式_type_。

这个函数中引入了Qt 4.2中。

**See also** [monthName](qlocale.html#monthName)（）和[standaloneDayName](qlocale.html#standaloneDayName)（ ） 。

```
QChar QLocale.decimalPoint (self)
```

返回此区域设置的小数点字符。

这个函数是Qt 4.1中引入。

```
QChar QLocale.exponential (self)
```

返回此语言环境的指数字符。

这个函数是Qt 4.1中引入。

```
Qt.DayOfWeek QLocale.firstDayOfWeek (self)
```

[

根据当前的语言环境返回一周的第一天。

此功能被引入Qt的4.8 。

```
QChar QLocale.groupSeparator (self)
```

返回此语言环境的组分隔符。

这个函数是Qt 4.1中引入。

](qt.html#DayOfWeek-enum)

```
Language QLocale.language (self)
```

[

返回此语言环境的语言。

](qlocale.html#Language-enum)

[**See also**](qlocale.html#Language-enum) [script](qlocale.html#script)（ ）[country](qlocale.html#country)（ ）[languageToString](qlocale.html#languageToString)（）和[bcp47Name](qlocale.html#bcp47Name)（ ） 。

```
QString QLocale.languageToString (Language language)
```

返回[QString](qstring.html)含有的名_language_。

**See also** [countryToString](qlocale.html#countryToString)（ ）[scriptToString](qlocale.html#scriptToString)（）和[bcp47Name](qlocale.html#bcp47Name)（ ） 。

```
list-of-QLocale QLocale.matchingLocales (Language language, Script script, Country country)
```

返回匹配给定的有效语言环境的对象列表_language_，_script_和_country_。

让所有语言环境的列表：[QList](index.htm)\u003c[QLocale](qlocale.html)\u003e allLocales = QLocale.matchingLocales （[QLocale.AnyLanguage](qlocale.html#Language-enum)，[QLocale.AnyScript](qlocale.html#Script-enum)，[QLocale.AnyCountry](qlocale.html#Country-enum)） ;

此功能被引入Qt的4.8 。

```
MeasurementSystem QLocale.measurementSystem (self)
```

[

返回该区域的测量系统。

此功能被引入Qt的4.4 。

```
QString QLocale.monthName (self, int, FormatType format = QLocale.LongFormat)
```

返回的本地化名称_month_在由指定的格式_type_。

这个函数中引入了Qt 4.2中。

](qlocale.html#MeasurementSystem-enum)

[**See also**](qlocale.html#MeasurementSystem-enum) [dayName](qlocale.html#dayName)（）和[standaloneMonthName](qlocale.html#standaloneMonthName)（ ） 。

```
QString QLocale.name (self)
```

返回此语言环境的语言和国家为形式的字符串“语言_国家”，其中语言是一个小写的两个字母的ISO 639语言代码，国家是大写，两个或三个字母的ISO 3166国家代码。

请注意，即使[QLocale](qlocale.html)对象是使用显式的脚本，名字（ ）将不会包含它的兼容性原因构成。使用[bcp47Name](qlocale.html#bcp47Name)（ ）来代替，如果你需要一个完整的语言环境名称。

**See also** [QLocale](qlocale.html#QLocale)（ ）[language](qlocale.html#language)（ ）[script](qlocale.html#script)（ ）[country](qlocale.html#country)（）和[bcp47Name](qlocale.html#bcp47Name)（ ） 。

```
QString QLocale.nativeCountryName (self)
```

返回该国的本土名称的语言环境。例如“ Espa駉±一个”对西班牙/西班牙语言环境。

此功能被引入Qt的4.8 。

**See also** [nativeLanguageName](qlocale.html#nativeLanguageName)（）和[countryToString](qlocale.html#countryToString)（ ） 。

```
QString QLocale.nativeLanguageName (self)
```

返回该语言的本机名称的语言环境。例如“ SchwiizertÃ ¼ Ã ¼ TSCH ”的瑞士德语语言环境。

此功能被引入Qt的4.8 。

**See also** [nativeCountryName](qlocale.html#nativeCountryName)（）和[languageToString](qlocale.html#languageToString)（ ） 。

```
QChar QLocale.negativeSign (self)
```

返回此语言环境的负号字符。

这个函数是Qt 4.1中引入。

```
NumberOptions QLocale.numberOptions (self)
```

[](index.htm)

[返回此相关的数字转换的选项](index.htm)[QLocale](qlocale.html)实例。

默认情况下，任何选项都为标准的语言环境设置。

这个函数中引入了Qt 4.2中。

**See also** [setNumberOptions](qlocale.html#setNumberOptions)（ ） 。

```
QChar QLocale.percent (self)
```

返回此语言环境的百分比字符。

这个函数是Qt 4.1中引入。

```
QString QLocale.pmText (self)
```

返回“PM ”后缀使用12小时制的惯例指定的时间的本地化名称。

此功能被引入Qt的4.5 。

**See also** [amText](qlocale.html#amText)（ ） 。

```
QChar QLocale.positiveSign (self)
```

返回此语言环境的积极迹象字符。

此功能被引入Qt的4.5 。

```
QString QLocale.quoteString (self, QString str, QuotationStyle style = QLocale.StandardQuotation)
```

Returns _str_根据当前的语言环境中使用给定的报价单报价_style_。

此功能被引入Qt的4.8 。

```
Script QLocale.script (self)
```

[

返回此语言环境的脚本。

此功能被引入Qt的4.8 。

](qlocale.html#Script-enum)

[**See also**](qlocale.html#Script-enum) [language](qlocale.html#language)（ ）[country](qlocale.html#country)（ ）[languageToString](qlocale.html#languageToString)（ ）[scriptToString](qlocale.html#scriptToString)（）和[bcp47Name](qlocale.html#bcp47Name)（ ） 。

```
QString QLocale.scriptToString (Script script)
```

返回[QString](qstring.html)含有的名_script_。

此功能被引入Qt的4.8 。

**See also** [languageToString](qlocale.html#languageToString)（ ）[countryToString](qlocale.html#countryToString)（ ）[script](qlocale.html#script)（）和[bcp47Name](qlocale.html#bcp47Name)（ ） 。

```
QLocale.setDefault (QLocale locale)
```

设置全局默认语言环境_locale_。这些值被用于当[QLocale](qlocale.html)对象被构造带任何参数。如果这个功能不叫，系统的区域设置。

**Warning:**在多线程应用程序中，默认区域设置应设置在应用程序启动时，在创建任何非GUI线程之前。

**Warning:**此功能不[reentrant](index.htm#reentrant)。

**See also** [system](qlocale.html#system)（）和[c](qlocale.html#c)（ ） 。

```
QLocale.setNumberOptions (self, NumberOptions options)
```

设置_options_有关数字转换为这个[QLocale](qlocale.html)实例。

这个函数中引入了Qt 4.2中。

**See also** [numberOptions](qlocale.html#numberOptions)（ ） 。

```
QString QLocale.standaloneDayName (self, int, FormatType format = QLocale.LongFormat)
```

返回的本地化名称_day_（其中， 1表示星期一， 2代表星期二等等），它作为一个独立的文本中，在由指定的格式_type_。

如果区域设置信息不指定独立日名称则返回值是一样的[dayName](qlocale.html#dayName)（ ） 。

此功能被引入Qt的4.5 。

**See also** [dayName](qlocale.html#dayName)（）和[standaloneMonthName](qlocale.html#standaloneMonthName)（ ） 。

```
QString QLocale.standaloneMonthName (self, int, FormatType format = QLocale.LongFormat)
```

返回的本地化名称_month_被用作一个独立的文本中，在由指定的格式_type_。

如果区域设置信息不指定独立的月份名称，然后返回值是一样的[monthName](qlocale.html#monthName)（ ） 。

此功能被引入Qt的4.5 。

**See also** [monthName](qlocale.html#monthName)（）和[standaloneDayName](qlocale.html#standaloneDayName)（ ） 。

```
QLocale QLocale.system ()
```

[](qlocale.html)

[返回](qlocale.html)[QLocale](qlocale.html)对象初始化系统区域设置。

在Windows和Mac上，这个区域将使用十进制/分组在系统配置面板中指定的字符和日期/时间格式。

**See also** [c](qlocale.html#c)（ ） 。

```
Qt.LayoutDirection QLocale.textDirection (self)
```

[

返回该语言的文字方向。

此功能被引入Qt的4.7 。

```
QString QLocale.timeFormat (self, FormatType format = QLocale.LongFormat)
```

返回用于当前语言环境的时间格式。

](qt.html#LayoutDirection-enum)

[If _format_ is](qt.html#LayoutDirection-enum) [LongFormat](qlocale.html#FormatType-enum)该格式将是一个漫长的版本。否则，它采用了较短的版本。

这个函数是Qt 4.1中引入。

**See also** [QTime.toString](qtime.html#toString)（）和[QTime.fromString](qtime.html#fromString)（ ） 。

```
QString QLocale.toCurrencyString (self, int value, QString symbol = QString())
```

返回一个本地化的字符串表示形式_value_作为货币。如果_symbol_是只要它是用来代替默认货币符号。

此功能被引入Qt的4.8 。

**See also** [currencySymbol](qlocale.html#currencySymbol)（ ） 。

```
QString QLocale.toCurrencyString (self, float value, QString symbol = QString())
```

这是一个重载函数。

此功能被引入Qt的4.8 。

```
QString QLocale.toCurrencyString (self, int value, QString symbol = QString())
```

这是一个重载函数。

此功能被引入Qt的4.8 。

```
QString QLocale.toCurrencyString (self, int value, QString symbol = QString())
```

这是一个重载函数。

此功能被引入Qt的4.8 。

```
QDate QLocale.toDate (self, QString string, FormatType format = QLocale.LongFormat)
```

[](qdate.html)

[解析中所给出的日期字符串_string_和返回日期。日期字符串的格式是根据所选择的_format_参数（见](qdate.html)[dateFormat](qlocale.html#dateFormat)（））。

如果日期无法解析，返回无效日期。

此功能被引入Qt的4.4 。

**See also** [dateFormat](qlocale.html#dateFormat)（ ）[toTime](qlocale.html#toTime)（ ）[toDateTime](qlocale.html#toDateTime)（）和[QDate.fromString](qdate.html#fromString)（ ） 。

```
QDate QLocale.toDate (self, QString string, QString format)
```

[](qdate.html)

[解析中所给出的日期字符串_string_和返回日期。看](qdate.html)[QDate.fromString](qdate.html#fromString)（）就可以使用此功能使用的表达式的信息。

该函数查找的月份名称和星期几的当前语言环境的名称。

如果日期无法解析，返回无效日期。

此功能被引入Qt的4.4 。

**See also** [dateFormat](qlocale.html#dateFormat)（ ）[toTime](qlocale.html#toTime)（ ）[toDateTime](qlocale.html#toDateTime)（）和[QDate.fromString](qdate.html#fromString)（ ） 。

```
QDateTime QLocale.toDateTime (self, QString string, FormatType format = QLocale.LongFormat)
```

[](qdatetime.html)

[解析中给出的日期/时间字符串_string_并返回的时间。的日期/时间字符串的格式是根据所选择的_format_参数（见](qdatetime.html)[dateTimeFormat](qlocale.html#dateTimeFormat)（））。

如果字符串不能解析，则返回一个无效的[QDateTime](qdatetime.html)。

此功能被引入Qt的4.4 。

**See also** [dateTimeFormat](qlocale.html#dateTimeFormat)（ ）[toTime](qlocale.html#toTime)（ ）[toDate](qlocale.html#toDate)（）和[QDateTime.fromString](qdatetime.html#fromString)（ ） 。

```
QDateTime QLocale.toDateTime (self, QString string, QString format)
```

[](qdatetime.html)

[解析中给出的日期/时间字符串_string_并返回的时间。看](qdatetime.html)[QDateTime.fromString](qdatetime.html#fromString)（）就可以使用此功能使用的表达式的信息。

**Note:**所使用的月和日的名称必须在用户的本地语言来给出。

如果字符串不能解析，则返回一个无效的[QDateTime](qdatetime.html)。

此功能被引入Qt的4.4 。

**See also** [dateTimeFormat](qlocale.html#dateTimeFormat)（ ）[toTime](qlocale.html#toTime)（ ）[toDate](qlocale.html#toDate)（）和[QDateTime.fromString](qdatetime.html#fromString)（ ） 。

```
(float, bool ok) QLocale.toDouble (self, QString s)
```

返回由本地化的字符串表示的double_s_，或0.0 ，如果转换失败。

If _ok_不为0 ，通过设置*确定为False，并成功通过设置*确定真正的故障报告。

不像[QString.toDouble](qstring.html#toDouble)（ ） ，这个函数不回落到了“ C”语言环境，如果该字符串不能在此区域进行解释。

```
 bool ok;
 double d;

 [QLocale](qlocale.html) c([QLocale](qlocale.html).C);
 d = c.toDouble( "1234.56", &ok );  // ok == true, d == 1234.56
 d = c.toDouble( "1,234.56", &ok ); // ok == true, d == 1234.56
 d = c.toDouble( "1234,56", &ok );  // ok == false

 [QLocale](qlocale.html) german([QLocale](qlocale.html).German);
 d = german.toDouble( "1234,56", &ok );  // ok == true, d == 1234.56
 d = german.toDouble( "1.234,56", &ok ); // ok == true, d == 1234.56
 d = german.toDouble( "1234.56", &ok );  // ok == false

 d = german.toDouble( "1.234", &ok );    // ok == true, d == 1234.0

```

请注意，最后转换返回1234.0 ，因为'。'在德语语言环境的数千组分隔符。

此函数忽略前导和尾随空白。

**See also** [toFloat](qlocale.html#toFloat)（ ）[toInt](qlocale.html#toInt)（）和[toString](qlocale.html#toString)（ ） 。

```
(float, bool ok) QLocale.toFloat (self, QString s)
```

返回由本地化的字符串表示的float_s_，或0.0 ，如果转换失败。

If _ok_不为0 ，通过设置*确定为False，并成功通过设置*确定真正的故障报告。

此函数忽略前导和尾随空白。

**See also** [toDouble](qlocale.html#toDouble)（ ）[toInt](qlocale.html#toInt)（）和[toString](qlocale.html#toString)（ ） 。

```
(int, bool ok) QLocale.toInt (self, QString s, int base = 0)
```

返回由本地化的字符串表示的整数_s_使用基_base_。如果_base_为0的基极被自动使用以下规则确定：如果字符串开头的“0x ” ，它被假定为十六进制的，如果它以“ 0 ”时，它被假定为八进制，否则它被假定为十进制。

如果转换失败则函数返回0 。

If _ok_不为0 ，故障报告通过设置*确定为False ，并成功通过设置*确定为True。

此函数忽略前导和尾随空白。

**See also** [toUInt](qlocale.html#toUInt)（）和[toString](qlocale.html#toString)（ ） 。

```
(int, bool ok) QLocale.toLongLong (self, QString s, int base = 0)
```

返回长long int类型的本地化字符串表示_s_使用基_base_。如果_base_为0的基极被自动使用以下规则确定：如果字符串开头的“0x ” ，它被假定为十六进制的，如果它以“ 0 ”时，它被假定为八进制，否则它被假定为十进制。

如果转换失败则函数返回0 。

If _ok_不为0 ，故障报告通过设置*确定为False ，并成功通过设置*确定为True。

此函数忽略前导和尾随空白。

**See also** [toInt](qlocale.html#toInt)（ ）[toULongLong](qlocale.html#toULongLong)（ ）[toDouble](qlocale.html#toDouble)（）和[toString](qlocale.html#toString)（ ） 。

```
QString QLocale.toLower (self, QString str)
```

返回一个小写副本_str_。

此功能被引入Qt的4.8 。

```
(int, bool ok) QLocale.toShort (self, QString s, int base = 0)
```

返回由本地化的字符串表示的短整型_s_使用基_base_。如果_base_为0的基极被自动使用以下规则确定：如果字符串开头的“0x ” ，它被假定为十六进制的，如果它以“ 0 ”时，它被假定为八进制，否则它被假定为十进制。

如果转换失败则函数返回0 。

If _ok_不为0 ，故障报告通过设置*确定为False ，并成功通过设置*确定为True。

此函数忽略前导和尾随空白。

**See also** [toUShort](qlocale.html#toUShort)（）和[toString](qlocale.html#toString)（ ） 。

```
QString QLocale.toString (self, int i)
```

返回一个本地化的字符串表示形式_i_。

**See also** [toLongLong](qlocale.html#toLongLong)（ ） 。

```
QString QLocale.toString (self, float i, str format = 'g', int precision = 6)
```

返回给定一个本地化的字符串表示形式_date_在指定的_format_。如果_format_是一个空字符串，则返回一个空字符串。

```
QString QLocale.toString (self, int i)
```

返回给定一个本地化的字符串表示形式_date_根据指定的_format_。

```
QString QLocale.toString (self, int i)
```

返回给定一个本地化的字符串表示形式_time_根据指定的_format_。如果_format_是一个空字符串，则返回一个空字符串。

```
QString QLocale.toString (self, QDateTime dateTime, QString format)
```

返回给定一个本地化的字符串表示形式_time_在指定的_format_。

```
QString QLocale.toString (self, QDateTime dateTime, FormatType format = QLocale.LongFormat)
```

返回给定一个本地化的字符串表示形式_dateTime_根据指定的_format_。

此功能被引入Qt的4.4 。

```
QString QLocale.toString (self, QDate date, QString formatStr)
```

返回给定一个本地化的字符串表示形式_dateTime_根据指定的_format_。如果_format_是一个空字符串，则返回一个空字符串。

此功能被引入Qt的4.4 。

```
QString QLocale.toString (self, QDate date, FormatType format = QLocale.LongFormat)
```

这是一个重载函数。

**See also** [toULongLong](qlocale.html#toULongLong)（ ） 。

```
QString QLocale.toString (self, QTime time, QString formatStr)
```

这是一个重载函数。

_f_和_prec_具有相同涵义与QString.number （双，字符型，整型） 。

**See also** [toDouble](qlocale.html#toDouble)（ ） 。

```
QString QLocale.toString (self, QTime time, FormatType format = QLocale.LongFormat)
```

这是一个重载函数。

**See also** [toShort](qlocale.html#toShort)（ ） 。

```
QTime QLocale.toTime (self, QString string, FormatType format = QLocale.LongFormat)
```

[](qtime.html)

[解析中给出的时间字符串_string_并返回的时间。时间字符串的格式是根据所选择的_format_参数（见](qtime.html)[timeFormat](qlocale.html#timeFormat)（））。

如果时间无法解析，则返回一个无效的时间。

此功能被引入Qt的4.4 。

**See also** [timeFormat](qlocale.html#timeFormat)（ ）[toDate](qlocale.html#toDate)（ ）[toDateTime](qlocale.html#toDateTime)（）和[QTime.fromString](qtime.html#fromString)（ ） 。

```
QTime QLocale.toTime (self, QString string, QString format)
```

[](qtime.html)

[解析中给出的时间字符串_string_并返回的时间。看](qtime.html)[QTime.fromString](qtime.html#fromString)（ ）对于什么是有效的格式字符串的信息。

如果时间无法解析，则返回一个无效的时间。

此功能被引入Qt的4.4 。

**See also** [timeFormat](qlocale.html#timeFormat)（ ）[toDate](qlocale.html#toDate)（ ）[toDateTime](qlocale.html#toDateTime)（）和[QTime.fromString](qtime.html#fromString)（ ） 。

```
(int, bool ok) QLocale.toUInt (self, QString s, int base = 0)
```

返回由本地化的字符串表示的无符号整型_s_使用基_base_。如果_base_为0的基极被自动使用以下规则确定：如果字符串开头的“0x ” ，它被假定为十六进制的，如果它以“ 0 ”时，它被假定为八进制，否则它被假定为十进制。

如果转换失败则函数返回0 。

If _ok_不为0 ，故障报告通过设置*确定为False ，并成功通过设置*确定为True。

此函数忽略前导和尾随空白。

**See also** [toInt](qlocale.html#toInt)（）和[toString](qlocale.html#toString)（ ） 。

```
(int, bool ok) QLocale.toULongLong (self, QString s, int base = 0)
```

返回无符号长整型长的本地化字符串表示_s_使用基_base_。如果_base_为0的基极被自动使用以下规则确定：如果字符串开头的“0x ” ，它被假定为十六进制的，如果它以“ 0 ”时，它被假定为八进制，否则它被假定为十进制。

如果转换失败则函数返回0 。

If _ok_不为0 ，故障报告通过设置*确定为False ，并成功通过设置*确定为True。

此函数忽略前导和尾随空白。

**See also** [toLongLong](qlocale.html#toLongLong)（ ）[toInt](qlocale.html#toInt)（ ）[toDouble](qlocale.html#toDouble)（）和[toString](qlocale.html#toString)（ ） 。

```
QString QLocale.toUpper (self, QString str)
```

返回的大写副本_str_。

此功能被引入Qt的4.8 。

```
(int, bool ok) QLocale.toUShort (self, QString s, int base = 0)
```

返回由本地化的字符串表示的无符号短整型_s_使用基_base_。如果_base_为0的基极被自动使用以下规则确定：如果字符串开头的“0x ” ，它被假定为十六进制的，如果它以“ 0 ”时，它被假定为八进制，否则它被假定为十进制。

如果转换失败则函数返回0 。

If _ok_不为0 ，故障报告通过设置*确定为False ，并成功通过设置*确定为True。

此函数忽略前导和尾随空白。

**See also** [toShort](qlocale.html#toShort)（）和[toString](qlocale.html#toString)（ ） 。

```
QStringList QLocale.uiLanguages (self)
```

返回地区名称的翻译目的优先次序的排序列表。

返回值表示用户希望看到的用户界面翻译英寸的地区名

最喜欢你不需要直接使用这个功能，但只是通过[QLocale](qlocale.html)反对[QTranslator.load](qtranslator.html#load)（）函数。

该列表中的第一个项目是最首选之一。

此功能被引入Qt的4.8 。

**See also** [QTranslator](qtranslator.html)和[bcp47Name](qlocale.html#bcp47Name)（ ） 。

```
list-of-Qt.DayOfWeek QLocale.weekdays (self)
```

返回的天那是根据当前的locale认为平日列表。

此功能被引入Qt的4.8 。

```
QChar QLocale.zeroDigit (self)
```

返回此语言环境的数字零字符。

这个函数是Qt 4.1中引入。

```
bool QLocale.__eq__ (self, QLocale other)
```

```
bool QLocale.__ne__ (self, QLocale other)
```