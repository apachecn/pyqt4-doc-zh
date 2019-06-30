# QHeaderView Class Reference

## [[QtGui](index.htm) module]

该QHeaderView类提供了一个标题行或项目的意见标题列。[More...](#details)

继承[QAbstractItemView](qabstractitemview.html)。

### Types

*   `enum ResizeMode { Interactive, Fixed, Stretch, ResizeToContents, Custom }`

### Methods

*   `__init__ (self, Qt.Orientation orientation, QWidget parent = None)`
*   `bool cascadingSectionResizes (self)`
*   `int count (self)`
*   `currentChanged (self, QModelIndex current, QModelIndex old)`
*   `dataChanged (self, QModelIndex topLeft, QModelIndex bottomRight)`
*   `Qt.Alignment defaultAlignment (self)`
*   `int defaultSectionSize (self)`
*   `bool event (self, QEvent e)`
*   `headerDataChanged (self, Qt.Orientation orientation, int logicalFirst, int logicalLast)`
*   `int hiddenSectionCount (self)`
*   `hideSection (self, int alogicalIndex)`
*   `bool highlightSections (self)`
*   `int horizontalOffset (self)`
*   `QModelIndex indexAt (self, QPoint p)`
*   `initialize (self)`
*   `initializeSections (self)`
*   `initializeSections (self, int start, int end)`
*   `initStyleOption (self, QStyleOptionHeader option)`
*   `bool isClickable (self)`
*   `bool isIndexHidden (self, QModelIndex index)`
*   `bool isMovable (self)`
*   `bool isSectionHidden (self, int logicalIndex)`
*   `bool isSortIndicatorShown (self)`
*   `int length (self)`
*   `int logicalIndex (self, int visualIndex)`
*   `int logicalIndexAt (self, int position)`
*   `int logicalIndexAt (self, int ax, int ay)`
*   `int logicalIndexAt (self, QPoint apos)`
*   `int minimumSectionSize (self)`
*   `mouseDoubleClickEvent (self, QMouseEvent e)`
*   `mouseMoveEvent (self, QMouseEvent e)`
*   `mousePressEvent (self, QMouseEvent e)`
*   `mouseReleaseEvent (self, QMouseEvent e)`
*   `QModelIndex moveCursor (self, QAbstractItemView.CursorAction, Qt.KeyboardModifiers)`
*   `moveSection (self, int from, int to)`
*   `int offset (self)`
*   `Qt.Orientation orientation (self)`
*   `paintEvent (self, QPaintEvent e)`
*   `paintSection (self, QPainter painter, QRect rect, int logicalIndex)`
*   `reset (self)`
*   `ResizeMode resizeMode (self, int logicalIndex)`
*   `resizeSection (self, int logicalIndex, int size)`
*   `resizeSections (self)`
*   `resizeSections (self, ResizeMode mode)`
*   `bool restoreState (self, QByteArray state)`
*   `rowsInserted (self, QModelIndex parent, int start, int end)`
*   `QByteArray saveState (self)`
*   `scrollContentsBy (self, int dx, int dy)`
*   `scrollTo (self, QModelIndex index, QAbstractItemView.ScrollHint hint)`
*   `int sectionPosition (self, int logicalIndex)`
*   `sectionsAboutToBeRemoved (self, QModelIndex parent, int logicalFirst, int logicalLast)`
*   `bool sectionsHidden (self)`
*   `sectionsInserted (self, QModelIndex parent, int logicalFirst, int logicalLast)`
*   `int sectionSize (self, int logicalIndex)`
*   `QSize sectionSizeFromContents (self, int logicalIndex)`
*   `int sectionSizeHint (self, int logicalIndex)`
*   `bool sectionsMoved (self)`
*   `int sectionViewportPosition (self, int logicalIndex)`
*   `setCascadingSectionResizes (self, bool enable)`
*   `setClickable (self, bool clickable)`
*   `setDefaultAlignment (self, Qt.Alignment alignment)`
*   `setDefaultSectionSize (self, int size)`
*   `setHighlightSections (self, bool highlight)`
*   `setMinimumSectionSize (self, int size)`
*   `setModel (self, QAbstractItemModel model)`
*   `setMovable (self, bool movable)`
*   `setOffset (self, int offset)`
*   `setOffsetToLastSection (self)`
*   `setOffsetToSectionPosition (self, int visualIndex)`
*   `setResizeMode (self, ResizeMode mode)`
*   `setResizeMode (self, int logicalIndex, ResizeMode mode)`
*   `setSectionHidden (self, int logicalIndex, bool hide)`
*   `setSelection (self, QRect, QItemSelectionModel.SelectionFlags)`
*   `setSortIndicator (self, int logicalIndex, Qt.SortOrder order)`
*   `setSortIndicatorShown (self, bool show)`
*   `setStretchLastSection (self, bool stretch)`
*   `showSection (self, int alogicalIndex)`
*   `QSize sizeHint (self)`
*   `Qt.SortOrder sortIndicatorOrder (self)`
*   `int sortIndicatorSection (self)`
*   `bool stretchLastSection (self)`
*   `int stretchSectionCount (self)`
*   `swapSections (self, int first, int second)`
*   `updateGeometries (self)`
*   `updateSection (self, int logicalIndex)`
*   `int verticalOffset (self)`
*   `bool viewportEvent (self, QEvent e)`
*   `int visualIndex (self, int logicalIndex)`
*   `int visualIndexAt (self, int position)`
*   `QRect visualRect (self, QModelIndex index)`
*   `QRegion visualRegionForSelection (self, QItemSelection selection)`

### Special Methods

*   `__len__ (self)`

### Qt Signals

*   `void geometriesChanged ()`
*   `void sectionAutoResize (int,QHeaderView::ResizeMode)`
*   `void sectionClicked (int)`
*   `void sectionCountChanged (int,int)`
*   `void sectionDoubleClicked (int)`
*   `void sectionEntered (int)`
*   `void sectionHandleDoubleClicked (int)`
*   `void sectionMoved (int,int,int)`
*   `void sectionPressed (int)`
*   `void sectionResized (int,int,int)`
*   `void sortIndicatorChanged (int,Qt::SortOrder)`

* * *

## Detailed Description

该QHeaderView类提供了一个标题行或项目的意见标题列。

一个QHeaderView显示在项目的意见，如使用的头[QTableView](qtableview.html)和[QTreeView](qtreeview.html)类。它需要Qt3的的地点`QHeader`级以前用于同样的目的，但使用Qt的模型/视图架构与项目视图类的一致性。

该QHeaderView类是一个[Model/View Classes](index.htm)并且是Qt的一部分[model/view framework](index.htm)。

从模型中使用的报头获取的每个部分中的数据的[QAbstractItemModel.headerData](qabstractitemmodel.html#headerData)（）函数。您可以通过使用数据集[QAbstractItemModel.setHeaderData](qabstractitemmodel.html#setHeaderData)（ ） 。

每个头都有一个[orientation](qheaderview.html#orientation)（）和若干节，由给定的[count](qheaderview.html#count)（）函数。甲部分指的是报头的一部分 - 要么一排或一列，取决于方位。

部分可以移动和调整大小使用[moveSection](qheaderview.html#moveSection)（）和[resizeSection](qheaderview.html#resizeSection)（） ，它们也可以被隐藏，以示[hideSection](qheaderview.html#hideSection)（）和[showSection](qheaderview.html#showSection)（ ） 。

报头的每个部分是由一个段的ID ，则其部分（指定的）中描述，并且可以位于特定的[visualIndex](qheaderview.html#visualIndex)（）的报头。 A节可以有一个排序的指标设置[setSortIndicator](qheaderview.html#setSortIndicator)（）;这表明无论是在相关的项目视图中的项目将在由部分给定的顺序进行排序。

对于一个水平标头中的部分等效于在模型中的一列，并为一个垂直头中的部分等效于一个行中的模型。

### Moving Header Sections

一个头可以固定在适当位置，或做成可移动的带[setMovable](qheaderview.html#setMovable)（ ） 。它可以制成可点击与[setClickable](qheaderview.html#setClickable)（） ，并调整大小按照行为[setResizeMode](qheaderview.html#setResizeMode)（ ） 。

**Note:**上一个头要调整部分双击仅适用于可见行。

一个头会发出[sectionMoved](qheaderview.html#sectionMoved)（）如果用户移动部分，[sectionResized](qheaderview.html#sectionResized)（）如果用户调整一个部分，[sectionClicked](qheaderview.html#sectionClicked)（）以及[sectionHandleDoubleClicked](qheaderview.html#sectionHandleDoubleClicked)（ ）响应鼠标点击。一个头也会放出[sectionCountChanged](qheaderview.html#sectionCountChanged)（）和[sectionAutoResize](qheaderview.html#sectionAutoResize)（ ） 。

您可以使用识别部分[logicalIndex](qheaderview.html#logicalIndex)（）和[logicalIndexAt](qheaderview.html#logicalIndexAt)（ ）函数，或者通过其索引位置，使用[visualIndex](qheaderview.html#visualIndex)（）和[visualIndexAt](qheaderview.html#visualIndexAt)（）函数。视觉索引会改变，如果一个部分被移动，但逻辑索引不会改变。

### Appearance

[QTableWidget](qtablewidget.html)和[QTableView](qtableview.html)创建默认标题。如果你想标题是可见的，你可以使用[setVisible()](qwidget.html#visible-prop)。

不是所有的[ItemDataRole](qt.html#ItemDataRole-enum)s将会有一个QHeaderView的效果。如果您需要绘制其他角色，你可以继承QHeaderView和重新实现[paintEvent()](qheaderview.html#paintEvent)。 QHeaderView尊重以下项目数据的作用：[TextAlignmentRole](qt.html#ItemDataRole-enum)，[DisplayRole](qt.html#ItemDataRole-enum)，[FontRole](qt.html#ItemDataRole-enum)，[DecorationRole](qt.html#ItemDataRole-enum)，[ForegroundRole](qt.html#ItemDataRole-enum)和[BackgroundRole](qt.html#ItemDataRole-enum)。

**Note:**每头呈现每个部分本身的数据，并且不依赖于委讬。其结果是，调用一个头的[setItemDelegate](qabstractitemview.html#setItemDelegate)（ ）函数就没有任何效果。

* * *

## Type Documentation

```
QHeaderView.ResizeMode
```

调整大小模式指定的标头部分的行为。它可以对整个头视图或在个别路段使用设置[setResizeMode](qheaderview.html#setResizeMode)（ ） 。

| Constant | Value | Description |
| --- | --- | --- |
| `QHeaderView.Interactive` | `0` | 用户可以调整该区段。的部分也可以通过使用编程的调整大小[resizeSection](qheaderview.html#resizeSection)（ ） 。本节大小默认为[defaultSectionSize](qheaderview.html#defaultSectionSize-prop)。 （另请参见[cascadingSectionResizes](qheaderview.html#cascadingSectionResizes-prop)。 ） |
| `QHeaderView.Fixed` | `2` | 用户不能调整的部分。节只能使用编程方式调整[resizeSection](qheaderview.html#resizeSection)（ ） 。本节大小默认为[defaultSectionSize](qheaderview.html#defaultSectionSize-prop)。 |
| `QHeaderView.Stretch` | `1` | [QHeaderView](qheaderview.html)会自动调整节的大小，以填满可用空间。大小不能由用户或编程来改变。 |
| `QHeaderView.ResizeToContents` | `3` | [QHeaderView](qheaderview.html)将自动调整大小的部分到其基于整个行或列的内容，最佳大小。大小不能由用户或编程来改变。 （该值是在4.2中引入） |

下面的值已过时：

| Constant | Value | Description |
| --- | --- | --- |
| `QHeaderView.Custom` | `Fixed` | 使用固定代替。 |

**See also** [setResizeMode](qheaderview.html#setResizeMode)（ ）[stretchLastSection](qheaderview.html#stretchLastSection-prop)和[minimumSectionSize](qheaderview.html#minimumSectionSize-prop)。

* * *

## Method Documentation

```
QHeaderView.__init__ (self, Qt.Orientation orientation, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建一个新的通用头与给定_orientation_和_parent_。

```
bool QHeaderView.cascadingSectionResizes (self)
```

```
int QHeaderView.count (self)
```

返回部分的标头中的数量。

**See also** [sectionCountChanged](qheaderview.html#sectionCountChanged)（）和[length](qheaderview.html#length)（ ） 。

```
QHeaderView.currentChanged (self, QModelIndex current, QModelIndex old)
```

从重新实现[QAbstractItemView.currentChanged](qabstractitemview.html#currentChanged)（ ） 。

```
QHeaderView.dataChanged (self, QModelIndex topLeft, QModelIndex bottomRight)
```

```
Qt.Alignment QHeaderView.defaultAlignment (self)
```

[

```
int QHeaderView.defaultSectionSize (self)
```

```
bool QHeaderView.event (self, QEvent e)
```

](index.htm)

[从重新实现](index.htm)[QObject.event](qobject.html#event)（ ） 。

```
QHeaderView.headerDataChanged (self, Qt.Orientation orientation, int logicalFirst, int logicalLast)
```

这种方法也是一个Qt槽与C + +的签名`void headerDataChanged(Qt::Orientation,int,int)`。

更新改变的报头部分与给定_orientation_，从_logicalFirst_至_logicalLast_包容性。

```
int QHeaderView.hiddenSectionCount (self)
```

返回部分中已隐藏的报头的数量。

这个函数是Qt 4.1中引入。

**See also** [setSectionHidden](qheaderview.html#setSectionHidden)（）和[isSectionHidden](qheaderview.html#isSectionHidden)（ ） 。

```
QHeaderView.hideSection (self, int alogicalIndex)
```

隐藏由指定的段_logicalIndex_。

**See also** [showSection](qheaderview.html#showSection)（ ）[isSectionHidden](qheaderview.html#isSectionHidden)（ ）[hiddenSectionCount](qheaderview.html#hiddenSectionCount)（）和[setSectionHidden](qheaderview.html#setSectionHidden)（ ） 。

```
bool QHeaderView.highlightSections (self)
```

```
int QHeaderView.horizontalOffset (self)
```

从重新实现[QAbstractItemView.horizontalOffset](qabstractitemview.html#horizontalOffset)（ ） 。

返回水平标头的偏移量。这是0垂直头。

**See also** [offset](qheaderview.html#offset)（ ） 。

```
QModelIndex QHeaderView.indexAt (self, QPoint p)
```

[

```
QHeaderView.initialize (self)
```

```
QHeaderView.initializeSections (self)
```

```
QHeaderView.initializeSections (self, int start, int end)
```

```
QHeaderView.initStyleOption (self, QStyleOptionHeader option)
```

](qmodelindex.html)

[初始化_option_与其它的值](qmodelindex.html)[QHeaderView](qheaderview.html)。当他们需要一个这种方法是有用的子类[QStyleOptionHeader](qstyleoptionheader.html)，但不希望在所有的信息填写自己。

**See also** [QStyleOption.initFrom](qstyleoption.html#initFrom)（ ） 。

```
bool QHeaderView.isClickable (self)
```

返回True如果标题是可点击的，否则返回False 。一个可点击的标题可以被设置为允许用户更改数据在相关的头视图中的代表性。

**See also** [setClickable](qheaderview.html#setClickable)（ ） 。

```
bool QHeaderView.isIndexHidden (self, QModelIndex index)
```

```
bool QHeaderView.isMovable (self)
```

返回True如果头可以被用户移动，否则返回False 。

**See also** [setMovable](qheaderview.html#setMovable)（ ） 。

```
bool QHeaderView.isSectionHidden (self, int logicalIndex)
```

返回True如果指定的节_logicalIndex_从用户明确地隐藏，否则返回False 。

**See also** [hideSection](qheaderview.html#hideSection)（ ）[showSection](qheaderview.html#showSection)（ ）[setSectionHidden](qheaderview.html#setSectionHidden)（）和[hiddenSectionCount](qheaderview.html#hiddenSectionCount)（ ） 。

```
bool QHeaderView.isSortIndicatorShown (self)
```

```
int QHeaderView.length (self)
```

返回沿头的方向的长度。

**See also** [sizeHint](qheaderview.html#sizeHint)（ ）[setResizeMode](qheaderview.html#setResizeMode)（）和[offset](qheaderview.html#offset)（ ） 。

```
int QHeaderView.logicalIndex (self, int visualIndex)
```

返回logicalIndex的部分在给定的_visualIndex_位置，或-1，如果visualIndex \u003c 0或visualIndex \u003e =[QHeaderView.count](qheaderview.html#count)（ ） 。

注意， visualIndex不受隐藏部分。

**See also** [visualIndex](qheaderview.html#visualIndex)（）和[sectionPosition](qheaderview.html#sectionPosition)（ ） 。

```
int QHeaderView.logicalIndexAt (self, int position)
```

返回复盖给定的节_position_在视口中。

**See also** [visualIndexAt](qheaderview.html#visualIndexAt)（）和[isSectionHidden](qheaderview.html#isSectionHidden)（ ） 。

```
int QHeaderView.logicalIndexAt (self, int ax, int ay)
```

返回部分的逻辑索引在给定的坐标。如果标题是水平_x_将被使用，否则_y_将被用来寻找逻辑索引。

```
int QHeaderView.logicalIndexAt (self, QPoint apos)
```

返回部分的逻辑索引在给定的位置_pos_。如果标题是水平的x坐标将被使用，否则y坐标将被用来寻找逻辑索引。

**See also** [sectionPosition](qheaderview.html#sectionPosition)（ ） 。

```
int QHeaderView.minimumSectionSize (self)
```

```
QHeaderView.mouseDoubleClickEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mouseDoubleClickEvent](qwidget.html#mouseDoubleClickEvent)（ ） 。

```
QHeaderView.mouseMoveEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mouseMoveEvent](qwidget.html#mouseMoveEvent)（ ） 。

```
QHeaderView.mousePressEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mousePressEvent](qwidget.html#mousePressEvent)（ ） 。

```
QHeaderView.mouseReleaseEvent (self, QMouseEvent e)
```

从重新实现[QWidget.mouseReleaseEvent](qwidget.html#mouseReleaseEvent)（ ） 。

```
QModelIndex QHeaderView.moveCursor (self, QAbstractItemView.CursorAction, Qt.KeyboardModifiers)
```

[

```
QHeaderView.moveSection (self, int from, int to)
```

移动部分在视觉索引_from_佔据视觉指数_to_。

](qmodelindex.html)

[**See also**](qmodelindex.html) [sectionsMoved](qheaderview.html#sectionsMoved)（ ） 。

```
int QHeaderView.offset (self)
```

返回头的偏移量：这是标题的最左边（或最顶层垂直头）可见像素。

**See also** [setOffset](qheaderview.html#setOffset)（ ） 。

```
Qt.Orientation QHeaderView.orientation (self)
```

[

返回头的方位。

](qt.html#Orientation-enum)

[**See also**](qt.html#Orientation-enum) [Qt.Orientation](qt.html#Orientation-enum)。

```
QHeaderView.paintEvent (self, QPaintEvent e)
```

从重新实现[QWidget.paintEvent](qwidget.html#paintEvent)（ ） 。

```
QHeaderView.paintSection (self, QPainter painter, QRect rect, int logicalIndex)
```

绘制由给定指定的节_logicalIndex_，使用给定的_painter_和_rect_。

通常情况下，你不必调用这个函数。

```
QHeaderView.reset (self)
```

从重新实现[QAbstractItemView.reset](qabstractitemview.html#reset)（ ） 。

```
ResizeMode QHeaderView.resizeMode (self, int logicalIndex)
```

[

返回适用于部分由给定指定的尺寸模式_logicalIndex_。

](qheaderview.html#ResizeMode-enum)

[**See also**](qheaderview.html#ResizeMode-enum) [setResizeMode](qheaderview.html#setResizeMode)（ ） 。

```
QHeaderView.resizeSection (self, int logicalIndex, int size)
```

重新调整所指定的部分_logicalIndex_至_size_以像素为单位。

**See also** [sectionResized](qheaderview.html#sectionResized)（ ）[resizeMode](qheaderview.html#resizeMode)（）和[sectionSize](qheaderview.html#sectionSize)（ ） 。

```
QHeaderView.resizeSections (self)
```

这种方法也是一个Qt槽与C + +的签名`void resizeSections()`。

根据给定的大小调整部分_mode_忽略当前调整模式。

**See also** [resizeMode](qheaderview.html#resizeMode)（）和[sectionResized](qheaderview.html#sectionResized)（ ） 。

```
QHeaderView.resizeSections (self, ResizeMode mode)
```

根据他们的大小提示重新调整的部分。通常情况下，你不必调用这个函数。

```
bool QHeaderView.restoreState (self, QByteArray state)
```

恢复_state_这头视图。这个函数返回`true`如果状态得到恢复，否则返回False 。

此功能被引入Qt的4.3 。

**See also** [saveState](qheaderview.html#saveState)（ ） 。

```
QHeaderView.rowsInserted (self, QModelIndex parent, int start, int end)
```

```
QByteArray QHeaderView.saveState (self)
```

[

保存这个头视图的当前状态。

](qbytearray.html)

[要恢复保存的状态，返回值传递给](qbytearray.html)[restoreState](qheaderview.html#restoreState)（ ） 。

此功能被引入Qt的4.3 。

**See also** [restoreState](qheaderview.html#restoreState)（ ） 。

```
QHeaderView.scrollContentsBy (self, int dx, int dy)
```

```
QHeaderView.scrollTo (self, QModelIndex index, QAbstractItemView.ScrollHint hint)
```

```
int QHeaderView.sectionPosition (self, int logicalIndex)
```

返回给定的区间位置_logicalIndex_，或-1，如果部分被隐藏。位置是衡量像素从第一个可见项的左上角，以该项目的左上角与_logicalIndex_。测量是沿x轴为水平的标头，并沿y轴为垂直的标头。

**See also** [sectionViewportPosition](qheaderview.html#sectionViewportPosition)（ ） 。

```
QHeaderView.sectionsAboutToBeRemoved (self, QModelIndex parent, int logicalFirst, int logicalLast)
```

这种方法也是一个Qt槽与C + +的签名`void sectionsAboutToBeRemoved(const QModelIndex&,int,int)`。

当部分被从删除该槽被调用_parent_。_logicalFirst_和_logicalLast_表示除去路段。

如果只有一个部分被去除，_logicalFirst_和_logicalLast_将是相同的。

```
bool QHeaderView.sectionsHidden (self)
```

返回True如果在头段已被隐藏，否则返回False ;

这个函数是Qt 4.1中引入。

**See also** [setSectionHidden](qheaderview.html#setSectionHidden)（ ） 。

```
QHeaderView.sectionsInserted (self, QModelIndex parent, int logicalFirst, int logicalLast)
```

这种方法也是一个Qt槽与C + +的签名`void sectionsInserted(const QModelIndex&,int,int)`。

当部分被插入到该插槽被称为_parent_。_logicalFirst_和_logicalLast_指数表示插入新的路段。

如果只插入一个部分，_logicalFirst_和_logicalLast_将是相同的。

```
int QHeaderView.sectionSize (self, int logicalIndex)
```

返回给定的宽度（或高度垂直头）_logicalIndex_。

**See also** [length](qheaderview.html#length)（ ）[setResizeMode](qheaderview.html#setResizeMode)（）和[defaultSectionSize](qheaderview.html#defaultSectionSize-prop)（ ） 。

```
QSize QHeaderView.sectionSizeFromContents (self, int logicalIndex)
```

[

返回的部分的内容由给定的指定尺寸_logicalIndex_。

](qsize.html)

[**See also**](qsize.html) [defaultSectionSize](qheaderview.html#defaultSectionSize-prop)（ ） 。

```
int QHeaderView.sectionSizeHint (self, int logicalIndex)
```

返回一个合适大小的提示由指定的节_logicalIndex_。

**See also** [sizeHint](qheaderview.html#sizeHint)（ ）[defaultSectionSize](qheaderview.html#defaultSectionSize-prop)（ ）[minimumSectionSize](qheaderview.html#minimumSectionSize-prop)（）和[Qt.SizeHintRole](qt.html#ItemDataRole-enum)。

```
bool QHeaderView.sectionsMoved (self)
```

返回True如果在头段已被移动，否则返回False ;

**See also** [moveSection](qheaderview.html#moveSection)（ ） 。

```
int QHeaderView.sectionViewportPosition (self, int logicalIndex)
```

返回给定的部分视口位置_logicalIndex_。

如果部分被隐藏，返回值是不确定的。

**See also** [sectionPosition](qheaderview.html#sectionPosition)（）和[isSectionHidden](qheaderview.html#isSectionHidden)（ ） 。

```
QHeaderView.setCascadingSectionResizes (self, bool enable)
```

```
QHeaderView.setClickable (self, bool clickable)
```

If _clickable_是真的，头将响应单一的点击。

**See also** [isClickable](qheaderview.html#isClickable)（ ）[sectionClicked](qheaderview.html#sectionClicked)（ ）[sectionPressed](qheaderview.html#sectionPressed)（）和[setSortIndicatorShown](qheaderview.html#showSortIndicator-prop)（ ） 。

```
QHeaderView.setDefaultAlignment (self, Qt.Alignment alignment)
```

```
QHeaderView.setDefaultSectionSize (self, int size)
```

```
QHeaderView.setHighlightSections (self, bool highlight)
```

```
QHeaderView.setMinimumSectionSize (self, int size)
```

```
QHeaderView.setModel (self, QAbstractItemModel model)
```

从重新实现[QAbstractItemView.setModel](qabstractitemview.html#setModel)（ ） 。

```
QHeaderView.setMovable (self, bool movable)
```

If _movable_为真，则报头可以被用户移动，否则它被固定在适当位置。

**See also** [isMovable](qheaderview.html#isMovable)（）和[sectionMoved](qheaderview.html#sectionMoved)（ ） 。

```
QHeaderView.setOffset (self, int offset)
```

这种方法也是一个Qt槽与C + +的签名`void setOffset(int)`。

套头的偏移量_offset_。

**See also** [offset](qheaderview.html#offset)（）和[length](qheaderview.html#length)（ ） 。

```
QHeaderView.setOffsetToLastSection (self)
```

这种方法也是一个Qt槽与C + +的签名`void setOffsetToLastSection()`。

设置偏移，使上节可见。

这个函数中引入了Qt 4.2中。

**See also** [setOffset](qheaderview.html#setOffset)（ ）[sectionPosition](qheaderview.html#sectionPosition)（）和[setOffsetToSectionPosition](qheaderview.html#setOffsetToSectionPosition)（ ） 。

```
QHeaderView.setOffsetToSectionPosition (self, int visualIndex)
```

这种方法也是一个Qt槽与C + +的签名`void setOffsetToSectionPosition(int)`。

集在给定的偏移量的部分的开始_visualIndex_。

这个函数中引入了Qt 4.2中。

**See also** [setOffset](qheaderview.html#setOffset)（）和[sectionPosition](qheaderview.html#sectionPosition)（ ） 。

```
QHeaderView.setResizeMode (self, ResizeMode mode)
```

设置如何头可以调整到那些由给定描述的约束_mode_。

**See also** [resizeMode](qheaderview.html#resizeMode)（ ）[length](qheaderview.html#length)（ ）[sectionResized](qheaderview.html#sectionResized)（）和[sectionAutoResize](qheaderview.html#sectionAutoResize)（ ） 。

```
QHeaderView.setResizeMode (self, int logicalIndex, ResizeMode mode)
```

这是一个重载函数。

设置约束的部分由指定如何_logicalIndex_在头可以调整到那些由给定的描述_mode_。逻辑索引应该存在在这个函数被调用的时间。

**Note:**此设置将被忽略的最后一节，如果[stretchLastSection](qheaderview.html#stretchLastSection-prop)属性设置为True。这是默认提供的水平标题[QTreeView](qtreeview.html)。

**See also** [setStretchLastSection](qheaderview.html#stretchLastSection-prop)（ ） 。

```
QHeaderView.setSectionHidden (self, int logicalIndex, bool hide)
```

If _hide_是真正的由指定的段_logicalIndex_是隐藏的，否则该部分被示出。

**See also** [isSectionHidden](qheaderview.html#isSectionHidden)（）和[hiddenSectionCount](qheaderview.html#hiddenSectionCount)（ ） 。

```
QHeaderView.setSelection (self, QRect, QItemSelectionModel.SelectionFlags)
```

从重新实现[QAbstractItemView.setSelection](qabstractitemview.html#setSelection)（ ） 。

选择在给定的项目_rect_根据指定的_flags_。

基类的实现不执行任何操作。

```
QHeaderView.setSortIndicator (self, int logicalIndex, Qt.SortOrder order)
```

设置排序指标由给定指定的节_logicalIndex_在所指定的方向_order_，并删除从已显示它的任何其他部分的排序指标。

_logicalIndex_可能是-1 ，在这种情况下，不排序指示器将显示与该模型将回到它的自然，未排序的顺序。请注意，并非所有型号都支持这一点，甚至可能会崩溃在这种情况下。

**See also** [sortIndicatorSection](qheaderview.html#sortIndicatorSection)（）和[sortIndicatorOrder](qheaderview.html#sortIndicatorOrder)（ ） 。

```
QHeaderView.setSortIndicatorShown (self, bool show)
```

```
QHeaderView.setStretchLastSection (self, bool stretch)
```

```
QHeaderView.showSection (self, int alogicalIndex)
```

显示由指定的节_logicalIndex_。

**See also** [hideSection](qheaderview.html#hideSection)（ ）[isSectionHidden](qheaderview.html#isSectionHidden)（ ）[hiddenSectionCount](qheaderview.html#hiddenSectionCount)（）和[setSectionHidden](qheaderview.html#setSectionHidden)（ ） 。

```
QSize QHeaderView.sizeHint (self)
```

[](qsize.html)

[从重新实现](qsize.html)[QWidget.sizeHint](qwidget.html#sizeHint-prop)（ ） 。

返回一个合适的尺寸暗示这个头。

**See also** [sectionSizeHint](qheaderview.html#sectionSizeHint)（ ） 。

```
Qt.SortOrder QHeaderView.sortIndicatorOrder (self)
```

[

返回排序指标的顺序。如果没有部分有一个排序指示器这个函数的返回值是不确定的。

](qt.html#SortOrder-enum)

[**See also**](qt.html#SortOrder-enum) [setSortIndicator](qheaderview.html#setSortIndicator)（）和[sortIndicatorSection](qheaderview.html#sortIndicatorSection)（ ） 。

```
int QHeaderView.sortIndicatorSection (self)
```

返回具有某种指示器部分的逻辑索引。默认情况下，这是一节0 。

**See also** [setSortIndicator](qheaderview.html#setSortIndicator)（ ）[sortIndicatorOrder](qheaderview.html#sortIndicatorOrder)（）和[setSortIndicatorShown](qheaderview.html#showSortIndicator-prop)（ ） 。

```
bool QHeaderView.stretchLastSection (self)
```

```
int QHeaderView.stretchSectionCount (self)
```

返回设置为调整模式舒展的节数。在视图中，这可以用来查看是否headerview需要调整的部分，当视图的几何变化。

这个函数是Qt 4.1中引入。

**See also** [stretchLastSection](qheaderview.html#stretchLastSection-prop)和[resizeMode](qheaderview.html#resizeMode)（ ） 。

```
QHeaderView.swapSections (self, int first, int second)
```

掉期的部分在视觉索引_first_与部分在视觉索引_second_。

这个函数中引入了Qt 4.2中。

**See also** [moveSection](qheaderview.html#moveSection)（ ） 。

```
QHeaderView.updateGeometries (self)
```

```
QHeaderView.updateSection (self, int logicalIndex)
```

这种方法也是一个Qt槽与C + +的签名`void updateSection(int)`。

```
int QHeaderView.verticalOffset (self)
```

从重新实现[QAbstractItemView.verticalOffset](qabstractitemview.html#verticalOffset)（ ） 。

返回垂直头的偏移量。这是0水平的标头。

**See also** [offset](qheaderview.html#offset)（ ） 。

```
bool QHeaderView.viewportEvent (self, QEvent e)
```

从重新实现[QAbstractScrollArea.viewportEvent](qabstractscrollarea.html#viewportEvent)（ ） 。

```
int QHeaderView.visualIndex (self, int logicalIndex)
```

返回段由给定指定的可视索引位置_logicalIndex_，否则返回-1 。

隐藏部分仍然具有有效的可视化索引。

**See also** [logicalIndex](qheaderview.html#logicalIndex)（ ） 。

```
int QHeaderView.visualIndexAt (self, int position)
```

返回复盖给定部分的视觉索引_position_在视口中。

**See also** [logicalIndexAt](qheaderview.html#logicalIndexAt)（ ） 。

```
QRect QHeaderView.visualRect (self, QModelIndex index)
```

[](qrect.html)

```
QRegion QHeaderView.visualRegionForSelection (self, QItemSelection selection)
```

[

```
 QHeaderView.__len__ (self)
```

* * *

## Qt Signal Documentation

```
void geometriesChanged ()
```

这是该信号的默认超载。

当标头的几何形状发生了变化，这个信号被发射。

这个函数中引入了Qt 4.2中。

```
void sectionAutoResize (int,QHeaderView::ResizeMode)
```

这是该信号的默认超载。

这个信号被发射时，部分会自动调整大小。该部分的逻辑索引是通过指定_logicalIndex_，并调整大小模式_mode_。

](qregion.html)

[**See also**](qregion.html) [setResizeMode](qheaderview.html#setResizeMode)（）和[stretchLastSection](qheaderview.html#stretchLastSection-prop)（ ） 。

```
void sectionClicked (int)
```

这是该信号的默认超载。

一个部分被点击时，这个信号被发射。该部分的逻辑索引是通过指定_logicalIndex_。

注意， sectionPressed信号也将被发射。

**See also** [setClickable](qheaderview.html#setClickable)（）和[sectionPressed](qheaderview.html#sectionPressed)（ ） 。

```
void sectionCountChanged (int,int)
```

这是该信号的默认超载。

这个信号被发射时，部分的数目发生变化，即，当部分被添加或删除。原始计数被指定_oldCount_，并且由新的计_newCount_。

**See also** [count](qheaderview.html#count)（ ）[length](qheaderview.html#length)（）和[headerDataChanged](qheaderview.html#headerDataChanged)（ ） 。

```
void sectionDoubleClicked (int)
```

这是该信号的默认超载。

当一个段被双击这个信号被发射。该部分的逻辑索引是通过指定_logicalIndex_。

**See also** [setClickable](qheaderview.html#setClickable)（ ） 。

```
void sectionEntered (int)
```

这是该信号的默认超载。

当光标移过的部分和鼠标左键被按下这个信号被发射。该部分的逻辑索引是通过指定_logicalIndex_。

此功能被引入Qt的4.3 。

**See also** [setClickable](qheaderview.html#setClickable)（）和[sectionPressed](qheaderview.html#sectionPressed)（ ） 。

```
void sectionHandleDoubleClicked (int)
```

这是该信号的默认超载。

当一个段被双击这个信号被发射。该部分的逻辑索引是通过指定_logicalIndex_。

**See also** [setClickable](qheaderview.html#setClickable)（ ） 。

```
void sectionMoved (int,int,int)
```

这是该信号的默认超载。

当一个区段被移动这个信号被发射。该部分的逻辑索引是通过指定_logicalIndex_，老指数由_oldVisualIndex_，并且由新的索引位置_newVisualIndex_。

**See also** [moveSection](qheaderview.html#moveSection)（ ） 。

```
void sectionPressed (int)
```

这是该信号的默认超载。

当一个区段被按下这个信号被发射。该部分的逻辑索引是通过指定_logicalIndex_。

**See also** [setClickable](qheaderview.html#setClickable)（ ） 。

```
void sectionResized (int,int,int)
```

这是该信号的默认超载。

当一个部分被调整大小，这个信号被发射。该部分的逻辑数由指定_logicalIndex_，旧的大小由_oldSize_，并以新的大小_newSize_。

**See also** [resizeSection](qheaderview.html#resizeSection)（ ） 。

```
void sortIndicatorChanged (int,Qt::SortOrder)
```

这是该信号的默认超载。

当改变包含排序指示器或指示的顺序的部分，这个信号被发射。该部分的逻辑索引是通过指定_logicalIndex_并通过指定的排序顺序_order_。

此功能被引入Qt的4.3 。

**See also** [setSortIndicator](qheaderview.html#setSortIndicator)（ ） 。