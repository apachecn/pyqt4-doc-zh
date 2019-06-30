# QPainter Class Reference

## [[QtGui](index.htm) module]

QPainter类的控件和其他绘图设备进行低级别的油画。[More...](#details)

通过继承[QStylePainter](qstylepainter.html)。

### Types

*   `enum CompositionMode { CompositionMode_SourceOver, CompositionMode_DestinationOver, CompositionMode_Clear, CompositionMode_Source, ..., RasterOp_SourceAndNotDestination }`
*   `class **[PixmapFragment](index.htm)**`
*   `enum PixmapFragmentHint { OpaqueHint }`
*   `class **[PixmapFragmentHints](index.htm)**`
*   `enum RenderHint { Antialiasing, TextAntialiasing, SmoothPixmapTransform, HighQualityAntialiasing, NonCosmeticDefaultPen }`
*   `class **[RenderHints](index.htm)**`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QPaintDevice)`
*   `QBrush background (self)`
*   `Qt.BGMode backgroundMode (self)`
*   `bool begin (self, QPaintDevice)`
*   `beginNativePainting (self)`
*   `QRectF boundingRect (self, QRectF rect, int flags, QString text)`
*   `QRect boundingRect (self, QRect rect, int flags, QString text)`
*   `QRectF boundingRect (self, QRectF rectangle, QString text, QTextOption option = QTextOption())`
*   `QRect boundingRect (self, int x, int y, int w, int h, int flags, QString text)`
*   `QBrush brush (self)`
*   `QPoint brushOrigin (self)`
*   `QRectF clipBoundingRect (self)`
*   `QPainterPath clipPath (self)`
*   `QRegion clipRegion (self)`
*   `QMatrix combinedMatrix (self)`
*   `QTransform combinedTransform (self)`
*   `CompositionMode compositionMode (self)`
*   `QPaintDevice device (self)`
*   `QMatrix deviceMatrix (self)`
*   `QTransform deviceTransform (self)`
*   `drawArc (self, QRectF rect, int a, int alen)`
*   `drawArc (self, QRect r, int a, int alen)`
*   `drawArc (self, int x, int y, int w, int h, int a, int alen)`
*   `drawChord (self, QRectF rect, int a, int alen)`
*   `drawChord (self, QRect rect, int a, int alen)`
*   `drawChord (self, int x, int y, int w, int h, int a, int alen)`
*   `drawConvexPolygon (self, QPointF point, ...)`
*   `drawConvexPolygon (self, QPolygonF poly)`
*   `drawConvexPolygon (self, QPoint point, ...)`
*   `drawConvexPolygon (self, QPolygon poly)`
*   `drawEllipse (self, QRectF r)`
*   `drawEllipse (self, QRect r)`
*   `drawEllipse (self, int x, int y, int w, int h)`
*   `drawEllipse (self, QPointF center, float rx, float ry)`
*   `drawEllipse (self, QPoint center, int rx, int ry)`
*   `drawGlyphRun (self, QPointF position, QGlyphRun glyphRun)`
*   `drawImage (self, QRectF targetRect, QImage image, QRectF sourceRect, Qt.ImageConversionFlags flags = Qt.AutoColor)`
*   `drawImage (self, QRect targetRect, QImage image, QRect sourceRect, Qt.ImageConversionFlags flags = Qt.AutoColor)`
*   `drawImage (self, QPointF p, QImage image, QRectF sr, Qt.ImageConversionFlags flags = Qt.AutoColor)`
*   `drawImage (self, QPoint p, QImage image, QRect sr, Qt.ImageConversionFlags flags = Qt.AutoColor)`
*   `drawImage (self, QRectF r, QImage image)`
*   `drawImage (self, QRect r, QImage image)`
*   `drawImage (self, QPointF p, QImage image)`
*   `drawImage (self, QPoint p, QImage image)`
*   `drawImage (self, int x, int y, QImage image, int sx = 0, int sy = 0, int sw = -1, int sh = -1, Qt.ImageConversionFlags flags = Qt.AutoColor)`
*   `drawLine (self, QLineF l)`
*   `drawLine (self, QLine line)`
*   `drawLine (self, int x1, int y1, int x2, int y2)`
*   `drawLine (self, QPoint p1, QPoint p2)`
*   `drawLine (self, QPointF p1, QPointF p2)`
*   `drawLines (self, QLineF line, ...)`
*   `drawLines (self, list-of-QLineF lines)`
*   `drawLines (self, QPointF pointPair, ...)`
*   `drawLines (self, list-of-QPointF pointPairs)`
*   `drawLines (self, QLine line, ...)`
*   `drawLines (self, list-of-QLine lines)`
*   `drawLines (self, QPoint pointPair, ...)`
*   `drawLines (self, list-of-QPoint pointPairs)`
*   `drawPath (self, QPainterPath path)`
*   `drawPicture (self, QPointF p, QPicture picture)`
*   `drawPicture (self, int x, int y, QPicture p)`
*   `drawPicture (self, QPoint pt, QPicture p)`
*   `drawPie (self, QRectF rect, int a, int alen)`
*   `drawPie (self, QRect rect, int a, int alen)`
*   `drawPie (self, int x, int y, int w, int h, int a, int alen)`
*   `drawPixmap (self, QRectF targetRect, QPixmap pixmap, QRectF sourceRect)`
*   `drawPixmap (self, QRect targetRect, QPixmap pixmap, QRect sourceRect)`
*   `drawPixmap (self, QPointF p, QPixmap pm)`
*   `drawPixmap (self, QPoint p, QPixmap pm)`
*   `drawPixmap (self, QRect r, QPixmap pm)`
*   `drawPixmap (self, int x, int y, QPixmap pm)`
*   `drawPixmap (self, int x, int y, int w, int h, QPixmap pm)`
*   `drawPixmap (self, int x, int y, int w, int h, QPixmap pm, int sx, int sy, int sw, int sh)`
*   `drawPixmap (self, int x, int y, QPixmap pm, int sx, int sy, int sw, int sh)`
*   `drawPixmap (self, QPointF p, QPixmap pm, QRectF sr)`
*   `drawPixmap (self, QPoint p, QPixmap pm, QRect sr)`
*   `drawPixmapFragments (self, list-of-QPainter.PixmapFragment fragments, QPixmap pixmap, PixmapFragmentHints hints = 0)`
*   `drawPixmapFragments (self, list-of-QRectF targetRects, list-of-QRectF sourceRects, QPixmap pixmap, PixmapFragmentHints hints = 0)`
*   `drawPoint (self, QPointF p)`
*   `drawPoint (self, int x, int y)`
*   `drawPoint (self, QPoint p)`
*   `drawPoints (self, QPointF point, ...)`
*   `drawPoints (self, QPolygonF points)`
*   `drawPoints (self, QPoint point, ...)`
*   `drawPoints (self, QPolygon points)`
*   `drawPolygon (self, QPointF point, ...)`
*   `drawPolygon (self, QPolygonF points, Qt.FillRule fillRule = Qt.OddEvenFill)`
*   `drawPolygon (self, QPoint point, ...)`
*   `drawPolygon (self, QPolygon points, Qt.FillRule fillRule = Qt.OddEvenFill)`
*   `drawPolyline (self, QPointF point, ...)`
*   `drawPolyline (self, QPolygonF polyline)`
*   `drawPolyline (self, QPoint point, ...)`
*   `drawPolyline (self, QPolygon polyline)`
*   `drawRect (self, QRectF rect)`
*   `drawRect (self, int x, int y, int w, int h)`
*   `drawRect (self, QRect r)`
*   `drawRects (self, QRectF rect, ...)`
*   `drawRects (self, list-of-QRectF rects)`
*   `drawRects (self, QRect rect, ...)`
*   `drawRects (self, list-of-QRect rects)`
*   `drawRoundedRect (self, QRectF rect, float xRadius, float yRadius, Qt.SizeMode mode = Qt.AbsoluteSize)`
*   `drawRoundedRect (self, int x, int y, int w, int h, float xRadius, float yRadius, Qt.SizeMode mode = Qt.AbsoluteSize)`
*   `drawRoundedRect (self, QRect rect, float xRadius, float yRadius, Qt.SizeMode mode = Qt.AbsoluteSize)`
*   `drawRoundRect (self, QRectF r, int xRound = 25, int yRound = 25)`
*   `drawRoundRect (self, int x, int y, int w, int h, int xRound = 25, int yRound = 25)`
*   `drawRoundRect (self, QRect r, int xRound = 25, int yRound = 25)`
*   `drawStaticText (self, QPointF topLeftPosition, QStaticText staticText)`
*   `drawStaticText (self, QPoint p, QStaticText staticText)`
*   `drawStaticText (self, int x, int y, QStaticText staticText)`
*   `drawText (self, QPointF p, QString s)`
*   `QRectF boundingRect drawText (self, QRectF rectangle, int flags, QString text)`
*   `QRect boundingRect drawText (self, QRect rectangle, int flags, QString text)`
*   `drawText (self, QRectF rectangle, QString text, QTextOption option = QTextOption())`
*   `drawText (self, QPoint p, QString s)`
*   `QRect boundingRect drawText (self, int x, int y, int width, int height, int flags, QString text)`
*   `drawText (self, int x, int y, QString s)`
*   `drawTiledPixmap (self, QRectF rectangle, QPixmap pixmap, QPointF pos = QPointF())`
*   `drawTiledPixmap (self, QRect rectangle, QPixmap pixmap, QPoint pos = QPoint())`
*   `drawTiledPixmap (self, int x, int y, int width, int height, QPixmap pixmap, int sx = 0, int sy = 0)`
*   `bool end (self)`
*   `endNativePainting (self)`
*   `eraseRect (self, QRectF)`
*   `eraseRect (self, QRect rect)`
*   `eraseRect (self, int x, int y, int w, int h)`
*   `fillPath (self, QPainterPath path, QBrush brush)`
*   `fillRect (self, QRectF, QBrush)`
*   `fillRect (self, QRect, QBrush)`
*   `fillRect (self, int x, int y, int w, int h, QBrush b)`
*   `fillRect (self, QRectF, QColor color)`
*   `fillRect (self, QRect, QColor color)`
*   `fillRect (self, int x, int y, int w, int h, QColor b)`
*   `fillRect (self, int x, int y, int w, int h, Qt.GlobalColor c)`
*   `fillRect (self, QRect r, Qt.GlobalColor c)`
*   `fillRect (self, QRectF r, Qt.GlobalColor c)`
*   `fillRect (self, int x, int y, int w, int h, Qt.BrushStyle style)`
*   `fillRect (self, QRect r, Qt.BrushStyle style)`
*   `fillRect (self, QRectF r, Qt.BrushStyle style)`
*   `QFont font (self)`
*   `QFontInfo fontInfo (self)`
*   `QFontMetrics fontMetrics (self)`
*   `bool hasClipping (self)`
*   `initFrom (self, QWidget widget)`
*   `bool isActive (self)`
*   `Qt.LayoutDirection layoutDirection (self)`
*   `QMatrix matrix (self)`
*   `bool matrixEnabled (self)`
*   `float opacity (self)`
*   `QPaintEngine paintEngine (self)`
*   `QPen pen (self)`
*   `RenderHints renderHints (self)`
*   `resetMatrix (self)`
*   `resetTransform (self)`
*   `restore (self)`
*   `rotate (self, float a)`
*   `save (self)`
*   `scale (self, float sx, float sy)`
*   `setBackground (self, QBrush bg)`
*   `setBackgroundMode (self, Qt.BGMode mode)`
*   `setBrush (self, QBrush brush)`
*   `setBrush (self, Qt.BrushStyle style)`
*   `setBrushOrigin (self, QPointF)`
*   `setBrushOrigin (self, int x, int y)`
*   `setBrushOrigin (self, QPoint p)`
*   `setClipPath (self, QPainterPath path, Qt.ClipOperation operation = Qt.ReplaceClip)`
*   `setClipping (self, bool enable)`
*   `setClipRect (self, QRectF rectangle, Qt.ClipOperation operation = Qt.ReplaceClip)`
*   `setClipRect (self, int x, int y, int width, int height, Qt.ClipOperation operation = Qt.ReplaceClip)`
*   `setClipRect (self, QRect rectangle, Qt.ClipOperation operation = Qt.ReplaceClip)`
*   `setClipRegion (self, QRegion region, Qt.ClipOperation operation = Qt.ReplaceClip)`
*   `setCompositionMode (self, CompositionMode mode)`
*   `setFont (self, QFont f)`
*   `setLayoutDirection (self, Qt.LayoutDirection direction)`
*   `setMatrix (self, QMatrix matrix, bool combine = False)`
*   `setMatrixEnabled (self, bool enabled)`
*   `setOpacity (self, float opacity)`
*   `setPen (self, QColor color)`
*   `setPen (self, QPen pen)`
*   `setPen (self, Qt.PenStyle style)`
*   `setRenderHint (self, RenderHint hint, bool on = True)`
*   `setRenderHints (self, RenderHints hints, bool on = True)`
*   `setTransform (self, QTransform transform, bool combine = False)`
*   `setViewport (self, QRect viewport)`
*   `setViewport (self, int x, int y, int w, int h)`
*   `setViewTransformEnabled (self, bool enable)`
*   `setWindow (self, QRect window)`
*   `setWindow (self, int x, int y, int w, int h)`
*   `setWorldMatrix (self, QMatrix matrix, bool combine = False)`
*   `setWorldMatrixEnabled (self, bool enabled)`
*   `setWorldTransform (self, QTransform matrix, bool combine = False)`
*   `shear (self, float sh, float sv)`
*   `strokePath (self, QPainterPath path, QPen pen)`
*   `bool testRenderHint (self, RenderHint hint)`
*   `QTransform transform (self)`
*   `translate (self, QPointF offset)`
*   `translate (self, float dx, float dy)`
*   `translate (self, QPoint offset)`
*   `QRect viewport (self)`
*   `bool viewTransformEnabled (self)`
*   `QRect window (self)`
*   `QMatrix worldMatrix (self)`
*   `bool worldMatrixEnabled (self)`
*   `QTransform worldTransform (self)`

### Static Methods

*   `QPaintDevice redirected (QPaintDevice device, QPoint offset = None)`
*   `restoreRedirected (QPaintDevice device)`
*   `setRedirected (QPaintDevice device, QPaintDevice replacement, QPoint offset = QPoint())`

### Special Methods

*   `object __enter__ (self)`
*   `__exit__ (self, object type, object value, object traceback)`

* * *

## Detailed Description

QPainter类的控件和其他绘图设备进行低级别的油画。

QPainter提供了高度优化的函数来完成大部分的绘图GUI程序的要求。由此可以得出一切从简单的线条到复杂的形状像馅饼和和弦。它也可以绘制对齐的文本和像素图。通常情况下，它绘制一个“自然”的坐标系中，但它也可以做视图和世界的改造。 QPainter可以在继承的任何对象操作[QPaintDevice](qpaintdevice.html)类。

共同使用的QPainter的是里面的一个小部件的绘制事件：构建和自定义（如设置笔或刷子）的画家。再画。记住拉丝后销毁QPainter的对象。例如：

```
 void SimpleExampleWidget.paintEvent([QPaintEvent](qpaintevent.html) *)
 {
     QPainter painter(this);
     painter.setPen([Qt](qt.html).blue);
     painter.setFont([QFont](qfont.html)("Arial", 30));
     painter.drawText(rect(), [Qt](qt.html).AlignCenter, "Qt");
 }

```

QPainter的核心功能是绘图，但是这个类还提供了几个函数，允许您自定义的QPainter的设置和它的渲染质量，和其他人，使削波。此外，您可以控制不同的形状如何通过指定画家的组成模式合并在一起。

该[isActive](qpainter.html#isActive)（）函数表示的画家是否处于活动状态。画家被激活[begin](qpainter.html#begin)（ ）函数，而这需要一个构造函数[QPaintDevice](qpaintdevice.html)的说法。该[end](qpainter.html#end)（ ）函数，析构函数，停用它。

连同[QPaintDevice](qpaintdevice.html)和[QPaintEngine](qpaintengine.html)类， QPainter的形成的基础， Qt的涂料体系。 QPainter的是用于执行绘图操作的类。[QPaintDevice](qpaintdevice.html)表示可以涂在使用QPainter的一个装置。[QPaintEngine](qpaintengine.html)规定，画家用来绘制到不同类型的设备的接口。如果画家是活动的，[device](qpainter.html#device)（ ）返回绘制设备上的画家描绘，和[paintEngine](qpainter.html#paintEngine)（ ）返回的绘图引擎，该画家目前在运行。欲了解更多信息，请参阅[Paint System](index.htm)。

有时候我们需要让别人漆上不同寻常的[QPaintDevice](qpaintdevice.html)。 QPainter的支持静态函数来做到这一点，[setRedirected](index.htm#setRedirected)（ ） 。

**Warning:**当paintdevice是一个小部件， QPainter的只能内的paintEvent （）函数或在一个称为的paintEvent （功能）中使用，也就是说，除非[Qt.WA_PaintOutsidePaintEvent](qt.html#WidgetAttribute-enum)插件属性设置。在Mac OS X和Windows ，你只能在一个的paintEvent （ ）函数漆不管这个属性的设置。

### Settings

有几个设置，您可以自定义，以使根据您的喜好了QPainter绘制：

*   [font](qpainter.html#font)() is the font used for drawing text. If the painter [isActive](qpainter.html#isActive)(), you can retrieve information about the currently set font, and its metrics, using the [fontInfo](qpainter.html#fontInfo)() and [fontMetrics](qpainter.html#fontMetrics)() functions respectively.
*   [brush](qpainter.html#brush)() defines the color or pattern that is used for filling shapes.
*   [pen](qpainter.html#pen)() defines the color or stipple that is used for drawing lines or boundaries.
*   [backgroundMode](qpainter.html#backgroundMode)() defines whether there is a [background](qpainter.html#background)() or not, i.e it is either [Qt.OpaqueMode](qt.html#BGMode-enum) or [Qt.TransparentMode](qt.html#BGMode-enum).
*   [background](qpainter.html#background)() only applies when [backgroundMode](qpainter.html#backgroundMode)() is [Qt.OpaqueMode](qt.html#BGMode-enum) and [pen](qpainter.html#pen)() is a stipple. In that case, it describes the color of the background pixels in the stipple.
*   [brushOrigin](qpainter.html#brushOrigin)() defines the origin of the tiled brushes, normally the origin of widget's background.
*   [viewport](qpainter.html#viewport)(), [window](qpainter.html#window)(), [worldTransform](qpainter.html#worldTransform)() make up the painter's coordinate transformation system. For more information, see the [Coordinate Transformations](#coordinate-transformations) section and the [Coordinate System](index.htm) documentation.
*   [hasClipping](qpainter.html#hasClipping)() tells whether the painter clips at all. (The paint device clips, too.) If the painter clips, it clips to [clipRegion](qpainter.html#clipRegion)().
*   [layoutDirection](qpainter.html#layoutDirection)() defines the layout direction used by the painter when drawing text.
*   [worldMatrixEnabled](qpainter.html#worldMatrixEnabled)() tells whether world transformation is enabled.
*   [viewTransformEnabled](qpainter.html#viewTransformEnabled)() tells whether view transformation is enabled.

需要注意的是其中的一些设置反映在一些油漆设备的设置，比如[QWidget.font](qwidget.html#font-prop)（ ） 。该[QPainter.begin](qpainter.html#begin)（ ）函数（或等价的QPainter的构造函数）从绘制设备拷贝这些属性。

您可以在任何时候保存了QPainter的状态通过调用[save](qpainter.html#save)（ ）函数，它节省了内部堆栈中的所有可用的设置。该[restore](qpainter.html#restore)（ ）函数弹出他们回来。

### Drawing

QPainter提供了许多功能来绘制最原语：[drawPoint](qpainter.html#drawPoint)（ ）[drawPoints](qpainter.html#drawPoints)（ ）[drawLine](qpainter.html#drawLine)（ ）[drawRect](qpainter.html#drawRect)（ ）[drawRoundedRect](qpainter.html#drawRoundedRect)（ ）[drawEllipse](qpainter.html#drawEllipse)（ ）[drawArc](qpainter.html#drawArc)（ ）[drawPie](qpainter.html#drawPie)（ ）[drawChord](qpainter.html#drawChord)（ ）[drawPolyline](qpainter.html#drawPolyline)（ ）[drawPolygon](qpainter.html#drawPolygon)（ ）[drawConvexPolygon](qpainter.html#drawConvexPolygon)（）和[drawCubicBezier](index.htm#drawCubicBezier)（ ） 。这两个便利的功能，[drawRects](qpainter.html#drawRects)（）和[drawLines](qpainter.html#drawLines)（ ） ，绘制矩形或线条的给定数组中的给定数量[QRects](qrect.html) or [QLines](qline.html)使用当前画笔和画刷。

QPainter类还提供了[fillRect](qpainter.html#fillRect)（）函数，其填埋所述给定[QRect](qrect.html)用给定的[QBrush](qbrush.html)和[eraseRect](qpainter.html#eraseRect)（ ）函数，删除给定矩形内的区域。

所有这些功能都同时具有整数和浮点版本。

| ![](../img/qpainter-basicdrawing.png) | **Basic Drawing Example**该[Basic Drawing](index.htm)示例显示了如何使用QPainter类在各种不同的风格显示基本的图形元素。 |

如果您需要绘制一个形状复杂，特别是如果你需要重复这样做，考虑创建一个[QPainterPath](qpainterpath.html)并用它绘制[drawPath](qpainter.html#drawPath)（ ） 。

| **Painter Paths example**该[QPainterPath](qpainterpath.html)类提供一个容器，用于绘制操作，从而能够构造和重用的图形形状。该[Painter Paths](index.htm)例子显示了画家的路径如何可以用来构建复杂的形状进行渲染。 | ![](../img/qpainter-painterpaths.png) |

的QPainter还提供了[fillPath](qpainter.html#fillPath)（）函数，其填埋所述给定[QPainterPath](qpainterpath.html)用给定的[QBrush](qbrush.html)和[strokePath](qpainter.html#strokePath)（ ）函数绘制给定路径的轮廓（即描边路径） 。

另见[Vector Deformation](index.htm)演示展示了如何利用先进的矢量技术，用来绘制文本[QPainterPath](qpainterpath.html)时，[Gradients](index.htm)演示显示了不同类型的梯度是在Qt中可用的，并且[Path Stroking](index.htm)演示这显示了Qt内建的虚线样式，并显示自定义模式可以如何用来扩展现有模式的范围。

| [Vector Deformation](index.htm) | [Gradients](index.htm) | [Path Stroking](index.htm) |
| --- | --- | --- |
| ![](../img/qpainter-vectordeformation.png) | ![](../img/qpainter-gradients.png) | ![](../img/qpainter-pathstroking.png) |

有功能绘制像素图/图像，即[drawPixmap](qpainter.html#drawPixmap)（ ）[drawImage](qpainter.html#drawImage)（）和[drawTiledPixmap](qpainter.html#drawTiledPixmap)（ ） 。两[drawPixmap](qpainter.html#drawPixmap)（）和[drawImage](qpainter.html#drawImage)（）产生相同的结果，不同之处在于[drawPixmap](qpainter.html#drawPixmap)（ ）更快的屏幕，而[drawImage](qpainter.html#drawImage)（ ）可能会更快的[QPrinter](qprinter.html)或其他装置。

使用文本绘制完成时[drawText](qpainter.html#drawText)（ ） 。当你需要细粒度的定位，[boundingRect](qpainter.html#boundingRect)（ ）告诉你在哪里给定的[drawText](qpainter.html#drawText)（ ）命令将绘制。

有一个[drawPicture](qpainter.html#drawPicture)（）函数绘制的整个内容[QPicture](qpicture.html)。该[drawPicture](qpainter.html#drawPicture)（ ）函数是忽略所有画家的设置作为唯一功能[QPicture](qpicture.html)有它自己的设置。

### Rendering Quality

要获得使用QPainter的最佳渲染效果，你应该使用平台无关[QImage](qimage.html)油漆设备;即使用[QImage](qimage.html)将确保结果具有在任何平台上相同的像素表示。

QPainter类还提供了通过控制渲染质量的一种手段其[RenderHint](qpainter.html#RenderHint-enum)枚举和浮点精度支持：绘制原语所有的功能都有一个浮点版本。这些通常以与组合使用[QPainter.Antialiasing](qpainter.html#RenderHint-enum)呈现提示。

| ![](../img/qpainter-concentriccircles.png) | **Concentric Circles Example**该[Concentric Circles](index.htm)实例表明，可以绘制自定义部件在使用浮点精度和抗混叠得到改善渲染质量。应用程序的主窗口中显示其正在使用的精度和抗混叠的各种组合，得出了几个小部件。 |

该[RenderHint](qpainter.html#RenderHint-enum)枚举指定标志来QPainter的，可能会或可能不会被任何给定的发动机尊重。[QPainter.Antialiasing](qpainter.html#RenderHint-enum)表明发动机应该反锯齿原语的边缘，如果可能的话，[QPainter.TextAntialiasing](qpainter.html#RenderHint-enum)表明发动机应尽可能消除文字锯齿，而[QPainter.SmoothPixmapTransform](qpainter.html#RenderHint-enum)表明发动机应该使用一个平滑的pixmap变换算法。[HighQualityAntialiasing](qpainter.html#RenderHint-enum)是一个OpenGL的具体呈现提示，指示引擎应使用片断程序和离屏渲染的抗锯齿。

该[renderHints](qpainter.html#renderHints)（ ）函数返回一个标志，指定在这个画家将呈现提示。使用[setRenderHint](qpainter.html#setRenderHint)（ ）函数来设置或清除当前设置的[RenderHints](qpainter.html#RenderHint-enum)。

### Coordinate Transformations

通常情况下， QPainter的操作设备自己的坐标系统（通常是像素） ，但QPainter的具有坐标变换良好的支持。

| nop | [rotate](qpainter.html#rotate)() | [scale](qpainter.html#scale)() | [translate](qpainter.html#translate)() |
| --- | --- | --- | --- |
| ![](../img/qpainter-clock.png) | ![](../img/qpainter-rotation.png) | ![](../img/qpainter-scale.png) | ![](../img/qpainter-translation.png) |

最常用的变换是缩放，旋转，平移和剪切。使用[scale](qpainter.html#scale)（）函数以一个给定的偏移量来缩放坐标系中，[rotate](qpainter.html#rotate)（ ）函数则顺时针旋转和[translate](qpainter.html#translate)（）把它翻译出来（即增加一个给定的偏移量点） 。也可以使用捻坐标系原点周围的[shear](qpainter.html#shear)（）函数。请参阅[Affine Transformations](index.htm)演示了剪切坐标系统的可视化。

另见[Transformations](index.htm)例如，显示转变如何影响了QPainter的渲染图元的方式。尤其是，它显示了如何变换的顺序会影响结果。

| **Affine Transformations Demo**该[Affine Transformations](index.htm)演示显示了Qt的能力画上执行的操作仿射变换。该演示还允许用户尝试使用转换操作，并立即看到结果。 | ![](../img/qpainter-affinetransformations.png) |

所有穿越 - 操作上进行改造工作[worldTransform](qpainter.html#worldTransform)（ ） 。矩阵转换成在平面上的点到另一点。如需变换矩阵的更多信息，请参见[Coordinate System](index.htm)和[QTransform](qtransform.html)文档。

该[setWorldTransform](qpainter.html#setWorldTransform)（ ）函数可以更换或添加到当前设置的[worldTransform](qpainter.html#worldTransform)（ ） 。该[resetTransform](qpainter.html#resetTransform)（ ）函数重置的是用做任何转换[translate](qpainter.html#translate)（ ）[scale](qpainter.html#scale)（ ）[shear](qpainter.html#shear)（ ）[rotate](qpainter.html#rotate)（ ）[setWorldTransform](qpainter.html#setWorldTransform)（ ）[setViewport](qpainter.html#setViewport)（）和[setWindow](qpainter.html#setWindow)（）函数。该[deviceTransform](qpainter.html#deviceTransform)（ ）返回一个转换从逻辑坐标到平台相关的绘图设备的设备坐标的矩阵。后者的功能是对平台相关的手柄使用平台的绘画命令时，才需要，而平台没有做转换nativly 。

当使用QPainter的绘图，我们使用它，然后被转换成漆设备的物理坐标逻辑坐标指定点。逻辑坐标物理坐标的映射由QPainter的的处理[combinedTransform](qpainter.html#combinedTransform)（ ）的组合[viewport](qpainter.html#viewport)（）和[window](qpainter.html#window)（）和[worldTransform](qpainter.html#worldTransform)（ ） 。该[viewport](qpainter.html#viewport)（）表示物理坐标指定一个任意的矩形，则[window](qpainter.html#window)（ ）描述在逻辑坐标相同的矩形，并且[worldTransform](qpainter.html#worldTransform)（）是相同的变换矩阵。

另请参阅[Coordinate System](index.htm)

### Clipping

QPainter的可夹任何拉伸操作到一个矩形，区域，或一个矢量路径。使用功能的当前片段可[clipRegion](qpainter.html#clipRegion)（）和[clipPath](qpainter.html#clipPath)（ ） 。无论路径或地区是首选（快）取决于相关[paintEngine](qpainter.html#paintEngine)（ ） 。例如，本[QImage](qimage.html)绘图引擎更喜欢的路径，而X11的绘图引擎更喜欢的区域。设置一个剪辑的画家逻辑坐标进行。

经过了QPainter的裁剪，绘制设备也可能被裁剪。例如，大多数的部件夹了使用的子控件的像素，并且大多数打印机夹了接近纸张的边缘区域。这种额外的裁剪不受的返回值反映[clipRegion](qpainter.html#clipRegion)（）或[hasClipping](qpainter.html#hasClipping)（ ） 。

### Composition Modes

QPainter提供了该[CompositionMode](qpainter.html#CompositionMode-enum)枚举它定义了数字图像合成波特 - 达芙的规则，它描述了一个模型，结合在一个图像，源像素，在另一个图像中，目标像素。

的组合物中的两种最常见的形式是[Source](qpainter.html#CompositionMode-enum)和[SourceOver](qpainter.html#CompositionMode-enum)。[Source](qpainter.html#CompositionMode-enum)用于绘制不透明的物体上绘制设备。在这种模式下，在源代码中的每个像素将替换目的地中的相应像素。在[SourceOver](qpainter.html#CompositionMode-enum)组合模式，源对象是透明的，被描绘在目标之上。

请注意，组成转变经营pixelwise 。出于这个原因，有使用图形原语本身和它的边界矩形之间的差：该边界矩形中包含与α == 0 （即周围的原始像素）的像素。这些像素将复盖其他图像的像素，情感上清除那些，而原始的只有复盖其自身的区域。

| ![](../img/qpainter-compositiondemo.png) | **Composition Modes Demo**该[Composition Modes](index.htm)演示中，在Qt的demo目录可用，让你体验不同的组合方式，并立即看到结果。 |

### Limitations

如果您使用的坐标与Qt的基于光栅的绘图引擎，一定要注意这一点很重要，而坐标大于+ / - 215可以使用，超出该范围的坐标进行任何绘画不保证显示;绘图可能会被裁剪。这是由于使用的`short int`在执行。

通过Qt的抚摩产生的轮廓是只是一个近似值与时曲线形状处理。它是在不可能代表使用另一个贝塞尔曲线段Bezier曲线段的轮廓大多数情况下，与这样的Qt近似曲线概述通过使用几个较小的曲线。出于性能的考虑是有限制的Qt多少曲线使用这些轮廓，从而使用大画笔的宽度时，或缩放的轮廓误差增大。以产生轮廓线具有较小的误差，可以使用[QPainterPathStroker](qpainterpathstroker.html)类，它有它，让我们的用户指定的误差容限的setCurveThreshold成员函数。另一种解决方法是将路径多边形先转换，然后绘制多边形来代替。

### Performance

QPainter的是一个丰富的框架，它允许开发者做一个伟大的各种图形操作，如渐变，组成方式和矢量图形。和QPainter的可以在各种不同的硬件和软件堆栈做到这一点。当然硬件和软件的基本组合有一定的影响性能，并确保每一个运算速度快结合的组成模式，画笔，裁剪，转换等所有各种组合，是因为接近一个不可能完成的任务排列的号码。作为一种妥协，我们选择了QPainter的API和后端，在性能保证是一样好，我们可以合理地得到它的硬件和软件的结合给定的一个子集。

我们专注于为高性能引擎的后端是：

*   Raster - This backend implements all rendering in pure software and is always used to render into QImages. For optimal performance only use the format types [QImage.Format_ARGB32_Premultiplied](qimage.html#Format-enum), [QImage.Format_RGB32](qimage.html#Format-enum) or [QImage.Format_RGB16](qimage.html#Format-enum). Any other format, including [QImage.Format_ARGB32](qimage.html#Format-enum), has significantly worse performance. This engine is also used by default on Windows and on QWS. It can be used as default graphics system on any OS/hardware/software combination by passing `-graphicssystem raster` on the command line
*   OpenGL 2.0 (ES) - This backend is the primary backend for hardware accelerated graphics. It can be run on desktop machines and embedded devices supporting the OpenGL 2.0 or OpenGL/ES 2.0 specification. This includes most graphics chips produced in the last couple of years. The engine can be enabled by using QPainter onto a [QGLWidget](qglwidget.html) or by passing `-graphicssystem opengl` on the command line when the underlying system supports it.
*   OpenVG - This backend implements the Khronos standard for 2D and Vector Graphics. It is primarily for embedded devices with hardware support for OpenVG. The engine can be enabled by passing `-graphicssystem openvg` on the command line when the underlying system supports it.

这些操作是：

*   Simple transformations, meaning translation and scaling, pluss 0, 90, 180, 270 degree rotations.
*   `drawPixmap()` in combination with simple transformations and opacity with non-smooth transformation mode (`QPainter.SmoothPixmapTransform` not enabled as a render hint).
*   Rectangle fills with solid color, two-color linear gradients and simple transforms.
*   Rectangular clipping with simple transformations and intersect clip.
*   Composition Modes `QPainter.CompositionMode_Source` and [QPainter.CompositionMode_SourceOver](qpainter.html#CompositionMode-enum)
*   Rounded rectangle filling using solid color and two-color linear gradients fills.
*   3x3 patched pixmaps, via qDrawBorderPixmap.

此列表提供了一个迹象，其中的功能在一个应用程序的性能是至关重要的安全使用。对于某些设置，其他操作可能会快过，但使它们的广泛使用之前，建议进行基准测试和验证他们的系统，该软件将在年底运行。此外，有昂贵的操作是确定使用的情况下，例如当结果被缓存在一个[QPixmap](qpixmap.html)。

* * *

## Type Documentation

```
QPainter.CompositionMode
```

定义了支持数字图像合成的模式。组合模式用于指定如何在一个图像中的像素，源，在另一图像中，目的地合并像素。

请注意，按位光栅操作模式，表示一个RasterOp的前缀，仅本地支持的X11和光栅涂料引擎。这意味着，利用Mac上这些模式的唯一途径是通过一个[QImage](qimage.html)。文件中的RasterOp表示混合模式_not_支持笔和画笔与alpha分量。另外，在接通[QPainter.Antialiasing](qpainter.html#RenderHint-enum)渲染暗示将有效地禁用RasterOp的模式。

![](../img/qpainter-compositionmode1.png)

![](../img/qpainter-compositionmode2.png)

最常见的类型是SourceOver （通常被称为只是α混合），其中源像素被混合在目标像素的顶部在这样一种方式，光源的阿尔法分量定义像素的透明度。

当涂料设备是[QImage](qimage.html)中，图像的格式必须被设置为[Format_ARGB32Premultiplied](qimage.html#Format-enum) or [Format_ARGB32](qimage.html#Format-enum)对于该组合物的模式有任何效果。对于业绩的预乘的版本是首选格式。

当一个组成模式设置适用于所有运营商的绘画，钢笔，画笔，渐变和像素图/影像图。

| Constant | Value | Description |
| --- | --- | --- |
| `QPainter.CompositionMode_SourceOver` | `0` | 这是默认模式。源的alpha被用于混合的像素上的目标的上方。 |
| `QPainter.CompositionMode_DestinationOver` | `1` | 目的地的阿尔法用于混在一起的源像素的上方。这个模式是CompositionMode_SourceOver的倒数。 |
| `QPainter.CompositionMode_Clear` | `2` | 在目标的像素被清除（设置为完全透明）来源无关。 |
| `QPainter.CompositionMode_Source` | `3` | 输出是源像素。 （这意味着一个基本的复印操作，并是相同的SourceOver当源像素是不透明的） 。 |
| `QPainter.CompositionMode_Destination` | `4` | 的输出是目标像素。这意味着它们的混合没有任何效果。这个模式是CompositionMode_Source的倒数。 |
| `QPainter.CompositionMode_SourceIn` | `5` | 的输出是源，其中所述的α是减少了该目的的。 |
| `QPainter.CompositionMode_DestinationIn` | `6` | 输出目的地，其中所述α是减少了源的。这个模式是CompositionMode_SourceIn的倒数。 |
| `QPainter.CompositionMode_SourceOut` | `7` | 的输出是源，其中所述的α是减少了目的地的倒数。 |
| `QPainter.CompositionMode_DestinationOut` | `8` | 输出目的地，其中所述α是减少了源的倒数。这个模式是CompositionMode_SourceOut的倒数。 |
| `QPainter.CompositionMode_SourceAtop` | `9` | 源像素混合在目标的顶部，与源像素减少了目标像素的alpha的alpha 。 |
| `QPainter.CompositionMode_DestinationAtop` | `10` | 目标像素混合的信号源的顶部，与目标像素的alpha是减少了目标像素的alpha 。这个模式是CompositionMode_SourceAtop的倒数。 |
| `QPainter.CompositionMode_Xor` | `11` | 源，其阿尔法减少与目标的α的倒数，被合并与目的地，其阿尔法减小由源的α的倒数。 CompositionMode_Xor是不一样的按位异或运算。 |
| `QPainter.CompositionMode_Plus` | `12` | 无论是α和在源和目标像素的颜色被加在一起。 |
| `QPainter.CompositionMode_Multiply` | `13` | 的输出是源颜色乘以目的地。乘用白色的叶子的颜色不变的颜色，而与黑色的颜色相乘，产生黑色。 |
| `QPainter.CompositionMode_Screen` | `14` | 源和目标色彩反相，然后相乘。筛选与白色的颜色会产生白色的，而筛选的颜色与黑色的颜色保持不变。 |
| `QPainter.CompositionMode_Overlay` | `15` | 乘法或屏幕上的颜色取决于目标颜色。目标颜色与光源颜色的混合，以反映目标的亮度或暗度。 |
| `QPainter.CompositionMode_Darken` | `16` | 的源颜色和目标颜色较暗被选中。 |
| `QPainter.CompositionMode_Lighten` | `17` | 的源和目的色彩的打火机被选中。 |
| `QPainter.CompositionMode_ColorDodge` | `18` | 目标颜色变亮以反映源颜色。黑色源色彩会使目标色不变。 |
| `QPainter.CompositionMode_ColorBurn` | `19` | 目标颜色变暗以反映源颜色。白源色彩会使目标色不变。 |
| `QPainter.CompositionMode_HardLight` | `20` | 乘法或屏幕上的颜色取决于源颜色。光源的颜色会变浅目标颜色，而深源颜色会变暗目标颜色。 |
| `QPainter.CompositionMode_SoftLight` | `21` | 变暗或变亮的颜色取决于源颜色。类似CompositionMode_HardLight 。 |
| `QPainter.CompositionMode_Difference` | `22` | 减去的颜色从较轻的更暗。用白色喷漆反转目标颜色，而画有黑色会使目标色不变。 |
| `QPainter.CompositionMode_Exclusion` | `23` | 类似CompositionMode_Difference ，但具有较低的对比度。用白色喷漆反转目标颜色，而画有黑色会使目标色不变。 |
| `QPainter.RasterOp_SourceOrDestination` | `24` | 是否在源和目标像素（ SRC或DST ）的按位OR运算。 |
| `QPainter.RasterOp_SourceAndDestination` | `25` | 是否在源和目标像素（ SRC与DST ）的按位与运算。 |
| `QPainter.RasterOp_SourceXorDestination` | `26` | 是否在源和目标像素（ SRC XOR DST）的按位异或运算。 |
| `QPainter.RasterOp_NotSourceAndNotDestination` | `27` | 是否在源和目标像素的按位NOR运算（ （不SRC ）和（不是DST ） ） 。 |
| `QPainter.RasterOp_NotSourceOrNotDestination` | `28` | 是否在源和目标像素（ （不SRC ）或（不是DST ） ）按位与非操作。 |
| `QPainter.RasterOp_NotSourceXorDestination` | `29` | 是否在源像素被反转，然后相异或目的地（ （不SRC ） XOR dst）的按位运算。 |
| `QPainter.RasterOp_NotSource` | `30` | 是否在源像素反转（不是SRC）按位运算。 |
| `QPainter.RasterOp_NotSourceAndDestination` | `31` | 请问其中源是倒，然后相与与目标（ （不SRC ）和DST ）按位运算。 |
| `QPainter.RasterOp_SourceAndNotDestination` | `32` | 请问那里的源逻辑与运算倒目的地像素（ src和（不是DST ） ）按位运算。 |

**See also** [compositionMode](qpainter.html#compositionMode)（ ）[setCompositionMode](qpainter.html#setCompositionMode)（ ）[Composition Modes](qpainter.html#composition-modes)和[Image Composition Example](index.htm)。

```
QPainter.PixmapFragmentHint
```

| Constant | Value | Description |
| --- | --- | --- |
| `QPainter.OpaqueHint` | `0x01` | 表示该像素映像的片段要被绘制为不透明。不透明的碎片可能更快得出。 |

这个枚举被引入或修改的Qt 4.7 。

该PixmapFragmentHints类型是一个typedef为[QFlags](index.htm)\u003cPixmapFragmentHint\u003e 。它存储PixmapFragmentHint值的或组合。

**See also** [QPainter.drawPixmapFragments](qpainter.html#drawPixmapFragments)（）和[QPainter.PixmapFragment](index.htm)。

```
QPainter.RenderHint
```

Renderhints用于指定标志来[QPainter](qpainter.html)可能会或可能不会被任何给定的发动机尊重。

| Constant | Value | Description |
| --- | --- | --- |
| `QPainter.Antialiasing` | `0x01` | 表明发动机应该反锯齿原语的边缘，如果可能的。 |
| `QPainter.TextAntialiasing` | `0x02` | 表明发动机应尽可能消除文字锯齿。强制禁用抗锯齿文本，不要使用此提示。相反，设置[QFont.NoAntialias](qfont.html#StyleStrategy-enum)你的字体的风格策略。 |
| `QPainter.SmoothPixmapTransform` | `0x04` | 表明发动机应该使用一个平滑的pixmap变换算法（例如，双线性）而不是最近的邻居。 |
| `QPainter.HighQualityAntialiasing` | `0x08` | 一个OpenGL的具体呈现提示，指示引擎应使用片断程序和离屏渲染的抗锯齿。 |
| `QPainter.NonCosmeticDefaultPen` | `0x10` | 发动机应该解释钢笔的宽度为0 （否则使[QPen.isCosmetic](qpen.html#isCosmetic)（ ） ）作为一种非化妆笔为1的宽度。 |

该RenderHints类型是一个typedef为[QFlags](index.htm)\u003cRenderHint\u003e 。它存储RenderHint值的或组合。

**See also** [renderHints](qpainter.html#renderHints)（ ）[setRenderHint](qpainter.html#setRenderHint)（ ）[Rendering Quality](qpainter.html#rendering-quality)和[Concentric Circles Example](index.htm)。

* * *

## Method Documentation

```
QPainter.__init__ (self)
```

构造一个画家。

**See also** [begin](qpainter.html#begin)（）和[end](qpainter.html#end)（ ） 。

```
QPainter.__init__ (self, QPaintDevice)
```

构造一个画家的画开始油漆_device_马上。

此构造方便短命的画家，如：在[QWidget.paintEvent](qwidget.html#paintEvent)（ ），并应只能使用一次。该构造函数调用[begin](qpainter.html#begin)（ ）为您和[QPainter](qpainter.html)析构函数会自动调用[end](qpainter.html#end)（ ） 。

下面是一个使用例子[begin](qpainter.html#begin)（）和[end](qpainter.html#end)（）：

```
 void MyWidget.paintEvent([QPaintEvent](qpaintevent.html) *)
 {
     [QPainter](qpainter.html) p;
     p.begin(this);
     p.drawLine(...);        // drawing code
     p.end();
 }

```

使用此构造相同的例子：

```
 void MyWidget.paintEvent([QPaintEvent](qpaintevent.html) *)
 {
     [QPainter](qpainter.html) p(this);
     p.drawLine(...);        // drawing code
 }

```

由于构造函数不能提供反馈时，画家的初始化失败，你应该宁可使用[begin](qpainter.html#begin)（）和[end](qpainter.html#end)（ ）画上的外部设备，例如打印机。

**See also** [begin](qpainter.html#begin)（）和[end](qpainter.html#end)（ ） 。

```
QBrush QPainter.background (self)
```

[

返回当前背景刷。

](qbrush.html)

[**See also**](qbrush.html) [setBackground](qpainter.html#setBackground)（）和[Settings](qpainter.html#settings)。

```
Qt.BGMode QPainter.backgroundMode (self)
```

[

返回当前背景模式。

](qt.html#BGMode-enum)

[**See also**](qt.html#BGMode-enum) [setBackgroundMode](qpainter.html#setBackgroundMode)（）和[Settings](qpainter.html#settings)。

```
bool QPainter.begin (self, QPaintDevice)
```

开始画漆_device_如果成功返回True，否则返回False 。

请注意，所有画家的设置（[setPen](qpainter.html#setPen)（ ）[setBrush](qpainter.html#setBrush)（ ）等）被重置为默认时开始值（ ）被调用。

可能发生的错误是严重的问题，如这些：

```
 painter->begin(0); // impossible - paint device cannot be 0

 [QPixmap](qpixmap.html) image(0, 0);
 painter->begin(&image); // impossible - image.isNull() == true;

 painter->begin(myWidget);
 painter2->begin(myWidget); // impossible - only one painter at a time

```

请注意，大多数的时候，你可以使用一个构造函数，而不是开始（ ） ，而[end](qpainter.html#end)（ ）会自动在毁灭完成。

**Warning:**一种涂料设备只能由一个画家在同一时间内绘。

**Warning:**画上一个[QImage](qimage.html)与格式[QImage.Format_Indexed8](qimage.html#Format-enum)不被支持。

**See also** [end](qpainter.html#end)（）和[QPainter](qpainter.html#QPainter)（ ） 。

```
QPainter.beginNativePainting (self)
```

刷新绘画管道，并准备直接与基础图形上下文发出命令的用户。必须后跟调用[endNativePainting](qpainter.html#endNativePainting)（ ） 。

请注意，只有国家的基本绘图引擎的变化将被重置为各自的默认状态。我们重置状态可能会改变从发布到解除。以下状态重置目前在OpenGL的2引擎：

*   blending is disabled
*   the depth, stencil and scissor tests are disabled
*   the active texture unit is reset to 0
*   the depth mask, depth function and the clear depth are reset to their default values
*   the stencil mask, stencil operation and stencil function are reset to their default values
*   the current color is reset to solid white

如果，例如OpenGL的多边形模式是由内部的beginNativePaint用户改变（）/[endNativePainting](qpainter.html#endNativePainting)（）块，它不会被重置为默认状态[endNativePainting](qpainter.html#endNativePainting)（ ） 。下面是一个例子，显示了画家的命令和原OpenGL命令的混杂：

```
 [QPainter](qpainter.html) painter(this);
 painter.fillRect(0, 0, 128, 128, [Qt](qt.html).green);
 painter.beginNativePainting();

 glEnable(GL_SCISSOR_TEST);
 glScissor(0, 0, 64, 64);

 glClearColor(1, 0, 0, 1);
 glClear(GL_COLOR_BUFFER_BIT);

 glDisable(GL_SCISSOR_TEST);

 painter.endNativePainting();

```

此功能被引入Qt的4.6 。

**See also** [endNativePainting](qpainter.html#endNativePainting)（ ） 。

```
QRectF QPainter.boundingRect (self, QRectF rect, int flags, QString text)
```

[](qrectf.html)

[返回的矩形边界_text_因为当内给定的绘制它会出现_rectangle_用指定的_flags_使用当前设置的](qrectf.html)[font](qpainter.html#font)（）;即该函数告诉你在哪里[drawText](qpainter.html#drawText)（ ）函数将以此给予相同的参数时。

如果_text_在给定的不适合_rectangle_使用指定的_flags_，该函数返回所需要的矩形。

该_flags_参数是下列标志的按位或：

*   [Qt.AlignLeft](qt.html#AlignmentFlag-enum)
*   [Qt.AlignRight](qt.html#AlignmentFlag-enum)
*   [Qt.AlignHCenter](qt.html#AlignmentFlag-enum)
*   [Qt.AlignTop](qt.html#AlignmentFlag-enum)
*   [Qt.AlignBottom](qt.html#AlignmentFlag-enum)
*   [Qt.AlignVCenter](qt.html#AlignmentFlag-enum)
*   [Qt.AlignCenter](qt.html#AlignmentFlag-enum)
*   [Qt.TextSingleLine](qt.html#TextFlag-enum)
*   [Qt.TextExpandTabs](qt.html#TextFlag-enum)
*   [Qt.TextShowMnemonic](qt.html#TextFlag-enum)
*   [Qt.TextWordWrap](qt.html#TextFlag-enum)
*   [Qt.TextIncludeTrailingSpaces](qt.html#TextFlag-enum)

如果多个水平或几个的垂直对齐的标志被设置，所产生的取向是不确定的。

**See also** [drawText](qpainter.html#drawText)（ ）[Qt.Alignment](qt.html#AlignmentFlag-enum)和[Qt.TextFlag](qt.html#TextFlag-enum)。

```
QRect QPainter.boundingRect (self, QRect rect, int flags, QString text)
```

[](qrect.html)

```
QRectF QPainter.boundingRect (self, QRectF rectangle, QString text, QTextOption option = QTextOption())
```

[](qrectf.html)

```
QRect QPainter.boundingRect (self, int x, int y, int w, int h, int flags, QString text)
```

[

这是一个重载函数。

](qrect.html)

[返回的矩形边界_text_因为当内给定的绘制它会出现_rectangle_用指定的_flags_使用当前设置的](qrect.html)[font](qpainter.html#font)（ ） 。

```
QBrush QPainter.brush (self)
```

[

返回画家的当前画笔。

](qbrush.html)

[**See also**](qbrush.html) [QPainter.setBrush](qpainter.html#setBrush)（）和[Settings](qpainter.html#settings)。

```
QPoint QPainter.brushOrigin (self)
```

[

返回当前设置的画刷原点。

](qpoint.html)

[**See also**](qpoint.html) [setBrushOrigin](qpainter.html#setBrushOrigin)（）和[Settings](qpainter.html#settings)。

```
QRectF QPainter.clipBoundingRect (self)
```

[

返回如果有一个夹子当前剪辑的边框，否则返回一个空的矩形。注意裁剪区域是由于在逻辑坐标。

矩形边界是不能保证是紧张。

此功能被引入Qt的4.8 。

](qrectf.html)

[**See also**](qrectf.html) [setClipRect](qpainter.html#setClipRect)（ ）[setClipPath](qpainter.html#setClipPath)（）和[setClipRegion](qpainter.html#setClipRegion)（ ） 。

```
QPainterPath QPainter.clipPath (self)
```

[

返回当前剪辑的路径。请注意，剪辑路径，给出了逻辑坐标。

](qpainterpath.html)

[**Warning:**](qpainterpath.html) [QPainter](qpainter.html)没有明确地存储该组合的片段，因为这是由底层处理[QPaintEngine](qpaintengine.html)的，所以路径被重新按要求并转化到当前的逻辑坐标系统。这是一个潜在的昂贵的操作。

**See also** [setClipPath](qpainter.html#setClipPath)（ ）[clipRegion](qpainter.html#clipRegion)（）和[setClipping](qpainter.html#setClipping)（ ） 。

```
QRegion QPainter.clipRegion (self)
```

[

返回当前设置的裁剪区域。注意裁剪区域是由于在逻辑坐标。

](qregion.html)

[**Warning:**](qregion.html) [QPainter](qpainter.html)没有明确地存储该组合的片段，因为这是由底层处理[QPaintEngine](qpaintengine.html)的，所以路径被重新按要求并转化到当前的逻辑坐标系统。这是一个潜在的昂贵的操作。

**See also** [setClipRegion](qpainter.html#setClipRegion)（ ）[clipPath](qpainter.html#clipPath)（）和[setClipping](qpainter.html#setClipping)（ ） 。

```
QMatrix QPainter.combinedMatrix (self)
```

[](qmatrix.html)

```
QTransform QPainter.combinedTransform (self)
```

[

将转换矩阵结合当前窗口/视口和世界的改造。

](qtransform.html)

[**See also**](qtransform.html) [setWorldTransform](qpainter.html#setWorldTransform)（ ）[setWindow](qpainter.html#setWindow)（）和[setViewport](qpainter.html#setViewport)（ ） 。

```
CompositionMode QPainter.compositionMode (self)
```

[

返回当前的组成模式。

](qpainter.html#CompositionMode-enum)

[**See also**](qpainter.html#CompositionMode-enum) [CompositionMode](qpainter.html#CompositionMode-enum)和[setCompositionMode](qpainter.html#setCompositionMode)（ ） 。

```
QPaintDevice QPainter.device (self)
```

[

返回漆设备上这个画家正在画画，或者0，如果画家不活跃。

](qpaintdevice.html)

[**See also**](qpaintdevice.html) [isActive](qpainter.html#isActive)（ ） 。

```
QMatrix QPainter.deviceMatrix (self)
```

[](qmatrix.html)

```
QTransform QPainter.deviceTransform (self)
```

[

返回从转换逻辑坐标到平台相关的绘图设备的设备坐标的矩阵。

](qtransform.html)

[这个功能是_only_在平台相关的句柄（使用平台的绘画命令时需要](qtransform.html)[Qt.HANDLE](qt.html#HANDLE-typedef)），以及平台不nativly做转换。

该[QPaintEngine.PaintEngineFeature](qpaintengine.html#PaintEngineFeature-enum)枚举可以被查询，以确定是否该平台进行变换与否。

**See also** [worldTransform](qpainter.html#worldTransform)（）和[QPaintEngine.hasFeature](qpaintengine.html#hasFeature)（ ） 。

```
QPainter.drawArc (self, QRectF rect, int a, int alen)
```

绘制由给定的定义的弧_rectangle_，_startAngle_和_spanAngle_。

该_startAngle_和_spanAngle_必须以一定程度的十六分之一来指定，即一个完整的圆等于5760 （ 16 * 360 ） 。用于角度的正值逆时针意思而负值意味着顺时针方向。零度是在3点钟的位置。

| ![](../img/qpainter-arc.png) | 

```
 [QRectF](qrectf.html) rectangle(10.0, 20.0, 80.0, 60.0);
 int startAngle = 30 * 16;
 int spanAngle = 120 * 16;

 [QPainter](qpainter.html) painter(this);
 painter.drawArc(rectangle, startAngle, spanAngle);

```

 |

**See also** [drawPie](qpainter.html#drawPie)（ ）[drawChord](qpainter.html#drawChord)（）和[Coordinate System](index.htm)。

```
QPainter.drawArc (self, QRect r, int a, int alen)
```

这是一个重载函数。

绘制由给定的定义的弧_rectangle_，_startAngle_和_spanAngle_。

```
QPainter.drawArc (self, int x, int y, int w, int h, int a, int alen)
```

这是一个重载函数。

绘制由矩形起点在（定义弧_x_，_y_）用指定的_width_和_height_和给定的_startAngle_和_spanAngle_。

```
QPainter.drawChord (self, QRectF rect, int a, int alen)
```

绘制和弦由给定的定义_rectangle_，_startAngle_和_spanAngle_。和弦填充有电流[brush](qpainter.html#brush)（ ） 。

该startAngle和spanAngle必须以一定程度的十六分之一来指定，即一个完整的圆等于5760 （ 16 * 360 ） 。用于角度的正值逆时针意思而负值意味着顺时针方向。零度是在3点钟的位置。

| ![](../img/qpainter-chord.png) | 

```
 [QRectF](qrectf.html) rectangle(10.0, 20.0, 80.0, 60.0);
 int startAngle = 30 * 16;
 int spanAngle = 120 * 16;

 [QPainter](qpainter.html) painter(this);
 painter.drawChord(rect, startAngle, spanAngle);

```

 |

**See also** [drawArc](qpainter.html#drawArc)（ ）[drawPie](qpainter.html#drawPie)（）和[Coordinate System](index.htm)。

```
QPainter.drawChord (self, QRect rect, int a, int alen)
```

这是一个重载函数。

绘制和弦由给定的定义_rectangle_，_startAngle_和_spanAngle_。

```
QPainter.drawChord (self, int x, int y, int w, int h, int a, int alen)
```

这是一个重载函数。

绘制由矩形开始在定义的弦（_x_，_y_）用指定的_width_和_height_和给定的_startAngle_和_spanAngle_。

```
QPainter.drawConvexPolygon (self, QPointF point, ...)
```

绘制由第一定义的凸多边形_pointCount_阵列中的点_points_使用当前画笔。

| ![](../img/qpainter-polygon.png) | 

```
 static const [QPointF](qpointf.html) points[4] = {
     [QPointF](qpointf.html)(10.0, 80.0),
     [QPointF](qpointf.html)(20.0, 10.0),
     [QPointF](qpointf.html)(80.0, 30.0),
     [QPointF](qpointf.html)(90.0, 70.0)
 };

 [QPainter](qpainter.html) painter(this);
 painter.drawConvexPolygon(points, 4);

```

 |

第一点是隐式连接到最后一个点，该多边形被填充有电流[brush](qpainter.html#brush)（ ） 。如果所提供的多边形不是凸的，也就是说，它至少包含一个角度大于180度大，其结果是不确定的。

在某些平台上（例如， X11 ）时， drawConvexPolygon （）函数可以比快[drawPolygon](qpainter.html#drawPolygon)（）函数。

**See also** [drawPolygon](qpainter.html#drawPolygon)（ ）[drawPolyline](qpainter.html#drawPolyline)（）和[Coordinate System](index.htm)。

```
QPainter.drawConvexPolygon (self, QPolygonF poly)
```

这是一个重载函数。

绘制由第一定义的凸多边形_pointCount_阵列中的点_points_使用当前画笔。

```
QPainter.drawConvexPolygon (self, QPoint point, ...)
```

这是一个重载函数。

绘制由定义的凸多边形_polygon_使用当前画笔和画刷。

```
QPainter.drawConvexPolygon (self, QPolygon poly)
```

这是一个重载函数。

绘制由定义的凸多边形_polygon_使用当前画笔和画刷。

```
QPainter.drawEllipse (self, QRectF r)
```

绘制由指定所定义的椭圆_rectangle_。

一个实心椭圆的大小为_rectangle_。[size()](qrect.html#size)。一个描边椭圆的大小为_rectangle_。[size()](qrect.html#size)加上画笔的宽度。

| ![](../img/qpainter-ellipse.png) | 

```
 [QRectF](qrectf.html) rectangle(10.0, 20.0, 80.0, 60.0);

 [QPainter](qpainter.html) painter(this);
 painter.drawEllipse(rectangle);

```

 |

**See also** [drawPie](qpainter.html#drawPie)（）和[Coordinate System](index.htm)。

```
QPainter.drawEllipse (self, QRect r)
```

这是一个重载函数。

绘制由指定所定义的椭圆_rectangle_。

```
QPainter.drawEllipse (self, int x, int y, int w, int h)
```

这是一个重载函数。

绘制由矩形开始在所定义的椭圆（_x_，_y_）用给定的_width_和_height_。

```
QPainter.drawEllipse (self, QPointF center, float rx, float ry)
```

这是一个重载函数。

绘制定位在椭圆_center_与半径_rx_和_ry_。

此功能被引入Qt的4.4 。

```
QPainter.drawEllipse (self, QPoint center, int rx, int ry)
```

这是一个重载函数。

绘制定位在椭圆_center_与半径_rx_和_ry_。

此功能被引入Qt的4.4 。

```
QPainter.drawGlyphRun (self, QPointF position, QGlyphRun glyphRun)
```

绘制指定_glyphs_在给定的_position_。该_position_给出了基线的字形串的边缘。字形将从所选择的字体检索_glyphs_以及在由位置给定偏移_glyphs_。

此功能被引入Qt的4.8 。

**See also** [QGlyphRun.setRawFont](qglyphrun.html#setRawFont)（ ）[QGlyphRun.setPositions](qglyphrun.html#setPositions)（）和[QGlyphRun.setGlyphIndexes](qglyphrun.html#setGlyphIndexes)（ ） 。

```
QPainter.drawImage (self, QRectF targetRect, QImage image, QRectF sourceRect, Qt.ImageConversionFlags flags = Qt.AutoColor)
```

绘制矩形部分_source_的给定_image_进入_target_矩形的绘图设备。

**Note:**图像缩放以适合该矩形，如果两个图像和矩形大小不同意。

如果图像需要进行修改，以适应在较低分辨率的结果（例如，从32位转换为8位），使用_flags_指定你将如何喜欢这样的事情发生。

| 

```
 [QRectF](qrectf.html) target(10.0, 20.0, 80.0, 60.0);
 [QRectF](qrectf.html) source(0.0, 0.0, 70.0, 40.0);
 [QImage](qimage.html) image(":/../img/myImage.png");

 [QPainter](qpainter.html) painter(this);
 painter.drawImage(target, image, source);

```

 |

**See also** [drawPixmap](qpainter.html#drawPixmap)（ ） 。

```
QPainter.drawImage (self, QRect targetRect, QImage image, QRect sourceRect, Qt.ImageConversionFlags flags = Qt.AutoColor)
```

这是一个重载函数。

绘制矩形部分_source_的给定_image_进入_target_矩形的绘图设备。

**Note:**图像缩放以适合该矩形，如果两个图像和矩形大小不同意。

```
QPainter.drawImage (self, QPointF p, QImage image, QRectF sr, Qt.ImageConversionFlags flags = Qt.AutoColor)
```

这是一个重载函数。

绘制给定的_image_在给定的_point_。

```
QPainter.drawImage (self, QPoint p, QImage image, QRect sr, Qt.ImageConversionFlags flags = Qt.AutoColor)
```

这是一个重载函数。

绘制给定的_image_在给定的_point_。

```
QPainter.drawImage (self, QRectF r, QImage image)
```

这是一个重载函数。

绘制矩形部分_source_的给定_image_其原点在给定的_point_。

```
QPainter.drawImage (self, QRect r, QImage image)
```

这是一个重载函数。

绘制矩形部分_source_的给定_image_其原点在给定的_point_。

```
QPainter.drawImage (self, QPointF p, QImage image)
```

这是一个重载函数。

绘制给定的_image_在给定的_rectangle_。

**Note:**图像缩放以适合该矩形，如果两个图像和矩形大小不同意。

```
QPainter.drawImage (self, QPoint p, QImage image)
```

这是一个重载函数。

绘制给定的_image_在给定的_rectangle_。

**Note:**图像缩放以适合该矩形，如果两个图像和矩形大小不同意。

```
QPainter.drawImage (self, int x, int y, QImage image, int sx = 0, int sy = 0, int sw = -1, int sh = -1, Qt.ImageConversionFlags flags = Qt.AutoColor)
```

这是一个重载函数。

绘制图像时（_x_，_y_）通过复制的一部分_image_入漆设备。

（_x_，_y_）指定在绘制设备将要被绘制到左上点。 （_sx_，_sy_）指定左上角点_image_要被绘制。默认值是（0 ，0）。

（_sw_，_sh_）指定将要被绘制的图像的大小。默认的，（0， 0）（和负）指一路图像的右下角。

```
QPainter.drawLine (self, QLineF l)
```

绘制由定义的直线_line_。

| ![](../img/qpainter-line.png) | 

```
 [QLineF](qlinef.html) line(10.0, 80.0, 90.0, 20.0);

 [QPainter](qpainter.html)(this);
 painter.drawLine(line);

```

 |

**See also** [drawLines](qpainter.html#drawLines)（ ）[drawPolyline](qpainter.html#drawPolyline)（）和[Coordinate System](index.htm)。

```
QPainter.drawLine (self, QLine line)
```

这是一个重载函数。

绘制由定义的直线_line_。

```
QPainter.drawLine (self, int x1, int y1, int x2, int y2)
```

这是一个重载函数。

绘制一条线从_p1_至_p2_。

```
QPainter.drawLine (self, QPoint p1, QPoint p2)
```

这是一个重载函数。

绘制一条线从_p1_至_p2_。

```
QPainter.drawLine (self, QPointF p1, QPointF p2)
```

这是一个重载函数。

绘制一条线从（_x1_，_y1_）至（_x2_，_y2_），并设置当前画笔位置为（_x2_，_y2_） 。

```
QPainter.drawLines (self, QLineF line, ...)
```

绘制第一_lineCount_阵列中的行_lines_使用当前画笔。

**See also** [drawLine](qpainter.html#drawLine)（）和[drawPolyline](qpainter.html#drawPolyline)（ ） 。

```
QPainter.drawLines (self, list-of-QLineF lines)
```

这是一个重载函数。

绘制第一_lineCount_阵列中的行_lines_使用当前画笔。

```
QPainter.drawLines (self, QPointF pointPair, ...)
```

这是一个重载函数。

绘制第一_lineCount_阵列中的行_pointPairs_使用当前画笔。的线被指定为点对这样的项的数目_pointPairs_必须至少_lineCount_* 2 。

```
QPainter.drawLines (self, list-of-QPointF pointPairs)
```

这是一个重载函数。

绘制第一_lineCount_阵列中的行_pointPairs_使用当前画笔。

```
QPainter.drawLines (self, QLine line, ...)
```

这是一个重载函数。

绘制一条线为每对点的矢量_pointPairs_ using the current pen. If there is an odd number of points in the array, the last point will be ignored.

```
QPainter.drawLines (self, list-of-QLine lines)
```

这是一个重载函数。

绘制一条线为每对点的矢量_pointPairs_使用当前画笔。

```
QPainter.drawLines (self, QPoint pointPair, ...)
```

这是一个重载函数。

绘制集的列表中定义的行_lines_使用当前画笔和画刷。

```
QPainter.drawLines (self, list-of-QPoint pointPairs)
```

这是一个重载函数。

绘制集的列表中定义的行_lines_使用当前画笔和画刷。

```
QPainter.drawPath (self, QPainterPath path)
```

绘制给定的画家_path_使用当前笔的轮廓和当前画笔填充。

| ![](../img/qpainter-path.png) | 

```
 [QPainterPath](qpainterpath.html) path;
 path.moveTo(20, 80);
 path.lineTo(20, 30);
 path.cubicTo(80, 0, 50, 50, 80, 80);

 [QPainter](qpainter.html) painter(this);
 painter.drawPath(path);

```

 |

**See also** [the Painter Paths example](index.htm)和[the Vector Deformation demo](index.htm)。

```
QPainter.drawPicture (self, QPointF p, QPicture picture)
```

重播给定的_picture_在给定的_point_。

该[QPicture](qpicture.html)类是一个绘图设备，记录和重放[QPainter](qpainter.html)的命令。的图片序列画家命令IO设备在一个平台无关的格式。可以涂在一个部件或pixmap的一切也可以被存储在一个图像。

这个函数完全一样[QPicture.play](qpicture.html#play)（ ）调用时使用_point_=[QPoint](qpoint.html)（0 ，0）。

| 

```
 [QPicture](qpicture.html) picture;
 [QPointF](qpointf.html) point(10.0, 20.0)
 picture.load("drawing.pic");

 [QPainter](qpainter.html) painter(this);
 painter.drawPicture(0, 0, picture);

```

 |

**See also** [QPicture.play](qpicture.html#play)（ ） 。

```
QPainter.drawPicture (self, int x, int y, QPicture p)
```

这是一个重载函数。

重播给定的_picture_在给定的_point_。

```
QPainter.drawPicture (self, QPoint pt, QPicture p)
```

这是一个重载函数。

绘制给定的_picture_在点（_x_，_y_） 。

```
QPainter.drawPie (self, QRectF rect, int a, int alen)
```

绘制由指定所定义的扇形_rectangle_，_startAngle_和和_spanAngle_。

馅饼填充有电流[brush](qpainter.html#brush)（ ） 。

该startAngle和spanAngle必须以一定程度的十六分之一来指定，即一个完整的圆等于5760 （ 16 * 360 ） 。用于角度的正值逆时针意思而负值意味着顺时针方向。零度是在3点钟的位置。

| ![](../img/qpainter-pie.png) | 

```
 [QRectF](qrectf.html) rectangle(10.0, 20.0, 80.0, 60.0);
 int startAngle = 30 * 16;
 int spanAngle = 120 * 16;

 [QPainter](qpainter.html) painter(this);
 painter.drawPie(rectangle, startAngle, spanAngle);

```

 |

**See also** [drawEllipse](qpainter.html#drawEllipse)（ ）[drawChord](qpainter.html#drawChord)（）和[Coordinate System](index.htm)。

```
QPainter.drawPie (self, QRect rect, int a, int alen)
```

这是一个重载函数。

绘制由指定所定义的扇形_rectangle_，_startAngle_和和_spanAngle_。

```
QPainter.drawPie (self, int x, int y, int w, int h, int a, int alen)
```

这是一个重载函数。

绘制由矩形开始在定义的馅饼（_x_，_y_）用指定的_width_和_height_和给定的_startAngle_和_spanAngle_。

```
QPainter.drawPixmap (self, QRectF targetRect, QPixmap pixmap, QRectF sourceRect)
```

绘制矩形部分_source_的给定_pixmap_在给定的_target_在油漆设备。

**Note:**像素图进行缩放以适合该矩形，如果两个像素图和矩形大小不同意。

| 

```
 [QRectF](qrectf.html) target(10.0, 20.0, 80.0, 60.0);
 [QRectF](qrectf.html) source(0.0, 0.0, 70.0, 40.0);
 [QPixmap](qpixmap.html) pixmap(":myPixmap.png");

 [QPainter](qpainter.html)(this);
 painter.drawPixmap(target, image, source);

```

 |

If _pixmap_是[QBitmap](qbitmap.html)它被画成与正在使用的笔的颜色“设置”的位。如果backgroundMode是[Qt.OpaqueMode](qt.html#BGMode-enum)中，“未设置”位所使用的背景画笔的颜色绘制，如果backgroundMode是[Qt.TransparentMode](qt.html#BGMode-enum)中，“未设置”位是透明的。不支持位图绘制具有渐变或纹理的颜色。

**See also** [drawImage](qpainter.html#drawImage)（ ） 。

```
QPainter.drawPixmap (self, QRect targetRect, QPixmap pixmap, QRect sourceRect)
```

这是一个重载函数。

绘制矩形部分_source_的给定_pixmap_在给定的_target_在油漆设备。

**Note:**像素图进行缩放以适合该矩形，如果两个像素图和矩形大小不同意。

```
QPainter.drawPixmap (self, QPointF p, QPixmap pm)
```

这是一个重载函数。

绘制矩形部分_source_的给定_pixmap_其原点在给定的_point_。

```
QPainter.drawPixmap (self, QPoint p, QPixmap pm)
```

这是一个重载函数。

绘制矩形部分_source_的给定_pixmap_其原点在给定的_point_。

```
QPainter.drawPixmap (self, QRect r, QPixmap pm)
```

这是一个重载函数。

绘制给定的_pixmap_其原点在给定的_point_。

```
QPainter.drawPixmap (self, int x, int y, QPixmap pm)
```

这是一个重载函数。

绘制给定的_pixmap_其原点在给定的_point_。

```
QPainter.drawPixmap (self, int x, int y, int w, int h, QPixmap pm)
```

这是一个重载函数。

绘制给定的_pixmap_在位置（_x_，_y_） 。

```
QPainter.drawPixmap (self, int x, int y, int w, int h, QPixmap pm, int sx, int sy, int sw, int sh)
```

这是一个重载函数。

绘制给定的_pixmap_在给定的_rectangle_。

**Note:**像素图进行缩放以适合该矩形，如果两个像素图和矩形大小不同意。

```
QPainter.drawPixmap (self, int x, int y, QPixmap pm, int sx, int sy, int sw, int sh)
```

这是一个重载函数。

绘制_pixmap_成在位置（矩形_x_，_y_）用给定的_width_和_height_。

```
QPainter.drawPixmap (self, QPointF p, QPixmap pm, QRectF sr)
```

这是一个重载函数。

绘制与原点的矩形部分（_sx_，_sy_） ，宽度_sw_和高度_sh_，的给定_pixmap_，在点（_x_，_y_） ，具有一宽_w_及的高度_h_。如果SW或SH都等于零的像素映像的宽度/高度被使用，并且调整由偏移SX / SY ;

```
QPainter.drawPixmap (self, QPoint p, QPixmap pm, QRect sr)
```

这是一个重载函数。

绘制像素图在（_x_，_y_）通过复制的特定部分_pixmap_入漆设备。

（_x_，_y_）指定在绘制设备将要被绘制到左上点。 （_sx_，_sy_）指定左上角点_pixmap_要被绘制。默认值是（0 ，0）。

（_sw_，_sh_）指定像素要被绘制的大小。默认的，（0， 0）（和负）是指所有的方式向像素图的右下角。

```
QPainter.drawPixmapFragments (self, list-of-QPainter.PixmapFragment fragments, QPixmap pixmap, PixmapFragmentHints hints = 0)
```

此功能是用来绘制_pixmap_，或者一个子矩形_pixmap_，在不同的缩放，旋转和透明度多个位置。_fragments_是阵列_fragmentCount_元素指定用于绘制每个像素映射片段的参数。该_hints_参数可用于传递在绘制提示。

此功能可能比多次调用更快[drawPixmap](qpainter.html#drawPixmap)（） ，因为后端可以优化状态的变化。

此功能被引入Qt的4.7 。

**See also** [QPainter.PixmapFragment](index.htm)和[QPainter.PixmapFragmentHint](qpainter.html#PixmapFragmentHint-enum)。

```
QPainter.drawPixmapFragments (self, list-of-QRectF targetRects, list-of-QRectF sourceRects, QPixmap pixmap, PixmapFragmentHints hints = 0)
```

该_sourceRects_参数也可能没有。

此功能是用来绘制相同_pixmap_由指定多个目标和源矩形_targetRects_。如果_sourceRects_为0 ，整个像素映像将在每个目标矩形的呈现。该_hints_参数可用于传递在绘制提示。

此功能可能比多次调用更快[drawPixmap](qpainter.html#drawPixmap)（） ，因为后端可以优化状态的变化。

此功能被引入Qt的4.8 。

**See also** [QPainter.PixmapFragmentHint](qpainter.html#PixmapFragmentHint-enum)。

```
QPainter.drawPoint (self, QPointF p)
```

绘制一个单点在给定的_position_使用当前画笔的颜色。

**See also** [Coordinate System](index.htm)。

```
QPainter.drawPoint (self, int x, int y)
```

这是一个重载函数。

绘制一个单点在给定的_position_使用当前画笔的颜色。

```
QPainter.drawPoint (self, QPoint p)
```

这是一个重载函数。

绘制一个单点位置（_x_，_y_） 。

```
QPainter.drawPoints (self, QPointF point, ...)
```

绘制第一_pointCount_阵列中的点_points_使用当前画笔的颜色。

**See also** [Coordinate System](index.htm)。

```
QPainter.drawPoints (self, QPolygonF points)
```

这是一个重载函数。

绘制第一_pointCount_阵列中的点_points_使用当前画笔的颜色。

```
QPainter.drawPoints (self, QPoint point, ...)
```

这是一个重载函数。

绘制点的矢量_points_。

```
QPainter.drawPoints (self, QPolygon points)
```

这是一个重载函数。

绘制点的矢量_points_。

```
QPainter.drawPolygon (self, QPointF point, ...)
```

绘制由第一定义的多边形_pointCount_阵列中的点_points_使用当前画笔和画刷。

| ![](../img/qpainter-polygon.png) | 

```
 static const [QPointF](qpointf.html) points[4] = {
     [QPointF](qpointf.html)(10.0, 80.0),
     [QPointF](qpointf.html)(20.0, 10.0),
     [QPointF](qpointf.html)(80.0, 30.0),
     [QPointF](qpointf.html)(90.0, 70.0)
 };

 [QPainter](qpainter.html) painter(this);
 painter.drawPolygon(points, 4);

```

 |

第一点是隐式连接到最后一个点，该多边形被填充有电流[brush](qpainter.html#brush)（ ） 。

If _fillRule_ is [Qt.WindingFill](qt.html#FillRule-enum)中，多边形是用绕组填充算法填充。如果_fillRule_ is [Qt.OddEvenFill](qt.html#FillRule-enum)中，多边形是使用奇偶填充算法填充。看[Qt.FillRule](qt.html#FillRule-enum)对于这些填充规则的更详细的描述。

**See also** [drawConvexPolygon](qpainter.html#drawConvexPolygon)（ ）[drawPolyline](qpainter.html#drawPolyline)（）和[Coordinate System](index.htm)。

```
QPainter.drawPolygon (self, QPolygonF points, Qt.FillRule fillRule = Qt.OddEvenFill)
```

这是一个重载函数。

绘制由第一定义的多边形_pointCount_阵列中的点_points_。

```
QPainter.drawPolygon (self, QPoint point, ...)
```

```
QPainter.drawPolygon (self, QPolygon points, Qt.FillRule fillRule = Qt.OddEvenFill)
```

```
QPainter.drawPolyline (self, QPointF point, ...)
```

绘制由第一定义的折线_pointCount_在点_points_使用当前画笔。

请注意，与[drawPolygon](qpainter.html#drawPolygon)（ ）函数的最后一点是_not_连接到第一个，也不是漫天的折线。

| 

```
 static const [QPointF](qpointf.html) points[3] = {
     [QPointF](qpointf.html)(10.0, 80.0),
     [QPointF](qpointf.html)(20.0, 10.0),
     [QPointF](qpointf.html)(80.0, 30.0),
 };

 [QPainter](qpainter.html) painter(this);
 painter.drawPolyline(points, 3);

```

 |

**See also** [drawLines](qpainter.html#drawLines)（ ）[drawPolygon](qpainter.html#drawPolygon)（）和[Coordinate System](index.htm)。

```
QPainter.drawPolyline (self, QPolygonF polyline)
```

这是一个重载函数。

绘制由第一定义的折线_pointCount_在点_points_使用当前画笔。

```
QPainter.drawPolyline (self, QPoint point, ...)
```

```
QPainter.drawPolyline (self, QPolygon polyline)
```

这是一个重载函数。

绘制由给定的定义的折线_points_使用当前画笔。

```
QPainter.drawRect (self, QRectF rect)
```

绘制电流_rectangle_与当前的画笔和画刷。

一个填充矩形的大小为_rectangle_。大小（ ） 。一个描边矩形的大小为_rectangle_。大小（ ），再加上画笔的宽度。

| ![](../img/qpainter-rectangle.png) | 

```
 [QRectF](qrectf.html) rectangle(10.0, 20.0, 80.0, 60.0);

 [QPainter](qpainter.html) painter(this);
 painter.drawRect(rectangle);

```

 |

**See also** [drawRects](qpainter.html#drawRects)（ ）[drawPolygon](qpainter.html#drawPolygon)（）和[Coordinate System](index.htm)。

```
QPainter.drawRect (self, int x, int y, int w, int h)
```

这是一个重载函数。

绘制电流_rectangle_与当前的画笔和画刷。

```
QPainter.drawRect (self, QRect r)
```

这是一个重载函数。

与绘制左上角的矩形在（_x_，_y_），并用给定的_width_和_height_。

```
QPainter.drawRects (self, QRectF rect, ...)
```

绘制第一_rectCount_的给定_rectangles_使用当前画笔和画刷。

**See also** [drawRect](qpainter.html#drawRect)（ ） 。

```
QPainter.drawRects (self, list-of-QRectF rects)
```

这是一个重载函数。

绘制第一_rectCount_的给定_rectangles_使用当前画笔和画刷。

```
QPainter.drawRects (self, QRect rect, ...)
```

这是一个重载函数。

绘制给定的_rectangles_使用当前画笔和画刷。

```
QPainter.drawRects (self, list-of-QRect rects)
```

这是一个重载函数。

绘制给定的_rectangles_使用当前画笔和画刷。

```
QPainter.drawRoundedRect (self, QRectF rect, float xRadius, float yRadius, Qt.SizeMode mode = Qt.AbsoluteSize)
```

绘制一个矩形_rect_带有圆角。

该_xRadius_和_yRadius_参数指定限定的圆角矩形的角部的椭圆形的半径。何时_mode_ is [Qt.RelativeSize](qt.html#SizeMode-enum)，_xRadius_和_yRadius_在一半的矩形的宽度和高度的比例分别指定，并应在范围0.0至100.0 。

填充的矩形具有rect.size （的大小） 。一个描边矩形具有rect.size的大小（ ），再加上画笔的宽度。

| ![](../img/qpainter-roundrect.png) | 

```
 [QRectF](qrectf.html) rectangle(10.0, 20.0, 80.0, 60.0);

 [QPainter](qpainter.html) painter(this);
 painter.drawRoundedRect(rectangle, 20.0, 15.0);

```

 |

此功能被引入Qt的4.4 。

**See also** [drawRect](qpainter.html#drawRect)（）和[QPen](qpen.html)。

```
QPainter.drawRoundedRect (self, int x, int y, int w, int h, float xRadius, float yRadius, Qt.SizeMode mode = Qt.AbsoluteSize)
```

这是一个重载函数。

绘制一个矩形_rect_带有圆角。

此功能被引入Qt的4.4 。

```
QPainter.drawRoundedRect (self, QRect rect, float xRadius, float yRadius, Qt.SizeMode mode = Qt.AbsoluteSize)
```

这是一个重载函数。

绘制一个矩形_x_，_y_，_w_，_h_带有圆角。

此功能被引入Qt的4.4 。

```
QPainter.drawRoundRect (self, QRectF r, int xRound = 25, int yRound = 25)
```

```
QPainter.drawRoundRect (self, int x, int y, int w, int h, int xRound = 25, int yRound = 25)
```

```
QPainter.drawRoundRect (self, QRect r, int xRound = 25, int yRound = 25)
```

```
QPainter.drawStaticText (self, QPointF topLeftPosition, QStaticText staticText)
```

绘制给定的_staticText_在给定的_topLeftPosition_。

该文本将使用的字体和画家的改造集绘制。如果画家设置字体和/或转型是从用来初始化的布局有些出入[QStaticText](qstatictext.html)，则布局将不得不被重新计算。使用[QStaticText.prepare](qstatictext.html#prepare)（）来初始化_staticText_与字体和转型与它稍后将绘制。

If _topLeftPosition_是不一样的，当_staticText_被初始化，或当它被最后绘制，那么就会有翻译文本到新的位置时，会有轻微的开销。

**Note:**如果画家的转变不仿射，然后_staticText_将使用普通电话要绘制[drawText](qpainter.html#drawText)（ ） ，失去对性能改善的潜力。

**Note:**y位置被用作字体的顶部。

此功能被引入Qt的4.7 。

**See also** [QStaticText](qstatictext.html)。

```
QPainter.drawStaticText (self, QPoint p, QStaticText staticText)
```

这是一个重载函数。

绘制_staticText_在_topLeftPosition_。

**Note:**y位置被用作字体的顶部。

此功能被引入Qt的4.7 。

```
QPainter.drawStaticText (self, int x, int y, QStaticText staticText)
```

这是一个重载函数。

绘制_staticText_在坐标_left_和_top_。

**Note:**y位置被用作字体的顶部。

此功能被引入Qt的4.7 。

```
QPainter.drawText (self, QPointF p, QString s)
```

绘制给定的_text_与当前定义的文字方向，开始在给定的_position_。

此功能不处理换行符（ \ n）的，因为它不能将文本分成多行，并且它不能显示换行符。使用QPainter.drawText （ ）重载采用一个矩形，而是如果要绘制与换行符多行文本，或者如果您希望文本换行。

默认情况下，[QPainter](qpainter.html)绘制文本抗锯齿。

**Note:**y位置被用作字体的基线。

```
QRectF boundingRect QPainter.drawText (self, QRectF rectangle, int flags, QString text)
```

[](qrectf.html)

```
QRect boundingRect QPainter.drawText (self, QRect rectangle, int flags, QString text)
```

[

```
QPainter.drawText (self, QRectF rectangle, QString text, QTextOption option = QTextOption())
```

```
QPainter.drawText (self, QPoint p, QString s)
```

](qrect.html)

```
QRect boundingRect QPainter.drawText (self, int x, int y, int width, int height, int flags, QString text)
```

[

```
QPainter.drawText (self, int x, int y, QString s)
```

```
QPainter.drawTiledPixmap (self, QRectF rectangle, QPixmap pixmap, QPointF pos = QPointF())
```

绘制的瓷砖_pixmap_，里面的定_rectangle_其原点在给定的_position_。

](qrect.html)

[调用drawTiledPixmap （ ）类似于调用](qrect.html)[drawPixmap](qpainter.html#drawPixmap)（ ）多次填写（瓦）的面积与像素图，而是取决于不同的底层窗口系统上可能效率更高。

**See also** [drawPixmap](qpainter.html#drawPixmap)（ ） 。

```
QPainter.drawTiledPixmap (self, QRect rectangle, QPixmap pixmap, QPoint pos = QPoint())
```

这是一个重载函数。

绘制的瓷砖_pixmap_，里面的定_rectangle_其原点在给定的_position_。

```
QPainter.drawTiledPixmap (self, int x, int y, int width, int height, QPixmap pixmap, int sx = 0, int sy = 0)
```

这是一个重载函数。

绘制的瓷砖_pixmap_在指定的矩形。

（_x_，_y_）指定在绘制设备将要被绘制到左上顶点;用给定的_width_和_height_。 （_sx_，_sy_）指定在左上角点_pixmap_要被绘制的，这默认为（0 ，0）。

```
bool QPainter.end (self)
```

完画。而画中使用的任何资源被释放。你通常不需要调用这个，因为它是由所谓的析构函数。

返回True如果画家不再有效，否则返回False 。

**See also** [begin](qpainter.html#begin)（）和[isActive](qpainter.html#isActive)（ ） 。

```
QPainter.endNativePainting (self)
```

后手动发布本地绘制命令恢复画家。让画家还原它依赖于调用任何其他画家的命令之前的任何原生状态。

此功能被引入Qt的4.6 。

**See also** [beginNativePainting](qpainter.html#beginNativePainting)（ ） 。

```
QPainter.eraseRect (self, QRectF)
```

擦除内部给定的区域_rectangle_。相当于调用

```
 fillRect(rectangle, background()).

```

**See also** [fillRect](qpainter.html#fillRect)（ ） 。

```
QPainter.eraseRect (self, QRect rect)
```

这是一个重载函数。

擦除内部给定的区域_rectangle_。

```
QPainter.eraseRect (self, int x, int y, int w, int h)
```

这是一个重载函数。

擦除矩形开始内部的区域处（_x_，_y_）用给定的_width_和_height_。

```
QPainter.fillPath (self, QPainterPath path, QBrush brush)
```

充填所给的_path_使用给定的_brush_。大纲中未画出。

或者，您可以指定一个[QColor](qcolor.html)代替[QBrush](qbrush.html);的[QBrush](qbrush.html)构造函数（服用[QColor](qcolor.html)参数）会自动创建一个坚实的图案画笔。

**See also** [drawPath](qpainter.html#drawPath)（ ） 。

```
QPainter.fillRect (self, QRectF, QBrush)
```

充填所给的_rectangle_与_brush_规定。

或者，您可以指定一个[QColor](qcolor.html)代替[QBrush](qbrush.html);的[QBrush](qbrush.html)构造函数（服用[QColor](qcolor.html)参数）会自动创建一个坚实的图案画笔。

**See also** [drawRect](qpainter.html#drawRect)（ ） 。

```
QPainter.fillRect (self, QRect, QBrush)
```

这是一个重载函数。

填充矩形开始时（_x_，_y_）用给定的_width_和_height_使用刷子_style_规定。

此功能被引入Qt的4.5 。

```
QPainter.fillRect (self, int x, int y, int w, int h, QBrush b)
```

这是一个重载函数。

充填所给的_rectangle_与刷_style_规定。

此功能被引入Qt的4.5 。

```
QPainter.fillRect (self, QRectF, QColor color)
```

这是一个重载函数。

充填所给的_rectangle_与刷_style_规定。

此功能被引入Qt的4.5 。

```
QPainter.fillRect (self, QRect, QColor color)
```

这是一个重载函数。

充填所给的_rectangle_用指定的_brush_。

```
QPainter.fillRect (self, int x, int y, int w, int h, QColor b)
```

这是一个重载函数。

充填所给的_rectangle_与_color_规定。

此功能被引入Qt的4.5 。

```
QPainter.fillRect (self, int x, int y, int w, int h, Qt.GlobalColor c)
```

这是一个重载函数。

充填所给的_rectangle_与_color_规定。

此功能被引入Qt的4.5 。

```
QPainter.fillRect (self, QRect r, Qt.GlobalColor c)
```

这是一个重载函数。

填充矩形开始时（_x_，_y_）用给定的_width_和_height_，使用给定的_brush_。

```
QPainter.fillRect (self, QRectF r, Qt.GlobalColor c)
```

这是一个重载函数。

填充矩形开始时（_x_，_y_）用给定的_width_和_height_，使用给定的_color_。

此功能被引入Qt的4.5 。

```
QPainter.fillRect (self, int x, int y, int w, int h, Qt.BrushStyle style)
```

这是一个重载函数。

填充矩形开始时（_x_，_y_）用给定的_width_和_height_，使用给定的_color_。

此功能被引入Qt的4.5 。

```
QPainter.fillRect (self, QRect r, Qt.BrushStyle style)
```

这是一个重载函数。

充填所给的_rectangle_用指定的_color_。

此功能被引入Qt的4.5 。

```
QPainter.fillRect (self, QRectF r, Qt.BrushStyle style)
```

这是一个重载函数。

充填所给的_rectangle_用指定的_color_。

此功能被引入Qt的4.5 。

```
QFont QPainter.font (self)
```

[

返回用于绘制文本的当前设置的字体。

](qfont.html)

[**See also**](qfont.html) [setFont](qpainter.html#setFont)（ ）[drawText](qpainter.html#drawText)（）和[Settings](qpainter.html#settings)。

```
QFontInfo QPainter.fontInfo (self)
```

[

返回画家的字体信息，如果画家是积极的。否则，返回值是不确定的。

](qfontinfo.html)

[**See also**](qfontinfo.html) [font](qpainter.html#font)（ ）[isActive](qpainter.html#isActive)（）和[Settings](qpainter.html#settings)。

```
QFontMetrics QPainter.fontMetrics (self)
```

[

返回的字体规格为画家当画家是积极的。否则，返回值是不确定的。

](qfontmetrics.html)

[**See also**](qfontmetrics.html) [font](qpainter.html#font)（ ）[isActive](qpainter.html#isActive)（）和[Settings](qpainter.html#settings)。

```
bool QPainter.hasClipping (self)
```

返回True如果裁剪已经设置，否则返回False 。

**See also** [setClipping](qpainter.html#setClipping)（）和[Clipping](qpainter.html#clipping)。

```
QPainter.initFrom (self, QWidget widget)
```

初始化画家的笔，背景和字体一样给出_widget_。当画家被打开的这个功能是自动调用[QWidget](qwidget.html)。

**See also** [begin](qpainter.html#begin)（）和[Settings](qpainter.html#settings)。

```
bool QPainter.isActive (self)
```

返回True如果[begin](qpainter.html#begin)（ ）被调用，并[end](qpainter.html#end)（ ）尚未被调用，否则返回False 。

**See also** [begin](qpainter.html#begin)（）和[QPaintDevice.paintingActive](qpaintdevice.html#paintingActive)（ ） 。

```
Qt.LayoutDirection QPainter.layoutDirection (self)
```

[

返回绘制文本时所使用的画家布局方向。

](qt.html#LayoutDirection-enum)

[**See also**](qt.html#LayoutDirection-enum) [QTextOption.textDirection](qtextoption.html#textDirection)（ ）[setLayoutDirection](qpainter.html#setLayoutDirection)（ ）[drawText](qpainter.html#drawText)（）和[Settings](qpainter.html#settings)。

```
QMatrix QPainter.matrix (self)
```

[

```
bool QPainter.matrixEnabled (self)
```

```
float QPainter.opacity (self)
```

返回画家的不透明度。默认值是1。

这个函数中引入了Qt 4.2中。

](qmatrix.html)

[**See also**](qmatrix.html) [setOpacity](qpainter.html#setOpacity)（ ） 。

```
QPaintEngine QPainter.paintEngine (self)
```

[

返回绘图引擎的画家是目前，如果画家是积极的运作，否则为0 。

](qpaintengine.html)

[**See also**](qpaintengine.html) [isActive](qpainter.html#isActive)（ ） 。

```
QPen QPainter.pen (self)
```

[

返回画家的当前画笔。

](qpen.html)

[**See also**](qpen.html) [setPen](qpainter.html#setPen)（）和[Settings](qpainter.html#settings)。

```
QPaintDevice QPainter.redirected (QPaintDevice device, QPoint offset = None)
```

[](qpaintdevice.html)

```
RenderHints QPainter.renderHints (self)
```

[

返回一个标志，指定在这个画家将呈现提示。

](index.htm)

[**See also**](index.htm) [setRenderHints](qpainter.html#setRenderHints)（ ）[testRenderHint](qpainter.html#testRenderHint)（）和[Rendering Quality](qpainter.html#rendering-quality)。

```
QPainter.resetMatrix (self)
```

```
QPainter.resetTransform (self)
```

重置过去使用的任何变革[translate](qpainter.html#translate)（ ）[scale](qpainter.html#scale)（ ）[shear](qpainter.html#shear)（ ）[rotate](qpainter.html#rotate)（ ）[setWorldTransform](qpainter.html#setWorldTransform)（ ）[setViewport](qpainter.html#setViewport)（）和[setWindow](qpainter.html#setWindow)（ ） 。

**See also** [Coordinate Transformations](qpainter.html#coordinate-transformations)。

```
QPainter.restore (self)
```

恢复当前的画家状态（弹出一个保存的状态出栈） 。

**See also** [save](qpainter.html#save)（ ） 。

```
QPainter.restoreRedirected (QPaintDevice device)
```

```
QPainter.rotate (self, float a)
```

旋转坐标系中给出_angle_顺时针方向旋转。

**See also** [setWorldTransform](qpainter.html#setWorldTransform)（）和[Coordinate Transformations](qpainter.html#coordinate-transformations)。

```
QPainter.save (self)
```

保存当前状态的画家（推状态入栈） 。一个save（）方法必须遵循的相应的[restore](qpainter.html#restore)（）;的[end](qpainter.html#end)（ ）函数展开栈。

**See also** [restore](qpainter.html#restore)（ ） 。

```
QPainter.scale (self, float sx, float sy)
```

由（缩放坐标系_sx_，_sy_） 。

**See also** [setWorldTransform](qpainter.html#setWorldTransform)（）和[Coordinate Transformations](qpainter.html#coordinate-transformations)。

```
QPainter.setBackground (self, QBrush bg)
```

设定画家的背景刷到给定_brush_。

背景画笔是绘制不透明文本，点画线和位图填充时，在刷。背景刷没有效果的透明背景模式（这是默认值） 。

**See also** [background](qpainter.html#background)（ ）[setBackgroundMode](qpainter.html#setBackgroundMode)（）和[Settings](qpainter.html#settings)。

```
QPainter.setBackgroundMode (self, Qt.BGMode mode)
```

设定画家的背景模式给定的_mode_

[Qt.TransparentMode](qt.html#BGMode-enum)（默认值）绘制点画线条和文字没有设置背景像素。[Qt.OpaqueMode](qt.html#BGMode-enum)填充这些空间与当前的背景色。

需要注意的是，为了绘制位图或像素透明，则必须使用[QPixmap.setMask](qpixmap.html#setMask)（ ） 。

**See also** [backgroundMode](qpainter.html#backgroundMode)（ ）[setBackground](qpainter.html#setBackground)（）和[Settings](qpainter.html#settings)。

```
QPainter.setBrush (self, QBrush brush)
```

集画家笔下的给定_brush_。

画家笔下的定义是如何的形状填充。

**See also** [brush](qpainter.html#brush)（）和[Settings](qpainter.html#settings)。

```
QPainter.setBrush (self, Qt.BrushStyle style)
```

这是一个重载函数。

集画家笔下的黑颜色和指定的_style_。

```
QPainter.setBrushOrigin (self, QPointF)
```

设置画笔原点_position_。

画刷原点指定（ 0 ， 0 ）画家笔下的坐标。

请注意，虽然[brushOrigin](qpainter.html#brushOrigin)（ ）是要采取父母的背景Qt中3小部件，这已不再是如此，因为Qt的4画家不画背景，除非你明确告诉它通过设置widget的这样做[autoFillBackground](qwidget.html#autoFillBackground-prop)属性设置为True 。

**See also** [brushOrigin](qpainter.html#brushOrigin)（）和[Settings](qpainter.html#settings)。

```
QPainter.setBrushOrigin (self, int x, int y)
```

这是一个重载函数。

设置画笔的原点给定的_position_。

```
QPainter.setBrushOrigin (self, QPoint p)
```

这是一个重载函数。

设置画笔的原点指向（_x_，_y_） 。

```
QPainter.setClipPath (self, QPainterPath path, Qt.ClipOperation operation = Qt.ReplaceClip)
```

使裁剪，并设置为给定的剪辑路径画家_path_与剪辑_operation_。

请注意，剪辑路径逻辑（画家）坐标指定。

**See also** [clipPath](qpainter.html#clipPath)（ ）[clipRegion](qpainter.html#clipRegion)（）和[Clipping](qpainter.html#clipping)。

```
QPainter.setClipping (self, bool enable)
```

使裁剪，如果_enable_是真的，或禁用裁剪，如果_enable_是假的。

**See also** [hasClipping](qpainter.html#hasClipping)（）和[Clipping](qpainter.html#clipping)。

```
QPainter.setClipRect (self, QRectF rectangle, Qt.ClipOperation operation = Qt.ReplaceClip)
```

使裁剪，并设置裁剪区域为给定的_rectangle_使用给定的夹_operation_。默认操作是替换当前剪辑矩形。

需要注意的是剪辑矩形的逻辑（画家）坐标指定。

**See also** [clipRegion](qpainter.html#clipRegion)（ ）[setClipping](qpainter.html#setClipping)（）和[Clipping](qpainter.html#clipping)。

```
QPainter.setClipRect (self, int x, int y, int width, int height, Qt.ClipOperation operation = Qt.ReplaceClip)
```

使裁剪，并设置裁剪区域为矩形开始时（_x_，_y_）用给定的_width_和_height_。

```
QPainter.setClipRect (self, QRect rectangle, Qt.ClipOperation operation = Qt.ReplaceClip)
```

这是一个重载函数。

使裁剪，并设置裁剪区域为给定的_rectangle_使用给定的夹_operation_。

```
QPainter.setClipRegion (self, QRegion region, Qt.ClipOperation operation = Qt.ReplaceClip)
```

设置剪辑区域给定的_region_使用指定的剪辑_operation_。默认剪辑操作是替换当前剪辑区域。

注意裁剪区域是由于在逻辑坐标。

**See also** [clipRegion](qpainter.html#clipRegion)（ ）[setClipRect](qpainter.html#setClipRect)（）和[Clipping](qpainter.html#clipping)。

```
QPainter.setCompositionMode (self, CompositionMode mode)
```

载的组成模式为给定的_mode_。

**Warning:**只有一个[QPainter](qpainter.html)在操作[QImage](qimage.html)完全支持所有的组成模式。如所描述的RasterOp的模式支持在X11[compositionMode](qpainter.html#compositionMode)（ ） 。

**See also** [compositionMode](qpainter.html#compositionMode)（ ） 。

```
QPainter.setFont (self, QFont f)
```

集画家的字体给定的_font_。

此字体用于后续的[drawText](qpainter.html#drawText)（）函数。文字颜色是一样的画笔颜色。

如果您设置的字体不可用， Qt的发现一场势均力敌的比赛。[font](qpainter.html#font)（ ）将返回你所设定使用中的setFont （）和[fontInfo](qpainter.html#fontInfo)（）返回的字体实际使用（其可以是相同的） 。

**See also** [font](qpainter.html#font)（ ）[drawText](qpainter.html#drawText)（）和[Settings](qpainter.html#settings)。

```
QPainter.setLayoutDirection (self, Qt.LayoutDirection direction)
```

设置绘制文本时所使用的画家布局方向，到指定的_direction_.

默认值是[Qt.LayoutDirectionAuto](qt.html#LayoutDirection-enum)，这将隐式地从绘制文本确定方向。

**See also** [QTextOption.setTextDirection](qtextoption.html#setTextDirection)（ ）[layoutDirection](qpainter.html#layoutDirection)（ ）[drawText](qpainter.html#drawText)（）和[Settings](qpainter.html#settings)。

```
QPainter.setMatrix (self, QMatrix matrix, bool combine = False)
```

```
QPainter.setMatrixEnabled (self, bool enabled)
```

```
QPainter.setOpacity (self, float opacity)
```

设定画家的不透明度为_opacity_。该值应在范围0.0到1.0 ，其中0.0表示完全透明和1.0表示完全不透明。

不透明的画家设置将适用于所有绘图操作分别。

这个函数中引入了Qt 4.2中。

**See also** [opacity](qpainter.html#opacity)（ ） 。

```
QPainter.setPen (self, QColor color)
```

设定画家的笔下被定_pen_。

该_pen_定义如何绘制线条和轮廓，而且还定义了文字颜色。

**See also** [pen](qpainter.html#pen)（）和[Settings](qpainter.html#settings)。

```
QPainter.setPen (self, QPen pen)
```

这是一个重载函数。

设定画家的笔下有风格[Qt.SolidLine](qt.html#PenStyle-enum)，宽0和指定的_color_。

```
QPainter.setPen (self, Qt.PenStyle style)
```

这是一个重载函数。

设定画家的笔下有定_style_，宽度0和黑色的颜色。

```
QPainter.setRedirected (QPaintDevice device, QPaintDevice replacement, QPoint offset = QPoint())
```

```
QPainter.setRenderHint (self, RenderHint hint, bool on = True)
```

设置给定的渲染_hint_在画家如果_on_为True，否则清除渲染提示。

**See also** [setRenderHints](qpainter.html#setRenderHints)（ ）[renderHints](qpainter.html#renderHints)（）和[Rendering Quality](qpainter.html#rendering-quality)。

```
QPainter.setRenderHints (self, RenderHints hints, bool on = True)
```

设置给定的渲染_hints_在画家如果_on_为True，否则清除渲染提示。

这个函数中引入了Qt 4.2中。

**See also** [setRenderHint](qpainter.html#setRenderHint)（ ）[renderHints](qpainter.html#renderHints)（）和[Rendering Quality](qpainter.html#rendering-quality)。

```
QPainter.setTransform (self, QTransform transform, bool combine = False)
```

设置世界变换矩阵。如果_combine_为True，则指定_transform_是结合当前矩阵，否则将替换当前矩阵。

此功能被引入Qt的4.3 。

**See also** [transform](qpainter.html#transform)（）和[setWorldTransform](qpainter.html#setWorldTransform)（ ） 。

```
QPainter.setViewport (self, QRect viewport)
```

设定画家的视口矩形到给定_rectangle_，并启用视图转换。

视口矩形是认为转型的一部分。视口指定设备坐标系统。它的姊妹，在[window](qpainter.html#window)（ ） ，指定的逻辑坐标系。

默认的视口矩形是相同的器件的矩形。

**See also** [viewport](qpainter.html#viewport)（ ）[viewTransformEnabled](qpainter.html#viewTransformEnabled)（）和[Window-Viewport Conversion](index.htm#window-viewport-conversion)。

```
QPainter.setViewport (self, int x, int y, int w, int h)
```

这是一个重载函数。

设定画家的视口矩形是开始在矩形（_x_，_y_）用给定的_width_和_height_。

```
QPainter.setViewTransformEnabled (self, bool enable)
```

启用视图变换，如果_enable_是真的，或禁用视图变换，如果_enable_是假的。

**See also** [viewTransformEnabled](qpainter.html#viewTransformEnabled)（）和[Window-Viewport Conversion](index.htm#window-viewport-conversion)。

```
QPainter.setWindow (self, QRect window)
```

集画家的窗口给定的_rectangle_，并启用视图转换。

窗口矩形认为转型的一部分。该窗口指定了逻辑坐标系统。它的姊妹，在[viewport](qpainter.html#viewport)（ ） ，指定设备坐标系统。

默认窗口矩形是相同的器件的矩形。

**See also** [window](qpainter.html#window)（ ）[viewTransformEnabled](qpainter.html#viewTransformEnabled)（）和[Window-Viewport Conversion](index.htm#window-viewport-conversion)。

```
QPainter.setWindow (self, int x, int y, int w, int h)
```

这是一个重载函数。

集画家的窗口，矩形开始时（_x_，_y_）和给定的_width_和_height_。

```
QPainter.setWorldMatrix (self, QMatrix matrix, bool combine = False)
```

```
QPainter.setWorldMatrixEnabled (self, bool enabled)
```

使转换，如果_enable_是真的，或禁用，如果转换_enable_是假的。世界变换矩阵不被改变。

这个函数中引入了Qt 4.2中。

**See also** [worldMatrixEnabled](qpainter.html#worldMatrixEnabled)（ ）[worldTransform](qpainter.html#worldTransform)（）和[Coordinate Transformations](qpainter.html#coordinate-transformations)。

```
QPainter.setWorldTransform (self, QTransform matrix, bool combine = False)
```

设置世界变换矩阵。如果_combine_为True，则指定_matrix_是结合当前矩阵，否则将替换当前矩阵。

**See also** [worldTransform](qpainter.html#worldTransform)（ ）[transform](qpainter.html#transform)（）和[setTransform](qpainter.html#setTransform)（ ） 。

```
QPainter.shear (self, float sh, float sv)
```

由（剪坐标系_sh_，_sv_） 。

**See also** [setWorldTransform](qpainter.html#setWorldTransform)（）和[Coordinate Transformations](qpainter.html#coordinate-transformations)。

```
QPainter.strokePath (self, QPainterPath path, QPen pen)
```

绘制轮廓（招）的路径_path_由指定的笔_pen_

**See also** [fillPath](qpainter.html#fillPath)（）和[Drawing](qpainter.html#drawing)。

```
bool QPainter.testRenderHint (self, RenderHint hint)
```

返回True如果_hint_被置位，否则返回False 。

此功能被引入Qt的4.3 。

**See also** [renderHints](qpainter.html#renderHints)（）和[setRenderHint](qpainter.html#setRenderHint)（ ） 。

```
QTransform QPainter.transform (self)
```

[

返回世界变换矩阵。

](qtransform.html)

[**See also**](qtransform.html) [setTransform](qpainter.html#setTransform)（）和[worldTransform](qpainter.html#worldTransform)（ ） 。

```
QPainter.translate (self, QPointF offset)
```

由给定的平移坐标系_offset_，即给定_offset_加入到分。

**See also** [setWorldTransform](qpainter.html#setWorldTransform)（）和[Coordinate Transformations](qpainter.html#coordinate-transformations)。

```
QPainter.translate (self, float dx, float dy)
```

这是一个重载函数。

由给定的平移坐标系_offset_。

```
QPainter.translate (self, QPoint offset)
```

这是一个重载函数。

转换由矢量的坐标系（_dx_，_dy_） 。

```
QRect QPainter.viewport (self)
```

[

返回视口矩形。

](qrect.html)

[**See also**](qrect.html) [setViewport](qpainter.html#setViewport)（）和[setViewTransformEnabled](qpainter.html#setViewTransformEnabled)（ ） 。

```
bool QPainter.viewTransformEnabled (self)
```

返回True如果视图转换被启用，否则返回False 。

**See also** [setViewTransformEnabled](qpainter.html#setViewTransformEnabled)（）和[worldTransform](qpainter.html#worldTransform)（ ） 。

```
QRect QPainter.window (self)
```

[

返回窗口的矩形。

](qrect.html)

[**See also**](qrect.html) [setWindow](qpainter.html#setWindow)（）和[setViewTransformEnabled](qpainter.html#setViewTransformEnabled)（ ） 。

```
QMatrix QPainter.worldMatrix (self)
```

[

```
bool QPainter.worldMatrixEnabled (self)
```

返回True如果世界变换被启用，否则返回False 。

这个函数中引入了Qt 4.2中。

](qmatrix.html)

[**See also**](qmatrix.html) [setWorldMatrixEnabled](qpainter.html#setWorldMatrixEnabled)（ ）[worldTransform](qpainter.html#worldTransform)（）和[Coordinate System](index.htm)。

```
QTransform QPainter.worldTransform (self)
```

[

返回世界变换矩阵。

](qtransform.html)

[**See also**](qtransform.html) [setWorldTransform](qpainter.html#setWorldTransform)（ ） 。

```
object QPainter.__enter__ (self)
```

```
QPainter.__exit__ (self, object type, object value, object traceback)
```