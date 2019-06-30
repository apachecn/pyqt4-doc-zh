# QPaintEngineState Class Reference

## [[QtGui](index.htm) module]

该QPaintEngineState类提供有关活动的绘图引擎的当前状态信息。[More...](#details)

### Methods

*   `__init__ (self)`
*   `__init__ (self, QPaintEngineState)`
*   `QBrush backgroundBrush (self)`
*   `Qt.BGMode backgroundMode (self)`
*   `QBrush brush (self)`
*   `bool brushNeedsResolving (self)`
*   `QPointF brushOrigin (self)`
*   `Qt.ClipOperation clipOperation (self)`
*   `QPainterPath clipPath (self)`
*   `QRegion clipRegion (self)`
*   `QPainter.CompositionMode compositionMode (self)`
*   `QFont font (self)`
*   `bool isClipEnabled (self)`
*   `QMatrix matrix (self)`
*   `float opacity (self)`
*   `QPainter painter (self)`
*   `QPen pen (self)`
*   `bool penNeedsResolving (self)`
*   `QPainter.RenderHints renderHints (self)`
*   `QPaintEngine.DirtyFlags state (self)`
*   `QTransform transform (self)`

* * *

## Detailed Description

该QPaintEngineState类提供有关活动的绘图引擎的当前状态信息。

哪些属性，自上一次绘图引擎进行了更新，以及它们的当前值已经改变QPaintEngineState记录。

这已更改的属性可以在任何时候使用被检索的[state](qpaintenginestate.html#state)（）函数。这个函数返回的一个实例[QPaintEngine.DirtyFlags](qpaintengine.html#DirtyFlag-enum)其中存储的一个或组合型[QPaintEngine.DirtyFlag](qpaintengine.html#DirtyFlag-enum)值。该[QPaintEngine.DirtyFlag](qpaintengine.html#DirtyFlag-enum)枚举定义了自上次更新还是不是一个属性是否已更改。

如果属性是标有一个肮脏的标志，其当前值可以使用相应的get函数来检索：

| Property Flag | Current Property Value |
| --- | --- |
| [QPaintEngine.DirtyBackground](qpaintengine.html#DirtyFlag-enum) | [backgroundBrush](qpaintenginestate.html#backgroundBrush)() |
| [QPaintEngine.DirtyBackgroundMode](qpaintengine.html#DirtyFlag-enum) | [backgroundMode](qpaintenginestate.html#backgroundMode)() |
| [QPaintEngine.DirtyBrush](qpaintengine.html#DirtyFlag-enum) | [brush](qpaintenginestate.html#brush)() |
| [QPaintEngine.DirtyBrushOrigin](qpaintengine.html#DirtyFlag-enum) | [brushOrigin](qpaintenginestate.html#brushOrigin)() |
| [QPaintEngine.DirtyClipRegion](qpaintengine.html#DirtyFlag-enum) _or_ [QPaintEngine.DirtyClipPath](qpaintengine.html#DirtyFlag-enum) | [clipOperation](qpaintenginestate.html#clipOperation)() |
| [QPaintEngine.DirtyClipPath](qpaintengine.html#DirtyFlag-enum) | [clipPath](qpaintenginestate.html#clipPath)() |
| [QPaintEngine.DirtyClipRegion](qpaintengine.html#DirtyFlag-enum) | [clipRegion](qpaintenginestate.html#clipRegion)() |
| [QPaintEngine.DirtyCompositionMode](qpaintengine.html#DirtyFlag-enum) | [compositionMode](qpaintenginestate.html#compositionMode)() |
| [QPaintEngine.DirtyFont](qpaintengine.html#DirtyFlag-enum) | [font](qpaintenginestate.html#font)() |
| [QPaintEngine.DirtyTransform](qpaintengine.html#DirtyFlag-enum) | [transform](qpaintenginestate.html#transform)() |
| [QPaintEngine.DirtyClipEnabled](qpaintengine.html#DirtyFlag-enum) | [isClipEnabled](qpaintenginestate.html#isClipEnabled)() |
| [QPaintEngine.DirtyPen](qpaintengine.html#DirtyFlag-enum) | [pen](qpaintenginestate.html#pen)() |
| [QPaintEngine.DirtyHints](qpaintengine.html#DirtyFlag-enum) | [renderHints](qpaintenginestate.html#renderHints)() |

该QPaintEngineState类还提供了[painter](qpaintenginestate.html#painter)（ ）函数返回一个指针，指向当前正在更新的绘图引擎的画家。

这个类，即主动绘图引擎的当前状态的一个实例，作为参数传递给[QPaintEngine.updateState](qpaintengine.html#updateState)（）函数。实现自己的绘图引擎时，你将不得不直接使用这个类的唯一情况是。

* * *

## Method Documentation

```
QPaintEngineState.__init__ (self)
```

```
QPaintEngineState.__init__ (self, QPaintEngineState)
```

```
QBrush QPaintEngineState.backgroundBrush (self)
```

[

返回当前绘图引擎状态的背景刷。

](qbrush.html)

[这个变量应该只用来当](qbrush.html)[state](qpaintenginestate.html#state)（ ）返回一个组合，其中包括[QPaintEngine.DirtyBackground](qpaintengine.html#DirtyFlag-enum)标志。

**See also** [state](qpaintenginestate.html#state)（）和[QPaintEngine.updateState](qpaintengine.html#updateState)（ ） 。

```
Qt.BGMode QPaintEngineState.backgroundMode (self)
```

[

返回后台模式在当前的绘图引擎的状态。

](qt.html#BGMode-enum)

[这个变量应该只用来当](qt.html#BGMode-enum)[state](qpaintenginestate.html#state)（ ）返回一个组合，其中包括[QPaintEngine.DirtyBackgroundMode](qpaintengine.html#DirtyFlag-enum)标志。

**See also** [state](qpaintenginestate.html#state)（）和[QPaintEngine.updateState](qpaintengine.html#updateState)（ ） 。

```
QBrush QPaintEngineState.brush (self)
```

[

返回当前绘图引擎状态的笔刷。

](qbrush.html)

[这个变量应该只用来当](qbrush.html)[state](qpaintenginestate.html#state)（ ）返回一个组合，其中包括[QPaintEngine.DirtyBrush](qpaintengine.html#DirtyFlag-enum)标志。

**See also** [state](qpaintenginestate.html#state)（）和[QPaintEngine.updateState](qpaintengine.html#updateState)（ ） 。

```
bool QPaintEngineState.brushNeedsResolving (self)
```

返回填充的坐标是否已被指定为界由当前的渲染操作和必须解决（关于当前呈现的原语） 。

此功能被引入Qt的4.3 。

```
QPointF QPaintEngineState.brushOrigin (self)
```

[

返回当前绘图引擎状态的画刷原点。

](qpointf.html)

[这个变量应该只用来当](qpointf.html)[state](qpaintenginestate.html#state)（ ）返回一个组合，其中包括[QPaintEngine.DirtyBrushOrigin](qpaintengine.html#DirtyFlag-enum)标志。

**See also** [state](qpaintenginestate.html#state)（）和[QPaintEngine.updateState](qpaintengine.html#updateState)（ ） 。

```
Qt.ClipOperation QPaintEngineState.clipOperation (self)
```

[

返回当前绘图引擎状态的剪辑操作。

](qt.html#ClipOperation-enum)

[这个变量应该只用来当](qt.html#ClipOperation-enum)[state](qpaintenginestate.html#state)（ ）返回一个组合，其中包括任[QPaintEngine.DirtyClipPath](qpaintengine.html#DirtyFlag-enum)或[QPaintEngine.DirtyClipRegion](qpaintengine.html#DirtyFlag-enum)标志。

**See also** [state](qpaintenginestate.html#state)（）和[QPaintEngine.updateState](qpaintengine.html#updateState)（ ） 。

```
QPainterPath QPaintEngineState.clipPath (self)
```

[

返回当前绘图引擎状态的剪辑路径。

](qpainterpath.html)

[这个变量应该只用来当](qpainterpath.html)[state](qpaintenginestate.html#state)（ ）返回一个组合，其中包括[QPaintEngine.DirtyClipPath](qpaintengine.html#DirtyFlag-enum)标志。

**See also** [state](qpaintenginestate.html#state)（）和[QPaintEngine.updateState](qpaintengine.html#updateState)（ ） 。

```
QRegion QPaintEngineState.clipRegion (self)
```

[

返回当前绘图引擎状态的剪辑区域。

](qregion.html)

[这个变量应该只用来当](qregion.html)[state](qpaintenginestate.html#state)（ ）返回一个组合，其中包括[QPaintEngine.DirtyClipRegion](qpaintengine.html#DirtyFlag-enum)标志。

**See also** [state](qpaintenginestate.html#state)（）和[QPaintEngine.updateState](qpaintengine.html#updateState)（ ） 。

```
QPainter.CompositionMode QPaintEngineState.compositionMode (self)
```

[

返回组成模式在当前的绘图引擎的状态。

](qpainter.html#CompositionMode-enum)

[这个变量应该只用来当](qpainter.html#CompositionMode-enum)[state](qpaintenginestate.html#state)（ ）返回一个组合，其中包括[QPaintEngine.DirtyCompositionMode](qpaintengine.html#DirtyFlag-enum)标志。

**See also** [state](qpaintenginestate.html#state)（）和[QPaintEngine.updateState](qpaintengine.html#updateState)（ ） 。

```
QFont QPaintEngineState.font (self)
```

[

返回当前绘图引擎状态的字体。

](qfont.html)

[这个变量应该只用来当](qfont.html)[state](qpaintenginestate.html#state)（ ）返回一个组合，其中包括[QPaintEngine.DirtyFont](qpaintengine.html#DirtyFlag-enum)标志。

**See also** [state](qpaintenginestate.html#state)（）和[QPaintEngine.updateState](qpaintengine.html#updateState)（ ） 。

```
bool QPaintEngineState.isClipEnabled (self)
```

返回剪裁是否启用或不在当前的绘图引擎的状态。

这个变量应该只用来当[state](qpaintenginestate.html#state)（ ）返回一个组合，其中包括[QPaintEngine.DirtyClipEnabled](qpaintengine.html#DirtyFlag-enum)标志。

**See also** [state](qpaintenginestate.html#state)（）和[QPaintEngine.updateState](qpaintengine.html#updateState)（ ） 。

```
QMatrix QPaintEngineState.matrix (self)
```

[

```
float QPaintEngineState.opacity (self)
```

返回当前绘图引擎状态的不透明度。

这个函数中引入了Qt 4.2中。

](qmatrix.html)

```
QPainter QPaintEngineState.painter (self)
```

[

返回一个指针，指向当前正在更新的绘图引擎的画家。

](qpainter.html)

```
QPen QPaintEngineState.pen (self)
```

[

返回当前绘图引擎状态的笔。

](qpen.html)

[这个变量应该只用来当](qpen.html)[state](qpaintenginestate.html#state)（ ）返回一个组合，其中包括[QPaintEngine.DirtyPen](qpaintengine.html#DirtyFlag-enum)标志。

**See also** [state](qpaintenginestate.html#state)（）和[QPaintEngine.updateState](qpaintengine.html#updateState)（ ） 。

```
bool QPaintEngineState.penNeedsResolving (self)
```

返回行程是否在坐标已被指定为界由当前渲染操作和必须解决（关于当前呈现的原语） 。

此功能被引入Qt的4.3 。

```
QPainter.RenderHints QPaintEngineState.renderHints (self)
```

[

返回当前绘图引擎状态的呈现提示。

](index.htm)

[这个变量应该只用来当](index.htm)[state](qpaintenginestate.html#state)（ ）返回一个组合，其中包括[QPaintEngine.DirtyHints](qpaintengine.html#DirtyFlag-enum)标志。

**See also** [state](qpaintenginestate.html#state)（）和[QPaintEngine.updateState](qpaintengine.html#updateState)（ ） 。

```
QPaintEngine.DirtyFlags QPaintEngineState.state (self)
```

[](index.htm)

[返回标志标识集，需要更新时，在调用期间更新绘图引擎的状态（即属性的组合](index.htm)[QPaintEngine.updateState](qpaintengine.html#updateState)（）函数） 。

**See also** [QPaintEngine.updateState](qpaintengine.html#updateState)（ ） 。

```
QTransform QPaintEngineState.transform (self)
```

[

返回当前绘图引擎状态矩阵。

](qtransform.html)

[这个变量应该只用来当](qtransform.html)[state](qpaintenginestate.html#state)（ ）返回一个组合，其中包括[QPaintEngine.DirtyTransform](qpaintengine.html#DirtyFlag-enum)标志。

此功能被引入Qt的4.3 。

**See also** [state](qpaintenginestate.html#state)（）和[QPaintEngine.updateState](qpaintengine.html#updateState)（ ） 。