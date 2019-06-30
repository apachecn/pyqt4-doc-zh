# QPen Class Reference

## [[QtGui](index.htm) module]

该QPen类定义了一个[QPainter](qpainter.html)要绘制形状的线条和轮廓。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, Qt.PenStyle)`
*   `__init__ (self, QColor color)`
*   `__init__ (self, QBrush brush, float width, Qt.PenStyle style = Qt.SolidLine, Qt.PenCapStyle cap = Qt.SquareCap, Qt.PenJoinStyle join = Qt.BevelJoin)`
*   `__init__ (self, QPen pen)`
*   `__init__ (self, QVariant variant)`
*   `QBrush brush (self)`
*   `Qt.PenCapStyle capStyle (self)`
*   `QColor color (self)`
*   `float dashOffset (self)`
*   `list-of-float dashPattern (self)`
*   `bool isCosmetic (self)`
*   `bool isSolid (self)`
*   `Qt.PenJoinStyle joinStyle (self)`
*   `float miterLimit (self)`
*   `setBrush (self, QBrush brush)`
*   `setCapStyle (self, Qt.PenCapStyle pcs)`
*   `setColor (self, QColor color)`
*   `setCosmetic (self, bool cosmetic)`
*   `setDashOffset (self, float doffset)`
*   `setDashPattern (self, list-of-float pattern)`
*   `setJoinStyle (self, Qt.PenJoinStyle pcs)`
*   `setMiterLimit (self, float limit)`
*   `setStyle (self, Qt.PenStyle)`
*   `setWidth (self, int width)`
*   `setWidthF (self, float width)`
*   `Qt.PenStyle style (self)`
*   `swap (self, QPen other)`
*   `int width (self)`
*   `float widthF (self)`

### Special Methods

*   `bool __eq__ (self, QPen p)`
*   `bool __ne__ (self, QPen p)`

* * *

## Detailed Description

A [QColor](qcolor.html)可用于每当一个[QPen](qpen.html)预计。

该QPen类定义了一个[QPainter](qpainter.html)要绘制形状的线条和轮廓。

一支笔有[style](qpen.html#style)（ ）[width](qpen.html#width)（ ）[brush](qpen.html#brush)（ ）[capStyle](qpen.html#capStyle)（）和[joinStyle](qpen.html#joinStyle)（ ） 。

笔式定义线型。画笔用于填充用钢笔生成的笔触。使用[QBrush](qbrush.html)类指定填充样式。帽风格决定了可使用画线端盖[QPainter](qpainter.html)，而加入的风格介绍了如何两条线之间的连接被吸引。钢笔的宽度可以在两个整数来指定（[width](qpen.html#width)（ ） ）和浮点（[widthF](qpen.html#widthF)（ ） ）的精度。零线宽表示化妆品的笔。这意味着画笔宽度总是绘制一个像素的宽度，独立的[transformation](qpainter.html#coordinate-transformations)设置的画家。

的各种设置可容易地使用相应的改性[setStyle](qpen.html#setStyle)（ ）[setWidth](qpen.html#setWidth)（ ）[setBrush](qpen.html#setBrush)（ ）[setCapStyle](qpen.html#setCapStyle)（）和[setJoinStyle](qpen.html#setJoinStyle)（ ）函数（注意，画家的笔下必须改变画笔的属性时被重置） 。

例如：

```
 [QPainter](qpainter.html) painter(this);
 QPen pen([Qt](qt.html).green, 3, [Qt](qt.html).DashDotLine, [Qt](qt.html).RoundCap, [Qt](qt.html).RoundJoin);
 painter.setPen(pen);

```

这相当于

```
 [QPainter](qpainter.html) painter(this);
 QPen pen;  // creates a default pen

 pen.setStyle([Qt](qt.html).DashDotLine);
 pen.setWidth(3);
 pen.setBrush([Qt](qt.html).green);
 pen.setCapStyle([Qt](qt.html).RoundCap);
 pen.setJoinStyle([Qt](qt.html).RoundJoin);

 painter.setPen(pen);

```

默认的笔是一个纯黑色画笔0宽，方帽风格（[Qt.SquareCap](qt.html#PenCapStyle-enum)）和斜角连接样式（[Qt.BevelJoin](qt.html#PenJoinStyle-enum)） 。

此外QPen提供[color](qpen.html#color)（）和[setColor](qpen.html#setColor)（ ）方便的功能来提取和设置画笔的画笔的颜色，分别为。笔也可以比较和流。

有关油画一般的详细信息，请参阅[Paint System](index.htm)文档。

### Pen Style

Qt提供了几个代表的内置样式[Qt.PenStyle](qt.html#PenStyle-enum)枚举：

| ![](../img/qpen-solid.png) | ![](../img/qpen-dash.png) | ![](../img/qpen-dot.png) |
| [Qt.SolidLine](qt.html#PenStyle-enum) | [Qt.DashLine](qt.html#PenStyle-enum) | [Qt.DotLine](qt.html#PenStyle-enum) |
| ![](../img/qpen-dashdot.png) | ![](../img/qpen-dashdotdot.png) | ![](../img/qpen-custom.png) |
| [Qt.DashDotLine](qt.html#PenStyle-enum) | [Qt.DashDotDotLine](qt.html#PenStyle-enum) | [Qt.CustomDashLine](qt.html#PenStyle-enum) |

简单地使用[setStyle](qpen.html#setStyle)（）函数的笔式转换为下列任一内置样式，除了[Qt.CustomDashLine](qt.html#PenStyle-enum)风格，我们会回来不久。将样式设置为[Qt.NoPen](qt.html#PenStyle-enum)告诉画家不画线或轮廓。默认的画笔风格[Qt.SolidLine](qt.html#PenStyle-enum)。

由于Qt的4.1 ，也可以使用指定自定义虚线图案的[setDashPattern](qpen.html#setDashPattern)（ ）函数，它的笔的款式隐式转换为[Qt.CustomDashLine](qt.html#PenStyle-enum)。该模式的说法，一[QVector](index.htm)，必须指定为偶数的[qreal](index.htm#qreal-typedef)条目，其中这些条目1，3， 5 ...是虚线和2，4， 6 ...是空格。例如，上面显示的自定义模式是使用下面的代码创建：

```
 QPen pen;
 [QVector](index.htm)<[qreal](index.htm#qreal-typedef)> dashes;
 [qreal](index.htm#qreal-typedef) space = 4;

 dashes << 1 << space << 3 << space << 9 << space
            << 27 << space << 9 << space;

 pen.setDashPattern(dashes);

```

请注意，虚线图案的钢笔的宽度，如为单位指定长度为5的宽度为10的破折号是50像素长。

当前设定的虚线样式可以使用检索的[dashPattern](qpen.html#dashPattern)（）函数。使用[isSolid](qpen.html#isSolid)（ ）函数来确定笔是否为实心填充，还是不行。

### Cap Style

帽样式定义如何线路的终点使用绘制[QPainter](qpainter.html)。帽风格只适用于宽线，即当宽度大于或等于1 。该[Qt.PenCapStyle](qt.html#PenCapStyle-enum)枚举提供了以下方式：

| ![](../img/qpen-square.png) | ![](../img/qpen-flat.png) | ![](../img/qpen-roundcap.png) |
| [Qt.SquareCap](qt.html#PenCapStyle-enum) | [Qt.FlatCap](qt.html#PenCapStyle-enum) | [Qt.RoundCap](qt.html#PenCapStyle-enum) |

该[Qt.SquareCap](qt.html#PenCapStyle-enum)风格是一个正方形行结束，涵盖了终点，一半线条宽度超出了它。该[Qt.FlatCap](qt.html#PenCapStyle-enum)样式是方形线端未复盖的线的终点。和[Qt.RoundCap](qt.html#PenCapStyle-enum)样式是圆形的线端复盖的终点。

默认值是[Qt.SquareCap](qt.html#PenCapStyle-enum)。

不论是否端点被绘制时，钢笔的宽度为0或1取决于帽样式。运用[Qt.SquareCap](qt.html#PenCapStyle-enum) or [Qt.RoundCap](qt.html#PenCapStyle-enum)它们被绘制，用[Qt.FlatCap](qt.html#PenCapStyle-enum)它们不绘制。

### Join Style

在加入样式定义如何将两个连接线之间的连接可以使用绘制[QPainter](qpainter.html)。接合风格只适用于宽线，即当宽度大于或等于1 。该[Qt.PenJoinStyle](qt.html#PenJoinStyle-enum)枚举提供了以下方式：

| ![](../img/qpen-bevel.png) | ![](../img/qpen-miter.png) | ![](../img/qpen-roundjoin.png) |
| [Qt.BevelJoin](qt.html#PenJoinStyle-enum) | [Qt.MiterJoin](qt.html#PenJoinStyle-enum) | [Qt.RoundJoin](qt.html#PenJoinStyle-enum) |

该[Qt.BevelJoin](qt.html#PenJoinStyle-enum)式填充两条线之间的三角形缺口。该[Qt.MiterJoin](qt.html#PenJoinStyle-enum)风格延伸线，以满足在一个角度。和[Qt.RoundJoin](qt.html#PenJoinStyle-enum)式填充两条线之间的圆弧。

默认值是[Qt.BevelJoin](qt.html#PenJoinStyle-enum)。

![](../img/qpen-miterlimit.png)

当[Qt.MiterJoin](qt.html#PenJoinStyle-enum)样式被应用，就可以使用[setMiterLimit](qpen.html#setMiterLimit)（ ）函数来指定多远斜角连接可以扩展的连接点。该[miterLimit](qpen.html#miterLimit)（）是用于减少线路之间的工件接合处的线是接近平行。

该[miterLimit](qpen.html#miterLimit)（）必须在笔为单位指定宽度，例如： 5在宽度为10的斜接限制为50像素长。默认的斜接限制为2 ，即两次以像素为单位的笔宽。

| ![](../img/qpen-demo.png) | **[The Path Stroking Demo](index.htm)**路径描边演示显示了Qt内建的虚线样式，并显示自定义模式可以如何用来扩展现有模式的范围。 |

* * *

## Method Documentation

```
QPen.__init__ (self)
```

构造一个默认的黑色实线与笔宽0 。

```
QPen.__init__ (self, Qt.PenStyle)
```

构造一个黑色的钢笔0宽度和给定_style_。

**See also** [setStyle](qpen.html#setStyle)（ ） 。

```
QPen.__init__ (self, QColor color)
```

构造一个实线画笔0宽度和给定_color_。

**See also** [setBrush](qpen.html#setBrush)（）和[setColor](qpen.html#setColor)（ ） 。

```
QPen.__init__ (self, QBrush brush, float width, Qt.PenStyle style = Qt.SolidLine, Qt.PenCapStyle cap = Qt.SquareCap, Qt.PenJoinStyle join = Qt.BevelJoin)
```

构造一个笔用指定的_brush_，_width_，笔_style_，_cap_风格和_join_风格。

**See also** [setBrush](qpen.html#setBrush)（ ）[setWidth](qpen.html#setWidth)（ ）[setStyle](qpen.html#setStyle)（ ）[setCapStyle](qpen.html#setCapStyle)（）和[setJoinStyle](qpen.html#setJoinStyle)（ ） 。

```
QPen.__init__ (self, QPen pen)
```

构造一个Pen，它是给定一个副本_pen_。

```
QPen.__init__ (self, QVariant variant)
```

```
QBrush QPen.brush (self)
```

[

返回用于填充此笔笔划产生的刷子。

](qbrush.html)

[**See also**](qbrush.html) [setBrush](qpen.html#setBrush)（ ） 。

```
Qt.PenCapStyle QPen.capStyle (self)
```

[

返回画笔的端点风格。

](qt.html#PenCapStyle-enum)

[**See also**](qt.html#PenCapStyle-enum) [setCapStyle](qpen.html#setCapStyle)（）和[Cap Style](qpen.html#cap-style)。

```
QColor QPen.color (self)
```

[

返回此笔的画笔的颜色。

](qcolor.html)

[**See also**](qcolor.html) [brush](qpen.html#brush)（）和[setColor](qpen.html#setColor)（ ） 。

```
float QPen.dashOffset (self)
```

返回破折号画笔偏移。

**See also** [setDashOffset](qpen.html#setDashOffset)（ ） 。

```
list-of-float QPen.dashPattern (self)
```

返回此笔的虚线样式。

**See also** [setDashPattern](qpen.html#setDashPattern)（ ）[style](qpen.html#style)（）和[isSolid](qpen.html#isSolid)（ ） 。

```
bool QPen.isCosmetic (self)
```

返回True如果笔是化妆品，否则返回False 。

化妆品的笔用于绘制具有一定宽度笔划不管施加到任何转换[QPainter](qpainter.html)它们被用于与。绘制形状与化妆品笔确保其轮廓将具有相同的厚度在不同的比例系数。

零宽度的笔是化妆品默认情况下，用钢笔一个非零宽度非化妆品。

**See also** [setCosmetic](qpen.html#setCosmetic)（）和[widthF](qpen.html#widthF)（ ） 。

```
bool QPen.isSolid (self)
```

如果笔有一个实心填充，否则为False ，则返回True 。

**See also** [style](qpen.html#style)（）和[dashPattern](qpen.html#dashPattern)（ ） 。

```
Qt.PenJoinStyle QPen.joinStyle (self)
```

[

返回画笔的接合风格。

](qt.html#PenJoinStyle-enum)

[**See also**](qt.html#PenJoinStyle-enum) [setJoinStyle](qpen.html#setJoinStyle)（）和[Join Style](qpen.html#join-style)。

```
float QPen.miterLimit (self)
```

返回钢笔斜接限制。斜接限制仅适用时加入样式设置为[Qt.MiterJoin](qt.html#PenJoinStyle-enum)。

**See also** [setMiterLimit](qpen.html#setMiterLimit)（）和[Join Style](qpen.html#join-style)。

```
QPen.setBrush (self, QBrush brush)
```

设置用于填充用这支笔生成的给定笔划刷_brush_。

**See also** [brush](qpen.html#brush)（）和[setColor](qpen.html#setColor)（ ） 。

```
QPen.setCapStyle (self, Qt.PenCapStyle pcs)
```

设置画笔的端点风格为给定的_style_。缺省值是[Qt.SquareCap](qt.html#PenCapStyle-enum)。

**See also** [capStyle](qpen.html#capStyle)（）和[Cap Style](qpen.html#cap-style)。

```
QPen.setColor (self, QColor color)
```

设置此笔的画笔的颜色来定_color_。

**See also** [setBrush](qpen.html#setBrush)（）和[color](qpen.html#color)（ ） 。

```
QPen.setCosmetic (self, bool cosmetic)
```

设置此笔化妆或不化妆，这取决于价值_cosmetic_。

**See also** [isCosmetic](qpen.html#isCosmetic)（ ） 。

```
QPen.setDashOffset (self, float doffset)
```

设置在仪表偏移（在虚线模式的出发点）就本笔到_offset_规定。的偏移量的测量是在用于指定虚线图案的单元计。

| ![](../img/qpen-dashpattern.png) | For example, a pattern where each stroke is four units long, followed by a gap of two units, will begin with the stroke when drawn as a line.然而，如果破折号偏移量设置为4.0时，得出的任何线将开始与间隙。的偏移量高达4.0的值将导致中风的一部分首先被绘制，而值4.0和6.0之间的偏移将导致与开始的间隙部分就行了。 |

**Note:**这种隐式转换用笔的风格[Qt.CustomDashLine](qt.html#PenStyle-enum)。

**See also** [dashOffset](qpen.html#dashOffset)（ ） 。

```
QPen.setDashPattern (self, list-of-float pattern)
```

设置此笔的虚线样式给定的_pattern_。这种隐式转换用笔的风格[Qt.CustomDashLine](qt.html#PenStyle-enum)。

图案必须被指定为偶数阳性条目，其中这些条目1，3， 5 ...是虚线和2，4， 6 ...是空格。例如：

| ![](../img/qpen-custom.png) | 

```
 [QPen](qpen.html) pen;
 [QVector](index.htm)&lt;[qreal](index.htm#qreal-typedef)&gt; dashes;
 [qreal](index.htm#qreal-typedef) space = 4;
 dashes &lt;&lt; 1 &lt;&lt; space &lt;&lt; 3 &lt;&lt; space &lt;&lt; 9 &lt;&lt; space
            &lt;&lt; 27 &lt;&lt; space &lt;&lt; 9 &lt;&lt; space;
 pen.setDashPattern(dashes);

```

 |

虚线样式被指定在钢笔的宽度为单位;例如：长度为5的宽度为10的破折号是50像素长。需要注意的是零宽度的笔相当于一个化妆品笔与1个像素的宽度。

每个破折号也受到帽样式，因此1方形帽套破折号将扩大0.5个像素在每个方向上产生2的总宽度。

请注意，默认帽风格[Qt.SquareCap](qt.html#PenCapStyle-enum)的，这意味着一个正方形线端复盖了终点，并通过半线宽度延伸超过它。

**See also** [setStyle](qpen.html#setStyle)（ ）[dashPattern](qpen.html#dashPattern)（ ）[setCapStyle](qpen.html#setCapStyle)（）和[setCosmetic](qpen.html#setCosmetic)（ ） 。

```
QPen.setJoinStyle (self, Qt.PenJoinStyle pcs)
```

设置画笔的接合风格为给定的_style_。缺省值是[Qt.BevelJoin](qt.html#PenJoinStyle-enum)。

**See also** [joinStyle](qpen.html#joinStyle)（）和[Join Style](qpen.html#join-style)。

```
QPen.setMiterLimit (self, float limit)
```

设置此笔的斜接限制为给定的_limit_。

![](../img/qpen-miterlimit.png)

斜接限制描述多远斜角连接可以从连接点延伸。这是用来减少线路之间的工件接合处的线是接近平行。

该值不会只影响当笔样式设置为[Qt.MiterJoin](qt.html#PenJoinStyle-enum)。该值在笔的宽度，如为单位指定5在宽度为10的斜接限制为50像素长。默认的斜接限制为2 ，即两次以像素为单位的笔宽。

**See also** [miterLimit](qpen.html#miterLimit)（ ）[setJoinStyle](qpen.html#setJoinStyle)（）和[Join Style](qpen.html#join-style)。

```
QPen.setStyle (self, Qt.PenStyle)
```

设置画笔样式给定的_style_。

请参阅[Qt.PenStyle](qt.html#PenStyle-enum)文档的可用样式列表。由于Qt的4.1 ，也可以使用指定自定义虚线图案的[setDashPattern](qpen.html#setDashPattern)（ ）函数，它的笔的款式隐式转换为[Qt.CustomDashLine](qt.html#PenStyle-enum)。

**Note:**该函数复位破折号偏移为零。

**See also** [style](qpen.html#style)（）和[Pen Style](qpen.html#pen-style)。

```
QPen.setWidth (self, int width)
```

设置钢笔的宽度为给定的_width_与精确到整数像素。

零线宽表示化妆品的笔。这意味着画笔宽度总是绘制一个像素的宽度，独立的[transformation](qpainter.html#coordinate-transformations)设置的画家。

设置画笔宽度为负值，不支持。

**See also** [setWidthF](qpen.html#setWidthF)（）和[width](qpen.html#width)（ ） 。

```
QPen.setWidthF (self, float width)
```

设置钢笔的宽度为给定的_width_与浮点精度像素。

零线宽表示化妆品的笔。这意味着画笔宽度总是绘制一个像素的宽度，独立的[transformation](qpainter.html#coordinate-transformations)在画家。

设置画笔宽度为负值，不支持。

**See also** [setWidth](qpen.html#setWidth)（）和[widthF](qpen.html#widthF)（ ） 。

```
Qt.PenStyle QPen.style (self)
```

[

返回画笔样式。

](qt.html#PenStyle-enum)

[**See also**](qt.html#PenStyle-enum) [setStyle](qpen.html#setStyle)（）和[Pen Style](qpen.html#pen-style)。

```
QPen.swap (self, QPen other)
```

笔掉期_other_用这种笔。这个操作是非常快的，而且永远不会。

此功能被引入Qt的4.8 。

```
int QPen.width (self)
```

返回画笔的宽度以整数精度。

**See also** [setWidth](qpen.html#setWidth)（）和[widthF](qpen.html#widthF)（ ） 。

```
float QPen.widthF (self)
```

返回与浮点精度的笔宽。

**See also** [setWidthF](qpen.html#setWidthF)（）和[width](qpen.html#width)（ ） 。

```
bool QPen.__eq__ (self, QPen p)
```

```
bool QPen.__ne__ (self, QPen p)
```