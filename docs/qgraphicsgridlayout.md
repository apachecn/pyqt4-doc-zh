# QGraphicsGridLayout Class Reference

## [[QtGui](index.htm) module]

该QGraphicsGridLayout类提供了在图形视图管理部件网格布局。[More...](#details)

继承[QGraphicsLayout](qgraphicslayout.html)。

### Methods

*   `__init__ (self, QGraphicsLayoutItem parent = None)`
*   `addItem (self, QGraphicsLayoutItem item, int row, int column, int rowSpan, int columnSpan, Qt.Alignment alignment = 0)`
*   `addItem (self, QGraphicsLayoutItem aitem, int arow, int acolumn, Qt.Alignment alignment = 0)`
*   `Qt.Alignment alignment (self, QGraphicsLayoutItem item)`
*   `Qt.Alignment columnAlignment (self, int column)`
*   `int columnCount (self)`
*   `float columnMaximumWidth (self, int column)`
*   `float columnMinimumWidth (self, int column)`
*   `float columnPreferredWidth (self, int column)`
*   `float columnSpacing (self, int column)`
*   `int columnStretchFactor (self, int column)`
*   `int count (self)`
*   `float horizontalSpacing (self)`
*   `invalidate (self)`
*   `QGraphicsLayoutItem itemAt (self, int row, int column)`
*   `QGraphicsLayoutItem itemAt (self, int index)`
*   `removeAt (self, int index)`
*   `removeItem (self, QGraphicsLayoutItem item)`
*   `Qt.Alignment rowAlignment (self, int row)`
*   `int rowCount (self)`
*   `float rowMaximumHeight (self, int row)`
*   `float rowMinimumHeight (self, int row)`
*   `float rowPreferredHeight (self, int row)`
*   `float rowSpacing (self, int row)`
*   `int rowStretchFactor (self, int row)`
*   `setAlignment (self, QGraphicsLayoutItem item, Qt.Alignment alignment)`
*   `setColumnAlignment (self, int column, Qt.Alignment alignment)`
*   `setColumnFixedWidth (self, int column, float width)`
*   `setColumnMaximumWidth (self, int column, float width)`
*   `setColumnMinimumWidth (self, int column, float width)`
*   `setColumnPreferredWidth (self, int column, float width)`
*   `setColumnSpacing (self, int column, float spacing)`
*   `setColumnStretchFactor (self, int column, int stretch)`
*   `setGeometry (self, QRectF rect)`
*   `setHorizontalSpacing (self, float spacing)`
*   `setRowAlignment (self, int row, Qt.Alignment alignment)`
*   `setRowFixedHeight (self, int row, float height)`
*   `setRowMaximumHeight (self, int row, float height)`
*   `setRowMinimumHeight (self, int row, float height)`
*   `setRowPreferredHeight (self, int row, float height)`
*   `setRowSpacing (self, int row, float spacing)`
*   `setRowStretchFactor (self, int row, int stretch)`
*   `setSpacing (self, float spacing)`
*   `setVerticalSpacing (self, float spacing)`
*   `QSizeF sizeHint (self, Qt.SizeHint which, QSizeF constraint = QSizeF())`
*   `float verticalSpacing (self)`

* * *

## Detailed Description

该QGraphicsGridLayout类提供了在图形视图管理部件网格布局。

使用QGraphicsGridLayout最常用的方法是通过调用构造一个对象在堆中，没有父母，添加控件和布局[addItem](qgraphicsgridlayout.html#addItem)（） ，最后是布局呼叫分配给一个小部件[QGraphicsWidget.setLayout](qgraphicswidget.html#layout-prop)（ ） 。当您添加的项目QGraphicsGridLayout自动计算网格的尺寸。

```
 [QGraphicsScene](qgraphicsscene.html) scene;
 [QGraphicsWidget](qgraphicswidget.html) *textEdit = scene.addWidget(new [QTextEdit](qtextedit.html));
 [QGraphicsWidget](qgraphicswidget.html) *pushButton = scene.addWidget(new [QPushButton](qpushbutton.html));

 QGraphicsGridLayout *layout = new QGraphicsGridLayout;
 layout->addItem(textEdit, 0, 0);
 layout->addItem(pushButton, 0, 1);

 [QGraphicsWidget](qgraphicswidget.html) *form = new [QGraphicsWidget](qgraphicswidget.html);
 form->setLayout(layout);
 scene.addItem(form);

```

布局需要的物品的所有权。在某些情况下，当项目的布局也继承自[QGraphicsItem](qgraphicsitem.html)（如[QGraphicsWidget](qgraphicswidget.html)）会有因为布局项目属于两个层次的所有权所有权的模糊性。看到的文档[QGraphicsLayoutItem.setOwnedByLayout](qgraphicslayoutitem.html#setOwnedByLayout)（ ）如何处理这个问题。你可以通过调用访问布局每个项目[count](qgraphicsgridlayout.html#count)（）和[itemAt](qgraphicsgridlayout.html#itemAt)（ ） 。调用[removeAt](qgraphicsgridlayout.html#removeAt)（ ）会从布局中删除某个项目，而不破坏它。

### Size Hints and Size Policies in QGraphicsGridLayout

QGraphicsGridLayout尊重每个项目的大小提示和大小政策，并在网格中的一个单元格有更多的空间比项目可以填写，每个项目是根据该项目的布局的对齐方式排列。你可以通过调用设置每个项目的对齐方式[setAlignment](qgraphicsgridlayout.html#setAlignment)（ ） ，并通过调用检查对齐任何项目[alignment](qgraphicsgridlayout.html#alignment)（ ） 。您也可以通过调用设置的对齐方式为整个行或列[setRowAlignment](qgraphicsgridlayout.html#setRowAlignment)（）和[setColumnAlignment](qgraphicsgridlayout.html#setColumnAlignment)（ ）分别。默认情况下，项目是一致的左上角。

* * *

## Method Documentation

```
QGraphicsGridLayout.__init__ (self, QGraphicsLayoutItem parent = None)
```

该_parent_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

构造一个[QGraphicsGridLayout](qgraphicsgridlayout.html)实例。_parent_被传递给[QGraphicsLayout](qgraphicslayout.html)的构造。

```
QGraphicsGridLayout.addItem (self, QGraphicsLayoutItem item, int row, int column, int rowSpan, int columnSpan, Qt.Alignment alignment = 0)
```

该_item_说法有它的所有权转移给Qt的。

添加_item_到网格上_row_和_column_。您可以指定一个_rowSpan_和_columnSpan_和可选的_alignment_。

```
QGraphicsGridLayout.addItem (self, QGraphicsLayoutItem aitem, int arow, int acolumn, Qt.Alignment alignment = 0)
```

该_aitem_的说法，如果不是没有，原因_self_通过Qt的，而不是PyQt的拥有。

添加_item_到网格上_row_和_column_。您可以指定一个可选的_alignment_为_item_。

```
Qt.Alignment QGraphicsGridLayout.alignment (self, QGraphicsLayoutItem item)
```

[

返回对齐_item_。

](index.htm)

[**See also**](index.htm) [setAlignment](qgraphicsgridlayout.html#setAlignment)（ ） 。

```
Qt.Alignment QGraphicsGridLayout.columnAlignment (self, int column)
```

[

返回对齐_column_。

](index.htm)

[**See also**](index.htm) [setColumnAlignment](qgraphicsgridlayout.html#setColumnAlignment)（ ） 。

```
int QGraphicsGridLayout.columnCount (self)
```

返回列的网格布局的数目。这总是比由布局项目佔据的最后一列的索引多一个（空列计数除了那些在最后） 。

```
float QGraphicsGridLayout.columnMaximumWidth (self, int column)
```

返回的最大宽度_column_。

**See also** [setColumnMaximumWidth](qgraphicsgridlayout.html#setColumnMaximumWidth)（ ） 。

```
float QGraphicsGridLayout.columnMinimumWidth (self, int column)
```

返回的最小宽度_column_。

**See also** [setColumnMinimumWidth](qgraphicsgridlayout.html#setColumnMinimumWidth)（ ） 。

```
float QGraphicsGridLayout.columnPreferredWidth (self, int column)
```

返回首选宽度_column_。

**See also** [setColumnPreferredWidth](qgraphicsgridlayout.html#setColumnPreferredWidth)（ ） 。

```
float QGraphicsGridLayout.columnSpacing (self, int column)
```

返回列间距_column_。

**See also** [setColumnSpacing](qgraphicsgridlayout.html#setColumnSpacing)（ ） 。

```
int QGraphicsGridLayout.columnStretchFactor (self, int column)
```

返回的拉伸因子_column_。

**See also** [setColumnStretchFactor](qgraphicsgridlayout.html#setColumnStretchFactor)（ ） 。

```
int QGraphicsGridLayout.count (self)
```

从重新实现[QGraphicsLayout.count](qgraphicslayout.html#count)（ ） 。

返回布局的项目在此网格布局的数量。

```
float QGraphicsGridLayout.horizontalSpacing (self)
```

返回默认的水平间距的网格布局。

**See also** [setHorizontalSpacing](qgraphicsgridlayout.html#setHorizontalSpacing)（ ） 。

```
QGraphicsGridLayout.invalidate (self)
```

从重新实现[QGraphicsLayout.invalidate](qgraphicslayout.html#invalidate)（ ） 。

```
QGraphicsLayoutItem QGraphicsGridLayout.itemAt (self, int row, int column)
```

[

返回一个指针布局项目时（_row_，_column_） 。

](qgraphicslayoutitem.html)

```
QGraphicsLayoutItem QGraphicsGridLayout.itemAt (self, int index)
```

[](qgraphicslayoutitem.html)

[从重新实现](qgraphicslayoutitem.html)[QGraphicsLayout.itemAt](qgraphicslayout.html#itemAt)（ ） 。

返回位于布局项目_index_，或者0 ，如果没有布局这个项目索引处。

```
QGraphicsGridLayout.removeAt (self, int index)
```

从重新实现[QGraphicsLayout.removeAt](qgraphicslayout.html#removeAt)（ ） 。

删除的项目布局_index_不破坏它。该项目的所有权转移给调用者。

**See also** [addItem](qgraphicsgridlayout.html#addItem)（ ） 。

```
QGraphicsGridLayout.removeItem (self, QGraphicsLayoutItem item)
```

该_item_争论

删除布局项目_item_不破坏它。该项目的所有权转移给调用者。

此功能被引入Qt的4.8 。

**See also** [addItem](qgraphicsgridlayout.html#addItem)（ ） 。

```
Qt.Alignment QGraphicsGridLayout.rowAlignment (self, int row)
```

[

返回的对齐方式_row_。

](index.htm)

[**See also**](index.htm) [setRowAlignment](qgraphicsgridlayout.html#setRowAlignment)（ ） 。

```
int QGraphicsGridLayout.rowCount (self)
```

返回行的网格布局的数量。这总是比由布局项目佔据的最后一行的索引多一个（空的行计数，除了那些在最后） 。

```
float QGraphicsGridLayout.rowMaximumHeight (self, int row)
```

返回的最大高度为行，_row_。

**See also** [setRowMaximumHeight](qgraphicsgridlayout.html#setRowMaximumHeight)（ ） 。

```
float QGraphicsGridLayout.rowMinimumHeight (self, int row)
```

返回的最小高度为行，_row_。

**See also** [setRowMinimumHeight](qgraphicsgridlayout.html#setRowMinimumHeight)（ ） 。

```
float QGraphicsGridLayout.rowPreferredHeight (self, int row)
```

返回该行的首选高度，_row_。

**See also** [setRowPreferredHeight](qgraphicsgridlayout.html#setRowPreferredHeight)（ ） 。

```
float QGraphicsGridLayout.rowSpacing (self, int row)
```

返回的行间距_row_。

**See also** [setRowSpacing](qgraphicsgridlayout.html#setRowSpacing)（ ） 。

```
int QGraphicsGridLayout.rowStretchFactor (self, int row)
```

返回的拉伸因子_row_。

**See also** [setRowStretchFactor](qgraphicsgridlayout.html#setRowStretchFactor)（ ） 。

```
QGraphicsGridLayout.setAlignment (self, QGraphicsLayoutItem item, Qt.Alignment alignment)
```

设置对齐方式_item_至_alignment_。

**See also** [alignment](qgraphicsgridlayout.html#alignment)（ ） 。

```
QGraphicsGridLayout.setColumnAlignment (self, int column, Qt.Alignment alignment)
```

设置对齐方式_column_至_alignment_。

**See also** [columnAlignment](qgraphicsgridlayout.html#columnAlignment)（ ） 。

```
QGraphicsGridLayout.setColumnFixedWidth (self, int column, float width)
```

设置的固定宽度_column_至_width_。

```
QGraphicsGridLayout.setColumnMaximumWidth (self, int column, float width)
```

设定的最大宽度_column_至_width_。

**See also** [columnMaximumWidth](qgraphicsgridlayout.html#columnMaximumWidth)（ ） 。

```
QGraphicsGridLayout.setColumnMinimumWidth (self, int column, float width)
```

设置为最小宽度_column_至_width_。

**See also** [columnMinimumWidth](qgraphicsgridlayout.html#columnMinimumWidth)（ ） 。

```
QGraphicsGridLayout.setColumnPreferredWidth (self, int column, float width)
```

设置为首选宽度_column_至_width_。

**See also** [columnPreferredWidth](qgraphicsgridlayout.html#columnPreferredWidth)（ ） 。

```
QGraphicsGridLayout.setColumnSpacing (self, int column, float spacing)
```

设置间距_column_至_spacing_。

**See also** [columnSpacing](qgraphicsgridlayout.html#columnSpacing)（ ） 。

```
QGraphicsGridLayout.setColumnStretchFactor (self, int column, int stretch)
```

设置为拉伸因子_column_至_stretch_。

**See also** [columnStretchFactor](qgraphicsgridlayout.html#columnStretchFactor)（ ） 。

```
QGraphicsGridLayout.setGeometry (self, QRectF rect)
```

从重新实现[QGraphicsLayoutItem.setGeometry](qgraphicslayoutitem.html#setGeometry)（ ） 。

设置网格布局的边界几何_rect_。

```
QGraphicsGridLayout.setHorizontalSpacing (self, float spacing)
```

设置默认的水平间距网格布局_spacing_。

**See also** [horizontalSpacing](qgraphicsgridlayout.html#horizontalSpacing)（ ） 。

```
QGraphicsGridLayout.setRowAlignment (self, int row, Qt.Alignment alignment)
```

设置的对齐方式_row_至_alignment_。

**See also** [rowAlignment](qgraphicsgridlayout.html#rowAlignment)（ ） 。

```
QGraphicsGridLayout.setRowFixedHeight (self, int row, float height)
```

设置为行的固定高度，_row_，以_height_。

```
QGraphicsGridLayout.setRowMaximumHeight (self, int row, float height)
```

设置最大高度为行，_row_，以_height_。

**See also** [rowMaximumHeight](qgraphicsgridlayout.html#rowMaximumHeight)（ ） 。

```
QGraphicsGridLayout.setRowMinimumHeight (self, int row, float height)
```

设置最小高度为行，_row_，以_height_。

**See also** [rowMinimumHeight](qgraphicsgridlayout.html#rowMinimumHeight)（ ） 。

```
QGraphicsGridLayout.setRowPreferredHeight (self, int row, float height)
```

设置为行的首选高度，_row_，以_height_。

**See also** [rowPreferredHeight](qgraphicsgridlayout.html#rowPreferredHeight)（ ） 。

```
QGraphicsGridLayout.setRowSpacing (self, int row, float spacing)
```

设置间距_row_至_spacing_。

**See also** [rowSpacing](qgraphicsgridlayout.html#rowSpacing)（ ） 。

```
QGraphicsGridLayout.setRowStretchFactor (self, int row, int stretch)
```

设置为拉伸因子_row_至_stretch_。

**See also** [rowStretchFactor](qgraphicsgridlayout.html#rowStretchFactor)（ ） 。

```
QGraphicsGridLayout.setSpacing (self, float spacing)
```

设置网格布局的预设间距，垂直和水平，以_spacing_。

**See also** [rowSpacing](qgraphicsgridlayout.html#rowSpacing)（）和[columnSpacing](qgraphicsgridlayout.html#columnSpacing)（ ） 。

```
QGraphicsGridLayout.setVerticalSpacing (self, float spacing)
```

设置网格布局为默认的垂直间距_spacing_。

**See also** [verticalSpacing](qgraphicsgridlayout.html#verticalSpacing)（ ） 。

```
QSizeF QGraphicsGridLayout.sizeHint (self, Qt.SizeHint which, QSizeF constraint = QSizeF())
```

[](qsizef.html)

[从重新实现](qsizef.html)[QGraphicsLayoutItem.sizeHint](qgraphicslayoutitem.html#sizeHint)（ ） 。

```
float QGraphicsGridLayout.verticalSpacing (self)
```

返回网格布局默认的垂直间距。

**See also** [setVerticalSpacing](qgraphicsgridlayout.html#setVerticalSpacing)（ ） 。