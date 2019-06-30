# QListView Class Reference

## [[QtGui](index.htm) module]

的而QListView类提供了一个列表或图标视图到模型。[More...](#details)

继承[QAbstractItemView](qabstractitemview.html)。

通过继承[QHelpIndexWidget](qhelpindexwidget.html)，[QListWidget](qlistwidget.html)和[QUndoView](qundoview.html)。

### Types

*   `enum Flow { LeftToRight, TopToBottom }`
*   `enum LayoutMode { SinglePass, Batched }`
*   `enum Movement { Static, Free, Snap }`
*   `enum ResizeMode { Fixed, Adjust }`
*   `enum ViewMode { ListMode, IconMode }`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `int batchSize (self)`
*   `clearPropertyFlags (self)`
*   `currentChanged (self, QModelIndex current, QModelIndex previous)`
*   `dataChanged (self, QModelIndex topLeft, QModelIndex bottomRight)`
*   `dragLeaveEvent (self, QDragLeaveEvent e)`
*   `dragMoveEvent (self, QDragMoveEvent e)`
*   `dropEvent (self, QDropEvent e)`
*   `bool event (self, QEvent e)`
*   `Flow flow (self)`
*   `QSize gridSize (self)`
*   `int horizontalOffset (self)`
*   `QModelIndex indexAt (self, QPoint p)`
*   `bool isIndexHidden (self, QModelIndex index)`
*   `bool isRowHidden (self, int row)`
*   `bool isSelectionRectVisible (self)`
*   `bool isWrapping (self)`
*   `LayoutMode layoutMode (self)`
*   `int modelColumn (self)`
*   `mouseMoveEvent (self, QMouseEvent e)`
*   `mouseReleaseEvent (self, QMouseEvent e)`
*   `QModelIndex moveCursor (self, QAbstractItemView.CursorAction cursorAction, Qt.KeyboardModifiers modifiers)`
*   `Movement movement (self)`
*   `paintEvent (self, QPaintEvent e)`
*   `QRect rectForIndex (self, QModelIndex index)`
*   `reset (self)`
*   `resizeEvent (self, QResizeEvent e)`
*   `ResizeMode resizeMode (self)`
*   `rowsAboutToBeRemoved (self, QModelIndex parent, int start, int end)`
*   `rowsInserted (self, QModelIndex parent, int start, int end)`
*   `scrollContentsBy (self, int dx, int dy)`
*   `scrollTo (self, QModelIndex index, QAbstractItemView.ScrollHint hint = QAbstractItemView.EnsureVisible)`
*   `list-of-QModelIndex selectedIndexes (self)`
*   `selectionChanged (self, QItemSelection selected, QItemSelection deselected)`
*   `setBatchSize (self, int batchSize)`
*   `setFlow (self, Flow flow)`
*   `setGridSize (self, QSize size)`
*   `setLayoutMode (self, LayoutMode mode)`
*   `setModelColumn (self, int column)`
*   `setMovement (self, Movement movement)`
*   `setPositionForIndex (self, QPoint position, QModelIndex index)`
*   `setResizeMode (self, ResizeMode mode)`
*   `setRootIndex (self, QModelIndex index)`
*   `setRowHidden (self, int row, bool hide)`
*   `setSelection (self, QRect rect, QItemSelectionModel.SelectionFlags command)`
*   `setSelectionRectVisible (self, bool show)`
*   `setSpacing (self, int space)`
*   `setUniformItemSizes (self, bool enable)`
*   `setViewMode (self, ViewMode mode)`
*   `setWordWrap (self, bool on)`
*   `setWrapping (self, bool enable)`
*   `int spacing (self)`
*   `startDrag (self, Qt.DropActions supportedActions)`
*   `timerEvent (self, QTimerEvent e)`
*   `bool uniformItemSizes (self)`
*   `updateGeometries (self)`
*   `int verticalOffset (self)`
*   `ViewMode viewMode (self)`
*   `QStyleOptionViewItem viewOptions (self)`
*   `QRect visualRect (self, QModelIndex index)`
*   `QRegion visualRegionForSelection (self, QItemSelection selection)`
*   `bool wordWrap (self)`

### Qt Signals

*   `void indexesMoved (const QModelIndexList&)`

* * *

## Detailed Description

的而QListView类提供了一个列表或图标视图到模型。

一而QListView呈现存储在一个模型中的项目，无论是作为一个简单的非层次结构列表，或作为图标的集合。这个类是用来提供以前由提供的列表和图标视图`QListBox`和`QIconView`类，但通过使用Qt的模型/视图结构中提供的更灵活的方法。

的而QListView类中的一个[Model/View Classes](index.htm)并且是Qt的一部分[model/view framework](index.htm)。

这种观点不显示水平或垂直头，显示项目列表与水平头，使用[QTreeView](qtreeview.html)代替。

而QListView实现由定义的接口[QAbstractItemView](qabstractitemview.html)类以允许其显示由从派生模型提供数据[QAbstractItemModel](qabstractitemmodel.html)类。

在：在列表视图中的项目，可以使用两种视图模式之一显示[ListMode](qlistview.html#ViewMode-enum)，该项目显示在一个简单的列表形式，在[IconMode](qlistview.html#ViewMode-enum)，列表视图采用的形式_icon view_在该项目在文件管理器中显示包含的文件图标。默认情况下，列表视图中[ListMode](qlistview.html#ViewMode-enum)。要更改视图模式下，使用[setViewMode](qlistview.html#viewMode-prop)（ ）函数，并确定当前视图模式下，使用[viewMode](qlistview.html#viewMode-prop)（ ） 。

在这些视图项目，由指定的方向布局[flow](qlistview.html#flow-prop)列表视图的（ ） 。该条目可以被固定在适当位置，或者可以移动，这取决于视图的[movement](qlistview.html#movement-prop)（ ）状态。

如果在模型中的项，不能完全在流动方向上布置，它们可以在视图窗口部件的边界被包裹，这取决于[isWrapping](qlistview.html#isWrapping-prop)（ ） 。当项目正由一个图标视图中表示此属性很有用。

该[resizeMode](qlistview.html#resizeMode-prop)（）和[layoutMode](qlistview.html#layoutMode-prop)（ ）治理项目的布局方式和时间。项目按他们的间隔[spacing](qlistview.html#spacing-prop)（） ，并能大小的由指定的名义网格内的存在[gridSize](qlistview.html#gridSize-prop)（ ） 。本项目可以根据被渲染为或大或小的图标[iconSize](qabstractitemview.html#iconSize-prop)（ ） 。

| ![Screenshot of a Windows XP style list view](../img/windowsxp-listview.png) | ![Screenshot of a Macintosh style table view](../img/macintosh-listview.png) | ![Screenshot of a Plastique style table view](../img/plastique-listview.png) |
| A [Windows XP style](index.htm) list view. | A [Macintosh style](index.htm) list view. | A [Plastique style](index.htm) list view. |

### Improving Performance

它可以给出关于它正在处理，以便显示大量项目时，以改善其性能的数据的视图的提示。可以采取一种方法对于旨在与相等尺寸的显示项目的观点是设置[uniformItemSizes](qlistview.html#uniformItemSizes-prop)属性设置为True 。

* * *

## Type Documentation

```
QListView.Flow
```

| Constant | Value | Description |
| --- | --- | --- |
| `QListView.LeftToRight` | `0` | 该项目奠定了在视图中从左边到右边。 |
| `QListView.TopToBottom` | `1` | 该项目的布局视图从顶部至底部。 |

```
QListView.LayoutMode
```

| Constant | Value | Description |
| --- | --- | --- |
| `QListView.SinglePass` | `0` | 该项目奠定了一下子。 |
| `QListView.Batched` | `1` | 该项目在分批布局[batchSize](qlistview.html#batchSize-prop)项目。 |

**See also** [batchSize](qlistview.html#batchSize-prop)。

```
QListView.Movement
```

| Constant | Value | Description |
| --- | --- | --- |
| `QListView.Static` | `0` | 该项目不能被用户移动。 |
| `QListView.Free` | `1` | 该项目可以由用户自由移动。 |
| `QListView.Snap` | `2` | 该项目捕捉到移动时指定的网格;见[setGridSize](qlistview.html#gridSize-prop)（ ） 。 |

```
QListView.ResizeMode
```

| Constant | Value | Description |
| --- | --- | --- |
| `QListView.Fixed` | `0` | 该项目将只在第一次的视图显示进行布局。 |
| `QListView.Adjust` | `1` | 该项目将在每次视图调整大小时布局。 |

```
QListView.ViewMode
```

| Constant | Value | Description |
| --- | --- | --- |
| `QListView.ListMode` | `0` | 该项目的布局使用[TopToBottom](qlistview.html#Flow-enum)流，具有体积小，静态运动 |
| `QListView.IconMode` | `1` | 该项目的布局使用[LeftToRight](qlistview.html#Flow-enum)流，具有大尺寸和自由流动 |

* * *

## Method Documentation

```
QListView.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建一个新的[QListView](qlistview.html)用给定的_parent_查看模型。使用[setModel](qabstractitemview.html#setModel)（）来设定模型。

```
int QListView.batchSize (self)
```

```
QListView.clearPropertyFlags (self)
```

清除[QListView](qlistview.html)特定的属性标志。看[viewMode](qlistview.html#viewMode-prop)。

属性继承自[QAbstractItemView](qabstractitemview.html)不包括由酒店的标志。具体来说，[dragEnabled](qabstractitemview.html#dragEnabled-prop)和[acceptsDrops](qwidget.html#acceptDrops-prop)通过计算[QListView](qlistview.html)当调用[setMovement](qlistview.html#movement-prop)（）或[setViewMode](qlistview.html#viewMode-prop)（ ） 。

```
QListView.currentChanged (self, QModelIndex current, QModelIndex previous)
```

从重新实现[QAbstractItemView.currentChanged](qabstractitemview.html#currentChanged)（ ） 。

```
QListView.dataChanged (self, QModelIndex topLeft, QModelIndex bottomRight)
```

从重新实现[QAbstractItemView.dataChanged](qabstractitemview.html#dataChanged)（ ） 。

```
QListView.dragLeaveEvent (self, QDragLeaveEvent e)
```

从重新实现[QWidget.dragLeaveEvent](qwidget.html#dragLeaveEvent)（ ） 。

```
QListView.dragMoveEvent (self, QDragMoveEvent e)
```

从重新实现[QWidget.dragMoveEvent](qwidget.html#dragMoveEvent)（ ） 。

```
QListView.dropEvent (self, QDropEvent e)
```

从重新实现[QWidget.dropEvent](qwidget.html#dropEvent)（ ） 。

```
bool QListView.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
Flow QListView.flow (self)
```

[](qlistview.html#Flow-enum)

```
QSize QListView.gridSize (self)
```

[

```
int QListView.horizontalOffset (self)
```

](qsize.html)

[从重新实现](qsize.html)[QAbstractItemView.horizontalOffset](qabstractitemview.html#horizontalOffset)（ ） 。

```
QModelIndex QListView.indexAt (self, QPoint p)
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemView.indexAt](qabstractitemview.html#indexAt)（ ） 。

```
bool QListView.isIndexHidden (self, QModelIndex index)
```

从重新实现[QAbstractItemView.isIndexHidden](qabstractitemview.html#isIndexHidden)（ ） 。

```
bool QListView.isRowHidden (self, int row)
```

返回True如果_row_被隐藏，否则返回False 。

```
bool QListView.isSelectionRectVisible (self)
```

```
bool QListView.isWrapping (self)
```

```
LayoutMode QListView.layoutMode (self)
```

[

```
int QListView.modelColumn (self)
```

```
QListView.mouseMoveEvent (self, QMouseEvent e)
```

](qlistview.html#LayoutMode-enum)

[从重新实现](qlistview.html#LayoutMode-enum)[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

```
QListView.mouseReleaseEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

```
QModelIndex QListView.moveCursor (self, QAbstractItemView.CursorAction cursorAction, Qt.KeyboardModifiers modifiers)
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemView.moveCursor](qabstractitemview.html#moveCursor)（ ） 。

```
Movement QListView.movement (self)
```

[

```
QListView.paintEvent (self, QPaintEvent e)
```

](qlistview.html#Movement-enum)

[从重新实现](qlistview.html#Movement-enum)[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QRect QListView.rectForIndex (self, QModelIndex index)
```

[

返回该项目的位置的矩形_index_在模型中。矩形是在内容坐标。

](qrect.html)

[**See also**](qrect.html) [visualRect](qlistview.html#visualRect)（ ） 。

```
QListView.reset (self)
```

```
QListView.resizeEvent (self, QResizeEvent e)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
ResizeMode QListView.resizeMode (self)
```

[

```
QListView.rowsAboutToBeRemoved (self, QModelIndex parent, int start, int end)
```

](qlistview.html#ResizeMode-enum)

[从重新实现](qlistview.html#ResizeMode-enum)[QAbstractItemView.rowsAboutToBeRemoved](qabstractitemview.html#rowsAboutToBeRemoved)（ ） 。

```
QListView.rowsInserted (self, QModelIndex parent, int start, int end)
```

从重新实现[QAbstractItemView.rowsInserted](qabstractitemview.html#rowsInserted)（ ） 。

```
QListView.scrollContentsBy (self, int dx, int dy)
```

```
QListView.scrollTo (self, QModelIndex index, QAbstractItemView.ScrollHint hint = QAbstractItemView.EnsureVisible)
```

从重新实现[QAbstractItemView.scrollTo](qabstractitemview.html#scrollTo)（ ） 。

```
list-of-QModelIndex QListView.selectedIndexes (self)
```

从重新实现[QAbstractItemView.selectedIndexes](qabstractitemview.html#selectedIndexes)（ ） 。

```
QListView.selectionChanged (self, QItemSelection selected, QItemSelection deselected)
```

从重新实现[QAbstractItemView.selectionChanged](qabstractitemview.html#selectionChanged)（ ） 。

```
QListView.setBatchSize (self, int batchSize)
```

```
QListView.setFlow (self, Flow flow)
```

```
QListView.setGridSize (self, QSize size)
```

```
QListView.setLayoutMode (self, LayoutMode mode)
```

```
QListView.setModelColumn (self, int column)
```

```
QListView.setMovement (self, Movement movement)
```

```
QListView.setPositionForIndex (self, QPoint position, QModelIndex index)
```

设置在该项目中的内容位置_index_在模型中，以给定的_position_。如果列表视图的运动模式是静态的还是它的视图模式是[ListView](index.htm)，此功能不会有任何效果。

这个函数是Qt 4.1中引入。

```
QListView.setResizeMode (self, ResizeMode mode)
```

```
QListView.setRootIndex (self, QModelIndex index)
```

```
QListView.setRowHidden (self, int row, bool hide)
```

If _hide_诚然，在给定_row_将被隐藏，否则_row_将显示。

**See also** [isRowHidden](qlistview.html#isRowHidden)（ ） 。

```
QListView.setSelection (self, QRect rect, QItemSelectionModel.SelectionFlags command)
```

从重新实现[QAbstractItemView.setSelection](qabstractitemview.html#setSelection)（ ） 。

```
QListView.setSelectionRectVisible (self, bool show)
```

```
QListView.setSpacing (self, int space)
```

```
QListView.setUniformItemSizes (self, bool enable)
```

```
QListView.setViewMode (self, ViewMode mode)
```

```
QListView.setWordWrap (self, bool on)
```

```
QListView.setWrapping (self, bool enable)
```

```
int QListView.spacing (self)
```

```
QListView.startDrag (self, Qt.DropActions supportedActions)
```

从重新实现[QAbstractItemView.startDrag](qabstractitemview.html#startDrag)（ ） 。

```
QListView.timerEvent (self, QTimerEvent e)
```

从重新实现[QObject.timerEvent](qobject.html#timerEvent)（ ） 。

```
bool QListView.uniformItemSizes (self)
```

```
QListView.updateGeometries (self)
```

从重新实现[QAbstractItemView.updateGeometries](qabstractitemview.html#updateGeometries)（ ） 。

```
int QListView.verticalOffset (self)
```

从重新实现[QAbstractItemView.verticalOffset](qabstractitemview.html#verticalOffset)（ ） 。

```
ViewMode QListView.viewMode (self)
```

[](qlistview.html#ViewMode-enum)

```
QStyleOptionViewItem QListView.viewOptions (self)
```

[](qstyleoptionviewitem.html)

[从重新实现](qstyleoptionviewitem.html)[QAbstractItemView.viewOptions](qabstractitemview.html#viewOptions)（ ） 。

```
QRect QListView.visualRect (self, QModelIndex index)
```

[](qrect.html)

[从重新实现](qrect.html)[QAbstractItemView.visualRect](qabstractitemview.html#visualRect)（ ） 。

```
QRegion QListView.visualRegionForSelection (self, QItemSelection selection)
```

[](qregion.html)

[从重新实现](qregion.html)[QAbstractItemView.visualRegionForSelection](qabstractitemview.html#visualRegionForSelection)（ ） 。

由于4.7 ，返回的区域仅包含矩形相交（或计入）的视口。

```
bool QListView.wordWrap (self)
```

* * *

## Qt Signal Documentation

```
void indexesMoved (const QModelIndexList&)
```

这是该信号的默认超载。

指定时，这个信号被发射_indexes_移动在视图中。

这个函数中引入了Qt 4.2中。