# QFont Class Reference

## [[QtGui](index.htm) module]

该QFont类指定用于绘制文本的字体。[More...](#details)

### Types

*   `enum Capitalization { MixedCase, AllUppercase, AllLowercase, SmallCaps, Capitalize }`
*   `enum HintingPreference { PreferDefaultHinting, PreferNoHinting, PreferVerticalHinting, PreferFullHinting }`
*   `enum SpacingType { PercentageSpacing, AbsoluteSpacing }`
*   `enum Stretch { UltraCondensed, ExtraCondensed, Condensed, SemiCondensed, ..., UltraExpanded }`
*   `enum Style { StyleNormal, StyleItalic, StyleOblique }`
*   `enum StyleHint { Helvetica, SansSerif, Times, Serif, ..., Fantasy }`
*   `enum StyleStrategy { PreferDefault, PreferBitmap, PreferDevice, PreferOutline, ..., ForceIntegerMetrics }`
*   `enum Weight { Light, Normal, DemiBold, Bold, Black }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QString family, int pointSize = -1, int weight = -1, bool italic = False)`
*   `__init__ (self, QFont, QPaintDevice pd)`
*   `__init__ (self, QFont)`
*   `__init__ (self, QVariant variant)`
*   `bool bold (self)`
*   `Capitalization capitalization (self)`
*   `QString defaultFamily (self)`
*   `bool exactMatch (self)`
*   `QString family (self)`
*   `bool fixedPitch (self)`
*   `bool fromString (self, QString)`
*   `int handle (self)`
*   `HintingPreference hintingPreference (self)`
*   `bool isCopyOf (self, QFont)`
*   `bool italic (self)`
*   `bool kerning (self)`
*   `QString key (self)`
*   `QString lastResortFamily (self)`
*   `QString lastResortFont (self)`
*   `float letterSpacing (self)`
*   `SpacingType letterSpacingType (self)`
*   `bool overline (self)`
*   `int pixelSize (self)`
*   `int pointSize (self)`
*   `float pointSizeF (self)`
*   `bool rawMode (self)`
*   `QString rawName (self)`
*   `QFont resolve (self, QFont)`
*   `setBold (self, bool enable)`
*   `setCapitalization (self, Capitalization)`
*   `setFamily (self, QString)`
*   `setFixedPitch (self, bool)`
*   `setHintingPreference (self, HintingPreference hintingPreference)`
*   `setItalic (self, bool b)`
*   `setKerning (self, bool)`
*   `setLetterSpacing (self, SpacingType type, float spacing)`
*   `setOverline (self, bool)`
*   `setPixelSize (self, int)`
*   `setPointSize (self, int)`
*   `setPointSizeF (self, float)`
*   `setRawMode (self, bool)`
*   `setRawName (self, QString)`
*   `setStretch (self, int)`
*   `setStrikeOut (self, bool)`
*   `setStyle (self, Style style)`
*   `setStyleHint (self, StyleHint hint, StyleStrategy strategy = QFont.PreferDefault)`
*   `setStyleName (self, QString styleName)`
*   `setStyleStrategy (self, StyleStrategy s)`
*   `setUnderline (self, bool)`
*   `setWeight (self, int)`
*   `setWordSpacing (self, float spacing)`
*   `int stretch (self)`
*   `bool strikeOut (self)`
*   `Style style (self)`
*   `StyleHint styleHint (self)`
*   `QString styleName (self)`
*   `StyleStrategy styleStrategy (self)`
*   `QString toString (self)`
*   `bool underline (self)`
*   `int weight (self)`
*   `float wordSpacing (self)`

### Static Methods

*   `cacheStatistics ()`
*   `cleanup ()`
*   `initialize ()`
*   `insertSubstitution (QString, QString)`
*   `insertSubstitutions (QString, QStringList)`
*   `removeSubstitution (QString)`
*   `QString substitute (QString)`
*   `QStringList substitutes (QString)`
*   `QStringList substitutions ()`

### Special Methods

*   `bool __eq__ (self, QFont)`
*   `bool __ge__ (self, QFont)`
*   `bool __lt__ (self, QFont)`
*   `bool __ne__ (self, QFont)`

* * *

## Detailed Description

该QFont类指定用于绘制文本的字体。

当你创建一个QFont对象，你指定你想要的字体有不同的属性。 Qt会使用的字体与指定的属性，或者如果没有匹配的字体存在， Qt会使用最接近的匹配安装的字体。实际使用的字体的属性是由可回收[QFontInfo](qfontinfo.html)对象。如果窗口系统提供的精确匹配[exactMatch](qfont.html#exactMatch)（ ）返回True 。使用[QFontMetrics](qfontmetrics.html)以获得测量值，例如使用字符串的像素长度[QFontMetrics.width](qfontmetrics.html#width)（ ） 。

请注意，一个[QApplication](qapplication.html)实例必须存在一个QFont才能使用。您可以设置应用程序的默认字体，[QApplication.setFont](qapplication.html#setFont)（ ） 。

如果选择的字体不包括所有需要显示的字符， QFont将试图找到在最接近的字体的字符。当[QPainter](qpainter.html)绘制一个字符从字体QFont会报告它是否有性格，如果没有的话，[QPainter](qpainter.html)将绘制一个空心的方形。

创建这样QFonts ：

```
 QFont serifFont("Times", 10, QFont.Bold);
 QFont sansFont("Helvetica [Cronyx]", 12);

```

在构造函数中设置的属性也可以在以后设置，例如：[setFamily](qfont.html#setFamily)（ ）[setPointSize](qfont.html#setPointSize)（ ）[setPointSizeFloat](index.htm#setPointSizeFloat)（ ）[setWeight](qfont.html#setWeight)（）和[setItalic](qfont.html#setItalic)（ ） 。其馀的属性后，必须contstruction ，例如设置[setBold](qfont.html#setBold)（ ）[setUnderline](qfont.html#setUnderline)（ ）[setOverline](qfont.html#setOverline)（ ）[setStrikeOut](qfont.html#setStrikeOut)（）和[setFixedPitch](qfont.html#setFixedPitch)（ ） 。[QFontInfo](qfontinfo.html)要创建的对象_after_字体的属性已被置位。一[QFontInfo](qfontinfo.html)对象将不会改变，即使改变字体的属性。相应的“获取”功能，例如[family](qfont.html#family)（ ）[pointSize](qfont.html#pointSize)（ ）等等，返回已设置的值，即使所使用的值可能不同。的实际值可以从一个[QFontInfo](qfontinfo.html)对象。

如果请求的字体系列不可用，你可以影响[font matching algorithm](#fontmatching)通过选择一个特定的[QFont.StyleHint](qfont.html#StyleHint-enum)和[QFont.StyleStrategy](qfont.html#StyleStrategy-enum)同[setStyleHint](qfont.html#setStyleHint)（ ） 。缺省家族（对应于当前样式的提示）被返回[defaultFamily](qfont.html#defaultFamily)（ ） 。

字体匹配算法有[lastResortFamily](qfont.html#lastResortFamily)（）和[lastResortFont](qfont.html#lastResortFont)（ ）在一个合适的匹配不能被发现的情况。您可以提供替代使用字体系列名称[insertSubstitution](qfont.html#insertSubstitution)（）和[insertSubstitutions](qfont.html#insertSubstitutions)（ ） 。取代基可以与被删除[removeSubstitution](qfont.html#removeSubstitution)（ ） 。使用[substitute](qfont.html#substitute)（ ）来获取一个家庭的第一替补，或姓本身，如果它没有替代品。使用[substitutes](qfont.html#substitutes)（ ）来获取一个家庭的替代品列表（可能为空） 。

每QFont有[key](qfont.html#key)（），它可以使用，例如，如在高速缓存或字典中的键。如果你想存储用户的字体首选项，您可以使用[QSettings](qsettings.html)，与写入的字体信息[toString](qfont.html#toString)（ ），并阅读它带回来[fromString](qfont.html#fromString)（ ） 。该运算符\u003c\u003c （）和operator \u003e\u003e （ ）功能也都具备，但他们的数据流工作。

它可以设置在屏幕上显示的字符，以像素为单位的指定数量的高度与[setPixelSize](qfont.html#setPixelSize)（ ），但是使用[setPointSize](qfont.html#setPointSize)（ ）也有类似的效果，并提供设备独立性。

在X11中，您可以使用其系统的具体名称与设置字体[setRawName](qfont.html#setRawName)（ ） 。

加载中字体可以是昂贵的，特别是在X11 。 QFont包含大量的优化，以使QFont的复制对象快，缓存它依赖于缓慢窗口系统功能的结果。

字体匹配算法的工作原理如下：

1.  指定字体系列中搜索。
2.  如果没有找到，[styleHint](qfont.html#styleHint)（）是用来选择一个替换的家庭。
3.  每次更换字体系列中搜索。
4.  如果没有这些被发现或没有[styleHint](qfont.html#styleHint)（ ） ， “黑体”将搜索。
5.  如果找不到“黑体” Qt会尝试[lastResortFamily](qfont.html#lastResortFamily)（ ） 。
6.  如果[lastResortFamily](qfont.html#lastResortFamily)（ ）没有找到Qt会尝试[lastResortFont](qfont.html#lastResortFont)（）将总是返回某种类型的名称。

请注意，实际的字体匹配算法变化从平台到平台。

在Windows的“信使”字体的请求将被自动更改为“宋体” ，快递的改进版本，它允许平滑缩放。旧的“信使”位图字体可以通过设置选择[PreferBitmap](qfont.html#StyleStrategy-enum)风格策略（见[setStyleStrategy](qfont.html#setStyleStrategy)（））。

一旦字体被发现，其馀的属性是匹配的优先顺序：

1.  [fixedPitch](qfont.html#fixedPitch)（ ）
2.  [pointSize](qfont.html#pointSize)（） （见下文）
3.  [weight](qfont.html#weight)（ ）
4.  [style](qfont.html#style)（ ）

如果你有一个相匹配的家庭字体，即使没有其他属性匹配，该字体将选择优先于字体不上家人匹配，但它确实对其他属性的匹配。这是因为字体家族是佔主导地位的搜索条件。

点的大小被定义为匹配，如果它是在所需的点尺寸的20％。当几个字体匹配，并且只由点的大小区分，与最接近的点大小为所请求的字体将被选择。

用于绘制文本的实际家庭，字体大小，重量等字体属性将取决于什么可供选择的家庭下的窗口系统。一[QFontInfo](qfontinfo.html)对象可以被用来确定用于绘制文本的实际值。

示例：

```
 QFont f("Helvetica");

```

如果你同时有一个Adobe和Cronyx Helvetica字体，你可能会得到两种。

```
 QFont f("Helvetica [Cronyx]");

```

您可以在家庭中的名称来指定你想要的代工。在上面的例子中的字体F可以被设置为“黑体[ Cronyx ]” 。

为了确定在窗口系统中实际使用的字体的属性，使用[QFontInfo](qfontinfo.html)对象，例如

```
 [QFontInfo](qfontinfo.html) info(f1);
 [QString](qstring.html) family = info.family();

```

要了解字体规格使用[QFontMetrics](qfontmetrics.html)对象，例如

```
 [QFontMetrics](qfontmetrics.html) fm(f1);
 int textWidthInPixels = fm.width("How many pixels wide is this text?");
 int textHeightInPixels = fm.height();

```

有关字体的常规信息，请参阅[comp.fonts FAQ.](http://nwalsh.com/comp.fonts/FAQ/)关于编码的信息可以发现[Roman Czyborra's](http://czyborra.com/)页面。

* * *

## Type Documentation

```
QFont.Capitalization
```

渲染选项，这个文本字体适用于。

| Constant | Value | Description |
| --- | --- | --- |
| `QFont.MixedCase` | `0` | 这是没有市值变化所应用的普通文本渲染选项。 |
| `QFont.AllUppercase` | `1` | 这改变在全部大写类型所要呈现的文本。 |
| `QFont.AllLowercase` | `2` | 这会改变所有小写类型所要呈现的文本。 |
| `QFont.SmallCaps` | `3` | 这改变了在小型股型要呈现的文本。 |
| `QFont.Capitalize` | `4` | 这改变与每个单词的第一个字符被呈现为一个大写字符的文本。 |

这个枚举被引入或修改的Qt 4.4 。

```
QFont.HintingPreference
```

该枚举描述暗示的不同级别，可以应用到字形，以提高易读性的地方，否则可能由像素的密度来保证显示器。

| Constant | Value | Description |
| --- | --- | --- |
| `QFont.PreferDefaultHinting` | `0` | 使用默认的暗示水平为目标平台。 |
| `QFont.PreferNoHinting` | `1` | 如果可能的话，渲染文本，而不提示字形的轮廓。文本布局将是印刷上准确的和可扩展性，使用与被使用，例如相同的度量打印时。 |
| `QFont.PreferVerticalHinting` | `2` | 如果可能的话，呈现文本无水平暗示，但字形排列的像素网格在垂直方向上。该文字会出现在其中显示的密度太低保鲜盒给予字形的准确渲染。但由于字形的水平度量unhinted ，文字的布局将扩展到更高密度的设备（如打印机） ，而不会影响细节，比如换行符。 |
| `QFont.PreferFullHinting` | `3` | 如果可能的话，呈现文本与暗示在水平和垂直方向。该文本将被修改，以优化可读性的目标设备上，但由于指标将取决于文本的目标大小，字形，换行符和其他排版细节的位置将无法扩展，这意味着文本的布局可能会与不同像素密度的设备不同。 |

请注意，此枚举只描述一个偏好，以全方位暗示的水平上不支持所有的Qt支持的平台的。下表载列于目标平台的选定的一组给定的暗示偏好的影响。

|  | PreferDefaultHinting | PreferNoHinting | PreferVerticalHinting | PreferFullHinting |
| --- | --- | --- | --- | --- |
| Windows Vista (w/o Platform Update) and earlier | Full hinting | Full hinting | Full hinting | Full hinting |
| Windows 7 and Windows Vista (w/Platform Update) and DirectWrite enabled in Qt | Full hinting | Vertical hinting | Vertical hinting | Full hinting |
| [FreeType](index.htm#freetype) | Operating System setting | No hinting | Vertical hinting (light) | Full hinting |
| Cocoa on Mac OS X | No hinting | No hinting | No hinting | No hinting |

**Note:**请注意，改变在Windows上提示的偏好可通过DirectWrite的字体引擎。这是适用于Windows Vista上安装平台更新后，和Windows 7 。为了使用这个扩展，配置Qt的使用， DirectWrite的。然后，目标应用程序将取决于DirectWrite中的目标系统上的可用性。

这个枚举被引入或修改的Qt 4.8 。

```
QFont.SpacingType
```

| Constant | Value | Description |
| --- | --- | --- |
| `QFont.PercentageSpacing` | `0` | 100的值将保持间距不变;值200将人物本身的宽度的字符后扩大的间距。 |
| `QFont.AbsoluteSpacing` | `1` | 正值增加字母间距由相应的像素;负值减小的间距。 |

这个枚举被引入或修改的Qt 4.4 。

```
QFont.Stretch
```

按照CSS的命名约定的预定义的拉伸值。该值越高，越伸文字是。

| Constant | Value | Description |
| --- | --- | --- |
| `QFont.UltraCondensed` | `50` | 50 |
| `QFont.ExtraCondensed` | `62` | 62 |
| `QFont.Condensed` | `75` | 75 |
| `QFont.SemiCondensed` | `87` | 87 |
| `QFont.Unstretched` | `100` | 100 |
| `QFont.SemiExpanded` | `112` | 112 |
| `QFont.Expanded` | `125` | 125 |
| `QFont.ExtraExpanded` | `150` | 150 |
| `QFont.UltraExpanded` | `200` | 200 |

**See also** [setStretch](qfont.html#setStretch)（）和[stretch](qfont.html#stretch)（ ） 。

```
QFont.Style
```

这个枚举变量描述了不同风格的字形，用于显示文本。

| Constant | Value | Description |
| --- | --- | --- |
| `QFont.StyleNormal` | `0` | 在无样式的文本中使用的正常字形。 |
| `QFont.StyleItalic` | `1` | 斜体字形专为代表斜体文本的目的而设计的。 |
| `QFont.StyleOblique` | `2` | 字形与通常基于无样式字形，但微调来表示斜体文本的目的，斜体的外观。 |

**See also** [Weight](qfont.html#Weight-enum)。

```
QFont.StyleHint
```

风格提示所使用的[font matching](qfont.html)算法来找到一个合适的默认的家庭，如果选择的字体系列不可用。

| Constant | Value | Description |
| --- | --- | --- |
| `QFont.AnyStyle` | ？ | 离开的字体匹配算法来选择家庭。这是默认的。 |
| `QFont.SansSerif` | `Helvetica` | 字体匹配更喜欢无衬线字体。 |
| `QFont.Helvetica` | `0` | 是同义词`SansSerif`。 |
| `QFont.Serif` | `Times` | 字体匹配更喜欢serif字体。 |
| `QFont.Times` | ？ | 是同义词`Serif`。 |
| `QFont.TypeWriter` | `Courier` | 字体匹配更喜欢固定的间距字体。 |
| `QFont.Courier` | ？ | 同义词`TypeWriter`。 |
| `QFont.OldEnglish` | ？ | 字体匹配更喜欢装饰性字体。 |
| `QFont.Decorative` | `OldEnglish` | 是同义词`OldEnglish`。 |
| `QFont.Monospace` | ？ | 字体匹配倾向于映射到CSS通用字体家庭“等宽”字体。 |
| `QFont.Fantasy` | ？ | 字体匹配倾向于映射到CSS通用字体家族'幻想'字型。 |
| `QFont.Cursive` | ？ | 字体匹配倾向于映射到CSS通用字体家族“草书”字体。 |
| `QFont.System` | ？ | 字体匹配喜欢的系统字体。 |

```
QFont.StyleStrategy
```

风格策略告诉[font matching](qfont.html)算法是什么类型的字体应该被用来找到一个合适的默认的家人。

以下策略可供选择：

| Constant | Value | Description |
| --- | --- | --- |
| `QFont.PreferDefault` | `0x0001` | 默认样式的策略。它不喜欢的任何类型的字体。 |
| `QFont.PreferBitmap` | `0x0002` | 喜欢点阵字体（相对于轮廓字体） 。 |
| `QFont.PreferDevice` | `0x0004` | 喜欢的设备字体。 |
| `QFont.PreferOutline` | `0x0008` | 喜欢轮廓字体（相对于位图字体） 。 |
| `QFont.ForceOutline` | `0x0010` | 强制使用轮廓字体。 |
| `QFont.NoAntialias` | `0x0100` | 不消除锯齿的字体。 |
| `QFont.PreferAntialias` | `0x0080` | 如果可能的话反锯齿。 |
| `QFont.OpenGLCompatible` | `0x0200` | 强制使用兼容OpenGL字体。 |
| `QFont.NoFontMerging` | `0x8000` | If the font selected for a certain writing system does not contain a character requested to draw, then Qt automatically chooses a similar looking font that contains the character. The NoFontMerging flag disables this feature. Please note that enabling this flag will not prevent Qt from automatically picking a suitable font when the selected font does not support the writing system of the text. |

任何这些可能是或的结果与这些标志之一：

| Constant | Value | Description |
| --- | --- | --- |
| `QFont.PreferMatch` | `0x0020` | 喜欢的精确匹配。字体匹配器将尝试使用已指定的确切的字体大小。 |
| `QFont.PreferQuality` | `0x0040` | 喜欢最优质的字体。字体匹配器将使用该字体支持的最接近的标准点的大小。 |
| `QFont.ForceIntegerMetrics` | `0x0400` | 部队在支持小数字体规格的字体引擎中使用的整数值。 |

```
QFont.Weight
```

Qt使用加权刻度从0到99类似，但不一样的，在Windows或CSS中使用的尺度。 0的重量为超轻，而99将是一个非常黑。

这个枚举包含预定义字体粗细：

| Constant | Value | Description |
| --- | --- | --- |
| `QFont.Light` | `25` | 25 |
| `QFont.Normal` | `50` | 50 |
| `QFont.DemiBold` | `63` | 63 |
| `QFont.Bold` | `75` | 75 |
| `QFont.Black` | `87` | 87 |

* * *

## Method Documentation

```
QFont.__init__ (self)
```

构造一个使用应用程序的默认字体的字体对象。

**See also** [QApplication.setFont](qapplication.html#setFont)（）和[QApplication.font](qapplication.html#font)（ ） 。

```
QFont.__init__ (self, QString family, int pointSize = -1, int weight = -1, bool italic = False)
```

构造一个字体对象与指定的_family_，_pointSize_，_weight_和_italic_设置。

If _pointSize_是零或负值，则字体的点大小被设定为一个系统有关的默认值。一般来说，这是12个点，除了在Symbian它是7分。

该_family_名称可以任选还包括一个铸造厂的名称，例如“黑体[ Cronyx ]” 。如果_family_可从一个以上的铸造和未指明的铸造，任意铸造被选择。如果家庭不具备的家庭将使用设置的[font matching](qfont.html)算法。

**See also** [Weight](qfont.html#Weight-enum)，[setFamily](qfont.html#setFamily)（ ）[setPointSize](qfont.html#setPointSize)（ ）[setWeight](qfont.html#setWeight)（ ）[setItalic](qfont.html#setItalic)（ ）[setStyleHint](qfont.html#setStyleHint)（）和[QApplication.font](qapplication.html#font)（ ） 。

```
QFont.__init__ (self, QFont, QPaintDevice pd)
```

构造一个从字体_font_供漆设备上使用_pd_。

```
QFont.__init__ (self, QFont)
```

构造一个字体是副本_font_。

```
QFont.__init__ (self, QVariant variant)
```

```
bool QFont.bold (self)
```

返回True如果[weight](qfont.html#weight)（）是一个大于[QFont.Normal](qfont.html#Weight-enum)否则返回False 。

**See also** [weight](qfont.html#weight)（ ）[setBold](qfont.html#setBold)（）和[QFontInfo.bold](qfontinfo.html#bold)（ ） 。

```
QFont.cacheStatistics ()
```

```
Capitalization QFont.capitalization (self)
```

[

返回该字体的当前市值类型。

此功能被引入Qt的4.4 。

](qfont.html#Capitalization-enum)

[**See also**](qfont.html#Capitalization-enum) [setCapitalization](qfont.html#setCapitalization)（ ） 。

```
QFont.cleanup ()
```

```
QString QFont.defaultFamily (self)
```

返回对应于当前样式提示的姓。

**See also** [StyleHint](qfont.html#StyleHint-enum)，[styleHint](qfont.html#styleHint)（）和[setStyleHint](qfont.html#setStyleHint)（ ） 。

```
bool QFont.exactMatch (self)
```

返回True如果一个窗口系统字体完全匹配该字体的设置是可用的。

**See also** [QFontInfo](qfontinfo.html)。

```
QString QFont.family (self)
```

返回请求的字体系列名称，即名称在构造或最后个setFont （ ）调用设置。

**See also** [setFamily](qfont.html#setFamily)（ ）[substitutes](qfont.html#substitutes)（）和[substitute](qfont.html#substitute)（ ） 。

```
bool QFont.fixedPitch (self)
```

返回True如果固定摊位已经被置位，否则返回False 。

**See also** [setFixedPitch](qfont.html#setFixedPitch)（）和[QFontInfo.fixedPitch](qfontinfo.html#fixedPitch)（ ） 。

```
bool QFont.fromString (self, QString)
```

设置该字体相匹配的说明_descrip_。该说明是用逗号分隔的字体属性列表，返回的[toString](qfont.html#toString)（ ） 。

**See also** [toString](qfont.html#toString)（ ） 。

```
int QFont.handle (self)
```

返回窗口的系统句柄的字体，对于低级别的访问。使用此功能是_not_便携。

```
HintingPreference QFont.hintingPreference (self)
```

[

返回字形与此字体渲染当前的优选暗示的水平。

此功能被引入Qt的4.8 。

](qfont.html#HintingPreference-enum)

[**See also**](qfont.html#HintingPreference-enum) [setHintingPreference](qfont.html#setHintingPreference)（ ） 。

```
QFont.initialize ()
```

```
QFont.insertSubstitution (QString, QString)
```

Inserts _substituteName_成家庭中的替换表_familyName_。

**See also** [insertSubstitutions](qfont.html#insertSubstitutions)（ ）[removeSubstitution](qfont.html#removeSubstitution)（ ）[substitutions](qfont.html#substitutions)（ ）[substitute](qfont.html#substitute)（）和[substitutes](qfont.html#substitutes)（ ） 。

```
QFont.insertSubstitutions (QString, QStringList)
```

插入家庭的名单_substituteNames_入替换列表_familyName_。

**See also** [insertSubstitution](qfont.html#insertSubstitution)（ ）[removeSubstitution](qfont.html#removeSubstitution)（ ）[substitutions](qfont.html#substitutions)（）和[substitute](qfont.html#substitute)（ ） 。

```
bool QFont.isCopyOf (self, QFont)
```

返回True如果这个字体和_f_是彼此的副本，即，其中的一个被创建为其它既不以来已经被修改的副本。这比平等更严格的。

**See also** [operator=](qfont.html#operator-eq)（）和[operator==](qfont.html#operator-eq-eq)（ ） 。

```
bool QFont.italic (self)
```

返回True如果[style](qfont.html#style)字体的（）不是[QFont.StyleNormal](qfont.html#Style-enum)

**See also** [setItalic](qfont.html#setItalic)（）和[style](qfont.html#style)（ ） 。

```
bool QFont.kerning (self)
```

返回True如果字距应绘制文本使用此字体时使用。

**See also** [setKerning](qfont.html#setKerning)（ ） 。

```
QString QFont.key (self)
```

返回字体的按键，字体的文字表述。它通常被用作密钥对字体的高速缓存或字典。

**See also** [QMap](index.htm)。

```
QString QFont.lastResortFamily (self)
```

返回“最后手段”字体系列名称。

当前的实现尝试多种常见的字体，返回的第一个发现。是有可能是没有家人在这种情况下，一个空字符串，则返回找到。

**See also** [lastResortFont](qfont.html#lastResortFont)（ ） 。

```
QString QFont.lastResortFont (self)
```

对于字体匹配算法返回一个“不得已而为之”的字体名称​​。这是使用，如果不得已家人不可用。它总是返回一个名称，如果需要返回类似于“固定”或“系统” 。

当前的实现尝试多种常见的字体，返回的第一个发现。实现可以在任何时候改变，但这个函数总是返回包含一些字符串。

这在理论上是可能的，是不是真的有一个lastResortFont （ ）在这种情况下， Qt会显示一条错误消息中止。我们一直无法识别的情况下发生这种情况。请[report it as a bug](index.htm)如果是的话，最好用你安装的字体列表。

**See also** [lastResortFamily](qfont.html#lastResortFamily)（）和[rawName](qfont.html#rawName)（ ） 。

```
float QFont.letterSpacing (self)
```

返回字母间距的字体。

此功能被引入Qt的4.4 。

**See also** [setLetterSpacing](qfont.html#setLetterSpacing)（ ）[letterSpacingType](qfont.html#letterSpacingType)（）和[setWordSpacing](qfont.html#setWordSpacing)（ ） 。

```
SpacingType QFont.letterSpacingType (self)
```

[

返回用于字母间距的间距类型。

此功能被引入Qt的4.4 。

](qfont.html#SpacingType-enum)

[**See also**](qfont.html#SpacingType-enum) [letterSpacing](qfont.html#letterSpacing)（ ）[setLetterSpacing](qfont.html#setLetterSpacing)（）和[setWordSpacing](qfont.html#setWordSpacing)（ ） 。

```
bool QFont.overline (self)
```

返回True如果划线已经被置位，否则返回False 。

**See also** [setOverline](qfont.html#setOverline)（ ） 。

```
int QFont.pixelSize (self)
```

返回该字体的像素大小，如果它被设置以[setPixelSize](qfont.html#setPixelSize)（ ） 。返回-1，如果将尺寸设定与[setPointSize](qfont.html#setPointSize)（）或[setPointSizeF](qfont.html#setPointSizeF)（ ） 。

**See also** [setPixelSize](qfont.html#setPixelSize)（ ）[pointSize](qfont.html#pointSize)（ ）[QFontInfo.pointSize](qfontinfo.html#pointSize)（）和[QFontInfo.pixelSize](qfontinfo.html#pixelSize)（ ） 。

```
int QFont.pointSize (self)
```

返回字体的点数大小。返回-1，如果字体大小被以像素为单位指定的。

**See also** [setPointSize](qfont.html#setPointSize)（）和[pointSizeF](qfont.html#pointSizeF)（ ） 。

```
float QFont.pointSizeF (self)
```

返回字体的点数大小。返回-1，如果字体大小被以像素为单位指定的。

**See also** [pointSize](qfont.html#pointSize)（ ）[setPointSizeF](qfont.html#setPointSizeF)（ ）[pixelSize](qfont.html#pixelSize)（ ）[QFontInfo.pointSize](qfontinfo.html#pointSize)（）和[QFontInfo.pixelSize](qfontinfo.html#pixelSize)（ ） 。

```
bool QFont.rawMode (self)
```

返回True如果原始模式用于字体名称匹配，否则返回False 。

**See also** [setRawMode](qfont.html#setRawMode)（）和[rawName](qfont.html#rawName)（ ） 。

```
QString QFont.rawName (self)
```

返回底层窗口系统中的字体的名称。

在X11上，这个函数会返回一个空字符串，如果Qt的是建立与fontconfig的支持，否则XLFD （ X逻辑字体描述）被返回。

使用这个函数的返回值通常是_not_ _portable_。

**See also** [setRawName](qfont.html#setRawName)（ ） 。

```
QFont.removeSubstitution (QString)
```

删除所有的换人_familyName_。

**See also** [insertSubstitutions](qfont.html#insertSubstitutions)（ ）[insertSubstitution](qfont.html#insertSubstitution)（ ）[substitutions](qfont.html#substitutions)（）和[substitute](qfont.html#substitute)（ ） 。

```
QFont QFont.resolve (self, QFont)
```

[](qfont.html)

[返回一个新的](qfont.html)[QFont](qfont.html)具有从属性复制_other_还没有对这种字体被预先设定。

```
QFont.setBold (self, bool enable)
```

If _enable_是真正的设置字体的重量[QFont.Bold](qfont.html#Weight-enum)否则设置的权重[QFont.Normal](qfont.html#Weight-enum)。

为了更好的气魄控制使用[setWeight](qfont.html#setWeight)（ ） 。

**See also** [bold](qfont.html#bold)（）和[setWeight](qfont.html#setWeight)（ ） 。

```
QFont.setCapitalization (self, Capitalization)
```

在设置该字体的文字，以资本化_caps_。

字体的大小写使文本显示在选定资本化模式。

此功能被引入Qt的4.4 。

**See also** [capitalization](qfont.html#capitalization)（ ） 。

```
QFont.setFamily (self, QString)
```

设置字体的系列名称。该名称是区分大小写的，并且可能包括代工的名称。

该_family_名称可以任选还包括一个铸造厂的名称，例如“黑体[ Cronyx ]” 。如果_family_可从一个以上的铸造和未指明的铸造，任意铸造被选择。如果家庭不具备的家庭将使用设置的[font matching](qfont.html)算法。

**See also** [family](qfont.html#family)（ ）[setStyleHint](qfont.html#setStyleHint)（）和[QFontInfo](qfontinfo.html)。

```
QFont.setFixedPitch (self, bool)
```

If _enable_诚然，在设置固定间距，否则套固定摊位了。

**See also** [fixedPitch](qfont.html#fixedPitch)（）和[QFontInfo](qfontinfo.html)。

```
QFont.setHintingPreference (self, HintingPreference hintingPreference)
```

偏爱字形的暗示级别设置为_hintingPreference_。这是一个暗示，底层的字体渲染系统使用暗示一定水平，并且跨平台具有不同的支持。请参阅下表说明文档中的[QFont.HintingPreference](qfont.html#HintingPreference-enum)更多的细节。

默认暗示偏好[QFont.PreferDefaultHinting](qfont.html#HintingPreference-enum)。

此功能被引入Qt的4.8 。

**See also** [hintingPreference](qfont.html#hintingPreference)（ ） 。

```
QFont.setItalic (self, bool b)
```

设置[style](qfont.html#style)的字体（）来[QFont.StyleItalic](qfont.html#Style-enum)如果_enable_是真的，否则样式设置为[QFont.StyleNormal](qfont.html#Style-enum)。

**See also** [italic](qfont.html#italic)（）和[QFontInfo](qfontinfo.html)。

```
QFont.setKerning (self, bool)
```

启用字距这个字体，如果_enable_为True，否则禁用它。默认情况下，启用字距调整。

如果启用字距调整，字形度量对不上号了，即使是拉丁文字。换句话说，该宽度（' a'）的宽度+ （' b'）中的假设是等于宽度（ “AB” ）是不neccesairly真。

**See also** [kerning](qfont.html#kerning)（）和[QFontMetrics](qfontmetrics.html)。

```
QFont.setLetterSpacing (self, SpacingType type, float spacing)
```

设置字母间距的字体_spacing_和间距的类型_type_。

字母间距改变了字体个别字母之间的默认间距。字母之间的间距可以做得更小以及更大。

此功能被引入Qt的4.4 。

**See also** [letterSpacing](qfont.html#letterSpacing)（ ）[letterSpacingType](qfont.html#letterSpacingType)（）和[setWordSpacing](qfont.html#setWordSpacing)（ ） 。

```
QFont.setOverline (self, bool)
```

If _enable_诚然，在设置上划线，否则套划线了。

**See also** [overline](qfont.html#overline)（）和[QFontInfo](qfontinfo.html)。

```
QFont.setPixelSize (self, int)
```

设置字体大小_pixelSize_像素。

使用此功能使字体与设备相关。使用[setPointSize](qfont.html#setPointSize)（）或[setPointSizeF](qfont.html#setPointSizeF)（）来设置的字体大小的设备中独立的方式。

**See also** [pixelSize](qfont.html#pixelSize)（ ） 。

```
QFont.setPointSize (self, int)
```

设置点的大小_pointSize_。点的大小必须大于零。

**See also** [pointSize](qfont.html#pointSize)（）和[setPointSizeF](qfont.html#setPointSizeF)（ ） 。

```
QFont.setPointSizeF (self, float)
```

设置点的大小_pointSize_。点的大小必须大于零。所要求的精度可能无法在所有平台上实现。

**See also** [pointSizeF](qfont.html#pointSizeF)（ ）[setPointSize](qfont.html#setPointSize)（）和[setPixelSize](qfont.html#setPixelSize)（ ） 。

```
QFont.setRawMode (self, bool)
```

If _enable_是真的，将原始的模式，否则将原始模式关闭。此功能只有在X11下的效果。

如果原始模式被激活， Qt会寻找一个X字体具有完整的字体名匹配的姓，忽略了设置的所有其他值[QFont](qfont.html)。如果字体名称匹配多种字体， Qt会使用由十传回的第一个字体[QFontInfo](qfontinfo.html) _cannot_用于获取有关信息[QFont](qfont.html)使用原始模式（它会返回在设置的值[QFont](qfont.html)对于所有参数，包括姓） 。

**Warning:**不要使用原始模式，除非你真的需要它！在大多数（如果不是全部）的情况下，[setRawName](qfont.html#setRawName)（ ）是一个更好的选择。

**See also** [rawMode](qfont.html#rawMode)（）和[setRawName](qfont.html#setRawName)（ ） 。

```
QFont.setRawName (self, QString)
```

其系统的具体名称设置字体。在X下该功能是非常有用的，其中系统字体设置（例如X资源）通常可在XLFD （ X逻辑字体描述）唯一形式。你可以传递一个XLFD为_name_此功能。

设置setRawName字体（ ）仍然是一个全功能的[QFont](qfont.html)。它可以查询（例如用[italic](qfont.html#italic)（））或修改（例如，利用[setItalic](qfont.html#setItalic)（） ），因此也适合用于呈现富文本。

如果Qt的内部字体数据库无法解析的原始名称，字体变成了原始的字体，_name_作为其家人。

需要注意的是，本实施中不XLFD的处理通配符很好，而且字体别名（文件`fonts.alias`在X11 ）字体目录不支持。

**See also** [rawName](qfont.html#rawName)（ ）[setRawMode](qfont.html#setRawMode)（）和[setFamily](qfont.html#setFamily)（ ） 。

```
QFont.setStretch (self, int)
```

设置为字体的拉伸因子。

伸展因子变化的字体中的所有字符的宽度_factor_个百分点。例如，设置_factor_150导致在字体被（即150 ％）的1.5倍更宽的所有字符。默认拉伸系数为100 。最小拉伸因子是1 ，最大伸长率是4000 。

上的伸长率是只适用于轮廓字体。拉伸系数被忽略的位图字体。

注意：[QFont](qfont.html)不能伸展XLFD字体。当装载在X11 XLFD字体，拉伸系数匹配一组预定义的值的XLFD的SETWIDTH_NAME领域。

**See also** [stretch](qfont.html#stretch)（）和[QFont.Stretch](qfont.html#Stretch-enum)。

```
QFont.setStrikeOut (self, bool)
```

If _enable_是真的，套三振上，否则套三振了。

**See also** [strikeOut](qfont.html#strikeOut)（）和[QFontInfo](qfontinfo.html)。

```
QFont.setStyle (self, Style style)
```

设置字体的样式_style_。

**See also** [style](qfont.html#style)（ ）[italic](qfont.html#italic)（）和[QFontInfo](qfontinfo.html)。

```
QFont.setStyleHint (self, StyleHint hint, StyleStrategy strategy = QFont.PreferDefault)
```

设置风格提示和策略，_hint_和_strategy_元。

如果这些都没有明确设定的样式提示将默认为`AnyStyle`和风格策略，`PreferDefault`。

Qt不支持样式提示在X11 ，因为没有提供窗口系统信息。

**See also** [StyleHint](qfont.html#StyleHint-enum)，[styleHint](qfont.html#styleHint)（ ）[StyleStrategy](qfont.html#StyleStrategy-enum)，[styleStrategy](qfont.html#styleStrategy)（）和[QFontInfo](qfontinfo.html)。

```
QFont.setStyleName (self, QString styleName)
```

设置字体的样式名称，以给定的_styleName_。就像当设置，其他样式属性[style](qfont.html#style)（）和[weight](qfont.html#weight)（ ）将被忽略字体匹配。

此功能被引入Qt的4.8 。

**See also** [styleName](qfont.html#styleName)（ ） 。

```
QFont.setStyleStrategy (self, StyleStrategy s)
```

设置样式战略字体_s_。

**See also** [styleStrategy](qfont.html#styleStrategy)（）和[QFont.StyleStrategy](qfont.html#StyleStrategy-enum)。

```
QFont.setUnderline (self, bool)
```

If _enable_是真的，套下划线上，否则设置下划线关闭。

**See also** [underline](qfont.html#underline)（）和[QFontInfo](qfontinfo.html)。

```
QFont.setWeight (self, int)
```

设置权重的字体_weight_，这应该是从一个值[QFont.Weight](qfont.html#Weight-enum)枚举。

**See also** [weight](qfont.html#weight)（）和[QFontInfo](qfontinfo.html)。

```
QFont.setWordSpacing (self, float spacing)
```

设置字间距的字体_spacing_。

字间距改变个别单词之间的默认间距。正值增加了字间距由像素的相应金额，而负值减小跨字相应的间距。

字间距将不适用于书写系统，其中indiviaul话是不是由空格分隔。

此功能被引入Qt的4.4 。

**See also** [wordSpacing](qfont.html#wordSpacing)（）和[setLetterSpacing](qfont.html#setLetterSpacing)（ ） 。

```
int QFont.stretch (self)
```

返回的字体拉伸因子。

**See also** [setStretch](qfont.html#setStretch)（ ） 。

```
bool QFont.strikeOut (self)
```

返回True如果三振出局已定，否则返回False 。

**See also** [setStrikeOut](qfont.html#setStrikeOut)（ ） 。

```
Style QFont.style (self)
```

[

返回字体的风格。

](qfont.html#Style-enum)

[**See also**](qfont.html#Style-enum) [setStyle](qfont.html#setStyle)（ ） 。

```
StyleHint QFont.styleHint (self)
```

[](qfont.html#StyleHint-enum)

[返回](qfont.html#StyleHint-enum)[StyleHint](qfont.html#StyleHint-enum)。

风格暗示的影响[font matching](qfont.html)算法。看[QFont.StyleHint](qfont.html#StyleHint-enum)对于可用的提示的列表。

**See also** [setStyleHint](qfont.html#setStyleHint)（ ）[QFont.StyleStrategy](qfont.html#StyleStrategy-enum)和[QFontInfo.styleHint](qfontinfo.html#styleHint)（ ） 。

```
QString QFont.styleName (self)
```

返回请求的字体样式名称，它将被用来配合不规则样式的字体（即不能在其他样式属性进行归一化） 。这取决于系统字体的支持，因此仅适用于Mac OS X和X11至今。在Windows中不规则的样式将被添加为单独的字体系列所以没有这种需要。

此功能被引入Qt的4.8 。

**See also** [setStyleName](qfont.html#setStyleName)（ ）[setFamily](qfont.html#setFamily)（）和[setStyle](qfont.html#setStyle)（ ） 。

```
StyleStrategy QFont.styleStrategy (self)
```

[](qfont.html#StyleStrategy-enum)

[返回](qfont.html#StyleStrategy-enum)[StyleStrategy](qfont.html#StyleStrategy-enum)。

风格策略的影响[font matching](qfont.html)算法。看[QFont.StyleStrategy](qfont.html#StyleStrategy-enum)可用策略的列表。

**See also** [setStyleStrategy](qfont.html#setStyleStrategy)（ ）[setStyleHint](qfont.html#setStyleHint)（）和[QFont.StyleHint](qfont.html#StyleHint-enum)。

```
QString QFont.substitute (QString)
```

返回第一个系列名称中使用时_familyName_是指定的。查找不区分大小写。

如果没有取代_familyName_，_familyName_返回。

取得替换使用列表[substitutes](qfont.html#substitutes)（ ） 。

**See also** [setFamily](qfont.html#setFamily)（ ）[insertSubstitutions](qfont.html#insertSubstitutions)（ ）[insertSubstitution](qfont.html#insertSubstitution)（）和[removeSubstitution](qfont.html#removeSubstitution)（ ） 。

```
QStringList QFont.substitutes (QString)
```

返回姓氏的情况下使用时的清单_familyName_是指定的。查找不区分大小写。

如果没有取代_familyName_，则返回空列表。

**See also** [substitute](qfont.html#substitute)（ ）[insertSubstitutions](qfont.html#insertSubstitutions)（ ）[insertSubstitution](qfont.html#insertSubstitution)（）和[removeSubstitution](qfont.html#removeSubstitution)（ ） 。

```
QStringList QFont.substitutions ()
```

返回取代姓氏排序的列表。

**See also** [insertSubstitution](qfont.html#insertSubstitution)（ ）[removeSubstitution](qfont.html#removeSubstitution)（）和[substitute](qfont.html#substitute)（ ） 。

```
QString QFont.toString (self)
```

返回该字体的描述。描述是一个以逗号分隔的属性，非常适合使用在列表[QSettings](qsettings.html)。

**See also** [fromString](qfont.html#fromString)（ ） 。

```
bool QFont.underline (self)
```

返回True如果底线已经被置位，否则返回False 。

**See also** [setUnderline](qfont.html#setUnderline)（ ） 。

```
int QFont.weight (self)
```

从返回的是枚举值中的一个字体的重量[QFont.Weight](qfont.html#Weight-enum)。

**See also** [setWeight](qfont.html#setWeight)（ ）[Weight](qfont.html#Weight-enum)和[QFontInfo](qfontinfo.html)。

```
float QFont.wordSpacing (self)
```

返回字间距字体。

此功能被引入Qt的4.4 。

**See also** [setWordSpacing](qfont.html#setWordSpacing)（）和[setLetterSpacing](qfont.html#setLetterSpacing)（ ） 。

```
bool QFont.__eq__ (self, QFont)
```

```
bool QFont.__ge__ (self, QFont)
```

```
bool QFont.__lt__ (self, QFont)
```

```
bool QFont.__ne__ (self, QFont)
```