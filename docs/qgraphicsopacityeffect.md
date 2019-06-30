# QGraphicsOpacityEffect Class Reference

## [[QtGui](index.htm) module]

该QGraphicsOpacityEffect类提供了一个不透明的效果。[More...](#details)

继承[QGraphicsEffect](qgraphicseffect.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `draw (self, QPainter painter)`
*   `float opacity (self)`
*   `QBrush opacityMask (self)`
*   `setOpacity (self, float opacity)`
*   `setOpacityMask (self, QBrush mask)`

### Qt Signals

*   `void opacityChanged (qreal)`
*   `void opacityMaskChanged (const QBrush&)`

* * *

## Detailed Description

该QGraphicsOpacityEffect类提供了一个不透明的效果。

不透明度效果呈现与不透明的来源。这种效果是用于使源半透明的，类似于一个淡入淡出序列是有用的。不透明度可以通过被修改的[setOpacity](qgraphicsopacityeffect.html#opacity-prop)（）函数。

默认情况下，不透明度为0.7 。

![](../img/graphicseffect-opacity.png)

* * *

## Method Documentation

```
QGraphicsOpacityEffect.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的[QGraphicsOpacityEffect](qgraphicsopacityeffect.html)实例。该_parent_参数被传递到[QGraphicsEffect](qgraphicseffect.html)的构造。

```
QGraphicsOpacityEffect.draw (self, QPainter painter)
```

从重新实现[QGraphicsEffect.draw](qgraphicseffect.html#draw)（ ） 。

```
float QGraphicsOpacityEffect.opacity (self)
```

```
QBrush QGraphicsOpacityEffect.opacityMask (self)
```

[

```
QGraphicsOpacityEffect.setOpacity (self, float opacity)
```

这种方法也是一个Qt槽与C + +的签名`void setOpacity(qreal)`。

```
QGraphicsOpacityEffect.setOpacityMask (self, QBrush mask)
```

这种方法也是一个Qt槽与C + +的签名`void setOpacityMask(const QBrush&)`。

* * *

## Qt Signal Documentation

```
void opacityChanged (qreal)
```

这是该信号的默认超载。

这个信号被发射时的效果的不透明度的变化。该_opacity_参数保存效果的新的不透明度。

```
void opacityMaskChanged (const QBrush&)
```

这是该信号的默认超载。

这个信号被发射时的效果的不透明蒙板的变化。该_mask_参数保存效果的新的不透明蒙板。

](qbrush.html)