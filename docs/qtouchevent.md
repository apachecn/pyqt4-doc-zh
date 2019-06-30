# QTouchEvent Class Reference

## [[QtGui](index.htm) module]

该QTouchEvent类包含描述一个触摸事件的参数。[More...](#details)

继承[QInputEvent](qinputevent.html)。

### Types

*   `enum DeviceType { TouchScreen, TouchPad }`
*   `class **[TouchPoint](index.htm)**`

### Methods

*   `__init__ (self, QEvent.Type eventType, DeviceType deviceType = QTouchEvent.TouchScreen, Qt.KeyboardModifiers modifiers = Qt.NoModifier, Qt.TouchPointStates touchPointStates = 0, list-of-QTouchEvent.TouchPoint touchPoints = QList&lt;QTouchEvent.TouchPoint&gt;())`
*   `__init__ (self, QTouchEvent)`
*   `DeviceType deviceType (self)`
*   `list-of-QTouchEvent.TouchPoint touchPoints (self)`
*   `Qt.TouchPointStates touchPointStates (self)`
*   `QWidget widget (self)`

* * *

## Detailed Description

该QTouchEvent类包含描述一个触摸事件的参数。

### Enabling Touch Events

触压时，释放，或移动触摸设备上的一个或多个触摸点（如触摸屏或轨道垫）事件发生。要接收触摸事件，小部件必须有[Qt.WA_AcceptTouchEvents](qt.html#WidgetAttribute-enum)属性设置和图形项目需要有[acceptTouchEvents](qgraphicsitem.html#setAcceptTouchEvents)属性设置为True。

当使用[QAbstractScrollArea](qabstractscrollarea.html)基于小部件，您应该启用[Qt.WA_AcceptTouchEvents](qt.html#WidgetAttribute-enum)属性上的滚动区域的[viewport](qabstractscrollarea.html#viewport)。

同样以[QMouseEvent](qmouseevent.html)， Qt的自动抓取上的小工具里面的第一次记者每个接触点，以及部件将接收所有的更新为触摸点，直到它被释放。需要注意的是它有可能为一个部件来接收事件为众多的接触点，并且多个部件可以在同一时间接收到触摸事件。

### Event Handling

所有的触摸事件的类型为[QEvent.TouchBegin](qevent.html#Type-enum)，[QEvent.TouchUpdate](qevent.html#Type-enum)或[QEvent.TouchEnd](qevent.html#Type-enum)。重新实现[QWidget.event](qwidget.html#event)（）或[QAbstractScrollArea.viewportEvent](qabstractscrollarea.html#viewportEvent)（ ）的部件和[QGraphicsItem.sceneEvent](qgraphicsitem.html#sceneEvent)（）在图形视图中的项目，以接收触摸事件。

该[QEvent.TouchUpdate](qevent.html#Type-enum)和[QEvent.TouchEnd](qevent.html#Type-enum)事件发送给窗口小部件或产品所接受的[QEvent.TouchBegin](qevent.html#Type-enum)事件。如果[QEvent.TouchBegin](qevent.html#Type-enum)事件是不能接受的，而不是由一个事件过滤器过滤，再没有进一步的触摸事件被发送，直到下一个[QEvent.TouchBegin](qevent.html#Type-enum)。

该[touchPoints](qtouchevent.html#touchPoints)（ ）函数返回包含在该事件的所有接触点的列表。关于每个触摸点信息可使用检索到的[QTouchEvent.TouchPoint](index.htm)类。该[Qt.TouchPointState](qt.html#TouchPointState-enum)枚举描述了不同的状态，一个触摸点可能有。

### Event Delivery and Propagation

默认情况下，[QWidget.event](qwidget.html#event)（）平移所述第一非主触摸点在QTouchEvent成[QMouseEvent](qmouseevent.html)。这使得它可以使在现有的小部件通常不处理QTouchEvent触摸事件。看看下面的这样做时需要一些特殊的注意事项的信息。

[QEvent.TouchBegin](qevent.html#Type-enum)是发送到插件的第一触摸事件。该[QEvent.TouchBegin](qevent.html#Type-enum)事件包含一个特殊的接受标志，指示接收者是否愿意事件。默认情况下，事件被接受。你应该调用[ignore](qevent.html#ignore)（ ）如果触摸事件不是由您的Widget处理。该[QEvent.TouchBegin](qevent.html#Type-enum)事件被传播到父控件链，直到一个小部件接受它[accept](qevent.html#accept)（ ） ，或者一个事件过滤器会消耗它。对于QGraphicsItems的[QEvent.TouchBegin](qevent.html#Type-enum)事件被传播到下鼠标（类似于用于QGraphicsItems鼠标事件传播）项目。

### Touch Point Grouping

如上面所提到的，有可能是几个部件可以接收QTouchEvents在同一时间。然而， Qt后，一定要永不重复发送[QEvent.TouchBegin](qevent.html#Type-enum)事件以相同的部件，它可以在传播过程中理论上发生，如果，例如，在用户触摸的2个独立的小部件在一个[QGroupBox](qgroupbox.html)和两个小部件忽略[QEvent.TouchBegin](qevent.html#Type-enum)事件。

为了避免这种情况， Qt会组新的接触点一起使用以下规则：

*   When the first touch point is detected, the destination widget is determined firstly by the location on screen and secondly by the propagation rules.
*   When additional touch points are detected, Qt first looks to see if there are any active touch points on any ancestor or descendent of the widget under the new touch point. If there are, the new touch point is grouped with the first, and the new touch point will be sent in a single QTouchEvent to the widget that handled the first touch point. (The widget under the new touch point will not receive an event).

这使得它可以为同级部件独立处理触摸事件，同时确保QTouchEvents的顺序永远是正确的。

### Mouse Events and the Primary Touch Point

QTouchEvent交付是独立于中[QMouseEvent](qmouseevent.html)。在一些窗口系统，鼠标事件也发送了[primary touch point](index.htm#isPrimary)。这意味着它有可能为你的widget能够同时接收QTouchEvent和[QMouseEvent](qmouseevent.html)对于相同的用户交互点。您可以使用[QTouchEvent.TouchPoint.isPrimary](index.htm#isPrimary)（ ）函数来确定的主要接触点。

请注意，在某些系统上，它可以接收触摸事件没有主触摸点。这一切都意味着，将有在QTouchEvent触摸点不产生鼠标事件。

### Caveats

*   As mentioned above, enabling touch events means multiple widgets can be receiving touch events simultaneously. Combined with the default [QWidget.event](qwidget.html#event)() handling for QTouchEvents, this gives you great flexibility in designing touch user interfaces. Be aware of the implications. For example, it is possible that the user is moving a [QSlider](qslider.html) with one finger and pressing a [QPushButton](qpushbutton.html) with another. The signals emitted by these widgets will be interleaved.
*   Recursion into the event loop using one of the exec() methods (e.g., [QDialog.exec](qdialog.html#exec)() or [QMenu.exec](qmenu.html#exec)()) in a QTouchEvent event handler is not supported. Since there are multiple event recipients, recursion may cause problems, including but not limited to lost events and unexpected infinite recursion.
*   QTouchEvents are not affected by a [mouse grab](qwidget.html#grabMouse) or an [active pop-up widget](qapplication.html#activePopupWidget). The behavior of QTouchEvents is undefined when opening a pop-up or grabbing the mouse while there are more than one active touch points.

* * *

## Type Documentation

```
QTouchEvent.DeviceType
```

该枚举表示所产生的一装置的类型[QTouchEvent](qtouchevent.html)。

| Constant | Value | Description |
| --- | --- | --- |
| `QTouchEvent.TouchScreen` | `0` | 在这种类型的设备中，触摸表面和显示器被集成。这意味着在表面和显示器通常具有相同的尺寸，使得在所述触摸点“物理位置和坐标报告之间的直接关系[QTouchEvent.TouchPoint](index.htm)。其结果是， Qt的允许用户直接与多个QWidgets和QGraphicsItems在同一时间进行交互。 |
| `QTouchEvent.TouchPad` | `1` | 在这种类型的设备，所述触摸表面是分开的显示。没有物理接触位置和屏幕上的坐标之间的直接关系。相反，它们被计算相对于当前鼠标位置，而用户必须使用触摸板移动至该参考点。不像触摸屏， Qt的允许用户只与一个单一的交互[QWidget](qwidget.html) or [QGraphicsItem](qgraphicsitem.html)在一个时间。 |

* * *

## Method Documentation

```
QTouchEvent.__init__ (self, QEvent.Type eventType, DeviceType deviceType = QTouchEvent.TouchScreen, Qt.KeyboardModifiers modifiers = Qt.NoModifier, Qt.TouchPointStates touchPointStates = 0, list-of-QTouchEvent.TouchPoint touchPoints = QList<QTouchEvent.TouchPoint>())
```

构造一个[QTouchEvent](qtouchevent.html)用给定的_eventType_，_deviceType_和_touchPoints_。该_touchPointStates_和_modifiers_是当前触摸点的状态和键盘功能键在事件发生的时间。

```
QTouchEvent.__init__ (self, QTouchEvent)
```

```
DeviceType QTouchEvent.deviceType (self)
```

[](qtouchevent.html#DeviceType-enum)

[返回触摸设备类型，它的类型是](qtouchevent.html#DeviceType-enum)[DeviceType](qtouchevent.html#DeviceType-enum)。

```
list-of-QTouchEvent.TouchPoint QTouchEvent.touchPoints (self)
```

返回包含在该触摸事件的触摸点的列表。

```
Qt.TouchPointStates QTouchEvent.touchPointStates (self)
```

[

返回此事件的一个位的所有接触点或国家。

](index.htm)

```
QWidget QTouchEvent.widget (self)
```

[

返回上发生事件的小部件。

](qwidget.html)