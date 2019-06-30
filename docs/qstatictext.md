# QStaticText Class Reference

## [[QtGui](index.htm) module]

该QStaticText类使文本时，其布局是很少更新的文字最优化的绘图。[More...](#details)

### Types

*   `enum PerformanceHint { ModerateCaching, AggressiveCaching }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QString text)`
*   `__init__ (self, QStaticText other)`
*   `PerformanceHint performanceHint (self)`
*   `prepare (self, QTransform matrix = QTransform(), QFont font = QFont())`
*   `setPerformanceHint (self, PerformanceHint performanceHint)`
*   `setText (self, QString text)`
*   `setTextFormat (self, Qt.TextFormat textFormat)`
*   `setTextOption (self, QTextOption textOption)`
*   `setTextWidth (self, float textWidth)`
*   `QSizeF size (self)`
*   `QString text (self)`
*   `Qt.TextFormat textFormat (self)`
*   `QTextOption textOption (self)`
*   `float textWidth (self)`

### Special Methods

*   `bool __eq__ (self, QStaticText)`
*   `bool __ne__ (self, QStaticText)`

* * *

## Detailed Description

该QStaticText类使文本时，其布局是很少更新的文字最优化的绘图。

QStaticText提供了一种方法来缓存布局数据为文本块，以便它可以通过使用更高效地绘制比[QPainter.drawText](qpainter.html#drawText)其中（ ）的布局信息重新计算每个呼叫。

该类主要提供情况的文字，其字体和画家的转变是静态的在几个油漆事件的优化。如果文本或它的布局发生变化，每一次迭代，[QPainter.drawText](qpainter.html#drawText)（）是更有效的替代方案，由于静态文本的布局就必须重新计算，以利用新的状态考虑在内。

翻译的画家不会导致重新计算文本的布局，但会造成drawStaticText一个非常小的性能影响（ ） 。改变画家的转换或画家的字体的任何其他部分将导致重新计算的静态文本的布局。这应该被避免尽可能多地最大限度地利用QStaticText的性能优势。

此外，只有仿射变换是由drawStaticText （ ）的支持。上投射画家调用drawStaticText （）将执行比使用常规的drawText （）调用略差，所以这应该被避免。

```
 class MyWidget: public [QWidget](qwidget.html)
 {
 public:
     MyWidget([QWidget](qwidget.html) *parent = 0) : [QWidget](qwidget.html)(parent), m_staticText("This is static text")

 protected:
     void paintEvent([QPaintEvent](qpaintevent.html) *)
     {
         [QPainter](qpainter.html) painter(this);
         painter.drawStaticText(0, 0, m_staticText);
     }

 private:
     QStaticText m_staticText;
 };

```

该QStaticText类可以用来模仿的行为[QPainter.drawText](qpainter.html#drawText)（ ）到一个特定的点，没有界限，也当[QPainter.drawText](qpainter.html#drawText)（ ）被调用矩形边框。

如果不需要矩形边框，创建一个QStaticText对象没有设定一个首选的文本的宽度。那么文本将佔据一行。

如果您在QStaticText对象上设置一个文本的宽度，这将势必文本。该文本将被格式化，这样行不超过给定的宽度。文本宽度为QStaticText设置将不会自动被用于裁剪。为了实现裁剪除了换行符，使用[QPainter.setClipRect](qpainter.html#setClipRect)（ ） 。文字的位置是由传递给该参数决定[QPainter.drawStaticText](qpainter.html#drawStaticText)（ ） ，可以从呼叫改变对性能的影响微乎其微打电话。

为了更加方便，可以使用所支持的HTML子集，以应用格式的文本[QTextDocument](qtextdocument.html)。 QStaticText会尝试猜测输入文本的使用格式[Qt.mightBeRichText](qt.html#mightBeRichText)（ ） ，并把它解释为富文本，如果这个函数返回True。要强制QStaticText以显示其内容为纯文本或富文本，使用功能[QStaticText.setTextFormat](qstatictext.html#setTextFormat)（ ），并通过在分别[Qt.PlainText](qt.html#TextFormat-enum)和[Qt.RichText](qt.html#TextFormat-enum)。

QStaticText只能代表文本，它改变文本的布局或外观所以只有HTML标籤会受到尊重。添加图像输入HTML格式，例如，将导致图像被包括作为布局的一部分，从而影响文本的字符的位置，但它不会被显示。其结果将是一个空的区域中的图像的尺寸在输出中。同样，使用表将导致文本进行布局以表格的形式，但边框将不会被绘制。

如果是第一次的静态文本绘制，或者如果静态文本，或画家的字体已经自最后一次修改它被绘制，文字的布局，必须重新计算。在某些涂料发动机，改变画家的矩阵也将导致布局进行重新计算。特别是，这会发生于任何发动机除了OpenGL2涂料引擎。重新计算布局将强加的开销[QPainter.drawStaticText](qpainter.html#drawStaticText)（ ）调用在那里发生。为了避免这种开销在内线时，可以调用[prepare](qstatictext.html#prepare)（）的时间提前，以确保布局的计算方法。

* * *

## Type Documentation

```
QStaticText.PerformanceHint
```

这个枚举，可以在设置的不同性能的提示[QStaticText](qstatictext.html)。这些提示可以被用来指示该[QStaticText](qstatictext.html)应该使用额外的缓存，如果可能的话，在记忆的费用，以提高性能。特别是，在设置性能暗示AggressiveCaching上[QStaticText](qstatictext.html)使用OpenGL图形系统或绘制到时将提高性能时[QGLWidget](qglwidget.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QStaticText.ModerateCaching` | `0` | 做基本的缓存高性能，低内存成本。 |
| `QStaticText.AggressiveCaching` | `1` | 使用额外的缓存时可用。这可能在更高的存储器成本提高性能。 |

* * *

## Method Documentation

```
QStaticText.__init__ (self)
```

构造一个空[QStaticText](qstatictext.html)

```
QStaticText.__init__ (self, QString text)
```

构造一个[QStaticText](qstatictext.html)与给定对象_text_。

```
QStaticText.__init__ (self, QStaticText other)
```

构造一个[QStaticText](qstatictext.html)对象，这是一个拷贝_other_。

```
PerformanceHint QStaticText.performanceHint (self)
```

[](qstatictext.html#PerformanceHint-enum)

[它的性能提示设置为回报](qstatictext.html#PerformanceHint-enum)[QStaticText](qstatictext.html)。

**See also** [setPerformanceHint](qstatictext.html#setPerformanceHint)（ ） 。

```
QStaticText.prepare (self, QTransform matrix = QTransform(), QFont font = QFont())
```

准备[QStaticText](qstatictext.html)对于对象被绘制与给定_matrix_和给定的_font_避免架空当实际drawStaticText （ ）调用。

当drawStaticText （ ）被调用时，的布局[QStaticText](qstatictext.html)将被重新计算，如果任何部分的[QStaticText](qstatictext.html)自从上一次被绘制的对象发生了变化。如果画家的字体是不一样的，因为它也将被重新计算时[QStaticText](qstatictext.html)被最后绘制，或在任何其他绘图引擎比OpenGL2引擎，如果画家的矩阵已经改变，因为静态文本的最后绘制。

为了避免创建布局中的第一次绘制的开销[QStaticText](qstatictext.html)在进行更改后，您可以使用prepare （ ）函数，并传入_matrix_和_font_你希望绘制文本时使用。

**See also** [QPainter.setFont](qpainter.html#setFont)（）和[QPainter.setMatrix](index.htm#setMatrix)（ ） 。

```
QStaticText.setPerformanceHint (self, PerformanceHint performanceHint)
```

设置的性能提示[QStaticText](qstatictext.html)根据本_performanceHint_提供。该_performanceHint_用于自定义多少缓存是在内部完成，以提高性能。

默认值是[QStaticText.ModerateCaching](qstatictext.html#PerformanceHint-enum)。

**Note:**此功能将导致需要重新计算的文本的布局。

**See also** [performanceHint](qstatictext.html#performanceHint)（ ） 。

```
QStaticText.setText (self, QString text)
```

设置的文本[QStaticText](qstatictext.html)至_text_。

**Note:**此功能将导致需要重新计算的文本的布局。

**See also** [text](qstatictext.html#text)（ ） 。

```
QStaticText.setTextFormat (self, Qt.TextFormat textFormat)
```

设置的文本格式[QStaticText](qstatictext.html)至_textFormat_。如果_textFormat_被设置为[Qt.AutoText](qt.html#TextFormat-enum)（默认） ，文本格式将尝试使用该功能来确定[Qt.mightBeRichText](qt.html#mightBeRichText)（ ） 。如果文本格式是[Qt.PlainText](qt.html#TextFormat-enum)，则文本将显示为是，则它会被解释为HTML格式是否为[Qt.RichText](qt.html#TextFormat-enum)。该改变文本的字体，颜色，或者其布局的HTML标籤都受到支持[QStaticText](qstatictext.html)。

**Note:**此功能将导致需要重新计算的文本的布局。

**See also** [textFormat](qstatictext.html#textFormat)（ ）[setText](qstatictext.html#setText)（）和[text](qstatictext.html#text)（ ） 。

```
QStaticText.setTextOption (self, QTextOption textOption)
```

设置文本选项的结构，控制布局过程中给定的_textOption_。

**See also** [textOption](qstatictext.html#textOption)（ ） 。

```
QStaticText.setTextWidth (self, float textWidth)
```

设置此的首选宽度[QStaticText](qstatictext.html)。如果文本比指定的宽度更宽，它会被分成多行和垂直增长。如果文字不能拆分成多行，它会比指定的大_textWidth_。

首选的文本宽度设置为负数会导致文本是无界的。

使用[size](qstatictext.html#size)（）来获取文本的实际大小。

**Note:**此功能将导致需要重新计算的文本的布局。

**See also** [textWidth](qstatictext.html#textWidth)（）和[size](qstatictext.html#size)（ ） 。

```
QSizeF QStaticText.size (self)
```

[](qsizef.html)

[返回该边界矩形的大小为这](qsizef.html)[QStaticText](qstatictext.html)。

**See also** [textWidth](qstatictext.html#textWidth)（ ） 。

```
QString QStaticText.text (self)
```

返回的文本[QStaticText](qstatictext.html)。

**See also** [setText](qstatictext.html#setText)（ ） 。

```
Qt.TextFormat QStaticText.textFormat (self)
```

[](qt.html#TextFormat-enum)

[返回的文本格式](qt.html#TextFormat-enum)[QStaticText](qstatictext.html)。

**See also** [setTextFormat](qstatictext.html#setTextFormat)（ ）[setText](qstatictext.html#setText)（）和[text](qstatictext.html#text)（ ） 。

```
QTextOption QStaticText.textOption (self)
```

[

返回用于控制布局过程中的当前文本选项。

](qtextoption.html)

[**See also**](qtextoption.html) [setTextOption](qstatictext.html#setTextOption)（ ） 。

```
float QStaticText.textWidth (self)
```

返回首选宽度为这个[QStaticText](qstatictext.html)。

**See also** [setTextWidth](qstatictext.html#setTextWidth)（ ） 。

```
bool QStaticText.__eq__ (self, QStaticText)
```

```
bool QStaticText.__ne__ (self, QStaticText)
```