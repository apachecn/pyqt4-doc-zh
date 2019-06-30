# QTextCharFormat Class Reference

## [[QtGui](index.htm) module]

该QTextCharFormat类提供格式设置信息的字符[QTextDocument](qtextdocument.html)。[More...](#details)

继承[QTextFormat](qtextformat.html)。

通过继承[QTextImageFormat](qtextimageformat.html)和[QTextTableCellFormat](qtexttablecellformat.html)。

### Types

*   `enum UnderlineStyle { NoUnderline, SingleUnderline, DashUnderline, DotLine, ..., SpellCheckUnderline }`
*   `enum VerticalAlignment { AlignNormal, AlignSuperScript, AlignSubScript, AlignMiddle, ..., AlignBaseline }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QTextCharFormat)`
*   `QString anchorHref (self)`
*   `QString anchorName (self)`
*   `QStringList anchorNames (self)`
*   `QFont font (self)`
*   `QFont.Capitalization fontCapitalization (self)`
*   `QString fontFamily (self)`
*   `bool fontFixedPitch (self)`
*   `QFont.HintingPreference fontHintingPreference (self)`
*   `bool fontItalic (self)`
*   `bool fontKerning (self)`
*   `float fontLetterSpacing (self)`
*   `bool fontOverline (self)`
*   `float fontPointSize (self)`
*   `bool fontStrikeOut (self)`
*   `QFont.StyleHint fontStyleHint (self)`
*   `QFont.StyleStrategy fontStyleStrategy (self)`
*   `bool fontUnderline (self)`
*   `int fontWeight (self)`
*   `float fontWordSpacing (self)`
*   `bool isAnchor (self)`
*   `bool isValid (self)`
*   `setAnchor (self, bool anchor)`
*   `setAnchorHref (self, QString value)`
*   `setAnchorName (self, QString name)`
*   `setAnchorNames (self, QStringList names)`
*   `setFont (self, QFont font)`
*   `setFontCapitalization (self, QFont.Capitalization capitalization)`
*   `setFontFamily (self, QString family)`
*   `setFontFixedPitch (self, bool fixedPitch)`
*   `setFontHintingPreference (self, QFont.HintingPreference hintingPreference)`
*   `setFontItalic (self, bool italic)`
*   `setFontKerning (self, bool enable)`
*   `setFontLetterSpacing (self, float spacing)`
*   `setFontOverline (self, bool overline)`
*   `setFontPointSize (self, float size)`
*   `setFontStrikeOut (self, bool strikeOut)`
*   `setFontStyleHint (self, QFont.StyleHint hint, QFont.StyleStrategy strategy = QFont.PreferDefault)`
*   `setFontStyleStrategy (self, QFont.StyleStrategy strategy)`
*   `setFontUnderline (self, bool underline)`
*   `setFontWeight (self, int weight)`
*   `setFontWordSpacing (self, float spacing)`
*   `setTableCellColumnSpan (self, int atableCellColumnSpan)`
*   `setTableCellRowSpan (self, int atableCellRowSpan)`
*   `setTextOutline (self, QPen pen)`
*   `setToolTip (self, QString tip)`
*   `setUnderlineColor (self, QColor color)`
*   `setUnderlineStyle (self, UnderlineStyle style)`
*   `setVerticalAlignment (self, VerticalAlignment alignment)`
*   `int tableCellColumnSpan (self)`
*   `int tableCellRowSpan (self)`
*   `QPen textOutline (self)`
*   `QString toolTip (self)`
*   `QColor underlineColor (self)`
*   `UnderlineStyle underlineStyle (self)`
*   `VerticalAlignment verticalAlignment (self)`

* * *

## Detailed Description

该QTextCharFormat类提供格式设置信息的字符[QTextDocument](qtextdocument.html)。

在文档中的文本的字符格式指定的文本的可视特性，以及关于其在一个超文本文件的作用的信息。

使用的字体可以通过提供一种字体的设置[setFont](qtextcharformat.html#setFont)（）函数，并且其外观的各个方面可以调整，以得到所需的效果。[setFontFamily](qtextcharformat.html#setFontFamily)（）和[setFontPointSize](qtextcharformat.html#setFontPointSize)（ ）定义字体的家庭（如时间）和印刷尺寸;[setFontWeight](qtextcharformat.html#setFontWeight)（）和[setFontItalic](qtextcharformat.html#setFontItalic)（ ）提供了对字体的样式控制。[setFontUnderline](qtextcharformat.html#setFontUnderline)（ ）[setFontOverline](qtextcharformat.html#setFontOverline)（ ）[setFontStrikeOut](qtextcharformat.html#setFontStrikeOut)（）和[setFontFixedPitch](qtextcharformat.html#setFontFixedPitch)（ ）为文本附加效果。

颜色设置与[setForeground](qtextformat.html#setForeground)（ ） 。如果文本旨在用作锚（超链接） ，这可以被启用[setAnchor](qtextcharformat.html#setAnchor)（ ） 。该[setAnchorHref](qtextcharformat.html#setAnchorHref)（）和[setAnchorNames](qtextcharformat.html#setAnchorNames)（）函数用于指定关于超链接的目标与锚的名称的信息。

* * *

## Type Documentation

```
QTextCharFormat.UnderlineStyle
```

这个枚举变量描述了不同的方式绘制下划线的文本。

| Constant | Value | Description |
| --- | --- | --- |
| `QTextCharFormat.NoUnderline` | `0` | 文字是画，没有任何强调装饰。 |
| `QTextCharFormat.SingleUnderline` | `1` | A线是用画[Qt.SolidLine](qt.html#PenStyle-enum)。 |
| `QTextCharFormat.DashUnderline` | `2` | 破折号使用绘制[Qt.DashLine](qt.html#PenStyle-enum)。 |
| `QTextCharFormat.DotLine` | `3` | 点是使用绘制[Qt.DotLine](qt.html#PenStyle-enum); |
| `QTextCharFormat.DashDotLine` | `4` | Dashs和点使用绘制[Qt.DashDotLine](qt.html#PenStyle-enum)。 |
| `QTextCharFormat.DashDotDotLine` | `5` | 强调用画绘制[Qt.DashDotDotLine](qt.html#PenStyle-enum)。 |
| `QTextCharFormat.WaveUnderline` | `6` | 该文本是用波浪形下划线标出。 |
| `QTextCharFormat.SpellCheckUnderline` | `7` | 视乎该QStyle.SH_SpellCeckUnderlineStyle风格提示下划线绘制[QApplication](qapplication.html)风格。默认情况下，这个被映射到WaveUnderline ，在Mac OS X被映射到DashDotLine 。 |

**See also** [Qt.PenStyle](qt.html#PenStyle-enum)。

```
QTextCharFormat.VerticalAlignment
```

该枚举描述的方式使相邻的字符可以垂直对齐。

| Constant | Value | Description |
| --- | --- | --- |
| `QTextCharFormat.AlignNormal` | `0` | 相邻字符被放置在标准方式中的写入系统中使用的文本。 |
| `QTextCharFormat.AlignSuperScript` | `1` | 字符放在高于正常文本基线。 |
| `QTextCharFormat.AlignSubScript` | `2` | 字符都放在下面的普通文本基线。 |
| `QTextCharFormat.AlignMiddle` | `3` | 对象的中心垂直基准线对齐。目前，这只是实施了内联对象。 |
| `QTextCharFormat.AlignBottom` | `5` | 物体的底部边缘垂直基准线对齐。 |
| `QTextCharFormat.AlignTop` | `4` | 对象的上边缘垂直的基准线对齐。 |
| `QTextCharFormat.AlignBaseline` | `6` | 字符的基线对齐。 |

* * *

## Method Documentation

```
QTextCharFormat.__init__ (self)
```

构造一个新的字符格式的对象。

```
QTextCharFormat.__init__ (self, QTextCharFormat)
```

```
QString QTextCharFormat.anchorHref (self)
```

返回如果没有设置文本格式的超文本链接，或空字符串。

**See also** [setAnchorHref](qtextcharformat.html#setAnchorHref)（ ） 。

```
QString QTextCharFormat.anchorName (self)
```

```
QStringList QTextCharFormat.anchorNames (self)
```

返回与此文本格式，或者一个空字符串列表相关联，如果没有设置锚的名称。如果锚的名称被设置，文本这种格式可以是一个超文本链接的目标。

此功能被引入Qt的4.3 。

**See also** [setAnchorNames](qtextcharformat.html#setAnchorNames)（ ） 。

```
QFont QTextCharFormat.font (self)
```

[

返回的字体为这个字符格式。

](qfont.html)

[**See also**](qfont.html) [setFont](qtextcharformat.html#setFont)（ ） 。

```
QFont.Capitalization QTextCharFormat.fontCapitalization (self)
```

[

返回该字体的当前市值类型。

此功能被引入Qt的4.4 。

](qfont.html#Capitalization-enum)

[**See also**](qfont.html#Capitalization-enum) [setFontCapitalization](qtextcharformat.html#setFontCapitalization)（ ） 。

```
QString QTextCharFormat.fontFamily (self)
```

返回文本格式的字体系列。

**See also** [setFontFamily](qtextcharformat.html#setFontFamily)（）和[font](qtextcharformat.html#font)（ ） 。

```
bool QTextCharFormat.fontFixedPitch (self)
```

返回True如果文本格式的字体是固定的间距，否则返回False 。

**See also** [setFontFixedPitch](qtextcharformat.html#setFontFixedPitch)（）和[font](qtextcharformat.html#font)（ ） 。

```
QFont.HintingPreference QTextCharFormat.fontHintingPreference (self)
```

[

返回此文本格式的暗示偏好设定。

此功能被引入Qt的4.8 。

](qfont.html#HintingPreference-enum)

[**See also**](qfont.html#HintingPreference-enum) [setFontHintingPreference](qtextcharformat.html#setFontHintingPreference)（ ）[font](qtextcharformat.html#font)（）和[QFont.hintingPreference](qfont.html#hintingPreference)（ ） 。

```
bool QTextCharFormat.fontItalic (self)
```

返回True如果文本格式的字体是斜体，否则返回False 。

**See also** [setFontItalic](qtextcharformat.html#setFontItalic)（）和[font](qtextcharformat.html#font)（ ） 。

```
bool QTextCharFormat.fontKerning (self)
```

如果字体启用字距调整，则返回True 。

此功能被引入Qt的4.5 。

**See also** [setFontKerning](qtextcharformat.html#setFontKerning)（）和[font](qtextcharformat.html#font)（ ） 。

```
float QTextCharFormat.fontLetterSpacing (self)
```

返回当前字母间距百分比。

此功能被引入Qt的4.4 。

**See also** [setFontLetterSpacing](qtextcharformat.html#setFontLetterSpacing)（ ） 。

```
bool QTextCharFormat.fontOverline (self)
```

返回True如果文本格式的字体是上划线，否则返回False 。

**See also** [setFontOverline](qtextcharformat.html#setFontOverline)（）和[font](qtextcharformat.html#font)（ ） 。

```
float QTextCharFormat.fontPointSize (self)
```

返回用于这种格式显示文本的字体大小。

**See also** [setFontPointSize](qtextcharformat.html#setFontPointSize)（）和[font](qtextcharformat.html#font)（ ） 。

```
bool QTextCharFormat.fontStrikeOut (self)
```

返回True如果文本格式的字体被剔除（有一个水平线通过它绘制的），否则返回False 。

**See also** [setFontStrikeOut](qtextcharformat.html#setFontStrikeOut)（）和[font](qtextcharformat.html#font)（ ） 。

```
QFont.StyleHint QTextCharFormat.fontStyleHint (self)
```

[

返回的字体样式提示。

此功能被引入Qt的4.5 。

](qfont.html#StyleHint-enum)

[**See also**](qfont.html#StyleHint-enum) [setFontStyleHint](qtextcharformat.html#setFontStyleHint)（）和[font](qtextcharformat.html#font)（ ） 。

```
QFont.StyleStrategy QTextCharFormat.fontStyleStrategy (self)
```

[

返回当前字体样式的策略。

此功能被引入Qt的4.5 。

](qfont.html#StyleStrategy-enum)

[**See also**](qfont.html#StyleStrategy-enum) [setFontStyleStrategy](qtextcharformat.html#setFontStyleStrategy)（）和[font](qtextcharformat.html#font)（ ） 。

```
bool QTextCharFormat.fontUnderline (self)
```

返回True如果文本格式的字体下划线，否则返回False 。

**See also** [setFontUnderline](qtextcharformat.html#setFontUnderline)（）和[font](qtextcharformat.html#font)（ ） 。

```
int QTextCharFormat.fontWeight (self)
```

返回文本格式的字体粗细。

**See also** [setFontWeight](qtextcharformat.html#setFontWeight)（ ）[font](qtextcharformat.html#font)（）和[QFont.Weight](qfont.html#Weight-enum)。

```
float QTextCharFormat.fontWordSpacing (self)
```

返回当前的字间距值。

此功能被引入Qt的4.4 。

**See also** [setFontWordSpacing](qtextcharformat.html#setFontWordSpacing)（ ） 。

```
bool QTextCharFormat.isAnchor (self)
```

返回True如果文本被格式化为一个锚，否则返回False 。

**See also** [setAnchor](qtextcharformat.html#setAnchor)（ ）[setAnchorHref](qtextcharformat.html#setAnchorHref)（）和[setAnchorNames](qtextcharformat.html#setAnchorNames)（ ） 。

```
bool QTextCharFormat.isValid (self)
```

返回True如果这个字符格式是有效的，否则返回False 。

```
QTextCharFormat.setAnchor (self, bool anchor)
```

If _anchor_是真的，文字这种格式表示锚，并格式化适当的方式，否则文本通常格式化。 （锚是这往往显示下划线，并以不同的颜色从纯文本的超链接。 ）

文本呈现的方式是独立的格式是否有定义的有效支撑点。使用[setAnchorHref](qtextcharformat.html#setAnchorHref)（） ，以及任选[setAnchorNames](qtextcharformat.html#setAnchorNames)（）来创建一个超文本链接。

**See also** [isAnchor](qtextcharformat.html#isAnchor)（ ） 。

```
QTextCharFormat.setAnchorHref (self, QString value)
```

设置超文本链接的文本格式，以给定的_value_。这通常是像“ http://example.com/index.html ”的URL。

锚将与被显示_value_作为其显示文本，如果你想显示不同的文本调用[setAnchorNames](qtextcharformat.html#setAnchorNames)（ ） 。

格式化文本作为超链接的使用[setAnchor](qtextcharformat.html#setAnchor)（ ） 。

**See also** [anchorHref](qtextcharformat.html#anchorHref)（ ） 。

```
QTextCharFormat.setAnchorName (self, QString name)
```

```
QTextCharFormat.setAnchorNames (self, QStringList names)
```

设置文本格式的锚_names_。对于锚的工作作为一个超链接时，目标必须与设置[setAnchorHref](qtextcharformat.html#setAnchorHref)（）和所述锚定必须被启用[setAnchor](qtextcharformat.html#setAnchor)（ ） 。

此功能被引入Qt的4.3 。

**See also** [anchorNames](qtextcharformat.html#anchorNames)（ ） 。

```
QTextCharFormat.setFont (self, QFont font)
```

设置文本格式的_font_。

**See also** [font](qtextcharformat.html#font)（ ） 。

```
QTextCharFormat.setFontCapitalization (self, QFont.Capitalization capitalization)
```

设置apppears在这种字体的文本的大小写_capitalization_。

字体的大小写使文本显示在选定资本化模式。

此功能被引入Qt的4.4 。

**See also** [fontCapitalization](qtextcharformat.html#fontCapitalization)（ ） 。

```
QTextCharFormat.setFontFamily (self, QString family)
```

设置文本格式的字体_family_。

**See also** [fontFamily](qtextcharformat.html#fontFamily)（）和[setFont](qtextcharformat.html#setFont)（ ） 。

```
QTextCharFormat.setFontFixedPitch (self, bool fixedPitch)
```

If _fixedPitch_诚然，设置文本格式的字体是固定的间距，否则非固定间距字体。

**See also** [fontFixedPitch](qtextcharformat.html#fontFixedPitch)（）和[setFont](qtextcharformat.html#setFont)（ ） 。

```
QTextCharFormat.setFontHintingPreference (self, QFont.HintingPreference hintingPreference)
```

设置文本格式的字体是的暗示偏好_hintingPreference_。

此功能被引入Qt的4.8 。

**See also** [fontHintingPreference](qtextcharformat.html#fontHintingPreference)（ ）[setFont](qtextcharformat.html#setFont)（）和[QFont.setHintingPreference](qfont.html#setHintingPreference)（ ） 。

```
QTextCharFormat.setFontItalic (self, bool italic)
```

If _italic_诚然，设置文本格式的字体是斜体，否则字体将非斜体。

**See also** [fontItalic](qtextcharformat.html#fontItalic)（）和[setFont](qtextcharformat.html#setFont)（ ） 。

```
QTextCharFormat.setFontKerning (self, bool enable)
```

启用字距这个字体，如果_enable_为True，否则禁用它。

如果启用字距调整，字形度量对不上号了，即使是拉丁文字。换句话说，该宽度（' a'）的宽度+ （' b'）中的假设是等于宽度（ “AB” ）是不neccesairly真。

此功能被引入Qt的4.5 。

**See also** [fontKerning](qtextcharformat.html#fontKerning)（）和[setFont](qtextcharformat.html#setFont)（ ） 。

```
QTextCharFormat.setFontLetterSpacing (self, float spacing)
```

设置此格式的字母间距为给定的_spacing_，以百分比表示。值为100表示默认间距; 200的值加倍的一封信需要的空间量。

此功能被引入Qt的4.4 。

**See also** [fontLetterSpacing](qtextcharformat.html#fontLetterSpacing)（ ） 。

```
QTextCharFormat.setFontOverline (self, bool overline)
```

If _overline_诚然，设置文本格式的字体要上划线，否则显示的字体不上划线。

**See also** [fontOverline](qtextcharformat.html#fontOverline)（）和[setFont](qtextcharformat.html#setFont)（ ） 。

```
QTextCharFormat.setFontPointSize (self, float size)
```

设置文本格式的字体_size_。

**See also** [fontPointSize](qtextcharformat.html#fontPointSize)（）和[setFont](qtextcharformat.html#setFont)（ ） 。

```
QTextCharFormat.setFontStrikeOut (self, bool strikeOut)
```

If _strikeOut_诚然，设置文本格式的字体与剔除启用（有横线穿过它） ，否则将显示不带删除线。

**See also** [fontStrikeOut](qtextcharformat.html#fontStrikeOut)（）和[setFont](qtextcharformat.html#setFont)（ ） 。

```
QTextCharFormat.setFontStyleHint (self, QFont.StyleHint hint, QFont.StyleStrategy strategy = QFont.PreferDefault)
```

设置字体样式_hint_和_strategy_。

Qt不支持样式提示在X11 ，因为没有提供窗口系统信息。

此功能被引入Qt的4.5 。

**See also** [fontStyleHint](qtextcharformat.html#fontStyleHint)（ ）[setFont](qtextcharformat.html#setFont)（）和[QFont.setStyleHint](qfont.html#setStyleHint)（ ） 。

```
QTextCharFormat.setFontStyleStrategy (self, QFont.StyleStrategy strategy)
```

设置字体样式_strategy_。

此功能被引入Qt的4.5 。

**See also** [fontStyleStrategy](qtextcharformat.html#fontStyleStrategy)（ ）[setFont](qtextcharformat.html#setFont)（）和[QFont.setStyleStrategy](qfont.html#setStyleStrategy)（ ） 。

```
QTextCharFormat.setFontUnderline (self, bool underline)
```

If _underline_诚然，设置文本格式的字体加下划线，否则将显示非下划线。

**See also** [fontUnderline](qtextcharformat.html#fontUnderline)（）和[setFont](qtextcharformat.html#setFont)（ ） 。

```
QTextCharFormat.setFontWeight (self, int weight)
```

设置文本格式的字体重量_weight_。

**See also** [fontWeight](qtextcharformat.html#fontWeight)（ ）[setFont](qtextcharformat.html#setFont)（）和[QFont.Weight](qfont.html#Weight-enum)。

```
QTextCharFormat.setFontWordSpacing (self, float spacing)
```

设置此格式的字间距为给定的_spacing_，以像素为单位。

此功能被引入Qt的4.4 。

**See also** [fontWordSpacing](qtextcharformat.html#fontWordSpacing)（ ） 。

```
QTextCharFormat.setTableCellColumnSpan (self, int atableCellColumnSpan)
```

```
QTextCharFormat.setTableCellRowSpan (self, int atableCellRowSpan)
```

```
QTextCharFormat.setTextOutline (self, QPen pen)
```

设置用于绘制人物的轮廓给定的笔_pen_。

**See also** [textOutline](qtextcharformat.html#textOutline)（ ） 。

```
QTextCharFormat.setToolTip (self, QString tip)
```

工具提示文本的片段设置为给定_text_。

此功能被引入Qt的4.3 。

**See also** [toolTip](qtextcharformat.html#toolTip)（ ） 。

```
QTextCharFormat.setUnderlineColor (self, QColor color)
```

设置用于与此格式的字符的下划线颜色_color_规定。

**See also** [underlineColor](qtextcharformat.html#underlineColor)（ ） 。

```
QTextCharFormat.setUnderlineStyle (self, UnderlineStyle style)
```

设置下划线的文本的样式_style_。

这个函数中引入了Qt 4.2中。

**See also** [underlineStyle](qtextcharformat.html#underlineStyle)（ ） 。

```
QTextCharFormat.setVerticalAlignment (self, VerticalAlignment alignment)
```

设置用于与此格式的字符的垂直对齐方式_alignment_规定。

**See also** [verticalAlignment](qtextcharformat.html#verticalAlignment)（ ） 。

```
int QTextCharFormat.tableCellColumnSpan (self)
```

```
int QTextCharFormat.tableCellRowSpan (self)
```

```
QPen QTextCharFormat.textOutline (self)
```

[

返回用于绘制人物的轮廓在这种格式的笔。

](qpen.html)

[**See also**](qpen.html) [setTextOutline](qtextcharformat.html#setTextOutline)（ ） 。

```
QString QTextCharFormat.toolTip (self)
```

返回显示的文本片段的工具提示。

此功能被引入Qt的4.3 。

**See also** [setToolTip](qtextcharformat.html#setToolTip)（ ） 。

```
QColor QTextCharFormat.underlineColor (self)
```

[

返回用于强调这种格式的字符的颜色。

](qcolor.html)

[**See also**](qcolor.html) [setUnderlineColor](qtextcharformat.html#setUnderlineColor)（ ） 。

```
UnderlineStyle QTextCharFormat.underlineStyle (self)
```

[

返回强调文本的样式。

这个函数中引入了Qt 4.2中。

](qtextcharformat.html#UnderlineStyle-enum)

[**See also**](qtextcharformat.html#UnderlineStyle-enum) [setUnderlineStyle](qtextcharformat.html#setUnderlineStyle)（ ） 。

```
VerticalAlignment QTextCharFormat.verticalAlignment (self)
```

[

返回用于与此格式字符的垂直对齐方式。

](qtextcharformat.html#VerticalAlignment-enum)

[**See also**](qtextcharformat.html#VerticalAlignment-enum) [setVerticalAlignment](qtextcharformat.html#setVerticalAlignment)（ ） 。