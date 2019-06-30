# QFontMetrics Class Reference

## [[QtGui](index.htm) module]

该QFontMetrics类提供的字体度量信息。[More...](#details)

### Methods

*   `__init__ (self, QFont)`
*   `__init__ (self, QFont, QPaintDevice pd)`
*   `__init__ (self, QFontMetrics)`
*   `int ascent (self)`
*   `int averageCharWidth (self)`
*   `QRect boundingRect (self, QChar)`
*   `QRect boundingRect (self, QString text)`
*   `QRect boundingRect (self, QRect rect, int flags, QString text, int tabStops = 0, list-of-int tabArray = 0)`
*   `QRect boundingRect (self, int x, int y, int width, int height, int flags, QString text, int tabStops = 0, list-of-int tabArray = 0)`
*   `QRect boundingRectChar (self, QChar)`
*   `int charWidth (self, QString str, int pos)`
*   `int descent (self)`
*   `QString elidedText (self, QString text, Qt.TextElideMode mode, int width, int flags = 0)`
*   `int height (self)`
*   `bool inFont (self, QChar)`
*   `bool inFontUcs4 (self, int character)`
*   `int leading (self)`
*   `int leftBearing (self, QChar)`
*   `int lineSpacing (self)`
*   `int lineWidth (self)`
*   `int maxWidth (self)`
*   `int minLeftBearing (self)`
*   `int minRightBearing (self)`
*   `int overlinePos (self)`
*   `int rightBearing (self, QChar)`
*   `QSize size (self, int flags, QString text, int tabStops = 0, list-of-int tabArray = 0)`
*   `int strikeOutPos (self)`
*   `QRect tightBoundingRect (self, QString text)`
*   `int underlinePos (self)`
*   `int width (self, QChar)`
*   `int width (self, QString text, int length = -1)`
*   `int widthChar (self, QChar)`
*   `int xHeight (self)`

### Special Methods

*   `bool __eq__ (self, QFontMetrics other)`
*   `bool __ne__ (self, QFontMetrics other)`

* * *

## Detailed Description

该QFontMetrics类提供的字体度量信息。

QFontMetrics函数计算字符和字符串给定字体的大小。有三种方法可以创建一个QFontMetrics对象：

1.  调用QFontMetrics构造带[QFont](qfont.html)创建一个字体规格对象的屏幕兼容的字体，即字体不能为打印机字体。如果字体是后来改，字体规格对象_not_更新。

    （注：如果您使用的打印机字体返回的值可能是不准确的打印机字体并不总是那么访问最近的屏幕字体时使用打印机字体提供。 ）

2.  [QWidget.fontMetrics](qwidget.html#fontMetrics)（ ）返回的字体度量一个小部件的字体。这相当于QFontMetrics （插件 - \u003e字体（））。如果控件的字体是后来改，字体规格对象_not_更新。
3.  [QPainter.fontMetrics](qpainter.html#fontMetrics)（ ）返回的字体规格为一个画家的当前字体。如果画家的字体后来改变，字体规格对象_not_更新。

一旦创建，该对象提供了访问字体，它的字符，并在字体渲染字符串的各个指标。

有迹象表明，在字体上运行几个功能：[ascent](qfontmetrics.html#ascent)（ ）[descent](qfontmetrics.html#descent)（ ）[height](qfontmetrics.html#height)（ ）[leading](qfontmetrics.html#leading)（）和[lineSpacing](qfontmetrics.html#lineSpacing)（ ）返回字体的基本大小属性。该[underlinePos](qfontmetrics.html#underlinePos)（ ）[overlinePos](qfontmetrics.html#overlinePos)（ ）[strikeOutPos](qfontmetrics.html#strikeOutPos)（）和[lineWidth](qfontmetrics.html#lineWidth)（ ）函数，返回强调， overlines或撞击出的字符的行的属性。这些功能都是快。

也有一些对集合中的字体字形的操作一些功能：[minLeftBearing](qfontmetrics.html#minLeftBearing)（ ）[minRightBearing](qfontmetrics.html#minRightBearing)（）和[maxWidth](qfontmetrics.html#maxWidth)（ ） 。这些都是必然缓慢，我们建议避免他们，如果可能的。

对于每一个字符，就可以得到其[width](qfontmetrics.html#width)（ ）[leftBearing](qfontmetrics.html#leftBearing)（）和[rightBearing](qfontmetrics.html#rightBearing)（ ），并找出是否是在使用字体[inFont](qfontmetrics.html#inFont)（ ） 。您也可以把字符作为字符串，并使用字符串函数就可以了。

字符串函数包括：[width](qfontmetrics.html#width)（） ，返回字符串的宽度以像素为单位（或点，用于打印机）[boundingRect](qfontmetrics.html#boundingRect)（ ）返回一个矩形足够大，以包含所呈现的串，并[size](qfontmetrics.html#size)（） ，以返回该矩形的大小。

例如：

```
 [QFont](qfont.html) font("times", 24);
 QFontMetrics fm(font);
 int pixelsWide = fm.width("What's the width of this text?");
 int pixelsHigh = fm.height();

```

* * *

## Method Documentation

```
QFontMetrics.__init__ (self, QFont)
```

构造一个字体规格对象为_font_。

字体规格将与用于创建paintdevice兼容_font_。

字体规格对象持有，在它被创建的时候被传递在构造函数中的字体的信息，并且不更新，如果字体的属性后来改。

使用[QFontMetrics](qfontmetrics.html)（常量[QFont](qfont.html)＆ ，[QPaintDevice](qpaintdevice.html)*）来获取字体度量标准，具有一定的绘图设备兼容。

```
QFontMetrics.__init__ (self, QFont, QPaintDevice pd)
```

构造一个字体规格对象为_font_和_paintdevice_。

字体规格将与通过paintdevice兼容。如果_paintdevice_为0时，度量将屏幕兼容的，即得。你得到，如果你使用的字体在绘制文本的指标[widgets](qwidget.html) or [pixmaps](qpixmap.html)，而不是在[QPicture](qpicture.html) or [QPrinter](qprinter.html)。

字体规格对象持有，在它被创建的时候被传递在构造函数中的字体的信息，并且不更新，如果字体的属性后来改。

```
QFontMetrics.__init__ (self, QFontMetrics)
```

构造的副本_fm_。

```
int QFontMetrics.ascent (self)
```

返回字体的上升。

字体的上升是从基线到最高位置的字符延伸到距离。在实践中，有些字体设计师打破了这个规则，如当他们把一个以上的口音就一个字之上，或者以适应异国的语言不同寻常的性格，所以它是可能的（虽然很少） ，这个值将是太小了。

**See also** [descent](qfontmetrics.html#descent)（ ） 。

```
int QFontMetrics.averageCharWidth (self)
```

返回字形在字体的平均宽度。

这个函数中引入了Qt 4.2中。

```
QRect QFontMetrics.boundingRect (self, QChar)
```

[

返回复盖油墨的矩形，如果字符_ch_分别在坐标系的原点被绘制。

请注意，边框可能会延伸到（ 0 ， 0 ） （例如，斜体字体）的左侧，该文本输出可能复盖_all_像素的边界矩形。对于一个空格字符的矩形通常是空的。

请注意，矩形通常既基线的上方和下方延伸。

](qrect.html)

[**Warning:**返回的矩形的宽度不是字符的超前宽度。使用boundingRect （常量](qrect.html)[QString](qstring.html)＆）或[width](qfontmetrics.html#width)（ ）来代替。

**See also** [width](qfontmetrics.html#width)（ ） 。

```
QRect QFontMetrics.boundingRect (self, QString text)
```

[

返回字符的边框由指定的字符串中_text_。边界矩形总是至少复盖的像素集合的文本将涵盖如果画在（ 0 ， 0 ） 。

](qrect.html)

[注意，边框可以延伸到的（0，0 ），例如左斜体字体，返回的矩形的宽度可能比什么不同](qrect.html)[width](qfontmetrics.html#width)（ ）方法返回。

如果你想知道字符串的超前宽度（布局彼此相邻一组字符串） ，使用[width](qfontmetrics.html#width)（ ）来代替。

换行符的处理方法与普通字符，_not_作为换行符。

的边界矩形的高度至少一样大，返回的值[height](qfontmetrics.html#height)（ ） 。

**See also** [width](qfontmetrics.html#width)（ ）[height](qfontmetrics.html#height)（ ）[QPainter.boundingRect](qpainter.html#boundingRect)（）和[tightBoundingRect](qfontmetrics.html#tightBoundingRect)（ ） 。

```
QRect QFontMetrics.boundingRect (self, QRect rect, int flags, QString text, int tabStops = 0, list-of-int tabArray = 0)
```

[

该_tabArray_参数也可能没有。

](qrect.html)

```
QRect QFontMetrics.boundingRect (self, int x, int y, int width, int height, int flags, QString text, int tabStops = 0, list-of-int tabArray = 0)
```

[

该_tabArray_参数也可能没有。

](qrect.html)

```
QRect QFontMetrics.boundingRectChar (self, QChar)
```

[

```
int QFontMetrics.charWidth (self, QString str, int pos)
```

```
int QFontMetrics.descent (self)
```

返回字体的血统。

的下降是从基准线到最低点的字符延伸到距离。在实践中，有些字体设计师打破了这个规则，如以容纳在一个异乎寻常的语言不寻常的字符，所以它是可能的（虽然很少） ，该值将是太小。

](qrect.html)

[**See also**](qrect.html) [ascent](qfontmetrics.html#ascent)（ ） 。

```
QString QFontMetrics.elidedText (self, QString text, Qt.TextElideMode mode, int width, int flags = 0)
```

如果字符串_text_比更宽_width_，返回字符串的省略版本（即，在用“ ...... ”一个字符串） 。否则，返回原始字符串。

该_mode_参数指定的文本是省略左侧（如“ ......技术” ） ，中间（例如，“风帆... CH” ） ，或在右边（例如，“ TROL ...” ） 。

该_width_指定以像素为单位，而不是以字符。

该_flags_参数是可选的，并且目前只支持[Qt.TextShowMnemonic](qt.html#TextFlag-enum)作为值。

艾莱德的标志将按照[layout direction](qt.html#LayoutDirection-enum);这将是在右侧的文本从右到左的布局，并在左侧为从右到左的布局。请注意，这种行为是独立的文本语言。

这个函数中引入了Qt 4.2中。

```
int QFontMetrics.height (self)
```

返回字体的高度。

这总是等于[ascent](qfontmetrics.html#ascent)（）+[descent](qfontmetrics.html#descent)（） 1 （ 1是基准线） 。

**See also** [leading](qfontmetrics.html#leading)（）和[lineSpacing](qfontmetrics.html#lineSpacing)（ ） 。

```
bool QFontMetrics.inFont (self, QChar)
```

返回True如果字符_ch_在字体中的有效字符，否则返回False 。

```
bool QFontMetrics.inFontUcs4 (self, int character)
```

返回True如果给定的_character_编码UCS-4/UTF-32是在字体中的有效字符，否则返回False 。

此功能被引入Qt的4.8 。

```
int QFontMetrics.leading (self)
```

返回字体的领先。

这是自然的线间间距。

**See also** [height](qfontmetrics.html#height)（）和[lineSpacing](qfontmetrics.html#lineSpacing)（ ） 。

```
int QFontMetrics.leftBearing (self, QChar)
```

返回字符的左轴承_ch_在字体。

左边的轴承是从字符的逻辑原点的字符的最左边的像素的右支距离。这个值是负的，如果该字符的像素延伸到逻辑原点的左边。

见宽（[QChar](qchar.html)）这个度量的图形化描述。

**See also** [rightBearing](qfontmetrics.html#rightBearing)（ ）[minLeftBearing](qfontmetrics.html#minLeftBearing)（）和[width](qfontmetrics.html#width)（ ） 。

```
int QFontMetrics.lineSpacing (self)
```

返回从一个基线的距离下。

该值始终等于[leading](qfontmetrics.html#leading)（）+[height](qfontmetrics.html#height)（ ） 。

**See also** [height](qfontmetrics.html#height)（）和[leading](qfontmetrics.html#leading)（ ） 。

```
int QFontMetrics.lineWidth (self)
```

返回下划线和删除线，调整字体的点大小的宽度。

**See also** [underlinePos](qfontmetrics.html#underlinePos)（ ）[overlinePos](qfontmetrics.html#overlinePos)（）和[strikeOutPos](qfontmetrics.html#strikeOutPos)（ ） 。

```
int QFontMetrics.maxWidth (self)
```

返回最宽的字符的字体的宽度。

```
int QFontMetrics.minLeftBearing (self)
```

返回字体的最小左轴承。

这是字体中的所有字符的最小leftBearing （字符） 。

请注意，此功能可能会非常缓慢，如果字体很大。

**See also** [minRightBearing](qfontmetrics.html#minRightBearing)（）和[leftBearing](qfontmetrics.html#leftBearing)（ ） 。

```
int QFontMetrics.minRightBearing (self)
```

返回字体的最低右侧轴承。

这是字体中的所有字符的最小rightBearing （字符） 。

请注意，此功能可能会非常缓慢，如果字体很大。

**See also** [minLeftBearing](qfontmetrics.html#minLeftBearing)（）和[rightBearing](qfontmetrics.html#rightBearing)（ ） 。

```
int QFontMetrics.overlinePos (self)
```

返回从基线的距离，其中一个上划线应绘制。

**See also** [underlinePos](qfontmetrics.html#underlinePos)（ ）[strikeOutPos](qfontmetrics.html#strikeOutPos)（）和[lineWidth](qfontmetrics.html#lineWidth)（ ） 。

```
int QFontMetrics.rightBearing (self, QChar)
```

返回字符的右侧轴承_ch_在字体。

右轴承是由一个后续字符的逻辑原点的最右边的像素的字符的左病房距离。这个值是负的，如果该字符的像素延伸到的权[width](qfontmetrics.html#width)的字符（） 。

See [width](qfontmetrics.html#width)（ ）这个指标的图形化描述。

**See also** [leftBearing](qfontmetrics.html#leftBearing)（ ）[minRightBearing](qfontmetrics.html#minRightBearing)（）和[width](qfontmetrics.html#width)（ ） 。

```
QSize QFontMetrics.size (self, int flags, QString text, int tabStops = 0, list-of-int tabArray = 0)
```

[

该_tabArray_参数也可能没有。

返回该尺寸中的像素_text_。

该_flags_参数是下列标志的按位或：

](qsize.html)

[](qsize.html)
*   [](qsize.html)[Qt.TextSingleLine](qt.html#TextFlag-enum) ignores newline characters.
*   [Qt.TextExpandTabs](qt.html#TextFlag-enum) expands tabs (see below)
*   [Qt.TextShowMnemonic](qt.html#TextFlag-enum) interprets "&x" as &lt;u&gt;x&lt;/u&gt;; i.e., underlined.
*   Qt.TextWordBreak breaks the text to fit the rectangle.

If [Qt.TextExpandTabs](qt.html#TextFlag-enum)在设置_flags_，则：如果_tabArray_不为null ，它指定了一个0结尾的像素位置的选项卡顺序，否则，如果_tabStops_是非零的，它被用作标籤间距（以像素为单位） 。

换行字符处理为换行符。

尽管在不同的实际字符的高度，的边界矩形的高度“是”， “是”是相同的。

**See also** [boundingRect](qfontmetrics.html#boundingRect)（ ） 。

```
int QFontMetrics.strikeOutPos (self)
```

返回从基准线的距离，其中应绘制的三振线。

**See also** [underlinePos](qfontmetrics.html#underlinePos)（ ）[overlinePos](qfontmetrics.html#overlinePos)（）和[lineWidth](qfontmetrics.html#lineWidth)（ ） 。

```
QRect QFontMetrics.tightBoundingRect (self, QString text)
```

[

返回字符周围紧张的边界矩形被指定的字符串中_text_。边界矩形总是至少复盖的像素集合的文本将涵盖如果画在（ 0 ， 0 ） 。

](qrect.html)

[注意，边框可以延伸到的（0，0 ），例如左斜体字体，返回的矩形的宽度可能比什么不同](qrect.html)[width](qfontmetrics.html#width)（ ）方法返回。

如果你想知道字符串的超前宽度（布局彼此相邻一组字符串） ，使用[width](qfontmetrics.html#width)（ ）来代替。

换行符的处理方法与普通字符，_not_作为换行符。

**Warning:**调用此方法将是非常缓慢的Windows 。

此功能被引入Qt的4.3 。

**See also** [width](qfontmetrics.html#width)（ ）[height](qfontmetrics.html#height)（）和[boundingRect](qfontmetrics.html#boundingRect)（ ） 。

```
int QFontMetrics.underlinePos (self)
```

返回从基线的距离，其中一个底线应绘制。

**See also** [overlinePos](qfontmetrics.html#overlinePos)（ ）[strikeOutPos](qfontmetrics.html#strikeOutPos)（）和[lineWidth](qfontmetrics.html#lineWidth)（ ） 。

```
int QFontMetrics.width (self, QChar)
```

返回该宽度在所述第一像素_len_字符_text_。如果_len_是负的（默认值） ，则整个字符串被使用。

注意，该值是_not_等于[boundingRect](qfontmetrics.html#boundingRect)（ ）宽（）;[boundingRect](qfontmetrics.html#boundingRect)（ ）返回一个描述像素的矩形这个字符串将复盖而宽度（ ）返回的距离应在其中绘制的下一个字符串。

**See also** [boundingRect](qfontmetrics.html#boundingRect)（ ） 。

```
int QFontMetrics.width (self, QString text, int length = -1)
```

```
int QFontMetrics.widthChar (self, QChar)
```

```
int QFontMetrics.xHeight (self)
```

返回字体的'X'的高度。这是常常但不总是相同的字符“X”的高度。

```
bool QFontMetrics.__eq__ (self, QFontMetrics other)
```

```
bool QFontMetrics.__ne__ (self, QFontMetrics other)
```