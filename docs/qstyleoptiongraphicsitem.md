# QStyleOptionGraphicsItem Class Reference

## [[QtGui](index.htm) module]

该QStyleOptionGraphicsItem类是用来描述绘制所需要的参数[QGraphicsItem](qgraphicsitem.html)。[More...](#details)

继承[QStyleOption](qstyleoption.html)。

### Types

*   `enum StyleOptionType { Type }`
*   `enum StyleOptionVersion { Version }`

### Methods

*   `__init__ (self)`
*   `__init__ (self, QStyleOptionGraphicsItem other)`

### Static Methods

*   `float levelOfDetailFromTransform (QTransform worldTransform)`

### Members

*   `QRectF **[exposedRect](qstyleoptiongraphicsitem.html#exposedRect-var)**`
*   `float **[levelOfDetail](qstyleoptiongraphicsitem.html#levelOfDetail-var)**`
*   `QMatrix **[matrix](qstyleoptiongraphicsitem.html#matrix-var)**`

* * *

## Detailed Description

该QStyleOptionGraphicsItem类是用来描述绘制所需要的参数[QGraphicsItem](qgraphicsitem.html)。

出于性能方面的原因，访问成员变量是直接的（即使用`.` or `-&gt;`操作符）。这种低层次的感觉，使结构简单的使用，并强调这些都是简单的参数。

举一个例子展示风格选择如何使用，请参阅[Styles](index.htm)例子。

* * *

## Type Documentation

```
QStyleOptionGraphicsItem.StyleOptionType
```

此枚举是用来保存有关样式选项的类型信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionGraphicsItem.Type` | `SO_GraphicsItem` | 风格选择该类型提供（[SO_GraphicsItem](qstyleoption.html#OptionType-enum)这个类） 。 |

该类型在内部使用[QStyleOption](qstyleoption.html)，它的子类，并[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（）来确定的样式选项的类型。一般来说，你不需要担心这个，除非你想创建自己的[QStyleOption](qstyleoption.html)子类和你自己的风格。

**See also** [StyleOptionVersion](qstyleoptiongraphicsitem.html#StyleOptionVersion-enum)。

```
QStyleOptionGraphicsItem.StyleOptionVersion
```

此枚举是用来保存有关样式选项的版本信息，并定义每个[QStyleOption](qstyleoption.html)子类。

| Constant | Value | Description |
| --- | --- | --- |
| `QStyleOptionGraphicsItem.Version` | `1` | 1 |

的版本是由[QStyleOption](qstyleoption.html)子类实现不破坏兼容性扩展。如果你使用[qstyleoption_cast](qstyleoption.html#qstyleoption_cast)（ ） ，你通常并不需要检查它。

**See also** [StyleOptionType](qstyleoptiongraphicsitem.html#StyleOptionType-enum)。

* * *

## Method Documentation

```
QStyleOptionGraphicsItem.__init__ (self)
```

构造一个[QStyleOptionGraphicsItem](qstyleoptiongraphicsitem.html)。

```
QStyleOptionGraphicsItem.__init__ (self, QStyleOptionGraphicsItem other)
```

构造的副本_other_。

```
float QStyleOptionGraphicsItem.levelOfDetailFromTransform (QTransform worldTransform)
```

返回细节从水平_worldTransform_。

它的值代表一个统一的矩形的高度和宽度的最大值，映射的使用_worldTransform_用于绘制该项目的画家。默认情况下，如果没有转换被应用，其值为1 。如果缩小1:2，详细程度将是0.5 ，而且如果放大​​2:1，它的值是2。

此功能被引入Qt的4.6 。

* * *

## Member Documentation

```
QRectF exposedRect
```

[

这个变量保存外露的矩形，在项目坐标。

](qrectf.html)

[利用这个矩形，加快项目图纸时，该项目只有部分被暴露。如果整个产品被暴露，这个长方形将是一样](qrectf.html)[QGraphicsItem.boundingRect](qgraphicsitem.html#boundingRect)（ ） 。

该成员仅适用于具有项目初始化[QGraphicsItem.ItemUsesExtendedStyleOption](qgraphicsitem.html#GraphicsItemFlag-enum)标志设置。

```
float levelOfDetail
```

```
QMatrix matrix
```

[](qmatrix.html)