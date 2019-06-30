# QGraphicsScene Class Reference

## [[QtGui](index.htm) module]

在QGraphicsScene类提供了用于管理大量的2D图形项的表面上。[More...](#details)

继承[QObject](qobject.html)。

### Types

*   `enum ItemIndexMethod { BspTreeIndex, NoIndex }`
*   `enum SceneLayer { ItemLayer, BackgroundLayer, ForegroundLayer, AllLayers }`
*   `class **[SceneLayers](index.htm)**`

### Methods

*   `__init__ (self, QObject parent = None)`
*   `__init__ (self, QRectF sceneRect, QObject parent = None)`
*   `__init__ (self, float x, float y, float width, float height, QObject parent = None)`
*   `QGraphicsItem activePanel (self)`
*   `QGraphicsWidget activeWindow (self)`
*   `QGraphicsEllipseItem addEllipse (self, QRectF rect, QPen pen = QPen(), QBrush brush = QBrush())`
*   `QGraphicsEllipseItem addEllipse (self, float x, float y, float w, float h, QPen pen = QPen(), QBrush brush = QBrush())`
*   `addItem (self, QGraphicsItem item)`
*   `QGraphicsLineItem addLine (self, QLineF line, QPen pen = QPen())`
*   `QGraphicsLineItem addLine (self, float x1, float y1, float x2, float y2, QPen pen = QPen())`
*   `QGraphicsPathItem addPath (self, QPainterPath path, QPen pen = QPen(), QBrush brush = QBrush())`
*   `QGraphicsPixmapItem addPixmap (self, QPixmap pixmap)`
*   `QGraphicsPolygonItem addPolygon (self, QPolygonF polygon, QPen pen = QPen(), QBrush brush = QBrush())`
*   `QGraphicsRectItem addRect (self, QRectF rect, QPen pen = QPen(), QBrush brush = QBrush())`
*   `QGraphicsRectItem addRect (self, float x, float y, float w, float h, QPen pen = QPen(), QBrush brush = QBrush())`
*   `QGraphicsSimpleTextItem addSimpleText (self, QString text, QFont font = QFont())`
*   `QGraphicsTextItem addText (self, QString text, QFont font = QFont())`
*   `QGraphicsProxyWidget addWidget (self, QWidget widget, Qt.WindowFlags flags = 0)`
*   `advance (self)`
*   `QBrush backgroundBrush (self)`
*   `int bspTreeDepth (self)`
*   `clear (self)`
*   `clearFocus (self)`
*   `clearSelection (self)`
*   `list-of-QGraphicsItem collidingItems (self, QGraphicsItem item, Qt.ItemSelectionMode mode = Qt.IntersectsItemShape)`
*   `contextMenuEvent (self, QGraphicsSceneContextMenuEvent event)`
*   `QGraphicsItemGroup createItemGroup (self, list-of-QGraphicsItem items)`
*   `destroyItemGroup (self, QGraphicsItemGroup group)`
*   `dragEnterEvent (self, QGraphicsSceneDragDropEvent event)`
*   `dragLeaveEvent (self, QGraphicsSceneDragDropEvent event)`
*   `dragMoveEvent (self, QGraphicsSceneDragDropEvent event)`
*   `drawBackground (self, QPainter painter, QRectF rect)`
*   `drawForeground (self, QPainter painter, QRectF rect)`
*   `drawItems (self, QPainter painter, list-of-QGraphicsItem items, list-of-QStyleOptionGraphicsItem options, QWidget widget = None)`
*   `dropEvent (self, QGraphicsSceneDragDropEvent event)`
*   `bool event (self, QEvent event)`
*   `bool eventFilter (self, QObject watched, QEvent event)`
*   `focusInEvent (self, QFocusEvent event)`
*   `QGraphicsItem focusItem (self)`
*   `bool focusNextPrevChild (self, bool next)`
*   `focusOutEvent (self, QFocusEvent event)`
*   `QFont font (self)`
*   `QBrush foregroundBrush (self)`
*   `bool hasFocus (self)`
*   `float height (self)`
*   `helpEvent (self, QGraphicsSceneHelpEvent event)`
*   `inputMethodEvent (self, QInputMethodEvent event)`
*   `QVariant inputMethodQuery (self, Qt.InputMethodQuery query)`
*   `invalidate (self, QRectF rect = QRectF(), SceneLayers layers = QGraphicsScene.AllLayers)`
*   `invalidate (self, float x, float y, float w, float h, SceneLayers layers = QGraphicsScene.AllLayers)`
*   `bool isActive (self)`
*   `bool isSortCacheEnabled (self)`
*   `QGraphicsItem itemAt (self, QPointF pos)`
*   `QGraphicsItem itemAt (self, float x, float y)`
*   `QGraphicsItem itemAt (self, QPointF pos, QTransform deviceTransform)`
*   `QGraphicsItem itemAt (self, float x, float y, QTransform deviceTransform)`
*   `ItemIndexMethod itemIndexMethod (self)`
*   `list-of-QGraphicsItem items (self)`
*   `list-of-QGraphicsItem items (self, Qt.SortOrder order)`
*   `list-of-QGraphicsItem items (self, QPointF pos)`
*   `list-of-QGraphicsItem items (self, QPointF pos, Qt.ItemSelectionMode mode, Qt.SortOrder order, QTransform deviceTransform = QTransform())`
*   `list-of-QGraphicsItem items (self, QRectF rectangle, Qt.ItemSelectionMode mode = Qt.IntersectsItemShape)`
*   `list-of-QGraphicsItem items (self, QRectF rect, Qt.ItemSelectionMode mode, Qt.SortOrder order, QTransform deviceTransform = QTransform())`
*   `list-of-QGraphicsItem items (self, QPolygonF polygon, Qt.ItemSelectionMode mode = Qt.IntersectsItemShape)`
*   `list-of-QGraphicsItem items (self, QPolygonF polygon, Qt.ItemSelectionMode mode, Qt.SortOrder order, QTransform deviceTransform = QTransform())`
*   `list-of-QGraphicsItem items (self, QPainterPath path, Qt.ItemSelectionMode mode = Qt.IntersectsItemShape)`
*   `list-of-QGraphicsItem items (self, QPainterPath path, Qt.ItemSelectionMode mode, Qt.SortOrder order, QTransform deviceTransform = QTransform())`
*   `list-of-QGraphicsItem items (self, float x, float y, float w, float h, Qt.ItemSelectionMode mode = Qt.IntersectsItemShape)`
*   `list-of-QGraphicsItem items (self, float x, float y, float w, float h, Qt.ItemSelectionMode mode, Qt.SortOrder order, QTransform deviceTransform = QTransform())`
*   `QRectF itemsBoundingRect (self)`
*   `keyPressEvent (self, QKeyEvent event)`
*   `keyReleaseEvent (self, QKeyEvent event)`
*   `mouseDoubleClickEvent (self, QGraphicsSceneMouseEvent event)`
*   `QGraphicsItem mouseGrabberItem (self)`
*   `mouseMoveEvent (self, QGraphicsSceneMouseEvent event)`
*   `mousePressEvent (self, QGraphicsSceneMouseEvent event)`
*   `mouseReleaseEvent (self, QGraphicsSceneMouseEvent event)`
*   `QPalette palette (self)`
*   `removeItem (self, QGraphicsItem item)`
*   `render (self, QPainter painter, QRectF target = QRectF(), QRectF source = QRectF(), Qt.AspectRatioMode mode = Qt.KeepAspectRatio)`
*   `QRectF sceneRect (self)`
*   `list-of-QGraphicsItem selectedItems (self)`
*   `QPainterPath selectionArea (self)`
*   `bool sendEvent (self, QGraphicsItem item, QEvent event)`
*   `setActivePanel (self, QGraphicsItem item)`
*   `setActiveWindow (self, QGraphicsWidget widget)`
*   `setBackgroundBrush (self, QBrush brush)`
*   `setBspTreeDepth (self, int depth)`
*   `setFocus (self, Qt.FocusReason focusReason = Qt.OtherFocusReason)`
*   `setFocusItem (self, QGraphicsItem item, Qt.FocusReason focusReason = Qt.OtherFocusReason)`
*   `setFont (self, QFont font)`
*   `setForegroundBrush (self, QBrush brush)`
*   `setItemIndexMethod (self, ItemIndexMethod method)`
*   `setPalette (self, QPalette palette)`
*   `setSceneRect (self, QRectF rect)`
*   `setSceneRect (self, float x, float y, float w, float h)`
*   `setSelectionArea (self, QPainterPath path, QTransform deviceTransform)`
*   `setSelectionArea (self, QPainterPath path)`
*   `setSelectionArea (self, QPainterPath path, Qt.ItemSelectionMode)`
*   `setSelectionArea (self, QPainterPath path, Qt.ItemSelectionMode mode, QTransform deviceTransform)`
*   `setSortCacheEnabled (self, bool enabled)`
*   `setStickyFocus (self, bool enabled)`
*   `setStyle (self, QStyle style)`
*   `bool stickyFocus (self)`
*   `QStyle style (self)`
*   `update (self, QRectF rect = QRectF())`
*   `update (self, float x, float y, float w, float h)`
*   `list-of-QGraphicsView views (self)`
*   `wheelEvent (self, QGraphicsSceneWheelEvent event)`
*   `float width (self)`

### Qt Signals

*   `void changed (const QList&lt;QRectF&gt;&)`
*   `void sceneRectChanged (const QRectF&)`
*   `void selectionChanged ()`

* * *

## Detailed Description

在QGraphicsScene类提供了用于管理大量的2D图形项的表面上。

这个类作为一个容器QGraphicsItems 。它是连同用于[QGraphicsView](qgraphicsview.html)用于可视化的二维表面的图形化的项目，如直线，矩形，文字，甚至是自定义项目。 QGraphicsScene是部分[Graphics View Framework](index.htm)。

QGraphicsScene还提供以下功能，可以让你有效地确定项目的两个位置，以及确定哪些项目是在现场的任意区域内可见。与[QGraphicsView](qgraphicsview.html)窗口小部件，你可以想像整个场景，或放大，查看现场的唯一部分。

例如：

```
 QGraphicsScene scene;
 scene.addText("Hello, world!");

 [QGraphicsView](qgraphicsview.html) view(&scene);
 view.show();

```

注意， QGraphicsScene都有自己的无视觉外观，它只管理项目。你需要创建一个[QGraphicsView](qgraphicsview.html)小工具，可视化的场景。

将项目添加到一个场景，你通过构建一个QGraphicsScene对象开始。那么，你有两个选择：要么加入您现有的[QGraphicsItem](qgraphicsitem.html)通过调用对象[addItem](qgraphicsscene.html#addItem)（ ） ，或者您也可以拨打方便的功能之一[addEllipse](qgraphicsscene.html#addEllipse)（ ）[addLine](qgraphicsscene.html#addLine)（ ）[addPath](qgraphicsscene.html#addPath)（ ）[addPixmap](qgraphicsscene.html#addPixmap)（ ）[addPolygon](qgraphicsscene.html#addPolygon)（ ）[addRect](qgraphicsscene.html#addRect)（） ，或[addText](qgraphicsscene.html#addText)（），它都返回一个指向新添加的项目。具有这些功能的添加物品的尺寸是相对于项目的坐标系，并在项目位置在场景初始化为（ 0,0） 。

然后，您可以使用可视化的场景[QGraphicsView](qgraphicsview.html)。当场景变化时， （例如，当一个项目移动或变换） QGraphicsScene放出[changed](qgraphicsscene.html#changed)（）信号。要删除某个项目，调用[removeItem](qgraphicsscene.html#removeItem)（ ） 。

QGraphicsScene使用一个索引算法能够有效地管理项目的位置。默认情况下，一个BSP （二进制空间划分）树被使用;适用于大场景中的大部分项目保持静态（即不走动）的算法。您可以选择通过调用禁用此指数[setItemIndexMethod](qgraphicsscene.html#itemIndexMethod-prop)（ ） 。有关可用的索引算法的详细信息，请参阅[itemIndexMethod](qgraphicsscene.html#itemIndexMethod-prop)属性。

场景的边界矩形是通过调用设置[setSceneRect](qgraphicsscene.html#sceneRect-prop)（ ） 。件可以被放置在现场的任何位置，并且场景的大小是由默认无限制。现场RECT仅用于内部簿记，维护现场的项目索引。如果场景RECT没有设置， QGraphicsScene将使用所有项目的边界区域，通过返回[itemsBoundingRect](qgraphicsscene.html#itemsBoundingRect)（ ） ，作为场景正确。但是，[itemsBoundingRect](qgraphicsscene.html#itemsBoundingRect)（ ）是一个比较耗时的功能，因为它的运作通过收集位置信息用于现场每一个项目。正因为如此，你应该对大场面的操作时，总是设置场景正确。

其中一个QGraphicsScene最大的优势是它能够有效地确定项目的位置。即使是数以百万计在现场的项目中，[items](qgraphicsscene.html#items)（ ）函数可以几毫秒内确定一个项目的位置。有几个重载[items](qgraphicsscene.html#items)（）： 1 ，发现件在某一位置， 1 ，发现里面或具有多边形或矩形相交，并且多个项目。返回的项目列表是通过堆叠顺序排列，最上面的项目是列表中的第一项进行排序。为方便起见，也有一个[itemAt](qgraphicsscene.html#itemAt)（ ）函数返回在给定位置的最上方项目。

QGraphicsScene保持选择信息的场景。要选择项目，请致电[setSelectionArea](qgraphicsscene.html#setSelectionArea)（ ） ，并清除当前的选择，通话[clearSelection](qgraphicsscene.html#clearSelection)（ ） 。通话[selectedItems](qgraphicsscene.html#selectedItems)（）来获取所有选定的项目清单。

### Event Handling and Propagation

该QGraphicsScene有另一个责任，就是从事件传播[QGraphicsView](qgraphicsview.html)。发送事件到场景中，你构建一个继承的事件[QEvent](qevent.html)，然后使用，例如发送，[QApplication.sendEvent](qcoreapplication.html#sendEvent)（ ） 。[event](qgraphicsscene.html#event)（ ）负责调度事件的个别项目。一些常见的事件被方便的事件处理程序来处理。例如，按键事件被处理[keyPressEvent](qgraphicsscene.html#keyPressEvent)（ ） ，和鼠标按下事件被处理[mousePressEvent](qgraphicsscene.html#mousePressEvent)（ ） 。

关键事件被传递到_focus item_。将焦点设置项，您可以调用[setFocusItem](qgraphicsscene.html#setFocusItem)（ ） ，传递，接受集中的项目，或项目本身可以调用[QGraphicsItem.setFocus](qgraphicsitem.html#setFocus)（ ） 。通话[focusItem](qgraphicsscene.html#focusItem)（ ）来获得当前焦点项目。对于小部件的相容性，现场还维护它自己的重点信息。默认情况下，现场没有焦点，所有的关键事件将被丢弃。如果[setFocus](qgraphicsscene.html#setFocus)（）被调用，或者在现场获得焦点的项目，现场自动获得焦点。如果场景有焦点，[hasFocus](qgraphicsscene.html#hasFocus)（ ）将返回True ，而关键事件将被转发到的重点项目，如果有的话。如果场景失去焦点， （即有人呼叫[clearFocus](qgraphicsscene.html#clearFocus)（ ） ），而一个项目具有焦点，现场将维持其项目重点信息，一旦现场重新获得焦点时，它会确保最后的重点项目重新获得焦点。

对于鼠标悬停效果， QGraphicsScene调度_hover events_。如果一个项目接受悬停事件（见[QGraphicsItem.acceptHoverEvents](qgraphicsitem.html#acceptHoverEvents)（ ） ） ，它会收到一个[GraphicsSceneHoverEnter](qevent.html#Type-enum)当鼠标进入其区域的事件。当鼠标移动继续该项目的区域内， QGraphicsScene将发送它[GraphicsSceneHoverMove](qevent.html#Type-enum)事件。当鼠标离开该项目的区域，该项目将获得[GraphicsSceneHoverLeave](qevent.html#Type-enum)事件。

所有的鼠标事件被传递到当前_mouse grabber_项目。项目成为现场的鼠标抓取，如果它接受鼠标事件（见[QGraphicsItem.acceptedMouseButtons](qgraphicsitem.html#acceptedMouseButtons)（ ） ），它接收鼠标按下。它保持鼠标采集卡，直到它收到一个鼠标释放时，没有其他的鼠标按钮被按下。您可以致电[mouseGrabberItem](qgraphicsscene.html#mouseGrabberItem)（ ） ，以确定哪些项目目前正在抓住鼠标。

* * *

## Type Documentation

```
QGraphicsScene.ItemIndexMethod
```

这个枚举变量描述了索引算法[QGraphicsScene](qgraphicsscene.html)为管理有关现场项目位置信息。

| Constant | Value | Description |
| --- | --- | --- |
| `QGraphicsScene.BspTreeIndex` | `0` | 一个二进制空间划分树被应用。所有[QGraphicsScene](qgraphicsscene.html)的项目定位算法是一种为了接近对数的复杂性，通过使用二进制搜索。添加，移动和删除的项目是对数。这种方法最适合于静态场景（即场景中的大部分项目不动） 。 |
| `QGraphicsScene.NoIndex` | `-1` | 没有索引被应用。项目位置的线性复杂度，因为在现场的所有项目进行搜索。添加，移动和删除的项目，然而，在常数时间内完成。这种方法非常适合于动态场景，许多项目被添加，移动或删除连续。 |

**See also** [setItemIndexMethod](qgraphicsscene.html#itemIndexMethod-prop)（）和[bspTreeDepth](qgraphicsscene.html#bspTreeDepth-prop)。

```
QGraphicsScene.SceneLayer
```

这个枚举变量描述了一个渲染层[QGraphicsScene](qgraphicsscene.html)。何时[QGraphicsScene](qgraphicsscene.html)绘制的场景内容，它使得每一层分开，为了。

每一层代表可调用的功能，如当被OR'ed在一起的标志[invalidate](qgraphicsscene.html#invalidate)（）或[QGraphicsView.invalidateScene](qgraphicsview.html#invalidateScene)（ ） 。

| Constant | Value | Description |
| --- | --- | --- |
| `QGraphicsScene.ItemLayer` | `0x1` | 该项目层。[QGraphicsScene](qgraphicsscene.html)渲染所有的项目都在这一层通过调用虚函数[drawItems](index.htm#drawItems)（ ） 。该项目层绘制背景层之后，但在此之前的前景层。 |
| `QGraphicsScene.BackgroundLayer` | `0x2` | 背景层。[QGraphicsScene](qgraphicsscene.html)通过调用虚函数渲染场景的背景在这一层[drawBackground](qgraphicsscene.html#drawBackground)（ ） 。背景层首先所有图层的绘制。 |
| `QGraphicsScene.ForegroundLayer` | `0x4` | 前景层。[QGraphicsScene](qgraphicsscene.html)通过调用虚函数呈现在这一层场景的前景[drawForeground](qgraphicsscene.html#drawForeground)（ ） 。前景层被最后绘制所有层。 |
| `QGraphicsScene.AllLayers` | `0xffff` | 所有的层，这个值表示所有三个层的结合。 |

这个枚举被引入或修改的Qt 4.3 。

该SceneLayers类型是一个typedef为[QFlags](index.htm)\u003cSceneLayer\u003e 。它存储SceneLayer值的或组合。

**See also** [invalidate](qgraphicsscene.html#invalidate)（）和[QGraphicsView.invalidateScene](qgraphicsview.html#invalidateScene)（ ） 。

* * *

## Method Documentation

```
QGraphicsScene.__init__ (self, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QGraphicsScene](qgraphicsscene.html)对象。该_parent_参数被传递到[QObject](qobject.html)的构造。

```
QGraphicsScene.__init__ (self, QRectF sceneRect, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QGraphicsScene](qgraphicsscene.html)对象，使用_sceneRect_其场景区域。该_parent_参数被传递到[QObject](qobject.html)的构造。

**See also** [sceneRect](qgraphicsscene.html#sceneRect-prop)。

```
QGraphicsScene.__init__ (self, float x, float y, float width, float height, QObject parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QGraphicsScene](qgraphicsscene.html)Object，使用（指定的矩形_x_，_y_） ，并在给定_width_和_height_其场景区域。该_parent_参数被传递到[QObject](qobject.html)的构造。

**See also** [sceneRect](qgraphicsscene.html#sceneRect-prop)。

```
QGraphicsItem QGraphicsScene.activePanel (self)
```

[

返回当前的面板，或者0 ，如果没有面板是目前活跃。

此功能被引入Qt的4.6 。

](qgraphicsitem.html)

[**See also**](qgraphicsitem.html) [QGraphicsScene.setActivePanel](qgraphicsscene.html#setActivePanel)（ ） 。

```
QGraphicsWidget QGraphicsScene.activeWindow (self)
```

[

返回当前活动窗口，或者0，如果没有窗口当前处于活动状态。

此功能被引入Qt的4.4 。

](qgraphicswidget.html)

[**See also**](qgraphicswidget.html) [QGraphicsScene.setActiveWindow](qgraphicsscene.html#setActiveWindow)（ ） 。

```
QGraphicsEllipseItem QGraphicsScene.addEllipse (self, QRectF rect, QPen pen = QPen(), QBrush brush = QBrush())
```

[

创建并添加一个椭圆项目现场，并返回该项的指针。椭圆的几何形状被定义为_rect_，其笔和刷子被初始化为_pen_和_brush_。

注意，该产品的几何形状在产品的坐标提供，并且它的位置被初始化为（ 0,0） 。

](qgraphicsellipseitem.html)

[如果该项目是可见的（即，](qgraphicsellipseitem.html)[QGraphicsItem.isVisible](qgraphicsitem.html#isVisible)（ ）返回True ） ，[QGraphicsScene](qgraphicsscene.html)会发出[changed](qgraphicsscene.html#changed)（ ）一旦控制返回到事件循环。

**See also** [addLine](qgraphicsscene.html#addLine)（ ）[addPath](qgraphicsscene.html#addPath)（ ）[addPixmap](qgraphicsscene.html#addPixmap)（ ）[addRect](qgraphicsscene.html#addRect)（ ）[addText](qgraphicsscene.html#addText)（ ）[addItem](qgraphicsscene.html#addItem)（）和[addWidget](qgraphicsscene.html#addWidget)（ ） 。

```
QGraphicsEllipseItem QGraphicsScene.addEllipse (self, float x, float y, float w, float h, QPen pen = QPen(), QBrush brush = QBrush())
```

[](qgraphicsellipseitem.html)

[这个方便的功能等同于调用addEllipse （](qgraphicsellipseitem.html)[QRectF](qrectf.html)（_x_，_y_，_w_，_h_） ，_pen_，_brush_） 。

此功能被引入Qt的4.3 。

```
QGraphicsScene.addItem (self, QGraphicsItem item)
```

该_item_说法有它的所有权转移给Qt的。

添加或移动_item_和所有的童装到了这一幕。这一幕发生的所有权_item_。

如果该项目是可见的（即，[QGraphicsItem.isVisible](qgraphicsitem.html#isVisible)（ ）返回True ） ，[QGraphicsScene](qgraphicsscene.html)会发出[changed](qgraphicsscene.html#changed)（ ）一旦控制返回到事件循环。

如果该项目已经在不同的场景，它会首先从它的旧场景去掉，然后加入到这一场景的顶层。

[QGraphicsScene](qgraphicsscene.html)将发送ItemSceneChange通知_item_而它被添加到场景中。如果项目目前并不属于一个场景，只有一个发送通知。如果它不属于现场已经（即，它被移动到了这一幕） ，[QGraphicsScene](qgraphicsscene.html)作为该项目是由它的前一个场景中删除将发送另外通知。

如果该项目是一个面板，场面活跃，而且没有活动面板中的场景，那么该项目将被激活。

**See also** [removeItem](qgraphicsscene.html#removeItem)（ ）[addEllipse](qgraphicsscene.html#addEllipse)（ ）[addLine](qgraphicsscene.html#addLine)（ ）[addPath](qgraphicsscene.html#addPath)（ ）[addPixmap](qgraphicsscene.html#addPixmap)（ ）[addRect](qgraphicsscene.html#addRect)（ ）[addText](qgraphicsscene.html#addText)（ ）[addWidget](qgraphicsscene.html#addWidget)（）和[Sorting](qgraphicsitem.html#sorting)。

```
QGraphicsLineItem QGraphicsScene.addLine (self, QLineF line, QPen pen = QPen())
```

[

创建并增加了一个行项目现场，并返回该项的指针。线的几何形状被定义为_line_，其笔被初始化为_pen_。

注意，该产品的几何形状在产品的坐标提供，并且它的位置被初始化为（ 0,0） 。

](qgraphicslineitem.html)

[如果该项目是可见的（即，](qgraphicslineitem.html)[QGraphicsItem.isVisible](qgraphicsitem.html#isVisible)（ ）返回True ） ，[QGraphicsScene](qgraphicsscene.html)会发出[changed](qgraphicsscene.html#changed)（ ）一旦控制返回到事件循环。

**See also** [addEllipse](qgraphicsscene.html#addEllipse)（ ）[addPath](qgraphicsscene.html#addPath)（ ）[addPixmap](qgraphicsscene.html#addPixmap)（ ）[addRect](qgraphicsscene.html#addRect)（ ）[addText](qgraphicsscene.html#addText)（ ）[addItem](qgraphicsscene.html#addItem)（）和[addWidget](qgraphicsscene.html#addWidget)（ ） 。

```
QGraphicsLineItem QGraphicsScene.addLine (self, float x1, float y1, float x2, float y2, QPen pen = QPen())
```

[](qgraphicslineitem.html)

[这个方便的功能等同于调用addLine （](qgraphicslineitem.html)[QLineF](qlinef.html)（_x1_，_y1_，_x2_，_y2_） ，_pen_） 。

此功能被引入Qt的4.3 。

```
QGraphicsPathItem QGraphicsScene.addPath (self, QPainterPath path, QPen pen = QPen(), QBrush brush = QBrush())
```

[

创建并添加一个路径项目现场，并返回该项的指针。的路径的几何形状被定义为_path_，其笔和刷子被初始化为_pen_和_brush_。

注意，该产品的几何形状在产品的坐标提供，并且它的位置被初始化为（ 0,0） 。

](qgraphicspathitem.html)

[如果该项目是可见的（即，](qgraphicspathitem.html)[QGraphicsItem.isVisible](qgraphicsitem.html#isVisible)（ ）返回True ） ，[QGraphicsScene](qgraphicsscene.html)会发出[changed](qgraphicsscene.html#changed)（ ）一旦控制返回到事件循环。

**See also** [addEllipse](qgraphicsscene.html#addEllipse)（ ）[addLine](qgraphicsscene.html#addLine)（ ）[addPixmap](qgraphicsscene.html#addPixmap)（ ）[addRect](qgraphicsscene.html#addRect)（ ）[addText](qgraphicsscene.html#addText)（ ）[addItem](qgraphicsscene.html#addItem)（）和[addWidget](qgraphicsscene.html#addWidget)（ ） 。

```
QGraphicsPixmapItem QGraphicsScene.addPixmap (self, QPixmap pixmap)
```

[

创建并增加了一个图片项目现场，并返回该项的指针。像素图被定义为_pixmap_。

注意，该产品的几何形状在产品的坐标提供，并且它的位置被初始化为（ 0,0） 。

](qgraphicspixmapitem.html)

[如果该项目是可见的（即，](qgraphicspixmapitem.html)[QGraphicsItem.isVisible](qgraphicsitem.html#isVisible)（ ）返回True ） ，[QGraphicsScene](qgraphicsscene.html)会发出[changed](qgraphicsscene.html#changed)（ ）一旦控制返回到事件循环。

**See also** [addEllipse](qgraphicsscene.html#addEllipse)（ ）[addLine](qgraphicsscene.html#addLine)（ ）[addPath](qgraphicsscene.html#addPath)（ ）[addRect](qgraphicsscene.html#addRect)（ ）[addText](qgraphicsscene.html#addText)（ ）[addItem](qgraphicsscene.html#addItem)（）和[addWidget](qgraphicsscene.html#addWidget)（ ） 。

```
QGraphicsPolygonItem QGraphicsScene.addPolygon (self, QPolygonF polygon, QPen pen = QPen(), QBrush brush = QBrush())
```

[

创建并增加了一个多边形项目现场，并返回该项的指针。多边形被定义为_polygon_，其笔和刷子被初始化为_pen_和_brush_。

注意，该产品的几何形状在产品的坐标提供，并且它的位置被初始化为（ 0,0） 。

](qgraphicspolygonitem.html)

[如果该项目是可见的（即，](qgraphicspolygonitem.html)[QGraphicsItem.isVisible](qgraphicsitem.html#isVisible)（ ）返回True ） ，[QGraphicsScene](qgraphicsscene.html)会发出[changed](qgraphicsscene.html#changed)（ ）一旦控制返回到事件循环。

**See also** [addEllipse](qgraphicsscene.html#addEllipse)（ ）[addLine](qgraphicsscene.html#addLine)（ ）[addPath](qgraphicsscene.html#addPath)（ ）[addRect](qgraphicsscene.html#addRect)（ ）[addText](qgraphicsscene.html#addText)（ ）[addItem](qgraphicsscene.html#addItem)（）和[addWidget](qgraphicsscene.html#addWidget)（ ） 。

```
QGraphicsRectItem QGraphicsScene.addRect (self, QRectF rect, QPen pen = QPen(), QBrush brush = QBrush())
```

[

创建并添加一个矩形项目现场，并返回该项的指针。矩形的几何形状被定义为_rect_，其笔和刷子被初始化为_pen_和_brush_。

](qgraphicsrectitem.html)

[注意，该产品的几何形状在产品的坐标提供，并且它的位置被初始化为（ 0,0） 。例如，如果一个](qgraphicsrectitem.html)[QRect](qrect.html)（50， 50 ，100，100 ）被添加，其左上角将在（50 ，50）相对于原点的物品的坐标系。

如果该项目是可见的（即，[QGraphicsItem.isVisible](qgraphicsitem.html#isVisible)（ ）返回True ） ，[QGraphicsScene](qgraphicsscene.html)会发出[changed](qgraphicsscene.html#changed)（ ）一旦控制返回到事件循环。

**See also** [addEllipse](qgraphicsscene.html#addEllipse)（ ）[addLine](qgraphicsscene.html#addLine)（ ）[addPixmap](qgraphicsscene.html#addPixmap)（ ）[addPixmap](qgraphicsscene.html#addPixmap)（ ）[addText](qgraphicsscene.html#addText)（ ）[addItem](qgraphicsscene.html#addItem)（）和[addWidget](qgraphicsscene.html#addWidget)（ ） 。

```
QGraphicsRectItem QGraphicsScene.addRect (self, float x, float y, float w, float h, QPen pen = QPen(), QBrush brush = QBrush())
```

[](qgraphicsrectitem.html)

[这个方便的功能等同于调用addRect （](qgraphicsrectitem.html)[QRectF](qrectf.html)（_x_，_y_，_w_，_h_） ，_pen_，_brush_） 。

此功能被引入Qt的4.3 。

```
QGraphicsSimpleTextItem QGraphicsScene.addSimpleText (self, QString text, QFont font = QFont())
```

[](qgraphicssimpletextitem.html)

[创建并增加了一个](qgraphicssimpletextitem.html)[QGraphicsSimpleTextItem](qgraphicssimpletextitem.html)到了现场，并返回该项的指针。文本字符串被初始化为_text_和其字体被初始化为_font_。

该项目的位置被初始化为（ 0,0） 。

如果该项目是可见的（即，[QGraphicsItem.isVisible](qgraphicsitem.html#isVisible)（ ）返回True ） ，[QGraphicsScene](qgraphicsscene.html)会发出[changed](qgraphicsscene.html#changed)（ ）一旦控制返回到事件循环。

**See also** [addEllipse](qgraphicsscene.html#addEllipse)（ ）[addLine](qgraphicsscene.html#addLine)（ ）[addPixmap](qgraphicsscene.html#addPixmap)（ ）[addPixmap](qgraphicsscene.html#addPixmap)（ ）[addRect](qgraphicsscene.html#addRect)（ ）[addItem](qgraphicsscene.html#addItem)（）和[addWidget](qgraphicsscene.html#addWidget)（ ） 。

```
QGraphicsTextItem QGraphicsScene.addText (self, QString text, QFont font = QFont())
```

[

创建并添加一个文本项目现场，并返回该项的指针。文本字符串被初始化为_text_和其字体被初始化为_font_。

该项目的位置被初始化为（ 0,0） 。

](qgraphicstextitem.html)

[如果该项目是可见的（即，](qgraphicstextitem.html)[QGraphicsItem.isVisible](qgraphicsitem.html#isVisible)（ ）返回True ） ，[QGraphicsScene](qgraphicsscene.html)会发出[changed](qgraphicsscene.html#changed)（ ）一旦控制返回到事件循环。

**See also** [addEllipse](qgraphicsscene.html#addEllipse)（ ）[addLine](qgraphicsscene.html#addLine)（ ）[addPixmap](qgraphicsscene.html#addPixmap)（ ）[addPixmap](qgraphicsscene.html#addPixmap)（ ）[addRect](qgraphicsscene.html#addRect)（ ）[addItem](qgraphicsscene.html#addItem)（）和[addWidget](qgraphicsscene.html#addWidget)（ ） 。

```
QGraphicsProxyWidget QGraphicsScene.addWidget (self, QWidget widget, Qt.WindowFlags flags = 0)
```

[

该_widget_说法有它的所有权转移给Qt的。

](qgraphicsproxywidget.html)

[创建一个新的](qgraphicsproxywidget.html)[QGraphicsProxyWidget](qgraphicsproxywidget.html)为_widget_，将其添加到场景中，并返回一个指针到代理。_wFlags_设置默认的窗口标志嵌入代理部件。

该项目的位置被初始化为（ 0,0） 。

如果该项目是可见的（即，[QGraphicsItem.isVisible](qgraphicsitem.html#isVisible)（ ）返回True ） ，[QGraphicsScene](qgraphicsscene.html)会发出[changed](qgraphicsscene.html#changed)（ ）一旦控制返回到事件循环。

需要注意的是小部件与[Qt.WA_PaintOnScreen](qt.html#WidgetAttribute-enum)小部件的属性设置和不支持的小工具，包装外部应用程序或控制器。例子是[QGLWidget](qglwidget.html)和[QAxWidget](index.htm)。

**See also** [addEllipse](qgraphicsscene.html#addEllipse)（ ）[addLine](qgraphicsscene.html#addLine)（ ）[addPixmap](qgraphicsscene.html#addPixmap)（ ）[addPixmap](qgraphicsscene.html#addPixmap)（ ）[addRect](qgraphicsscene.html#addRect)（ ）[addText](qgraphicsscene.html#addText)（ ）[addSimpleText](qgraphicsscene.html#addSimpleText)（）和[addItem](qgraphicsscene.html#addItem)（ ） 。

```
QGraphicsScene.advance (self)
```

这种方法也是一个Qt槽与C + +的签名`void advance()`。

这个插槽_advances_现场一步，通过调用[QGraphicsItem.advance](qgraphicsitem.html#advance)（）用于在现场的所有项目。这样做是在两个阶段：在第一阶段，所有的项目都通知到场即将改变，而在第二阶段的所有项目都通知他们可以移动。在第一阶段，[QGraphicsItem.advance](qgraphicsitem.html#advance)（）被调用传递0值作为参数，并且1被传递到第二阶段。

**See also** [QGraphicsItem.advance](qgraphicsitem.html#advance)（ ）[QGraphicsItemAnimation](qgraphicsitemanimation.html)和[QTimeLine](qtimeline.html)。

```
QBrush QGraphicsScene.backgroundBrush (self)
```

[

```
int QGraphicsScene.bspTreeDepth (self)
```

```
QGraphicsScene.clear (self)
```

这种方法也是一个Qt槽与C + +的签名`void clear()`。

删除，并删除所有项目从场景，但其他原因而离开现场的不变的状态。

此功能被引入Qt的4.4 。

](qbrush.html)

[**See also**](qbrush.html) [addItem](qgraphicsscene.html#addItem)（ ） 。

```
QGraphicsScene.clearFocus (self)
```

从现场清除焦点。如果有任何项目具有焦点时，这个函数被调用时，它会失去焦点，并再次重新获得焦点，一旦现场重新获得焦点。

不具有焦点场景忽略的关键事件。

**See also** [hasFocus](qgraphicsscene.html#hasFocus)（ ）[setFocus](qgraphicsscene.html#setFocus)（）和[setFocusItem](qgraphicsscene.html#setFocusItem)（ ） 。

```
QGraphicsScene.clearSelection (self)
```

清除当前的选择。

**See also** [setSelectionArea](qgraphicsscene.html#setSelectionArea)（）和[selectedItems](qgraphicsscene.html#selectedItems)（ ） 。

```
list-of-QGraphicsItem QGraphicsScene.collidingItems (self, QGraphicsItem item, Qt.ItemSelectionMode mode = Qt.IntersectsItemShape)
```

返回与碰撞的所有项目的列表_item_。碰撞是通过调用确定[QGraphicsItem.collidesWithItem](qgraphicsitem.html#collidesWithItem)（）;碰撞检测是通过测定_mode_。默认情况下，所有的项目，其形状相交_item_或者是包含内部_item_的形状返回。

该项目以递减顺序堆叠（即，在列表中的第一个项目是最上面的项目，最后项目是最下面的项目）返回。

**See also** [items](qgraphicsscene.html#items)（ ）[itemAt](qgraphicsscene.html#itemAt)（ ）[QGraphicsItem.collidesWithItem](qgraphicsitem.html#collidesWithItem)（）和[Sorting](qgraphicsitem.html#sorting)。

```
QGraphicsScene.contextMenuEvent (self, QGraphicsSceneContextMenuEvent event)
```

此事件处理程序，对于事件_contextMenuEvent_，可重新实现在子类中获得上下文菜单事件。默认实现转发的事件接受上下文菜单事件的事件的位置的最上方项目。如果没有任何项目接受上下文菜单事件在这个位置上，​​事件被忽略。

**See also** [QGraphicsItem.contextMenuEvent](qgraphicsitem.html#contextMenuEvent)（ ） 。

```
QGraphicsItemGroup QGraphicsScene.createItemGroup (self, list-of-QGraphicsItem items)
```

[

该_items_说法有它的所有权转移给Qt的。

](qgraphicsitemgroup.html)

[组中的所有项目_items_成一个新的](qgraphicsitemgroup.html)[QGraphicsItemGroup](qgraphicsitemgroup.html)，并返回一个指针到组。该组与共同祖先创造_items_作为其父，并与位置（0 ，0）。该项目全部重设父到组，以及它们的位置和转换映射到该组。如果_items_是空的，这个函数会返回一个空的顶层[QGraphicsItemGroup](qgraphicsitemgroup.html)。

[QGraphicsScene](qgraphicsscene.html)有团体项目的所有权，你不需要删除它。拆除（取消组合）一组，呼[destroyItemGroup](qgraphicsscene.html#destroyItemGroup)（ ） 。

**See also** [destroyItemGroup](qgraphicsscene.html#destroyItemGroup)（）和[QGraphicsItemGroup.addToGroup](qgraphicsitemgroup.html#addToGroup)（ ） 。

```
QGraphicsScene.destroyItemGroup (self, QGraphicsItemGroup group)
```

该_group_说法有它的所有权转移给Qt的。

Reparents中的所有项目_group_至_group_的父项，然后删除_group_从现场，终于将其删除。该项目的位置和转换是从组映射到集团母公司。

**See also** [createItemGroup](qgraphicsscene.html#createItemGroup)（）和[QGraphicsItemGroup.removeFromGroup](qgraphicsitemgroup.html#removeFromGroup)（ ） 。

```
QGraphicsScene.dragEnterEvent (self, QGraphicsSceneDragDropEvent event)
```

此事件处理程序，对于事件_event_，可重新实现在子类中接收拖动进入事件现场。

默认实现接受事件并准备现场接受拖动移动事件。

**See also** [QGraphicsItem.dragEnterEvent](qgraphicsitem.html#dragEnterEvent)（ ）[dragMoveEvent](qgraphicsscene.html#dragMoveEvent)（ ）[dragLeaveEvent](qgraphicsscene.html#dragLeaveEvent)（）和[dropEvent](qgraphicsscene.html#dropEvent)（ ） 。

```
QGraphicsScene.dragLeaveEvent (self, QGraphicsSceneDragDropEvent event)
```

此事件处理程序，对于事件_event_，可重新实现在子类中接收拖动离开事件现场。

**See also** [QGraphicsItem.dragLeaveEvent](qgraphicsitem.html#dragLeaveEvent)（ ）[dragEnterEvent](qgraphicsscene.html#dragEnterEvent)（ ）[dragMoveEvent](qgraphicsscene.html#dragMoveEvent)（）和[dropEvent](qgraphicsscene.html#dropEvent)（ ） 。

```
QGraphicsScene.dragMoveEvent (self, QGraphicsSceneDragDropEvent event)
```

此事件处理程序，对于事件_event_，可重新实现在子类中接收拖放移动事件现场。

**See also** [QGraphicsItem.dragMoveEvent](qgraphicsitem.html#dragMoveEvent)（ ）[dragEnterEvent](qgraphicsscene.html#dragEnterEvent)（ ）[dragLeaveEvent](qgraphicsscene.html#dragLeaveEvent)（）和[dropEvent](qgraphicsscene.html#dropEvent)（ ） 。

```
QGraphicsScene.drawBackground (self, QPainter painter, QRectF rect)
```

绘制的场景采用背景_painter_之前，任何产品和前景绘制。重新实现此功能提供了自定义背景的场景。

所有的绘制是在做_scene_坐标。该_rect_参数是暴露的矩形。

如果你想要的是定义一个颜色，纹理或渐变的背景，你可以调用[setBackgroundBrush](qgraphicsscene.html#backgroundBrush-prop)（ ）来代替。

**See also** [drawForeground](qgraphicsscene.html#drawForeground)（）和[drawItems](index.htm#drawItems)（ ） 。

```
QGraphicsScene.drawForeground (self, QPainter painter, QRectF rect)
```

绘制场景的使用前景_painter_，背景和所有项目后已经制定。重新实现这个函数提供一个自定义前景的场景。

所有的绘制是在做_scene_坐标。该_rect_参数是暴露的矩形。

如果你想要的是定义一个颜色，纹理或渐变的前景，你可以调用[setForegroundBrush](qgraphicsscene.html#foregroundBrush-prop)（ ）来代替。

**See also** [drawBackground](qgraphicsscene.html#drawBackground)（）和[drawItems](index.htm#drawItems)（ ） 。

```
QGraphicsScene.drawItems (self, QPainter painter, list-of-QGraphicsItem items, list-of-QStyleOptionGraphicsItem options, QWidget widget = None)
```

```
QGraphicsScene.dropEvent (self, QGraphicsSceneDragDropEvent event)
```

此事件处理程序，对于事件_event_，可重新实现在子类中接收拖放事件的现场。

**See also** [QGraphicsItem.dropEvent](qgraphicsitem.html#dropEvent)（ ）[dragEnterEvent](qgraphicsscene.html#dragEnterEvent)（ ）[dragMoveEvent](qgraphicsscene.html#dragMoveEvent)（）和[dragLeaveEvent](qgraphicsscene.html#dragLeaveEvent)（ ） 。

```
bool QGraphicsScene.event (self, QEvent event)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

处理事件_event_，并分派到相应的事件处理程序。

除了调用方便的事件处理程序，这个功能是负责将鼠标移动事件悬停事件时，没有鼠标采集项目。悬停事件直接交付给项目，没有方便的功能他们。

不像[QWidget](qwidget.html)，[QGraphicsScene](qgraphicsscene.html)不具备的便利功能[enterEvent()](qwidget.html#enterEvent)和[leaveEvent()](qwidget.html#leaveEvent)。使用此功能来获得这些事件来代替。

**See also** [contextMenuEvent](qgraphicsscene.html#contextMenuEvent)（ ）[keyPressEvent](qgraphicsscene.html#keyPressEvent)（ ）[keyReleaseEvent](qgraphicsscene.html#keyReleaseEvent)（ ）[mousePressEvent](qgraphicsscene.html#mousePressEvent)（ ）[mouseMoveEvent](qgraphicsscene.html#mouseMoveEvent)（ ）[mouseReleaseEvent](qgraphicsscene.html#mouseReleaseEvent)（ ）[mouseDoubleClickEvent](qgraphicsscene.html#mouseDoubleClickEvent)（ ）[focusInEvent](qgraphicsscene.html#focusInEvent)（）和[focusOutEvent](qgraphicsscene.html#focusOutEvent)（ ） 。

```
bool QGraphicsScene.eventFilter (self, QObject watched, QEvent event)
```

从重新实现[QObject.eventFilter](qobject.html#eventFilter)（ ） 。

[QGraphicsScene](qgraphicsscene.html) filters [QApplication](qapplication.html)的事件，以检测调色板和字体的变化。

```
QGraphicsScene.focusInEvent (self, QFocusEvent event)
```

此事件处理程序，对于事件_focusEvent_，可重新实现在子类中要获得焦点的事件。

默认实现将焦点设置在现场，然后在最后一个重点项目。

**See also** [QGraphicsItem.focusOutEvent](qgraphicsitem.html#focusOutEvent)（ ） 。

```
QGraphicsItem QGraphicsScene.focusItem (self)
```

[

当现场被激活，该函数返回现场目前的重点项目，或者0，如果没有项目目前具有焦点。当场景是无效的，这个函数返回将获得输入焦点时的情景被激活的项目。

重点项目接收键盘输入的时候，现场收到一个关键事件。

](qgraphicsitem.html)

[**See also**](qgraphicsitem.html) [setFocusItem](qgraphicsscene.html#setFocusItem)（ ）[QGraphicsItem.hasFocus](qgraphicsitem.html#hasFocus)（）和[isActive](qgraphicsscene.html#isActive)（ ） 。

```
bool QGraphicsScene.focusNextPrevChild (self, bool next)
```

发现一个新的widget ，让键盘焦点，以适合Tab和Shift + Tab键，如果能找到一个新的widget返回True ，否则返回FALSE ，如果它不能。如果_next_诚然，这个函数向前搜索，如果_next_是假的，它向后搜索。

您可以在子类中重新实现这个功能[QGraphicsScene](qgraphicsscene.html)提供细粒度地控制标籤焦点传递你的场景里面。默认的实现是基于定义的选项卡焦点链[QGraphicsWidget.setTabOrder](qgraphicswidget.html#setTabOrder)（ ） 。

此功能被引入Qt的4.4 。

```
QGraphicsScene.focusOutEvent (self, QFocusEvent event)
```

此事件处理程序，对于事件_focusEvent_，可重新实现在子类中获得了焦点事件。

默认实现消除重点从任何重点项目，然后从现场移除焦点。

**See also** [QGraphicsItem.focusInEvent](qgraphicsitem.html#focusInEvent)（ ） 。

```
QFont QGraphicsScene.font (self)
```

[](qfont.html)

```
QBrush QGraphicsScene.foregroundBrush (self)
```

[

```
bool QGraphicsScene.hasFocus (self)
```

](qbrush.html)

[返回True如果现场有焦点，否则返回False 。如果场景有焦点，它将会把关键事件从](qbrush.html)[QKeyEvent](qkeyevent.html)到具有焦点的任何项目。

**See also** [setFocus](qgraphicsscene.html#setFocus)（）和[setFocusItem](qgraphicsscene.html#setFocusItem)（ ） 。

```
float QGraphicsScene.height (self)
```

这个方便的功能等同于调用`sceneRect().height()`。

**See also** [width](qgraphicsscene.html#width)（ ） 。

```
QGraphicsScene.helpEvent (self, QGraphicsSceneHelpEvent event)
```

此事件处理程序，对于事件_helpEvent_，可重新实现在子类中接受帮助的事件。该事件的类型为[QEvent.ToolTip](qevent.html#Type-enum)，这在工具提示要求创建。

默认实现显示的最上方项目，即具有最高z值的项目，在鼠标光标位置的工具提示。如果没有项目有一个工具提示集，这个函数什么都不做。

**See also** [QGraphicsItem.toolTip](qgraphicsitem.html#toolTip)（）和[QGraphicsSceneHelpEvent](qgraphicsscenehelpevent.html)。

```
QGraphicsScene.inputMethodEvent (self, QInputMethodEvent event)
```

此事件处理程序，对于事件_event_，可重新实现在子类来接收输入法事件的现场。

默认实现转发事件到[focusItem](qgraphicsscene.html#focusItem)（ ） 。如果没有项目目前已经集中或者当前焦点项目不接受输入法，这个函数不执行任何操作。

**See also** [QGraphicsItem.inputMethodEvent](qgraphicsitem.html#inputMethodEvent)（ ） 。

```
QVariant QGraphicsScene.inputMethodQuery (self, Qt.InputMethodQuery query)
```

此方法用于通过输入法来查询一组场景的属性，能够支持复杂的输入法操作为周围的文字和reconversions支持。

该_query_参数指定了属性进行查询。

**See also** [QWidget.inputMethodQuery](qwidget.html#inputMethodQuery)（ ） 。

```
QGraphicsScene.invalidate (self, QRectF rect = QRectF(), SceneLayers layers = QGraphicsScene.AllLayers)
```

这种方法也是一个Qt槽与C + +的签名`void invalidate(const QRectF& = QRectF(),QGraphicsScene::SceneLayers = QGraphicsScene.AllLayers)`。

废止及时间表的重绘_layers_在_rect_在现场。在任何缓存的内容_layers_无条件失效并重新绘制。

您可以使用此函数重载通知[QGraphicsScene](qgraphicsscene.html)的改变，背景或场景的前景。这个函数是常用的场景与基于区块的背景来通知改变时[QGraphicsView](qgraphicsview.html)已启用[CacheBackground](qgraphicsview.html#CacheModeFlag-enum)。

例如：

```
 [QRectF](qrectf.html) TileScene.rectForTile(int x, int y) const
 {
     // Return the rectangle for the tile at position (x, y).
     return [QRectF](qrectf.html)(x * tileWidth, y * tileHeight, tileWidth, tileHeight);
 }

 void TileScene.setTile(int x, int y, const [QPixmap](qpixmap.html) &pixmap)
 {
     // Sets or replaces the tile at position (x, y) with pixmap.
     if (x >= 0 && x < numTilesH && y >= 0 && y < numTilesV) {
         tiles[y][x] = pixmap;
         invalidate(rectForTile(x, y), BackgroundLayer);
     }
 }

 void TileScene.drawBackground([QPainter](qpainter.html) *painter, const [QRectF](qrectf.html) &exposed)
 {
     // Draws all tiles that intersect the exposed area.
     for (int y = 0; y < numTilesV; ++y) {
         for (int x = 0; x < numTilesH; ++x) {
             [QRectF](qrectf.html) rect = rectForTile(x, y);
             if (exposed.intersects(rect))
                 painter->drawPixmap(rect.topLeft(), tiles[y][x]);
         }
     }
 }

```

需要注意的是[QGraphicsView](qgraphicsview.html)目前支持后台缓存只（见[QGraphicsView.CacheBackground](qgraphicsview.html#CacheModeFlag-enum)） 。此功能相当于调用[update](qgraphicsscene.html#update)（ ）如有层，但[BackgroundLayer](qgraphicsscene.html#SceneLayer-enum)被传递。

**See also** [QGraphicsView.resetCachedContent](qgraphicsview.html#resetCachedContent)（ ） 。

```
QGraphicsScene.invalidate (self, float x, float y, float w, float h, SceneLayers layers = QGraphicsScene.AllLayers)
```

这是一个重载函数。

这个方便的功能等同于调用无效（[QRectF](qrectf.html)（_x_，_y_，_w_，_h_） ，_layers_） ;

此功能被引入Qt的4.3 。

```
bool QGraphicsScene.isActive (self)
```

返回True如果场景是活跃的（如，它是由至少一个观察[QGraphicsView](qgraphicsview.html)这是积极的），否则返回False 。

此功能被引入Qt的4.6 。

**See also** [QGraphicsItem.isActive](qgraphicsitem.html#isActive)（）和[QWidget.isActiveWindow](qwidget.html#isActiveWindow-prop)（ ） 。

```
bool QGraphicsScene.isSortCacheEnabled (self)
```

```
QGraphicsItem QGraphicsScene.itemAt (self, QPointF pos)
```

[

返回指定最顶端可见项目_position_，或者0，如果有在这个位置没有任何项目。

_deviceTransform_是适用于该视图，​​并且需要如果场景中包含忽略的转换项目提供了转型。

此功能被引入Qt的4.6 。

](qgraphicsitem.html)

[**See also**](qgraphicsitem.html) [items](qgraphicsscene.html#items)（ ）[collidingItems](qgraphicsscene.html#collidingItems)（）和[Sorting](qgraphicsitem.html#sorting)。

```
QGraphicsItem QGraphicsScene.itemAt (self, float x, float y)
```

[](qgraphicsitem.html)

```
QGraphicsItem QGraphicsScene.itemAt (self, QPointF pos, QTransform deviceTransform)
```

[

这是一个重载函数。

返回时由（指定的位置的最上方项目_x_，_y_） ，或者0，如果有在这个位置没有任何项目。

_deviceTransform_是适用于该视图，​​并且需要如果场景中包含忽略的转换项目提供了转型。

这个方便的功能等同于调用`itemAt(QPointF(x, y), deviceTransform)`。

此功能被引入Qt的4.6 。

](qgraphicsitem.html)

```
QGraphicsItem QGraphicsScene.itemAt (self, float x, float y, QTransform deviceTransform)
```

[](qgraphicsitem.html)

```
ItemIndexMethod QGraphicsScene.itemIndexMethod (self)
```

[

```
list-of-QGraphicsItem QGraphicsScene.items (self)
```

按降序返回堆叠顺序的场景中所有项目的列表。

](qgraphicsscene.html#ItemIndexMethod-enum)

[**See also**](qgraphicsscene.html#ItemIndexMethod-enum) [addItem](qgraphicsscene.html#addItem)（ ）[removeItem](qgraphicsscene.html#removeItem)（）和[Sorting](qgraphicsitem.html#sorting)。

```
list-of-QGraphicsItem QGraphicsScene.items (self, Qt.SortOrder order)
```

返回现场的所有项目的有序列表。_order_决定堆叠顺序。

**See also** [addItem](qgraphicsscene.html#addItem)（ ）[removeItem](qgraphicsscene.html#removeItem)（）和[Sorting](qgraphicsitem.html#sorting)。

```
list-of-QGraphicsItem QGraphicsScene.items (self, QPointF pos)
```

回报，这取决于所有可见项目_mode_，是在指定的_pos_在列表中使用排序_order_。

为默认值_mode_ is [Qt.IntersectsItemShape](qt.html#ItemSelectionMode-enum);所有项目的确切形状与相交_pos_返回。

_deviceTransform_是适用于该视图，​​并且需要如果场景中包含忽略的转换项目提供了转型。

此功能被引入Qt的4.6 。

**See also** [itemAt](qgraphicsscene.html#itemAt)（）和[Sorting](qgraphicsitem.html#sorting)。

```
list-of-QGraphicsItem QGraphicsScene.items (self, QPointF pos, Qt.ItemSelectionMode mode, Qt.SortOrder order, QTransform deviceTransform = QTransform())
```

```
list-of-QGraphicsItem QGraphicsScene.items (self, QRectF rectangle, Qt.ItemSelectionMode mode = Qt.IntersectsItemShape)
```

```
list-of-QGraphicsItem QGraphicsScene.items (self, QRectF rect, Qt.ItemSelectionMode mode, Qt.SortOrder order, QTransform deviceTransform = QTransform())
```

```
list-of-QGraphicsItem QGraphicsScene.items (self, QPolygonF polygon, Qt.ItemSelectionMode mode = Qt.IntersectsItemShape)
```

这是一个重载函数。

回报，这取决于所有可见项目_mode_，是内部或相交由定义的矩形_x_，_y_，_w_和_h_，在列表中使用排序_order_。

_deviceTransform_是适用于该视图，​​并且需要如果场景中包含忽略的转换项目提供了转型。

此功能被引入Qt的4.6 。

```
list-of-QGraphicsItem QGraphicsScene.items (self, QPolygonF polygon, Qt.ItemSelectionMode mode, Qt.SortOrder order, QTransform deviceTransform = QTransform())
```

```
list-of-QGraphicsItem QGraphicsScene.items (self, QPainterPath path, Qt.ItemSelectionMode mode = Qt.IntersectsItemShape)
```

```
list-of-QGraphicsItem QGraphicsScene.items (self, QPainterPath path, Qt.ItemSelectionMode mode, Qt.SortOrder order, QTransform deviceTransform = QTransform())
```

这是一个重载函数。

回报，这取决于所有可见项目_mode_，是内部或相交与指定_rect_并返回一个列表排序的使用_order_。

为默认值_mode_ is [Qt.IntersectsItemShape](qt.html#ItemSelectionMode-enum);所有项目的确切形状相交或包含由_rect_返回。

_deviceTransform_是适用于该视图，​​并且需要如果场景中包含忽略的转换项目提供了转型。

此功能被引入Qt的4.6 。

**See also** [itemAt](qgraphicsscene.html#itemAt)（）和[Sorting](qgraphicsitem.html#sorting)。

```
list-of-QGraphicsItem QGraphicsScene.items (self, float x, float y, float w, float h, Qt.ItemSelectionMode mode = Qt.IntersectsItemShape)
```

这是一个重载函数。

回报，这取决于所有可见项目_mode_，是内部或相交与指定_polygon_并返回一个列表排序的使用_order_。

为默认值_mode_ is [Qt.IntersectsItemShape](qt.html#ItemSelectionMode-enum);所有项目的确切形状相交或包含由_polygon_返回。

_deviceTransform_是适用于该视图，​​并且需要如果场景中包含忽略的转换项目提供了转型。

此功能被引入Qt的4.6 。

**See also** [itemAt](qgraphicsscene.html#itemAt)（）和[Sorting](qgraphicsitem.html#sorting)。

```
list-of-QGraphicsItem QGraphicsScene.items (self, float x, float y, float w, float h, Qt.ItemSelectionMode mode, Qt.SortOrder order, QTransform deviceTransform = QTransform())
```

这是一个重载函数。

回报，这取决于所有可见项目_mode_，是内部或相交与指定_path_并返回一个列表排序的使用_order_。

为默认值_mode_ is [Qt.IntersectsItemShape](qt.html#ItemSelectionMode-enum);所有项目的确切形状相交或包含由_path_返回。

_deviceTransform_是适用于该视图，​​并且需要如果场景中包含忽略的转换项目提供了转型。

此功能被引入Qt的4.6 。

**See also** [itemAt](qgraphicsscene.html#itemAt)() and [Sorting](qgraphicsitem.html#sorting).

```
QRectF QGraphicsScene.itemsBoundingRect (self)
```

[

计算并返回现场所有项目的边界矩形。此功能通过遍历所有项目，并且因为如果这一点，它可能会很慢的大场面。

](qrectf.html)

[**See also**](qrectf.html) [sceneRect](qgraphicsscene.html#sceneRect-prop)（ ） 。

```
QGraphicsScene.keyPressEvent (self, QKeyEvent event)
```

此事件处理程序，对于事件_keyEvent_，可重新实现在子类来接收按键事件。默认实现转发事件到当前的重点项目。

**See also** [QGraphicsItem.keyPressEvent](qgraphicsitem.html#keyPressEvent)（）和[focusItem](qgraphicsscene.html#focusItem)（ ） 。

```
QGraphicsScene.keyReleaseEvent (self, QKeyEvent event)
```

此事件处理程序，对于事件_keyEvent_，可重新实现在子类中接收键释放事件。默认实现转发事件到当前的重点项目。

**See also** [QGraphicsItem.keyReleaseEvent](qgraphicsitem.html#keyReleaseEvent)（）和[focusItem](qgraphicsscene.html#focusItem)（ ） 。

```
QGraphicsScene.mouseDoubleClickEvent (self, QGraphicsSceneMouseEvent event)
```

此事件处理程序，对于事件_mouseEvent_，可重新实现在子类中接收鼠标双击事件现场。

如果有人在现场doubleclicks ，现场将先收到一个鼠标按下事件，随后释放事件（即点击） ，然后双击事件，终于释放事件。如果双击事件被传递到不同的项目比收到的第一个记者一个和释放，这将作为一个新闻事件。然而， tripleclick事件不传递在这种情况下双击事件。

默认的实现是类似[mousePressEvent](qgraphicsscene.html#mousePressEvent)（ ） 。

**See also** [QGraphicsItem.mousePressEvent](qgraphicsitem.html#mousePressEvent)（ ）[QGraphicsItem.mouseMoveEvent](qgraphicsitem.html#mouseMoveEvent)（ ）[QGraphicsItem.mouseReleaseEvent](qgraphicsitem.html#mouseReleaseEvent)（）和[QGraphicsItem.setAcceptedMouseButtons](qgraphicsitem.html#setAcceptedMouseButtons)（ ） 。

```
QGraphicsItem QGraphicsScene.mouseGrabberItem (self)
```

[

返回当前鼠标抓取物品，或者0，如果没有项目目前正在抓住鼠标。鼠标采集卡产品接收发送到场景中的所有鼠标事件的项目。

一个项目变成了鼠标抓取，当它收到并接受鼠标按下事件，它保持鼠标采集卡，直到以下事件发生：

*   If the item receives a mouse release event when there are no other buttons pressed, it loses the mouse grab.
*   If the item becomes invisible (i.e., someone calls `item-&gt;setVisible(false)`), or if it becomes disabled (i.e., someone calls `item-&gt;setEnabled(false)`), it loses the mouse grab.
*   If the item is removed from the scene, it loses the mouse grab.

如果该项目失去了它的鼠标抢，现场将忽略所有的鼠标事件，直到一个新的项目抓起鼠标（即，直到一个新的项目接收鼠标按下事件） 。

```
QGraphicsScene.mouseMoveEvent (self, QGraphicsSceneMouseEvent event)
```

此事件处理程序，对于事件_mouseEvent_，可重新实现在子类中接收鼠标移动事件的现场。

默认的实现依赖于鼠标抓取状态。如果有一个鼠标采集项目时，事件被发送给小鼠采集。如果有接受悬停事件在当前位置的任何物品，该事件被转化成一个悬停事件和接受，否则它忽略。

](qgraphicsitem.html)

[**See also**](qgraphicsitem.html) [QGraphicsItem.mousePressEvent](qgraphicsitem.html#mousePressEvent)（ ）[QGraphicsItem.mouseReleaseEvent](qgraphicsitem.html#mouseReleaseEvent)（ ）[QGraphicsItem.mouseDoubleClickEvent](qgraphicsitem.html#mouseDoubleClickEvent)（）和[QGraphicsItem.setAcceptedMouseButtons](qgraphicsitem.html#setAcceptedMouseButtons)（ ） 。

```
QGraphicsScene.mousePressEvent (self, QGraphicsSceneMouseEvent event)
```

此事件处理程序，对于事件_mouseEvent_，可重新实现在子类中接收鼠标按下事件现场。

默认的实现依赖于场景的状态。如果有一个鼠标采集卡产品，然后该事件被发送给小鼠采集。否则，它被转发到接受鼠标事件从事件现场位置的最上方项目，而该项目迅速成为鼠标抓取物品。

如果没有项目在现场给定的位置，选择区域被重置，所有重点项目失去了输入焦点，而该事件随后被忽略。

**See also** [QGraphicsItem.mousePressEvent](qgraphicsitem.html#mousePressEvent)（）和[QGraphicsItem.setAcceptedMouseButtons](qgraphicsitem.html#setAcceptedMouseButtons)（ ） 。

```
QGraphicsScene.mouseReleaseEvent (self, QGraphicsSceneMouseEvent event)
```

此事件处理程序，对于事件_mouseEvent_，可重新实现在子类中接收鼠标释放事件的现场。

默认的实现依赖于鼠标抓取状态。如果没有鼠标采集卡，该事件将被忽略。否则，如果有一个鼠标采集项目时，事件被发送给小鼠采集。如果这个鼠标释放代表鼠标上的最后按下按钮，鼠标采集项目，然后失去鼠标抢。

**See also** [QGraphicsItem.mousePressEvent](qgraphicsitem.html#mousePressEvent)（ ）[QGraphicsItem.mouseMoveEvent](qgraphicsitem.html#mouseMoveEvent)（ ）[QGraphicsItem.mouseDoubleClickEvent](qgraphicsitem.html#mouseDoubleClickEvent)（）和[QGraphicsItem.setAcceptedMouseButtons](qgraphicsitem.html#setAcceptedMouseButtons)（ ） 。

```
QPalette QGraphicsScene.palette (self)
```

[

```
QGraphicsScene.removeItem (self, QGraphicsItem item)
```

该_item_争论

](qpalette.html)

[删除的项目_item_而从现场的所有儿童。所有权_item_被传递给调用者（即](qpalette.html)[QGraphicsScene](qgraphicsscene.html)将不再删除_item_销毁时） 。

**See also** [addItem](qgraphicsscene.html#addItem)（ ） 。

```
QGraphicsScene.render (self, QPainter painter, QRectF target = QRectF(), QRectF source = QRectF(), Qt.AspectRatioMode mode = Qt.KeepAspectRatio)
```

呈现_source_从现场到RECT_target_，使用_painter_。此功能可用于捕捉场景的内容到一个绘图设备，如一个有用的[QImage](qimage.html)（例如，采取截图） ，或与印刷[QPrinter](qprinter.html)。例如：

```
 [QGraphicsScene](qgraphicsscene.html) scene;
 scene.addItem(...
 ...
 [QPrinter](qprinter.html) printer([QPrinter](qprinter.html).HighResolution);
 printer.setPaperSize([QPrinter](qprinter.html).A4);

 [QPainter](qpainter.html) painter(&printer);
 scene.render(&painter);

```

If _source_是一个空矩形，该函数将使用[sceneRect](qgraphicsscene.html#sceneRect-prop)（）来确定要呈现什么。如果_target_是一个空矩形，的尺寸_painter_的绘图设备将被使用。

矩形内容源将根据待转化_aspectRatioMode_以适应目标矩形。默认情况下，纵横比蒙了，_source_缩放以适合_target_。

**See also** [QGraphicsView.render](qgraphicsview.html#render)（ ） 。

```
QRectF QGraphicsScene.sceneRect (self)
```

[

```
list-of-QGraphicsItem QGraphicsScene.selectedItems (self)
```

将返回所有当前选定项的列表。该项目在没有特定的顺序返回。

](qrectf.html)

[**See also**](qrectf.html) [setSelectionArea](qgraphicsscene.html#setSelectionArea)（ ） 。

```
QPainterPath QGraphicsScene.selectionArea (self)
```

[](qpainterpath.html)

[返回先前设置的选择区域](qpainterpath.html)[setSelectionArea](qgraphicsscene.html#setSelectionArea)（ ） ，或空[QPainterPath](qpainterpath.html)如果没有选择区域已设置。

**See also** [setSelectionArea](qgraphicsscene.html#setSelectionArea)（ ） 。

```
bool QGraphicsScene.sendEvent (self, QGraphicsItem item, QEvent event)
```

发送事件_event_项_item_可以通过事件过滤器。

只有当项目被勾选的情况下被发送。

Returns `false`如果事件已被过滤或如果该项目被禁用。否则返回从事件处理程序返回的值。

此功能被引入Qt的4.6 。

**See also** [QGraphicsItem.sceneEvent](qgraphicsitem.html#sceneEvent)（）和[QGraphicsItem.sceneEventFilter](qgraphicsitem.html#sceneEventFilter)（ ） 。

```
QGraphicsScene.setActivePanel (self, QGraphicsItem item)
```

激活_item_，它必须是在这个场景中的项目。您也可以通过0_item_在这种情况下[QGraphicsScene](qgraphicsscene.html)将停用任何当前活动面板。

如果场景是目前处于非活动状态，_item_保持非活动状态，直到现场被激活（或IR_item_为0 ，没有任何产品将被激活） 。

此功能被引入Qt的4.6 。

**See also** [activePanel](qgraphicsscene.html#activePanel)（ ）[isActive](qgraphicsscene.html#isActive)（）和[QGraphicsItem.isActive](qgraphicsitem.html#isActive)（ ） 。

```
QGraphicsScene.setActiveWindow (self, QGraphicsWidget widget)
```

激活_widget_，它必须是在这个场景中的小部件。您也可以通过0_widget_在这种情况下[QGraphicsScene](qgraphicsscene.html)将停用任何当前活动窗口。

此功能被引入Qt的4.4 。

**See also** [activeWindow](qgraphicsscene.html#activeWindow)（）和[QGraphicsWidget.isActiveWindow](qgraphicswidget.html#isActiveWindow)（ ） 。

```
QGraphicsScene.setBackgroundBrush (self, QBrush brush)
```

```
QGraphicsScene.setBspTreeDepth (self, int depth)
```

```
QGraphicsScene.setFocus (self, Qt.FocusReason focusReason = Qt.OtherFocusReason)
```

将焦点设置在现场通过发送[QFocusEvent](qfocusevent.html)到了现场，经过_focusReason_作为原因。如果场景早先失去它，而一个项目具有焦点后重新获得焦点，最后的重点项目将获得焦点与_focusReason_作为原因。

如果场景已经成为焦点，此函数什么都不做。

**See also** [hasFocus](qgraphicsscene.html#hasFocus)（ ）[clearFocus](qgraphicsscene.html#clearFocus)（）和[setFocusItem](qgraphicsscene.html#setFocusItem)（ ） 。

```
QGraphicsScene.setFocusItem (self, QGraphicsItem item, Qt.FocusReason focusReason = Qt.OtherFocusReason)
```

设置场景的重点项目_item_，重点原因_focusReason_，从可能有焦点以往任何物品取出后焦点。

If _item_是0 ，或者如果它要么不接受焦点（即，它不具有[QGraphicsItem.ItemIsFocusable](qgraphicsitem.html#GraphicsItemFlag-enum)标志启用） ，或者是不可见的或不启用，该功能只删除焦点由以往任何focusitem 。

如果产品不为0 ，场面目前没有焦点（即，[hasFocus](qgraphicsscene.html#hasFocus)（ ）返回False ） ，这个函数会调用[setFocus](qgraphicsscene.html#setFocus)（自动） 。

**See also** [focusItem](qgraphicsscene.html#focusItem)（ ）[hasFocus](qgraphicsscene.html#hasFocus)（）和[setFocus](qgraphicsscene.html#setFocus)（ ） 。

```
QGraphicsScene.setFont (self, QFont font)
```

```
QGraphicsScene.setForegroundBrush (self, QBrush brush)
```

```
QGraphicsScene.setItemIndexMethod (self, ItemIndexMethod method)
```

```
QGraphicsScene.setPalette (self, QPalette palette)
```

```
QGraphicsScene.setSceneRect (self, QRectF rect)
```

```
QGraphicsScene.setSceneRect (self, float x, float y, float w, float h)
```

```
QGraphicsScene.setSelectionArea (self, QPainterPath path, QTransform deviceTransform)
```

设置选择区域_path_。在此区域内的所有项目会立即选中，所有项目外均为Unselected 。你可以通过调用获取所有选定的项目清单[selectedItems](qgraphicsscene.html#selectedItems)（ ） 。

_deviceTransform_是适用于该视图，​​并且需要如果场景中包含忽略的转换项目提供了转型。

为一个项目被选中，它必须被标记为_selectable_（[QGraphicsItem.ItemIsSelectable](qgraphicsitem.html#GraphicsItemFlag-enum)） 。

此功能被引入Qt的4.6 。

**See also** [clearSelection](qgraphicsscene.html#clearSelection)（）和[selectionArea](qgraphicsscene.html#selectionArea)（ ） 。

```
QGraphicsScene.setSelectionArea (self, QPainterPath path)
```

```
QGraphicsScene.setSelectionArea (self, QPainterPath path, Qt.ItemSelectionMode)
```

```
QGraphicsScene.setSelectionArea (self, QPainterPath path, Qt.ItemSelectionMode mode, QTransform deviceTransform)
```

这是一个重载函数。

设置选择区域_path_ using _mode_以确定数据项都包含在选择的区域。

_deviceTransform_是适用于该视图，​​并且需要如果场景中包含忽略的转换项目提供了转型。

此功能被引入Qt的4.6 。

**See also** [clearSelection](qgraphicsscene.html#clearSelection)（）和[selectionArea](qgraphicsscene.html#selectionArea)（ ） 。

```
QGraphicsScene.setSortCacheEnabled (self, bool enabled)
```

```
QGraphicsScene.setStickyFocus (self, bool enabled)
```

```
QGraphicsScene.setStyle (self, QStyle style)
```

该_style_说法有它的所有权转移给Qt的。

设置或替换场景的风格_style_和reparents的风格了这一幕。任何先前分配的风格被删除。场景的风格默认为[QApplication.style](qapplication.html#style)（ ） ，并作为默认为全部[QGraphicsWidget](qgraphicswidget.html)场景中的项目。

改变风格，无论是直接通过调用调用这个函数，或间接[QApplication.setStyle](qapplication.html#setStyle)（ ） ，会自动更新样式场景中的所有部件没有明确分配给他们的风格。

If _style_为0时，[QGraphicsScene](qgraphicsscene.html)将恢复到[QApplication.style](qapplication.html#style)（ ） 。

此功能被引入Qt的4.4 。

**See also** [style](qgraphicsscene.html#style)（ ） 。

```
bool QGraphicsScene.stickyFocus (self)
```

```
QStyle QGraphicsScene.style (self)
```

[](qstyle.html)

[返回场景的风格，还是一样](qstyle.html)[QApplication.style](qapplication.html#style)（ ）如果场景没有被明确指定的样式。

此功能被引入Qt的4.4 。

**See also** [setStyle](qgraphicsscene.html#setStyle)（ ） 。

```
QGraphicsScene.update (self, QRectF rect = QRectF())
```

这种方法也是一个Qt槽与C + +的签名`void update(const QRectF& = QRectF())`。

调度区域的重绘_rect_在现场。

**See also** [sceneRect](qgraphicsscene.html#sceneRect-prop)（）和[changed](qgraphicsscene.html#changed)（ ） 。

```
QGraphicsScene.update (self, float x, float y, float w, float h)
```

这是一个重载函数。

此功能相当于调用update （[QRectF](qrectf.html)（_x_，_y_，_w_，_h_））;

此功能被引入Qt的4.3 。

```
list-of-QGraphicsView QGraphicsScene.views (self)
```

返回的所有显示这一幕的视图的列表。

**See also** [QGraphicsView.scene](qgraphicsview.html#scene)（ ） 。

```
QGraphicsScene.wheelEvent (self, QGraphicsSceneWheelEvent event)
```

此事件处理程序，对于事件_wheelEvent_，可重新实现在子类中接收鼠标滚轮事件的现场。

默认情况下，该事件被光标下传递到最上面的可见项目。如果置之不理，事件传播到项目之下，并再次，直到事件被接受，或到达现场。如果没有任何项目接受的情况下，它会被忽略。

**See also** [QGraphicsItem.wheelEvent](qgraphicsitem.html#wheelEvent)（ ） 。

```
float QGraphicsScene.width (self)
```

这个方便的功能等同于调用[sceneRect](qgraphicsscene.html#sceneRect-prop)（ ） ，宽（ ） 。

**See also** [height](qgraphicsscene.html#height)（ ） 。

* * *

## Qt Signal Documentation

```
void changed (const QList<QRectF>&)
```

这是该信号的默认超载。

这个信号是由发射[QGraphicsScene](qgraphicsscene.html)当控制到达事件循环，如果场景内容的变化。该_region_参数包含场景的矩形，表明已经改变了该地区的名单。

**See also** [QGraphicsView.updateScene](qgraphicsview.html#updateScene)（ ） 。

```
void sceneRectChanged (const QRectF&)
```

这是该信号的默认超载。

这个信号是由发射[QGraphicsScene](qgraphicsscene.html)每当现场RECT变化。该_rect_参数是新场景的矩形。

**See also** [QGraphicsView.updateSceneRect](qgraphicsview.html#updateSceneRect)（ ） 。

```
void selectionChanged ()
```

这是该信号的默认超载。

这个信号是由发射[QGraphicsScene](qgraphicsscene.html)只要选择发生改变。您可以致电[selectedItems](qgraphicsscene.html#selectedItems)（）来获取选定项的新列表。

当一个项目被选中或取消选择，一个选择区域设置，清除或以其他方式改变时，如果预先选择的项目被添加到场景中，或者如果选择的项目是从场景中删除的选择改变。

[QGraphicsScene](qgraphicsscene.html)为组选择操作发出这个信号只有一次。例如，如果你设置一个选择区域，选择或取消选择[QGraphicsItemGroup](qgraphicsitemgroup.html)，或者如果您添加或从场景中删除包含多个选定项目的SelectionChanged （ ）是（每个项目，而不是一次）发出只有一次操作完成后，一个父项。

此功能被引入Qt的4.3 。

**See also** [setSelectionArea](qgraphicsscene.html#setSelectionArea)（ ）[selectedItems](qgraphicsscene.html#selectedItems)（）和[QGraphicsItem.setSelected](qgraphicsitem.html#setSelected)（ ） 。