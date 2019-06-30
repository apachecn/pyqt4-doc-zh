# QSvgGenerator Class Reference

## [[QtSvg](index.htm) module]

该QSvgGenerator类提供用于创建SVG绘图的绘图设备。[More...](#details)

继承[QPaintDevice](qpaintdevice.html)。

### Methods

*   `__init__ (self)`
*   `QString description (self)`
*   `QString fileName (self)`
*   `int metric (self, QPaintDevice.PaintDeviceMetric metric)`
*   `QIODevice outputDevice (self)`
*   `QPaintEngine paintEngine (self)`
*   `int resolution (self)`
*   `setDescription (self, QString description)`
*   `setFileName (self, QString fileName)`
*   `setOutputDevice (self, QIODevice outputDevice)`
*   `setResolution (self, int resolution)`
*   `setSize (self, QSize size)`
*   `setTitle (self, QString title)`
*   `setViewBox (self, QRect viewBox)`
*   `setViewBox (self, QRectF viewBox)`
*   `QSize size (self)`
*   `QString title (self)`
*   `QRect viewBox (self)`
*   `QRectF viewBoxF (self)`

* * *

## Detailed Description

该QSvgGenerator类提供用于创建SVG绘图的绘图设备。

这种涂料设备代表一个可伸缩矢量图形（SVG ）绘图。喜欢[QPrinter](qprinter.html)，它被设计为生成输出以特定格式只写设备。

写一个SVG文件，您首先需要通过设置来配置输出[fileName](qsvggenerator.html#fileName-prop) or [outputDevice](qsvggenerator.html#outputDevice-prop)属性。通常需要通过设置来指定绘图的大小的[size](qsvggenerator.html#size-prop)属性，并且在一些情况下，该图将被包括在另一个中，[viewBox](qsvggenerator.html#viewBox-prop)属性也需要设置。

```
     QSvgGenerator generator;
     generator.setFileName(path);
     generator.setSize([QSize](qsize.html)(200, 200));
     generator.setViewBox([QRect](qrect.html)(0, 0, 200, 200));
     generator.setTitle(tr("SVG Generator Example Drawing"));
     generator.setDescription(tr("An SVG drawing created by the SVG Generator "
                                 "Example provided with Qt."));

```

其他元数据可以通过设置指定的_title_，_description_和_resolution_属性。

与其他[QPaintDevice](qpaintdevice.html)子类，一[QPainter](qpainter.html)对象用来绘制到这个类的一个实例：

```
     [QPainter](qpainter.html) painter;
     painter.begin(&generator);
     ...
     painter.end();

```

绘画以同样的方式为其他任何涂料设备执行。然而，有必要使用[QPainter.begin](qpainter.html#begin)（）和[end()](qpainter.html#end)明确的开始和设备上年底画。

该[SVG Generator Example](index.htm)显示了相同的绘画命令如何可以用于画一个widget ，写一个SVG文件。

* * *

## Method Documentation

```
QSvgGenerator.__init__ (self)
```

构造一个新的发电机。

```
QString QSvgGenerator.description (self)
```

```
QString QSvgGenerator.fileName (self)
```

```
int QSvgGenerator.metric (self, QPaintDevice.PaintDeviceMetric metric)
```

从重新实现[QPaintDevice.metric](qpaintdevice.html#metric)（ ） 。

```
QIODevice QSvgGenerator.outputDevice (self)
```

[](qiodevice.html)

```
QPaintEngine QSvgGenerator.paintEngine (self)
```

[](qpaintengine.html)

[从重新实现](qpaintengine.html)[QPaintDevice.paintEngine](qpaintdevice.html#paintEngine)（ ） 。

返回用于呈现图形转换为SVG格式信息的绘图引擎。

```
int QSvgGenerator.resolution (self)
```

```
QSvgGenerator.setDescription (self, QString description)
```

```
QSvgGenerator.setFileName (self, QString fileName)
```

```
QSvgGenerator.setOutputDevice (self, QIODevice outputDevice)
```

```
QSvgGenerator.setResolution (self, int resolution)
```

```
QSvgGenerator.setSize (self, QSize size)
```

```
QSvgGenerator.setTitle (self, QString title)
```

```
QSvgGenerator.setViewBox (self, QRect viewBox)
```

```
QSvgGenerator.setViewBox (self, QRectF viewBox)
```

```
QSize QSvgGenerator.size (self)
```

[

```
QString QSvgGenerator.title (self)
```

](qsize.html)

```
QRect QSvgGenerator.viewBox (self)
```

[](qrect.html)

[Returns](qrect.html) [viewBoxF](qsvggenerator.html#viewBox-prop)（ ） 。 toRect （ ） 。

此功能被引入Qt的4.5 。

**See also** [setViewBox](qsvggenerator.html#viewBox-prop)（）和[viewBoxF](qsvggenerator.html#viewBox-prop)（ ） 。

```
QRectF QSvgGenerator.viewBoxF (self)
```

[](qrectf.html)