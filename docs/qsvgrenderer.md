# QSvgRenderer Class Reference

## [[QtSvg](index.htm) module]

该QSvgRenderer类用于绘制SVG文件的内容复制到绘图设备。[More...](#details)

继承[QObject](qobject.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `__init__ (self, QString filename, QObject parent = None)`
*   `__init__ (self, QByteArray contents, QObject parent = None)`
*   `__init__ (self, QXmlStreamReader contents, QObject parent = None)`
*   `bool animated (self)`
*   `int animationDuration (self)`
*   `QRectF boundsOnElement (self, QString id)`
*   `int currentFrame (self)`
*   `QSize defaultSize (self)`
*   `bool elementExists (self, QString id)`
*   `int framesPerSecond (self)`
*   `bool isValid (self)`
*   `bool load (self, QString filename)`
*   `bool load (self, QByteArray contents)`
*   `bool load (self, QXmlStreamReader contents)`
*   `QMatrix matrixForElement (self, QString id)`
*   `render (self, QPainter p)`
*   `render (self, QPainter p, QRectF bounds)`
*   `render (self, QPainter painter, QString elementId, QRectF bounds = QRectF())`
*   `setCurrentFrame (self, int)`
*   `setFramesPerSecond (self, int num)`
*   `setViewBox (self, QRect viewbox)`
*   `setViewBox (self, QRectF viewbox)`
*   `QRect viewBox (self)`
*   `QRectF viewBoxF (self)`

### Qt Signals

*   `void repaintNeeded ()`

* * *

## Detailed Description

该QSvgRenderer类用于绘制SVG文件的内容复制到绘图设备。

使用QSvgRenderer ，可伸缩矢量图形（SVG ）可以渲染到任何[QPaintDevice](qpaintdevice.html)子类，包括[QWidget](qwidget.html)，[QImage](qimage.html)和[QGLWidget](qglwidget.html)。

QSvgRenderer提供了一个支持SVG渲染的基本功能，如加载和渲染静态的图纸，和喜欢动漫的更多互动功能的API。由于使用所执行的渲染[QPainter](qpainter.html)， SVG图形可以在任意子类被渲染[QPaintDevice](qpaintdevice.html)。

SVG绘图要么加载时QSvgRenderer构造，或加载后使用[load](qsvgrenderer.html#load)（）函数。数据是提供直接作为序列化的XML ，或间接使用文件名。如果一个有效的文件已经被加载，或者当渲染器构造或在一段时间后，[isValid](qsvgrenderer.html#isValid)（ ）返回True ，否则返回False 。 QSvgRenderer提供[render](qsvgrenderer.html#render)（）槽呈现当前文件或动画文件的当前帧中，使用给定的画家。

该[defaultSize](qsvgrenderer.html#defaultSize)（）函数，提供了有关的空间来呈现当前加载的SVG文件所需要的量的信息。这是用于涂料的设备，如可使用[QWidget](qwidget.html)，往往需要提供尺寸暗示给其父布局。图形的默认大小可以从它的可视面积，发现使用不同的[viewBox](qsvgrenderer.html#viewBox-prop)属性。

动画SVG图形的支持，并且可以用函数和属性的简单集合进行控制：

*   The [animated](qsvgrenderer.html#animated)() function indicates whether a drawing contains animation information.
*   The [framesPerSecond](qsvgrenderer.html#framesPerSecond-prop) property contains the rate at which the animation plays.

最后， QSvgRenderer类提供了[repaintNeeded](qsvgrenderer.html#repaintNeeded)（），它被发射每当需要更新的文件的再现信号。

* * *

## Method Documentation

```
QSvgRenderer.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的渲染器给定的_parent_。

```
QSvgRenderer.__init__ (self, QString filename, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的渲染器给定的_parent_并载入SVG文件中的内容与指定_filename_。

```
QSvgRenderer.__init__ (self, QByteArray contents, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的渲染器给定的_parent_并加载从指定的字节数组中的SVG数据_contents_。

```
QSvgRenderer.__init__ (self, QXmlStreamReader contents, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的渲染器给定的_parent_并且通过使用指定的流读取器加载SVG数据_contents_。

此功能被引入Qt的4.5 。

```
bool QSvgRenderer.animated (self)
```

返回True如果当前文档包含动画元素，否则返回False 。

**See also** [framesPerSecond](qsvgrenderer.html#framesPerSecond-prop)（ ） 。

```
int QSvgRenderer.animationDuration (self)
```

```
QRectF QSvgRenderer.boundsOnElement (self, QString id)
```

[

返回边界项目的矩形与给定_id_。父元素的变换矩阵是不影响该元素的边界。

这个函数中引入了Qt 4.2中。

](qrectf.html)

[**See also**](qrectf.html) [matrixForElement](qsvgrenderer.html#matrixForElement)（ ） 。

```
int QSvgRenderer.currentFrame (self)
```

```
QSize QSvgRenderer.defaultSize (self)
```

[

返回的文档内容的默认大小。

```
bool QSvgRenderer.elementExists (self, QString id)
```

返回True如果与元素给定的_id_存在于当前解析SVG文件，是一个可渲染的元素。

注意：此方法仅适用于可渲染的元素返回True 。这意味着被视为填充/描边样式属性的一部分元素，例如：甚至强硬的标有“身份证” radialGradients属性不会用这种方法发现。

这个函数中引入了Qt 4.2中。

```
int QSvgRenderer.framesPerSecond (self)
```

```
bool QSvgRenderer.isValid (self)
```

返回True如果有一个有效的当前文档，否则返回False 。

```
bool QSvgRenderer.load (self, QString filename)
```

这种方法也是一个Qt槽与C + +的签名`bool load(const QString&)`。

通过加载指定的SVG文件_filename_，返回True，如果内容被成功解析，否则返回False 。

```
bool QSvgRenderer.load (self, QByteArray contents)
```

这种方法也是一个Qt槽与C + +的签名`bool load(const QByteArray&)`。

加载指定的SVG格式_contents_，返回True，如果内容被成功解析，否则返回False 。

```
bool QSvgRenderer.load (self, QXmlStreamReader contents)
```

这种方法也是一个Qt槽与C + +的签名`bool load(QXmlStreamReader *)`。

加载指定的SVG中_contents_，返回True，如果内容被成功解析，否则返回False 。

读者将用于从那里它目前的位置。如果_contents_ is `null`，行为是未定义的。

此功能被引入Qt的4.5 。

](qsize.html)

```
QMatrix QSvgRenderer.matrixForElement (self, QString id)
```

[

返回该元素的变换矩阵与给定_id_。该矩阵元素的父母转型的产物。不包括元素本身的转型。

](qmatrix.html)

[要查找在逻辑坐标元素的边框，你可以申请矩阵从返回的矩形](qmatrix.html)[boundsOnElement](qsvgrenderer.html#boundsOnElement)（ ） 。

这个函数中引入了Qt 4.2中。

**See also** [boundsOnElement](qsvgrenderer.html#boundsOnElement)（ ） 。

```
QSvgRenderer.render (self, QPainter p)
```

这种方法也是一个Qt槽与C + +的签名`void render(QPainter *)`。

呈现当前文档或动画文件的当前帧，使用给定的_painter_。

```
QSvgRenderer.render (self, QPainter p, QRectF bounds)
```

这种方法也是一个Qt槽与C + +的签名`void render(QPainter *,const QRectF&)`。

呈现当前文档或动画文件的当前帧，使用给定的_painter_在指定的_bounds_在画家。如果未指定边界矩形是SVG文件被映射到整个绘图设备。

```
QSvgRenderer.render (self, QPainter painter, QString elementId, QRectF bounds = QRectF())
```

这种方法也是一个Qt槽与C + +的签名`void render(QPainter *,const QString&,const QRectF& = QRectF())`。

呈现给定的元素与_elementId_使用给定的_painter_在指定的_bounds_。如果未指定边界矩形是SVG元素映射到整个绘图设备。

```
QSvgRenderer.setCurrentFrame (self, int)
```

```
QSvgRenderer.setFramesPerSecond (self, int num)
```

```
QSvgRenderer.setViewBox (self, QRect viewbox)
```

```
QSvgRenderer.setViewBox (self, QRectF viewbox)
```

```
QRect QSvgRenderer.viewBox (self)
```

[](qrect.html)

[Returns](qrect.html) [viewBoxF](qsvgrenderer.html#viewBox-prop)（ ） 。 toRect （ ） 。

**See also** [setViewBox](qsvgrenderer.html#viewBox-prop)（）和[viewBoxF](qsvgrenderer.html#viewBox-prop)（ ） 。

```
QRectF QSvgRenderer.viewBoxF (self)
```

[

* * *

## Qt Signal Documentation

```
void repaintNeeded ()
```

这是该信号的默认超载。

这个信号被发射每当需要更新时，通常为动画的目的文件的呈现。

](qrectf.html)