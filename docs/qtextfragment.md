# QTextFragment Class Reference

## [[QtGui](index.htm) module]

该QTextFragment类包含一段文字中[QTextDocument](qtextdocument.html)与单个[QTextCharFormat](qtextcharformat.html)。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QTextFragment o)`
*   `QTextCharFormat charFormat (self)`
*   `int charFormatIndex (self)`
*   `bool contains (self, int position)`
*   `list-of-QGlyphRun glyphRuns (self)`
*   `bool isValid (self)`
*   `int length (self)`
*   `int position (self)`
*   `QString text (self)`

### Special Methods

*   `bool __eq__ (self, QTextFragment o)`
*   `bool __ge__ (self, QTextFragment o)`
*   `bool __lt__ (self, QTextFragment o)`
*   `bool __ne__ (self, QTextFragment o)`

* * *

## Detailed Description

该QTextFragment类包含一段文字中[QTextDocument](qtextdocument.html)与单个[QTextCharFormat](qtextcharformat.html)。

文本片段描述一张存储与单个字符格式的文本。文本中的字符格式的变化可以通过文本片段具有不同格式的序列来表示。

如果用户编辑的文本片段，并引入不同的字符格式，片段的文字将被分割在各点的格式变化，以及新的片段将会被创建。例如，改变一些文本的样式在句子的中间将导致片段被分成三个独立的片段：第一个和第三个前具有相同的格式，第二个与新的风格。第一个片段将包含文本从句子的开头，第二个将包含从中间的文本，第三个从句子的结尾获取文本。

![](../img/qtextfragment-split.png)

片段的文本和字符格式可以用得到[text](qtextfragment.html#text)（）和[charFormat](qtextfragment.html#charFormat)（）函数。该[length](qtextfragment.html#length)（）函数给出了在片段中的文本的长度。[position](qtextfragment.html#position)（ ）给出了该片段的开始的文档中的位置。为了确定该片段是否包含在文档中的特定位置，请使用[contains](qtextfragment.html#contains)（）函数。

* * *

## Method Documentation

```
QTextFragment.__init__ (self)
```

创建一个新的空文本片段。

```
QTextFragment.__init__ (self, QTextFragment o)
```

```
QTextCharFormat QTextFragment.charFormat (self)
```

[

返回文本片段的字符格式。

](qtextcharformat.html)

[**See also**](qtextcharformat.html) [text](qtextfragment.html#text)（ ） 。

```
int QTextFragment.charFormatIndex (self)
```

返回一个索引到文档内部的字符格式的文本片段的字符格式列表。

**See also** [QTextDocument.allFormats](qtextdocument.html#allFormats)（ ） 。

```
bool QTextFragment.contains (self, int position)
```

如果文本片段包含文本在给定的，则返回True_position_在文件中，否则返回False 。

```
list-of-QGlyphRun QTextFragment.glyphRuns (self)
```

返回此文字片段的字形。字形的位置是相对于的位置[QTextBlock](qtextblock.html)的布局。

**See also** [QGlyphRun](qglyphrun.html)，[QTextBlock.layout](qtextblock.html#layout)（ ）[QTextLayout.position](qtextlayout.html#position)（）和[QPainter.drawGlyphRun](qpainter.html#drawGlyphRun)（ ） 。

```
bool QTextFragment.isValid (self)
```

返回True如果这是一个有效的文本片段（即在文档中的有效位置），否则返回False 。

```
int QTextFragment.length (self)
```

返回字符的文本片段的数量。

**See also** [text](qtextfragment.html#text)（ ） 。

```
int QTextFragment.position (self)
```

返回文档中当前文本片段中的位置。

```
QString QTextFragment.text (self)
```

返回文本片段的为纯文本。

**See also** [length](qtextfragment.html#length)（）和[charFormat](qtextfragment.html#charFormat)（ ） 。

```
bool QTextFragment.__eq__ (self, QTextFragment o)
```

```
bool QTextFragment.__ge__ (self, QTextFragment o)
```

```
bool QTextFragment.__lt__ (self, QTextFragment o)
```

```
bool QTextFragment.__ne__ (self, QTextFragment o)
```