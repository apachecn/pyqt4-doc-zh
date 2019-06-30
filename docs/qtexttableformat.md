# QTextTableFormat Class Reference

## [[QtGui](index.htm) module]

该QTextTableFormat类提供的格式设置信息表[QTextDocument](qtextdocument.html)。[More...](#details)

继承[QTextFrameFormat](qtextframeformat.html)。

### Methods

*   `__init__ (self)`
*   `__init__ (self, QTextTableFormat)`
*   `Qt.Alignment alignment (self)`
*   `float cellPadding (self)`
*   `float cellSpacing (self)`
*   `clearColumnWidthConstraints (self)`
*   `int columns (self)`
*   `list-of-QTextLength columnWidthConstraints (self)`
*   `int headerRowCount (self)`
*   `bool isValid (self)`
*   `setAlignment (self, Qt.Alignment aalignment)`
*   `setCellPadding (self, float apadding)`
*   `setCellSpacing (self, float spacing)`
*   `setColumns (self, int acolumns)`
*   `setColumnWidthConstraints (self, list-of-QTextLength constraints)`
*   `setHeaderRowCount (self, int count)`

* * *

## Detailed Description

该QTextTableFormat类提供的格式设置信息表[QTextDocument](qtextdocument.html)。

表是一组细胞有序的行和列。每个表包含至少一行和一列。每个小区包含一个块。在富文本文档表格使用这个类中定义的属性格式化。

他们的父框架内，根据表中的排列表水平合理。这可以读取的[alignment](qtexttableformat.html#alignment)（ ）函数，并与集[setAlignment](qtexttableformat.html#setAlignment)（ ） 。

在表中的细胞通过细胞间距隔开。细胞之间的像素的数目被设置以[setCellSpacing](qtexttableformat.html#setCellSpacing)（）和read与[cellSpacing](qtexttableformat.html#cellSpacing)（ ） 。每个单元格的内容是由单元格填充包围。每个小区边缘与其内容之间的像素的数目被设置以[setCellPadding](qtexttableformat.html#setCellPadding)（）和read与[cellPadding](qtexttableformat.html#cellPadding)（ ） 。

![](../img/qtexttableformat-cell.png)

表中的背景颜色，可以读取与该[background](qtextformat.html#background)（）函数，并且可以与被指定[setBackground](qtextformat.html#setBackground)（ ） 。每一单元格的背景颜色可以单独设置，并且将控制该填充区域内的单元格的颜色。

表格格式还提供了一种在表中约束的列的宽度。列可以被分配一个固定的宽度，宽度可变，或可用宽度的百分比（见[QTextLength](qtextlength.html)） 。该[columns](qtexttableformat.html#columns)（ ）函数返回一个约束的列数，以及[columnWidthConstraints](qtexttableformat.html#columnWidthConstraints)（ ）函数返回表中定义的约束。这些量也可以通过调用设置[setColumnWidthConstraints](qtexttableformat.html#setColumnWidthConstraints)（）用含有新的约束条件的载体。如果没有限制是必需的，[clearColumnWidthConstraints](qtexttableformat.html#clearColumnWidthConstraints)（ ）可以用来删除它们。

* * *

## Method Documentation

```
QTextTableFormat.__init__ (self)
```

构造一个新的表格式对象。

```
QTextTableFormat.__init__ (self, QTextTableFormat)
```

```
Qt.Alignment QTextTableFormat.alignment (self)
```

[

返回表的对齐方式。

](index.htm)

[**See also**](index.htm) [setAlignment](qtexttableformat.html#setAlignment)（ ） 。

```
float QTextTableFormat.cellPadding (self)
```

返回表的单元格填充。这描述了一种细胞，其内容的边框之间的距离。

**See also** [setCellPadding](qtexttableformat.html#setCellPadding)（ ） 。

```
float QTextTableFormat.cellSpacing (self)
```

返回表的单元格间距。这描述了相邻单元之间的距离。

**See also** [setCellSpacing](qtexttableformat.html#setCellSpacing)（ ） 。

```
QTextTableFormat.clearColumnWidthConstraints (self)
```

清除列宽限制为表。

**See also** [columnWidthConstraints](qtexttableformat.html#columnWidthConstraints)（）和[setColumnWidthConstraints](qtexttableformat.html#setColumnWidthConstraints)（ ） 。

```
int QTextTableFormat.columns (self)
```

返回由表格式中指定的列数。

```
list-of-QTextLength QTextTableFormat.columnWidthConstraints (self)
```

返回使用该表格格式来控制列在一个表中的出现的约束列表。

**See also** [setColumnWidthConstraints](qtexttableformat.html#setColumnWidthConstraints)（ ） 。

```
int QTextTableFormat.headerRowCount (self)
```

返回行的表中的定义的头的数目。

这个函数中引入了Qt 4.2中。

**See also** [setHeaderRowCount](qtexttableformat.html#setHeaderRowCount)（ ） 。

```
bool QTextTableFormat.isValid (self)
```

返回True如果该表格式是有效的，否则返回False 。

```
QTextTableFormat.setAlignment (self, Qt.Alignment aalignment)
```

设置表的_alignment_。

**See also** [alignment](qtexttableformat.html#alignment)（ ） 。

```
QTextTableFormat.setCellPadding (self, float apadding)
```

设置单元格_padding_为表。这决定了细胞和其内容的边框之间的距离。

**See also** [cellPadding](qtexttableformat.html#cellPadding)（ ） 。

```
QTextTableFormat.setCellSpacing (self, float spacing)
```

设置单元格_spacing_为表。这决定了相邻单元之间的距离。

**See also** [cellSpacing](qtexttableformat.html#cellSpacing)（ ） 。

```
QTextTableFormat.setColumns (self, int acolumns)
```

```
QTextTableFormat.setColumnWidthConstraints (self, list-of-QTextLength constraints)
```

设置列宽_constraints_为表。

**See also** [columnWidthConstraints](qtexttableformat.html#columnWidthConstraints)（）和[clearColumnWidthConstraints](qtexttableformat.html#clearColumnWidthConstraints)（ ） 。

```
QTextTableFormat.setHeaderRowCount (self, int count)
```

宣布第一_count_行的表的表头。表格标题行重复得到，当一个表跨越页边界断裂。

这个函数中引入了Qt 4.2中。

**See also** [headerRowCount](qtexttableformat.html#headerRowCount)（ ） 。