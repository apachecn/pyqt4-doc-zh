# QGraphicsView Class Reference

## [[QtGui](index.htm) module]

该QGraphicsView类提供了一个小工具，用于显示的内容[QGraphicsScene](qgraphicsscene.html)。[More...](#details)

继承[QAbstractScrollArea](qabstractscrollarea.html)。

通过继承[QDeclarativeView](qdeclarativeview.html)。

### Types

*   `class **[CacheMode](index.htm)**`
*   `enum CacheModeFlag { CacheNone, CacheBackground }`
*   `enum DragMode { NoDrag, ScrollHandDrag, RubberBandDrag }`
*   `enum OptimizationFlag { DontClipPainter, DontSavePainterState, DontAdjustForAntialiasing }`
*   `class **[OptimizationFlags](index.htm)**`
*   `enum ViewportAnchor { NoAnchor, AnchorViewCenter, AnchorUnderMouse }`
*   `enum ViewportUpdateMode { FullViewportUpdate, MinimalViewportUpdate, SmartViewportUpdate, BoundingRectViewportUpdate, NoViewportUpdate }`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `__init__ (self, QGraphicsScene scene, QWidget parent = None)`
*   `Qt.Alignment alignment (self)`
*   `QBrush backgroundBrush (self)`
*   `CacheMode cacheMode (self)`
*   `centerOn (self, QPointF pos)`
*   `centerOn (self, QGraphicsItem item)`
*   `centerOn (self, float ax, float ay)`
*   `contextMenuEvent (self, QContextMenuEvent event)`
*   `dragEnterEvent (self, QDragEnterEvent event)`
*   `dragLeaveEvent (self, QDragLeaveEvent event)`
*   `DragMode dragMode (self)`
*   `dragMoveEvent (self, QDragMoveEvent event)`
*   `drawBackground (self, QPainter painter, QRectF rect)`
*   `drawForeground (self, QPainter painter, QRectF rect)`
*   `drawItems (self, QPainter painter, list-of-QGraphicsItem items, list-of-QStyleOptionGraphicsItem options)`
*   `dropEvent (self, QDropEvent event)`
*   `ensureVisible (self, QRectF rect, int xMargin = 50, int yMargin = 50)`
*   `ensureVisible (self, QGraphicsItem item, int xMargin = 50, int yMargin = 50)`
*   `ensureVisible (self, float x, float y, float w, float h, int xMargin = 50, int yMargin = 50)`
*   `bool event (self, QEvent event)`
*   `fitInView (self, QRectF rect, Qt.AspectRatioMode mode = Qt.IgnoreAspectRatio)`
*   `fitInView (self, QGraphicsItem item, Qt.AspectRatioMode mode = Qt.IgnoreAspectRatio)`
*   `fitInView (self, float x, float y, float w, float h, Qt.AspectRatioMode mode = Qt.IgnoreAspectRatio)`
*   `focusInEvent (self, QFocusEvent event)`
*   `bool focusNextPrevChild (self, bool next)`
*   `focusOutEvent (self, QFocusEvent event)`
*   `QBrush foregroundBrush (self)`
*   `inputMethodEvent (self, QInputMethodEvent event)`
*   `QVariant inputMethodQuery (self, Qt.InputMethodQuery query)`
*   `invalidateScene (self, QRectF rect = QRectF(), QGraphicsScene.SceneLayers layers = QGraphicsScene.AllLayers)`
*   `bool isInteractive (self)`
*   `bool isTransformed (self)`
*   `QGraphicsItem itemAt (self, QPoint pos)`
*   `QGraphicsItem itemAt (self, int ax, int ay)`
*   `list-of-QGraphicsItem items (self)`
*   `list-of-QGraphicsItem items (self, QPoint pos)`
*   `list-of-QGraphicsItem items (self, int ax, int ay)`
*   `list-of-QGraphicsItem items (self, int x, int y, int w, int h, Qt.ItemSelectionMode mode = Qt.IntersectsItemShape)`
*   `list-of-QGraphicsItem items (self, QRect rect, Qt.ItemSelectionMode mode = Qt.IntersectsItemShape)`
*   `list-of-QGraphicsItem items (self, QPolygon polygon, Qt.ItemSelectionMode mode = Qt.IntersectsItemShape)`
*   `list-of-QGraphicsItem items (self, QPainterPath path, Qt.ItemSelectionMode mode = Qt.IntersectsItemShape)`
*   `keyPressEvent (self, QKeyEvent event)`
*   `keyReleaseEvent (self, QKeyEvent event)`
*   `QPoint mapFromScene (self, QPointF point)`
*   `QPolygon mapFromScene (self, QRectF rect)`
*   `QPolygon mapFromScene (self, QPolygonF polygon)`
*   `QPainterPath mapFromScene (self, QPainterPath path)`
*   `QPoint mapFromScene (self, float ax, float ay)`
*   `QPolygon mapFromScene (self, float ax, float ay, float w, float h)`
*   `QPointF mapToScene (self, QPoint point)`
*   `QPolygonF mapToScene (self, QRect rect)`
*   `QPolygonF mapToScene (self, QPolygon polygon)`
*   `QPainterPath mapToScene (self, QPainterPath path)`
*   `QPointF mapToScene (self, int ax, int ay)`
*   `QPolygonF mapToScene (self, int ax, int ay, int w, int h)`
*   `QMatrix matrix (self)`
*   `mouseDoubleClickEvent (self, QMouseEvent event)`
*   `mouseMoveEvent (self, QMouseEvent event)`
*   `mousePressEvent (self, QMouseEvent event)`
*   `mouseReleaseEvent (self, QMouseEvent event)`
*   `OptimizationFlags optimizationFlags (self)`
*   `paintEvent (self, QPaintEvent event)`
*   `render (self, QPainter painter, QRectF target = QRectF(), QRect source = QRect(), Qt.AspectRatioMode mode = Qt.KeepAspectRatio)`
*   `QPainter.RenderHints renderHints (self)`
*   `resetCachedContent (self)`
*   `resetMatrix (self)`
*   `resetTransform (self)`
*   `ViewportAnchor resizeAnchor (self)`
*   `resizeEvent (self, QResizeEvent event)`
*   `rotate (self, float angle)`
*   `Qt.ItemSelectionMode rubberBandSelectionMode (self)`
*   `scale (self, float sx, float sy)`
*   `QGraphicsScene scene (self)`
*   `QRectF sceneRect (self)`
*   `scrollContentsBy (self, int dx, int dy)`
*   `setAlignment (self, Qt.Alignment alignment)`
*   `setBackgroundBrush (self, QBrush brush)`
*   `setCacheMode (self, CacheMode mode)`
*   `setDragMode (self, DragMode mode)`
*   `setForegroundBrush (self, QBrush brush)`
*   `setInteractive (self, bool allowed)`
*   `setMatrix (self, QMatrix matrix, bool combine = False)`
*   `setOptimizationFlag (self, OptimizationFlag flag, bool enabled = True)`
*   `setOptimizationFlags (self, OptimizationFlags flags)`
*   `setRenderHint (self, QPainter.RenderHint hint, bool on = True)`
*   `setRenderHints (self, QPainter.RenderHints hints)`
*   `setResizeAnchor (self, ViewportAnchor anchor)`
*   `setRubberBandSelectionMode (self, Qt.ItemSelectionMode mode)`
*   `setScene (self, QGraphicsScene scene)`
*   `setSceneRect (self, QRectF rect)`
*   `setSceneRect (self, float ax, float ay, float aw, float ah)`
*   `setTransform (self, QTransform matrix, bool combine = False)`
*   `setTransformationAnchor (self, ViewportAnchor anchor)`
*   `setupViewport (self, QWidget widget)`
*   `setViewportUpdateMode (self, ViewportUpdateMode mode)`
*   `shear (self, float sh, float sv)`
*   `showEvent (self, QShowEvent event)`
*   `QSize sizeHint (self)`
*   `QTransform transform (self)`
*   `ViewportAnchor transformationAnchor (self)`
*   `translate (self, float dx, float dy)`
*   `updateScene (self, list-of-QRectF rects)`
*   `updateSceneRect (self, QRectF rect)`
*   `bool viewportEvent (self, QEvent event)`
*   `QTransform viewportTransform (self)`
*   `ViewportUpdateMode viewportUpdateMode (self)`
*   `wheelEvent (self, QWheelEvent event)`

* * *

## Detailed Description

该QGraphicsView类提供了一个小工具，用于显示的内容[QGraphicsScene](qgraphicsscene.html)。

QGraphicsView可视化的内容[QGraphicsScene](qgraphicsscene.html)在一个可滚动的视口。要创建具有几何项目的场景，看到[QGraphicsScene](qgraphicsscene.html)的文档。 QGraphicsView是部分[Graphics View Framework](index.htm)。

看到一个场景，你通过构建一个QGraphicsView对象，传递你希望显示到QGraphicsView的构造场景的地址开始。或者，您也可以致电[setScene](qgraphicsview.html#setScene)（）来设置场景在稍后一点。你打电话后[show](qwidget.html#show)（ ） ，视图将默认滚动到场景的中心，并显示在这一点上可见的任何物品。例如：

```
 [QGraphicsScene](qgraphicsscene.html) scene;
 scene.addText("Hello, world!");

 QGraphicsView view(&scene);
 view.show();

```

你可以明确地滚动到现场使用滚动条的任何位置，或致电[centerOn](qgraphicsview.html#centerOn)（ ） 。通过传递点[centerOn](qgraphicsview.html#centerOn)（ ） ， QGraphicsView将滚动的视口，以确保点集中在视图中。过载提供滚动到[QGraphicsItem](qgraphicsitem.html)在这种情况下QGraphicsView将看到的项的中心为中心的视图。如果你想要的是确保一定的区域是可见的， （但不一定为中心），你可以调用[ensureVisible](qgraphicsview.html#ensureVisible)（ ）来代替。

QGraphicsView可以用来可视化整个场景，或仅部分。可视化领域是默认自动检测时显示的视图第一次（通过调用[QGraphicsScene.itemsBoundingRect](qgraphicsscene.html#itemsBoundingRect)（））。要设置可视区域矩形自己，你可以调用[setSceneRect](qgraphicsview.html#sceneRect-prop)（ ） 。这将适当调整滚动条“的范围。请注意，虽然场景支持几乎无限的大小，滚动条的范围不会超过一个整数（ INT_MIN ， INT_MAX ）的范围内。

QGraphicsView通过调用可视化场景[render](qgraphicsview.html#render)（ ） 。默认情况下，该项目通过使用常规绘制到视[QPainter](qpainter.html)以及使用默认呈现提示。要更改默认的渲染提示QGraphicsView传递到[QPainter](qpainter.html)涂装项目时，您可以拨打[setRenderHints](qgraphicsview.html#renderHints-prop)（ ） 。

默认情况下， QGraphicsView提供了一个正规[QWidget](qwidget.html)为视角构件。您可以通过调用访问这个widget[viewport](qabstractscrollarea.html#viewport)（ ） ，或者你可以通过调用替换它[setViewport](qabstractscrollarea.html#setViewport)（ ） 。为了呈现使用OpenGL ，只需调用setViewport （新[QGLWidget](qglwidget.html)） 。 QGraphicsView需要视口部件的所有权。

QGraphicsView支持仿射变换，用[QTransform](qtransform.html)。您可以将矩阵要么传递给[setTransform](qgraphicsview.html#setTransform)（ ） ，或者您也可以拨打方便的功能之一[rotate](qgraphicsview.html#rotate)（ ）[scale](qgraphicsview.html#scale)（ ）[translate](qgraphicsview.html#translate)（）或[shear](qgraphicsview.html#shear)（ ） 。最常见2转换的比例，这是用于实现缩放和旋转。 QGraphicsView保持在转换过程中的固定视图的中心。因为现场校准（ setAligment （ ） ）的，翻译的看法不会有视觉冲击力。

您可以使用鼠标和键盘对场景中的项目进行互动。 QGraphicsView转化鼠标和键盘事件到_scene_事件（事件继承[QGraphicsSceneEvent](qgraphicssceneevent.html)， ） ，并将其转发到可视化的场景。在最后，它是处理该事件并发生反应，它们的个别项目。例如，如果你点击一个可选项目，该项目将通常让现场知道它已被选中，它也将重绘自身来显示一个选择矩形。 Similiary ，如果您单击并拖动鼠标来移动一个可移动的项目，它是处理鼠标移动和移动自己的项目。项目的互动是默认启用的，你可以通过调用它切换[setInteractive](qgraphicsview.html#interactive-prop)（ ） 。

您也可以提供自己的自定义场景的交互，通过创建QGraphicsView的一个子类，并重新实现鼠标和键盘事件处理程序。为了简化你如何与视图中的项编程交互， QGraphicsView提供了映射函数[mapToScene](qgraphicsview.html#mapToScene)（）和[mapFromScene](qgraphicsview.html#mapFromScene)（） ，并且项目的存取[items](qgraphicsview.html#items)（）和[itemAt](qgraphicsview.html#itemAt)（ ） 。这些功能允许你映射视图坐标和场景之间的坐标点，矩形，多边形和路径，并找到使用视图坐标在现场的项目。

![](../img/graphicsview-view.png)

* * *

## Type Documentation

```
QGraphicsView.CacheModeFlag
```

这个枚举说明您可以对设置的标志[QGraphicsView](qgraphicsview.html)的缓存模式。

| Constant | Value | Description |
| --- | --- | --- |
| `QGraphicsView.CacheNone` | `0x0` | 所有的画是直接完成到视口。 |
| `QGraphicsView.CacheBackground` | `0x1` | 后台缓存。这会影响自定义的背景，并基于该背景[backgroundBrush](qgraphicsview.html#backgroundBrush-prop)属性。当这个标志被启用，[QGraphicsView](qgraphicsview.html)将分配一个像素图与视口的全尺寸。 |

CacheMode参数类型是一个typedef为[QFlags](index.htm)\u003cCacheModeFlag\u003e 。它存储CacheModeFlag值的或组合。

**See also** [cacheMode](qgraphicsview.html#cacheMode-prop)。

```
QGraphicsView.DragMode
```

按住并拖动鼠标移到视口时，此枚举描述的默认操作的视图。

| Constant | Value | Description |
| --- | --- | --- |
| `QGraphicsView.NoDrag` | `0` | 什么也没有发生;鼠标事件被忽略。 |
| `QGraphicsView.ScrollHandDrag` | `1` | 光标变为手形指针，和周围拖动鼠标将滚动scrolbars 。此模式无论是在[interactive](qgraphicsview.html#interactive-prop)和非交互模式。 |
| `QGraphicsView.RubberBandDrag` | `2` | 橡胶带将出现。拖动鼠标，将设置橡皮筋的几何形状，以及所涵盖的橡皮筋​​会选择所有项目。这种模式对于非交互式的看法禁用。 |

**See also** [dragMode](qgraphicsview.html#dragMode-prop)和[QGraphicsScene.setSelectionArea](qgraphicsscene.html#setSelectionArea)（ ） 。

```
QGraphicsView.OptimizationFlag
```

这个枚举说明标志，您可以启用，以提高渲染性能[QGraphicsView](qgraphicsview.html)。默认情况下，没有这些标志的设置。请注意，设置一个标志，通常对一个副作用，这种作用可以喷漆设备和平台之间变化。

| Constant | Value | Description |
| --- | --- | --- |
| `QGraphicsView.DontClipPainter` | `0x1` | 此值已过时，没有任何效果。 |
| `QGraphicsView.DontSavePainterState` | `0x2` | 当渲染，[QGraphicsView](qgraphicsview.html)保护画家状态（见[QPainter.save](qpainter.html#save)（ ） ）绘制背景或前景时，并呈现每个项目时。这可以让你离开画家在改变状态（例如，你可以调用[QPainter.setPen](qpainter.html#setPen)（）或[QPainter.setBrush](qpainter.html#setBrush)（ ）无涂装后恢复状态） 。但是，如果项目持续做恢复状态，您应该启用这个标志，以防止[QGraphicsView](qgraphicsview.html)从做同样的。 |
| `QGraphicsView.DontAdjustForAntialiasing` | `0x4` | 禁用[QGraphicsView](qgraphicsview.html)的抗锯齿自动调整曝光过的区域。该渲染的抗锯齿边界线的项目[QGraphicsItem.boundingRect](qgraphicsitem.html#boundingRect)（ ）可以结束了渲染线的部分外。为了防止渲染文物，[QGraphicsView](qgraphicsview.html)通过在各个方向2像素展开所有暴露区域。如果您启用这个标志，[QGraphicsView](qgraphicsview.html)将不再执行这些调整，最大限度地减少需要重绘，从而提高了性能方面。一个常见的副作用是那些绘制抗锯齿项目能留下痕迹的绘画背后的身影，因为他们所感动。 |
| `QGraphicsView.IndirectPainting` | `0x8` | 由于Qt的4.6 ，恢复旧的绘画算法调用[QGraphicsView.drawItems](index.htm#drawItems)（）和[QGraphicsScene.drawItems](index.htm#drawItems)（ ） 。要只是为了与旧代码的兼容性使用。 |

这个枚举被引入或修改的Qt 4.3 。

该OptimizationFlags类型是一个typedef为[QFlags](index.htm)\u003cOptimizationFlag\u003e 。它存储OptimizationFlag值的或组合。

```
QGraphicsView.ViewportAnchor
```

此枚举描述了可能的锚[QGraphicsView](qgraphicsview.html)当用户改变视图或视图时转化可以使用。

| Constant | Value | Description |
| --- | --- | --- |
| `QGraphicsView.NoAnchor` | `0` | 无锚，即认为离开现场的位置不变。 |
| `QGraphicsView.AnchorViewCenter` | `1` | 在视图的中心现场点作为支撑点。 |
| `QGraphicsView.AnchorUnderMouse` | `2` | 鼠标下的点作为支撑点。 |

**See also** [resizeAnchor](qgraphicsview.html#resizeAnchor-prop)和[transformationAnchor](qgraphicsview.html#transformationAnchor-prop)。

```
QGraphicsView.ViewportUpdateMode
```

这个枚举说明如何[QGraphicsView](qgraphicsview.html)更新其视口时的情景内容变更或暴露。

| Constant | Value | Description |
| --- | --- | --- |
| `QGraphicsView.FullViewportUpdate` | `0` | 当场景中任何可见部分改变或再次暴露，[QGraphicsView](qgraphicsview.html)将更新整个视口。这种方法是最快的时候[QGraphicsView](qgraphicsview.html)花费更多的时间搞清楚什么画会比花绘图（例如，当非常多的小项目，多次更新） 。这是优选的更新模式对视口不支持部分更新，如[QGLWidget](qglwidget.html)，为此，需要禁用滚动优化的视口。 |
| `QGraphicsView.MinimalViewportUpdate` | `1` | [QGraphicsView](qgraphicsview.html)将确定的最小视口区域需要重绘，尽量减少避免那些没有改变的区域重绘图纸花费的时间。这是[QGraphicsView](qgraphicsview.html)的默认模式。虽然这种方法提供了最佳的性能在一般情况下，如果有在现场许多小可见的变化，[QGraphicsView](qgraphicsview.html)最终可能会花费更多的时间寻找最小的方法比将斥资绘图。 |
| `QGraphicsView.SmartViewportUpdate` | `2` | [QGraphicsView](qgraphicsview.html)将尝试通过分析那些需要重绘的区域找到一个最佳的更新模式。 |
| `QGraphicsView.BoundingRectViewportUpdate` | `4` | 在视口中的所有更改的边框将被重新绘制。这种模式具有的优点是[QGraphicsView](qgraphicsview.html)搜索只有一个变化区域，最大限度地减少花费的时间确定什么需要重绘。它的缺点是没有变化的区域也需要被重新绘制。 |
| `QGraphicsView.NoViewportUpdate` | `3` | [QGraphicsView](qgraphicsview.html)永远不会更新其视口时的情景变化，用户有望控制所有更新。此模式禁用所有（可能慢）项的可见性测试[QGraphicsView](qgraphicsview.html)以及适合于场景，要么需要固定帧速率，或在视口外部，否则更新。 |

这个枚举被引入或修改的Qt 4.3 。

**See also** [viewportUpdateMode](qgraphicsview.html#viewportUpdateMode-prop)。

* * *

## Method Documentation

```
QGraphicsView.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QGraphicsView](qgraphicsview.html)。_parent_被传递给[QWidget](qwidget.html)的构造。

```
QGraphicsView.__init__ (self, QGraphicsScene scene, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QGraphicsView](qgraphicsview.html)并设置可视化场景_scene_。_parent_被传递给[QWidget](qwidget.html)的构造。

```
Qt.Alignment QGraphicsView.alignment (self)
```

[](index.htm)

```
QBrush QGraphicsView.backgroundBrush (self)
```

[](qbrush.html)

```
CacheMode QGraphicsView.cacheMode (self)
```

[

```
QGraphicsView.centerOn (self, QPointF pos)
```

滚动视口的内容，以确保现场协调_pos_，集中在视图中。

因为_pos_是一个浮点坐标，滚动条上的整数坐标进行操作，对中只是一个近似值。

**Note:**如果该项目已接近或外部的边界，这将是可见的视图，但不集中。

](index.htm)

[**See also**](index.htm) [ensureVisible](qgraphicsview.html#ensureVisible)（ ） 。

```
QGraphicsView.centerOn (self, QGraphicsItem item)
```

这是一个重载函数。

此功能提供了方便。这相当于调用centerOn （[QPointF](qpointf.html)（_x_，_y_））。

```
QGraphicsView.centerOn (self, float ax, float ay)
```

这是一个重载函数。

滚动视口的内容，以确保_item_集中在视图中。

**See also** [ensureVisible](qgraphicsview.html#ensureVisible)（ ） 。

```
QGraphicsView.contextMenuEvent (self, QContextMenuEvent event)
```

从重新实现[QWidget.contextMenuEvent](qwidget.html#contextMenuEvent)（ ） 。

```
QGraphicsView.dragEnterEvent (self, QDragEnterEvent event)
```

从重新实现[QWidget.dragEnterEvent](qwidget.html#dragEnterEvent)（ ） 。

```
QGraphicsView.dragLeaveEvent (self, QDragLeaveEvent event)
```

从重新实现[QWidget.dragLeaveEvent](qwidget.html#dragLeaveEvent)（ ） 。

```
DragMode QGraphicsView.dragMode (self)
```

[

```
QGraphicsView.dragMoveEvent (self, QDragMoveEvent event)
```

](qgraphicsview.html#DragMode-enum)

[从重新实现](qgraphicsview.html#DragMode-enum)[QWidget.dragMoveEvent](qwidget.html#dragMoveEvent)（ ） 。

```
QGraphicsView.drawBackground (self, QPainter painter, QRectF rect)
```

绘制的场景采用背景_painter_之前，任何产品和前景绘制。重新实现这个函数提供一个自定义的背景这一观点。

如果你想要的是定义一个颜色，纹理或渐变的背景，你可以调用[setBackgroundBrush](qgraphicsview.html#backgroundBrush-prop)（ ）来代替。

所有的绘制是在做_scene_坐标。_rect_是暴露的矩形。

默认实现罢了_rect_使用视图的[backgroundBrush](qgraphicsview.html#backgroundBrush-prop)。如果没有这样的笔刷定义（默认） ，场景的drawBackground （ ）函数被调用来代替。

**See also** [drawForeground](qgraphicsview.html#drawForeground)（）和[QGraphicsScene.drawBackground](qgraphicsscene.html#drawBackground)（ ） 。

```
QGraphicsView.drawForeground (self, QPainter painter, QRectF rect)
```

绘制场景的使用前景_painter_，背景和所有项目后得出。重新实现这个函数提供一个自定义前景的这一观点。

如果你想要的是定义一个颜色，纹理或渐变的前景，你可以调用[setForegroundBrush](qgraphicsview.html#foregroundBrush-prop)（ ）来代替。

所有的绘制是在做_scene_坐标。_rect_是暴露的矩形。

默认实现罢了_rect_使用视图的[foregroundBrush](qgraphicsview.html#foregroundBrush-prop)。如果没有这样的笔刷定义（默认） ，场景的drawForeground （ ）函数被调用来代替。

**See also** [drawBackground](qgraphicsview.html#drawBackground)（）和[QGraphicsScene.drawForeground](qgraphicsscene.html#drawForeground)（ ） 。

```
QGraphicsView.drawItems (self, QPainter painter, list-of-QGraphicsItem items, list-of-QStyleOptionGraphicsItem options)
```

```
QGraphicsView.dropEvent (self, QDropEvent event)
```

从重新实现[QWidget.dropEvent](qwidget.html#dropEvent)（ ） 。

```
QGraphicsView.ensureVisible (self, QRectF rect, int xMargin = 50, int yMargin = 50)
```

视口的滚动内容，使现场的矩形_rect_可见，与以像素为单位指定页边距_xmargin_和_ymargin_。如果指定的矩形无法达成，内容滚动到最近的有效位置。两个边距的默认值是50个像素。

**See also** [centerOn](qgraphicsview.html#centerOn)（ ） 。

```
QGraphicsView.ensureVisible (self, QGraphicsItem item, int xMargin = 50, int yMargin = 50)
```

这是一个重载函数。

此功能提供了方便。这相当于调用ensureVisible （[QRectF](qrectf.html)（_x_，_y_，_w_，_h_） ，_xmargin_，_ymargin_） 。

```
QGraphicsView.ensureVisible (self, float x, float y, float w, float h, int xMargin = 50, int yMargin = 50)
```

这是一个重载函数。

滚动视口的内容，使项目的中心_item_可见，与以像素为单位指定页边距_xmargin_和_ymargin_。如果指定的点不能达到，其内容被滚动到最近的有效位置。两个边距的默认值是50个像素。

**See also** [centerOn](qgraphicsview.html#centerOn)（ ） 。

```
bool QGraphicsView.event (self, QEvent event)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
QGraphicsView.fitInView (self, QRectF rect, Qt.AspectRatioMode mode = Qt.IgnoreAspectRatio)
```

缩放视图矩阵和滚动滚动条，以确保现场的矩形_rect_适合视口内。_rect_必须是现场矩形内部，否则fitInView （ ）不能保证整个RECT是可见的。

此功能保持视图的旋转，平移，或剪切。该视图是根据缩放_aspectRatioMode_。_rect_将集中在视图中，如果它不紧紧贴合。

这是常见的从一个重新实现内部调用fitInView （ ）[resizeEvent](qgraphicsview.html#resizeEvent)（ ） ，以确保整个场景或场景的部分，自动缩放以适应视口的新大小作为视图调整大小。不过请注意，从里面调用fitInView （ ）[resizeEvent](qgraphicsview.html#resizeEvent)（ ）可能会导致不必要的调整大小递归，如果新的变革切换滚动条的自动状态。您可以切换滚动条政策，以常开或常关闭，以防止这种情况（见[horizontalScrollBarPolicy](qabstractscrollarea.html#horizontalScrollBarPolicy-prop)（）和[verticalScrollBarPolicy](qabstractscrollarea.html#verticalScrollBarPolicy-prop)（））。

If _rect_是空的，或者如果视口太小，这个函数不会做任何事。

**See also** [setTransform](qgraphicsview.html#setTransform)（ ）[ensureVisible](qgraphicsview.html#ensureVisible)（）和[centerOn](qgraphicsview.html#centerOn)（ ） 。

```
QGraphicsView.fitInView (self, QGraphicsItem item, Qt.AspectRatioMode mode = Qt.IgnoreAspectRatio)
```

这是一个重载函数。

这个方便的功能等同于调用fitInView （[QRectF](qrectf.html)（_x_，_y_，_w_，_h_） ，_aspectRatioMode_） 。

**See also** [ensureVisible](qgraphicsview.html#ensureVisible)（）和[centerOn](qgraphicsview.html#centerOn)（ ） 。

```
QGraphicsView.fitInView (self, float x, float y, float w, float h, Qt.AspectRatioMode mode = Qt.IgnoreAspectRatio)
```

这是一个重载函数。

确保_item_紧密配合在视图内，根据缩放视图_aspectRatioMode_。

**See also** [ensureVisible](qgraphicsview.html#ensureVisible)（）和[centerOn](qgraphicsview.html#centerOn)（ ） 。

```
QGraphicsView.focusInEvent (self, QFocusEvent event)
```

从重新实现[QWidget.focusInEvent](qwidget.html#focusInEvent)（ ） 。

```
bool QGraphicsView.focusNextPrevChild (self, bool next)
```

从重新实现[QWidget.focusNextPrevChild](qwidget.html#focusNextPrevChild)（ ） 。

```
QGraphicsView.focusOutEvent (self, QFocusEvent event)
```

从重新实现[QWidget.focusOutEvent](qwidget.html#focusOutEvent)（ ） 。

```
QBrush QGraphicsView.foregroundBrush (self)
```

[

```
QGraphicsView.inputMethodEvent (self, QInputMethodEvent event)
```

](qbrush.html)

[从重新实现](qbrush.html)[QWidget.inputMethodEvent](qwidget.html#inputMethodEvent)（ ） 。

```
QVariant QGraphicsView.inputMethodQuery (self, Qt.InputMethodQuery query)
```

从重新实现[QWidget.inputMethodQuery](qwidget.html#inputMethodQuery)（ ） 。

```
QGraphicsView.invalidateScene (self, QRectF rect = QRectF(), QGraphicsScene.SceneLayers layers = QGraphicsScene.AllLayers)
```

这种方法也是一个Qt槽与C + +的签名`void invalidateScene(const QRectF& = QRectF(),QGraphicsScene::SceneLayers = QGraphicsScene.AllLayers)`。

废止及时间表重绘_layers_内_rect_。_rect_在场景坐标。对于任何缓存的内容_layers_内_rect_无条件失效并重新绘制。

你可以调用这个函数来通知[QGraphicsView](qgraphicsview.html)的改变，背景或场景的前景。它通常用于场景与基于区块的背景来通知改变时[QGraphicsView](qgraphicsview.html)启用了后台缓存。

需要注意的是[QGraphicsView](qgraphicsview.html)目前支持后台缓存只（见[QGraphicsView.CacheBackground](qgraphicsview.html#CacheModeFlag-enum)） 。此功能相当于调用[update](qwidget.html#update)（ ）如有层，但[QGraphicsScene.BackgroundLayer](qgraphicsscene.html#SceneLayer-enum)被传递。

**See also** [QGraphicsScene.invalidate](qgraphicsscene.html#invalidate)（）和[update](qwidget.html#update)（ ） 。

```
bool QGraphicsView.isInteractive (self)
```

```
bool QGraphicsView.isTransformed (self)
```

返回True如果视图被转换（即，非恒等变换已被分配，或滚动条进行调整） 。

此功能被引入Qt的4.6 。

**See also** [setTransform](qgraphicsview.html#setTransform)（ ）[horizontalScrollBar](qabstractscrollarea.html#horizontalScrollBar)（）和[verticalScrollBar](qabstractscrollarea.html#verticalScrollBar)（ ） 。

```
QGraphicsItem QGraphicsView.itemAt (self, QPoint pos)
```

[

返回在位置的项目_pos_，这是在视口坐标。如果有多个项目在这个位置，这个函数返回的最上方项目。

例如：

](qgraphicsitem.html)

```
 void CustomView.mousePressEvent(QMouseEvent *event)
 {
     if ([QGraphicsItem](qgraphicsitem.html) *item = itemAt(event->pos())) {
         qDebug() << "You clicked on item" << item;
     } else {
         qDebug() << "You didn't click on an item.";
     }
 }

```

**See also** [items](qgraphicsview.html#items)（）和[Sorting](qgraphicsitem.html#sorting)。

```
QGraphicsItem QGraphicsView.itemAt (self, int ax, int ay)
```

[

这是一个重载函数。

](qgraphicsitem.html)

[此功能提供了方便。这相当于调用itemAt （](qgraphicsitem.html)[QPoint](qpoint.html)（_x_，_y_））。

```
list-of-QGraphicsItem QGraphicsView.items (self)
```

返回相关联的场景中的所有项目，按降序堆叠顺序（即，在返回列表中的第一项是最上面的项目）的列表。

**See also** [QGraphicsScene.items](qgraphicsscene.html#items)（）和[Sorting](qgraphicsitem.html#sorting)。

```
list-of-QGraphicsItem QGraphicsView.items (self, QPoint pos)
```

返回所有项目的列表的位置_pos_在视图中。该项目按递减顺序堆叠（即，在列表中的第一个项目是最上面的项目，最后项目是最下面的项目） 。_pos_在视口中坐标。

这个功能是最常用的内鼠标事件处理程序调用子类中的[QGraphicsView](qgraphicsview.html)。_pos_在未转化的视口坐标，就像[QMouseEvent.pos](qmouseevent.html#pos)（ ） 。

```
 void CustomView.mousePressEvent([QMouseEvent](qmouseevent.html) *event)
 {
     qDebug() << "There are" << items(event->pos()).size()
              << "items at position" << mapToScene(event->pos());
 }

```

**See also** [QGraphicsScene.items](qgraphicsscene.html#items)（）和[Sorting](qgraphicsitem.html#sorting)。

```
list-of-QGraphicsItem QGraphicsView.items (self, int ax, int ay)
```

此功能提供了方便。这相当于调用项目（[QPoint](qpoint.html)（_x_，_y_））。

```
list-of-QGraphicsItem QGraphicsView.items (self, int x, int y, int w, int h, Qt.ItemSelectionMode mode = Qt.IntersectsItemShape)
```

这个方便的功能等同于调用项目（[QRectF](qrectf.html)（_x_，_y_，_w_，_h_） ，_mode_） 。

此功能被引入Qt的4.3 。

```
list-of-QGraphicsItem QGraphicsView.items (self, QRect rect, Qt.ItemSelectionMode mode = Qt.IntersectsItemShape)
```

这是一个重载函数。

返回所有的，取决于项目的列表_mode_，是由两种或包含与相交_rect_。_rect_在视口中坐标。

为默认值_mode_ is [Qt.IntersectsItemShape](qt.html#ItemSelectionMode-enum);所有项目的确切形状相交或包含由_rect_返回。

该项目按降序堆叠顺序（即，在返回列表中的第一项是最上面的项目） 。

**See also** [itemAt](qgraphicsview.html#itemAt)（ ）[items](qgraphicsview.html#items)（ ）[mapToScene](qgraphicsview.html#mapToScene)（）和[Sorting](qgraphicsitem.html#sorting)。

```
list-of-QGraphicsItem QGraphicsView.items (self, QPolygon polygon, Qt.ItemSelectionMode mode = Qt.IntersectsItemShape)
```

这是一个重载函数。

返回所有的，取决于项目的列表_mode_，是由两种或包含与相交_polygon_。_polygon_在视口中坐标。

为默认值_mode_ is [Qt.IntersectsItemShape](qt.html#ItemSelectionMode-enum);所有项目的确切形状相交或包含由_polygon_返回。

该项目是由递减堆栈顺序（即，在返回列表中的第一项是最上面的项目）进行分类。

**See also** [itemAt](qgraphicsview.html#itemAt)（ ）[items](qgraphicsview.html#items)（ ）[mapToScene](qgraphicsview.html#mapToScene)（）和[Sorting](qgraphicsitem.html#sorting)。

```
list-of-QGraphicsItem QGraphicsView.items (self, QPainterPath path, Qt.ItemSelectionMode mode = Qt.IntersectsItemShape)
```

这是一个重载函数。

返回所有的，取决于项目的列表_mode_，是由两种或包含与相交_path_。_path_在视口中坐标。

为默认值_mode_ is [Qt.IntersectsItemShape](qt.html#ItemSelectionMode-enum);所有项目的确切形状相交或包含由_path_返回。

**See also** [itemAt](qgraphicsview.html#itemAt)（ ）[items](qgraphicsview.html#items)（ ）[mapToScene](qgraphicsview.html#mapToScene)（）和[Sorting](qgraphicsitem.html#sorting)。

```
QGraphicsView.keyPressEvent (self, QKeyEvent event)
```

从重新实现[QWidget.keyPressEvent](qwidget.html#keyPressEvent)（ ） 。

```
QGraphicsView.keyReleaseEvent (self, QKeyEvent event)
```

从重新实现[QWidget.keyReleaseEvent](qwidget.html#keyReleaseEvent)（ ） 。

```
QPoint QGraphicsView.mapFromScene (self, QPointF point)
```

[

返回现场协调_point_视口坐标。

](qpoint.html)

[**See also**](qpoint.html) [mapToScene](qgraphicsview.html#mapToScene)（ ） 。

```
QPolygon QGraphicsView.mapFromScene (self, QRectF rect)
```

[

返回矩形现场_rect_一个视口坐标的多边形。

](qpolygon.html)

[**See also**](qpolygon.html) [mapToScene](qgraphicsview.html#mapToScene)（ ） 。

```
QPolygon QGraphicsView.mapFromScene (self, QPolygonF polygon)
```

[

返回现场多边形的坐标_polygon_一个视口坐标的多边形。

](qpolygon.html)

[**See also**](qpolygon.html) [mapToScene](qgraphicsview.html#mapToScene)（ ） 。

```
QPainterPath QGraphicsView.mapFromScene (self, QPainterPath path)
```

[

返回现场协调画家路径_path_一个视口坐标画家路径。

](qpainterpath.html)

[**See also**](qpainterpath.html) [mapToScene](qgraphicsview.html#mapToScene)（ ） 。

```
QPoint QGraphicsView.mapFromScene (self, float ax, float ay)
```

[](qpoint.html)

[此功能提供了方便。这相当于调用mapFromScene （](qpoint.html)[QPointF](qpointf.html)（_x_，_y_））。

```
QPolygon QGraphicsView.mapFromScene (self, float ax, float ay, float w, float h)
```

[](qpolygon.html)

[此功能提供了方便。这相当于调用mapFromScene （](qpolygon.html)[QRectF](qrectf.html)（_x_，_y_，_w_，_h_））。

```
QPointF QGraphicsView.mapToScene (self, QPoint point)
```

[

返回视口坐标_point_映射到场景坐标。

](qpointf.html)

[注意：它可以是有用的映射所复盖的像素在整个矩形_point_代替点本身。要做到这一点，你可以调用mapToScene （](qpointf.html)[QRect](qrect.html)（_point_，[QSize](qsize.html)（ 2，2） ））。

**See also** [mapFromScene](qgraphicsview.html#mapFromScene)（ ） 。

```
QPolygonF QGraphicsView.mapToScene (self, QRect rect)
```

[

返回视口矩形_rect_映射到一个场景坐标的多边形。

](qpolygonf.html)

[**See also**](qpolygonf.html) [mapFromScene](qgraphicsview.html#mapFromScene)（ ） 。

```
QPolygonF QGraphicsView.mapToScene (self, QPolygon polygon)
```

[

返回多边形视口_polygon_映射到一个场景坐标的多边形。

](qpolygonf.html)

[**See also**](qpolygonf.html) [mapFromScene](qgraphicsview.html#mapFromScene)（ ） 。

```
QPainterPath QGraphicsView.mapToScene (self, QPainterPath path)
```

[

返回视口画家路径_path_映射到一个场景的坐标画家路径。

](qpainterpath.html)

[**See also**](qpainterpath.html) [mapFromScene](qgraphicsview.html#mapFromScene)（ ） 。

```
QPointF QGraphicsView.mapToScene (self, int ax, int ay)
```

[](qpointf.html)

[此功能提供了方便。这相当于调用mapToScene （](qpointf.html)[QPoint](qpoint.html)（_x_，_y_））。

```
QPolygonF QGraphicsView.mapToScene (self, int ax, int ay, int w, int h)
```

[](qpolygonf.html)

[此功能提供了方便。这相当于调用mapToScene （](qpolygonf.html)[QRect](qrect.html)（_x_，_y_，_w_，_h_））。

```
QMatrix QGraphicsView.matrix (self)
```

[

返回该视图的当前转换矩阵。如果没有当前变换设置，返回单位矩阵。

](qmatrix.html)

[**See also**](qmatrix.html) [setMatrix](qgraphicsview.html#setMatrix)（ ）[transform](qgraphicsview.html#transform)（ ）[rotate](qgraphicsview.html#rotate)（ ）[scale](qgraphicsview.html#scale)（ ）[shear](qgraphicsview.html#shear)（）和[translate](qgraphicsview.html#translate)（ ） 。

```
QGraphicsView.mouseDoubleClickEvent (self, QMouseEvent event)
```

从重新实现[QWidget.mouseDoubleClickEvent](qwidget.html#mouseDoubleClickEvent)（ ） 。

```
QGraphicsView.mouseMoveEvent (self, QMouseEvent event)
```

从重新实现[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

```
QGraphicsView.mousePressEvent (self, QMouseEvent event)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

```
QGraphicsView.mouseReleaseEvent (self, QMouseEvent event)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

```
OptimizationFlags QGraphicsView.optimizationFlags (self)
```

[

```
QGraphicsView.paintEvent (self, QPaintEvent event)
```

](index.htm)

[从重新实现](index.htm)[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QGraphicsView.render (self, QPainter painter, QRectF target = QRectF(), QRect source = QRect(), Qt.AspectRatioMode mode = Qt.KeepAspectRatio)
```

呈现_source_矩形，这是在视图坐标，从场景到_target_，这是在绘制设备坐标，使用_painter_。此功能可用于捕获视图的内容到一个绘图设备，如一个有用的[QImage](qimage.html)（例如，采取截图） ，或用于印刷[QPrinter](qprinter.html)。例如：

```
 [QGraphicsScene](qgraphicsscene.html) scene;
 scene.addItem(...
 ...

 [QGraphicsView](qgraphicsview.html) view(&scene);
 view.show();
 ...

 [QPrinter](qprinter.html) printer([QPrinter](qprinter.html).HighResolution);
 printer.setPageSize([QPrinter](qprinter.html).A4);
 [QPainter](qpainter.html) painter(&printer);

 // print, fitting the viewport contents into a full page
 view.render(&painter);

 // print the upper half of the viewport into the lower.
 // half of the page.
 [QRect](qrect.html) viewport = view.viewport()->rect();
 view.render(&painter,
             [QRectF](qrectf.html)(0, printer.height() / 2,
                    printer.width(), printer.height() / 2),
             viewport.adjusted(0, 0, 0, -viewport.height() / 2));

```

If _source_是一个空矩形，该函数将使用[viewport](qabstractscrollarea.html#viewport)（） - \u003e[rect](qwidget.html#rect-prop)（）来确定要画什么。如果_target_是一个空矩形，的全尺寸_painter_的涂料设备（例如，对于一个[QPrinter](qprinter.html)，页大小）将被使用。

矩形内容源将根据待转化_aspectRatioMode_以适应目标矩形。默认情况下，纵横比蒙了，_source_缩放以适合_target_。

**See also** [QGraphicsScene.render](qgraphicsscene.html#render)（ ） 。

```
QPainter.RenderHints QGraphicsView.renderHints (self)
```

[

```
QGraphicsView.resetCachedContent (self)
```

](index.htm)

[重置任何缓存内容。调用此函数将清除](index.htm)[QGraphicsView](qgraphicsview.html)的缓存。如果当前缓存模式[CacheNone](qgraphicsview.html#CacheModeFlag-enum)，这个函数不执行任何操作。

此功能自动为您调用的时候，[backgroundBrush](qgraphicsview.html#backgroundBrush-prop) or [QGraphicsScene.backgroundBrush](qgraphicsscene.html#backgroundBrush-prop)性质发生变化，你只需要调用这个函数，如果你已经重新实现[QGraphicsScene.drawBackground](qgraphicsscene.html#drawBackground)（）或[QGraphicsView.drawBackground](qgraphicsview.html#drawBackground)（）来绘制一个自定义背景，以及需要触发一个完全重绘。

**See also** [cacheMode](qgraphicsview.html#cacheMode-prop)（ ） 。

```
QGraphicsView.resetMatrix (self)
```

重置视图变换矩阵为单位矩阵。

**See also** [resetTransform](qgraphicsview.html#resetTransform)（ ） 。

```
QGraphicsView.resetTransform (self)
```

重置视图转换为单位矩阵。

**See also** [transform](qgraphicsview.html#transform)（）和[setTransform](qgraphicsview.html#setTransform)（ ） 。

```
ViewportAnchor QGraphicsView.resizeAnchor (self)
```

[

```
QGraphicsView.resizeEvent (self, QResizeEvent event)
```

](qgraphicsview.html#ViewportAnchor-enum)

[从重新实现](qgraphicsview.html#ViewportAnchor-enum)[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
QGraphicsView.rotate (self, float angle)
```

旋转当前视图转换_angle_度顺时针旋转。

**See also** [setTransform](qgraphicsview.html#setTransform)（ ）[transform](qgraphicsview.html#transform)（ ）[scale](qgraphicsview.html#scale)（ ）[shear](qgraphicsview.html#shear)（）和[translate](qgraphicsview.html#translate)（ ） 。

```
Qt.ItemSelectionMode QGraphicsView.rubberBandSelectionMode (self)
```

[

```
QGraphicsView.scale (self, float sx, float sy)
```

由（缩放当前视图转换_sx_，_sy_） 。

](qt.html#ItemSelectionMode-enum)

[**See also**](qt.html#ItemSelectionMode-enum) [setTransform](qgraphicsview.html#setTransform)（ ）[transform](qgraphicsview.html#transform)（ ）[rotate](qgraphicsview.html#rotate)（ ）[shear](qgraphicsview.html#shear)（）和[translate](qgraphicsview.html#translate)（ ） 。

```
QGraphicsScene QGraphicsView.scene (self)
```

[

返回一个指针，在视图中当前可视化的场景。如果没有现场正在显现，则返回0 。

](qgraphicsscene.html)

[**See also**](qgraphicsscene.html) [setScene](qgraphicsview.html#setScene)().

```
QRectF QGraphicsView.sceneRect (self)
```

[

```
QGraphicsView.scrollContentsBy (self, int dx, int dy)
```

](qrectf.html)

[从重新实现](qrectf.html)[QAbstractScrollArea.scrollContentsBy](qabstractscrollarea.html#scrollContentsBy)（ ） 。

```
QGraphicsView.setAlignment (self, Qt.Alignment alignment)
```

```
QGraphicsView.setBackgroundBrush (self, QBrush brush)
```

```
QGraphicsView.setCacheMode (self, CacheMode mode)
```

```
QGraphicsView.setDragMode (self, DragMode mode)
```

```
QGraphicsView.setForegroundBrush (self, QBrush brush)
```

```
QGraphicsView.setInteractive (self, bool allowed)
```

```
QGraphicsView.setMatrix (self, QMatrix matrix, bool combine = False)
```

设置视图的当前转换矩阵_matrix_。

If _combine_是真的，那么_matrix_是结合当前矩阵，否则_matrix_ _replaces_当前矩阵。_combine_默认为False 。

变换矩阵tranforms现场成视图坐标。使用默认的转变，由单位矩阵提供，在视图中一个像素代表一个单位中的场景（例如，一个10×10的矩形项目使用视图10X10像素绘制） 。如果一个2x2矩阵缩放应用，该场景将在1:2绘制（例如，一个10×10的矩形产品，然后使用视图20×20像素绘制） 。

例如：

```
 [QGraphicsScene](qgraphicsscene.html) scene;
 scene.addText("GraphicsView rotated clockwise");

 [QGraphicsView](qgraphicsview.html) view(&scene);
 view.rotate(90); // the text is rendered with a 90 degree clockwise rotation
 view.show();

```

为了简化互为作用与使用转换视图中的项目，[QGraphicsView](qgraphicsview.html)提供mapTo ...和mapFrom ...功能，可以现场和视图坐标之间的转换。例如，你可以调用[mapToScene](qgraphicsview.html#mapToScene)（ ）映射视图坐标为浮点场景坐标，或[mapFromScene](qgraphicsview.html#mapFromScene)（）从浮点数的场景地图坐标，查看坐标。

**See also** [matrix](qgraphicsview.html#matrix)（ ）[setTransform](qgraphicsview.html#setTransform)（ ）[rotate](qgraphicsview.html#rotate)（ ）[scale](qgraphicsview.html#scale)（ ）[shear](qgraphicsview.html#shear)（）和[translate](qgraphicsview.html#translate)（ ） 。

```
QGraphicsView.setOptimizationFlag (self, OptimizationFlag flag, bool enabled = True)
```

Enables _flag_如果_enabled_为True，否则禁用_flag_。

**See also** [optimizationFlags](qgraphicsview.html#optimizationFlags-prop)。

```
QGraphicsView.setOptimizationFlags (self, OptimizationFlags flags)
```

```
QGraphicsView.setRenderHint (self, QPainter.RenderHint hint, bool on = True)
```

If _enabled_是真的，渲染提示_hint_被启用，否则它被禁用。

**See also** [renderHints](qgraphicsview.html#renderHints-prop)。

```
QGraphicsView.setRenderHints (self, QPainter.RenderHints hints)
```

```
QGraphicsView.setResizeAnchor (self, ViewportAnchor anchor)
```

```
QGraphicsView.setRubberBandSelectionMode (self, Qt.ItemSelectionMode mode)
```

```
QGraphicsView.setScene (self, QGraphicsScene scene)
```

设置当前场景_scene_。如果_scene_正在被查看，该函数不起作用。

当一个场景设置在一个视图中，[QGraphicsScene.changed](qgraphicsscene.html#changed)（ ）信号会自动连接到这个视图的[updateScene](qgraphicsview.html#updateScene)（ ）插槽，以及视图的滚动条进行调整，以适应现场的大小。

**See also** [scene](qgraphicsview.html#scene)（ ） 。

```
QGraphicsView.setSceneRect (self, QRectF rect)
```

```
QGraphicsView.setSceneRect (self, float ax, float ay, float aw, float ah)
```

```
QGraphicsView.setTransform (self, QTransform matrix, bool combine = False)
```

设置视图的当前转换矩阵_matrix_。

If _combine_是真的，那么_matrix_是结合当前矩阵，否则_matrix_ _replaces_当前矩阵。_combine_默认为False 。

变换矩阵tranforms现场成视图坐标。使用默认的转变，由单位矩阵提供，在视图中一个像素代表一个单位中的场景（例如，一个10×10的矩形项目使用视图10X10像素绘制） 。如果一个2x2矩阵缩放应用，该场景将在1:2绘制（例如，一个10×10的矩形产品，然后使用视图20×20像素绘制） 。

例如：

```
 [QGraphicsScene](qgraphicsscene.html) scene;
 scene.addText("GraphicsView rotated clockwise");

 [QGraphicsView](qgraphicsview.html) view(&scene);
 view.rotate(90); // the text is rendered with a 90 degree clockwise rotation
 view.show();

```

为了简化互为作用与使用转换视图中的项目，[QGraphicsView](qgraphicsview.html)提供mapTo ...和mapFrom ...功能，可以现场和视图坐标之间的转换。例如，你可以调用[mapToScene](qgraphicsview.html#mapToScene)（ ）到一个视图coordiate映射到一个浮点场景坐标，或[mapFromScene](qgraphicsview.html#mapFromScene)（）从浮点数的场景地图坐标，查看坐标。

**See also** [transform](qgraphicsview.html#transform)（ ）[rotate](qgraphicsview.html#rotate)（ ）[scale](qgraphicsview.html#scale)（ ）[shear](qgraphicsview.html#shear)（）和[translate](qgraphicsview.html#translate)（ ） 。

```
QGraphicsView.setTransformationAnchor (self, ViewportAnchor anchor)
```

```
QGraphicsView.setupViewport (self, QWidget widget)
```

这种方法也是一个Qt槽与C + +的签名`void setupViewport(QWidget *)`。

这个槽被调用者[QAbstractScrollArea](qabstractscrollarea.html)后[setViewport](qabstractscrollarea.html#setViewport)（ ）被调用。在子类重新实现此功能[QGraphicsView](qgraphicsview.html)初始化新视_widget_之前就被采用。

**See also** [setViewport](qabstractscrollarea.html#setViewport)（ ） 。

```
QGraphicsView.setViewportUpdateMode (self, ViewportUpdateMode mode)
```

```
QGraphicsView.shear (self, float sh, float sv)
```

由（剪当前视图转型_sh_，_sv_） 。

**See also** [setTransform](qgraphicsview.html#setTransform)（ ）[transform](qgraphicsview.html#transform)（ ）[rotate](qgraphicsview.html#rotate)（ ）[scale](qgraphicsview.html#scale)（）和[translate](qgraphicsview.html#translate)（ ） 。

```
QGraphicsView.showEvent (self, QShowEvent event)
```

从重新实现[QWidget.showEvent](qwidget.html#showEvent)（ ） 。

```
QSize QGraphicsView.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

```
QTransform QGraphicsView.transform (self)
```

[

返回该视图的当前转换矩阵。如果没有当前变换设置，返回单位矩阵。

](qtransform.html)

[**See also**](qtransform.html) [setTransform](qgraphicsview.html#setTransform)（ ）[rotate](qgraphicsview.html#rotate)（ ）[scale](qgraphicsview.html#scale)（ ）[shear](qgraphicsview.html#shear)（）和[translate](qgraphicsview.html#translate)（ ） 。

```
ViewportAnchor QGraphicsView.transformationAnchor (self)
```

[

```
QGraphicsView.translate (self, float dx, float dy)
```

由（平移当前视图转型_dx_，_dy_） 。

](qgraphicsview.html#ViewportAnchor-enum)

[**See also**](qgraphicsview.html#ViewportAnchor-enum) [setTransform](qgraphicsview.html#setTransform)（ ）[transform](qgraphicsview.html#transform)（ ）[rotate](qgraphicsview.html#rotate)（）和[shear](qgraphicsview.html#shear)（ ） 。

```
QGraphicsView.updateScene (self, list-of-QRectF rects)
```

这种方法也是一个Qt槽与C + +的签名`void updateScene(const QList&lt;QRectF&gt;&)`。

附表现场矩形的更新_rects_。

**See also** [QGraphicsScene.changed](qgraphicsscene.html#changed)（ ） 。

```
QGraphicsView.updateSceneRect (self, QRectF rect)
```

这种方法也是一个Qt槽与C + +的签名`void updateSceneRect(const QRectF&)`。

通知[QGraphicsView](qgraphicsview.html)该场景的场景RECT发生了变化。_rect_是新的场景正确。如果视图已经有一个明确设定的场景矩形，该函数不起作用。

**See also** [sceneRect](qgraphicsview.html#sceneRect-prop)和[QGraphicsScene.sceneRectChanged](qgraphicsscene.html#sceneRectChanged)（ ） 。

```
bool QGraphicsView.viewportEvent (self, QEvent event)
```

从重新实现[QAbstractScrollArea.viewportEvent](qabstractscrollarea.html#viewportEvent)（ ） 。

```
QTransform QGraphicsView.viewportTransform (self)
```

[

返回映射视口坐标场景坐标的矩阵。

](qtransform.html)

[**See also**](qtransform.html) [mapToScene](qgraphicsview.html#mapToScene)（）和[mapFromScene](qgraphicsview.html#mapFromScene)（ ） 。

```
ViewportUpdateMode QGraphicsView.viewportUpdateMode (self)
```

[

```
QGraphicsView.wheelEvent (self, QWheelEvent event)
```

](qgraphicsview.html#ViewportUpdateMode-enum)

[从重新实现](qgraphicsview.html#ViewportUpdateMode-enum)[QWidget.wheelEvent](qwidget.html#wheelEvent)（ ） 。