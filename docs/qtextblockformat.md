# QTextBlockFormat Class Reference

## [[QtGui](index.htm) module]

该QTextBlockFormat类提供格式设置信息的文本在一个块[QTextDocument](qtextdocument.html)。[More...](#details)

继承[QTextFormat](qtextformat.html)。

### Types

*   `enum LineHeightTypes { SingleHeight, ProportionalHeight, FixedHeight, MinimumHeight, LineDistanceHeight }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QTextBlockFormat)`
*   `Qt.Alignment alignment (self)`
*   `float bottomMargin (self)`
*   `int indent (self)`
*   `bool isValid (self)`
*   `float leftMargin (self)`
*   `float lineHeight (self, float scriptLineHeight, float scaling)`
*   `float lineHeight (self)`
*   `int lineHeightType (self)`
*   `bool nonBreakableLines (self)`
*   `QTextFormat.PageBreakFlags pageBreakPolicy (self)`
*   `float rightMargin (self)`
*   `setAlignment (self, Qt.Alignment aalignment)`
*   `setBottomMargin (self, float margin)`
*   `setIndent (self, int aindent)`
*   `setLeftMargin (self, float margin)`
*   `setLineHeight (self, float height, int heightType)`
*   `setNonBreakableLines (self, bool b)`
*   `setPageBreakPolicy (self, QTextFormat.PageBreakFlags flags)`
*   `setRightMargin (self, float margin)`
*   `setTabPositions (self, list-of-QTextOption.Tab tabs)`
*   `setTextIndent (self, float margin)`
*   `setTopMargin (self, float margin)`
*   `list-of-QTextOption.Tab tabPositions (self)`
*   `float textIndent (self)`
*   `float topMargin (self)`

* * *

## Detailed Description

该QTextBlockFormat类提供格式设置信息的文本在一个块[QTextDocument](qtextdocument.html)。

文档是由块的列表为代表的[QTextBlock](qtextblock.html)对象。每个块可以包含某种类型的产品，如一个文本段落，表格，列表或图像。每个块都有一个关联的QTextBlockFormat ，指定其特性。

为了照顾左到右，右到左的语言，你可以用setDirection （ ）设置一个块的方向。段落对齐方式设置与[setAlignment](qtextblockformat.html#setAlignment)（ ） 。利润是由控制[setTopMargin](qtextblockformat.html#setTopMargin)（ ）[setBottomMargin](qtextblockformat.html#setBottomMargin)（ ）[setLeftMargin](qtextblockformat.html#setLeftMargin)（ ）[setRightMargin](qtextblockformat.html#setRightMargin)（ ） 。整体缩进设置[setIndent](qtextblockformat.html#setIndent)（） ，与所述第一行的缩进[setTextIndent](qtextblockformat.html#setTextIndent)（ ） 。

行距设置与[setLineHeight](qtextblockformat.html#setLineHeight)（ ），并通过检索[lineHeight](qtextblockformat.html#lineHeight)（）和[lineHeightType](qtextblockformat.html#lineHeightType)（ ） 。行距可用的类型是在[LineHeightTypes](qtextblockformat.html#LineHeightTypes-enum)枚举。

断行可以启用和禁用[setNonBreakableLines](qtextblockformat.html#setNonBreakableLines)（ ） 。

用于绘制段落的背景的画笔设置与[setBackground()](qtextformat.html#setBackground)和文本的外观的其他方面可以通过使用自定义的[setProperty()](qtextformat.html#setProperty)与功能`OutlinePen`，`ForegroundBrush`和`BackgroundBrush` [QTextFormat.Property](qtextformat.html#Property-enum)值。

如果文本块是一个列表的一部分，它也可以有一个列表的格式，与该listFormat （）函数访问。

* * *

## Type Documentation

```
QTextBlockFormat.LineHeightTypes
```

这个枚举变量描述了不同类型的线间距支持段落可以有。

| Constant | Value | Description |
| --- | --- | --- |
| `QTextBlockFormat.SingleHeight` | `0` | 这是默认行高：单倍行距。 |
| `QTextBlockFormat.ProportionalHeight` | `1` | 这个设置的间距成正比线（百分比） 。例如，设置为200双间距。 |
| `QTextBlockFormat.FixedHeight` | `2` | 这将设置行高为固定行高（以像素为单位） 。 |
| `QTextBlockFormat.MinimumHeight` | `3` | 此设置最小行高（以像素为单位） 。 |
| `QTextBlockFormat.LineDistanceHeight` | `4` | 这增加了线路之间的指定高度（以像素为单位） 。 |

这个枚举被引入或修改的Qt 4.8 。

**See also** [lineHeight](qtextblockformat.html#lineHeight)（ ）[lineHeightType](qtextblockformat.html#lineHeightType)（）和[setLineHeight](qtextblockformat.html#setLineHeight)（ ） 。

* * *

## Method Documentation

```
QTextBlockFormat.__init__ (self)
```

构造一个新的[QTextBlockFormat](qtextblockformat.html)。

```
QTextBlockFormat.__init__ (self, QTextBlockFormat)
```

```
Qt.Alignment QTextBlockFormat.alignment (self)
```

[

返回段落的对齐方式。

](index.htm)

[**See also**](index.htm) [setAlignment](qtextblockformat.html#setAlignment)（ ） 。

```
float QTextBlockFormat.bottomMargin (self)
```

返回段的下边界。

**See also** [setBottomMargin](qtextblockformat.html#setBottomMargin)（）和[topMargin](qtextblockformat.html#topMargin)（ ） 。

```
int QTextBlockFormat.indent (self)
```

返回段落的缩进。

**See also** [setIndent](qtextblockformat.html#setIndent)（ ） 。

```
bool QTextBlockFormat.isValid (self)
```

返回True如果该块格式是有效的，否则返回False 。

```
float QTextBlockFormat.leftMargin (self)
```

返回段落的左边距。

**See also** [setLeftMargin](qtextblockformat.html#setLeftMargin)（ ）[rightMargin](qtextblockformat.html#rightMargin)（）和[indent](qtextblockformat.html#indent)（ ） 。

```
float QTextBlockFormat.lineHeight (self, float scriptLineHeight, float scaling)
```

返回该行的高度，在基于由给定的脚本行的高度的段落_scriptLineHeight_和指定的_scaling_因素。

返回的值也依赖于给定的[LineHeightType](qtextformat.html#Property-enum)该段以及作为[LineHeight](qtextformat.html#Property-enum)已经被设置为段设置。

缩放是需要的高度，其中包括固定像素数量，能够适当地调整它们进行打印。

此功能被引入Qt的4.8 。

**See also** [LineHeightTypes](qtextblockformat.html#LineHeightTypes-enum)，[setLineHeight](qtextblockformat.html#setLineHeight)（）和[lineHeightType](qtextblockformat.html#lineHeightType)（ ） 。

```
float QTextBlockFormat.lineHeight (self)
```

这将返回[LineHeight](qtextformat.html#Property-enum)属性的段落。

此功能被引入Qt的4.8 。

**See also** [LineHeightTypes](qtextblockformat.html#LineHeightTypes-enum)，[setLineHeight](qtextblockformat.html#setLineHeight)（）和[lineHeightType](qtextblockformat.html#lineHeightType)（ ） 。

```
int QTextBlockFormat.lineHeightType (self)
```

这将返回[LineHeightType](qtextformat.html#Property-enum)该段的属性。

此功能被引入Qt的4.8 。

**See also** [LineHeightTypes](qtextblockformat.html#LineHeightTypes-enum)，[setLineHeight](qtextblockformat.html#setLineHeight)（）和[lineHeight](qtextblockformat.html#lineHeight)（ ） 。

```
bool QTextBlockFormat.nonBreakableLines (self)
```

返回True如果段落中的行是不易碎，否则返回False 。

**See also** [setNonBreakableLines](qtextblockformat.html#setNonBreakableLines)（ ） 。

```
QTextFormat.PageBreakFlags QTextBlockFormat.pageBreakPolicy (self)
```

[](index.htm)

[返回段落中的当前设置的分页符政策。默认值是](index.htm)[QTextFormat.PageBreak_Auto](qtextformat.html#PageBreakFlag-enum)。

这个函数中引入了Qt 4.2中。

**See also** [setPageBreakPolicy](qtextblockformat.html#setPageBreakPolicy)（ ） 。

```
float QTextBlockFormat.rightMargin (self)
```

返回段落的右边距。

**See also** [setRightMargin](qtextblockformat.html#setRightMargin)（）和[leftMargin](qtextblockformat.html#leftMargin)（ ） 。

```
QTextBlockFormat.setAlignment (self, Qt.Alignment aalignment)
```

设置段落的_alignment_。

**See also** [alignment](qtextblockformat.html#alignment)（ ） 。

```
QTextBlockFormat.setBottomMargin (self, float margin)
```

设置段落的底部_margin_。

**See also** [bottomMargin](qtextblockformat.html#bottomMargin)（ ）[setTopMargin](qtextblockformat.html#setTopMargin)（ ）[setLeftMargin](qtextblockformat.html#setLeftMargin)（）和[setRightMargin](qtextblockformat.html#setRightMargin)（ ） 。

```
QTextBlockFormat.setIndent (self, int aindent)
```

设置段落的_indentation_。边距独立设置的凹槽构成的[setLeftMargin](qtextblockformat.html#setLeftMargin)（）和[setTextIndent](qtextblockformat.html#setTextIndent)（ ） 。该_indentation_是一个整数相乘与广泛的文档标准的缩进，导致该段的实际缩进。

**See also** [indent](qtextblockformat.html#indent)（）和[QTextDocument.indentWidth](qtextdocument.html#indentWidth-prop)（ ） 。

```
QTextBlockFormat.setLeftMargin (self, float margin)
```

设置段落的左_margin_。压痕可分别与应用[setIndent](qtextblockformat.html#setIndent)（ ） 。

**See also** [leftMargin](qtextblockformat.html#leftMargin)（ ）[setRightMargin](qtextblockformat.html#setRightMargin)（ ）[setTopMargin](qtextblockformat.html#setTopMargin)（）和[setBottomMargin](qtextblockformat.html#setBottomMargin)（ ） 。

```
QTextBlockFormat.setLineHeight (self, float height, int heightType)
```

设置行高的段落，通过给定的值_height_这是依赖于_heightType_在由所述的方式[LineHeightTypes](qtextblockformat.html#LineHeightTypes-enum)枚举。

此功能被引入Qt的4.8 。

**See also** [LineHeightTypes](qtextblockformat.html#LineHeightTypes-enum)，[lineHeight](qtextblockformat.html#lineHeight)（）和[lineHeightType](qtextblockformat.html#lineHeightType)（ ） 。

```
QTextBlockFormat.setNonBreakableLines (self, bool b)
```

If _b_诚然，在该段线路被视为非易碎，否则他们是易碎的。

**See also** [nonBreakableLines](qtextblockformat.html#nonBreakableLines)（ ） 。

```
QTextBlockFormat.setPageBreakPolicy (self, QTextFormat.PageBreakFlags flags)
```

设置为段落分页政策_policy_。

这个函数中引入了Qt 4.2中。

**See also** [pageBreakPolicy](qtextblockformat.html#pageBreakPolicy)（ ） 。

```
QTextBlockFormat.setRightMargin (self, float margin)
```

设置段落的权利_margin_。

**See also** [rightMargin](qtextblockformat.html#rightMargin)（ ）[setLeftMargin](qtextblockformat.html#setLeftMargin)（ ）[setTopMargin](qtextblockformat.html#setTopMargin)（）和[setBottomMargin](qtextblockformat.html#setBottomMargin)（ ） 。

```
QTextBlockFormat.setTabPositions (self, list-of-QTextOption.Tab tabs)
```

设置文本块的制表符位置，以那些由指定的_tabs_。

此功能被引入Qt的4.4 。

**See also** [tabPositions](qtextblockformat.html#tabPositions)（ ） 。

```
QTextBlockFormat.setTextIndent (self, float margin)
```

设置_indent_对于在块中的第一行。这允许一个段落的第一行缩进不同的其他线，提高文字的可读性。

**See also** [textIndent](qtextblockformat.html#textIndent)（ ）[setLeftMargin](qtextblockformat.html#setLeftMargin)（ ）[setRightMargin](qtextblockformat.html#setRightMargin)（ ）[setTopMargin](qtextblockformat.html#setTopMargin)（）和[setBottomMargin](qtextblockformat.html#setBottomMargin)（ ） 。

```
QTextBlockFormat.setTopMargin (self, float margin)
```

设置段落的顶部_margin_。

**See also** [topMargin](qtextblockformat.html#topMargin)（ ）[setBottomMargin](qtextblockformat.html#setBottomMargin)（ ）[setLeftMargin](qtextblockformat.html#setLeftMargin)（）和[setRightMargin](qtextblockformat.html#setRightMargin)（ ） 。

```
list-of-QTextOption.Tab QTextBlockFormat.tabPositions (self)
```

返回的文本块中定义的选项卡位置的列表。

此功能被引入Qt的4.4 。

**See also** [setTabPositions](qtextblockformat.html#setTabPositions)（ ） 。

```
float QTextBlockFormat.textIndent (self)
```

返回段落的文本缩进。

**See also** [setTextIndent](qtextblockformat.html#setTextIndent)（ ） 。

```
float QTextBlockFormat.topMargin (self)
```

返回段的上边界。

**See also** [setTopMargin](qtextblockformat.html#setTopMargin)（）和[bottomMargin](qtextblockformat.html#bottomMargin)（ ） 。