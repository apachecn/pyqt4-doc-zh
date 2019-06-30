# QTableWidget Class Reference

## [[QtGui](index.htm) module]

该QTableWidget类提供了默认的模型基于物品的表视图。[More...](#details)

继承[QTableView](qtableview.html)。

### Methods

*   `__init__ (self, QWidget parent = None)`
*   `__init__ (self, int rows, int columns, QWidget parent = None)`
*   `QWidget cellWidget (self, int row, int column)`
*   `clear (self)`
*   `clearContents (self)`
*   `closePersistentEditor (self, QTableWidgetItem item)`
*   `int column (self, QTableWidgetItem item)`
*   `int columnCount (self)`
*   `int currentColumn (self)`
*   `QTableWidgetItem currentItem (self)`
*   `int currentRow (self)`
*   `dropEvent (self, QDropEvent event)`
*   `bool dropMimeData (self, int row, int column, QMimeData data, Qt.DropAction action)`
*   `editItem (self, QTableWidgetItem item)`
*   `bool event (self, QEvent e)`
*   `list-of-QTableWidgetItem findItems (self, QString text, Qt.MatchFlags flags)`
*   `QTableWidgetItem horizontalHeaderItem (self, int column)`
*   `QModelIndex indexFromItem (self, QTableWidgetItem item)`
*   `insertColumn (self, int column)`
*   `insertRow (self, int row)`
*   `bool isItemSelected (self, QTableWidgetItem item)`
*   `bool isSortingEnabled (self)`
*   `QTableWidgetItem item (self, int row, int column)`
*   `QTableWidgetItem itemAt (self, QPoint p)`
*   `QTableWidgetItem itemAt (self, int ax, int ay)`
*   `QTableWidgetItem itemFromIndex (self, QModelIndex index)`
*   `QTableWidgetItem itemPrototype (self)`
*   `list-of-QTableWidgetItem items (self, QMimeData data)`
*   `QMimeData mimeData (self, list-of-QTableWidgetItem items)`
*   `QStringList mimeTypes (self)`
*   `openPersistentEditor (self, QTableWidgetItem item)`
*   `removeCellWidget (self, int arow, int acolumn)`
*   `removeColumn (self, int column)`
*   `removeRow (self, int row)`
*   `int row (self, QTableWidgetItem item)`
*   `int rowCount (self)`
*   `scrollToItem (self, QTableWidgetItem item, QAbstractItemView.ScrollHint hint = QAbstractItemView.EnsureVisible)`
*   `list-of-QTableWidgetItem selectedItems (self)`
*   `list-of-QTableWidgetSelectionRange selectedRanges (self)`
*   `setCellWidget (self, int row, int column, QWidget widget)`
*   `setColumnCount (self, int columns)`
*   `setCurrentCell (self, int row, int column)`
*   `setCurrentCell (self, int row, int column, QItemSelectionModel.SelectionFlags command)`
*   `setCurrentItem (self, QTableWidgetItem item)`
*   `setCurrentItem (self, QTableWidgetItem item, QItemSelectionModel.SelectionFlags command)`
*   `setHorizontalHeaderItem (self, int column, QTableWidgetItem item)`
*   `setHorizontalHeaderLabels (self, QStringList labels)`
*   `setItem (self, int row, int column, QTableWidgetItem item)`
*   `setItemPrototype (self, QTableWidgetItem item)`
*   `setItemSelected (self, QTableWidgetItem item, bool select)`
*   `setRangeSelected (self, QTableWidgetSelectionRange range, bool select)`
*   `setRowCount (self, int rows)`
*   `setSortingEnabled (self, bool enable)`
*   `setVerticalHeaderItem (self, int row, QTableWidgetItem item)`
*   `setVerticalHeaderLabels (self, QStringList labels)`
*   `sortItems (self, int column, Qt.SortOrder order = Qt.AscendingOrder)`
*   `Qt.DropActions supportedDropActions (self)`
*   `QTableWidgetItem takeHorizontalHeaderItem (self, int column)`
*   `QTableWidgetItem takeItem (self, int row, int column)`
*   `QTableWidgetItem takeVerticalHeaderItem (self, int row)`
*   `QTableWidgetItem verticalHeaderItem (self, int row)`
*   `int visualColumn (self, int logicalColumn)`
*   `QRect visualItemRect (self, QTableWidgetItem item)`
*   `int visualRow (self, int logicalRow)`

### Qt Signals

*   `void cellActivated (int,int)`
*   `void cellChanged (int,int)`
*   `void cellClicked (int,int)`
*   `void cellDoubleClicked (int,int)`
*   `void cellEntered (int,int)`
*   `void cellPressed (int,int)`
*   `void currentCellChanged (int,int,int,int)`
*   `void currentItemChanged (QTableWidgetItem *,QTableWidgetItem *)`
*   `void itemActivated (QTableWidgetItem *)`
*   `void itemChanged (QTableWidgetItem *)`
*   `void itemClicked (QTableWidgetItem *)`
*   `void itemDoubleClicked (QTableWidgetItem *)`
*   `void itemEntered (QTableWidgetItem *)`
*   `void itemPressed (QTableWidgetItem *)`
*   `void itemSelectionChanged ()`

* * *

## Detailed Description

该QTableWidget类提供了默认的模型基于物品的表视图。

表部件提供标准表的显示设备的应用程序。在一个QTableWidget的项目是由提供[QTableWidgetItem](qtablewidgetitem.html)。

如果你想使用自己的数据模型中的表，你应该使用[QTableView](qtableview.html)而不是这个类。

表部件可以用行和列的数目需要构造：

```
     tableWidget = new QTableWidget(12, 3, this);

```

另外，表格可以在不给定大小的构造和调整后：

```
     tableWidget = new QTableWidget(this);
     tableWidget->setRowCount(10);
     tableWidget->setColumnCount(5);

```

项目创建ouside的表（没有父widget ），并插入到表[setItem](qtablewidget.html#setItem)（）：

```
     [QTableWidgetItem](qtablewidgetitem.html) *newItem = new [QTableWidgetItem](qtablewidgetitem.html)(tr("%1").arg(
         (row+1)*(column+1)));
     tableWidget->setItem(row, column, newItem);

```

如果您想要启用表中的小部件整理，这样做你填充了项目后，否则排序与插入顺序可能会影响（见[setItem](qtablewidget.html#setItem)（ ）了解详情） 。

表可以被给定的水平和垂直标头。来创建报头中的最简单的方法是提供一个字符串列表的[setHorizontalHeaderLabels](qtablewidget.html#setHorizontalHeaderLabels)（）和[setVerticalHeaderLabels](qtablewidget.html#setVerticalHeaderLabels)（）函数。这些将提供简单的文本表格的标题的列和行。更复杂的标题可以从通常建造在表外存在的表项被创建。例如，我们可以构造一个表项有一个图标和对齐文本，并把它作为一个特定列的标题：

```
     [QTableWidgetItem](qtablewidgetitem.html) *cubesHeaderItem = new [QTableWidgetItem](qtablewidgetitem.html)(tr("Cubes"));
     cubesHeaderItem->setIcon([QIcon](qicon.html)([QPixmap](qpixmap.html)(":/../img/cubed.png")));
     cubesHeaderItem->setTextAlignment([Qt](qt.html).AlignVCenter);

```

表中的行数可以与发现[rowCount](qtablewidget.html#rowCount-prop)（）和列的数目[columnCount](qtablewidget.html#columnCount-prop)（ ） 。该表可与被清除[clear](qtablewidget.html#clear)（）函数。

| ![Screenshot of a Windows XP style table widget](../img/windowsxp-tableview.png) | ![Screenshot of a Macintosh style table widget](../img/macintosh-tableview.png) | ![Screenshot of a Plastique style table widget](../img/plastique-tableview.png) |
| A [Windows XP style](index.htm) table widget. | A [Macintosh style](index.htm) table widget. | A [Plastique style](index.htm) table widget. |

* * *

## Method Documentation

```
QTableWidget.__init__ (self, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建具有给定一个新的表视图_parent_。

```
QTableWidget.__init__ (self, int rows, int columns, QWidget parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

创建具有给定一个新的表视图_rows_和_columns_，并用给定的_parent_。

```
QWidget QTableWidget.cellWidget (self, int row, int column)
```

[

返回在给定显示在单元格中的插件_row_和_column_。

**Note:**该表采用了小部件的所有权。

这个函数是Qt 4.1中引入。

](qwidget.html)

[**See also**](qwidget.html) [setCellWidget](qtablewidget.html#setCellWidget)（ ） 。

```
QTableWidget.clear (self)
```

这种方法也是一个Qt槽与C + +的签名`void clear()`。

删除所有项目在视图中。这也将删除所有选择。该表的尺寸保持不变。

```
QTableWidget.clearContents (self)
```

这种方法也是一个Qt槽与C + +的签名`void clearContents()`。

删除所有项目不从视图中的标头。这也将删除所有选择。该表的尺寸保持不变。

这个函数中引入了Qt 4.2中。

```
QTableWidget.closePersistentEditor (self, QTableWidgetItem item)
```

关闭执着编辑器_item_。

**See also** [openPersistentEditor](qtablewidget.html#openPersistentEditor)（ ） 。

```
int QTableWidget.column (self, QTableWidgetItem item)
```

返回的列_item_。

```
int QTableWidget.columnCount (self)
```

```
int QTableWidget.currentColumn (self)
```

返回当前项目的列。

**See also** [currentRow](qtablewidget.html#currentRow)（）和[setCurrentCell](qtablewidget.html#setCurrentCell)（ ） 。

```
QTableWidgetItem QTableWidget.currentItem (self)
```

[

返回当前项目。

](qtablewidgetitem.html)

[**See also**](qtablewidgetitem.html) [setCurrentItem](qtablewidget.html#setCurrentItem)（ ） 。

```
int QTableWidget.currentRow (self)
```

返回当前项目的行。

**See also** [currentColumn](qtablewidget.html#currentColumn)（）和[setCurrentCell](qtablewidget.html#setCurrentCell)（ ） 。

```
QTableWidget.dropEvent (self, QDropEvent event)
```

从重新实现[QWidget.dropEvent](qwidget.html#dropEvent)（ ） 。

```
bool QTableWidget.dropMimeData (self, int row, int column, QMimeData data, Qt.DropAction action)
```

处理_data_通过拖放操作，与给定的供给结束_action_在给定的_row_和_column_。返回True如果数据和动作可以通过模型来处理，否则返回False 。

**See also** [supportedDropActions](qtablewidget.html#supportedDropActions)（ ） 。

```
QTableWidget.editItem (self, QTableWidgetItem item)
```

开始编辑_item_如果是可编辑的。

```
bool QTableWidget.event (self, QEvent e)
```

从重新实现[QObject.event](qobject.html#event)（ ） 。

```
list-of-QTableWidgetItem QTableWidget.findItems (self, QString text, Qt.MatchFlags flags)
```

找到符合的项目_text_使用给定的_flags_。

```
QTableWidgetItem QTableWidget.horizontalHeaderItem (self, int column)
```

[

返回列的水平标题项，_column_，如果已设定，否则返回0 。

](qtablewidgetitem.html)

[**See also**](qtablewidgetitem.html) [setHorizontalHeaderItem](qtablewidget.html#setHorizontalHeaderItem)（ ） 。

```
QModelIndex QTableWidget.indexFromItem (self, QTableWidgetItem item)
```

[](qmodelindex.html)

[返回](qmodelindex.html)[QModelIndex](qmodelindex.html)assocated用给定的_item_。

```
QTableWidget.insertColumn (self, int column)
```

这种方法也是一个Qt槽与C + +的签名`void insertColumn(int)`。

插入一个空列到表中_column_。

```
QTableWidget.insertRow (self, int row)
```

这种方法也是一个Qt槽与C + +的签名`void insertRow(int)`。

插入一个空行到表中_row_。

```
bool QTableWidget.isItemSelected (self, QTableWidgetItem item)
```

```
bool QTableWidget.isSortingEnabled (self)
```

```
QTableWidgetItem QTableWidget.item (self, int row, int column)
```

[

返回的项目为给定的_row_和_column_如果已经设置，否则返回0 。

](qtablewidgetitem.html)

[**See also**](qtablewidgetitem.html) [setItem](qtablewidget.html#setItem)（ ） 。

```
QTableWidgetItem QTableWidget.itemAt (self, QPoint p)
```

[

返回一个指向该项目在给定的_point_，或返回0，如果_point_未在表格部件所复盖的项目。

](qtablewidgetitem.html)

[**See also**](qtablewidgetitem.html) [item](qtablewidget.html#item)（ ） 。

```
QTableWidgetItem QTableWidget.itemAt (self, int ax, int ay)
```

[](qtablewidgetitem.html)

[返回以相等于位置的项目](qtablewidgetitem.html)[QPoint](qpoint.html)（_ax_，_ay_）表格部件的坐标系中，或者指定的点是不是在表部件有相应的项目返回0 。

**See also** [item](qtablewidget.html#item)（ ） 。

```
QTableWidgetItem QTableWidget.itemFromIndex (self, QModelIndex index)
```

[](qtablewidgetitem.html)

[返回一个指针](qtablewidgetitem.html)[QTableWidgetItem](qtablewidgetitem.html)assocated用给定的_index_。

```
QTableWidgetItem QTableWidget.itemPrototype (self)
```

[

返回产品原型所使用的表。

](qtablewidgetitem.html)

[**See also**](qtablewidgetitem.html) [setItemPrototype](qtablewidget.html#setItemPrototype)（ ） 。

```
list-of-QTableWidgetItem QTableWidget.items (self, QMimeData data)
```

返回指针的列表，包含在该项目_data_对象。如果对象不是由创建[QTreeWidget](qtreewidget.html)在同一过程中，该列表是空的。

```
QMimeData QTableWidget.mimeData (self, list-of-QTableWidgetItem items)
```

[

该_QMimeData_结果

](qmimedata.html)

[返回一个对象，该对象包含指定的序列化描述_items_。用于描述的项目的格式是从所获得的](qmimedata.html)[mimeTypes](qtablewidget.html#mimeTypes)（）函数。

如果项目列表为空，则返回0 ，而不是一个序列化的空单。

```
QStringList QTableWidget.mimeTypes (self)
```

返回可用于描述tablewidget项目清单的MIME类型的列表。

**See also** [mimeData](qtablewidget.html#mimeData)（ ） 。

```
QTableWidget.openPersistentEditor (self, QTableWidgetItem item)
```

打开一个编辑器的给予_item_。该编辑器编辑后仍保持打开状态。

**See also** [closePersistentEditor](qtablewidget.html#closePersistentEditor)（ ） 。

```
QTableWidget.removeCellWidget (self, int arow, int acolumn)
```

删除小部件所指示的单元格设置_row_和_column_。

此功能被引入Qt的4.3 。

```
QTableWidget.removeColumn (self, int column)
```

这种方法也是一个Qt槽与C + +的签名`void removeColumn(int)`。

删除列_column_和从表中的所有项目。

```
QTableWidget.removeRow (self, int row)
```

这种方法也是一个Qt槽与C + +的签名`void removeRow(int)`。

删除的行_row_和从表中的所有项目。

```
int QTableWidget.row (self, QTableWidgetItem item)
```

返回该行的_item_。

```
int QTableWidget.rowCount (self)
```

```
QTableWidget.scrollToItem (self, QTableWidgetItem item, QAbstractItemView.ScrollHint hint = QAbstractItemView.EnsureVisible)
```

这种方法也是一个Qt槽与C + +的签名`void scrollToItem(const QTableWidgetItem *,QAbstractItemView::ScrollHint = QAbstractItemView.EnsureVisible)`。

滚动的视图，如果必要，以确保_item_是可见的。该_hint_参数指定更精确的地方_item_应设在手术后。

```
list-of-QTableWidgetItem QTableWidget.selectedItems (self)
```

返回所有选定项的列表。

这个函数返回一个指针列表，选中单元格的内容。使用[selectedIndexes](qtableview.html#selectedIndexes)（ ）函数来获取完整的选择_including_空单元格。

**See also** [selectedIndexes](qtableview.html#selectedIndexes)（ ） 。

```
list-of-QTableWidgetSelectionRange QTableWidget.selectedRanges (self)
```

返回所有选定范围的列表。

**See also** [QTableWidgetSelectionRange](qtablewidgetselectionrange.html)。

```
QTableWidget.setCellWidget (self, int row, int column, QWidget widget)
```

该_widget_说法有它的所有权转移给Qt的。

设置给定_widget_在给定的要被显示在单元格中_row_和_column_，通过widget的所有权表。

如果电池部件A被替换电池部件B，细胞小部件A将被删除。例如，下面的代码片段中，[QLineEdit](qlineedit.html)对象将被删除。

```
 setCellWidget(index, new [QLineEdit](qlineedit.html));
 ...
 setCellWidget(index, new [QTextEdit](qtextedit.html));

```

这个函数是Qt 4.1中引入。

**See also** [cellWidget](qtablewidget.html#cellWidget)（ ） 。

```
QTableWidget.setColumnCount (self, int columns)
```

```
QTableWidget.setCurrentCell (self, int row, int column)
```

将当前单元格是在位置的单元格（_row_，_column_） 。

根据当前的[selection mode](qabstractitemview.html#SelectionMode-enum)中，细胞也可能被选中。

这个函数是Qt 4.1中引入。

**See also** [setCurrentItem](qtablewidget.html#setCurrentItem)（ ）[currentRow](qtablewidget.html#currentRow)（）和[currentColumn](qtablewidget.html#currentColumn)（ ） 。

```
QTableWidget.setCurrentCell (self, int row, int column, QItemSelectionModel.SelectionFlags command)
```

将当前单元格是在位置的单元格（_row_，_column_） ，使用给定的_command_。

此功能被引入Qt的4.4 。

**See also** [setCurrentItem](qtablewidget.html#setCurrentItem)（ ）[currentRow](qtablewidget.html#currentRow)（）和[currentColumn](qtablewidget.html#currentColumn)（ ） 。

```
QTableWidget.setCurrentItem (self, QTableWidgetItem item)
```

设置当前项目_item_。

除非选择模式为[NoSelection](qabstractitemview.html#SelectionMode-enum)时，该项目也被选中。

**See also** [currentItem](qtablewidget.html#currentItem)（）和[setCurrentCell](qtablewidget.html#setCurrentCell)（ ） 。

```
QTableWidget.setCurrentItem (self, QTableWidgetItem item, QItemSelectionModel.SelectionFlags command)
```

设置当前项目是_item_，使用给定的_command_。

此功能被引入Qt的4.4 。

**See also** [currentItem](qtablewidget.html#currentItem)（）和[setCurrentCell](qtablewidget.html#setCurrentCell)（ ） 。

```
QTableWidget.setHorizontalHeaderItem (self, int column, QTableWidgetItem item)
```

该_item_说法有它的所有权转移给Qt的。

设置列的水平标题的项目_column_至_item_。

**See also** [horizontalHeaderItem](qtablewidget.html#horizontalHeaderItem)（ ） 。

```
QTableWidget.setHorizontalHeaderLabels (self, QStringList labels)
```

设置使用水平标题标籤_labels_。

```
QTableWidget.setItem (self, int row, int column, QTableWidgetItem item)
```

该_item_说法有它的所有权转移给Qt的。

设置项对于给定的_row_和_column_至_item_。

该表采用了项目的所有权。

请注意，如果排序是启用（见[sortingEnabled](qtableview.html#sortingEnabled-prop)）和_column_是当前排序列中，_row_将被移动到所确定的排序位置_item_。

如果你想（在一个循环中说，通过调用SetItem使用（ ） ）设置一个特定行的几个项目，你可能想关闭在这样做之前排序，并重新开启之后，这将允许您使用相同的_row_参数为同一行中的所有项目（即SetItem使用（ ）将不会移动的行） 。

**See also** [item](qtablewidget.html#item)（）和[takeItem](qtablewidget.html#takeItem)（ ） 。

```
QTableWidget.setItemPrototype (self, QTableWidgetItem item)
```

该_item_说法有它的所有权转移给Qt的。

设置项原型的表的指定的_item_。

该表部件将使用的项目原型克隆功能，当它需要创建一个新的表项。例如，当用户在编辑一个空单元格。当你有这是一个非常有用[QTableWidgetItem](qtablewidgetitem.html)子类，并希望确保[QTableWidget](qtablewidget.html)创建你的子类的实例。

该表采用了原型的所有权。

**See also** [itemPrototype](qtablewidget.html#itemPrototype)（ ） 。

```
QTableWidget.setItemSelected (self, QTableWidgetItem item, bool select)
```

```
QTableWidget.setRangeSelected (self, QTableWidgetSelectionRange range, bool select)
```

选择或取消选择_range_根据_select_。

```
QTableWidget.setRowCount (self, int rows)
```

```
QTableWidget.setSortingEnabled (self, bool enable)
```

```
QTableWidget.setVerticalHeaderItem (self, int row, QTableWidgetItem item)
```

该_item_说法有它的所有权转移给Qt的。

设置为行的垂直标题项_row_至_item_。

**See also** [verticalHeaderItem](qtablewidget.html#verticalHeaderItem)（ ） 。

```
QTableWidget.setVerticalHeaderLabels (self, QStringList labels)
```

设置使用垂直标题标籤_labels_。

```
QTableWidget.sortItems (self, int column, Qt.SortOrder order = Qt.AscendingOrder)
```

排序表中的小部件中的所有行的基础上_column_和_order_。

```
Qt.DropActions QTableWidget.supportedDropActions (self)
```

[

返回此视图支持的放置动作。

](index.htm)

[**See also**](index.htm) [Qt.DropActions](qt.html#DropAction-enum)。

```
QTableWidgetItem QTableWidget.takeHorizontalHeaderItem (self, int column)
```

[

该_QTableWidgetItem_结果

删除在水平标题项_column_从而不删除它的头。

这个函数是Qt 4.1中引入。

](qtablewidgetitem.html)

```
QTableWidgetItem QTableWidget.takeItem (self, int row, int column)
```

[

该_QTableWidgetItem_结果

在删除的项目_row_和_column_从表而不删除它。

](qtablewidgetitem.html)

```
QTableWidgetItem QTableWidget.takeVerticalHeaderItem (self, int row)
```

[

该_QTableWidgetItem_结果

删除在垂直标题项_row_从而不删除它的头。

这个函数是Qt 4.1中引入。

](qtablewidgetitem.html)

```
QTableWidgetItem QTableWidget.verticalHeaderItem (self, int row)
```

[

返回行的垂直标题项_row_。

](qtablewidgetitem.html)

[**See also**](qtablewidgetitem.html) [setVerticalHeaderItem](qtablewidget.html#setVerticalHeaderItem)（ ） 。

```
int QTableWidget.visualColumn (self, int logicalColumn)
```

返回给定的可视列_logicalColumn_。

```
QRect QTableWidget.visualItemRect (self, QTableWidgetItem item)
```

[

返回矩形上通过了该项目所佔用的视_item_。

```
int QTableWidget.visualRow (self, int logicalRow)
```

返回给定的可视化排_logicalRow_。

* * *

## Qt Signal Documentation

```
void cellActivated (int,int)
```

这是该信号的默认超载。

当指定由小区这个信号被发射_row_和_column_已激活

这个函数是Qt 4.1中引入。

```
void cellChanged (int,int)
```

这是该信号的默认超载。

每当该项目的单元格中的数据通过指定这个信号被发射_row_和_column_已经改变。

这个函数是Qt 4.1中引入。

```
void cellClicked (int,int)
```

这是该信号的默认超载。

每当在表中的单元格被点击这个信号被发射。该_row_和_column_指定是被单击的单元格。

这个函数是Qt 4.1中引入。

```
void cellDoubleClicked (int,int)
```

这是该信号的默认超载。

这个信号被发射时在表中的单元格被双点击。该_row_和_column_指定是被双击时的电池。

这个函数是Qt 4.1中引入。

```
void cellEntered (int,int)
```

这是该信号的默认超载。

当鼠标光标进入细胞这个信号被发射。被指定的小区_row_和_column_。

](qrect.html)

[这个信号只发射时](qrect.html)[mouseTracking](qwidget.html#mouseTracking-prop)被接通时，或者当在移动到一个产品上，按下鼠标按钮。

这个函数是Qt 4.1中引入。

```
void cellPressed (int,int)
```

这是该信号的默认超载。

每当在表中的单元格被按下时，这个信号被发射。该_row_和_column_指定的是被按下的细胞。

这个函数是Qt 4.1中引入。

```
void currentCellChanged (int,int,int,int)
```

这是该信号的默认超载。

这个信号被发射时当前单元格的变化。由指定的小区_previousRow_和_previousColumn_是，以前有焦点的单元格，指定的单元格_currentRow_和_currentColumn_是新的当前单元格。

这个函数是Qt 4.1中引入。

```
void currentItemChanged (QTableWidgetItem *,QTableWidgetItem *)
```

这是该信号的默认超载。

这个信号被发射时的当前项的变化。该_previous_产品以前具有焦点的项目，_current_是新的当前项。

```
void itemActivated (QTableWidgetItem *)
```

这是该信号的默认超载。

指定时，这个信号被发射_item_已激活

```
void itemChanged (QTableWidgetItem *)
```

这是该信号的默认超载。

这个信号被发射时的数据_item_已经改变。

```
void itemClicked (QTableWidgetItem *)
```

这是该信号的默认超载。

每当表格中的项被点击这个信号被发射。该_item_指定是被单击的项目。

```
void itemDoubleClicked (QTableWidgetItem *)
```

这是该信号的默认超载。

这个信号被发射时表格中的项目被双击时。该_item_指定是被双击了项目。

```
void itemEntered (QTableWidgetItem *)
```

这是该信号的默认超载。

当鼠标光标进入一个项目，这个信号被发射。该_item_在该项目进入。

这个信号只发射时[mouseTracking](qwidget.html#mouseTracking-prop)被接通时，或者当在移动到一个产品上，按下鼠标按钮。

```
void itemPressed (QTableWidgetItem *)
```

这是该信号的默认超载。

每当在表中的项目被按下​​这个信号被发射。该_item_指定的是被按下的项目。

```
void itemSelectionChanged ()
```

这是该信号的默认超载。

这个信号被发射时的选择改变。

**See also** [selectedItems](qtablewidget.html#selectedItems)（）和[QTableWidgetItem.isSelected](qtablewidgetitem.html#isSelected)（ ） 。