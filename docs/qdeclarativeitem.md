# QDeclarativeItem Class Reference

## [[QtDeclarative](index.htm) module]

该QDeclarativeItem类提供了最基本的QML中所有可视的项目。[More...](#details)

继承[QGraphicsObject](qgraphicsobject.html)和[QDeclarativeParserStatus](qdeclarativeparserstatus.html)。

### Types

*   `enum TransformOrigin { TopLeft, Top, TopRight, Left, ..., BottomRight }`

### Methods

*   `__init__ (self, QDeclarativeItem parent = None)`
*   `float baselineOffset (self)`
*   `QRectF boundingRect (self)`
*   `QRectF childrenRect (self)`
*   `classBegin (self)`
*   `bool clip (self)`
*   `componentComplete (self)`
*   `bool event (self, QEvent)`
*   `geometryChanged (self, QRectF newGeometry, QRectF oldGeometry)`
*   `bool hasFocus (self)`
*   `bool heightValid (self)`
*   `float implicitHeight (self)`
*   `float implicitWidth (self)`
*   `inputMethodEvent (self, QInputMethodEvent)`
*   `QVariant inputMethodQuery (self, Qt.InputMethodQuery query)`
*   `bool isComponentComplete (self)`
*   `QVariant itemChange (self, QGraphicsItem.GraphicsItemChange, QVariant)`
*   `bool keepMouseGrab (self)`
*   `keyPressEvent (self, QKeyEvent event)`
*   `keyReleaseEvent (self, QKeyEvent event)`
*   `paint (self, QPainter, QStyleOptionGraphicsItem, QWidget)`
*   `QDeclarativeItem parentItem (self)`
*   `bool sceneEvent (self, QEvent)`
*   `setBaselineOffset (self, float)`
*   `setClip (self, bool)`
*   `setHeight (self, float)`
*   `setImplicitHeight (self, float)`
*   `setImplicitWidth (self, float)`
*   `setKeepMouseGrab (self, bool)`
*   `setParentItem (self, QDeclarativeItem parent)`
*   `setSmooth (self, bool)`
*   `setTransformOrigin (self, TransformOrigin)`
*   `setWidth (self, float)`
*   `bool smooth (self)`
*   `TransformOrigin transformOrigin (self)`
*   `bool widthValid (self)`

* * *

## Detailed Description

该QDeclarativeItem类提供了最基本的QML中所有可视的项目。

Qt中声明的所有视觉项目都继承自QDeclarativeItem 。虽然QDeclarativeItem没有视觉外观，它定义了所有属于通用的可视化项目的属性 - 例如x和y位置，宽度和高度，[anchoring](index.htm#anchor-layout)和按键处理。

你可以继承QDeclarativeItem提供继承这些功能你自己的自定义可视项目。需要注意的是，因为它不画任何东西， QDeclarativeItem设置[QGraphicsItem.ItemHasNoContents](qgraphicsitem.html#GraphicsItemFlag-enum)标志。如果子类QDeclarativeItem创建一个可视化的项目，您将需要取消设置此标志。

* * *

## Type Documentation

```
QDeclarativeItem.TransformOrigin
```

控制点哪些简单的变换一样的规模应用。

| Constant | Value | Description |
| --- | --- | --- |
| `QDeclarativeItem.TopLeft` | `0` | 该项目的左上角。 |
| `QDeclarativeItem.Top` | `1` | 该项目的顶部的中心点。 |
| `QDeclarativeItem.TopRight` | `2` | 该项目的右上角。 |
| `QDeclarativeItem.Left` | `3` | 最左边的点的垂直中间。 |
| `QDeclarativeItem.Center` | `4` | 该项目的中心。 |
| `QDeclarativeItem.Right` | `5` | 最右点的垂直中间。 |
| `QDeclarativeItem.BottomLeft` | `6` | 该项目的左下角。 |
| `QDeclarativeItem.Bottom` | `7` | 该项目的底部的中心点。 |
| `QDeclarativeItem.BottomRight` | `8` | 该项目的右下角。 |

* * *

## Method Documentation

```
QDeclarativeItem.__init__ (self, QDeclarativeItem parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QDeclarativeItem](qdeclarativeitem.html)用给定的_parent_。

```
float QDeclarativeItem.baselineOffset (self)
```

```
QRectF QDeclarativeItem.boundingRect (self)
```

[](qrectf.html)

```
QRectF QDeclarativeItem.childrenRect (self)
```

[

```
QDeclarativeItem.classBegin (self)
```

```
bool QDeclarativeItem.clip (self)
```

```
QDeclarativeItem.componentComplete (self)
```

```
bool QDeclarativeItem.event (self, QEvent)
```

```
QDeclarativeItem.geometryChanged (self, QRectF newGeometry, QRectF oldGeometry)
```

调用此函数从处理这个项目的变化几何_oldGeometry_至_newGeometry_。如果两个几何是相同的，它不会做任何事情。

```
bool QDeclarativeItem.hasFocus (self)
```

```
bool QDeclarativeItem.heightValid (self)
```

返回是否高度属性已显式设置。

```
float QDeclarativeItem.implicitHeight (self)
```

```
float QDeclarativeItem.implicitWidth (self)
```

```
QDeclarativeItem.inputMethodEvent (self, QInputMethodEvent)
```

```
QVariant QDeclarativeItem.inputMethodQuery (self, Qt.InputMethodQuery query)
```

```
bool QDeclarativeItem.isComponentComplete (self)
```

返回True如果建设QML组件是完整的，否则返回False 。

它通常是可取的延迟一定的处理，直到该组件完成。

](qrectf.html)

[**See also**](qrectf.html) [componentComplete](qdeclarativeparserstatus.html#componentComplete)（ ） 。

```
QVariant QDeclarativeItem.itemChange (self, QGraphicsItem.GraphicsItemChange, QVariant)
```

```
bool QDeclarativeItem.keepMouseGrab (self)
```

返回一个值，指示鼠标输入是否应该保持这资料的独家。

**See also** [setKeepMouseGrab](qdeclarativeitem.html#setKeepMouseGrab)（ ） 。

```
QDeclarativeItem.keyPressEvent (self, QKeyEvent event)
```

```
QDeclarativeItem.keyReleaseEvent (self, QKeyEvent event)
```

```
QDeclarativeItem.paint (self, QPainter, QStyleOptionGraphicsItem, QWidget)
```

```
QDeclarativeItem QDeclarativeItem.parentItem (self)
```

[

```
bool QDeclarativeItem.sceneEvent (self, QEvent)
```

```
QDeclarativeItem.setBaselineOffset (self, float)
```

```
QDeclarativeItem.setClip (self, bool)
```

```
QDeclarativeItem.setHeight (self, float)
```

```
QDeclarativeItem.setImplicitHeight (self, float)
```

设置项的隐含高度_h_。这是由确定的内容的其他属性隐含的高度。

](qdeclarativeitem.html)

[**See also**](qdeclarativeitem.html) [implicitHeight](qdeclarativeitem.html#implicitHeight-prop)（ ） 。

```
QDeclarativeItem.setImplicitWidth (self, float)
```

设置项的隐含宽度_w_。这是由确定的内容的其他属性隐含的宽度。

**See also** [implicitWidth](qdeclarativeitem.html#implicitWidth-prop)（ ） 。

```
QDeclarativeItem.setKeepMouseGrab (self, bool)
```

该标志指示鼠标是否应该保留此项目设置为_keep_。

这对于那些希望抓住并保持鼠标交互下一个预定义手势的项目有用。例如，一个项目，有兴趣水平移动鼠标可设置keepMouseGrab为True一旦已超过阈值。一旦keepMouseGrab已被设置为True，则过滤项将不响应鼠标事件。

如果该项目没有表明它希望保留鼠标抓取，过滤项目可能窃取抢。例如， Flickable可能会尝试，如果它检测到用户已经开始移动视偷鼠标抓取。

**See also** [keepMouseGrab](qdeclarativeitem.html#keepMouseGrab)（ ） 。

```
QDeclarativeItem.setParentItem (self, QDeclarativeItem parent)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

```
QDeclarativeItem.setSmooth (self, bool)
```

```
QDeclarativeItem.setTransformOrigin (self, TransformOrigin)
```

设置变换_origin_。

**See also** [transformOrigin](qdeclarativeitem.html#transformOrigin)（ ） 。

```
QDeclarativeItem.setWidth (self, float)
```

```
bool QDeclarativeItem.smooth (self)
```

```
TransformOrigin QDeclarativeItem.transformOrigin (self)
```

[

返回当前变换原点。

](qdeclarativeitem.html#TransformOrigin-enum)

[**See also**](qdeclarativeitem.html#TransformOrigin-enum) [setTransformOrigin](qdeclarativeitem.html#setTransformOrigin)（ ） 。

```
bool QDeclarativeItem.widthValid (self)
```

返回是否width属性被显式设置。