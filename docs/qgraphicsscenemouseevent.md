# QGraphicsSceneMouseEvent Class Reference

## [[QtGui](index.htm) module]

该QGraphicsSceneMouseEvent类提供在图形视图框架的鼠标事件。[More...](#details)

继承[QGraphicsSceneEvent](qgraphicssceneevent.html)。

### Methods

*   `Qt.MouseButton button (self)`
*   `QPointF buttonDownPos (self, Qt.MouseButton button)`
*   `QPointF buttonDownScenePos (self, Qt.MouseButton button)`
*   `QPoint buttonDownScreenPos (self, Qt.MouseButton button)`
*   `Qt.MouseButtons buttons (self)`
*   `QPointF lastPos (self)`
*   `QPointF lastScenePos (self)`
*   `QPoint lastScreenPos (self)`
*   `Qt.KeyboardModifiers modifiers (self)`
*   `QPointF pos (self)`
*   `QPointF scenePos (self)`
*   `QPoint screenPos (self)`

* * *

## Detailed Description

该QGraphicsSceneMouseEvent类提供在图形视图框架的鼠标事件。

当[QGraphicsView](qgraphicsview.html)收到[QMouseEvent](qmouseevent.html)，它转换到一个QGraphicsSceneMouseEvent 。然后，此事件转发到[QGraphicsScene](qgraphicsscene.html)与视图相关联。如果事件没有被处理的情景时，视图可以使用它，例如，对于[DragMode](qgraphicsview.html#DragMode-enum)。

除了包含该事件的项目，场景，和屏幕坐标（如[pos](qgraphicsscenemouseevent.html#pos)（ ）[scenePos](qgraphicsscenemouseevent.html#scenePos)（）和[screenPos](qgraphicsscenemouseevent.html#screenPos)（ ） ） ，鼠标事件还包含由视图收到以前的鼠标事件的坐标。这些可以被检索以[lastPos](qgraphicsscenemouseevent.html#lastPos)（ ）[lastScreenPos](qgraphicsscenemouseevent.html#lastScreenPos)（）和[lastScenePos](qgraphicsscenemouseevent.html#lastScenePos)（ ） 。

* * *

## Method Documentation

```
Qt.MouseButton QGraphicsSceneMouseEvent.button (self)
```

[

返回鼠标按钮（如果有的话）引发事件。

](qt.html#MouseButton-enum)

[**See also**](qt.html#MouseButton-enum) [buttons](qgraphicsscenemouseevent.html#buttons)（）和[modifiers](qgraphicsscenemouseevent.html#modifiers)（ ） 。

```
QPointF QGraphicsSceneMouseEvent.buttonDownPos (self, Qt.MouseButton button)
```

[

返回项目的鼠标光标位置坐标指定的地方_button_被点击了。

](qpointf.html)

[**See also**](qpointf.html) [buttonDownScenePos](qgraphicsscenemouseevent.html#buttonDownScenePos)（ ）[buttonDownScreenPos](qgraphicsscenemouseevent.html#buttonDownScreenPos)（）和[pos](qgraphicsscenemouseevent.html#pos)（ ） 。

```
QPointF QGraphicsSceneMouseEvent.buttonDownScenePos (self, Qt.MouseButton button)
```

[

返回场景中的鼠标光标位置坐标指定的地方_button_被点击了。

](qpointf.html)

[**See also**](qpointf.html) [buttonDownPos](qgraphicsscenemouseevent.html#buttonDownPos)（ ）[buttonDownScreenPos](qgraphicsscenemouseevent.html#buttonDownScreenPos)（）和[scenePos](qgraphicsscenemouseevent.html#scenePos)（ ） 。

```
QPoint QGraphicsSceneMouseEvent.buttonDownScreenPos (self, Qt.MouseButton button)
```

[

返回屏幕的鼠标光标位置坐标指定的地方_button_被点击了。

](qpoint.html)

[**See also**](qpoint.html) [screenPos](qgraphicsscenemouseevent.html#screenPos)（ ）[buttonDownPos](qgraphicsscenemouseevent.html#buttonDownPos)（）和[buttonDownScenePos](qgraphicsscenemouseevent.html#buttonDownScenePos)（ ） 。

```
Qt.MouseButtons QGraphicsSceneMouseEvent.buttons (self)
```

[

返回的是在事件被发送的时间按下鼠标按钮的组合。

](index.htm)

[**See also**](index.htm) [button](qgraphicsscenemouseevent.html#button)（）和[modifiers](qgraphicsscenemouseevent.html#modifiers)（ ） 。

```
QPointF QGraphicsSceneMouseEvent.lastPos (self)
```

[

返回项的坐标最后记录的鼠标光标位置。

](qpointf.html)

[**See also**](qpointf.html) [lastScenePos](qgraphicsscenemouseevent.html#lastScenePos)（ ）[lastScreenPos](qgraphicsscenemouseevent.html#lastScreenPos)（）和[pos](qgraphicsscenemouseevent.html#pos)（ ） 。

```
QPointF QGraphicsSceneMouseEvent.lastScenePos (self)
```

[

返回场景坐标中的最后一个记录鼠标的光标位置。最后记录的位置是由创建该事件的观点获得了以前的鼠标事件的位置。

](qpointf.html)

[**See also**](qpointf.html) [lastPos](qgraphicsscenemouseevent.html#lastPos)（ ）[lastScreenPos](qgraphicsscenemouseevent.html#lastScreenPos)（）和[scenePos](qgraphicsscenemouseevent.html#scenePos)（ ） 。

```
QPoint QGraphicsSceneMouseEvent.lastScreenPos (self)
```

[

返回屏幕坐标的最后一个记录鼠标的光标位置。最后记录的位置是由创建该事件的观点获得了以前的鼠标事件的位置。

](qpoint.html)

[**See also**](qpoint.html) [lastPos](qgraphicsscenemouseevent.html#lastPos)（ ）[lastScenePos](qgraphicsscenemouseevent.html#lastScenePos)（）和[screenPos](qgraphicsscenemouseevent.html#screenPos)（ ） 。

```
Qt.KeyboardModifiers QGraphicsSceneMouseEvent.modifiers (self)
```

[

返回当前使用的键盘功能键在事件的发送时间。

](index.htm)

[**See also**](index.htm) [buttons](qgraphicsscenemouseevent.html#buttons)（）和[button](qgraphicsscenemouseevent.html#button)（ ） 。

```
QPointF QGraphicsSceneMouseEvent.pos (self)
```

[

返回项目坐标中的鼠标光标位置。

](qpointf.html)

[**See also**](qpointf.html) [scenePos](qgraphicsscenemouseevent.html#scenePos)（ ）[screenPos](qgraphicsscenemouseevent.html#screenPos)（）和[lastPos](qgraphicsscenemouseevent.html#lastPos)（ ） 。

```
QPointF QGraphicsSceneMouseEvent.scenePos (self)
```

[

返回场景坐标中的鼠标光标位置。

](qpointf.html)

[**See also**](qpointf.html) [pos](qgraphicsscenemouseevent.html#pos)（ ）[screenPos](qgraphicsscenemouseevent.html#screenPos)（）和[lastScenePos](qgraphicsscenemouseevent.html#lastScenePos)（ ） 。

```
QPoint QGraphicsSceneMouseEvent.screenPos (self)
```

[

返回在屏幕坐标中的鼠标光标位置。

](qpoint.html)

[**See also**](qpoint.html) [pos](qgraphicsscenemouseevent.html#pos)（ ）[scenePos](qgraphicsscenemouseevent.html#scenePos)（）和[lastScreenPos](qgraphicsscenemouseevent.html#lastScreenPos)（ ） 。