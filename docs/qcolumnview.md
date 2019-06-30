# QColumnView Class Reference

## [[QtGui](index.htm) module]

该QColumnView类提供了一个模型/视图实现列视图中。[More...](#details)

继承[QAbstractItemView](qabstractitemview.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `list-of-int columnWidths (self)`
*   `QAbstractItemView createColumn (self, QModelIndex rootIndex)`
*   `currentChanged (self, QModelIndex current, QModelIndex previous)`
*   `int horizontalOffset (self)`
*   `QModelIndex indexAt (self, QPoint point)`
*   `initializeColumn (self, QAbstractItemView column)`
*   `bool isIndexHidden (self, QModelIndex index)`
*   `QModelIndex moveCursor (self, QAbstractItemView.CursorAction cursorAction, Qt.KeyboardModifiers modifiers)`
*   `QWidget previewWidget (self)`
*   `resizeEvent (self, QResizeEvent event)`
*   `bool resizeGripsVisible (self)`
*   `rowsInserted (self, QModelIndex parent, int start, int end)`
*   `scrollContentsBy (self, int dx, int dy)`
*   `scrollTo (self, QModelIndex index, QAbstractItemView.ScrollHint hint = QAbstractItemView.EnsureVisible)`
*   `selectAll (self)`
*   `setColumnWidths (self, list-of-int list)`
*   `setModel (self, QAbstractItemModel model)`
*   `setPreviewWidget (self, QWidget widget)`
*   `setResizeGripsVisible (self, bool visible)`
*   `setRootIndex (self, QModelIndex index)`
*   `setSelection (self, QRect rect, QItemSelectionModel.SelectionFlags command)`
*   `setSelectionModel (self, QItemSelectionModel selectionModel)`
*   `QSize sizeHint (self)`
*   `int verticalOffset (self)`
*   `QRect visualRect (self, QModelIndex index)`
*   `QRegion visualRegionForSelection (self, QItemSelection selection)`

### Qt Signals

*   `void updatePreviewWidget (const QModelIndex&)`

* * *

## Detailed Description

该QColumnView类提供了一个模型/视图实现列视图中。

QColumnView在一些QListViews ，一个用于在该树中的每个层次的显示一个模型。这有时被称为级联列表。

该QColumnView类是一个[Model/View Classes](index.htm)并且是Qt的一部分[model/view framework](index.htm)。

QColumnView实现由定义的接口[QAbstractItemView](qabstractitemview.html)类以允许其显示由从派生模型提供数据[QAbstractItemModel](qabstractitemmodel.html)类。

![](../img/qcolumnview.png)

* * *

## Method Documentation

```
QColumnView.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个列视图_parent_来表示模型的数据。使用[setModel](qcolumnview.html#setModel)（）来设定模型。

**See also** [QAbstractItemModel](qabstractitemmodel.html)。

```
list-of-int QColumnView.columnWidths (self)
```

返回此视图中的所有列的宽度的列表。

**See also** [setColumnWidths](qcolumnview.html#setColumnWidths)（ ） 。

```
QAbstractItemView QColumnView.createColumn (self, QModelIndex rootIndex)
```

[

要使用自定义部件的最后一列，当你选择一个项目超负荷此功能，并返回一个widget 。_index_是将被分配到该视图的根索引。

](qabstractitemview.html)

[返回新的观点。](qabstractitemview.html)[QColumnView](qcolumnview.html)便会自动将窗口小部件的所有权。

**See also** [setPreviewWidget](qcolumnview.html#setPreviewWidget)（ ） 。

```
QColumnView.currentChanged (self, QModelIndex current, QModelIndex previous)
```

这种方法也是一个Qt槽与C + +的签名`void currentChanged(const QModelIndex&,const QModelIndex&)`。

从重新实现[QAbstractItemView.currentChanged](qabstractitemview.html#currentChanged)（ ） 。

```
int QColumnView.horizontalOffset (self)
```

从重新实现[QAbstractItemView.horizontalOffset](qabstractitemview.html#horizontalOffset)（ ） 。

```
QModelIndex QColumnView.indexAt (self, QPoint point)
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemView.indexAt](qabstractitemview.html#indexAt)（ ） 。

```
QColumnView.initializeColumn (self, QAbstractItemView column)
```

复制列视图的行为和选择，并将它们应用到_column_如[iconSize](qabstractitemview.html#iconSize-prop)（ ）[textElideMode](qabstractitemview.html#textElideMode-prop)（）和[alternatingRowColors](qabstractitemview.html#alternatingRowColors-prop)（ ） 。重新实现时，这可能是有用的[createColumn](qcolumnview.html#createColumn)（ ） 。

此功能被引入Qt的4.4 。

**See also** [createColumn](qcolumnview.html#createColumn)（ ） 。

```
bool QColumnView.isIndexHidden (self, QModelIndex index)
```

从重新实现[QAbstractItemView.isIndexHidden](qabstractitemview.html#isIndexHidden)（ ） 。

```
QModelIndex QColumnView.moveCursor (self, QAbstractItemView.CursorAction cursorAction, Qt.KeyboardModifiers modifiers)
```

[](qmodelindex.html)

[从重新实现](qmodelindex.html)[QAbstractItemView.moveCursor](qabstractitemview.html#moveCursor)（ ） 。

向左移动应该去主指数向右移动应该去子索引或下降，如果没有孩子

```
QWidget QColumnView.previewWidget (self)
```

[

返回预览窗口小部件，或者0，如果是没有的。

](qwidget.html)

[**See also**](qwidget.html) [setPreviewWidget](qcolumnview.html#setPreviewWidget)（）和[updatePreviewWidget](qcolumnview.html#updatePreviewWidget)（ ） 。

```
QColumnView.resizeEvent (self, QResizeEvent event)
```

从重新实现[QWidget.resizeEvent](qwidget.html#resizeEvent)（ ） 。

```
bool QColumnView.resizeGripsVisible (self)
```

```
QColumnView.rowsInserted (self, QModelIndex parent, int start, int end)
```

从重新实现[QAbstractItemView.rowsInserted](qabstractitemview.html#rowsInserted)（ ） 。

```
QColumnView.scrollContentsBy (self, int dx, int dy)
```

从重新实现[QAbstractScrollArea.scrollContentsBy](qabstractscrollarea.html#scrollContentsBy)（ ） 。

```
QColumnView.scrollTo (self, QModelIndex index, QAbstractItemView.ScrollHint hint = QAbstractItemView.EnsureVisible)
```

从重新实现[QAbstractItemView.scrollTo](qabstractitemview.html#scrollTo)（ ） 。

```
QColumnView.selectAll (self)
```

从重新实现[QAbstractItemView.selectAll](qabstractitemview.html#selectAll)（ ） 。

```
QColumnView.setColumnWidths (self, list-of-int list)
```

列宽设置为在给定的值_list_。在列表中多馀的值会保持不变，在创建列时使用。

如果列表中包含的值太少，只有宽度的列的其馀部分将不会被修改。

**See also** [columnWidths](qcolumnview.html#columnWidths)（）和[createColumn](qcolumnview.html#createColumn)（ ） 。

```
QColumnView.setModel (self, QAbstractItemModel model)
```

从重新实现[QAbstractItemView.setModel](qabstractitemview.html#setModel)（ ） 。

```
QColumnView.setPreviewWidget (self, QWidget widget)
```

该_widget_说法有它的所有权转移给Qt的。

设置预览_widget_。

该_widget_成为列视图的孩子，当列区域被删除或者当一个新的widget设定将被破坏。

**See also** [previewWidget](qcolumnview.html#previewWidget)（）和[updatePreviewWidget](qcolumnview.html#updatePreviewWidget)（ ） 。

```
QColumnView.setResizeGripsVisible (self, bool visible)
```

```
QColumnView.setRootIndex (self, QModelIndex index)
```

从重新实现[QAbstractItemView.setRootIndex](qabstractitemview.html#setRootIndex)（ ） 。

```
QColumnView.setSelection (self, QRect rect, QItemSelectionModel.SelectionFlags command)
```

从重新实现[QAbstractItemView.setSelection](qabstractitemview.html#setSelection)（ ） 。

```
QColumnView.setSelectionModel (self, QItemSelectionModel selectionModel)
```

从重新实现[QAbstractItemView.setSelectionModel](qabstractitemview.html#setSelectionModel)（ ） 。

```
QSize QColumnView.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

```
int QColumnView.verticalOffset (self)
```

从重新实现[QAbstractItemView.verticalOffset](qabstractitemview.html#verticalOffset)（ ） 。

```
QRect QColumnView.visualRect (self, QModelIndex index)
```

[](qrect.html)

[从重新实现](qrect.html)[QAbstractItemView.visualRect](qabstractitemview.html#visualRect)（ ） 。

```
QRegion QColumnView.visualRegionForSelection (self, QItemSelection selection)
```

[](qregion.html)

[从重新实现](qregion.html)[QAbstractItemView.visualRegionForSelection](qabstractitemview.html#visualRegionForSelection)（ ） 。

* * *

## Qt Signal Documentation

```
void updatePreviewWidget (const QModelIndex&)
```

这是该信号的默认超载。

这个信号被发射时，预览窗口小部件应进行更新，以提供有关致富信息_index_

**See also** [previewWidget](qcolumnview.html#previewWidget)（ ） 。