# QTextFormat Class Reference

## [[QtGui](index.htm) module]

该QTextFormat类提供的格式化信息的[QTextDocument](qtextdocument.html)。[More...](#details)

通过继承[QTextBlockFormat](qtextblockformat.html)，[QTextCharFormat](qtextcharformat.html)，[QTextFrameFormat](qtextframeformat.html)和[QTextListFormat](qtextlistformat.html)。

### Types

*   `enum FormatType { InvalidFormat, BlockFormat, CharFormat, ListFormat, ..., UserFormat }`
*   `enum ObjectTypes { NoObject, ImageObject, TableObject, TableCellObject, UserObject }`
*   `enum PageBreakFlag { PageBreak_Auto, PageBreak_AlwaysBefore, PageBreak_AlwaysAfter }`
*   `class **[PageBreakFlags](index.htm)**`
*   `enum Property { ObjectIndex, CssFloat, LayoutDirection, OutlinePen, ..., UserProperty }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, int type)`
*   `__init__ (self, QTextFormat rhs)`
*   `__init__ (self, QVariant variant)`
*   `QBrush background (self)`
*   `bool boolProperty (self, int propertyId)`
*   `QBrush brushProperty (self, int propertyId)`
*   `clearBackground (self)`
*   `clearForeground (self)`
*   `clearProperty (self, int propertyId)`
*   `QColor colorProperty (self, int propertyId)`
*   `float doubleProperty (self, int propertyId)`
*   `QBrush foreground (self)`
*   `bool hasProperty (self, int propertyId)`
*   `int intProperty (self, int propertyId)`
*   `bool isBlockFormat (self)`
*   `bool isCharFormat (self)`
*   `bool isFrameFormat (self)`
*   `bool isImageFormat (self)`
*   `bool isListFormat (self)`
*   `bool isTableCellFormat (self)`
*   `bool isTableFormat (self)`
*   `bool isValid (self)`
*   `Qt.LayoutDirection layoutDirection (self)`
*   `QTextLength lengthProperty (self, int propertyId)`
*   `list-of-QTextLength lengthVectorProperty (self, int propertyId)`
*   `merge (self, QTextFormat other)`
*   `int objectIndex (self)`
*   `int objectType (self)`
*   `QPen penProperty (self, int propertyId)`
*   `dict-of-int-QVariant properties (self)`
*   `QVariant property (self, int propertyId)`
*   `int propertyCount (self)`
*   `setBackground (self, QBrush brush)`
*   `setForeground (self, QBrush brush)`
*   `setLayoutDirection (self, Qt.LayoutDirection direction)`
*   `setObjectIndex (self, int object)`
*   `setObjectType (self, int atype)`
*   `setProperty (self, int propertyId, QVariant value)`
*   `setProperty (self, int propertyId, list-of-QTextLength lengths)`
*   `QString stringProperty (self, int propertyId)`
*   `QTextBlockFormat toBlockFormat (self)`
*   `QTextCharFormat toCharFormat (self)`
*   `QTextFrameFormat toFrameFormat (self)`
*   `QTextImageFormat toImageFormat (self)`
*   `QTextListFormat toListFormat (self)`
*   `QTextTableCellFormat toTableCellFormat (self)`
*   `QTextTableFormat toTableFormat (self)`
*   `int type (self)`

### Special Methods

*   `bool __eq__ (self, QTextFormat rhs)`
*   `bool __ne__ (self, QTextFormat rhs)`

* * *

## Detailed Description

该QTextFormat类提供的格式化信息的[QTextDocument](qtextdocument.html)。

一个QTextFormat是用于描述一个部分的格式泛型类[QTextDocument](qtextdocument.html)。派生类[QTextCharFormat](qtextcharformat.html)，[QTextBlockFormat](qtextblockformat.html)，[QTextListFormat](qtextlistformat.html)和[QTextTableFormat](qtexttableformat.html)通常比较有益的，并且描述了应用到文档的特定部分的格式。

的一种格式有`FormatType`它指定了各种文本项目也可以格式化;如文本块，列表，表格等的一种格式还具有各种属性（一些具体的特定格式类型） ，所描述的属性枚举。每个属性都有相应的属性。

格式类型由下式给出[type](qtextformat.html#type)（） ，并且格式可以与测试[isCharFormat](qtextformat.html#isCharFormat)（ ）[isBlockFormat](qtextformat.html#isBlockFormat)（ ）[isListFormat](qtextformat.html#isListFormat)（ ）[isTableFormat](qtextformat.html#isTableFormat)（ ）[isFrameFormat](qtextformat.html#isFrameFormat)（）和[isImageFormat](qtextformat.html#isImageFormat)（ ） 。如果类型是确定的，它可以被检索以[toCharFormat](qtextformat.html#toCharFormat)（ ）[toBlockFormat](qtextformat.html#toBlockFormat)（ ）[toListFormat](qtextformat.html#toListFormat)（ ）[toTableFormat](qtextformat.html#toTableFormat)（ ）[toFrameFormat](qtextformat.html#toFrameFormat)（）和[toImageFormat](qtextformat.html#toImageFormat)（ ） 。

的一种格式的属性可以与设置[setProperty](qtextformat.html#setProperty)（）函数，并检索与[boolProperty](qtextformat.html#boolProperty)（ ）[intProperty](qtextformat.html#intProperty)（ ）[doubleProperty](qtextformat.html#doubleProperty)（）和[stringProperty](qtextformat.html#stringProperty)（ ） （如适用） 。所有的格式使用的属性ID可以检索到allPropertyIds （ ） 。一种格式可以被合并到另一个使用[merge](qtextformat.html#merge)（ ） 。

的一种格式的对象的索引可以被设置[setObjectIndex](qtextformat.html#setObjectIndex)（） ，并检索与[objectIndex](qtextformat.html#objectIndex)（ ） 。这些方法可用于编排格式，相关联[QTextObject](qtextobject.html)。它是用来表示文档内列出，框架和表格。

* * *

## Type Documentation

```
QTextFormat.FormatType
```

这个枚举变量描述文本项目的[QTextFormat](qtextformat.html)对象被格式化。

| Constant | Value | Description |
| --- | --- | --- |
| `QTextFormat.InvalidFormat` | `-1` | 由默认的构造函数创建一个无效的格式 |
| `QTextFormat.BlockFormat` | `1` | 对象格式化文本块 |
| `QTextFormat.CharFormat` | `2` | 对象格式的单个字符 |
| `QTextFormat.ListFormat` | `3` | 对象格式列表 |
| `QTextFormat.TableFormat` | `4` | 对象格式的表 |
| `QTextFormat.FrameFormat` | `5` | 对象格式的帧 |
| `QTextFormat.UserFormat` | `100` |   |

**See also** [QTextCharFormat](qtextcharformat.html)，[QTextBlockFormat](qtextblockformat.html)，[QTextListFormat](qtextlistformat.html)，[QTextTableFormat](qtexttableformat.html)和[type](qtextformat.html#type)（ ） 。

```
QTextFormat.ObjectTypes
```

这个枚举说明是什么样的[QTextObject](qtextobject.html)此格式是与相关联。

| Constant | Value | Description |
| --- | --- | --- |
| `QTextFormat.NoObject` | `0` |   |
| `QTextFormat.ImageObject` | `1` |   |
| `QTextFormat.TableObject` | `2` |   |
| `QTextFormat.TableCellObject` | `3` |   |
| `QTextFormat.UserObject` | `0x1000` | 第一对象，该对象可以用于特定应用的目的。 |

**See also** [QTextObject](qtextobject.html)，[QTextTable](qtexttable.html)和[QTextObject.format](qtextobject.html#format)（ ） 。

```
QTextFormat.PageBreakFlag
```

这个枚举变量描述了如何打印网页时断进行。它映射到相应的CSS属性。

| Constant | Value | Description |
| --- | --- | --- |
| `QTextFormat.PageBreak_Auto` | `0` | 分页符是根据当前页面上的可用空间自动确定 |
| `QTextFormat.PageBreak_AlwaysBefore` | `0x001` | 该页面段落/表之前被破 |
| `QTextFormat.PageBreak_AlwaysAfter` | `0x010` | 一个新的页面段落/表后总是启动 |

这个枚举被引入或修改的Qt 4.2 。

该PageBreakFlags类型是一个typedef为[QFlags](index.htm)\u003cPageBreakFlag\u003e 。它存储PageBreakFlag值的或组合。

**See also** [QTextBlockFormat.pageBreakPolicy](qtextblockformat.html#pageBreakPolicy)（ ）[QTextFrameFormat.pageBreakPolicy](qtextframeformat.html#pageBreakPolicy)（）和[PageBreakPolicy](qtextformat.html#Property-enum)。

```
QTextFormat.Property
```

这个枚举变量描述了不同属性的格式可以有。

| Constant | Value | Description |
| --- | --- | --- |
| `QTextFormat.ObjectIndex` | `0x0` | 格式化的对象的索引。看[objectIndex](qtextformat.html#objectIndex)（ ） 。 |

段落和字符属性

| Constant | Value | Description |
| --- | --- | --- |
| `QTextFormat.CssFloat` | `0x0800` | 如何一帧位于相对于周围文本 |
| `QTextFormat.LayoutDirection` | `0x0801` | 本文档中的文本的布局方向（[Qt.LayoutDirection](qt.html#LayoutDirection-enum)） 。 |
| `QTextFormat.OutlinePen` | `0x810` |   |
| `QTextFormat.ForegroundBrush` | `0x821` |   |
| `QTextFormat.BackgroundBrush` | `0x820` |   |
| `QTextFormat.BackgroundImageUrl` | `0x823` |   |

段落属性

| Constant | Value | Description |
| --- | --- | --- |
| `QTextFormat.BlockAlignment` | `0x1010` |   |
| `QTextFormat.BlockTopMargin` | `0x1030` |   |
| `QTextFormat.BlockBottomMargin` | `0x1031` |   |
| `QTextFormat.BlockLeftMargin` | `0x1032` |   |
| `QTextFormat.BlockRightMargin` | `0x1033` |   |
| `QTextFormat.TextIndent` | `0x1034` |   |
| `QTextFormat.TabPositions` | `0x1035` | 指定标籤的位置。该选项卡的位置是结构[QTextOption.Tab](index.htm)它们被存储在一个[QList](index.htm)（在内部，在[QList](index.htm)\u003c[QVariant](qvariant.html)\u003e ） 。 |
| `QTextFormat.BlockIndent` | `0x1040` |   |
| `QTextFormat.LineHeight` | `0x1048` |   |
| `QTextFormat.LineHeightType` | `0x1049` |   |
| `QTextFormat.BlockNonBreakableLines` | `0x1050` |   |
| `QTextFormat.BlockTrailingHorizontalRulerWidth` | `0x1060` | 水平尺元素的宽度。 |

字符属性

| Constant | Value | Description |
| --- | --- | --- |
| `QTextFormat.FontFamily` | `0x2000` |   |
| `QTextFormat.FontPointSize` | `0x2001` |   |
| `QTextFormat.FontPixelSize` | `0x2009` |   |
| `QTextFormat.FontSizeAdjustment` | `0x2002` | 指定给使用FontPointSize或FontPixelSize已经设置字号大小的变化。 |
| `QTextFormat.FontFixedPitch` | `0x2008` |   |
| `QTextFormat.FontWeight` | `0x2003` |   |
| `QTextFormat.FontItalic` | `0x2004` |   |
| `QTextFormat.FontUnderline` | `0x2005` | _This property has been deprecated._使用QTextFormat.TextUnderlineStyle代替。 |
| `QTextFormat.FontOverline` | `0x2006` |   |
| `QTextFormat.FontStrikeOut` | `0x2007` |   |
| `QTextFormat.FontCapitalization` | `FirstFontProperty` | 指定大写类型将要被施加到文本。 |
| `QTextFormat.FontLetterSpacing` | `0x1FE1` | 改变字体中的各个字母之间的默认间距。该值指定百分比，100为默认值。 |
| `QTextFormat.FontWordSpacing` | `0x1FE2` | 改变个别单词之间的默认间距。正值增加了字间距由相应的像素;负值减小的间距。 |
| `QTextFormat.FontStyleHint` | `0x1FE3` | 对应于[QFont.StyleHint](qfont.html#StyleHint-enum)属性 |
| `QTextFormat.FontStyleStrategy` | `0x1FE4` | 对应于[QFont.StyleStrategy](qfont.html#StyleStrategy-enum)属性 |
| `QTextFormat.FontKerning` | `0x1FE5` | 指定字体是否已经字距调整开启。 |
| `QTextFormat.FontHintingPreference` | `0x1FE6` | 控制根据的值的提示的使用[QFont.HintingPreference](qfont.html#HintingPreference-enum)枚举。 |
| `QTextFormat.TextUnderlineColor` | `0x2010` |   |
| `QTextFormat.TextVerticalAlignment` | `0x2021` |   |
| `QTextFormat.TextOutline` | `0x2022` |   |
| `QTextFormat.TextUnderlineStyle` | `0x2023` |   |
| `QTextFormat.TextToolTip` | `0x2024` | 指定（可选）刀尖要显示的文本片段。 |
| `QTextFormat.IsAnchor` | `0x2030` |   |
| `QTextFormat.AnchorHref` | `0x2031` |   |
| `QTextFormat.AnchorName` | `0x2032` |   |
| `QTextFormat.ObjectType` | `0x2f00` |   |

列表属性

| Constant | Value | Description |
| --- | --- | --- |
| `QTextFormat.ListStyle` | `0x3000` | 指定用于在一个列表中的项目的样式，由值描述[QTextListFormat.Style](qtextlistformat.html#Style-enum)枚举。 |
| `QTextFormat.ListIndent` | `0x3001` | 指定缩进用于列表的量。 |
| `QTextFormat.ListNumberPrefix` | `0x3002` | 定义了被前置到项目编号以数字列表的文本。 |
| `QTextFormat.ListNumberSuffix` | `0x3003` | 定义了附加到项目编号以数字列表的文本。 |

表和框架属性

| Constant | Value | Description |
| --- | --- | --- |
| `QTextFormat.FrameBorder` | `0x4000` |   |
| `QTextFormat.FrameBorderBrush` | `0x4009` |   |
| `QTextFormat.FrameBorderStyle` | `0x4010` | 请参阅[BorderStyle](qtextframeformat.html#BorderStyle-enum)枚举。 |
| `QTextFormat.FrameBottomMargin` | `0x4006` |   |
| `QTextFormat.FrameHeight` | `0x4004` |   |
| `QTextFormat.FrameLeftMargin` | `0x4007` |   |
| `QTextFormat.FrameMargin` | `0x4001` |   |
| `QTextFormat.FramePadding` | `0x4002` |   |
| `QTextFormat.FrameRightMargin` | `0x4008` |   |
| `QTextFormat.FrameTopMargin` | `0x4005` |   |
| `QTextFormat.FrameWidth` | `0x4003` |   |
| `QTextFormat.TableCellSpacing` | `0x4102` |   |
| `QTextFormat.TableCellPadding` | `0x4103` |   |
| `QTextFormat.TableColumns` | `0x4100` |   |
| `QTextFormat.TableColumnWidthConstraints` | `0x4101` |   |
| `QTextFormat.TableHeaderRowCount` | `0x4104` |   |

表单元格属性

| Constant | Value |
| --- | --- |
| `QTextFormat.TableCellRowSpan` | `0x4810` |
| `QTextFormat.TableCellColumnSpan` | `0x4811` |
| `QTextFormat.TableCellLeftPadding` | `0x4814` |
| `QTextFormat.TableCellRightPadding` | `0x4815` |
| `QTextFormat.TableCellTopPadding` | `0x4812` |
| `QTextFormat.TableCellBottomPadding` | `0x4813` |

图像性能

| Constant | Value |
| --- | --- |
| `QTextFormat.ImageName` | `0x5000` |
| `QTextFormat.ImageWidth` | `0x5010` |
| `QTextFormat.ImageHeight` | `0x5011` |

选择属性

| Constant | Value | Description |
| --- | --- | --- |
| `QTextFormat.FullWidthSelection` | `0x06000` | 当在选择的characterFormat设置，文本的整个宽度上会显示所选的。 |

分页符的属性

| Constant | Value | Description |
| --- | --- | --- |
| `QTextFormat.PageBreakPolicy` | `0x7000` | 指定如何页面被打破。请参阅[PageBreakFlag](qtextformat.html#PageBreakFlag-enum)枚举。 |
| `QTextFormat.UserProperty` | `0x100000` |   |

**See also** [property](qtextformat.html#property)（）和[setProperty](qtextformat.html#setProperty)（ ） 。

* * *

## Method Documentation

```
QTextFormat.__init__ (self)
```

创建有一个新的文本格式`InvalidFormat`。

**See also** [FormatType](qtextformat.html#FormatType-enum)。

```
QTextFormat.__init__ (self, int type)
```

创建给定一个新的文本格式_type_。

**See also** [FormatType](qtextformat.html#FormatType-enum)。

```
QTextFormat.__init__ (self, QTextFormat rhs)
```

创建一个具有相同属性的新文本格式_other_文本格式。

```
QTextFormat.__init__ (self, QVariant variant)
```

```
QBrush QTextFormat.background (self)
```

[

返回用于绘制文档的背景的画笔。

](qbrush.html)

[**See also**](qbrush.html) [setBackground](qtextformat.html#setBackground)（ ）[clearBackground](qtextformat.html#clearBackground)（）和[foreground](qtextformat.html#foreground)（ ） 。

```
bool QTextFormat.boolProperty (self, int propertyId)
```

返回由指定的属性值_propertyId_。如果属性是QTextFormat.Bool类型没有，则返回False来代替。

**See also** [setProperty](qtextformat.html#setProperty)（ ）[intProperty](qtextformat.html#intProperty)（ ）[doubleProperty](qtextformat.html#doubleProperty)（ ）[stringProperty](qtextformat.html#stringProperty)（ ）[colorProperty](qtextformat.html#colorProperty)（ ）[lengthProperty](qtextformat.html#lengthProperty)（ ）[lengthVectorProperty](qtextformat.html#lengthVectorProperty)（）和[Property](qtextformat.html#Property-enum)。

```
QBrush QTextFormat.brushProperty (self, int propertyId)
```

[](qbrush.html)

[返回由给定属性的值_propertyId_;如果属性是不](qbrush.html)[QVariant.Brush](qvariant.html#Type-enum)型，[Qt.NoBrush](qt.html#BrushStyle-enum)返回来代替。

**See also** [setProperty](qtextformat.html#setProperty)（ ）[boolProperty](qtextformat.html#boolProperty)（ ）[intProperty](qtextformat.html#intProperty)（ ）[doubleProperty](qtextformat.html#doubleProperty)（ ）[stringProperty](qtextformat.html#stringProperty)（ ）[lengthProperty](qtextformat.html#lengthProperty)（ ）[lengthVectorProperty](qtextformat.html#lengthVectorProperty)（）和[Property](qtextformat.html#Property-enum)。

```
QTextFormat.clearBackground (self)
```

清除用于绘制文档的背景的画笔。默认刷将被使用。

**See also** [background](qtextformat.html#background)（ ）[setBackground](qtextformat.html#setBackground)（）和[clearForeground](qtextformat.html#clearForeground)（ ） 。

```
QTextFormat.clearForeground (self)
```

清除用于绘制文档的前景刷。默认刷将被使用。

**See also** [foreground](qtextformat.html#foreground)（ ）[setForeground](qtextformat.html#setForeground)（）和[clearBackground](qtextformat.html#clearBackground)（ ） 。

```
QTextFormat.clearProperty (self, int propertyId)
```

清除由给定属性的值_propertyId_

**See also** [Property](qtextformat.html#Property-enum)。

```
QColor QTextFormat.colorProperty (self, int propertyId)
```

[](qcolor.html)

[返回由给定属性的值_propertyId_;如果属性是不](qcolor.html)[QVariant.Color](qvariant.html#Type-enum)输入时，将返回一个无效的颜色来代替。

**See also** [setProperty](qtextformat.html#setProperty)（ ）[boolProperty](qtextformat.html#boolProperty)（ ）[intProperty](qtextformat.html#intProperty)（ ）[doubleProperty](qtextformat.html#doubleProperty)（ ）[stringProperty](qtextformat.html#stringProperty)（ ）[lengthProperty](qtextformat.html#lengthProperty)（ ）[lengthVectorProperty](qtextformat.html#lengthVectorProperty)（）和[Property](qtextformat.html#Property-enum)。

```
float QTextFormat.doubleProperty (self, int propertyId)
```

返回由指定的属性值_propertyId_。如果属性是不[QVariant.Double](qvariant.html#Type-enum) or [QMetaType.Float](qmetatype.html#Type-enum)类型，则返回0代替。

**See also** [setProperty](qtextformat.html#setProperty)（ ）[boolProperty](qtextformat.html#boolProperty)（ ）[intProperty](qtextformat.html#intProperty)（ ）[stringProperty](qtextformat.html#stringProperty)（ ）[colorProperty](qtextformat.html#colorProperty)（ ）[lengthProperty](qtextformat.html#lengthProperty)（ ）[lengthVectorProperty](qtextformat.html#lengthVectorProperty)（）和[Property](qtextformat.html#Property-enum)。

```
QBrush QTextFormat.foreground (self)
```

[

返回用于渲染前景的详细信息，如文字，边框轮廓，和表格边框的画笔。

](qbrush.html)

[**See also**](qbrush.html) [setForeground](qtextformat.html#setForeground)（ ）[clearForeground](qtextformat.html#clearForeground)（）和[background](qtextformat.html#background)（ ） 。

```
bool QTextFormat.hasProperty (self, int propertyId)
```

如果文本格式有一个属性与给定的，则返回True_propertyId_否则返回False 。

**See also** [properties](qtextformat.html#properties)（）和[Property](qtextformat.html#Property-enum)。

```
int QTextFormat.intProperty (self, int propertyId)
```

返回由指定的属性值_propertyId_。如果属性是QTextFormat.Integer类型没有，则返回0代替。

**See also** [setProperty](qtextformat.html#setProperty)（ ）[boolProperty](qtextformat.html#boolProperty)（ ）[doubleProperty](qtextformat.html#doubleProperty)（ ）[stringProperty](qtextformat.html#stringProperty)（ ）[colorProperty](qtextformat.html#colorProperty)（ ）[lengthProperty](qtextformat.html#lengthProperty)（ ）[lengthVectorProperty](qtextformat.html#lengthVectorProperty)（）和[Property](qtextformat.html#Property-enum)。

```
bool QTextFormat.isBlockFormat (self)
```

返回True如果文本格式是`BlockFormat`否则返回False 。

```
bool QTextFormat.isCharFormat (self)
```

返回True如果文本格式是`CharFormat`否则返回False 。

```
bool QTextFormat.isFrameFormat (self)
```

返回True如果文本格式是`FrameFormat`否则返回False 。

```
bool QTextFormat.isImageFormat (self)
```

返回True如果文本格式是一种图像格式，否则返回False 。

```
bool QTextFormat.isListFormat (self)
```

返回True如果文本格式是`ListFormat`否则返回False 。

```
bool QTextFormat.isTableCellFormat (self)
```

返回True如果文本格式是`TableCellFormat`否则返回False 。

此功能被引入Qt的4.4 。

```
bool QTextFormat.isTableFormat (self)
```

返回True如果文本格式是`TableFormat`否则返回False 。

```
bool QTextFormat.isValid (self)
```

返回True如果该格式是有效的（即不[InvalidFormat](qtextformat.html#FormatType-enum)），否则返回False 。

```
Qt.LayoutDirection QTextFormat.layoutDirection (self)
```

[

返回文档的布局方向。

](qt.html#LayoutDirection-enum)

[**See also**](qt.html#LayoutDirection-enum) [setLayoutDirection](qtextformat.html#setLayoutDirection)（ ） 。

```
QTextLength QTextFormat.lengthProperty (self, int propertyId)
```

[

返回由给定属性的值_propertyId_。

](qtextlength.html)

[**See also**](qtextlength.html) [setProperty](qtextformat.html#setProperty)（ ）[boolProperty](qtextformat.html#boolProperty)（ ）[intProperty](qtextformat.html#intProperty)（ ）[doubleProperty](qtextformat.html#doubleProperty)（ ）[stringProperty](qtextformat.html#stringProperty)（ ）[colorProperty](qtextformat.html#colorProperty)（ ）[lengthVectorProperty](qtextformat.html#lengthVectorProperty)（）和[Property](qtextformat.html#Property-enum)。

```
list-of-QTextLength QTextFormat.lengthVectorProperty (self, int propertyId)
```

返回由给定属性的值_propertyId_。如果属性是QTextFormat.LengthVector类型没有，则返回空长向量来代替。

**See also** [setProperty](qtextformat.html#setProperty)（ ）[boolProperty](qtextformat.html#boolProperty)（ ）[intProperty](qtextformat.html#intProperty)（ ）[doubleProperty](qtextformat.html#doubleProperty)（ ）[stringProperty](qtextformat.html#stringProperty)（ ）[colorProperty](qtextformat.html#colorProperty)（ ）[lengthProperty](qtextformat.html#lengthProperty)（）和[Property](qtextformat.html#Property-enum)。

```
QTextFormat.merge (self, QTextFormat other)
```

合并的_other_这种格式的格式;那里有冲突_other_格式为准。

```
int QTextFormat.objectIndex (self)
```

返回格式对象的索引，或者-1，如果格式对象是无效的。

**See also** [setObjectIndex](qtextformat.html#setObjectIndex)（ ） 。

```
int QTextFormat.objectType (self)
```

返回文本格式的对象类型。

**See also** [ObjectTypes](qtextformat.html#ObjectTypes-enum)和[setObjectType](qtextformat.html#setObjectType)（ ） 。

```
QPen QTextFormat.penProperty (self, int propertyId)
```

[](qpen.html)

[返回由给定属性的值_propertyId_;如果属性是不](qpen.html)[QVariant.Pen](qvariant.html#Type-enum)型，[Qt.NoPen](qt.html#PenStyle-enum)返回来代替。

**See also** [setProperty](qtextformat.html#setProperty)（ ）[boolProperty](qtextformat.html#boolProperty)（ ）[intProperty](qtextformat.html#intProperty)（ ）[doubleProperty](qtextformat.html#doubleProperty)（ ）[stringProperty](qtextformat.html#stringProperty)（ ）[lengthProperty](qtextformat.html#lengthProperty)（ ）[lengthVectorProperty](qtextformat.html#lengthVectorProperty)（）和[Property](qtextformat.html#Property-enum)。

```
dict-of-int-QVariant QTextFormat.properties (self)
```

返回与此文本格式的所有属性的映射。

```
QVariant QTextFormat.property (self, int propertyId)
```

返回由给定指定的属性_propertyId_。

**See also** [setProperty](qtextformat.html#setProperty)（）和[Property](qtextformat.html#Property-enum)。

```
int QTextFormat.propertyCount (self)
```

返回存储在格式属性的数量。

此功能被引入Qt的4.3 。

```
QTextFormat.setBackground (self, QBrush brush)
```

设置画笔使用到文档的底色漆的_brush_规定。

**See also** [background](qtextformat.html#background)（ ）[clearBackground](qtextformat.html#clearBackground)（）和[setForeground](qtextformat.html#setForeground)（ ） 。

```
QTextFormat.setForeground (self, QBrush brush)
```

设置前景色刷到指定的_brush_。前台刷主要是用来渲染文本。

**See also** [foreground](qtextformat.html#foreground)（ ）[clearForeground](qtextformat.html#clearForeground)（）和[setBackground](qtextformat.html#setBackground)（ ） 。

```
QTextFormat.setLayoutDirection (self, Qt.LayoutDirection direction)
```

设置文档的布局方向的指定的_direction_。

**See also** [layoutDirection](qtextformat.html#layoutDirection)（ ） 。

```
QTextFormat.setObjectIndex (self, int object)
```

设置格式的对象的对象_index_。

**See also** [objectIndex](qtextformat.html#objectIndex)（ ） 。

```
QTextFormat.setObjectType (self, int atype)
```

设置文本格式的对象类型_type_。

**See also** [ObjectTypes](qtextformat.html#ObjectTypes-enum)和[objectType](qtextformat.html#objectType)（ ） 。

```
QTextFormat.setProperty (self, int propertyId, QVariant value)
```

设置由指定的属性_propertyId_为给定的_value_。

**See also** [property](qtextformat.html#property)（）和[Property](qtextformat.html#Property-enum)。

```
QTextFormat.setProperty (self, int propertyId, list-of-QTextLength lengths)
```

设置由给定属性的值_propertyId_至_value_。

**See also** [lengthVectorProperty](qtextformat.html#lengthVectorProperty)（）和[Property](qtextformat.html#Property-enum)。

```
QString QTextFormat.stringProperty (self, int propertyId)
```

返回由给定属性的值_propertyId_;如果属性是不[QVariant.String](qvariant.html#Type-enum)输入时，将返回一个空字符串代替。

**See also** [setProperty](qtextformat.html#setProperty)（ ）[boolProperty](qtextformat.html#boolProperty)（ ）[intProperty](qtextformat.html#intProperty)（ ）[doubleProperty](qtextformat.html#doubleProperty)（ ）[colorProperty](qtextformat.html#colorProperty)（ ）[lengthProperty](qtextformat.html#lengthProperty)（ ）[lengthVectorProperty](qtextformat.html#lengthVectorProperty)（）和[Property](qtextformat.html#Property-enum)。

```
QTextBlockFormat QTextFormat.toBlockFormat (self)
```

[

返回此格式作为块格式。

](qtextblockformat.html)

```
QTextCharFormat QTextFormat.toCharFormat (self)
```

[

返回此格式的字符格式。

](qtextcharformat.html)

```
QTextFrameFormat QTextFormat.toFrameFormat (self)
```

[

返回此格式的帧格式。

](qtextframeformat.html)

```
QTextImageFormat QTextFormat.toImageFormat (self)
```

[

返回此格式的图像格式。

](qtextimageformat.html)

```
QTextListFormat QTextFormat.toListFormat (self)
```

[

返回此格式列表格式。

](qtextlistformat.html)

```
QTextTableCellFormat QTextFormat.toTableCellFormat (self)
```

[

返回此格式的表格单元格的格式。

此功能被引入Qt的4.4 。

](qtexttablecellformat.html)

```
QTextTableFormat QTextFormat.toTableFormat (self)
```

[

返回此格式为表格式。

```
int QTextFormat.type (self)
```

返回此格式的类型。

](qtexttableformat.html)

[**See also**](qtexttableformat.html) [FormatType](qtextformat.html#FormatType-enum)。

```
bool QTextFormat.__eq__ (self, QTextFormat rhs)
```

```
bool QTextFormat.__ne__ (self, QTextFormat rhs)
```