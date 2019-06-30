# QPaintEngine Class Reference

## [[QtGui](index.htm) module]

该QPaintEngine类提供了如何的抽象定义[QPainter](qpainter.html)绘制到一个给定的设备在给定平台上。[More...](#details)

### Types

*   `enum DirtyFlag { DirtyPen, DirtyBrush, DirtyBrushOrigin, DirtyFont, ..., AllDirty }`
*   `class **[DirtyFlags](index.htm)**`
*   `enum PaintEngineFeature { PrimitiveTransform, PatternTransform, PixmapTransform, PatternBrush, ..., AllFeatures }`
*   `class **[PaintEngineFeatures](index.htm)**`
*   `enum PolygonDrawMode { OddEvenMode, WindingMode, ConvexMode, PolylineMode }`
*   `enum Type { X11, Windows, QuickDraw, CoreGraphics, ..., MaxUser }`

### Methods

*   `__init__ (self, PaintEngineFeatures features = 0)`
*   `bool begin (self, QPaintDevice pdev)`
*   `drawEllipse (self, QRectF r)`
*   `drawEllipse (self, QRect r)`
*   `drawImage (self, QRectF r, QImage pm, QRectF sr, Qt.ImageConversionFlags flags = Qt.AutoColor)`
*   `drawLines (self, QLine lines)`
*   `drawLines (self, QLineF lines)`
*   `drawPath (self, QPainterPath path)`
*   `drawPixmap (self, QRectF r, QPixmap pm, QRectF sr)`
*   `drawPoints (self, QPointF points)`
*   `drawPoints (self, QPoint points)`
*   `drawPolygon (self, QPointF points, PolygonDrawMode mode)`
*   `drawPolygon (self, QPoint points, PolygonDrawMode mode)`
*   `drawRects (self, QRect rects)`
*   `drawRects (self, QRectF rects)`
*   `drawTextItem (self, QPointF p, QTextItem textItem)`
*   `drawTiledPixmap (self, QRectF r, QPixmap pixmap, QPointF s)`
*   `bool end (self)`
*   `bool hasFeature (self, PaintEngineFeatures feature)`
*   `bool isActive (self)`
*   `QPaintDevice paintDevice (self)`
*   `QPainter painter (self)`
*   `setActive (self, bool newState)`
*   `setPaintDevice (self, QPaintDevice device)`
*   `Type type (self)`
*   `updateState (self, QPaintEngineState state)`

* * *

## Detailed Description

该QPaintEngine类提供了如何的抽象定义[QPainter](qpainter.html)绘制到一个给定的设备在给定平台上。

的Qt 4.0提供QPaintEngine的几个预制的实现，因为我们支持不同的画家后端。我们为每个窗口系统和绘画框架，我们支持提供一个绘制引擎。这包括X11在Unix / Linux和[CoreGraphics](qpaintengine.html#Type-enum)在Mac OS X此外，我们提供QPaintEngine的实现[OpenGL](qpaintengine.html#Type-enum)（可通过[QGLWidget](qglwidget.html)）和[PostScript](qpaintengine.html#Type-enum)（通过QPSPrinter在X11访问） 。此外，还有一个基于光栅的涂料引擎，是一个后备，当引擎不支持某些功能。

如果一个人想用[QPainter](qpainter.html)绘制到不同的后端，必须继承QPaintEngine并重新实现其所有的虚函数。该QPaintEngine执行，然后提供通过继承[QPaintDevice](qpaintdevice.html)并重新实现虚函数[QPaintDevice.paintEngine](qpaintdevice.html#paintEngine)（ ） 。

QPaintEngine创建和拥有的[QPaintDevice](qpaintdevice.html)创建它。

该QPaintEngine办法反对的Qt 3的的一大优点[QPainter](qpainter.html)/ QPaintDevice.cmd （ ）方法，它现在可以适应多种技术在每个平台上，充分利用每一个发挥到淋漓尽致。

* * *

## Type Documentation

```
QPaintEngine.DirtyFlag
```

| Constant | Value | Description |
| --- | --- | --- |
| `QPaintEngine.DirtyPen` | `0x0001` | 笔是脏，需要更新。 |
| `QPaintEngine.DirtyBrush` | `0x0002` | 刷脏了，需要更新。 |
| `QPaintEngine.DirtyBrushOrigin` | `0x0004` | 刷原点是脏的，需要更新的。 |
| `QPaintEngine.DirtyFont` | `0x0008` | 字体变脏，需要进行更新。 |
| `QPaintEngine.DirtyBackground` | `0x0010` | 背景是脏的，需要被更新。 |
| `QPaintEngine.DirtyBackgroundMode` | `0x0020` | 背景模式是脏的，需要被更新。 |
| `QPaintEngine.DirtyTransform` | `0x0040` | 该变换是脏的，需要被更新。 |
| `QPaintEngine.DirtyClipRegion` | `0x0080` | 裁剪区域变脏，需要进行更新。 |
| `QPaintEngine.DirtyClipPath` | `0x0100` | 剪辑路径是脏的，需要被更新。 |
| `QPaintEngine.DirtyHints` | `0x0200` | 渲染提示脏了，需要更新。 |
| `QPaintEngine.DirtyCompositionMode` | `0x0400` | 该组合物模式是脏的，需要被更新。 |
| `QPaintEngine.DirtyClipEnabled` | `0x0800` | 无论裁剪启用与否是脏，需要更新。 |
| `QPaintEngine.DirtyOpacity` | `0x1000` | 不透明度的常已发生变化，需要进行更新的状态变化的一部分[QPaintEngine.updateState](qpaintengine.html#updateState)（ ） 。 |
| `QPaintEngine.AllDirty` | `0xffff` | 内部使用的便利枚举。 |

这些类型用于通过[QPainter](qpainter.html)来触发各种状态的懒惰更新[QPaintEngine](qpaintengine.html) using [QPaintEngine.updateState](qpaintengine.html#updateState)（ ） 。

一种涂料引擎必须更新每个脏状态。

该DirtyFlags类型是一个typedef为[QFlags](index.htm)\u003cDirtyFlag\u003e 。它存储DirtyFlag值的或组合。

```
QPaintEngine.PaintEngineFeature
```

此枚举是用来描述的特征或功能，油漆引擎。如果某个特性不支持的引擎，[QPainter](qpainter.html)会做通过其他方式来模拟该功能，并通过对混合阿尔法尽力[QImage](qimage.html)与模拟结果的引擎。有些功能不能被仿真： AlphaBlend的和PorterDuff 。

| Constant | Value | Description |
| --- | --- | --- |
| `QPaintEngine.AlphaBlend` | `0x00000080` | 该引擎可以alpha混合语。 |
| `QPaintEngine.Antialiasing` | `0x00000400` | 发动机可以使用antialising提高渲染图元的外观。 |
| `QPaintEngine.BlendModes` | `0x00008000` | 该引擎支持混合模式。 |
| `QPaintEngine.BrushStroke` | `0x00000800` | 该引擎支持绘制包含画笔作为填充招，不只是纯色（如宽度2虚线渐变线） 。 |
| `QPaintEngine.ConicalGradientFill` | `0x00000040` | 该引擎支持的锥形渐变填充。 |
| `QPaintEngine.ConstantOpacity` | `0x00001000` | 该引擎支持所提供的功能[QPainter.setOpacity](qpainter.html#setOpacity)（ ） 。 |
| `QPaintEngine.LinearGradientFill` | `0x00000010` | 该引擎支持线性渐变填充。 |
| `QPaintEngine.MaskedBrush` | `0x00002000` | 该引擎能够呈现画笔，有带有alpha通道或遮罩的质感。 |
| `QPaintEngine.ObjectBoundingModeGradients` | `0x00010000` | 该发动机具有梯度与原生支持坐标模式[QGradient.ObjectBoundingMode](qgradient.html#CoordinateMode-enum)。否则，如果支持QPaintEngine.PatternTransform ，对象边界模式渐变转换为梯度与协调模式[QGradient.LogicalMode](qgradient.html#CoordinateMode-enum)和一个刷子变换的坐标映射关系。 |
| `QPaintEngine.PainterPaths` | `0x00000200` | 该发动机具有路径的支持。 |
| `QPaintEngine.PaintOutsidePaintEvent` | `0x20000000` | 该引擎能够画的绘制事件之外。 |
| `QPaintEngine.PatternBrush` | `0x00000008` | 该引擎能够呈现刷子在指定的笔刷模式[Qt.BrushStyle](qt.html#BrushStyle-enum)。 |
| `QPaintEngine.PatternTransform` | `0x00000002` | 该发动机具有转化刷模式的支持。 |
| `QPaintEngine.PerspectiveTransform` | `0x00004000` | 该发动机具有对原语进行视角转换的支持。 |
| `QPaintEngine.PixmapTransform` | `0x00000004` | 该引擎可以将像素图，包括旋转和剪切。 |
| `QPaintEngine.PorterDuff` | `0x00000100` | 该引擎支持波特 - 达夫操作 |
| `QPaintEngine.PrimitiveTransform` | `0x00000001` | 该发动机具有转化的绘图图元的支持。 |
| `QPaintEngine.RadialGradientFill` | `0x00000020` | 该引擎支持的径向渐变填充。 |
| `QPaintEngine.RasterOpModes` | `0x00020000` | 该引擎支持按位光栅操作。 |
| `QPaintEngine.AllFeatures` | `0xffffffff` | 所有的上述功能。这个枚举值通常被用作一个位掩码。 |

该PaintEngineFeatures类型是一个typedef为[QFlags](index.htm)\u003cPaintEngineFeature\u003e 。它存储PaintEngineFeature值的或组合。

```
QPaintEngine.PolygonDrawMode
```

| Constant | Value | Description |
| --- | --- | --- |
| `QPaintEngine.OddEvenMode` | `0` | 多边形应使用OddEven填充规则绘制。 |
| `QPaintEngine.WindingMode` | `1` | 多边形应使用绕线填充规则绘制。 |
| `QPaintEngine.ConvexMode` | `2` | 多边形是凸多边形，并可以使用提供的专门的算法，其中绘制。 |
| `QPaintEngine.PolylineMode` | `3` | 多边形的唯一的轮廓应绘制。 |

```
QPaintEngine.Type
```

| Constant | Value | Description |
| --- | --- | --- |
| `QPaintEngine.X11` | `0` |   |
| `QPaintEngine.Windows` | `1` |   |
| `QPaintEngine.MacPrinter` | `4` |   |
| `QPaintEngine.CoreGraphics` | `3` | Mac OS X的Quartz2D （核芯显卡） |
| `QPaintEngine.QuickDraw` | `2` | Mac OS X的的QuickDraw |
| `QPaintEngine.QWindowSystem` | `5` | Qt嵌入式Linux的 |
| `QPaintEngine.PostScript` | `6` |   |
| `QPaintEngine.OpenGL` | `7` |   |
| `QPaintEngine.Picture` | `8` | [QPicture](qpicture.html)格式 |
| `QPaintEngine.SVG` | `9` | 可伸缩矢量图形的XML格式 |
| `QPaintEngine.Raster` | `10` |   |
| `QPaintEngine.Direct3D` | `11` | 仅适用于Windows ，基于Direct3D的发动机 |
| `QPaintEngine.Pdf` | `12` | 可移植文档格式 |
| `QPaintEngine.OpenVG` | `13` |   |
| `QPaintEngine.User` | `50` | 第一个用户类型ID |
| `QPaintEngine.MaxUser` | `100` | 最后用户类型ID |
| `QPaintEngine.OpenGL2` | `14` |   |
| `QPaintEngine.PaintBuffer` | `15` |   |
| `QPaintEngine.Blitter` | `16` |   |

* * *

## Method Documentation

```
QPaintEngine.__init__ (self, PaintEngineFeatures features = 0)
```

创建一个绘图引擎与指定的FEATURESET_caps_。

```
bool QPaintEngine.begin (self, QPaintDevice pdev)
```

这种方法是抽象的，应在任何子类中重新实现。

重新实现这个函数绘制时初始化你的绘图引擎是开始绘制设备上_pdev_。返回True，如果初始化成功，否则返回False 。

**See also** [end](qpaintengine.html#end)（）和[isActive](qpaintengine.html#isActive)（ ） 。

```
QPaintEngine.drawEllipse (self, QRectF r)
```

重新实现这个函数来绘制，可以包含在矩形上最大的椭圆_rect_。

默认实现调用[drawPolygon](qpaintengine.html#drawPolygon)（ ） 。

```
QPaintEngine.drawEllipse (self, QRect r)
```

此函数的默认实现调用这个函数的浮点版本

```
QPaintEngine.drawImage (self, QRectF r, QImage pm, QRectF sr, Qt.ImageConversionFlags flags = Qt.AutoColor)
```

重新实现这个函数来绘制的部分_image_由指定的_sr_矩形在给定的_rectangle_使用给定的转换标志_flags_，将其转换为像素图。

```
QPaintEngine.drawLines (self, QLine lines)
```

默认实现拆分中的行列表_lines_成_lineCount_单独调用[drawPath](qpaintengine.html#drawPath)（）或[drawPolygon](qpaintengine.html#drawPolygon)（ ），这取决于绘图引擎的功能集。

```
QPaintEngine.drawLines (self, QLineF lines)
```

这是一个重载函数。

默认实现将第一_lineCount_在线路_lines_到[QLineF](qlinef.html)并调用这个函数的浮点版本。

```
QPaintEngine.drawPath (self, QPainterPath path)
```

默认实现忽略_path_而什么都不做。

```
QPaintEngine.drawPixmap (self, QRectF r, QPixmap pm, QRectF sr)
```

这种方法是抽象的，应在任何子类中重新实现。

重新实现这个函数来绘制的部分_pm_由指定的_sr_矩形在给定的_r_。

```
QPaintEngine.drawPoints (self, QPointF points)
```

绘制第一_pointCount_在缓冲点_points_

```
QPaintEngine.drawPoints (self, QPoint points)
```

绘制第一_pointCount_在缓冲点_points_

默认实现将第一_pointCount_在QPoints_points_到QPointFs并调用drawPoints的浮点版本。

```
QPaintEngine.drawPolygon (self, QPointF points, PolygonDrawMode mode)
```

重新实现这个虚函数绘制由定义的多边形_pointCount_在第一分_points_，使用模式_mode_。

**Note:**至少有一个的drawPolygon （ ）函数必须被重新实现。

```
QPaintEngine.drawPolygon (self, QPoint points, PolygonDrawMode mode)
```

这是一个重载函数。

重新实现这个虚函数绘制由定义的多边形_pointCount_在第一分_points_，使用模式_mode_。

**Note:**中的至少一个的[drawPolygon](qpaintengine.html#drawPolygon)（ ）函数必须被重新实现。

```
QPaintEngine.drawRects (self, QRect rects)
```

绘制第一_rectCount_在缓冲区中的矩形_rects_。此函数的默认实现调用[drawPath](qpaintengine.html#drawPath)（）或[drawPolygon](qpaintengine.html#drawPolygon)（ ），这取决于绘图引擎的功能集。

```
QPaintEngine.drawRects (self, QRectF rects)
```

这是一个重载函数。

默认实现将第一_rectCount_在缓冲区中的矩形_rects_到[QRectF](qrectf.html)并调用这个函数的浮点版本。

```
QPaintEngine.drawTextItem (self, QPointF p, QTextItem textItem)
```

这个函数绘制文本项_textItem_在位置_p_。这个函数的默认实现文本转换为[QPainterPath](qpainterpath.html)和油漆产生的路径。

```
QPaintEngine.drawTiledPixmap (self, QRectF r, QPixmap pixmap, QPointF s)
```

重新实现这个函数来绘制_pixmap_在给定的_rect_开始，在给定的_p_。像素图将被重复绘制，直到_rect_被充满。

```
bool QPaintEngine.end (self)
```

这种方法是抽象的，应在任何子类中重新实现。

重新实现此功能可将当前绘图设备上完成绘画。返回True，如果绘画是成功完成，否则返回False 。

**See also** [begin](qpaintengine.html#begin)（）和[isActive](qpaintengine.html#isActive)（ ） 。

```
bool QPaintEngine.hasFeature (self, PaintEngineFeatures feature)
```

如果绘图引擎支持指定，则返回True_feature_否则返回False 。

```
bool QPaintEngine.isActive (self)
```

返回True如果绘图引擎正在积极制订，否则返回False 。

**See also** [setActive](qpaintengine.html#setActive)（ ） 。

```
QPaintDevice QPaintEngine.paintDevice (self)
```

[

返回这款发动机是画上，如果画的是积极的装置，否则返回0 。

](qpaintdevice.html)

```
QPainter QPaintEngine.painter (self)
```

[

返回绘图引擎的画家。

```
QPaintEngine.setActive (self, bool newState)
```

设置绘图引擎的工作状态，以_state_。

](qpainter.html)

[**See also**](qpainter.html) [isActive](qpaintengine.html#isActive)（ ） 。

```
QPaintEngine.setPaintDevice (self, QPaintDevice device)
```

```
Type QPaintEngine.type (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

](qpaintengine.html#Type-enum)

[重新实现这个函数返回的绘图引擎](qpaintengine.html#Type-enum)[Type](qpaintengine.html#Type-enum)。

```
QPaintEngine.updateState (self, QPaintEngineState state)
```

这种方法是抽象的，应在任何子类中重新实现。

重新实现这个函数来更新绘图引擎的状态。

完成后，该功能是负责检查油漆引擎的当前_state_并更新已更改的属性。使用[QPaintEngineState.state](qpaintenginestate.html#state)（ ）函数来找出哪些属性，必须更新，​​然后使用相应的[get function](qpaintenginestate.html#getfunction)检索给定的属性的当前值。

**See also** [QPaintEngineState](qpaintenginestate.html)。