# QFontInfo Class Reference

## [[QtGui](index.htm) module]

该QFontInfo类提供有关字体的常规信息。[More...](#details)

### Methods

*   `__init__ (self, QFont)`
*   `__init__ (self, QFontInfo)`
*   `bool bold (self)`
*   `bool exactMatch (self)`
*   `QString family (self)`
*   `bool fixedPitch (self)`
*   `bool italic (self)`
*   `int pixelSize (self)`
*   `int pointSize (self)`
*   `float pointSizeF (self)`
*   `bool rawMode (self)`
*   `QFont.Style style (self)`
*   `QFont.StyleHint styleHint (self)`
*   `QString styleName (self)`
*   `int weight (self)`

* * *

## Detailed Description

该QFontInfo类提供有关字体的常规信息。

该QFontInfo类提供相同的访问功能[QFont](qfont.html)如[family](qfontinfo.html#family)（ ）[pointSize](qfontinfo.html#pointSize)（ ）[italic](qfontinfo.html#italic)（ ）[weight](qfontinfo.html#weight)（ ）[fixedPitch](qfontinfo.html#fixedPitch)（ ）[styleHint](qfontinfo.html#styleHint)（ ）等，不过，虽然在[QFont](qfont.html)访问函数返回已设置的值，一个QFontInfo对象返回应用到实际将用于绘制文本的字体的值。

例如，当程序要求一个25pt Courier字体的机器上有一个不可扩展的24PT Courier字体上，[QFont](qfont.html)将（通常）使用24PT快递渲染。在这种情况下，[QFont.pointSize](qfont.html#pointSize)（）返回25和[QFontInfo.pointSize](qfontinfo.html#pointSize)（）返回24 。

有三种方法来创建一个QFontInfo对象。

1.  调用QFontInfo构造带[QFont](qfont.html)对于屏幕兼容的字体创建字体信息对象，即字体不能是打印机字体。如果字体是后来改，字体信息对象_not_更新。

    （注：如果您使用的打印机字体返回的值可能是不准确的打印机字体并不总是那么访问最近的屏幕字体时使用打印机字体提供。 ）

2.  [QWidget.fontInfo](qwidget.html#fontInfo)（ ）返回一个Widget的字体的字体信息。这等同于调用QFontInfo （小部件 - \u003e字体（ ） ） 。如果控件的字体是后来改，字体信息对象_not_更新。
3.  [QPainter.fontInfo](qpainter.html#fontInfo)（ ）返回一个画家的当前字体的字体信息。如果画家的字体后来改变，字体信息对象_not_更新。

* * *

## Method Documentation

```
QFontInfo.__init__ (self, QFont)
```

构造一个字体信息对象_font_。

字体必须是屏幕兼容，即在绘制文本时使用的字体[widgets](qwidget.html) or [pixmaps](qpixmap.html)，不[QPicture](qpicture.html) or [QPrinter](qprinter.html)。

字体信息对象持有，在它被创建的时候被传递在构造函数中的字体的信息，并且不更新，如果字体的属性后来改。

使用[QPainter.fontInfo](qpainter.html#fontInfo)（）来绘制时获取字体信息。这将喷漆设备，是不是屏幕兼容上画的时候给出正确的结果也。

```
QFontInfo.__init__ (self, QFontInfo)
```

构造的副本_fi_。

```
bool QFontInfo.bold (self)
```

返回True如果[weight](qfontinfo.html#weight)（ ）将返回一个值大于[QFont.Normal](qfont.html#Weight-enum)否则返回False 。

**See also** [weight](qfontinfo.html#weight)（）和[QFont.bold](qfont.html#bold)（ ） 。

```
bool QFontInfo.exactMatch (self)
```

返回True如果匹配的窗口系统字体是完全一样的字体指定一个，否则返回False 。

**See also** [QFont.exactMatch](qfont.html#exactMatch)（ ） 。

```
QString QFontInfo.family (self)
```

返回匹配窗口系统字体的系列名称。

**See also** [QFont.family](qfont.html#family)（ ） 。

```
bool QFontInfo.fixedPitch (self)
```

返回匹配窗口系统字体的固定摊位价值。

**See also** [QFont.fixedPitch](qfont.html#fixedPitch)（ ） 。

```
bool QFontInfo.italic (self)
```

返回匹配窗口系统字体的斜体价值。

**See also** [QFont.italic](qfont.html#italic)（ ） 。

```
int QFontInfo.pixelSize (self)
```

返回匹配窗口的系统字体的像素大小。

**See also** [QFont.pointSize](qfont.html#pointSize)（ ） 。

```
int QFontInfo.pointSize (self)
```

返回匹配窗口的系统字体的磅值。

**See also** [pointSizeF](qfontinfo.html#pointSizeF)（）和[QFont.pointSize](qfont.html#pointSize)（ ） 。

```
float QFontInfo.pointSizeF (self)
```

返回匹配窗口的系统字体的磅值。

**See also** [QFont.pointSizeF](qfont.html#pointSizeF)（ ） 。

```
bool QFontInfo.rawMode (self)
```

返回True如果字体为原始模式的字体，否则返回False 。

如果它是一个原始模式的字体，在所有其他功能[QFontInfo](qfontinfo.html)将返回的设置相同的值[QFont](qfont.html)不管字体的实际使用。

**See also** [QFont.rawMode](qfont.html#rawMode)（ ） 。

```
QFont.Style QFontInfo.style (self)
```

[

返回匹配窗口系统字体的样式值。

](qfont.html#Style-enum)

[**See also**](qfont.html#Style-enum) [QFont.style](qfont.html#style)（ ） 。

```
QFont.StyleHint QFontInfo.styleHint (self)
```

[

返回匹配窗口的系统字体的风格。

](qfont.html#StyleHint-enum)

[目前只返回样式提示设置中](qfont.html#StyleHint-enum)[QFont](qfont.html)。

**See also** [QFont.styleHint](qfont.html#styleHint)（）和[QFont.StyleHint](qfont.html#StyleHint-enum)。

```
QString QFontInfo.styleName (self)
```

返回系统匹配窗口的系统字体，支持它的样式名称。

此功能被引入Qt的4.8 。

**See also** [QFont.styleName](qfont.html#styleName)（ ） 。

```
int QFontInfo.weight (self)
```

返回匹配窗口系统字体的粗细。

**See also** [QFont.weight](qfont.html#weight)（）和[bold](qfontinfo.html#bold)（ ） 。