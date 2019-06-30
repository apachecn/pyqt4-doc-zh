# QGraphicsColorizeEffect Class Reference

## [[QtGui](index.htm) module]

该QGraphicsColorizeEffect类提供了一个着色效果。[More...](#details)

继承[QGraphicsEffect](qgraphicseffect.html)。

### Methods

*   `__init__ (self, QObject parent = None)`
*   `QColor color (self)`
*   `draw (self, QPainter painter)`
*   `setColor (self, QColor c)`
*   `setStrength (self, float strength)`
*   `float strength (self)`

### Qt Signals

*   `void colorChanged (const QColor&)`
*   `void strengthChanged (qreal)`

* * *

## Detailed Description

该QGraphicsColorizeEffect类提供了一个着色效果。

一个着色效果与呈现的色调源其[color](qgraphicscolorizeeffect.html#color-prop)（ ） 。颜色可以用修改的[setColor](qgraphicscolorizeeffect.html#color-prop)（）函数。

默认情况下，颜色为淡蓝色（[QColor](qcolor.html)（ 0，0， 192 ））。

![](../img/graphicseffect-colorize.png)

* * *

## Method Documentation

```
QGraphicsColorizeEffect.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个新的[QGraphicsColorizeEffect](qgraphicscolorizeeffect.html)实例。该_parent_参数被传递到[QGraphicsEffect](qgraphicseffect.html)的构造。

```
QColor QGraphicsColorizeEffect.color (self)
```

[

```
QGraphicsColorizeEffect.draw (self, QPainter painter)
```

](qcolor.html)

[从重新实现](qcolor.html)[QGraphicsEffect.draw](qgraphicseffect.html#draw)（ ） 。

```
QGraphicsColorizeEffect.setColor (self, QColor c)
```

这种方法也是一个Qt槽与C + +的签名`void setColor(const QColor&)`。

```
QGraphicsColorizeEffect.setStrength (self, float strength)
```

这种方法也是一个Qt槽与C + +的签名`void setStrength(qreal)`。

```
float QGraphicsColorizeEffect.strength (self)
```

* * *

## Qt Signal Documentation

```
void colorChanged (const QColor&)
```

这是该信号的默认超载。

这个信号被发射时的效果的颜色变化。该_color_参数保存效果的新颜色。

```
void strengthChanged (qreal)
```

这是该信号的默认超载。

这个信号被发射时[setStrength](qgraphicscolorizeeffect.html#strength-prop)（ ）改变了着色强度性能。_strength_包含的着色效果的新的力量值。