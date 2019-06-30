# QGraphicsBlurEffect Class Reference

## [[QtGui](index.htm) module]

该QGraphicsBlurEffect类提供了一个模糊效果。[More...](#details)

继承[QGraphicsEffect](qgraphicseffect.html)。

### Types

*   `enum BlurHint { PerformanceHint, QualityHint, AnimationHint }`
*   `class **[BlurHints](index.htm)**`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `BlurHints blurHints (self)`
*   `float blurRadius (self)`
*   `QRectF boundingRectFor (self, QRectF rect)`
*   `draw (self, QPainter painter)`
*   `setBlurHints (self, BlurHints hints)`
*   `setBlurRadius (self, float blurRadius)`

### Qt Signals

*   `void blurHintsChanged (QGraphicsBlurEffect::BlurHints)`
*   `void blurRadiusChanged (qreal)`

* * *

## Detailed Description

该QGraphicsBlurEffect类提供了一个模糊效果。

一个模糊效果模糊的来源。这种效果是减少细节，当源失去焦点，如有用的，你想提请注意的其他元素。信息的详细程度可使用修改的[setBlurRadius](qgraphicsblureffect.html#blurRadius-prop)（）函数。使用[setBlurHints](qgraphicsblureffect.html#blurHints-prop)（ ）选择模糊的提示。

默认情况下，模糊半径为5像素。模糊半径被指定在设备坐标。

![](../img/graphicseffect-blur.png)

* * *

## Type Documentation

```
QGraphicsBlurEffect.BlurHint
```

这个枚举变量描述了可用于控制如何虚化效果应用的可能的提示。该提示可能没有效果在所有油漆引擎。

| Constant | Value | Description |
| --- | --- | --- |
| `QGraphicsBlurEffect.PerformanceHint` | `0x00` | 表示渲染性能是最重要的因素，在低质量的潜在成本。 |
| `QGraphicsBlurEffect.QualityHint` | `0x01` | 表示渲染质量是最重要的因素，在低性能的潜在成本。 |
| `QGraphicsBlurEffect.AnimationHint` | `0x02` | 表明模糊半径将被动画化，暗示该实现可以保持源的模糊verisons的缓存。请不要使用此提示如果源将是动态变化的。 |

这个枚举被引入或修改的Qt 4.6 。

该BlurHints类型是一个typedef为[QFlags](index.htm)\u003cBlurHint\u003e 。它存储BlurHint值的或组合。

**See also** [blurHints](qgraphicsblureffect.html#blurHints-prop)（）和[setBlurHints](qgraphicsblureffect.html#blurHints-prop)（ ） 。

* * *

## Method Documentation

```
QGraphicsBlurEffect.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的[QGraphicsBlurEffect](qgraphicsblureffect.html)实例。该_parent_参数被传递到[QGraphicsEffect](qgraphicseffect.html)的构造。

```
BlurHints QGraphicsBlurEffect.blurHints (self)
```

[

```
float QGraphicsBlurEffect.blurRadius (self)
```

](index.htm)

```
QRectF QGraphicsBlurEffect.boundingRectFor (self, QRectF rect)
```

[](qrectf.html)

[从重新实现](qrectf.html)[QGraphicsEffect.boundingRectFor](qgraphicseffect.html#boundingRectFor)（ ） 。

```
QGraphicsBlurEffect.draw (self, QPainter painter)
```

从重新实现[QGraphicsEffect.draw](qgraphicseffect.html#draw)（ ） 。

```
QGraphicsBlurEffect.setBlurHints (self, BlurHints hints)
```

这种方法也是一个Qt槽与C + +的签名`void setBlurHints(QGraphicsBlurEffect::BlurHints)`。

```
QGraphicsBlurEffect.setBlurRadius (self, float blurRadius)
```

这种方法也是一个Qt槽与C + +的签名`void setBlurRadius(qreal)`。

* * *

## Qt Signal Documentation

```
void blurHintsChanged (QGraphicsBlurEffect::BlurHints)
```

这是该信号的默认超载。

这个信号被发射时的效果的模糊暗示的改变。该_hints_参数保存效果的新型模糊的提示。

```
void blurRadiusChanged (qreal)
```

这是该信号的默认超载。

这个信号被发射时的效果的模糊半径的变化。该_radius_参数保存效果的新的模糊半径。