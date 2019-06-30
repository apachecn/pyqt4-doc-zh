# QTableView Class Reference

## [[QtGui](index.htm) module]

在QTableView中的类提供了默认的模型/视图实现表视图中。[More...](#details)

继承[QAbstractItemView](qabstractitemview.html)。

通过继承[QTableWidget](qtablewidget.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `clearSpans (self)`
*   `int columnAt (self, int x)`
*   `columnCountChanged (self, int oldCount, int newCount)`
*   `columnMoved (self, int column, int oldIndex, int newIndex)`
*   `columnResized (self, int column, int oldWidth, int newWidth)`
*   `int columnSpan (self, int row, int column)`
*   `int columnViewportPosition (self, int column)`
*   `int columnWidth (self, int column)`
*   `currentChanged (self, QModelIndex current, QModelIndex previous)`
*   `Qt.PenStyle gridStyle (self)`
*   `hideColumn (self, int column)`
*   `hideRow (self, int row)`
*   `QHeaderView horizontalHeader (self)`
*   `int horizontalOffset (self)`
*   `horizontalScrollbarAction (self, int action)`
*   `QModelIndex indexAt (self, QPoint p)`
*   `bool isColumnHidden (self, int column)`
*   `bool isCornerButtonEnabled (self)`
*   `bool isIndexHidden (self, QModelIndex index)`
*   `bool isRowHidden (self, int row)`
*   `bool isSortingEnabled (self)`
*   `QModelIndex moveCursor (self, QAbstractItemView.CursorAction cursorAction, Qt.KeyboardModifiers modifiers)`
*   `paintEvent (self, QPaintEvent e)`
*   `resizeColumnsToContents (self)`
*   `resizeColumnToContents (self, int column)`
*   `resizeRowsToContents (self)`
*   `resizeRowToContents (self, int row)`
*   `int rowAt (self, int y)`
*   `rowCountChanged (self, int oldCount, int newCount)`
*   `int rowHeight (self, int row)`
*   `rowMoved (self, int row, int oldIndex, int newIndex)`
*   `rowResized (self, int row, int oldHeight, int newHeight)`
*   `int rowSpan (self, int row, int column)`
*   `int rowViewportPosition (self, int row)`
*   `scrollContentsBy (self, int dx, int dy)`
*   `scrollTo (self, QModelIndex index, QAbstractItemView.ScrollHint hint = QAbstractItemView.EnsureVisible)`
*   `selectColumn (self, int column)`
*   `list-of-QModelIndex selectedIndexes (self)`
*   `selectionChanged (self, QItemSelection selected, QItemSelection deselected)`
*   `selectRow (self, int row)`
*   `setColumnHidden (self, int column, bool hide)`
*   `setColumnWidth (self, int column, int width)`
*   `setCornerButtonEnabled (self, bool enable)`
*   `setGridStyle (self, Qt.PenStyle style)`
*   `setHorizontalHeader (self, QHeaderView header)`
*   `setModel (self, QAbstractItemModel model)`
*   `setRootIndex (self, QModelIndex index)`
*   `setRowHeight (self, int row, int height)`
*   `setRowHidden (self, int row, bool hide)`
*   `setSelection (self, QRect rect, QItemSelectionModel.SelectionFlags command)`
*   `setSelectionModel (self, QItemSelectionModel selectionModel)`
*   `setShowGrid (self, bool show)`
*   `setSortingEnabled (self, bool enable)`
*   `setSpan (self, int row, int column, int rowSpan, int columnSpan)`
*   `setVerticalHeader (self, QHeaderView header)`
*   `setWordWrap (self, bool on)`
*   `showColumn (self, int column)`
*   `bool showGrid (self)`
*   `showRow (self, int row)`
*   `int sizeHintForColumn (self, int column)`
*   `int sizeHintForRow (self, int row)`
*   `sortByColumn (self, int column)`
*   `sortByColumn (self, int column, Qt.SortOrder order)`
*   `timerEvent (self, QTimerEvent event)`
*   `updateGeometries (self)`
*   `QHeaderView verticalHeader (self)`
*   `int verticalOffset (self)`
*   `verticalScrollbarAction (self, int action)`
*   `QStyleOptionViewItem viewOptions (self)`
*   `QRect visualRect (self, QModelIndex index)`
*   `QRegion visualRegionForSelection (self, QItemSelection selection)`
*   `bool wordWrap (self)`

* * *

## Detailed Description

在QTableView中的类提供了默认的模型/视图实现表视图中。

一个QTableView中实现了显示从模型项目的表视图。这个类是用来提供以前由提供的标准表[QTable](index.htm#qtable)类，但使用Qt的模型/视图结构中提供的更灵活的方法。

在QTableView中类是一个[Model/View Classes](index.htm)并且是Qt的一部分[model/view framework](index.htm)。

QTableView中实现由定义的接口[QAbstractItemView](qabstractitemview.html)类以允许其显示由从派生模型提供数据[QAbstractItemModel](qabstractitemmodel.html)类。

### Navigation

您可以通过点击一个单元格，用鼠标，或者使用箭头键导航的单元格在表中。因为QTableView中启用[tabKeyNavigation](qabstractitemview.html#tabKeyNavigation-prop)默认情况下，你也可以按下Tab键和BACKTAB移动从细胞到细胞。

### Visual Appearance

该表具有可利用以下方式获得一个垂直头中的[verticalHeader](qtableview.html#verticalHeader)（）函数，和一个水平标头，可通过[horizontalHeader](qtableview.html#horizontalHeader)（）函数。表中的每一行的高度可以通过使用被发现[rowHeight](qtableview.html#rowHeight)（）;类似地，列的宽度可以通过使用发现[columnWidth](qtableview.html#columnWidth)（ ） 。由于这两个都是普通的小工具，你可以使用隐藏其中任何一个的[hide](qwidget.html#hide)（）函数。

行和列可以隐藏和显示[hideRow](qtableview.html#hideRow)（ ）[hideColumn](qtableview.html#hideColumn)（ ）[showRow](qtableview.html#showRow)（）和[showColumn](qtableview.html#showColumn)（ ） 。它们可以与被选择[selectRow](qtableview.html#selectRow)（）和[selectColumn](qtableview.html#selectColumn)（ ） 。该表将显示一个网格取决于[showGrid](qtableview.html#showGrid-prop)属性。

在表视图中显示的项目，像那些在其他项目的意见，被渲染并使用标准编辑[delegates](qitemdelegate.html)。然而，对于某些任务它能够插入部件中的表而不是有时是有用的。 Widget是针对特定的索引设置与[setIndexWidget()](qabstractitemview.html#setIndexWidget)功能，后来与检索[indexWidget()](qabstractitemview.html#indexWidget)。

| ![](../img/qtableview-resized.png) | By default, the cells in a table do not expand to fill the available space.可以通过拉伸最后一个头部分使细胞填满可用空间。通过访问相关的头[horizontalHeader](qtableview.html#horizontalHeader)（）或[verticalHeader](qtableview.html#verticalHeader)（）和set头的[stretchLastSection](qheaderview.html#stretchLastSection-prop)属性。要根据每列或行的空间需求分配的可用空间，调用视图的[resizeColumnsToContents](qtableview.html#resizeColumnsToContents)（）或[resizeRowsToContents](qtableview.html#resizeRowsToContents)（）函数。 |

### Coordinate Systems

对于一些特殊形式的表它能够以行和列索引和widget的坐标之间的转换是非常有用的。该[rowAt](qtableview.html#rowAt)（）函数提供的指定行的视图中的y坐标;行索引可以被用来获取一个对应的y坐标[rowViewportPosition](qtableview.html#rowViewportPosition)（ ） 。该[columnAt](qtableview.html#columnAt)（）和[columnViewportPosition](qtableview.html#columnViewportPosition)（）函数提供x坐标和列索引之间的等效转换操作。

### Styles

QTableView中适当称呼为每个平台。下图显示它的外观在三个不同的平台。转到[Qt Widget Gallery](index.htm)看到它在其他样式的外观。

| ![Screenshot of a Windows XP style table view](../img/windowsxp-tableview.png) | ![Screenshot of a Macintosh style table view](../img/macintosh-tableview.png) | ![Screenshot of a Plastique style table view](../img/plastique-tableview.png) |
| A [Windows XP style](index.htm) table view. | A [Macintosh style](index.htm) table view. | A [Plastique style](index.htm) table view. |

* * *

## Method Documentation

```
QTableView.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个表格视图_parent_来表示数据。

**See also** [QAbstractItemModel](qabstractitemmodel.html)。

```
QTableView.clearSpans (self)
```

删除所有的行和列跨度的表格视图。

此功能被引入Qt的4.4 。

**See also** [setSpan](qtableview.html#setSpan)（ ） 。

```
int QTableView.columnAt (self, int x)
```

返回该塔，在其中给定的x坐标，_x_在内容坐标系的位置。

**Note:**该函数返回-1，如果给定的坐标是无效的（无柱） 。

**See also** [rowAt](qtableview.html#rowAt)（ ） 。

```
QTableView.columnCountChanged (self, int oldCount, int newCount)
```

这种方法也是一个Qt槽与C + +的签名`void columnCountChanged(int,int)`。

这个槽被调用时列添加或删除。由指定的列以前的数_oldCount_，由指定的列的新号码_newCount_。

```
QTableView.columnMoved (self, int column, int oldIndex, int newIndex)
```

这种方法也是一个Qt槽与C + +的签名`void columnMoved(int,int,int)`。

这个槽被调用来改变给定的索引_column_在表视图。旧索引由指定_oldIndex_，并且由新的索引_newIndex_。

**See also** [rowMoved](qtableview.html#rowMoved)（ ） 。

```
QTableView.columnResized (self, int column, int oldWidth, int newWidth)
```

这种方法也是一个Qt槽与C + +的签名`void columnResized(int,int,int)`。

这个槽被调用来改变给定的宽度_column_。旧的宽度由规定_oldWidth_，并且由新的宽度_newWidth_。

**See also** [rowResized](qtableview.html#rowResized)（ ） 。

```
int QTableView.columnSpan (self, int row, int column)
```

返回table元素的列跨度为（_row_，_column_） 。默认值是1 。

这个函数中引入了Qt 4.2中。

**See also** [setSpan](qtableview.html#setSpan)（）和[rowSpan](qtableview.html#rowSpan)（ ） 。

```
int QTableView.columnViewportPosition (self, int column)
```

返回给定的内容中x坐标坐标_column_。

```
int QTableView.columnWidth (self, int column)
```

返回给定的宽度_column_。

**See also** [setColumnWidth](qtableview.html#setColumnWidth)（ ）[resizeColumnToContents](qtableview.html#resizeColumnToContents)（）和[rowHeight](qtableview.html#rowHeight)（ ） 。

```
QTableView.currentChanged (self, QModelIndex current, QModelIndex previous)
```

从重新实现[QAbstractItemView.currentChanged](qabstractitemview.html#currentChanged)（ ） 。

```
Qt.PenStyle QTableView.gridStyle (self)
```

[

```
QTableView.hideColumn (self, int column)
```

这种方法也是一个Qt槽与C + +的签名`void hideColumn(int)`。

隐藏指定_column_。

](qt.html#PenStyle-enum)

[**See also**](qt.html#PenStyle-enum) [showColumn](qtableview.html#showColumn)（）和[hideRow](qtableview.html#hideRow)（ ） 。

```
QTableView.hideRow (self, int row)
```

这种方法也是一个Qt槽与C + +的签名`void hideRow(int)`。

隐藏指定_row_。

**See also** [showRow](qtableview.html#showRow)（）和[hideColumn](qtableview.html#hideColumn)（ ） 。

```
QHeaderView QTableView.horizontalHeader (self)
```

[

返回表视图的水平标题。

](qheaderview.html)

[**See also**](qheaderview.html) [setHorizontalHeader](qtableview.html#setHorizontalHeader)（ ）[verticalHeader](qtableview.html#verticalHeader)（）和[QAbstractItemModel.headerData](qabstractitemmodel.html#headerData)（ ） 。

```
int QTableView.horizontalOffset (self)
```

从重新实现[QAbstractItemView.horizontalOffset](qabstractitemview.html#horizontalOffset)（ ） 。

返回水平在表视图中的项目所抵销。

请注意，表视图使用水平标题部分的位置来确定的列在视图中的位置。

**See also** [verticalOffset](qtableview.html#verticalOffset)（ ） 。

```
QTableView.horizontalScrollbarAction (self, int action)
```

```
QModelIndex QTableView.indexAt (self, QPoint p)
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemView.indexAt](qabstractitemview.html#indexAt)（ ） 。

返回相应的模型项的索引位置在位置表项目_pos_在内容坐标。

```
bool QTableView.isColumnHidden (self, int column)
```

返回True如果给定的_column_被隐藏，否则返回False 。

**See also** [isRowHidden](qtableview.html#isRowHidden)（ ） 。

```
bool QTableView.isCornerButtonEnabled (self)
```

```
bool QTableView.isIndexHidden (self, QModelIndex index)
```

从重新实现[QAbstractItemView.isIndexHidden](qabstractitemview.html#isIndexHidden)（ ） 。

```
bool QTableView.isRowHidden (self, int row)
```

返回True如果给定的_row_被隐藏，否则返回False 。

**See also** [isColumnHidden](qtableview.html#isColumnHidden)（ ） 。

```
bool QTableView.isSortingEnabled (self)
```

```
QModelIndex QTableView.moveCursor (self, QAbstractItemView.CursorAction cursorAction, Qt.KeyboardModifiers modifiers)
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemView.moveCursor](qabstractitemview.html#moveCursor)（ ） 。

移动光标按照给定的_cursorAction_使用由所提供的信息_modifiers_。

**See also** [QAbstractItemView.CursorAction](qabstractitemview.html#CursorAction-enum)。

```
QTableView.paintEvent (self, QPaintEvent e)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

绘制表格收据上给定的油漆事件_event_。

```
QTableView.resizeColumnsToContents (self)
```

这种方法也是一个Qt槽与C + +的签名`void resizeColumnsToContents()`。

重新调整的基础上用来呈现在列的每个项目委讬的大小暗示的所有列。

```
QTableView.resizeColumnToContents (self, int column)
```

这种方法也是一个Qt槽与C + +的签名`void resizeColumnToContents(int)`。

调整大小给定的_column_根据用于呈现列中每个项目委讬的大小的提示。

**Note:**唯一可见的列将被调整。重新实现[sizeHintForColumn](qtableview.html#sizeHintForColumn)（ ）调整隐藏的列也是如此。

```
QTableView.resizeRowsToContents (self)
```

这种方法也是一个Qt槽与C + +的签名`void resizeRowsToContents()`。

重新调整的基础上用来渲染中的行的每个项目委讬的大小暗示的所有行。

```
QTableView.resizeRowToContents (self, int row)
```

这种方法也是一个Qt槽与C + +的签名`void resizeRowToContents(int)`。

调整大小给定的_row_基于用于渲染的行中的每个项目委讬的大小的提示。

```
int QTableView.rowAt (self, int y)
```

返回该行中给定的y坐标，_y_在内容坐标系的位置。

**Note:**该函数返回-1，如果给定的坐标是无效的（没有行） 。

**See also** [columnAt](qtableview.html#columnAt)（ ） 。

```
QTableView.rowCountChanged (self, int oldCount, int newCount)
```

这种方法也是一个Qt槽与C + +的签名`void rowCountChanged(int,int)`。

这个槽被调用时行添加或删除。由指定的行之前的数_oldCount_，并且通过指定的行数的新_newCount_。

```
int QTableView.rowHeight (self, int row)
```

返回给定的高度_row_。

**See also** [setRowHeight](qtableview.html#setRowHeight)（ ）[resizeRowToContents](qtableview.html#resizeRowToContents)（）和[columnWidth](qtableview.html#columnWidth)（ ） 。

```
QTableView.rowMoved (self, int row, int oldIndex, int newIndex)
```

这种方法也是一个Qt槽与C + +的签名`void rowMoved(int,int,int)`。

这个槽被调用来改变给定的索引_row_在表视图。旧索引由指定_oldIndex_，并且由新的索引_newIndex_。

**See also** [columnMoved](qtableview.html#columnMoved)（ ） 。

```
QTableView.rowResized (self, int row, int oldHeight, int newHeight)
```

这种方法也是一个Qt槽与C + +的签名`void rowResized(int,int,int)`。

这个槽被调用来改变给定的高度_row_。旧的高度由指定_oldHeight_，和新的高度由_newHeight_。

**See also** [columnResized](qtableview.html#columnResized)（ ） 。

```
int QTableView.rowSpan (self, int row, int column)
```

返回表元素的行间距为（_row_，_column_） 。默认值是1 。

这个函数中引入了Qt 4.2中。

**See also** [setSpan](qtableview.html#setSpan)（）和[columnSpan](qtableview.html#columnSpan)（ ） 。

```
int QTableView.rowViewportPosition (self, int row)
```

返回给定的内容中y坐标坐标_row_。

```
QTableView.scrollContentsBy (self, int dx, int dy)
```

```
QTableView.scrollTo (self, QModelIndex index, QAbstractItemView.ScrollHint hint = QAbstractItemView.EnsureVisible)
```

```
QTableView.selectColumn (self, int column)
```

这种方法也是一个Qt槽与C + +的签名`void selectColumn(int)`。

选择给定的_column_在表视图，如果当前[SelectionMode](qabstractitemview.html#SelectionMode-enum)和[SelectionBehavior](qabstractitemview.html#SelectionBehavior-enum)允许选择的列。

**See also** [selectRow](qtableview.html#selectRow)（ ） 。

```
list-of-QModelIndex QTableView.selectedIndexes (self)
```

从重新实现[QAbstractItemView.selectedIndexes](qabstractitemview.html#selectedIndexes)（ ） 。

```
QTableView.selectionChanged (self, QItemSelection selected, QItemSelection deselected)
```

从重新实现[QAbstractItemView.selectionChanged](qabstractitemview.html#selectionChanged)（ ） 。

```
QTableView.selectRow (self, int row)
```

这种方法也是一个Qt槽与C + +的签名`void selectRow(int)`。

选择给定的_row_在表视图，如果当前[SelectionMode](qabstractitemview.html#SelectionMode-enum)和[SelectionBehavior](qabstractitemview.html#SelectionBehavior-enum)允许选择的行。

**See also** [selectColumn](qtableview.html#selectColumn)（ ） 。

```
QTableView.setColumnHidden (self, int column, bool hide)
```

If _hide_是真正的给定_column_将被隐藏，否则将被显示。

**See also** [isColumnHidden](qtableview.html#isColumnHidden)（）和[setRowHidden](qtableview.html#setRowHidden)（ ） 。

```
QTableView.setColumnWidth (self, int column, int width)
```

设定的给定的宽度_column_要_width_。

这个函数是Qt 4.1中引入。

**See also** [columnWidth](qtableview.html#columnWidth)（ ） 。

```
QTableView.setCornerButtonEnabled (self, bool enable)
```

```
QTableView.setGridStyle (self, Qt.PenStyle style)
```

```
QTableView.setHorizontalHeader (self, QHeaderView header)
```

该_header_说法有它的所有权转移给Qt的。

设置部件用于在水平标头_header_。

**See also** [horizontalHeader](qtableview.html#horizontalHeader)（）和[setVerticalHeader](qtableview.html#setVerticalHeader)（ ） 。

```
QTableView.setModel (self, QAbstractItemModel model)
```

从重新实现[QAbstractItemView.setModel](qabstractitemview.html#setModel)（ ） 。

```
QTableView.setRootIndex (self, QModelIndex index)
```

从重新实现[QAbstractItemView.setRootIndex](qabstractitemview.html#setRootIndex)（ ） 。

```
QTableView.setRowHeight (self, int row, int height)
```

设定的给定的高度_row_要_height_。

这个函数是Qt 4.1中引入。

**See also** [rowHeight](qtableview.html#rowHeight)（ ） 。

```
QTableView.setRowHidden (self, int row, bool hide)
```

If _hide_是真的_row_将被隐藏，否则会被显示。

**See also** [isRowHidden](qtableview.html#isRowHidden)（）和[setColumnHidden](qtableview.html#setColumnHidden)（ ） 。

```
QTableView.setSelection (self, QRect rect, QItemSelectionModel.SelectionFlags command)
```

从重新实现[QAbstractItemView.setSelection](qabstractitemview.html#setSelection)（ ） 。

选择在给定的项目_rect_并按照指定的选择_flags_。

```
QTableView.setSelectionModel (self, QItemSelectionModel selectionModel)
```

从重新实现[QAbstractItemView.setSelectionModel](qabstractitemview.html#setSelectionModel)（ ） 。

```
QTableView.setShowGrid (self, bool show)
```

```
QTableView.setSortingEnabled (self, bool enable)
```

```
QTableView.setSpan (self, int row, int column, int rowSpan, int columnSpan)
```

设置表格单元的跨度为（_row_，_column_），以通过（指定的行和列的数量_rowSpanCount_，_columnSpanCount_） 。

这个函数中引入了Qt 4.2中。

**See also** [rowSpan](qtableview.html#rowSpan)（）和[columnSpan](qtableview.html#columnSpan)（ ） 。

```
QTableView.setVerticalHeader (self, QHeaderView header)
```

该_header_说法有它的所有权转移给Qt的。

设置部件用于在垂直头_header_。

**See also** [verticalHeader](qtableview.html#verticalHeader)（）和[setHorizontalHeader](qtableview.html#setHorizontalHeader)（ ） 。

```
QTableView.setWordWrap (self, bool on)
```

```
QTableView.showColumn (self, int column)
```

这种方法也是一个Qt槽与C + +的签名`void showColumn(int)`。

显示给定的_column_。

**See also** [hideColumn](qtableview.html#hideColumn)（）和[showRow](qtableview.html#showRow)（ ） 。

```
bool QTableView.showGrid (self)
```

```
QTableView.showRow (self, int row)
```

这种方法也是一个Qt槽与C + +的签名`void showRow(int)`。

显示给定的_row_。

**See also** [hideRow](qtableview.html#hideRow)（）和[showColumn](qtableview.html#showColumn)（ ） 。

```
int QTableView.sizeHintForColumn (self, int column)
```

从重新实现[QAbstractItemView.sizeHintForColumn](qabstractitemview.html#sizeHintForColumn)（ ） 。

返回尺寸暗示对于给定的_column_的宽度或-1 ，如果没有模型。

如果你需要一个给定列的宽度设置为一个固定值，调用[QHeaderView.resizeSection](qheaderview.html#resizeSection)（ ）在桌子上的水平标题。

如果在子类中重新实现这个功能，请注意您返回值时，将使用[resizeColumnToContents](qtableview.html#resizeColumnToContents)（）或[QHeaderView.resizeSections](qheaderview.html#resizeSections)（）被调用。如果一个较大的列宽是必需的任何一方的横头或项目的委讬，较大的宽度将被代替使用。

**See also** [QWidget.sizeHint](qwidget.html#sizeHint-prop)和[horizontalHeader](qtableview.html#horizontalHeader)（ ） 。

```
int QTableView.sizeHintForRow (self, int row)
```

从重新实现[QAbstractItemView.sizeHintForRow](qabstractitemview.html#sizeHintForRow)（ ） 。

返回尺寸暗示对于给定的_row_的高度或-1 ，如果没有模型。

如果你需要一个给定的行的高度设置为一个固定值，调用[QHeaderView.resizeSection](qheaderview.html#resizeSection)（ ）在桌子上的垂直标题。

如果在子类中重新实现这个功能，请注意您返回值时只使用[resizeRowToContents](qtableview.html#resizeRowToContents)（）被调用。在这种情况下，如果一个较大的行高是必需的任何一方向垂直头或项目委讬时，该宽度将被代替使用。

**See also** [QWidget.sizeHint](qwidget.html#sizeHint-prop)和[verticalHeader](qtableview.html#verticalHeader)（ ） 。

```
QTableView.sortByColumn (self, int column)
```

这种方法也是一个Qt槽与C + +的签名`void sortByColumn(int)`。

通过在给定的值进行排序的模型_column_在给定的_order_。

这个函数中引入了Qt 4.2中。

**See also** [sortingEnabled](qtableview.html#sortingEnabled-prop)。

```
QTableView.sortByColumn (self, int column, Qt.SortOrder order)
```

```
QTableView.timerEvent (self, QTimerEvent event)
```

从重新实现[QObject.timerEvent](qobject.html#timerEvent)（ ） 。

```
QTableView.updateGeometries (self)
```

从重新实现[QAbstractItemView.updateGeometries](qabstractitemview.html#updateGeometries)（ ） 。

```
QHeaderView QTableView.verticalHeader (self)
```

[

返回表视图的垂直插头。

](qheaderview.html)

[**See also**](qheaderview.html) [setVerticalHeader](qtableview.html#setVerticalHeader)（ ）[horizontalHeader](qtableview.html#horizontalHeader)（）和[QAbstractItemModel.headerData](qabstractitemmodel.html#headerData)（ ） 。

```
int QTableView.verticalOffset (self)
```

从重新实现[QAbstractItemView.verticalOffset](qabstractitemview.html#verticalOffset)（ ） 。

返回垂直的表视图中的项目所抵销。

请注意，表视图使用垂直标题部分的位置来确定的行视图的位置。

**See also** [horizontalOffset](qtableview.html#horizontalOffset)（ ） 。

```
QTableView.verticalScrollbarAction (self, int action)
```

```
QStyleOptionViewItem QTableView.viewOptions (self)
```

[](qstyleoptionviewitem.html)

[从重新实现](qstyleoptionviewitem.html)[QAbstractItemView.viewOptions](qabstractitemview.html#viewOptions)（ ） 。

```
QRect QTableView.visualRect (self, QModelIndex index)
```

[](qrect.html)

```
QRegion QTableView.visualRegionForSelection (self, QItemSelection selection)
```

[

```
bool QTableView.wordWrap (self)
```

](qregion.html)