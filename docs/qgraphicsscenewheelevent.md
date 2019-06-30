# QGraphicsSceneWheelEvent Class Reference

## [[QtGui](index.htm) module]

该QGraphicsSceneWheelEvent类提供在图形滚轮事件视图框架。[More...](#details)

继承[QGraphicsSceneEvent](qgraphicssceneevent.html)。

### Methods

*   `Qt.MouseButtons buttons (self)`
*   `int delta (self)`
*   `Qt.KeyboardModifiers modifiers (self)`
*   `Qt.Orientation orientation (self)`
*   `QPointF pos (self)`
*   `QPointF scenePos (self)`
*   `QPoint screenPos (self)`

* * *

## Detailed Description

该QGraphicsSceneWheelEvent类提供在图形滚轮事件视图框架。

该QGraphicsSceneWheelEvent类提供在图形滚轮事件视图框架。

[QWheelEvent](qwheelevent.html)s内收到由[QGraphicsView](qgraphicsview.html)被翻译成QGraphicsSceneWheelEvents ，它的转换[QWheelEvent.globalPos](qwheelevent.html#globalPos)（ ）到项目，场景，和屏幕坐标（[pos](qgraphicsscenewheelevent.html#pos)（ ）[scenePos](qgraphicsscenewheelevent.html#scenePos)（）和[screenPos](qgraphicsscenewheelevent.html#screenPos)（））。

* * *

## Method Documentation

```
Qt.MouseButtons QGraphicsSceneWheelEvent.buttons (self)
```

[

返回被压在车轮发生事件的鼠标按键。

](index.htm)

[**See also**](index.htm) [modifiers](qgraphicsscenewheelevent.html#modifiers)（ ） 。

```
int QGraphicsSceneWheelEvent.delta (self)
```

返回一定程度的车轮转动的距离，在八分（ 1/8S ） 。正值表示滚轮是向前旋转远离用户，负值表示滚轮被向后旋转朝向用户。

大多数类型的鼠标，步长为15度工作，在这种情况下，增量值是120 （== 15 * 8）的倍数。

```
Qt.KeyboardModifiers QGraphicsSceneWheelEvent.modifiers (self)
```

[

返回键盘功能键时，滚轮事件发生的活跃。

](index.htm)

[**See also**](index.htm) [buttons](qgraphicsscenewheelevent.html#buttons)（ ） 。

```
Qt.Orientation QGraphicsSceneWheelEvent.orientation (self)
```

[

返回车轮方向。

](qt.html#Orientation-enum)

```
QPointF QGraphicsSceneWheelEvent.pos (self)
```

[

返回时，滚轮事件发生光标在项目的位置坐标。

](qpointf.html)

[**See also**](qpointf.html) [scenePos](qgraphicsscenewheelevent.html#scenePos)（）和[screenPos](qgraphicsscenewheelevent.html#screenPos)（ ） 。

```
QPointF QGraphicsSceneWheelEvent.scenePos (self)
```

[

返回时，滚轮事件发生光标在现场的位置坐标。

](qpointf.html)

[**See also**](qpointf.html) [pos](qgraphicsscenewheelevent.html#pos)（）和[screenPos](qgraphicsscenewheelevent.html#screenPos)（ ） 。

```
QPoint QGraphicsSceneWheelEvent.screenPos (self)
```

[

返回时，滚轮事件发生光标在屏幕上的位置坐标。

](qpoint.html)

[**See also**](qpoint.html) [pos](qgraphicsscenewheelevent.html#pos)（）和[scenePos](qgraphicsscenewheelevent.html#scenePos)（ ） 。