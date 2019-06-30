# QTextLayout Class Reference

## [[QtGui](index.htm) module]

该QTextLayout类用于布局并呈现文本。[More...](#details)

### Types

*   `enum CursorMode { SkipCharacters, SkipWords }`
*   `class **[FormatRange](index.htm)**`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QString text)`
*   `__init__ (self, QString text, QFont font, QPaintDevice paintDevice = None)`
*   `__init__ (self, QTextBlock b)`
*   `list-of-QTextLayout.FormatRange additionalFormats (self)`
*   `beginLayout (self)`
*   `QRectF boundingRect (self)`
*   `bool cacheEnabled (self)`
*   `clearAdditionalFormats (self)`
*   `clearLayout (self)`
*   `QTextLine createLine (self)`
*   `Qt.CursorMoveStyle cursorMoveStyle (self)`
*   `draw (self, QPainter p, QPointF pos, list-of-QTextLayout.FormatRange selections = list-of-QTextLayout.FormatRange, QRectF clip = QRectF())`
*   `drawCursor (self, QPainter p, QPointF pos, int cursorPosition)`
*   `drawCursor (self, QPainter p, QPointF pos, int cursorPosition, int width)`
*   `endLayout (self)`
*   `QFont font (self)`
*   `list-of-QGlyphRun glyphRuns (self)`
*   `bool isValidCursorPosition (self, int pos)`
*   `int leftCursorPosition (self, int oldPos)`
*   `QTextLine lineAt (self, int i)`
*   `int lineCount (self)`
*   `QTextLine lineForTextPosition (self, int pos)`
*   `float maximumWidth (self)`
*   `float minimumWidth (self)`
*   `int nextCursorPosition (self, int oldPos, CursorMode mode = QTextLayout.SkipCharacters)`
*   `QPointF position (self)`
*   `int preeditAreaPosition (self)`
*   `QString preeditAreaText (self)`
*   `int previousCursorPosition (self, int oldPos, CursorMode mode = QTextLayout.SkipCharacters)`
*   `int rightCursorPosition (self, int oldPos)`
*   `setAdditionalFormats (self, list-of-QTextLayout.FormatRange overrides)`
*   `setCacheEnabled (self, bool enable)`
*   `setCursorMoveStyle (self, Qt.CursorMoveStyle style)`
*   `setFont (self, QFont f)`
*   `setPosition (self, QPointF p)`
*   `setPreeditArea (self, int position, QString text)`
*   `setText (self, QString string)`
*   `setTextOption (self, QTextOption option)`
*   `QString text (self)`
*   `QTextOption textOption (self)`

* * *

## Detailed Description

该QTextLayout类用于布局并呈现文本。

它提供了从现代文字排版引擎预期的许多功能，包括Unicode标准的渲染，断行和处理游标定位。它也可以产生并呈现独立于设备的布局，东西是所见即所得的应用非常重要。

这个类有一个相当低级别的API ，除非你打算实现自己的文本呈现为一些专门的小工具，你可能不会需要直接使用它。

QTextLayout可以同时用于普通和丰富的文本。

QTextLayout可以被用来创建一个序列[QTextLine](qtextline.html)用实例给出的宽度，并且可以在屏幕上独立地放置它们。一旦布局完成，这些线可以得出一个油漆设备上。

进行布局的文本可以在构造函数中提供或设置[setText](qtextlayout.html#setText)（ ） 。

布局可以被看作是一个序列[QTextLine](qtextline.html)对象;使用[createLine](qtextlayout.html#createLine)（ ）来创建一个[QTextLine](qtextline.html)例如，与[lineAt](qtextlayout.html#lineAt)（）或[lineForTextPosition](qtextlayout.html#lineForTextPosition)（ ）来检索创建的行。

下面是一个代码片段，演示了布局阶段：

```
 int leading = fontMetrics.leading();
 [qreal](index.htm#qreal-typedef) height = 0;
 textLayout.beginLayout();
 while (1) {
     [QTextLine](qtextline.html) line = textLayout.createLine();
     if (!line.isValid())
         break;

     line.setLineWidth(lineWidth);
     height += leading;
     line.setPosition([QPointF](qpointf.html)(0, height));
     height += line.height();
 }
 textLayout.endLayout();

```

文字可以再通过调用布局的呈现[draw](qtextlayout.html#draw)（ ）函数：

```
 [QPainter](qpainter.html) painter(this);
 textLayout.draw(&painter, [QPoint](qpoint.html)(0, 0));

```

文本中的一个给定的位置，你可以找到一个有效的光标位置与[isValidCursorPosition](qtextlayout.html#isValidCursorPosition)（ ）[nextCursorPosition](qtextlayout.html#nextCursorPosition)（）和[previousCursorPosition](qtextlayout.html#previousCursorPosition)（ ） 。

该QTextLayout本身可被定位以[setPosition](qtextlayout.html#setPosition)（） ，它有一个[boundingRect](qtextlayout.html#boundingRect)（） ，和一个[minimumWidth](qtextlayout.html#minimumWidth)（）和一个[maximumWidth](qtextlayout.html#maximumWidth)（ ） 。

* * *

## Type Documentation

```
QTextLayout.CursorMode
```

| Constant | Value |
| --- | --- |
| `QTextLayout.SkipCharacters` | `0` |
| `QTextLayout.SkipWords` | `1` |

* * *

## Method Documentation

```
QTextLayout.__init__ (self)
```

构造一个空的文本布局。

**See also** [setText](qtextlayout.html#setText)（ ） 。

```
QTextLayout.__init__ (self, QString text)
```

构造一个文本布局奠定了给定的_text_。

```
QTextLayout.__init__ (self, QString text, QFont font, QPaintDevice paintDevice = None)
```

构造一个文本布局奠定了给定的_text_用指定的_font_。

所有的度量和布局计算将在绘制设备的条款进行，_paintdevice_。如果_paintdevice_为0计算将在屏幕上的指标来完成。

```
QTextLayout.__init__ (self, QTextBlock b)
```

```
list-of-QTextLayout.FormatRange QTextLayout.additionalFormats (self)
```

返回由文本布局支持其他格式的列表。

**See also** [setAdditionalFormats](qtextlayout.html#setAdditionalFormats)（）和[clearAdditionalFormats](qtextlayout.html#clearAdditionalFormats)（ ） 。

```
QTextLayout.beginLayout (self)
```

开始布局过程。

**See also** [endLayout](qtextlayout.html#endLayout)（ ） 。

```
QRectF QTextLayout.boundingRect (self)
```

[

最小的矩形包含在布局的所有行。

```
bool QTextLayout.cacheEnabled (self)
```

返回True如果完整的布局信息被缓存，否则返回False 。

](qrectf.html)

[**See also**](qrectf.html) [setCacheEnabled](qtextlayout.html#setCacheEnabled)（ ） 。

```
QTextLayout.clearAdditionalFormats (self)
```

清除由文本布局支持其他格式的列表。

**See also** [additionalFormats](qtextlayout.html#additionalFormats)（）和[setAdditionalFormats](qtextlayout.html#setAdditionalFormats)（ ） 。

```
QTextLayout.clearLayout (self)
```

清除布局的线路信息。已调用该函数后，[lineCount](qtextlayout.html#lineCount)（ ）返回0 。

此功能被引入Qt的4.4 。

```
QTextLine QTextLayout.createLine (self)
```

[

返回一个新的文本行进行布局，如果有文本被插入到布局，否则返回一个无效的文本行。

](qtextline.html)

[文本布局创建布局的最后一行之后开始，或如果布局是空的开始一个新行的对象。布局维护内部光标，每行充满了文本从光标所在位置开始的时候](qtextline.html)[QTextLine.setLineWidth](qtextline.html#setLineWidth)（ ）函数被调用。

一旦[QTextLine.setLineWidth](qtextline.html#setLineWidth)（）被调用时，一个新的行可以被创建和填充文本。重复这个过程会布置文本包含在整个区块[QTextLayout](qtextlayout.html)。如果没有文本左被插入到布局，[QTextLine](qtextline.html)返回的将是无效的（参考isValid （ ）将返回False ） 。

```
Qt.CursorMoveStyle QTextLayout.cursorMoveStyle (self)
```

[](qt.html#CursorMoveStyle-enum)

[这样做的光标运动风格](qt.html#CursorMoveStyle-enum)[QTextLayout](qtextlayout.html)。默认值是[Qt.LogicalMoveStyle](qt.html#CursorMoveStyle-enum)。

此功能被引入Qt的4.8 。

**See also** [setCursorMoveStyle](qtextlayout.html#setCursorMoveStyle)（ ） 。

```
QTextLayout.draw (self, QPainter p, QPointF pos, list-of-QTextLayout.FormatRange selections = list-of-QTextLayout.FormatRange, QRectF clip = QRectF())
```

绘制整个布局上的画家_p_在所指定的位置_pos_。所呈现的布局包括给定的_selections_并通过指定的矩形内裁剪_clip_。

```
QTextLayout.drawCursor (self, QPainter p, QPointF pos, int cursorPosition)
```

绘制文本光标与当前的画笔和指定_width_在给定的_position_使用_painter_规定。在文本中的相应位置被指定_cursorPosition_。

```
QTextLayout.drawCursor (self, QPainter p, QPointF pos, int cursorPosition, int width)
```

这是一个重载函数。

绘制文本光标与当前的画笔在给定的_position_使用_painter_规定。在文本中的相应位置被指定_cursorPosition_。

```
QTextLayout.endLayout (self)
```

结束的布局过程。

**See also** [beginLayout](qtextlayout.html#beginLayout)（ ） 。

```
QFont QTextLayout.font (self)
```

[

返回当前字体是用于布局，或一个默认的字体，如果没有被设置。

](qfont.html)

[**See also**](qfont.html) [setFont](qtextlayout.html#setFont)（ ） 。

```
list-of-QGlyphRun QTextLayout.glyphRuns (self)
```

返回所有字形的字形索引和位置在这[QTextLayout](qtextlayout.html)。这是一个昂贵的功能，并且不应该被称为在一个时间敏感的上下文。

此功能被引入Qt的4.8 。

**See also** [draw](qtextlayout.html#draw)（）和[QPainter.drawGlyphRun](qpainter.html#drawGlyphRun)（ ） 。

```
bool QTextLayout.isValidCursorPosition (self, int pos)
```

/返回True如果位置_pos_是一个有效的光标位置。

在Unicode上下文中的文字部分职位是无效的光标位置，因为该位置是一个Unicode代理或字形集群内。

一字形群集是两个或两个以上构成屏幕上的一个不可分割的实体Unicode字符序列。例如拉丁字符`A （ 0X41 ） ，以及结合diaresis （ 0x308 ） '可以在Unicode中由两个字符， 'A来表示' 。文本光标只能有效地定位之前或之后，这两个人物，他们之间从来没有因为这没有任何意义。在印度语每一个音节构成字形集群。

```
int QTextLayout.leftCursorPosition (self, int oldPos)
```

返回光标位置的左边_oldPos_，在它旁边。该位置是依赖于字符的视觉位置，后双向重新排序。

此功能被引入Qt的4.8 。

**See also** [rightCursorPosition](qtextlayout.html#rightCursorPosition)（）和[previousCursorPosition](qtextlayout.html#previousCursorPosition)（ ） 。

```
QTextLine QTextLayout.lineAt (self, int i)
```

[

返回_i_个线在这个文本布局的文本。

](qtextline.html)

[**See also**](qtextline.html) [lineCount](qtextlayout.html#lineCount)（）和[lineForTextPosition](qtextlayout.html#lineForTextPosition)（ ） 。

```
int QTextLayout.lineCount (self)
```

返回总行在这个文本布局的数量。

**See also** [lineAt](qtextlayout.html#lineAt)（ ） 。

```
QTextLine QTextLayout.lineForTextPosition (self, int pos)
```

[

返回包含由指定的光标位置的行_pos_。

](qtextline.html)

[**See also**](qtextline.html) [isValidCursorPosition](qtextlayout.html#isValidCursorPosition)（）和[lineAt](qtextlayout.html#lineAt)（ ） 。

```
float QTextLayout.maximumWidth (self)
```

最大宽度的布局可能会扩大到，这基本上是整个文本的宽度。

**Warning:**这个函数只返回一个有效的值的布局已经完成之后。

**See also** [minimumWidth](qtextlayout.html#minimumWidth)（ ） 。

```
float QTextLayout.minimumWidth (self)
```

最小宽度的布局需要。这是布局的最小的非易碎的子串的宽度。

**Warning:**这个函数只返回一个有效的值的布局已经完成之后。

**See also** [maximumWidth](qtextlayout.html#maximumWidth)（ ） 。

```
int QTextLayout.nextCursorPosition (self, int oldPos, CursorMode mode = QTextLayout.SkipCharacters)
```

后返回下一个有效的光标位置_oldPos_尊重给定的游标_mode_。的回报价值_oldPos_如果_oldPos_不是一个有效的光标位置。

**See also** [isValidCursorPosition](qtextlayout.html#isValidCursorPosition)（）和[previousCursorPosition](qtextlayout.html#previousCursorPosition)（ ） 。

```
QPointF QTextLayout.position (self)
```

[

布局的全球地位。这是独立于布局过程中的边界矩形和。

这个函数中引入了Qt 4.2中。

](qpointf.html)

[**See also**](qpointf.html) [setPosition](qtextlayout.html#setPosition)（ ） 。

```
int QTextLayout.preeditAreaPosition (self)
```

返回编辑发生之前，将待处理的文本布局的区域的位置。

**See also** [preeditAreaText](qtextlayout.html#preeditAreaText)（ ） 。

```
QString QTextLayout.preeditAreaText (self)
```

返回插入在布局编辑发生前的文本。

**See also** [preeditAreaPosition](qtextlayout.html#preeditAreaPosition)（ ） 。

```
int QTextLayout.previousCursorPosition (self, int oldPos, CursorMode mode = QTextLayout.SkipCharacters)
```

返回前的第一个有效的光标位置_oldPos_尊重给定的游标_mode_。的回报价值_oldPos_如果_oldPos_不是一个有效的光标位置。

**See also** [isValidCursorPosition](qtextlayout.html#isValidCursorPosition)（）和[nextCursorPosition](qtextlayout.html#nextCursorPosition)（ ） 。

```
int QTextLayout.rightCursorPosition (self, int oldPos)
```

返回光标位置的右侧_oldPos_，在它旁边。该位置是依赖于字符的视觉位置，后双向重新排序。

此功能被引入Qt的4.8 。

**See also** [leftCursorPosition](qtextlayout.html#leftCursorPosition)（）和[nextCursorPosition](qtextlayout.html#nextCursorPosition)（ ） 。

```
QTextLayout.setAdditionalFormats (self, list-of-QTextLayout.FormatRange overrides)
```

设置由文本布局，以支持更多的格式_formatList_。

**See also** [additionalFormats](qtextlayout.html#additionalFormats)（）和[clearAdditionalFormats](qtextlayout.html#clearAdditionalFormats)（ ） 。

```
QTextLayout.setCacheEnabled (self, bool enable)
```

启用的完整布局信息，如果缓存_enable_为True，否则将禁用布局缓存。平时[QTextLayout](qtextlayout.html)调用后抛出的大部分布点信息了[endLayout](qtextlayout.html#endLayout)（）来减少内存消耗。但是，如果你要绘制奠定了文字后直接启用缓存可能会加快显着绘图。

**See also** [cacheEnabled](qtextlayout.html#cacheEnabled)（ ） 。

```
QTextLayout.setCursorMoveStyle (self, Qt.CursorMoveStyle style)
```

设置光标的运动风格。如果[QTextLayout](qtextlayout.html)由文件的支持，你可以忽略这一点，在使用该选项[QTextDocument](qtextdocument.html)，这个选项对于像小部件[QLineEdit](qlineedit.html)或自定义部件没有[QTextDocument](qtextdocument.html)。默认值是[Qt.LogicalMoveStyle](qt.html#CursorMoveStyle-enum)。

此功能被引入Qt的4.8 。

**See also** [cursorMoveStyle](qtextlayout.html#cursorMoveStyle)（ ） 。

```
QTextLayout.setFont (self, QFont f)
```

设置布局的字体给定的_font_。布局是无效的，必须重新布局。

**See also** [font](qtextlayout.html#font)（ ） 。

```
QTextLayout.setPosition (self, QPointF p)
```

将文本布局指向_p_。

**See also** [position](qtextlayout.html#position)（ ） 。

```
QTextLayout.setPreeditArea (self, int position, QString text)
```

设置_position_和_text_编辑发生之前被处理在布局区域。

**See also** [preeditAreaPosition](qtextlayout.html#preeditAreaPosition)（）和[preeditAreaText](qtextlayout.html#preeditAreaText)（ ） 。

```
QTextLayout.setText (self, QString string)
```

设置布局的文本给定的_string_。布局是无效的，必须重新布局。

当使用这种注意[QTextLayout](qtextlayout.html)作为一个部分[QTextDocument](qtextdocument.html)这种方法不会有任何影响。

**See also** [text](qtextlayout.html#text)（ ） 。

```
QTextLayout.setTextOption (self, QTextOption option)
```

设置文本选项的结构，控制布局过程中给定的_option_。

**See also** [textOption](qtextlayout.html#textOption)（ ） 。

```
QString QTextLayout.text (self)
```

返回布局的文本。

**See also** [setText](qtextlayout.html#setText)（ ） 。

```
QTextOption QTextLayout.textOption (self)
```

[

返回用于控制布局过程中的当前文本选项。

](qtextoption.html)

[**See also**](qtextoption.html) [setTextOption](qtextlayout.html#setTextOption)（ ） 。