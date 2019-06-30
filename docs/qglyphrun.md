# QGlyphRun Class Reference

## [[QtGui](index.htm) module]

该QGlyphRun类提供了直接访问字体内部字形。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QGlyphRun other)`
*   `clear (self)`
*   `list-of-int glyphIndexes (self)`
*   `bool overline (self)`
*   `list-of-QPointF positions (self)`
*   `QRawFont rawFont (self)`
*   `setGlyphIndexes (self, list-of-int glyphIndexes)`
*   `setOverline (self, bool overline)`
*   `setPositions (self, list-of-QPointF positions)`
*   `setRawFont (self, QRawFont rawFont)`
*   `setStrikeOut (self, bool strikeOut)`
*   `setUnderline (self, bool underline)`
*   `bool strikeOut (self)`
*   `bool underline (self)`

### Special Methods

*   `bool __eq__ (self, QGlyphRun other)`
*   `bool __ne__ (self, QGlyphRun other)`

* * *

## Detailed Description

该QGlyphRun类提供了直接访问字体内部字形。

当Qt的显示文本的字符串以Unicode编码，它会先转换成Unicode的点到字形索引的列表，并基于一种或多种字体位置的列表。文本的Unicode表示和[QFont](qfont.html)对象将在这种情况下作为一个方便的抽象，隐藏的显示在屏幕上的文本时，什么实际发生的细节。例如，通过在文本实际到达屏幕的时候，它可以由一组字体除了由用户指定的一个表示，例如在情况下，最初选择的字体不支持所有包含在文本的书写系统。

在某些情况下，它可以作为一个应用程序开发人员有更多的低级别的控制权而在一个特定的字体字形绘制到屏幕上是有用的。这可能是例如在使用外部字体引擎和文本整形连同Qt应用程序的情况。 QGlyphRun提供一个接口，需要得到的屏幕上的文本的原始数据。它包含的字形索引，每个字形的位置和字体的列表。

它是用户的责任，以确保所选的字体实际上包含所提供的字形索引。

[QTextLayout.glyphRuns](qtextlayout.html#glyphRuns)（）或[QTextFragment.glyphRuns](qtextfragment.html#glyphRuns)（ ）可用于Unicode编码的文本转换成QGlyphRun对象的列表，并[QPainter.drawGlyphRun](qpainter.html#drawGlyphRun)（ ）可以用来绘制字形。

**Note:**请注意[QRawFont](qrawfont.html)被认为是局部的，其中它被构造的线程。这反过来意味着一个新的[QRawFont](qrawfont.html)将要被创建并在QGlyphRun设置，如果它被移动到一个不同的线程。如果QGlyphRun包含引用[QRawFont](qrawfont.html)从一个不同的线程以外的线程的电流，它也不可能使用以绘制字形一[QPainter](qpainter.html)作为[QRawFont](qrawfont.html)被视为无效，无法在这种情况下。

* * *

## Method Documentation

```
QGlyphRun.__init__ (self)
```

构造一个空[QGlyphRun](qglyphrun.html)对象。

```
QGlyphRun.__init__ (self, QGlyphRun other)
```

构造一个[QGlyphRun](qglyphrun.html)对象，这是一个拷贝_other_。

```
QGlyphRun.clear (self)
```

清除所有数据在[QGlyphRun](qglyphrun.html)对象。

```
list-of-int QGlyphRun.glyphIndexes (self)
```

返回该字形索引此[QGlyphRun](qglyphrun.html)对象。

**See also** [setGlyphIndexes](qglyphrun.html#setGlyphIndexes)（）和[setPositions](qglyphrun.html#setPositions)（ ） 。

```
bool QGlyphRun.overline (self)
```

返回True如果[QGlyphRun](qglyphrun.html)应涂以划线的装饰。

**See also** [setOverline](qglyphrun.html#setOverline)（ ） 。

```
list-of-QPointF QGlyphRun.positions (self)
```

返回基线每个字形的这套字形索引的边缘的位置。

**See also** [setPositions](qglyphrun.html#setPositions)（ ） 。

```
QRawFont QGlyphRun.rawFont (self)
```

[](qrawfont.html)

[返回选定为这个字体](qrawfont.html)[QGlyphRun](qglyphrun.html)对象。

**See also** [setRawFont](qglyphrun.html#setRawFont)（ ） 。

```
QGlyphRun.setGlyphIndexes (self, list-of-int glyphIndexes)
```

设置此标志符号索引[QGlyphRun](qglyphrun.html)反对_glyphIndexes_。字形索引必须是有效的选择的字体。

**See also** [glyphIndexes](qglyphrun.html#glyphIndexes)（ ） 。

```
QGlyphRun.setOverline (self, bool overline)
```

表明这[QGlyphRun](qglyphrun.html)应涂以划线的装饰，如果_overline_是真实的。否则，[QGlyphRun](qglyphrun.html)应涂有没有划线的装饰。

**See also** [overline](qglyphrun.html#overline)（ ） 。

```
QGlyphRun.setPositions (self, list-of-QPointF positions)
```

设置基线每个字形的边缘在这套字形索引的位置，以_positions_。

**See also** [positions](qglyphrun.html#positions)（ ） 。

```
QGlyphRun.setRawFont (self, QRawFont rawFont)
```

设置由指定的字体_rawFont_要用于查找的字形索引的字体。

**See also** [rawFont](qglyphrun.html#rawFont)（）和[setGlyphIndexes](qglyphrun.html#setGlyphIndexes)（ ） 。

```
QGlyphRun.setStrikeOut (self, bool strikeOut)
```

表明这[QGlyphRun](qglyphrun.html)应涂用重拳出击，如果装修_strikeOut_是真实的。否则，[QGlyphRun](qglyphrun.html)应该涂上不重拳出击装修。

**See also** [strikeOut](qglyphrun.html#strikeOut)（ ） 。

```
QGlyphRun.setUnderline (self, bool underline)
```

表明这[QGlyphRun](qglyphrun.html)应涂带下划线的装饰，如果_underline_是真实的。否则，[QGlyphRun](qglyphrun.html)应涂上无下划线装饰。

**See also** [underline](qglyphrun.html#underline)（ ） 。

```
bool QGlyphRun.strikeOut (self)
```

返回True如果[QGlyphRun](qglyphrun.html)应涂以重拳出击的装饰。

**See also** [setStrikeOut](qglyphrun.html#setStrikeOut)（ ） 。

```
bool QGlyphRun.underline (self)
```

返回True如果[QGlyphRun](qglyphrun.html)应涂带下划线的装饰。

**See also** [setUnderline](qglyphrun.html#setUnderline)（ ） 。

```
bool QGlyphRun.__eq__ (self, QGlyphRun other)
```

```
bool QGlyphRun.__ne__ (self, QGlyphRun other)
```