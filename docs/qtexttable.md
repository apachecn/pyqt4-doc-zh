# QTextTable Class Reference

## [[QtGui](index.htm) module]

该QTextTable类表示一个表[QTextDocument](qtextdocument.html)。[More...](#details)

继承[QTextFrame](qtextframe.html)。

### Methods

*   `__init__ (self, QTextDocument doc)`
*   `appendColumns (self, int count)`
*   `appendRows (self, int count)`
*   `QTextTableCell cellAt (self, int row, int col)`
*   `QTextTableCell cellAt (self, int position)`
*   `QTextTableCell cellAt (self, QTextCursor c)`
*   `int columns (self)`
*   `QTextTableFormat format (self)`
*   `insertColumns (self, int pos, int num)`
*   `insertRows (self, int pos, int num)`
*   `mergeCells (self, int row, int col, int numRows, int numCols)`
*   `mergeCells (self, QTextCursor cursor)`
*   `removeColumns (self, int pos, int num)`
*   `removeRows (self, int pos, int num)`
*   `resize (self, int rows, int cols)`
*   `QTextCursor rowEnd (self, QTextCursor c)`
*   `int rows (self)`
*   `QTextCursor rowStart (self, QTextCursor c)`
*   `setFormat (self, QTextTableFormat aformat)`
*   `splitCell (self, int row, int col, int numRows, int numCols)`

* * *

## Detailed Description

该QTextTable类表示一个表[QTextDocument](qtextdocument.html)。

表是一组细胞有序的行和列。每个表包含至少一行和一列。每个小区包含一个块，并且是由一个帧所包围。

表通常被创建和插入到与一个文件[QTextCursor.insertTable](qtextcursor.html#insertTable)（）函数。例如，我们可以使用下面的代码行在编辑器中当前光标位置插入一个表格三行两列：

```
     [QTextCursor](qtextcursor.html) cursor(editor->textCursor());
     cursor.movePosition([QTextCursor](qtextcursor.html).Start);

     QTextTable *table = cursor.insertTable(rows, columns, tableFormat);

```

在创建或更新版本改变时，该表与表格式要么是定义[setFormat](qtexttable.html#setFormat)（ ） 。

当前正在编辑光标找到该表与[QTextCursor.currentTable](qtextcursor.html#currentTable)（ ） 。这使得它的格式或尺寸后，它已经被插入到一个文件被改变。

一个表的大小可以用改变[resize](qtexttable.html#resize)（） ，或者通过使用[insertRows](qtexttable.html#insertRows)（ ）[insertColumns](qtexttable.html#insertColumns)（ ）[removeRows](qtexttable.html#removeRows)（） ，或[removeColumns](qtexttable.html#removeColumns)（ ） 。使用[cellAt](qtexttable.html#cellAt)（ ）来检索表格单元格。

表行的起始位置和结束位置可以通过移动光标在表内，并使用被发现[rowStart](qtexttable.html#rowStart)（）和[rowEnd](qtexttable.html#rowEnd)（ ）函数的开始和每一行的末端，获得游标。

一个QTextTable内的行和列可以进行合并和拆分使用的[mergeCells](qtexttable.html#mergeCells)（）和[splitCell](qtexttable.html#splitCell)（）函数。然而，只有跨越多个行或列的单元可以拆分。 （合并或拆分不增加或减少的行数和列数。 ）

请注意，如果你已经合并了多个列和行到一个单元格，你将无法在合并单元格拆分成跨越多个行或列新的细胞。为了能够拆分单元格跨越了你需要这样做了几个迭代若干行和列。

| ![Original Table](../img/texttable-split.png) | Suppose we have a 2x3 table of names and addresses. To merge both columns in the first row we invoke [mergeCells](qtexttable.html#mergeCells)() with _row_ = 0, _column_ = 0, _numRows_ = 1 and _numColumns_ = 2.

```
     table-&gt;mergeCells(0, 0, 1, 2);

```

 |
| ![](../img/texttable-merge.png) | This gives us the following table. To split the first row of the table back into two cells, we invoke the [splitCell](qtexttable.html#splitCell)() function with _numRows_ and _numCols_ = 1.

```
     table-&gt;splitCell(0, 0, 1, 1);

```

 |
| ![Split Table](../img/texttable-split.png) | This results in the original table. |

* * *

## Method Documentation

```
QTextTable.__init__ (self, QTextDocument doc)
```

```
QTextTable.appendColumns (self, int count)
```

追加可_count_列的右侧的表。

此功能被引入Qt的4.5 。

**See also** [insertColumns](qtexttable.html#insertColumns)（ ）[insertRows](qtexttable.html#insertRows)（ ）[resize](qtexttable.html#resize)（ ）[removeRows](qtexttable.html#removeRows)（ ）[removeColumns](qtexttable.html#removeColumns)（）和[appendRows](qtexttable.html#appendRows)（ ） 。

```
QTextTable.appendRows (self, int count)
```

追加可_count_行于该表的底部。

此功能被引入Qt的4.5 。

**See also** [insertColumns](qtexttable.html#insertColumns)（ ）[insertRows](qtexttable.html#insertRows)（ ）[resize](qtexttable.html#resize)（ ）[removeRows](qtexttable.html#removeRows)（ ）[removeColumns](qtexttable.html#removeColumns)（）和[appendColumns](qtexttable.html#appendColumns)（ ） 。

```
QTextTableCell QTextTable.cellAt (self, int row, int col)
```

[

返回表格单元在给定的_row_和_column_在表中。

](qtexttablecell.html)

[**See also**](qtexttablecell.html) [columns](qtexttable.html#columns)（）和[rows](qtexttable.html#rows)（ ） 。

```
QTextTableCell QTextTable.cellAt (self, int position)
```

[

这是一个重载函数。

返回包含字符在给定的表格单元格_position_在文档中。

](qtexttablecell.html)

```
QTextTableCell QTextTable.cellAt (self, QTextCursor c)
```

[

这是一个重载函数。

返回包含给定的表格单元格_cursor_。

```
int QTextTable.columns (self)
```

返回的列在表中的编号。

](qtexttablecell.html)

[**See also**](qtexttablecell.html) [rows](qtexttable.html#rows)（ ） 。

```
QTextTableFormat QTextTable.format (self)
```

[

返回表的格式。

](qtexttableformat.html)

[**See also**](qtexttableformat.html) [setFormat](qtexttable.html#setFormat)（ ） 。

```
QTextTable.insertColumns (self, int pos, int num)
```

插入一个编号的_columns_与指定的列前_index_。

**See also** [insertRows](qtexttable.html#insertRows)（ ）[resize](qtexttable.html#resize)（ ）[removeRows](qtexttable.html#removeRows)（ ）[removeColumns](qtexttable.html#removeColumns)（ ）[appendRows](qtexttable.html#appendRows)（）和[appendColumns](qtexttable.html#appendColumns)（ ） 。

```
QTextTable.insertRows (self, int pos, int num)
```

插入一个编号的_rows_具有指定的行之前_index_。

**See also** [resize](qtexttable.html#resize)（ ）[insertColumns](qtexttable.html#insertColumns)（ ）[removeRows](qtexttable.html#removeRows)（ ）[removeColumns](qtexttable.html#removeColumns)（ ）[appendRows](qtexttable.html#appendRows)（）和[appendColumns](qtexttable.html#appendColumns)（ ） 。

```
QTextTable.mergeCells (self, int row, int col, int numRows, int numCols)
```

合并的单元格中的指定_row_和_column_与相邻的细胞进入一个小区。新的细胞将跨越_numRows_行和_numCols_列。如果_numRows_ or _numCols_小于行或列的单元格跨越的当前数目，则此方法不执行任何操作。

这个函数是Qt 4.1中引入。

**See also** [splitCell](qtexttable.html#splitCell)（ ） 。

```
QTextTable.mergeCells (self, QTextCursor cursor)
```

这是一个重载函数。

合并由提供选择的单元_cursor_。

这个函数是Qt 4.1中引入。

**See also** [splitCell](qtexttable.html#splitCell)（ ） 。

```
QTextTable.removeColumns (self, int pos, int num)
```

除去了一些_columns_开始在指定的列_index_。

**See also** [insertRows](qtexttable.html#insertRows)（ ）[insertColumns](qtexttable.html#insertColumns)（ ）[removeRows](qtexttable.html#removeRows)（ ）[resize](qtexttable.html#resize)（ ）[appendRows](qtexttable.html#appendRows)（）和[appendColumns](qtexttable.html#appendColumns)（ ） 。

```
QTextTable.removeRows (self, int pos, int num)
```

除去了一些_rows_开始的行中的指定_index_。

**See also** [insertRows](qtexttable.html#insertRows)（ ）[insertColumns](qtexttable.html#insertColumns)（ ）[resize](qtexttable.html#resize)（ ）[removeColumns](qtexttable.html#removeColumns)（ ）[appendRows](qtexttable.html#appendRows)（）和[appendColumns](qtexttable.html#appendColumns)（ ） 。

```
QTextTable.resize (self, int rows, int cols)
```

调整大小的表包含所需数量的_rows_和_columns_。

**See also** [insertRows](qtexttable.html#insertRows)（ ）[insertColumns](qtexttable.html#insertColumns)（ ）[removeRows](qtexttable.html#removeRows)（）和[removeColumns](qtexttable.html#removeColumns)（ ） 。

```
QTextCursor QTextTable.rowEnd (self, QTextCursor c)
```

[

返回一个指针指向该行的末尾包含给定_cursor_。

](qtextcursor.html)

[**See also**](qtextcursor.html) [rowStart](qtexttable.html#rowStart)（ ） 。

```
int QTextTable.rows (self)
```

返回行的表的数目。

**See also** [columns](qtexttable.html#columns)（ ） 。

```
QTextCursor QTextTable.rowStart (self, QTextCursor c)
```

[

返回一个指针指向该行的开始，包含给定的_cursor_。

](qtextcursor.html)

[**See also**](qtextcursor.html) [rowEnd](qtexttable.html#rowEnd)（ ） 。

```
QTextTable.setFormat (self, QTextTableFormat aformat)
```

设置表的_format_。

**See also** [format](qtexttable.html#format)（ ） 。

```
QTextTable.splitCell (self, int row, int col, int numRows, int numCols)
```

拆分在指定的单元格_row_和_column_成多个细胞与指定尺寸的数组_numRows_和_numCols_。

**Note:**这是唯一可能的分裂跨越多行或多列的细胞，如已使用合并的行[mergeCells](qtexttable.html#mergeCells)（ ） 。

这个函数是Qt 4.1中引入。

**See also** [mergeCells](qtexttable.html#mergeCells)（ ） 。