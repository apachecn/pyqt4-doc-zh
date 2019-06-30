# QPainterPathStroker Class Reference

## [[QtGui](index.htm) module]

该QPainterPathStroker类是用来产生可填写概述对于给定的画家路径。[More...](#details)

### Methods

*   `__init__ (self)`
*   `Qt.PenCapStyle capStyle (self)`
*   `QPainterPath createStroke (self, QPainterPath path)`
*   `float curveThreshold (self)`
*   `float dashOffset (self)`
*   `list-of-float dashPattern (self)`
*   `Qt.PenJoinStyle joinStyle (self)`
*   `float miterLimit (self)`
*   `setCapStyle (self, Qt.PenCapStyle style)`
*   `setCurveThreshold (self, float threshold)`
*   `setDashOffset (self, float offset)`
*   `setDashPattern (self, Qt.PenStyle)`
*   `setDashPattern (self, list-of-float dashPattern)`
*   `setJoinStyle (self, Qt.PenJoinStyle style)`
*   `setMiterLimit (self, float length)`
*   `setWidth (self, float width)`
*   `float width (self)`

* * *

## Detailed Description

该QPainterPathStroker类是用来产生可填写概述对于给定的画家路径。

通过调用[createStroke](qpainterpathstroker.html#createStroke)（ ）函数，传递一个给定的[QPainterPath](qpainterpath.html)作为参数，表示给定路径的轮廓的新画家路径被创建。新创建的画家路径然后可以填充绘制原画师路径的轮廓。

您可以控制​​各种设计方面使用以下功能的概述（宽度，帽样式，加入风格和虚线样式） ：

*   [setWidth](qpainterpathstroker.html#setWidth)()
*   [setCapStyle](qpainterpathstroker.html#setCapStyle)()
*   [setJoinStyle](qpainterpathstroker.html#setJoinStyle)()
*   [setDashPattern](qpainterpathstroker.html#setDashPattern)()

该[setDashPattern](qpainterpathstroker.html#setDashPattern)（ ）函数接受一个既[Qt.PenStyle](qt.html#PenStyle-enum)对象和模式作为参数向量表示。

此外，您可以指定一个曲线的阈值时，控制与曲线绘制的粒度，使用[setCurveThreshold](qpainterpathstroker.html#setCurveThreshold)（）函数。预设的阈值是一个很好的调整值（ 0.25 ） ，并且通常你不需要修改它。但是，您可以通过降低它的价值使曲线的外观更光滑。

您还可以控制斜接限制使用生成的轮廓[setMiterLimit](qpainterpathstroker.html#setMiterLimit)（）函数。斜接限制说明如何远离每个加盟斜角连接可以延长。在宽的单位是所指定的限制，因此pixelwise斜接限制会`miterlimit * width`。此值仅用于联接风格[Qt.MiterJoin](qt.html#PenJoinStyle-enum)。

通过所产生的画家路径[createStroke](qpainterpathstroker.html#createStroke)（ ）函数应该只用于概述给定的画家路径。否则可能会导致意外行为。生成的轮廓也需要[Qt.WindingFill](qt.html#FillRule-enum)排除这是默认设置。

* * *

## Method Documentation

```
QPainterPathStroker.__init__ (self)
```

创建一个新的司炉。

```
Qt.PenCapStyle QPainterPathStroker.capStyle (self)
```

[

返回生成轮廓的端点样式。

](qt.html#PenCapStyle-enum)

[**See also**](qt.html#PenCapStyle-enum) [setCapStyle](qpainterpathstroker.html#setCapStyle)（ ） 。

```
QPainterPath QPainterPathStroker.createStroke (self, QPainterPath path)
```

[

产生一个新的路径就是代表给定的轮廓可填写区域_path_。

](qpainterpath.html)

[轮廓的各个方面的设计都是基于抚摩的属性：](qpainterpath.html)[width](qpainterpathstroker.html#width)（ ）[capStyle](qpainterpathstroker.html#capStyle)（ ）[joinStyle](qpainterpathstroker.html#joinStyle)（ ）[dashPattern](qpainterpathstroker.html#dashPattern)（ ）[curveThreshold](qpainterpathstroker.html#curveThreshold)（）和[miterLimit](qpainterpathstroker.html#miterLimit)（ ） 。

生成的路径应该只用于概述给定的画家路径。否则可能会导致意外行为。生成的轮廓也需要[Qt.WindingFill](qt.html#FillRule-enum)排除这是默认设置。

```
float QPainterPathStroker.curveThreshold (self)
```

返回生成的轮廓曲线扁平化的门槛。

**See also** [setCurveThreshold](qpainterpathstroker.html#setCurveThreshold)（ ） 。

```
float QPainterPathStroker.dashOffset (self)
```

返回冲刺的轮廓产生偏移。

**See also** [setDashOffset](qpainterpathstroker.html#setDashOffset)（ ） 。

```
list-of-float QPainterPathStroker.dashPattern (self)
```

返回生成的轮廓虚线样式。

**See also** [setDashPattern](qpainterpathstroker.html#setDashPattern)（ ） 。

```
Qt.PenJoinStyle QPainterPathStroker.joinStyle (self)
```

[

返回生成的轮廓线的连接样式。

](qt.html#PenJoinStyle-enum)

[**See also**](qt.html#PenJoinStyle-enum) [setJoinStyle](qpainterpathstroker.html#setJoinStyle)（ ） 。

```
float QPainterPathStroker.miterLimit (self)
```

返回斜接限制为生成的轮廓。

**See also** [setMiterLimit](qpainterpathstroker.html#setMiterLimit)（ ） 。

```
QPainterPathStroker.setCapStyle (self, Qt.PenCapStyle style)
```

设置生成的轮廓的帽子风格_style_。如果一个虚线样式设置，图案各部分是受帽_style_。

**See also** [capStyle](qpainterpathstroker.html#capStyle)（ ） 。

```
QPainterPathStroker.setCurveThreshold (self, float threshold)
```

指定曲线变平_threshold_，控制与所生成的轮廓'曲线绘制的粒度。

预设的阈值是一个很好的调整值（ 0.25 ） ，并且通常你不需要修改它。但是，您可以通过降低它的价值使曲线的外观更光滑。

**See also** [curveThreshold](qpainterpathstroker.html#curveThreshold)（ ） 。

```
QPainterPathStroker.setDashOffset (self, float offset)
```

设置破折号所生成的轮廓，以抵消_offset_。

请参阅该文档[QPen.setDashOffset](qpen.html#setDashOffset)（ ）为破折号的描述偏移。

**See also** [dashOffset](qpainterpathstroker.html#dashOffset)（ ） 。

```
QPainterPathStroker.setDashPattern (self, Qt.PenStyle)
```

设置所生成的轮廓的虚线样式_style_。

**See also** [dashPattern](qpainterpathstroker.html#dashPattern)（ ） 。

```
QPainterPathStroker.setDashPattern (self, list-of-float dashPattern)
```

这是一个重载函数。

设置所生成的轮廓的虚线样式_dashPattern_。此功能使得它可以指定自定义虚线样式。

向量中的每个元素都包含在行程短划线和空格的长度，用连字符和空格之间的第一个元素的第一个破折号，在第二个元素的第一个空间，并为每个下列成对的元素交替的开始。

该载体可含有的元素，在这种情况下，最后一个元素将通过当图案重复第一元件的长度延伸的一个奇数。

```
QPainterPathStroker.setJoinStyle (self, Qt.PenJoinStyle style)
```

设置生成的轮廓的风格加入到_style_。

**See also** [joinStyle](qpainterpathstroker.html#joinStyle)（ ） 。

```
QPainterPathStroker.setMiterLimit (self, float length)
```

设置生成的轮廓的斜接限制_limit_。

斜接限制说明如何远离每个加盟斜角连接可以延长。被指定在当前设置的宽度为单位的限制。所以pixelwise斜接限制会`miterlimit * width`。

此值仅用于联接风格[Qt.MiterJoin](qt.html#PenJoinStyle-enum)。

**See also** [miterLimit](qpainterpathstroker.html#miterLimit)（ ） 。

```
QPainterPathStroker.setWidth (self, float width)
```

设置所生成的轮廓画家路径的宽度_width_。

所生成的轮廓将延长约50％的_width_为给定的输入路径的原始轮廓的每一侧。

**See also** [width](qpainterpathstroker.html#width)（ ） 。

```
float QPainterPathStroker.width (self)
```

返回生成的轮廓的宽度。

**See also** [setWidth](qpainterpathstroker.html#setWidth)（ ） 。