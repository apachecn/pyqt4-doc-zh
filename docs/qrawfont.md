# QRawFont Class Reference

## [[QtGui](index.htm) module]

该QRawFont类提供了访问字体的单个物理实例。[More...](#details)

### Types

*   `enum AntialiasingType { PixelAntialiasing, SubPixelAntialiasing }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QString fileName, float pixelSize, QFont.HintingPreference hintingPreference = QFont.PreferDefaultHinting)`
*   `__init__ (self, QByteArray fontData, float pixelSize, QFont.HintingPreference hintingPreference = QFont.PreferDefaultHinting)`
*   `__init__ (self, QRawFont other)`
*   `list-of-QPointF advancesForGlyphIndexes (self, list-of-int glyphIndexes)`
*   `QImage alphaMapForGlyph (self, int glyphIndex, AntialiasingType antialiasingType = QRawFont.SubPixelAntialiasing, QTransform transform = QTransform())`
*   `float ascent (self)`
*   `float averageCharWidth (self)`
*   `float descent (self)`
*   `QString familyName (self)`
*   `QByteArray fontTable (self, str tagName)`
*   `list-of-int glyphIndexesForString (self, QString text)`
*   `QFont.HintingPreference hintingPreference (self)`
*   `bool isValid (self)`
*   `float leading (self)`
*   `loadFromData (self, QByteArray fontData, float pixelSize, QFont.HintingPreference hintingPreference)`
*   `loadFromFile (self, QString fileName, float pixelSize, QFont.HintingPreference hintingPreference)`
*   `float maxCharWidth (self)`
*   `QPainterPath pathForGlyph (self, int glyphIndex)`
*   `float pixelSize (self)`
*   `setPixelSize (self, float pixelSize)`
*   `QFont.Style style (self)`
*   `QString styleName (self)`
*   `list-of-QFontDatabase.WritingSystem supportedWritingSystems (self)`
*   `bool supportsCharacter (self, int ucs4)`
*   `bool supportsCharacter (self, QChar character)`
*   `float unitsPerEm (self)`
*   `int weight (self)`
*   `float xHeight (self)`

### Static Methods

*   `QRawFont fromFont (QFont font, QFontDatabase.WritingSystem writingSystem = QFontDatabase.Any)`

### Special Methods

*   `bool __eq__ (self, QRawFont other)`
*   `bool __ne__ (self, QRawFont other)`

* * *

## Detailed Description

该QRawFont类提供了访问字体的单个物理实例。

**Note:**QRawFont是一个低级别的类。对于大多数用途[QFont](qfont.html)是一个比较合适的类。

最常见的是，在用户界面中显示文本时，确切的字体用于呈现字符在某种程度上是未知的。这可能是有几个原因的情况：例如，在实际的物理存在于目标系统上的字体可能会不期而至的开发商，或者文本可以包含用户选择的样式，尺寸或书写系统不支持所选择的字体的代码。

因此， Qt的[QFont](qfont.html)类真正代表字体的查询。当文本被解释， Qt会尽力的文字查询匹配，但根据的支持，不同的字体可用于在幕后。

对于大多数用例来说，这既是预期的和必要的，因为它最大限度地减少文本的用户界面是不可显示的可能性。在某些情况下，但是，更直接地控制这个过程可能是有用的。正是由于这些用例的QRawFont类存在。

一个QRawFont对象代表一个给定的字体在一个给定的像素大小单个物理实例。即在典型的情况下，它代表一组TrueType或OpenType字体表，并使用用户指定的像素大小来度量转换为逻辑像素单位。它可与组合使用[QGlyphRun](qglyphrun.html)类绘制特定的字形索引在特定位置，也有访问到物理字体的一些相关数据。

QRawFont只提供了主要的字体技术支持： GDI和DirectWrite在Windows平台上，[FreeType](index.htm#freetype)Symbian和Linux平台和CoreText在Mac OS X。对于其他字体后端上，这些API将被禁用。

QRawFont可以以多种方式进行构造：

*   It can be constructed by calling QTextLayout.glyphs() or QTextFragment.glyphs(). The returned QGlyphs objects will contain QRawFont objects which represent the actual fonts used to render each portion of the text.
*   It can be constructed by passing a [QFont](qfont.html) object to [QRawFont.fromFont](qrawfont.html#fromFont)(). The function will return a QRawFont object representing the font that will be selected as response to the [QFont](qfont.html) query and the selected writing system.
*   It can be constructed by passing a file name or [QByteArray](qbytearray.html) directly to the QRawFont constructor, or by calling [loadFromFile](qrawfont.html#loadFromFile)() or [loadFromData](qrawfont.html#loadFromData)(). In this case, the font will not be registered in [QFontDatabase](qfontdatabase.html), and it will not be available as part of regular font selection.

QRawFont被认为是本地在其构造（或者使用构造函数的线程，或致电[loadFromData](qrawfont.html#loadFromData)（）或[loadFromFile](qrawfont.html#loadFromFile)（））。该QRawFont不能移动到一个不同的线程，但会在有问题的线程被创建。

**Note:**对于缓存字形索引和字体选项的静态文本，以避免重塑和relayouting在应用程序的内部循环的要求，更好的选择是[QStaticText](qstatictext.html)类，因为它优化高速缓存的存储器成本并且还提供了额外的加速绘图引擎的特定高速缓存的可能性。

* * *

## Type Documentation

```
QRawFont.AntialiasingType
```

这个枚举变量代表了不同方式的字形可以在函数被光栅化[alphaMapForGlyph](qrawfont.html#alphaMapForGlyph)（ ） 。

| Constant | Value | Description |
| --- | --- | --- |
| `QRawFont.PixelAntialiasing` | `0` | 通过测量全像素形状的复盖范围将栅格化。返回的图像中包含的每个像素的基础上，字形形状的复盖范围的alpha值。 |
| `QRawFont.SubPixelAntialiasing` | `1` | 通过测量各子像素的显示，对于每个各像素的红色，绿色和蓝色分量的返回一个单独的α值将栅格化。 |

* * *

## Method Documentation

```
QRawFont.__init__ (self)
```

构造一个无效的[QRawFont](qrawfont.html)。

```
QRawFont.__init__ (self, QString fileName, float pixelSize, QFont.HintingPreference hintingPreference = QFont.PreferDefaultHinting)
```

构造一个[QRawFont](qrawfont.html)表示包含由所引用的文件中的字体_fileName_对于通过给定的大小（以像素为单位）_pixelSize_，并使用所指定的提示的优先级_hintingPreference_。

**Note:**引用的文件必须包含一个TrueType或OpenType字体。

```
QRawFont.__init__ (self, QByteArray fontData, float pixelSize, QFont.HintingPreference hintingPreference = QFont.PreferDefaultHinting)
```

构造一个[QRawFont](qrawfont.html)表示包含在所提供的字体_fontData_对于通过给定的大小（以像素为单位）_pixelSize_，并使用所指定的提示的优先级_hintingPreference_。

**Note:**该数据必须包含TrueType或OpenType字体。

```
QRawFont.__init__ (self, QRawFont other)
```

创建[QRawFont](qrawfont.html)这是一个拷贝_other_。

```
list-of-QPointF QRawFont.advancesForGlyphIndexes (self, list-of-int glyphIndexes)
```

返回[QRawFont](qrawfont.html)的前进对每个_glyphIndexes_以像素为单位。该贷款给从给定字形的位置到下一个字形应绘制，使其看起来好像两个字形unspaced的距离。

**See also** [QTextLine.horizontalAdvance](qtextline.html#horizontalAdvance)（）和[QFontMetricsF.width](qfontmetricsf.html#width)（ ） 。

```
QImage QRawFont.alphaMapForGlyph (self, int glyphIndex, AntialiasingType antialiasingType = QRawFont.SubPixelAntialiasing, QTransform transform = QTransform())
```

[](qimage.html)

[该函数返回字形的光栅化图像在给定的_glyphIndex_在底层的字体，用_transform_规定。如果](qimage.html)[QRawFont](qrawfont.html)是无效的，该函数将返回一个无效[QImage](qimage.html)。

If _antialiasingType_被设置为[QRawFont.SubPixelAntialiasing](qrawfont.html#AntialiasingType-enum)，然后将生成的图像将在[QImage.Format_RGB32](qimage.html#Format-enum)和每个像素的RGB值，将表示在该字形的光栅化的像素的子像素的不透明度。否则，图像将在格式[QImage.Format_Indexed8](qimage.html#Format-enum)和每个像素将包含像素的光栅化的不透明度。

**See also** [pathForGlyph](qrawfont.html#pathForGlyph)（）和[QPainter.drawGlyphRun](qpainter.html#drawGlyphRun)（ ） 。

```
float QRawFont.ascent (self)
```

返回此东昇[QRawFont](qrawfont.html)以像素为单位。

**See also** [QFontMetricsF.ascent](qfontmetricsf.html#ascent)（ ） 。

```
float QRawFont.averageCharWidth (self)
```

返回此字符的平均宽度[QRawFont](qrawfont.html)以像素为单位。

**See also** [QFontMetricsF.averageCharWidth](qfontmetricsf.html#averageCharWidth)（ ） 。

```
float QRawFont.descent (self)
```

返回此下降[QRawFont](qrawfont.html)以像素为单位。

**See also** [QFontMetricsF.descent](qfontmetricsf.html#descent)（ ） 。

```
QString QRawFont.familyName (self)
```

返回此姓氏[QRawFont](qrawfont.html)。

```
QByteArray QRawFont.fontTable (self, str tagName)
```

[

检索评为SFNT表_tagName_从底层的物理字体，或者一个空字节数组，如果没有这样的表被发现。返回的字体表中的字节顺序是大端，像SFNT格式指定。该_tagName_必须为四个字符，并应在当前平台的默认字节顺序进行格式化。

](qbytearray.html)

```
QRawFont QRawFont.fromFont (QFont font, QFontDatabase.WritingSystem writingSystem = QFontDatabase.Any)
```

[

取基于物理表示_font_查询。返回的物理字体是由Qt的首选，以在选定的显示文本的字体_writingSystem_。

```
list-of-int QRawFont.glyphIndexesForString (self, QString text)
```

unicode的点串由下式给出转换_text_使用CMAP表的基本字体到字形索引，并返回包含结果的载体。

](qrawfont.html)

[需要注意的是，在存在于该字体的其他表影响文本的成形的情况下，返回的字形索引将不正确地表示该文本的渲染。为了得到正确的形文字，可以使用](qrawfont.html)[QTextLayout](qtextlayout.html)布置和形状的文本，然后调用QTextLayout.glyphs （ ）来获取一套字形索引列表和[QRawFont](qrawfont.html)对。

**See also** [advancesForGlyphIndexes](qrawfont.html#advancesForGlyphIndexes)（ ）[glyphIndexesForChars](qrawfont.html#glyphIndexesForChars)（ ）[QGlyphRun](qglyphrun.html)，[QTextLayout.glyphRuns](qtextlayout.html#glyphRuns)（）和[QTextFragment.glyphRuns](qtextfragment.html#glyphRuns)（ ） 。

```
QFont.HintingPreference QRawFont.hintingPreference (self)
```

[](qfont.html#HintingPreference-enum)

[返回用于构造这个暗示偏好](qfont.html#HintingPreference-enum)[QRawFont](qrawfont.html)。

**See also** [QFont.hintingPreference](qfont.html#hintingPreference)（ ） 。

```
bool QRawFont.isValid (self)
```

返回True如果[QRawFont](qrawfont.html)是有效的，否则为False。

```
float QRawFont.leading (self)
```

返回此领先[QRawFont](qrawfont.html)以像素为单位。

**See also** [QFontMetricsF.leading](qfontmetricsf.html#leading)（ ） 。

```
QRawFont.loadFromData (self, QByteArray fontData, float pixelSize, QFont.HintingPreference hintingPreference)
```

替换当前[QRawFont](qrawfont.html)与包含在所提供的字体_fontData_对于通过给定的大小（以像素为单位）_pixelSize_，并使用所指定的提示的优先级_hintingPreference_。

该_fontData_必须包含TrueType或OpenType字体。

**See also** [loadFromFile](qrawfont.html#loadFromFile)（ ） 。

```
QRawFont.loadFromFile (self, QString fileName, float pixelSize, QFont.HintingPreference hintingPreference)
```

替换当前[QRawFont](qrawfont.html)由所引用的文件中的内容_fileName_对于通过给定的大小（以像素为单位）_pixelSize_，并使用所指定的提示的优先级_hintingPreference_。

该文件必须引用一个TrueType或OpenType字体。

**See also** [loadFromData](qrawfont.html#loadFromData)（ ） 。

```
float QRawFont.maxCharWidth (self)
```

返回最宽的字符的字体的宽度。

**See also** [QFontMetricsF.maxWidth](qfontmetricsf.html#maxWidth)（ ） 。

```
QPainterPath QRawFont.pathForGlyph (self, int glyphIndex)
```

[](qpainterpath.html)

[这个函数返回该字形的形状在给定的_glyphIndex_在底层的字体，如果](qpainterpath.html)[QRawFont](qrawfont.html)是有效的。否则，它返回一个空[QPainterPath](qpainterpath.html)。

返回的字形将始终unhinted 。

**See also** [alphaMapForGlyph](qrawfont.html#alphaMapForGlyph)（）和[QPainterPath.addText](qpainterpath.html#addText)（ ） 。

```
float QRawFont.pixelSize (self)
```

返回此像素大小设置[QRawFont](qrawfont.html)。像素大小会影响字形光栅，通过回字形的大小[pathForGlyph](qrawfont.html#pathForGlyph)（） ，并用于内部度量转换设计单位逻辑像素单位。

**See also** [setPixelSize](qrawfont.html#setPixelSize)（ ） 。

```
QRawFont.setPixelSize (self, float pixelSize)
```

设置像素大小与该字体应该被渲染到_pixelSize_。

**See also** [pixelSize](qrawfont.html#pixelSize)（ ） 。

```
QFont.Style QRawFont.style (self)
```

[](qfont.html#Style-enum)

[返回此风格](qfont.html#Style-enum)[QRawFont](qrawfont.html)。

**See also** [QFont.style](qfont.html#style)（ ） 。

```
QString QRawFont.styleName (self)
```

返回此样式名[QRawFont](qrawfont.html)。

**See also** [QFont.styleName](qfont.html#styleName)（ ） 。

```
list-of-QFontDatabase.WritingSystem QRawFont.supportedWritingSystems (self)
```

返回根据设计师对字体支持的书写系统列表中的字体文件中提供的信息。请注意，这并不能保证在字体特定的Unicode点支撑。您可以使用[supportsCharacter](qrawfont.html#supportsCharacter)（ ）来检查一个单一的，特定的字符支持。

**Note:**该列表是基于字体的OS / 2表设置，需要这样一个表存在于底层的字体文件Unicode范围和代码页范围内确定。

**See also** [supportsCharacter](qrawfont.html#supportsCharacter)（ ） 。

```
bool QRawFont.supportsCharacter (self, int ucs4)
```

如果字体有对应于给定的字形，则返回True_character_。

**See also** [supportedWritingSystems](qrawfont.html#supportedWritingSystems)（ ） 。

```
bool QRawFont.supportsCharacter (self, QChar character)
```

这是一个重载函数。

如果字体有对应于UCS- 4编码的字符的字形，则返回True_ucs4_。

**See also** [supportedWritingSystems](qrawfont.html#supportedWritingSystems)（ ） 。

```
float QRawFont.unitsPerEm (self)
```

返回设计单位的数量界定em方形这个的宽度和高度[QRawFont](qrawfont.html)。此值与像素尺寸转换设计度量时，以像素单位使用的，作为内部度量在设计单位指定与像素大小给出1烯的大小（像素）。

**See also** [pixelSize](qrawfont.html#pixelSize)（）和[setPixelSize](qrawfont.html#setPixelSize)（ ） 。

```
int QRawFont.weight (self)
```

返回此重量[QRawFont](qrawfont.html)。

**See also** [QFont.weight](qfont.html#weight)（ ） 。

```
float QRawFont.xHeight (self)
```

返回此的xHeight[QRawFont](qrawfont.html)以像素为单位。

**See also** [QFontMetricsF.xHeight](qfontmetricsf.html#xHeight)（ ） 。

```
bool QRawFont.__eq__ (self, QRawFont other)
```

```
bool QRawFont.__ne__ (self, QRawFont other)
```