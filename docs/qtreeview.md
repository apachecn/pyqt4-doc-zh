# QTreeView Class Reference

## [[QtGui](index.htm) module]

该QTreeView则类提供了一个默认的模型/视图实现树形视图中。[More...](#details)

继承[QAbstractItemView](qabstractitemview.html)。

通过继承[QHelpContentWidget](qhelpcontentwidget.html)和[QTreeWidget](qtreewidget.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `bool allColumnsShowFocus (self)`
*   `int autoExpandDelay (self)`
*   `collapse (self, QModelIndex index)`
*   `collapseAll (self)`
*   `int columnAt (self, int x)`
*   `columnCountChanged (self, int oldCount, int newCount)`
*   `columnMoved (self)`
*   `columnResized (self, int column, int oldSize, int newSize)`
*   `int columnViewportPosition (self, int column)`
*   `int columnWidth (self, int column)`
*   `currentChanged (self, QModelIndex current, QModelIndex previous)`
*   `dataChanged (self, QModelIndex topLeft, QModelIndex bottomRight)`
*   `dragMoveEvent (self, QDragMoveEvent event)`
*   `drawBranches (self, QPainter painter, QRect rect, QModelIndex index)`
*   `drawRow (self, QPainter painter, QStyleOptionViewItem options, QModelIndex index)`
*   `drawTree (self, QPainter painter, QRegion region)`
*   `expand (self, QModelIndex index)`
*   `expandAll (self)`
*   `bool expandsOnDoubleClick (self)`
*   `expandToDepth (self, int depth)`
*   `QHeaderView header (self)`
*   `hideColumn (self, int column)`
*   `int horizontalOffset (self)`
*   `horizontalScrollbarAction (self, int action)`
*   `int indentation (self)`
*   `QModelIndex indexAbove (self, QModelIndex index)`
*   `QModelIndex indexAt (self, QPoint p)`
*   `QModelIndex indexBelow (self, QModelIndex index)`
*   `int indexRowSizeHint (self, QModelIndex index)`
*   `bool isAnimated (self)`
*   `bool isColumnHidden (self, int column)`
*   `bool isExpanded (self, QModelIndex index)`
*   `bool isFirstColumnSpanned (self, int row, QModelIndex parent)`
*   `bool isHeaderHidden (self)`
*   `bool isIndexHidden (self, QModelIndex index)`
*   `bool isRowHidden (self, int row, QModelIndex parent)`
*   `bool isSortingEnabled (self)`
*   `bool itemsExpandable (self)`
*   `keyboardSearch (self, QString search)`
*   `keyPressEvent (self, QKeyEvent event)`
*   `mouseDoubleClickEvent (self, QMouseEvent e)`
*   `mouseMoveEvent (self, QMouseEvent event)`
*   `mousePressEvent (self, QMouseEvent e)`
*   `mouseReleaseEvent (self, QMouseEvent event)`
*   `QModelIndex moveCursor (self, QAbstractItemView.CursorAction cursorAction, Qt.KeyboardModifiers modifiers)`
*   `paintEvent (self, QPaintEvent e)`
*   `reexpand (self)`
*   `reset (self)`
*   `resizeColumnToContents (self, int column)`
*   `bool rootIsDecorated (self)`
*   `int rowHeight (self, QModelIndex index)`
*   `rowsAboutToBeRemoved (self, QModelIndex parent, int start, int end)`
*   `rowsInserted (self, QModelIndex parent, int start, int end)`
*   `rowsRemoved (self, QModelIndex parent, int first, int last)`
*   `scrollContentsBy (self, int dx, int dy)`
*   `scrollTo (self, QModelIndex index, QAbstractItemView.ScrollHint hint = QAbstractItemView.EnsureVisible)`
*   `selectAll (self)`
*   `list-of-QModelIndex selectedIndexes (self)`
*   `selectionChanged (self, QItemSelection selected, QItemSelection deselected)`
*   `setAllColumnsShowFocus (self, bool enable)`
*   `setAnimated (self, bool enable)`
*   `setAutoExpandDelay (self, int delay)`
*   `setColumnHidden (self, int column, bool hide)`
*   `setColumnWidth (self, int column, int width)`
*   `setExpanded (self, QModelIndex index, bool expand)`
*   `setExpandsOnDoubleClick (self, bool enable)`
*   `setFirstColumnSpanned (self, int row, QModelIndex parent, bool span)`
*   `setHeader (self, QHeaderView header)`
*   `setHeaderHidden (self, bool hide)`
*   `setIndentation (self, int i)`
*   `setItemsExpandable (self, bool enable)`
*   `setModel (self, QAbstractItemModel model)`
*   `setRootIndex (self, QModelIndex index)`
*   `setRootIsDecorated (self, bool show)`
*   `setRowHidden (self, int row, QModelIndex parent, bool hide)`
*   `setSelection (self, QRect rect, QItemSelectionModel.SelectionFlags command)`
*   `setSelectionModel (self, QItemSelectionModel selectionModel)`
*   `setSortingEnabled (self, bool enable)`
*   `setUniformRowHeights (self, bool uniform)`
*   `setWordWrap (self, bool on)`
*   `showColumn (self, int column)`
*   `int sizeHintForColumn (self, int column)`
*   `sortByColumn (self, int column)`
*   `sortByColumn (self, int column, Qt.SortOrder order)`
*   `timerEvent (self, QTimerEvent event)`
*   `bool uniformRowHeights (self)`
*   `updateGeometries (self)`
*   `int verticalOffset (self)`
*   `bool viewportEvent (self, QEvent event)`
*   `QRect visualRect (self, QModelIndex index)`
*   `QRegion visualRegionForSelection (self, QItemSelection selection)`
*   `bool wordWrap (self)`

### Qt Signals

*   `void collapsed (const QModelIndex&)`
*   `void expanded (const QModelIndex&)`

* * *

## Detailed Description

该QTreeView则类提供了一个默认的模型/视图实现树形视图中。

一个QTreeView则实现了从模型项目的树表示。这个类是用来提供以前由提供的标准分层列表`QListView`类，但使用Qt的模型/视图结构中提供的更灵活的方法。

在QTreeView则类是一个[Model/View Classes](index.htm)并且是Qt的一部分[model/view framework](index.htm)。

QTreeView则实现由定义的接口[QAbstractItemView](qabstractitemview.html)类以允许其显示由从派生模型提供数据[QAbstractItemModel](qabstractitemmodel.html)类。

它是简单的构造一个树形视图中显示从模型数据。在下面的例子中，目录中的内容是由供给[QFileSystemModel](qfilesystemmodel.html)并显示为一个树：

```
     [QFileSystemModel](qfilesystemmodel.html) *model = new [QFileSystemModel](qfilesystemmodel.html);
     model->setRootPath([QDir](qdir.html).currentPath());
     QTreeView *tree = new QTreeView(splitter);
     tree->setModel(model);

```

该模型/视图结构保证了树视图中的内容被更新模型的变化。

有孩子的项目可以在一个扩展的（孩子是可见的）或折叠（隐藏子项）的状态。在这种状态下改变了[collapsed](qtreeview.html#collapsed)（）或[expanded](qtreeview.html#expanded)（）信号被发射的相关项的模型索引。

在用来表示层次结构级别的缩进量由控制[indentation](qtreeview.html#indentation-prop)属性。

在树视图标头使用的构造[QHeaderView](qheaderview.html)类，并且可以使用被隐藏`header()-&gt;hide()`。请注意，每个头被配置成与它的[stretchLastSection](qheaderview.html#stretchLastSection-prop)属性设置为True ，以确保该视图不会浪费任何分配给它，它的头部空间。如果这个值被设置为True ，则此属性将复盖调整大小模式标头中的最后一节设置。

### Key Bindings

QTreeView则支持一组键绑定，使用户能够在浏览视图，并与项目的内容进行交互的：

| Key | Action |
| --- | --- |
| Up | Moves the cursor to the item in the same column on the previous row. If the parent of the current item has no more rows to navigate to, the cursor moves to the relevant item in the last row of the sibling that precedes the parent. |
| Down | Moves the cursor to the item in the same column on the next row. If the parent of the current item has no more rows to navigate to, the cursor moves to the relevant item in the first row of the sibling that follows the parent. |
| Left | Hides the children of the current item (if present) by collapsing a branch. |
| Minus | Same as LeftArrow. |
| Right | Reveals the children of the current item (if present) by expanding a branch. |
| Plus | Same as RightArrow. |
| Asterisk | Expands all children of the current item (if present). |
| PageUp | Moves the cursor up one page. |
| PageDown | Moves the cursor down one page. |
| Home | Moves the cursor to an item in the same column of the first row of the first top-level item in the model. |
| End | Moves the cursor to an item in the same column of the last row of the last top-level item in the model. |
| F2 | In editable models, this opens the current item for editing. The Escape key can be used to cancel the editing process and revert any changes to the data displayed. |

| ![Screenshot of a Windows XP style tree view](../img/windowsxp-treeview.png) | ![Screenshot of a Macintosh style tree view](../img/macintosh-treeview.png) | ![Screenshot of a Plastique style tree view](../img/plastique-treeview.png) |
| A [Windows XP style](index.htm) tree view. | A [Macintosh style](index.htm) tree view. | A [Plastique style](index.htm) tree view. |

### Improving Performance

它可以给出关于它正在处理，以便显示大量项目时，以改善其性能的数据的视图的提示。可以采取一种方法对于旨在与高度相等显示项目的观点是设置[uniformRowHeights](qtreeview.html#uniformRowHeights-prop)属性设置为True 。

* * *

## Method Documentation

```
QTreeView.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个树视图与_parent_来表示模型的数据。使用[setModel](qtreeview.html#setModel)（）来设定模型。

**See also** [QAbstractItemModel](qabstractitemmodel.html)。

```
bool QTreeView.allColumnsShowFocus (self)
```

```
int QTreeView.autoExpandDelay (self)
```

```
QTreeView.collapse (self, QModelIndex index)
```

这种方法也是一个Qt槽与C + +的签名`void collapse(const QModelIndex&)`。

折叠由指定的模型项目_index_。

**See also** [collapsed](qtreeview.html#collapsed)（ ） 。

```
QTreeView.collapseAll (self)
```

这种方法也是一个Qt槽与C + +的签名`void collapseAll()`。

折叠所有展开的项目。

这个函数中引入了Qt 4.2中。

**See also** [expandAll](qtreeview.html#expandAll)（ ）[expand](qtreeview.html#expand)（ ）[collapse](qtreeview.html#collapse)（）和[setExpanded](qtreeview.html#setExpanded)（ ） 。

```
int QTreeView.columnAt (self, int x)
```

返回在树视图中的列，其标题复盖_x_坐标给出。

```
QTreeView.columnCountChanged (self, int oldCount, int newCount)
```

这种方法也是一个Qt槽与C + +的签名`void columnCountChanged(int,int)`。

通知树视图中的树视图中的列数已经从_oldCount_至_newCount_。

```
QTreeView.columnMoved (self)
```

这种方法也是一个Qt槽与C + +的签名`void columnMoved()`。

这个槽被调用，每当一列已被移动。

```
QTreeView.columnResized (self, int column, int oldSize, int newSize)
```

这种方法也是一个Qt槽与C + +的签名`void columnResized(int,int,int)`。

这个函数被调用时_column_的大小在头改变。_oldSize_和_newSize_给先前的大小和新的像素大小。

**See also** [setColumnWidth](qtreeview.html#setColumnWidth)（ ） 。

```
int QTreeView.columnViewportPosition (self, int column)
```

返回的水平位置_column_在视口中。

```
int QTreeView.columnWidth (self, int column)
```

返回的宽度_column_。

**See also** [resizeColumnToContents](qtreeview.html#resizeColumnToContents)（）和[setColumnWidth](qtreeview.html#setColumnWidth)（ ） 。

```
QTreeView.currentChanged (self, QModelIndex current, QModelIndex previous)
```

从重新实现[QAbstractItemView.currentChanged](qabstractitemview.html#currentChanged)（ ） 。

```
QTreeView.dataChanged (self, QModelIndex topLeft, QModelIndex bottomRight)
```

这种方法也是一个Qt槽与C + +的签名`void dataChanged(const QModelIndex&,const QModelIndex&)`。

从重新实现[QAbstractItemView.dataChanged](qabstractitemview.html#dataChanged)（ ） 。

```
QTreeView.dragMoveEvent (self, QDragMoveEvent event)
```

从重新实现[QWidget.dragMoveEvent](qwidget.html#dragMoveEvent)（ ） 。

```
QTreeView.drawBranches (self, QPainter painter, QRect rect, QModelIndex index)
```

绘制树枝在树视图中的同一行的模型项目_index_使用_painter_给出。该分支绘制由指定的矩形_rect_。

```
QTreeView.drawRow (self, QPainter painter, QStyleOptionViewItem options, QModelIndex index)
```

在绘制包含模型项树视图中的列_index_使用_painter_给出。该_option_控制如何显示该项目。

**See also** [setAlternatingRowColors](qabstractitemview.html#alternatingRowColors-prop)（ ） 。

```
QTreeView.drawTree (self, QPainter painter, QRegion region)
```

绘制树的相交给定的部分_region_使用指定的_painter_。

这个函数中引入了Qt 4.2中。

**See also** [paintEvent](qtreeview.html#paintEvent)（ ） 。

```
QTreeView.expand (self, QModelIndex index)
```

这种方法也是一个Qt槽与C + +的签名`void expand(const QModelIndex&)`。

扩大由指定的模型项目_index_。

**See also** [expanded](qtreeview.html#expanded)（ ） 。

```
QTreeView.expandAll (self)
```

这种方法也是一个Qt槽与C + +的签名`void expandAll()`。

展开所有扩展项目。

警告：如果模型中包含了大量的项目，此功能需要一定的时间来执行。

这个函数中引入了Qt 4.2中。

**See also** [collapseAll](qtreeview.html#collapseAll)（ ）[expand](qtreeview.html#expand)（ ）[collapse](qtreeview.html#collapse)（）和[setExpanded](qtreeview.html#setExpanded)（ ） 。

```
bool QTreeView.expandsOnDoubleClick (self)
```

```
QTreeView.expandToDepth (self, int depth)
```

这种方法也是一个Qt槽与C + +的签名`void expandToDepth(int)`。

展开所有的项目扩展到给定_depth_。

此功能被引入Qt的4.3 。

**See also** [expandAll](qtreeview.html#expandAll)（ ）[collapseAll](qtreeview.html#collapseAll)（ ）[expand](qtreeview.html#expand)（ ）[collapse](qtreeview.html#collapse)（）和[setExpanded](qtreeview.html#setExpanded)（ ） 。

```
QHeaderView QTreeView.header (self)
```

[

返回树状视图的标题。

](qheaderview.html)

[**See also**](qheaderview.html) [setHeader](qtreeview.html#setHeader)（）和[QAbstractItemModel.headerData](qabstractitemmodel.html#headerData)（ ） 。

```
QTreeView.hideColumn (self, int column)
```

这种方法也是一个Qt槽与C + +的签名`void hideColumn(int)`。

隐藏_column_给出。

**Note:**此功能只应调用该模型已被初始化后，如认为需要知道为了隐藏列数_column_。

**See also** [showColumn](qtreeview.html#showColumn)（）和[setColumnHidden](qtreeview.html#setColumnHidden)（ ） 。

```
int QTreeView.horizontalOffset (self)
```

从重新实现[QAbstractItemView.horizontalOffset](qabstractitemview.html#horizontalOffset)（ ） 。

返回水平的树形视图中的项目所抵销。

需要注意的是树视图使用水平标题部分的位置来确定的列在视图中的位置。

**See also** [verticalOffset](qtreeview.html#verticalOffset)（ ） 。

```
QTreeView.horizontalScrollbarAction (self, int action)
```

```
int QTreeView.indentation (self)
```

```
QModelIndex QTreeView.indexAbove (self, QModelIndex index)
```

[

返回上述项目的模型索引_index_。

](qmodelindex.html)

```
QModelIndex QTreeView.indexAt (self, QPoint p)
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemView.indexAt](qabstractitemview.html#indexAt)（ ） 。

```
QModelIndex QTreeView.indexBelow (self, QModelIndex index)
```

[

返回下面的项的模型索引_index_。

```
int QTreeView.indexRowSizeHint (self, QModelIndex index)
```

返回尺寸暗示由指定的行_index_。

](qmodelindex.html)

[**See also**](qmodelindex.html) [sizeHintForColumn](qtreeview.html#sizeHintForColumn)（）和[uniformRowHeights](qtreeview.html#uniformRowHeights-prop)（ ） 。

```
bool QTreeView.isAnimated (self)
```

```
bool QTreeView.isColumnHidden (self, int column)
```

返回True如果_column_被隐藏，否则返回False 。

**See also** [hideColumn](qtreeview.html#hideColumn)（）和[isRowHidden](qtreeview.html#isRowHidden)（ ） 。

```
bool QTreeView.isExpanded (self, QModelIndex index)
```

返回True如果模型项目_index_为扩大;否则返回False。

**See also** [expand](qtreeview.html#expand)（ ）[expanded](qtreeview.html#expanded)（）和[setExpanded](qtreeview.html#setExpanded)（ ） 。

```
bool QTreeView.isFirstColumnSpanned (self, int row, QModelIndex parent)
```

返回True如果在给定的第一列中的项_row_的_parent_是跨越所有的列，否则返回False 。

此功能被引入Qt的4.3 。

**See also** [setFirstColumnSpanned](qtreeview.html#setFirstColumnSpanned)（ ） 。

```
bool QTreeView.isHeaderHidden (self)
```

```
bool QTreeView.isIndexHidden (self, QModelIndex index)
```

从重新实现[QAbstractItemView.isIndexHidden](qabstractitemview.html#isIndexHidden)（ ） 。

```
bool QTreeView.isRowHidden (self, int row, QModelIndex parent)
```

返回True如果该项目在给定_row_的_parent_被隐藏，否则返回False 。

**See also** [setRowHidden](qtreeview.html#setRowHidden)（）和[isColumnHidden](qtreeview.html#isColumnHidden)（ ） 。

```
bool QTreeView.isSortingEnabled (self)
```

```
bool QTreeView.itemsExpandable (self)
```

```
QTreeView.keyboardSearch (self, QString search)
```

从重新实现[QAbstractItemView.keyboardSearch](qabstractitemview.html#keyboardSearch)（ ） 。

```
QTreeView.keyPressEvent (self, QKeyEvent event)
```

从重新实现[QWidget.keyPressEvent](qwidget.html#keyPressEvent)（ ） 。

```
QTreeView.mouseDoubleClickEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mouseDoubleClickEvent](qwidget.html#mouseDoubleClickEvent)（ ） 。

```
QTreeView.mouseMoveEvent (self, QMouseEvent event)
```

从重新实现[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

```
QTreeView.mousePressEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

```
QTreeView.mouseReleaseEvent (self, QMouseEvent event)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

```
QModelIndex QTreeView.moveCursor (self, QAbstractItemView.CursorAction cursorAction, Qt.KeyboardModifiers modifiers)
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemView.moveCursor](qabstractitemview.html#moveCursor)（ ） 。

移动光标在所描述的方式_cursorAction_使用由按键提供的信息_modifiers_。

```
QTreeView.paintEvent (self, QPaintEvent e)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QTreeView.reexpand (self)
```

这种方法也是一个Qt槽与C + +的签名`void reexpand()`。

```
QTreeView.reset (self)
```

从重新实现[QAbstractItemView.reset](qabstractitemview.html#reset)（ ） 。

```
QTreeView.resizeColumnToContents (self, int column)
```

这种方法也是一个Qt槽与C + +的签名`void resizeColumnToContents(int)`。

在调整大小_column_提供给它的内容的大小。

**See also** [columnWidth](qtreeview.html#columnWidth)（）和[setColumnWidth](qtreeview.html#setColumnWidth)（ ） 。

```
bool QTreeView.rootIsDecorated (self)
```

```
int QTreeView.rowHeight (self, QModelIndex index)
```

返回该行的由给定的表示的高度_index_。

此功能被引入Qt的4.3 。

**See also** [indexRowSizeHint](qtreeview.html#indexRowSizeHint)（ ） 。

```
QTreeView.rowsAboutToBeRemoved (self, QModelIndex parent, int start, int end)
```

从重新实现[QAbstractItemView.rowsAboutToBeRemoved](qabstractitemview.html#rowsAboutToBeRemoved)（ ） 。

通知认为，从行_start_排在_end_行所包含的是关于从给定的删除_parent_模型项目。

```
QTreeView.rowsInserted (self, QModelIndex parent, int start, int end)
```

从重新实现[QAbstractItemView.rowsInserted](qabstractitemview.html#rowsInserted)（ ） 。

通知认为，从行_start_排在_end_行包已被插入到_parent_模型项目。

```
QTreeView.rowsRemoved (self, QModelIndex parent, int first, int last)
```

这种方法也是一个Qt槽与C + +的签名`void rowsRemoved(const QModelIndex&,int,int)`。

通知认为，从行_start_排在_end_行包被从给定的删除_parent_模型项目。

这个函数是Qt 4.1中引入。

```
QTreeView.scrollContentsBy (self, int dx, int dy)
```

从重新实现[QAbstractScrollArea.scrollContentsBy](qabstractscrollarea.html#scrollContentsBy)（ ） 。

由（滚动树视图中的内容_dx_，_dy_） 。

```
QTreeView.scrollTo (self, QModelIndex index, QAbstractItemView.ScrollHint hint = QAbstractItemView.EnsureVisible)
```

从重新实现[QAbstractItemView.scrollTo](qabstractitemview.html#scrollTo)（ ） 。

滚动树视图中的内容，直到给定的模型项目_index_是可见的。该_hint_参数指定更精确而该项目应位于操作之后。如果任何模型项的父母都崩溃了，他们将扩大，以确保模型项目是可见的。

```
QTreeView.selectAll (self)
```

这种方法也是一个Qt槽与C + +的签名`void selectAll()`。

从重新实现[QAbstractItemView.selectAll](qabstractitemview.html#selectAll)（ ） 。

```
list-of-QModelIndex QTreeView.selectedIndexes (self)
```

从重新实现[QAbstractItemView.selectedIndexes](qabstractitemview.html#selectedIndexes)（ ） 。

```
QTreeView.selectionChanged (self, QItemSelection selected, QItemSelection deselected)
```

从重新实现[QAbstractItemView.selectionChanged](qabstractitemview.html#selectionChanged)（ ） 。

```
QTreeView.setAllColumnsShowFocus (self, bool enable)
```

```
QTreeView.setAnimated (self, bool enable)
```

```
QTreeView.setAutoExpandDelay (self, int delay)
```

```
QTreeView.setColumnHidden (self, int column, bool hide)
```

If _hide_是真实的_column_是隐藏的，否则，_column_示。

**See also** [isColumnHidden](qtreeview.html#isColumnHidden)（ ）[hideColumn](qtreeview.html#hideColumn)（）和[setRowHidden](qtreeview.html#setRowHidden)（ ） 。

```
QTreeView.setColumnWidth (self, int column, int width)
```

设定的给定的宽度_column_到_width_规定。

这个函数中引入了Qt 4.2中。

**See also** [columnWidth](qtreeview.html#columnWidth)（）和[resizeColumnToContents](qtreeview.html#resizeColumnToContents)（ ） 。

```
QTreeView.setExpanded (self, QModelIndex index, bool expand)
```

设置项转交_index_要么崩溃或膨胀，这取决于的值_expanded_。

**See also** [expanded](qtreeview.html#expanded)（ ）[expand](qtreeview.html#expand)（）和[isExpanded](qtreeview.html#isExpanded)（ ） 。

```
QTreeView.setExpandsOnDoubleClick (self, bool enable)
```

```
QTreeView.setFirstColumnSpanned (self, int row, QModelIndex parent, bool span)
```

If _span_是真正的产品中的第一列_row_用给定的_parent_设置为跨越所有列，否则，所有的项目_row_示。

此功能被引入Qt的4.3 。

**See also** [isFirstColumnSpanned](qtreeview.html#isFirstColumnSpanned)（ ） 。

```
QTreeView.setHeader (self, QHeaderView header)
```

该_header_说法有它的所有权转移给Qt的。

设置树视图的标题，给定_header_。

该视图取得所有权在给定_header_并删除它，当一个新的头被设置。

**See also** [QAbstractItemModel.headerData](qabstractitemmodel.html#headerData)（ ） 。

```
QTreeView.setHeaderHidden (self, bool hide)
```

```
QTreeView.setIndentation (self, int i)
```

```
QTreeView.setItemsExpandable (self, bool enable)
```

```
QTreeView.setModel (self, QAbstractItemModel model)
```

从重新实现[QAbstractItemView.setModel](qabstractitemview.html#setModel)（ ） 。

```
QTreeView.setRootIndex (self, QModelIndex index)
```

从重新实现[QAbstractItemView.setRootIndex](qabstractitemview.html#setRootIndex)（ ） 。

```
QTreeView.setRootIsDecorated (self, bool show)
```

```
QTreeView.setRowHidden (self, int row, QModelIndex parent, bool hide)
```

If _hide_是真实的_row_用给定的_parent_是隐藏的，否则，_row_示。

**See also** [isRowHidden](qtreeview.html#isRowHidden)（）和[setColumnHidden](qtreeview.html#setColumnHidden)（ ） 。

```
QTreeView.setSelection (self, QRect rect, QItemSelectionModel.SelectionFlags command)
```

从重新实现[QAbstractItemView.setSelection](qabstractitemview.html#setSelection)（ ） 。

适用的选择_command_在项目或由矩形触摸时，_rect_。

**See also** [selectionCommand](qabstractitemview.html#selectionCommand)（ ） 。

```
QTreeView.setSelectionModel (self, QItemSelectionModel selectionModel)
```

从重新实现[QAbstractItemView.setSelectionModel](qabstractitemview.html#setSelectionModel)（ ） 。

```
QTreeView.setSortingEnabled (self, bool enable)
```

```
QTreeView.setUniformRowHeights (self, bool uniform)
```

```
QTreeView.setWordWrap (self, bool on)
```

```
QTreeView.showColumn (self, int column)
```

这种方法也是一个Qt槽与C + +的签名`void showColumn(int)`。

显示了给定的_column_在树视图中。

**See also** [hideColumn](qtreeview.html#hideColumn)（）和[setColumnHidden](qtreeview.html#setColumnHidden)（ ） 。

```
int QTreeView.sizeHintForColumn (self, int column)
```

从重新实现[QAbstractItemView.sizeHintForColumn](qabstractitemview.html#sizeHintForColumn)（ ） 。

返回尺寸暗示的_column_的宽度或-1 ，如果没有模型。

如果你需要一个给定列的宽度设置为一个固定值，调用[QHeaderView.resizeSection](qheaderview.html#resizeSection)（ ）在视图的标题。

如果在子类中重新实现这个功能，请注意您返回值时只使用[resizeColumnToContents](qtreeview.html#resizeColumnToContents)（）被调用。在这种情况下，如果一个更大的列宽，需要通过两种视图的页眉或项目委讬，该宽度将被代替使用。

**See also** [QWidget.sizeHint](qwidget.html#sizeHint-prop)和[header](qtreeview.html#header)（ ） 。

```
QTreeView.sortByColumn (self, int column)
```

这种方法也是一个Qt槽与C + +的签名`void sortByColumn(int)`。

设定模型向上通过在给定的值进行排序_column_和_order_。

_column_可能是-1 ，在这种情况下，不排序指示器将显示与该模型将回到它的自然，未排序的顺序。请注意，并非所有型号都支持这一点，甚至可能会崩溃在这种情况下。

这个函数中引入了Qt 4.2中。

**See also** [sortingEnabled](qtreeview.html#sortingEnabled-prop)。

```
QTreeView.sortByColumn (self, int column, Qt.SortOrder order)
```

```
QTreeView.timerEvent (self, QTimerEvent event)
```

从重新实现[QObject.timerEvent](qobject.html#timerEvent)（ ） 。

```
bool QTreeView.uniformRowHeights (self)
```

```
QTreeView.updateGeometries (self)
```

从重新实现[QAbstractItemView.updateGeometries](qabstractitemview.html#updateGeometries)（ ） 。

```
int QTreeView.verticalOffset (self)
```

从重新实现[QAbstractItemView.verticalOffset](qabstractitemview.html#verticalOffset)（ ） 。

返回垂直的树视图中项目的偏移。

**See also** [horizontalOffset](qtreeview.html#horizontalOffset)（ ） 。

```
bool QTreeView.viewportEvent (self, QEvent event)
```

从重新实现[QAbstractScrollArea.viewportEvent](qabstractscrollarea.html#viewportEvent)（ ） 。

```
QRect QTreeView.visualRect (self, QModelIndex index)
```

[](qrect.html)

[从重新实现](qrect.html)[QAbstractItemView.visualRect](qabstractitemview.html#visualRect)（ ） 。

返回矩形上通过了该项目所佔用的视_index_。如果索引不可见或隐藏明确，返回的矩形是无效的。

```
QRegion QTreeView.visualRegionForSelection (self, QItemSelection selection)
```

[](qregion.html)

[从重新实现](qregion.html)[QAbstractItemView.visualRegionForSelection](qabstractitemview.html#visualRegionForSelection)（ ） 。

从在给定的项目的视口返回矩形_selection_。

由于4.7 ，返回的区域仅包含矩形相交（或计入）的视口。

```
bool QTreeView.wordWrap (self)
```

* * *

## Qt Signal Documentation

```
void collapsed (const QModelIndex&)
```

这是该信号的默认超载。

当指定的项目，该信号被发射_index_已展开。

```
void expanded (const QModelIndex&)
```

这是该信号的默认超载。

当指定的项目，该信号被发射_index_已展开。

**See also** [setExpanded](qtreeview.html#setExpanded)（ ） 。