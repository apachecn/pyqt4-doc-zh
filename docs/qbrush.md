# QBrush Class Reference

## [[QtGui](index.htm) module]

该QBrush类定义形状由绘制的填充图案[QPainter](qpainter.html)。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, Qt.BrushStyle bs)`
*   `__init__ (self, QColor color, Qt.BrushStyle style = Qt.SolidPattern)`
*   `__init__ (self, Qt.GlobalColor color, Qt.BrushStyle style = Qt.SolidPattern)`
*   `__init__ (self, QColor color, QPixmap pixmap)`
*   `__init__ (self, Qt.GlobalColor color, QPixmap pixmap)`
*   `__init__ (self, QPixmap pixmap)`
*   `__init__ (self, QImage image)`
*   `__init__ (self, QGradient gradient)`
*   `__init__ (self, QBrush brush)`
*   `__init__ (self, QVariant variant)`
*   `QColor color (self)`
*   `QGradient gradient (self)`
*   `bool isOpaque (self)`
*   `QMatrix matrix (self)`
*   `setColor (self, QColor color)`
*   `setColor (self, Qt.GlobalColor acolor)`
*   `setMatrix (self, QMatrix mat)`
*   `setStyle (self, Qt.BrushStyle)`
*   `setTexture (self, QPixmap pixmap)`
*   `setTextureImage (self, QImage image)`
*   `setTransform (self, QTransform)`
*   `Qt.BrushStyle style (self)`
*   `swap (self, QBrush other)`
*   `QPixmap texture (self)`
*   `QImage textureImage (self)`
*   `QTransform transform (self)`

### Special Methods

*   `bool __eq__ (self, QBrush b)`
*   `bool __ne__ (self, QBrush b)`

* * *

## Detailed Description

A [QColor](qcolor.html)或[QGradient](qgradient.html)可用于每当一个[QBrush](qbrush.html)预计。

该QBrush类定义形状由绘制的填充图案[QPainter](qpainter.html)。

刷子有一种风格，一种颜色，渐变和纹理。

刷[style](qbrush.html#style)（ ）定义了使用填充图案[Qt.BrushStyle](qt.html#BrushStyle-enum)枚举。默认的画笔风格[Qt.NoBrush](qt.html#BrushStyle-enum)（这取决于你如何构建一个刷） 。这种风格告诉画家不填充形状。标准样式的填充物是[Qt.SolidPattern](qt.html#BrushStyle-enum)。该风格时，可以使用适当的构造函数创建的画笔进行设置，另外的[setStyle](qbrush.html#setStyle)（）函数，提供了用于改变样式一旦刷子构造。

![Brush Styles](../img/brush-styles.png)

刷[color](qbrush.html#color)（）定义的填充图案的颜色。颜色可以是Qt的预定义的颜色之一，[Qt.GlobalColor](qt.html#GlobalColor-enum)或任何其它定制[QColor](qcolor.html)。当前设置的颜色可以检索和使用改变了[color](qbrush.html#color)（）和[setColor](qbrush.html#setColor)（ ）函数，分别为。

该[gradient](qbrush.html#gradient)（ ）定义所使用的渐变填充时，当前样式可以是[Qt.LinearGradientPattern](qt.html#BrushStyle-enum)，[Qt.RadialGradientPattern](qt.html#BrushStyle-enum) or [Qt.ConicalGradientPattern](qt.html#BrushStyle-enum)。渐变画刷是由给人一种创造[QGradient](qgradient.html)作为创建QBrush当一个构造函数的参数。 Qt提供了三种不同的梯度：[QLinearGradient](qlineargradient.html)，[QConicalGradient](qconicalgradient.html)和[QRadialGradient](qradialgradient.html) - 所有这些都继承[QGradient](qgradient.html)。

```
     [QRadialGradient](qradialgradient.html) gradient(50, 50, 50, 50, 50);
     gradient.setColorAt(0, [QColor](qcolor.html).fromRgbF(0, 1, 0, 1));
     gradient.setColorAt(1, [QColor](qcolor.html).fromRgbF(0, 0, 0, 0));

     QBrush brush(gradient);

```

该[texture](qbrush.html#texture)（ ）定义了像素图使用时的电流风格[Qt.TexturePattern](qt.html#BrushStyle-enum)。您可以通过创建刷的时候提供的像素映射或通过使用创建带有纹理笔刷[setTexture](qbrush.html#setTexture)（ ） 。

请注意，申请[setTexture](qbrush.html#setTexture)（ ）使[style](qbrush.html#style)（）==[Qt.TexturePattern](qt.html#BrushStyle-enum)，不管先前的样式设置。此外，调用[setColor](qbrush.html#setColor)（ ）将不会有所作为，如果风格是一个梯度。同样的情况下，如果风格[Qt.TexturePattern](qt.html#BrushStyle-enum)风格，除非当前的纹理是[QBitmap](qbitmap.html)。

该[isOpaque](qbrush.html#isOpaque)如果刷的是完全不透明的，否则为False （ ）函数返回True。刷子被认为是不透明的，如果：

*   The alpha component of the [color](qbrush.html#color)() is 255.
*   Its [texture](qbrush.html#texture)() does not have an alpha channel and is not a [QBitmap](qbitmap.html).
*   The colors in the [gradient](qbrush.html#gradient)() all have an alpha component that is 255.

| ![Outlines](../img/brush-outline.png) | To specify the style and color of lines and outlines, use the [QPainter](qpainter.html)'s [pen](qpen.html) combined with [Qt.PenStyle](qt.html#PenStyle-enum) and [Qt.GlobalColor](qt.html#GlobalColor-enum):

```
 [QPainter](qpainter.html) painter(this);

 painter.setBrush([Qt](qt.html).cyan);
 painter.setPen([Qt](qt.html).darkCyan);
 painter.drawRect(0, 0, 100,100);

 painter.setBrush([Qt](qt.html).NoBrush);
 painter.setPen([Qt](qt.html).darkGreen);
 painter.drawRect(40, 40, 100, 100);

```

需要注意的是，默认情况下，[QPainter](qpainter.html)绘制形状时呈现的轮廓（使用当前设置的画笔） 。使用[`painter.setPen(Qt.NoPen)`](qt.html#PenStyle-enum)要禁用此行为。 |

有关油画一般的详细信息，请参阅[Paint System](index.htm)。

* * *

## Method Documentation

```
QBrush.__init__ (self)
```

构造一个默认的黑色画笔的风格[Qt.NoBrush](qt.html#BrushStyle-enum)（即此刷不会填充形状） 。

```
QBrush.__init__ (self, Qt.BrushStyle bs)
```

构造一个黑色画笔给定的_style_。

**See also** [setStyle](qbrush.html#setStyle)（ ） 。

```
QBrush.__init__ (self, QColor color, Qt.BrushStyle style = Qt.SolidPattern)
```

构造一个刷用给定的_color_和_style_。

**See also** [setColor](qbrush.html#setColor)（）和[setStyle](qbrush.html#setStyle)（ ） 。

```
QBrush.__init__ (self, Qt.GlobalColor color, Qt.BrushStyle style = Qt.SolidPattern)
```

构造一个刷用给定的_color_和_style_。

**See also** [setColor](qbrush.html#setColor)（）和[setStyle](qbrush.html#setStyle)（ ） 。

```
QBrush.__init__ (self, QColor color, QPixmap pixmap)
```

构造一个刷用给定的_color_和存储在所述定制模式_pixmap_。

该样式设置为[Qt.TexturePattern](qt.html#BrushStyle-enum)。颜色将只对QBitmaps的效果。

**See also** [setColor](qbrush.html#setColor)（）和[setPixmap](index.htm#setPixmap)（ ） 。

```
QBrush.__init__ (self, Qt.GlobalColor color, QPixmap pixmap)
```

构造一个刷用给定的_color_和存储在所述定制模式_pixmap_。

该样式设置为[Qt.TexturePattern](qt.html#BrushStyle-enum)。颜色将只对QBitmaps的效果。

**See also** [setColor](qbrush.html#setColor)（）和[setPixmap](index.htm#setPixmap)（ ） 。

```
QBrush.__init__ (self, QPixmap pixmap)
```

构造一个刷黑颜色和一组纹理定_pixmap_。该样式设置为[Qt.TexturePattern](qt.html#BrushStyle-enum)。

**See also** [setTexture](qbrush.html#setTexture)（ ） 。

```
QBrush.__init__ (self, QImage image)
```

构造一个刷黑颜色和一组纹理定_image_。该样式设置为[Qt.TexturePattern](qt.html#BrushStyle-enum)。

**See also** [setTextureImage](qbrush.html#setTextureImage)（ ） 。

```
QBrush.__init__ (self, QGradient gradient)
```

构造的副本_other_。

```
QBrush.__init__ (self, QBrush brush)
```

构建了基于给定的一个刷_gradient_。

画笔样式设置为相应的渐变样式（无论是[Qt.LinearGradientPattern](qt.html#BrushStyle-enum)，[Qt.RadialGradientPattern](qt.html#BrushStyle-enum) or [Qt.ConicalGradientPattern](qt.html#BrushStyle-enum)） 。

```
QBrush.__init__ (self, QVariant variant)
```

```
QColor QBrush.color (self)
```

[

返回画笔颜色。

](qcolor.html)

[**See also**](qcolor.html) [setColor](qbrush.html#setColor)（ ） 。

```
QGradient QBrush.gradient (self)
```

[

返回描述此刷的梯度。

```
bool QBrush.isOpaque (self)
```

返回True如果刷的是完全不透明的，否则为False 。刷子被认为是不透明的，如果：

](qgradient.html)

[](qgradient.html)
*   [The alpha component of the](qgradient.html) [color](qbrush.html#color)() is 255.
*   Its [texture](qbrush.html#texture)() does not have an alpha channel and is not a [QBitmap](qbitmap.html).
*   The colors in the [gradient](qbrush.html#gradient)() all have an alpha component that is 255.
*   It is an extended radial gradient.

```
QMatrix QBrush.matrix (self)
```

[

返回刷当前变换矩阵。

这个函数中引入了Qt 4.2中。

](qmatrix.html)

[**See also**](qmatrix.html) [setMatrix](qbrush.html#setMatrix)（ ） 。

```
QBrush.setColor (self, QColor color)
```

设置画笔颜色为给定的_color_。

请注意，调用的setColor （ ）将不会有所作为，如果风格是一个梯度。同样的情况下，如果风格[Qt.TexturePattern](qt.html#BrushStyle-enum)风格，除非当前的纹理是[QBitmap](qbitmap.html)。

**See also** [color](qbrush.html#color)（ ） 。

```
QBrush.setColor (self, Qt.GlobalColor acolor)
```

这是一个重载函数。

设置画笔颜色为给定的_color_。

```
QBrush.setMatrix (self, QMatrix mat)
```

Sets _matrix_作为当前画笔明确的变换矩阵。刷变换矩阵合并[QPainter](qpainter.html)变换矩阵，以产生最终结果。

这个函数中引入了Qt 4.2中。

**See also** [matrix](qbrush.html#matrix)（ ） 。

```
QBrush.setStyle (self, Qt.BrushStyle)
```

设置画笔样式_style_。

**See also** [style](qbrush.html#style)（ ） 。

```
QBrush.setTexture (self, QPixmap pixmap)
```

设置画笔像素图来_pixmap_。该样式设置为[Qt.TexturePattern](qt.html#BrushStyle-enum)。

当前画笔的颜色只会有单色像素图的效果，即对[QPixmap.depth](qpixmap.html#depth)（）== 1 （[QBitmaps](qbitmap.html)） 。

**See also** [texture](qbrush.html#texture)（ ） 。

```
QBrush.setTextureImage (self, QImage image)
```

刷图像设置为_image_。该样式设置为[Qt.TexturePattern](qt.html#BrushStyle-enum)。

请注意当前的画笔颜色会_not_在单色图像有什么影响，而不是调用[setTexture](qbrush.html#setTexture)（ ）与[QBitmap](qbitmap.html)。如果你想改变单色图像画笔的颜色，可以将图像转换为[QBitmap](qbitmap.html)同`QBitmap.fromImage()`并设定产生的[QBitmap](qbitmap.html)作为纹理，或更改图像中的颜色表中的条目。

这个函数中引入了Qt 4.2中。

**See also** [textureImage](qbrush.html#textureImage)（）和[setTexture](qbrush.html#setTexture)（ ） 。

```
QBrush.setTransform (self, QTransform)
```

Sets _matrix_作为当前画笔明确的变换矩阵。刷变换矩阵合并[QPainter](qpainter.html)变换矩阵，以产生最终结果。

此功能被引入Qt的4.3 。

**See also** [transform](qbrush.html#transform)（ ） 。

```
Qt.BrushStyle QBrush.style (self)
```

[

返回画笔样式。

](qt.html#BrushStyle-enum)

[**See also**](qt.html#BrushStyle-enum) [setStyle](qbrush.html#setStyle)（ ） 。

```
QBrush.swap (self, QBrush other)
```

掉期刷_other_用这个刷子。这个操作是非常快的，而且永远不会。

此功能被引入Qt的4.8 。

```
QPixmap QBrush.texture (self)
```

[

返回自定义画笔模式，或者如果没有自定义画笔格局已定一个空的像素图。

](qpixmap.html)

[**See also**](qpixmap.html) [setTexture](qbrush.html#setTexture)（ ） 。

```
QImage QBrush.textureImage (self)
```

[

返回自定义画笔模式，或者如果没有自定义画笔格局已定一个空的图像。

](qimage.html)

[如果纹理被设置为](qimage.html)[QPixmap](qpixmap.html)它会被转换为一个[QImage](qimage.html)。

这个函数中引入了Qt 4.2中。

**See also** [setTextureImage](qbrush.html#setTextureImage)（ ） 。

```
QTransform QBrush.transform (self)
```

[

返回刷当前变换矩阵。

此功能被引入Qt的4.3 。

](qtransform.html)

[**See also**](qtransform.html) [setTransform](qbrush.html#setTransform)（ ） 。

```
bool QBrush.__eq__ (self, QBrush b)
```

```
bool QBrush.__ne__ (self, QBrush b)
```