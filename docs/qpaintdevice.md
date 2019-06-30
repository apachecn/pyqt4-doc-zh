# QPaintDevice Class Reference

## [[QtGui](index.htm) module]

在一个QPaintDevice类是可绘对象的基类。[More...](#details)

通过继承[QGLFramebufferObject](qglframebufferobject.html)，[QGLPixelBuffer](qglpixelbuffer.html)，[QImage](qimage.html)，[QPicture](qpicture.html)，[QPixmap](qpixmap.html)，[QPrinter](qprinter.html)，[QSvgGenerator](qsvggenerator.html)和[QWidget](qwidget.html)。

### Types

*   `enum PaintDeviceMetric { PdmWidth, PdmHeight, PdmWidthMM, PdmHeightMM, ..., PdmPhysicalDpiY }`

### Methods

*   `__init__ (self)`
*   `int colorCount (self)`
*   `int depth (self)`
*   `int height (self)`
*   `int heightMM (self)`
*   `int logicalDpiX (self)`
*   `int logicalDpiY (self)`
*   `int metric (self, PaintDeviceMetric metric)`
*   `int numColors (self)`
*   `QPaintEngine paintEngine (self)`
*   `bool paintingActive (self)`
*   `int physicalDpiX (self)`
*   `int physicalDpiY (self)`
*   `int width (self)`
*   `int widthMM (self)`

* * *

## Detailed Description

在一个QPaintDevice类是可绘对象的基类。

一种涂料设备是一个二维空间的抽象，可以使用被绘制[QPainter](qpainter.html)。其默认的坐标系统的原点位于左上角的位置。 X增加的权利和Y向下增加。该单元是一个像素。

一个QPaintDevice的绘图功能由目前实施[QWidget](qwidget.html)，[QImage](qimage.html)，[QPixmap](qpixmap.html)，[QGLPixelBuffer](qglpixelbuffer.html)，[QPicture](qpicture.html)和[QPrinter](qprinter.html)子类。

要实现一个新的后台支持，您必须来自一个QPaintDevice和重新实现虚拟[paintEngine](qpaintdevice.html#paintEngine)（ ）函数来告诉[QPainter](qpainter.html)其中绘图引擎应该被用来绘制这个特定的设备上。请注意，您还必须创建一个相应的绘图引擎，能够绘制在设备上，即派生自[QPaintEngine](qpaintengine.html)并重新实现其虚函数。

**Warning:**Qt的规定，[QApplication](qapplication.html)对象存在可以创建任何油漆设备之前。油漆设备访问窗口的系统资源，并创建一个应用程序对象之前，这些资源不被初始化。

在一个QPaintDevice类提供了一些函数返回的各种设备指标：该[depth](qpaintdevice.html#depth)（）函数返回它的比特深度（位平面的数量）。该[height](qpaintdevice.html#height)（ ）函数返回它的高度在默认坐标系统的单位（如像素[QPixmap](qpixmap.html)和[QWidget](qwidget.html)），而[heightMM](qpaintdevice.html#heightMM)（ ）返回设备的高度以毫米为单位。 Similiarily时，[width](qpaintdevice.html#width)（）和[widthMM](qpaintdevice.html#widthMM)（ ）函数返回的设备在默认的宽度坐标系单位和以毫米为单位，分别。或者，受保护的[metric](qpaintdevice.html#metric)（）函数可用于通过指定所希望的检索度量信息[PaintDeviceMetric](qpaintdevice.html#PaintDeviceMetric-enum)作为参数。

该[logicalDpiX](qpaintdevice.html#logicalDpiX)（）和[logicalDpiY](qpaintdevice.html#logicalDpiY)（ ）函数返回设备的每英寸的点数的水平和垂直分辨率。该[physicalDpiX](qpaintdevice.html#physicalDpiX)（）和[physicalDpiY](qpaintdevice.html#physicalDpiY)（ ）函数也返回该设备以每英寸点数的分辨率，但要注意，如果逻辑和物理分辨率不同，相应的[QPaintEngine](qpaintengine.html)必须处理的映射。最后，该[colorCount](qpaintdevice.html#colorCount)（ ）函数返回不同的颜色可供绘制设备的数量。

* * *

## Type Documentation

```
QPaintDevice.PaintDeviceMetric
```

描述了一个绘图设备的各种指标。

| Constant | Value | Description |
| --- | --- | --- |
| `QPaintDevice.PdmWidth` | `1` | 涂料设备的默认宽度坐标系单位（如像素[QPixmap](qpixmap.html)和[QWidget](qwidget.html)） 。另请参阅[width](qpaintdevice.html#width)（ ） 。 |
| `QPaintDevice.PdmHeight` | `2` | 涂料设备的默认高度坐标系单位（如像素[QPixmap](qpixmap.html)和[QWidget](qwidget.html)） 。另请参阅[height](qpaintdevice.html#height)（ ） 。 |
| `QPaintDevice.PdmWidthMM` | `3` | 涂料设备以毫米为单位的宽度。另请参阅[widthMM](qpaintdevice.html#widthMM)（ ） 。 |
| `QPaintDevice.PdmHeightMM` | `4` | 涂料设备以毫米为单位的高度。另请参阅[heightMM](qpaintdevice.html#heightMM)（ ） 。 |
| `QPaintDevice.PdmNumColors` | `5` | 不同颜色可供油漆设备的数量。另请参阅[colorCount](qpaintdevice.html#colorCount)（ ） 。 |
| `QPaintDevice.PdmDepth` | `6` | 绘制设备的比特深度（位平面的数量）。另请参阅[depth](qpaintdevice.html#depth)（ ） 。 |
| `QPaintDevice.PdmDpiX` | `7` | 该设备每英寸的点数的水平分辨率。另请参阅[logicalDpiX](qpaintdevice.html#logicalDpiX)（ ） 。 |
| `QPaintDevice.PdmDpiY` | `8` | 该设备每英寸的点数的垂直分辨率。另请参阅[logicalDpiY](qpaintdevice.html#logicalDpiY)（ ） 。 |
| `QPaintDevice.PdmPhysicalDpiX` | `9` | 该设备每英寸的点数的水平分辨率。另请参阅[physicalDpiX](qpaintdevice.html#physicalDpiX)（ ） 。 |
| `QPaintDevice.PdmPhysicalDpiY` | `10` | 该设备每英寸的点数的垂直分辨率。另请参阅[physicalDpiY](qpaintdevice.html#physicalDpiY)（ ） 。 |

**See also** [metric](qpaintdevice.html#metric)（ ） 。

* * *

## Method Documentation

```
QPaintDevice.__init__ (self)
```

构造一个绘图设备。此构造函数只能从子类调用[QPaintDevice](qpaintdevice.html)。

```
int QPaintDevice.colorCount (self)
```

返回不同的颜色可供绘制设备的数量。因为这个值是一个整数，它不会是足以代表在32位显示的颜色的数量，在这种情况下INT_MAX被返回来代替。

```
int QPaintDevice.depth (self)
```

返回绘制设备的比特深度（位平面的数量）。

```
int QPaintDevice.height (self)
```

返回绘制设备的默认高度坐标系统的单位（如像素[QPixmap](qpixmap.html)和[QWidget](qwidget.html)） 。

**See also** [heightMM](qpaintdevice.html#heightMM)（ ） 。

```
int QPaintDevice.heightMM (self)
```

返回漆装置以毫米为单位的高度。由于平台的限制，它可能无法使用这个函数来确定屏幕上的一个小部件的实际物理尺寸。

**See also** [height](qpaintdevice.html#height)（ ） 。

```
int QPaintDevice.logicalDpiX (self)
```

返回以每英寸点数，这是计算的字体大小时使用的设备的水平分辨率。为X11 ，这通常是因为可以从计算同一[widthMM](qpaintdevice.html#widthMM)（ ） 。

请注意，如果logicalDpiX （ ）不等于[physicalDpiX](qpaintdevice.html#physicalDpiX)（）时，相应的[QPaintEngine](qpaintengine.html)必须处理分辨率的映射。

**See also** [logicalDpiY](qpaintdevice.html#logicalDpiY)（）和[physicalDpiX](qpaintdevice.html#physicalDpiX)（ ） 。

```
int QPaintDevice.logicalDpiY (self)
```

返回以每英寸点数，这是计算的字体大小时使用的设备的垂直分辨率。为X11 ，这通常是因为可以从计算同一[heightMM](qpaintdevice.html#heightMM)（ ） 。

请注意，如果logicalDpiY （ ）不等于[physicalDpiY](qpaintdevice.html#physicalDpiY)（）时，相应的[QPaintEngine](qpaintengine.html)必须处理分辨率的映射。

**See also** [logicalDpiX](qpaintdevice.html#logicalDpiX)（）和[physicalDpiY](qpaintdevice.html#physicalDpiY)（ ） 。

```
int QPaintDevice.metric (self, PaintDeviceMetric metric)
```

返回度量信息对于给定的涂料设备_metric_。

**See also** [PaintDeviceMetric](qpaintdevice.html#PaintDeviceMetric-enum)。

```
int QPaintDevice.numColors (self)
```

此功能已被弃用。

使用[colorCount](qpaintdevice.html#colorCount)（ ）来代替。

返回不同的颜色可供绘制设备的数量。因为这个值是一个整数，它不会是足以代表在32位显示的颜色的数量，在这种情况下INT_MAX被返回来代替。

```
QPaintEngine QPaintDevice.paintEngine (self)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回一个指针，指向绘图引擎用于在设备上绘制。

```
bool QPaintDevice.paintingActive (self)
```

](qpaintengine.html)

[如果返回设备当前正在绘制的，即有人叫真](qpaintengine.html)[QPainter.begin](qpainter.html#begin)（），但尚未被称为[QPainter.end](qpainter.html#end)（ ）此设备，否则返回False 。

**See also** [QPainter.isActive](qpainter.html#isActive)（ ） 。

```
int QPaintDevice.physicalDpiX (self)
```

返回以每英寸点数设备的水平分辨率。例如，在打印时，这项决议是指物理打印机的分辨率。在另一方面的逻辑DPI ，是指所使用的实际绘图引擎的分辨率。

请注意，如果physicalDpiX （ ）不等于[logicalDpiX](qpaintdevice.html#logicalDpiX)（）时，相应的[QPaintEngine](qpaintengine.html)必须处理分辨率的映射。

**See also** [physicalDpiY](qpaintdevice.html#physicalDpiY)（）和[logicalDpiX](qpaintdevice.html#logicalDpiX)（ ） 。

```
int QPaintDevice.physicalDpiY (self)
```

返回以每英寸点数设备的水平分辨率。例如，在打印时，这项决议是指物理打印机的分辨率。在另一方面的逻辑DPI ，是指所使用的实际绘图引擎的分辨率。

请注意，如果physicalDpiY （ ）不等于[logicalDpiY](qpaintdevice.html#logicalDpiY)（）时，相应的[QPaintEngine](qpaintengine.html)必须处理分辨率的映射。

**See also** [physicalDpiX](qpaintdevice.html#physicalDpiX)（）和[logicalDpiY](qpaintdevice.html#logicalDpiY)（ ） 。

```
int QPaintDevice.width (self)
```

返回绘制设备的默认宽度坐标系单位（如像素[QPixmap](qpixmap.html)和[QWidget](qwidget.html)） 。

**See also** [widthMM](qpaintdevice.html#widthMM)（ ） 。

```
int QPaintDevice.widthMM (self)
```

返回漆装置以毫米为单位的宽度。由于平台的限制，它可能无法使用这个函数来确定屏幕上的一个小部件的实际物理尺寸。

**See also** [width](qpaintdevice.html#width)（ ） 。