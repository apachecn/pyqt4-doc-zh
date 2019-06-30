# QAbstractItemView Class Reference

## [[QtGui](index.htm) module]

该QAbstractItemView类为项目视图类的基本功能。[More...](#details)

继承[QAbstractScrollArea](qabstractscrollarea.html)。

通过继承[QColumnView](qcolumnview.html)，[QHeaderView](qheaderview.html)，[QListView](qlistview.html)，[QTableView](qtableview.html)和[QTreeView](qtreeview.html)。

### Types

*   `enum CursorAction { MoveUp, MoveDown, MoveLeft, MoveRight, ..., MovePrevious }`
*   `enum DragDropMode { NoDragDrop, DragOnly, DropOnly, DragDrop, InternalMove }`
*   `enum DropIndicatorPosition { OnItem, AboveItem, BelowItem, OnViewport }`
*   `enum EditTrigger { NoEditTriggers, CurrentChanged, DoubleClicked, SelectedClicked, ..., AllEditTriggers }`
*   `class **[EditTriggers](index.htm)**`
*   `enum ScrollHint { EnsureVisible, PositionAtTop, PositionAtBottom, PositionAtCenter }`
*   `enum ScrollMode { ScrollPerItem, ScrollPerPixel }`
*   `enum SelectionBehavior { SelectItems, SelectRows, SelectColumns }`
*   `enum SelectionMode { NoSelection, SingleSelection, MultiSelection, ExtendedSelection, ContiguousSelection }`
*   `enum State { NoState, DraggingState, DragSelectingState, EditingState, ..., AnimatingState }`

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `bool alternatingRowColors (self)`
*   `int autoScrollMargin (self)`
*   `clearSelection (self)`
*   `closeEditor (self, QWidget editor, QAbstractItemDelegate.EndEditHint hint)`
*   `closePersistentEditor (self, QModelIndex index)`
*   `commitData (self, QWidget editor)`
*   `currentChanged (self, QModelIndex current, QModelIndex previous)`
*   `QModelIndex currentIndex (self)`
*   `dataChanged (self, QModelIndex topLeft, QModelIndex bottomRight)`
*   `Qt.DropAction defaultDropAction (self)`
*   `QPoint dirtyRegionOffset (self)`
*   `DragDropMode dragDropMode (self)`
*   `bool dragDropOverwriteMode (self)`
*   `bool dragEnabled (self)`
*   `dragEnterEvent (self, QDragEnterEvent e)`
*   `dragLeaveEvent (self, QDragLeaveEvent e)`
*   `dragMoveEvent (self, QDragMoveEvent e)`
*   `dropEvent (self, QDropEvent e)`
*   `DropIndicatorPosition dropIndicatorPosition (self)`
*   `edit (self, QModelIndex index)`
*   `bool edit (self, QModelIndex index, EditTrigger trigger, QEvent event)`
*   `editorDestroyed (self, QObject editor)`
*   `EditTriggers editTriggers (self)`
*   `bool event (self, QEvent event)`
*   `executeDelayedItemsLayout (self)`
*   `focusInEvent (self, QFocusEvent e)`
*   `bool focusNextPrevChild (self, bool next)`
*   `focusOutEvent (self, QFocusEvent e)`
*   `bool hasAutoScroll (self)`
*   `int horizontalOffset (self)`
*   `horizontalScrollbarAction (self, int action)`
*   `horizontalScrollbarValueChanged (self, int value)`
*   `ScrollMode horizontalScrollMode (self)`
*   `int horizontalStepsPerItem (self)`
*   `QSize iconSize (self)`
*   `QModelIndex indexAt (self, QPoint p)`
*   `QWidget indexWidget (self, QModelIndex index)`
*   `inputMethodEvent (self, QInputMethodEvent event)`
*   `QVariant inputMethodQuery (self, Qt.InputMethodQuery query)`
*   `bool isIndexHidden (self, QModelIndex index)`
*   `QAbstractItemDelegate itemDelegate (self)`
*   `QAbstractItemDelegate itemDelegate (self, QModelIndex index)`
*   `QAbstractItemDelegate itemDelegateForColumn (self, int column)`
*   `QAbstractItemDelegate itemDelegateForRow (self, int row)`
*   `keyboardSearch (self, QString search)`
*   `keyPressEvent (self, QKeyEvent e)`
*   `QAbstractItemModel model (self)`
*   `mouseDoubleClickEvent (self, QMouseEvent e)`
*   `mouseMoveEvent (self, QMouseEvent e)`
*   `mousePressEvent (self, QMouseEvent e)`
*   `mouseReleaseEvent (self, QMouseEvent e)`
*   `QModelIndex moveCursor (self, CursorAction cursorAction, Qt.KeyboardModifiers modifiers)`
*   `openPersistentEditor (self, QModelIndex index)`
*   `reset (self)`
*   `resizeEvent (self, QResizeEvent e)`
*   `QModelIndex rootIndex (self)`
*   `rowsAboutToBeRemoved (self, QModelIndex parent, int start, int end)`
*   `rowsInserted (self, QModelIndex parent, int start, int end)`
*   `scheduleDelayedItemsLayout (self)`
*   `scrollDirtyRegion (self, int dx, int dy)`
*   `scrollTo (self, QModelIndex index, ScrollHint hint = QAbstractItemView.EnsureVisible)`
*   `scrollToBottom (self)`
*   `scrollToTop (self)`
*   `selectAll (self)`
*   `list-of-QModelIndex selectedIndexes (self)`
*   `SelectionBehavior selectionBehavior (self)`
*   `selectionChanged (self, QItemSelection selected, QItemSelection deselected)`
*   `QItemSelectionModel.SelectionFlags selectionCommand (self, QModelIndex index, QEvent event = None)`
*   `SelectionMode selectionMode (self)`
*   `QItemSelectionModel selectionModel (self)`
*   `setAlternatingRowColors (self, bool enable)`
*   `setAutoScroll (self, bool enable)`
*   `setAutoScrollMargin (self, int margin)`
*   `setCurrentIndex (self, QModelIndex index)`
*   `setDefaultDropAction (self, Qt.DropAction dropAction)`
*   `setDirtyRegion (self, QRegion region)`
*   `setDragDropMode (self, DragDropMode behavior)`
*   `setDragDropOverwriteMode (self, bool overwrite)`
*   `setDragEnabled (self, bool enable)`
*   `setDropIndicatorShown (self, bool enable)`
*   `setEditTriggers (self, EditTriggers triggers)`
*   `setHorizontalScrollMode (self, ScrollMode mode)`
*   `setHorizontalStepsPerItem (self, int steps)`
*   `setIconSize (self, QSize size)`
*   `setIndexWidget (self, QModelIndex index, QWidget widget)`
*   `setItemDelegate (self, QAbstractItemDelegate delegate)`
*   `setItemDelegateForColumn (self, int column, QAbstractItemDelegate delegate)`
*   `setItemDelegateForRow (self, int row, QAbstractItemDelegate delegate)`
*   `setModel (self, QAbstractItemModel model)`
*   `setRootIndex (self, QModelIndex index)`
*   `setSelection (self, QRect rect, QItemSelectionModel.SelectionFlags command)`
*   `setSelectionBehavior (self, SelectionBehavior behavior)`
*   `setSelectionMode (self, SelectionMode mode)`
*   `setSelectionModel (self, QItemSelectionModel selectionModel)`
*   `setState (self, State state)`
*   `setTabKeyNavigation (self, bool enable)`
*   `setTextElideMode (self, Qt.TextElideMode mode)`
*   `setVerticalScrollMode (self, ScrollMode mode)`
*   `setVerticalStepsPerItem (self, int steps)`
*   `bool showDropIndicator (self)`
*   `int sizeHintForColumn (self, int column)`
*   `QSize sizeHintForIndex (self, QModelIndex index)`
*   `int sizeHintForRow (self, int row)`
*   `startDrag (self, Qt.DropActions supportedActions)`
*   `State state (self)`
*   `bool tabKeyNavigation (self)`
*   `Qt.TextElideMode textElideMode (self)`
*   `timerEvent (self, QTimerEvent e)`
*   `update (self)`
*   `update (self, QModelIndex index)`
*   `updateEditorData (self)`
*   `updateEditorGeometries (self)`
*   `updateGeometries (self)`
*   `int verticalOffset (self)`
*   `verticalScrollbarAction (self, int action)`
*   `verticalScrollbarValueChanged (self, int value)`
*   `ScrollMode verticalScrollMode (self)`
*   `int verticalStepsPerItem (self)`
*   `QStyleOptionViewItem viewOptions (self)`
*   `bool viewportEvent (self, QEvent e)`
*   `QRect visualRect (self, QModelIndex index)`
*   `QRegion visualRegionForSelection (self, QItemSelection selection)`

### Qt Signals

*   `void activated (const QModelIndex&)`
*   `void clicked (const QModelIndex&)`
*   `void doubleClicked (const QModelIndex&)`
*   `void entered (const QModelIndex&)`
*   `void pressed (const QModelIndex&)`
*   `void viewportEntered ()`

* * *

## Detailed Description

该QAbstractItemView类为项目视图类的基本功能。

QAbstractItemView类是使用每个标准视图的基类[QAbstractItemModel](qabstractitemmodel.html)。 QAbstractItemView是一个抽象类，本身不能被实例化。它提供了通过信号和槽机制与模型进行交互操作，使子类必须跟上最新的变化，以他们的模型的标准接口。这个类提供了用于键盘和鼠标导航，视口滚动，项目编辑和选择标准的支持。键盘导航实现了这个功能：

| Keys | Functionality |
| --- | --- |
| Arrow keys | Changes the current item and selects it. |
| Ctrl+Arrow keys | Changes the current item but does not select it. |
| Shift+Arrow keys | Changes the current item and selects it. The previously selected item(s) is not deselected. |
| Ctr+Space | Toggles selection of the current item. |
| Tab/Backtab | Changes the current item to the next/previous item. |
| Home/End | Selects the first/last item in the model. |
| Page up/Page down | Scrolls the rows shown up/down by the number of visible rows in the view. |
| Ctrl+A | Selects all items in the model. |

注意，上述表假设[selection mode](qabstractitemview.html#selectionMode-prop)允许的操作。例如，你不能选择项目，如果选择模式为[QAbstractItemView.NoSelection](qabstractitemview.html#SelectionMode-enum)。

该QAbstractItemView类是一个[Model/View Classes](index.htm)并且是Qt的一部分[model/view framework](index.htm)。

继承QAbstractItemView的视图类只需要实现自己的看法特定的功能，如绘图项目，返回项目的几何形状，寻找项目，等等。

QAbstractItemView提供通用的插槽，如[edit](qabstractitemview.html#edit)（）和[setCurrentIndex](qabstractitemview.html#setCurrentIndex)（ ） 。还提供了许多保护的时隙，包括[dataChanged](qabstractitemview.html#dataChanged)（ ）[rowsInserted](qabstractitemview.html#rowsInserted)（ ）[rowsAboutToBeRemoved](qabstractitemview.html#rowsAboutToBeRemoved)（ ）[selectionChanged](qabstractitemview.html#selectionChanged)（）和[currentChanged](qabstractitemview.html#currentChanged)（ ） 。

根项目是由返回[rootIndex](qabstractitemview.html#rootIndex)（） ，并且通过当前项目[currentIndex](qabstractitemview.html#currentIndex)（ ） 。为了确保一个项目是可见的使用[scrollTo](qabstractitemview.html#scrollTo)（ ） 。

一些QAbstractItemView的功能所关心的滚动，例如[setHorizontalScrollMode](qabstractitemview.html#horizontalScrollMode-prop)（）和[setVerticalScrollMode](qabstractitemview.html#verticalScrollMode-prop)（ ） 。要设置滚动条的范围内，你可以，例如，重新实现视图的[resizeEvent](qabstractitemview.html#resizeEvent)（ ）函数：

```
 void MyView.resizeEvent([QResizeEvent](qresizeevent.html) *event) {
     horizontalScrollBar()->setRange(0, realWidth - width());
     ...
 }

```

请注意，该区域未更新，直到小部件显示。

其他一些功能所关心的选择控制，例如[setSelectionMode](qabstractitemview.html#selectionMode-prop)（）和[setSelectionBehavior](qabstractitemview.html#selectionBehavior-prop)（ ） 。这个类提供了一个默认的选择模型一起工作（[selectionModel](qabstractitemview.html#selectionModel)（） ），但是这可以通过使用代替[setSelectionModel](qabstractitemview.html#setSelectionModel)（ ）与实例[QItemSelectionModel](qitemselectionmodel.html)。

有关完整的控制项的显示和编辑您可以指定一个委讬[setItemDelegate](qabstractitemview.html#setItemDelegate)（ ） 。

QAbstractItemView提供了很多保护功能。一些所关注的编辑，例如，[edit](qabstractitemview.html#edit)（）和[commitData](qabstractitemview.html#commitData)（ ） ，而有些则是键盘和鼠标的事件处理程序。

**Note:**如果你继承QAbstractItemView并打算更新视口的内容，你应该使用视口 - \u003e[update](qabstractitemview.html#update)（）而不是[update()](qwidget.html#update)因为所有的绘画操作需要视口的地方。

* * *

## Type Documentation

```
QAbstractItemView.CursorAction
```

这个枚举变量描述的不同方法的项目之间导航，

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractItemView.MoveUp` | `0` | 移动到高于目前项目的项目。 |
| `QAbstractItemView.MoveDown` | `1` | 移动到低于当前项目的项目。 |
| `QAbstractItemView.MoveLeft` | `2` | 移动到当前项目的左边的项目。 |
| `QAbstractItemView.MoveRight` | `3` | 移动到当前项目的项目的权利。 |
| `QAbstractItemView.MoveHome` | `4` | 移动到左上角的项目。 |
| `QAbstractItemView.MoveEnd` | `5` | 移动到右下角项目。 |
| `QAbstractItemView.MovePageUp` | `6` | 移动一页了高于目前的项目。 |
| `QAbstractItemView.MovePageDown` | `7` | 移动一页向下跌破目前的项目。 |
| `QAbstractItemView.MoveNext` | `8` | 目前项目后移至该项目。 |
| `QAbstractItemView.MovePrevious` | `9` | 移动到该项目目前的项目之前。 |

**See also** [moveCursor](qabstractitemview.html#moveCursor)（ ） 。

```
QAbstractItemView.DragDropMode
```

介绍了各种拖放事件的视图可以进行操作。默认情况下，视图不支持拖动或下降（`NoDragDrop`） 。

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractItemView.NoDragDrop` | `0` | 不支持拖放或删除。 |
| `QAbstractItemView.DragOnly` | `1` | 该视图支持自己的物品拖动 |
| `QAbstractItemView.DropOnly` | `2` | 该视图接受滴 |
| `QAbstractItemView.DragDrop` | `3` | 该视图支持拖放 |
| `QAbstractItemView.InternalMove` | `4` | 认为接受移动（**not copy**）只能从本身的操作。 |

请注意，该模式使用需求，提供拖放操作的支持。

这个枚举被引入或修改的Qt 4.2 。

**See also** [setDragDropMode](qabstractitemview.html#dragDropMode-prop)（）和[Using drag and drop with item views](index.htm#using-drag-and-drop-with-item-views)。

```
QAbstractItemView.DropIndicatorPosition
```

这个枚举表示有关该指数的下降指标在当前鼠标位置的位置：

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractItemView.OnItem` | `0` | 该项目将在指数下跌。 |
| `QAbstractItemView.AboveItem` | `1` | 该项目将索引上面被丢弃。 |
| `QAbstractItemView.BelowItem` | `2` | 该项目将被丢弃指数下方。 |
| `QAbstractItemView.OnViewport` | `3` | 该项目将被丢弃到视口的区域，没有项目。每个视图处理项目拖放到视口的方式取决于所使用的底层模型的行为。 |

```
QAbstractItemView.EditTrigger
```

这个枚举变量描述了将启动项目编辑操作。

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractItemView.NoEditTriggers` | `0` | 没有编辑成为可能。 |
| `QAbstractItemView.CurrentChanged` | `1` | 编辑启动时电流项的变化。 |
| `QAbstractItemView.DoubleClicked` | `2` | 编辑开始当一个项目被双击。 |
| `QAbstractItemView.SelectedClicked` | `4` | 编辑在已经选定的项目时，点击开始。 |
| `QAbstractItemView.EditKeyPressed` | `8` | 当平台的编辑键被按下了某个项目开始编辑。 |
| `QAbstractItemView.AnyKeyPressed` | `16` | 当任何键被按下了某个项目开始编辑。 |
| `QAbstractItemView.AllEditTriggers` | `31` | 编辑开始对所有上述行动。 |

该EditTriggers类型是一个typedef为[QFlags](index.htm)\u003cEditTrigger\u003e 。它存储EditTrigger值的或组合。

```
QAbstractItemView.ScrollHint
```

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractItemView.EnsureVisible` | `0` | 滚动，以确保该项目是可见的。 |
| `QAbstractItemView.PositionAtTop` | `1` | 滚动的视口的顶部位置的项目。 |
| `QAbstractItemView.PositionAtBottom` | `2` | 滚动的视口的底部位置的项目。 |
| `QAbstractItemView.PositionAtCenter` | `3` | 滚动的视口的中心位置的项目。 |

```
QAbstractItemView.ScrollMode
```

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractItemView.ScrollPerItem` | `0` | 该视图会滚动的内容一个项目的时间。 |
| `QAbstractItemView.ScrollPerPixel` | `1` | 该视图会滚动的内容一个像素的时间。 |

这个枚举被引入或修改的Qt 4.2 。

```
QAbstractItemView.SelectionBehavior
```

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractItemView.SelectItems` | `0` | 选择单个项目。 |
| `QAbstractItemView.SelectRows` | `1` | 只选择行。 |
| `QAbstractItemView.SelectColumns` | `2` | 只选择列。 |

```
QAbstractItemView.SelectionMode
```

这个枚举表示视图如何响应用户的选择：

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractItemView.SingleSelection` | `1` | 当用户选择一个项目，任何已选定的项目变成未选中，并单击其上的用户无法取消选择所选的项目。 |
| `QAbstractItemView.ContiguousSelection` | `4` | 当用户以通常的方式选择一个项目时，该选择被清除，新的项目中选定。但是，如果用户按下Shift键的同时单击某个项目，目前的项目和被点击的项目之间的所有项目都选择或取消选择，这取决于单击项的状态。 |
| `QAbstractItemView.ExtendedSelection` | `3` | 当用户以通常的方式选择一个项目时，该选择被清除，新的项目中选定。但是，如果用户对某个项目时，点击按下Ctrl键，单击该项目被触发，其他所有项均保持不变。如果用户按下Shift键的同时单击某个项目，目前的项目和被点击的项目之间的所有项目都选择或取消选择，这取决于单击项的状态。多个项目可以通过拖动鼠标在他们被选中。 |
| `QAbstractItemView.MultiSelection` | `2` | 当用户在通常的方式选择一个项目，该项目的选择状态翻转，其他项目都单独留在家中。多个项目可以通过拖动鼠标在他们进行切换。 |
| `QAbstractItemView.NoSelection` | `0` | 项目无法选择。 |

最常用的方式是SingleSelection和ExtendedSelection 。

```
QAbstractItemView.State
```

描述了不同状态下的视图可以是英寸重新实现自己的看法时，这通常是只有趣。

| Constant | Value | Description |
| --- | --- | --- |
| `QAbstractItemView.NoState` | `0` | 的是默认状态。 |
| `QAbstractItemView.DraggingState` | `1` | 用户拖动项目。 |
| `QAbstractItemView.DragSelectingState` | `2` | 该用户选择项目的操作。 |
| `QAbstractItemView.EditingState` | `3` | 用户正在编辑一个项目中一个小部件的编辑器。 |
| `QAbstractItemView.ExpandingState` | `4` | 用户被打开的项目的一个分支。 |
| `QAbstractItemView.CollapsingState` | `5` | 该用户被关闭的项目的一个分支。 |
| `QAbstractItemView.AnimatingState` | `6` | 项目视图正在执行的动画。 |

* * *

## Method Documentation

```
QAbstractItemView.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个抽象的项目视图与给定_parent_。

```
bool QAbstractItemView.alternatingRowColors (self)
```

```
int QAbstractItemView.autoScrollMargin (self)
```

```
QAbstractItemView.clearSelection (self)
```

这种方法也是一个Qt槽与C + +的签名`void clearSelection()`。

取消选择所有选定的项目。当前索引将不会被改变。

**See also** [setSelection](qabstractitemview.html#setSelection)（）和[selectAll](qabstractitemview.html#selectAll)（ ） 。

```
QAbstractItemView.closeEditor (self, QWidget editor, QAbstractItemDelegate.EndEditHint hint)
```

这种方法也是一个Qt槽与C + +的签名`void closeEditor(QWidget *,QAbstractItemDelegate::EndEditHint)`。

关闭给定的_editor_，并释放它。该_hint_用于指定视图如何应于编辑操作结束时作出响应。例如，提示可能表明，在视图中的下一个项目应该打开进行编辑。

**See also** [edit](qabstractitemview.html#edit)（）和[commitData](qabstractitemview.html#commitData)（ ） 。

```
QAbstractItemView.closePersistentEditor (self, QModelIndex index)
```

关闭持久编辑该项目在给定的_index_。

**See also** [openPersistentEditor](qabstractitemview.html#openPersistentEditor)（ ） 。

```
QAbstractItemView.commitData (self, QWidget editor)
```

这种方法也是一个Qt槽与C + +的签名`void commitData(QWidget *)`。

提交的资料_editor_到模型中。

**See also** [closeEditor](qabstractitemview.html#closeEditor)（ ） 。

```
QAbstractItemView.currentChanged (self, QModelIndex current, QModelIndex previous)
```

这种方法也是一个Qt槽与C + +的签名`void currentChanged(const QModelIndex&,const QModelIndex&)`。

当一个新项目成为当前项目这个槽被调用。先前的目前的项目是由指定的_previous_指数，并且由新的项目_current_索引。

如果您想了解变更的项目看[dataChanged](qabstractitemview.html#dataChanged)（）信号。

```
QModelIndex QAbstractItemView.currentIndex (self)
```

[

返回当前项的模型索引。

](qmodelindex.html)

[**See also**](qmodelindex.html) [setCurrentIndex](qabstractitemview.html#setCurrentIndex)（ ） 。

```
QAbstractItemView.dataChanged (self, QModelIndex topLeft, QModelIndex bottomRight)
```

这种方法也是一个Qt槽与C + +的签名`void dataChanged(const QModelIndex&,const QModelIndex&)`。

这个槽被调用时，项目模型被改变。该变更的项目是那些从_topLeft_至_bottomRight_包容性。如果只有一个项目被改变_topLeft_==_bottomRight_。

```
Qt.DropAction QAbstractItemView.defaultDropAction (self)
```

[](qt.html#DropAction-enum)

```
QPoint QAbstractItemView.dirtyRegionOffset (self)
```

[

肮脏的地区，在视图返回偏移量。

](qpoint.html)

[如果你使用](qpoint.html)[scrollDirtyRegion](qabstractitemview.html#scrollDirtyRegion)（ ）和实施[paintEvent](qabstractscrollarea.html#paintEvent)（）中的子类[QAbstractItemView](qabstractitemview.html)，你应该翻译的Paint事件与此功能的偏移返回给定的区域。

**See also** [scrollDirtyRegion](qabstractitemview.html#scrollDirtyRegion)（）和[setDirtyRegion](qabstractitemview.html#setDirtyRegion)（ ） 。

```
DragDropMode QAbstractItemView.dragDropMode (self)
```

[

```
bool QAbstractItemView.dragDropOverwriteMode (self)
```

```
bool QAbstractItemView.dragEnabled (self)
```

```
QAbstractItemView.dragEnterEvent (self, QDragEnterEvent e)
```

](qabstractitemview.html#DragDropMode-enum)

[从重新实现](qabstractitemview.html#DragDropMode-enum)[QWidget.dragEnterEvent](qwidget.html#dragEnterEvent)（ ） 。

这个函数被调用给定的_event_当拖放操作进入小部件。如果拖动是在一个有效的滴地方（如在接受滴的项目） ，该事件被接受，否则它将被忽略。

**See also** [dropEvent](qabstractitemview.html#dropEvent)（）和[startDrag](qabstractitemview.html#startDrag)（ ） 。

```
QAbstractItemView.dragLeaveEvent (self, QDragLeaveEvent e)
```

从重新实现[QWidget.dragLeaveEvent](qwidget.html#dragLeaveEvent)（ ） 。

这个函数被调用时，被拖动的项叶的看法。该_event_介绍了拖放操作的状态。

```
QAbstractItemView.dragMoveEvent (self, QDragMoveEvent e)
```

从重新实现[QWidget.dragMoveEvent](qwidget.html#dragMoveEvent)（ ） 。

此功能是与给定的连续叫_event_一个拖放操作在小部件中。它可以使视图的，举个例子，用户拖动鼠标选择要查看的右侧或底部边缘滚动。在这种情况下，事件将被接受，否则将被忽略。

**See also** [dropEvent](qabstractitemview.html#dropEvent)（）和[startDrag](qabstractitemview.html#startDrag)（ ） 。

```
QAbstractItemView.dropEvent (self, QDropEvent e)
```

从重新实现[QWidget.dropEvent](qwidget.html#dropEvent)（ ） 。

这个函数被调用给定的_event_当一个放置事件发生在窗口小部件。如果模型接受甚至定位放置事件被接受，否则它将被忽略。

**See also** [startDrag](qabstractitemview.html#startDrag)（ ） 。

```
DropIndicatorPosition QAbstractItemView.dropIndicatorPosition (self)
```

[

返回相对于最接近的项目拖放指示符的位置。

这个函数是Qt 4.1中引入。

```
QAbstractItemView.edit (self, QModelIndex index)
```

这种方法也是一个Qt槽与C + +的签名`void edit(const QModelIndex&)`。

开始编辑对应于给定的产品_index_如果是可编辑的。

](qabstractitemview.html#DropIndicatorPosition-enum)

[注意，这个函数不改变当前索引。由于目前指数定义了一个和以前的项目进行编辑，用户可能会发现，由于预期键盘导航不起作用。为了提供一致的导航行为，请致电](qabstractitemview.html#DropIndicatorPosition-enum)[setCurrentIndex](qabstractitemview.html#setCurrentIndex)（ ）这个函数有相同的模型索引之前。

**See also** [QModelIndex.flags](qmodelindex.html#flags)（ ） 。

```
bool QAbstractItemView.edit (self, QModelIndex index, EditTrigger trigger, QEvent event)
```

开始编辑了该项目_index_，如果有必要创建一个编辑器，并返回True，如果该视图的[State](qabstractitemview.html#State-enum)现在是[EditingState](qabstractitemview.html#State-enum)否则返回False 。

导致该编辑过程中的作用通过描述_trigger_以及是由指定的相关联的事件_event_。

编辑可以通过指定强制的_trigger_要[QAbstractItemView.AllEditTriggers](qabstractitemview.html#EditTrigger-enum)。

**See also** [closeEditor](qabstractitemview.html#closeEditor)（ ） 。

```
QAbstractItemView.editorDestroyed (self, QObject editor)
```

这种方法也是一个Qt槽与C + +的签名`void editorDestroyed(QObject *)`。

这个函数被调用的时候给出_editor_已被摧毁。

**See also** [closeEditor](qabstractitemview.html#closeEditor)（ ） 。

```
EditTriggers QAbstractItemView.editTriggers (self)
```

[

```
bool QAbstractItemView.event (self, QEvent event)
```

](index.htm)

[从重新实现](index.htm)[QObject.event](qobject.html#event)（ ） 。

```
QAbstractItemView.executeDelayedItemsLayout (self)
```

执行预定的布局，而无需等待该事件的处理开始。

**See also** [scheduleDelayedItemsLayout](qabstractitemview.html#scheduleDelayedItemsLayout)（ ） 。

```
QAbstractItemView.focusInEvent (self, QFocusEvent e)
```

从重新实现[QWidget.focusInEvent](qwidget.html#focusInEvent)（ ） 。

这个函数被调用给定的_event_当插件获得焦点。默认情况下，事件被忽略。

**See also** [setFocus](qwidget.html#setFocus)（）和[focusOutEvent](qabstractitemview.html#focusOutEvent)（ ） 。

```
bool QAbstractItemView.focusNextPrevChild (self, bool next)
```

从重新实现[QWidget.focusNextPrevChild](qwidget.html#focusNextPrevChild)（ ） 。

```
QAbstractItemView.focusOutEvent (self, QFocusEvent e)
```

从重新实现[QWidget.focusOutEvent](qwidget.html#focusOutEvent)（ ） 。

这个函数被调用给定的_event_当小部件失去焦点。默认情况下，事件被忽略。

**See also** [clearFocus](qwidget.html#clearFocus)（）和[focusInEvent](qabstractitemview.html#focusInEvent)（ ） 。

```
bool QAbstractItemView.hasAutoScroll (self)
```

```
int QAbstractItemView.horizontalOffset (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回水平视图的偏移量。

在基类中，这是一个纯虚函数。

**See also** [verticalOffset](qabstractitemview.html#verticalOffset)（ ） 。

```
QAbstractItemView.horizontalScrollbarAction (self, int action)
```

这种方法也是一个Qt槽与C + +的签名`void horizontalScrollbarAction(int)`。

```
QAbstractItemView.horizontalScrollbarValueChanged (self, int value)
```

这种方法也是一个Qt槽与C + +的签名`void horizontalScrollbarValueChanged(int)`。

```
ScrollMode QAbstractItemView.horizontalScrollMode (self)
```

[

```
int QAbstractItemView.horizontalStepsPerItem (self)
```

](qabstractitemview.html#ScrollMode-enum)

```
QSize QAbstractItemView.iconSize (self)
```

[](qsize.html)

```
QModelIndex QAbstractItemView.indexAt (self, QPoint p)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回项的模型索引处的视口坐标_point_。

在基类中，这是一个纯虚函数。

](qmodelindex.html)

[**See also**](qmodelindex.html) [visualRect](qabstractitemview.html#visualRect)（ ） 。

```
QWidget QAbstractItemView.indexWidget (self, QModelIndex index)
```

[

返回部件的项目在给定的_index_。

这个函数是Qt 4.1中引入。

](qwidget.html)

[**See also**](qwidget.html) [setIndexWidget](qabstractitemview.html#setIndexWidget)（ ） 。

```
QAbstractItemView.inputMethodEvent (self, QInputMethodEvent event)
```

从重新实现[QWidget.inputMethodEvent](qwidget.html#inputMethodEvent)（ ） 。

```
QVariant QAbstractItemView.inputMethodQuery (self, Qt.InputMethodQuery query)
```

从重新实现[QWidget.inputMethodQuery](qwidget.html#inputMethodQuery)（ ） 。

```
bool QAbstractItemView.isIndexHidden (self, QModelIndex index)
```

这种方法是抽象的，应在任何子类中重新实现。

返回True ，如果该项目由给定的简称_index_隐藏在视图，否则返回False 。

隐藏的是一个视图特定的功能。例如在TableView中的列可以被标记为隐藏或行中的树视图。

在基类中，这是一个纯虚函数。

```
QAbstractItemDelegate QAbstractItemView.itemDelegate (self)
```

[](qabstractitemdelegate.html)

[返回此视图和模型的项目委讬。这可能是一组与](qabstractitemdelegate.html)[setItemDelegate](qabstractitemview.html#setItemDelegate)（ ） ，或默认之一。

**See also** [setItemDelegate](qabstractitemview.html#setItemDelegate)（ ） 。

```
QAbstractItemDelegate QAbstractItemView.itemDelegate (self, QModelIndex index)
```

[

返回此视图和模型对于给定的项目代表_index_。

](qabstractitemdelegate.html)

```
QAbstractItemDelegate QAbstractItemView.itemDelegateForColumn (self, int column)
```

[](qabstractitemdelegate.html)

[返回此视图和模型对于给定的项目代表_column_。您可以致电](qabstractitemdelegate.html)[itemDelegate](qabstractitemview.html#itemDelegate)（）来获得一个指向当前委讬一个给定的索引。

这个函数中引入了Qt 4.2中。

**See also** [setItemDelegateForColumn](qabstractitemview.html#setItemDelegateForColumn)（ ）[itemDelegateForRow](qabstractitemview.html#itemDelegateForRow)（）和[itemDelegate](qabstractitemview.html#itemDelegate)（ ） 。

```
QAbstractItemDelegate QAbstractItemView.itemDelegateForRow (self, int row)
```

[](qabstractitemdelegate.html)

[返回此视图和模型对于给定的项目代表_row_，或者0 ，如果没有委讬已分配。您可以致电](qabstractitemdelegate.html)[itemDelegate](qabstractitemview.html#itemDelegate)（）来获得一个指向当前委讬一个给定的索引。

这个函数中引入了Qt 4.2中。

**See also** [setItemDelegateForRow](qabstractitemview.html#setItemDelegateForRow)（ ）[itemDelegateForColumn](qabstractitemview.html#itemDelegateForColumn)（）和[setItemDelegate](qabstractitemview.html#setItemDelegate)（ ） 。

```
QAbstractItemView.keyboardSearch (self, QString search)
```

移动到并选择最好的项目相匹配的字符串_search_。如果没有项目被发现没有任何反应。

在默认实现中，搜索是复位，如果_search_是空的，或时间间隔上次的搜索已经超过[QApplication.keyboardInputInterval](qapplication.html#keyboardInputInterval-prop)（ ） 。

```
QAbstractItemView.keyPressEvent (self, QKeyEvent e)
```

从重新实现[QWidget.keyPressEvent](qwidget.html#keyPressEvent)（ ） 。

这个函数被调用给定的_event_当一个键事件被发送给窗口小部件。默认实现处理基本的光标移动，如上，下，左，右，首页，上一页，和PageDown ;的[activated](qabstractitemview.html#activated)如果当前索引有效和激活键被按下（例如Enter键或Return ，取决于平台） （ ）信号被发射。这个功能就是编辑是由按键启动，如如果F2被按下。

**See also** [edit](qabstractitemview.html#edit)（ ）[moveCursor](qabstractitemview.html#moveCursor)（ ）[keyboardSearch](qabstractitemview.html#keyboardSearch)（）和[tabKeyNavigation](qabstractitemview.html#tabKeyNavigation-prop)。

```
QAbstractItemModel QAbstractItemView.model (self)
```

[

返回该视图呈现模式。

](qabstractitemmodel.html)

[**See also**](qabstractitemmodel.html) [setModel](qabstractitemview.html#setModel)（ ） 。

```
QAbstractItemView.mouseDoubleClickEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mouseDoubleClickEvent](qwidget.html#mouseDoubleClickEvent)（ ） 。

这个函数被调用给定的_event_当鼠标按钮被双击的widget内点击。如果双击是一个有效的项目它发出的[doubleClicked](qabstractitemview.html#doubleClicked)（ ）信号和通话[edit](qabstractitemview.html#edit)（ ）上的项目。

```
QAbstractItemView.mouseMoveEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

这个函数被调用给定的_event_当鼠标移动事件被发送给窗口小部件。如果选择是在进步和新项目移到选择是延长;如果拖动操作正在进行，它继续。

```
QAbstractItemView.mousePressEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

这个函数被调用给定的_event_当按下鼠标按钮时光标在widget内。如果一个有效的项目上按下制成的当前项。此功能会发出[pressed](qabstractitemview.html#pressed)（）信号。

```
QAbstractItemView.mouseReleaseEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

这个函数被调用给定的_event_当释放鼠标按钮，在窗口小部件鼠标按下事件后。如果用户按下你的widget里面的鼠标，然后拖动鼠标到另一个位置释放鼠标按钮之前，你的widget接收释放事件。该函数将放出[clicked](qabstractitemview.html#clicked)（ ）如果一个项目是被按下的信号。

```
QModelIndex QAbstractItemView.moveCursor (self, CursorAction cursorAction, Qt.KeyboardModifiers modifiers)
```

[

这种方法是抽象的，应在任何子类中重新实现。

](qmodelindex.html)

[返回](qmodelindex.html)[QModelIndex](qmodelindex.html)对象指向在视图中的下一个对象，根据给定的_cursorAction_并通过指定的键盘功能键_modifiers_。

在基类中，这是一个纯虚函数。

```
QAbstractItemView.openPersistentEditor (self, QModelIndex index)
```

打开关于该项目的持续性编辑器在给定的_index_。如果没有编辑器存在，则委讬将创建一个新的编辑器。

**See also** [closePersistentEditor](qabstractitemview.html#closePersistentEditor)（ ） 。

```
QAbstractItemView.reset (self)
```

这种方法也是一个Qt槽与C + +的签名`void reset()`。

重置视图的内部状态。

**Warning:**此功能将重新打开的编辑器，滚动条的位置，选择等现有的更改将不会被提交。如果你想重置视图时，保存更改，您可以重新实现此功能，提交你的修改，然后调用父类的实现。

```
QAbstractItemView.resizeEvent (self, QResizeEvent e)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

这个函数被调用给定的_event_当resize事件被发送给窗口小部件。

**See also** [QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
QModelIndex QAbstractItemView.rootIndex (self)
```

[

返回模型的根项的模型索引。根项目是父项视图的顶层项目。根可以是无效的。

](qmodelindex.html)

[**See also**](qmodelindex.html) [setRootIndex](qabstractitemview.html#setRootIndex)（ ） 。

```
QAbstractItemView.rowsAboutToBeRemoved (self, QModelIndex parent, int start, int end)
```

这种方法也是一个Qt槽与C + +的签名`void rowsAboutToBeRemoved(const QModelIndex&,int,int)`。

这个槽被调用时的行是要被去除。被删除的行是指在给定的_parent_从_start_至_end_包容性。

**See also** [rowsInserted](qabstractitemview.html#rowsInserted)（ ） 。

```
QAbstractItemView.rowsInserted (self, QModelIndex parent, int start, int end)
```

这种方法也是一个Qt槽与C + +的签名`void rowsInserted(const QModelIndex&,int,int)`。

插入行时这个槽被调用。新行是指在给定的_parent_从_start_至_end_包容性。基类实现调用fetchMore （ ）在模型上，以检查更多的数据。

**See also** [rowsAboutToBeRemoved](qabstractitemview.html#rowsAboutToBeRemoved)（ ） 。

```
QAbstractItemView.scheduleDelayedItemsLayout (self)
```

附表的事件处理开始时要执行在视图中的项目的布局。

即使scheduleDelayedItemsLayout （ ）被调用前，事件被处理多次，认为只会做布局一次。

**See also** [executeDelayedItemsLayout](qabstractitemview.html#executeDelayedItemsLayout)（ ） 。

```
QAbstractItemView.scrollDirtyRegion (self, int dx, int dy)
```

准备由（视图为滚动_dx_，_dy_）像素通过移动脏区在相反的方向。你只需要调用这个函数，如果你要实现一个滚动视口在你的视图子类。

如果您实现[scrollContentsBy](qabstractscrollarea.html#scrollContentsBy)（）中的子类[QAbstractItemView](qabstractitemview.html)，在打电话之前调用这个函数[QWidget.scroll](qwidget.html#scroll)（ ）上的视口。另外，只需要调用[update](qabstractitemview.html#update)（ ） 。

**See also** [scrollContentsBy](qabstractscrollarea.html#scrollContentsBy)（ ）[dirtyRegionOffset](qabstractitemview.html#dirtyRegionOffset)（）和[setDirtyRegion](qabstractitemview.html#setDirtyRegion)（ ） 。

```
QAbstractItemView.scrollTo (self, QModelIndex index, ScrollHint hint = QAbstractItemView.EnsureVisible)
```

这种方法是抽象的，应在任何子类中重新实现。

滚动的视图，如果必要，以确保在产品_index_是可见的。该视图将尝试根据给定定位产品_hint_。

在基类中，这是一个纯虚函数。

```
QAbstractItemView.scrollToBottom (self)
```

这种方法也是一个Qt槽与C + +的签名`void scrollToBottom()`。

滚动视图的底部。

这个函数是Qt 4.1中引入。

**See also** [scrollTo](qabstractitemview.html#scrollTo)（）和[scrollToTop](qabstractitemview.html#scrollToTop)（ ） 。

```
QAbstractItemView.scrollToTop (self)
```

这种方法也是一个Qt槽与C + +的签名`void scrollToTop()`。

滚动视图顶端。

这个函数是Qt 4.1中引入。

**See also** [scrollTo](qabstractitemview.html#scrollTo)（）和[scrollToBottom](qabstractitemview.html#scrollToBottom)（ ） 。

```
QAbstractItemView.selectAll (self)
```

这种方法也是一个Qt槽与C + +的签名`void selectAll()`。

选择视图中的所有项目。此功能将使用选择的行为选择时，在视图中设置。

**See also** [setSelection](qabstractitemview.html#setSelection)（ ）[selectedIndexes](qabstractitemview.html#selectedIndexes)（）和[clearSelection](qabstractitemview.html#clearSelection)（ ） 。

```
list-of-QModelIndex QAbstractItemView.selectedIndexes (self)
```

这个便利函数返回所有选定和非隐藏项的索引视图的列表。该列表包含没有重复，并没有排序。

**See also** [QItemSelectionModel.selectedIndexes](qitemselectionmodel.html#selectedIndexes)（ ） 。

```
SelectionBehavior QAbstractItemView.selectionBehavior (self)
```

[

```
QAbstractItemView.selectionChanged (self, QItemSelection selected, QItemSelection deselected)
```

这种方法也是一个Qt槽与C + +的签名`void selectionChanged(const QItemSelection&,const QItemSelection&)`。

当选择改变这个槽被调用。先前的选择（可能是空的） ，通过指定_deselected_，和新的选择由_selected_。

](qabstractitemview.html#SelectionBehavior-enum)

[**See also**](qabstractitemview.html#SelectionBehavior-enum) [setSelection](qabstractitemview.html#setSelection)（ ） 。

```
QItemSelectionModel.SelectionFlags QAbstractItemView.selectionCommand (self, QModelIndex index, QEvent event = None)
```

[

更新与选择要包括在返回要使用的SelectionFlags的_index_规定。该_event_是一个用户输入事件，例如鼠标或键盘事件。

重新实现这个函数来定义自己的选择行为。

](index.htm)

[**See also**](index.htm) [setSelection](qabstractitemview.html#setSelection)（ ） 。

```
SelectionMode QAbstractItemView.selectionMode (self)
```

[](qabstractitemview.html#SelectionMode-enum)

```
QItemSelectionModel QAbstractItemView.selectionModel (self)
```

[

返回当前的选择模型。

](qitemselectionmodel.html)

[**See also**](qitemselectionmodel.html) [setSelectionModel](qabstractitemview.html#setSelectionModel)（）和[selectedIndexes](qabstractitemview.html#selectedIndexes)（ ） 。

```
QAbstractItemView.setAlternatingRowColors (self, bool enable)
```

```
QAbstractItemView.setAutoScroll (self, bool enable)
```

```
QAbstractItemView.setAutoScrollMargin (self, int margin)
```

```
QAbstractItemView.setCurrentIndex (self, QModelIndex index)
```

这种方法也是一个Qt槽与C + +的签名`void setCurrentIndex(const QModelIndex&)`。

设置当前项目是在该项目_index_。

除非目前的选择模式[NoSelection](qabstractitemview.html#SelectionMode-enum)时，该项目也被选中。请注意，此功能也更新任何新的选择，用户执行的起始位置。

设定的项目为当前项目而不选择它，调用

`selectionModel()-&gt;setCurrentIndex(index, QItemSelectionModel.NoUpdate);`

**See also** [currentIndex](qabstractitemview.html#currentIndex)（ ）[currentChanged](qabstractitemview.html#currentChanged)（）和[selectionMode](qabstractitemview.html#selectionMode-prop)。

```
QAbstractItemView.setDefaultDropAction (self, Qt.DropAction dropAction)
```

```
QAbstractItemView.setDirtyRegion (self, QRegion region)
```

标志着定_region_脏和时间表加以更新。你只需要调用这个函数，如果你要实现自己的视图子类。

这个函数是Qt 4.1中引入。

**See also** [scrollDirtyRegion](qabstractitemview.html#scrollDirtyRegion)（）和[dirtyRegionOffset](qabstractitemview.html#dirtyRegionOffset)（ ） 。

```
QAbstractItemView.setDragDropMode (self, DragDropMode behavior)
```

```
QAbstractItemView.setDragDropOverwriteMode (self, bool overwrite)
```

```
QAbstractItemView.setDragEnabled (self, bool enable)
```

```
QAbstractItemView.setDropIndicatorShown (self, bool enable)
```

```
QAbstractItemView.setEditTriggers (self, EditTriggers triggers)
```

```
QAbstractItemView.setHorizontalScrollMode (self, ScrollMode mode)
```

```
QAbstractItemView.setHorizontalStepsPerItem (self, int steps)
```

```
QAbstractItemView.setIconSize (self, QSize size)
```

```
QAbstractItemView.setIndexWidget (self, QModelIndex index, QWidget widget)
```

该_widget_说法有它的所有权转移给Qt的。

设置给定_widget_于在给定的产品_index_，通过widget的所有权视域。

If _index_无效（例如，如果您通过根指数） ，这个函数不会做任何事。

给定_widget_的[autoFillBackground](qwidget.html)属性必须设置为True，否则widget的背景是透明的，显示出在给定两个模型数据与项目_index_。

如果指数小部件A被替换为索引部件B，指数控件A将被删除。例如，下面的代码片段中，[QLineEdit](qlineedit.html)对象将被删除。

```
 setIndexWidget(index, new [QLineEdit](qlineedit.html));
 ...
 setIndexWidget(index, new [QTextEdit](qtextedit.html));

```

这个功能应该仅被用于对应于数据项的可见区域内显示静态内容。如果你想显示自定义的动态内容或实现自定义编辑器部件，子类[QItemDelegate](qitemdelegate.html)代替。

这个函数是Qt 4.1中引入。

**See also** [indexWidget](qabstractitemview.html#indexWidget)（）和[Delegate Classes](index.htm#delegate-classes)。

```
QAbstractItemView.setItemDelegate (self, QAbstractItemDelegate delegate)
```

设置项委讬该视图及其模型_delegate_。如果你想完全控制了项目的编辑和显示，这是很有用的。

任何现有的委讬将被删除，但不会被删除。[QAbstractItemView](qabstractitemview.html)不采取所有权_delegate_。

**Warning:**你不应该共享视图之间的委讬的同一实例。否则会导致不正确或不直观的编辑行为，因为在一个给定的委讬每个视图可能会收到[closeEditor()](qabstractitemdelegate.html#closeEditor)信号，并试图访问，修改或关闭一个已经被关闭的编辑器。

**See also** [itemDelegate](qabstractitemview.html#itemDelegate)（ ） 。

```
QAbstractItemView.setItemDelegateForColumn (self, int column, QAbstractItemDelegate delegate)
```

设置给定项目_delegate_使用此视图和模型对于给定的_column_。所有项目_column_将绘制和管理_delegate_而不是使用默认的委讬（即，[itemDelegate](qabstractitemview.html#itemDelegate)（））。

任何现有列委讬_column_将被删除，但不删除。[QAbstractItemView](qabstractitemview.html)不采取所有权_delegate_。

**Note:**如果委讬已被分配到两个行和列，行的委讬将优先考虑和管理的交叉单元索引。

**Warning:**你不应该共享视图之间的委讬的同一实例。否则会导致不正确或不直观的编辑行为，因为在一个给定的委讬每个视图可能会收到[closeEditor()](qabstractitemdelegate.html#closeEditor)信号，并试图访问，修改或关闭一个已经被关闭的编辑器。

这个函数中引入了Qt 4.2中。

**See also** [itemDelegateForColumn](qabstractitemview.html#itemDelegateForColumn)（ ）[setItemDelegateForRow](qabstractitemview.html#setItemDelegateForRow)（）和[itemDelegate](qabstractitemview.html#itemDelegate)（ ） 。

```
QAbstractItemView.setItemDelegateForRow (self, int row, QAbstractItemDelegate delegate)
```

设置给定项目_delegate_使用此视图和模型对于给定的_row_。所有项目_row_将绘制和管理_delegate_而不是使用默认的委讬（即，[itemDelegate](qabstractitemview.html#itemDelegate)（））。

任何现有的行委讬_row_将被删除，但不删除。[QAbstractItemView](qabstractitemview.html)不采取所有权_delegate_。

**Note:**如果委讬已被分配到两个行和列，行委讬（即该委讬）将优先考虑和管理的交叉单元索引。

**Warning:**你不应该共享视图之间的委讬的同一实例。否则会导致不正确或不直观的编辑行为，因为在一个给定的委讬每个视图可能会收到[closeEditor()](qabstractitemdelegate.html#closeEditor)信号，并试图访问，修改或关闭一个已经被关闭的编辑器。

这个函数中引入了Qt 4.2中。

**See also** [itemDelegateForRow](qabstractitemview.html#itemDelegateForRow)（ ）[setItemDelegateForColumn](qabstractitemview.html#setItemDelegateForColumn)（）和[itemDelegate](qabstractitemview.html#itemDelegate)（ ） 。

```
QAbstractItemView.setModel (self, QAbstractItemModel model)
```

设置_model_该视图呈现。

这个函数将创建并设置一个新的选择模式，取代先前设置的任何模型[setSelectionModel](qabstractitemview.html#setSelectionModel)（ ） 。然而，旧的选择模型不会因为它可能被多个视图之间共享删除。我们建议您删除，如果它不再需要旧的选择模型。这样做是用下面的代码：

```
 [QItemSelectionModel](qitemselectionmodel.html) *m = view->selectionModel();
 view->setModel(new model);
 delete m;

```

如果两个旧的模式和旧的选择模型没有父母，或者他们的父母长期存活的对象，它可能是最好打电话到他们的[deleteLater](qobject.html#deleteLater)（ ）函数来显式地删除它们。

视图_does not_取模型的所有权，除非它是模型的父对象，因为该模型可以被许多不同的视图之间共享。

**See also** [model](qabstractitemview.html#model)（ ）[selectionModel](qabstractitemview.html#selectionModel)（）和[setSelectionModel](qabstractitemview.html#setSelectionModel)（ ） 。

```
QAbstractItemView.setRootIndex (self, QModelIndex index)
```

这种方法也是一个Qt槽与C + +的签名`void setRootIndex(const QModelIndex&)`。

根项目设置的项目在给定的_index_。

**See also** [rootIndex](qabstractitemview.html#rootIndex)（ ） 。

```
QAbstractItemView.setSelection (self, QRect rect, QItemSelectionModel.SelectionFlags command)
```

这种方法是抽象的，应在任何子类中重新实现。

适用的选择_flags_在项目或由矩形触摸时，_rect_。

当实现自己的ItemView控件setSelection应该调用[selectionModel](qabstractitemview.html#selectionModel)（ ） - \u003e选择（选择，旗），其中选择要么是空的[QModelIndex](qmodelindex.html)或[QItemSelection](qitemselection.html)包含所包含的所有项目_rect_。

**See also** [selectionCommand](qabstractitemview.html#selectionCommand)（）和[selectedIndexes](qabstractitemview.html#selectedIndexes)（ ） 。

```
QAbstractItemView.setSelectionBehavior (self, SelectionBehavior behavior)
```

```
QAbstractItemView.setSelectionMode (self, SelectionMode mode)
```

```
QAbstractItemView.setSelectionModel (self, QItemSelectionModel selectionModel)
```

设置当前选择模型给定的_selectionModel_。

需要注意的是，如果你调用[setModel](qabstractitemview.html#setModel)（ ）这个函数之后，给定的_selectionModel_将由一个由视图中创建所取代。

**Note:**它是由应用程序，如果它不再需要删除旧的选择模型，也就是说，如果它不被使用的其它视图。当它的父对象被删除，这会自动发生。然而，如果它不具有父，或者如果父是一个长期存在的对象，它可能是优选的，以调用其[deleteLater](qobject.html#deleteLater)（ ）函数来显式地删除它。

**See also** [selectionModel](qabstractitemview.html#selectionModel)（ ）[setModel](qabstractitemview.html#setModel)（）和[clearSelection](qabstractitemview.html#clearSelection)（ ） 。

```
QAbstractItemView.setState (self, State state)
```

设置项视图的状态给定的_state_。

**See also** [state](qabstractitemview.html#state)().

```
QAbstractItemView.setTabKeyNavigation (self, bool enable)
```

```
QAbstractItemView.setTextElideMode (self, Qt.TextElideMode mode)
```

```
QAbstractItemView.setVerticalScrollMode (self, ScrollMode mode)
```

```
QAbstractItemView.setVerticalStepsPerItem (self, int steps)
```

```
bool QAbstractItemView.showDropIndicator (self)
```

```
int QAbstractItemView.sizeHintForColumn (self, int column)
```

返回的宽度尺寸暗示指定_column_或者-1，如果没有模型。

此功能用于在一个水平标题的观点找到尺寸暗示根据对给定内容的标题部分_column_。

**See also** [sizeHintForRow](qabstractitemview.html#sizeHintForRow)（ ） 。

```
QSize QAbstractItemView.sizeHintForIndex (self, QModelIndex index)
```

[

返回尺寸暗示该项目具有指定_index_或无效的大小无效索引。

](qsize.html)

[**See also**](qsize.html) [sizeHintForRow](qabstractitemview.html#sizeHintForRow)（）和[sizeHintForColumn](qabstractitemview.html#sizeHintForColumn)（ ） 。

```
int QAbstractItemView.sizeHintForRow (self, int row)
```

返回的高度尺寸暗示的指定_row_或者-1，如果没有模型。

返回的高度是用给定大小的提示计算_row_的项目，即返回值是项目中的最大高度。请注意，要控制一个行的高度，你必须重新实现[QAbstractItemDelegate.sizeHint](qabstractitemdelegate.html#sizeHint)（）函数。

此功能用于在与垂直插头观点找到尺寸暗示根据对给定内容的标题部分_row_。

**See also** [sizeHintForColumn](qabstractitemview.html#sizeHintForColumn)（ ） 。

```
QAbstractItemView.startDrag (self, Qt.DropActions supportedActions)
```

使用给定的调用拖 - \u003e EXEC （启动拖动）_supportedActions_。

```
State QAbstractItemView.state (self)
```

[

返回该项目视图的状态。

](qabstractitemview.html#State-enum)

[**See also**](qabstractitemview.html#State-enum) [setState](qabstractitemview.html#setState)（ ） 。

```
bool QAbstractItemView.tabKeyNavigation (self)
```

```
Qt.TextElideMode QAbstractItemView.textElideMode (self)
```

[

```
QAbstractItemView.timerEvent (self, QTimerEvent e)
```

](qt.html#TextElideMode-enum)

[从重新实现](qt.html#TextElideMode-enum)[QObject.timerEvent](qobject.html#timerEvent)（ ） 。

这个函数被调用给定的_event_当一个计时器事件被发送给窗口小部件。

**See also** [QObject.timerEvent](qobject.html#timerEvent)（ ） 。

```
QAbstractItemView.update (self)
```

这种方法也是一个Qt槽与C + +的签名`void update()`。

更新由给定的所佔据的区域_index_。

此功能被引入Qt的4.3 。

```
QAbstractItemView.update (self, QModelIndex index)
```

这种方法也是一个Qt槽与C + +的签名`void update(const QModelIndex&)`。

```
QAbstractItemView.updateEditorData (self)
```

这种方法也是一个Qt槽与C + +的签名`void updateEditorData()`。

```
QAbstractItemView.updateEditorGeometries (self)
```

这种方法也是一个Qt槽与C + +的签名`void updateEditorGeometries()`。

```
QAbstractItemView.updateGeometries (self)
```

这种方法也是一个Qt槽与C + +的签名`void updateGeometries()`。

更新视图的子部件的几何形状。

此功能被引入Qt的4.4 。

```
int QAbstractItemView.verticalOffset (self)
```

这种方法是抽象的，应在任何子类中重新实现。

返回垂直视图的偏移量。

在基类中，这是一个纯虚函数。

**See also** [horizontalOffset](qabstractitemview.html#horizontalOffset)（ ） 。

```
QAbstractItemView.verticalScrollbarAction (self, int action)
```

这种方法也是一个Qt槽与C + +的签名`void verticalScrollbarAction(int)`。

```
QAbstractItemView.verticalScrollbarValueChanged (self, int value)
```

这种方法也是一个Qt槽与C + +的签名`void verticalScrollbarValueChanged(int)`。

```
ScrollMode QAbstractItemView.verticalScrollMode (self)
```

[

```
int QAbstractItemView.verticalStepsPerItem (self)
```

](qabstractitemview.html#ScrollMode-enum)

```
QStyleOptionViewItem QAbstractItemView.viewOptions (self)
```

[](qstyleoptionviewitem.html)

[返回](qstyleoptionviewitem.html)[QStyleOptionViewItem](qstyleoptionviewitem.html)结构填充视图的调色板，字体，状态，线路走向等。

```
bool QAbstractItemView.viewportEvent (self, QEvent e)
```

从重新实现[QAbstractScrollArea.viewportEvent](qabstractscrollarea.html#viewportEvent)（ ） 。

这个函数是用来处理工具提示，并这是什么？模式时，如果给定的_event_是[QEvent.ToolTip](qevent.html#Type-enum)或[QEvent.WhatsThis](qevent.html#Type-enum)。它传递给它的基类viewportEvent （）处理所有其他事件。

```
QRect QAbstractItemView.visualRect (self, QModelIndex index)
```

[

这种方法是抽象的，应在任何子类中重新实现。

返回矩形上通过了该项目所佔用的视_index_。

如果你的项目会显示在几个方面，然后visualRect应该返回一个包含索引，而不是完整的区域指数可能包括，触摸或导致绘图的主要区域。

在基类中，这是一个纯虚函数。

](qrect.html)

[**See also**](qrect.html) [indexAt](qabstractitemview.html#indexAt)（）和[visualRegionForSelection](qabstractitemview.html#visualRegionForSelection)（ ） 。

```
QRegion QAbstractItemView.visualRegionForSelection (self, QItemSelection selection)
```

[

这种方法是抽象的，应在任何子类中重新实现。

从在给定的项目的视口返回区域_selection_。

在基类中，这是一个纯虚函数。

](qregion.html)

[**See also**](qregion.html) [visualRect](qabstractitemview.html#visualRect)（）和[selectedIndexes](qabstractitemview.html#selectedIndexes)（ ） 。

* * *

## Qt Signal Documentation

```
void activated (const QModelIndex&)
```

这是该信号的默认超载。

当指定的项目，该信号被发射_index_由用户激活。如何激活项目取决于平台，例如，通过单或双击该项目，或按回车键该项目是目前的当。

**See also** [clicked](qabstractitemview.html#clicked)（ ）[doubleClicked](qabstractitemview.html#doubleClicked)（ ）[entered](qabstractitemview.html#entered)（）和[pressed](qabstractitemview.html#pressed)（ ） 。

```
void clicked (const QModelIndex&)
```

这是该信号的默认超载。

单击鼠标按钮时，这个信号被发射。鼠标被点击的项目是由指定的_index_。当索引是有效的信号只发射。

**See also** [activated](qabstractitemview.html#activated)（ ）[doubleClicked](qabstractitemview.html#doubleClicked)（ ）[entered](qabstractitemview.html#entered)（）和[pressed](qabstractitemview.html#pressed)（ ） 。

```
void doubleClicked (const QModelIndex&)
```

这是该信号的默认超载。

当鼠标按钮被双击这个信号被发射。鼠标被双击的项目是由指定的_index_。当索引是有效的信号只发射。

**See also** [clicked](qabstractitemview.html#clicked)（）和[activated](qabstractitemview.html#activated)（ ） 。

```
void entered (const QModelIndex&)
```

这是该信号的默认超载。

当鼠标光标进入由指定的项目，这个信号被发射_index_。鼠标跟踪需要启用此功能工作。

**See also** [viewportEntered](qabstractitemview.html#viewportEntered)（ ）[activated](qabstractitemview.html#activated)（ ）[clicked](qabstractitemview.html#clicked)（ ）[doubleClicked](qabstractitemview.html#doubleClicked)（）和[pressed](qabstractitemview.html#pressed)（ ） 。

```
void pressed (const QModelIndex&)
```

这是该信号的默认超载。

当按下鼠标按键，这个信号被发射。鼠标被按下的项目是由指定的_index_。当索引是有效的信号只发射。

使用[QApplication.mouseButtons](qapplication.html#mouseButtons)（ ）函数来获得鼠标按钮的状态。

**See also** [activated](qabstractitemview.html#activated)（ ）[clicked](qabstractitemview.html#clicked)（ ）[doubleClicked](qabstractitemview.html#doubleClicked)（）和[entered](qabstractitemview.html#entered)（ ） 。

```
void viewportEntered ()
```

这是该信号的默认超载。

当鼠标光标进入视这个信号被发射。鼠标跟踪需要启用此功能工作。

**See also** [entered](qabstractitemview.html#entered)（ ） 。